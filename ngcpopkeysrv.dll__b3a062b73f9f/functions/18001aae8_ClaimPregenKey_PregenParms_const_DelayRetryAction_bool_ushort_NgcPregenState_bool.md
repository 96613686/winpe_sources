# ClaimPregenKey(_PregenParms const *,DelayRetryAction *,bool *,ushort * *,_NgcPregenState *,bool *)

- ea: `0x18001aae8`
- end: `0x18001b054`
- name: `?ClaimPregenKey@@YAJPEBU_PregenParms@@PEAW4DelayRetryAction@@PEA_NPEAPEAGPEAU_NgcPregenState@@2@Z`
- size: `1388`
- prototype: `__int64 __fastcall(const struct _PregenParms *, enum DelayRetryAction *, bool *, unsigned __int16 **, struct _NgcPregenState *, bool *)`
- caller_count: `4`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019f44`
- `0x18001a170`
- `0x18001a698`
- `0x18001bee8`

## callees

- `0x18000b0fc`
- `0x18000db5c`
- `0x18001069c`
- `0x180010730`
- `0x180014e40`
- `0x180015030`
- `0x1800153f0`
- `0x18001737c`
- `0x18001aa6c`
- `0x18001aae8`
- `0x18001dc5c`
- `0x180022ef4`
- `0x18002308c`
- `0x180023264`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001adac`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001adac`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001aef7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001aef7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001abe7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001abe7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001aea9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001aea9`

## string_xrefs

- `0x18001abab`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001ac04`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001ac60`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001ac76`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
__int64 __fastcall ClaimPregenKey(
        const struct _PregenParms *a1,
        enum DelayRetryAction *a2,
        bool *a3,
        unsigned __int16 **a4,
        struct _NgcPregenState *a5,
        bool *a6)
{
  DWORD v7; // r12d
  const unsigned __int16 *v8; // rdx
  NgcUtils *v9; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  signed int v11; // ebx
  HKEY *v12; // rax
  int v13; // eax
  unsigned int *v14; // r9
  bool v15; // sf
  __int64 v16; // rdx
  int v17; // eax
  int v18; // r14d
  struct _NgcPregenState *v19; // rsi
  int RegistryDwordValue; // eax
  const unsigned __int16 *v21; // rdx
  NgcUtils *v22; // rcx
  int v23; // eax
  void *p_lpName; // rcx
  int v25; // eax
  DWORD v26; // r15d
  WCHAR *v27; // r14
  LSTATUS v28; // eax
  bool v29; // cl
  const unsigned __int16 *v30; // rdx
  NgcUtils *v31; // rcx
  int v32; // eax
  int v33; // eax
  HKEY *v34; // rax
  LSTATUS Key; // eax
  int v36; // eax
  bool v37; // sf
  __int64 v39; // rdx
  unsigned __int16 **phkResult; // [rsp+28h] [rbp-A9h]
  int phkResulta; // [rsp+28h] [rbp-A9h]
  unsigned int *phkResultb; // [rsp+28h] [rbp-A9h]
  unsigned int *phkResultc; // [rsp+28h] [rbp-A9h]
  unsigned __int16 **phkResultd; // [rsp+28h] [rbp-A9h]
  int phkResulte; // [rsp+28h] [rbp-A9h]
  bool v46; // [rsp+58h] [rbp-79h] BYREF
  char v47; // [rsp+59h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-71h] BYREF
  LPWSTR lpName; // [rsp+68h] [rbp-69h] BYREF
  LPCWSTR v50; // [rsp+70h] [rbp-61h] BYREF
  int v51; // [rsp+78h] [rbp-59h] BYREF
  DWORD cchName; // [rsp+7Ch] [rbp-55h] BYREF
  NgcUtils *v53; // [rsp+80h] [rbp-51h] BYREF
  LPCWSTR lpSubKey; // [rsp+88h] [rbp-49h] BYREF
  __int64 v55; // [rsp+90h] [rbp-41h] BYREF
  _QWORD v56[6]; // [rsp+98h] [rbp-39h] BYREF
  __int16 v57; // [rsp+C8h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+4Fh]
  const struct _PregenParms *v59; // [rsp+128h] [rbp+57h] BYREF
  enum DelayRetryAction *v60; // [rsp+130h] [rbp+5Fh] BYREF
  bool *v61; // [rsp+138h] [rbp+67h]
  char v62; // [rsp+140h] [rbp+6Fh] BYREF

  v61 = a3;
  v60 = a2;
  v59 = a1;
  v47 = 1;
  v7 = 0;
  v51 = 0;
  *a3 = 0;
  *a6 = 0;
  if ( v60 )
    *v60 = DelayRetryUnknown;
  v62 = 0;
  if ( a4 )
  {
    *a4 = 0;
    v62 = 1;
  }
  v56[0] = &v47;
  v56[1] = &v59;
  v56[2] = &v60;
  v56[3] = &v62;
  v56[4] = &v51;
  v56[5] = &a6;
  v57 = 256;
  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        v9,
                                        v8,
                                        *((const unsigned __int16 **)v59 + 3),
                                        (const unsigned __int16 *)&lpSubKey,
                                        phkResult);
  v11 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      phkResulta);
LABEL_64:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
    wil::details::ScopeExitFnGuard__lambda_d8c3b9e5f5c58a07f3d3914d6b90376c___::operator()(v56);
    return (unsigned int)v11;
  }
  hKey = 0;
  v12 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, v12);
  v15 = v13 < 0;
  if ( v13 > 0 )
  {
    v13 = (unsigned __int16)v13 | 0x80070000;
    v15 = v13 < 0;
  }
  if ( v15 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x16C,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v13,
      (int)phkResultb);
    v16 = 366;
LABEL_11:
    v51 = 1;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)0x80070103LL,
      (int)phkResultb);
LABEL_58:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v11 = -2147024637;
    goto LABEL_64;
  }
  cchName = 0;
  LODWORD(lpName) = 0;
  v17 = NgcUtils::QueryRegistrySubKeys((NgcUtils *)hKey, (HKEY)&lpName, &cchName, v14);
  v11 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v17,
      (int)phkResultb);
LABEL_63:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_64;
  }
  v18 = (int)lpName;
  v19 = a5;
  if ( a5 )
  {
    *((_DWORD *)a5 + 1) = (_DWORD)lpName;
    RegistryDwordValue = NgcUtils::GetRegistryDwordValue(
                           (NgcUtils *)hKey,
                           0,
                           (const unsigned __int16 *)&stru_18002B278,
                           (const unsigned __int16 *)v19 + 4,
                           phkResultb);
    if ( RegistryDwordValue < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x181,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)RegistryDwordValue,
        (int)phkResultb);
    if ( *(_DWORD *)v59 == 1 )
    {
      v50 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v50,
        0);
      v23 = NgcUtils::GetNgcStateSeparatedRegistryLocation(
              v22,
              v21,
              L"AIKCertEnroll",
              (const unsigned __int16 *)&v50,
              (unsigned __int16 **)phkResultb);
      v11 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x188,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
          (const char *)(unsigned int)v23,
          (int)phkResultc);
        p_lpName = &v50;
LABEL_62:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(p_lpName);
        goto LABEL_63;
      }
      v25 = NgcUtils::GetRegistryDwordValue(
              (NgcUtils *)0xFFFFFFFF80000002LL,
              (HKEY)v50,
              (const unsigned __int16 *)&stru_18002B278,
              (const unsigned __int16 *)v19 + 6,
              phkResultc);
      if ( v25 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x18E,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
          (const char *)(unsigned int)v25,
          (int)phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
    }
  }
  if ( !v18 )
  {
    v16 = 405;
    goto LABEL_11;
  }
  v26 = cchName + 1;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpName,
    0,
    cchName + 1);
  v27 = lpName;
  if ( !lpName )
  {
    v11 = -2147024882;
    v39 = 410;
LABEL_60:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v39,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v11,
      (int)phkResultb);
LABEL_61:
    p_lpName = &lpName;
    goto LABEL_62;
  }
  while ( 1 )
  {
    cchName = v26;
    v28 = RegEnumKeyExW(hKey, v7, v27, &cchName, 0, 0, 0, 0);
    v11 = v28;
    if ( v28 > 0 )
      v11 = (unsigned __int16)v28 | 0x80070000;
    if ( v11 == -2147024637 )
    {
      v51 = 1;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
      goto LABEL_58;
    }
    if ( v11 < 0 )
    {
      v39 = 430;
      goto LABEL_60;
    }
    if ( *(_DWORD *)v59 != 1 )
      goto LABEL_41;
    v46 = 0;
    if ( OpenKeyAndVerifyCertExists(v29, v27, &v46) >= 0 )
      break;
    if ( v46 )
      *v61 = 1;
LABEL_46:
    ++v7;
  }
  if ( !v62 )
    goto LABEL_53;
  v53 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v53,
    0);
  v32 = NgcUtils::GetNgcStateSeparatedRegistryLocation(
          v31,
          v30,
          L"PregenKeys\\ClaimedAIK",
          (const unsigned __int16 *)&v53,
          (unsigned __int16 **)phkResultb);
  v11 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C6,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v32,
      (int)phkResultd);
    goto LABEL_51;
  }
  v50 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v50,
    0);
  v33 = NgcUtils::CombineSeparateStrings(v53, L"\\", v27, (const unsigned __int16 *)&v50, phkResultd);
  v11 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D0,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v33,
      phkResulte);
    goto LABEL_49;
  }
  v55 = 0;
  v34 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v55);
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v50, 0, 0, 0, 0x2001Fu, 0, v34, 0);
  v11 = Key;
  if ( Key > 0 )
    v11 = (unsigned __int16)Key | 0x80070000;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DC,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v11,
      (int)phkResultb);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v55);
LABEL_49:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
LABEL_51:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
    goto LABEL_61;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v55);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
LABEL_41:
  if ( !v62 )
    goto LABEL_53;
  v36 = RegDeleteKeyExW(hKey, v27, 0, 0);
  v37 = v36 < 0;
  if ( v36 > 0 )
  {
    v36 = (unsigned __int16)v36 | 0x80070000;
    v37 = v36 < 0;
  }
  if ( v37 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1EB,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v36,
      (int)phkResultb);
    goto LABEL_46;
  }
  lpName = 0;
  *a4 = v27;
  v51 = 3;
LABEL_53:
  if ( v60 )
    *v60 = DelayRetrySuccess;
  v47 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
  wil::details::ScopeExitFnGuard__lambda_d8c3b9e5f5c58a07f3d3914d6b90376c___::operator()(v56);
  return 0;
}

```

## disassembly

```asm
0x18001aae8  mov     rax, rsp
0x18001aaeb  mov     [rax+18h], r8
0x18001aaef  mov     [rax+10h], rdx
0x18001aaf3  mov     [rax+8], rcx
0x18001aaf7  push    rbp
0x18001aaf8  push    rbx
0x18001aaf9  push    rsi
0x18001aafa  push    rdi
0x18001aafb  push    r12
0x18001aafd  push    r13
0x18001aaff  push    r14
0x18001ab01  push    r15
0x18001ab03  lea     rbp, [rax-4Fh]
0x18001ab07  sub     rsp, 0D8h
0x18001ab0e  mov     r13, r9
0x18001ab11  mov     r15d, 1
0x18001ab17  mov     [rbp+47h+var_BF], r15b
0x18001ab1b  xor     r12d, r12d
0x18001ab1e  mov     [rbp+47h+var_A0], r12d
0x18001ab22  mov     [r8], r12b
0x18001ab25  mov     rax, [rbp+47h+arg_28]
0x18001ab29  mov     [rax], r12b
0x18001ab2c  mov     rax, [rbp+47h+arg_8]
0x18001ab30  test    rax, rax
0x18001ab33  jz      short loc_18001AB38
0x18001ab35  mov     [rax], r12d
0x18001ab38  mov     [rbp+47h+arg_18], r12b
0x18001ab3c  test    r13, r13
0x18001ab3f  jz      short loc_18001AB48
0x18001ab41  mov     [r9], r12
0x18001ab44  mov     [rbp+47h+arg_18], r15b
0x18001ab48  lea     rax, [rbp+47h+var_BF]
0x18001ab4c  mov     [rbp+47h+var_80], rax
0x18001ab50  lea     rax, [rbp+47h+arg_0]
0x18001ab54  mov     [rbp+47h+var_78], rax
0x18001ab58  lea     rax, [rbp+47h+arg_8]
0x18001ab5c  mov     [rbp+47h+var_70], rax
0x18001ab60  lea     rax, [rbp+47h+arg_18]
0x18001ab64  mov     [rbp+47h+var_68], rax
0x18001ab68  lea     rax, [rbp+47h+var_A0]
0x18001ab6c  mov     [rbp+47h+var_60], rax
0x18001ab70  lea     rax, [rbp+47h+arg_28]
0x18001ab74  mov     [rbp+47h+var_58], rax
0x18001ab78  mov     [rbp+47h+var_50], 100h
0x18001ab7e  mov     [rbp+47h+lpSubKey], r12
0x18001ab82  xor     edx, edx
0x18001ab84  lea     rcx, [rbp+47h+lpSubKey]
0x18001ab88  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001ab8d  lea     r9, [rbp+47h+lpSubKey]; unsigned __int16 *
0x18001ab91  mov     r8, [rbp+47h+arg_0]
0x18001ab95  mov     r8, [r8+18h]; unsigned __int16 *
0x18001ab99  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001ab9e  mov     ebx, eax
0x18001aba0  test    eax, eax
0x18001aba2  jns     short loc_18001ABC1
0x18001aba4  mov     rcx, [rbp+4Fh]; this
0x18001aba8  mov     r9d, eax; char *
0x18001abab  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001abb2  mov     edx, 15Eh; void *
0x18001abb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001abbc  jmp     loc_18001B02B
0x18001abc1  mov     [rbp+47h+hKey], r12
0x18001abc5  lea     rcx, [rbp+47h+hKey]
0x18001abc9  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18001abce  mov     [rsp+110h+phkResult], rax; int
0x18001abd3  mov     r9d, 0F003Fh; samDesired
0x18001abd9  xor     r8d, r8d; ulOptions
0x18001abdc  mov     rdx, [rbp+47h+lpSubKey]; lpSubKey
0x18001abe0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001abe7  call    cs:__imp_RegOpenKeyExW
0x18001abed  test    eax, eax
0x18001abef  jle     short loc_18001ABFB
0x18001abf1  movzx   eax, ax
0x18001abf4  or      eax, 80070000h
0x18001abf9  test    eax, eax
0x18001abfb  jns     short loc_18001AC3A
0x18001abfd  mov     rcx, [rbp+4Fh]; this
0x18001ac01  mov     r9d, eax; char *
0x18001ac04  lea     rdi, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001ac0b  mov     r8, rdi; unsigned int
0x18001ac0e  mov     edx, 16Ch; void *
0x18001ac13  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ac18  mov     edx, 16Eh; void *
0x18001ac1d  mov     esi, 80070103h
0x18001ac22  mov     r8, rdi; unsigned int
0x18001ac25  mov     r9d, esi; char *
0x18001ac28  mov     rcx, [rbp+4Fh]; this
0x18001ac2c  mov     [rbp+47h+var_A0], r15d
0x18001ac30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ac35  jmp     loc_18001AFF0
0x18001ac3a  mov     [rbp+47h+cchName], r12d
0x18001ac3e  mov     dword ptr [rbp+47h+lpName], r12d
0x18001ac42  lea     r8, [rbp+47h+cchName]; unsigned int *
0x18001ac46  lea     rdx, [rbp+47h+lpName]; HKEY
0x18001ac4a  mov     rcx, [rbp+47h+hKey]; this
0x18001ac4e  call    ?QueryRegistrySubKeys@NgcUtils@@YAJPEAUHKEY__@@PEAK1@Z; NgcUtils::QueryRegistrySubKeys(HKEY__ *,ulong *,ulong *)
0x18001ac53  mov     ebx, eax
0x18001ac55  test    eax, eax
0x18001ac57  jns     short loc_18001AC76
0x18001ac59  mov     rcx, [rbp+4Fh]; this
0x18001ac5d  mov     r9d, eax; char *
0x18001ac60  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001ac67  mov     edx, 177h; void *
0x18001ac6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ac71  jmp     loc_18001B021
0x18001ac76  lea     rdi, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001ac7d  mov     r14d, dword ptr [rbp+47h+lpName]
0x18001ac81  mov     rsi, [rbp+47h+arg_20]
0x18001ac85  test    rsi, rsi
0x18001ac88  jz      loc_18001AD4D
0x18001ac8e  mov     [rsi+4], r14d
0x18001ac92  lea     r9, [rsi+8]; unsigned __int16 *
0x18001ac96  lea     r8, stru_18002B278; unsigned __int16 *
0x18001ac9d  xor     edx, edx; HKEY
0x18001ac9f  mov     rcx, [rbp+47h+hKey]; this
0x18001aca3  call    ?GetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1PEAK@Z; NgcUtils::GetRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001aca8  mov     rcx, [rbp+4Fh]; this
0x18001acac  test    eax, eax
0x18001acae  jns     short loc_18001ACC0
0x18001acb0  mov     r9d, eax; char *
0x18001acb3  mov     r8, rdi; unsigned int
0x18001acb6  mov     edx, 181h; void *
0x18001acbb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001acc0  mov     rax, [rbp+47h+arg_0]
0x18001acc4  cmp     [rax], r15d
0x18001acc7  jnz     loc_18001AD4D
0x18001accd  mov     [rbp+47h+var_A8], r12
0x18001acd1  xor     edx, edx
0x18001acd3  lea     rcx, [rbp+47h+var_A8]
0x18001acd7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001acdc  lea     r9, [rbp+47h+var_A8]; unsigned __int16 *
0x18001ace0  lea     r8, aAikcertenroll; "AIKCertEnroll"
0x18001ace7  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001acec  mov     ebx, eax
0x18001acee  test    eax, eax
0x18001acf0  jns     short loc_18001AD10
0x18001acf2  mov     rcx, [rbp+4Fh]; this
0x18001acf6  mov     r9d, eax; char *
0x18001acf9  mov     r8, rdi; unsigned int
0x18001acfc  mov     edx, 188h; void *
0x18001ad01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ad06  nop
0x18001ad07  lea     rcx, [rbp+47h+var_A8]
0x18001ad0b  jmp     loc_18001B01B
0x18001ad10  lea     r9, [rsi+0Ch]; unsigned __int16 *
0x18001ad14  lea     r8, stru_18002B278; unsigned __int16 *
0x18001ad1b  mov     rdx, [rbp+47h+var_A8]; HKEY
0x18001ad1f  mov     rcx, 0FFFFFFFF80000002h; this
0x18001ad26  call    ?GetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1PEAK@Z; NgcUtils::GetRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001ad2b  mov     rcx, [rbp+4Fh]; this
0x18001ad2f  test    eax, eax
0x18001ad31  jns     short loc_18001AD44
0x18001ad33  mov     r9d, eax; char *
0x18001ad36  mov     r8, rdi; unsigned int
0x18001ad39  mov     edx, 18Eh; void *
0x18001ad3e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ad43  nop
0x18001ad44  lea     rcx, [rbp+47h+var_A8]
0x18001ad48  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001ad4d  test    r14d, r14d
0x18001ad50  jnz     short loc_18001AD5C
0x18001ad52  mov     edx, 195h
0x18001ad57  jmp     loc_18001AC1D
0x18001ad5c  mov     r15d, [rbp+47h+cchName]
0x18001ad60  inc     r15d
0x18001ad63  mov     r8d, r15d
0x18001ad66  xor     edx, edx
0x18001ad68  lea     rcx, [rbp+47h+lpName]
0x18001ad6c  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001ad71  nop
0x18001ad72  mov     r14, [rbp+47h+lpName]
0x18001ad76  test    r14, r14
0x18001ad79  jz      loc_18001AFFD
0x18001ad7f  mov     esi, 80070103h
0x18001ad84  xor     ebx, ebx
0x18001ad86  mov     [rbp+47h+cchName], r15d
0x18001ad8a  mov     [rsp+110h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18001ad8f  mov     [rsp+110h+lpcchClass], rbx; lpcchClass
0x18001ad94  mov     [rsp+110h+lpClass], rbx; lpClass
0x18001ad99  mov     [rsp+110h+phkResult], rbx; int
0x18001ad9e  lea     r9, [rbp+47h+cchName]; lpcchName
0x18001ada2  mov     r8, r14; lpName
0x18001ada5  mov     edx, r12d; dwIndex
0x18001ada8  mov     rcx, [rbp+47h+hKey]; hKey
0x18001adac  call    cs:__imp_RegEnumKeyExW
0x18001adb2  mov     ebx, eax
0x18001adb4  test    eax, eax
0x18001adb6  jle     short loc_18001ADC1
0x18001adb8  movzx   ebx, ax
0x18001adbb  or      ebx, 80070000h
0x18001adc1  cmp     ebx, esi
0x18001adc3  jz      loc_18001AFDF
0x18001adc9  test    ebx, ebx
0x18001adcb  js      loc_18001AFD8
0x18001add1  mov     rax, [rbp+47h+arg_0]
0x18001add5  cmp     dword ptr [rax], 1
0x18001add8  jnz     loc_18001AEDF
0x18001adde  xor     ebx, ebx
0x18001ade0  mov     [rbp+47h+var_C0], bl
0x18001ade3  lea     r8, [rbp+47h+var_C0]; bool *
0x18001ade7  mov     rdx, r14; unsigned __int16 *
0x18001adea  call    ?OpenKeyAndVerifyCertExists@@YAJ_NPEBGPEA_N@Z; OpenKeyAndVerifyCertExists(bool,ushort const *,bool *)
0x18001adef  test    eax, eax
0x18001adf1  jns     short loc_18001AE08
0x18001adf3  cmp     [rbp+47h+var_C0], bl
0x18001adf6  jz      loc_18001AF21
0x18001adfc  mov     rax, [rbp+47h+arg_10]
0x18001ae00  mov     byte ptr [rax], 1
0x18001ae03  jmp     loc_18001AF21
0x18001ae08  cmp     [rbp+47h+arg_18], bl
0x18001ae0b  jz      loc_18001AF9B
0x18001ae11  mov     [rbp+47h+var_98], rbx
0x18001ae15  xor     edx, edx
0x18001ae17  lea     rcx, [rbp+47h+var_98]
0x18001ae1b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001ae20  lea     r9, [rbp+47h+var_98]; unsigned __int16 *
0x18001ae24  lea     r8, aPregenkeysClai; "PregenKeys\\ClaimedAIK"
0x18001ae2b  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001ae30  mov     ebx, eax
0x18001ae32  test    eax, eax
0x18001ae34  js      loc_18001AF69
0x18001ae3a  mov     [rbp+47h+var_A8], 0
0x18001ae42  xor     edx, edx
0x18001ae44  lea     rcx, [rbp+47h+var_A8]
0x18001ae48  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001ae4d  lea     r9, [rbp+47h+var_A8]; unsigned __int16 *
0x18001ae51  mov     r8, r14; unsigned __int16 *
0x18001ae54  lea     rdx, asc_18002A2B8; "\\"
0x18001ae5b  mov     rcx, [rbp+47h+var_98]; this
0x18001ae5f  call    ?CombineSeparateStrings@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::CombineSeparateStrings(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001ae64  mov     ebx, eax
0x18001ae66  test    eax, eax
0x18001ae68  js      loc_18001AF49
0x18001ae6e  xor     ebx, ebx
0x18001ae70  mov     [rbp+47h+var_88], rbx
0x18001ae74  lea     rcx, [rbp+47h+var_88]
0x18001ae78  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18001ae7d  mov     [rsp+40h], rbx; lpdwDisposition
0x18001ae82  mov     [rsp+110h+lpftLastWriteTime], rax; phkResult
0x18001ae87  mov     [rsp+110h+lpcchClass], rbx; lpSecurityAttributes
0x18001ae8c  mov     dword ptr [rsp+110h+lpClass], 2001Fh; samDesired
0x18001ae94  mov     dword ptr [rsp+110h+phkResult], ebx; int
0x18001ae98  xor     r9d, r9d; lpClass
0x18001ae9b  xor     r8d, r8d; Reserved
0x18001ae9e  mov     rdx, [rbp+47h+var_A8]; lpSubKey
0x18001aea2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001aea9  call    cs:__imp_RegCreateKeyExW
0x18001aeaf  mov     ebx, eax
0x18001aeb1  test    eax, eax
0x18001aeb3  jle     short loc_18001AEBE
0x18001aeb5  movzx   ebx, ax
0x18001aeb8  or      ebx, 80070000h
0x18001aebe  test    ebx, ebx
0x18001aec0  js      short loc_18001AF29
0x18001aec2  lea     rcx, [rbp+47h+var_88]
0x18001aec6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001aecb  nop
0x18001aecc  lea     rcx, [rbp+47h+var_A8]
0x18001aed0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001aed5  nop
0x18001aed6  lea     rcx, [rbp+47h+var_98]
0x18001aeda  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001aedf  xor     ebx, ebx
0x18001aee1  cmp     [rbp+47h+arg_18], bl
0x18001aee4  jz      loc_18001AF9B
0x18001aeea  xor     r9d, r9d; Reserved
0x18001aeed  xor     r8d, r8d; samDesired
0x18001aef0  mov     rdx, r14; lpSubKey
0x18001aef3  mov     rcx, [rbp+47h+hKey]; hKey
0x18001aef7  call    cs:__imp_RegDeleteKeyExW
0x18001aefd  test    eax, eax
0x18001aeff  jle     short loc_18001AF0B
0x18001af01  movzx   eax, ax
0x18001af04  or      eax, 80070000h
0x18001af09  test    eax, eax
0x18001af0b  jns     short loc_18001AF8C
0x18001af0d  mov     rcx, [rbp+4Fh]; this
0x18001af11  mov     r9d, eax; char *
0x18001af14  mov     r8, rdi; unsigned int
0x18001af17  mov     edx, 1EBh; void *
0x18001af1c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001af21  inc     r12d
0x18001af24  jmp     loc_18001AD86
0x18001af29  mov     rcx, [rbp+4Fh]; this
0x18001af2d  mov     r9d, ebx; char *
0x18001af30  mov     r8, rdi; unsigned int
0x18001af33  mov     edx, 1DCh; void *
0x18001af38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001af3d  nop
0x18001af3e  lea     rcx, [rbp+47h+var_88]
0x18001af42  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001af47  jmp     short loc_18001AF5E
0x18001af49  mov     rcx, [rbp+4Fh]; this
0x18001af4d  mov     r9d, eax; char *
0x18001af50  mov     r8, rdi; unsigned int
0x18001af53  mov     edx, 1D0h; void *
0x18001af58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001af5d  nop
0x18001af5e  lea     rcx, [rbp+47h+var_A8]
0x18001af62  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
  ... truncated ...
```
