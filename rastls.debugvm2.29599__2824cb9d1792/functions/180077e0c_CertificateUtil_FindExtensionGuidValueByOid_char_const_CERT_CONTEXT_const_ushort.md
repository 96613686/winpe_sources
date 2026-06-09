# CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x180077e0c`
- end: `0x180077fdf`
- name: `?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `467`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x180077698`
- `0x180079000`

## callees

- `0x18002c90c`
- `0x18002cb48`
- `0x18002ce0c`
- `0x180035664`
- `0x180077db8`
- `0x180077e0c`
- `0x1800785cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077f37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077f37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077fc9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077fc9`
- `CRYPT32!CryptDecodeObjectEx` at `0x180077f2d`
- `CRYPT32!CryptDecodeObjectEx` at `0x180077f2d`

## string_xrefs

- `0x180077e4a`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180077e64`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180077e86`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180077eb3`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180077edf`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180077f40`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180077f94`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180077ee6`: `%s: Extension was not found in the certificate. OID: %hs.`

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
      &stru_180087E98);
    v8 = (const unsigned __int16 *)&stru_180087E98;
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
0x180077e0c  mov     rax, rsp
0x180077e0f  mov     [rax+10h], rbx
0x180077e13  push    rsi
0x180077e14  push    rdi
0x180077e15  push    r14
0x180077e17  sub     rsp, 50h
0x180077e1b  xor     esi, esi
0x180077e1d  mov     qword ptr [rax-28h], 0
0x180077e25  mov     dword ptr [rax+8], 0
0x180077e2c  mov     rdi, r8
0x180077e2f  mov     [rax+20h], rsi
0x180077e33  mov     r14, rdx
0x180077e36  mov     rbx, rcx
0x180077e39  test    rcx, rcx
0x180077e3c  jnz     short loc_180077E75
0x180077e3e  lea     r8, aPcszoid; "pcszOid"
0x180077e45  mov     ebx, 80070057h
0x180077e4a  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180077e51  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180077e58  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077e5d  lea     rdx, aPcszoid; "pcszOid"
0x180077e64  lea     rcx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180077e6b  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180077e70  jmp     loc_180077FBC
0x180077e75  test    rdi, rdi
0x180077e78  jnz     short loc_180077EA2
0x180077e7a  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x180077e81  mov     ebx, 80070057h
0x180077e86  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180077e8d  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180077e94  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077e99  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x180077ea0  jmp     short loc_180077E64
0x180077ea2  test    r14, r14
0x180077ea5  jnz     short loc_180077ECF
0x180077ea7  lea     r8, stru_180087E98
0x180077eae  mov     ebx, 80070057h
0x180077eb3  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180077eba  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180077ec1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077ec6  lea     rdx, stru_180087E98; struct _CERT_CONTEXT *
0x180077ecd  jmp     short loc_180077E64
0x180077ecf  mov     [r8], rsi
0x180077ed2  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x180077ed7  test    rax, rax
0x180077eda  jnz     short loc_180077EFC
0x180077edc  mov     r8, rbx
0x180077edf  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180077ee6  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x180077eed  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180077ef2  mov     ebx, 80092004h
0x180077ef7  jmp     loc_180077FBC
0x180077efc  mov     r9d, [rax+10h]; cbEncoded
0x180077f00  lea     rcx, [rsp+68h+arg_0]
0x180077f05  mov     r8, [rax+18h]; pbEncoded
0x180077f09  mov     edx, 19h; lpszStructType
0x180077f0e  mov     [rsp+68h+pcbStructInfo], rcx; pcbStructInfo
0x180077f13  lea     rcx, [rsp+68h+hMem]
0x180077f18  mov     [rsp+68h+pvStructInfo], rcx; pvStructInfo
0x180077f1d  mov     ecx, [r14]; dwCertEncodingType
0x180077f20  mov     [rsp+68h+pDecodePara], rsi; pDecodePara
0x180077f25  mov     [rsp+68h+dwFlags], 8000h; dwFlags
0x180077f2d  call    cs:__imp_CryptDecodeObjectEx
0x180077f33  test    eax, eax
0x180077f35  jnz     short loc_180077F6C
0x180077f37  call    cs:__imp_GetLastError
0x180077f3d  mov     r8d, eax
0x180077f40  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180077f47  lea     rcx, aSCryptdecodeob_0; "%s: CryptDecodeObjectEx failed with err"...
0x180077f4e  mov     edi, eax
0x180077f50  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077f55  xor     ebx, ebx
0x180077f57  test    edi, edi
0x180077f59  jz      short loc_180077FBC
0x180077f5b  jg      short loc_180077F61
0x180077f5d  mov     ebx, edi
0x180077f5f  jmp     short loc_180077FBC
0x180077f61  movzx   ebx, di
0x180077f64  or      ebx, 80070000h
0x180077f6a  jmp     short loc_180077FBC
0x180077f6c  mov     rcx, [rsp+68h+hMem]
0x180077f71  lea     r8, [rsp+68h+arg_18]; unsigned __int16 **
0x180077f79  mov     edx, [rcx]; unsigned int
0x180077f7b  mov     rcx, [rcx+8]; unsigned __int8 *
0x180077f7f  call    ?GuidStringFromByteArray@CertificateUtil@@CAJPEBEKPEAPEAG@Z; CertificateUtil::GuidStringFromByteArray(uchar const *,ulong,ushort * *)
0x180077f84  mov     ebx, eax
0x180077f86  test    eax, eax
0x180077f88  jns     short loc_180077FB1
0x180077f8a  mov     r9d, eax
0x180077f8d  lea     r8, aCertificateuti_3; "CertificateUtil::GuidStringFromByteArra"...
0x180077f94  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180077f9b  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x180077fa2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077fa7  mov     rsi, [rsp+68h+arg_18]
0x180077faf  jmp     short loc_180077FBC
0x180077fb1  mov     rax, [rsp+68h+arg_18]
0x180077fb9  mov     [rdi], rax
0x180077fbc  mov     rcx, rsi; Block
0x180077fbf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180077fc4  mov     rcx, [rsp+68h+hMem]; hMem
0x180077fc9  call    cs:__imp_LocalFree
0x180077fcf  mov     eax, ebx
0x180077fd1  mov     rbx, [rsp+68h+arg_8]
0x180077fd6  add     rsp, 50h
0x180077fda  pop     r14
0x180077fdc  pop     rdi
0x180077fdd  pop     rsi
0x180077fde  retn
```
