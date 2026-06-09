# CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x180008a5c`
- end: `0x180008d75`
- name: `?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `793`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800086b0`

## callees

- `0x1800084f4`
- `0x180008a5c`
- `0x18000bac0`
- `0x18000cbd8`
- `0x1800307c4`
- `0x18003334c`
- `0x180043ef8`
- `0x180044300`
- `0x180044d30`
- `0x18004654c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008b02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008b02`
- `CRYPT32!CertFindExtension` at `0x180008acc`
- `CRYPT32!CertFindExtension` at `0x180008acc`
- `CRYPT32!CryptDecodeObjectEx` at `0x180008bed`
- `CRYPT32!CryptDecodeObjectEx` at `0x180008bed`
- `CRYPT32!CryptBinaryToStringW` at `0x180008c19`
- `CRYPT32!CryptBinaryToStringW` at `0x180008c7e`
- `CRYPT32!CryptBinaryToStringW` at `0x180008c19`
- `CRYPT32!CryptBinaryToStringW` at `0x180008c7e`

## string_xrefs

- `0x180008ade`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180008b39`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180008c9b`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180008cc2`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180008ced`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180008d35`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180008ae5`: `%s: Extension was not found in the certificate. OID: %hs.`
- `0x180008ba7`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x180008ba0`: `EventWriteNullOrEmptyParameterFailureEvent`

## pseudocode

```c
__int64 __fastcall CertificateUtil::FindExtensionStrValueByOid(
        const char *a1,
        const struct _CERT_CONTEXT *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v3; // r14
  PCERT_EXTENSION Extension; // rax
  unsigned int v8; // edi
  __int64 v10; // r8
  unsigned int v11; // eax
  unsigned __int64 v12; // rax
  unsigned __int16 *v13; // rax
  DWORD LastError; // eax
  const unsigned __int16 *v15; // rcx
  int v16; // esi
  const unsigned __int16 *v17; // rdx
  DWORD pcchString; // [rsp+40h] [rbp-19h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-11h] BYREF
  DWORD pcbStructInfo; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v21[16]; // [rsp+58h] [rbp-1h] BYREF
  const unsigned __int16 *v22; // [rsp+68h] [rbp+Fh]
  __int64 v23; // [rsp+70h] [rbp+17h]
  const unsigned __int16 *v24; // [rsp+78h] [rbp+1Fh]
  __int64 v25; // [rsp+80h] [rbp+27h]

  v3 = 0;
  hMem = 0;
  pcbStructInfo = 0;
  pcchString = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::FindExtensionStrValueByOid", L"pcszOid");
    v17 = L"pcszOid";
LABEL_22:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindExtensionStrValueByOid", v17);
    goto LABEL_6;
  }
  if ( !a3 )
  {
    v8 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionStrValueByOid",
      L"ppszOutBuffer");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v22 = L"CertificateUtil::FindExtensionStrValueByOid";
      v23 = 88;
      v24 = L"ppszOutBuffer";
      v25 = 28;
      v11 = McGenEventWrite_EventWriteTransfer(
              &UserDeviceRegistrationEventProvider_Context,
              NullOrEmptyParameterFailureEvent,
              v10,
              3,
              v21);
      if ( v11 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNullOrEmptyParameterFailureEvent",
          L"EventWriteNullOrEmptyParameterFailureEvent",
          v11);
    }
    goto LABEL_6;
  }
  if ( !a2 )
  {
    v8 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionStrValueByOid",
      L"pCertContext");
    v17 = L"pCertContext";
    goto LABEL_22;
  }
  *a3 = 0;
  Extension = CertFindExtension(a1, a2->pCertInfo->cExtension, a2->pCertInfo->rgExtension);
  if ( Extension )
  {
    v8 = 0;
    if ( CryptDecodeObjectEx(
           a2->dwCertEncodingType,
           (LPCSTR)0x19,
           Extension->Value.pbData,
           Extension->Value.cbData,
           0x8000u,
           0,
           &hMem,
           &pcbStructInfo) )
    {
      if ( CryptBinaryToStringW(*((const BYTE **)hMem + 1), *(_DWORD *)hMem, 0x40000002u, 0, &pcchString) )
      {
        v12 = 2LL * (pcchString + 1);
        if ( !is_mul_ok(pcchString + 1, 2u) )
          v12 = -1;
        v13 = (unsigned __int16 *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
        v3 = v13;
        if ( !v13 )
        {
          v8 = -2147024882;
          Logger::TraceCritical(
            L"%s: Out of memory. Allocation failed.",
            L"CertificateUtil::FindExtensionStrValueByOid");
          goto LABEL_6;
        }
        memset_0(v13, 0, 2LL * (pcchString + 1));
        if ( CryptBinaryToStringW(*((const BYTE **)hMem + 1), *(_DWORD *)hMem, 0x40000002u, v3, &pcchString) )
        {
          v3[pcchString] = 0;
          *a3 = v3;
          v3 = 0;
          goto LABEL_6;
        }
      }
      LastError = GetLastError();
      v15 = L"%s: CryptBinaryToStringW with error code: 0x%08x";
    }
    else
    {
      LastError = GetLastError();
      v15 = L"%s: CryptDecodeObjectEx with error code: 0x%08x";
    }
    v16 = LastError;
    Logger::TraceError(v15, L"CertificateUtil::FindExtensionStrValueByOid", LastError);
    if ( v16 )
    {
      if ( v16 > 0 )
        v8 = (unsigned __int16)v16 | 0x80070000;
      else
        v8 = v16;
    }
  }
  else
  {
    Logger::TraceVerbose(
      (wchar_t *)L"%s: Extension was not found in the certificate. OID: %hs.",
      L"CertificateUtil::FindExtensionStrValueByOid",
      a1);
    v8 = -2146885628;
  }
LABEL_6:
  operator delete(v3);
  LocalFree(hMem);
  return v8;
}

```

## disassembly

```asm
0x180008a5c  mov     [rsp-8+arg_18], rbx
0x180008a61  push    rbp
0x180008a62  push    rsi
0x180008a63  push    rdi
0x180008a64  push    r14
0x180008a66  push    r15
0x180008a68  lea     rbp, [rsp-37h]
0x180008a6d  sub     rsp, 90h
0x180008a74  mov     rax, cs:__security_cookie
0x180008a7b  xor     rax, rsp
0x180008a7e  mov     [rbp+57h+var_28], rax
0x180008a82  xor     r14d, r14d
0x180008a85  mov     [rbp+57h+hMem], 0
0x180008a8d  mov     [rbp+57h+var_60], 0
0x180008a94  mov     r15, r8
0x180008a97  mov     [rbp+57h+pcchString], r14d
0x180008a9b  mov     rsi, rdx
0x180008a9e  mov     rbx, rcx
0x180008aa1  test    rcx, rcx
0x180008aa4  jz      loc_180008CC2
0x180008aaa  test    r8, r8
0x180008aad  jz      short loc_180008B2D
0x180008aaf  test    rdx, rdx
0x180008ab2  jz      loc_180008CED
0x180008ab8  mov     [r8], r14
0x180008abb  mov     rdx, [rdx+18h]
0x180008abf  mov     r8, [rdx+0C8h]; rgExtensions
0x180008ac6  mov     edx, [rdx+0C0h]; cExtensions
0x180008acc  call    cs:__imp_CertFindExtension
0x180008ad2  test    rax, rax
0x180008ad5  jnz     loc_180008BBF
0x180008adb  mov     r8, rbx
0x180008ade  lea     rdx, aCertificateuti_6; "CertificateUtil::FindExtensionStrValueB"...
0x180008ae5  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x180008aec  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180008af1  mov     edi, 80092004h
0x180008af6  mov     rcx, r14; Block
0x180008af9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008afe  mov     rcx, [rbp+57h+hMem]; hMem
0x180008b02  call    cs:__imp_LocalFree
0x180008b08  mov     eax, edi
0x180008b0a  mov     rcx, [rbp+57h+var_28]
0x180008b0e  xor     rcx, rsp; StackCookie
0x180008b11  call    __security_check_cookie
0x180008b16  mov     rbx, [rsp+0B0h+arg_18]
0x180008b1e  add     rsp, 90h
0x180008b25  pop     r15
0x180008b27  pop     r14
0x180008b29  pop     rdi
0x180008b2a  pop     rsi
0x180008b2b  pop     rbp
0x180008b2c  retn
0x180008b2d  lea     rsi, aPpszoutbuffer; "ppszOutBuffer"
0x180008b34  mov     edi, 80070057h
0x180008b39  lea     rbx, aCertificateuti_6; "CertificateUtil::FindExtensionStrValueB"...
0x180008b40  mov     r8, rsi
0x180008b43  mov     rdx, rbx
0x180008b46  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180008b4d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008b52  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180008b59  jz      short loc_180008AF6
0x180008b5b  lea     rax, [rbp+57h+var_58]
0x180008b5f  mov     [rbp+57h+var_48], rbx
0x180008b63  mov     r9d, 3
0x180008b69  mov     qword ptr [rsp+0B0h+dwFlags], rax
0x180008b6e  lea     rdx, NullOrEmptyParameterFailureEvent
0x180008b75  mov     [rbp+57h+var_40], 58h ; 'X'
0x180008b7d  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180008b84  mov     [rbp+57h+var_38], rsi
0x180008b88  mov     [rbp+57h+var_30], 1Ch
0x180008b90  call    McGenEventWrite_EventWriteTransfer
0x180008b95  test    eax, eax
0x180008b97  jz      loc_180008AF6
0x180008b9d  mov     r9d, eax
0x180008ba0  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x180008ba7  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x180008bae  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180008bb5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008bba  jmp     loc_180008AF6
0x180008bbf  mov     r9d, [rax+10h]; cbEncoded
0x180008bc3  lea     rcx, [rbp+57h+var_60]
0x180008bc7  mov     r8, [rax+18h]; pbEncoded
0x180008bcb  xor     edi, edi
0x180008bcd  mov     [rsp+0B0h+pcbStructInfo], rcx; pcbStructInfo
0x180008bd2  lea     rcx, [rbp+57h+hMem]
0x180008bd6  mov     [rsp+0B0h+pvStructInfo], rcx; pvStructInfo
0x180008bdb  mov     ecx, [rsi]; dwCertEncodingType
0x180008bdd  mov     [rsp+0B0h+pDecodePara], rdi; pDecodePara
0x180008be2  lea     edx, [rdi+19h]; lpszStructType
0x180008be5  mov     [rsp+0B0h+dwFlags], 8000h; dwFlags
0x180008bed  call    cs:__imp_CryptDecodeObjectEx
0x180008bf3  test    eax, eax
0x180008bf5  jz      loc_180008D23
0x180008bfb  mov     rcx, [rbp+57h+hMem]
0x180008bff  lea     rax, [rbp+57h+pcchString]
0x180008c03  mov     ebx, 40000002h
0x180008c08  mov     qword ptr [rsp+0B0h+dwFlags], rax; pcchString
0x180008c0d  xor     r9d, r9d; pszString
0x180008c10  mov     r8d, ebx; dwFlags
0x180008c13  mov     edx, [rcx]; cbBinary
0x180008c15  mov     rcx, [rcx+8]; pbBinary
0x180008c19  call    cs:__imp_CryptBinaryToStringW
0x180008c1f  test    eax, eax
0x180008c21  jz      short loc_180008C8C
0x180008c23  mov     ecx, [rbp+57h+pcchString]
0x180008c26  lea     eax, [rdi+2]
0x180008c29  inc     ecx
0x180008c2b  mul     rcx
0x180008c2e  lea     rcx, [rdi-1]
0x180008c32  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008c39  cmovb   rax, rcx
0x180008c3d  mov     rcx, rax; unsigned __int64
0x180008c40  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008c45  mov     r14, rax
0x180008c48  test    rax, rax
0x180008c4b  jz      loc_180008D35
0x180008c51  mov     r8d, [rbp+57h+pcchString]
0x180008c55  xor     edx, edx; Val
0x180008c57  inc     r8d
0x180008c5a  mov     rcx, rax; void *
0x180008c5d  add     r8, r8; Size
0x180008c60  call    memset_0
0x180008c65  mov     rcx, [rbp+57h+hMem]
0x180008c69  lea     rax, [rbp+57h+pcchString]
0x180008c6d  mov     r9, r14; pszString
0x180008c70  mov     qword ptr [rsp+0B0h+dwFlags], rax; pcchString
0x180008c75  mov     r8d, ebx; dwFlags
0x180008c78  mov     edx, [rcx]; cbBinary
0x180008c7a  mov     rcx, [rcx+8]; pbBinary
0x180008c7e  call    cs:__imp_CryptBinaryToStringW
0x180008c84  test    eax, eax
0x180008c86  jnz     loc_180008D60
0x180008c8c  call    cs:__imp_GetLastError
0x180008c92  lea     rcx, aSCryptbinaryto; "%s: CryptBinaryToStringW with error cod"...
0x180008c99  mov     esi, eax
0x180008c9b  lea     rbx, aCertificateuti_6; "CertificateUtil::FindExtensionStrValueB"...
0x180008ca2  mov     r8d, eax
0x180008ca5  mov     rdx, rbx
0x180008ca8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008cad  test    esi, esi
0x180008caf  jz      loc_180008AF6
0x180008cb5  jg      loc_180008D52
0x180008cbb  mov     edi, esi
0x180008cbd  jmp     loc_180008AF6
0x180008cc2  lea     rbx, aCertificateuti_6; "CertificateUtil::FindExtensionStrValueB"...
0x180008cc9  mov     edi, 80070057h
0x180008cce  mov     rdx, rbx
0x180008cd1  lea     r8, aPcszoid; "pcszOid"
0x180008cd8  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180008cdf  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008ce4  lea     rdx, aPcszoid; "pcszOid"
0x180008ceb  jmp     short loc_180008D16
0x180008ced  lea     rbx, aCertificateuti_6; "CertificateUtil::FindExtensionStrValueB"...
0x180008cf4  mov     edi, 80070057h
0x180008cf9  mov     rdx, rbx
0x180008cfc  lea     r8, aPcertcontext; "pCertContext"
0x180008d03  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180008d0a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008d0f  lea     rdx, aPcertcontext; "pCertContext"
0x180008d16  mov     rcx, rbx; unsigned __int16 *
0x180008d19  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180008d1e  jmp     loc_180008AF6
0x180008d23  call    cs:__imp_GetLastError
0x180008d29  lea     rcx, aSCryptdecodeob; "%s: CryptDecodeObjectEx with error code"...
0x180008d30  jmp     loc_180008C99
0x180008d35  lea     rdx, aCertificateuti_6; "CertificateUtil::FindExtensionStrValueB"...
0x180008d3c  mov     edi, 8007000Eh
0x180008d41  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180008d48  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180008d4d  jmp     loc_180008AF6
0x180008d52  movzx   edi, si
0x180008d55  or      edi, 80070000h
0x180008d5b  jmp     loc_180008AF6
0x180008d60  mov     edx, [rbp+57h+pcchString]
0x180008d63  xor     ecx, ecx
0x180008d65  mov     [r14+rdx*2], cx
0x180008d6a  mov     [r15], r14
0x180008d6d  xor     r14d, r14d
0x180008d70  jmp     loc_180008AF6
```
