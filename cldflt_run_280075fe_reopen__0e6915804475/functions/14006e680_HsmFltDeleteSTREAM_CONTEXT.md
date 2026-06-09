# HsmFltDeleteSTREAM_CONTEXT

- ea: `0x14006e680`
- end: `0x14006e770`
- name: `HsmFltDeleteSTREAM_CONTEXT`
- size: `240`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x14001e220`
- `0x14003659c`
- `0x14006e680`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006e6ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e6d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e6ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e6d2`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14006e73c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14006e73c`
- `FLTMGR!FltFreeFileLock` at `0x14006e74d`
- `FLTMGR!FltFreeFileLock` at `0x14006e74d`
- `FLTMGR!FltReleaseContext` at `0x14006e6e2`
- `FLTMGR!FltReleaseContext` at `0x14006e6e2`

## pseudocode

```c
void __fastcall HsmFltDeleteSTREAM_CONTEXT(__int64 a1)
{
  void *v2; // rcx
  __int64 v3; // rax
  void *v4; // rcx
  FILE_LOCK *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx

  if ( *(_QWORD *)(a1 + 8) )
    ((void (*)(void))qword_140029710)();
  v2 = *(void **)(a1 + 104);
  if ( v2 )
    ExFreePoolWithTag(v2, 0x76437348u);
  v3 = *(_QWORD *)(a1 + 160);
  if ( v3 )
  {
    v5 = *(FILE_LOCK **)(v3 + 32);
    if ( v5 )
      FltFreeFileLock(v5);
    v6 = *(_QWORD *)(*(_QWORD *)(a1 + 160) + 56LL);
    if ( v6 )
      HsmpBitmapRelease(v6);
    v7 = *(_QWORD *)(*(_QWORD *)(a1 + 160) + 64LL);
    if ( v7 )
      HsmpBitmapRelease(v7);
    v8 = *(_QWORD *)(*(_QWORD *)(a1 + 160) + 72LL);
    if ( v8 )
      HsmpBitmapRelease(v8);
    ExFreeToPagedLookasideList(&stru_140029440, *(PVOID *)(a1 + 160));
  }
  v4 = *(void **)(a1 + 48);
  if ( v4 )
    ExFreePoolWithTag(v4, 0x69467348u);
  FltReleaseContext(*(PFLT_CONTEXT *)(a1 + 16));
}

```

## disassembly

```asm
0x14006e680  push    rbx
0x14006e682  sub     rsp, 20h
0x14006e686  mov     rbx, rcx
0x14006e689  mov     rcx, [rcx+8]
0x14006e68d  test    rcx, rcx
0x14006e690  jz      short loc_14006E69E
0x14006e692  mov     rax, cs:qword_140029710
0x14006e699  call    _guard_dispatch_icall
0x14006e69e  mov     rcx, [rbx+68h]; P
0x14006e6a2  test    rcx, rcx
0x14006e6a5  jz      short loc_14006E6B8
0x14006e6a7  mov     edx, 76437348h; Tag
0x14006e6ac  call    cs:__imp_ExFreePoolWithTag
0x14006e6b3  nop     dword ptr [rax+rax+00h]
0x14006e6b8  mov     rax, [rbx+0A0h]
0x14006e6bf  test    rax, rax
0x14006e6c2  jnz     short loc_14006E6F5
0x14006e6c4  mov     rcx, [rbx+30h]; P
0x14006e6c8  test    rcx, rcx
0x14006e6cb  jz      short loc_14006E6DE
0x14006e6cd  mov     edx, 69467348h; Tag
0x14006e6d2  call    cs:__imp_ExFreePoolWithTag
0x14006e6d9  nop     dword ptr [rax+rax+00h]
0x14006e6de  mov     rcx, [rbx+10h]; Context
0x14006e6e2  call    cs:__imp_FltReleaseContext
0x14006e6e9  nop     dword ptr [rax+rax+00h]
0x14006e6ee  add     rsp, 20h
0x14006e6f2  pop     rbx
0x14006e6f3  retn
0x14006e6f5  mov     rcx, [rax+20h]; FileLock
0x14006e6f9  test    rcx, rcx
0x14006e6fc  jnz     short loc_14006E74D
0x14006e6fe  mov     rax, [rbx+0A0h]
0x14006e705  mov     rcx, [rax+38h]
0x14006e709  test    rcx, rcx
0x14006e70c  jnz     short loc_14006E75B
0x14006e70e  mov     rax, [rbx+0A0h]
0x14006e715  mov     rcx, [rax+40h]
0x14006e719  test    rcx, rcx
0x14006e71c  jnz     short loc_14006E762
0x14006e71e  mov     rax, [rbx+0A0h]
0x14006e725  mov     rcx, [rax+48h]
0x14006e729  test    rcx, rcx
0x14006e72c  jnz     short loc_14006E769
0x14006e72e  mov     rdx, [rbx+0A0h]; Entry
0x14006e735  lea     rcx, stru_140029440; Lookaside
0x14006e73c  call    cs:__imp_ExFreeToPagedLookasideList
0x14006e743  nop     dword ptr [rax+rax+00h]
0x14006e748  jmp     loc_14006E6C4
0x14006e74d  call    cs:__imp_FltFreeFileLock
0x14006e754  nop     dword ptr [rax+rax+00h]
0x14006e759  jmp     short loc_14006E6FE
0x14006e75b  call    HsmpBitmapRelease
0x14006e760  jmp     short loc_14006E70E
0x14006e762  call    HsmpBitmapRelease
0x14006e767  jmp     short loc_14006E71E
0x14006e769  call    HsmpBitmapRelease
0x14006e76e  jmp     short loc_14006E72E
```
