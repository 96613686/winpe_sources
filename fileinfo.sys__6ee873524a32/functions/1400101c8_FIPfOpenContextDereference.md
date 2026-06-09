# FIPfOpenContextDereference

- ea: `0x1400101c8`
- end: `0x140010231`
- name: `FIPfOpenContextDereference`
- size: `105`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140010240`
- `0x140010350`
- `0x1400156d4`
- `0x140017700`

## callees

- `0x1400101c8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001021e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001021e`
- `FLTMGR!FltFreeGenericWorkItem` at `0x1400101f8`
- `FLTMGR!FltFreeGenericWorkItem` at `0x1400101f8`
- `FLTMGR!FltReleaseContext` at `0x14001020d`
- `FLTMGR!FltReleaseContext` at `0x14001020d`

## pseudocode

```c
void __fastcall FIPfOpenContextDereference(volatile signed __int64 *P)
{
  signed __int64 v2; // rax
  bool v3; // cc
  signed __int64 v4; // rax
  struct _FLT_GENERIC_WORKITEM *v5; // rcx
  void *v6; // rcx

  v2 = _InterlockedExchangeAdd64(P + 12, 0xFFFFFFFFFFFFFFFFuLL);
  v3 = v2 <= 1;
  v4 = v2 - 1;
  if ( v3 )
  {
    if ( v4 )
      __fastfail(0xEu);
    v5 = (struct _FLT_GENERIC_WORKITEM *)*((_QWORD *)P + 6);
    if ( v5 )
      FltFreeGenericWorkItem(v5);
    v6 = (void *)*((_QWORD *)P + 7);
    if ( v6 )
      FltReleaseContext(v6);
    ExFreePoolWithTag((PVOID)P, 0);
  }
}

```

## disassembly

```asm
0x1400101c8  push    rbx
0x1400101ca  sub     rsp, 20h
0x1400101ce  mov     rbx, rcx
0x1400101d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400101d5  lock xadd [rcx+60h], rax
0x1400101db  sub     rax, 1
0x1400101df  jg      short loc_14001022A
0x1400101e1  test    rax, rax
0x1400101e4  jz      short loc_1400101EF
0x1400101e6  mov     ecx, 0Eh
0x1400101eb  int     29h; Win8: RtlFailFast(ecx)
0x1400101ed  jmp     short loc_14001022A
0x1400101ef  mov     rcx, [rcx+30h]; FltWorkItem
0x1400101f3  test    rcx, rcx
0x1400101f6  jz      short loc_140010204
0x1400101f8  call    cs:__imp_FltFreeGenericWorkItem
0x1400101ff  nop     dword ptr [rax+rax+00h]
0x140010204  mov     rcx, [rbx+38h]; Context
0x140010208  test    rcx, rcx
0x14001020b  jz      short loc_140010219
0x14001020d  call    cs:__imp_FltReleaseContext
0x140010214  nop     dword ptr [rax+rax+00h]
0x140010219  xor     edx, edx; Tag
0x14001021b  mov     rcx, rbx; P
0x14001021e  call    cs:__imp_ExFreePoolWithTag
0x140010225  nop     dword ptr [rax+rax+00h]
0x14001022a  add     rsp, 20h
0x14001022e  pop     rbx
0x14001022f  retn
```
