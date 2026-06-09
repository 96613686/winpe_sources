# wlansecurity::crypto::impl::details::Prf(void *,utl::span<uchar const,-1>,utl::span<uchar const,-1>,utl::span<uchar const,-1>,utl::span<uchar,-1>)

- ea: `0x14000b130`
- end: `0x14000b3e8`
- name: `?Prf@details@impl@crypto@wlansecurity@@YAJPEAXV?$span@$$CBE$0?0@utl@@11V?$span@E$0?0@6@@Z`
- size: `696`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000b7a0`

## callees

- `0x14000599c`
- `0x14000b130`
- `0x14000ba58`
- `0x140020aa4`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b2d0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b2ff`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b344`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b373`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b3a6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b2d0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b2ff`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b344`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b373`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b3a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b2e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b310`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b355`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b384`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b3b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b2e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b310`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b355`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b384`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b3b7`

## pseudocode

```c
__int64 __fastcall wlansecurity::crypto::impl::details::Prf(
        wlansecurity::crypto::impl::details *a1,
        __int128 *a2,
        __int64 a3,
        __int64 a4,
        void **a5)
{
  const struct std::nothrow_t *v7; // rdx
  unsigned int HashLength; // ebx
  size_t v9; // rsi
  size_t v10; // r14
  size_t v11; // r15
  const struct std::nothrow_t *v12; // rdx
  PNPAGED_LOOKASIDE_LIST *v13; // rdi
  size_t v14; // rbp
  _BYTE *v15; // rbx
  const void *v16; // rdx
  size_t v17; // r12
  unsigned __int64 v18; // rdx
  unsigned int v19; // eax
  int v20; // esi
  size_t v21; // r14
  char *v22; // rsi
  _BYTE *v23; // rax
  _BYTE *v25; // rax
  unsigned int v26; // [rsp+20h] [rbp-88h]
  unsigned __int64 v27; // [rsp+28h] [rbp-80h]
  _QWORD v28[2]; // [rsp+40h] [rbp-68h] BYREF
  _QWORD v29[2]; // [rsp+50h] [rbp-58h] BYREF
  __int128 v30[4]; // [rsp+60h] [rbp-48h] BYREF

  HashLength = wlansecurity::crypto::impl::details::GetHashLength(a1, a2);
  if ( !HashLength )
    return 3221225485LL;
  v9 = *(_QWORD *)(a3 + 8);
  v10 = *(_QWORD *)(a4 + 8);
  v11 = v9 + v10 + 2;
  if ( v11 < v9 || v11 < v10 || !v11 )
    return 3221225485LL;
  v13 = (PNPAGED_LOOKASIDE_LIST *)operator new(v9 + v10 + 2, v7);
  if ( !v13 )
    return 3221225495LL;
  v14 = HashLength;
  v15 = operator new(HashLength, v12);
  if ( !v15 )
  {
    if ( *(v13 - 2) )
      ExFreeToNPagedLookasideList(*(v13 - 2), v13 - 2);
    else
      ExFreePoolWithTag(v13 - 2, *((_DWORD *)v13 - 2));
    return 3221225495LL;
  }
  memmove(v13, *(const void **)a3, v9);
  v16 = *(const void **)a4;
  *((_BYTE *)v13 + v9) = 0;
  memmove((char *)v13 + v9 + 1, v16, v10);
  *((_BYTE *)v13 + v11 - 1) = 0;
  v17 = (size_t)a5[1];
  v18 = (v14 + v17 - 1) / v14;
  v27 = v18;
  v19 = 0;
  while ( 1 )
  {
    v26 = v19;
    if ( v19 >= v18 )
      break;
    v28[0] = v15;
    v28[1] = v14;
    v29[0] = v13;
    v30[0] = *a2;
    v29[1] = v11;
    v20 = wlansecurity::crypto::impl::details::Hash(a1, v29, v30, v28);
    if ( v20 < 0 )
    {
      v23 = v15;
      do
      {
        *v23++ = 0;
        --v14;
      }
      while ( v14 );
      if ( *((_QWORD *)v15 - 2) )
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v15 - 2), v15 - 16);
      else
        ExFreePoolWithTag(v15 - 16, *((_DWORD *)v15 - 2));
      if ( *(v13 - 2) )
        ExFreeToNPagedLookasideList(*(v13 - 2), v13 - 2);
      else
        ExFreePoolWithTag(v13 - 2, *((_DWORD *)v13 - 2));
      return (unsigned int)v20;
    }
    v21 = v14;
    if ( v14 >= v17 )
      v21 = v17;
    v22 = (char *)*a5;
    memmove(*a5, v15, v21);
    ++*((_BYTE *)v13 + v11 - 1);
    v17 -= v21;
    v18 = v27;
    *a5 = &v22[v21];
    v19 = v26 + 1;
    a5[1] = (void *)v17;
  }
  v25 = v15;
  do
  {
    *v25++ = 0;
    --v14;
  }
  while ( v14 );
  if ( *((_QWORD *)v15 - 2) )
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v15 - 2), v15 - 16);
  else
    ExFreePoolWithTag(v15 - 16, *((_DWORD *)v15 - 2));
  if ( *(v13 - 2) )
    ExFreeToNPagedLookasideList(*(v13 - 2), v13 - 2);
  else
    ExFreePoolWithTag(v13 - 2, *((_DWORD *)v13 - 2));
  return 0;
}

```

## disassembly

```asm
0x14000b130  mov     [rsp+arg_10], rbx
0x14000b135  mov     [rsp+arg_8], rdx
0x14000b13a  mov     [rsp+arg_0], rcx
0x14000b13f  push    rbp
0x14000b140  push    rsi
0x14000b141  push    rdi
0x14000b142  push    r12
0x14000b144  push    r13
0x14000b146  push    r14
0x14000b148  push    r15
0x14000b14a  sub     rsp, 70h
0x14000b14e  mov     r12, r9
0x14000b151  mov     r13, r8
0x14000b154  call    ?GetHashLength@details@impl@crypto@wlansecurity@@YAKQEAX@Z; wlansecurity::crypto::impl::details::GetHashLength(void * const)
0x14000b159  mov     ebx, eax
0x14000b15b  test    eax, eax
0x14000b15d  jz      loc_14000B3CA
0x14000b163  mov     rsi, [r13+8]
0x14000b167  mov     r14, [r12+8]
0x14000b16c  lea     r15, [r14+2]
0x14000b170  add     r15, rsi
0x14000b173  cmp     r15, rsi
0x14000b176  jb      loc_14000B3CA
0x14000b17c  cmp     r15, r14
0x14000b17f  jb      loc_14000B3CA
0x14000b185  cmp     r15, 1
0x14000b189  jb      loc_14000B3CA
0x14000b18f  mov     rcx, r15; unsigned __int64
0x14000b192  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000b197  mov     rdi, rax
0x14000b19a  test    rax, rax
0x14000b19d  jz      loc_14000B3C3
0x14000b1a3  mov     ecx, ebx; unsigned __int64
0x14000b1a5  mov     ebp, ebx
0x14000b1a7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000b1ac  mov     rbx, rax
0x14000b1af  test    rax, rax
0x14000b1b2  jz      loc_14000B394
0x14000b1b8  mov     rdx, [r13+0]; Src
0x14000b1bc  mov     r8, rsi; Size
0x14000b1bf  mov     rcx, rdi; void *
0x14000b1c2  call    memmove
0x14000b1c7  mov     rdx, [r12]; Src
0x14000b1cb  lea     rcx, [rsi+1]
0x14000b1cf  add     rcx, rdi; void *
0x14000b1d2  mov     byte ptr [rsi+rdi], 0
0x14000b1d6  mov     r8, r14; Size
0x14000b1d9  call    memmove
0x14000b1de  mov     r12, [rsp+0A8h+arg_20]
0x14000b1e6  xor     edx, edx
0x14000b1e8  mov     r13, [rsp+0A8h+arg_0]
0x14000b1f0  mov     byte ptr [rdi+r15-1], 0
0x14000b1f6  mov     r12, [r12+8]
0x14000b1fb  lea     rax, [r12-1]
0x14000b200  add     rax, rbp
0x14000b203  div     rbp
0x14000b206  mov     rdx, rax
0x14000b209  mov     [rsp+0A8h+var_80], rax
0x14000b20e  xor     eax, eax
0x14000b210  mov     ecx, eax
0x14000b212  mov     [rsp+0A8h+var_88], eax
0x14000b216  cmp     rcx, rdx
0x14000b219  jnb     loc_14000B323
0x14000b21f  mov     rax, [rsp+0A8h+arg_8]
0x14000b227  lea     r9, [rsp+0A8h+var_68]
0x14000b22c  lea     r8, [rsp+0A8h+var_48]
0x14000b231  mov     [rsp+0A8h+var_68], rbx
0x14000b236  lea     rdx, [rsp+0A8h+var_58]
0x14000b23b  mov     [rsp+0A8h+var_60], rbp
0x14000b240  mov     rcx, r13
0x14000b243  mov     [rsp+0A8h+var_58], rdi
0x14000b248  movaps  xmm0, xmmword ptr [rax]
0x14000b24b  movdqu  [rsp+0A8h+var_48], xmm0
0x14000b251  mov     [rsp+0A8h+var_50], r15
0x14000b256  call    ?Hash@details@impl@crypto@wlansecurity@@YAJPEAXV?$span@$$CBE$0?0@utl@@1V?$span@E$0?0@6@@Z; wlansecurity::crypto::impl::details::Hash(void *,utl::span<uchar const,-1>,utl::span<uchar const,-1>,utl::span<uchar,-1>)
0x14000b25b  mov     esi, eax
0x14000b25d  test    eax, eax
0x14000b25f  js      short loc_14000B2AF
0x14000b261  mov     rax, [rsp+0A8h+arg_20]
0x14000b269  cmp     rbp, r12
0x14000b26c  mov     r14, rbp
0x14000b26f  mov     rdx, rbx; Src
0x14000b272  cmovnb  r14, r12
0x14000b276  mov     r8, r14; Size
0x14000b279  mov     rsi, [rax]
0x14000b27c  mov     rcx, rsi; void *
0x14000b27f  call    memmove
0x14000b284  mov     rcx, [rsp+0A8h+arg_20]
0x14000b28c  lea     rax, [r14+rsi]
0x14000b290  inc     byte ptr [rdi+r15-1]
0x14000b295  sub     r12, r14
0x14000b298  mov     rdx, [rsp+0A8h+var_80]
0x14000b29d  mov     [rcx], rax
0x14000b2a0  mov     eax, [rsp+0A8h+var_88]
0x14000b2a4  inc     eax
0x14000b2a6  mov     [rcx+8], r12
0x14000b2aa  jmp     loc_14000B210
0x14000b2af  mov     rax, rbx
0x14000b2b2  mov     byte ptr [rax], 0
0x14000b2b5  inc     rax
0x14000b2b8  sub     rbp, 1
0x14000b2bc  jnz     short loc_14000B2B2
0x14000b2be  lea     rcx, [rbx-10h]; P
0x14000b2c2  mov     rax, [rcx]
0x14000b2c5  test    rax, rax
0x14000b2c8  jz      short loc_14000B2DE
0x14000b2ca  mov     rdx, rcx; Entry
0x14000b2cd  mov     rcx, rax; Lookaside
0x14000b2d0  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b2d7  nop     dword ptr [rax+rax+00h]
0x14000b2dc  jmp     short loc_14000B2ED
0x14000b2de  mov     edx, [rcx+8]; Tag
0x14000b2e1  call    cs:__imp_ExFreePoolWithTag
0x14000b2e8  nop     dword ptr [rax+rax+00h]
0x14000b2ed  lea     rcx, [rdi-10h]; P
0x14000b2f1  mov     rax, [rcx]
0x14000b2f4  test    rax, rax
0x14000b2f7  jz      short loc_14000B30D
0x14000b2f9  mov     rdx, rcx; Entry
0x14000b2fc  mov     rcx, rax; Lookaside
0x14000b2ff  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b306  nop     dword ptr [rax+rax+00h]
0x14000b30b  jmp     short loc_14000B31C
0x14000b30d  mov     edx, [rcx+8]; Tag
0x14000b310  call    cs:__imp_ExFreePoolWithTag
0x14000b317  nop     dword ptr [rax+rax+00h]
0x14000b31c  mov     eax, esi
0x14000b31e  jmp     loc_14000B3CF
0x14000b323  mov     rax, rbx
0x14000b326  mov     byte ptr [rax], 0
0x14000b329  inc     rax
0x14000b32c  sub     rbp, 1
0x14000b330  jnz     short loc_14000B326
0x14000b332  lea     rcx, [rbx-10h]; P
0x14000b336  mov     rax, [rcx]
0x14000b339  test    rax, rax
0x14000b33c  jz      short loc_14000B352
0x14000b33e  mov     rdx, rcx; Entry
0x14000b341  mov     rcx, rax; Lookaside
0x14000b344  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b34b  nop     dword ptr [rax+rax+00h]
0x14000b350  jmp     short loc_14000B361
0x14000b352  mov     edx, [rcx+8]; Tag
0x14000b355  call    cs:__imp_ExFreePoolWithTag
0x14000b35c  nop     dword ptr [rax+rax+00h]
0x14000b361  lea     rcx, [rdi-10h]; P
0x14000b365  mov     rax, [rcx]
0x14000b368  test    rax, rax
0x14000b36b  jz      short loc_14000B381
0x14000b36d  mov     rdx, rcx; Entry
0x14000b370  mov     rcx, rax; Lookaside
0x14000b373  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b37a  nop     dword ptr [rax+rax+00h]
0x14000b37f  jmp     short loc_14000B390
0x14000b381  mov     edx, [rcx+8]; Tag
0x14000b384  call    cs:__imp_ExFreePoolWithTag
0x14000b38b  nop     dword ptr [rax+rax+00h]
0x14000b390  xor     eax, eax
0x14000b392  jmp     short loc_14000B3CF
0x14000b394  lea     rcx, [rdi-10h]; P
0x14000b398  mov     rax, [rcx]
0x14000b39b  test    rax, rax
0x14000b39e  jz      short loc_14000B3B4
0x14000b3a0  mov     rdx, rcx; Entry
0x14000b3a3  mov     rcx, rax; Lookaside
0x14000b3a6  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b3ad  nop     dword ptr [rax+rax+00h]
0x14000b3b2  jmp     short loc_14000B3C3
0x14000b3b4  mov     edx, [rcx+8]; Tag
0x14000b3b7  call    cs:__imp_ExFreePoolWithTag
0x14000b3be  nop     dword ptr [rax+rax+00h]
0x14000b3c3  mov     eax, 0C0000017h
0x14000b3c8  jmp     short loc_14000B3CF
0x14000b3ca  mov     eax, 0C000000Dh
0x14000b3cf  mov     rbx, [rsp+0A8h+arg_10]
0x14000b3d7  add     rsp, 70h
0x14000b3db  pop     r15
0x14000b3dd  pop     r14
0x14000b3df  pop     r13
0x14000b3e1  pop     r12
0x14000b3e3  pop     rdi
0x14000b3e4  pop     rsi
0x14000b3e5  pop     rbp
0x14000b3e6  retn
```
