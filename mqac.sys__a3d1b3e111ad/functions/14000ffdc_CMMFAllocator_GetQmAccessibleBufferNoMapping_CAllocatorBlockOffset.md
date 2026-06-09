# CMMFAllocator::GetQmAccessibleBufferNoMapping(CAllocatorBlockOffset)

- ea: `0x14000ffdc`
- end: `0x14000ffee`
- name: `?GetQmAccessibleBufferNoMapping@CMMFAllocator@@QEBAPEAVCAccessibleBlock@@VCAllocatorBlockOffset@@@Z`
- size: `18`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ff9c`
- `0x140018c5c`
- `0x140021080`

## callees

- `0x14000ffdc`

## pseudocode

```c
__int64 __fastcall CMMFAllocator::GetQmAccessibleBufferNoMapping(__int64 a1, unsigned int a2)
{
  if ( *(_QWORD *)(a1 + 88) )
    return *(_QWORD *)(a1 + 96) + a2;
  else
    return 0;
}

```

## disassembly

```asm
0x14000ffdc  cmp     qword ptr [rcx+58h], 0
0x14000ffe1  jnz     short loc_14000FFE7
0x14000ffe3  xor     eax, eax
0x14000ffe5  retn
0x14000ffe7  mov     eax, edx
0x14000ffe9  add     rax, [rcx+60h]
0x14000ffed  retn
```
