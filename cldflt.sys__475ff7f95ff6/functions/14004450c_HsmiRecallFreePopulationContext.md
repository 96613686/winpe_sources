# HsmiRecallFreePopulationContext

- ea: `0x14004450c`
- end: `0x1400445e1`
- name: `HsmiRecallFreePopulationContext`
- size: `213`
- prototype: `void __fastcall(PVOID Entry)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140003cf0`
- `0x140044200`
- `0x1400445f0`

## callees

- `0x14000a048`
- `0x14004450c`
- `0x14005cdd0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140044551`
- `ntoskrnl!ObfDereferenceObject` at `0x140044551`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004459e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400445b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004459e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400445b8`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400445ce`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400445ce`
- `FLTMGR!FltReleaseContext` at `0x14004456f`
- `FLTMGR!FltReleaseContext` at `0x140044584`
- `FLTMGR!FltReleaseContext` at `0x14004456f`
- `FLTMGR!FltReleaseContext` at `0x140044584`

## pseudocode

```c
void __fastcall HsmiRecallFreePopulationContext(PVOID Entry)
{
  signed __int64 v2; // rax
  bool v3; // cc
  signed __int64 v4; // rax
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx

  v2 = _InterlockedExchangeAdd64((volatile signed __int64 *)Entry + 1, 0xFFFFFFFFFFFFFFFFuLL);
  v3 = v2 <= 1;
  v4 = v2 - 1;
  if ( v3 )
  {
    if ( v4 )
      __fastfail(0xEu);
    v5 = (void *)*((_QWORD *)Entry + 8);
    if ( v5 )
      HsmpCleanupAttributionInformation(v5);
    v6 = (void *)*((_QWORD *)Entry + 2);
    if ( v6 )
      ObfDereferenceObject(v6);
    v7 = (void *)*((_QWORD *)Entry + 7);
    if ( v7 )
    {
      HsmpReleaseSyncOpRundownProtection(v7);
      FltReleaseContext(*((PFLT_CONTEXT *)Entry + 7));
    }
    v8 = (void *)*((_QWORD *)Entry + 6);
    if ( v8 )
      FltReleaseContext(v8);
    v9 = (void *)*((_QWORD *)Entry + 9);
    if ( v9 )
      ExFreePoolWithTag(v9, 0x63527348u);
    v10 = (void *)*((_QWORD *)Entry + 5);
    if ( v10 )
      ExFreePoolWithTag(v10, 0x73557348u);
    ExFreeToPagedLookasideList(&stru_1400293C0, Entry);
  }
}

```

## disassembly

```asm
0x14004450c  push    rbx
0x14004450e  sub     rsp, 20h
0x140044512  mov     rbx, rcx
0x140044515  or      rax, 0FFFFFFFFFFFFFFFFh
0x140044519  lock xadd [rcx+8], rax
0x14004451f  sub     rax, 1
0x140044523  jg      loc_1400445DA
0x140044529  test    rax, rax
0x14004452c  jz      short loc_14004453A
0x14004452e  mov     ecx, 0Eh
0x140044533  int     29h; Win8: RtlFailFast(ecx)
0x140044535  jmp     loc_1400445DA
0x14004453a  mov     rcx, [rcx+40h]; P
0x14004453e  test    rcx, rcx
0x140044541  jz      short loc_140044548
0x140044543  call    HsmpCleanupAttributionInformation
0x140044548  mov     rcx, [rbx+10h]; Object
0x14004454c  test    rcx, rcx
0x14004454f  jz      short loc_14004455D
0x140044551  call    cs:__imp_ObfDereferenceObject
0x140044558  nop     dword ptr [rax+rax+00h]
0x14004455d  mov     rcx, [rbx+38h]; Context
0x140044561  test    rcx, rcx
0x140044564  jz      short loc_14004457B
0x140044566  call    HsmpReleaseSyncOpRundownProtection
0x14004456b  mov     rcx, [rbx+38h]; Context
0x14004456f  call    cs:__imp_FltReleaseContext
0x140044576  nop     dword ptr [rax+rax+00h]
0x14004457b  mov     rcx, [rbx+30h]; Context
0x14004457f  test    rcx, rcx
0x140044582  jz      short loc_140044590
0x140044584  call    cs:__imp_FltReleaseContext
0x14004458b  nop     dword ptr [rax+rax+00h]
0x140044590  mov     rcx, [rbx+48h]; P
0x140044594  test    rcx, rcx
0x140044597  jz      short loc_1400445AA
0x140044599  mov     edx, 63527348h; Tag
0x14004459e  call    cs:__imp_ExFreePoolWithTag
0x1400445a5  nop     dword ptr [rax+rax+00h]
0x1400445aa  mov     rcx, [rbx+28h]; P
0x1400445ae  test    rcx, rcx
0x1400445b1  jz      short loc_1400445C4
0x1400445b3  mov     edx, 73557348h; Tag
0x1400445b8  call    cs:__imp_ExFreePoolWithTag
0x1400445bf  nop     dword ptr [rax+rax+00h]
0x1400445c4  mov     rdx, rbx; Entry
0x1400445c7  lea     rcx, stru_1400293C0; Lookaside
0x1400445ce  call    cs:__imp_ExFreeToPagedLookasideList
0x1400445d5  nop     dword ptr [rax+rax+00h]
0x1400445da  add     rsp, 20h
0x1400445de  pop     rbx
0x1400445df  retn
```
