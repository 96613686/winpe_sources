# RsnOConnection::CleanupRsnIEs(_NWF_KEY_CONTEXT *)

- ea: `0x140041398`
- end: `0x14004165f`
- name: `?CleanupRsnIEs@RsnOConnection@@YAXPEAU_NWF_KEY_CONTEXT@@@Z`
- size: `711`
- prototype: `void __fastcall(RsnOConnection *__hidden this, struct _NWF_KEY_CONTEXT *)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140045a90`
- `0x1400463a8`
- `0x140046910`
- `0x14004ac7c`
- `0x14004b2f0`

## callees

- `0x140041398`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400413c2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041404`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004144c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041491`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400414d3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041518`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041557`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041599`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400415e1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041629`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400413c2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041404`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004144c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041491`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400414d3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041518`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041557`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041599`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400415e1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041629`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400413d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041415`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004145d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400414a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400414e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041529`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041568`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400415aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400415f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004163a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400413d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041415`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004145d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400414a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400414e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041529`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041568`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400415aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400415f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004163a`

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
0x140041398  mov     [rsp+arg_0], rbx
0x14004139d  push    rdi
0x14004139e  sub     rsp, 20h
0x1400413a2  mov     rbx, rcx
0x1400413a5  xor     edi, edi
0x1400413a7  mov     rcx, [rcx+60h]
0x1400413ab  test    rcx, rcx
0x1400413ae  jz      short loc_1400413DF
0x1400413b0  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400413b4  mov     rax, [rcx]
0x1400413b7  test    rax, rax
0x1400413ba  jz      short loc_1400413D0
0x1400413bc  mov     rdx, rcx; Entry
0x1400413bf  mov     rcx, rax; Lookaside
0x1400413c2  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400413c9  nop     dword ptr [rax+rax+00h]
0x1400413ce  jmp     short loc_1400413DF
0x1400413d0  mov     edx, [rcx+8]; Tag
0x1400413d3  call    cs:__imp_ExFreePoolWithTag
0x1400413da  nop     dword ptr [rax+rax+00h]
0x1400413df  mov     [rbx+60h], rdi
0x1400413e3  mov     [rbx+68h], edi
0x1400413e6  mov     rcx, [rbx+80h]
0x1400413ed  test    rcx, rcx
0x1400413f0  jz      short loc_140041421
0x1400413f2  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400413f6  mov     rax, [rcx]
0x1400413f9  test    rax, rax
0x1400413fc  jz      short loc_140041412
0x1400413fe  mov     rdx, rcx; Entry
0x140041401  mov     rcx, rax; Lookaside
0x140041404  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004140b  nop     dword ptr [rax+rax+00h]
0x140041410  jmp     short loc_140041421
0x140041412  mov     edx, [rcx+8]; Tag
0x140041415  call    cs:__imp_ExFreePoolWithTag
0x14004141c  nop     dword ptr [rax+rax+00h]
0x140041421  mov     [rbx+80h], rdi
0x140041428  mov     [rbx+88h], edi
0x14004142e  mov     rcx, [rbx+90h]
0x140041435  test    rcx, rcx
0x140041438  jz      short loc_140041469
0x14004143a  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004143e  mov     rax, [rcx]
0x140041441  test    rax, rax
0x140041444  jz      short loc_14004145A
0x140041446  mov     rdx, rcx; Entry
0x140041449  mov     rcx, rax; Lookaside
0x14004144c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140041453  nop     dword ptr [rax+rax+00h]
0x140041458  jmp     short loc_140041469
0x14004145a  mov     edx, [rcx+8]; Tag
0x14004145d  call    cs:__imp_ExFreePoolWithTag
0x140041464  nop     dword ptr [rax+rax+00h]
0x140041469  mov     [rbx+90h], rdi
0x140041470  mov     [rbx+98h], edi
0x140041476  mov     rcx, [rbx+70h]
0x14004147a  test    rcx, rcx
0x14004147d  jz      short loc_1400414AE
0x14004147f  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140041483  mov     rax, [rcx]
0x140041486  test    rax, rax
0x140041489  jz      short loc_14004149F
0x14004148b  mov     rdx, rcx; Entry
0x14004148e  mov     rcx, rax; Lookaside
0x140041491  call    cs:__imp_ExFreeToNPagedLookasideList
0x140041498  nop     dword ptr [rax+rax+00h]
0x14004149d  jmp     short loc_1400414AE
0x14004149f  mov     edx, [rcx+8]; Tag
0x1400414a2  call    cs:__imp_ExFreePoolWithTag
0x1400414a9  nop     dword ptr [rax+rax+00h]
0x1400414ae  mov     [rbx+70h], rdi
0x1400414b2  mov     [rbx+78h], edi
0x1400414b5  mov     rcx, [rbx+0A0h]
0x1400414bc  test    rcx, rcx
0x1400414bf  jz      short loc_1400414F0
0x1400414c1  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400414c5  mov     rax, [rcx]
0x1400414c8  test    rax, rax
0x1400414cb  jz      short loc_1400414E1
0x1400414cd  mov     rdx, rcx; Entry
0x1400414d0  mov     rcx, rax; Lookaside
0x1400414d3  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400414da  nop     dword ptr [rax+rax+00h]
0x1400414df  jmp     short loc_1400414F0
0x1400414e1  mov     edx, [rcx+8]; Tag
0x1400414e4  call    cs:__imp_ExFreePoolWithTag
0x1400414eb  nop     dword ptr [rax+rax+00h]
0x1400414f0  mov     [rbx+0A0h], rdi
0x1400414f7  mov     [rbx+0A8h], edi
0x1400414fd  mov     rcx, [rbx+38h]
0x140041501  test    rcx, rcx
0x140041504  jz      short loc_140041535
0x140041506  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004150a  mov     rax, [rcx]
0x14004150d  test    rax, rax
0x140041510  jz      short loc_140041526
0x140041512  mov     rdx, rcx; Entry
0x140041515  mov     rcx, rax; Lookaside
0x140041518  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004151f  nop     dword ptr [rax+rax+00h]
0x140041524  jmp     short loc_140041535
0x140041526  mov     edx, [rcx+8]; Tag
0x140041529  call    cs:__imp_ExFreePoolWithTag
0x140041530  nop     dword ptr [rax+rax+00h]
0x140041535  mov     [rbx+38h], rdi
0x140041539  mov     [rbx+40h], edi
0x14004153c  mov     rcx, [rbx+48h]
0x140041540  test    rcx, rcx
0x140041543  jz      short loc_140041574
0x140041545  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140041549  mov     rax, [rcx]
0x14004154c  test    rax, rax
0x14004154f  jz      short loc_140041565
0x140041551  mov     rdx, rcx; Entry
0x140041554  mov     rcx, rax; Lookaside
0x140041557  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004155e  nop     dword ptr [rax+rax+00h]
0x140041563  jmp     short loc_140041574
0x140041565  mov     edx, [rcx+8]; Tag
0x140041568  call    cs:__imp_ExFreePoolWithTag
0x14004156f  nop     dword ptr [rax+rax+00h]
0x140041574  mov     [rbx+48h], rdi
0x140041578  mov     [rbx+50h], edi
0x14004157b  mov     rcx, [rbx+0B0h]
0x140041582  test    rcx, rcx
0x140041585  jz      short loc_1400415B6
0x140041587  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004158b  mov     rax, [rcx]
0x14004158e  test    rax, rax
0x140041591  jz      short loc_1400415A7
0x140041593  mov     rdx, rcx; Entry
0x140041596  mov     rcx, rax; Lookaside
0x140041599  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400415a0  nop     dword ptr [rax+rax+00h]
0x1400415a5  jmp     short loc_1400415B6
0x1400415a7  mov     edx, [rcx+8]; Tag
0x1400415aa  call    cs:__imp_ExFreePoolWithTag
0x1400415b1  nop     dword ptr [rax+rax+00h]
0x1400415b6  mov     [rbx+0B0h], rdi
0x1400415bd  mov     [rbx+0B8h], edi
0x1400415c3  mov     rcx, [rbx+0C0h]
0x1400415ca  test    rcx, rcx
0x1400415cd  jz      short loc_1400415FE
0x1400415cf  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400415d3  mov     rax, [rcx]
0x1400415d6  test    rax, rax
0x1400415d9  jz      short loc_1400415EF
0x1400415db  mov     rdx, rcx; Entry
0x1400415de  mov     rcx, rax; Lookaside
0x1400415e1  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400415e8  nop     dword ptr [rax+rax+00h]
0x1400415ed  jmp     short loc_1400415FE
0x1400415ef  mov     edx, [rcx+8]; Tag
0x1400415f2  call    cs:__imp_ExFreePoolWithTag
0x1400415f9  nop     dword ptr [rax+rax+00h]
0x1400415fe  mov     [rbx+0C0h], rdi
0x140041605  mov     [rbx+0C8h], edi
0x14004160b  mov     rcx, [rbx+0D0h]
0x140041612  test    rcx, rcx
0x140041615  jz      short loc_140041646
0x140041617  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004161b  mov     rax, [rcx]
0x14004161e  test    rax, rax
0x140041621  jz      short loc_140041637
0x140041623  mov     rdx, rcx; Entry
0x140041626  mov     rcx, rax; Lookaside
0x140041629  call    cs:__imp_ExFreeToNPagedLookasideList
0x140041630  nop     dword ptr [rax+rax+00h]
0x140041635  jmp     short loc_140041646
0x140041637  mov     edx, [rcx+8]; Tag
0x14004163a  call    cs:__imp_ExFreePoolWithTag
0x140041641  nop     dword ptr [rax+rax+00h]
0x140041646  mov     [rbx+0D0h], rdi
0x14004164d  mov     [rbx+0D8h], edi
0x140041653  mov     rbx, [rsp+28h+arg_0]
0x140041658  add     rsp, 20h
0x14004165c  pop     rdi
0x14004165d  retn
```
