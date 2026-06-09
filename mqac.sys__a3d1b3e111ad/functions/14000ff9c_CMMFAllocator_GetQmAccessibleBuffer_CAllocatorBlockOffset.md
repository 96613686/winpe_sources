# CMMFAllocator::GetQmAccessibleBuffer(CAllocatorBlockOffset)

- ea: `0x14000ff9c`
- end: `0x14000ffd5`
- name: `?GetQmAccessibleBuffer@CMMFAllocator@@QEAAPEAVCAccessibleBlock@@VCAllocatorBlockOffset@@@Z`
- size: `57`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ef4c`
- `0x14000fe84`
- `0x1400107b4`
- `0x14001adac`

## callees

- `0x14000ff9c`
- `0x14000ffdc`
- `0x14001035c`

## pseudocode

```c
__int64 __fastcall CMMFAllocator::GetQmAccessibleBuffer(CMMFAllocator *a1, unsigned int a2)
{
  __int64 v4; // r8

  if ( *((_QWORD *)a1 + 11) && (int)CMMFAllocator::MapQmViewWithRetry(a1) >= 0 )
    return CMMFAllocator::GetQmAccessibleBufferNoMapping(a1, a2, v4);
  else
    return 0;
}

```

## disassembly

```asm
0x14000ff9c  mov     [rsp+arg_0], rbx
0x14000ffa1  push    rdi
0x14000ffa2  sub     rsp, 20h
0x14000ffa6  cmp     qword ptr [rcx+58h], 0
0x14000ffab  mov     ebx, edx
0x14000ffad  mov     rdi, rcx
0x14000ffb0  jz      short loc_14000FFC7
0x14000ffb2  call    ?MapQmViewWithRetry@CMMFAllocator@@AEAAJXZ; CMMFAllocator::MapQmViewWithRetry(void)
0x14000ffb7  test    eax, eax
0x14000ffb9  js      short loc_14000FFC7
0x14000ffbb  mov     edx, ebx
0x14000ffbd  mov     rcx, rdi
0x14000ffc0  call    ?GetQmAccessibleBufferNoMapping@CMMFAllocator@@QEBAPEAVCAccessibleBlock@@VCAllocatorBlockOffset@@@Z; CMMFAllocator::GetQmAccessibleBufferNoMapping(CAllocatorBlockOffset)
0x14000ffc5  jmp     short loc_14000FFC9
0x14000ffc7  xor     eax, eax
0x14000ffc9  mov     rbx, [rsp+28h+arg_0]
0x14000ffce  add     rsp, 20h
0x14000ffd2  pop     rdi
0x14000ffd3  retn
```
