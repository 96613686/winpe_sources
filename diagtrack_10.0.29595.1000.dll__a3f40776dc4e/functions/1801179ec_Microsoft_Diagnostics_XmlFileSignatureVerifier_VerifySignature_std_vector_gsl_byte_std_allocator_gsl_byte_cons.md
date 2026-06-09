# Microsoft::Diagnostics::XmlFileSignatureVerifier::VerifySignature(std::vector<gsl::byte,std::allocator<gsl::byte>> const &,_FILETIME)

- ea: `0x1801179ec`
- end: `0x18011835a`
- name: `?VerifySignature@XmlFileSignatureVerifier@Diagnostics@Microsoft@@CAJAEBV?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@U_FILETIME@@@Z`
- size: `2414`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180117564`

## callees

- `0x180064e6c`
- `0x180064e8c`
- `0x18008abf4`
- `0x1801179ec`
- `0x180118360`
- `0x180118480`
- `0x18011859c`
- `0x180118728`
- `0x180118754`
- `0x1801dc37c`
- `0x18020aac0`
- `0x180369010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117b76`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117bda`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117c24`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117c6f`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117cbd`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117d22`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117da5`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117e1a`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117eae`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117f42`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117fc7`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180118034`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1801180c0`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180118142`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1801181d9`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180118250`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1801182b2`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180118303`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18011830a`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180118311`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117b76`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117bda`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117c24`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117c6f`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117cbd`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117d22`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117da5`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117e1a`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117eae`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117f42`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180117fc7`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180118034`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1801180c0`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180118142`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1801181d9`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180118250`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1801182b2`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180118303`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18011830a`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180118311`
- `CRYPT32!CertFreeCertificateContext` at `0x180117de0`
- `CRYPT32!CertFreeCertificateContext` at `0x180117e76`
- `CRYPT32!CertFreeCertificateContext` at `0x180117f0a`
- `CRYPT32!CertFreeCertificateContext` at `0x1801181a1`
- `CRYPT32!CertFreeCertificateContext` at `0x1801182cc`
- `CRYPT32!CertFreeCertificateContext` at `0x180117de0`
- `CRYPT32!CertFreeCertificateContext` at `0x180117e76`
- `CRYPT32!CertFreeCertificateContext` at `0x180117f0a`
- `CRYPT32!CertFreeCertificateContext` at `0x1801181a1`
- `CRYPT32!CertFreeCertificateContext` at `0x1801182cc`
- `CRYPT32!CertCreateCertificateContext` at `0x180117d46`
- `CRYPT32!CertCreateCertificateContext` at `0x180117d46`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x180117e42`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x180117e42`
- `CRYPT32!CertCloseStore` at `0x180117cfb`
- `CRYPT32!CertCloseStore` at `0x180117df1`
- `CRYPT32!CertCloseStore` at `0x180117e87`
- `CRYPT32!CertCloseStore` at `0x180117f1b`
- `CRYPT32!CertCloseStore` at `0x1801181b2`
- `CRYPT32!CertCloseStore` at `0x1801182dd`
- `CRYPT32!CertCloseStore` at `0x180117cfb`
- `CRYPT32!CertCloseStore` at `0x180117df1`
- `CRYPT32!CertCloseStore` at `0x180117e87`
- `CRYPT32!CertCloseStore` at `0x180117f1b`
- `CRYPT32!CertCloseStore` at `0x1801181b2`
- `CRYPT32!CertCloseStore` at `0x1801182dd`
- `bcrypt!BCryptDestroyKey` at `0x180117e6c`
- `bcrypt!BCryptDestroyKey` at `0x180117f00`
- `bcrypt!BCryptDestroyKey` at `0x180118197`
- `bcrypt!BCryptDestroyKey` at `0x1801182c2`
- `bcrypt!BCryptDestroyKey` at `0x180117e6c`
- `bcrypt!BCryptDestroyKey` at `0x180117f00`
- `bcrypt!BCryptDestroyKey` at `0x180118197`
- `bcrypt!BCryptDestroyKey` at `0x1801182c2`

## string_xrefs

- `0x180117b42`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x180117bab`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x180117bf5`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x180117c48`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x180117c86`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x180117cde`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x180117d5c`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x180117dcb`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x180117e50`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x180117ee5`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x180117f77`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x180117fe4`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x180118070`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x1801180f1`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x18011817c`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x180118200`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x180118261`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x180118322`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
int __fastcall Microsoft::Diagnostics::XmlFileSignatureVerifier::VerifySignature(__int64 *a1, __int64 LastError)
{
  __int64 v4; // rcx
  int v5; // eax
  int v6; // edi
  int v8; // eax
  __int64 v9; // rax
  void (*v10)(void); // rax
  __int64 *v11; // rax
  __int64 v12; // r14
  const struct _CRYPT_XML_KEY_INFO *v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  PCCERT_CONTEXT CertificateContext; // rdi
  const char *v17; // r9
  struct _FILETIME v18; // r8
  int v19; // eax
  int v20; // esi
  const char *v21; // r9
  int v22; // eax
  int v23; // eax
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int *phKey; // [rsp+20h] [rbp-89h]
  __int64 v30; // [rsp+40h] [rbp-69h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+48h] [rbp-61h] BYREF
  HCERTSTORE hCertStore; // [rsp+50h] [rbp-59h] BYREF
  PCCERT_CONTEXT v33; // [rsp+58h] [rbp-51h] BYREF
  int v34; // [rsp+60h] [rbp-49h] BYREF
  __int64 v35; // [rsp+68h] [rbp-41h] BYREF
  __int64 v36; // [rsp+70h] [rbp-39h] BYREF
  __int64 v37; // [rsp+78h] [rbp-31h] BYREF
  int v38[2]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v39; // [rsp+88h] [rbp-21h]
  int v40; // [rsp+90h] [rbp-19h] BYREF
  int *v41; // [rsp+98h] [rbp-11h]
  int v42; // [rsp+A0h] [rbp-9h]
  __int64 *v43; // [rsp+A8h] [rbp-1h]
  char *v44; // [rsp+B0h] [rbp+7h]
  char v45; // [rsp+B8h] [rbp+Fh]
  __int64 v46; // [rsp+C0h] [rbp+17h] BYREF
  int v47; // [rsp+C8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  Microsoft::Diagnostics::OptionalApiHelper::LoadCryptXml((Microsoft::Diagnostics::OptionalApiHelper *)&byte_180462BF0);
  if ( !qword_180462DC0 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xDA,
             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
             (const char *)0x7F,
             (unsigned int)phKey);
  Microsoft::Diagnostics::OptionalApiHelper::LoadCryptXml((Microsoft::Diagnostics::OptionalApiHelper *)&byte_180462BF0);
  if ( !qword_180462DC8 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xDA,
             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
             (const char *)0x7F,
             (unsigned int)phKey);
  Microsoft::Diagnostics::OptionalApiHelper::LoadCryptXml((Microsoft::Diagnostics::OptionalApiHelper *)&byte_180462BF0);
  if ( !qword_180462DD0 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xDA,
             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
             (const char *)0x7F,
             (unsigned int)phKey);
  Microsoft::Diagnostics::OptionalApiHelper::LoadCryptXml((Microsoft::Diagnostics::OptionalApiHelper *)&byte_180462BF0);
  if ( !qword_180462DD8 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xDA,
             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
             (const char *)0x7F,
             (unsigned int)phKey);
  Microsoft::Diagnostics::OptionalApiHelper::LoadCryptXml((Microsoft::Diagnostics::OptionalApiHelper *)&byte_180462BF0);
  if ( !qword_180462DE0 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xDA,
             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
             (const char *)0x7F,
             (unsigned int)phKey);
  Microsoft::Diagnostics::OptionalApiHelper::LoadCryptXml((Microsoft::Diagnostics::OptionalApiHelper *)&byte_180462BF0);
  if ( !qword_180462DE8 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xDA,
             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
             (const char *)0x7F,
             (unsigned int)phKey);
  Microsoft::Diagnostics::OptionalApiHelper::LoadCryptXml((Microsoft::Diagnostics::OptionalApiHelper *)&byte_180462BF0);
  if ( !qword_180462DF0 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xDA,
             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
             (const char *)0x7F,
             (unsigned int)phKey);
  v34 = 1;
  v40 = 3;
  v41 = &v34;
  v42 = 4;
  v38[0] = 0;
  v4 = *a1;
  v38[1] = *((_DWORD *)a1 + 2) - *a1;
  v39 = v4;
  v30 = 0;
  v43 = &v30;
  v44 = &byte_180462BF0;
  v45 = 1;
  if ( qword_180462DC8 )
  {
    phKey = v38;
    v5 = qword_180462DC8(0, 0x10000000, &v40, 1);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF8,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
        (const char *)(unsigned int)v5,
        (int)v38);
      if ( !v30 )
        return v6;
      if ( qword_180462DC0 )
      {
        qword_180462DC0();
        return v6;
      }
      _o_terminate();
    }
    v35 = 0;
    if ( qword_180462DD0 )
    {
      v8 = qword_180462DD0(v30, &v35);
      v6 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
          (const char *)(unsigned int)v8,
          (int)phKey);
        if ( !v30 )
          return v6;
        if ( qword_180462DC0 )
        {
          qword_180462DC0();
          return v6;
        }
        _o_terminate();
      }
      v9 = v35;
      if ( *(_DWORD *)(v35 + 24) != 1 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFC,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
          (const char *)0x8007000DLL,
          (int)phKey);
        if ( !v30 )
          return -2147024883;
        v10 = (void (*)(void))qword_180462DC0;
        if ( qword_180462DC0 )
          goto LABEL_33;
        v9 = _o_terminate();
      }
      v11 = *(__int64 **)(v9 + 32);
      v12 = *v11;
      v13 = *(const struct _CRYPT_XML_KEY_INFO **)(*v11 + 152);
      if ( v13 )
      {
LABEL_30:
        if ( v13->cKeyInfo )
        {
LABEL_36:
          hCertStore = 0;
          v14 = Microsoft::Diagnostics::XmlFileSignatureVerifier::GenerateCertificateStoreFromKeyInfo(v13, &hCertStore);
          v6 = v14;
          if ( v14 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x104,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
              (const char *)(unsigned int)v14,
              (int)phKey);
            if ( hCertStore )
              CertCloseStore(hCertStore, 0);
            if ( !v30 )
              return v6;
            if ( qword_180462DC0 )
            {
              qword_180462DC0();
              return v6;
            }
            _o_terminate();
          }
          v15 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v12 + 152) + 24LL) + 144LL);
          CertificateContext = CertCreateCertificateContext(1u, *(const BYTE **)(v15 + 16), *(_DWORD *)(v15 + 8));
          v33 = CertificateContext;
          if ( !CertificateContext )
          {
            LastError = (unsigned int)wil::details::in1diag3::Return_GetLastError(
                                        retaddr,
                                        (void *)0x10B,
                                        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
                                        v17);
            wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v33);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hCertStore);
            if ( !v30 )
              return LastError;
            if ( qword_180462DC0 )
            {
              qword_180462DC0();
              return LastError;
            }
            _o_terminate();
          }
          v18 = (struct _FILETIME)LastError;
          LastError = (__int64)hCertStore;
          v19 = Microsoft::Diagnostics::XmlFileSignatureVerifier::ValidateCertificateChain(
                  CertificateContext,
                  hCertStore,
                  v18);
          v20 = v19;
          if ( v19 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x10C,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
              (const char *)(unsigned int)v19,
              (int)phKey);
            CertFreeCertificateContext(CertificateContext);
            if ( LastError )
              CertCloseStore((HCERTSTORE)LastError, 0);
            if ( !v30 )
              return v20;
            if ( qword_180462DC0 )
            {
              qword_180462DC0();
              return v20;
            }
            _o_terminate();
          }
          hKey = 0;
          if ( !CryptImportPublicKeyInfoEx2(
                  1u,
                  &CertificateContext->pCertInfo->SubjectPublicKeyInfo,
                  0x80000000,
                  0,
                  &hKey) )
          {
            v20 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x115,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
                    v21);
            if ( hKey )
              BCryptDestroyKey(hKey);
            CertFreeCertificateContext(CertificateContext);
            if ( LastError )
              CertCloseStore((HCERTSTORE)LastError, 0);
            if ( !v30 )
              return v20;
            if ( qword_180462DC0 )
            {
              qword_180462DC0();
              return v20;
            }
            _o_terminate();
          }
          if ( qword_180462DD8 )
          {
            v22 = qword_180462DD8(*(_QWORD *)(v12 + 8), hKey, 0x10000000);
            v20 = v22;
            if ( v22 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x118,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
                (const char *)(unsigned int)v22,
                (int)phKey);
              if ( hKey )
                BCryptDestroyKey(hKey);
              CertFreeCertificateContext(CertificateContext);
              if ( LastError )
                CertCloseStore((HCERTSTORE)LastError, 0);
              if ( !v30 )
                return v20;
              if ( qword_180462DC0 )
              {
                qword_180462DC0();
                return v20;
              }
              _o_terminate();
            }
            v36 = 0;
            if ( qword_180462DE0 )
            {
              v23 = qword_180462DE0(*(_QWORD *)(v12 + 8), &v36);
              v20 = v23;
              if ( v23 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x11C,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
                  (const char *)(unsigned int)v23,
                  (int)phKey);
                wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
                wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v33);
                __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hCertStore);
                if ( !v30 )
                  return v20;
                if ( qword_180462DC0 )
                {
                  qword_180462DC0();
                  return v20;
                }
                _o_terminate();
              }
              v24 = v36;
              if ( *(_DWORD *)(v36 + 104) != 1 )
              {
                LastError = 2147944190LL;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x11D,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
                  (const char *)0x800706FELL,
                  (int)phKey);
                wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
                wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v33);
                __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hCertStore);
                if ( !v30 )
                  return LastError;
                if ( qword_180462DC0 )
                {
                  qword_180462DC0();
                  return LastError;
                }
                _o_terminate();
              }
              v37 = 0;
              if ( qword_180462DE8 )
              {
                v25 = qword_180462DE8(*(_QWORD *)(**(_QWORD **)(v24 + 112) + 8LL), &v37);
                v20 = v25;
                if ( v25 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x124,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
                    (const char *)(unsigned int)v25,
                    (int)phKey);
                  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
                  wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v33);
                  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hCertStore);
                  if ( !v30 )
                    return v20;
                  if ( qword_180462DC0 )
                  {
                    qword_180462DC0();
                    return v20;
                  }
                  _o_terminate();
                }
                v26 = *(_QWORD *)(v37 + 24);
                if ( v26 )
                {
                  v27 = -1;
                  do
                    ++v27;
                  while ( *(_WORD *)(v26 + 2 * v27) );
                  if ( v27 )
                  {
                    LastError = (unsigned int)wil::details::in1diag3::Return_Win32(
                                                retaddr,
                                                (void *)0x127,
                                                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesig"
                                                              "natureverifier.cpp",
                                                (const char *)0x6FE,
                                                (unsigned int)phKey);
                    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
                    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v33);
                    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hCertStore);
                    if ( !v30 )
                      return LastError;
                    if ( qword_180462DC0 )
                    {
                      qword_180462DC0();
                      return LastError;
                    }
                    _o_terminate();
                  }
                }
                v46 = 0;
                v47 = 0;
                if ( qword_180462DF0 )
                {
                  v28 = qword_180462DF0(*(_QWORD *)(v12 + 8), &v46);
                  v20 = v28;
                  if ( v28 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x12B,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
                      (const char *)(unsigned int)v28,
                      (int)phKey);
                    if ( hKey )
                      BCryptDestroyKey(hKey);
                    CertFreeCertificateContext(CertificateContext);
                    if ( LastError )
                      CertCloseStore((HCERTSTORE)LastError, 0);
                    if ( !v30 )
                      return v20;
                    if ( qword_180462DC0 )
                    {
                      qword_180462DC0();
                      return v20;
                    }
                    _o_terminate();
                  }
                  if ( HIDWORD(v46) )
                  {
                    if ( (v46 & 0x200000000LL) == 0 && (v46 & 0x100000000LL) == 0 )
                    {
                      LODWORD(LastError) = -2147467259;
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x135,
                        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
                        (const char *)0x80004005LL,
                        (int)phKey);
                      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
                      wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v33);
                      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hCertStore);
                      if ( !v30 )
                        return LastError;
                      if ( qword_180462DC0 )
                      {
                        qword_180462DC0();
                        return LastError;
                      }
                      _o_terminate();
                    }
                    LastError = (unsigned int)wil::details::in1diag3::Return_Win32(
                                                retaddr,
                                                (void *)0x132,
                                                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesig"
                                                              "natureverifier.cpp",
                                                (const char *)0x6FE,
                                                (unsigned int)phKey);
                    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
                    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v33);
                    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hCertStore);
                    if ( !v30 )
                      return LastError;
                    if ( qword_180462DC0 )
                    {
                      qword_180462DC0();
                      return LastError;
                    }
                    _o_terminate();
                  }
                  if ( hKey )
                    BCryptDestroyKey(hKey);
                  CertFreeCertificateContext(CertificateContext);
                  if ( LastError )
                    CertCloseStore((HCERTSTORE)LastError, 0);
                  if ( !v30 )
                    return 0;
                  if ( qword_180462DC0 )
                  {
                    qword_180462DC0();
                    return 0;
                  }
                  _o_terminate();
                }
              }
            }
          }
          _o_terminate();
          goto LABEL_142;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x100,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
          (const char *)0x8007000DLL,
          (int)phKey);
        if ( v30 )
        {
          v10 = (void (*)(void))qword_180462DC0;
          if ( qword_180462DC0 )
            goto LABEL_33;
          _o_terminate();
          goto LABEL_36;
        }
        return -2147024883;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFF,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
        (const char *)0x8007000DLL,
        (int)phKey);
      if ( !v30 )
        return -2147024883;
      v10 = (void (*)(void))qword_180462DC0;
      if ( !qword_180462DC0 )
      {
        _o_terminate();
        goto LABEL_30;
      }
LABEL_33:
      v10();
      return -2147024883;
    }
  }
LABEL_142:
  _o_terminate();
  return wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xDA,
           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
           (const char *)0x7F,
           (unsigned int)phKey);
}

```

## disassembly

```asm
0x1801179ec  mov     [rsp-8+arg_10], rbx
0x1801179f1  mov     [rsp-8+arg_18], rsi
0x1801179f6  push    rbp
0x1801179f7  push    rdi
0x1801179f8  push    r12
0x1801179fa  push    r14
0x1801179fc  push    r15
0x1801179fe  lea     rbp, [rsp-37h]
0x180117a03  sub     rsp, 0E0h
0x180117a0a  mov     rax, cs:__security_cookie
0x180117a11  xor     rax, rsp
0x180117a14  mov     [rbp+57h+var_30], rax
0x180117a18  mov     rbx, rdx
0x180117a1b  mov     rdi, rcx
0x180117a1e  lea     rsi, byte_180462BF0
0x180117a25  mov     rcx, rsi; this
0x180117a28  call    ?LoadCryptXml@OptionalApiHelper@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::OptionalApiHelper::LoadCryptXml(void)
0x180117a2d  xor     r15d, r15d
0x180117a30  cmp     cs:qword_180462DC0, r15
0x180117a37  jz      loc_180118318
0x180117a3d  mov     rcx, rsi; this
0x180117a40  call    ?LoadCryptXml@OptionalApiHelper@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::OptionalApiHelper::LoadCryptXml(void)
0x180117a45  cmp     cs:qword_180462DC8, r15
0x180117a4c  jz      loc_180118318
0x180117a52  mov     rcx, rsi; this
0x180117a55  call    ?LoadCryptXml@OptionalApiHelper@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::OptionalApiHelper::LoadCryptXml(void)
0x180117a5a  cmp     cs:qword_180462DD0, r15
0x180117a61  jz      loc_180118318
0x180117a67  mov     rcx, rsi; this
0x180117a6a  call    ?LoadCryptXml@OptionalApiHelper@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::OptionalApiHelper::LoadCryptXml(void)
0x180117a6f  cmp     cs:qword_180462DD8, r15
0x180117a76  jz      loc_180118318
0x180117a7c  mov     rcx, rsi; this
0x180117a7f  call    ?LoadCryptXml@OptionalApiHelper@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::OptionalApiHelper::LoadCryptXml(void)
0x180117a84  cmp     cs:qword_180462DE0, r15
0x180117a8b  jz      loc_180118318
0x180117a91  mov     rcx, rsi; this
0x180117a94  call    ?LoadCryptXml@OptionalApiHelper@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::OptionalApiHelper::LoadCryptXml(void)
0x180117a99  cmp     cs:qword_180462DE8, r15
0x180117aa0  jz      loc_180118318
0x180117aa6  mov     rcx, rsi; this
0x180117aa9  call    ?LoadCryptXml@OptionalApiHelper@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::OptionalApiHelper::LoadCryptXml(void)
0x180117aae  cmp     cs:qword_180462DF0, r15
0x180117ab5  jz      loc_180118318
0x180117abb  lea     r12d, [r15+1]
0x180117abf  mov     [rbp+57h+var_A0], r12d
0x180117ac3  mov     [rbp+57h+var_70], 3
0x180117aca  lea     rax, [rbp+57h+var_A0]
0x180117ace  mov     [rbp+57h+var_68], rax
0x180117ad2  mov     [rbp+57h+var_60], 4
0x180117ad9  mov     [rbp+57h+var_80], r15d
0x180117add  mov     rcx, [rdi]
0x180117ae0  mov     eax, [rdi+8]
0x180117ae3  sub     eax, ecx
0x180117ae5  mov     [rbp+57h+var_7C], eax
0x180117ae8  mov     [rbp+57h+var_78], rcx
0x180117aec  mov     [rbp+57h+var_C0], r15
0x180117af0  lea     rax, [rbp+57h+var_C0]
0x180117af4  mov     [rbp+57h+var_58], rax
0x180117af8  mov     [rbp+57h+var_50], rsi
0x180117afc  mov     [rbp+57h+var_48], r12b
0x180117b00  mov     rax, cs:qword_180462DC8
0x180117b07  test    rax, rax
0x180117b0a  jz      loc_180118311
0x180117b10  lea     rcx, [rbp+57h+var_C0]
0x180117b14  mov     [rsp+100h+var_D8], rcx
0x180117b19  lea     rcx, [rbp+57h+var_80]
0x180117b1d  mov     [rsp+100h+phKey], rcx; int
0x180117b22  mov     r9d, r12d
0x180117b25  lea     r8, [rbp+57h+var_70]
0x180117b29  mov     edx, 10000000h
0x180117b2e  xor     ecx, ecx
0x180117b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117b35  mov     edi, eax
0x180117b37  test    eax, eax
0x180117b39  jns     short loc_180117B7D
0x180117b3b  mov     rcx, [rbp+5Fh]; this
0x180117b3f  mov     r9d, eax; char *
0x180117b42  lea     r8, aOnecoreBaseTel_211; "onecore\\base\\telemetry\\utc\\service"...
0x180117b49  mov     edx, 0F8h; void *
0x180117b4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117b53  nop
0x180117b54  mov     rcx, [rbp+57h+var_C0]
0x180117b58  test    rcx, rcx
0x180117b5b  jz      short loc_180117B6F
0x180117b5d  mov     rax, cs:qword_180462DC0
0x180117b64  test    rax, rax
0x180117b67  jz      short loc_180117B76
0x180117b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117b6e  nop
0x180117b6f  mov     eax, edi
0x180117b71  jmp     loc_180118332
0x180117b76  call    cs:__imp__o_terminate
0x180117b7c  nop
0x180117b7d  mov     [rbp+57h+var_98], r15
0x180117b81  mov     rax, cs:qword_180462DD0
0x180117b88  test    rax, rax
0x180117b8b  jz      loc_180118311
0x180117b91  lea     rdx, [rbp+57h+var_98]
0x180117b95  mov     rcx, [rbp+57h+var_C0]
0x180117b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117b9e  mov     edi, eax
0x180117ba0  test    eax, eax
0x180117ba2  jns     short loc_180117BE1
0x180117ba4  mov     rcx, [rbp+5Fh]; this
0x180117ba8  mov     r9d, eax; char *
0x180117bab  lea     r8, aOnecoreBaseTel_211; "onecore\\base\\telemetry\\utc\\service"...
0x180117bb2  mov     edx, 0FBh; void *
0x180117bb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117bbc  nop
0x180117bbd  mov     rcx, [rbp+57h+var_C0]
0x180117bc1  test    rcx, rcx
0x180117bc4  jz      short loc_180117BD8
0x180117bc6  mov     rax, cs:qword_180462DC0
0x180117bcd  test    rax, rax
0x180117bd0  jz      short loc_180117BDA
0x180117bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117bd7  nop
0x180117bd8  jmp     short loc_180117B6F
0x180117bda  call    cs:__imp__o_terminate
0x180117be0  nop
0x180117be1  mov     rax, [rbp+57h+var_98]
0x180117be5  cmp     [rax+18h], r12d
0x180117be9  jz      short loc_180117C2B
0x180117beb  mov     rcx, [rbp+5Fh]; this
0x180117bef  mov     r9d, 8007000Dh; char *
0x180117bf5  lea     r8, aOnecoreBaseTel_211; "onecore\\base\\telemetry\\utc\\service"...
0x180117bfc  mov     edx, 0FCh; void *
0x180117c01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117c06  nop
0x180117c07  mov     rcx, [rbp+57h+var_C0]
0x180117c0b  test    rcx, rcx
0x180117c0e  jz      loc_180117CB3
0x180117c14  mov     rax, cs:qword_180462DC0
0x180117c1b  test    rax, rax
0x180117c1e  jnz     loc_180117CAD
0x180117c24  call    cs:__imp__o_terminate
0x180117c2a  nop
0x180117c2b  mov     rax, [rax+20h]
0x180117c2f  mov     r14, [rax]
0x180117c32  mov     rcx, [r14+98h]
0x180117c39  test    rcx, rcx
0x180117c3c  jnz     short loc_180117C76
0x180117c3e  mov     rcx, [rbp+5Fh]; this
0x180117c42  mov     r9d, 8007000Dh; char *
0x180117c48  lea     r8, aOnecoreBaseTel_211; "onecore\\base\\telemetry\\utc\\service"...
0x180117c4f  mov     edx, 0FFh; void *
0x180117c54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117c59  nop
0x180117c5a  mov     rcx, [rbp+57h+var_C0]
0x180117c5e  test    rcx, rcx
0x180117c61  jz      short loc_180117CB3
0x180117c63  mov     rax, cs:qword_180462DC0
0x180117c6a  test    rax, rax
0x180117c6d  jnz     short loc_180117CAD
0x180117c6f  call    cs:__imp__o_terminate
0x180117c75  nop
0x180117c76  cmp     [rcx+10h], r15d
0x180117c7a  jnz     short loc_180117CC4
0x180117c7c  mov     rcx, [rbp+5Fh]; this
0x180117c80  mov     r9d, 8007000Dh; char *
0x180117c86  lea     r8, aOnecoreBaseTel_211; "onecore\\base\\telemetry\\utc\\service"...
0x180117c8d  mov     edx, 100h; void *
0x180117c92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117c97  nop
0x180117c98  mov     rcx, [rbp+57h+var_C0]
0x180117c9c  test    rcx, rcx
0x180117c9f  jz      short loc_180117CB3
0x180117ca1  mov     rax, cs:qword_180462DC0
0x180117ca8  test    rax, rax
0x180117cab  jz      short loc_180117CBD
0x180117cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117cb2  nop
0x180117cb3  mov     eax, 8007000Dh
0x180117cb8  jmp     loc_180118332
0x180117cbd  call    cs:__imp__o_terminate
0x180117cc3  nop
0x180117cc4  mov     [rbp+57h+hCertStore], r15
0x180117cc8  lea     rdx, [rbp+57h+hCertStore]; void **
0x180117ccc  call    ?GenerateCertificateStoreFromKeyInfo@XmlFileSignatureVerifier@Diagnostics@Microsoft@@CAJAEBU_CRYPT_XML_KEY_INFO@@PEAPEAX@Z; Microsoft::Diagnostics::XmlFileSignatureVerifier::GenerateCertificateStoreFromKeyInfo(_CRYPT_XML_KEY_INFO const &,void * *)
0x180117cd1  mov     edi, eax
0x180117cd3  test    eax, eax
0x180117cd5  jns     short loc_180117D29
0x180117cd7  mov     rcx, [rbp+5Fh]; this
0x180117cdb  mov     r9d, eax; char *
0x180117cde  lea     r8, aOnecoreBaseTel_211; "onecore\\base\\telemetry\\utc\\service"...
0x180117ce5  mov     edx, 104h; void *
0x180117cea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117cef  nop
0x180117cf0  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x180117cf4  test    rcx, rcx
0x180117cf7  jz      short loc_180117D02
0x180117cf9  xor     edx, edx; dwFlags
0x180117cfb  call    cs:__imp_CertCloseStore
0x180117d01  nop
0x180117d02  mov     rcx, [rbp+57h+var_C0]
0x180117d06  test    rcx, rcx
0x180117d09  jz      short loc_180117D1D
0x180117d0b  mov     rax, cs:qword_180462DC0
0x180117d12  test    rax, rax
0x180117d15  jz      short loc_180117D22
0x180117d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117d1c  nop
0x180117d1d  jmp     loc_180117B6F
0x180117d22  call    cs:__imp__o_terminate
0x180117d28  nop
0x180117d29  mov     rax, [r14+98h]
0x180117d30  mov     rcx, [rax+18h]
0x180117d34  mov     rdx, [rcx+90h]
0x180117d3b  mov     r8d, [rdx+8]; cbCertEncoded
0x180117d3f  mov     rdx, [rdx+10h]; pbCertEncoded
0x180117d43  mov     ecx, r12d; dwCertEncodingType
0x180117d46  call    cs:__imp_CertCreateCertificateContext
0x180117d4c  mov     rdi, rax
0x180117d4f  mov     [rbp+57h+var_A8], rax
0x180117d53  test    rax, rax
0x180117d56  jnz     short loc_180117DAC
0x180117d58  mov     rcx, [rbp+5Fh]; this
0x180117d5c  lea     r8, aOnecoreBaseTel_211; "onecore\\base\\telemetry\\utc\\service"...
0x180117d63  mov     edx, 10Bh; void *
0x180117d68  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180117d6d  mov     ebx, eax
0x180117d6f  lea     rcx, [rbp+57h+var_A8]
0x180117d73  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180117d78  nop
0x180117d79  lea     rcx, [rbp+57h+hCertStore]
0x180117d7d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180117d82  nop
0x180117d83  mov     rcx, [rbp+57h+var_C0]
0x180117d87  test    rcx, rcx
0x180117d8a  jz      short loc_180117D9E
0x180117d8c  mov     rax, cs:qword_180462DC0
0x180117d93  test    rax, rax
0x180117d96  jz      short loc_180117DA5
0x180117d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117d9d  nop
0x180117d9e  mov     eax, ebx
0x180117da0  jmp     loc_180118332
0x180117da5  call    cs:__imp__o_terminate
0x180117dab  nop
0x180117dac  mov     r8, rbx; struct _FILETIME
0x180117daf  mov     rbx, [rbp+57h+hCertStore]
0x180117db3  mov     rdx, rbx; hAdditionalStore
0x180117db6  mov     rcx, rdi; pCertContext
0x180117db9  call    ?ValidateCertificateChain@XmlFileSignatureVerifier@Diagnostics@Microsoft@@CAJAEBU_CERT_CONTEXT@@PEAXU_FILETIME@@@Z; Microsoft::Diagnostics::XmlFileSignatureVerifier::ValidateCertificateChain(_CERT_CONTEXT const &,void *,_FILETIME)
0x180117dbe  mov     esi, eax
0x180117dc0  test    eax, eax
0x180117dc2  jns     short loc_180117E21
0x180117dc4  mov     rcx, [rbp+5Fh]; this
0x180117dc8  mov     r9d, eax; char *
0x180117dcb  lea     r8, aOnecoreBaseTel_211; "onecore\\base\\telemetry\\utc\\service"...
0x180117dd2  mov     edx, 10Ch; void *
0x180117dd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117ddc  nop
0x180117ddd  mov     rcx, rdi; pCertContext
0x180117de0  call    cs:__imp_CertFreeCertificateContext
0x180117de6  nop
0x180117de7  test    rbx, rbx
0x180117dea  jz      short loc_180117DF8
0x180117dec  xor     edx, edx; dwFlags
0x180117dee  mov     rcx, rbx; hCertStore
0x180117df1  call    cs:__imp_CertCloseStore
0x180117df7  nop
0x180117df8  mov     rcx, [rbp+57h+var_C0]
0x180117dfc  test    rcx, rcx
0x180117dff  jz      short loc_180117E13
0x180117e01  mov     rax, cs:qword_180462DC0
0x180117e08  test    rax, rax
0x180117e0b  jz      short loc_180117E1A
0x180117e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117e12  nop
0x180117e13  mov     eax, esi
0x180117e15  jmp     loc_180118332
0x180117e1a  call    cs:__imp__o_terminate
0x180117e20  nop
0x180117e21  mov     [rbp+57h+hKey], r15
0x180117e25  mov     rdx, [rdi+18h]
0x180117e29  add     rdx, 60h ; '`'; pInfo
0x180117e2d  lea     rax, [rbp+57h+hKey]
0x180117e31  mov     [rsp+100h+phKey], rax; unsigned int
0x180117e36  xor     r9d, r9d; pvAuxInfo
0x180117e39  mov     r8d, 80000000h; dwFlags
0x180117e3f  mov     ecx, r12d; dwCertEncodingType
0x180117e42  call    cs:__imp_CryptImportPublicKeyInfoEx2
0x180117e48  test    eax, eax
0x180117e4a  jnz     short loc_180117EB5
0x180117e4c  mov     rcx, [rbp+5Fh]; this
0x180117e50  lea     r8, aOnecoreBaseTel_211; "onecore\\base\\telemetry\\utc\\service"...
0x180117e57  mov     edx, 115h; void *
0x180117e5c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180117e61  mov     esi, eax
0x180117e63  mov     rcx, [rbp+57h+hKey]; hKey
0x180117e67  test    rcx, rcx
0x180117e6a  jz      short loc_180117E73
0x180117e6c  call    cs:__imp_BCryptDestroyKey
0x180117e72  nop
0x180117e73  mov     rcx, rdi; pCertContext
0x180117e76  call    cs:__imp_CertFreeCertificateContext
0x180117e7c  nop
0x180117e7d  test    rbx, rbx
  ... truncated ...
```
