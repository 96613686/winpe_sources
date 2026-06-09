# CreateKeyAndAddToPool(_PregenParms const *)

- ea: `0x18001b0b4`
- end: `0x18001b69a`
- name: `?CreateKeyAndAddToPool@@YAJPEBU_PregenParms@@@Z`
- size: `1510`
- prototype: `__int64 __fastcall(const struct _PregenParms *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001c2f8`

## callees

- `0x18000b0dc`
- `0x18000b0fc`
- `0x18000dad8`
- `0x18000db5c`
- `0x18001069c`
- `0x18001070c`
- `0x180010730`
- `0x180011e48`
- `0x180013f9c`
- `0x1800148b4`
- `0x180014918`
- `0x180015030`
- `0x1800153f0`
- `0x18001737c`
- `0x18001a8a8`
- `0x18001b0b4`
- `0x18001ba2c`
- `0x180022ef4`
- `0x18002336c`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b3db`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b3db`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001b5e4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001b5e4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001b38a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001b407`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001b38a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001b407`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001b341`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001b341`
- `ncrypt!NCryptFinalizeKey` at `0x18001b3e7`
- `ncrypt!NCryptFinalizeKey` at `0x18001b3e7`
- `ncrypt!NCryptCreatePersistedKey` at `0x18001b1c7`
- `ncrypt!NCryptCreatePersistedKey` at `0x18001b1c7`
- `ncrypt!NCryptSetProperty` at `0x18001b3aa`
- `ncrypt!NCryptSetProperty` at `0x18001b427`
- `ncrypt!NCryptSetProperty` at `0x18001b3aa`
- `ncrypt!NCryptSetProperty` at `0x18001b427`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001b0e4`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001b0e4`

## string_xrefs

- `0x18001b39f`: `Security Descr`
- `0x18001b41c`: `Security Descr`
- `0x18001b0f7`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001b132`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001b186`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001b1db`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001b245`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001b2c0`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001b34f`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001b3c2`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001b470`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001b4f7`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001b580`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001b604`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
__int64 __fastcall CreateKeyAndAddToPool(const struct _PregenParms *a1)
{
  SECURITY_STATUS v2; // eax
  unsigned int LastError; // ebx
  unsigned __int16 **v4; // rdx
  int v5; // eax
  int v6; // eax
  struct _SECURITY_ATTRIBUTES *v7; // rbx
  SECURITY_STATUS v8; // eax
  unsigned int v9; // r9d
  int NgcStateSeparatedRegistryLocation; // r14d
  const unsigned __int16 *v11; // r8
  __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  const unsigned __int16 *v14; // r8
  int v15; // r9d
  int v16; // r12d
  unsigned int v17; // r15d
  int v18; // eax
  __int64 v19; // rdx
  const char *v20; // r9
  DWORD SecurityDescriptorLength; // eax
  SECURITY_STATUS v22; // eax
  DWORD v23; // eax
  const unsigned __int16 *v24; // rdx
  NgcUtils *v25; // rcx
  NgcUtils *v26; // rcx
  __int64 v27; // rdx
  const unsigned __int16 *v28; // rdx
  NgcUtils *v29; // rcx
  int v30; // eax
  unsigned int v31; // esi
  int v32; // eax
  HKEY *v33; // rax
  LSTATUS Key; // eax
  unsigned __int16 **dwLegacyKeySpec; // [rsp+20h] [rbp-69h]
  DWORD dwLegacyKeySpeca; // [rsp+20h] [rbp-69h]
  unsigned __int16 *dwLegacyKeySpecb; // [rsp+20h] [rbp-69h]
  DWORD dwLegacyKeySpecc; // [rsp+20h] [rbp-69h]
  DWORD dwLegacyKeySpecd; // [rsp+20h] [rbp-69h]
  unsigned __int8 *lpSecurityAttributes; // [rsp+30h] [rbp-59h]
  unsigned int phkResult; // [rsp+38h] [rbp-51h]
  LPCWSTR pszKeyName; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v44[2]; // [rsp+58h] [rbp-31h] BYREF
  NCRYPT_KEY_HANDLE *p_phKey; // [rsp+60h] [rbp-29h] BYREF
  __int16 v46; // [rsp+68h] [rbp-21h]
  LPCWSTR lpSubKey; // [rsp+70h] [rbp-19h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+78h] [rbp-11h] BYREF
  __int64 v49; // [rsp+80h] [rbp-9h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+88h] [rbp-1h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+90h] [rbp+7h] BYREF
  unsigned int *v52; // [rsp+98h] [rbp+Fh] BYREF
  unsigned __int8 *v53; // [rsp+A0h] [rbp+17h] BYREF
  char v54; // [rsp+A8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  HKEY v56; // [rsp+F8h] [rbp+6Fh] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+100h] [rbp+77h] BYREF
  unsigned __int16 *v58; // [rsp+108h] [rbp+7Fh] BYREF

  phProvider = 0;
  v2 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  LastError = v2;
  if ( v2 >= 0 )
  {
    v58 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v58,
      0);
    v5 = NgcUtils::GenRandomGuid((NgcUtils *)&v58, v4);
    LastError = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x533,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)v5,
        (int)dwLegacyKeySpec);
LABEL_5:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
      goto LABEL_56;
    }
    pszKeyName = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pszKeyName,
      0);
    v6 = NgcUtils::CombineSeparateStrings(
           *((NgcUtils **)a1 + 2),
           L"-",
           v58,
           (const unsigned __int16 *)&pszKeyName,
           dwLegacyKeySpec);
    LastError = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53A,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)v6,
        dwLegacyKeySpeca);
LABEL_8:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
      goto LABEL_5;
    }
    v7 = (struct _SECURITY_ATTRIBUTES *)pszKeyName;
    phKey = 0;
    v8 = NCryptCreatePersistedKey(phProvider, &phKey, L"RSA", pszKeyName, 0, 0);
    NgcStateSeparatedRegistryLocation = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x543,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)v8,
        (int)dwLegacyKeySpecb);
LABEL_11:
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
      LastError = NgcStateSeparatedRegistryLocation;
      goto LABEL_56;
    }
    p_phKey = &phKey;
    v46 = 256;
    v11 = (const unsigned __int16 *)*((unsigned int *)a1 + 1);
    if ( (_DWORD)v11 )
    {
      NgcStateSeparatedRegistryLocation = NgcUtils::SetNCryptDwordProperty(
                                            (NgcUtils *)phKey,
                                            (unsigned __int64)L"PCP_KEY_USAGE_POLICY",
                                            v11,
                                            v9);
      if ( NgcStateSeparatedRegistryLocation < 0 )
      {
        v12 = 1375;
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
          (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
          (int)dwLegacyKeySpecb);
LABEL_16:
        wil::details::ScopeExitFnGuard__lambda_28030fa6131f545f18ddbcdce04591c4___::operator()(&p_phKey);
        goto LABEL_11;
      }
    }
    NgcStateSeparatedRegistryLocation = NgcUtils::SetNCryptDwordProperty(
                                          (NgcUtils *)phKey,
                                          (unsigned __int64)L"Length",
                                          (const unsigned __int16 *)0x800,
                                          v9);
    if ( NgcStateSeparatedRegistryLocation < 0 )
    {
      v12 = 1382;
      goto LABEL_15;
    }
    v16 = 0;
    LODWORD(v56) = 0;
    *(_QWORD *)v44 = 0;
    LOBYTE(v17) = 0;
    SecurityDescriptor = 0;
    if ( *((_QWORD *)a1 + 4) )
    {
      v18 = NgcUtils::SetNCryptBoolProperty((NgcUtils *)phKey, v13, v14, v15);
      NgcStateSeparatedRegistryLocation = v18;
      if ( v18 < 0 && v18 != -2146893783 )
      {
        v19 = 1396;
LABEL_23:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
          (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
          (int)dwLegacyKeySpecb);
LABEL_24:
        wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
          v44,
          0);
        goto LABEL_16;
      }
      v52 = v44;
      v53 = 0;
      v54 = 1;
      NgcStateSeparatedRegistryLocation = GenerateAndSetPin((NgcUtils *)phKey, &v53, (unsigned int *)&v56);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v52);
      if ( NgcStateSeparatedRegistryLocation < 0 )
      {
        v19 = 1403;
        goto LABEL_23;
      }
      v16 = (int)v56;
    }
    else if ( *(_DWORD *)a1 == 1 )
    {
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
              L"D:P(A;;GA;;;CO)(A;;GA;;;SY)(A;;GA;;;BA)(A;;GR;;;NS)",
              1u,
              &SecurityDescriptor,
              0) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x583,
                      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
                      v20);
        goto LABEL_31;
      }
      SecurityDescriptorLength = GetSecurityDescriptorLength(SecurityDescriptor);
      v22 = NCryptSetProperty(phKey, L"Security Descr", (PBYTE)SecurityDescriptor, SecurityDescriptorLength, 4u);
      v17 = (unsigned int)v22 >> 31;
      if ( v22 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x58D,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
          (const char *)(unsigned int)v22,
          (int)dwLegacyKeySpecb);
    }
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    NgcStateSeparatedRegistryLocation = NCryptFinalizeKey(phKey, 0);
    if ( NgcStateSeparatedRegistryLocation < 0 )
    {
      v19 = 1431;
      goto LABEL_23;
    }
    if ( (_BYTE)v17 )
    {
      v23 = GetSecurityDescriptorLength(SecurityDescriptor);
      NgcStateSeparatedRegistryLocation = NCryptSetProperty(
                                            phKey,
                                            L"Security Descr",
                                            (PBYTE)SecurityDescriptor,
                                            v23,
                                            4u);
      if ( NgcStateSeparatedRegistryLocation < 0 )
      {
        v19 = 1440;
        goto LABEL_23;
      }
    }
    if ( *((_QWORD *)a1 + 4) )
    {
      v56 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v56,
        0);
      NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                            v25,
                                            v24,
                                            *((const unsigned __int16 **)a1 + 5),
                                            (unsigned __int16 *)&v56);
      if ( NgcStateSeparatedRegistryLocation < 0 )
      {
        v27 = 1448;
LABEL_42:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
          (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
          (int)dwLegacyKeySpecb);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v56);
        goto LABEL_24;
      }
      LODWORD(lpSecurityAttributes) = v16;
      LODWORD(dwLegacyKeySpecb) = 3;
      NgcStateSeparatedRegistryLocation = NgcUtils::SetRegistryValue(
                                            v26,
                                            v56,
                                            0,
                                            v7,
                                            dwLegacyKeySpecb,
                                            v44[0],
                                            lpSecurityAttributes,
                                            phkResult);
      if ( NgcStateSeparatedRegistryLocation < 0 )
      {
        v27 = 1459;
        goto LABEL_42;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v56);
    }
    v56 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v56,
      0);
    v30 = NgcUtils::GetNgcStateSeparatedRegistryLocation(
            v29,
            v28,
            *((const unsigned __int16 **)a1 + 3),
            (unsigned __int16 *)&v56);
    v31 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B9,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)v30,
        (int)dwLegacyKeySpecb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v56);
      wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        v44,
        0);
      wil::details::ScopeExitFnGuard__lambda_28030fa6131f545f18ddbcdce04591c4___::operator()(&p_phKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
      LastError = v31;
      goto LABEL_56;
    }
    lpSubKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpSubKey,
      0);
    v32 = NgcUtils::CombineSeparateStrings(
            (NgcUtils *)v56,
            L"\\",
            (const unsigned __int16 *)v7,
            (const unsigned __int16 *)&lpSubKey,
            (unsigned __int16 **)dwLegacyKeySpecb);
    LastError = v32;
    if ( v32 >= 0 )
    {
      v49 = 0;
      v33 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v49);
      Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Fu, 0, v33, 0);
      LastError = Key;
      if ( Key > 0 )
        LastError = (unsigned __int16)Key | 0x80070000;
      if ( (LastError & 0x80000000) == 0 )
      {
        HIBYTE(v46) = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v49);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v56);
        wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
          v44,
          0);
        wil::details::ScopeExitFnGuard__lambda_28030fa6131f545f18ddbcdce04591c4___::operator()(&p_phKey);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
        LastError = 0;
        goto LABEL_56;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5CE,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)LastError,
        dwLegacyKeySpecd);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v49);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C2,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)v32,
        dwLegacyKeySpecc);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v56);
LABEL_31:
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(v44, 0);
    wil::details::ScopeExitFnGuard__lambda_28030fa6131f545f18ddbcdce04591c4___::operator()(&p_phKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    goto LABEL_8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x52E,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
    (const char *)(unsigned int)v2,
    (int)dwLegacyKeySpec);
LABEL_56:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
  return LastError;
}

```

## disassembly

```asm
0x18001b0b4  push    rbp
0x18001b0b6  push    rbx
0x18001b0b7  push    rsi
0x18001b0b8  push    r12
0x18001b0ba  push    r13
0x18001b0bc  push    r14
0x18001b0be  push    r15
0x18001b0c0  lea     rbp, [rsp-27h]
0x18001b0c5  sub     rsp, 0B0h
0x18001b0cc  mov     rsi, rcx
0x18001b0cf  xor     r13d, r13d
0x18001b0d2  mov     [rbp+57h+phProvider], r13
0x18001b0d6  xor     r8d, r8d; dwFlags
0x18001b0d9  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x18001b0e0  lea     rcx, [rbp+57h+phProvider]; phProvider
0x18001b0e4  call    cs:__imp_NCryptOpenStorageProvider
0x18001b0ea  mov     ebx, eax
0x18001b0ec  test    eax, eax
0x18001b0ee  jns     short loc_18001B10D
0x18001b0f0  mov     rcx, [rbp+5Fh]; this
0x18001b0f4  mov     r9d, eax; char *
0x18001b0f7  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001b0fe  mov     edx, 52Eh; void *
0x18001b103  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b108  jmp     loc_18001B67C
0x18001b10d  mov     [rbp+57h+arg_18], r13
0x18001b111  xor     edx, edx
0x18001b113  lea     rcx, [rbp+57h+arg_18]
0x18001b117  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001b11c  lea     rcx, [rbp+57h+arg_18]; this
0x18001b120  call    ?GenRandomGuid@NgcUtils@@YAJPEAPEAG@Z; NgcUtils::GenRandomGuid(ushort * *)
0x18001b125  mov     ebx, eax
0x18001b127  test    eax, eax
0x18001b129  jns     short loc_18001B152
0x18001b12b  mov     rcx, [rbp+5Fh]; this
0x18001b12f  mov     r9d, eax; char *
0x18001b132  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001b139  mov     edx, 533h; void *
0x18001b13e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b143  nop
0x18001b144  lea     rcx, [rbp+57h+arg_18]
0x18001b148  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b14d  jmp     loc_18001B67C
0x18001b152  mov     [rbp+57h+pszKeyName], r13
0x18001b156  xor     edx, edx
0x18001b158  lea     rcx, [rbp+57h+pszKeyName]
0x18001b15c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001b161  lea     r9, [rbp+57h+pszKeyName]; unsigned __int16 *
0x18001b165  mov     r8, [rbp+57h+arg_18]; unsigned __int16 *
0x18001b169  lea     rdx, asc_18002B344; "-"
0x18001b170  mov     rcx, [rsi+10h]; this
0x18001b174  call    ?CombineSeparateStrings@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::CombineSeparateStrings(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001b179  mov     ebx, eax
0x18001b17b  test    eax, eax
0x18001b17d  jns     short loc_18001B1A3
0x18001b17f  mov     rcx, [rbp+5Fh]; this
0x18001b183  mov     r9d, eax; char *
0x18001b186  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001b18d  mov     edx, 53Ah; void *
0x18001b192  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b197  nop
0x18001b198  lea     rcx, [rbp+57h+pszKeyName]
0x18001b19c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b1a1  jmp     short loc_18001B144
0x18001b1a3  mov     rbx, [rbp+57h+pszKeyName]
0x18001b1a7  mov     [rbp+57h+phKey], r13
0x18001b1ab  mov     [rsp+0E0h+dwFlags], r13d; dwFlags
0x18001b1b0  mov     dword ptr [rsp+0E0h+dwLegacyKeySpec], r13d; int
0x18001b1b5  mov     r9, rbx; pszKeyName
0x18001b1b8  lea     r8, pszAlgId; "RSA"
0x18001b1bf  lea     rdx, [rbp+57h+phKey]; phKey
0x18001b1c3  mov     rcx, [rbp+57h+phProvider]; hProvider
0x18001b1c7  call    cs:__imp_NCryptCreatePersistedKey
0x18001b1cd  mov     r14d, eax
0x18001b1d0  test    eax, eax
0x18001b1d2  jns     short loc_18001B212
0x18001b1d4  mov     rcx, [rbp+5Fh]; this
0x18001b1d8  mov     r9d, eax; char *
0x18001b1db  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001b1e2  mov     edx, 543h; void *
0x18001b1e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b1ec  nop
0x18001b1ed  lea     rcx, [rbp+57h+phKey]
0x18001b1f1  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001b1f6  nop
0x18001b1f7  lea     rcx, [rbp+57h+pszKeyName]
0x18001b1fb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b200  nop
0x18001b201  lea     rcx, [rbp+57h+arg_18]
0x18001b205  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b20a  mov     ebx, r14d
0x18001b20d  jmp     loc_18001B67C
0x18001b212  lea     rax, [rbp+57h+phKey]
0x18001b216  mov     [rbp+57h+var_80], rax
0x18001b21a  mov     [rbp+57h+var_78], 100h
0x18001b220  mov     r8d, [rsi+4]; unsigned __int16 *
0x18001b224  test    r8d, r8d
0x18001b227  jz      short loc_18001B264
0x18001b229  lea     rdx, aPcpKeyUsagePol; "PCP_KEY_USAGE_POLICY"
0x18001b230  mov     rcx, [rbp+57h+phKey]; this
0x18001b234  call    ?SetNCryptDwordProperty@NgcUtils@@YAJ_KPEBGK@Z; NgcUtils::SetNCryptDwordProperty(unsigned __int64,ushort const *,ulong)
0x18001b239  mov     r14d, eax
0x18001b23c  test    eax, eax
0x18001b23e  jns     short loc_18001B264
0x18001b240  mov     edx, 55Fh; void *
0x18001b245  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001b24c  mov     r9d, r14d; char *
0x18001b24f  mov     rcx, [rbp+5Fh]; this
0x18001b253  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b258  nop
0x18001b259  lea     rcx, [rbp+57h+var_80]
0x18001b25d  call    wil__details__ScopeExitFnGuard__lambda_28030fa6131f545f18ddbcdce04591c4_____operator__
0x18001b262  jmp     short loc_18001B1ED
0x18001b264  mov     r8d, 800h; unsigned __int16 *
0x18001b26a  lea     rdx, aLength; "Length"
0x18001b271  mov     rcx, [rbp+57h+phKey]; this
0x18001b275  call    ?SetNCryptDwordProperty@NgcUtils@@YAJ_KPEBGK@Z; NgcUtils::SetNCryptDwordProperty(unsigned __int64,ushort const *,ulong)
0x18001b27a  mov     r14d, eax
0x18001b27d  test    eax, eax
0x18001b27f  jns     short loc_18001B288
0x18001b281  mov     edx, 566h
0x18001b286  jmp     short loc_18001B245
0x18001b288  mov     r12d, r13d
0x18001b28b  mov     dword ptr [rbp+57h+arg_8], r13d
0x18001b28f  mov     qword ptr [rbp+57h+var_88], r13
0x18001b293  mov     r15b, r13b
0x18001b296  mov     [rbp+57h+SecurityDescriptor], r13
0x18001b29a  cmp     [rsi+20h], r13
0x18001b29e  jz      loc_18001B326
0x18001b2a4  mov     rcx, [rbp+57h+phKey]; this
0x18001b2a8  call    ?SetNCryptBoolProperty@NgcUtils@@YAJ_KPEBGH@Z; NgcUtils::SetNCryptBoolProperty(unsigned __int64,ushort const *,int)
0x18001b2ad  mov     r14d, eax
0x18001b2b0  test    eax, eax
0x18001b2b2  jns     short loc_18001B2E4
0x18001b2b4  cmp     eax, 80090029h
0x18001b2b9  jz      short loc_18001B2E4
0x18001b2bb  mov     edx, 574h; void *
0x18001b2c0  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001b2c7  mov     r9d, r14d; char *
0x18001b2ca  mov     rcx, [rbp+5Fh]; this
0x18001b2ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b2d3  nop
0x18001b2d4  xor     edx, edx
0x18001b2d6  lea     rcx, [rbp+57h+var_88]
0x18001b2da  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001b2df  jmp     loc_18001B259
0x18001b2e4  lea     rax, [rbp+57h+var_88]
0x18001b2e8  mov     [rbp+57h+var_48], rax
0x18001b2ec  mov     [rbp+57h+var_40], r13
0x18001b2f0  mov     [rbp+57h+var_38], 1
0x18001b2f4  lea     r8, [rbp+57h+arg_8]; unsigned int *
0x18001b2f8  lea     rdx, [rbp+57h+var_40]; unsigned __int8 **
0x18001b2fc  mov     rcx, [rbp+57h+phKey]; this
0x18001b300  call    ?GenerateAndSetPin@@YAJ_KPEAPEAEPEAK@Z; GenerateAndSetPin(unsigned __int64,uchar * *,ulong *)
0x18001b305  mov     r14d, eax
0x18001b308  lea     rcx, [rbp+57h+var_48]
0x18001b30c  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001b311  test    r14d, r14d
0x18001b314  jns     short loc_18001B31D
0x18001b316  mov     edx, 57Bh
0x18001b31b  jmp     short loc_18001B2C0
0x18001b31d  mov     r12d, dword ptr [rbp+57h+arg_8]
0x18001b321  jmp     loc_18001B3D3
0x18001b326  cmp     dword ptr [rsi], 1
0x18001b329  jnz     loc_18001B3D3
0x18001b32f  xor     r9d, r9d; SecurityDescriptorSize
0x18001b332  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18001b336  lea     edx, [r9+1]; StringSDRevision
0x18001b33a  lea     rcx, aDPAGaCoAGaSyAG; "D:P(A;;GA;;;CO)(A;;GA;;;SY)(A;;GA;;;BA)"...
0x18001b341  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001b347  test    eax, eax
0x18001b349  jnz     short loc_18001B386
0x18001b34b  mov     rcx, [rbp+5Fh]; this
0x18001b34f  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001b356  mov     edx, 583h; void *
0x18001b35b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001b360  mov     ebx, eax
0x18001b362  xor     edx, edx
0x18001b364  lea     rcx, [rbp+57h+var_88]
0x18001b368  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001b36d  nop
0x18001b36e  lea     rcx, [rbp+57h+var_80]
0x18001b372  call    wil__details__ScopeExitFnGuard__lambda_28030fa6131f545f18ddbcdce04591c4_____operator__
0x18001b377  nop
0x18001b378  lea     rcx, [rbp+57h+phKey]
0x18001b37c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001b381  jmp     loc_18001B198
0x18001b386  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18001b38a  call    cs:__imp_GetSecurityDescriptorLength
0x18001b390  mov     dword ptr [rsp+0E0h+dwLegacyKeySpec], 4; int
0x18001b398  mov     r9d, eax; cbInput
0x18001b39b  mov     r8, [rbp+57h+SecurityDescriptor]; pbInput
0x18001b39f  lea     rdx, aSecurityDescr; "Security Descr"
0x18001b3a6  mov     rcx, [rbp+57h+phKey]; hObject
0x18001b3aa  call    cs:__imp_NCryptSetProperty
0x18001b3b0  mov     r15d, eax
0x18001b3b3  shr     r15d, 1Fh
0x18001b3b7  mov     rcx, [rbp+5Fh]; this
0x18001b3bb  test    eax, eax
0x18001b3bd  jns     short loc_18001B3D3
0x18001b3bf  mov     r9d, eax; char *
0x18001b3c2  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001b3c9  mov     edx, 58Dh; void *
0x18001b3ce  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b3d3  mov     qword ptr [rbp+57h+PerformanceCount], r13
0x18001b3d7  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x18001b3db  call    cs:__imp_QueryPerformanceCounter
0x18001b3e1  xor     edx, edx; dwFlags
0x18001b3e3  mov     rcx, [rbp+57h+phKey]; hKey
0x18001b3e7  call    cs:__imp_NCryptFinalizeKey
0x18001b3ed  mov     r14d, eax
0x18001b3f0  test    eax, eax
0x18001b3f2  jns     short loc_18001B3FE
0x18001b3f4  mov     edx, 597h
0x18001b3f9  jmp     loc_18001B2C0
0x18001b3fe  test    r15b, r15b
0x18001b401  jz      short loc_18001B43E
0x18001b403  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18001b407  call    cs:__imp_GetSecurityDescriptorLength
0x18001b40d  mov     dword ptr [rsp+0E0h+dwLegacyKeySpec], 4; dwFlags
0x18001b415  mov     r9d, eax; cbInput
0x18001b418  mov     r8, [rbp+57h+SecurityDescriptor]; pbInput
0x18001b41c  lea     rdx, aSecurityDescr; "Security Descr"
0x18001b423  mov     rcx, [rbp+57h+phKey]; hObject
0x18001b427  call    cs:__imp_NCryptSetProperty
0x18001b42d  mov     r14d, eax
0x18001b430  test    eax, eax
0x18001b432  jns     short loc_18001B43E
0x18001b434  mov     edx, 5A0h
0x18001b439  jmp     loc_18001B2C0
0x18001b43e  cmp     [rsi+20h], r13
0x18001b442  jz      loc_18001B4CE
0x18001b448  mov     [rbp+57h+arg_8], r13
0x18001b44c  xor     edx, edx
0x18001b44e  lea     rcx, [rbp+57h+arg_8]
0x18001b452  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001b457  lea     r9, [rbp+57h+arg_8]; unsigned __int16 *
0x18001b45b  mov     r8, [rsi+28h]; unsigned __int16 *
0x18001b45f  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001b464  mov     r14d, eax
0x18001b467  test    eax, eax
0x18001b469  jns     short loc_18001B492
0x18001b46b  mov     edx, 5A8h; void *
0x18001b470  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001b477  mov     r9d, r14d; char *
0x18001b47a  mov     rcx, [rbp+5Fh]; this
0x18001b47e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b483  nop
0x18001b484  lea     rcx, [rbp+57h+arg_8]
0x18001b488  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b48d  jmp     loc_18001B2D4
0x18001b492  mov     rax, qword ptr [rbp+57h+var_88]
0x18001b496  mov     dword ptr [rsp+0E0h+lpSecurityAttributes], r12d; unsigned __int8 *
0x18001b49b  mov     qword ptr [rsp+0E0h+dwFlags], rax; unsigned int
0x18001b4a0  mov     dword ptr [rsp+0E0h+dwLegacyKeySpec], 3; int
0x18001b4a8  mov     r9, rbx; struct _SECURITY_ATTRIBUTES *
0x18001b4ab  xor     r8d, r8d; unsigned __int16 *
0x18001b4ae  mov     rdx, [rbp+57h+arg_8]; HKEY
0x18001b4b2  call    ?SetRegistryValue@NgcUtils@@YAJPEAUHKEY__@@PEBGPEAU_SECURITY_ATTRIBUTES@@1KPEAEK@Z; NgcUtils::SetRegistryValue(HKEY__ *,ushort const *,_SECURITY_ATTRIBUTES *,ushort const *,ulong,uchar *,ulong)
0x18001b4b7  mov     r14d, eax
0x18001b4ba  test    eax, eax
0x18001b4bc  jns     short loc_18001B4C5
0x18001b4be  mov     edx, 5B3h
0x18001b4c3  jmp     short loc_18001B470
0x18001b4c5  lea     rcx, [rbp+57h+arg_8]
0x18001b4c9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b4ce  mov     [rbp+57h+arg_8], r13
0x18001b4d2  xor     edx, edx
0x18001b4d4  lea     rcx, [rbp+57h+arg_8]
0x18001b4d8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001b4dd  lea     r9, [rbp+57h+arg_8]; unsigned __int16 *
0x18001b4e1  mov     r8, [rsi+18h]; unsigned __int16 *
0x18001b4e5  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001b4ea  mov     esi, eax
0x18001b4ec  test    eax, eax
0x18001b4ee  jns     short loc_18001B54D
0x18001b4f0  mov     rcx, [rbp+5Fh]; this
0x18001b4f4  mov     r9d, eax; char *
0x18001b4f7  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001b4fe  mov     edx, 5B9h; void *
0x18001b503  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b508  nop
0x18001b509  lea     rcx, [rbp+57h+arg_8]
0x18001b50d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b512  nop
0x18001b513  xor     edx, edx
0x18001b515  lea     rcx, [rbp+57h+var_88]
0x18001b519  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001b51e  nop
0x18001b51f  lea     rcx, [rbp+57h+var_80]
0x18001b523  call    wil__details__ScopeExitFnGuard__lambda_28030fa6131f545f18ddbcdce04591c4_____operator__
0x18001b528  nop
0x18001b529  lea     rcx, [rbp+57h+phKey]
0x18001b52d  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001b532  nop
0x18001b533  lea     rcx, [rbp+57h+pszKeyName]
0x18001b537  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b53c  nop
0x18001b53d  lea     rcx, [rbp+57h+arg_18]
0x18001b541  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
  ... truncated ...
```
