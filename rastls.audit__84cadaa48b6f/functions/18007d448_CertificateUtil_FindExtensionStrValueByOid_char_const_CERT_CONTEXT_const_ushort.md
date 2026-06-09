# CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x18007d448`
- end: `0x18007d6ce`
- name: `?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `646`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x18007ca8c`

## callees

- `0x18002ee04`
- `0x18002f048`
- `0x18002f324`
- `0x180038254`
- `0x180038e64`
- `0x18003a3ac`
- `0x18007d200`
- `0x18007d448`
- `0x18007dd0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d653`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007d6ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007d6ab`
- `CRYPT32!CryptBinaryToStringW` at `0x18007d5b6`
- `CRYPT32!CryptBinaryToStringW` at `0x18007d643`
- `CRYPT32!CryptBinaryToStringW` at `0x18007d5b6`
- `CRYPT32!CryptBinaryToStringW` at `0x18007d643`
- `CRYPT32!CryptDecodeObjectEx` at `0x18007d570`
- `CRYPT32!CryptDecodeObjectEx` at `0x18007d570`

## string_xrefs

- `0x18007d47f`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18007d4ba`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18007d4ea`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18007d525`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18007d5f9`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18007d668`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18007d52c`: `%s: Extension was not found in the certificate. OID: %hs.`

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
      &stru_18008DE98);
    v8 = (const unsigned __int16 *)&stru_18008DE98;
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
0x18007d448  mov     [rsp-28h+arg_8], rbx
0x18007d44d  push    rbp
0x18007d44e  push    rsi
0x18007d44f  push    rdi
0x18007d450  push    r14
0x18007d452  push    r15
0x18007d454  mov     rbp, rsp
0x18007d457  sub     rsp, 50h
0x18007d45b  xor     r14d, r14d
0x18007d45e  mov     [rbp+hMem], 0
0x18007d466  mov     [rbp+arg_18], 0
0x18007d46d  mov     r15, r8
0x18007d470  mov     [rbp+pcchString], r14d
0x18007d474  mov     rsi, rdx
0x18007d477  mov     rbx, rcx
0x18007d47a  test    rcx, rcx
0x18007d47d  jnz     short loc_18007D4B5
0x18007d47f  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18007d486  mov     edi, 80070057h
0x18007d48b  mov     rdx, rbx
0x18007d48e  lea     r8, aPcszoid; "pcszOid"
0x18007d495  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007d49c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007d4a1  lea     rdx, aPcszoid; "pcszOid"
0x18007d4a8  mov     rcx, rbx; unsigned __int16 *
0x18007d4ab  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18007d4b0  jmp     loc_18007D69F
0x18007d4b5  test    r15, r15
0x18007d4b8  jnz     short loc_18007D4E5
0x18007d4ba  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18007d4c1  mov     edi, 80070057h
0x18007d4c6  mov     rdx, rbx
0x18007d4c9  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x18007d4d0  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007d4d7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007d4dc  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x18007d4e3  jmp     short loc_18007D4A8
0x18007d4e5  test    rsi, rsi
0x18007d4e8  jnz     short loc_18007D515
0x18007d4ea  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18007d4f1  mov     edi, 80070057h
0x18007d4f6  mov     rdx, rbx
0x18007d4f9  lea     r8, stru_18008DE98
0x18007d500  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007d507  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007d50c  lea     rdx, stru_18008DE98; struct _CERT_CONTEXT *
0x18007d513  jmp     short loc_18007D4A8
0x18007d515  mov     [r8], r14
0x18007d518  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x18007d51d  test    rax, rax
0x18007d520  jnz     short loc_18007D542
0x18007d522  mov     r8, rbx
0x18007d525  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18007d52c  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x18007d533  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007d538  mov     edi, 80092004h
0x18007d53d  jmp     loc_18007D69F
0x18007d542  mov     r9d, [rax+10h]; cbEncoded
0x18007d546  lea     rcx, [rbp+arg_18]
0x18007d54a  mov     r8, [rax+18h]; pbEncoded
0x18007d54e  xor     edi, edi
0x18007d550  mov     [rsp+50h+pcbStructInfo], rcx; pcbStructInfo
0x18007d555  lea     rcx, [rbp+hMem]
0x18007d559  mov     [rsp+50h+pvStructInfo], rcx; pvStructInfo
0x18007d55e  mov     ecx, [rsi]; dwCertEncodingType
0x18007d560  mov     [rsp+50h+pDecodePara], rdi; pDecodePara
0x18007d565  lea     edx, [rdi+19h]; lpszStructType
0x18007d568  mov     [rsp+50h+dwFlags], 8000h; dwFlags
0x18007d570  call    cs:__imp_CryptDecodeObjectEx
0x18007d577  nop     dword ptr [rax+rax+00h]
0x18007d57c  test    eax, eax
0x18007d57e  jnz     short loc_18007D598
0x18007d580  call    cs:__imp_GetLastError
0x18007d587  nop     dword ptr [rax+rax+00h]
0x18007d58c  lea     rcx, aSCryptdecodeob; "%s: CryptDecodeObjectEx with error code"...
0x18007d593  jmp     loc_18007D666
0x18007d598  mov     rcx, [rbp+hMem]
0x18007d59c  lea     rax, [rbp+pcchString]
0x18007d5a0  mov     ebx, 40000002h
0x18007d5a5  mov     qword ptr [rsp+50h+dwFlags], rax; pcchString
0x18007d5aa  xor     r9d, r9d; pszString
0x18007d5ad  mov     r8d, ebx; dwFlags
0x18007d5b0  mov     edx, [rcx]; cbBinary
0x18007d5b2  mov     rcx, [rcx+8]; pbBinary
0x18007d5b6  call    cs:__imp_CryptBinaryToStringW
0x18007d5bd  nop     dword ptr [rax+rax+00h]
0x18007d5c2  test    eax, eax
0x18007d5c4  jz      loc_18007D653
0x18007d5ca  mov     ecx, [rbp+pcchString]
0x18007d5cd  mov     eax, 2
0x18007d5d2  inc     ecx
0x18007d5d4  mul     rcx
0x18007d5d7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18007d5de  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007d5e5  cmovb   rax, rcx
0x18007d5e9  mov     rcx, rax; unsigned __int64
0x18007d5ec  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18007d5f1  mov     r14, rax
0x18007d5f4  test    rax, rax
0x18007d5f7  jnz     short loc_18007D616
0x18007d5f9  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18007d600  mov     edi, 8007000Eh
0x18007d605  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18007d60c  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18007d611  jmp     loc_18007D69F
0x18007d616  mov     r8d, [rbp+pcchString]
0x18007d61a  xor     edx, edx; Val
0x18007d61c  inc     r8d
0x18007d61f  mov     rcx, r14; void *
0x18007d622  add     r8, r8; Size
0x18007d625  call    memset_0
0x18007d62a  mov     rcx, [rbp+hMem]
0x18007d62e  lea     rax, [rbp+pcchString]
0x18007d632  mov     r9, r14; pszString
0x18007d635  mov     qword ptr [rsp+50h+dwFlags], rax; pcchString
0x18007d63a  mov     r8d, ebx; dwFlags
0x18007d63d  mov     edx, [rcx]; cbBinary
0x18007d63f  mov     rcx, [rcx+8]; pbBinary
0x18007d643  call    cs:__imp_CryptBinaryToStringW
0x18007d64a  nop     dword ptr [rax+rax+00h]
0x18007d64f  test    eax, eax
0x18007d651  jnz     short loc_18007D68F
0x18007d653  call    cs:__imp_GetLastError
0x18007d65a  nop     dword ptr [rax+rax+00h]
0x18007d65f  lea     rcx, aSCryptbinaryto; "%s: CryptBinaryToStringW with error cod"...
0x18007d666  mov     esi, eax
0x18007d668  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18007d66f  mov     r8d, eax
0x18007d672  mov     rdx, rbx
0x18007d675  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007d67a  test    esi, esi
0x18007d67c  jz      short loc_18007D69F
0x18007d67e  jg      short loc_18007D684
0x18007d680  mov     edi, esi
0x18007d682  jmp     short loc_18007D69F
0x18007d684  movzx   edi, si
0x18007d687  or      edi, 80070000h
0x18007d68d  jmp     short loc_18007D69F
0x18007d68f  mov     edx, [rbp+pcchString]
0x18007d692  xor     ecx, ecx
0x18007d694  mov     [r15], r14
0x18007d697  mov     [r14+rdx*2], cx
0x18007d69c  xor     r14d, r14d
0x18007d69f  mov     rcx, r14; Block
0x18007d6a2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007d6a7  mov     rcx, [rbp+hMem]; hMem
0x18007d6ab  call    cs:__imp_LocalFree
0x18007d6b2  nop     dword ptr [rax+rax+00h]
0x18007d6b7  mov     rbx, [rsp+50h+arg_8]
0x18007d6bf  mov     eax, edi
0x18007d6c1  add     rsp, 50h
0x18007d6c5  pop     r15
0x18007d6c7  pop     r14
0x18007d6c9  pop     rdi
0x18007d6ca  pop     rsi
0x18007d6cb  pop     rbp
0x18007d6cc  retn
```
