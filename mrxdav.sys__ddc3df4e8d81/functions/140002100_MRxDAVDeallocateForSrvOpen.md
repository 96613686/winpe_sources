# MRxDAVDeallocateForSrvOpen

- ea: `0x140002100`
- end: `0x140002131`
- name: `MRxDAVDeallocateForSrvOpen`
- size: `49`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140002100`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002114`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002114`

## pseudocode

```c
__int64 __fastcall MRxDAVDeallocateForSrvOpen(__int64 a1, __int64 a2)
{
  void *v2; // rcx

  v2 = *(void **)(a2 + 48);
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0);
    *(_QWORD *)(a2 + 48) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x140002100  push    rbx
0x140002102  sub     rsp, 20h
0x140002106  mov     rcx, [rdx+30h]; P
0x14000210a  mov     rbx, rdx
0x14000210d  test    rcx, rcx
0x140002110  jz      short loc_140002128
0x140002112  xor     edx, edx; Tag
0x140002114  call    cs:__imp_ExFreePoolWithTag
0x14000211b  nop     dword ptr [rax+rax+00h]
0x140002120  mov     qword ptr [rbx+30h], 0
0x140002128  xor     eax, eax
0x14000212a  add     rsp, 20h
0x14000212e  pop     rbx
0x14000212f  retn
```
