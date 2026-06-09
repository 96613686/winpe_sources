# wlansecurity::crypto::impl::details::Prf(void *,utl::span<uchar const,-1>,utl::span<uchar const,-1>,utl::span<uchar const,-1>,utl::span<uchar,-1>)

- ea: `0x14000b120`
- end: `0x14000b3d8`
- name: `?Prf@details@impl@crypto@wlansecurity@@YAJPEAXV?$span@$$CBE$0?0@utl@@11V?$span@E$0?0@6@@Z`
- size: `696`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000b790`

## callees

- `0x14000599c`
- `0x14000b120`
- `0x14000ba48`
- `0x140020aa4`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b2c0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b2ef`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b334`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b363`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b396`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b2c0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b2ef`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b334`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b363`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b396`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b2d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b300`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b345`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b374`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b3a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b2d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b300`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b345`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b374`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b3a7`

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
0x14000b120  mov     [rsp+arg_10], rbx
0x14000b125  mov     [rsp+arg_8], rdx
0x14000b12a  mov     [rsp+arg_0], rcx
0x14000b12f  push    rbp
0x14000b130  push    rsi
0x14000b131  push    rdi
0x14000b132  push    r12
0x14000b134  push    r13
0x14000b136  push    r14
0x14000b138  push    r15
0x14000b13a  sub     rsp, 70h
0x14000b13e  mov     r12, r9
0x14000b141  mov     r13, r8
0x14000b144  call    ?GetHashLength@details@impl@crypto@wlansecurity@@YAKQEAX@Z; wlansecurity::crypto::impl::details::GetHashLength(void * const)
0x14000b149  mov     ebx, eax
0x14000b14b  test    eax, eax
0x14000b14d  jz      loc_14000B3BA
0x14000b153  mov     rsi, [r13+8]
0x14000b157  mov     r14, [r12+8]
0x14000b15c  lea     r15, [r14+2]
0x14000b160  add     r15, rsi
0x14000b163  cmp     r15, rsi
0x14000b166  jb      loc_14000B3BA
0x14000b16c  cmp     r15, r14
0x14000b16f  jb      loc_14000B3BA
0x14000b175  cmp     r15, 1
0x14000b179  jb      loc_14000B3BA
0x14000b17f  mov     rcx, r15; unsigned __int64
0x14000b182  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000b187  mov     rdi, rax
0x14000b18a  test    rax, rax
0x14000b18d  jz      loc_14000B3B3
0x14000b193  mov     ecx, ebx; unsigned __int64
0x14000b195  mov     ebp, ebx
0x14000b197  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000b19c  mov     rbx, rax
0x14000b19f  test    rax, rax
0x14000b1a2  jz      loc_14000B384
0x14000b1a8  mov     rdx, [r13+0]; Src
0x14000b1ac  mov     r8, rsi; Size
0x14000b1af  mov     rcx, rdi; void *
0x14000b1b2  call    memmove
0x14000b1b7  mov     rdx, [r12]; Src
0x14000b1bb  lea     rcx, [rsi+1]
0x14000b1bf  add     rcx, rdi; void *
0x14000b1c2  mov     byte ptr [rsi+rdi], 0
0x14000b1c6  mov     r8, r14; Size
0x14000b1c9  call    memmove
0x14000b1ce  mov     r12, [rsp+0A8h+arg_20]
0x14000b1d6  xor     edx, edx
0x14000b1d8  mov     r13, [rsp+0A8h+arg_0]
0x14000b1e0  mov     byte ptr [rdi+r15-1], 0
0x14000b1e6  mov     r12, [r12+8]
0x14000b1eb  lea     rax, [r12-1]
0x14000b1f0  add     rax, rbp
0x14000b1f3  div     rbp
0x14000b1f6  mov     rdx, rax
0x14000b1f9  mov     [rsp+0A8h+var_80], rax
0x14000b1fe  xor     eax, eax
0x14000b200  mov     ecx, eax
0x14000b202  mov     [rsp+0A8h+var_88], eax
0x14000b206  cmp     rcx, rdx
0x14000b209  jnb     loc_14000B313
0x14000b20f  mov     rax, [rsp+0A8h+arg_8]
0x14000b217  lea     r9, [rsp+0A8h+var_68]
0x14000b21c  lea     r8, [rsp+0A8h+var_48]
0x14000b221  mov     [rsp+0A8h+var_68], rbx
0x14000b226  lea     rdx, [rsp+0A8h+var_58]
0x14000b22b  mov     [rsp+0A8h+var_60], rbp
0x14000b230  mov     rcx, r13
0x14000b233  mov     [rsp+0A8h+var_58], rdi
0x14000b238  movaps  xmm0, xmmword ptr [rax]
0x14000b23b  movdqu  [rsp+0A8h+var_48], xmm0
0x14000b241  mov     [rsp+0A8h+var_50], r15
0x14000b246  call    ?Hash@details@impl@crypto@wlansecurity@@YAJPEAXV?$span@$$CBE$0?0@utl@@1V?$span@E$0?0@6@@Z; wlansecurity::crypto::impl::details::Hash(void *,utl::span<uchar const,-1>,utl::span<uchar const,-1>,utl::span<uchar,-1>)
0x14000b24b  mov     esi, eax
0x14000b24d  test    eax, eax
0x14000b24f  js      short loc_14000B29F
0x14000b251  mov     rax, [rsp+0A8h+arg_20]
0x14000b259  cmp     rbp, r12
0x14000b25c  mov     r14, rbp
0x14000b25f  mov     rdx, rbx; Src
0x14000b262  cmovnb  r14, r12
0x14000b266  mov     r8, r14; Size
0x14000b269  mov     rsi, [rax]
0x14000b26c  mov     rcx, rsi; void *
0x14000b26f  call    memmove
0x14000b274  mov     rcx, [rsp+0A8h+arg_20]
0x14000b27c  lea     rax, [r14+rsi]
0x14000b280  inc     byte ptr [rdi+r15-1]
0x14000b285  sub     r12, r14
0x14000b288  mov     rdx, [rsp+0A8h+var_80]
0x14000b28d  mov     [rcx], rax
0x14000b290  mov     eax, [rsp+0A8h+var_88]
0x14000b294  inc     eax
0x14000b296  mov     [rcx+8], r12
0x14000b29a  jmp     loc_14000B200
0x14000b29f  mov     rax, rbx
0x14000b2a2  mov     byte ptr [rax], 0
0x14000b2a5  inc     rax
0x14000b2a8  sub     rbp, 1
0x14000b2ac  jnz     short loc_14000B2A2
0x14000b2ae  lea     rcx, [rbx-10h]; P
0x14000b2b2  mov     rax, [rcx]
0x14000b2b5  test    rax, rax
0x14000b2b8  jz      short loc_14000B2CE
0x14000b2ba  mov     rdx, rcx; Entry
0x14000b2bd  mov     rcx, rax; Lookaside
0x14000b2c0  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b2c7  nop     dword ptr [rax+rax+00h]
0x14000b2cc  jmp     short loc_14000B2DD
0x14000b2ce  mov     edx, [rcx+8]; Tag
0x14000b2d1  call    cs:__imp_ExFreePoolWithTag
0x14000b2d8  nop     dword ptr [rax+rax+00h]
0x14000b2dd  lea     rcx, [rdi-10h]; P
0x14000b2e1  mov     rax, [rcx]
0x14000b2e4  test    rax, rax
0x14000b2e7  jz      short loc_14000B2FD
0x14000b2e9  mov     rdx, rcx; Entry
0x14000b2ec  mov     rcx, rax; Lookaside
0x14000b2ef  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b2f6  nop     dword ptr [rax+rax+00h]
0x14000b2fb  jmp     short loc_14000B30C
0x14000b2fd  mov     edx, [rcx+8]; Tag
0x14000b300  call    cs:__imp_ExFreePoolWithTag
0x14000b307  nop     dword ptr [rax+rax+00h]
0x14000b30c  mov     eax, esi
0x14000b30e  jmp     loc_14000B3BF
0x14000b313  mov     rax, rbx
0x14000b316  mov     byte ptr [rax], 0
0x14000b319  inc     rax
0x14000b31c  sub     rbp, 1
0x14000b320  jnz     short loc_14000B316
0x14000b322  lea     rcx, [rbx-10h]; P
0x14000b326  mov     rax, [rcx]
0x14000b329  test    rax, rax
0x14000b32c  jz      short loc_14000B342
0x14000b32e  mov     rdx, rcx; Entry
0x14000b331  mov     rcx, rax; Lookaside
0x14000b334  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b33b  nop     dword ptr [rax+rax+00h]
0x14000b340  jmp     short loc_14000B351
0x14000b342  mov     edx, [rcx+8]; Tag
0x14000b345  call    cs:__imp_ExFreePoolWithTag
0x14000b34c  nop     dword ptr [rax+rax+00h]
0x14000b351  lea     rcx, [rdi-10h]; P
0x14000b355  mov     rax, [rcx]
0x14000b358  test    rax, rax
0x14000b35b  jz      short loc_14000B371
0x14000b35d  mov     rdx, rcx; Entry
0x14000b360  mov     rcx, rax; Lookaside
0x14000b363  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b36a  nop     dword ptr [rax+rax+00h]
0x14000b36f  jmp     short loc_14000B380
0x14000b371  mov     edx, [rcx+8]; Tag
0x14000b374  call    cs:__imp_ExFreePoolWithTag
0x14000b37b  nop     dword ptr [rax+rax+00h]
0x14000b380  xor     eax, eax
0x14000b382  jmp     short loc_14000B3BF
0x14000b384  lea     rcx, [rdi-10h]; P
0x14000b388  mov     rax, [rcx]
0x14000b38b  test    rax, rax
0x14000b38e  jz      short loc_14000B3A4
0x14000b390  mov     rdx, rcx; Entry
0x14000b393  mov     rcx, rax; Lookaside
0x14000b396  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b39d  nop     dword ptr [rax+rax+00h]
0x14000b3a2  jmp     short loc_14000B3B3
0x14000b3a4  mov     edx, [rcx+8]; Tag
0x14000b3a7  call    cs:__imp_ExFreePoolWithTag
0x14000b3ae  nop     dword ptr [rax+rax+00h]
0x14000b3b3  mov     eax, 0C0000017h
0x14000b3b8  jmp     short loc_14000B3BF
0x14000b3ba  mov     eax, 0C000000Dh
0x14000b3bf  mov     rbx, [rsp+0A8h+arg_10]
0x14000b3c7  add     rsp, 70h
0x14000b3cb  pop     r15
0x14000b3cd  pop     r14
0x14000b3cf  pop     r13
0x14000b3d1  pop     r12
0x14000b3d3  pop     rdi
0x14000b3d4  pop     rsi
0x14000b3d5  pop     rbp
0x14000b3d6  retn
```
