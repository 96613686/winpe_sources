# CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x180024c04`
- end: `0x180024e62`
- name: `?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `606`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x180024834`

## callees

- `0x18000febc`
- `0x180010218`
- `0x18001029c`
- `0x180013bd0`
- `0x180014610`
- `0x1800149b0`
- `0x1800249d4`
- `0x180024c04`
- `0x180025468`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024e46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024e46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024df4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024df4`
- `CRYPT32!CryptBinaryToStringW` at `0x180024d66`
- `CRYPT32!CryptBinaryToStringW` at `0x180024dea`
- `CRYPT32!CryptBinaryToStringW` at `0x180024d66`
- `CRYPT32!CryptBinaryToStringW` at `0x180024dea`
- `CRYPT32!CryptDecodeObjectEx` at `0x180024d2c`
- `CRYPT32!CryptDecodeObjectEx` at `0x180024d2c`

## string_xrefs

- `0x180024c3b`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180024c76`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180024ca6`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180024ce1`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180024da3`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180024e03`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180024ce8`: `%s: Extension was not found in the certificate. OID: %hs.`

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
      &stru_18002C008);
    v8 = (const unsigned __int16 *)&stru_18002C008;
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
        v13 = (unsigned __int16 *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
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
0x180024c04  mov     [rsp-28h+arg_8], rbx
0x180024c09  push    rbp
0x180024c0a  push    rsi
0x180024c0b  push    rdi
0x180024c0c  push    r14
0x180024c0e  push    r15
0x180024c10  mov     rbp, rsp
0x180024c13  sub     rsp, 50h
0x180024c17  xor     r14d, r14d
0x180024c1a  mov     [rbp+hMem], 0
0x180024c22  mov     [rbp+arg_18], 0
0x180024c29  mov     r15, r8
0x180024c2c  mov     [rbp+pcchString], r14d
0x180024c30  mov     rsi, rdx
0x180024c33  mov     rbx, rcx
0x180024c36  test    rcx, rcx
0x180024c39  jnz     short loc_180024C71
0x180024c3b  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180024c42  mov     edi, 80070057h
0x180024c47  mov     rdx, rbx
0x180024c4a  lea     r8, aPcszoid; "pcszOid"
0x180024c51  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180024c58  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180024c5d  lea     rdx, aPcszoid; "pcszOid"
0x180024c64  mov     rcx, rbx; unsigned __int16 *
0x180024c67  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180024c6c  jmp     loc_180024E3A
0x180024c71  test    r15, r15
0x180024c74  jnz     short loc_180024CA1
0x180024c76  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180024c7d  mov     edi, 80070057h
0x180024c82  mov     rdx, rbx
0x180024c85  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x180024c8c  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180024c93  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180024c98  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x180024c9f  jmp     short loc_180024C64
0x180024ca1  test    rsi, rsi
0x180024ca4  jnz     short loc_180024CD1
0x180024ca6  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180024cad  mov     edi, 80070057h
0x180024cb2  mov     rdx, rbx
0x180024cb5  lea     r8, stru_18002C008
0x180024cbc  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180024cc3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180024cc8  lea     rdx, stru_18002C008; struct _CERT_CONTEXT *
0x180024ccf  jmp     short loc_180024C64
0x180024cd1  mov     [r8], r14
0x180024cd4  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x180024cd9  test    rax, rax
0x180024cdc  jnz     short loc_180024CFE
0x180024cde  mov     r8, rbx
0x180024ce1  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180024ce8  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x180024cef  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180024cf4  mov     edi, 80092004h
0x180024cf9  jmp     loc_180024E3A
0x180024cfe  mov     r9d, [rax+10h]; cbEncoded
0x180024d02  lea     rcx, [rbp+arg_18]
0x180024d06  mov     r8, [rax+18h]; pbEncoded
0x180024d0a  xor     edi, edi
0x180024d0c  mov     [rsp+50h+pcbStructInfo], rcx; pcbStructInfo
0x180024d11  lea     rcx, [rbp+hMem]
0x180024d15  mov     [rsp+50h+pvStructInfo], rcx; pvStructInfo
0x180024d1a  mov     ecx, [rsi]; dwCertEncodingType
0x180024d1c  mov     [rsp+50h+pDecodePara], rdi; pDecodePara
0x180024d21  lea     edx, [rdi+19h]; lpszStructType
0x180024d24  mov     [rsp+50h+dwFlags], 8000h; dwFlags
0x180024d2c  call    cs:__imp_CryptDecodeObjectEx
0x180024d32  test    eax, eax
0x180024d34  jnz     short loc_180024D48
0x180024d36  call    cs:__imp_GetLastError
0x180024d3c  lea     rcx, aSCryptdecodeob; "%s: CryptDecodeObjectEx with error code"...
0x180024d43  jmp     loc_180024E01
0x180024d48  mov     rcx, [rbp+hMem]
0x180024d4c  lea     rax, [rbp+pcchString]
0x180024d50  mov     ebx, 40000002h
0x180024d55  mov     qword ptr [rsp+50h+dwFlags], rax; pcchString
0x180024d5a  xor     r9d, r9d; pszString
0x180024d5d  mov     r8d, ebx; dwFlags
0x180024d60  mov     edx, [rcx]; cbBinary
0x180024d62  mov     rcx, [rcx+8]; pbBinary
0x180024d66  call    cs:__imp_CryptBinaryToStringW
0x180024d6c  test    eax, eax
0x180024d6e  jz      loc_180024DF4
0x180024d74  mov     ecx, [rbp+pcchString]
0x180024d77  mov     eax, 2
0x180024d7c  inc     ecx
0x180024d7e  mul     rcx
0x180024d81  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180024d88  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024d8f  cmovb   rax, rcx
0x180024d93  mov     rcx, rax; unsigned __int64
0x180024d96  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180024d9b  mov     r14, rax
0x180024d9e  test    rax, rax
0x180024da1  jnz     short loc_180024DBD
0x180024da3  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180024daa  mov     edi, 8007000Eh
0x180024daf  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x180024db6  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180024dbb  jmp     short loc_180024E3A
0x180024dbd  mov     r8d, [rbp+pcchString]
0x180024dc1  xor     edx, edx; Val
0x180024dc3  inc     r8d
0x180024dc6  mov     rcx, r14; void *
0x180024dc9  add     r8, r8; Size
0x180024dcc  call    memset_0
0x180024dd1  mov     rcx, [rbp+hMem]
0x180024dd5  lea     rax, [rbp+pcchString]
0x180024dd9  mov     r9, r14; pszString
0x180024ddc  mov     qword ptr [rsp+50h+dwFlags], rax; pcchString
0x180024de1  mov     r8d, ebx; dwFlags
0x180024de4  mov     edx, [rcx]; cbBinary
0x180024de6  mov     rcx, [rcx+8]; pbBinary
0x180024dea  call    cs:__imp_CryptBinaryToStringW
0x180024df0  test    eax, eax
0x180024df2  jnz     short loc_180024E2A
0x180024df4  call    cs:__imp_GetLastError
0x180024dfa  lea     rcx, aSCryptbinaryto; "%s: CryptBinaryToStringW with error cod"...
0x180024e01  mov     esi, eax
0x180024e03  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180024e0a  mov     r8d, eax
0x180024e0d  mov     rdx, rbx
0x180024e10  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180024e15  test    esi, esi
0x180024e17  jz      short loc_180024E3A
0x180024e19  jg      short loc_180024E1F
0x180024e1b  mov     edi, esi
0x180024e1d  jmp     short loc_180024E3A
0x180024e1f  movzx   edi, si
0x180024e22  or      edi, 80070000h
0x180024e28  jmp     short loc_180024E3A
0x180024e2a  mov     edx, [rbp+pcchString]
0x180024e2d  xor     ecx, ecx
0x180024e2f  mov     [r15], r14
0x180024e32  mov     [r14+rdx*2], cx
0x180024e37  xor     r14d, r14d
0x180024e3a  mov     rcx, r14; Block
0x180024e3d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024e42  mov     rcx, [rbp+hMem]; hMem
0x180024e46  call    cs:__imp_LocalFree
0x180024e4c  mov     rbx, [rsp+50h+arg_8]
0x180024e54  mov     eax, edi
0x180024e56  add     rsp, 50h
0x180024e5a  pop     r15
0x180024e5c  pop     r14
0x180024e5e  pop     rdi
0x180024e5f  pop     rsi
0x180024e60  pop     rbp
0x180024e61  retn
```
