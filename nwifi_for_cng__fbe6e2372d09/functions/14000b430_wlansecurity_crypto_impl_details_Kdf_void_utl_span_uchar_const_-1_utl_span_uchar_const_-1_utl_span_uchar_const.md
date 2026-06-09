# wlansecurity::crypto::impl::details::Kdf(void *,utl::span<uchar const,-1>,utl::span<uchar const,-1>,utl::span<uchar const,-1>,utl::span<uchar,-1>)

- ea: `0x14000b430`
- end: `0x14000b781`
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
- `0x14000b430`
- `0x14000ba48`
- `0x140020aa4`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b53b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b56a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b67d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b6ac`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b6f5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b724`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b75a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b53b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b56a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b67d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b6ac`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b6f5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b724`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b75a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b54c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b590`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b68e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b6bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b706`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b735`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b76b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b54c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b590`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b68e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b6bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b706`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b735`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b76b`

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
0x14000b430  mov     [rsp+arg_8], rdx
0x14000b435  mov     [rsp+arg_0], rcx
0x14000b43a  push    rbx
0x14000b43b  push    rbp
0x14000b43c  push    rsi
0x14000b43d  push    rdi
0x14000b43e  push    r12
0x14000b440  push    r13
0x14000b442  push    r14
0x14000b444  push    r15
0x14000b446  sub     rsp, 68h
0x14000b44a  mov     r15, r9
0x14000b44d  mov     r13, r8
0x14000b450  call    ?GetHashLength@details@impl@crypto@wlansecurity@@YAKQEAX@Z; wlansecurity::crypto::impl::details::GetHashLength(void * const)
0x14000b455  mov     rsi, [r13+8]
0x14000b459  mov     rdi, [r15+8]
0x14000b45d  mov     ebp, eax
0x14000b45f  lea     r12, [rdi+4]
0x14000b463  add     r12, rsi
0x14000b466  cmp     r12, rsi
0x14000b469  jb      loc_14000B576
0x14000b46f  cmp     r12, rdi
0x14000b472  jb      loc_14000B576
0x14000b478  cmp     r12, 4
0x14000b47c  jb      loc_14000B576
0x14000b482  mov     rcx, r12; unsigned __int64
0x14000b485  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000b48a  mov     rbx, rax
0x14000b48d  test    rax, rax
0x14000b490  jz      loc_14000B777
0x14000b496  mov     ecx, ebp; unsigned __int64
0x14000b498  mov     r14d, ebp
0x14000b49b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000b4a0  mov     rbp, rax
0x14000b4a3  test    rax, rax
0x14000b4a6  jz      loc_14000B748
0x14000b4ac  mov     rdx, [r13+0]; Src
0x14000b4b0  lea     rcx, [rbx+2]; void *
0x14000b4b4  xor     eax, eax
0x14000b4b6  mov     r8, rsi; Size
0x14000b4b9  mov     [rbx], ax
0x14000b4bc  call    memmove
0x14000b4c1  mov     rdx, [r15]; Src
0x14000b4c4  lea     rcx, [rsi+2]
0x14000b4c8  add     rcx, rbx; void *
0x14000b4cb  mov     r8, rdi; Size
0x14000b4ce  call    memmove
0x14000b4d3  mov     r13, [rsp+0A8h+arg_20]
0x14000b4db  xor     edx, edx
0x14000b4dd  mov     r13, [r13+8]
0x14000b4e1  movzx   eax, r13w
0x14000b4e5  shl     ax, 3
0x14000b4e9  mov     [rbx+r12-2], ax
0x14000b4ef  lea     rax, [r13-1]
0x14000b4f3  add     rax, r14
0x14000b4f6  div     r14
0x14000b4f9  mov     [rsp+0A8h+arg_18], rax
0x14000b501  mov     rdx, rax
0x14000b504  cmp     rax, 0FFFFh
0x14000b50a  jbe     loc_14000B59E
0x14000b510  mov     rax, rbp
0x14000b513  test    r14, r14
0x14000b516  jz      short loc_14000B529
0x14000b518  mov     r15d, 1
0x14000b51e  mov     byte ptr [rax], 0
0x14000b521  add     rax, r15
0x14000b524  sub     r14, r15
0x14000b527  jnz     short loc_14000B51E
0x14000b529  lea     rcx, [rbp-10h]; P
0x14000b52d  mov     rax, [rcx]
0x14000b530  test    rax, rax
0x14000b533  jz      short loc_14000B549
0x14000b535  mov     rdx, rcx; Entry
0x14000b538  mov     rcx, rax; Lookaside
0x14000b53b  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b542  nop     dword ptr [rax+rax+00h]
0x14000b547  jmp     short loc_14000B558
0x14000b549  mov     edx, [rcx+8]; Tag
0x14000b54c  call    cs:__imp_ExFreePoolWithTag
0x14000b553  nop     dword ptr [rax+rax+00h]
0x14000b558  lea     rcx, [rbx-10h]; P
0x14000b55c  mov     rax, [rcx]
0x14000b55f  test    rax, rax
0x14000b562  jz      short loc_14000B58D
0x14000b564  mov     rdx, rcx; Entry
0x14000b567  mov     rcx, rax; Lookaside
0x14000b56a  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b571  nop     dword ptr [rax+rax+00h]
0x14000b576  mov     eax, 0C000000Dh
0x14000b57b  add     rsp, 68h
0x14000b57f  pop     r15
0x14000b581  pop     r14
0x14000b583  pop     r13
0x14000b585  pop     r12
0x14000b587  pop     rdi
0x14000b588  pop     rsi
0x14000b589  pop     rbp
0x14000b58a  pop     rbx
0x14000b58b  retn
0x14000b58d  mov     edx, [rcx+8]; Tag
0x14000b590  call    cs:__imp_ExFreePoolWithTag
0x14000b597  nop     dword ptr [rax+rax+00h]
0x14000b59c  jmp     short loc_14000B576
0x14000b59e  mov     r15d, 1
0x14000b5a4  movzx   ecx, r15w
0x14000b5a8  movzx   eax, cx
0x14000b5ab  mov     [rsp+0A8h+arg_10], cx
0x14000b5b3  cmp     rax, rdx
0x14000b5b6  ja      loc_14000B6D0
0x14000b5bc  mov     rax, [rsp+0A8h+arg_8]
0x14000b5c4  lea     r9, [rsp+0A8h+var_78]
0x14000b5c9  mov     [rbx], cx
0x14000b5cc  lea     r8, [rsp+0A8h+var_58]
0x14000b5d1  mov     rcx, [rsp+0A8h+arg_0]
0x14000b5d9  lea     rdx, [rsp+0A8h+var_68]
0x14000b5de  mov     [rsp+0A8h+var_78], rbp
0x14000b5e3  movaps  xmm0, xmmword ptr [rax]
0x14000b5e6  movdqu  [rsp+0A8h+var_58], xmm0
0x14000b5ec  mov     [rsp+0A8h+var_70], r14
0x14000b5f1  mov     [rsp+0A8h+var_68], rbx
0x14000b5f6  mov     [rsp+0A8h+var_60], r12
0x14000b5fb  call    ?Hash@details@impl@crypto@wlansecurity@@YAJPEAXV?$span@$$CBE$0?0@utl@@1V?$span@E$0?0@6@@Z; wlansecurity::crypto::impl::details::Hash(void *,utl::span<uchar const,-1>,utl::span<uchar const,-1>,utl::span<uchar,-1>)
0x14000b600  mov     edi, eax
0x14000b602  test    eax, eax
0x14000b604  js      short loc_14000B658
0x14000b606  mov     rax, [rsp+0A8h+arg_20]
0x14000b60e  cmp     r14, r13
0x14000b611  mov     rsi, r14
0x14000b614  mov     rdx, rbp; Src
0x14000b617  cmovnb  rsi, r13
0x14000b61b  mov     r8, rsi; Size
0x14000b61e  mov     rdi, [rax]
0x14000b621  mov     rcx, rdi; void *
0x14000b624  call    memmove
0x14000b629  mov     rcx, [rsp+0A8h+arg_20]
0x14000b631  lea     rax, [rdi+rsi]
0x14000b635  mov     rdx, [rsp+0A8h+arg_18]
0x14000b63d  sub     r13, rsi
0x14000b640  mov     [rcx], rax
0x14000b643  mov     [rcx+8], r13
0x14000b647  movzx   ecx, [rsp+0A8h+arg_10]
0x14000b64f  add     cx, r15w
0x14000b653  jmp     loc_14000B5A8
0x14000b658  mov     rax, rbp
0x14000b65b  test    r14, r14
0x14000b65e  jz      short loc_14000B66B
0x14000b660  mov     byte ptr [rax], 0
0x14000b663  add     rax, r15
0x14000b666  sub     r14, r15
0x14000b669  jnz     short loc_14000B660
0x14000b66b  lea     rcx, [rbp-10h]; P
0x14000b66f  mov     rax, [rcx]
0x14000b672  test    rax, rax
0x14000b675  jz      short loc_14000B68B
0x14000b677  mov     rdx, rcx; Entry
0x14000b67a  mov     rcx, rax; Lookaside
0x14000b67d  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b684  nop     dword ptr [rax+rax+00h]
0x14000b689  jmp     short loc_14000B69A
0x14000b68b  mov     edx, [rcx+8]; Tag
0x14000b68e  call    cs:__imp_ExFreePoolWithTag
0x14000b695  nop     dword ptr [rax+rax+00h]
0x14000b69a  lea     rcx, [rbx-10h]; P
0x14000b69e  mov     rax, [rcx]
0x14000b6a1  test    rax, rax
0x14000b6a4  jz      short loc_14000B6BA
0x14000b6a6  mov     rdx, rcx; Entry
0x14000b6a9  mov     rcx, rax; Lookaside
0x14000b6ac  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b6b3  nop     dword ptr [rax+rax+00h]
0x14000b6b8  jmp     short loc_14000B6C9
0x14000b6ba  mov     edx, [rcx+8]; Tag
0x14000b6bd  call    cs:__imp_ExFreePoolWithTag
0x14000b6c4  nop     dword ptr [rax+rax+00h]
0x14000b6c9  mov     eax, edi
0x14000b6cb  jmp     loc_14000B57B
0x14000b6d0  mov     rax, rbp
0x14000b6d3  test    r14, r14
0x14000b6d6  jz      short loc_14000B6E3
0x14000b6d8  mov     byte ptr [rax], 0
0x14000b6db  add     rax, r15
0x14000b6de  sub     r14, r15
0x14000b6e1  jnz     short loc_14000B6D8
0x14000b6e3  lea     rcx, [rbp-10h]; P
0x14000b6e7  mov     rax, [rcx]
0x14000b6ea  test    rax, rax
0x14000b6ed  jz      short loc_14000B703
0x14000b6ef  mov     rdx, rcx; Entry
0x14000b6f2  mov     rcx, rax; Lookaside
0x14000b6f5  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b6fc  nop     dword ptr [rax+rax+00h]
0x14000b701  jmp     short loc_14000B712
0x14000b703  mov     edx, [rcx+8]; Tag
0x14000b706  call    cs:__imp_ExFreePoolWithTag
0x14000b70d  nop     dword ptr [rax+rax+00h]
0x14000b712  lea     rcx, [rbx-10h]; P
0x14000b716  mov     rax, [rcx]
0x14000b719  test    rax, rax
0x14000b71c  jz      short loc_14000B732
0x14000b71e  mov     rdx, rcx; Entry
0x14000b721  mov     rcx, rax; Lookaside
0x14000b724  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b72b  nop     dword ptr [rax+rax+00h]
0x14000b730  jmp     short loc_14000B741
0x14000b732  mov     edx, [rcx+8]; Tag
0x14000b735  call    cs:__imp_ExFreePoolWithTag
0x14000b73c  nop     dword ptr [rax+rax+00h]
0x14000b741  xor     eax, eax
0x14000b743  jmp     loc_14000B57B
0x14000b748  lea     rcx, [rbx-10h]; P
0x14000b74c  mov     rax, [rcx]
0x14000b74f  test    rax, rax
0x14000b752  jz      short loc_14000B768
0x14000b754  mov     rdx, rcx; Entry
0x14000b757  mov     rcx, rax; Lookaside
0x14000b75a  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b761  nop     dword ptr [rax+rax+00h]
0x14000b766  jmp     short loc_14000B777
0x14000b768  mov     edx, [rcx+8]; Tag
0x14000b76b  call    cs:__imp_ExFreePoolWithTag
0x14000b772  nop     dword ptr [rax+rax+00h]
0x14000b777  mov     eax, 0C0000017h
0x14000b77c  jmp     loc_14000B57B
```
