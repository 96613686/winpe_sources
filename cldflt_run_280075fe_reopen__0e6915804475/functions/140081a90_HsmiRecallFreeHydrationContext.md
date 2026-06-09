# HsmiRecallFreeHydrationContext

- ea: `0x140081a90`
- end: `0x140081b88`
- name: `HsmiRecallFreeHydrationContext`
- size: `248`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002aec`
- `0x140084eb0`

## callees

- `0x14000a048`
- `0x14003659c`
- `0x14005ccb0`
- `0x140081a90`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140081ad5`
- `ntoskrnl!ObfDereferenceObject` at `0x140081ad5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081b42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081b5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081b42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081b5f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140081b75`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140081b75`
- `FLTMGR!FltReleaseContext` at `0x140081b04`
- `FLTMGR!FltReleaseContext` at `0x140081b28`
- `FLTMGR!FltReleaseContext` at `0x140081b04`
- `FLTMGR!FltReleaseContext` at `0x140081b28`

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
0x140081a90  push    rbx
0x140081a92  sub     rsp, 20h
0x140081a96  mov     rbx, rcx
0x140081a99  or      rax, 0FFFFFFFFFFFFFFFFh
0x140081a9d  lock xadd [rcx+8], rax
0x140081aa3  sub     rax, 1
0x140081aa7  jg      loc_140081B81
0x140081aad  test    rax, rax
0x140081ab0  jz      short loc_140081ABE
0x140081ab2  mov     ecx, 0Eh
0x140081ab7  int     29h; Win8: RtlFailFast(ecx)
0x140081ab9  jmp     loc_140081B81
0x140081abe  mov     rcx, [rcx+68h]; P
0x140081ac2  test    rcx, rcx
0x140081ac5  jz      short loc_140081ACC
0x140081ac7  call    HsmpCleanupAttributionInformation
0x140081acc  mov     rcx, [rbx+10h]; Object
0x140081ad0  test    rcx, rcx
0x140081ad3  jz      short loc_140081AE1
0x140081ad5  call    cs:__imp_ObfDereferenceObject
0x140081adc  nop     dword ptr [rax+rax+00h]
0x140081ae1  mov     rcx, [rbx+80h]
0x140081ae8  test    rcx, rcx
0x140081aeb  jz      short loc_140081AF2
0x140081aed  call    HsmpBitmapRelease
0x140081af2  mov     rcx, [rbx+78h]; Context
0x140081af6  test    rcx, rcx
0x140081af9  jz      short loc_140081B10
0x140081afb  call    HsmpReleaseSyncOpRundownProtection
0x140081b00  mov     rcx, [rbx+78h]; Context
0x140081b04  call    cs:__imp_FltReleaseContext
0x140081b0b  nop     dword ptr [rax+rax+00h]
0x140081b10  mov     rdx, [rbx+70h]
0x140081b14  test    rdx, rdx
0x140081b17  jz      short loc_140081B34
0x140081b19  xor     ecx, ecx
0x140081b1b  mov     rax, rbx
0x140081b1e  lock cmpxchg [rdx+38h], rcx
0x140081b24  mov     rcx, [rbx+70h]; Context
0x140081b28  call    cs:__imp_FltReleaseContext
0x140081b2f  nop     dword ptr [rax+rax+00h]
0x140081b34  mov     rcx, [rbx+60h]; P
0x140081b38  test    rcx, rcx
0x140081b3b  jz      short loc_140081B4E
0x140081b3d  mov     edx, 73557348h; Tag
0x140081b42  call    cs:__imp_ExFreePoolWithTag
0x140081b49  nop     dword ptr [rax+rax+00h]
0x140081b4e  mov     rcx, [rbx+88h]; P
0x140081b55  test    rcx, rcx
0x140081b58  jz      short loc_140081B6B
0x140081b5a  mov     edx, 63527348h; Tag
0x140081b5f  call    cs:__imp_ExFreePoolWithTag
0x140081b66  nop     dword ptr [rax+rax+00h]
0x140081b6b  mov     rdx, rbx; Entry
0x140081b6e  lea     rcx, stru_140029340; Lookaside
0x140081b75  call    cs:__imp_ExFreeToPagedLookasideList
0x140081b7c  nop     dword ptr [rax+rax+00h]
0x140081b81  add     rsp, 20h
0x140081b85  pop     rbx
0x140081b86  retn
```
