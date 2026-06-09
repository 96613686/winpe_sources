# RsnOConnection::CleanupRsnIEs(_NWF_KEY_CONTEXT *)

- ea: `0x140041e34`
- end: `0x1400420fb`
- name: `?CleanupRsnIEs@RsnOConnection@@YAXPEAU_NWF_KEY_CONTEXT@@@Z`
- size: `711`
- prototype: `void __fastcall(RsnOConnection *__hidden this, struct _NWF_KEY_CONTEXT *)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140046610`
- `0x140046f4c`
- `0x1400474b4`
- `0x14004bf04`
- `0x14004c578`

## callees

- `0x140041e34`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041e5e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041ea0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041ee8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041f2d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041f6f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041fb4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041ff3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140042035`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004207d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400420c5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041e5e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041ea0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041ee8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041f2d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041f6f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041fb4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041ff3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140042035`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004207d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400420c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041e6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041eb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041ef9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041f3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041f80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041fc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042004`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042046`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004208e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400420d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041e6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041eb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041ef9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041f3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041f80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041fc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042004`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042046`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004208e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400420d6`

## pseudocode

```c
void __fastcall RsnOConnection::CleanupRsnIEs(RsnOConnection *this, struct _NWF_KEY_CONTEXT *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx

  v3 = *((_QWORD *)this + 12);
  if ( v3 )
  {
    v4 = v3 - 16;
    if ( *(_QWORD *)v4 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v4, (PVOID)v4);
    else
      ExFreePoolWithTag((PVOID)v4, *(_DWORD *)(v4 + 8));
  }
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 26) = 0;
  v5 = *((_QWORD *)this + 16);
  if ( v5 )
  {
    v6 = v5 - 16;
    if ( *(_QWORD *)v6 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v6, (PVOID)v6);
    else
      ExFreePoolWithTag((PVOID)v6, *(_DWORD *)(v6 + 8));
  }
  *((_QWORD *)this + 16) = 0;
  *((_DWORD *)this + 34) = 0;
  v7 = *((_QWORD *)this + 18);
  if ( v7 )
  {
    v8 = v7 - 16;
    if ( *(_QWORD *)v8 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v8, (PVOID)v8);
    else
      ExFreePoolWithTag((PVOID)v8, *(_DWORD *)(v8 + 8));
  }
  *((_QWORD *)this + 18) = 0;
  *((_DWORD *)this + 38) = 0;
  v9 = *((_QWORD *)this + 14);
  if ( v9 )
  {
    v10 = v9 - 16;
    if ( *(_QWORD *)v10 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v10, (PVOID)v10);
    else
      ExFreePoolWithTag((PVOID)v10, *(_DWORD *)(v10 + 8));
  }
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = 0;
  v11 = *((_QWORD *)this + 20);
  if ( v11 )
  {
    v12 = v11 - 16;
    if ( *(_QWORD *)v12 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v12, (PVOID)v12);
    else
      ExFreePoolWithTag((PVOID)v12, *(_DWORD *)(v12 + 8));
  }
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 42) = 0;
  v13 = *((_QWORD *)this + 7);
  if ( v13 )
  {
    v14 = v13 - 16;
    if ( *(_QWORD *)v14 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v14, (PVOID)v14);
    else
      ExFreePoolWithTag((PVOID)v14, *(_DWORD *)(v14 + 8));
  }
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  v15 = *((_QWORD *)this + 9);
  if ( v15 )
  {
    v16 = v15 - 16;
    if ( *(_QWORD *)v16 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v16, (PVOID)v16);
    else
      ExFreePoolWithTag((PVOID)v16, *(_DWORD *)(v16 + 8));
  }
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  v17 = *((_QWORD *)this + 22);
  if ( v17 )
  {
    v18 = v17 - 16;
    if ( *(_QWORD *)v18 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v18, (PVOID)v18);
    else
      ExFreePoolWithTag((PVOID)v18, *(_DWORD *)(v18 + 8));
  }
  *((_QWORD *)this + 22) = 0;
  *((_DWORD *)this + 46) = 0;
  v19 = *((_QWORD *)this + 24);
  if ( v19 )
  {
    v20 = v19 - 16;
    if ( *(_QWORD *)v20 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v20, (PVOID)v20);
    else
      ExFreePoolWithTag((PVOID)v20, *(_DWORD *)(v20 + 8));
  }
  *((_QWORD *)this + 24) = 0;
  *((_DWORD *)this + 50) = 0;
  v21 = *((_QWORD *)this + 26);
  if ( v21 )
  {
    v22 = v21 - 16;
    if ( *(_QWORD *)v22 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v22, (PVOID)v22);
    else
      ExFreePoolWithTag((PVOID)v22, *(_DWORD *)(v22 + 8));
  }
  *((_QWORD *)this + 26) = 0;
  *((_DWORD *)this + 54) = 0;
}

```

## disassembly

```asm
0x140041e34  mov     [rsp+arg_0], rbx
0x140041e39  push    rdi
0x140041e3a  sub     rsp, 20h
0x140041e3e  mov     rbx, rcx
0x140041e41  xor     edi, edi
0x140041e43  mov     rcx, [rcx+60h]
0x140041e47  test    rcx, rcx
0x140041e4a  jz      short loc_140041E7B
0x140041e4c  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140041e50  mov     rax, [rcx]
0x140041e53  test    rax, rax
0x140041e56  jz      short loc_140041E6C
0x140041e58  mov     rdx, rcx; Entry
0x140041e5b  mov     rcx, rax; Lookaside
0x140041e5e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140041e65  nop     dword ptr [rax+rax+00h]
0x140041e6a  jmp     short loc_140041E7B
0x140041e6c  mov     edx, [rcx+8]; Tag
0x140041e6f  call    cs:__imp_ExFreePoolWithTag
0x140041e76  nop     dword ptr [rax+rax+00h]
0x140041e7b  mov     [rbx+60h], rdi
0x140041e7f  mov     [rbx+68h], edi
0x140041e82  mov     rcx, [rbx+80h]
0x140041e89  test    rcx, rcx
0x140041e8c  jz      short loc_140041EBD
0x140041e8e  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140041e92  mov     rax, [rcx]
0x140041e95  test    rax, rax
0x140041e98  jz      short loc_140041EAE
0x140041e9a  mov     rdx, rcx; Entry
0x140041e9d  mov     rcx, rax; Lookaside
0x140041ea0  call    cs:__imp_ExFreeToNPagedLookasideList
0x140041ea7  nop     dword ptr [rax+rax+00h]
0x140041eac  jmp     short loc_140041EBD
0x140041eae  mov     edx, [rcx+8]; Tag
0x140041eb1  call    cs:__imp_ExFreePoolWithTag
0x140041eb8  nop     dword ptr [rax+rax+00h]
0x140041ebd  mov     [rbx+80h], rdi
0x140041ec4  mov     [rbx+88h], edi
0x140041eca  mov     rcx, [rbx+90h]
0x140041ed1  test    rcx, rcx
0x140041ed4  jz      short loc_140041F05
0x140041ed6  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140041eda  mov     rax, [rcx]
0x140041edd  test    rax, rax
0x140041ee0  jz      short loc_140041EF6
0x140041ee2  mov     rdx, rcx; Entry
0x140041ee5  mov     rcx, rax; Lookaside
0x140041ee8  call    cs:__imp_ExFreeToNPagedLookasideList
0x140041eef  nop     dword ptr [rax+rax+00h]
0x140041ef4  jmp     short loc_140041F05
0x140041ef6  mov     edx, [rcx+8]; Tag
0x140041ef9  call    cs:__imp_ExFreePoolWithTag
0x140041f00  nop     dword ptr [rax+rax+00h]
0x140041f05  mov     [rbx+90h], rdi
0x140041f0c  mov     [rbx+98h], edi
0x140041f12  mov     rcx, [rbx+70h]
0x140041f16  test    rcx, rcx
0x140041f19  jz      short loc_140041F4A
0x140041f1b  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140041f1f  mov     rax, [rcx]
0x140041f22  test    rax, rax
0x140041f25  jz      short loc_140041F3B
0x140041f27  mov     rdx, rcx; Entry
0x140041f2a  mov     rcx, rax; Lookaside
0x140041f2d  call    cs:__imp_ExFreeToNPagedLookasideList
0x140041f34  nop     dword ptr [rax+rax+00h]
0x140041f39  jmp     short loc_140041F4A
0x140041f3b  mov     edx, [rcx+8]; Tag
0x140041f3e  call    cs:__imp_ExFreePoolWithTag
0x140041f45  nop     dword ptr [rax+rax+00h]
0x140041f4a  mov     [rbx+70h], rdi
0x140041f4e  mov     [rbx+78h], edi
0x140041f51  mov     rcx, [rbx+0A0h]
0x140041f58  test    rcx, rcx
0x140041f5b  jz      short loc_140041F8C
0x140041f5d  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140041f61  mov     rax, [rcx]
0x140041f64  test    rax, rax
0x140041f67  jz      short loc_140041F7D
0x140041f69  mov     rdx, rcx; Entry
0x140041f6c  mov     rcx, rax; Lookaside
0x140041f6f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140041f76  nop     dword ptr [rax+rax+00h]
0x140041f7b  jmp     short loc_140041F8C
0x140041f7d  mov     edx, [rcx+8]; Tag
0x140041f80  call    cs:__imp_ExFreePoolWithTag
0x140041f87  nop     dword ptr [rax+rax+00h]
0x140041f8c  mov     [rbx+0A0h], rdi
0x140041f93  mov     [rbx+0A8h], edi
0x140041f99  mov     rcx, [rbx+38h]
0x140041f9d  test    rcx, rcx
0x140041fa0  jz      short loc_140041FD1
0x140041fa2  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140041fa6  mov     rax, [rcx]
0x140041fa9  test    rax, rax
0x140041fac  jz      short loc_140041FC2
0x140041fae  mov     rdx, rcx; Entry
0x140041fb1  mov     rcx, rax; Lookaside
0x140041fb4  call    cs:__imp_ExFreeToNPagedLookasideList
0x140041fbb  nop     dword ptr [rax+rax+00h]
0x140041fc0  jmp     short loc_140041FD1
0x140041fc2  mov     edx, [rcx+8]; Tag
0x140041fc5  call    cs:__imp_ExFreePoolWithTag
0x140041fcc  nop     dword ptr [rax+rax+00h]
0x140041fd1  mov     [rbx+38h], rdi
0x140041fd5  mov     [rbx+40h], edi
0x140041fd8  mov     rcx, [rbx+48h]
0x140041fdc  test    rcx, rcx
0x140041fdf  jz      short loc_140042010
0x140041fe1  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140041fe5  mov     rax, [rcx]
0x140041fe8  test    rax, rax
0x140041feb  jz      short loc_140042001
0x140041fed  mov     rdx, rcx; Entry
0x140041ff0  mov     rcx, rax; Lookaside
0x140041ff3  call    cs:__imp_ExFreeToNPagedLookasideList
0x140041ffa  nop     dword ptr [rax+rax+00h]
0x140041fff  jmp     short loc_140042010
0x140042001  mov     edx, [rcx+8]; Tag
0x140042004  call    cs:__imp_ExFreePoolWithTag
0x14004200b  nop     dword ptr [rax+rax+00h]
0x140042010  mov     [rbx+48h], rdi
0x140042014  mov     [rbx+50h], edi
0x140042017  mov     rcx, [rbx+0B0h]
0x14004201e  test    rcx, rcx
0x140042021  jz      short loc_140042052
0x140042023  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140042027  mov     rax, [rcx]
0x14004202a  test    rax, rax
0x14004202d  jz      short loc_140042043
0x14004202f  mov     rdx, rcx; Entry
0x140042032  mov     rcx, rax; Lookaside
0x140042035  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004203c  nop     dword ptr [rax+rax+00h]
0x140042041  jmp     short loc_140042052
0x140042043  mov     edx, [rcx+8]; Tag
0x140042046  call    cs:__imp_ExFreePoolWithTag
0x14004204d  nop     dword ptr [rax+rax+00h]
0x140042052  mov     [rbx+0B0h], rdi
0x140042059  mov     [rbx+0B8h], edi
0x14004205f  mov     rcx, [rbx+0C0h]
0x140042066  test    rcx, rcx
0x140042069  jz      short loc_14004209A
0x14004206b  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004206f  mov     rax, [rcx]
0x140042072  test    rax, rax
0x140042075  jz      short loc_14004208B
0x140042077  mov     rdx, rcx; Entry
0x14004207a  mov     rcx, rax; Lookaside
0x14004207d  call    cs:__imp_ExFreeToNPagedLookasideList
0x140042084  nop     dword ptr [rax+rax+00h]
0x140042089  jmp     short loc_14004209A
0x14004208b  mov     edx, [rcx+8]; Tag
0x14004208e  call    cs:__imp_ExFreePoolWithTag
0x140042095  nop     dword ptr [rax+rax+00h]
0x14004209a  mov     [rbx+0C0h], rdi
0x1400420a1  mov     [rbx+0C8h], edi
0x1400420a7  mov     rcx, [rbx+0D0h]
0x1400420ae  test    rcx, rcx
0x1400420b1  jz      short loc_1400420E2
0x1400420b3  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400420b7  mov     rax, [rcx]
0x1400420ba  test    rax, rax
0x1400420bd  jz      short loc_1400420D3
0x1400420bf  mov     rdx, rcx; Entry
0x1400420c2  mov     rcx, rax; Lookaside
0x1400420c5  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400420cc  nop     dword ptr [rax+rax+00h]
0x1400420d1  jmp     short loc_1400420E2
0x1400420d3  mov     edx, [rcx+8]; Tag
0x1400420d6  call    cs:__imp_ExFreePoolWithTag
0x1400420dd  nop     dword ptr [rax+rax+00h]
0x1400420e2  mov     [rbx+0D0h], rdi
0x1400420e9  mov     [rbx+0D8h], edi
0x1400420ef  mov     rbx, [rsp+28h+arg_0]
0x1400420f4  add     rsp, 20h
0x1400420f8  pop     rdi
0x1400420f9  retn
```
