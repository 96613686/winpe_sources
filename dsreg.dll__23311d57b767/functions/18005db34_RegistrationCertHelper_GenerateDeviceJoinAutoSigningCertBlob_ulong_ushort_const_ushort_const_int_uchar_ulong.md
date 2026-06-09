# RegistrationCertHelper::GenerateDeviceJoinAutoSigningCertBlob(ulong,ushort const *,ushort const *,int,uchar * *,ulong *)

- ea: `0x18005db34`
- end: `0x18005e0ad`
- name: `?GenerateDeviceJoinAutoSigningCertBlob@RegistrationCertHelper@@QEAAJKPEBG0HPEAPEAEPEAK@Z`
- size: `1401`
- prototype: `__int64 __fastcall(RegistrationCertHelper *__hidden this, unsigned int, const unsigned __int16 *, const unsigned __int16 *, int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x1800573cc`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x180012948`
- `0x1800307c4`
- `0x18003334c`
- `0x1800436a4`
- `0x180043ef8`
- `0x180044300`
- `0x18004654c`
- `0x18005b348`
- `0x18005db34`
- `0x1800747bc`
- `0x180076658`
- `0x18007683c`
- `0x18008a810`
- `0x180098f54`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18005dd95`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18005dd95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dcde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dd77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ded4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dfa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dcde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dd77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ded4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dfa7`
- `CRYPT32!CertStrToNameW` at `0x18005dcd4`
- `CRYPT32!CertStrToNameW` at `0x18005dd6d`
- `CRYPT32!CertStrToNameW` at `0x18005dcd4`
- `CRYPT32!CertStrToNameW` at `0x18005dd6d`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x18005deba`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x18005df99`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x18005deba`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x18005df99`
- `CRYPT32!CertFreeCertificateContext` at `0x18005e059`
- `CRYPT32!CertFreeCertificateContext` at `0x18005e059`
- `ncrypt!NCryptFreeObject` at `0x18005e068`
- `ncrypt!NCryptFreeObject` at `0x18005e068`

## string_xrefs

- `0x18005dfe3`: `CopyStringA`
- `0x18005de75`: `RegistrationKeyHelper::CreateNCryptKeyHandle`
- `0x18005df45`: `RegistrationKeyHelper::CreateNCryptKeyHandle`
- `0x18005de18`: `%s: Unable to open the existing auto sign key. RegistrationKeyHelper::GetNCryptKeyHandle failed with error code: 0x%08x. Will try to delete the existing key and generate a new one.`
- `0x18005dee4`: `%s: Cannot generate auto signing cert using the existing key. CertCreateSelfSignCertificate failed with win32 error code: 0x%08x. Will try to delete the existing key and generate a new one.`
- `0x18005dfb7`: `%s: Cannot generate auto signing cert using the newly generated key. CertCreateSelfSignCertificate failed with win32 error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall RegistrationCertHelper::GenerateDeviceJoinAutoSigningCertBlob(
        RegistrationCertHelper *this,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  __int64 v7; // rdi
  PCCERT_CONTEXT v9; // r14
  WCHAR *v10; // r15
  BYTE *v11; // rsi
  unsigned int v12; // ebx
  const unsigned __int16 *v13; // rdx
  char *v14; // r12
  unsigned __int64 v15; // r8
  int v16; // eax
  DWORD LastError; // eax
  unsigned __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // r8
  const wchar_t *v21; // r8
  int v22; // ecx
  char IsEnabled; // al
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rcx
  int NCryptKeyHandleNew; // eax
  int v28; // esi
  DWORD v29; // eax
  __int64 v30; // r8
  int v31; // eax
  DWORD cbCertEncoded; // esi
  int v33; // eax
  char *Block; // [rsp+50h] [rbp-81h]
  DWORD pcbEncoded; // [rsp+58h] [rbp-79h] BYREF
  LPCWSTR pszX500; // [rsp+60h] [rbp-71h] BYREF
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE hCryptProvOrNCryptKey; // [rsp+68h] [rbp-69h] BYREF
  char *v39; // [rsp+70h] [rbp-61h] BYREF
  void *v40; // [rsp+78h] [rbp-59h] BYREF
  struct _CRYPTOAPI_BLOB pSubjectIssuerBlob; // [rsp+80h] [rbp-51h] BYREF
  unsigned int *v42; // [rsp+90h] [rbp-41h]
  struct _CRYPT_ALGORITHM_IDENTIFIER pSignatureAlgorithm; // [rsp+98h] [rbp-39h] BYREF
  struct _SYSTEMTIME pEndTime; // [rsp+B0h] [rbp-21h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+C0h] [rbp-11h] BYREF

  LODWORD(v7) = 0;
  v42 = a7;
  Block = 0;
  v39 = 0;
  hCryptProvOrNCryptKey = 0;
  pSignatureAlgorithm.pszObjId = "1.2.840.113549.1.1.11";
  v9 = 0;
  pszX500 = 0;
  v40 = 0;
  v10 = 0;
  pcbEncoded = 0;
  v11 = 0;
  *(_QWORD *)&pSignatureAlgorithm.Parameters.cbData = 0;
  pSignatureAlgorithm.Parameters.pbData = 0;
  pSubjectIssuerBlob = 0;
  pEndTime = 0;
  SystemTime = 0;
  if ( !a4 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationCertHelper::GenerateDeviceJoinAutoSigningCertBlob",
      L"pcszSubjectName");
    v13 = L"pcszSubjectName";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationCertHelper::GenerateDeviceJoinAutoSigningCertBlob", v13);
LABEL_4:
    v14 = 0;
    goto LABEL_49;
  }
  if ( !a6 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationCertHelper::GenerateDeviceJoinAutoSigningCertBlob",
      L"ppbCertBlob");
    v13 = L"ppbCertBlob";
    goto LABEL_3;
  }
  if ( !a7 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationCertHelper::GenerateDeviceJoinAutoSigningCertBlob",
      L"pdwCertBlobLen");
    v13 = L"pdwCertBlobLen";
    goto LABEL_3;
  }
  *a6 = 0;
  v15 = -1;
  *a7 = 0;
  do
    ++v15;
  while ( a4[v15] );
  v16 = ConcatenateStringW(3u, L"CN=", v15, a4, (unsigned __int16 **)&pszX500);
  v12 = v16;
  if ( v16 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationCertHelper::GenerateDeviceJoinAutoSigningCertBlob",
      L"ConcatenateStringW",
      (unsigned int)v16);
    v10 = (WCHAR *)pszX500;
    goto LABEL_4;
  }
  v10 = (WCHAR *)pszX500;
  if ( !CertStrToNameW(1u, pszX500, 2u, 0, 0, &pcbEncoded, 0) )
  {
    LastError = GetLastError();
    LODWORD(v7) = LastError;
    if ( LastError )
      goto LABEL_15;
  }
  pszX500 = (LPCWSTR)operator new[](pcbEncoded, (const struct std::nothrow_t *)&std::nothrow);
  v11 = (BYTE *)pszX500;
  if ( !pszX500 )
  {
    v12 = -2147024882;
    Logger::TraceCritical(
      L"%s: Out of memory. Allocation failed.",
      L"RegistrationCertHelper::GenerateDeviceJoinAutoSigningCertBlob");
LABEL_18:
    v14 = 0;
    goto LABEL_45;
  }
  if ( CertStrToNameW(1u, v10, 2u, 0, (BYTE *)pszX500, &pcbEncoded, 0)
    || (LastError = GetLastError(), (LODWORD(v7) = LastError) == 0) )
  {
    pSubjectIssuerBlob.cbData = pcbEncoded;
    pSubjectIssuerBlob.pbData = v11;
    GetSystemTime(&SystemTime);
    v19 = SystemTimeAddSeconds(&SystemTime, v18, &pEndTime);
    v12 = v19;
    if ( v19 < 0 )
    {
      v21 = L"SystemTimeAddYears";
LABEL_23:
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"RegistrationCertHelper::GenerateDeviceJoinAutoSigningCertBlob",
        v21,
        (unsigned int)v19);
      goto LABEL_18;
    }
    v22 = a5;
    if ( !a5 )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_EntraIdClientPlutonKsp>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EntraIdClientPlutonKsp>::GetImpl'::`2'::impl);
      v26 = *(unsigned int *)this;
      if ( IsEnabled )
        NCryptKeyHandleNew = RegistrationKeyHelper::GetNCryptKeyHandleNew(
                               v26,
                               *((unsigned int *)this + 1),
                               v25,
                               &hCryptProvOrNCryptKey);
      else
        NCryptKeyHandleNew = RegistrationKeyHelper::GetNCryptKeyHandle(v26, v24, v25, &hCryptProvOrNCryptKey);
      if ( NCryptKeyHandleNew >= 0 )
      {
        v28 = 1;
LABEL_34:
        v9 = CertCreateSelfSignCertificate(
               hCryptProvOrNCryptKey,
               &pSubjectIssuerBlob,
               2u,
               0,
               &pSignatureAlgorithm,
               0,
               &pEndTime,
               0);
        if ( !v9 )
        {
          if ( !v28 )
            goto LABEL_40;
          v29 = GetLastError();
          Logger::TraceWarning(
            (wchar_t *)L"%s: Cannot generate auto signing cert using the existing key. CertCreateSelfSignCertificate faile"
                        "d with win32 error code: 0x%08x. Will try to delete the existing key and generate a new one.",
            L"RegistrationCertHelper::GenerateDeviceJoinAutoSigningCertBlob",
            v29);
          v31 = RegistrationKeyHelper::CreateNCryptKeyHandle(
                  *(unsigned int *)this,
                  *((unsigned int *)this + 1),
                  v30,
                  L"6b30069e-b381-42cc-9fae-421915a9e9f3",
                  *((_DWORD *)this + 2) == 1,
                  1,
                  &hCryptProvOrNCryptKey,
                  &v40,
                  0);
          v12 = v31;
          if ( v31 < 0 )
          {
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"RegistrationCertHelper::GenerateDeviceJoinAutoSigningCertBlob",
              L"RegistrationKeyHelper::CreateNCryptKeyHandle",
              (unsigned int)v31);
            goto LABEL_38;
          }
          Logger::TraceInformation(
            L"%s: New signing key generated for sync'ed auto join.",
            L"RegistrationCertHelper::GenerateDeviceJoinAutoSigningCertBlob");
          v9 = CertCreateSelfSignCertificate(
                 hCryptProvOrNCryptKey,
                 &pSubjectIssuerBlob,
                 2u,
                 0,
                 &pSignatureAlgorithm,
                 0,
                 &pEndTime,
                 0);
          if ( !v9 )
          {
LABEL_40:
            v7 = GetLastError();
            Logger::TraceError(
              L"%s: Cannot generate auto signing cert using the newly generated key. CertCreateSelfSignCertificate failed "
               "with win32 error code: 0x%08x.",
              L"RegistrationCertHelper::GenerateDeviceJoinAutoSigningCertBlob",
              v7);
            goto LABEL_38;
          }
        }
        cbCertEncoded = v9->cbCertEncoded;
        v33 = CopyStringA((const char *)v9->pbCertEncoded, cbCertEncoded, &v39);
        v12 = v33;
        if ( v33 >= 0 )
        {
          v14 = 0;
          *a6 = (unsigned __int8 *)v39;
          *v42 = cbCertEncoded;
          goto LABEL_44;
        }
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"RegistrationCertHelper::GenerateDeviceJoinAutoSigningCertBlob",
          L"CopyStringA",
          (unsigned int)v33);
        Block = v39;
LABEL_38:
        v14 = Block;
LABEL_44:
        v11 = (BYTE *)pszX500;
LABEL_45:
        if ( !(_DWORD)v7 )
          goto LABEL_49;
        goto LABEL_46;
      }
      Logger::TraceWarning(
        (wchar_t *)L"%s: Unable to open the existing auto sign key. RegistrationKeyHelper::GetNCryptKeyHandle failed with "
                    "error code: 0x%08x. Will try to delete the existing key and generate a new one.",
        L"RegistrationCertHelper::GenerateDeviceJoinAutoSigningCertBlob",
        (unsigned int)NCryptKeyHandleNew);
      v22 = 1;
    }
    v19 = RegistrationKeyHelper::CreateNCryptKeyHandle(
            *(unsigned int *)this,
            *((unsigned int *)this + 1),
            v20,
            L"6b30069e-b381-42cc-9fae-421915a9e9f3",
            *((_DWORD *)this + 2) == 1,
            v22,
            &hCryptProvOrNCryptKey,
            &v40,
            0);
    v12 = v19;
    if ( v19 < 0 )
    {
      v21 = L"RegistrationKeyHelper::CreateNCryptKeyHandle";
      goto LABEL_23;
    }
    v28 = 0;
    Logger::TraceInformation(
      L"%s: New signing key generated for sync'ed auto join.",
      L"RegistrationCertHelper::GenerateDeviceJoinAutoSigningCertBlob");
    goto LABEL_34;
  }
LABEL_15:
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"RegistrationCertHelper::GenerateDeviceJoinAutoSigningCertBlob",
    L"CertStrToNameW",
    LastError);
  v14 = 0;
LABEL_46:
  if ( (int)v7 > 0 )
    v12 = (unsigned __int16)v7 | 0x80070000;
  else
    v12 = v7;
LABEL_49:
  operator delete(v10);
  operator delete(v11);
  operator delete(v14);
  operator delete(v40);
  CertFreeCertificateContext(v9);
  if ( hCryptProvOrNCryptKey )
    NCryptFreeObject(hCryptProvOrNCryptKey);
  Logger::TraceVerbose(
    (wchar_t *)L"%s - hr: 0x%08x",
    L"RegistrationCertHelper::GenerateDeviceJoinAutoSigningCertBlob",
    v12);
  return v12;
}

```

## disassembly

```asm
0x18005db34  mov     [rsp-8+arg_8], rbx
0x18005db39  push    rbp
0x18005db3a  push    rsi
0x18005db3b  push    rdi
0x18005db3c  push    r12
0x18005db3e  push    r13
0x18005db40  push    r14
0x18005db42  push    r15
0x18005db44  lea     rbp, [rsp-0Fh]
0x18005db49  sub     rsp, 0E0h
0x18005db50  mov     rax, cs:__security_cookie
0x18005db57  xor     rax, rsp
0x18005db5a  mov     [rbp+3Fh+var_40], rax
0x18005db5e  mov     rax, [rbp+3Fh+arg_30]
0x18005db62  xor     edi, edi
0x18005db64  mov     r13, [rbp+3Fh+arg_28]
0x18005db68  mov     r12, rcx
0x18005db6b  mov     ecx, edi
0x18005db6d  mov     [rbp+3Fh+var_80], rax
0x18005db71  mov     [rsp+110h+Block], rcx
0x18005db76  xorps   xmm0, xmm0
0x18005db79  mov     [rbp+3Fh+var_A0], rcx
0x18005db7d  xorps   xmm1, xmm1
0x18005db80  lea     rcx, a12840113549111; "1.2.840.113549.1.1.11"
0x18005db87  mov     [rbp+3Fh+hCryptProvOrNCryptKey], rdi
0x18005db8b  mov     [rbp+3Fh+pSignatureAlgorithm.pszObjId], rcx
0x18005db8f  mov     r14d, edi
0x18005db92  xor     ecx, ecx
0x18005db94  mov     [rbp+3Fh+pszX500], rdi
0x18005db98  mov     [rbp+3Fh+var_98], rdi
0x18005db9c  mov     r15d, edi
0x18005db9f  mov     [rbp+3Fh+var_B8], edi
0x18005dba2  mov     esi, edi
0x18005dba4  mov     qword ptr [rbp+3Fh+pSignatureAlgorithm.Parameters.cbData], rdi
0x18005dba8  mov     [rbp+3Fh+pSignatureAlgorithm.Parameters.pbData], rcx
0x18005dbac  movups  xmmword ptr [rbp+3Fh+pSubjectIssuerBlob.cbData], xmm0
0x18005dbb0  movups  xmmword ptr [rbp+3Fh+pEndTime.wYear], xmm1
0x18005dbb4  movups  xmmword ptr [rbp+3Fh+SystemTime.wYear], xmm0
0x18005dbb8  test    r9, r9
0x18005dbbb  jnz     short loc_18005DBF9
0x18005dbbd  lea     r8, aPcszsubjectnam; "pcszSubjectName"
0x18005dbc4  mov     ebx, 80070057h
0x18005dbc9  lea     rdx, aRegistrationce_14; "RegistrationCertHelper::GenerateDeviceJ"...
0x18005dbd0  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18005dbd7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005dbdc  lea     rdx, aPcszsubjectnam; "pcszSubjectName"
0x18005dbe3  lea     rcx, aRegistrationce_14; "RegistrationCertHelper::GenerateDeviceJ"...
0x18005dbea  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18005dbef  mov     r12, [rsp+110h+Block]
0x18005dbf4  jmp     loc_18005E035
0x18005dbf9  test    r13, r13
0x18005dbfc  jnz     short loc_18005DC26
0x18005dbfe  lea     r8, aPpbcertblob; "ppbCertBlob"
0x18005dc05  mov     ebx, 80070057h
0x18005dc0a  lea     rdx, aRegistrationce_14; "RegistrationCertHelper::GenerateDeviceJ"...
0x18005dc11  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18005dc18  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005dc1d  lea     rdx, aPpbcertblob; "ppbCertBlob"
0x18005dc24  jmp     short loc_18005DBE3
0x18005dc26  test    rax, rax
0x18005dc29  jnz     short loc_18005DC53
0x18005dc2b  lea     r8, aPdwcertbloblen; "pdwCertBlobLen"
0x18005dc32  mov     ebx, 80070057h
0x18005dc37  lea     rdx, aRegistrationce_14; "RegistrationCertHelper::GenerateDeviceJ"...
0x18005dc3e  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18005dc45  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005dc4a  lea     rdx, aPdwcertbloblen; "pdwCertBlobLen"
0x18005dc51  jmp     short loc_18005DBE3
0x18005dc53  mov     [r13+0], rdi
0x18005dc57  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005dc5b  mov     [rax], edi
0x18005dc5d  inc     r8; unsigned __int64
0x18005dc60  cmp     [r9+r8*2], di
0x18005dc65  jnz     short loc_18005DC5D
0x18005dc67  lea     rax, [rbp+3Fh+pszX500]
0x18005dc6b  mov     ecx, 3; unsigned __int64
0x18005dc70  lea     rdx, aCn; "CN="
0x18005dc77  mov     [rsp+110h+pbEncoded], rax; unsigned __int16 **
0x18005dc7c  call    ?ConcatenateStringW@@YAJ_KPEBG01PEAPEAG@Z; ConcatenateStringW(unsigned __int64,ushort const *,unsigned __int64,ushort const *,ushort * *)
0x18005dc81  mov     ebx, eax
0x18005dc83  test    eax, eax
0x18005dc85  jns     short loc_18005DCAD
0x18005dc87  mov     r9d, eax
0x18005dc8a  lea     r8, aConcatenatestr; "ConcatenateStringW"
0x18005dc91  lea     rdx, aRegistrationce_14; "RegistrationCertHelper::GenerateDeviceJ"...
0x18005dc98  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005dc9f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005dca4  mov     r15, [rbp+3Fh+pszX500]
0x18005dca8  jmp     loc_18005DBEF
0x18005dcad  mov     r15, [rbp+3Fh+pszX500]
0x18005dcb1  lea     rax, [rbp+3Fh+var_B8]
0x18005dcb5  xor     r9d, r9d; pvReserved
0x18005dcb8  mov     [rsp+110h+ppszError], rdi; ppszError
0x18005dcbd  mov     [rsp+110h+pcbEncoded], rax; pcbEncoded
0x18005dcc2  mov     rdx, r15; pszX500
0x18005dcc5  mov     [rsp+110h+pbEncoded], rdi; pbEncoded
0x18005dcca  lea     ebx, [r9+1]
0x18005dcce  mov     ecx, ebx; dwCertEncodingType
0x18005dcd0  lea     r8d, [r9+2]; dwStrType
0x18005dcd4  call    cs:__imp_CertStrToNameW
0x18005dcda  test    eax, eax
0x18005dcdc  jnz     short loc_18005DD11
0x18005dcde  call    cs:__imp_GetLastError
0x18005dce4  mov     edi, eax
0x18005dce6  test    eax, eax
0x18005dce8  jz      short loc_18005DD11
0x18005dcea  mov     r9d, eax
0x18005dced  lea     r8, aCertstrtonamew_0; "CertStrToNameW"
0x18005dcf4  lea     rdx, aRegistrationce_14; "RegistrationCertHelper::GenerateDeviceJ"...
0x18005dcfb  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18005dd02  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005dd07  mov     r12, [rsp+110h+Block]
0x18005dd0c  jmp     loc_18005E024
0x18005dd11  mov     ecx, [rbp+3Fh+var_B8]; unsigned __int64
0x18005dd14  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005dd1b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005dd20  mov     [rbp+3Fh+pszX500], rax
0x18005dd24  mov     rsi, rax
0x18005dd27  test    rax, rax
0x18005dd2a  jnz     short loc_18005DD4E
0x18005dd2c  lea     rdx, aRegistrationce_14; "RegistrationCertHelper::GenerateDeviceJ"...
0x18005dd33  mov     ebx, 8007000Eh
0x18005dd38  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18005dd3f  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18005dd44  mov     r12, [rsp+110h+Block]
0x18005dd49  jmp     loc_18005E020
0x18005dd4e  xor     r9d, r9d; pvReserved
0x18005dd51  mov     [rsp+110h+ppszError], r14; ppszError
0x18005dd56  lea     rax, [rbp+3Fh+var_B8]
0x18005dd5a  mov     rdx, r15; pszX500
0x18005dd5d  mov     [rsp+110h+pcbEncoded], rax; pcbEncoded
0x18005dd62  mov     ecx, ebx; dwCertEncodingType
0x18005dd64  mov     [rsp+110h+pbEncoded], rsi; pbEncoded
0x18005dd69  lea     r8d, [r9+2]; dwStrType
0x18005dd6d  call    cs:__imp_CertStrToNameW
0x18005dd73  test    eax, eax
0x18005dd75  jnz     short loc_18005DD87
0x18005dd77  call    cs:__imp_GetLastError
0x18005dd7d  mov     edi, eax
0x18005dd7f  test    eax, eax
0x18005dd81  jnz     loc_18005DCEA
0x18005dd87  mov     eax, [rbp+3Fh+var_B8]
0x18005dd8a  lea     rcx, [rbp+3Fh+SystemTime]; lpSystemTime
0x18005dd8e  mov     [rbp+3Fh+pSubjectIssuerBlob.cbData], eax
0x18005dd91  mov     [rbp+3Fh+pSubjectIssuerBlob.pbData], rsi
0x18005dd95  call    cs:__imp_GetSystemTime
0x18005dd9b  lea     r8, [rbp+3Fh+pEndTime]; struct _SYSTEMTIME *
0x18005dd9f  lea     rcx, [rbp+3Fh+SystemTime]; struct _SYSTEMTIME *
0x18005dda3  call    ?SystemTimeAddSeconds@@YAJPEBU_SYSTEMTIME@@_KPEAU1@@Z; SystemTimeAddSeconds(_SYSTEMTIME const *,unsigned __int64,_SYSTEMTIME *)
0x18005dda8  mov     ebx, eax
0x18005ddaa  test    eax, eax
0x18005ddac  jns     short loc_18005DDD0
0x18005ddae  lea     r8, aSystemtimeaddy; "SystemTimeAddYears"
0x18005ddb5  lea     rdx, aRegistrationce_14; "RegistrationCertHelper::GenerateDeviceJ"...
0x18005ddbc  mov     r9d, eax
0x18005ddbf  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005ddc6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005ddcb  jmp     loc_18005DD44
0x18005ddd0  mov     ecx, [rbp+3Fh+arg_20]
0x18005ddd3  test    ecx, ecx
0x18005ddd5  jnz     short loc_18005DE29
0x18005ddd7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EntraIdClientPlutonKsp@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EntraIdClientPlutonKsp@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EntraIdClientPlutonKsp> `wil::Feature<__WilFeatureTraits_Feature_EntraIdClientPlutonKsp>::GetImpl(void)'::`2'::impl
0x18005ddde  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EntraIdClientPlutonKsp@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EntraIdClientPlutonKsp>::__private_IsEnabled(void)
0x18005dde3  mov     ecx, [r12]
0x18005dde7  lea     r9, [rbp+3Fh+hCryptProvOrNCryptKey]
0x18005ddeb  test    al, al
0x18005dded  jz      short loc_18005DDFB
0x18005ddef  mov     edx, [r12+4]
0x18005ddf4  call    ?GetNCryptKeyHandleNew@RegistrationKeyHelper@@SAJW4_KEY_POLICY@@W4_HARDWARE_POLICY@@PEBGPEA_K@Z; RegistrationKeyHelper::GetNCryptKeyHandleNew(_KEY_POLICY,_HARDWARE_POLICY,ushort const *,unsigned __int64 *)
0x18005ddf9  jmp     short loc_18005DE00
0x18005ddfb  call    ?GetNCryptKeyHandle@RegistrationKeyHelper@@SAJW4_KEY_POLICY@@W4_HARDWARE_POLICY@@PEBGPEA_K@Z; RegistrationKeyHelper::GetNCryptKeyHandle(_KEY_POLICY,_HARDWARE_POLICY,ushort const *,unsigned __int64 *)
0x18005de00  test    eax, eax
0x18005de02  js      short loc_18005DE0E
0x18005de04  mov     esi, 1
0x18005de09  jmp     loc_18005DE8F
0x18005de0e  mov     r8d, eax
0x18005de11  lea     rdx, aRegistrationce_14; "RegistrationCertHelper::GenerateDeviceJ"...
0x18005de18  lea     rcx, aSUnableToOpenT; "%s: Unable to open the existing auto si"...
0x18005de1f  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18005de24  mov     ecx, 1
0x18005de29  xor     eax, eax
0x18005de2b  mov     [rsp+110h+var_D0], r14
0x18005de30  cmp     dword ptr [r12+8], 1
0x18005de36  lea     rdx, [rbp+3Fh+var_98]
0x18005de3a  mov     [rsp+110h+pExtensions], rdx
0x18005de3f  lea     r9, pszKeyName; "6b30069e-b381-42cc-9fae-421915a9e9f3"
0x18005de46  lea     rdx, [rbp+3Fh+hCryptProvOrNCryptKey]
0x18005de4a  setz    al
0x18005de4d  mov     [rsp+110h+ppszError], rdx
0x18005de52  mov     edx, [r12+4]
0x18005de57  mov     dword ptr [rsp+110h+pcbEncoded], ecx
0x18005de5b  mov     ecx, [r12]
0x18005de5f  mov     dword ptr [rsp+110h+pbEncoded], eax
0x18005de63  call    ?CreateNCryptKeyHandle@RegistrationKeyHelper@@SAJW4_KEY_POLICY@@W4_HARDWARE_POLICY@@KPEBGHHPEA_KPEAPEAGPEAH@Z; RegistrationKeyHelper::CreateNCryptKeyHandle(_KEY_POLICY,_HARDWARE_POLICY,ulong,ushort const *,int,int,unsigned __int64 *,ushort * *,int *)
0x18005de68  lea     rdx, aRegistrationce_14; "RegistrationCertHelper::GenerateDeviceJ"...
0x18005de6f  mov     ebx, eax
0x18005de71  test    eax, eax
0x18005de73  jns     short loc_18005DE81
0x18005de75  lea     r8, aRegistrationke_5; "RegistrationKeyHelper::CreateNCryptKeyH"...
0x18005de7c  jmp     loc_18005DDBC
0x18005de81  xor     esi, esi
0x18005de83  lea     rcx, aSNewSigningKey; "%s: New signing key generated for sync'"...
0x18005de8a  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18005de8f  mov     rcx, [rbp+3Fh+hCryptProvOrNCryptKey]; hCryptProvOrNCryptKey
0x18005de93  lea     rax, [rbp+3Fh+pEndTime]
0x18005de97  mov     [rsp+110h+pExtensions], r14; pExtensions
0x18005de9c  lea     rdx, [rbp+3Fh+pSubjectIssuerBlob]; pSubjectIssuerBlob
0x18005dea0  mov     [rsp+110h+ppszError], rax; pEndTime
0x18005dea5  xor     r9d, r9d; pKeyProvInfo
0x18005dea8  lea     rax, [rbp+3Fh+pSignatureAlgorithm]
0x18005deac  mov     [rsp+110h+pcbEncoded], r14; pStartTime
0x18005deb1  mov     [rsp+110h+pbEncoded], rax; pSignatureAlgorithm
0x18005deb6  lea     r8d, [r9+2]; dwFlags
0x18005deba  call    cs:__imp_CertCreateSelfSignCertificate
0x18005dec0  mov     r14, rax
0x18005dec3  test    rax, rax
0x18005dec6  jnz     loc_18005DFC7
0x18005decc  test    esi, esi
0x18005dece  jz      loc_18005DFA7
0x18005ded4  call    cs:__imp_GetLastError
0x18005deda  mov     r8d, eax
0x18005dedd  lea     rdx, aRegistrationce_14; "RegistrationCertHelper::GenerateDeviceJ"...
0x18005dee4  lea     rcx, aSCannotGenerat_1; "%s: Cannot generate auto signing cert u"...
0x18005deeb  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18005def0  mov     edx, [r12+4]
0x18005def5  lea     rax, [rbp+3Fh+var_98]
0x18005def9  xor     esi, esi
0x18005defb  lea     r9, pszKeyName; "6b30069e-b381-42cc-9fae-421915a9e9f3"
0x18005df02  cmp     dword ptr [r12+8], 1
0x18005df08  mov     ecx, esi
0x18005df0a  mov     [rsp+110h+var_D0], rsi
0x18005df0f  mov     [rsp+110h+pExtensions], rax
0x18005df14  setz    cl
0x18005df17  lea     rax, [rbp+3Fh+hCryptProvOrNCryptKey]
0x18005df1b  mov     [rsp+110h+ppszError], rax
0x18005df20  mov     dword ptr [rsp+110h+pcbEncoded], 1
0x18005df28  mov     dword ptr [rsp+110h+pbEncoded], ecx
0x18005df2c  mov     ecx, [r12]
0x18005df30  call    ?CreateNCryptKeyHandle@RegistrationKeyHelper@@SAJW4_KEY_POLICY@@W4_HARDWARE_POLICY@@KPEBGHHPEA_KPEAPEAGPEAH@Z; RegistrationKeyHelper::CreateNCryptKeyHandle(_KEY_POLICY,_HARDWARE_POLICY,ulong,ushort const *,int,int,unsigned __int64 *,ushort * *,int *)
0x18005df35  lea     rdx, aRegistrationce_14; "RegistrationCertHelper::GenerateDeviceJ"...
0x18005df3c  mov     ebx, eax
0x18005df3e  test    eax, eax
0x18005df40  jns     short loc_18005DF62
0x18005df42  mov     r9d, eax
0x18005df45  lea     r8, aRegistrationke_5; "RegistrationKeyHelper::CreateNCryptKeyH"...
0x18005df4c  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005df53  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005df58  mov     r12, [rsp+110h+Block]
0x18005df5d  jmp     loc_18005E01C
0x18005df62  lea     rcx, aSNewSigningKey; "%s: New signing key generated for sync'"...
0x18005df69  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18005df6e  mov     rcx, [rbp+3Fh+hCryptProvOrNCryptKey]; hCryptProvOrNCryptKey
0x18005df72  lea     rax, [rbp+3Fh+pEndTime]
0x18005df76  mov     [rsp+110h+pExtensions], rsi; pExtensions
0x18005df7b  lea     rdx, [rbp+3Fh+pSubjectIssuerBlob]; pSubjectIssuerBlob
0x18005df7f  mov     [rsp+110h+ppszError], rax; pEndTime
0x18005df84  xor     r9d, r9d; pKeyProvInfo
0x18005df87  lea     rax, [rbp+3Fh+pSignatureAlgorithm]
0x18005df8b  mov     [rsp+110h+pcbEncoded], rsi; pStartTime
0x18005df90  mov     [rsp+110h+pbEncoded], rax; pSignatureAlgorithm
0x18005df95  lea     r8d, [r9+2]; dwFlags
0x18005df99  call    cs:__imp_CertCreateSelfSignCertificate
0x18005df9f  mov     r14, rax
0x18005dfa2  test    rax, rax
0x18005dfa5  jnz     short loc_18005DFC7
0x18005dfa7  call    cs:__imp_GetLastError
0x18005dfad  mov     r8d, eax
0x18005dfb0  lea     rdx, aRegistrationce_14; "RegistrationCertHelper::GenerateDeviceJ"...
0x18005dfb7  lea     rcx, aSCannotGenerat_0; "%s: Cannot generate auto signing cert u"...
0x18005dfbe  mov     edi, eax
0x18005dfc0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005dfc5  jmp     short loc_18005DF58
0x18005dfc7  mov     esi, [r14+10h]
0x18005dfcb  lea     r8, [rbp+3Fh+var_A0]; char **
0x18005dfcf  mov     rcx, [r14+8]; Source
0x18005dfd3  mov     edx, esi; SourceSize
0x18005dfd5  call    ?CopyStringA@@YAJPEBD_KPEAPEAD@Z; CopyStringA(char const *,unsigned __int64,char * *)
0x18005dfda  mov     ebx, eax
0x18005dfdc  test    eax, eax
0x18005dfde  jns     short loc_18005E00B
0x18005dfe0  mov     r9d, eax
0x18005dfe3  lea     r8, aCopystringa; "CopyStringA"
0x18005dfea  lea     rdx, aRegistrationce_14; "RegistrationCertHelper::GenerateDeviceJ"...
0x18005dff1  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005dff8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005dffd  mov     rcx, [rbp+3Fh+var_A0]
0x18005e001  mov     [rsp+110h+Block], rcx
0x18005e006  jmp     loc_18005DF58
0x18005e00b  mov     rax, [rbp+3Fh+var_A0]
0x18005e00f  xor     r12d, r12d
0x18005e012  mov     [r13+0], rax
0x18005e016  mov     rax, [rbp+3Fh+var_80]
0x18005e01a  mov     [rax], esi
0x18005e01c  mov     rsi, [rbp+3Fh+pszX500]
0x18005e020  test    edi, edi
0x18005e022  jz      short loc_18005E035
0x18005e024  test    edi, edi
0x18005e026  jg      short loc_18005E02C
0x18005e028  mov     ebx, edi
0x18005e02a  jmp     short loc_18005E035
  ... truncated ...
```
