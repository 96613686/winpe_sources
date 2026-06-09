# wlansecurity::crypto::impl::details::Kdf(void *,utl::span<uchar const,-1>,utl::span<uchar const,-1>,utl::span<uchar const,-1>,utl::span<uchar,-1>)

- ea: `0x14000b440`
- end: `0x14000b791`
- name: `?Kdf@details@impl@crypto@wlansecurity@@YAJPEAXV?$span@$$CBE$0?0@utl@@11V?$span@E$0?0@6@@Z`
- size: `849`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140023dac`
- `0x140024f14`

## callees

- `0x14000599c`
- `0x14000b440`
- `0x14000ba58`
- `0x140020aa4`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b54b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b57a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b68d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b6bc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b705`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b734`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b76a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b54b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b57a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b68d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b6bc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b705`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b734`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b76a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b55c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b5a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b69e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b6cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b716`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b745`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b77b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b55c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b5a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b69e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b6cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b716`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b745`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b77b`

## pseudocode

```c
__int64 __fastcall wlansecurity::crypto::impl::details::Kdf(
        wlansecurity::crypto::impl::details *a1,
        __int128 *a2,
        __int64 a3,
        __int64 a4,
        void **a5)
{
  unsigned int HashLength; // eax
  const struct std::nothrow_t *v8; // rdx
  size_t v9; // rsi
  size_t v10; // rdi
  unsigned int v11; // ebp
  unsigned __int64 v12; // r12
  const struct std::nothrow_t *v13; // rdx
  unsigned __int16 *v14; // rbx
  size_t v15; // r14
  _BYTE *v16; // rbp
  const void *v17; // rdx
  size_t v18; // r13
  unsigned __int64 v19; // rdx
  _BYTE *v20; // rax
  unsigned __int16 i; // cx
  int v23; // edi
  size_t v24; // rsi
  char *v25; // rdi
  _BYTE *v26; // rax
  _BYTE *v27; // rax
  _QWORD v28[2]; // [rsp+30h] [rbp-78h] BYREF
  _QWORD v29[2]; // [rsp+40h] [rbp-68h] BYREF
  __int128 v30[5]; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int16 v33; // [rsp+C0h] [rbp+18h]
  unsigned __int64 v34; // [rsp+C8h] [rbp+20h]

  HashLength = wlansecurity::crypto::impl::details::GetHashLength(a1, a2);
  v9 = *(_QWORD *)(a3 + 8);
  v10 = *(_QWORD *)(a4 + 8);
  v11 = HashLength;
  v12 = v9 + v10 + 4;
  if ( v12 < v9 || v12 < v10 || v12 < 4 )
    return 3221225485LL;
  v14 = (unsigned __int16 *)operator new(v9 + v10 + 4, v8);
  if ( !v14 )
    return 3221225495LL;
  v15 = v11;
  v16 = operator new(v11, v13);
  if ( !v16 )
  {
    if ( *((_QWORD *)v14 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v14 - 2), v14 - 8);
    else
      ExFreePoolWithTag(v14 - 8, *((_DWORD *)v14 - 2));
    return 3221225495LL;
  }
  v17 = *(const void **)a3;
  *v14 = 0;
  memmove(v14 + 1, v17, v9);
  memmove((char *)v14 + v9 + 2, *(const void **)a4, v10);
  v18 = (size_t)a5[1];
  *(unsigned __int16 *)((char *)v14 + v12 - 2) = 8 * v18;
  v34 = (v15 + v18 - 1) / v15;
  v19 = v34;
  if ( v34 > 0xFFFF )
  {
    v20 = v16;
    do
    {
      *v20++ = 0;
      --v15;
    }
    while ( v15 );
    if ( *((_QWORD *)v16 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v16 - 2), v16 - 16);
    else
      ExFreePoolWithTag(v16 - 16, *((_DWORD *)v16 - 2));
    if ( *((_QWORD *)v14 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v14 - 2), v14 - 8);
    else
      ExFreePoolWithTag(v14 - 8, *((_DWORD *)v14 - 2));
    return 3221225485LL;
  }
  for ( i = 1; ; i = v33 + 1 )
  {
    v33 = i;
    if ( i > v19 )
      break;
    *v14 = i;
    v28[0] = v16;
    v30[0] = *a2;
    v28[1] = v15;
    v29[0] = v14;
    v29[1] = v12;
    v23 = wlansecurity::crypto::impl::details::Hash(a1, v29, v30, v28);
    if ( v23 < 0 )
    {
      v26 = v16;
      do
      {
        *v26++ = 0;
        --v15;
      }
      while ( v15 );
      if ( *((_QWORD *)v16 - 2) )
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v16 - 2), v16 - 16);
      else
        ExFreePoolWithTag(v16 - 16, *((_DWORD *)v16 - 2));
      if ( *((_QWORD *)v14 - 2) )
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v14 - 2), v14 - 8);
      else
        ExFreePoolWithTag(v14 - 8, *((_DWORD *)v14 - 2));
      return (unsigned int)v23;
    }
    v24 = v15;
    if ( v15 >= v18 )
      v24 = v18;
    v25 = (char *)*a5;
    memmove(*a5, v16, v24);
    v19 = v34;
    v18 -= v24;
    *a5 = &v25[v24];
    a5[1] = (void *)v18;
  }
  v27 = v16;
  do
  {
    *v27++ = 0;
    --v15;
  }
  while ( v15 );
  if ( *((_QWORD *)v16 - 2) )
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v16 - 2), v16 - 16);
  else
    ExFreePoolWithTag(v16 - 16, *((_DWORD *)v16 - 2));
  if ( *((_QWORD *)v14 - 2) )
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v14 - 2), v14 - 8);
  else
    ExFreePoolWithTag(v14 - 8, *((_DWORD *)v14 - 2));
  return 0;
}

```

## disassembly

```asm
0x14000b440  mov     [rsp+arg_8], rdx
0x14000b445  mov     [rsp+arg_0], rcx
0x14000b44a  push    rbx
0x14000b44b  push    rbp
0x14000b44c  push    rsi
0x14000b44d  push    rdi
0x14000b44e  push    r12
0x14000b450  push    r13
0x14000b452  push    r14
0x14000b454  push    r15
0x14000b456  sub     rsp, 68h
0x14000b45a  mov     r15, r9
0x14000b45d  mov     r13, r8
0x14000b460  call    ?GetHashLength@details@impl@crypto@wlansecurity@@YAKQEAX@Z; wlansecurity::crypto::impl::details::GetHashLength(void * const)
0x14000b465  mov     rsi, [r13+8]
0x14000b469  mov     rdi, [r15+8]
0x14000b46d  mov     ebp, eax
0x14000b46f  lea     r12, [rdi+4]
0x14000b473  add     r12, rsi
0x14000b476  cmp     r12, rsi
0x14000b479  jb      loc_14000B586
0x14000b47f  cmp     r12, rdi
0x14000b482  jb      loc_14000B586
0x14000b488  cmp     r12, 4
0x14000b48c  jb      loc_14000B586
0x14000b492  mov     rcx, r12; unsigned __int64
0x14000b495  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000b49a  mov     rbx, rax
0x14000b49d  test    rax, rax
0x14000b4a0  jz      loc_14000B787
0x14000b4a6  mov     ecx, ebp; unsigned __int64
0x14000b4a8  mov     r14d, ebp
0x14000b4ab  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000b4b0  mov     rbp, rax
0x14000b4b3  test    rax, rax
0x14000b4b6  jz      loc_14000B758
0x14000b4bc  mov     rdx, [r13+0]; Src
0x14000b4c0  lea     rcx, [rbx+2]; void *
0x14000b4c4  xor     eax, eax
0x14000b4c6  mov     r8, rsi; Size
0x14000b4c9  mov     [rbx], ax
0x14000b4cc  call    memmove
0x14000b4d1  mov     rdx, [r15]; Src
0x14000b4d4  lea     rcx, [rsi+2]
0x14000b4d8  add     rcx, rbx; void *
0x14000b4db  mov     r8, rdi; Size
0x14000b4de  call    memmove
0x14000b4e3  mov     r13, [rsp+0A8h+arg_20]
0x14000b4eb  xor     edx, edx
0x14000b4ed  mov     r13, [r13+8]
0x14000b4f1  movzx   eax, r13w
0x14000b4f5  shl     ax, 3
0x14000b4f9  mov     [rbx+r12-2], ax
0x14000b4ff  lea     rax, [r13-1]
0x14000b503  add     rax, r14
0x14000b506  div     r14
0x14000b509  mov     [rsp+0A8h+arg_18], rax
0x14000b511  mov     rdx, rax
0x14000b514  cmp     rax, 0FFFFh
0x14000b51a  jbe     loc_14000B5AE
0x14000b520  mov     rax, rbp
0x14000b523  test    r14, r14
0x14000b526  jz      short loc_14000B539
0x14000b528  mov     r15d, 1
0x14000b52e  mov     byte ptr [rax], 0
0x14000b531  add     rax, r15
0x14000b534  sub     r14, r15
0x14000b537  jnz     short loc_14000B52E
0x14000b539  lea     rcx, [rbp-10h]; P
0x14000b53d  mov     rax, [rcx]
0x14000b540  test    rax, rax
0x14000b543  jz      short loc_14000B559
0x14000b545  mov     rdx, rcx; Entry
0x14000b548  mov     rcx, rax; Lookaside
0x14000b54b  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b552  nop     dword ptr [rax+rax+00h]
0x14000b557  jmp     short loc_14000B568
0x14000b559  mov     edx, [rcx+8]; Tag
0x14000b55c  call    cs:__imp_ExFreePoolWithTag
0x14000b563  nop     dword ptr [rax+rax+00h]
0x14000b568  lea     rcx, [rbx-10h]; P
0x14000b56c  mov     rax, [rcx]
0x14000b56f  test    rax, rax
0x14000b572  jz      short loc_14000B59D
0x14000b574  mov     rdx, rcx; Entry
0x14000b577  mov     rcx, rax; Lookaside
0x14000b57a  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b581  nop     dword ptr [rax+rax+00h]
0x14000b586  mov     eax, 0C000000Dh
0x14000b58b  add     rsp, 68h
0x14000b58f  pop     r15
0x14000b591  pop     r14
0x14000b593  pop     r13
0x14000b595  pop     r12
0x14000b597  pop     rdi
0x14000b598  pop     rsi
0x14000b599  pop     rbp
0x14000b59a  pop     rbx
0x14000b59b  retn
0x14000b59d  mov     edx, [rcx+8]; Tag
0x14000b5a0  call    cs:__imp_ExFreePoolWithTag
0x14000b5a7  nop     dword ptr [rax+rax+00h]
0x14000b5ac  jmp     short loc_14000B586
0x14000b5ae  mov     r15d, 1
0x14000b5b4  movzx   ecx, r15w
0x14000b5b8  movzx   eax, cx
0x14000b5bb  mov     [rsp+0A8h+arg_10], cx
0x14000b5c3  cmp     rax, rdx
0x14000b5c6  ja      loc_14000B6E0
0x14000b5cc  mov     rax, [rsp+0A8h+arg_8]
0x14000b5d4  lea     r9, [rsp+0A8h+var_78]
0x14000b5d9  mov     [rbx], cx
0x14000b5dc  lea     r8, [rsp+0A8h+var_58]
0x14000b5e1  mov     rcx, [rsp+0A8h+arg_0]
0x14000b5e9  lea     rdx, [rsp+0A8h+var_68]
0x14000b5ee  mov     [rsp+0A8h+var_78], rbp
0x14000b5f3  movaps  xmm0, xmmword ptr [rax]
0x14000b5f6  movdqu  [rsp+0A8h+var_58], xmm0
0x14000b5fc  mov     [rsp+0A8h+var_70], r14
0x14000b601  mov     [rsp+0A8h+var_68], rbx
0x14000b606  mov     [rsp+0A8h+var_60], r12
0x14000b60b  call    ?Hash@details@impl@crypto@wlansecurity@@YAJPEAXV?$span@$$CBE$0?0@utl@@1V?$span@E$0?0@6@@Z; wlansecurity::crypto::impl::details::Hash(void *,utl::span<uchar const,-1>,utl::span<uchar const,-1>,utl::span<uchar,-1>)
0x14000b610  mov     edi, eax
0x14000b612  test    eax, eax
0x14000b614  js      short loc_14000B668
0x14000b616  mov     rax, [rsp+0A8h+arg_20]
0x14000b61e  cmp     r14, r13
0x14000b621  mov     rsi, r14
0x14000b624  mov     rdx, rbp; Src
0x14000b627  cmovnb  rsi, r13
0x14000b62b  mov     r8, rsi; Size
0x14000b62e  mov     rdi, [rax]
0x14000b631  mov     rcx, rdi; void *
0x14000b634  call    memmove
0x14000b639  mov     rcx, [rsp+0A8h+arg_20]
0x14000b641  lea     rax, [rdi+rsi]
0x14000b645  mov     rdx, [rsp+0A8h+arg_18]
0x14000b64d  sub     r13, rsi
0x14000b650  mov     [rcx], rax
0x14000b653  mov     [rcx+8], r13
0x14000b657  movzx   ecx, [rsp+0A8h+arg_10]
0x14000b65f  add     cx, r15w
0x14000b663  jmp     loc_14000B5B8
0x14000b668  mov     rax, rbp
0x14000b66b  test    r14, r14
0x14000b66e  jz      short loc_14000B67B
0x14000b670  mov     byte ptr [rax], 0
0x14000b673  add     rax, r15
0x14000b676  sub     r14, r15
0x14000b679  jnz     short loc_14000B670
0x14000b67b  lea     rcx, [rbp-10h]; P
0x14000b67f  mov     rax, [rcx]
0x14000b682  test    rax, rax
0x14000b685  jz      short loc_14000B69B
0x14000b687  mov     rdx, rcx; Entry
0x14000b68a  mov     rcx, rax; Lookaside
0x14000b68d  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b694  nop     dword ptr [rax+rax+00h]
0x14000b699  jmp     short loc_14000B6AA
0x14000b69b  mov     edx, [rcx+8]; Tag
0x14000b69e  call    cs:__imp_ExFreePoolWithTag
0x14000b6a5  nop     dword ptr [rax+rax+00h]
0x14000b6aa  lea     rcx, [rbx-10h]; P
0x14000b6ae  mov     rax, [rcx]
0x14000b6b1  test    rax, rax
0x14000b6b4  jz      short loc_14000B6CA
0x14000b6b6  mov     rdx, rcx; Entry
0x14000b6b9  mov     rcx, rax; Lookaside
0x14000b6bc  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b6c3  nop     dword ptr [rax+rax+00h]
0x14000b6c8  jmp     short loc_14000B6D9
0x14000b6ca  mov     edx, [rcx+8]; Tag
0x14000b6cd  call    cs:__imp_ExFreePoolWithTag
0x14000b6d4  nop     dword ptr [rax+rax+00h]
0x14000b6d9  mov     eax, edi
0x14000b6db  jmp     loc_14000B58B
0x14000b6e0  mov     rax, rbp
0x14000b6e3  test    r14, r14
0x14000b6e6  jz      short loc_14000B6F3
0x14000b6e8  mov     byte ptr [rax], 0
0x14000b6eb  add     rax, r15
0x14000b6ee  sub     r14, r15
0x14000b6f1  jnz     short loc_14000B6E8
0x14000b6f3  lea     rcx, [rbp-10h]; P
0x14000b6f7  mov     rax, [rcx]
0x14000b6fa  test    rax, rax
0x14000b6fd  jz      short loc_14000B713
0x14000b6ff  mov     rdx, rcx; Entry
0x14000b702  mov     rcx, rax; Lookaside
0x14000b705  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b70c  nop     dword ptr [rax+rax+00h]
0x14000b711  jmp     short loc_14000B722
0x14000b713  mov     edx, [rcx+8]; Tag
0x14000b716  call    cs:__imp_ExFreePoolWithTag
0x14000b71d  nop     dword ptr [rax+rax+00h]
0x14000b722  lea     rcx, [rbx-10h]; P
0x14000b726  mov     rax, [rcx]
0x14000b729  test    rax, rax
0x14000b72c  jz      short loc_14000B742
0x14000b72e  mov     rdx, rcx; Entry
0x14000b731  mov     rcx, rax; Lookaside
0x14000b734  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b73b  nop     dword ptr [rax+rax+00h]
0x14000b740  jmp     short loc_14000B751
0x14000b742  mov     edx, [rcx+8]; Tag
0x14000b745  call    cs:__imp_ExFreePoolWithTag
0x14000b74c  nop     dword ptr [rax+rax+00h]
0x14000b751  xor     eax, eax
0x14000b753  jmp     loc_14000B58B
0x14000b758  lea     rcx, [rbx-10h]; P
0x14000b75c  mov     rax, [rcx]
0x14000b75f  test    rax, rax
0x14000b762  jz      short loc_14000B778
0x14000b764  mov     rdx, rcx; Entry
0x14000b767  mov     rcx, rax; Lookaside
0x14000b76a  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b771  nop     dword ptr [rax+rax+00h]
0x14000b776  jmp     short loc_14000B787
0x14000b778  mov     edx, [rcx+8]; Tag
0x14000b77b  call    cs:__imp_ExFreePoolWithTag
0x14000b782  nop     dword ptr [rax+rax+00h]
0x14000b787  mov     eax, 0C0000017h
0x14000b78c  jmp     loc_14000B58B
```
