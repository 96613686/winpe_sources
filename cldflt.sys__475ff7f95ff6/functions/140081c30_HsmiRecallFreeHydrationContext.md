# HsmiRecallFreeHydrationContext

- ea: `0x140081c30`
- end: `0x140081d28`
- name: `HsmiRecallFreeHydrationContext`
- size: `248`
- prototype: `void __fastcall(signed __int64 Entry)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002aec`
- `0x14008506c`

## callees

- `0x14000a048`
- `0x14003659c`
- `0x14005cdd0`
- `0x140081c30`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140081c75`
- `ntoskrnl!ObfDereferenceObject` at `0x140081c75`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081ce2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081cff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081ce2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081cff`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140081d15`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140081d15`
- `FLTMGR!FltReleaseContext` at `0x140081ca4`
- `FLTMGR!FltReleaseContext` at `0x140081cc8`
- `FLTMGR!FltReleaseContext` at `0x140081ca4`
- `FLTMGR!FltReleaseContext` at `0x140081cc8`

## pseudocode

```c
void __fastcall HsmiRecallFreeHydrationContext(signed __int64 Entry)
{
  signed __int64 v2; // rax
  bool v3; // cc
  signed __int64 v4; // rax
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rcx
  void *v8; // rcx
  __int64 v9; // rdx
  void *v10; // rcx
  void *v11; // rcx

  v2 = _InterlockedExchangeAdd64((volatile signed __int64 *)(Entry + 8), 0xFFFFFFFFFFFFFFFFuLL);
  v3 = v2 <= 1;
  v4 = v2 - 1;
  if ( v3 )
  {
    if ( v4 )
      __fastfail(0xEu);
    v5 = *(void **)(Entry + 104);
    if ( v5 )
      HsmpCleanupAttributionInformation(v5);
    v6 = *(void **)(Entry + 16);
    if ( v6 )
      ObfDereferenceObject(v6);
    v7 = *(_QWORD *)(Entry + 128);
    if ( v7 )
      HsmpBitmapRelease(v7);
    v8 = *(void **)(Entry + 120);
    if ( v8 )
    {
      HsmpReleaseSyncOpRundownProtection(v8);
      FltReleaseContext(*(PFLT_CONTEXT *)(Entry + 120));
    }
    v9 = *(_QWORD *)(Entry + 112);
    if ( v9 )
    {
      _InterlockedCompareExchange64((volatile signed __int64 *)(v9 + 56), 0, Entry);
      FltReleaseContext(*(PFLT_CONTEXT *)(Entry + 112));
    }
    v10 = *(void **)(Entry + 96);
    if ( v10 )
      ExFreePoolWithTag(v10, 0x73557348u);
    v11 = *(void **)(Entry + 136);
    if ( v11 )
      ExFreePoolWithTag(v11, 0x63527348u);
    ExFreeToPagedLookasideList(&stru_140029340, (PVOID)Entry);
  }
}

```

## disassembly

```asm
0x140081c30  push    rbx
0x140081c32  sub     rsp, 20h
0x140081c36  mov     rbx, rcx
0x140081c39  or      rax, 0FFFFFFFFFFFFFFFFh
0x140081c3d  lock xadd [rcx+8], rax
0x140081c43  sub     rax, 1
0x140081c47  jg      loc_140081D21
0x140081c4d  test    rax, rax
0x140081c50  jz      short loc_140081C5E
0x140081c52  mov     ecx, 0Eh
0x140081c57  int     29h; Win8: RtlFailFast(ecx)
0x140081c59  jmp     loc_140081D21
0x140081c5e  mov     rcx, [rcx+68h]; P
0x140081c62  test    rcx, rcx
0x140081c65  jz      short loc_140081C6C
0x140081c67  call    HsmpCleanupAttributionInformation
0x140081c6c  mov     rcx, [rbx+10h]; Object
0x140081c70  test    rcx, rcx
0x140081c73  jz      short loc_140081C81
0x140081c75  call    cs:__imp_ObfDereferenceObject
0x140081c7c  nop     dword ptr [rax+rax+00h]
0x140081c81  mov     rcx, [rbx+80h]
0x140081c88  test    rcx, rcx
0x140081c8b  jz      short loc_140081C92
0x140081c8d  call    HsmpBitmapRelease
0x140081c92  mov     rcx, [rbx+78h]; Context
0x140081c96  test    rcx, rcx
0x140081c99  jz      short loc_140081CB0
0x140081c9b  call    HsmpReleaseSyncOpRundownProtection
0x140081ca0  mov     rcx, [rbx+78h]; Context
0x140081ca4  call    cs:__imp_FltReleaseContext
0x140081cab  nop     dword ptr [rax+rax+00h]
0x140081cb0  mov     rdx, [rbx+70h]
0x140081cb4  test    rdx, rdx
0x140081cb7  jz      short loc_140081CD4
0x140081cb9  xor     ecx, ecx
0x140081cbb  mov     rax, rbx
0x140081cbe  lock cmpxchg [rdx+38h], rcx
0x140081cc4  mov     rcx, [rbx+70h]; Context
0x140081cc8  call    cs:__imp_FltReleaseContext
0x140081ccf  nop     dword ptr [rax+rax+00h]
0x140081cd4  mov     rcx, [rbx+60h]; P
0x140081cd8  test    rcx, rcx
0x140081cdb  jz      short loc_140081CEE
0x140081cdd  mov     edx, 73557348h; Tag
0x140081ce2  call    cs:__imp_ExFreePoolWithTag
0x140081ce9  nop     dword ptr [rax+rax+00h]
0x140081cee  mov     rcx, [rbx+88h]; P
0x140081cf5  test    rcx, rcx
0x140081cf8  jz      short loc_140081D0B
0x140081cfa  mov     edx, 63527348h; Tag
0x140081cff  call    cs:__imp_ExFreePoolWithTag
0x140081d06  nop     dword ptr [rax+rax+00h]
0x140081d0b  mov     rdx, rbx; Entry
0x140081d0e  lea     rcx, stru_140029340; Lookaside
0x140081d15  call    cs:__imp_ExFreeToPagedLookasideList
0x140081d1c  nop     dword ptr [rax+rax+00h]
0x140081d21  add     rsp, 20h
0x140081d25  pop     rbx
0x140081d26  retn
```
