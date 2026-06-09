# tagCHANNELCLOSECONTEXT::`scalar deleting destructor'(uint)

- ea: `0x140025480`
- end: `0x1400254b1`
- name: `??_GtagCHANNELCLOSECONTEXT@@QEAAPEAXI@Z`
- size: `49`
- prototype: `void *__fastcall(PVOID P, unsigned int)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x14001b608`
- `0x140023cf0`
- `0x140024830`
- `0x140025000`
- `0x1400251d0`
- `0x14002abf0`

## callees

- `0x140001660`
- `0x140025480`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002549b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002549b`

## pseudocode

```c
RefCount **__fastcall tagCHANNELCLOSECONTEXT::`scalar deleting destructor'(RefCount **P)
{
  RefCount *v2; // rcx

  v2 = *P;
  if ( v2 )
    RefCount::Release(v2);
  ExFreePoolWithTag(P, 0);
  return P;
}

```

## disassembly

```asm
0x140025480  push    rbx
0x140025482  sub     rsp, 20h
0x140025486  mov     rbx, rcx
0x140025489  mov     rcx, [rcx]; this
0x14002548c  test    rcx, rcx
0x14002548f  jz      short loc_140025496
0x140025491  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140025496  xor     edx, edx; Tag
0x140025498  mov     rcx, rbx; P
0x14002549b  call    cs:__imp_ExFreePoolWithTag
0x1400254a2  nop     dword ptr [rax+rax+00h]
0x1400254a7  mov     rax, rbx
0x1400254aa  add     rsp, 20h
0x1400254ae  pop     rbx
0x1400254af  retn
```
