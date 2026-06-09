# CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x1800eec90`
- end: `0x1800eee63`
- name: `?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `467`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x1800eea9c`
- `0x1800f0024`

## callees

- `0x18006f680`
- `0x18006f6dc`
- `0x18006f848`
- `0x180070f00`
- `0x1800eec3c`
- `0x1800eec90`
- `0x1800ef450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eedbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eedbb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800eee4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800eee4d`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800eedb1`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800eedb1`

## string_xrefs

- `0x1800eecce`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800eece8`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800eed0a`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800eed37`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800eed63`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800eedc4`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800eee18`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800eed6a`: `%s: Extension was not found in the certificate. OID: %hs.`

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
      &stru_1801282C8);
    v8 = (const unsigned __int16 *)&stru_1801282C8;
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
0x1800eec90  mov     rax, rsp
0x1800eec93  mov     [rax+10h], rbx
0x1800eec97  push    rsi
0x1800eec98  push    rdi
0x1800eec99  push    r14
0x1800eec9b  sub     rsp, 50h
0x1800eec9f  xor     esi, esi
0x1800eeca1  mov     qword ptr [rax-28h], 0
0x1800eeca9  mov     dword ptr [rax+8], 0
0x1800eecb0  mov     rdi, r8
0x1800eecb3  mov     [rax+20h], rsi
0x1800eecb7  mov     r14, rdx
0x1800eecba  mov     rbx, rcx
0x1800eecbd  test    rcx, rcx
0x1800eecc0  jnz     short loc_1800EECF9
0x1800eecc2  lea     r8, aPcszoid; "pcszOid"
0x1800eecc9  mov     ebx, 80070057h
0x1800eecce  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x1800eecd5  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800eecdc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800eece1  lea     rdx, aPcszoid; "pcszOid"
0x1800eece8  lea     rcx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x1800eecef  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800eecf4  jmp     loc_1800EEE40
0x1800eecf9  test    rdi, rdi
0x1800eecfc  jnz     short loc_1800EED26
0x1800eecfe  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x1800eed05  mov     ebx, 80070057h
0x1800eed0a  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x1800eed11  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800eed18  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800eed1d  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x1800eed24  jmp     short loc_1800EECE8
0x1800eed26  test    r14, r14
0x1800eed29  jnz     short loc_1800EED53
0x1800eed2b  lea     r8, stru_1801282C8
0x1800eed32  mov     ebx, 80070057h
0x1800eed37  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x1800eed3e  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800eed45  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800eed4a  lea     rdx, stru_1801282C8; struct _CERT_CONTEXT *
0x1800eed51  jmp     short loc_1800EECE8
0x1800eed53  mov     [r8], rsi
0x1800eed56  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x1800eed5b  test    rax, rax
0x1800eed5e  jnz     short loc_1800EED80
0x1800eed60  mov     r8, rbx
0x1800eed63  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x1800eed6a  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x1800eed71  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800eed76  mov     ebx, 80092004h
0x1800eed7b  jmp     loc_1800EEE40
0x1800eed80  mov     r9d, [rax+10h]; cbEncoded
0x1800eed84  lea     rcx, [rsp+68h+arg_0]
0x1800eed89  mov     r8, [rax+18h]; pbEncoded
0x1800eed8d  mov     edx, 19h; lpszStructType
0x1800eed92  mov     [rsp+68h+pcbStructInfo], rcx; pcbStructInfo
0x1800eed97  lea     rcx, [rsp+68h+hMem]
0x1800eed9c  mov     [rsp+68h+pvStructInfo], rcx; pvStructInfo
0x1800eeda1  mov     ecx, [r14]; dwCertEncodingType
0x1800eeda4  mov     [rsp+68h+pDecodePara], rsi; pDecodePara
0x1800eeda9  mov     [rsp+68h+dwFlags], 8000h; dwFlags
0x1800eedb1  call    cs:__imp_CryptDecodeObjectEx
0x1800eedb7  test    eax, eax
0x1800eedb9  jnz     short loc_1800EEDF0
0x1800eedbb  call    cs:__imp_GetLastError
0x1800eedc1  mov     r8d, eax
0x1800eedc4  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x1800eedcb  lea     rcx, aSCryptdecodeob_0; "%s: CryptDecodeObjectEx failed with err"...
0x1800eedd2  mov     edi, eax
0x1800eedd4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800eedd9  xor     ebx, ebx
0x1800eeddb  test    edi, edi
0x1800eeddd  jz      short loc_1800EEE40
0x1800eeddf  jg      short loc_1800EEDE5
0x1800eede1  mov     ebx, edi
0x1800eede3  jmp     short loc_1800EEE40
0x1800eede5  movzx   ebx, di
0x1800eede8  or      ebx, 80070000h
0x1800eedee  jmp     short loc_1800EEE40
0x1800eedf0  mov     rcx, [rsp+68h+hMem]
0x1800eedf5  lea     r8, [rsp+68h+arg_18]; unsigned __int16 **
0x1800eedfd  mov     edx, [rcx]; unsigned int
0x1800eedff  mov     rcx, [rcx+8]; unsigned __int8 *
0x1800eee03  call    ?GuidStringFromByteArray@CertificateUtil@@CAJPEBEKPEAPEAG@Z; CertificateUtil::GuidStringFromByteArray(uchar const *,ulong,ushort * *)
0x1800eee08  mov     ebx, eax
0x1800eee0a  test    eax, eax
0x1800eee0c  jns     short loc_1800EEE35
0x1800eee0e  mov     r9d, eax
0x1800eee11  lea     r8, aCertificateuti_3; "CertificateUtil::GuidStringFromByteArra"...
0x1800eee18  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x1800eee1f  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x1800eee26  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800eee2b  mov     rsi, [rsp+68h+arg_18]
0x1800eee33  jmp     short loc_1800EEE40
0x1800eee35  mov     rax, [rsp+68h+arg_18]
0x1800eee3d  mov     [rdi], rax
0x1800eee40  mov     rcx, rsi; Block
0x1800eee43  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800eee48  mov     rcx, [rsp+68h+hMem]; hMem
0x1800eee4d  call    cs:__imp_LocalFree
0x1800eee53  mov     eax, ebx
0x1800eee55  mov     rbx, [rsp+68h+arg_8]
0x1800eee5a  add     rsp, 50h
0x1800eee5e  pop     r14
0x1800eee60  pop     rdi
0x1800eee61  pop     rsi
0x1800eee62  retn
```
