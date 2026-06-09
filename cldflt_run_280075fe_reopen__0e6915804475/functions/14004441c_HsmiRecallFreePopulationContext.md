# HsmiRecallFreePopulationContext

- ea: `0x14004441c`
- end: `0x1400444f1`
- name: `HsmiRecallFreePopulationContext`
- size: `213`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140003cf0`
- `0x140044110`
- `0x140044500`

## callees

- `0x14000a048`
- `0x14004441c`
- `0x14005ccb0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140044461`
- `ntoskrnl!ObfDereferenceObject` at `0x140044461`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400444ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400444c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400444ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400444c8`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400444de`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400444de`
- `FLTMGR!FltReleaseContext` at `0x14004447f`
- `FLTMGR!FltReleaseContext` at `0x140044494`
- `FLTMGR!FltReleaseContext` at `0x14004447f`
- `FLTMGR!FltReleaseContext` at `0x140044494`

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
0x14004441c  push    rbx
0x14004441e  sub     rsp, 20h
0x140044422  mov     rbx, rcx
0x140044425  or      rax, 0FFFFFFFFFFFFFFFFh
0x140044429  lock xadd [rcx+8], rax
0x14004442f  sub     rax, 1
0x140044433  jg      loc_1400444EA
0x140044439  test    rax, rax
0x14004443c  jz      short loc_14004444A
0x14004443e  mov     ecx, 0Eh
0x140044443  int     29h; Win8: RtlFailFast(ecx)
0x140044445  jmp     loc_1400444EA
0x14004444a  mov     rcx, [rcx+40h]; P
0x14004444e  test    rcx, rcx
0x140044451  jz      short loc_140044458
0x140044453  call    HsmpCleanupAttributionInformation
0x140044458  mov     rcx, [rbx+10h]; Object
0x14004445c  test    rcx, rcx
0x14004445f  jz      short loc_14004446D
0x140044461  call    cs:__imp_ObfDereferenceObject
0x140044468  nop     dword ptr [rax+rax+00h]
0x14004446d  mov     rcx, [rbx+38h]; Context
0x140044471  test    rcx, rcx
0x140044474  jz      short loc_14004448B
0x140044476  call    HsmpReleaseSyncOpRundownProtection
0x14004447b  mov     rcx, [rbx+38h]; Context
0x14004447f  call    cs:__imp_FltReleaseContext
0x140044486  nop     dword ptr [rax+rax+00h]
0x14004448b  mov     rcx, [rbx+30h]; Context
0x14004448f  test    rcx, rcx
0x140044492  jz      short loc_1400444A0
0x140044494  call    cs:__imp_FltReleaseContext
0x14004449b  nop     dword ptr [rax+rax+00h]
0x1400444a0  mov     rcx, [rbx+48h]; P
0x1400444a4  test    rcx, rcx
0x1400444a7  jz      short loc_1400444BA
0x1400444a9  mov     edx, 63527348h; Tag
0x1400444ae  call    cs:__imp_ExFreePoolWithTag
0x1400444b5  nop     dword ptr [rax+rax+00h]
0x1400444ba  mov     rcx, [rbx+28h]; P
0x1400444be  test    rcx, rcx
0x1400444c1  jz      short loc_1400444D4
0x1400444c3  mov     edx, 73557348h; Tag
0x1400444c8  call    cs:__imp_ExFreePoolWithTag
0x1400444cf  nop     dword ptr [rax+rax+00h]
0x1400444d4  mov     rdx, rbx; Entry
0x1400444d7  lea     rcx, stru_1400293C0; Lookaside
0x1400444de  call    cs:__imp_ExFreeToPagedLookasideList
0x1400444e5  nop     dword ptr [rax+rax+00h]
0x1400444ea  add     rsp, 20h
0x1400444ee  pop     rbx
0x1400444ef  retn
```
