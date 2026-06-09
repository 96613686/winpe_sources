# HsmFltDeleteSTREAM_CONTEXT

- ea: `0x14006e7a0`
- end: `0x14006e890`
- name: `HsmFltDeleteSTREAM_CONTEXT`
- size: `240`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x14001e2a0`
- `0x14003659c`
- `0x14006e7a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006e7cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e7f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e7cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e7f2`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14006e85c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14006e85c`
- `FLTMGR!FltFreeFileLock` at `0x14006e86d`
- `FLTMGR!FltFreeFileLock` at `0x14006e86d`
- `FLTMGR!FltReleaseContext` at `0x14006e802`
- `FLTMGR!FltReleaseContext` at `0x14006e802`

## pseudocode

```c
void __fastcall HsmFltDeleteSTREAM_CONTEXT(__int64 a1)
{
  void *v2; // rcx
  __int64 v3; // rax
  void *v4; // rcx
  FILE_LOCK *v5; // rcx

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
    if ( *(_QWORD *)(*(_QWORD *)(a1 + 160) + 56LL) )
      HsmpBitmapRelease();
    if ( *(_QWORD *)(*(_QWORD *)(a1 + 160) + 64LL) )
      HsmpBitmapRelease();
    if ( *(_QWORD *)(*(_QWORD *)(a1 + 160) + 72LL) )
      HsmpBitmapRelease();
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
0x14006e7a0  push    rbx
0x14006e7a2  sub     rsp, 20h
0x14006e7a6  mov     rbx, rcx
0x14006e7a9  mov     rcx, [rcx+8]
0x14006e7ad  test    rcx, rcx
0x14006e7b0  jz      short loc_14006E7BE
0x14006e7b2  mov     rax, cs:qword_140029710
0x14006e7b9  call    _guard_dispatch_icall
0x14006e7be  mov     rcx, [rbx+68h]; P
0x14006e7c2  test    rcx, rcx
0x14006e7c5  jz      short loc_14006E7D8
0x14006e7c7  mov     edx, 76437348h; Tag
0x14006e7cc  call    cs:__imp_ExFreePoolWithTag
0x14006e7d3  nop     dword ptr [rax+rax+00h]
0x14006e7d8  mov     rax, [rbx+0A0h]
0x14006e7df  test    rax, rax
0x14006e7e2  jnz     short loc_14006E815
0x14006e7e4  mov     rcx, [rbx+30h]; P
0x14006e7e8  test    rcx, rcx
0x14006e7eb  jz      short loc_14006E7FE
0x14006e7ed  mov     edx, 69467348h; Tag
0x14006e7f2  call    cs:__imp_ExFreePoolWithTag
0x14006e7f9  nop     dword ptr [rax+rax+00h]
0x14006e7fe  mov     rcx, [rbx+10h]; Context
0x14006e802  call    cs:__imp_FltReleaseContext
0x14006e809  nop     dword ptr [rax+rax+00h]
0x14006e80e  add     rsp, 20h
0x14006e812  pop     rbx
0x14006e813  retn
0x14006e815  mov     rcx, [rax+20h]; FileLock
0x14006e819  test    rcx, rcx
0x14006e81c  jnz     short loc_14006E86D
0x14006e81e  mov     rax, [rbx+0A0h]
0x14006e825  mov     rcx, [rax+38h]
0x14006e829  test    rcx, rcx
0x14006e82c  jnz     short loc_14006E87B
0x14006e82e  mov     rax, [rbx+0A0h]
0x14006e835  mov     rcx, [rax+40h]
0x14006e839  test    rcx, rcx
0x14006e83c  jnz     short loc_14006E882
0x14006e83e  mov     rax, [rbx+0A0h]
0x14006e845  mov     rcx, [rax+48h]
0x14006e849  test    rcx, rcx
0x14006e84c  jnz     short loc_14006E889
0x14006e84e  mov     rdx, [rbx+0A0h]; Entry
0x14006e855  lea     rcx, stru_140029440; Lookaside
0x14006e85c  call    cs:__imp_ExFreeToPagedLookasideList
0x14006e863  nop     dword ptr [rax+rax+00h]
0x14006e868  jmp     loc_14006E7E4
0x14006e86d  call    cs:__imp_FltFreeFileLock
0x14006e874  nop     dword ptr [rax+rax+00h]
0x14006e879  jmp     short loc_14006E81E
0x14006e87b  call    HsmpBitmapRelease
0x14006e880  jmp     short loc_14006E82E
0x14006e882  call    HsmpBitmapRelease
0x14006e887  jmp     short loc_14006E83E
0x14006e889  call    HsmpBitmapRelease
0x14006e88e  jmp     short loc_14006E84E
```
