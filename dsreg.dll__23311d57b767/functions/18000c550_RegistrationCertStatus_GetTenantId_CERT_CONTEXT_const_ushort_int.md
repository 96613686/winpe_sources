# RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)

- ea: `0x18000c550`
- end: `0x18000c808`
- name: `?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z`
- size: `696`
- prototype: `static int(const struct _CERT_CONTEXT *, unsigned __int16 **, int *)`
- caller_count: `15`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x18000c0d0`
- `0x1800108e0`
- `0x1800264a8`
- `0x180042c18`
- `0x1800496d0`
- `0x180052698`
- `0x1800543ec`
- `0x180054738`
- `0x180059e74`
- `0x18005c95c`
- `0x18005d424`
- `0x180093f00`
- `0x18009434c`
- `0x1800945a8`
- `0x180096d08`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x18000c550`
- `0x18000d110`
- `0x18000ddf0`
- `0x1800307c4`
- `0x180043ef8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c655`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c655`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c689`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c689`
- `CRYPT32!CertFindExtension` at `0x18000c5d5`
- `CRYPT32!CertFindExtension` at `0x18000c5d5`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000c619`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000c619`

## string_xrefs

- `0x18000c68f`: `RegistrationCertStatus::GetTenantIdExtensionValue`
- `0x18000c65e`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18000c721`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18000c73b`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18000c753`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18000c788`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18000c7dc`: `CopyStringW`
- `0x18000c75a`: `%s: Extension was not found in the certificate. OID: %hs.`

## pseudocode

```c
__int64 __fastcall RegistrationCertStatus::GetTenantId(const struct _CERT_CONTEXT *a1, unsigned __int16 **a2, int *a3)
{
  unsigned __int16 *v6; // r14
  PCERT_EXTENSION Extension; // rax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 LastError; // rbp
  const wchar_t *v11; // rbp
  DWORD pcbStructInfo; // [rsp+88h] [rbp+10h] BYREF
  unsigned __int16 *v14; // [rsp+90h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp+20h] BYREF

  if ( a3 )
    *a3 = 0;
  if ( !a2 )
  {
    v9 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationCertStatus::GetTenantId", L"ppszOutBuffer");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationCertStatus::GetTenantId", L"ppszOutBuffer");
    goto LABEL_12;
  }
  v6 = 0;
  *a2 = 0;
  hMem = 0;
  pcbStructInfo = 0;
  v14 = 0;
  if ( a1 )
  {
    Extension = CertFindExtension("1.2.840.113556.1.5.284.5", a1->pCertInfo->cExtension, a1->pCertInfo->rgExtension);
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
        v8 = CertificateUtil::GuidStringFromByteArray(*((const unsigned __int8 **)hMem + 1), *(_DWORD *)hMem, &v14);
        v9 = v8;
        if ( v8 < 0 )
        {
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CertificateUtil::FindExtensionGuidValueByOid",
            L"CertificateUtil::GuidStringFromByteArray",
            (unsigned int)v8);
          v6 = v14;
        }
        else
        {
          *a2 = v14;
        }
      }
      else
      {
        LastError = GetLastError();
        Logger::TraceError(
          L"%s: CryptDecodeObjectEx failed with error code: 0x%08x",
          L"CertificateUtil::FindExtensionGuidValueByOid",
          LastError);
        v9 = 0;
        if ( (_DWORD)LastError )
        {
          if ( (int)LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
          else
            v9 = LastError;
        }
      }
    }
    else
    {
      Logger::TraceVerbose(
        (wchar_t *)L"%s: Extension was not found in the certificate. OID: %hs.",
        L"CertificateUtil::FindExtensionGuidValueByOid",
        "1.2.840.113556.1.5.284.5");
      v9 = -2146885628;
    }
  }
  else
  {
    v9 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      L"pCertContext");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindExtensionGuidValueByOid", L"pCertContext");
  }
  operator delete(v6);
  LocalFree(hMem);
  v11 = L"RegistrationCertStatus::GetTenantIdExtensionValue";
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetTenantIdExtensionValue", v9);
  if ( v9 != -2146885628 )
  {
    if ( (v9 & 0x80000000) == 0 )
      goto LABEL_12;
LABEL_24:
    Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"RegistrationCertStatus::GetTenantId", v11, v9);
    operator delete(*a2);
    *a2 = 0;
    goto LABEL_12;
  }
  if ( a3 )
    *a3 = 1;
  operator delete(*a2);
  *a2 = 0;
  v9 = CopyStringW(L"383a3889-5bc9-47a3-846c-2b70f0b7fe0e", 0x24u, a2);
  if ( (v9 & 0x80000000) != 0 )
  {
    v11 = L"CopyStringW";
    goto LABEL_24;
  }
LABEL_12:
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetTenantId", v9);
  return v9;
}

```

## disassembly

```asm
0x18000c550  push    rbx
0x18000c552  push    rbp
0x18000c553  push    rsi
0x18000c554  push    rdi
0x18000c555  push    r13
0x18000c557  push    r14
0x18000c559  push    r15
0x18000c55b  sub     rsp, 40h
0x18000c55f  mov     rsi, r8
0x18000c562  mov     rdi, rdx
0x18000c565  mov     rbx, rcx
0x18000c568  test    r8, r8
0x18000c56b  jz      short loc_18000C574
0x18000c56d  mov     dword ptr [r8], 0
0x18000c574  lea     r13, aRegistrationce_21; "RegistrationCertStatus::GetTenantId"
0x18000c57b  test    rdi, rdi
0x18000c57e  jz      loc_18000C6E9
0x18000c584  xor     r14d, r14d
0x18000c587  mov     qword ptr [rdx], 0
0x18000c58e  mov     [rsp+78h+hMem], 0
0x18000c59a  lea     r15, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18000c5a1  mov     [rsp+78h+arg_8], 0
0x18000c5ac  mov     [rsp+78h+arg_10], r14
0x18000c5b4  test    rbx, rbx
0x18000c5b7  jz      loc_18000C715
0x18000c5bd  mov     rdx, [rcx+18h]
0x18000c5c1  lea     rcx, a12840113556152; "1.2.840.113556.1.5.284.5"
0x18000c5c8  mov     r8, [rdx+0C8h]; rgExtensions
0x18000c5cf  mov     edx, [rdx+0C0h]; cExtensions
0x18000c5d5  call    cs:__imp_CertFindExtension
0x18000c5db  test    rax, rax
0x18000c5de  jz      loc_18000C74C
0x18000c5e4  mov     r9d, [rax+10h]; cbEncoded
0x18000c5e8  lea     rcx, [rsp+78h+arg_8]
0x18000c5f0  mov     r8, [rax+18h]; pbEncoded
0x18000c5f4  lea     edx, [r14+19h]; lpszStructType
0x18000c5f8  mov     [rsp+78h+pcbStructInfo], rcx; pcbStructInfo
0x18000c5fd  lea     rcx, [rsp+78h+hMem]
0x18000c605  mov     [rsp+78h+pvStructInfo], rcx; pvStructInfo
0x18000c60a  mov     ecx, [rbx]; dwCertEncodingType
0x18000c60c  mov     [rsp+78h+pDecodePara], r14; pDecodePara
0x18000c611  mov     [rsp+78h+dwFlags], 8000h; dwFlags
0x18000c619  call    cs:__imp_CryptDecodeObjectEx
0x18000c61f  test    eax, eax
0x18000c621  jz      short loc_18000C655
0x18000c623  mov     rcx, [rsp+78h+hMem]
0x18000c62b  lea     r8, [rsp+78h+arg_10]; unsigned __int16 **
0x18000c633  mov     edx, [rcx]; unsigned int
0x18000c635  mov     rcx, [rcx+8]; unsigned __int8 *
0x18000c639  call    ?GuidStringFromByteArray@CertificateUtil@@CAJPEBEKPEAPEAG@Z; CertificateUtil::GuidStringFromByteArray(uchar const *,ulong,ushort * *)
0x18000c63e  mov     ebx, eax
0x18000c640  test    eax, eax
0x18000c642  js      loc_18000C77E
0x18000c648  mov     rax, [rsp+78h+arg_10]
0x18000c650  mov     [rdi], rax
0x18000c653  jmp     short loc_18000C679
0x18000c655  call    cs:__imp_GetLastError
0x18000c65b  mov     r8d, eax
0x18000c65e  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionGuidValue"...
0x18000c665  lea     rcx, aSCryptdecodeob_0; "%s: CryptDecodeObjectEx failed with err"...
0x18000c66c  mov     ebp, eax
0x18000c66e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c673  xor     ebx, ebx
0x18000c675  test    ebp, ebp
0x18000c677  jnz     short loc_18000C6DF
0x18000c679  mov     rcx, r14; Block
0x18000c67c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c681  mov     rcx, [rsp+78h+hMem]; hMem
0x18000c689  call    cs:__imp_LocalFree
0x18000c68f  lea     rbp, aRegistrationce_5; "RegistrationCertStatus::GetTenantIdExte"...
0x18000c696  mov     r8d, ebx
0x18000c699  mov     rdx, rbp
0x18000c69c  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18000c6a3  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000c6a8  cmp     ebx, 80092004h
0x18000c6ae  jz      loc_18000C7A4
0x18000c6b4  test    ebx, ebx
0x18000c6b6  js      loc_18000C7E3
0x18000c6bc  mov     r8d, ebx
0x18000c6bf  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18000c6c6  mov     rdx, r13
0x18000c6c9  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000c6ce  mov     eax, ebx
0x18000c6d0  add     rsp, 40h
0x18000c6d4  pop     r15
0x18000c6d6  pop     r14
0x18000c6d8  pop     r13
0x18000c6da  pop     rdi
0x18000c6db  pop     rsi
0x18000c6dc  pop     rbp
0x18000c6dd  pop     rbx
0x18000c6de  retn
0x18000c6df  jg      loc_18000C770
0x18000c6e5  mov     ebx, ebp
0x18000c6e7  jmp     short loc_18000C679
0x18000c6e9  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x18000c6f0  mov     rdx, r13
0x18000c6f3  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18000c6fa  mov     ebx, 80070057h
0x18000c6ff  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c704  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x18000c70b  mov     rcx, r13; unsigned __int16 *
0x18000c70e  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18000c713  jmp     short loc_18000C6BC
0x18000c715  lea     r8, aPcertcontext; "pCertContext"
0x18000c71c  mov     ebx, 80070057h
0x18000c721  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionGuidValue"...
0x18000c728  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18000c72f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c734  lea     rdx, aPcertcontext; "pCertContext"
0x18000c73b  lea     rcx, aCertificateuti_5; "CertificateUtil::FindExtensionGuidValue"...
0x18000c742  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18000c747  jmp     loc_18000C679
0x18000c74c  lea     r8, a12840113556152; "1.2.840.113556.1.5.284.5"
0x18000c753  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionGuidValue"...
0x18000c75a  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x18000c761  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000c766  mov     ebx, 80092004h
0x18000c76b  jmp     loc_18000C679
0x18000c770  movzx   ebx, bp
0x18000c773  or      ebx, 80070000h
0x18000c779  jmp     loc_18000C679
0x18000c77e  mov     r9d, eax
0x18000c781  lea     r8, aCertificateuti_4; "CertificateUtil::GuidStringFromByteArra"...
0x18000c788  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionGuidValue"...
0x18000c78f  mov     rcx, r15; unsigned __int16 *
0x18000c792  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c797  mov     r14, [rsp+78h+arg_10]
0x18000c79f  jmp     loc_18000C679
0x18000c7a4  test    rsi, rsi
0x18000c7a7  jz      short loc_18000C7AF
0x18000c7a9  mov     dword ptr [rsi], 1
0x18000c7af  mov     rcx, [rdi]; Block
0x18000c7b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c7b7  mov     r8, rdi; unsigned __int16 **
0x18000c7ba  mov     qword ptr [rdi], 0
0x18000c7c1  mov     edx, 24h ; '$'; unsigned __int64
0x18000c7c6  lea     rcx, a383a38895bc947; "383a3889-5bc9-47a3-846c-2b70f0b7fe0e"
0x18000c7cd  call    ?CopyStringW@@YAJPEBG_KPEAPEAG@Z; CopyStringW(ushort const *,unsigned __int64,ushort * *)
0x18000c7d2  mov     ebx, eax
0x18000c7d4  test    eax, eax
0x18000c7d6  jns     loc_18000C6BC
0x18000c7dc  lea     rbp, aCopystringw; "CopyStringW"
0x18000c7e3  mov     rdx, r13
0x18000c7e6  mov     r9d, ebx
0x18000c7e9  mov     r8, rbp
0x18000c7ec  mov     rcx, r15; unsigned __int16 *
0x18000c7ef  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c7f4  mov     rcx, [rdi]; Block
0x18000c7f7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c7fc  mov     qword ptr [rdi], 0
0x18000c803  jmp     loc_18000C6BC
```
