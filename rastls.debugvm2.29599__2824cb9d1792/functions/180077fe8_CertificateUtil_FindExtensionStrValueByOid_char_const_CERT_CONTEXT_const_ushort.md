# CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x180077fe8`
- end: `0x180078246`
- name: `?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `606`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x180077698`

## callees

- `0x18002c90c`
- `0x18002cb48`
- `0x18002ce0c`
- `0x180035664`
- `0x180036254`
- `0x18003779c`
- `0x180077db8`
- `0x180077fe8`
- `0x18007885c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007811a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800781d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007811a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800781d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007822a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007822a`
- `CRYPT32!CryptBinaryToStringW` at `0x18007814a`
- `CRYPT32!CryptBinaryToStringW` at `0x1800781ce`
- `CRYPT32!CryptBinaryToStringW` at `0x18007814a`
- `CRYPT32!CryptBinaryToStringW` at `0x1800781ce`
- `CRYPT32!CryptDecodeObjectEx` at `0x180078110`
- `CRYPT32!CryptDecodeObjectEx` at `0x180078110`

## string_xrefs

- `0x18007801f`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18007805a`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18007808a`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800780c5`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180078187`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800781e7`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800780cc`: `%s: Extension was not found in the certificate. OID: %hs.`

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
      &stru_180087E98);
    v8 = (const unsigned __int16 *)&stru_180087E98;
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
0x180077fe8  mov     [rsp-28h+arg_8], rbx
0x180077fed  push    rbp
0x180077fee  push    rsi
0x180077fef  push    rdi
0x180077ff0  push    r14
0x180077ff2  push    r15
0x180077ff4  mov     rbp, rsp
0x180077ff7  sub     rsp, 50h
0x180077ffb  xor     r14d, r14d
0x180077ffe  mov     [rbp+hMem], 0
0x180078006  mov     [rbp+arg_18], 0
0x18007800d  mov     r15, r8
0x180078010  mov     [rbp+pcchString], r14d
0x180078014  mov     rsi, rdx
0x180078017  mov     rbx, rcx
0x18007801a  test    rcx, rcx
0x18007801d  jnz     short loc_180078055
0x18007801f  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180078026  mov     edi, 80070057h
0x18007802b  mov     rdx, rbx
0x18007802e  lea     r8, aPcszoid; "pcszOid"
0x180078035  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007803c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180078041  lea     rdx, aPcszoid; "pcszOid"
0x180078048  mov     rcx, rbx; unsigned __int16 *
0x18007804b  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180078050  jmp     loc_18007821E
0x180078055  test    r15, r15
0x180078058  jnz     short loc_180078085
0x18007805a  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180078061  mov     edi, 80070057h
0x180078066  mov     rdx, rbx
0x180078069  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x180078070  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180078077  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007807c  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x180078083  jmp     short loc_180078048
0x180078085  test    rsi, rsi
0x180078088  jnz     short loc_1800780B5
0x18007808a  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180078091  mov     edi, 80070057h
0x180078096  mov     rdx, rbx
0x180078099  lea     r8, stru_180087E98
0x1800780a0  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800780a7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800780ac  lea     rdx, stru_180087E98; struct _CERT_CONTEXT *
0x1800780b3  jmp     short loc_180078048
0x1800780b5  mov     [r8], r14
0x1800780b8  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x1800780bd  test    rax, rax
0x1800780c0  jnz     short loc_1800780E2
0x1800780c2  mov     r8, rbx
0x1800780c5  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800780cc  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x1800780d3  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800780d8  mov     edi, 80092004h
0x1800780dd  jmp     loc_18007821E
0x1800780e2  mov     r9d, [rax+10h]; cbEncoded
0x1800780e6  lea     rcx, [rbp+arg_18]
0x1800780ea  mov     r8, [rax+18h]; pbEncoded
0x1800780ee  xor     edi, edi
0x1800780f0  mov     [rsp+50h+pcbStructInfo], rcx; pcbStructInfo
0x1800780f5  lea     rcx, [rbp+hMem]
0x1800780f9  mov     [rsp+50h+pvStructInfo], rcx; pvStructInfo
0x1800780fe  mov     ecx, [rsi]; dwCertEncodingType
0x180078100  mov     [rsp+50h+pDecodePara], rdi; pDecodePara
0x180078105  lea     edx, [rdi+19h]; lpszStructType
0x180078108  mov     [rsp+50h+dwFlags], 8000h; dwFlags
0x180078110  call    cs:__imp_CryptDecodeObjectEx
0x180078116  test    eax, eax
0x180078118  jnz     short loc_18007812C
0x18007811a  call    cs:__imp_GetLastError
0x180078120  lea     rcx, aSCryptdecodeob; "%s: CryptDecodeObjectEx with error code"...
0x180078127  jmp     loc_1800781E5
0x18007812c  mov     rcx, [rbp+hMem]
0x180078130  lea     rax, [rbp+pcchString]
0x180078134  mov     ebx, 40000002h
0x180078139  mov     qword ptr [rsp+50h+dwFlags], rax; pcchString
0x18007813e  xor     r9d, r9d; pszString
0x180078141  mov     r8d, ebx; dwFlags
0x180078144  mov     edx, [rcx]; cbBinary
0x180078146  mov     rcx, [rcx+8]; pbBinary
0x18007814a  call    cs:__imp_CryptBinaryToStringW
0x180078150  test    eax, eax
0x180078152  jz      loc_1800781D8
0x180078158  mov     ecx, [rbp+pcchString]
0x18007815b  mov     eax, 2
0x180078160  inc     ecx
0x180078162  mul     rcx
0x180078165  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18007816c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180078173  cmovb   rax, rcx
0x180078177  mov     rcx, rax; unsigned __int64
0x18007817a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18007817f  mov     r14, rax
0x180078182  test    rax, rax
0x180078185  jnz     short loc_1800781A1
0x180078187  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18007818e  mov     edi, 8007000Eh
0x180078193  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18007819a  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18007819f  jmp     short loc_18007821E
0x1800781a1  mov     r8d, [rbp+pcchString]
0x1800781a5  xor     edx, edx; Val
0x1800781a7  inc     r8d
0x1800781aa  mov     rcx, r14; void *
0x1800781ad  add     r8, r8; Size
0x1800781b0  call    memset_0
0x1800781b5  mov     rcx, [rbp+hMem]
0x1800781b9  lea     rax, [rbp+pcchString]
0x1800781bd  mov     r9, r14; pszString
0x1800781c0  mov     qword ptr [rsp+50h+dwFlags], rax; pcchString
0x1800781c5  mov     r8d, ebx; dwFlags
0x1800781c8  mov     edx, [rcx]; cbBinary
0x1800781ca  mov     rcx, [rcx+8]; pbBinary
0x1800781ce  call    cs:__imp_CryptBinaryToStringW
0x1800781d4  test    eax, eax
0x1800781d6  jnz     short loc_18007820E
0x1800781d8  call    cs:__imp_GetLastError
0x1800781de  lea     rcx, aSCryptbinaryto; "%s: CryptBinaryToStringW with error cod"...
0x1800781e5  mov     esi, eax
0x1800781e7  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800781ee  mov     r8d, eax
0x1800781f1  mov     rdx, rbx
0x1800781f4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800781f9  test    esi, esi
0x1800781fb  jz      short loc_18007821E
0x1800781fd  jg      short loc_180078203
0x1800781ff  mov     edi, esi
0x180078201  jmp     short loc_18007821E
0x180078203  movzx   edi, si
0x180078206  or      edi, 80070000h
0x18007820c  jmp     short loc_18007821E
0x18007820e  mov     edx, [rbp+pcchString]
0x180078211  xor     ecx, ecx
0x180078213  mov     [r15], r14
0x180078216  mov     [r14+rdx*2], cx
0x18007821b  xor     r14d, r14d
0x18007821e  mov     rcx, r14; Block
0x180078221  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180078226  mov     rcx, [rbp+hMem]; hMem
0x18007822a  call    cs:__imp_LocalFree
0x180078230  mov     rbx, [rsp+50h+arg_8]
0x180078238  mov     eax, edi
0x18007823a  add     rsp, 50h
0x18007823e  pop     r15
0x180078240  pop     r14
0x180078242  pop     rdi
0x180078243  pop     rsi
0x180078244  pop     rbp
0x180078245  retn
```
