# PrjfReleaseRenameOrLinkCompletionContext

- ea: `0x140003d9c`
- end: `0x140003e65`
- name: `PrjfReleaseRenameOrLinkCompletionContext`
- size: `201`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001b3c`
- `0x14002c3f8`
- `0x14002c98c`

## callees

- `0x140003d9c`
- `0x140003e6c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140003db3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003dcd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003db3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003dcd`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140003e52`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140003e52`
- `ntoskrnl!ObfDereferenceObject` at `0x140003df7`
- `ntoskrnl!ObfDereferenceObject` at `0x140003e3c`
- `ntoskrnl!ObfDereferenceObject` at `0x140003df7`
- `ntoskrnl!ObfDereferenceObject` at `0x140003e3c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003de2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003de2`
- `FLTMGR!FltReleaseContext` at `0x140003e0c`
- `FLTMGR!FltReleaseContext` at `0x140003e0c`

## pseudocode

```c
void __fastcall PrjfReleaseRenameOrLinkCompletionContext(char **Entry, __int64 a2, __int64 a3, __int64 a4)
{
  char *v5; // rcx
  char *v6; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v7; // rcx
  char *v8; // rcx
  char *v9; // rcx
  char *v10; // rcx
  char *v11; // rcx

  v5 = Entry[2];
  if ( v5 )
    ExFreePoolWithTag(v5, 0x6E664A50u);
  v6 = Entry[9];
  if ( v6 )
    ExFreePoolWithTag(v6, 0x6E664A50u);
  v7 = (struct _FLT_FILE_NAME_INFORMATION *)Entry[4];
  if ( v7 )
    FltReleaseFileNameInformation(v7);
  v8 = Entry[3];
  if ( v8 )
    ObfDereferenceObject(v8);
  v9 = Entry[5];
  if ( v9 )
    FltReleaseContext(v9);
  if ( *Entry )
    PrjfReleaseUnionContext(*Entry, a2, a3, a4);
  v10 = Entry[7];
  if ( v10 )
    PrjfReleaseUnionContext(v10, a2, a3, a4);
  v11 = Entry[10];
  if ( v11 )
    ObfDereferenceObject(v11);
  ExFreeToPagedLookasideList(&Lookaside, Entry);
}

```

## disassembly

```asm
0x140003d9c  push    rbx
0x140003d9e  sub     rsp, 20h
0x140003da2  mov     rbx, rcx
0x140003da5  mov     rcx, [rcx+10h]; P
0x140003da9  test    rcx, rcx
0x140003dac  jz      short loc_140003DBF
0x140003dae  mov     edx, 6E664A50h; Tag
0x140003db3  call    cs:__imp_ExFreePoolWithTag
0x140003dba  nop     dword ptr [rax+rax+00h]
0x140003dbf  mov     rcx, [rbx+48h]; P
0x140003dc3  test    rcx, rcx
0x140003dc6  jz      short loc_140003DD9
0x140003dc8  mov     edx, 6E664A50h; Tag
0x140003dcd  call    cs:__imp_ExFreePoolWithTag
0x140003dd4  nop     dword ptr [rax+rax+00h]
0x140003dd9  mov     rcx, [rbx+20h]; FileNameInformation
0x140003ddd  test    rcx, rcx
0x140003de0  jz      short loc_140003DEE
0x140003de2  call    cs:__imp_FltReleaseFileNameInformation
0x140003de9  nop     dword ptr [rax+rax+00h]
0x140003dee  mov     rcx, [rbx+18h]; Object
0x140003df2  test    rcx, rcx
0x140003df5  jz      short loc_140003E03
0x140003df7  call    cs:__imp_ObfDereferenceObject
0x140003dfe  nop     dword ptr [rax+rax+00h]
0x140003e03  mov     rcx, [rbx+28h]; Context
0x140003e07  test    rcx, rcx
0x140003e0a  jz      short loc_140003E18
0x140003e0c  call    cs:__imp_FltReleaseContext
0x140003e13  nop     dword ptr [rax+rax+00h]
0x140003e18  mov     rcx, [rbx]; P
0x140003e1b  test    rcx, rcx
0x140003e1e  jz      short loc_140003E25
0x140003e20  call    PrjfReleaseUnionContext
0x140003e25  mov     rcx, [rbx+38h]; P
0x140003e29  test    rcx, rcx
0x140003e2c  jz      short loc_140003E33
0x140003e2e  call    PrjfReleaseUnionContext
0x140003e33  mov     rcx, [rbx+50h]; Object
0x140003e37  test    rcx, rcx
0x140003e3a  jz      short loc_140003E48
0x140003e3c  call    cs:__imp_ObfDereferenceObject
0x140003e43  nop     dword ptr [rax+rax+00h]
0x140003e48  mov     rdx, rbx; Entry
0x140003e4b  lea     rcx, Lookaside; Lookaside
0x140003e52  call    cs:__imp_ExFreeToPagedLookasideList
0x140003e59  nop     dword ptr [rax+rax+00h]
0x140003e5e  add     rsp, 20h
0x140003e62  pop     rbx
0x140003e63  retn
```
