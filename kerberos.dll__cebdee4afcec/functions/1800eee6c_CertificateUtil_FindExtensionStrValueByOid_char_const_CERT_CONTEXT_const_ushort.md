# CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x1800eee6c`
- end: `0x1800ef0ca`
- name: `?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `606`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x1800eea9c`

## callees

- `0x18006f680`
- `0x18006f6dc`
- `0x18006f848`
- `0x180070f00`
- `0x18007108c`
- `0x1800740f4`
- `0x1800eec3c`
- `0x1800eee6c`
- `0x1800ef7a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eef9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef05c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eef9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef05c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ef0ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ef0ae`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800eef94`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800eef94`
- `CRYPT32!CryptBinaryToStringW` at `0x1800eefce`
- `CRYPT32!CryptBinaryToStringW` at `0x1800ef052`
- `CRYPT32!CryptBinaryToStringW` at `0x1800eefce`
- `CRYPT32!CryptBinaryToStringW` at `0x1800ef052`

## string_xrefs

- `0x1800eeea3`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800eeede`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800eef0e`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800eef49`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800ef00b`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800ef06b`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800eef50`: `%s: Extension was not found in the certificate. OID: %hs.`

## pseudocode

```c
__int64 __fastcall CertificateUtil::FindExtensionStrValueByOid(
        const char *a1,
        const struct _CERT_CONTEXT *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v3; // r14
  unsigned int v7; // edi
  const unsigned __int16 *v8; // rdx
  struct _CERT_EXTENSION *ExtensionByOid; // rax
  DWORD LastError; // eax
  const unsigned __int16 *v11; // rcx
  unsigned __int64 v12; // rax
  unsigned __int16 *v13; // rax
  int v14; // esi
  __int64 v15; // rdx
  HLOCAL hMem[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD pcchString; // [rsp+80h] [rbp+30h] BYREF
  DWORD pcbStructInfo; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  hMem[0] = 0;
  pcbStructInfo = 0;
  pcchString = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::FindExtensionStrValueByOid", L"pcszOid");
    v8 = L"pcszOid";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindExtensionStrValueByOid", v8);
    goto LABEL_24;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionStrValueByOid",
      L"ppszOutBuffer");
    v8 = L"ppszOutBuffer";
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionStrValueByOid",
      &stru_1801282C8);
    v8 = (const unsigned __int16 *)&stru_1801282C8;
    goto LABEL_3;
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
           hMem,
           &pcbStructInfo) )
    {
      if ( CryptBinaryToStringW(*((const BYTE **)hMem[0] + 1), *(_DWORD *)hMem[0], 0x40000002u, 0, &pcchString) )
      {
        v12 = 2LL * (pcchString + 1);
        if ( !is_mul_ok(pcchString + 1, 2u) )
          v12 = -1;
        v13 = (unsigned __int16 *)operator new[](v12, (const struct std::nothrow_t *)std::nothrow);
        v3 = v13;
        if ( !v13 )
        {
          v7 = -2147024882;
          Logger::TraceCritical(
            L"%s: Out of memory. Allocation failed.",
            L"CertificateUtil::FindExtensionStrValueByOid");
          goto LABEL_24;
        }
        memset_0(v13, 0, 2LL * (pcchString + 1));
        if ( CryptBinaryToStringW(*((const BYTE **)hMem[0] + 1), *(_DWORD *)hMem[0], 0x40000002u, v3, &pcchString) )
        {
          v15 = pcchString;
          *a3 = v3;
          v3[v15] = 0;
          v3 = 0;
          goto LABEL_24;
        }
      }
      LastError = GetLastError();
      v11 = L"%s: CryptBinaryToStringW with error code: 0x%08x";
    }
    else
    {
      LastError = GetLastError();
      v11 = L"%s: CryptDecodeObjectEx with error code: 0x%08x";
    }
    v14 = LastError;
    Logger::TraceError(v11, L"CertificateUtil::FindExtensionStrValueByOid", LastError);
    if ( v14 )
    {
      if ( v14 > 0 )
        v7 = (unsigned __int16)v14 | 0x80070000;
      else
        v7 = v14;
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
LABEL_24:
  operator delete(v3);
  LocalFree(hMem[0]);
  return v7;
}

```

## disassembly

```asm
0x1800eee6c  mov     [rsp-28h+arg_8], rbx
0x1800eee71  push    rbp
0x1800eee72  push    rsi
0x1800eee73  push    rdi
0x1800eee74  push    r14
0x1800eee76  push    r15
0x1800eee78  mov     rbp, rsp
0x1800eee7b  sub     rsp, 50h
0x1800eee7f  xor     r14d, r14d
0x1800eee82  mov     [rbp+hMem], 0
0x1800eee8a  mov     [rbp+arg_18], 0
0x1800eee91  mov     r15, r8
0x1800eee94  mov     [rbp+pcchString], r14d
0x1800eee98  mov     rsi, rdx
0x1800eee9b  mov     rbx, rcx
0x1800eee9e  test    rcx, rcx
0x1800eeea1  jnz     short loc_1800EEED9
0x1800eeea3  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800eeeaa  mov     edi, 80070057h
0x1800eeeaf  mov     rdx, rbx
0x1800eeeb2  lea     r8, aPcszoid; "pcszOid"
0x1800eeeb9  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800eeec0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800eeec5  lea     rdx, aPcszoid; "pcszOid"
0x1800eeecc  mov     rcx, rbx; unsigned __int16 *
0x1800eeecf  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800eeed4  jmp     loc_1800EF0A2
0x1800eeed9  test    r15, r15
0x1800eeedc  jnz     short loc_1800EEF09
0x1800eeede  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800eeee5  mov     edi, 80070057h
0x1800eeeea  mov     rdx, rbx
0x1800eeeed  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x1800eeef4  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800eeefb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800eef00  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x1800eef07  jmp     short loc_1800EEECC
0x1800eef09  test    rsi, rsi
0x1800eef0c  jnz     short loc_1800EEF39
0x1800eef0e  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800eef15  mov     edi, 80070057h
0x1800eef1a  mov     rdx, rbx
0x1800eef1d  lea     r8, stru_1801282C8
0x1800eef24  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800eef2b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800eef30  lea     rdx, stru_1801282C8; struct _CERT_CONTEXT *
0x1800eef37  jmp     short loc_1800EEECC
0x1800eef39  mov     [r8], r14
0x1800eef3c  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x1800eef41  test    rax, rax
0x1800eef44  jnz     short loc_1800EEF66
0x1800eef46  mov     r8, rbx
0x1800eef49  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800eef50  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x1800eef57  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800eef5c  mov     edi, 80092004h
0x1800eef61  jmp     loc_1800EF0A2
0x1800eef66  mov     r9d, [rax+10h]; cbEncoded
0x1800eef6a  lea     rcx, [rbp+arg_18]
0x1800eef6e  mov     r8, [rax+18h]; pbEncoded
0x1800eef72  xor     edi, edi
0x1800eef74  mov     [rsp+50h+pcbStructInfo], rcx; pcbStructInfo
0x1800eef79  lea     rcx, [rbp+hMem]
0x1800eef7d  mov     [rsp+50h+pvStructInfo], rcx; pvStructInfo
0x1800eef82  mov     ecx, [rsi]; dwCertEncodingType
0x1800eef84  mov     [rsp+50h+pDecodePara], rdi; pDecodePara
0x1800eef89  lea     edx, [rdi+19h]; lpszStructType
0x1800eef8c  mov     [rsp+50h+dwFlags], 8000h; dwFlags
0x1800eef94  call    cs:__imp_CryptDecodeObjectEx
0x1800eef9a  test    eax, eax
0x1800eef9c  jnz     short loc_1800EEFB0
0x1800eef9e  call    cs:__imp_GetLastError
0x1800eefa4  lea     rcx, aSCryptdecodeob; "%s: CryptDecodeObjectEx with error code"...
0x1800eefab  jmp     loc_1800EF069
0x1800eefb0  mov     rcx, [rbp+hMem]
0x1800eefb4  lea     rax, [rbp+pcchString]
0x1800eefb8  mov     ebx, 40000002h
0x1800eefbd  mov     qword ptr [rsp+50h+dwFlags], rax; pcchString
0x1800eefc2  xor     r9d, r9d; pszString
0x1800eefc5  mov     r8d, ebx; dwFlags
0x1800eefc8  mov     edx, [rcx]; cbBinary
0x1800eefca  mov     rcx, [rcx+8]; pbBinary
0x1800eefce  call    cs:__imp_CryptBinaryToStringW
0x1800eefd4  test    eax, eax
0x1800eefd6  jz      loc_1800EF05C
0x1800eefdc  mov     ecx, [rbp+pcchString]
0x1800eefdf  mov     eax, 2
0x1800eefe4  inc     ecx
0x1800eefe6  mul     rcx
0x1800eefe9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800eeff0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800eeff7  cmovb   rax, rcx
0x1800eeffb  mov     rcx, rax; unsigned __int64
0x1800eeffe  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800ef003  mov     r14, rax
0x1800ef006  test    rax, rax
0x1800ef009  jnz     short loc_1800EF025
0x1800ef00b  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800ef012  mov     edi, 8007000Eh
0x1800ef017  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x1800ef01e  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800ef023  jmp     short loc_1800EF0A2
0x1800ef025  mov     r8d, [rbp+pcchString]
0x1800ef029  xor     edx, edx; Val
0x1800ef02b  inc     r8d
0x1800ef02e  mov     rcx, r14; void *
0x1800ef031  add     r8, r8; Size
0x1800ef034  call    memset_0
0x1800ef039  mov     rcx, [rbp+hMem]
0x1800ef03d  lea     rax, [rbp+pcchString]
0x1800ef041  mov     r9, r14; pszString
0x1800ef044  mov     qword ptr [rsp+50h+dwFlags], rax; pcchString
0x1800ef049  mov     r8d, ebx; dwFlags
0x1800ef04c  mov     edx, [rcx]; cbBinary
0x1800ef04e  mov     rcx, [rcx+8]; pbBinary
0x1800ef052  call    cs:__imp_CryptBinaryToStringW
0x1800ef058  test    eax, eax
0x1800ef05a  jnz     short loc_1800EF092
0x1800ef05c  call    cs:__imp_GetLastError
0x1800ef062  lea     rcx, aSCryptbinaryto; "%s: CryptBinaryToStringW with error cod"...
0x1800ef069  mov     esi, eax
0x1800ef06b  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800ef072  mov     r8d, eax
0x1800ef075  mov     rdx, rbx
0x1800ef078  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ef07d  test    esi, esi
0x1800ef07f  jz      short loc_1800EF0A2
0x1800ef081  jg      short loc_1800EF087
0x1800ef083  mov     edi, esi
0x1800ef085  jmp     short loc_1800EF0A2
0x1800ef087  movzx   edi, si
0x1800ef08a  or      edi, 80070000h
0x1800ef090  jmp     short loc_1800EF0A2
0x1800ef092  mov     edx, [rbp+pcchString]
0x1800ef095  xor     ecx, ecx
0x1800ef097  mov     [r15], r14
0x1800ef09a  mov     [r14+rdx*2], cx
0x1800ef09f  xor     r14d, r14d
0x1800ef0a2  mov     rcx, r14; Block
0x1800ef0a5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ef0aa  mov     rcx, [rbp+hMem]; hMem
0x1800ef0ae  call    cs:__imp_LocalFree
0x1800ef0b4  mov     rbx, [rsp+50h+arg_8]
0x1800ef0bc  mov     eax, edi
0x1800ef0be  add     rsp, 50h
0x1800ef0c2  pop     r15
0x1800ef0c4  pop     r14
0x1800ef0c6  pop     rdi
0x1800ef0c7  pop     rsi
0x1800ef0c8  pop     rbp
0x1800ef0c9  retn
```
