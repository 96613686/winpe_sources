# RegistrationCertHelper::VerifyDeviceJoinAutoSigningCert(ushort const *,_BYTE_ARRAY const *,unsigned __int64,int *)

- ea: `0x18005e84c`
- end: `0x18005ebe2`
- name: `?VerifyDeviceJoinAutoSigningCert@RegistrationCertHelper@@QEAAJPEBGPEBU_BYTE_ARRAY@@_KPEAH@Z`
- size: `918`
- prototype: `__int64 __fastcall(RegistrationCertHelper *__hidden this, const unsigned __int16 *, const struct _BYTE_ARRAY *, unsigned __int64, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18005b078`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x180009780`
- `0x18000bac0`
- `0x180012948`
- `0x180012cf0`
- `0x1800307c4`
- `0x18003334c`
- `0x18005b348`
- `0x18005e84c`
- `0x180076658`
- `0x18007683c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e9ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ea40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eadc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e9ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ea40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eadc`
- `CRYPT32!CertComparePublicKeyInfo` at `0x18005eb11`
- `CRYPT32!CertComparePublicKeyInfo` at `0x18005eb11`
- `CRYPT32!CertOpenStore` at `0x18005ea32`
- `CRYPT32!CertOpenStore` at `0x18005ea32`
- `CRYPT32!CertCloseStore` at `0x18005eb7b`
- `CRYPT32!CertCloseStore` at `0x18005eb7b`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x18005e9a1`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x18005ea12`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x18005e9a1`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x18005ea12`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18005ead2`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18005ead2`
- `CRYPT32!CertFreeCertificateContext` at `0x18005ea9e`
- `CRYPT32!CertFreeCertificateContext` at `0x18005eb6d`
- `CRYPT32!CertFreeCertificateContext` at `0x18005ea9e`
- `CRYPT32!CertFreeCertificateContext` at `0x18005eb6d`
- `ncrypt!NCryptFreeObject` at `0x18005eb5b`
- `ncrypt!NCryptFreeObject` at `0x18005eb5b`

## string_xrefs

- `0x18005ea4f`: `CertOpenStore`
- `0x18005e9be`: `%s: Cannot get local public key with name %s. CryptExportPublicKeyInfo failed with win32 error code: 0x%08x. Assuming local key does not match key in the directory...`
- `0x18005eaef`: `%s: Cannot decode the auto signing certificate at index %d from the directory. CertAddEncodedCertificateToStore failed with error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall RegistrationCertHelper::VerifyDeviceJoinAutoSigningCert(
        RegistrationCertHelper *this,
        const unsigned __int16 *a2,
        const struct _BYTE_ARRAY *a3,
        unsigned __int64 a4,
        int *a5)
{
  int *v5; // r12
  struct _CERT_PUBLIC_KEY_INFO *v6; // r15
  HCERTSTORE v7; // r13
  unsigned int v8; // edi
  unsigned __int64 v9; // r14
  unsigned int v11; // ebx
  const unsigned __int16 *v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  char IsEnabled; // al
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rcx
  int NCryptKeyHandleNew; // eax
  DWORD LastError; // eax
  int v21; // edi
  DWORD v22; // eax
  const struct _BYTE_ARRAY *v23; // rax
  unsigned __int64 i; // rsi
  DWORD v25; // eax
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE hCryptProvOrNCryptKey; // [rsp+30h] [rbp-10h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+38h] [rbp-8h] BYREF
  DWORD pcbInfo; // [rsp+88h] [rbp+48h] BYREF
  int v30; // [rsp+8Ch] [rbp+4Ch]
  const struct _BYTE_ARRAY *v31; // [rsp+90h] [rbp+50h]
  unsigned __int64 v32; // [rsp+98h] [rbp+58h]

  v32 = a4;
  v31 = a3;
  v30 = HIDWORD(a2);
  v5 = a5;
  v6 = 0;
  v7 = 0;
  hCryptProvOrNCryptKey = 0;
  v8 = -1;
  pcbInfo = 0;
  pCertContext = 0;
  v9 = a4;
  if ( !a5 )
  {
    v11 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationCertHelper::VerifyDeviceJoinAutoSigningCert",
      L"pMatchedKeyIndex");
    v12 = L"pMatchedKeyIndex";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationCertHelper::VerifyDeviceJoinAutoSigningCert", v12);
    goto LABEL_38;
  }
  *a5 = -1;
  if ( (unsigned int)IsEmptyString(L"6b30069e-b381-42cc-9fae-421915a9e9f3") )
  {
    v11 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null or empty.",
      L"RegistrationCertHelper::VerifyDeviceJoinAutoSigningCert",
      L"pcszKeyContainerName");
    v12 = L"pcszKeyContainerName";
    goto LABEL_3;
  }
  if ( v13 && v14 )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_EntraIdClientPlutonKsp>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EntraIdClientPlutonKsp>::GetImpl'::`2'::impl);
    v18 = *(unsigned int *)this;
    if ( IsEnabled )
      NCryptKeyHandleNew = RegistrationKeyHelper::GetNCryptKeyHandleNew(
                             v18,
                             *((unsigned int *)this + 1),
                             v17,
                             &hCryptProvOrNCryptKey);
    else
      NCryptKeyHandleNew = RegistrationKeyHelper::GetNCryptKeyHandle(v18, v16, v17, &hCryptProvOrNCryptKey);
    v11 = NCryptKeyHandleNew;
    if ( NCryptKeyHandleNew == -2146893802 )
    {
      Logger::TraceInformation(
        L"%s: The local key with name %s is not found.",
        L"RegistrationCertHelper::VerifyDeviceJoinAutoSigningCert",
        L"6b30069e-b381-42cc-9fae-421915a9e9f3");
LABEL_13:
      v11 = 0;
      goto LABEL_38;
    }
    if ( NCryptKeyHandleNew < 0 )
    {
      Logger::TraceError(
        L"%s: Cannot get local private key handle with name %s. RegistrationKeyHelper::GetNCryptKeyHandle failed with erro"
         "r code: 0x%08x. Assuming local key does not exist...",
        L"RegistrationCertHelper::VerifyDeviceJoinAutoSigningCert",
        L"6b30069e-b381-42cc-9fae-421915a9e9f3",
        (unsigned int)NCryptKeyHandleNew);
      goto LABEL_13;
    }
    if ( !CryptExportPublicKeyInfo(hCryptProvOrNCryptKey, 0, 1u, 0, &pcbInfo) )
      goto LABEL_17;
    v6 = (struct _CERT_PUBLIC_KEY_INFO *)SafeAlloc(pcbInfo);
    if ( !v6 )
    {
      v11 = -2147024882;
      Logger::TraceCritical(
        L"%s: Out of memory. Allocation failed.",
        L"RegistrationCertHelper::VerifyDeviceJoinAutoSigningCert");
      goto LABEL_38;
    }
    if ( !CryptExportPublicKeyInfo(hCryptProvOrNCryptKey, 0, 1u, v6, &pcbInfo) )
    {
LABEL_17:
      LastError = GetLastError();
      Logger::TraceError(
        L"%s: Cannot get local public key with name %s. CryptExportPublicKeyInfo failed with win32 error code: 0x%08x. Ass"
         "uming local key does not match key in the directory...",
        L"RegistrationCertHelper::VerifyDeviceJoinAutoSigningCert",
        L"6b30069e-b381-42cc-9fae-421915a9e9f3",
        LastError);
      goto LABEL_38;
    }
    v21 = 0;
    v7 = CertOpenStore((LPCSTR)2, 1u, 0, 0x2000u, 0);
    if ( v7 || (v22 = GetLastError(), (v21 = v22) == 0) )
    {
      v23 = v31;
      for ( i = 0; i < v9; ++i )
      {
        if ( *((_QWORD *)v23 + 2 * i) && *((_QWORD *)v23 + 2 * i + 1) )
        {
          CertFreeCertificateContext(pCertContext);
          pCertContext = 0;
          if ( CertAddEncodedCertificateToStore(
                 v7,
                 1u,
                 *((const BYTE **)v31 + 2 * i),
                 *((_DWORD *)v31 + 4 * i + 2),
                 3u,
                 &pCertContext) )
          {
            if ( CertComparePublicKeyInfo(1u, v6, &pCertContext->pCertInfo->SubjectPublicKeyInfo) )
            {
              *v5 = i;
              Logger::TraceVerbose(
                (wchar_t *)L"%s: Certificate at index %d matched the local key.",
                L"RegistrationCertHelper::VerifyDeviceJoinAutoSigningCert",
                i);
              break;
            }
          }
          else
          {
            v25 = GetLastError();
            Logger::TraceError(
              L"%s: Cannot decode the auto signing certificate at index %d from the directory. CertAddEncodedCertificateTo"
               "Store failed with error code: 0x%08x.",
              L"RegistrationCertHelper::VerifyDeviceJoinAutoSigningCert",
              i,
              v25);
          }
          v23 = v31;
        }
        v9 = v32;
      }
      if ( !v21 )
        goto LABEL_37;
    }
    else
    {
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"RegistrationCertHelper::VerifyDeviceJoinAutoSigningCert",
        L"CertOpenStore",
        v22);
    }
    if ( v21 > 0 )
      v11 = (unsigned __int16)v21 | 0x80070000;
    else
      v11 = v21;
LABEL_37:
    v8 = -1;
    goto LABEL_38;
  }
  v11 = 0;
  Logger::TraceVerbose(
    (wchar_t *)L"%s: Cert array is empty.",
    L"RegistrationCertHelper::VerifyDeviceJoinAutoSigningCert");
LABEL_38:
  if ( hCryptProvOrNCryptKey )
    NCryptFreeObject(hCryptProvOrNCryptKey);
  SafeFree(v6);
  CertFreeCertificateContext(pCertContext);
  CertCloseStore(v7, 1u);
  if ( v5 )
    v8 = *v5;
  Logger::TraceVerbose(
    (wchar_t *)L"%s: hr: 0x%08x. pMatchedKeyIndex: %d.",
    L"RegistrationCertHelper::VerifyDeviceJoinAutoSigningCert",
    v11,
    v8);
  return v11;
}

```

## disassembly

```asm
0x18005e84c  mov     rax, rsp
0x18005e84f  mov     [rax+8], rbx
0x18005e853  mov     [rax+20h], r9
0x18005e857  mov     [rax+18h], r8
0x18005e85b  mov     [rax+10h], rdx
0x18005e85f  push    rbp
0x18005e860  push    rsi
0x18005e861  push    rdi
0x18005e862  push    r12
0x18005e864  push    r13
0x18005e866  push    r14
0x18005e868  push    r15
0x18005e86a  mov     rbp, rsp
0x18005e86d  sub     rsp, 40h
0x18005e871  mov     r12, [rbp+arg_20]
0x18005e875  xor     r15d, r15d
0x18005e878  xor     r13d, r13d
0x18005e87b  mov     [rbp+hCryptProvOrNCryptKey], 0
0x18005e883  or      edi, 0FFFFFFFFh
0x18005e886  mov     [rbp+arg_8], r15d
0x18005e88a  mov     [rbp+pCertContext], r13
0x18005e88e  mov     r14, r9
0x18005e891  mov     rbx, rcx
0x18005e894  test    r12, r12
0x18005e897  jnz     short loc_18005E8D0
0x18005e899  lea     r8, aPmatchedkeyind; "pMatchedKeyIndex"
0x18005e8a0  mov     ebx, 80070057h
0x18005e8a5  lea     rdx, aRegistrationce_25; "RegistrationCertHelper::VerifyDeviceJoi"...
0x18005e8ac  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18005e8b3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005e8b8  lea     rdx, aPmatchedkeyind; "pMatchedKeyIndex"
0x18005e8bf  lea     rcx, aRegistrationce_25; "RegistrationCertHelper::VerifyDeviceJoi"...
0x18005e8c6  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18005e8cb  jmp     loc_18005EB52
0x18005e8d0  lea     rsi, pszKeyName; "6b30069e-b381-42cc-9fae-421915a9e9f3"
0x18005e8d7  mov     [r12], edi
0x18005e8db  mov     rcx, rsi; unsigned __int16 *
0x18005e8de  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18005e8e3  test    eax, eax
0x18005e8e5  jz      short loc_18005E90F
0x18005e8e7  lea     r8, aPcszkeycontain; "pcszKeyContainerName"
0x18005e8ee  mov     ebx, 80070057h
0x18005e8f3  lea     rdx, aRegistrationce_25; "RegistrationCertHelper::VerifyDeviceJoi"...
0x18005e8fa  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null or empty."
0x18005e901  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005e906  lea     rdx, aPcszkeycontain; "pcszKeyContainerName"
0x18005e90d  jmp     short loc_18005E8BF
0x18005e90f  test    r8, r8
0x18005e912  jz      loc_18005EBC8
0x18005e918  test    r9, r9
0x18005e91b  jz      loc_18005EBC8
0x18005e921  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EntraIdClientPlutonKsp@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EntraIdClientPlutonKsp@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EntraIdClientPlutonKsp> `wil::Feature<__WilFeatureTraits_Feature_EntraIdClientPlutonKsp>::GetImpl(void)'::`2'::impl
0x18005e928  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EntraIdClientPlutonKsp@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EntraIdClientPlutonKsp>::__private_IsEnabled(void)
0x18005e92d  mov     ecx, [rbx]
0x18005e92f  lea     r9, [rbp+hCryptProvOrNCryptKey]
0x18005e933  test    al, al
0x18005e935  jz      short loc_18005E941
0x18005e937  mov     edx, [rbx+4]
0x18005e93a  call    ?GetNCryptKeyHandleNew@RegistrationKeyHelper@@SAJW4_KEY_POLICY@@W4_HARDWARE_POLICY@@PEBGPEA_K@Z; RegistrationKeyHelper::GetNCryptKeyHandleNew(_KEY_POLICY,_HARDWARE_POLICY,ushort const *,unsigned __int64 *)
0x18005e93f  jmp     short loc_18005E946
0x18005e941  call    ?GetNCryptKeyHandle@RegistrationKeyHelper@@SAJW4_KEY_POLICY@@W4_HARDWARE_POLICY@@PEBGPEA_K@Z; RegistrationKeyHelper::GetNCryptKeyHandle(_KEY_POLICY,_HARDWARE_POLICY,ushort const *,unsigned __int64 *)
0x18005e946  mov     ebx, eax
0x18005e948  cmp     eax, 80090016h
0x18005e94d  jnz     short loc_18005E96C
0x18005e94f  mov     r8, rsi
0x18005e952  lea     rdx, aRegistrationce_25; "RegistrationCertHelper::VerifyDeviceJoi"...
0x18005e959  lea     rcx, aSTheLocalKeyWi; "%s: The local key with name %s is not f"...
0x18005e960  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18005e965  xor     ebx, ebx
0x18005e967  jmp     loc_18005EB52
0x18005e96c  test    ebx, ebx
0x18005e96e  jns     short loc_18005E98B
0x18005e970  mov     r9d, ebx
0x18005e973  lea     rdx, aRegistrationce_25; "RegistrationCertHelper::VerifyDeviceJoi"...
0x18005e97a  mov     r8, rsi
0x18005e97d  lea     rcx, aSCannotGetLoca; "%s: Cannot get local private key handle"...
0x18005e984  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005e989  jmp     short loc_18005E965
0x18005e98b  mov     rcx, [rbp+hCryptProvOrNCryptKey]; hCryptProvOrNCryptKey
0x18005e98f  lea     rax, [rbp+arg_8]
0x18005e993  xor     r9d, r9d; pInfo
0x18005e996  mov     [rsp+40h+pcbInfo], rax; pcbInfo
0x18005e99b  xor     edx, edx; dwKeySpec
0x18005e99d  lea     r8d, [r9+1]; dwCertEncodingType
0x18005e9a1  call    cs:__imp_CryptExportPublicKeyInfo
0x18005e9a7  test    eax, eax
0x18005e9a9  jnz     short loc_18005E9CF
0x18005e9ab  call    cs:__imp_GetLastError
0x18005e9b1  mov     r8, rsi
0x18005e9b4  lea     rdx, aRegistrationce_25; "RegistrationCertHelper::VerifyDeviceJoi"...
0x18005e9bb  mov     r9d, eax
0x18005e9be  lea     rcx, aSCannotGetLoca_1; "%s: Cannot get local public key with na"...
0x18005e9c5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005e9ca  jmp     loc_18005EB52
0x18005e9cf  mov     ecx, [rbp+arg_8]; unsigned __int64
0x18005e9d2  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x18005e9d7  mov     r15, rax
0x18005e9da  test    rax, rax
0x18005e9dd  jnz     short loc_18005E9FC
0x18005e9df  lea     rdx, aRegistrationce_25; "RegistrationCertHelper::VerifyDeviceJoi"...
0x18005e9e6  mov     ebx, 8007000Eh
0x18005e9eb  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18005e9f2  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18005e9f7  jmp     loc_18005EB52
0x18005e9fc  mov     rcx, [rbp+hCryptProvOrNCryptKey]; hCryptProvOrNCryptKey
0x18005ea00  lea     rax, [rbp+arg_8]
0x18005ea04  xor     edx, edx; dwKeySpec
0x18005ea06  mov     [rsp+40h+pcbInfo], rax; pcbInfo
0x18005ea0b  mov     r9, r15; pInfo
0x18005ea0e  lea     r8d, [rdx+1]; dwCertEncodingType
0x18005ea12  call    cs:__imp_CryptExportPublicKeyInfo
0x18005ea18  test    eax, eax
0x18005ea1a  jz      short loc_18005E9AB
0x18005ea1c  xor     edi, edi
0x18005ea1e  mov     r9d, 2000h; dwFlags
0x18005ea24  xor     r8d, r8d; hCryptProv
0x18005ea27  mov     [rsp+40h+pcbInfo], rdi; pvPara
0x18005ea2c  lea     edx, [rdi+1]; dwEncodingType
0x18005ea2f  lea     ecx, [rdi+2]; lpszStoreProvider
0x18005ea32  call    cs:__imp_CertOpenStore
0x18005ea38  mov     r13, rax
0x18005ea3b  test    rax, rax
0x18005ea3e  jnz     short loc_18005EA6E
0x18005ea40  call    cs:__imp_GetLastError
0x18005ea46  mov     edi, eax
0x18005ea48  test    eax, eax
0x18005ea4a  jz      short loc_18005EA6E
0x18005ea4c  mov     r9d, eax
0x18005ea4f  lea     r8, aCertopenstore_0; "CertOpenStore"
0x18005ea56  lea     rdx, aRegistrationce_25; "RegistrationCertHelper::VerifyDeviceJoi"...
0x18005ea5d  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18005ea64  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005ea69  jmp     loc_18005EB49
0x18005ea6e  mov     rax, [rbp+arg_10]
0x18005ea72  xor     esi, esi
0x18005ea74  cmp     rsi, r14
0x18005ea77  jnb     loc_18005EB45
0x18005ea7d  mov     r14, rsi
0x18005ea80  add     r14, r14
0x18005ea83  cmp     qword ptr [rax+r14*8], 0
0x18005ea88  jz      loc_18005EB1F
0x18005ea8e  cmp     qword ptr [rax+r14*8+8], 0
0x18005ea94  jz      loc_18005EB1F
0x18005ea9a  mov     rcx, [rbp+pCertContext]; pCertContext
0x18005ea9e  call    cs:__imp_CertFreeCertificateContext
0x18005eaa4  lea     rax, [rbp+pCertContext]
0x18005eaa8  mov     [rbp+pCertContext], 0
0x18005eab0  mov     [rsp+40h+ppCertContext], rax; ppCertContext
0x18005eab5  mov     edx, 1; dwCertEncodingType
0x18005eaba  mov     rax, [rbp+arg_10]
0x18005eabe  mov     rcx, r13; hCertStore
0x18005eac1  mov     dword ptr [rsp+40h+pcbInfo], 3; dwAddDisposition
0x18005eac9  mov     r9d, [rax+r14*8+8]; cbCertEncoded
0x18005eace  mov     r8, [rax+r14*8]; pbCertEncoded
0x18005ead2  call    cs:__imp_CertAddEncodedCertificateToStore
0x18005ead8  test    eax, eax
0x18005eada  jnz     short loc_18005EAFD
0x18005eadc  call    cs:__imp_GetLastError
0x18005eae2  mov     r8, rsi
0x18005eae5  lea     rdx, aRegistrationce_25; "RegistrationCertHelper::VerifyDeviceJoi"...
0x18005eaec  mov     r9d, eax
0x18005eaef  lea     rcx, aSCannotDecodeT; "%s: Cannot decode the auto signing cert"...
0x18005eaf6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005eafb  jmp     short loc_18005EB1B
0x18005eafd  mov     rax, [rbp+pCertContext]
0x18005eb01  mov     rdx, r15; pPublicKey1
0x18005eb04  mov     ecx, 1; dwCertEncodingType
0x18005eb09  mov     r8, [rax+18h]
0x18005eb0d  add     r8, 60h ; '`'; pPublicKey2
0x18005eb11  call    cs:__imp_CertComparePublicKeyInfo
0x18005eb17  test    eax, eax
0x18005eb19  jnz     short loc_18005EB2B
0x18005eb1b  mov     rax, [rbp+arg_10]
0x18005eb1f  mov     r14, [rbp+arg_18]
0x18005eb23  inc     rsi
0x18005eb26  jmp     loc_18005EA74
0x18005eb2b  mov     r8, rsi
0x18005eb2e  mov     [r12], esi
0x18005eb32  lea     rdx, aRegistrationce_25; "RegistrationCertHelper::VerifyDeviceJoi"...
0x18005eb39  lea     rcx, aSCertificateAt; "%s: Certificate at index %d matched the"...
0x18005eb40  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005eb45  test    edi, edi
0x18005eb47  jz      short loc_18005EB4F
0x18005eb49  test    edi, edi
0x18005eb4b  jg      short loc_18005EBBD
0x18005eb4d  mov     ebx, edi
0x18005eb4f  or      edi, 0FFFFFFFFh
0x18005eb52  mov     rcx, [rbp+hCryptProvOrNCryptKey]; hObject
0x18005eb56  test    rcx, rcx
0x18005eb59  jz      short loc_18005EB61
0x18005eb5b  call    cs:__imp_NCryptFreeObject
0x18005eb61  mov     rcx, r15; lpMem
0x18005eb64  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18005eb69  mov     rcx, [rbp+pCertContext]; pCertContext
0x18005eb6d  call    cs:__imp_CertFreeCertificateContext
0x18005eb73  mov     edx, 1; dwFlags
0x18005eb78  mov     rcx, r13; hCertStore
0x18005eb7b  call    cs:__imp_CertCloseStore
0x18005eb81  test    r12, r12
0x18005eb84  jz      short loc_18005EB8A
0x18005eb86  mov     edi, [r12]
0x18005eb8a  mov     r9d, edi
0x18005eb8d  lea     rdx, aRegistrationce_25; "RegistrationCertHelper::VerifyDeviceJoi"...
0x18005eb94  mov     r8d, ebx
0x18005eb97  lea     rcx, aSHr0x08xPmatch; "%s: hr: 0x%08x. pMatchedKeyIndex: %d."
0x18005eb9e  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005eba3  mov     eax, ebx
0x18005eba5  mov     rbx, [rsp+40h+arg_0]
0x18005ebad  add     rsp, 40h
0x18005ebb1  pop     r15
0x18005ebb3  pop     r14
0x18005ebb5  pop     r13
0x18005ebb7  pop     r12
0x18005ebb9  pop     rdi
0x18005ebba  pop     rsi
0x18005ebbb  pop     rbp
0x18005ebbc  retn
0x18005ebbd  movzx   ebx, di
0x18005ebc0  or      ebx, 80070000h
0x18005ebc6  jmp     short loc_18005EB4F
0x18005ebc8  xor     ebx, ebx
0x18005ebca  lea     rdx, aRegistrationce_25; "RegistrationCertHelper::VerifyDeviceJoi"...
0x18005ebd1  lea     rcx, aSCertArrayIsEm; "%s: Cert array is empty."
0x18005ebd8  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005ebdd  jmp     loc_18005EB52
```
