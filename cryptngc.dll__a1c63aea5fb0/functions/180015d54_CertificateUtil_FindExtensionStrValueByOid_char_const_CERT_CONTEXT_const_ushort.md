# CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x180015d54`
- end: `0x180016041`
- name: `?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `749`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180015b10`

## callees

- `0x1800073c0`
- `0x180015d54`
- `0x1800166e0`
- `0x180027278`
- `0x180027448`
- `0x1800274cc`
- `0x18002bc58`
- `0x18002e664`
- `0x18002e850`
- `0x18002f710`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015fc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015fc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016016`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016016`
- `CRYPT32!CryptBinaryToStringW` at `0x180015f36`
- `CRYPT32!CryptBinaryToStringW` at `0x180015fba`
- `CRYPT32!CryptBinaryToStringW` at `0x180015f36`
- `CRYPT32!CryptBinaryToStringW` at `0x180015fba`
- `CRYPT32!CryptDecodeObjectEx` at `0x180015efc`
- `CRYPT32!CryptDecodeObjectEx` at `0x180015efc`

## string_xrefs

- `0x180015dae`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180015e3b`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180015e76`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180015eb1`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180015f73`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180015fd3`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180015e1e`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x180015e17`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x180015eb8`: `%s: Extension was not found in the certificate. OID: %hs.`

## pseudocode

```c
__int64 __fastcall CertificateUtil::FindExtensionStrValueByOid(
        const char *a1,
        const struct _CERT_CONTEXT *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v3; // r14
  unsigned int v7; // edi
  __int64 v8; // r8
  unsigned int v9; // eax
  HCERTSTORE *p_hCertStore; // rdx
  struct _CERT_EXTENSION *ExtensionByOid; // rax
  DWORD LastError; // eax
  const unsigned __int16 *v13; // rcx
  unsigned __int64 v14; // rax
  unsigned __int16 *v15; // rax
  int v16; // esi
  DWORD pcchString; // [rsp+40h] [rbp-19h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-11h] BYREF
  DWORD pcbStructInfo; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v21[16]; // [rsp+58h] [rbp-1h] BYREF
  const unsigned __int16 *v22; // [rsp+68h] [rbp+Fh]
  __int64 v23; // [rsp+70h] [rbp+17h]
  const wchar_t *v24; // [rsp+78h] [rbp+1Fh]
  __int64 v25; // [rsp+80h] [rbp+27h]

  v3 = 0;
  hMem = 0;
  pcbStructInfo = 0;
  pcchString = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::FindExtensionStrValueByOid", L"pcszOid");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v22 = L"CertificateUtil::FindExtensionStrValueByOid";
      v23 = 88;
      v24 = L"pcszOid";
      v25 = 16;
      v9 = McGenEventWrite_EventWriteTransfer(
             &UserDeviceRegistrationEventProvider_Context,
             NullOrEmptyParameterFailureEvent,
             v8,
             3,
             v21);
      if ( v9 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNullOrEmptyParameterFailureEvent",
          L"EventWriteNullOrEmptyParameterFailureEvent",
          v9);
    }
    goto LABEL_26;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionStrValueByOid",
      &stru_1800542A8.hCertStore);
    p_hCertStore = &stru_1800542A8.hCertStore;
LABEL_7:
    Logger::WriteNullOrEmptyParameterFailureEvent(
      L"CertificateUtil::FindExtensionStrValueByOid",
      (const unsigned __int16 *)p_hCertStore);
    goto LABEL_26;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionStrValueByOid",
      &stru_1800542A8);
    p_hCertStore = (HCERTSTORE *)&stru_1800542A8;
    goto LABEL_7;
  }
  *a3 = 0;
  ExtensionByOid = CertificateUtil::FindExtensionByOid(a1, a2);
  if ( ExtensionByOid )
  {
    v7 = 0;
    if ( CryptDecodeObjectEx(
           a2->dwCertEncodingType,
           (LPCSTR)0x19,
           ExtensionByOid->Value.pbData,
           ExtensionByOid->Value.cbData,
           0x8000u,
           0,
           &hMem,
           &pcbStructInfo) )
    {
      if ( CryptBinaryToStringW(*((const BYTE **)hMem + 1), *(_DWORD *)hMem, 0x40000002u, 0, &pcchString) )
      {
        v14 = 2LL * (pcchString + 1);
        if ( !is_mul_ok(pcchString + 1, 2u) )
          v14 = -1;
        v15 = (unsigned __int16 *)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
        v3 = v15;
        if ( !v15 )
        {
          v7 = -2147024882;
          Logger::TraceCritical(
            L"%s: Out of memory. Allocation failed.",
            L"CertificateUtil::FindExtensionStrValueByOid");
          goto LABEL_26;
        }
        memset_0(v15, 0, 2LL * (pcchString + 1));
        if ( CryptBinaryToStringW(*((const BYTE **)hMem + 1), *(_DWORD *)hMem, 0x40000002u, v3, &pcchString) )
        {
          v3[pcchString] = 0;
          *a3 = v3;
          v3 = 0;
          goto LABEL_26;
        }
      }
      LastError = GetLastError();
      v13 = L"%s: CryptBinaryToStringW with error code: 0x%08x";
    }
    else
    {
      LastError = GetLastError();
      v13 = L"%s: CryptDecodeObjectEx with error code: 0x%08x";
    }
    v16 = LastError;
    Logger::TraceError(v13, L"CertificateUtil::FindExtensionStrValueByOid", LastError);
    if ( v16 > 0 )
    {
      v7 = (unsigned __int16)v16 | 0x80070000;
    }
    else if ( v16 )
    {
      v7 = v16;
    }
  }
  else
  {
    Logger::TraceVerbose(
      L"%s: Extension was not found in the certificate. OID: %hs.",
      L"CertificateUtil::FindExtensionStrValueByOid",
      a1);
    v7 = -2146885628;
  }
LABEL_26:
  operator delete(v3);
  LocalFree(hMem);
  return v7;
}

```

## disassembly

```asm
0x180015d54  mov     [rsp-8+arg_18], rbx
0x180015d59  push    rbp
0x180015d5a  push    rsi
0x180015d5b  push    rdi
0x180015d5c  push    r14
0x180015d5e  push    r15
0x180015d60  lea     rbp, [rsp-37h]
0x180015d65  sub     rsp, 90h
0x180015d6c  mov     rax, cs:__security_cookie
0x180015d73  xor     rax, rsp
0x180015d76  mov     [rbp+57h+var_28], rax
0x180015d7a  xor     r14d, r14d
0x180015d7d  mov     [rbp+57h+hMem], 0
0x180015d85  mov     [rbp+57h+var_60], 0
0x180015d8c  mov     r15, r8
0x180015d8f  mov     [rbp+57h+pcchString], r14d
0x180015d93  mov     rsi, rdx
0x180015d96  mov     rbx, rcx
0x180015d99  test    rcx, rcx
0x180015d9c  jnz     loc_180015E36
0x180015da2  lea     rsi, aPcszoid; "pcszOid"
0x180015da9  mov     edi, 80070057h
0x180015dae  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180015db5  mov     r8, rsi
0x180015db8  mov     rdx, rbx
0x180015dbb  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180015dc2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180015dc7  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180015dce  jz      loc_18001600A
0x180015dd4  lea     rax, [rbp+57h+var_58]
0x180015dd8  mov     [rbp+57h+var_48], rbx
0x180015ddc  lea     r9d, [r14+3]
0x180015de0  mov     qword ptr [rsp+0B0h+dwFlags], rax
0x180015de5  lea     rdx, NullOrEmptyParameterFailureEvent
0x180015dec  mov     [rbp+57h+var_40], 58h ; 'X'
0x180015df4  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180015dfb  mov     [rbp+57h+var_38], rsi
0x180015dff  mov     [rbp+57h+var_30], 10h
0x180015e07  call    McGenEventWrite_EventWriteTransfer
0x180015e0c  test    eax, eax
0x180015e0e  jz      loc_18001600A
0x180015e14  mov     r9d, eax
0x180015e17  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x180015e1e  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x180015e25  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180015e2c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180015e31  jmp     loc_18001600A
0x180015e36  test    r15, r15
0x180015e39  jnz     short loc_180015E71
0x180015e3b  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180015e42  mov     edi, 80070057h
0x180015e47  mov     rdx, rbx
0x180015e4a  lea     r8, stru_1800542A8.hCertStore
0x180015e51  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180015e58  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180015e5d  lea     rdx, stru_1800542A8.hCertStore; unsigned __int16 *
0x180015e64  mov     rcx, rbx; unsigned __int16 *
0x180015e67  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180015e6c  jmp     loc_18001600A
0x180015e71  test    rsi, rsi
0x180015e74  jnz     short loc_180015EA1
0x180015e76  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180015e7d  mov     edi, 80070057h
0x180015e82  mov     rdx, rbx
0x180015e85  lea     r8, stru_1800542A8
0x180015e8c  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180015e93  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180015e98  lea     rdx, stru_1800542A8; struct _CERT_CONTEXT *
0x180015e9f  jmp     short loc_180015E64
0x180015ea1  mov     [r8], r14
0x180015ea4  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x180015ea9  test    rax, rax
0x180015eac  jnz     short loc_180015ECE
0x180015eae  mov     r8, rbx
0x180015eb1  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180015eb8  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x180015ebf  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180015ec4  mov     edi, 80092004h
0x180015ec9  jmp     loc_18001600A
0x180015ece  mov     r9d, [rax+10h]; cbEncoded
0x180015ed2  lea     rcx, [rbp+57h+var_60]
0x180015ed6  mov     r8, [rax+18h]; pbEncoded
0x180015eda  xor     edi, edi
0x180015edc  mov     [rsp+0B0h+pcbStructInfo], rcx; pcbStructInfo
0x180015ee1  lea     rcx, [rbp+57h+hMem]
0x180015ee5  mov     [rsp+0B0h+pvStructInfo], rcx; pvStructInfo
0x180015eea  mov     ecx, [rsi]; dwCertEncodingType
0x180015eec  mov     [rsp+0B0h+pDecodePara], rdi; pDecodePara
0x180015ef1  lea     edx, [rdi+19h]; lpszStructType
0x180015ef4  mov     [rsp+0B0h+dwFlags], 8000h; dwFlags
0x180015efc  call    cs:__imp_CryptDecodeObjectEx
0x180015f02  test    eax, eax
0x180015f04  jnz     short loc_180015F18
0x180015f06  call    cs:__imp_GetLastError
0x180015f0c  lea     rcx, aSCryptdecodeob; "%s: CryptDecodeObjectEx with error code"...
0x180015f13  jmp     loc_180015FD1
0x180015f18  mov     rcx, [rbp+57h+hMem]
0x180015f1c  lea     rax, [rbp+57h+pcchString]
0x180015f20  mov     ebx, 40000002h
0x180015f25  mov     qword ptr [rsp+0B0h+dwFlags], rax; pcchString
0x180015f2a  xor     r9d, r9d; pszString
0x180015f2d  mov     r8d, ebx; dwFlags
0x180015f30  mov     edx, [rcx]; cbBinary
0x180015f32  mov     rcx, [rcx+8]; pbBinary
0x180015f36  call    cs:__imp_CryptBinaryToStringW
0x180015f3c  test    eax, eax
0x180015f3e  jz      loc_180015FC4
0x180015f44  mov     ecx, [rbp+57h+pcchString]
0x180015f47  mov     eax, 2
0x180015f4c  inc     ecx
0x180015f4e  mul     rcx
0x180015f51  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180015f58  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015f5f  cmovb   rax, rcx
0x180015f63  mov     rcx, rax; unsigned __int64
0x180015f66  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180015f6b  mov     r14, rax
0x180015f6e  test    rax, rax
0x180015f71  jnz     short loc_180015F8D
0x180015f73  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180015f7a  mov     edi, 8007000Eh
0x180015f7f  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x180015f86  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180015f8b  jmp     short loc_18001600A
0x180015f8d  mov     r8d, [rbp+57h+pcchString]
0x180015f91  xor     edx, edx; Val
0x180015f93  inc     r8d
0x180015f96  mov     rcx, r14; void *
0x180015f99  add     r8, r8; Size
0x180015f9c  call    memset_0
0x180015fa1  mov     rcx, [rbp+57h+hMem]
0x180015fa5  lea     rax, [rbp+57h+pcchString]
0x180015fa9  mov     r9, r14; pszString
0x180015fac  mov     qword ptr [rsp+0B0h+dwFlags], rax; pcchString
0x180015fb1  mov     r8d, ebx; dwFlags
0x180015fb4  mov     edx, [rcx]; cbBinary
0x180015fb6  mov     rcx, [rcx+8]; pbBinary
0x180015fba  call    cs:__imp_CryptBinaryToStringW
0x180015fc0  test    eax, eax
0x180015fc2  jnz     short loc_180015FFA
0x180015fc4  call    cs:__imp_GetLastError
0x180015fca  lea     rcx, aSCryptbinaryto; "%s: CryptBinaryToStringW with error cod"...
0x180015fd1  mov     esi, eax
0x180015fd3  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180015fda  mov     r8d, eax
0x180015fdd  mov     rdx, rbx
0x180015fe0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180015fe5  test    esi, esi
0x180015fe7  jg      short loc_180015FEF
0x180015fe9  jz      short loc_18001600A
0x180015feb  mov     edi, esi
0x180015fed  jmp     short loc_18001600A
0x180015fef  movzx   edi, si
0x180015ff2  or      edi, 80070000h
0x180015ff8  jmp     short loc_18001600A
0x180015ffa  mov     edx, [rbp+57h+pcchString]
0x180015ffd  xor     ecx, ecx
0x180015fff  mov     [r14+rdx*2], cx
0x180016004  mov     [r15], r14
0x180016007  xor     r14d, r14d
0x18001600a  mov     rcx, r14; Block
0x18001600d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016012  mov     rcx, [rbp+57h+hMem]; hMem
0x180016016  call    cs:__imp_LocalFree
0x18001601c  mov     eax, edi
0x18001601e  mov     rcx, [rbp+57h+var_28]
0x180016022  xor     rcx, rsp; StackCookie
0x180016025  call    __security_check_cookie
0x18001602a  mov     rbx, [rsp+0B0h+arg_18]
0x180016032  add     rsp, 90h
0x180016039  pop     r15
0x18001603b  pop     r14
0x18001603d  pop     rdi
0x18001603e  pop     rsi
0x18001603f  pop     rbp
0x180016040  retn
```
