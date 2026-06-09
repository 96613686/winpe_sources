# RegistrationCertHelper::DeleteCertificatesAADStore(ushort const *,ushort const *)

- ea: `0x18005ce14`
- end: `0x18005d0ea`
- name: `?DeleteCertificatesAADStore@RegistrationCertHelper@@SAJPEBG0@Z`
- size: `726`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180056c98`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x1800307c4`
- `0x180043ef8`
- `0x18005ce14`
- `0x18005d0f0`
- `0x18009685c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ce9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cf41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d0bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ce9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cf41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d0bf`
- `CRYPT32!CertOpenStore` at `0x18005ce8e`
- `CRYPT32!CertOpenStore` at `0x18005ce8e`
- `CRYPT32!CertFindCertificateInStore` at `0x18005cef5`
- `CRYPT32!CertFindCertificateInStore` at `0x18005cef5`
- `CRYPT32!CertCloseStore` at `0x18005d0b5`
- `CRYPT32!CertCloseStore` at `0x18005d0b5`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18005cf33`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18005cf33`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18005cfec`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18005cfec`
- `CRYPT32!CertFreeCertificateContext` at `0x18005d08a`
- `CRYPT32!CertFreeCertificateContext` at `0x18005d098`
- `CRYPT32!CertFreeCertificateContext` at `0x18005d08a`
- `CRYPT32!CertFreeCertificateContext` at `0x18005d098`

## string_xrefs

- `0x18005ceab`: `CertOpenStore`
- `0x18005ce6f`: `AAD Token Issuer`
- `0x18005cf0a`: `AAD Token Issuer`
- `0x18005d025`: `CertDeleteCertificateFromStore`
- `0x18005ce39`: `RegistrationCertHelper::DeleteCertificatesAADStore`
- `0x18005ceb2`: `RegistrationCertHelper::DeleteCertificatesAADStore`
- `0x18005ced2`: `RegistrationCertHelper::DeleteCertificatesAADStore`
- `0x18005d034`: `RegistrationCertHelper::DeleteDeviceUserCertificates`

## pseudocode

```c
__int64 __fastcall RegistrationCertHelper::DeleteCertificatesAADStore(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2)
{
  void *v2; // rbp
  unsigned int v4; // ebx
  int v5; // edi
  const CERT_CONTEXT *pPrevCertContext; // r12
  HCERTSTORE v7; // r13
  DWORD LastError; // eax
  const CERT_CONTEXT *v9; // r14
  const wchar_t *v10; // r8
  int StringField; // eax
  __int64 v12; // r8
  int v13; // eax
  __int64 v14; // r8
  DWORD v15; // eax
  int v17; // [rsp+80h] [rbp+8h] BYREF
  const unsigned __int16 *v18; // [rsp+88h] [rbp+10h]
  int v19; // [rsp+90h] [rbp+18h] BYREF
  void *Block; // [rsp+98h] [rbp+20h] BYREF

  v18 = a2;
  v2 = 0;
  Block = 0;
  if ( !a1 )
  {
    v4 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationCertHelper::DeleteCertificatesAADStore",
      L"pcszTenantId");
    Logger::WriteNullOrEmptyParameterFailureEvent(
      L"RegistrationCertHelper::DeleteCertificatesAADStore",
      L"pcszTenantId");
    return v4;
  }
  v5 = 0;
  pPrevCertContext = 0;
  v7 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, L"AAD Token Issuer");
  if ( v7 || (LastError = GetLastError(), (v5 = LastError) == 0) )
  {
    v4 = 0;
    while ( 1 )
    {
      v9 = 0;
      pPrevCertContext = CertFindCertificateInStore(v7, 0x10001u, 0, 0, 0, pPrevCertContext);
      if ( !pPrevCertContext )
        break;
      v17 = 0;
      v19 = 0;
      Logger::TraceVerbose(
        (wchar_t *)L"%s: Certificate found in %s store.",
        L"RegistrationCertHelper::DeleteCertificatesAADStore",
        L"AAD Token Issuer");
      v9 = CertDuplicateCertificateContext(pPrevCertContext);
      if ( !v9 )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError )
        {
          v10 = L"CertDuplicateCertificateContext";
          goto LABEL_6;
        }
      }
      StringField = CertificateUtil::GetStringField(1, v9, &Block);
      v4 = StringField;
      if ( StringField < 0 )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"RegistrationCertHelper::DeleteCertificatesAADStore",
          L"CertificateGetIssuer",
          (unsigned int)StringField);
        v2 = Block;
        break;
      }
      v2 = Block;
      v13 = RegistrationCertHelper::DeleteDeviceUserCertificates(1, Block, v12, a1, v18, &v17);
      v4 = v13;
      if ( v13 < 0
        || (v13 = RegistrationCertHelper::DeleteDeviceUserCertificates(0, v2, v14, a1, v18, &v19), v4 = v13, v13 < 0) )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"RegistrationCertHelper::DeleteCertificatesAADStore",
          L"RegistrationCertHelper::DeleteDeviceUserCertificates",
          (unsigned int)v13);
        break;
      }
      if ( !(v19 + v17) && !CertDeleteCertificateFromStore(v9) )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError )
        {
          v10 = L"CertDeleteCertificateFromStore";
          goto LABEL_6;
        }
      }
      operator delete(v2);
      v2 = 0;
      Block = 0;
    }
    if ( !v5 )
      goto LABEL_26;
  }
  else
  {
    v9 = 0;
    v10 = L"CertOpenStore";
LABEL_6:
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"RegistrationCertHelper::DeleteCertificatesAADStore",
      v10,
      LastError);
  }
  if ( v5 > 0 )
    v4 = (unsigned __int16)v5 | 0x80070000;
  else
    v4 = v5;
LABEL_26:
  if ( v9 )
    CertFreeCertificateContext(v9);
  if ( pPrevCertContext )
    CertFreeCertificateContext(pPrevCertContext);
  if ( v2 )
    operator delete(v2);
  if ( v7 && !CertCloseStore(v7, 0) )
  {
    v15 = GetLastError();
    Logger::TraceWarning(
      (wchar_t *)L"%s: CertCloseStore failed with error code: 0x%08x. Igored.",
      L"RegistrationCertHelper::DeleteCertificatesAADStore",
      v15);
  }
  return v4;
}

```

## disassembly

```asm
0x18005ce14  mov     rax, rsp
0x18005ce17  mov     [rax+10h], rdx
0x18005ce1b  push    rbx
0x18005ce1c  push    rbp
0x18005ce1d  push    rsi
0x18005ce1e  push    rdi
0x18005ce1f  push    r12
0x18005ce21  push    r13
0x18005ce23  push    r14
0x18005ce25  push    r15
0x18005ce27  sub     rsp, 38h
0x18005ce2b  xor     ebp, ebp
0x18005ce2d  mov     r15, rcx
0x18005ce30  mov     [rax+20h], rbp
0x18005ce34  test    rcx, rcx
0x18005ce37  jnz     short loc_18005CE6F
0x18005ce39  lea     rsi, aRegistrationce_12; "RegistrationCertHelper::DeleteCertifica"...
0x18005ce40  mov     ebx, 80070057h
0x18005ce45  mov     rdx, rsi
0x18005ce48  lea     r8, aPcsztenantid; "pcszTenantId"
0x18005ce4f  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18005ce56  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005ce5b  lea     rdx, aPcsztenantid; "pcszTenantId"
0x18005ce62  mov     rcx, rsi; unsigned __int16 *
0x18005ce65  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18005ce6a  jmp     loc_18005D0D7
0x18005ce6f  lea     rax, aAadTokenIssuer; "AAD Token Issuer"
0x18005ce76  xor     edi, edi
0x18005ce78  mov     r9d, 20000h; dwFlags
0x18005ce7e  mov     [rsp+78h+pvPara], rax; pvPara
0x18005ce83  xor     r8d, r8d; hCryptProv
0x18005ce86  xor     edx, edx; dwEncodingType
0x18005ce88  xor     r12d, r12d
0x18005ce8b  lea     ecx, [rdi+0Ah]; lpszStoreProvider
0x18005ce8e  call    cs:__imp_CertOpenStore
0x18005ce94  mov     r13, rax
0x18005ce97  test    rax, rax
0x18005ce9a  jnz     short loc_18005CED0
0x18005ce9c  call    cs:__imp_GetLastError
0x18005cea2  mov     edi, eax
0x18005cea4  test    eax, eax
0x18005cea6  jz      short loc_18005CED0
0x18005cea8  xor     r14d, r14d
0x18005ceab  lea     r8, aCertopenstore_0; "CertOpenStore"
0x18005ceb2  lea     rsi, aRegistrationce_12; "RegistrationCertHelper::DeleteCertifica"...
0x18005ceb9  mov     r9d, eax
0x18005cebc  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18005cec3  mov     rdx, rsi
0x18005cec6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005cecb  jmp     loc_18005D071
0x18005ced0  xor     ebx, ebx
0x18005ced2  lea     rsi, aRegistrationce_12; "RegistrationCertHelper::DeleteCertifica"...
0x18005ced9  mov     [rsp+78h+pPrevCertContext], r12; pPrevCertContext
0x18005cede  xor     r9d, r9d; dwFindType
0x18005cee1  xor     r8d, r8d; dwFindFlags
0x18005cee4  mov     [rsp+78h+pvPara], 0; pvFindPara
0x18005ceed  mov     edx, 10001h; dwCertEncodingType
0x18005cef2  mov     rcx, r13; hCertStore
0x18005cef5  call    cs:__imp_CertFindCertificateInStore
0x18005cefb  xor     r14d, r14d
0x18005cefe  mov     r12, rax
0x18005cf01  test    rax, rax
0x18005cf04  jz      loc_18005D06D
0x18005cf0a  lea     r8, aAadTokenIssuer; "AAD Token Issuer"
0x18005cf11  mov     [rsp+78h+arg_0], r14d
0x18005cf19  mov     rdx, rsi
0x18005cf1c  mov     [rsp+78h+arg_10], r14d
0x18005cf24  lea     rcx, aSCertificateFo; "%s: Certificate found in %s store."
0x18005cf2b  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005cf30  mov     rcx, r12; pCertContext
0x18005cf33  call    cs:__imp_CertDuplicateCertificateContext
0x18005cf39  mov     r14, rax
0x18005cf3c  test    rax, rax
0x18005cf3f  jnz     short loc_18005CF51
0x18005cf41  call    cs:__imp_GetLastError
0x18005cf47  mov     edi, eax
0x18005cf49  test    eax, eax
0x18005cf4b  jnz     loc_18005D019
0x18005cf51  lea     r8, [rsp+78h+Block]
0x18005cf59  mov     rdx, r14
0x18005cf5c  mov     ecx, 1
0x18005cf61  call    ?GetStringField@CertificateUtil@@CAJW4StringFieldType@1@PEBU_CERT_CONTEXT@@PEAPEAG_N@Z; CertificateUtil::GetStringField(CertificateUtil::StringFieldType,_CERT_CONTEXT const *,ushort * *,bool)
0x18005cf66  mov     ebx, eax
0x18005cf68  test    eax, eax
0x18005cf6a  js      loc_18005D04C
0x18005cf70  mov     rbp, [rsp+78h+Block]
0x18005cf78  lea     rax, [rsp+78h+arg_0]
0x18005cf80  mov     [rsp+78h+pPrevCertContext], rax
0x18005cf85  mov     r9, r15
0x18005cf88  mov     rax, [rsp+78h+arg_8]
0x18005cf90  mov     rdx, rbp
0x18005cf93  mov     ecx, 1
0x18005cf98  mov     [rsp+78h+pvPara], rax
0x18005cf9d  call    ?DeleteDeviceUserCertificates@RegistrationCertHelper@@CAJW4_CERTFICATE_LOCATION@@PEBG111AEAK@Z; RegistrationCertHelper::DeleteDeviceUserCertificates(_CERTFICATE_LOCATION,ushort const *,ushort const *,ushort const *,ushort const *,ulong &)
0x18005cfa2  mov     ebx, eax
0x18005cfa4  test    eax, eax
0x18005cfa6  js      loc_18005D031
0x18005cfac  lea     rax, [rsp+78h+arg_10]
0x18005cfb4  mov     r9, r15
0x18005cfb7  mov     [rsp+78h+pPrevCertContext], rax
0x18005cfbc  mov     rdx, rbp
0x18005cfbf  mov     rax, [rsp+78h+arg_8]
0x18005cfc7  xor     ecx, ecx
0x18005cfc9  mov     [rsp+78h+pvPara], rax
0x18005cfce  call    ?DeleteDeviceUserCertificates@RegistrationCertHelper@@CAJW4_CERTFICATE_LOCATION@@PEBG111AEAK@Z; RegistrationCertHelper::DeleteDeviceUserCertificates(_CERTFICATE_LOCATION,ushort const *,ushort const *,ushort const *,ushort const *,ulong &)
0x18005cfd3  mov     ebx, eax
0x18005cfd5  test    eax, eax
0x18005cfd7  js      short loc_18005D031
0x18005cfd9  mov     ecx, [rsp+78h+arg_0]
0x18005cfe0  add     ecx, [rsp+78h+arg_10]
0x18005cfe7  jnz     short loc_18005D002
0x18005cfe9  mov     rcx, r14; pCertContext
0x18005cfec  call    cs:__imp_CertDeleteCertificateFromStore
0x18005cff2  test    eax, eax
0x18005cff4  jnz     short loc_18005D002
0x18005cff6  call    cs:__imp_GetLastError
0x18005cffc  mov     edi, eax
0x18005cffe  test    eax, eax
0x18005d000  jnz     short loc_18005D025
0x18005d002  mov     rcx, rbp; Block
0x18005d005  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005d00a  xor     ebp, ebp
0x18005d00c  mov     [rsp+78h+Block], rbp
0x18005d014  jmp     loc_18005CED9
0x18005d019  lea     r8, aCertduplicatec_0; "CertDuplicateCertificateContext"
0x18005d020  jmp     loc_18005CEB9
0x18005d025  lea     r8, aCertdeletecert_0; "CertDeleteCertificateFromStore"
0x18005d02c  jmp     loc_18005CEB9
0x18005d031  mov     r9d, eax
0x18005d034  lea     r8, aRegistrationce_23; "RegistrationCertHelper::DeleteDeviceUse"...
0x18005d03b  mov     rdx, rsi
0x18005d03e  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005d045  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005d04a  jmp     short loc_18005D06D
0x18005d04c  mov     r9d, eax
0x18005d04f  lea     r8, aCertificateget; "CertificateGetIssuer"
0x18005d056  mov     rdx, rsi
0x18005d059  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005d060  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005d065  mov     rbp, [rsp+78h+Block]
0x18005d06d  test    edi, edi
0x18005d06f  jz      short loc_18005D082
0x18005d071  test    edi, edi
0x18005d073  jg      short loc_18005D079
0x18005d075  mov     ebx, edi
0x18005d077  jmp     short loc_18005D082
0x18005d079  movzx   ebx, di
0x18005d07c  or      ebx, 80070000h
0x18005d082  test    r14, r14
0x18005d085  jz      short loc_18005D090
0x18005d087  mov     rcx, r14; pCertContext
0x18005d08a  call    cs:__imp_CertFreeCertificateContext
0x18005d090  test    r12, r12
0x18005d093  jz      short loc_18005D09E
0x18005d095  mov     rcx, r12; pCertContext
0x18005d098  call    cs:__imp_CertFreeCertificateContext
0x18005d09e  test    rbp, rbp
0x18005d0a1  jz      short loc_18005D0AB
0x18005d0a3  mov     rcx, rbp; Block
0x18005d0a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005d0ab  test    r13, r13
0x18005d0ae  jz      short loc_18005D0D7
0x18005d0b0  xor     edx, edx; dwFlags
0x18005d0b2  mov     rcx, r13; hCertStore
0x18005d0b5  call    cs:__imp_CertCloseStore
0x18005d0bb  test    eax, eax
0x18005d0bd  jnz     short loc_18005D0D7
0x18005d0bf  call    cs:__imp_GetLastError
0x18005d0c5  mov     rdx, rsi
0x18005d0c8  lea     rcx, aSCertclosestor; "%s: CertCloseStore failed with error co"...
0x18005d0cf  mov     r8d, eax
0x18005d0d2  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18005d0d7  mov     eax, ebx
0x18005d0d9  add     rsp, 38h
0x18005d0dd  pop     r15
0x18005d0df  pop     r14
0x18005d0e1  pop     r13
0x18005d0e3  pop     r12
0x18005d0e5  pop     rdi
0x18005d0e6  pop     rsi
0x18005d0e7  pop     rbp
0x18005d0e8  pop     rbx
0x18005d0e9  retn
```
