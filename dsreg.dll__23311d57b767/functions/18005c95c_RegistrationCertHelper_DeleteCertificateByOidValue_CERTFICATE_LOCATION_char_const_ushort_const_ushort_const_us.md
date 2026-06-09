# RegistrationCertHelper::DeleteCertificateByOidValue(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18005c95c`
- end: `0x18005ce0b`
- name: `?DeleteCertificateByOidValue@RegistrationCertHelper@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22@Z`
- size: `1199`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18005d424`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x1800086b0`
- `0x18000bac0`
- `0x18000c550`
- `0x18000cc2c`
- `0x180012948`
- `0x180017fd0`
- `0x18001b560`
- `0x1800307c4`
- `0x18003b434`
- `0x180043ef8`
- `0x18005c95c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ca07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cc9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ccc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cdd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ca07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cc9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ccc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cdd9`
- `CRYPT32!CertOpenStore` at `0x18005c9f8`
- `CRYPT32!CertOpenStore` at `0x18005c9f8`
- `CRYPT32!CertFindCertificateInStore` at `0x18005ca61`
- `CRYPT32!CertFindCertificateInStore` at `0x18005ca61`
- `CRYPT32!CertCloseStore` at `0x18005cdcf`
- `CRYPT32!CertCloseStore` at `0x18005cdcf`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18005cc8c`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18005cc8c`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18005ccbf`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18005ccbf`
- `CRYPT32!CertFreeCertificateContext` at `0x18005cdb1`
- `CRYPT32!CertFreeCertificateContext` at `0x18005cdbf`
- `CRYPT32!CertFreeCertificateContext` at `0x18005cdb1`
- `CRYPT32!CertFreeCertificateContext` at `0x18005cdbf`

## string_xrefs

- `0x18005cd67`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18005cced`: `StringCompare`
- `0x18005ca13`: `CertOpenStore`
- `0x18005cd4f`: `RegistrationCertHelper::DeletePrivateKeyByCertificate`
- `0x18005c99a`: `RegistrationCertHelper::DeleteCertificateByOidValue`
- `0x18005ca1a`: `RegistrationCertHelper::DeleteCertificateByOidValue`
- `0x18005ca3e`: `RegistrationCertHelper::DeleteCertificateByOidValue`
- `0x18005cd40`: `CertDeleteCertificateFromStore`
- `0x18005ccd8`: `%s: Certificate deleted`

## pseudocode

```c
__int64 RegistrationCertHelper::DeleteCertificateByOidValue(int a1, ...)
{
  wchar_t *v1; // r13
  WCHAR *v2; // r12
  PCCERT_CONTEXT pPrevCertContext; // r15
  const CERT_CONTEXT *v4; // r14
  void *v5; // rsi
  unsigned int v6; // ebx
  int v7; // esi
  HCERTSTORE v8; // rax
  DWORD LastError; // eax
  const wchar_t *v10; // r8
  __int64 v11; // r14
  int DoesExtensionWithValueExist; // eax
  int TenantId; // eax
  const wchar_t *v14; // rax
  unsigned __int16 *v15; // r9
  const wchar_t *v16; // r8
  int DeviceId; // eax
  const wchar_t *v18; // rax
  const wchar_t *v19; // r8
  unsigned __int16 *v20; // rbx
  unsigned __int16 *v21; // rax
  int v22; // eax
  const unsigned __int16 *v23; // r8
  DWORD v24; // eax
  int v26; // [rsp+30h] [rbp-20h] BYREF
  HCERTSTORE v27; // [rsp+38h] [rbp-18h]
  void *Block; // [rsp+40h] [rbp-10h] BYREF
  LPCWCH lpString1; // [rsp+48h] [rbp-8h] BYREF
  unsigned __int16 *v30; // [rsp+98h] [rbp+48h] BYREF
  va_list va; // [rsp+98h] [rbp+48h]
  __int64 v32; // [rsp+A0h] [rbp+50h]
  unsigned __int16 *v33; // [rsp+A8h] [rbp+58h]
  __int64 v34; // [rsp+B0h] [rbp+60h] BYREF
  va_list va1; // [rsp+B0h] [rbp+60h]
  va_list va2; // [rsp+B8h] [rbp+68h] BYREF

  va_start(va2, a1);
  va_start(va1, a1);
  va_start(va, a1);
  v30 = va_arg(va1, unsigned __int16 *);
  v32 = va_arg(va1, _QWORD);
  v33 = va_arg(va1, unsigned __int16 *);
  va_copy(va2, va1);
  v34 = va_arg(va2, _QWORD);
  v1 = 0;
  v2 = 0;
  pPrevCertContext = 0;
  Block = 0;
  v4 = 0;
  lpString1 = 0;
  if ( !v32 )
  {
    v5 = 0;
    v6 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationCertHelper::DeleteCertificateByOidValue",
      L"pcszOidValue");
    Logger::WriteNullOrEmptyParameterFailureEvent(
      L"RegistrationCertHelper::DeleteCertificateByOidValue",
      L"pcszOidValue");
    goto LABEL_56;
  }
  v7 = 0;
  v8 = CertOpenStore((LPCSTR)0xA, 0, 0, a1 != 0 ? 0x20000 : 0x10000, L"My");
  v27 = v8;
  if ( v8 )
  {
LABEL_8:
    v6 = 0;
    while ( 1 )
    {
      v4 = 0;
      pPrevCertContext = CertFindCertificateInStore(v8, 0x10001u, 0, 0, 0, pPrevCertContext);
      if ( !pPrevCertContext )
        break;
      LODWORD(v30) = 0;
      v11 = v32;
      LODWORD(v34) = 1;
      v26 = 1;
      DoesExtensionWithValueExist = CertificateUtil::DoesExtensionWithValueExist(
                                      "1.2.840.113556.1.5.284.7",
                                      v32,
                                      0,
                                      pPrevCertContext,
                                      (unsigned __int16 **)va);
      v6 = DoesExtensionWithValueExist;
      if ( DoesExtensionWithValueExist < 0 )
      {
        v23 = L"CertificateUtil::DoesExtensionWithValueExist";
LABEL_49:
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"RegistrationCertHelper::DeleteCertificateByOidValue",
          v23,
          (unsigned int)DoesExtensionWithValueExist);
LABEL_50:
        v4 = 0;
        break;
      }
      if ( (_DWORD)v30 )
      {
        Logger::TraceVerbose(
          (wchar_t *)L"%s: Found certificate with OID: '%hs' and value: '%s'",
          L"RegistrationCertHelper::DeleteCertificateByOidValue",
          "1.2.840.113556.1.5.284.7",
          v11);
        if ( !(unsigned int)IsEmptyString(v33) )
        {
          TenantId = RegistrationCertStatus::GetTenantId(pPrevCertContext, (unsigned __int16 **)&Block, 0);
          v6 = TenantId;
          if ( TenantId < 0 )
          {
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"RegistrationCertHelper::DeleteCertificateByOidValue",
              L"RegistrationCertStatus::GetTenantId",
              (unsigned int)TenantId);
            v1 = (wchar_t *)Block;
            goto LABEL_50;
          }
          v1 = (wchar_t *)Block;
          DoesExtensionWithValueExist = StringCompare((LPCWCH)Block, v33, 1u, (int *)va1);
          v6 = DoesExtensionWithValueExist;
          if ( DoesExtensionWithValueExist < 0 )
            goto LABEL_42;
          v14 = L"TRUE";
          if ( !(_DWORD)v34 )
            v14 = L"FALSE";
          v15 = L"<NULL>";
          v16 = L"<NULL>";
          if ( v33 )
            v15 = v33;
          if ( v1 )
            v16 = v1;
          Logger::TraceVerbose(
            (wchar_t *)L"%s: Certitifcate tenant ID: '%s'. Target tenant ID '%s'. Matching: %s.",
            L"RegistrationCertHelper::DeleteCertificateByOidValue",
            v16,
            v15,
            v14);
          operator delete(v1);
          v1 = 0;
          Block = 0;
        }
        if ( !(unsigned int)IsEmptyString(0) )
        {
          DeviceId = RegistrationCertStatus::GetDeviceId(pPrevCertContext, (unsigned __int16 **)&lpString1);
          v6 = DeviceId;
          if ( DeviceId < 0 )
          {
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"RegistrationCertHelper::DeleteCertificateByOidValue",
              L"RegistrationCertStatus::GetDeviceId",
              (unsigned int)DeviceId);
            v2 = (WCHAR *)lpString1;
            goto LABEL_50;
          }
          v2 = (WCHAR *)lpString1;
          DoesExtensionWithValueExist = StringCompare(lpString1, 0, 1u, &v26);
          v6 = DoesExtensionWithValueExist;
          if ( DoesExtensionWithValueExist < 0 )
          {
LABEL_42:
            v23 = L"StringCompare";
            goto LABEL_49;
          }
          v18 = L"TRUE";
          if ( !v26 )
            v18 = L"FALSE";
          v19 = L"<NULL>";
          if ( v2 )
            v19 = v2;
          Logger::TraceVerbose(
            (wchar_t *)L"%s: Certitifcate device ID: '%s'. Target device ID '%s'. Matching: %s.",
            L"RegistrationCertHelper::DeleteCertificateByOidValue",
            v19,
            L"<NULL>",
            v18);
          operator delete(v2);
          v2 = 0;
          lpString1 = 0;
        }
      }
      else
      {
        Logger::TraceVerbose(
          (wchar_t *)L"%s: The certificate does not contain the OID: '%hs' with this value: '%s'",
          L"RegistrationCertHelper::DeleteCertificateByOidValue",
          "1.2.840.113556.1.5.284.7",
          v11);
      }
      v8 = v27;
      if ( (_DWORD)v30 && (_DWORD)v34 && v26 )
      {
        v30 = 0;
        CertificateUtil::GetCertificateThumbprint(pPrevCertContext, (unsigned __int16 **)va);
        v20 = v30;
        v21 = L"N/A";
        if ( v30 )
          v21 = v30;
        Logger::TraceVerbose(
          (wchar_t *)L"%s: Deleting certificate with OID '%hs' and value '%s' (thumbprint: %s)...",
          L"RegistrationCertHelper::DeleteCertificateByOidValue",
          "1.2.840.113556.1.5.284.7",
          v11,
          v21);
        operator delete(v20);
        v4 = CertDuplicateCertificateContext(pPrevCertContext);
        if ( !v4 )
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError )
          {
            v10 = L"CertDuplicateCertificateContext";
            goto LABEL_6;
          }
        }
        v22 = RegistrationCertHelper::DeletePrivateKeyByCertificate(v4);
        v6 = v22;
        if ( v22 < 0 )
        {
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"RegistrationCertHelper::DeleteCertificateByOidValue",
            L"RegistrationCertHelper::DeletePrivateKeyByCertificate",
            (unsigned int)v22);
          break;
        }
        if ( !CertDeleteCertificateFromStore(v4) )
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError )
          {
            v10 = L"CertDeleteCertificateFromStore";
            goto LABEL_6;
          }
        }
        Logger::TraceInformation(L"%s: Certificate deleted", L"RegistrationCertHelper::DeleteCertificateByOidValue");
        v8 = v27;
      }
    }
    if ( !v7 )
      goto LABEL_55;
    goto LABEL_52;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( !LastError )
  {
    v8 = v27;
    goto LABEL_8;
  }
  v10 = L"CertOpenStore";
LABEL_6:
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"RegistrationCertHelper::DeleteCertificateByOidValue",
    v10,
    LastError);
LABEL_52:
  if ( v7 > 0 )
    v6 = (unsigned __int16)v7 | 0x80070000;
  else
    v6 = v7;
LABEL_55:
  v5 = v27;
LABEL_56:
  operator delete(v1);
  operator delete(v2);
  if ( v4 )
    CertFreeCertificateContext(v4);
  if ( pPrevCertContext )
    CertFreeCertificateContext(pPrevCertContext);
  if ( v5 && !CertCloseStore(v5, 0) )
  {
    v24 = GetLastError();
    Logger::TraceWarning(
      (wchar_t *)L"%s: CertCloseStore failed with error code: 0x%08x. Igored.",
      L"RegistrationCertHelper::DeleteCertificateByOidValue",
      v24);
  }
  return v6;
}

```

## disassembly

```asm
0x18005c95c  mov     rax, rsp
0x18005c95f  mov     [rax+8], rbx
0x18005c963  mov     [rax+20h], r9
0x18005c967  mov     [rax+18h], r8
0x18005c96b  mov     [rax+10h], rdx
0x18005c96f  push    rbp
0x18005c970  push    rsi
0x18005c971  push    rdi
0x18005c972  push    r12
0x18005c974  push    r13
0x18005c976  push    r14
0x18005c978  push    r15
0x18005c97a  mov     rbp, rsp
0x18005c97d  sub     rsp, 50h
0x18005c981  xor     r13d, r13d
0x18005c984  xor     r12d, r12d
0x18005c987  xor     r15d, r15d
0x18005c98a  mov     [rbp+Block], r13
0x18005c98e  xor     r14d, r14d
0x18005c991  mov     [rbp+lpString1], r12
0x18005c995  test    r8, r8
0x18005c998  jnz     short loc_18005C9D2
0x18005c99a  lea     rdi, aRegistrationce_13; "RegistrationCertHelper::DeleteCertifica"...
0x18005c9a1  xor     esi, esi
0x18005c9a3  mov     rdx, rdi
0x18005c9a6  lea     r8, aPcszoidvalue; "pcszOidValue"
0x18005c9ad  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18005c9b4  mov     ebx, 80070057h
0x18005c9b9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005c9be  lea     rdx, aPcszoidvalue; "pcszOidValue"
0x18005c9c5  mov     rcx, rdi; unsigned __int16 *
0x18005c9c8  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18005c9cd  jmp     loc_18005CD99
0x18005c9d2  mov     eax, 10000h
0x18005c9d7  xor     esi, esi
0x18005c9d9  neg     ecx
0x18005c9db  sbb     r9d, r9d
0x18005c9de  xor     r8d, r8d; hCryptProv
0x18005c9e1  and     r9d, eax
0x18005c9e4  lea     ecx, [rsi+0Ah]; lpszStoreProvider
0x18005c9e7  add     r9d, eax; dwFlags
0x18005c9ea  xor     edx, edx; dwEncodingType
0x18005c9ec  lea     rax, aMy; "My"
0x18005c9f3  mov     [rsp+50h+pvPara], rax; pvPara
0x18005c9f8  call    cs:__imp_CertOpenStore
0x18005c9fe  mov     [rbp+var_18], rax
0x18005ca02  test    rax, rax
0x18005ca05  jnz     short loc_18005CA3C
0x18005ca07  call    cs:__imp_GetLastError
0x18005ca0d  mov     esi, eax
0x18005ca0f  test    eax, eax
0x18005ca11  jz      short loc_18005CA38
0x18005ca13  lea     r8, aCertopenstore_0; "CertOpenStore"
0x18005ca1a  lea     rdi, aRegistrationce_13; "RegistrationCertHelper::DeleteCertifica"...
0x18005ca21  mov     r9d, eax
0x18005ca24  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18005ca2b  mov     rdx, rdi
0x18005ca2e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005ca33  jmp     loc_18005CD84
0x18005ca38  mov     rax, [rbp+var_18]
0x18005ca3c  xor     ebx, ebx
0x18005ca3e  lea     rdi, aRegistrationce_13; "RegistrationCertHelper::DeleteCertifica"...
0x18005ca45  mov     [rsp+50h+pPrevCertContext], r15; pPrevCertContext
0x18005ca4a  xor     r9d, r9d; dwFindType
0x18005ca4d  xor     r8d, r8d; dwFindFlags
0x18005ca50  mov     [rsp+50h+pvPara], 0; pvFindPara
0x18005ca59  mov     edx, 10001h; dwCertEncodingType
0x18005ca5e  mov     rcx, rax; hCertStore
0x18005ca61  call    cs:__imp_CertFindCertificateInStore
0x18005ca67  xor     r14d, r14d
0x18005ca6a  mov     r15, rax
0x18005ca6d  test    rax, rax
0x18005ca70  jz      loc_18005CD80
0x18005ca76  lea     eax, [r14+1]
0x18005ca7a  mov     dword ptr [rbp+arg_8], r14d
0x18005ca7e  mov     r14, [rbp+arg_10]
0x18005ca82  lea     rcx, a12840113556152_1; "1.2.840.113556.1.5.284.7"
0x18005ca89  mov     dword ptr [rbp+arg_20], eax
0x18005ca8c  mov     r9, r15
0x18005ca8f  mov     [rbp+var_20], eax
0x18005ca92  xor     r8d, r8d
0x18005ca95  lea     rax, [rbp+arg_8]
0x18005ca99  mov     rdx, r14
0x18005ca9c  mov     [rsp+50h+pvPara], rax
0x18005caa1  call    ?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z; CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)
0x18005caa6  mov     ebx, eax
0x18005caa8  mov     rdx, rdi
0x18005caab  test    eax, eax
0x18005caad  js      loc_18005CD67
0x18005cab3  cmp     dword ptr [rbp+arg_8], 0
0x18005cab7  lea     r8, a12840113556152_1; "1.2.840.113556.1.5.284.7"
0x18005cabe  mov     r9, r14
0x18005cac1  jz      loc_18005CC0F
0x18005cac7  lea     rcx, aSFoundCertific; "%s: Found certificate with OID: '%hs' a"...
0x18005cace  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005cad3  mov     rcx, [rbp+arg_18]; unsigned __int16 *
0x18005cad7  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18005cadc  test    eax, eax
0x18005cade  jnz     loc_18005CB7A
0x18005cae4  xor     r8d, r8d; int *
0x18005cae7  lea     rdx, [rbp+Block]; unsigned __int16 **
0x18005caeb  mov     rcx, r15; struct _CERT_CONTEXT *
0x18005caee  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x18005caf3  mov     ebx, eax
0x18005caf5  test    eax, eax
0x18005caf7  js      loc_18005CCF6
0x18005cafd  mov     r13, [rbp+Block]
0x18005cb01  lea     r9, [rbp+arg_20]; int *
0x18005cb05  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x18005cb09  mov     rcx, r13; lpString1
0x18005cb0c  mov     r8d, 1; unsigned int
0x18005cb12  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x18005cb17  mov     ebx, eax
0x18005cb19  mov     rdx, rdi
0x18005cb1c  test    eax, eax
0x18005cb1e  js      loc_18005CCED
0x18005cb24  cmp     dword ptr [rbp+arg_20], 0
0x18005cb28  lea     rcx, aFalse_0; "FALSE"
0x18005cb2f  lea     rax, aTrue_0; "TRUE"
0x18005cb36  cmovz   rax, rcx
0x18005cb3a  lea     r9, aNull_2; "<NULL>"
0x18005cb41  mov     rcx, [rbp+arg_18]
0x18005cb45  lea     r8, aNull_2; "<NULL>"
0x18005cb4c  test    rcx, rcx
0x18005cb4f  mov     [rsp+50h+pvPara], rax
0x18005cb54  cmovnz  r9, rcx
0x18005cb58  test    r13, r13
0x18005cb5b  lea     rcx, aSCertitifcateT; "%s: Certitifcate tenant ID: '%s'. Targe"...
0x18005cb62  cmovnz  r8, r13
0x18005cb66  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005cb6b  mov     rcx, r13; Block
0x18005cb6e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005cb73  xor     r13d, r13d
0x18005cb76  mov     [rbp+Block], r13
0x18005cb7a  xor     ecx, ecx; unsigned __int16 *
0x18005cb7c  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18005cb81  test    eax, eax
0x18005cb83  jnz     loc_18005CC1B
0x18005cb89  lea     rdx, [rbp+lpString1]; unsigned __int16 **
0x18005cb8d  mov     rcx, r15; struct _CERT_CONTEXT *
0x18005cb90  call    ?GetDeviceId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; RegistrationCertStatus::GetDeviceId(_CERT_CONTEXT const *,ushort * *)
0x18005cb95  mov     ebx, eax
0x18005cb97  test    eax, eax
0x18005cb99  js      loc_18005CD15
0x18005cb9f  mov     r12, [rbp+lpString1]
0x18005cba3  lea     r9, [rbp+var_20]; int *
0x18005cba7  xor     edx, edx; unsigned __int16 *
0x18005cba9  mov     rcx, r12; lpString1
0x18005cbac  lea     r8d, [rdx+1]; unsigned int
0x18005cbb0  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x18005cbb5  mov     ebx, eax
0x18005cbb7  mov     rdx, rdi
0x18005cbba  test    eax, eax
0x18005cbbc  js      loc_18005CCED
0x18005cbc2  cmp     [rbp+var_20], 0
0x18005cbc6  lea     rcx, aFalse_0; "FALSE"
0x18005cbcd  lea     rax, aTrue_0; "TRUE"
0x18005cbd4  cmovz   rax, rcx
0x18005cbd8  lea     r8, aNull_2; "<NULL>"
0x18005cbdf  test    r12, r12
0x18005cbe2  mov     [rsp+50h+pvPara], rax
0x18005cbe7  lea     r9, aNull_2; "<NULL>"
0x18005cbee  cmovnz  r8, r12
0x18005cbf2  lea     rcx, aSCertitifcateD; "%s: Certitifcate device ID: '%s'. Targe"...
0x18005cbf9  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005cbfe  mov     rcx, r12; Block
0x18005cc01  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005cc06  xor     r12d, r12d
0x18005cc09  mov     [rbp+lpString1], r12
0x18005cc0d  jmp     short loc_18005CC1B
0x18005cc0f  lea     rcx, aSTheCertificat_2; "%s: The certificate does not contain th"...
0x18005cc16  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005cc1b  cmp     dword ptr [rbp+arg_8], 0
0x18005cc1f  mov     rax, [rbp+var_18]
0x18005cc23  jz      loc_18005CA45
0x18005cc29  cmp     dword ptr [rbp+arg_20], 0
0x18005cc2d  jz      loc_18005CA45
0x18005cc33  cmp     [rbp+var_20], 0
0x18005cc37  jz      loc_18005CA45
0x18005cc3d  lea     rdx, [rbp+arg_8]; unsigned __int16 **
0x18005cc41  mov     [rbp+arg_8], 0
0x18005cc49  mov     rcx, r15; pCertContext
0x18005cc4c  call    ?GetCertificateThumbprint@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::GetCertificateThumbprint(_CERT_CONTEXT const *,ushort * *)
0x18005cc51  mov     rbx, [rbp+arg_8]
0x18005cc55  lea     rax, aNA; "N/A"
0x18005cc5c  test    rbx, rbx
0x18005cc5f  lea     r8, a12840113556152_1; "1.2.840.113556.1.5.284.7"
0x18005cc66  mov     r9, r14
0x18005cc69  lea     rcx, aSDeletingCerti; "%s: Deleting certificate with OID '%hs'"...
0x18005cc70  cmovnz  rax, rbx
0x18005cc74  mov     rdx, rdi
0x18005cc77  mov     [rsp+50h+pvPara], rax
0x18005cc7c  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005cc81  mov     rcx, rbx; Block
0x18005cc84  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005cc89  mov     rcx, r15; pCertContext
0x18005cc8c  call    cs:__imp_CertDuplicateCertificateContext
0x18005cc92  mov     r14, rax
0x18005cc95  test    rax, rax
0x18005cc98  jnz     short loc_18005CCAA
0x18005cc9a  call    cs:__imp_GetLastError
0x18005cca0  mov     esi, eax
0x18005cca2  test    eax, eax
0x18005cca4  jnz     loc_18005CD34
0x18005ccaa  mov     rcx, r14; pCert
0x18005ccad  call    ?DeletePrivateKeyByCertificate@RegistrationCertHelper@@CAJPEBU_CERT_CONTEXT@@@Z; RegistrationCertHelper::DeletePrivateKeyByCertificate(_CERT_CONTEXT const *)
0x18005ccb2  mov     ebx, eax
0x18005ccb4  test    eax, eax
0x18005ccb6  js      loc_18005CD4C
0x18005ccbc  mov     rcx, r14; pCertContext
0x18005ccbf  call    cs:__imp_CertDeleteCertificateFromStore
0x18005ccc5  test    eax, eax
0x18005ccc7  jnz     short loc_18005CCD5
0x18005ccc9  call    cs:__imp_GetLastError
0x18005cccf  mov     esi, eax
0x18005ccd1  test    eax, eax
0x18005ccd3  jnz     short loc_18005CD40
0x18005ccd5  mov     rdx, rdi
0x18005ccd8  lea     rcx, aSCertificateDe; "%s: Certificate deleted"
0x18005ccdf  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18005cce4  mov     rax, [rbp+var_18]
0x18005cce8  jmp     loc_18005CA45
0x18005cced  lea     r8, aStringcompare; "StringCompare"
0x18005ccf4  jmp     short loc_18005CD6E
0x18005ccf6  mov     r9d, eax
0x18005ccf9  lea     r8, aRegistrationce_21; "RegistrationCertStatus::GetTenantId"
0x18005cd00  mov     rdx, rdi
0x18005cd03  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005cd0a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005cd0f  mov     r13, [rbp+Block]
0x18005cd13  jmp     short loc_18005CD7D
0x18005cd15  mov     r9d, eax
0x18005cd18  lea     r8, aRegistrationce_24; "RegistrationCertStatus::GetDeviceId"
0x18005cd1f  mov     rdx, rdi
0x18005cd22  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005cd29  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005cd2e  mov     r12, [rbp+lpString1]
0x18005cd32  jmp     short loc_18005CD7D
0x18005cd34  lea     r8, aCertduplicatec_0; "CertDuplicateCertificateContext"
0x18005cd3b  jmp     loc_18005CA21
0x18005cd40  lea     r8, aCertdeletecert_0; "CertDeleteCertificateFromStore"
0x18005cd47  jmp     loc_18005CA21
0x18005cd4c  mov     r9d, eax
0x18005cd4f  lea     r8, aRegistrationce_0; "RegistrationCertHelper::DeletePrivateKe"...
0x18005cd56  mov     rdx, rdi
0x18005cd59  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005cd60  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005cd65  jmp     short loc_18005CD80
0x18005cd67  lea     r8, aCertificateuti_8; "CertificateUtil::DoesExtensionWithValue"...
0x18005cd6e  mov     r9d, eax
0x18005cd71  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005cd78  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005cd7d  xor     r14d, r14d
0x18005cd80  test    esi, esi
0x18005cd82  jz      short loc_18005CD95
0x18005cd84  test    esi, esi
0x18005cd86  jg      short loc_18005CD8C
0x18005cd88  mov     ebx, esi
0x18005cd8a  jmp     short loc_18005CD95
0x18005cd8c  movzx   ebx, si
0x18005cd8f  or      ebx, 80070000h
0x18005cd95  mov     rsi, [rbp+var_18]
0x18005cd99  mov     rcx, r13; Block
0x18005cd9c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005cda1  mov     rcx, r12; Block
0x18005cda4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005cda9  test    r14, r14
0x18005cdac  jz      short loc_18005CDB7
0x18005cdae  mov     rcx, r14; pCertContext
0x18005cdb1  call    cs:__imp_CertFreeCertificateContext
0x18005cdb7  test    r15, r15
0x18005cdba  jz      short loc_18005CDC5
0x18005cdbc  mov     rcx, r15; pCertContext
0x18005cdbf  call    cs:__imp_CertFreeCertificateContext
0x18005cdc5  test    rsi, rsi
0x18005cdc8  jz      short loc_18005CDF1
0x18005cdca  xor     edx, edx; dwFlags
0x18005cdcc  mov     rcx, rsi; hCertStore
0x18005cdcf  call    cs:__imp_CertCloseStore
0x18005cdd5  test    eax, eax
0x18005cdd7  jnz     short loc_18005CDF1
0x18005cdd9  call    cs:__imp_GetLastError
0x18005cddf  mov     rdx, rdi
0x18005cde2  lea     rcx, aSCertclosestor; "%s: CertCloseStore failed with error co"...
0x18005cde9  mov     r8d, eax
0x18005cdec  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18005cdf1  mov     eax, ebx
0x18005cdf3  mov     rbx, [rsp+50h+arg_0]
0x18005cdfb  add     rsp, 50h
0x18005cdff  pop     r15
0x18005ce01  pop     r14
0x18005ce03  pop     r13
0x18005ce05  pop     r12
0x18005ce07  pop     rdi
0x18005ce08  pop     rsi
0x18005ce09  pop     rbp
0x18005ce0a  retn
```
