# sqlencrypt::AzureKeyVault::DecryptColumnEncryptionKey(CEKeystoreContext *,void (*)(CEKeystoreContext *,ushort const *,...),ushort const *,ushort const *,uchar *,ushort,uchar * *,ushort *)

- ea: `0x10046dab0`
- end: `0x10046edde`
- name: `?DecryptColumnEncryptionKey@AzureKeyVault@sqlencrypt@@SAHPEAUCEKeystoreContext@@P6AX0PEBGZZ11PEAEGPEAPEAEPEAG@Z`
- size: `4910`
- prototype: `__int64 __usercall@<rax>(struct CEKeystoreContext *@<rcx>, void (*)(struct CEKeystoreContext *, const unsigned __int16 *, ...)@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, BYTE *pbData, unsigned __int16, unsigned __int8 **, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `26`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x10040128c`
- `0x1004245f0`
- `0x10042a440`
- `0x100430674`
- `0x1004306f0`
- `0x100431464`
- `0x1004385b0`
- `0x10046dab0`
- `0x10046ffa4`
- `0x1004700b4`
- `0x1004709a8`
- `0x100470b78`
- `0x100471184`
- `0x100471648`
- `0x1004717c4`
- `0x10047dd74`
- `0x100483318`
- `0x100483714`
- `0x1004837f0`
- `0x100486308`
- `0x100546aa8`
- `0x1005480f8`
- `0x100548170`
- `0x100548210`
- `0x1005494b8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x10046ebef`
- `KERNEL32!LocalAlloc` at `0x10046ebef`
- `KERNEL32!GetLastError` at `0x10046e471`
- `KERNEL32!GetLastError` at `0x10046e556`
- `KERNEL32!GetLastError` at `0x10046e471`
- `KERNEL32!GetLastError` at `0x10046e556`
- `ADVAPI32!CryptDestroyHash` at `0x10046e574`
- `ADVAPI32!CryptDestroyHash` at `0x10046e5a5`
- `ADVAPI32!CryptDestroyHash` at `0x10046e574`
- `ADVAPI32!CryptDestroyHash` at `0x10046e5a5`
- `ADVAPI32!CryptHashData` at `0x10046e504`
- `ADVAPI32!CryptHashData` at `0x10046e504`
- `ADVAPI32!CryptCreateHash` at `0x10046e4af`
- `ADVAPI32!CryptCreateHash` at `0x10046e4af`
- `ADVAPI32!CryptGetHashParam` at `0x10046e59b`
- `ADVAPI32!CryptGetHashParam` at `0x10046e59b`
- `VCRUNTIME140!strchr` at `0x10046dcb9`
- `VCRUNTIME140!strchr` at `0x10046dcb9`
- `api-ms-win-crt-string-l1-1-0!_strnicmp` at `0x10046dc06`
- `api-ms-win-crt-string-l1-1-0!_strnicmp` at `0x10046dc06`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10046e355`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10046ea65`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10046eabf`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10046ec4e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10046eca8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10046e355`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10046ea65`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10046eabf`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10046ec4e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10046eca8`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall sqlencrypt::AzureKeyVault::DecryptColumnEncryptionKey(
        struct CEKeystoreContext *a1,
        void (*a2)(struct CEKeystoreContext *, const unsigned __int16 *, ...),
        const unsigned __int16 *a3,
        wchar_t *a4,
        BYTE *pbData,
        unsigned __int16 a6,
        unsigned __int8 **a7,
        unsigned __int16 *a8)
{
  const unsigned __int16 *v11; // rax
  __int64 v12; // r8
  unsigned int i; // r12d
  const char *v14; // rcx
  bool v15; // cf
  __int64 v16; // rdx
  struct sqlencrypt::AzureKeyVault::ConfigData *Config; // rax
  const char *v18; // rcx
  const char *v19; // rdx
  const char *v20; // r13
  char *v21; // rax
  char *v22; // rbx
  __int64 v23; // rax
  char **v24; // rcx
  __int64 v25; // rax
  unsigned __int64 v26; // r13
  char **v27; // rax
  _BYTE *v28; // rax
  unsigned __int64 v29; // rbx
  char **v30; // rbx
  __int64 v31; // rax
  char **v32; // rcx
  char **v33; // rax
  _BYTE *v34; // rax
  unsigned __int64 v35; // rax
  char **v36; // r9
  char **v37; // r9
  _QWORD *v38; // r8
  unsigned int v39; // edx
  sqlencrypt::utils *v40; // rcx
  char *Value; // rbx
  __int64 v42; // rdx
  char *v43; // r13
  char **v44; // r9
  __int64 v45; // r9
  _QWORD *v46; // r8
  char *v47; // r8
  _QWORD *v48; // rdx
  _QWORD *v49; // r8
  sqlencrypt::utils *v50; // rcx
  char *v51; // rax
  sqlencrypt::utils *v52; // rcx
  __int64 v53; // rcx
  unsigned __int64 v54; // rax
  unsigned __int64 v55; // rbx
  sqlencrypt::utils *v56; // rdx
  unsigned __int16 *v57; // rcx
  __int64 v58; // rdx
  BYTE *v59; // rbx
  BYTE *v60; // rcx
  HCRYPTPROV WinCryptProvider; // rax
  wchar_t *v62; // r9
  __int64 v63; // r8
  DWORD LastError; // eax
  DWORD v65; // eax
  __int64 v66; // r8
  __int64 v67; // rax
  int *v68; // r9
  int v69; // ebx
  _QWORD *v70; // r15
  size_t v71; // r8
  const void *j; // rcx
  __int64 v73; // r8
  const void *v74; // rbx
  char *v75; // rax
  char *v76; // rbx
  _QWORD *v77; // r8
  unsigned __int64 v78; // r15
  __int64 v79; // rax
  void **v80; // r9
  bool v81; // bl
  char **v82; // r9
  void *v83; // rdx
  void *v84; // rdx
  __int64 v85; // rdx
  sqlencrypt::utils *v86; // rcx
  char *v87; // rax
  char *v88; // rdi
  __int64 v89; // rdx
  __int64 v90; // rax
  SIZE_T v91; // rbx
  sqlencrypt::utils *v92; // rax
  sqlencrypt::utils *v93; // rdx
  void *v94; // rdx
  _QWORD *v95; // r8
  HCRYPTHASH *phHash; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v98; // [rsp+28h] [rbp-D8h]
  wchar_t *v99; // [rsp+30h] [rbp-D0h]
  BYTE *v100; // [rsp+38h] [rbp-C8h]
  int v101; // [rsp+40h] [rbp-C0h]
  unsigned __int8 **v102; // [rsp+48h] [rbp-B8h]
  int v103; // [rsp+50h] [rbp-B0h]
  char **v104; // [rsp+68h] [rbp-98h]
  unsigned int v105; // [rsp+68h] [rbp-98h]
  char **v106; // [rsp+68h] [rbp-98h]
  BYTE *v107; // [rsp+68h] [rbp-98h]
  DWORD pdwDataLen; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v109; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v110; // [rsp+80h] [rbp-80h]
  HCRYPTHASH hHash; // [rsp+88h] [rbp-78h] BYREF
  int v112[4]; // [rsp+90h] [rbp-70h] BYREF
  BYTE *v113; // [rsp+A0h] [rbp-60h]
  char v114[8]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 **v115; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v116; // [rsp+B8h] [rbp-48h]
  __int64 v117; // [rsp+C0h] [rbp-40h]
  char *String1[2]; // [rsp+C8h] [rbp-38h] BYREF
  size_t MaxCount; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v120; // [rsp+E0h] [rbp-20h]
  _QWORD v121[3]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v122; // [rsp+100h] [rbp+0h]
  sqlencrypt::utils *v123[2]; // [rsp+108h] [rbp+8h] BYREF
  __m128i si128; // [rsp+118h] [rbp+18h]
  _QWORD v125[2]; // [rsp+128h] [rbp+28h] BYREF
  __m128i v126; // [rsp+138h] [rbp+38h]
  void *v127[2]; // [rsp+148h] [rbp+48h] BYREF
  __m128i v128; // [rsp+158h] [rbp+58h]
  sqlencrypt::utils *v129[2]; // [rsp+168h] [rbp+68h] BYREF
  __m128i v130; // [rsp+178h] [rbp+78h]
  void *v131[2]; // [rsp+188h] [rbp+88h] BYREF
  __m128i v132; // [rsp+198h] [rbp+98h]
  _BYTE Src[16]; // [rsp+1A8h] [rbp+A8h] BYREF
  __m128i v134; // [rsp+1B8h] [rbp+B8h]
  _QWORD v135[3]; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned __int64 v136; // [rsp+1E0h] [rbp+E0h]
  _QWORD v137[2]; // [rsp+1E8h] [rbp+E8h] BYREF
  __m128i v138; // [rsp+1F8h] [rbp+F8h]
  int v139[4]; // [rsp+208h] [rbp+108h] BYREF
  __int128 v140; // [rsp+218h] [rbp+118h]
  void *v141[2]; // [rsp+228h] [rbp+128h] BYREF
  __m128i v142; // [rsp+238h] [rbp+138h]
  _BYTE v143[16]; // [rsp+248h] [rbp+148h] BYREF
  __int128 v144; // [rsp+258h] [rbp+158h]
  _BYTE v145[32]; // [rsp+268h] [rbp+168h] BYREF
  _BYTE v146[32]; // [rsp+288h] [rbp+188h] BYREF
  BYTE v147[32]; // [rsp+2A8h] [rbp+1A8h] BYREF
  BYTE v148[32]; // [rsp+2C8h] [rbp+1C8h] BYREF

  v117 = -2;
  v109 = a4;
  v115 = a7;
  v116 = a8;
  if ( (bidGblFlags & 2) != 0 && off_1005E6C88[0] )
  {
    v103 = *a8;
    v102 = a7;
    v101 = a6;
    v100 = pbData;
    v99 = a4;
    v98 = a3;
    bidTraceW(0, 247808, off_1005E6C88[0], a1);
  }
  v121[2] = 0;
  v122 = 7;
  LOWORD(v121[0]) = 0;
  v11 = a3;
  v12 = 0;
  for ( i = 1; *v11; ++v11 )
    ++v12;
  std::basic_string<char16_t>::assign(v121, a3, v12);
  MaxCount = 0;
  v120 = 15;
  LOBYTE(String1[0]) = 0;
  std::string::_Construct<char16_t const *>(String1);
  v14 = (const char *)String1;
  if ( v120 >= 0x10 )
    v14 = String1[0];
  if ( _strnicmp(v14, "https://", 8u) )
  {
    if ( (bidGblFlags & 2) != 0 && off_1005E6C90[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, const unsigned __int16 *, wchar_t *, BYTE *, int, unsigned __int8 **, int))off_1005D39E0[0])(
        bidID,
        0,
        264192,
        off_1005E6C90[0],
        0,
        v98,
        v99,
        v100,
        v101,
        v102,
        v103);
    v15 = v122 < 8;
    v16 = 41341;
LABEL_245:
    v95 = v121;
    if ( !v15 )
      v95 = (_QWORD *)v121[0];
    a2(a1, (const unsigned __int16 *)v16, v95);
LABEL_248:
    i = 0;
    goto LABEL_249;
  }
  Config = sqlencrypt::AzureKeyVault::GetConfig(a1);
  v110 = (wchar_t *)Config;
  if ( !*((_QWORD *)Config + 14) )
    goto LABEL_40;
  v18 = (char *)Config + 96;
  v19 = (char *)Config + 96;
  if ( *((_QWORD *)Config + 15) >= 0x10u )
    v19 = *(const char **)v18;
  if ( *v19 == 59 )
  {
LABEL_40:
    v105 = 0;
    v30 = off_1005CFC60;
    do
    {
      v31 = -1;
      do
        ++v31;
      while ( (*v30)[v31] );
      v32 = String1;
      if ( v120 >= 0x10 )
        v32 = (char **)String1[0];
      v26 = std::_Traits_find<std::char_traits<char>>(v32, MaxCount, 0);
      if ( v26 != -1 )
        break;
      ++v105;
      ++v30;
    }
    while ( v105 < 8 );
  }
  else
  {
    if ( *((_QWORD *)Config + 15) >= 0x10u )
      v18 = *(const char **)v18;
    v20 = v18 + 1;
    if ( *v18 != 59 )
      v20 = v18;
    while ( 1 )
    {
      v21 = strchr(v20, 59);
      v22 = v21;
      if ( v21 )
        *v21 = 0;
      v23 = -1;
      do
        ++v23;
      while ( v20[v23] );
      v24 = String1;
      if ( v120 >= 0x10 )
        v24 = (char **)String1[0];
      v25 = std::_Traits_find<std::char_traits<char>>(v24, MaxCount, 0);
      v26 = v25;
      if ( v22 )
        *v22 = 59;
      if ( v25 != -1 )
        break;
      if ( v22 )
        ++v22;
      v20 = v22;
      if ( !v22 )
      {
        v26 = v25;
        break;
      }
    }
  }
  v27 = String1;
  if ( v120 >= 0x10 )
    v27 = (char **)String1[0];
  v104 = v27;
  if ( MaxCount && (v28 = memchr_0(v27, 64, MaxCount)) != 0 )
    v29 = v28 - (_BYTE *)v104;
  else
    v29 = -1;
  if ( v26 == -1 )
    goto LABEL_242;
  v33 = String1;
  if ( v120 >= 0x10 )
    v33 = (char **)String1[0];
  v106 = v33;
  if ( MaxCount > 8 && (v34 = memchr_0(v33 + 1, 47, MaxCount - 8)) != 0 )
    v35 = v34 - (_BYTE *)v106;
  else
    v35 = -1;
  if ( v35 < v26 || v29 != -1 && v26 < v29 )
  {
LABEL_242:
    if ( (bidGblFlags & 2) != 0 && off_1005E6C98[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, const unsigned __int16 *, wchar_t *, BYTE *, int, unsigned __int8 **, int))off_1005D39E0[0])(
        bidID,
        0,
        316416,
        off_1005E6C98[0],
        0,
        v98,
        v99,
        v100,
        v101,
        v102,
        v103);
    v15 = v122 < 8;
    v16 = 41342;
    goto LABEL_245;
  }
  if ( wcscmp_0(v109, L"RSA_OAEP") && wcscmp_0(v109, L"RSA-OAEP") )
  {
    if ( (bidGblFlags & 2) != 0 && off_1005E6CA0[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, const unsigned __int16 *, wchar_t *, BYTE *, int, unsigned __int8 **, int))off_1005D39E0[0])(
        bidID,
        0,
        324608,
        off_1005E6CA0[0],
        0,
        v98,
        v99,
        v100,
        v101,
        v102,
        v103);
    a2(a1, (const unsigned __int16 *)41313, v109, L"RSA_OAEP");
    goto LABEL_248;
  }
  if ( a6 < 5u )
  {
    _mm_lfence();
    if ( (bidGblFlags & 2) != 0 && off_1005E6CA8[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, const unsigned __int16 *, wchar_t *, BYTE *, int, unsigned __int8 **, int))off_1005D39E0[0])(
        bidID,
        0,
        333824,
        off_1005E6CA8[0],
        0,
        v98,
        v99,
        v100,
        v101,
        v102,
        v103);
    a2(a1, (const unsigned __int16 *)41319, a6, 5);
    goto LABEL_248;
  }
  if ( *pbData != 1 )
  {
    if ( (bidGblFlags & 2) != 0 && off_1005E6CB0[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, const unsigned __int16 *, wchar_t *, BYTE *, int, unsigned __int8 **, int))off_1005D39E0[0])(
        bidID,
        0,
        339968,
        off_1005E6CB0[0],
        0,
        v98,
        v99,
        v100,
        v101,
        v102,
        v103);
    a2(a1, (const unsigned __int16 *)41317, *pbData, 1);
    goto LABEL_248;
  }
  aadauth::AzureADAuth::AzureADAuth(
    (aadauth::AzureADAuth *)v112,
    *((_DWORD *)v110 + 34),
    *((_DWORD *)v110 + 35),
    *((_DWORD *)v110 + 36));
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v123[0]) = 0;
  v36 = String1;
  if ( v120 >= 0x10 )
    LODWORD(v36) = String1[0];
  if ( (unsigned int)sqlencrypt::AzureKeyVault::AKVRequest((int)v112, (int)a1, (int)a2, (int)v36, v123, 0, 0) != 200 )
  {
    if ( (bidGblFlags & 2) != 0 && off_1005E6CB8[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
        bidID,
        0,
        354304,
        off_1005E6CB8[0],
        0);
    v38 = v121;
    if ( v122 >= 8 )
      v38 = (_QWORD *)v121[0];
    a2(a1, (const unsigned __int16 *)41343, v38);
    goto LABEL_118;
  }
  v40 = (sqlencrypt::utils *)v123;
  if ( si128.m128i_i64[1] >= 0x10uLL )
    v40 = v123[0];
  Value = sqlencrypt::utils::ExtractValue(v40, "\"kty\":\"", (char *)&v109, v37);
  if ( !Value )
  {
    if ( (bidGblFlags & 2) != 0 && off_1005E6CC0[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
        bidID,
        0,
        360448,
        off_1005E6CC0[0],
        0);
    v42 = 41344;
LABEL_117:
    a2(a1, (const unsigned __int16 *)v42);
    goto LABEL_118;
  }
  v110 = v109;
  v43 = (char *)((char *)v109 - Value);
  if ( !memcmp_0(Value, "RSA", (char *)v109 - Value) || !memcmp_0(Value, "RSA-HSM", (size_t)v43) )
  {
    v50 = (sqlencrypt::utils *)v123;
    if ( si128.m128i_i64[1] >= 0x10uLL )
      v50 = v123[0];
    v51 = sqlencrypt::utils::ExtractValue(v50, "\"n\":\"", (char *)&v109, v44);
    if ( !v51 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E6CD0[0] && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
          bidID,
          0,
          375808,
          off_1005E6CD0[0],
          0);
      v42 = 41346;
      goto LABEL_117;
    }
    v53 = ((_BYTE)v109 - (_BYTE)v51) & 3;
    v54 = 3 * ((unsigned __int64)((char *)v109 - v51) >> 2);
    v55 = v54 + v53 - 1;
    if ( !v53 )
      v55 = v54;
    if ( si128.m128i_i64[1] >= 0x10uLL )
    {
      v56 = v123[0];
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        if ( ((__int64)v123[0] & 0x1F) != 0 )
          goto LABEL_131;
        v56 = (sqlencrypt::utils *)*((_QWORD *)v123[0] - 1);
        if ( v56 >= v123[0] || (unsigned __int64)(v123[0] - v56 - 8) > 0x1F )
          goto LABEL_131;
      }
      operator delete(v56);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v123[0]) = 0;
    v57 = (unsigned __int16 *)(pbData + 3);
    v107 = pbData + 3;
    v58 = *(unsigned __int16 *)(pbData + 3);
    if ( v55 != v58 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E6CD8[0] && bidID != -1 )
      {
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
          bidID,
          0,
          386048,
          off_1005E6CD8[0],
          0);
        v57 = (unsigned __int16 *)(pbData + 3);
      }
      a2(a1, (const unsigned __int16 *)41319, *v57, v55);
      goto LABEL_238;
    }
    v59 = &pbData[*(unsigned __int16 *)(pbData + 1) + 5];
    v113 = v59;
    v60 = &pbData[a6];
    if ( v59 >= v60 || &v59[v58] > v60 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E6CE0[0] && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
          bidID,
          0,
          393216,
          off_1005E6CE0[0],
          0);
      a2(a1, (const unsigned __int16 *)41347);
      goto LABEL_238;
    }
    WinCryptProvider = sqlencrypt::SqlSecurityUtility::GetWinCryptProvider();
    if ( !WinCryptProvider )
    {
      if ( (bidGblFlags & 2) == 0 || !off_1005E6CE8[0] || bidID == -1 )
        goto LABEL_147;
      v62 = off_1005E6CE8[0];
      v63 = 409600;
LABEL_146:
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(bidID, 0, v63, v62, 0);
LABEL_147:
      LastError = GetLastError();
      a2(a1, (const unsigned __int16 *)41328, LastError);
      goto LABEL_238;
    }
    pdwDataLen = 32;
    if ( !CryptCreateHash(WinCryptProvider, 0x800Cu, 0, 0, &hHash) )
    {
      if ( (bidGblFlags & 2) == 0 || !off_1005E6CF0[0] || bidID == -1 )
        goto LABEL_147;
      v62 = off_1005E6CF0[0];
      v63 = 417792;
      goto LABEL_146;
    }
    if ( !CryptHashData(hHash, pbData, (_DWORD)v59 + *(unsigned __int16 *)v107 - (_DWORD)pbData, 0) )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E6CF8[0] && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
          bidID,
          0,
          423936,
          off_1005E6CF8[0],
          0);
      v65 = GetLastError();
      a2(a1, (const unsigned __int16 *)41328, v65);
      CryptDestroyHash(hHash);
      goto LABEL_238;
    }
    _mm_lfence();
    CryptGetHashParam(hHash, 2u, v148, &pdwDataLen, 0);
    CryptDestroyHash(hHash);
    v134 = _mm_load_si128((const __m128i *)&_xmm);
    Src[0] = 0;
    _mm_lfence();
    LOBYTE(v66) = Src[0];
    std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(
      Src,
      25,
      v66,
      "{\"alg\":\"RS256\",\"digest\":\"");
    sqlencrypt::utils::Base64URLencode(v145, v148, 32);
    std::string::append(Src);
    std::string::_Tidy_deallocate(v145);
    std::string::append(Src);
    sqlencrypt::utils::Base64URLencode(
      v146,
      &v59[*(unsigned __int16 *)v107],
      pbData - v59 - *(unsigned __int16 *)v107 + a6);
    std::string::append(Src);
    std::string::_Tidy_deallocate(v146);
    std::string::append(Src);
    v138 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v137[0]) = 0;
    v144 = 0;
    std::string::_Construct_lv_contents(v143, String1);
    v67 = std::string::append(v143);
    v140 = 0;
    *(_OWORD *)v139 = *(_OWORD *)v67;
    v140 = *(_OWORD *)(v67 + 16);
    *(_QWORD *)(v67 + 16) = 0;
    *(_QWORD *)(v67 + 24) = 15;
    *(_BYTE *)v67 = 0;
    v68 = v139;
    if ( *((_QWORD *)&v140 + 1) >= 0x10u )
      LODWORD(v68) = v139[0];
    v69 = sqlencrypt::AzureKeyVault::AKVRequest((int)v112, (int)a1, (int)a2, (int)v68, v137, (__int64)Src, 0);
    std::string::_Tidy_deallocate(v139);
    std::string::_Tidy_deallocate(v143);
    if ( v69 != 200 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E6D00[0] && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
          bidID,
          0,
          442368,
          off_1005E6D00[0],
          0);
      a2(a1, (const unsigned __int16 *)41348);
      goto LABEL_181;
    }
    v70 = v137;
    if ( v138.m128i_i64[1] >= 0x10uLL )
      v70 = (_QWORD *)v137[0];
    if ( v138.m128i_i64[0] < 0xCuLL )
    {
LABEL_174:
      if ( (bidGblFlags & 2) != 0 && off_1005E6D08[0] && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
          bidID,
          0,
          448512,
          off_1005E6D08[0],
          0);
      v77 = v121;
      if ( v122 >= 8 )
        v77 = (_QWORD *)v121[0];
      a2(a1, (const unsigned __int16 *)41318, v77);
LABEL_181:
      i = 0;
LABEL_182:
      std::string::_Tidy_deallocate(v137);
      std::string::_Tidy_deallocate(Src);
      goto LABEL_239;
    }
    v110 = (wchar_t *)((char *)v70 + v138.m128i_i64[0] - 11);
    v71 = v138.m128i_i64[0] - 11;
    for ( j = v70; ; j = v74 )
    {
      v75 = (char *)memchr_0(j, 34, v71);
      v76 = v75;
      if ( !v75 )
        goto LABEL_174;
      if ( !memcmp_0(v75, "\"value\":true", 0xCu) )
        break;
      v74 = v76 + 1;
      v71 = (char *)v110 - (_BYTE *)v74;
    }
    if ( v76 - (char *)v70 == -1 )
      goto LABEL_174;
    v132 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v78) = 0;
    LOBYTE(v131[0]) = 0;
    _mm_lfence();
    LOBYTE(v73) = v131[0];
    std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(
      v131,
      27,
      v73,
      "{\"alg\":\"RSA-OAEP\",\"value\":\"");
    sqlencrypt::utils::Base64URLencode(v147, v113, *(unsigned __int16 *)v107);
    std::string::append(v131);
    std::string::_Tidy_deallocate(v147);
    std::string::append(v131);
    v130 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v129[0]) = 0;
    v142 = 0;
    std::string::_Construct_lv_contents(v141, String1);
    v79 = std::string::append(v141);
    v128 = 0;
    *(_OWORD *)v127 = *(_OWORD *)v79;
    v128 = *(__m128i *)(v79 + 16);
    *(_QWORD *)(v79 + 16) = 0;
    *(_QWORD *)(v79 + 24) = 15;
    *(_BYTE *)v79 = 0;
    v80 = v127;
    if ( v128.m128i_i64[1] >= 0x10uLL )
      LODWORD(v80) = v127[0];
    v81 = (unsigned int)sqlencrypt::AzureKeyVault::AKVRequest(
                          (int)v112,
                          (int)a1,
                          (int)a2,
                          (int)v80,
                          v129,
                          (__int64)v131,
                          0) != 200;
    if ( v128.m128i_i64[1] >= 0x10uLL )
    {
      v83 = v127[0];
      if ( (unsigned __int64)(v128.m128i_i64[1] + 1) >= 0x1000 )
      {
        if ( ((__int64)v127[0] & 0x1F) != 0
          || (v83 = (void *)*((_QWORD *)v127[0] - 1), v83 >= v127[0])
          || (unsigned __int64)((char *)v127[0] - (char *)v83 - 8) > 0x1F )
        {
          _invalid_parameter_noinfo_noreturn();
        }
      }
      operator delete(v83);
    }
    v128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v127[0]) = 0;
    if ( v142.m128i_i64[1] >= 0x10uLL )
    {
      v84 = v141[0];
      if ( (unsigned __int64)(v142.m128i_i64[1] + 1) >= 0x1000 )
      {
        if ( ((__int64)v141[0] & 0x1F) != 0
          || (v84 = (void *)*((_QWORD *)v141[0] - 1), v84 >= v141[0])
          || (unsigned __int64)((char *)v141[0] - (char *)v84 - 8) > 0x1F )
        {
          _invalid_parameter_noinfo_noreturn();
        }
      }
      operator delete(v84);
    }
    v142 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v141[0]) = 0;
    if ( v81 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E6D10[0] && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
          bidID,
          0,
          460800,
          off_1005E6D10[0],
          0);
      v85 = 41349;
    }
    else
    {
      v86 = (sqlencrypt::utils *)v129;
      if ( v130.m128i_i64[1] >= 0x10uLL )
        v86 = v129[0];
      v87 = sqlencrypt::utils::ExtractValue(v86, "\"value\":\"", v114, v82);
      v78 = (unsigned __int64)v87;
      if ( v87 )
      {
        v88 = (char *)(*(_QWORD *)v114 - (_QWORD)v87);
        v89 = (v114[0] - (_BYTE)v87) & 3;
        v90 = (*(_QWORD *)v114 - (_QWORD)v87) >> 2;
        v91 = 3 * v90 + v89 - 1;
        if ( ((v114[0] - (_BYTE)v78) & 3) == 0 )
          v91 = 3 * v90;
        **(_BYTE **)v114 = 0;
        v92 = (sqlencrypt::utils *)LocalAlloc(0, v91);
        *v115 = (unsigned __int8 *)v92;
        sqlencrypt::utils::Base64URLdecode(v92, (unsigned __int8 *)v91, v78, v88, (unsigned __int64)phHash);
        *v116 = v91;
        LOBYTE(v78) = 0;
        goto LABEL_218;
      }
      if ( (bidGblFlags & 2) != 0 && off_1005E6D18[0] && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
          bidID,
          0,
          472064,
          off_1005E6D18[0],
          0);
      v85 = 41350;
    }
    a2(a1, (const unsigned __int16 *)v85);
    i = 0;
LABEL_218:
    if ( v130.m128i_i64[1] >= 0x10uLL )
    {
      v93 = v129[0];
      if ( (unsigned __int64)(v130.m128i_i64[1] + 1) >= 0x1000 )
      {
        if ( ((__int64)v129[0] & 0x1F) != 0
          || (v93 = (sqlencrypt::utils *)*((_QWORD *)v129[0] - 1), v93 >= v129[0])
          || (unsigned __int64)(v129[0] - v93 - 8) > 0x1F )
        {
          _invalid_parameter_noinfo_noreturn();
        }
      }
      operator delete(v93);
    }
    v130 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v129[0]) = v78;
    if ( v132.m128i_i64[1] >= 0x10uLL )
    {
      v94 = v131[0];
      if ( (unsigned __int64)(v132.m128i_i64[1] + 1) >= 0x1000 )
      {
        if ( ((__int64)v131[0] & 0x1F) != 0
          || (v94 = (void *)*((_QWORD *)v131[0] - 1), v94 >= v131[0])
          || (unsigned __int64)((char *)v131[0] - (char *)v94 - 8) > 0x1F )
        {
          _invalid_parameter_noinfo_noreturn();
        }
      }
      operator delete(v94);
    }
    v132 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v131[0]) = v78;
    goto LABEL_182;
  }
  *(_BYTE *)v110 = 0;
  v126 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v125[0]) = 0;
  std::string::assign(v125);
  v46 = v125;
  if ( v126.m128i_i64[1] >= 0x10uLL )
    v46 = (_QWORD *)v125[0];
  v47 = (char *)v46 + v126.m128i_i64[0];
  v48 = v125;
  if ( v126.m128i_i64[1] >= 0x10uLL )
    v48 = (_QWORD *)v125[0];
  v135[2] = 0;
  v136 = 7;
  LOWORD(v135[0]) = 0;
  LOBYTE(v45) = a6;
  std::basic_string<char16_t>::_Construct<char *>(v135, v48, v47, v45);
  if ( (bidGblFlags & 2) != 0 && off_1005E6CC8[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
      bidID,
      0,
      369664,
      off_1005E6CC8[0],
      0);
  v49 = v135;
  if ( v136 >= 8 )
    v49 = (_QWORD *)v135[0];
  a2(a1, (const unsigned __int16 *)41345, v49);
  std::basic_string<char16_t>::_Tidy_deallocate(v135);
  std::string::_Tidy_deallocate(v125);
LABEL_118:
  if ( si128.m128i_i64[1] >= 0x10uLL )
  {
    v52 = v123[0];
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) < 0x1000
      || ((__int64)v123[0] & 0x1F) == 0
      && (v52 = (sqlencrypt::utils *)*((_QWORD *)v123[0] - 1), v52 < v123[0])
      && (unsigned __int64)(v123[0] - v52 - 8) <= 0x1F )
    {
      operator delete(v52);
      goto LABEL_238;
    }
LABEL_131:
    _invalid_parameter_noinfo_noreturn();
  }
LABEL_238:
  i = 0;
LABEL_239:
  SNI_IOCPIOQueue::Poll((SNI_IOCPIOQueue *)v112, v39);
LABEL_249:
  std::string::_Tidy_deallocate(String1);
  std::basic_string<char16_t>::_Tidy_deallocate(v121);
  return i;
}

```

## disassembly

```asm
0x10046dab0  push    rbp
0x10046dab2  push    rbx
0x10046dab3  push    rsi
0x10046dab4  push    rdi
0x10046dab5  push    r12
0x10046dab7  push    r13
0x10046dab9  push    r14
0x10046dabb  push    r15
0x10046dabd  lea     rbp, [rsp-1F8h]
0x10046dac5  sub     rsp, 2F8h
0x10046dacc  mov     [rbp+230h+var_270], 0FFFFFFFFFFFFFFFEh
0x10046dad4  mov     rax, cs:__security_cookie
0x10046dadb  xor     rax, rsp
0x10046dade  mov     [rbp+230h+var_48], rax
0x10046dae5  mov     [rsp+330h+var_2B8], r9
0x10046daea  mov     rbx, r8
0x10046daed  mov     r14, rdx
0x10046daf0  mov     rsi, rcx
0x10046daf3  mov     r15, [rbp+230h+pbData]
0x10046dafa  movzx   ecx, [rbp+230h+arg_28]
0x10046db01  mov     [rsp+330h+var_2D0], cx
0x10046db06  mov     rdx, [rbp+230h+arg_30]
0x10046db0d  mov     [rbp+230h+var_280], rdx
0x10046db11  mov     r8, [rbp+230h+arg_38]
0x10046db18  mov     [rbp+230h+var_278], r8
0x10046db1c  xor     r13d, r13d
0x10046db1f  test    byte ptr cs:_bidGblFlags, 2
0x10046db26  jz      short loc_10046DB6F
0x10046db28  mov     rax, cs:off_1005E6C88; "<sqlencrypt::AzureKeyVault::DecryptColu"...
0x10046db2f  test    rax, rax
0x10046db32  jz      short loc_10046DB6F
0x10046db34  movzx   eax, word ptr [r8]
0x10046db38  mov     [rsp+330h+var_2E0], eax
0x10046db3c  mov     [rsp+330h+var_2E8], rdx
0x10046db41  mov     [rsp+330h+var_2F0], ecx
0x10046db45  mov     [rsp+330h+var_2F8], r15
0x10046db4a  mov     qword ptr [rsp+330h+var_300], r9
0x10046db4f  mov     [rsp+330h+var_308], rbx
0x10046db54  mov     [rsp+330h+phHash], r14
0x10046db59  mov     r9, rsi
0x10046db5c  mov     r8, cs:off_1005E6C88; "<sqlencrypt::AzureKeyVault::DecryptColu"...
0x10046db63  mov     edx, 3C800h
0x10046db68  xor     ecx, ecx
0x10046db6a  call    _bidTraceW
0x10046db6f  mov     [rbp+230h+var_238], r13
0x10046db73  mov     [rbp+230h+var_230], 7
0x10046db7b  mov     word ptr [rbp+230h+var_248], r13w
0x10046db80  mov     rax, rbx
0x10046db83  mov     r8, r13
0x10046db86  mov     r12d, 1
0x10046db8c  cmp     [rbx], r13w
0x10046db90  jz      short loc_10046DB9F
0x10046db92  add     r8, r12
0x10046db95  lea     rax, [rax+2]
0x10046db99  cmp     [rax], r13w
0x10046db9d  jnz     short loc_10046DB92
0x10046db9f  mov     rdx, rbx
0x10046dba2  lea     rcx, [rbp+230h+var_248]
0x10046dba6  call    ?assign@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAAEAV12@QEB_S_K@Z; std::basic_string<char16_t>::assign(char16_t const * const,unsigned __int64)
0x10046dbab  nop
0x10046dbac  lea     rcx, [rbp+230h+var_248]
0x10046dbb0  mov     ebx, 8
0x10046dbb5  cmp     [rbp+230h+var_230], rbx
0x10046dbb9  cmovnb  rcx, [rbp+230h+var_248]
0x10046dbbe  mov     rax, [rbp+230h+var_238]
0x10046dbc2  lea     r8, [rcx+rax*2]
0x10046dbc6  lea     rdx, [rbp+230h+var_248]
0x10046dbca  cmovnb  rdx, [rbp+230h+var_248]
0x10046dbcf  mov     [rbp+230h+MaxCount], r13
0x10046dbd3  mov     [rbp+230h+var_250], 0Fh
0x10046dbdb  mov     byte ptr [rbp+230h+String1], r13b
0x10046dbdf  mov     r9b, byte ptr [rsp+330h+var_2D0]
0x10046dbe4  lea     rcx, [rbp+230h+String1]; Src
0x10046dbe8  call    ??$_Construct@PEB_S@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXQEB_S0Uforward_iterator_tag@1@@Z; std::string::_Construct<char16_t const *>(char16_t const * const,char16_t const * const,std::forward_iterator_tag)
0x10046dbed  nop
0x10046dbee  lea     rcx, [rbp+230h+String1]
0x10046dbf2  cmp     [rbp+230h+var_250], 10h
0x10046dbf7  cmovnb  rcx, [rbp+230h+String1]; String1
0x10046dbfc  mov     r8d, ebx; MaxCount
0x10046dbff  lea     rdx, aHttps_0; "https://"
0x10046dc06  call    cs:__imp__strnicmp
0x10046dc0c  test    eax, eax
0x10046dc0e  jz      short loc_10046DC68
0x10046dc10  test    byte ptr cs:_bidGblFlags, 2
0x10046dc17  jz      short loc_10046DC5A
0x10046dc19  mov     rax, cs:off_1005E6C90; "<sqlencrypt::AzureKeyVault::DecryptColu"...
0x10046dc20  test    rax, rax
0x10046dc23  jz      short loc_10046DC5A
0x10046dc25  or      rdi, 0FFFFFFFFFFFFFFFFh
0x10046dc29  cmp     cs:_bidID, rdi
0x10046dc30  jz      short loc_10046DC5A
0x10046dc32  mov     rax, cs:off_1005D39E0
0x10046dc39  mov     [rsp+330h+phHash], r13
0x10046dc3e  mov     r9, cs:off_1005E6C90; "<sqlencrypt::AzureKeyVault::DecryptColu"...
0x10046dc45  xor     edx, edx
0x10046dc47  mov     r8d, 40800h
0x10046dc4d  mov     rcx, cs:_bidID
0x10046dc54  call    cs:__guard_dispatch_icall_fptr
0x10046dc5a  cmp     [rbp+230h+var_230], rbx
0x10046dc5e  mov     edx, 0A17Dh
0x10046dc63  jmp     loc_10046ED8D
0x10046dc68  mov     rcx, rsi; struct CEKeystoreContext *
0x10046dc6b  call    ?GetConfig@AzureKeyVault@sqlencrypt@@CAAEAUConfigData@12@PEAUCEKeystoreContext@@@Z; sqlencrypt::AzureKeyVault::GetConfig(CEKeystoreContext *)
0x10046dc70  mov     [rbp+230h+var_2B0], rax
0x10046dc74  cmp     [rax+70h], r13
0x10046dc78  jz      loc_10046DD5F
0x10046dc7e  lea     rcx, [rax+60h]
0x10046dc82  mov     rdx, rcx
0x10046dc85  cmp     qword ptr [rcx+18h], 10h
0x10046dc8a  jb      short loc_10046DC8F
0x10046dc8c  mov     rdx, [rcx]
0x10046dc8f  cmp     byte ptr [rdx], 3Bh ; ';'
0x10046dc92  jz      loc_10046DD5F
0x10046dc98  cmp     qword ptr [rcx+18h], 10h
0x10046dc9d  jb      short loc_10046DCA2
0x10046dc9f  mov     rcx, [rcx]
0x10046dca2  lea     r13, [rcx+1]
0x10046dca6  cmp     byte ptr [rcx], 3Bh ; ';'
0x10046dca9  cmovnz  r13, rcx
0x10046dcad  or      rdi, 0FFFFFFFFFFFFFFFFh
0x10046dcb1  mov     edx, 3Bh ; ';'; Val
0x10046dcb6  mov     rcx, r13; Str
0x10046dcb9  call    cs:__imp_strchr
0x10046dcbf  mov     rbx, rax
0x10046dcc2  xor     ecx, ecx
0x10046dcc4  test    rax, rax
0x10046dcc7  jz      short loc_10046DCCB
0x10046dcc9  mov     [rax], cl
0x10046dccb  mov     rax, rdi
0x10046dcce  inc     rax
0x10046dcd1  cmp     [rax+r13], cl
0x10046dcd5  jnz     short loc_10046DCCE
0x10046dcd7  lea     rcx, [rbp+230h+String1]
0x10046dcdb  cmp     [rbp+230h+var_250], 10h
0x10046dce0  cmovnb  rcx, [rbp+230h+String1]
0x10046dce5  mov     [rsp+330h+phHash], rax
0x10046dcea  mov     r9, r13
0x10046dced  xor     r8d, r8d
0x10046dcf0  mov     rdx, [rbp+230h+MaxCount]
0x10046dcf4  call    ??$_Traits_find@U?$char_traits@D@std@@@std@@YA_KQEBD_K101@Z; std::_Traits_find<std::char_traits<char>>(char const * const,unsigned __int64,unsigned __int64,char const * const,unsigned __int64)
0x10046dcf9  mov     r13, rax
0x10046dcfc  mov     [rsp+330h+var_2C8], rax
0x10046dd01  test    rbx, rbx
0x10046dd04  jz      short loc_10046DD09
0x10046dd06  mov     byte ptr [rbx], 3Bh ; ';'
0x10046dd09  cmp     r13, rdi
0x10046dd0c  jnz     short loc_10046DD23
0x10046dd0e  test    rbx, rbx
0x10046dd11  jz      short loc_10046DD16
0x10046dd13  add     rbx, r12
0x10046dd16  mov     r13, rbx
0x10046dd19  test    rbx, rbx
0x10046dd1c  jnz     short loc_10046DCB1
0x10046dd1e  mov     r13, [rsp+330h+var_2C8]
0x10046dd23  lea     rax, [rbp+230h+String1]
0x10046dd27  cmp     [rbp+230h+var_250], 10h
0x10046dd2c  cmovnb  rax, [rbp+230h+String1]
0x10046dd31  mov     [rsp+330h+var_2C8], rax
0x10046dd36  mov     r8, [rbp+230h+MaxCount]; MaxCount
0x10046dd3a  test    r8, r8
0x10046dd3d  jz      loc_10046DDC7
0x10046dd43  mov     edx, 40h ; '@'; Val
0x10046dd48  mov     rcx, rax; Buf
0x10046dd4b  call    memchr_0
0x10046dd50  mov     rbx, rax
0x10046dd53  test    rax, rax
0x10046dd56  jz      short loc_10046DDC7
0x10046dd58  sub     rbx, [rsp+330h+var_2C8]
0x10046dd5d  jmp     short loc_10046DDCA
0x10046dd5f  mov     dword ptr [rsp+330h+var_2C8], r13d
0x10046dd64  lea     rbx, off_1005CFC60; "vault.azure.net"
0x10046dd6b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x10046dd6f  jmp     short loc_10046DD74
0x10046dd71  xor     r13d, r13d
0x10046dd74  mov     r9, [rbx]
0x10046dd77  mov     rax, rdi
0x10046dd7a  inc     rax
0x10046dd7d  cmp     [r9+rax], r13b
0x10046dd81  jnz     short loc_10046DD7A
0x10046dd83  lea     rcx, [rbp+230h+String1]
0x10046dd87  cmp     [rbp+230h+var_250], 10h
0x10046dd8c  cmovnb  rcx, [rbp+230h+String1]
0x10046dd91  mov     [rsp+330h+phHash], rax
0x10046dd96  xor     r8d, r8d
0x10046dd99  mov     rdx, [rbp+230h+MaxCount]
0x10046dd9d  call    ??$_Traits_find@U?$char_traits@D@std@@@std@@YA_KQEBD_K101@Z; std::_Traits_find<std::char_traits<char>>(char const * const,unsigned __int64,unsigned __int64,char const * const,unsigned __int64)
0x10046dda2  mov     r13, rax
0x10046dda5  cmp     rax, rdi
0x10046dda8  jnz     loc_10046DD23
0x10046ddae  mov     ecx, dword ptr [rsp+330h+var_2C8]
0x10046ddb2  add     ecx, r12d
0x10046ddb5  mov     dword ptr [rsp+330h+var_2C8], ecx
0x10046ddb9  add     rbx, 8
0x10046ddbd  cmp     ecx, 8
0x10046ddc0  jb      short loc_10046DD71
0x10046ddc2  jmp     loc_10046DD23
0x10046ddc7  mov     rbx, rdi
0x10046ddca  cmp     r13, rdi
0x10046ddcd  jz      loc_10046ED3A
0x10046ddd3  lea     rax, [rbp+230h+String1]
0x10046ddd7  cmp     [rbp+230h+var_250], 10h
0x10046dddc  cmovnb  rax, [rbp+230h+String1]
0x10046dde1  mov     [rsp+330h+var_2C8], rax
0x10046dde6  mov     rcx, [rbp+230h+MaxCount]
0x10046ddea  cmp     rcx, 8
0x10046ddee  jbe     short loc_10046DE0E
0x10046ddf0  lea     r8, [rcx-8]; MaxCount
0x10046ddf4  lea     rcx, [rax+8]; Buf
0x10046ddf8  mov     edx, 2Fh ; '/'; Val
0x10046ddfd  call    memchr_0
0x10046de02  test    rax, rax
0x10046de05  jz      short loc_10046DE0E
0x10046de07  sub     rax, [rsp+330h+var_2C8]
0x10046de0c  jmp     short loc_10046DE11
0x10046de0e  mov     rax, rdi
0x10046de11  cmp     rax, r13
0x10046de14  jb      loc_10046ED3A
0x10046de1a  cmp     rbx, rdi
0x10046de1d  jz      short loc_10046DE28
0x10046de1f  cmp     r13, rbx
0x10046de22  jb      loc_10046ED3A
0x10046de28  lea     rdx, aRsaOaep_0; "RSA_OAEP"
0x10046de2f  mov     rbx, [rsp+330h+var_2B8]
0x10046de34  mov     rcx, rbx; String1
0x10046de37  call    wcscmp_0
0x10046de3c  xor     r13d, r13d
0x10046de3f  test    eax, eax
0x10046de41  jz      short loc_10046DEBC
0x10046de43  lea     rdx, aRsaOaep; "RSA-OAEP"
0x10046de4a  mov     rcx, rbx; String1
0x10046de4d  call    wcscmp_0
0x10046de52  test    eax, eax
0x10046de54  jz      short loc_10046DEBC
0x10046de56  test    byte ptr cs:_bidGblFlags, 2
0x10046de5d  jz      short loc_10046DE9C
0x10046de5f  mov     rax, cs:off_1005E6CA0; "<sqlencrypt::AzureKeyVault::DecryptColu"...
0x10046de66  test    rax, rax
0x10046de69  jz      short loc_10046DE9C
0x10046de6b  cmp     cs:_bidID, rdi
0x10046de72  jz      short loc_10046DE9C
0x10046de74  mov     rax, cs:off_1005D39E0
0x10046de7b  mov     [rsp+330h+phHash], r13
0x10046de80  mov     r9, cs:off_1005E6CA0; "<sqlencrypt::AzureKeyVault::DecryptColu"...
0x10046de87  xor     edx, edx
0x10046de89  mov     r8d, 4F400h
0x10046de8f  mov     rcx, cs:_bidID
0x10046de96  call    cs:__guard_dispatch_icall_fptr
0x10046de9c  lea     r9, aRsaOaep_0; "RSA_OAEP"
0x10046dea3  mov     r8, rbx
0x10046dea6  mov     edx, 0A161h
0x10046deab  mov     rcx, rsi
0x10046deae  mov     rax, r14
0x10046deb1  call    cs:__guard_dispatch_icall_fptr
0x10046deb7  jmp     loc_10046EDA2
0x10046debc  mov     ecx, 5
0x10046dec1  movzx   ebx, [rsp+330h+var_2D0]
0x10046dec6  cmp     bx, cx
0x10046dec9  jnb     short loc_10046DF35
0x10046decb  lfence
0x10046dece  test    byte ptr cs:_bidGblFlags, 2
0x10046ded5  jz      short loc_10046DF19
0x10046ded7  mov     rax, cs:off_1005E6CA8; "<sqlencrypt::AzureKeyVault::DecryptColu"...
0x10046dede  test    rax, rax
0x10046dee1  jz      short loc_10046DF19
0x10046dee3  cmp     cs:_bidID, rdi
0x10046deea  jz      short loc_10046DF19
0x10046deec  mov     rax, cs:off_1005D39E0
0x10046def3  mov     [rsp+330h+phHash], r13
0x10046def8  mov     r9, cs:off_1005E6CA8; "<sqlencrypt::AzureKeyVault::DecryptColu"...
0x10046deff  xor     edx, edx
0x10046df01  mov     r8d, 51800h
0x10046df07  mov     rcx, cs:_bidID
0x10046df0e  call    cs:__guard_dispatch_icall_fptr
0x10046df14  mov     ecx, 5
0x10046df19  mov     r8d, ebx
0x10046df1c  mov     r9, rcx
0x10046df1f  mov     edx, 0A167h
0x10046df24  mov     rcx, rsi
0x10046df27  mov     rax, r14
0x10046df2a  call    cs:__guard_dispatch_icall_fptr
0x10046df30  jmp     loc_10046EDA2
0x10046df35  cmp     [r15], r12b
0x10046df38  jz      short loc_10046DF9D
0x10046df3a  test    byte ptr cs:_bidGblFlags, 2
0x10046df41  jz      short loc_10046DF80
0x10046df43  mov     rax, cs:off_1005E6CB0; "<sqlencrypt::AzureKeyVault::DecryptColu"...
0x10046df4a  test    rax, rax
0x10046df4d  jz      short loc_10046DF80
0x10046df4f  cmp     cs:_bidID, rdi
0x10046df56  jz      short loc_10046DF80
0x10046df58  mov     rax, cs:off_1005D39E0
0x10046df5f  mov     [rsp+330h+phHash], r13
0x10046df64  mov     r9, cs:off_1005E6CB0; "<sqlencrypt::AzureKeyVault::DecryptColu"...
0x10046df6b  xor     edx, edx
0x10046df6d  mov     r8d, 53000h
0x10046df73  mov     rcx, cs:_bidID
0x10046df7a  call    cs:__guard_dispatch_icall_fptr
0x10046df80  movzx   r8d, byte ptr [r15]
0x10046df84  mov     r9d, r12d
0x10046df87  mov     edx, 0A165h
  ... truncated ...
```
