# CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x18007d25c`
- end: `0x18007d442`
- name: `?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `486`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x18007ca8c`
- `0x18007e4cc`

## callees

- `0x18002ee04`
- `0x18002f048`
- `0x18002f324`
- `0x180038254`
- `0x18007d200`
- `0x18007d25c`
- `0x18007da7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d38d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d38d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007d425`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007d425`
- `CRYPT32!CryptDecodeObjectEx` at `0x18007d37d`
- `CRYPT32!CryptDecodeObjectEx` at `0x18007d37d`

## string_xrefs

- `0x18007d336`: `%s: Extension was not found in the certificate. OID: %hs.`
- `0x18007d29a`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18007d2b4`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18007d2d6`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18007d303`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18007d32f`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18007d39c`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18007d3f0`: `CertificateUtil::FindExtensionGuidValueByOid`

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
      &stru_18008DE98);
    v8 = (const unsigned __int16 *)&stru_18008DE98;
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
0x18007d25c  mov     rax, rsp
0x18007d25f  mov     [rax+10h], rbx
0x18007d263  push    rsi
0x18007d264  push    rdi
0x18007d265  push    r14
0x18007d267  sub     rsp, 50h
0x18007d26b  xor     esi, esi
0x18007d26d  mov     qword ptr [rax-28h], 0
0x18007d275  mov     dword ptr [rax+8], 0
0x18007d27c  mov     rdi, r8
0x18007d27f  mov     [rax+20h], rsi
0x18007d283  mov     r14, rdx
0x18007d286  mov     rbx, rcx
0x18007d289  test    rcx, rcx
0x18007d28c  jnz     short loc_18007D2C5
0x18007d28e  lea     r8, aPcszoid; "pcszOid"
0x18007d295  mov     ebx, 80070057h
0x18007d29a  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18007d2a1  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007d2a8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007d2ad  lea     rdx, aPcszoid; "pcszOid"
0x18007d2b4  lea     rcx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18007d2bb  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18007d2c0  jmp     loc_18007D418
0x18007d2c5  test    rdi, rdi
0x18007d2c8  jnz     short loc_18007D2F2
0x18007d2ca  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x18007d2d1  mov     ebx, 80070057h
0x18007d2d6  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18007d2dd  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007d2e4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007d2e9  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x18007d2f0  jmp     short loc_18007D2B4
0x18007d2f2  test    r14, r14
0x18007d2f5  jnz     short loc_18007D31F
0x18007d2f7  lea     r8, stru_18008DE98
0x18007d2fe  mov     ebx, 80070057h
0x18007d303  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18007d30a  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007d311  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007d316  lea     rdx, stru_18008DE98; struct _CERT_CONTEXT *
0x18007d31d  jmp     short loc_18007D2B4
0x18007d31f  mov     [r8], rsi
0x18007d322  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x18007d327  test    rax, rax
0x18007d32a  jnz     short loc_18007D34C
0x18007d32c  mov     r8, rbx
0x18007d32f  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18007d336  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x18007d33d  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007d342  mov     ebx, 80092004h
0x18007d347  jmp     loc_18007D418
0x18007d34c  mov     r9d, [rax+10h]; cbEncoded
0x18007d350  lea     rcx, [rsp+68h+arg_0]
0x18007d355  mov     r8, [rax+18h]; pbEncoded
0x18007d359  mov     edx, 19h; lpszStructType
0x18007d35e  mov     [rsp+68h+pcbStructInfo], rcx; pcbStructInfo
0x18007d363  lea     rcx, [rsp+68h+hMem]
0x18007d368  mov     [rsp+68h+pvStructInfo], rcx; pvStructInfo
0x18007d36d  mov     ecx, [r14]; dwCertEncodingType
0x18007d370  mov     [rsp+68h+pDecodePara], rsi; pDecodePara
0x18007d375  mov     [rsp+68h+dwFlags], 8000h; dwFlags
0x18007d37d  call    cs:__imp_CryptDecodeObjectEx
0x18007d384  nop     dword ptr [rax+rax+00h]
0x18007d389  test    eax, eax
0x18007d38b  jnz     short loc_18007D3C8
0x18007d38d  call    cs:__imp_GetLastError
0x18007d394  nop     dword ptr [rax+rax+00h]
0x18007d399  mov     r8d, eax
0x18007d39c  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18007d3a3  lea     rcx, aSCryptdecodeob_0; "%s: CryptDecodeObjectEx failed with err"...
0x18007d3aa  mov     edi, eax
0x18007d3ac  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007d3b1  xor     ebx, ebx
0x18007d3b3  test    edi, edi
0x18007d3b5  jz      short loc_18007D418
0x18007d3b7  jg      short loc_18007D3BD
0x18007d3b9  mov     ebx, edi
0x18007d3bb  jmp     short loc_18007D418
0x18007d3bd  movzx   ebx, di
0x18007d3c0  or      ebx, 80070000h
0x18007d3c6  jmp     short loc_18007D418
0x18007d3c8  mov     rcx, [rsp+68h+hMem]
0x18007d3cd  lea     r8, [rsp+68h+arg_18]; unsigned __int16 **
0x18007d3d5  mov     edx, [rcx]; unsigned int
0x18007d3d7  mov     rcx, [rcx+8]; unsigned __int8 *
0x18007d3db  call    ?GuidStringFromByteArray@CertificateUtil@@CAJPEBEKPEAPEAG@Z; CertificateUtil::GuidStringFromByteArray(uchar const *,ulong,ushort * *)
0x18007d3e0  mov     ebx, eax
0x18007d3e2  test    eax, eax
0x18007d3e4  jns     short loc_18007D40D
0x18007d3e6  mov     r9d, eax
0x18007d3e9  lea     r8, aCertificateuti_3; "CertificateUtil::GuidStringFromByteArra"...
0x18007d3f0  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18007d3f7  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x18007d3fe  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007d403  mov     rsi, [rsp+68h+arg_18]
0x18007d40b  jmp     short loc_18007D418
0x18007d40d  mov     rax, [rsp+68h+arg_18]
0x18007d415  mov     [rdi], rax
0x18007d418  mov     rcx, rsi; Block
0x18007d41b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007d420  mov     rcx, [rsp+68h+hMem]; hMem
0x18007d425  call    cs:__imp_LocalFree
0x18007d42c  nop     dword ptr [rax+rax+00h]
0x18007d431  mov     eax, ebx
0x18007d433  mov     rbx, [rsp+68h+arg_8]
0x18007d438  add     rsp, 50h
0x18007d43c  pop     r14
0x18007d43e  pop     rdi
0x18007d43f  pop     rsi
0x18007d440  retn
```
