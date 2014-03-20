ECE281_Lab3
===========

Elevator Controller Implementation

## Prelab 

### Nexys2_top_shell Schematic

![alt text](pre_lab.jpg "Initial top_shell Schematic")

## Main Lab

### Basic Moore Functionality

[Moore Functionality](http://youtu.be/LDSwDRbXAXY)

### Basic Mealey Functionality

[Mealey Functionality](http://youtu.be/B3NE3ttPqws)

### More Floors

[More Floors Functionality](http://youtu.be/oHlq-hV_Xw4)

### More Inputs

[More Inputs Functionality](http://youtu.be/M-YbjZEz-oM)

### Moving Lights

[Lights Functionality](http://youtu.be/aXaQ48NkGOY)

## Code Critique

### Example 1


#### Bad Code

`if clk'event and clk='1' then`

#### Better Code

`if rising_edge(clk) then`

This is prefered because it's cleaner, more descriptive and the `rising_edge()` function can deal with values other than 0 or 1 better than the bad code. 

### Example 2

#### Bad Code

```
floor_state_machine: process(clk)
```

This process in unnecessarily long and complicated

#### Good Code

```
next_state_logic: process(reset, floor_state, stop)
...
state_memory: process(clk)
```

This method allows you to better keep track of where you are creating memory so you don't accidentaly infer a latch somewhere. The next_state_logic process will need a signal called next_floor_state which will drive floor_state in the state_memory process. Overall this code is much more readable and understandable to the outsider. 

### Documentation

I looked at my fellow students readme to try and figure out which file we were critiquing and not for any specific critiques. I also used [VHDL Best Practices](http://stackoverflow.com/questions/326880/what-are-the-best-practices-for-hardware-description-languages-verilog-vhdl-et) to help me analyze the code for the code critique. Capt Silva helped me get started on the last functionality by generally describing his solution but I never completed it. 
