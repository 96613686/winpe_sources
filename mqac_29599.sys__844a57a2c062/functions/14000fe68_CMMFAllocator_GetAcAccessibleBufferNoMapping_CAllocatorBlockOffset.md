# CMMFAllocator::GetAcAccessibleBufferNoMapping(CAllocatorBlockOffset)

- ea: `0x14000fe68`
- end: `0x14000fe7a`
- name: `?GetAcAccessibleBufferNoMapping@CMMFAllocator@@AEBAPEAVCAccessibleBlock@@VCAllocatorBlockOffset@@@Z`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000fe84`

## callees

- `0x14000fe68`

## pseudocode

```c
__int64 __fastcall CMMFAllocator::GetAcAccessibleBufferNoMapping(__int64 a1, unsigned int a2)
{
  if ( *(_QWORD *)(a1 + 88) )
    return *(_QWORD *)(a1 + 104) + a2;
  else
    return 0;
}

```

## disassembly

```asm
0x14000fe68  cmp     qword ptr [rcx+58h], 0
0x14000fe6d  jnz     short loc_14000FE73
0x14000fe6f  xor     eax, eax
0x14000fe71  retn
0x14000fe73  mov     eax, edx
0x14000fe75  add     rax, [rcx+68h]
0x14000fe79  retn
```
