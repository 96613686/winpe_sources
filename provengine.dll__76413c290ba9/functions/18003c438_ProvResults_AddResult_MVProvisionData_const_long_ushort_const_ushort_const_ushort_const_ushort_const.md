# ProvResults::AddResult(_MVProvisionData const &,long,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18003c438`
- end: `0x18003cc91`
- name: `?AddResult@ProvResults@@QEBA_KAEBU_MVProvisionData@@JPEBG111@Z`
- size: `2137`
- prototype: `__int64 __fastcall(HKEY *this, const struct _MVProvisionData *, int, const unsigned __int16 *, BYTE *lpData, const BYTE *lpValueName, BYTE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x180018f74`

## callees

- `0x180002e70`
- `0x180021cf4`
- `0x180021d14`
- `0x18002f9bc`
- `0x18003c438`
- `0x18003cc98`
- `0x18003ce00`
- `0x18003d0dc`
- `0x18003d534`
- `0x18004371a`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003ca08`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003ca57`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003ca08`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003ca57`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003ca34`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003ca34`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003c825`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003c825`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c5f9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c688`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c721`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c7c2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c892`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c8c5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c9b8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c9ef`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003caa9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c5f9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c688`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c721`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c7c2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c892`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c8c5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c9b8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c9ef`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003caa9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ca27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ca45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ca27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ca45`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c4dc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c919`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c4dc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c919`

## string_xrefs

- `0x18003c715`: `FailingNodePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ProvResults::AddResult(
        HKEY *this,
        const struct _MVProvisionData *a2,
        int a3,
        const unsigned __int16 *a4,
        BYTE *lpData,
        const BYTE *lpValueName,
        BYTE *a7)
{
  const WCHAR *v9; // rdx
  unsigned int v10; // eax
  __int64 v11; // rax
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // rbx
  BYTE *v14; // rax
  const char *v15; // r9
  BYTE *v16; // r14
  unsigned __int64 v17; // rcx
  __int64 v18; // rax
  unsigned __int16 v19; // ax
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rax
  __int64 v22; // r9
  unsigned int v23; // eax
  __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // rax
  __int64 v27; // r9
  unsigned int v28; // eax
  __int64 v29; // rcx
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rax
  __int64 v32; // r9
  unsigned int v33; // eax
  __int64 v34; // rcx
  unsigned __int64 v35; // rcx
  unsigned __int64 v36; // rax
  __int64 v37; // r9
  unsigned int v38; // eax
  unsigned int ValueW; // eax
  void *v40; // rdx
  unsigned int v41; // r8d
  unsigned int v42; // edx
  unsigned int v43; // ecx
  int v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  HKEY *v47; // rbx
  unsigned int v48; // eax
  unsigned __int64 v49; // rax
  __int64 v50; // r9
  DWORD v51; // ecx
  const BYTE *v52; // rax
  unsigned int v53; // eax
  unsigned int v54; // eax
  __int64 v55; // rbx
  unsigned int v57; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-C1h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-C1h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-C1h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-C1h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-C1h]
  unsigned int dwOptionse; // [rsp+20h] [rbp-C1h]
  unsigned int dwOptionsf; // [rsp+20h] [rbp-C1h]
  unsigned int dwOptionsg; // [rsp+20h] [rbp-C1h]
  unsigned int dwOptionsh; // [rsp+20h] [rbp-C1h]
  unsigned int dwOptionsi; // [rsp+20h] [rbp-C1h]
  unsigned int dwOptionsj; // [rsp+20h] [rbp-C1h]
  unsigned int pvData; // [rsp+50h] [rbp-91h] BYREF
  DWORD pcbData; // [rsp+54h] [rbp-8Dh] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-89h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-81h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-79h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-71h] BYREF
  const struct _MVProvisionData *v75; // [rsp+78h] [rbp-69h]
  BYTE *v76; // [rsp+80h] [rbp-61h]
  HKEY *v77; // [rsp+88h] [rbp-59h]
  BYTE *v78[2]; // [rsp+90h] [rbp-51h] BYREF
  __int64 v79; // [rsp+A0h] [rbp-41h]
  unsigned __int64 v80; // [rsp+A8h] [rbp-39h]
  LPCWSTR lpSubKey[3]; // [rsp+B0h] [rbp-31h] BYREF
  unsigned __int64 v82; // [rsp+C8h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]

  v75 = a2;
  v77 = this;
  *(_DWORD *)Data = a3;
  ProvResults::LazyCreateParentKey((ProvResults *)this);
  ProvResults::GetChildKeyNameFromProvData(lpSubKey);
  dwDisposition = 0;
  hKey = 0;
  v9 = (const WCHAR *)lpSubKey;
  if ( v82 >= 8 )
    v9 = lpSubKey[0];
  v10 = RegCreateKeyExW(this[9], v9, 0, 0, 0, 3u, 0, &hKey, &dwDisposition);
  if ( v10 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xC0,
      (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)v10,
      dwOptions);
  v11 = -1;
  do
    ++v11;
  while ( a4[v11] );
  v12 = v11 + 2;
  v76 = 0;
  v13 = saturated_mul(v11 + 2, 2u);
  v14 = (BYTE *)operator new[](v13);
  v16 = v14;
  if ( v14 )
    memset_0(v14, 0, v13);
  else
    v16 = 0;
  v76 = v16;
  if ( !v16 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0xC6,
      (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      v15);
  v17 = 0;
  v18 = -1;
  do
    ++v18;
  while ( a4[v18] );
  if ( v18 )
  {
    do
    {
      v19 = 0;
      if ( a4[v17] != 47 )
        v19 = a4[v17];
      *(_WORD *)&v16[2 * v17++] = v19;
      v20 = -1;
      do
        ++v20;
      while ( a4[v20] );
    }
    while ( v17 < v20 );
  }
  phkResult = 0;
  v21 = 2 * v12;
  if ( is_mul_ok(v12, 2u) )
  {
    v22 = 0;
  }
  else
  {
    v21 = -1;
    v22 = 2147942934LL;
  }
  if ( (int)v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCE,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)v22,
      dwOptions);
  if ( v21 > 0xFFFFFFFF )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      v21 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
      dwOptions);
  v23 = RegSetValueExW(hKey, L"Categories", 0, 7u, v16, v21);
  if ( v23 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xD3,
      (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)v23,
      dwOptionsa);
  v24 = -1;
  do
    ++v24;
  while ( *(_WORD *)&lpData[2 * v24] );
  phkResult = 0;
  v25 = v24 + 1;
  v26 = 2 * v25;
  if ( is_mul_ok(v25, 2u) )
  {
    v27 = 0;
  }
  else
  {
    v26 = -1;
    v27 = 2147942934LL;
  }
  if ( (int)v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)v27,
      dwOptionsa);
  if ( v26 > 0xFFFFFFFF )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      v26 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
      dwOptionsa);
  v28 = RegSetValueExW(hKey, L"Message", 0, 1u, lpData, v26);
  if ( v28 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xDB,
      (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)v28,
      dwOptionsb);
  if ( lpValueName )
  {
    v29 = -1;
    do
      ++v29;
    while ( *(_WORD *)&lpValueName[2 * v29] );
    phkResult = 0;
    v30 = v29 + 1;
    v31 = 2 * v30;
    if ( is_mul_ok(v30, 2u) )
    {
      v32 = 0;
    }
    else
    {
      v31 = -1;
      v32 = 2147942934LL;
    }
    if ( (int)v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE2,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
        (const char *)v32,
        dwOptionsb);
    if ( v31 > 0xFFFFFFFF )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE3,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
        v31 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
        dwOptionsb);
    v33 = RegSetValueExW(hKey, L"FailingNodePath", 0, 1u, lpValueName, v31);
    if ( v33 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xE5,
        (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
        (const char *)v33,
        dwOptionsb);
  }
  if ( a7 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *(_WORD *)&a7[2 * v34] );
    if ( v34 )
    {
      phkResult = 0;
      v35 = v34 + 1;
      v36 = 2 * v35;
      if ( is_mul_ok(v35, 2u) )
      {
        v37 = 0;
      }
      else
      {
        v36 = -1;
        v37 = 2147942934LL;
      }
      if ( (int)v37 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xED,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
          (const char *)v37,
          dwOptionsb);
      if ( v36 > 0xFFFFFFFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xEE,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
          v36 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
          dwOptionsb);
      v38 = RegSetValueExW(hKey, L"FailingCategory", 0, 1u, a7, v36);
      if ( v38 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0xF0,
          (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
          (const char *)v38,
          dwOptionsc);
    }
  }
  pvData = 0;
  if ( *(int *)Data < 0 || *(_DWORD *)Data == 44761091 )
  {
    pcbData = 4;
    ValueW = RegGetValueW(hKey, 0, L"NumFailures", 0x10u, 0, &pvData, &pcbData);
    if ( ValueW )
    {
      wil::details::in1diag3::_Log_Win32(retaddr, v40, v41, (const char *)ValueW, dwOptionsd);
      v42 = 0;
      pvData = 0;
    }
    else
    {
      v42 = pvData;
    }
    if ( *(int *)Data < 0 )
    {
      v43 = v42 + 1;
      v44 = -1;
      if ( v42 + 1 >= v42 )
        v44 = v42 + 1;
      pvData = v44;
      if ( v43 < v42 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x105,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
          v43 < v42 ? (const char *)0x80070216LL : 0,
          dwOptionsd);
    }
  }
  v45 = RegSetValueExW(hKey, L"LastResult", 0, 4u, Data, 4u);
  if ( v45 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x10B,
      (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)v45,
      dwOptionse);
  v46 = RegSetValueExW(hKey, L"NumFailures", 0, 4u, (const BYTE *)&pvData, 4u);
  if ( v46 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x10D,
      (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)v46,
      dwOptionsf);
  if ( *(_DWORD *)Data == 44761091 )
  {
    phkResult = 0;
    v47 = v77;
    v48 = RegCreateKeyExW(v77[4], L"PendingResults", 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
    if ( v48 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x114,
        (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
        (const char *)v48,
        dwOptionsg);
    ProvResults::GetResultsKeyNameFromProvData(v47, v78, v75);
    v49 = 2 * (v79 + 1);
    if ( is_mul_ok(v79 + 1, 2u) )
    {
      v50 = 0;
    }
    else
    {
      v49 = -1;
      v50 = 2147942934LL;
    }
    if ( (int)v50 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11A,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
        (const char *)v50,
        dwOptionsg);
    v51 = v49;
    if ( v49 > 0xFFFFFFFF )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11B,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
        v49 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
        dwOptionsg);
    v52 = (const BYTE *)v78;
    if ( v80 >= 8 )
      v52 = v78[0];
    v53 = RegSetValueExW(phkResult, (LPCWSTR)lpValueName, 0, 1u, v52, v51);
    if ( v53 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x11C,
        (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
        (const char *)v53,
        dwOptionsh);
    pcbData = 2;
    v54 = RegSetValueExW(hKey, L"State", 0, 4u, (const BYTE *)&pcbData, 4u);
    if ( v54 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x123,
        (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
        (const char *)v54,
        dwOptionsi);
    if ( v80 >= 8 )
      operator delete(v78[0]);
    v80 = 7;
    v79 = 0;
    LOWORD(v78[0]) = 0;
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  else
  {
    pcbData = 3;
    v57 = RegSetValueExW(hKey, L"State", 0, 4u, (const BYTE *)&pcbData, 4u);
    if ( v57 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x12A,
        (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
        (const char *)v57,
        dwOptionsj);
  }
  v55 = pvData;
  operator delete[](v16);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v82 >= 8 )
    operator delete((void *)lpSubKey[0]);
  return v55;
}

```

## disassembly

```asm
0x18003c438  push    rbp
0x18003c43a  push    rbx
0x18003c43b  push    rsi
0x18003c43c  push    rdi
0x18003c43d  push    r12
0x18003c43f  push    r13
0x18003c441  push    r14
0x18003c443  push    r15
0x18003c445  lea     rbp, [rsp-7]
0x18003c44a  sub     rsp, 0E8h
0x18003c451  mov     rax, cs:__security_cookie
0x18003c458  xor     rax, rsp
0x18003c45b  mov     [rbp+3Fh+var_50], rax
0x18003c45f  mov     rdi, r9
0x18003c462  mov     rsi, rdx
0x18003c465  mov     [rbp+3Fh+var_A8], rdx
0x18003c469  mov     rbx, rcx
0x18003c46c  mov     [rbp+3Fh+var_98], rcx
0x18003c470  mov     dword ptr [rsp+120h+Data], r8d
0x18003c475  mov     r15, [rbp+3Fh+lpData]
0x18003c479  mov     r13, [rbp+3Fh+lpValueName]
0x18003c47d  mov     r12, [rbp+3Fh+arg_30]
0x18003c481  xor     r14d, r14d
0x18003c484  call    ?LazyCreateParentKey@ProvResults@@AEBAXXZ; ProvResults::LazyCreateParentKey(void)
0x18003c489  mov     rdx, rsi
0x18003c48c  lea     rcx, [rbp+3Fh+lpSubKey]; void *
0x18003c490  call    ?GetChildKeyNameFromProvData@ProvResults@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_MVProvisionData@@@Z; ProvResults::GetChildKeyNameFromProvData(_MVProvisionData const &)
0x18003c495  nop
0x18003c496  mov     [rbp+3Fh+dwDisposition], r14d
0x18003c49a  mov     [rsp+120h+hKey], r14
0x18003c49f  lea     rdx, [rbp+3Fh+lpSubKey]
0x18003c4a3  cmp     [rbp+3Fh+var_58], 8
0x18003c4a8  cmovnb  rdx, [rbp+3Fh+lpSubKey]; lpSubKey
0x18003c4ad  lea     rax, [rbp+3Fh+dwDisposition]
0x18003c4b1  mov     [rsp+120h+lpdwDisposition], rax; lpdwDisposition
0x18003c4b6  lea     rax, [rsp+120h+hKey]
0x18003c4bb  mov     [rsp+120h+phkResult], rax; phkResult
0x18003c4c0  mov     [rsp+120h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18003c4c5  mov     [rsp+120h+samDesired], 3; samDesired
0x18003c4cd  mov     [rsp+120h+dwOptions], r14d; int
0x18003c4d2  xor     r9d, r9d; lpClass
0x18003c4d5  xor     r8d, r8d; Reserved
0x18003c4d8  mov     rcx, [rbx+48h]; hKey
0x18003c4dc  call    cs:__imp_RegCreateKeyExW
0x18003c4e2  mov     rcx, [rbp+47h]; this
0x18003c4e6  test    eax, eax
0x18003c4e8  jnz     loc_18003CAEA
0x18003c4ee  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003c4f2  mov     rax, rcx
0x18003c4f5  inc     rax
0x18003c4f8  cmp     [rdi+rax*2], r14w
0x18003c4fd  jnz     short loc_18003C4F5
0x18003c4ff  lea     rsi, [rax+2]
0x18003c503  mov     [rbp+3Fh+var_A0], r14
0x18003c507  mov     eax, 2
0x18003c50c  mul     rsi
0x18003c50f  mov     rbx, rax
0x18003c512  cmovb   rbx, rcx
0x18003c516  mov     rcx, rbx; unsigned __int64
0x18003c519  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003c51e  mov     r14, rax
0x18003c521  xor     edx, edx; Val
0x18003c523  test    rax, rax
0x18003c526  jz      short loc_18003C537
0x18003c528  mov     r8, rbx; Size
0x18003c52b  mov     rcx, rax; void *
0x18003c52e  call    memset_0
0x18003c533  xor     edx, edx
0x18003c535  jmp     short loc_18003C53A
0x18003c537  mov     r14, rdx
0x18003c53a  mov     [rbp+3Fh+var_A0], r14
0x18003c53e  mov     rcx, [rbp+47h]; this
0x18003c542  test    r14, r14
0x18003c545  jz      loc_18003CAFF
0x18003c54b  mov     rcx, rdx
0x18003c54e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003c552  mov     rax, rbx
0x18003c555  inc     rax
0x18003c558  cmp     [rdi+rax*2], dx
0x18003c55c  jnz     short loc_18003C555
0x18003c55e  test    rax, rax
0x18003c561  jz      short loc_18003C588
0x18003c563  mov     eax, edx
0x18003c565  cmp     word ptr [rdi+rcx*2], 2Fh ; '/'
0x18003c56a  cmovnz  ax, [rdi+rcx*2]
0x18003c56f  mov     [r14+rcx*2], ax
0x18003c574  inc     rcx
0x18003c577  mov     rax, rbx
0x18003c57a  inc     rax
0x18003c57d  cmp     [rdi+rax*2], dx
0x18003c581  jnz     short loc_18003C57A
0x18003c583  cmp     rcx, rax
0x18003c586  jb      short loc_18003C563
0x18003c588  xor     edi, edi
0x18003c58a  mov     [rbp+3Fh+var_B8], rdi
0x18003c58e  lea     eax, [rdi+2]
0x18003c591  mul     rsi
0x18003c594  mov     r8d, 80070216h
0x18003c59a  test    rdx, rdx
0x18003c59d  jnz     short loc_18003C5A4
0x18003c59f  mov     r9d, edi
0x18003c5a2  jmp     short loc_18003C5AA
0x18003c5a4  mov     rax, rbx
0x18003c5a7  mov     r9d, r8d; char *
0x18003c5aa  mov     rcx, [rbp+47h]; this
0x18003c5ae  test    r9d, r9d
0x18003c5b1  js      loc_18003CB11
0x18003c5b7  mov     esi, 0FFFFFFFFh
0x18003c5bc  cmp     rax, rsi
0x18003c5bf  mov     ecx, eax
0x18003c5c1  jbe     short loc_18003C5C5
0x18003c5c3  mov     ecx, esi
0x18003c5c5  cmp     rsi, rax
0x18003c5c8  sbb     r9d, r9d
0x18003c5cb  and     r9d, r8d; char *
0x18003c5ce  mov     r10, [rbp+47h]
0x18003c5d2  cmp     rax, rsi
0x18003c5d5  ja      loc_18003CB23
0x18003c5db  mov     [rsp+120h+samDesired], ecx; cbData
0x18003c5df  mov     qword ptr [rsp+120h+dwOptions], r14; int
0x18003c5e4  mov     r9d, 7; dwType
0x18003c5ea  xor     r8d, r8d; Reserved
0x18003c5ed  lea     rdx, aCategories; "Categories"
0x18003c5f4  mov     rcx, [rsp+120h+hKey]; hKey
0x18003c5f9  call    cs:__imp_RegSetValueExW
0x18003c5ff  mov     rcx, [rbp+47h]; this
0x18003c603  test    eax, eax
0x18003c605  jnz     loc_18003CB38
0x18003c60b  mov     rcx, rbx
0x18003c60e  inc     rcx
0x18003c611  cmp     [r15+rcx*2], di
0x18003c616  jnz     short loc_18003C60E
0x18003c618  mov     [rbp+3Fh+var_B8], rdi
0x18003c61c  inc     rcx
0x18003c61f  mov     eax, 2
0x18003c624  mul     rcx
0x18003c627  test    rdx, rdx
0x18003c62a  jnz     short loc_18003C631
0x18003c62c  mov     r9d, edi
0x18003c62f  jmp     short loc_18003C63A
0x18003c631  mov     rax, rbx
0x18003c634  mov     r9d, 80070216h; char *
0x18003c63a  mov     rcx, [rbp+47h]; this
0x18003c63e  test    r9d, r9d
0x18003c641  js      loc_18003CB4D
0x18003c647  cmp     rax, rsi
0x18003c64a  mov     ecx, eax
0x18003c64c  jbe     short loc_18003C650
0x18003c64e  mov     ecx, esi
0x18003c650  cmp     rsi, rax
0x18003c653  sbb     r9d, r9d
0x18003c656  and     r9d, 80070216h; char *
0x18003c65d  mov     r10, [rbp+47h]
0x18003c661  cmp     rax, rsi
0x18003c664  ja      loc_18003CB5F
0x18003c66a  mov     [rsp+120h+samDesired], ecx; cbData
0x18003c66e  mov     qword ptr [rsp+120h+dwOptions], r15; int
0x18003c673  mov     r9d, 1; dwType
0x18003c679  xor     r8d, r8d; Reserved
0x18003c67c  lea     rdx, aMessage; "Message"
0x18003c683  mov     rcx, [rsp+120h+hKey]; hKey
0x18003c688  call    cs:__imp_RegSetValueExW
0x18003c68e  mov     rcx, [rbp+47h]; this
0x18003c692  test    eax, eax
0x18003c694  jnz     loc_18003CB74
0x18003c69a  test    r13, r13
0x18003c69d  jz      loc_18003C733
0x18003c6a3  mov     rcx, rbx
0x18003c6a6  inc     rcx
0x18003c6a9  cmp     [r13+rcx*2+0], di
0x18003c6af  jnz     short loc_18003C6A6
0x18003c6b1  mov     [rbp+3Fh+var_B8], rdi
0x18003c6b5  inc     rcx
0x18003c6b8  mov     eax, 2
0x18003c6bd  mul     rcx
0x18003c6c0  test    rdx, rdx
0x18003c6c3  jnz     short loc_18003C6CA
0x18003c6c5  mov     r9d, edi
0x18003c6c8  jmp     short loc_18003C6D3
0x18003c6ca  mov     rax, rbx
0x18003c6cd  mov     r9d, 80070216h; char *
0x18003c6d3  mov     rcx, [rbp+47h]; this
0x18003c6d7  test    r9d, r9d
0x18003c6da  js      loc_18003CB89
0x18003c6e0  cmp     rax, rsi
0x18003c6e3  mov     ecx, eax
0x18003c6e5  jbe     short loc_18003C6E9
0x18003c6e7  mov     ecx, esi
0x18003c6e9  cmp     rsi, rax
0x18003c6ec  sbb     r9d, r9d
0x18003c6ef  and     r9d, 80070216h; char *
0x18003c6f6  mov     r10, [rbp+47h]
0x18003c6fa  cmp     rax, rsi
0x18003c6fd  ja      loc_18003CB9B
0x18003c703  mov     [rsp+120h+samDesired], ecx; cbData
0x18003c707  mov     qword ptr [rsp+120h+dwOptions], r13; int
0x18003c70c  mov     r9d, 1; dwType
0x18003c712  xor     r8d, r8d; Reserved
0x18003c715  lea     rdx, aFailingnodepat; "FailingNodePath"
0x18003c71c  mov     rcx, [rsp+120h+hKey]; hKey
0x18003c721  call    cs:__imp_RegSetValueExW
0x18003c727  mov     rcx, [rbp+47h]; this
0x18003c72b  test    eax, eax
0x18003c72d  jnz     loc_18003CBB0
0x18003c733  test    r12, r12
0x18003c736  jz      loc_18003C7D4
0x18003c73c  mov     rcx, rbx
0x18003c73f  inc     rcx
0x18003c742  cmp     [r12+rcx*2], di
0x18003c747  jnz     short loc_18003C73F
0x18003c749  test    rcx, rcx
0x18003c74c  jz      loc_18003C7D4
0x18003c752  mov     [rbp+3Fh+var_B8], rdi
0x18003c756  inc     rcx
0x18003c759  mov     eax, 2
0x18003c75e  mul     rcx
0x18003c761  test    rdx, rdx
0x18003c764  jnz     short loc_18003C76B
0x18003c766  mov     r9d, edi
0x18003c769  jmp     short loc_18003C774
0x18003c76b  mov     rax, rbx
0x18003c76e  mov     r9d, 80070216h; char *
0x18003c774  mov     rcx, [rbp+47h]; this
0x18003c778  test    r9d, r9d
0x18003c77b  js      loc_18003CBC5
0x18003c781  cmp     rax, rsi
0x18003c784  mov     ecx, eax
0x18003c786  jbe     short loc_18003C78A
0x18003c788  mov     ecx, esi
0x18003c78a  cmp     rsi, rax
0x18003c78d  sbb     r9d, r9d
0x18003c790  and     r9d, 80070216h; char *
0x18003c797  mov     r10, [rbp+47h]
0x18003c79b  cmp     rax, rsi
0x18003c79e  ja      loc_18003CBD7
0x18003c7a4  mov     [rsp+120h+samDesired], ecx; cbData
0x18003c7a8  mov     qword ptr [rsp+120h+dwOptions], r12; unsigned int
0x18003c7ad  mov     r9d, 1; dwType
0x18003c7b3  xor     r8d, r8d; Reserved
0x18003c7b6  lea     rdx, aFailingcategor; "FailingCategory"
0x18003c7bd  mov     rcx, [rsp+120h+hKey]; hKey
0x18003c7c2  call    cs:__imp_RegSetValueExW
0x18003c7c8  mov     rcx, [rbp+47h]; this
0x18003c7cc  test    eax, eax
0x18003c7ce  jnz     loc_18003CBEC
0x18003c7d4  mov     [rsp+120h+pvData], edi
0x18003c7d8  mov     ebx, 2AB0003h
0x18003c7dd  mov     r15d, 4
0x18003c7e3  test    dword ptr [rsp+120h+Data], 80000000h
0x18003c7eb  jnz     short loc_18003C7F3
0x18003c7ed  cmp     dword ptr [rsp+120h+Data], ebx
0x18003c7f1  jnz     short loc_18003C871
0x18003c7f3  mov     [rsp+120h+pcbData], r15d
0x18003c7f8  lea     rax, [rsp+120h+pcbData]
0x18003c7fd  mov     [rsp+120h+lpSecurityAttributes], rax; pcbData
0x18003c802  lea     rax, [rsp+120h+pvData]
0x18003c807  mov     qword ptr [rsp+120h+samDesired], rax; pvData
0x18003c80c  mov     qword ptr [rsp+120h+dwOptions], rdi; int
0x18003c811  mov     r9d, 10h; dwFlags
0x18003c817  lea     r8, aNumfailures; "NumFailures"
0x18003c81e  xor     edx, edx; lpSubKey
0x18003c820  mov     rcx, [rsp+120h+hKey]; hkey
0x18003c825  call    cs:__imp_RegGetValueW
0x18003c82b  mov     rcx, [rbp+47h]; this
0x18003c82f  test    eax, eax
0x18003c831  jz      short loc_18003C843
0x18003c833  mov     r9d, eax; char *
0x18003c836  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18003c83b  mov     edx, edi
0x18003c83d  mov     [rsp+120h+pvData], edx
0x18003c841  jmp     short loc_18003C847
0x18003c843  mov     edx, [rsp+120h+pvData]
0x18003c847  cmp     dword ptr [rsp+120h+Data], edi
0x18003c84b  jge     short loc_18003C871
0x18003c84d  lea     ecx, [rdx+1]
0x18003c850  mov     eax, esi
0x18003c852  cmp     ecx, edx
0x18003c854  cmovnb  eax, ecx
0x18003c857  sbb     r9d, r9d
0x18003c85a  and     r9d, 80070216h; char *
0x18003c861  mov     [rsp+120h+pvData], eax
0x18003c865  mov     rax, [rbp+47h]
0x18003c869  cmp     ecx, edx
0x18003c86b  jb      loc_18003CC01
0x18003c871  mov     [rsp+120h+samDesired], r15d; cbData
0x18003c876  lea     rax, [rsp+120h+Data]
0x18003c87b  mov     qword ptr [rsp+120h+dwOptions], rax; unsigned int
0x18003c880  mov     r9d, r15d; dwType
0x18003c883  xor     r8d, r8d; Reserved
0x18003c886  lea     rdx, aLastresult; "LastResult"
0x18003c88d  mov     rcx, [rsp+120h+hKey]; hKey
0x18003c892  call    cs:__imp_RegSetValueExW
0x18003c898  mov     rcx, [rbp+47h]; this
0x18003c89c  test    eax, eax
0x18003c89e  jnz     loc_18003CC16
0x18003c8a4  mov     [rsp+120h+samDesired], r15d; cbData
0x18003c8a9  lea     rax, [rsp+120h+pvData]
0x18003c8ae  mov     qword ptr [rsp+120h+dwOptions], rax; unsigned int
0x18003c8b3  mov     r9d, r15d; dwType
0x18003c8b6  xor     r8d, r8d; Reserved
  ... truncated ...
```
