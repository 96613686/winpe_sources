# CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x180024a28`
- end: `0x180024bfb`
- name: `?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `467`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x180024834`
- `0x180025c90`

## callees

- `0x18000febc`
- `0x180010218`
- `0x18001029c`
- `0x180013bd0`
- `0x1800249d4`
- `0x180024a28`
- `0x1800251e8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024be5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024be5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b53`
- `CRYPT32!CryptDecodeObjectEx` at `0x180024b49`
- `CRYPT32!CryptDecodeObjectEx` at `0x180024b49`

## string_xrefs

- `0x180024a66`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180024a80`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180024aa2`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180024acf`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180024afb`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180024b5c`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180024bb0`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180024b02`: `%s: Extension was not found in the certificate. OID: %hs.`

## pseudocode

```c
__int64 __fastcall CertificateUtil::FindExtensionGuidValueByOid(
        const char *a1,
        const struct _CERT_CONTEXT *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v3; // rsi
  unsigned int v7; // ebx
  const unsigned __int16 *v8; // rdx
  struct _CERT_EXTENSION *ExtensionByOid; // rax
  __int64 LastError; // rdi
  int v11; // eax
  HLOCAL hMem[5]; // [rsp+40h] [rbp-28h] BYREF
  DWORD pcbStructInfo; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int16 *v15; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  hMem[0] = 0;
  pcbStructInfo = 0;
  v15 = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::FindExtensionGuidValueByOid", L"pcszOid");
    v8 = L"pcszOid";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindExtensionGuidValueByOid", v8);
    goto LABEL_18;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      L"ppszOutBuffer");
    v8 = L"ppszOutBuffer";
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      &stru_18002C008);
    v8 = (const unsigned __int16 *)&stru_18002C008;
    goto LABEL_3;
  }
  *a3 = 0;
  ExtensionByOid = CertificateUtil::FindExtensionByOid(a1, a2);
  if ( ExtensionByOid )
  {
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
      v11 = CertificateUtil::GuidStringFromByteArray(*((const unsigned __int8 **)hMem[0] + 1), *(_DWORD *)hMem[0], &v15);
      v7 = v11;
      if ( v11 >= 0 )
      {
        *a3 = v15;
      }
      else
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"CertificateUtil::FindExtensionGuidValueByOid",
          L"CertificateUtil::GuidStringFromByteArray",
          (unsigned int)v11);
        v3 = v15;
      }
    }
    else
    {
      LastError = GetLastError();
      Logger::TraceError(
        L"%s: CryptDecodeObjectEx failed with error code: 0x%08x",
        L"CertificateUtil::FindExtensionGuidValueByOid",
        LastError);
      v7 = 0;
      if ( (_DWORD)LastError )
      {
        if ( (int)LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        else
          v7 = LastError;
      }
    }
  }
  else
  {
    Logger::TraceVerbose(
      L"%s: Extension was not found in the certificate. OID: %hs.",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      a1);
    v7 = -2146885628;
  }
LABEL_18:
  operator delete(v3);
  LocalFree(hMem[0]);
  return v7;
}

```

## disassembly

```asm
0x180024a28  mov     rax, rsp
0x180024a2b  mov     [rax+10h], rbx
0x180024a2f  push    rsi
0x180024a30  push    rdi
0x180024a31  push    r14
0x180024a33  sub     rsp, 50h
0x180024a37  xor     esi, esi
0x180024a39  mov     qword ptr [rax-28h], 0
0x180024a41  mov     dword ptr [rax+8], 0
0x180024a48  mov     rdi, r8
0x180024a4b  mov     [rax+20h], rsi
0x180024a4f  mov     r14, rdx
0x180024a52  mov     rbx, rcx
0x180024a55  test    rcx, rcx
0x180024a58  jnz     short loc_180024A91
0x180024a5a  lea     r8, aPcszoid; "pcszOid"
0x180024a61  mov     ebx, 80070057h
0x180024a66  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180024a6d  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180024a74  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180024a79  lea     rdx, aPcszoid; "pcszOid"
0x180024a80  lea     rcx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180024a87  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180024a8c  jmp     loc_180024BD8
0x180024a91  test    rdi, rdi
0x180024a94  jnz     short loc_180024ABE
0x180024a96  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x180024a9d  mov     ebx, 80070057h
0x180024aa2  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180024aa9  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180024ab0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180024ab5  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x180024abc  jmp     short loc_180024A80
0x180024abe  test    r14, r14
0x180024ac1  jnz     short loc_180024AEB
0x180024ac3  lea     r8, stru_18002C008
0x180024aca  mov     ebx, 80070057h
0x180024acf  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180024ad6  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180024add  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180024ae2  lea     rdx, stru_18002C008; struct _CERT_CONTEXT *
0x180024ae9  jmp     short loc_180024A80
0x180024aeb  mov     [r8], rsi
0x180024aee  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x180024af3  test    rax, rax
0x180024af6  jnz     short loc_180024B18
0x180024af8  mov     r8, rbx
0x180024afb  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180024b02  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x180024b09  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180024b0e  mov     ebx, 80092004h
0x180024b13  jmp     loc_180024BD8
0x180024b18  mov     r9d, [rax+10h]; cbEncoded
0x180024b1c  lea     rcx, [rsp+68h+arg_0]
0x180024b21  mov     r8, [rax+18h]; pbEncoded
0x180024b25  mov     edx, 19h; lpszStructType
0x180024b2a  mov     [rsp+68h+pcbStructInfo], rcx; pcbStructInfo
0x180024b2f  lea     rcx, [rsp+68h+hMem]
0x180024b34  mov     [rsp+68h+pvStructInfo], rcx; pvStructInfo
0x180024b39  mov     ecx, [r14]; dwCertEncodingType
0x180024b3c  mov     [rsp+68h+pDecodePara], rsi; pDecodePara
0x180024b41  mov     [rsp+68h+dwFlags], 8000h; dwFlags
0x180024b49  call    cs:__imp_CryptDecodeObjectEx
0x180024b4f  test    eax, eax
0x180024b51  jnz     short loc_180024B88
0x180024b53  call    cs:__imp_GetLastError
0x180024b59  mov     r8d, eax
0x180024b5c  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180024b63  lea     rcx, aSCryptdecodeob_0; "%s: CryptDecodeObjectEx failed with err"...
0x180024b6a  mov     edi, eax
0x180024b6c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180024b71  xor     ebx, ebx
0x180024b73  test    edi, edi
0x180024b75  jz      short loc_180024BD8
0x180024b77  jg      short loc_180024B7D
0x180024b79  mov     ebx, edi
0x180024b7b  jmp     short loc_180024BD8
0x180024b7d  movzx   ebx, di
0x180024b80  or      ebx, 80070000h
0x180024b86  jmp     short loc_180024BD8
0x180024b88  mov     rcx, [rsp+68h+hMem]
0x180024b8d  lea     r8, [rsp+68h+arg_18]; unsigned __int16 **
0x180024b95  mov     edx, [rcx]; unsigned int
0x180024b97  mov     rcx, [rcx+8]; unsigned __int8 *
0x180024b9b  call    ?GuidStringFromByteArray@CertificateUtil@@CAJPEBEKPEAPEAG@Z; CertificateUtil::GuidStringFromByteArray(uchar const *,ulong,ushort * *)
0x180024ba0  mov     ebx, eax
0x180024ba2  test    eax, eax
0x180024ba4  jns     short loc_180024BCD
0x180024ba6  mov     r9d, eax
0x180024ba9  lea     r8, aCertificateuti_3; "CertificateUtil::GuidStringFromByteArra"...
0x180024bb0  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180024bb7  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x180024bbe  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180024bc3  mov     rsi, [rsp+68h+arg_18]
0x180024bcb  jmp     short loc_180024BD8
0x180024bcd  mov     rax, [rsp+68h+arg_18]
0x180024bd5  mov     [rdi], rax
0x180024bd8  mov     rcx, rsi; Block
0x180024bdb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024be0  mov     rcx, [rsp+68h+hMem]; hMem
0x180024be5  call    cs:__imp_LocalFree
0x180024beb  mov     eax, ebx
0x180024bed  mov     rbx, [rsp+68h+arg_8]
0x180024bf2  add     rsp, 50h
0x180024bf6  pop     r14
0x180024bf8  pop     rdi
0x180024bf9  pop     rsi
0x180024bfa  retn
```
