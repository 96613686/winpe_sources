# PrjfReleaseRenameOrLinkCompletionContext

- ea: `0x140003d9c`
- end: `0x140003e65`
- name: `PrjfReleaseRenameOrLinkCompletionContext`
- size: `201`
- prototype: `void __fastcall(PVOID *Entry)`
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
void __fastcall PrjfReleaseRenameOrLinkCompletionContext(PVOID *Entry)
{
  PVOID v2; // rcx
  PVOID v3; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v4; // rcx
  PVOID v5; // rcx
  PVOID v6; // rcx
  PVOID v7; // rcx
  PVOID v8; // rcx

  v2 = Entry[2];
  if ( v2 )
    ExFreePoolWithTag(v2, 0x6E664A50u);
  v3 = Entry[9];
  if ( v3 )
    ExFreePoolWithTag(v3, 0x6E664A50u);
  v4 = (struct _FLT_FILE_NAME_INFORMATION *)Entry[4];
  if ( v4 )
    FltReleaseFileNameInformation(v4);
  v5 = Entry[3];
  if ( v5 )
    ObfDereferenceObject(v5);
  v6 = Entry[5];
  if ( v6 )
    FltReleaseContext(v6);
  if ( *Entry )
    PrjfReleaseUnionContext(*Entry);
  v7 = Entry[7];
  if ( v7 )
    PrjfReleaseUnionContext(v7);
  v8 = Entry[10];
  if ( v8 )
    ObfDereferenceObject(v8);
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
