# Csl::OfflineHive::EnumerateSubkeys(ushort const *,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &,bool)

- ea: `0x140021d08`
- end: `0x1400223d4`
- name: `?EnumerateSubkeys@OfflineHive@Csl@@QEBAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@_N@Z`
- size: `1740`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x140019e40`
- `0x140021b64`
- `0x140021d08`

## callees

- `0x140002344`
- `0x140002b2c`
- `0x140002bb0`
- `0x140006fe4`
- `0x140008f90`
- `0x14000a9b8`
- `0x14000aa58`
- `0x14000d7bc`
- `0x14000dd3c`
- `0x140014f44`
- `0x140021628`
- `0x140021d08`
- `0x140023c20`
- `0x140024540`
- `0x140024760`
- `0x140024af0`

## string_xrefs

- `0x140021da6`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x140021e2f`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x140021f6c`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x140022108`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x140022162`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x1400221c5`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x14002221f`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x14002227d`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x1400222e0`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x140022332`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Csl::OfflineHive::EnumerateSubkeys(__int64 a1, __int64 a2, __int64 *a3, char a4)
{
  __m128i si128; // xmm6
  __int64 v7; // r15
  unsigned int v8; // r12d
  __int64 v9; // rsi
  __int64 v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  unsigned int v14; // eax
  unsigned __int64 v15; // rbx
  _WORD *v16; // rax
  _WORD *v17; // r14
  __int64 v18; // rcx
  unsigned int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // r9
  const struct std::nothrow_t *v23; // rdx
  int v24; // eax
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // r10
  __int64 v28; // rcx
  unsigned __int64 v29; // r9
  unsigned __int64 v30; // r15
  unsigned __int64 v31; // r15
  unsigned __int64 v32; // rdx
  const struct std::nothrow_t *v33; // rdx
  const struct std::nothrow_t *v34; // rdx
  const struct std::nothrow_t *v35; // rdx
  const struct std::nothrow_t *v36; // rdx
  const struct std::nothrow_t *v37; // rdx
  const struct std::nothrow_t *v38; // rdx
  const struct std::nothrow_t *v39; // rdx
  __int64 v40; // rbx
  __int64 v41; // rdi
  const struct std::nothrow_t *v42; // rdx
  unsigned int v44; // [rsp+28h] [rbp-B9h]
  unsigned int v45; // [rsp+28h] [rbp-B9h]
  unsigned int v46; // [rsp+28h] [rbp-B9h]
  void *v47[2]; // [rsp+68h] [rbp-79h] BYREF
  _WORD v48[8]; // [rsp+78h] [rbp-69h] BYREF
  __m128i v49; // [rsp+88h] [rbp-59h] BYREF
  __int64 v50; // [rsp+98h] [rbp-49h]
  int v51; // [rsp+A0h] [rbp-41h]
  __m128i v52; // [rsp+A8h] [rbp-39h] BYREF
  __int64 v53; // [rsp+B8h] [rbp-29h]
  __int64 v54; // [rsp+C0h] [rbp-21h]
  __int64 v55; // [rsp+C8h] [rbp-19h]
  _WORD *v56; // [rsp+D0h] [rbp-11h]
  __int64 v57; // [rsp+D8h] [rbp-9h]
  _WORD *v58; // [rsp+E0h] [rbp-1h]
  __int64 v59; // [rsp+E8h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+5Fh]
  __int64 v61; // [rsp+148h] [rbp+67h]
  __int64 v62; // [rsp+150h] [rbp+6Fh] BYREF
  unsigned int v63; // [rsp+160h] [rbp+7Fh] BYREF

  LOBYTE(v63) = a4;
  v61 = a1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v49 = si128;
  v7 = -1;
  v50 = -1;
  v8 = 0;
  v9 = 0;
  v62 = 0;
  if ( a2 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(a2 + 2 * v10) );
    if ( v10 )
    {
      v11 = OROpenKey(*(_QWORD *)(a1 + 8), a2, &v62);
      if ( v11 == 2 )
      {
        if ( v62 )
          ORCloseKey(v62);
        v12 = -2147024894;
        goto LABEL_103;
      }
      if ( v11 )
      {
        v12 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x43B,
                (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
                (const char *)v11,
                v44);
        if ( v62 )
          ORCloseKey(v62);
        goto LABEL_103;
      }
      v9 = v62;
      a1 = v61;
    }
  }
  v63 = 0;
  LODWORD(v62) = 0;
  if ( v9 )
    LODWORD(v13) = v9;
  else
    v13 = *(_QWORD *)(a1 + 8);
  v14 = ORQueryInfoKey(v13, 0, 0, (unsigned int)&v63, (__int64)&v62, 0, 0, 0, 0, 0, 0);
  if ( v14 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x44D,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)v14,
            v45);
    if ( v9 )
      ORCloseKey(v9);
    goto LABEL_103;
  }
  v51 = v62 + 1;
  v15 = 2LL * (unsigned int)(v62 + 1);
  if ( !is_mul_ok((unsigned int)(v62 + 1), 2u) )
    v15 = -1;
  v16 = operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
  v17 = v16;
  if ( v16 )
    memset_0(v16, 0, v15);
  else
    v17 = 0;
  if ( v63 )
  {
    while ( 1 )
    {
      LODWORD(v62) = v51;
      LODWORD(v18) = v9;
      if ( !v9 )
        v18 = *(_QWORD *)(v61 + 8);
      v19 = OREnumKey(v18, v8, (_DWORD)v17, (unsigned int)&v62, 0, 0, 0);
      if ( v19 )
        break;
      v17[(unsigned int)v62] = 0;
      v47[0] = v48;
      v47[1] = v48;
      v48[0] = 0;
      v20 = -1;
      if ( a2 )
      {
        v54 = a2;
        do
          ++v20;
        while ( *(_WORD *)(a2 + 2 * v20) );
        v55 = v20;
        if ( !(unsigned __int8)Csl::Path::Assign((Csl::Path *)v47) )
        {
          v12 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x469,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)0x8007000ELL,
            v46);
          if ( v47[0] != v48 )
            operator delete(v47[0], (const struct std::nothrow_t *)&std::nothrow);
          if ( v17 )
            operator delete(v17, v33);
          if ( !v9 )
            goto LABEL_103;
          goto LABEL_102;
        }
        v56 = v17;
        v21 = -1;
        do
          ++v21;
        while ( v17[v21] );
        v57 = v21;
        if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v47) )
        {
          v12 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x46A,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)0x8007000ELL,
            v46);
          if ( v47[0] != v48 )
            operator delete(v47[0], (const struct std::nothrow_t *)&std::nothrow);
          if ( v17 )
            operator delete(v17, v23);
          if ( !v9 )
            goto LABEL_103;
          goto LABEL_102;
        }
      }
      else
      {
        v58 = v17;
        do
          ++v20;
        while ( v17[v20] );
        v59 = v20;
        if ( !(unsigned __int8)Csl::Path::Assign((Csl::Path *)v47) )
        {
          v12 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x46E,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)0x8007000ELL,
            v46);
          if ( v47[0] != v48 )
            operator delete(v47[0], (const struct std::nothrow_t *)&std::nothrow);
          if ( v17 )
            operator delete(v17, v38);
          if ( !v9 )
            goto LABEL_103;
          goto LABEL_102;
        }
      }
      v52 = si128;
      v53 = -1;
      LOBYTE(v22) = 1;
      v24 = Csl::OfflineHive::EnumerateSubkeys(v61, v47[0], &v52, v22);
      v12 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x475,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
          (const char *)(unsigned int)v24,
          v46);
        utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&v52);
        if ( v47[0] != v48 )
          operator delete(v47[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v17 )
          operator delete(v17, v37);
        if ( !v9 )
          goto LABEL_103;
        goto LABEL_102;
      }
      v25 = v52.m128i_i64[1];
      v26 = v52.m128i_i64[0];
      v27 = v49.m128i_i64[1];
      v28 = (v49.m128i_i64[1] - v49.m128i_i64[0]) >> 5;
      v29 = v28 + ((v52.m128i_i64[1] - v52.m128i_i64[0]) >> 5);
      v30 = (v7 - v49.m128i_i64[0]) >> 5;
      if ( v29 > v30 )
      {
        v31 = v30 >> 2;
        v32 = v28 + ((v52.m128i_i64[1] - v52.m128i_i64[0]) >> 5);
        if ( 7 * v31 + 8 >= v29 )
          v32 = 7 * v31 + 8;
        if ( v32 > 0x3FFFFFFFFFFFFFFLL )
          v32 = 0x3FFFFFFFFFFFFFFLL;
        if ( v29 > v32
          || !(unsigned __int8)utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_SetCapacity(&v49) )
        {
          v12 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x478,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)0x8007000ELL,
            v46);
          utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&v52);
          if ( v47[0] != v48 )
            operator delete(v47[0], (const struct std::nothrow_t *)&std::nothrow);
          if ( v17 )
            operator delete(v17, v34);
          if ( !v9 )
            goto LABEL_103;
          goto LABEL_102;
        }
        v27 = v49.m128i_i64[1];
        v25 = v52.m128i_i64[1];
        v26 = v52.m128i_i64[0];
      }
      v62 = v26;
      if ( !utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_InsertManyFillFn<_lambda_ed58fc3d430a473cb6fe469fa0fa9d34_>(
              &v49,
              v27,
              (v25 - v26) >> 5,
              &v62) )
      {
        v12 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x47B,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
          (const char *)0x8007000ELL,
          v46);
        utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&v52);
        if ( v47[0] != v48 )
          operator delete(v47[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v17 )
          operator delete(v17, v36);
        if ( !v9 )
          goto LABEL_103;
        goto LABEL_102;
      }
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&v52);
      if ( !(unsigned __int8)utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::emplace_back<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const &,0>(
                               &v49,
                               v47) )
      {
        v12 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x47F,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
          (const char *)0x8007000ELL,
          v46);
        if ( v47[0] != v48 )
          operator delete(v47[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v17 )
          operator delete(v17, v35);
        if ( !v9 )
          goto LABEL_103;
        goto LABEL_102;
      }
      if ( v47[0] != v48 )
        operator delete(v47[0], (const struct std::nothrow_t *)&std::nothrow);
      ++v8;
      v7 = v50;
      if ( v8 >= v63 )
        goto LABEL_99;
    }
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x45E,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)v19,
            v46);
    if ( v17 )
      operator delete(v17, v39);
    if ( !v9 )
      goto LABEL_103;
    goto LABEL_102;
  }
LABEL_99:
  v41 = v49.m128i_i64[1];
  v40 = v49.m128i_i64[0];
  v49 = si128;
  v50 = -1;
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(a3);
  *a3 = v40;
  a3[1] = v41;
  a3[2] = v7;
  v12 = 0;
  if ( v17 )
    operator delete(v17, v42);
  if ( v9 )
LABEL_102:
    ORCloseKey(v9);
LABEL_103:
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&v49);
  return v12;
}

```

## disassembly

```asm
0x140021d08  mov     rax, rsp
0x140021d0b  mov     [rax+18h], rbx
0x140021d0f  mov     [rax+20h], r9b
0x140021d13  mov     [rax+8], rcx
0x140021d17  push    rbp
0x140021d18  push    rsi
0x140021d19  push    rdi
0x140021d1a  push    r12
0x140021d1c  push    r13
0x140021d1e  push    r14
0x140021d20  push    r15
0x140021d22  lea     rbp, [rax-5Fh]
0x140021d26  sub     rsp, 100h
0x140021d2d  movaps  xmmword ptr [rax-48h], xmm6
0x140021d31  mov     r13, r8
0x140021d34  mov     rdi, rdx
0x140021d37  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140021d3f  movdqu  [rbp+57h+var_B0], xmm6
0x140021d44  or      r14, 0FFFFFFFFFFFFFFFFh
0x140021d48  mov     r15, r14
0x140021d4b  mov     [rbp+57h+var_A0], r14
0x140021d4f  xor     r12d, r12d
0x140021d52  mov     esi, r12d
0x140021d55  mov     [rbp+57h+arg_8], r12
0x140021d59  test    rdx, rdx
0x140021d5c  jz      short loc_140021DD9
0x140021d5e  mov     rax, r14
0x140021d61  inc     rax
0x140021d64  cmp     [rdx+rax*2], r12w
0x140021d69  jnz     short loc_140021D61
0x140021d6b  test    rax, rax
0x140021d6e  jz      short loc_140021DD9
0x140021d70  lea     r8, [rbp+57h+arg_8]
0x140021d74  mov     rcx, [rcx+8]
0x140021d78  call    OROpenKey
0x140021d7d  cmp     eax, 2
0x140021d80  jnz     short loc_140021D9B
0x140021d82  mov     rcx, [rbp+57h+arg_8]
0x140021d86  test    rcx, rcx
0x140021d89  jz      short loc_140021D91
0x140021d8b  call    ORCloseKey
0x140021d90  nop
0x140021d91  mov     ebx, 80070002h
0x140021d96  jmp     loc_1400223A8
0x140021d9b  test    eax, eax
0x140021d9d  jz      short loc_140021DD1
0x140021d9f  mov     rcx, [rbp+5Fh]; this
0x140021da3  mov     r9d, eax; char *
0x140021da6  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140021dad  mov     edx, 43Bh; void *
0x140021db2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140021db7  mov     ebx, eax
0x140021db9  mov     rcx, [rbp+57h+arg_8]
0x140021dbd  test    rcx, rcx
0x140021dc0  jz      loc_1400223A8
0x140021dc6  call    ORCloseKey
0x140021dcb  nop
0x140021dcc  jmp     loc_1400223A8
0x140021dd1  mov     rsi, [rbp+57h+arg_8]
0x140021dd5  mov     rcx, [rbp+57h+arg_0]
0x140021dd9  mov     [rbp+57h+arg_18], r12d
0x140021ddd  mov     dword ptr [rbp+57h+arg_8], r12d
0x140021de1  test    rsi, rsi
0x140021de4  jz      short loc_140021DEB
0x140021de6  mov     rcx, rsi
0x140021de9  jmp     short loc_140021DEF
0x140021deb  mov     rcx, [rcx+8]
0x140021def  mov     [rsp+130h+var_E0], r12
0x140021df4  mov     [rsp+130h+var_E8], r12
0x140021df9  mov     [rsp+130h+var_F0], r12
0x140021dfe  mov     [rsp+130h+var_F8], r12
0x140021e03  mov     [rsp+130h+var_100], r12
0x140021e08  mov     [rsp+130h+var_108], r12
0x140021e0d  lea     rax, [rbp+57h+arg_8]
0x140021e11  mov     qword ptr [rsp+130h+var_110], rax; unsigned int
0x140021e16  lea     r9, [rbp+57h+arg_18]
0x140021e1a  xor     r8d, r8d
0x140021e1d  xor     edx, edx
0x140021e1f  call    ORQueryInfoKey
0x140021e24  test    eax, eax
0x140021e26  jz      short loc_140021E59
0x140021e28  mov     rcx, [rbp+5Fh]; this
0x140021e2c  mov     r9d, eax; char *
0x140021e2f  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140021e36  mov     edx, 44Dh; void *
0x140021e3b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140021e40  mov     ebx, eax
0x140021e42  test    rsi, rsi
0x140021e45  jz      loc_1400223A8
0x140021e4b  mov     rcx, rsi
0x140021e4e  call    ORCloseKey
0x140021e53  nop
0x140021e54  jmp     loc_1400223A8
0x140021e59  mov     eax, dword ptr [rbp+57h+arg_8]
0x140021e5c  inc     eax
0x140021e5e  mov     [rbp+57h+var_98], eax
0x140021e61  mov     ecx, eax
0x140021e63  mov     eax, 2
0x140021e68  mul     rcx
0x140021e6b  mov     rbx, rax
0x140021e6e  cmovb   rbx, r14
0x140021e72  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140021e79  mov     rcx, rbx; unsigned __int64
0x140021e7c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140021e81  mov     r14, rax
0x140021e84  test    rax, rax
0x140021e87  jz      short loc_140021E98
0x140021e89  mov     r8, rbx; Size
0x140021e8c  xor     edx, edx; Val
0x140021e8e  mov     rcx, rax; void *
0x140021e91  call    memset_0
0x140021e96  jmp     short loc_140021E9B
0x140021e98  mov     r14, r12
0x140021e9b  xor     edx, edx
0x140021e9d  cmp     [rbp+57h+arg_18], edx
0x140021ea0  jbe     loc_140022362
0x140021ea6  mov     eax, [rbp+57h+var_98]
0x140021ea9  mov     dword ptr [rbp+57h+arg_8], eax
0x140021eac  mov     rbx, [rbp+57h+arg_0]
0x140021eb0  test    rsi, rsi
0x140021eb3  mov     rcx, rsi
0x140021eb6  jnz     short loc_140021EBC
0x140021eb8  mov     rcx, [rbx+8]
0x140021ebc  mov     [rsp+130h+var_100], rdx
0x140021ec1  mov     [rsp+130h+var_108], rdx
0x140021ec6  mov     qword ptr [rsp+130h+var_110], rdx; unsigned int
0x140021ecb  lea     r9, [rbp+57h+arg_8]
0x140021ecf  mov     r8, r14
0x140021ed2  mov     edx, r12d
0x140021ed5  call    OREnumKey
0x140021eda  xor     edx, edx
0x140021edc  test    eax, eax
0x140021ede  jnz     loc_14002232B
0x140021ee4  mov     ecx, dword ptr [rbp+57h+arg_8]
0x140021ee7  mov     [r14+rcx*2], dx
0x140021eec  lea     rax, [rbp+57h+var_C0]
0x140021ef0  mov     [rbp+57h+var_D0], rax
0x140021ef4  lea     rax, [rbp+57h+var_C0]
0x140021ef8  mov     [rbp+57h+var_C8], rax
0x140021efc  mov     [rbp+57h+var_C0], dx
0x140021f00  or      rax, 0FFFFFFFFFFFFFFFFh
0x140021f04  test    rdi, rdi
0x140021f07  jz      loc_140021FBA
0x140021f0d  mov     [rbp+57h+var_78], rdi
0x140021f11  inc     rax
0x140021f14  cmp     [rdi+rax*2], dx
0x140021f18  jnz     short loc_140021F11
0x140021f1a  mov     [rbp+57h+var_70], rax
0x140021f1e  lea     rdx, [rbp+57h+var_78]
0x140021f22  lea     rcx, [rbp+57h+var_D0]; this
0x140021f26  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x140021f2b  xor     ecx, ecx
0x140021f2d  test    al, al
0x140021f2f  jz      loc_1400220FC
0x140021f35  mov     [rbp+57h+var_68], r14
0x140021f39  or      rax, 0FFFFFFFFFFFFFFFFh
0x140021f3d  inc     rax
0x140021f40  cmp     [r14+rax*2], cx
0x140021f45  jnz     short loc_140021F3D
0x140021f47  mov     [rbp+57h+var_60], rax
0x140021f4b  lea     rdx, [rbp+57h+var_68]
0x140021f4f  lea     rcx, [rbp+57h+var_D0]; this
0x140021f53  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x140021f58  test    al, al
0x140021f5a  jnz     loc_140021FE1
0x140021f60  mov     rcx, [rbp+5Fh]; this
0x140021f64  mov     ebx, 8007000Eh
0x140021f69  mov     r9d, ebx; char *
0x140021f6c  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140021f73  mov     edx, 46Ah; void *
0x140021f78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140021f7d  mov     rcx, [rbp+57h+var_D0]; void *
0x140021f81  lea     rax, [rbp+57h+var_C0]
0x140021f85  cmp     rcx, rax
0x140021f88  jz      short loc_140021F96
0x140021f8a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140021f91  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140021f96  test    r14, r14
0x140021f99  jz      short loc_140021FA3
0x140021f9b  mov     rcx, r14; void *
0x140021f9e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140021fa3  test    rsi, rsi
0x140021fa6  jz      loc_1400223A8
0x140021fac  mov     rcx, rsi
0x140021faf  call    ORCloseKey
0x140021fb4  nop
0x140021fb5  jmp     loc_1400223A8
0x140021fba  mov     [rbp+57h+var_58], r14
0x140021fbe  inc     rax
0x140021fc1  cmp     [r14+rax*2], dx
0x140021fc6  jnz     short loc_140021FBE
0x140021fc8  mov     [rbp+57h+var_50], rax
0x140021fcc  lea     rdx, [rbp+57h+var_58]
0x140021fd0  lea     rcx, [rbp+57h+var_D0]; this
0x140021fd4  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x140021fd9  test    al, al
0x140021fdb  jz      loc_1400222D4
0x140021fe1  movdqu  [rbp+57h+var_90], xmm6
0x140021fe6  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFFh
0x140021fee  mov     r9b, 1
0x140021ff1  lea     r8, [rbp+57h+var_90]
0x140021ff5  mov     rdx, [rbp+57h+var_D0]
0x140021ff9  mov     rcx, rbx
0x140021ffc  call    ?EnumerateSubkeys@OfflineHive@Csl@@QEBAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@_N@Z; Csl::OfflineHive::EnumerateSubkeys(ushort const *,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &,bool)
0x140022001  mov     ebx, eax
0x140022003  test    eax, eax
0x140022005  js      loc_140022276
0x14002200b  mov     r8, qword ptr [rbp+57h+var_90+8]
0x14002200f  mov     r9, r8
0x140022012  mov     rax, qword ptr [rbp+57h+var_90]
0x140022016  sub     r9, rax
0x140022019  sar     r9, 5
0x14002201d  mov     r10, qword ptr [rbp+57h+var_B0+8]
0x140022021  mov     rcx, r10
0x140022024  sub     rcx, qword ptr [rbp+57h+var_B0]
0x140022028  sar     rcx, 5
0x14002202c  add     r9, rcx
0x14002202f  sub     r15, qword ptr [rbp+57h+var_B0]
0x140022033  sar     r15, 5
0x140022037  cmp     r9, r15
0x14002203a  jbe     short loc_140022089
0x14002203c  shr     r15, 2
0x140022040  imul    rax, r15, 7
0x140022044  add     rax, 8
0x140022048  mov     rdx, r9
0x14002204b  cmp     rax, r9
0x14002204e  cmovnb  rdx, rax
0x140022052  mov     rbx, 3FFFFFFFFFFFFFFh
0x14002205c  cmp     rdx, rbx
0x14002205f  cmova   rdx, rbx
0x140022063  cmp     r9, rdx
0x140022066  ja      loc_140022156
0x14002206c  lea     rcx, [rbp+57h+var_B0]
0x140022070  call    ?_SetCapacity@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::_SetCapacity(unsigned __int64)
0x140022075  test    al, al
0x140022077  jz      loc_140022156
0x14002207d  mov     r10, qword ptr [rbp+57h+var_B0+8]
0x140022081  mov     r8, qword ptr [rbp+57h+var_90+8]
0x140022085  mov     rax, qword ptr [rbp+57h+var_90]
0x140022089  mov     [rbp+57h+arg_8], rax
0x14002208d  sub     r8, rax
0x140022090  sar     r8, 5
0x140022094  lea     r9, [rbp+57h+arg_8]
0x140022098  mov     rdx, r10
0x14002209b  lea     rcx, [rbp+57h+var_B0]
0x14002209f  call    ??$_InsertManyFillFn@V_lambda_ed58fc3d430a473cb6fe469fa0fa9d34_@@@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@AEAAPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@PEAV21@_KV_lambda_ed58fc3d430a473cb6fe469fa0fa9d34_@@@Z; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::_InsertManyFillFn<_lambda_ed58fc3d430a473cb6fe469fa0fa9d34_>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,unsigned __int64,_lambda_ed58fc3d430a473cb6fe469fa0fa9d34_)
0x1400220a4  test    rax, rax
0x1400220a7  jz      loc_140022213
0x1400220ad  lea     rcx, [rbp+57h+var_90]
0x1400220b1  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x1400220b6  lea     rdx, [rbp+57h+var_D0]
0x1400220ba  lea     rcx, [rbp+57h+var_B0]
0x1400220be  call    ??$emplace_back@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@$0A@@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::emplace_back<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,0>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x1400220c3  test    al, al
0x1400220c5  jz      loc_1400221B9
0x1400220cb  mov     rcx, [rbp+57h+var_D0]; void *
0x1400220cf  lea     rax, [rbp+57h+var_C0]
0x1400220d3  cmp     rcx, rax
0x1400220d6  jz      short loc_1400220E4
0x1400220d8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400220df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400220e4  inc     r12d
0x1400220e7  mov     r15, [rbp+57h+var_A0]
0x1400220eb  cmp     r12d, [rbp+57h+arg_18]
0x1400220ef  jnb     loc_140022362
0x1400220f5  xor     edx, edx
0x1400220f7  jmp     loc_140021EA6
0x1400220fc  mov     rcx, [rbp+5Fh]; this
0x140022100  mov     ebx, 8007000Eh
0x140022105  mov     r9d, ebx; char *
0x140022108  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14002210f  mov     edx, 469h; void *
0x140022114  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022119  mov     rcx, [rbp+57h+var_D0]; void *
0x14002211d  lea     rax, [rbp+57h+var_C0]
0x140022121  cmp     rcx, rax
0x140022124  jz      short loc_140022132
0x140022126  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002212d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140022132  test    r14, r14
0x140022135  jz      short loc_14002213F
0x140022137  mov     rcx, r14; void *
0x14002213a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002213f  test    rsi, rsi
0x140022142  jz      loc_1400223A8
0x140022148  mov     rcx, rsi
0x14002214b  call    ORCloseKey
0x140022150  nop
0x140022151  jmp     loc_1400223A8
0x140022156  mov     rcx, [rbp+5Fh]; this
0x14002215a  mov     ebx, 8007000Eh
0x14002215f  mov     r9d, ebx; char *
0x140022162  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140022169  mov     edx, 478h; void *
0x14002216e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022173  lea     rcx, [rbp+57h+var_90]
0x140022177  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14002217c  mov     rcx, [rbp+57h+var_D0]; void *
0x140022180  lea     rax, [rbp+57h+var_C0]
0x140022184  cmp     rcx, rax
  ... truncated ...
```
