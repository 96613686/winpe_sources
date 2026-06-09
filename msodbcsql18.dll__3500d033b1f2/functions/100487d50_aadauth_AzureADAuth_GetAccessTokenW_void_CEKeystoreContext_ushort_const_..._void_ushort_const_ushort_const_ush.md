# aadauth::AzureADAuth::GetAccessTokenW(void (*)(CEKeystoreContext *,ushort const *,...),void *,ushort const *,ushort const *,ushort const *,ushort const *,int,ulong,ushort const *,ushort * *,ulong *)

- ea: `0x100487d50`
- end: `0x1004886a6`
- name: `?GetAccessTokenW@AzureADAuth@aadauth@@QEBAJP6AXPEAUCEKeystoreContext@@PEBGZZPEAX1111HK1PEAPEAGPEAK@Z`
- size: `2390`
- prototype: `__int64 __fastcall(aadauth::AzureADAuth *__hidden this, void (*)(struct CEKeystoreContext *, const unsigned __int16 *, ...), void *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, unsigned int, const unsigned __int16 *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x100453f4c`

## callees

- `0x10040128c`
- `0x100407940`
- `0x10042a440`
- `0x100431464`
- `0x10046ffa4`
- `0x1004700b4`
- `0x1004837f0`
- `0x100486398`
- `0x100487d50`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `VCRUNTIME140!strstr` at `0x100488312`
- `VCRUNTIME140!strstr` at `0x100488312`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004883da`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004883da`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100488164`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004881af`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004881fa`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100488245`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100488299`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004884d5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004884dc`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004884e3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10048868a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100488691`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100488698`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10048869f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100488164`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004881af`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004881fa`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100488245`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100488299`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004884d5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004884dc`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004884e3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10048868a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100488691`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x100488698`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10048869f`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall aadauth::AzureADAuth::GetAccessTokenW(
        aadauth::AzureADAuth *this,
        void (*a2)(struct CEKeystoreContext *, const unsigned __int16 *, ...),
        struct CEKeystoreContext *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        int a8,
        unsigned int a9,
        const unsigned __int16 *a10,
        unsigned __int16 **a11,
        unsigned int *a12)
{
  char v13; // r15
  const unsigned __int16 *v14; // rax
  __int64 i; // r8
  const unsigned __int16 *v16; // rax
  __int64 j; // r8
  const unsigned __int16 *v18; // rax
  __int64 k; // r8
  const unsigned __int16 *v20; // rax
  __int64 m; // r8
  const unsigned __int16 *v22; // rax
  __int64 n; // r8
  char *v24; // rbx
  void **v25; // rax
  void **v26; // r10
  void **v27; // r8
  void **v28; // rdx
  struct CEKeystoreContext *v29; // rsi
  unsigned int AccessToken; // edi
  char **v31; // r9
  void *v32; // rdx
  void *v33; // rdx
  void *v34; // rdx
  void *v35; // rdx
  void *v36; // rdx
  sqlencrypt::utils *v37; // rcx
  char *Value; // rax
  char **v39; // r9
  sqlencrypt::utils *v40; // rcx
  const char *v41; // rax
  char *v42; // rax
  sqlencrypt::utils **v43; // r8
  char *v44; // r8
  sqlencrypt::utils **v45; // rdx
  unsigned __int16 *v46; // rax
  unsigned int v47; // ebx
  void **v48; // r8
  void *v49; // rcx
  void *v50; // rcx
  sqlencrypt::utils *v51; // rdx
  void *v52; // rcx
  void *v53; // rcx
  void *v54; // rcx
  void *v55; // rcx
  char v57; // [rsp+60h] [rbp-A0h]
  char v58[8]; // [rsp+68h] [rbp-98h] BYREF
  struct CEKeystoreContext *v59; // [rsp+70h] [rbp-90h]
  aadauth::AzureADAuth *v60; // [rsp+78h] [rbp-88h]
  unsigned __int16 **v61; // [rsp+80h] [rbp-80h]
  __int64 v62; // [rsp+88h] [rbp-78h]
  sqlencrypt::utils *v63[2]; // [rsp+90h] [rbp-70h] BYREF
  __m128i v64; // [rsp+A0h] [rbp-60h]
  void *Source[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v66; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v67; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v68; // [rsp+D0h] [rbp-30h] BYREF
  __m128i v69; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v70; // [rsp+F0h] [rbp-10h] BYREF
  __m128i v71; // [rsp+100h] [rbp+0h]
  unsigned __int64 v72; // [rsp+110h] [rbp+10h] BYREF
  __m128i v73; // [rsp+120h] [rbp+20h]
  unsigned __int64 v74; // [rsp+130h] [rbp+30h] BYREF
  __m128i v75; // [rsp+140h] [rbp+40h]
  unsigned __int64 v76; // [rsp+150h] [rbp+50h] BYREF
  __m128i si128; // [rsp+160h] [rbp+60h]
  void *v78[2]; // [rsp+170h] [rbp+70h] BYREF
  __m128i v79; // [rsp+180h] [rbp+80h]
  void *v80[2]; // [rsp+190h] [rbp+90h] BYREF
  __m128i v81; // [rsp+1A0h] [rbp+A0h]
  void *v82[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  __m128i v83; // [rsp+1C0h] [rbp+C0h]
  void *v84[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  __m128i v85; // [rsp+1E0h] [rbp+E0h]
  void *Src[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  __m128i v87; // [rsp+200h] [rbp+100h]

  v62 = -2;
  v59 = a3;
  v60 = this;
  v61 = a11;
  v13 = 0;
  *(_DWORD *)v58 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v76) = 0;
  v14 = a4;
  for ( i = 0; *v14; ++v14 )
    ++i;
  std::basic_string<char16_t>::assign(&v76, a4, i);
  v75 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v74) = 0;
  v16 = a5;
  for ( j = 0; *v16; ++v16 )
    ++j;
  std::basic_string<char16_t>::assign(&v74, a5, j);
  v73 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v72) = 0;
  v18 = a6;
  for ( k = 0; *v18; ++v18 )
    ++k;
  std::basic_string<char16_t>::assign(&v72, a6, k);
  v71 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v70) = 0;
  v20 = a7;
  for ( m = 0; *v20; ++v20 )
    ++m;
  std::basic_string<char16_t>::assign(&v70, a7, m);
  v64 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v63[0]) = 0;
  v69 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v68) = 0;
  v22 = a10;
  for ( n = 0; *v22; ++v22 )
    ++n;
  std::basic_string<char16_t>::assign(&v68, a10, n);
  if ( a8 == 5 )
  {
    v24 = (char *)aadauth::AzureADAuth::stsMSI;
  }
  else
  {
    v87 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(Src[0]) = 0;
    std::string::_Construct<char16_t const *>(Src);
    v13 = 1;
    *(_DWORD *)v58 = 1;
    v24 = (char *)Src;
    if ( v87.m128i_i64[1] >= 0x10uLL )
      v24 = (char *)Src[0];
  }
  v85 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v84[0]) = 0;
  std::string::_Construct<char16_t const *>(v84);
  v83 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v82[0]) = 0;
  std::string::_Construct<char16_t const *>(v82);
  v81 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v80[0]) = 0;
  std::string::_Construct<char16_t const *>(v80);
  v79 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v78[0]) = 0;
  std::string::_Construct<char16_t const *>(v78);
  v25 = v84;
  if ( v85.m128i_i64[1] >= 0x10uLL )
    v25 = (void **)v84[0];
  v26 = v82;
  if ( v83.m128i_i64[1] >= 0x10uLL )
    v26 = (void **)v82[0];
  v27 = v80;
  if ( v81.m128i_i64[1] >= 0x10uLL )
    v27 = (void **)v80[0];
  v28 = v78;
  if ( v79.m128i_i64[1] >= 0x10uLL )
    v28 = (void **)v78[0];
  v29 = v59;
  AccessToken = aadauth::AzureADAuth::GetAccessToken(
                  (__int64)v60,
                  (void (__fastcall *)(__int64, __int64, __int64, _QWORD *))a2,
                  (__int64)v59,
                  a8,
                  v28,
                  (__int64)v27,
                  v24,
                  (__int64)v26,
                  a9,
                  (__int64)v25,
                  (__int64)v63,
                  0);
  if ( v79.m128i_i64[1] >= 0x10uLL )
  {
    v32 = v78[0];
    if ( (unsigned __int64)(v79.m128i_i64[1] + 1) >= 0x1000 )
    {
      if ( ((__int64)v78[0] & 0x1F) != 0
        || (v32 = (void *)*((_QWORD *)v78[0] - 1), v32 >= v78[0])
        || (unsigned __int64)((char *)v78[0] - (char *)v32 - 8) > 0x1F )
      {
        _invalid_parameter_noinfo_noreturn();
      }
    }
    operator delete(v32);
  }
  if ( v81.m128i_i64[1] >= 0x10uLL )
  {
    v33 = v80[0];
    if ( (unsigned __int64)(v81.m128i_i64[1] + 1) >= 0x1000 )
    {
      if ( ((__int64)v80[0] & 0x1F) != 0
        || (v33 = (void *)*((_QWORD *)v80[0] - 1), v33 >= v80[0])
        || (unsigned __int64)((char *)v80[0] - (char *)v33 - 8) > 0x1F )
      {
        _invalid_parameter_noinfo_noreturn();
      }
    }
    operator delete(v33);
  }
  if ( v83.m128i_i64[1] >= 0x10uLL )
  {
    v34 = v82[0];
    if ( (unsigned __int64)(v83.m128i_i64[1] + 1) >= 0x1000 )
    {
      if ( ((__int64)v82[0] & 0x1F) != 0
        || (v34 = (void *)*((_QWORD *)v82[0] - 1), v34 >= v82[0])
        || (unsigned __int64)((char *)v82[0] - (char *)v34 - 8) > 0x1F )
      {
        _invalid_parameter_noinfo_noreturn();
      }
    }
    operator delete(v34);
  }
  if ( v85.m128i_i64[1] >= 0x10uLL )
  {
    v35 = v84[0];
    if ( (unsigned __int64)(v85.m128i_i64[1] + 1) >= 0x1000 )
    {
      if ( ((__int64)v84[0] & 0x1F) != 0
        || (v35 = (void *)*((_QWORD *)v84[0] - 1), v35 >= v84[0])
        || (unsigned __int64)((char *)v84[0] - (char *)v35 - 8) > 0x1F )
      {
        _invalid_parameter_noinfo_noreturn();
      }
    }
    operator delete(v35);
  }
  if ( (v13 & 1) != 0 && v87.m128i_i64[1] >= 0x10uLL )
  {
    v36 = Src[0];
    if ( (unsigned __int64)(v87.m128i_i64[1] + 1) >= 0x1000 )
    {
      if ( ((__int64)Src[0] & 0x1F) != 0
        || (v36 = (void *)*((_QWORD *)Src[0] - 1), v36 >= Src[0])
        || (unsigned __int64)((char *)Src[0] - (char *)v36 - 8) > 0x1F )
      {
        _invalid_parameter_noinfo_noreturn();
      }
    }
    operator delete(v36);
  }
  if ( AccessToken )
  {
    v37 = (sqlencrypt::utils *)v63;
    if ( v64.m128i_i64[1] >= 0x10uLL )
      v37 = v63[0];
    Value = sqlencrypt::utils::ExtractValue(v37, "\"error_description\":\"", v58, v31);
    v40 = (sqlencrypt::utils *)v63;
    if ( Value )
    {
      **(_BYTE **)v58 = 0;
LABEL_69:
      std::string::assign(v63);
      goto LABEL_70;
    }
    if ( v64.m128i_i64[1] >= 0x10uLL )
      v40 = v63[0];
    v41 = sqlencrypt::utils::ExtractValue(v40, "<s:Reason>", v58, v39);
    if ( v41 )
    {
      v42 = strstr(v41, "</s:Reason>");
      *(_QWORD *)v58 = v42;
      if ( v42 )
        *v42 = 0;
      goto LABEL_69;
    }
  }
LABEL_70:
  v43 = v63;
  if ( v64.m128i_i64[1] >= 0x10uLL )
    v43 = (sqlencrypt::utils **)v63[0];
  v44 = (char *)v43 + v64.m128i_i64[0];
  v45 = v63;
  if ( v64.m128i_i64[1] >= 0x10uLL )
    v45 = (sqlencrypt::utils **)v63[0];
  v66 = 0;
  v67 = 7;
  LOWORD(Source[0]) = 0;
  LOBYTE(v31) = v57;
  std::basic_string<char16_t>::_Construct<char *>(Source, v45, v44, v31);
  *a12 = 2 * v66 + 2;
  v46 = (unsigned __int16 *)operator new[](saturated_mul(v66 + 1, 2u));
  *v61 = v46;
  if ( v46 )
  {
    v48 = Source;
    if ( v67 >= 8 )
      v48 = (void **)Source[0];
    memcpy_s(v46, *a12, v48, *a12);
    v47 = AccessToken;
  }
  else
  {
    v47 = 40157;
    a2(v29, (const unsigned __int16 *)40157);
  }
  if ( v67 >= 8 )
  {
    v49 = Source[0];
    if ( v67 + 1 > 0x7FFFFFFFFFFFFFFFLL
      || 2 * (v67 + 1) >= 0x1000
      && (((__int64)Source[0] & 0x1F) != 0
       || (v49 = (void *)*((_QWORD *)Source[0] - 1), v49 >= Source[0])
       || (unsigned __int64)((char *)Source[0] - (char *)v49 - 8) > 0x1F) )
    {
      _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v49);
  }
  v66 = 0;
  v67 = 7;
  LOWORD(Source[0]) = 0;
  if ( v69.m128i_i64[1] >= 8uLL )
  {
    v50 = (void *)v68;
    if ( (unsigned __int64)(v69.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL
      || (unsigned __int64)(2 * (v69.m128i_i64[1] + 1)) >= 0x1000
      && ((v68 & 0x1F) != 0
       || (v50 = *(void **)(v68 - 8), (unsigned __int64)v50 >= v68)
       || v68 - (unsigned __int64)v50 - 8 > 0x1F) )
    {
      _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v50);
  }
  v69 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v68) = 0;
  if ( v64.m128i_i64[1] >= 0x10uLL )
  {
    v51 = v63[0];
    if ( (unsigned __int64)(v64.m128i_i64[1] + 1) >= 0x1000 )
    {
      if ( ((__int64)v63[0] & 0x1F) != 0
        || (v51 = (sqlencrypt::utils *)*((_QWORD *)v63[0] - 1), v51 >= v63[0])
        || (unsigned __int64)(v63[0] - v51 - 8) > 0x1F )
      {
        _invalid_parameter_noinfo_noreturn();
      }
    }
    operator delete(v51);
  }
  v64 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v63[0]) = 0;
  if ( v71.m128i_i64[1] >= 8uLL )
  {
    v52 = (void *)v70;
    if ( (unsigned __int64)(v71.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL
      || (unsigned __int64)(2 * (v71.m128i_i64[1] + 1)) >= 0x1000
      && ((v70 & 0x1F) != 0
       || (v52 = *(void **)(v70 - 8), (unsigned __int64)v52 >= v70)
       || v70 - (unsigned __int64)v52 - 8 > 0x1F) )
    {
      _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v52);
  }
  v71 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v70) = 0;
  if ( v73.m128i_i64[1] >= 8uLL )
  {
    v53 = (void *)v72;
    if ( (unsigned __int64)(v73.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL
      || (unsigned __int64)(2 * (v73.m128i_i64[1] + 1)) >= 0x1000
      && ((v72 & 0x1F) != 0
       || (v53 = *(void **)(v72 - 8), (unsigned __int64)v53 >= v72)
       || v72 - (unsigned __int64)v53 - 8 > 0x1F) )
    {
      _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v53);
  }
  v73 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v72) = 0;
  if ( v75.m128i_i64[1] >= 8uLL )
  {
    v54 = (void *)v74;
    if ( (unsigned __int64)(v75.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL
      || (unsigned __int64)(2 * (v75.m128i_i64[1] + 1)) >= 0x1000
      && ((v74 & 0x1F) != 0
       || (v54 = *(void **)(v74 - 8), (unsigned __int64)v54 >= v74)
       || v74 - (unsigned __int64)v54 - 8 > 0x1F) )
    {
      _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v54);
  }
  v75 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v74) = 0;
  if ( si128.m128i_i64[1] >= 8uLL )
  {
    v55 = (void *)v76;
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) > 0x7FFFFFFFFFFFFFFFLL
      || (unsigned __int64)(2 * (si128.m128i_i64[1] + 1)) >= 0x1000
      && ((v76 & 0x1F) != 0
       || (v55 = *(void **)(v76 - 8), (unsigned __int64)v55 >= v76)
       || v76 - (unsigned __int64)v55 - 8 > 0x1F) )
    {
      _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v55);
  }
  return v47;
}

```

## disassembly

```asm
0x100487d50  push    rbp
0x100487d52  push    rbx
0x100487d53  push    rsi
0x100487d54  push    rdi
0x100487d55  push    r12
0x100487d57  push    r13
0x100487d59  push    r14
0x100487d5b  push    r15
0x100487d5d  lea     rbp, [rsp-128h]
0x100487d65  sub     rsp, 228h
0x100487d6c  mov     [rbp+160h+var_1D8], 0FFFFFFFFFFFFFFFEh
0x100487d74  mov     rax, cs:__security_cookie
0x100487d7b  xor     rax, rsp
0x100487d7e  mov     [rbp+160h+var_50], rax
0x100487d85  mov     [rsp+260h+var_1F0], r8
0x100487d8a  mov     r13, rdx
0x100487d8d  mov     [rsp+260h+var_1E8], rcx
0x100487d92  mov     rbx, [rbp+160h+arg_20]
0x100487d99  mov     rdi, [rbp+160h+arg_28]
0x100487da0  mov     rsi, [rbp+160h+arg_30]
0x100487da7  mov     r14, [rbp+160h+arg_48]
0x100487dae  mov     rax, [rbp+160h+arg_50]
0x100487db5  mov     [rbp+160h+var_1E0], rax
0x100487db9  mov     r12, [rbp+160h+arg_58]
0x100487dc0  xor     ecx, ecx
0x100487dc2  mov     r15d, ecx
0x100487dc5  mov     dword ptr [rsp+260h+var_1F8], ecx
0x100487dc9  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100487dd1  movdqu  [rbp+160h+var_100], xmm0
0x100487dd6  mov     word ptr [rbp+160h+var_110], cx
0x100487dda  mov     rax, r9
0x100487ddd  mov     r8d, ecx
0x100487de0  cmp     [r9], cx
0x100487de4  jz      short loc_100487DF2
0x100487de6  inc     r8
0x100487de9  lea     rax, [rax+2]
0x100487ded  cmp     [rax], cx
0x100487df0  jnz     short loc_100487DE6
0x100487df2  mov     rdx, r9
0x100487df5  lea     rcx, [rbp+160h+var_110]
0x100487df9  call    ?assign@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAAEAV12@QEB_S_K@Z; std::basic_string<char16_t>::assign(char16_t const * const,unsigned __int64)
0x100487dfe  nop
0x100487dff  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100487e07  movdqu  [rbp+160h+var_120], xmm0
0x100487e0c  xor     ecx, ecx
0x100487e0e  mov     word ptr [rbp+160h+var_130], cx
0x100487e12  mov     rax, rbx
0x100487e15  mov     r8d, ecx
0x100487e18  cmp     [rbx], cx
0x100487e1b  jz      short loc_100487E29
0x100487e1d  inc     r8
0x100487e20  lea     rax, [rax+2]
0x100487e24  cmp     [rax], cx
0x100487e27  jnz     short loc_100487E1D
0x100487e29  mov     rdx, rbx
0x100487e2c  lea     rcx, [rbp+160h+var_130]
0x100487e30  call    ?assign@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAAEAV12@QEB_S_K@Z; std::basic_string<char16_t>::assign(char16_t const * const,unsigned __int64)
0x100487e35  nop
0x100487e36  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100487e3e  movdqu  [rbp+160h+var_140], xmm0
0x100487e43  xor     ebx, ebx
0x100487e45  mov     word ptr [rbp+160h+var_150], bx
0x100487e49  mov     rax, rdi
0x100487e4c  mov     r8d, ebx
0x100487e4f  cmp     [rdi], bx
0x100487e52  jz      short loc_100487E60
0x100487e54  inc     r8
0x100487e57  lea     rax, [rax+2]
0x100487e5b  cmp     [rax], bx
0x100487e5e  jnz     short loc_100487E54
0x100487e60  mov     rdx, rdi
0x100487e63  lea     rcx, [rbp+160h+var_150]
0x100487e67  call    ?assign@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAAEAV12@QEB_S_K@Z; std::basic_string<char16_t>::assign(char16_t const * const,unsigned __int64)
0x100487e6c  nop
0x100487e6d  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100487e75  movdqu  [rbp+160h+var_160], xmm0
0x100487e7a  mov     word ptr [rbp+160h+var_170], bx
0x100487e7e  mov     rax, rsi
0x100487e81  mov     r8, rbx
0x100487e84  cmp     [rsi], bx
0x100487e87  jz      short loc_100487E95
0x100487e89  inc     r8
0x100487e8c  lea     rax, [rax+2]
0x100487e90  cmp     [rax], bx
0x100487e93  jnz     short loc_100487E89
0x100487e95  mov     rdx, rsi
0x100487e98  lea     rcx, [rbp+160h+var_170]
0x100487e9c  call    ?assign@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAAEAV12@QEB_S_K@Z; std::basic_string<char16_t>::assign(char16_t const * const,unsigned __int64)
0x100487ea1  nop
0x100487ea2  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x100487eaa  movdqu  [rbp+160h+var_1C0], xmm0
0x100487eaf  mov     byte ptr [rbp+160h+var_1D0], bl
0x100487eb2  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x100487eba  movdqu  [rbp+160h+var_180], xmm0
0x100487ebf  mov     word ptr [rbp+160h+var_190], bx
0x100487ec3  mov     rax, r14
0x100487ec6  mov     r8, rbx
0x100487ec9  cmp     [r14], bx
0x100487ecd  jz      short loc_100487EDB
0x100487ecf  inc     r8
0x100487ed2  lea     rax, [rax+2]
0x100487ed6  cmp     [rax], bx
0x100487ed9  jnz     short loc_100487ECF
0x100487edb  mov     rdx, r14
0x100487ede  lea     rcx, [rbp+160h+var_190]
0x100487ee2  call    ?assign@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAAEAV12@QEB_S_K@Z; std::basic_string<char16_t>::assign(char16_t const * const,unsigned __int64)
0x100487ee7  nop
0x100487ee8  mov     edi, 8
0x100487eed  cmp     [rbp+160h+arg_38], 5
0x100487ef4  jnz     short loc_100487F02
0x100487ef6  mov     rbx, cs:?stsMSI@AzureADAuth@aadauth@@0PEBDEB; char const * const aadauth::AzureADAuth::stsMSI
0x100487efd  xor     r14d, r14d
0x100487f00  jmp     short loc_100487F6C
0x100487f02  lea     rcx, [rbp+160h+var_150]
0x100487f06  cmp     qword ptr [rbp+160h+var_140+8], rdi
0x100487f0a  cmovnb  rcx, [rbp+160h+var_150]
0x100487f0f  mov     rax, qword ptr [rbp+160h+var_140]
0x100487f13  lea     r8, [rcx+rax*2]
0x100487f17  lea     rdx, [rbp+160h+var_150]
0x100487f1b  cmovnb  rdx, [rbp+160h+var_150]
0x100487f20  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x100487f28  movdqu  [rbp+160h+var_60], xmm0
0x100487f30  xor     r14d, r14d
0x100487f33  mov     byte ptr [rbp+160h+Src], r14b
0x100487f3a  mov     r9b, [rsp+260h+var_200]
0x100487f3f  lea     rcx, [rbp+160h+Src]; Src
0x100487f46  call    ??$_Construct@PEB_S@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXQEB_S0Uforward_iterator_tag@1@@Z; std::string::_Construct<char16_t const *>(char16_t const * const,char16_t const * const,std::forward_iterator_tag)
0x100487f4b  nop
0x100487f4c  lea     r15d, [r14+1]
0x100487f50  mov     dword ptr [rsp+260h+var_1F8], r15d
0x100487f55  lea     rbx, [rbp+160h+Src]
0x100487f5c  cmp     qword ptr [rbp+160h+var_60+8], 10h
0x100487f64  cmovnb  rbx, [rbp+160h+Src]
0x100487f6c  lea     rcx, [rbp+160h+var_190]
0x100487f70  cmp     qword ptr [rbp+160h+var_180+8], rdi
0x100487f74  cmovnb  rcx, [rbp+160h+var_190]
0x100487f79  mov     rax, qword ptr [rbp+160h+var_180]
0x100487f7d  lea     r8, [rcx+rax*2]
0x100487f81  lea     rdx, [rbp+160h+var_190]
0x100487f85  cmovnb  rdx, [rbp+160h+var_190]
0x100487f8a  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x100487f92  movdqu  [rbp+160h+var_80], xmm0
0x100487f9a  mov     byte ptr [rbp+160h+var_90], r14b
0x100487fa1  mov     r9b, [rsp+260h+var_200]
0x100487fa6  lea     rcx, [rbp+160h+var_90]; Src
0x100487fad  call    ??$_Construct@PEB_S@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXQEB_S0Uforward_iterator_tag@1@@Z; std::string::_Construct<char16_t const *>(char16_t const * const,char16_t const * const,std::forward_iterator_tag)
0x100487fb2  nop
0x100487fb3  lea     rcx, [rbp+160h+var_170]
0x100487fb7  cmp     qword ptr [rbp+160h+var_160+8], rdi
0x100487fbb  cmovnb  rcx, [rbp+160h+var_170]
0x100487fc0  mov     rax, qword ptr [rbp+160h+var_160]
0x100487fc4  lea     r8, [rcx+rax*2]
0x100487fc8  lea     rdx, [rbp+160h+var_170]
0x100487fcc  cmovnb  rdx, [rbp+160h+var_170]
0x100487fd1  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x100487fd9  movdqu  [rbp+160h+var_A0], xmm0
0x100487fe1  mov     byte ptr [rbp+160h+var_B0], r14b
0x100487fe8  mov     r9b, [rsp+260h+var_200]
0x100487fed  lea     rcx, [rbp+160h+var_B0]; Src
0x100487ff4  call    ??$_Construct@PEB_S@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXQEB_S0Uforward_iterator_tag@1@@Z; std::string::_Construct<char16_t const *>(char16_t const * const,char16_t const * const,std::forward_iterator_tag)
0x100487ff9  nop
0x100487ffa  lea     rcx, [rbp+160h+var_130]
0x100487ffe  cmp     qword ptr [rbp+160h+var_120+8], rdi
0x100488002  cmovnb  rcx, [rbp+160h+var_130]
0x100488007  mov     rax, qword ptr [rbp+160h+var_120]
0x10048800b  lea     r8, [rcx+rax*2]
0x10048800f  lea     rdx, [rbp+160h+var_130]
0x100488013  cmovnb  rdx, [rbp+160h+var_130]
0x100488018  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x100488020  movdqu  [rbp+160h+var_C0], xmm0
0x100488028  mov     byte ptr [rbp+160h+var_D0], r14b
0x10048802f  mov     r9b, [rsp+260h+var_200]
0x100488034  lea     rcx, [rbp+160h+var_D0]; Src
0x10048803b  call    ??$_Construct@PEB_S@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXQEB_S0Uforward_iterator_tag@1@@Z; std::string::_Construct<char16_t const *>(char16_t const * const,char16_t const * const,std::forward_iterator_tag)
0x100488040  nop
0x100488041  lea     rcx, [rbp+160h+var_110]
0x100488045  cmp     qword ptr [rbp+160h+var_100+8], rdi
0x100488049  cmovnb  rcx, [rbp+160h+var_110]
0x10048804e  mov     rax, qword ptr [rbp+160h+var_100]
0x100488052  lea     r8, [rcx+rax*2]
0x100488056  lea     rdx, [rbp+160h+var_110]
0x10048805a  cmovnb  rdx, [rbp+160h+var_110]
0x10048805f  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x100488067  movdqu  [rbp+160h+var_E0], xmm0
0x10048806f  mov     byte ptr [rbp+160h+var_F0], r14b
0x100488073  mov     r9b, [rsp+260h+var_200]
0x100488078  lea     rcx, [rbp+160h+var_F0]; Src
0x10048807c  call    ??$_Construct@PEB_S@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXQEB_S0Uforward_iterator_tag@1@@Z; std::string::_Construct<char16_t const *>(char16_t const * const,char16_t const * const,std::forward_iterator_tag)
0x100488081  nop
0x100488082  lea     rax, [rbp+160h+var_90]
0x100488089  cmp     qword ptr [rbp+160h+var_80+8], 10h
0x100488091  cmovnb  rax, [rbp+160h+var_90]
0x100488099  lea     r10, [rbp+160h+var_B0]
0x1004880a0  cmp     qword ptr [rbp+160h+var_A0+8], 10h
0x1004880a8  cmovnb  r10, [rbp+160h+var_B0]
0x1004880b0  lea     r8, [rbp+160h+var_D0]
0x1004880b7  cmp     qword ptr [rbp+160h+var_C0+8], 10h
0x1004880bf  cmovnb  r8, [rbp+160h+var_D0]
0x1004880c7  lea     rdx, [rbp+160h+var_F0]
0x1004880cb  cmp     qword ptr [rbp+160h+var_E0+8], 10h
0x1004880d3  cmovnb  rdx, [rbp+160h+var_F0]
0x1004880d8  mov     [rsp+260h+var_208], r14
0x1004880dd  lea     rcx, [rbp+160h+var_1D0]
0x1004880e1  mov     [rsp+260h+var_210], rcx
0x1004880e6  mov     [rsp+260h+var_218], rax
0x1004880eb  mov     eax, [rbp+160h+arg_40]
0x1004880f1  mov     [rsp+260h+var_220], eax
0x1004880f5  mov     [rsp+260h+var_228], r10
0x1004880fa  mov     [rsp+260h+var_230], rbx
0x1004880ff  mov     [rsp+260h+var_238], r8
0x100488104  mov     [rsp+260h+var_240], rdx
0x100488109  mov     r9d, [rbp+160h+arg_38]
0x100488110  mov     rsi, [rsp+260h+var_1F0]
0x100488115  mov     r8, rsi
0x100488118  mov     rdx, r13
0x10048811b  mov     rcx, [rsp+260h+var_1E8]
0x100488120  call    ?GetAccessToken@AzureADAuth@aadauth@@QEBAJP6AXPEAUCEKeystoreContext@@PEBGZZPEAXHPEBD444K4AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEA_J@Z; aadauth::AzureADAuth::GetAccessToken(void (*)(CEKeystoreContext *,ushort const *,...),void *,int,char const *,char const *,char const *,char const *,ulong,char const *,std::string &,__int64 *)
0x100488125  mov     edi, eax
0x100488127  mov     ebx, 1Fh
0x10048812c  mov     rax, qword ptr [rbp+160h+var_E0+8]
0x100488133  cmp     rax, 10h
0x100488137  jb      short loc_100488174
0x100488139  inc     rax
0x10048813c  mov     rdx, [rbp+160h+var_F0]
0x100488140  mov     rcx, rdx
0x100488143  cmp     rax, 1000h
0x100488149  jb      short loc_10048816B
0x10048814b  test    bl, cl
0x10048814d  jnz     short loc_100488164
0x10048814f  mov     rdx, [rdx-8]
0x100488153  cmp     rdx, rcx
0x100488156  jnb     short loc_100488164
0x100488158  sub     rcx, rdx
0x10048815b  sub     rcx, 8
0x10048815f  cmp     rcx, rbx
0x100488162  jbe     short loc_10048816B
0x100488164  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x10048816b  mov     rcx, rdx; void *
0x10048816e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x100488173  nop
0x100488174  mov     rax, qword ptr [rbp+160h+var_C0+8]
0x10048817b  cmp     rax, 10h
0x10048817f  jb      short loc_1004881BF
0x100488181  inc     rax
0x100488184  mov     rdx, [rbp+160h+var_D0]
0x10048818b  mov     rcx, rdx
0x10048818e  cmp     rax, 1000h
0x100488194  jb      short loc_1004881B6
0x100488196  test    bl, cl
0x100488198  jnz     short loc_1004881AF
0x10048819a  mov     rdx, [rdx-8]
0x10048819e  cmp     rdx, rcx
0x1004881a1  jnb     short loc_1004881AF
0x1004881a3  sub     rcx, rdx
0x1004881a6  sub     rcx, 8
0x1004881aa  cmp     rcx, rbx
0x1004881ad  jbe     short loc_1004881B6
0x1004881af  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1004881b6  mov     rcx, rdx; void *
0x1004881b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1004881be  nop
0x1004881bf  mov     rax, qword ptr [rbp+160h+var_A0+8]
0x1004881c6  cmp     rax, 10h
0x1004881ca  jb      short loc_10048820A
0x1004881cc  inc     rax
0x1004881cf  mov     rdx, [rbp+160h+var_B0]
0x1004881d6  mov     rcx, rdx
0x1004881d9  cmp     rax, 1000h
0x1004881df  jb      short loc_100488201
0x1004881e1  test    bl, cl
0x1004881e3  jnz     short loc_1004881FA
0x1004881e5  mov     rdx, [rdx-8]
0x1004881e9  cmp     rdx, rcx
0x1004881ec  jnb     short loc_1004881FA
0x1004881ee  sub     rcx, rdx
0x1004881f1  sub     rcx, 8
0x1004881f5  cmp     rcx, rbx
0x1004881f8  jbe     short loc_100488201
0x1004881fa  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x100488201  mov     rcx, rdx; void *
0x100488204  call    ??3@YAXPEAX@Z; operator delete(void *)
0x100488209  nop
0x10048820a  mov     rax, qword ptr [rbp+160h+var_80+8]
0x100488211  cmp     rax, 10h
0x100488215  jb      short loc_100488255
0x100488217  inc     rax
0x10048821a  mov     rdx, [rbp+160h+var_90]
0x100488221  mov     rcx, rdx
0x100488224  cmp     rax, 1000h
0x10048822a  jb      short loc_10048824C
0x10048822c  test    bl, cl
0x10048822e  jnz     short loc_100488245
0x100488230  mov     rdx, [rdx-8]
0x100488234  cmp     rdx, rcx
0x100488237  jnb     short loc_100488245
0x100488239  sub     rcx, rdx
0x10048823c  sub     rcx, 8
0x100488240  cmp     rcx, rbx
0x100488243  jbe     short loc_10048824C
0x100488245  call    cs:__imp__invalid_parameter_noinfo_noreturn
  ... truncated ...
```
