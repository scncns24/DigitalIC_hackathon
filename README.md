Title of Project : Custom Multiply-Accumulate (MAC) instruction for Microwatt POWER CPU 


Project Description :

This project extends the Microwatt POWER ISA CPU core with a custom Multiply-Accumulate (MAC) instruction that performs:
𝑟𝐷 ← (𝑟𝐴 × 𝑟𝐵) + 𝑟𝐶
in a single instruction. This reduces the instruction sequence length and improves performance for DSP and ML workloads such as FIR filters, dot products, and matrix multiplications. The implementation requires the following key RTL modifications:

1.Instruction Encoding – Define a new opcode by selecting an unused slot in the POWER ISA encoding space for the MAC instruction.
2.Instruction Decode – Extend the decode logic to recognize the new opcode and generate the appropriate control signals for execution.
3.Pipeline Execution – Modify the execution stage to introduce a fused datapath where the multiplier output is directly combined with an additional operand through the adder, completing the MAC operation in one step.
4.Result Write-back – Ensure the computed result is correctly written back into the destination register, maintaining consistency with the register file and hazard control logic.

The new instruction will be validated with simulation testbenches and application-level benchmarks, comparing cycle counts against equivalent multiply–add sequences. This work will demonstrate how Microwatt can be extended for domain-specific acceleration and provides a reusable reference for adding custom instructions in the OpenPOWER ecosystem.


Project Proposal :

This project proposes the design and integration of a Multiply-Accumulate (MAC) instruction into the Microwatt POWER CPU core to enhance support for DSP and machine learning workloads. The new instruction fuses multiplication and addition in a single operation, reducing instruction count and improving execution efficiency for algorithms such as dot products and matrix multiplications. The work includes defining the instruction encoding, extending the pipeline to support fused multiply-add functionality, and validating correctness through simulation and application-level benchmarks. The final outcome will be an open-source, reusable extension that demonstrates the potential of customizing Microwatt for domain-specific acceleration within the OpenPOWER ecosystem.
