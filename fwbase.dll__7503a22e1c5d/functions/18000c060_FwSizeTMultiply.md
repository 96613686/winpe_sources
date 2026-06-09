# FwSizeTMultiply

- ea: `0x18000c060`
- end: `0x18000c08c`
- name: `FwSizeTMultiply`
- size: `44`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180006b68`
- `0x1800138f0`
- `0x180020470`
- `0x180020b10`
- `0x180020e90`
- `0x180020f80`
- `0x180021270`
- `0x180029d10`
- `0x18002b410`
- `0x18002c0e0`

## callees

- `0x18000c060`

## pseudocode

```c
__int64 __fastcall FwSizeTMultiply(unsigned __int64 a1, unsigned __int64 a2, _QWORD *a3)
{
  *a3 = a2 * a1;
  if ( a2 && a1 > 0xFFFFFFFFFFFFFFFFuLL / a2 )
    return 2147942934LL;
  else
    return 0;
}

```

## disassembly

```asm
0x18000c060  mov     rax, rcx
0x18000c063  mov     r9, rdx
0x18000c066  imul    rax, rdx
0x18000c06a  mov     [r8], rax
0x18000c06d  test    rdx, rdx
0x18000c070  jz      short loc_18000C089
0x18000c072  xor     edx, edx
0x18000c074  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c07b  div     r9
0x18000c07e  cmp     rcx, rax
0x18000c081  jbe     short loc_18000C089
0x18000c083  mov     eax, 80070216h
0x18000c088  retn
0x18000c089  xor     eax, eax
0x18000c08b  retn
```
