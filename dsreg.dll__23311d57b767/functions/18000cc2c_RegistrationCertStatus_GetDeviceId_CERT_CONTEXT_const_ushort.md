# RegistrationCertStatus::GetDeviceId(_CERT_CONTEXT const *,ushort * *)

- ea: `0x18000cc2c`
- end: `0x18000ce14`
- name: `?GetDeviceId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `488`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `11`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180005bbc`
- `0x1800496d0`
- `0x180049f70`
- `0x180052698`
- `0x180054738`
- `0x180055a5c`
- `0x180059e74`
- `0x18005c95c`
- `0x180093f00`
- `0x18009434c`
- `0x180096d08`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x18000cc2c`
- `0x18000d110`
- `0x1800307c4`
- `0x180043ef8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cd20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cd20`
- `CRYPT32!CertFindExtension` at `0x18000cc7f`
- `CRYPT32!CertFindExtension` at `0x18000cc7f`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000ccbc`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000ccbc`

## string_xrefs

- `0x18000ccf8`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18000cd90`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18000cdaa`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18000cdc2`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18000cdf7`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18000cdc9`: `%s: Extension was not found in the certificate. OID: %hs.`

## pseudocode

```c
__int64 __fastcall RegistrationCertStatus::GetDeviceId(const struct _CERT_CONTEXT *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rsi
  PCERT_EXTENSION Extension; // rax
  int v6; // eax
  unsigned int v7; // ebx
  __int64 LastError; // rdi
  DWORD pcbStructInfo; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int16 *v11; // [rsp+70h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+20h] BYREF

  if ( a1 )
  {
    v4 = 0;
    hMem = 0;
    pcbStructInfo = 0;
    v11 = 0;
    if ( a2 )
    {
      *a2 = 0;
      Extension = CertFindExtension("1.2.840.113556.1.5.284.2", a1->pCertInfo->cExtension, a1->pCertInfo->rgExtension);
      if ( Extension )
      {
        if ( CryptDecodeObjectEx(
               a1->dwCertEncodingType,
               (LPCSTR)0x19,
               Extension->Value.pbData,
               Extension->Value.cbData,
               0x8000u,
               0,
               &hMem,
               &pcbStructInfo) )
        {
          v6 = CertificateUtil::GuidStringFromByteArray(*((const unsigned __int8 **)hMem + 1), *(_DWORD *)hMem, &v11);
          v7 = v6;
          if ( v6 < 0 )
          {
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"CertificateUtil::FindExtensionGuidValueByOid",
              L"CertificateUtil::GuidStringFromByteArray",
              (unsigned int)v6);
            v4 = v11;
          }
          else
          {
            *a2 = v11;
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
          (wchar_t *)L"%s: Extension was not found in the certificate. OID: %hs.",
          L"CertificateUtil::FindExtensionGuidValueByOid",
          "1.2.840.113556.1.5.284.2");
        v7 = -2146885628;
      }
    }
    else
    {
      v7 = -2147024809;
      Logger::TraceError(
        L"%s: \"%s\" should not be null.",
        L"CertificateUtil::FindExtensionGuidValueByOid",
        L"ppszOutBuffer");
      Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindExtensionGuidValueByOid", L"ppszOutBuffer");
    }
    operator delete(v4);
    LocalFree(hMem);
  }
  else
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationCertStatus::GetDeviceId", L"pCertContext");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationCertStatus::GetDeviceId", L"pCertContext");
  }
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetDeviceId", v7);
  return v7;
}

```

## disassembly

```asm
0x18000cc2c  push    rbx
0x18000cc2e  push    rsi
0x18000cc2f  push    rdi
0x18000cc30  sub     rsp, 40h
0x18000cc34  mov     rdi, rdx
0x18000cc37  mov     rbx, rcx
0x18000cc3a  test    rcx, rcx
0x18000cc3d  jz      loc_18000CD50
0x18000cc43  xor     esi, esi
0x18000cc45  mov     [rsp+58h+hMem], 0
0x18000cc4e  mov     [rsp+58h+arg_0], 0
0x18000cc56  mov     [rsp+58h+arg_10], rsi
0x18000cc5b  test    rdx, rdx
0x18000cc5e  jz      loc_18000CD84
0x18000cc64  mov     [rdx], rsi
0x18000cc67  mov     rdx, [rcx+18h]
0x18000cc6b  lea     rcx, pszObjId; "1.2.840.113556.1.5.284.2"
0x18000cc72  mov     r8, [rdx+0C8h]; rgExtensions
0x18000cc79  mov     edx, [rdx+0C0h]; cExtensions
0x18000cc7f  call    cs:__imp_CertFindExtension
0x18000cc85  test    rax, rax
0x18000cc88  jz      loc_18000CDBB
0x18000cc8e  mov     r9d, [rax+10h]; cbEncoded
0x18000cc92  lea     rcx, [rsp+58h+arg_0]
0x18000cc97  mov     r8, [rax+18h]; pbEncoded
0x18000cc9b  lea     edx, [rsi+19h]; lpszStructType
0x18000cc9e  mov     [rsp+58h+pcbStructInfo], rcx; pcbStructInfo
0x18000cca3  lea     rcx, [rsp+58h+hMem]
0x18000cca8  mov     [rsp+58h+pvStructInfo], rcx; pvStructInfo
0x18000ccad  mov     ecx, [rbx]; dwCertEncodingType
0x18000ccaf  mov     [rsp+58h+pDecodePara], rsi; pDecodePara
0x18000ccb4  mov     [rsp+58h+dwFlags], 8000h; dwFlags
0x18000ccbc  call    cs:__imp_CryptDecodeObjectEx
0x18000ccc2  test    eax, eax
0x18000ccc4  jz      short loc_18000CCEF
0x18000ccc6  mov     rcx, [rsp+58h+hMem]
0x18000cccb  lea     r8, [rsp+58h+arg_10]; unsigned __int16 **
0x18000ccd0  mov     edx, [rcx]; unsigned int
0x18000ccd2  mov     rcx, [rcx+8]; unsigned __int8 *
0x18000ccd6  call    ?GuidStringFromByteArray@CertificateUtil@@CAJPEBEKPEAPEAG@Z; CertificateUtil::GuidStringFromByteArray(uchar const *,ulong,ushort * *)
0x18000ccdb  mov     ebx, eax
0x18000ccdd  test    eax, eax
0x18000ccdf  js      loc_18000CDED
0x18000cce5  mov     rax, [rsp+58h+arg_10]
0x18000ccea  mov     [rdi], rax
0x18000cced  jmp     short loc_18000CD13
0x18000ccef  call    cs:__imp_GetLastError
0x18000ccf5  mov     r8d, eax
0x18000ccf8  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionGuidValue"...
0x18000ccff  lea     rcx, aSCryptdecodeob_0; "%s: CryptDecodeObjectEx failed with err"...
0x18000cd06  mov     edi, eax
0x18000cd08  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000cd0d  xor     ebx, ebx
0x18000cd0f  test    edi, edi
0x18000cd11  jnz     short loc_18000CD46
0x18000cd13  mov     rcx, rsi; Block
0x18000cd16  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cd1b  mov     rcx, [rsp+58h+hMem]; hMem
0x18000cd20  call    cs:__imp_LocalFree
0x18000cd26  mov     r8d, ebx
0x18000cd29  lea     rdx, aRegistrationce_24; "RegistrationCertStatus::GetDeviceId"
0x18000cd30  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18000cd37  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000cd3c  mov     eax, ebx
0x18000cd3e  add     rsp, 40h
0x18000cd42  pop     rdi
0x18000cd43  pop     rsi
0x18000cd44  pop     rbx
0x18000cd45  retn
0x18000cd46  jg      loc_18000CDDF
0x18000cd4c  mov     ebx, edi
0x18000cd4e  jmp     short loc_18000CD13
0x18000cd50  lea     r8, aPcertcontext; "pCertContext"
0x18000cd57  mov     ebx, 80070057h
0x18000cd5c  lea     rdx, aRegistrationce_24; "RegistrationCertStatus::GetDeviceId"
0x18000cd63  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18000cd6a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000cd6f  lea     rdx, aPcertcontext; "pCertContext"
0x18000cd76  lea     rcx, aRegistrationce_24; "RegistrationCertStatus::GetDeviceId"
0x18000cd7d  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18000cd82  jmp     short loc_18000CD26
0x18000cd84  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x18000cd8b  mov     ebx, 80070057h
0x18000cd90  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionGuidValue"...
0x18000cd97  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18000cd9e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000cda3  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x18000cdaa  lea     rcx, aCertificateuti_5; "CertificateUtil::FindExtensionGuidValue"...
0x18000cdb1  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18000cdb6  jmp     loc_18000CD13
0x18000cdbb  lea     r8, pszObjId; "1.2.840.113556.1.5.284.2"
0x18000cdc2  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionGuidValue"...
0x18000cdc9  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x18000cdd0  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000cdd5  mov     ebx, 80092004h
0x18000cdda  jmp     loc_18000CD13
0x18000cddf  movzx   ebx, di
0x18000cde2  or      ebx, 80070000h
0x18000cde8  jmp     loc_18000CD13
0x18000cded  mov     r9d, eax
0x18000cdf0  lea     r8, aCertificateuti_4; "CertificateUtil::GuidStringFromByteArra"...
0x18000cdf7  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionGuidValue"...
0x18000cdfe  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18000ce05  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000ce0a  mov     rsi, [rsp+58h+arg_10]
0x18000ce0f  jmp     loc_18000CD13
```
