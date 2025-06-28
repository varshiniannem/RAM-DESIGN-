# RAM-DESIGN-
*COMPANY*: CODETECH IT SOLUTIONS 
*NAME*: ANNEM VARSHINI 
*INTERN ID*: CT08DN207
*DOMAIN* : VLSI
*DURIATION*: 8 WEEKS
*MENTOR*: NEELA SANTOSH
Random Access Memory (RAM) is a crucial component in digital systems and microprocessors. It is used to temporarily store data that the CPU or digital circuits need to access quickly. This project focuses on designing a synchronous RAM module in Verilog Hardware Description Language (HDL) with configurable parameters such as data width and address width. The module supports both read and write operations and is controlled by a clock signal, making it synchronous.

Objective The main objective is to:

Design a parameterized synchronous RAM module.

Simulate its behavior using a Verilog testbench.

Verify the correctness of read and write operations.

Analyze results using both console outputs and waveform
The RAM module, named sync_ram, is parameterized with DATA_WIDTH and ADDR_WIDTH. This allows the module to be flexible for different memory sizes. For example, if DATA_WIDTH = 8 and ADDR_WIDTH = 4, the memory will have 16 locations (2^4) each storing 8-bit data.

The module has the following ports:

clk: Clock input, triggers all operations on the rising edge.

we: Write Enable. When we = 1, data is written to memory. When we = 0, data is read.

addr: Address input to select a memory location.

din: Data input for writing into memory.

dout: Data output for reading from memory.

The memory array is declared as a 2D register array. Read and write operations are implemented inside an always @(posedge clk) block to ensure synchronous operation.

Testbench Design A separate module tb_sync_ram is written to test the RAM. It includes:

Clock generation using an always block with a 10 ns period.

Sequential read and write operations using @(posedge clk) for synchronization.

$display and $monitor statements for real-time output during simulation.

$dumpfile and $dumpvars to generate a .vcd file for waveform viewing.

The testbench writes known values to different addresses and then reads them back to verify correctness. It also reads from an unwritten address to observe default behavior.

Simulation and Results The simulation was run using Icarus Verilog and viewed with EPWave. Console output confirmed that values written to specific addresses were correctly read back. For example, writing A5 to address 4 and reading from the same address returned A5, confirming correct memory behavior.

The waveform showed:

Proper clock signal.

Correct timing of data input and output.

Synchronous updates of dout one cycle after address is set (due to clocked behavior).

Conclusion The synchronous RAM module performed as expected. It successfully handled read and write operations on the clock edge, making it suitable for integration into digital systems like CPUs or FPGAs. The design is clean, reusable, and can be extended for more advanced features such as reset, dual-port operation, or memory initialization from files. This project reinforces key concepts of synchronous design, memory control, and Verilog simulation techniques.
#output
![Image](https://github.com/user-attachments/assets/d30c213e-f1b0-49be-a0f3-7b5e2b04499d)
