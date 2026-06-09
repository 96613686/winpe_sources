# EnumInfo_Initialize(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort,PSFORMAT_ENUMINFO *)

- ea: `0x18002c3fc`
- end: `0x18002c7a5`
- name: `?EnumInfo_Initialize@@YAJPEBG0000GPEAUPSFORMAT_ENUMINFO@@@Z`
- size: `937`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16, struct PSFORMAT_ENUMINFO *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ae2c`

## callees

- `0x180009240`
- `0x18002c3fc`
- `0x18002cd24`
- `0x18002cd94`
- `0x18002d070`
- `0x18006ed20`
- `0x18006fb80`
- `0x18006fb98`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002c509`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002c509`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c48a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c53f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c661`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c48a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c53f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c661`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnumInfo_Initialize(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        VARTYPE a6,
        struct PSFORMAT_ENUMINFO *a7)
{
  unsigned __int64 v9; // rbp
  __int64 v10; // rax
  SIZE_T v11; // rbx
  void *v12; // rax
  HRESULT v13; // ebx
  unsigned __int64 v14; // rsi
  unsigned __int64 v15; // rdi
  WCHAR *v17; // rdx
  const WCHAR *v18; // r12
  __int64 v19; // rcx
  const WCHAR *v20; // r9
  unsigned __int64 v21; // r8
  WCHAR *v22; // rax
  __int64 v23; // r11
  WCHAR v24; // r10
  __int64 v25; // r9
  WCHAR *v26; // rcx
  __int64 v27; // rdi
  bool v28; // cf
  unsigned __int64 v29; // rdi
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rcx
  unsigned __int64 v33; // r8
  WCHAR *v34; // rax
  __int64 v35; // r10
  WCHAR v36; // r9
  __int64 v37; // r9
  __int64 v38; // rdi
  PROPVARIANT propvarSrc[2]; // [rsp+40h] [rbp-68h] BYREF
  __int64 v42; // [rsp+50h] [rbp-58h]

  memset_0((char *)a7 + 4, 0, 0x6Cu);
  *(_DWORD *)a7 = 0;
  *(_OWORD *)propvarSrc = 0;
  v42 = 0;
  if ( !a2 )
  {
    v13 = -2147024809;
    goto LABEL_58;
  }
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  v11 = 2 * v10 + 2;
  v12 = CoTaskMemAlloc(v11);
  propvarSrc[1] = v12;
  if ( !v12 )
  {
    v13 = -2147024882;
LABEL_58:
    *(_OWORD *)propvarSrc = 0;
    v42 = 0;
    goto LABEL_12;
  }
  if ( v11 )
    memcpy_0(v12, a2, v11);
  LOWORD(propvarSrc[0]) = 31;
  v13 = PropVariantChangeType((PROPVARIANT *)a7 + 1, propvarSrc, 0, a6);
  if ( v13 < 0 )
    goto LABEL_12;
  v14 = -1;
  do
    ++v14;
  while ( a1[v14] );
  *((_QWORD *)a7 + 10) = 0;
  v15 = v14 + 1;
  if ( v14 + 1 < v14 || !is_mul_ok(v15, 2u) )
    goto LABEL_11;
  v17 = (WCHAR *)CoTaskMemAlloc(2 * v15);
  *((_QWORD *)a7 + 10) = v17;
  v13 = v17 == 0 ? 0x8007000E : 0;
  v18 = &Src;
  if ( !v17 )
    goto LABEL_12;
  if ( v15 > 0x7FFFFFFF )
    goto LABEL_62;
  if ( v14 >= 0x7FFFFFFF )
  {
    if ( v14 == -1 )
      goto LABEL_33;
LABEL_62:
    *v17 = 0;
    goto LABEL_33;
  }
  v19 = v14 & -(__int64)(a1 != 0);
  v20 = &Src;
  if ( a1 )
    v20 = a1;
  v21 = v14 + 1;
  v22 = v17;
  v23 = 0;
  do
  {
    if ( !v19 )
      break;
    v24 = *v20;
    if ( !*v20 )
      break;
    ++v20;
    *v22++ = v24;
    --v19;
    ++v23;
    --v21;
  }
  while ( v21 );
  v25 = v23 - 1;
  if ( v21 )
    v25 = v23;
  v26 = v22 - 1;
  if ( v21 )
    v26 = v22;
  *v26 = 0;
  if ( v21 )
  {
    v28 = v15 == v25;
    v27 = v15 - v25;
    if ( !v28 && v27 != 1 && (unsigned __int64)(2 * v27) > 2 )
      memset_0(&v17[v25 + 1], 0, 2 * v27 - 2);
  }
LABEL_33:
  LoadIndirectStringAlloc(a3, (unsigned __int16 **)a7 + 11);
  do
    ++v9;
  while ( a4[v9] );
  *((_QWORD *)a7 + 12) = 0;
  v29 = v9 + 1;
  if ( v9 + 1 < v9 || !is_mul_ok(v29, 2u) )
  {
LABEL_11:
    v13 = -2147024362;
LABEL_12:
    EnumInfo_Clear((PROPVARIANT *)a7);
    goto LABEL_13;
  }
  v30 = (__int64)CoTaskMemAlloc(2 * v29);
  *((_QWORD *)a7 + 12) = v30;
  v31 = -v30;
  v13 = v30 == 0 ? 0x8007000E : 0;
  if ( !v30 )
    goto LABEL_12;
  if ( v29 > 0x7FFFFFFF )
    goto LABEL_64;
  if ( v9 >= 0x7FFFFFFF )
  {
    if ( v9 == -1 )
      goto LABEL_51;
LABEL_64:
    *(_WORD *)v30 = 0;
    goto LABEL_51;
  }
  v32 = v9 & -(__int64)(a4 != 0);
  if ( a4 )
    v18 = a4;
  v33 = v9 + 1;
  v34 = (WCHAR *)v30;
  v35 = 0;
  do
  {
    if ( !v32 )
      break;
    v36 = *v18;
    if ( !*v18 )
      break;
    ++v18;
    *v34++ = v36;
    --v32;
    ++v35;
    --v33;
  }
  while ( v33 );
  v37 = v35 - 1;
  if ( v33 )
    v37 = v35;
  v31 = (__int64)(v34 - 1);
  if ( v33 )
    v31 = (__int64)v34;
  *(_WORD *)v31 = 0;
  if ( v33 )
  {
    v28 = v29 == v37;
    v38 = v29 - v37;
    if ( !v28 && v38 != 1 && (unsigned __int64)(2 * v38) > 2 )
      memset_0((void *)(v30 + 2 * (v37 + 1)), 0, 2 * v38 - 2);
  }
LABEL_51:
  if ( *a5 )
  {
    v13 = _AllocString<CTCoAllocPolicy>(v31, v30, a5, (char *)a7 + 104);
    if ( v13 < 0 )
      goto LABEL_12;
  }
LABEL_13:
  PropVariantClear(propvarSrc);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002c3fc  push    rbx
0x18002c3fe  push    rbp
0x18002c3ff  push    rsi
0x18002c400  push    rdi
0x18002c401  push    r12
0x18002c403  push    r13
0x18002c405  push    r14
0x18002c407  push    r15
0x18002c409  sub     rsp, 68h
0x18002c40d  mov     rax, cs:__security_cookie
0x18002c414  xor     rax, rsp
0x18002c417  mov     [rsp+0A8h+var_50], rax
0x18002c41c  mov     [rsp+0A8h+var_80], r9
0x18002c421  mov     [rsp+0A8h+var_88], r8
0x18002c426  mov     rdi, rdx
0x18002c429  mov     r13, rcx
0x18002c42c  mov     r14, [rsp+0A8h+arg_30]
0x18002c434  mov     rax, [rsp+0A8h+arg_20]
0x18002c43c  mov     [rsp+0A8h+var_78], rax
0x18002c441  lea     rcx, [r14+4]; void *
0x18002c445  xor     edx, edx; Val
0x18002c447  lea     r8d, [rdx+6Ch]; Size
0x18002c44b  call    memset_0
0x18002c450  xor     r15d, r15d
0x18002c453  mov     [r14], r15d
0x18002c456  xorps   xmm0, xmm0
0x18002c459  xor     eax, eax
0x18002c45b  movups  xmmword ptr [rsp+0A8h+propvarSrc], xmm0
0x18002c460  mov     [rsp+0A8h+var_58], rax
0x18002c465  test    rdi, rdi
0x18002c468  jz      loc_18002C79D
0x18002c46e  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18002c472  mov     rax, rbp
0x18002c475  inc     rax
0x18002c478  cmp     [rdi+rax*2], r15w
0x18002c47d  jnz     short loc_18002C475
0x18002c47f  lea     rbx, ds:2[rax*2]
0x18002c487  mov     rcx, rbx; cb
0x18002c48a  call    cs:__imp_CoTaskMemAlloc
0x18002c490  mov     [rsp+0A8h+propvarSrc+8], rax
0x18002c495  test    rax, rax
0x18002c498  jz      loc_18002C74E
0x18002c49e  test    rbx, rbx
0x18002c4a1  jz      short loc_18002C4B1
0x18002c4a3  mov     r8, rbx; Size
0x18002c4a6  mov     rdx, rdi; Src
0x18002c4a9  mov     rcx, rax; void *
0x18002c4ac  call    memcpy_0
0x18002c4b1  mov     eax, 1Fh
0x18002c4b6  mov     word ptr [rsp+0A8h+propvarSrc], ax
0x18002c4bb  lea     rcx, [r14+8]; ppropvarDest
0x18002c4bf  movzx   r9d, [rsp+0A8h+arg_28]; vt
0x18002c4c8  xor     r8d, r8d; flags
0x18002c4cb  lea     rdx, [rsp+0A8h+propvarSrc]; propvarSrc
0x18002c4d0  call    PropVariantChangeType
0x18002c4d5  mov     ebx, eax
0x18002c4d7  test    eax, eax
0x18002c4d9  js      short loc_18002C4FB
0x18002c4db  mov     rsi, rbp
0x18002c4de  inc     rsi
0x18002c4e1  cmp     [r13+rsi*2+0], r15w
0x18002c4e7  jnz     short loc_18002C4DE
0x18002c4e9  mov     [r14+50h], r15
0x18002c4ed  lea     rdi, [rsi+1]
0x18002c4f1  cmp     rdi, rsi
0x18002c4f4  jnb     short loc_18002C52F
0x18002c4f6  mov     ebx, 80070216h
0x18002c4fb  mov     rcx, r14; struct PSFORMAT_ENUMINFO *
0x18002c4fe  call    ?EnumInfo_Clear@@YAXPEAUPSFORMAT_ENUMINFO@@@Z; EnumInfo_Clear(PSFORMAT_ENUMINFO *)
0x18002c503  nop
0x18002c504  lea     rcx, [rsp+0A8h+propvarSrc]; pvar
0x18002c509  call    cs:__imp_PropVariantClear
0x18002c50f  mov     eax, ebx
0x18002c511  mov     rcx, [rsp+0A8h+var_50]
0x18002c516  xor     rcx, rsp; StackCookie
0x18002c519  call    __security_check_cookie
0x18002c51e  add     rsp, 68h
0x18002c522  pop     r15
0x18002c524  pop     r14
0x18002c526  pop     r13
0x18002c528  pop     r12
0x18002c52a  pop     rdi
0x18002c52b  pop     rsi
0x18002c52c  pop     rbp
0x18002c52d  pop     rbx
0x18002c52e  retn
0x18002c52f  mov     eax, 2
0x18002c534  mul     rdi
0x18002c537  test    rdx, rdx
0x18002c53a  jnz     short loc_18002C4F6
0x18002c53c  mov     rcx, rax; cb
0x18002c53f  call    cs:__imp_CoTaskMemAlloc
0x18002c545  mov     rdx, rax
0x18002c548  mov     [r14+50h], rax
0x18002c54c  mov     rcx, rax
0x18002c54f  neg     rcx
0x18002c552  sbb     ebx, ebx
0x18002c554  not     ebx
0x18002c556  mov     r15d, 8007000Eh
0x18002c55c  and     ebx, r15d
0x18002c55f  lea     r12, Src
0x18002c566  mov     eax, 7FFFFFFFh
0x18002c56b  test    rdx, rdx
0x18002c56e  jz      loc_18002C614
0x18002c574  cmp     rdi, rax
0x18002c577  ja      loc_18002C771
0x18002c57d  cmp     rsi, rax
0x18002c580  jnb     loc_18002C776
0x18002c586  mov     rax, r13
0x18002c589  neg     rax
0x18002c58c  sbb     rcx, rcx
0x18002c58f  and     rcx, rsi
0x18002c592  mov     r9, r12
0x18002c595  test    r13, r13
0x18002c598  cmovnz  r9, r13
0x18002c59c  xor     r13d, r13d
0x18002c59f  test    rdi, rdi
0x18002c5a2  jz      short loc_18002C61F
0x18002c5a4  mov     r8, rdi
0x18002c5a7  mov     rax, rdx
0x18002c5aa  mov     r11d, r13d
0x18002c5ad  test    rcx, rcx
0x18002c5b0  jz      short loc_18002C5D4
0x18002c5b2  movzx   r10d, word ptr [r9]
0x18002c5b6  test    r10w, r10w
0x18002c5ba  jz      short loc_18002C5D4
0x18002c5bc  add     r9, 2
0x18002c5c0  mov     [rax], r10w
0x18002c5c4  add     rax, 2
0x18002c5c8  dec     rcx
0x18002c5cb  inc     r11
0x18002c5ce  sub     r8, 1
0x18002c5d2  jnz     short loc_18002C5AD
0x18002c5d4  lea     r9, [r11-1]
0x18002c5d8  test    r8, r8
0x18002c5db  cmovnz  r9, r11
0x18002c5df  lea     rcx, [rax-2]
0x18002c5e3  cmovnz  rcx, rax
0x18002c5e7  mov     [rcx], r13w
0x18002c5eb  jz      short loc_18002C61F
0x18002c5ed  sub     rdi, r9
0x18002c5f0  cmp     rdi, 1
0x18002c5f4  jbe     short loc_18002C61F
0x18002c5f6  lea     r8, [rdi+rdi]
0x18002c5fa  cmp     r8, 2
0x18002c5fe  jbe     short loc_18002C61F
0x18002c600  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18002c604  inc     r9
0x18002c607  lea     rcx, [rdx+r9*2]; void *
0x18002c60b  xor     edx, edx; Val
0x18002c60d  call    memset_0
0x18002c612  jmp     short loc_18002C61F
0x18002c614  xor     r13d, r13d
0x18002c617  test    ebx, ebx
0x18002c619  js      loc_18002C4FB
0x18002c61f  lea     rdx, [r14+58h]; unsigned __int16 **
0x18002c623  mov     rcx, [rsp+0A8h+var_88]; unsigned __int16 *
0x18002c628  call    ?LoadIndirectStringAlloc@@YAJPEBGPEAPEAG@Z; LoadIndirectStringAlloc(ushort const *,ushort * *)
0x18002c62d  mov     rsi, [rsp+0A8h+var_80]
0x18002c632  inc     rbp
0x18002c635  cmp     [rsi+rbp*2], r13w
0x18002c63a  jnz     short loc_18002C632
0x18002c63c  mov     [r14+60h], r13
0x18002c640  lea     rdi, [rbp+1]
0x18002c644  cmp     rdi, rbp
0x18002c647  jb      loc_18002C4F6
0x18002c64d  mov     eax, 2
0x18002c652  mul     rdi
0x18002c655  test    rdx, rdx
0x18002c658  jnz     loc_18002C4F6
0x18002c65e  mov     rcx, rax; cb
0x18002c661  call    cs:__imp_CoTaskMemAlloc
0x18002c667  mov     rdx, rax
0x18002c66a  mov     [r14+60h], rax
0x18002c66e  mov     rcx, rax
0x18002c671  neg     rcx
0x18002c674  sbb     ebx, ebx
0x18002c676  not     ebx
0x18002c678  and     ebx, r15d
0x18002c67b  test    rax, rax
0x18002c67e  jz      loc_18002C767
0x18002c684  mov     eax, 7FFFFFFFh
0x18002c689  cmp     rdi, rax
0x18002c68c  ja      loc_18002C794
0x18002c692  cmp     rbp, rax
0x18002c695  jnb     loc_18002C78B
0x18002c69b  mov     rax, rsi
0x18002c69e  neg     rax
0x18002c6a1  sbb     rcx, rcx
0x18002c6a4  and     rcx, rbp
0x18002c6a7  test    rsi, rsi
0x18002c6aa  cmovnz  r12, rsi
0x18002c6ae  test    rdi, rdi
0x18002c6b1  jz      short loc_18002C6FD
0x18002c6b3  mov     r8, rdi
0x18002c6b6  mov     rax, rdx
0x18002c6b9  mov     r10, r13
0x18002c6bc  test    rcx, rcx
0x18002c6bf  jz      short loc_18002C6E4
0x18002c6c1  movzx   r9d, word ptr [r12]
0x18002c6c6  test    r9w, r9w
0x18002c6ca  jz      short loc_18002C6E4
0x18002c6cc  add     r12, 2
0x18002c6d0  mov     [rax], r9w
0x18002c6d4  add     rax, 2
0x18002c6d8  dec     rcx
0x18002c6db  inc     r10
0x18002c6de  sub     r8, 1
0x18002c6e2  jnz     short loc_18002C6BC
0x18002c6e4  lea     r9, [r10-1]
0x18002c6e8  test    r8, r8
0x18002c6eb  cmovnz  r9, r10
0x18002c6ef  lea     rcx, [rax-2]
0x18002c6f3  cmovnz  rcx, rax
0x18002c6f7  mov     [rcx], r13w
0x18002c6fb  jnz     short loc_18002C727
0x18002c6fd  mov     rax, [rsp+0A8h+var_78]
0x18002c702  cmp     [rax], r13w
0x18002c706  jz      loc_18002C504
0x18002c70c  lea     r9, [r14+68h]
0x18002c710  mov     r8, rax
0x18002c713  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18002c718  mov     ebx, eax
0x18002c71a  test    eax, eax
0x18002c71c  jns     loc_18002C504
0x18002c722  jmp     loc_18002C4FB
0x18002c727  sub     rdi, r9
0x18002c72a  cmp     rdi, 1
0x18002c72e  jbe     short loc_18002C6FD
0x18002c730  lea     r8, [rdi+rdi]
0x18002c734  cmp     r8, 2
0x18002c738  jbe     short loc_18002C6FD
0x18002c73a  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18002c73e  inc     r9
0x18002c741  lea     rcx, [rdx+r9*2]; void *
0x18002c745  xor     edx, edx; Val
0x18002c747  call    memset_0
0x18002c74c  jmp     short loc_18002C6FD
0x18002c74e  mov     ebx, 8007000Eh
0x18002c753  xorps   xmm0, xmm0
0x18002c756  xor     eax, eax
0x18002c758  movups  xmmword ptr [rsp+0A8h+propvarSrc], xmm0
0x18002c75d  mov     [rsp+0A8h+var_58], rax
0x18002c762  jmp     loc_18002C4FB
0x18002c767  test    ebx, ebx
0x18002c769  js      loc_18002C4FB
0x18002c76f  jmp     short loc_18002C6FD
0x18002c771  xor     r13d, r13d
0x18002c774  jmp     short loc_18002C782
0x18002c776  xor     r13d, r13d
0x18002c779  test    rdi, rdi
0x18002c77c  jz      loc_18002C61F
0x18002c782  mov     [rdx], r13w
0x18002c786  jmp     loc_18002C61F
0x18002c78b  test    rdi, rdi
0x18002c78e  jz      loc_18002C6FD
0x18002c794  mov     [rdx], r13w
0x18002c798  jmp     loc_18002C6FD
0x18002c79d  mov     ebx, 80070057h
0x18002c7a2  jmp     short loc_18002C753
```
