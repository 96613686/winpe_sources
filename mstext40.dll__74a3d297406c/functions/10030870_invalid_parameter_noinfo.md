# __invalid_parameter_noinfo

- ea: `0x10030870`
- end: `0x10030880`
- name: `__invalid_parameter_noinfo`
- size: `16`
- prototype: `void __cdecl()`
- caller_count: `53`
- callee_count: `1`
- tags: ``

## callers

- `0x1002c520`
- `0x1002caf0`
- `0x1002cdf5`
- `0x1002d562`
- `0x1002d730`
- `0x1002d804`
- `0x1002d9e1`
- `0x1002da74`
- `0x1002dffc`
- `0x1002e0f7`
- `0x1002f856`
- `0x1002fbd0`
- `0x1002fd21`
- `0x1002fdef`
- `0x1002fedb`
- `0x1002ff9c`
- `0x100308ab`
- `0x10030969`
- `0x10030c59`
- `0x10032382`
- `0x10032721`
- `0x100334b0`
- `0x10034055`
- `0x10034171`
- `0x10034242`
- `0x10036235`
- `0x100366af`
- `0x10036c5e`
- `0x10036d9d`
- `0x10037004`
- `0x1003711c`
- `0x10037188`
- `0x1003735a`
- `0x1003737e`
- `0x100373d2`
- `0x100374c1`
- `0x10037d26`
- `0x10038c67`
- `0x1003a31c`
- `0x1003a51e`
- `0x1003a9e2`
- `0x1003b5cc`
- `0x1003b6ed`
- `0x1003b7cd`
- `0x1003b83d`
- `0x1003bcf2`
- `0x1003c104`
- `0x1003c2b7`
- `0x1003c3cb`
- `0x1003cb5c`

## callees

- `0x10030845`

## pseudocode

```c
void __cdecl _invalid_parameter_noinfo()
{
  _invalid_parameter(0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x10030870  xor     eax, eax
0x10030872  push    eax; Reserved
0x10030873  push    eax; LineNo
0x10030874  push    eax; FileName
0x10030875  push    eax; FunctionName
0x10030876  push    eax; Expression
0x10030877  call    __invalid_parameter
0x1003087c  add     esp, 14h
0x1003087f  retn
```
