# RegistrationCertHelper::InstallCertificate(_CERTFICATE_LOCATION,ushort const *,ushort const *,ushort const *,int,_CERT_CONTEXT const * *)

- ea: `0x180035390`
- end: `0x180035811`
- name: `?InstallCertificate@RegistrationCertHelper@@SAJW4_CERTFICATE_LOCATION@@PEBG11HPEAPEBU_CERT_CONTEXT@@@Z`
- size: `1153`
- prototype: `static int __high(enum _CERTFICATE_LOCATION, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, const struct _CERT_CONTEXT **)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800439d4`
- `0x180058e98`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x1800307c4`
- `0x18003334c`
- `0x180035390`
- `0x180035818`
- `0x180035880`
- `0x18005d424`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800354dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800354e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003558f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800355e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800355ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003571a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800357b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800354dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800354e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003558f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800355e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800355ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003571a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800357b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180035525`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180035525`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035758`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035758`
- `CRYPT32!CryptStringToBinaryW` at `0x1800354d2`
- `CRYPT32!CryptStringToBinaryW` at `0x180035576`
- `CRYPT32!CryptStringToBinaryW` at `0x1800354d2`
- `CRYPT32!CryptStringToBinaryW` at `0x180035576`
- `CRYPT32!CertOpenStore` at `0x1800356c7`
- `CRYPT32!CertOpenStore` at `0x1800356c7`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18003563c`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18003563c`
- `CRYPT32!CertCloseStore` at `0x1800357ac`
- `CRYPT32!CertCloseStore` at `0x1800357ac`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18003574b`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18003574b`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180035710`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180035710`
- `CRYPT32!CertCreateCertificateContext` at `0x1800355d3`
- `CRYPT32!CertCreateCertificateContext` at `0x1800355d3`
- `CRYPT32!CertFreeCertificateContext` at `0x180035766`
- `CRYPT32!CertFreeCertificateContext` at `0x180035766`

## string_xrefs

- `0x1800353e7`: `RegistrationCertHelper::InstallCertificate`
- `0x180035401`: `RegistrationCertHelper::InstallCertificate`
- `0x180035429`: `RegistrationCertHelper::InstallCertificate`
- `0x180035456`: `RegistrationCertHelper::InstallCertificate`
- `0x180035483`: `RegistrationCertHelper::InstallCertificate`
- `0x180035508`: `RegistrationCertHelper::InstallCertificate`
- `0x180035534`: `RegistrationCertHelper::InstallCertificate`
- `0x1800355b5`: `RegistrationCertHelper::InstallCertificate`
- `0x18003578c`: `RegistrationCertHelper::InstallCertificate`
- `0x1800357d2`: `RegistrationCertHelper::InstallCertificate`
- `0x1800357e8`: `RegistrationCertHelper::InstallCertificate`
- `0x1800356f7`: `CertOpenStore`
- `0x180035603`: `CertCreateCertificateContext`
- `0x18003568f`: `RegistrationCertHelper::DeleteOtherExistingCertificatesIfNecessary`

## pseudocode

```c
__int64 __fastcall RegistrationCertHelper::InstallCertificate(
        unsigned int a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        PCCERT_CONTEXT *a6)
{
  const CERT_CONTEXT *CertificateContext; // rdi
  unsigned int v11; // ebx
  const unsigned __int16 *v12; // rdx
  void *v13; // rsi
  __int64 v14; // rbx
  DWORD v15; // eax
  signed int v16; // eax
  BYTE *v17; // rax
  BOOL v18; // eax
  DWORD v19; // eax
  signed int v20; // eax
  const wchar_t *v21; // r8
  DWORD v22; // eax
  signed int v23; // eax
  DWORD v24; // eax
  signed int v25; // eax
  int v26; // eax
  HCERTSTORE v27; // rax
  DWORD v28; // eax
  signed int v29; // eax
  DWORD LastError; // eax
  signed int v31; // eax
  signed int v32; // eax
  signed int v33; // eax
  DWORD cbCertEncoded; // [rsp+40h] [rbp-49h] BYREF
  DWORD pdwFlags[3]; // [rsp+44h] [rbp-45h] BYREF
  BYTE *pbCertEncoded; // [rsp+50h] [rbp-39h]
  __int128 pvData; // [rsp+58h] [rbp-31h] BYREF
  __int128 v39; // [rsp+68h] [rbp-21h]
  __int128 v40; // [rsp+78h] [rbp-11h]

  pbCertEncoded = 0;
  cbCertEncoded = 0;
  CertificateContext = 0;
  pdwFlags[0] = 0;
  pvData = 0;
  v39 = 0;
  v40 = 0;
  if ( !a6 )
  {
    v11 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationCertHelper::InstallCertificate",
      L"ppCertContext");
    v12 = L"ppCertContext";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationCertHelper::InstallCertificate", v12);
    goto LABEL_4;
  }
  *a6 = 0;
  if ( !a2 )
  {
    v11 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationCertHelper::InstallCertificate",
      L"pcszRawCertificate");
    v12 = L"pcszRawCertificate";
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v11 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationCertHelper::InstallCertificate",
      L"pcszKeyContainerName");
    v12 = L"pcszKeyContainerName";
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v11 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationCertHelper::InstallCertificate",
      L"pcszProviderName");
    v12 = L"pcszProviderName";
    goto LABEL_3;
  }
  v14 = -1;
  do
    ++v14;
  while ( a2[v14] );
  if ( CryptStringToBinaryW(a2, v14, 1u, 0, &cbCertEncoded, 0, pdwFlags) )
  {
    v17 = (BYTE *)LocalAlloc(0, cbCertEncoded);
    pbCertEncoded = v17;
    if ( v17 )
    {
      v18 = CryptStringToBinaryW(a2, v14, 1u, v17, &cbCertEncoded, 0, pdwFlags);
      v13 = 0;
      if ( v18 )
      {
        CertificateContext = CertCreateCertificateContext(0x10001u, pbCertEncoded, cbCertEncoded);
        if ( CertificateContext )
        {
          *(_QWORD *)&pvData = a3;
          *((_QWORD *)&pvData + 1) = a4;
          LODWORD(v39) = 0;
          *(_QWORD *)&v40 = 0;
          *(_QWORD *)((char *)&v39 + 4) = a1 != 0 ? 0x20uLL : 0;
          DWORD2(v40) = 0;
          if ( CertSetCertificateContextProperty(CertificateContext, 2u, 0, &pvData) )
          {
            v11 = 0;
            if ( a5 )
            {
              v26 = RegistrationCertHelper::DeleteOtherExistingCertificatesIfNecessary(a1, CertificateContext);
              v11 = v26;
              if ( v26 < 0 )
              {
                Logger::TraceError(
                  L"%s: %s failed with error code: 0x%08x.",
                  L"RegistrationCertHelper::InstallCertificate",
                  L"RegistrationCertHelper::DeleteOtherExistingCertificatesIfNecessary",
                  (unsigned int)v26);
                goto LABEL_45;
              }
            }
            v27 = CertOpenStore((LPCSTR)0xA, 0, 0, a1 != 0 ? 0x20000 : 0x10000, L"My");
            v13 = v27;
            if ( v27 )
            {
              if ( CertAddCertificateContextToStore(v27, CertificateContext, 4u, 0) )
              {
                *a6 = CertDuplicateCertificateContext(CertificateContext);
                goto LABEL_45;
              }
              LastError = GetLastError();
              Logger::WriteCertSaveFailureEvent(LastError);
              v31 = GetLastError();
              v11 = v31;
              if ( v31 > 0 )
                v11 = (unsigned __int16)v31 | 0x80070000;
              v21 = L"CertAddCertificateContextToStore";
            }
            else
            {
              v28 = GetLastError();
              Logger::WriteCertSaveFailureEvent(v28);
              v29 = GetLastError();
              v11 = v29;
              if ( v29 > 0 )
                v11 = (unsigned __int16)v29 | 0x80070000;
              v21 = L"CertOpenStore";
            }
          }
          else
          {
            v24 = GetLastError();
            Logger::WriteCertSetupFailureEvent(v24);
            v25 = GetLastError();
            v11 = v25;
            if ( v25 > 0 )
              v11 = (unsigned __int16)v25 | 0x80070000;
            v21 = L"CertSetCertificateContextProperty";
          }
        }
        else
        {
          v22 = GetLastError();
          Logger::WriteCertSetupFailureEvent(v22);
          v23 = GetLastError();
          v11 = v23;
          if ( v23 > 0 )
            v11 = (unsigned __int16)v23 | 0x80070000;
          v21 = L"CertCreateCertificateContext";
        }
      }
      else
      {
        v19 = GetLastError();
        Logger::WriteCertSetupFailureEvent(v19);
        v20 = GetLastError();
        v11 = v20;
        if ( v20 > 0 )
          v11 = (unsigned __int16)v20 | 0x80070000;
        v21 = L"CryptStringToBinaryW";
      }
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x",
        L"RegistrationCertHelper::InstallCertificate",
        v21,
        v11);
      goto LABEL_45;
    }
    v11 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegistrationCertHelper::InstallCertificate");
  }
  else
  {
    v15 = GetLastError();
    Logger::WriteCertSetupFailureEvent(v15);
    v16 = GetLastError();
    v11 = v16;
    if ( v16 > 0 )
      v11 = (unsigned __int16)v16 | 0x80070000;
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x",
      L"RegistrationCertHelper::InstallCertificate",
      L"CryptStringToBinaryW",
      v11);
  }
LABEL_4:
  v13 = 0;
LABEL_45:
  LocalFree(pbCertEncoded);
  if ( CertificateContext && !CertFreeCertificateContext(CertificateContext) )
  {
    v32 = GetLastError();
    if ( v32 > 0 )
      v32 = (unsigned __int16)v32 | 0x80070000;
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x",
      L"RegistrationCertHelper::InstallCertificate",
      L"CertFreeCertificateContext",
      (unsigned int)v32);
  }
  if ( v13 && !CertCloseStore(v13, 2u) )
  {
    v33 = GetLastError();
    if ( v33 > 0 )
      v33 = (unsigned __int16)v33 | 0x80070000;
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x",
      L"RegistrationCertHelper::InstallCertificate",
      L"CertCloseStore",
      (unsigned int)v33);
  }
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationCertHelper::InstallCertificate", v11);
  return v11;
}

```

## disassembly

```asm
0x180035390  push    rbp
0x180035392  push    rbx
0x180035393  push    rsi
0x180035394  push    rdi
0x180035395  push    r12
0x180035397  push    r13
0x180035399  push    r14
0x18003539b  push    r15
0x18003539d  lea     rbp, [rsp-0Fh]
0x1800353a2  sub     rsp, 98h
0x1800353a9  mov     r15, [rbp+47h+arg_28]
0x1800353ad  xorps   xmm0, xmm0
0x1800353b0  mov     r14d, ecx
0x1800353b3  mov     r12, r9
0x1800353b6  xor     ecx, ecx
0x1800353b8  mov     r13, r8
0x1800353bb  mov     [rbp+47h+pbCertEncoded], rcx
0x1800353bf  mov     rsi, rdx
0x1800353c2  mov     [rbp+47h+cbCertEncoded], ecx
0x1800353c5  mov     edi, ecx
0x1800353c7  mov     [rbp+47h+var_8C], ecx
0x1800353ca  movups  [rbp+47h+pvData], xmm0
0x1800353ce  movups  [rbp+47h+var_68], xmm0
0x1800353d2  movups  [rbp+47h+var_58], xmm0
0x1800353d6  test    r15, r15
0x1800353d9  jnz     short loc_180035415
0x1800353db  lea     r8, aPpcertcontext; "ppCertContext"
0x1800353e2  mov     ebx, 80070057h
0x1800353e7  lea     rdx, aRegistrationce_28; "RegistrationCertHelper::InstallCertific"...
0x1800353ee  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800353f5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800353fa  lea     rdx, aPpcertcontext; "ppCertContext"
0x180035401  lea     rcx, aRegistrationce_28; "RegistrationCertHelper::InstallCertific"...
0x180035408  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18003540d  mov     rsi, rdi
0x180035410  jmp     loc_180035754
0x180035415  mov     [r15], rcx
0x180035418  test    rsi, rsi
0x18003541b  jnz     short loc_180035445
0x18003541d  lea     r8, aPcszrawcertifi; "pcszRawCertificate"
0x180035424  mov     ebx, 80070057h
0x180035429  lea     rdx, aRegistrationce_28; "RegistrationCertHelper::InstallCertific"...
0x180035430  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180035437  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003543c  lea     rdx, aPcszrawcertifi; "pcszRawCertificate"
0x180035443  jmp     short loc_180035401
0x180035445  test    r13, r13
0x180035448  jnz     short loc_180035472
0x18003544a  lea     r8, aPcszkeycontain; "pcszKeyContainerName"
0x180035451  mov     ebx, 80070057h
0x180035456  lea     rdx, aRegistrationce_28; "RegistrationCertHelper::InstallCertific"...
0x18003545d  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180035464  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180035469  lea     rdx, aPcszkeycontain; "pcszKeyContainerName"
0x180035470  jmp     short loc_180035401
0x180035472  test    r12, r12
0x180035475  jnz     short loc_1800354A2
0x180035477  lea     r8, aPcszproviderna; "pcszProviderName"
0x18003547e  mov     ebx, 80070057h
0x180035483  lea     rdx, aRegistrationce_28; "RegistrationCertHelper::InstallCertific"...
0x18003548a  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180035491  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180035496  lea     rdx, aPcszproviderna; "pcszProviderName"
0x18003549d  jmp     loc_180035401
0x1800354a2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800354a6  inc     rbx
0x1800354a9  cmp     [rdx+rbx*2], cx
0x1800354ad  jnz     short loc_1800354A6
0x1800354af  xor     r9d, r9d; pbBinary
0x1800354b2  lea     rax, [rbp+47h+var_8C]
0x1800354b6  mov     [rsp+0D0h+pdwFlags], rax; pdwFlags
0x1800354bb  mov     edx, ebx; cchString
0x1800354bd  mov     [rsp+0D0h+pdwSkip], rcx; pdwSkip
0x1800354c2  lea     rax, [rbp+47h+cbCertEncoded]
0x1800354c6  mov     rcx, rsi; pszString
0x1800354c9  mov     [rsp+0D0h+pcbBinary], rax; pcbBinary
0x1800354ce  lea     r8d, [r9+1]; dwFlags
0x1800354d2  call    cs:__imp_CryptStringToBinaryW
0x1800354d8  test    eax, eax
0x1800354da  jnz     short loc_180035520
0x1800354dc  call    cs:__imp_GetLastError
0x1800354e2  mov     ecx, eax; unsigned int
0x1800354e4  call    ?WriteCertSetupFailureEvent@Logger@@SAJK@Z; Logger::WriteCertSetupFailureEvent(ulong)
0x1800354e9  call    cs:__imp_GetLastError
0x1800354ef  mov     ebx, eax
0x1800354f1  test    eax, eax
0x1800354f3  jle     short loc_1800354FE
0x1800354f5  movzx   ebx, ax
0x1800354f8  or      ebx, 80070000h
0x1800354fe  mov     r9d, ebx
0x180035501  lea     r8, aCryptstringtob_0; "CryptStringToBinaryW"
0x180035508  lea     rdx, aRegistrationce_28; "RegistrationCertHelper::InstallCertific"...
0x18003550f  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x180035516  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003551b  jmp     loc_18003540D
0x180035520  mov     edx, [rbp+47h+cbCertEncoded]; uBytes
0x180035523  xor     ecx, ecx; uFlags
0x180035525  call    cs:__imp_LocalAlloc
0x18003552b  mov     [rbp+47h+pbCertEncoded], rax
0x18003552f  test    rax, rax
0x180035532  jnz     short loc_180035551
0x180035534  lea     rdx, aRegistrationce_28; "RegistrationCertHelper::InstallCertific"...
0x18003553b  mov     ebx, 8007000Eh
0x180035540  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180035547  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18003554c  jmp     loc_18003540D
0x180035551  lea     rcx, [rbp+47h+var_8C]
0x180035555  mov     r9, rax; pbBinary
0x180035558  mov     [rsp+0D0h+pdwFlags], rcx; pdwFlags
0x18003555d  mov     r8d, 1; dwFlags
0x180035563  lea     rcx, [rbp+47h+cbCertEncoded]
0x180035567  mov     [rsp+0D0h+pdwSkip], rdi; pdwSkip
0x18003556c  mov     [rsp+0D0h+pcbBinary], rcx; pcbBinary
0x180035571  mov     edx, ebx; cchString
0x180035573  mov     rcx, rsi; pszString
0x180035576  call    cs:__imp_CryptStringToBinaryW
0x18003557c  xor     esi, esi
0x18003557e  test    eax, eax
0x180035580  jnz     short loc_1800355C6
0x180035582  call    cs:__imp_GetLastError
0x180035588  mov     ecx, eax; unsigned int
0x18003558a  call    ?WriteCertSetupFailureEvent@Logger@@SAJK@Z; Logger::WriteCertSetupFailureEvent(ulong)
0x18003558f  call    cs:__imp_GetLastError
0x180035595  mov     ebx, eax
0x180035597  test    eax, eax
0x180035599  jle     short loc_1800355A4
0x18003559b  movzx   ebx, ax
0x18003559e  or      ebx, 80070000h
0x1800355a4  lea     r8, aCryptstringtob_0; "CryptStringToBinaryW"
0x1800355ab  mov     r9d, ebx
0x1800355ae  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x1800355b5  lea     rdx, aRegistrationce_28; "RegistrationCertHelper::InstallCertific"...
0x1800355bc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800355c1  jmp     loc_180035754
0x1800355c6  mov     r8d, [rbp+47h+cbCertEncoded]; cbCertEncoded
0x1800355ca  mov     ecx, 10001h; dwCertEncodingType
0x1800355cf  mov     rdx, [rbp+47h+pbCertEncoded]; pbCertEncoded
0x1800355d3  call    cs:__imp_CertCreateCertificateContext
0x1800355d9  mov     rdi, rax
0x1800355dc  test    rax, rax
0x1800355df  jnz     short loc_18003560C
0x1800355e1  call    cs:__imp_GetLastError
0x1800355e7  mov     ecx, eax; unsigned int
0x1800355e9  call    ?WriteCertSetupFailureEvent@Logger@@SAJK@Z; Logger::WriteCertSetupFailureEvent(ulong)
0x1800355ee  call    cs:__imp_GetLastError
0x1800355f4  mov     ebx, eax
0x1800355f6  test    eax, eax
0x1800355f8  jle     short loc_180035603
0x1800355fa  movzx   ebx, ax
0x1800355fd  or      ebx, 80070000h
0x180035603  lea     r8, aCertcreatecert_0; "CertCreateCertificateContext"
0x18003560a  jmp     short loc_1800355AB
0x18003560c  mov     eax, r14d
0x18003560f  mov     qword ptr [rbp+47h+pvData], r13
0x180035613  neg     eax
0x180035615  mov     qword ptr [rbp+47h+pvData+8], r12
0x180035619  lea     r9, [rbp+47h+pvData]; pvData
0x18003561d  mov     dword ptr [rbp+47h+var_68], esi
0x180035620  sbb     ecx, ecx
0x180035622  mov     dword ptr [rbp+47h+var_68+8], esi
0x180035625  and     ecx, 20h
0x180035628  mov     qword ptr [rbp+47h+var_58], rsi
0x18003562c  xor     r8d, r8d; dwFlags
0x18003562f  mov     dword ptr [rbp+47h+var_68+4], ecx
0x180035632  mov     rcx, rdi; pCertContext
0x180035635  mov     dword ptr [rbp+47h+var_58+8], esi
0x180035638  lea     edx, [r8+2]; dwPropId
0x18003563c  call    cs:__imp_CertSetCertificateContextProperty
0x180035642  test    eax, eax
0x180035644  jnz     short loc_180035674
0x180035646  call    cs:__imp_GetLastError
0x18003564c  mov     ecx, eax; unsigned int
0x18003564e  call    ?WriteCertSetupFailureEvent@Logger@@SAJK@Z; Logger::WriteCertSetupFailureEvent(ulong)
0x180035653  call    cs:__imp_GetLastError
0x180035659  mov     ebx, eax
0x18003565b  test    eax, eax
0x18003565d  jle     short loc_180035668
0x18003565f  movzx   ebx, ax
0x180035662  or      ebx, 80070000h
0x180035668  lea     r8, aCertsetcertifi_0; "CertSetCertificateContextProperty"
0x18003566f  jmp     loc_1800355AB
0x180035674  mov     ebx, esi
0x180035676  cmp     [rbp+47h+arg_20], esi
0x180035679  jz      short loc_1800356A2
0x18003567b  mov     rdx, rdi
0x18003567e  mov     ecx, r14d
0x180035681  call    ?DeleteOtherExistingCertificatesIfNecessary@RegistrationCertHelper@@CAJW4_CERTFICATE_LOCATION@@PEBU_CERT_CONTEXT@@@Z; RegistrationCertHelper::DeleteOtherExistingCertificatesIfNecessary(_CERTFICATE_LOCATION,_CERT_CONTEXT const *)
0x180035686  mov     ebx, eax
0x180035688  test    eax, eax
0x18003568a  jns     short loc_1800356A2
0x18003568c  mov     r9d, eax
0x18003568f  lea     r8, aRegistrationce_17; "RegistrationCertHelper::DeleteOtherExis"...
0x180035696  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18003569d  jmp     loc_1800355B5
0x1800356a2  mov     eax, 10000h
0x1800356a7  neg     r14d
0x1800356aa  sbb     r9d, r9d
0x1800356ad  xor     edx, edx; dwEncodingType
0x1800356af  and     r9d, eax
0x1800356b2  xor     r8d, r8d; hCryptProv
0x1800356b5  add     r9d, eax; dwFlags
0x1800356b8  lea     rax, aMy; "My"
0x1800356bf  mov     [rsp+0D0h+pcbBinary], rax; pvPara
0x1800356c4  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x1800356c7  call    cs:__imp_CertOpenStore
0x1800356cd  mov     rsi, rax
0x1800356d0  test    rax, rax
0x1800356d3  jnz     short loc_180035703
0x1800356d5  call    cs:__imp_GetLastError
0x1800356db  mov     ecx, eax; unsigned int
0x1800356dd  call    ?WriteCertSaveFailureEvent@Logger@@SAJK@Z; Logger::WriteCertSaveFailureEvent(ulong)
0x1800356e2  call    cs:__imp_GetLastError
0x1800356e8  mov     ebx, eax
0x1800356ea  test    eax, eax
0x1800356ec  jle     short loc_1800356F7
0x1800356ee  movzx   ebx, ax
0x1800356f1  or      ebx, 80070000h
0x1800356f7  lea     r8, aCertopenstore_0; "CertOpenStore"
0x1800356fe  jmp     loc_1800355AB
0x180035703  xor     r9d, r9d; ppStoreContext
0x180035706  mov     rdx, rdi; pCertContext
0x180035709  mov     rcx, rax; hCertStore
0x18003570c  lea     r8d, [r9+4]; dwAddDisposition
0x180035710  call    cs:__imp_CertAddCertificateContextToStore
0x180035716  test    eax, eax
0x180035718  jnz     short loc_180035748
0x18003571a  call    cs:__imp_GetLastError
0x180035720  mov     ecx, eax; unsigned int
0x180035722  call    ?WriteCertSaveFailureEvent@Logger@@SAJK@Z; Logger::WriteCertSaveFailureEvent(ulong)
0x180035727  call    cs:__imp_GetLastError
0x18003572d  mov     ebx, eax
0x18003572f  test    eax, eax
0x180035731  jle     short loc_18003573C
0x180035733  movzx   ebx, ax
0x180035736  or      ebx, 80070000h
0x18003573c  lea     r8, aCertaddcertifi_0; "CertAddCertificateContextToStore"
0x180035743  jmp     loc_1800355AB
0x180035748  mov     rcx, rdi; pCertContext
0x18003574b  call    cs:__imp_CertDuplicateCertificateContext
0x180035751  mov     [r15], rax
0x180035754  mov     rcx, [rbp+47h+pbCertEncoded]; hMem
0x180035758  call    cs:__imp_LocalFree
0x18003575e  test    rdi, rdi
0x180035761  jz      short loc_18003579F
0x180035763  mov     rcx, rdi; pCertContext
0x180035766  call    cs:__imp_CertFreeCertificateContext
0x18003576c  test    eax, eax
0x18003576e  jnz     short loc_18003579F
0x180035770  call    cs:__imp_GetLastError
0x180035776  test    eax, eax
0x180035778  jle     short loc_180035782
0x18003577a  movzx   eax, ax
0x18003577d  or      eax, 80070000h
0x180035782  mov     r9d, eax
0x180035785  lea     r8, aCertfreecertif_0; "CertFreeCertificateContext"
0x18003578c  lea     rdx, aRegistrationce_28; "RegistrationCertHelper::InstallCertific"...
0x180035793  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x18003579a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003579f  test    rsi, rsi
0x1800357a2  jz      short loc_1800357E5
0x1800357a4  mov     edx, 2; dwFlags
0x1800357a9  mov     rcx, rsi; hCertStore
0x1800357ac  call    cs:__imp_CertCloseStore
0x1800357b2  test    eax, eax
0x1800357b4  jnz     short loc_1800357E5
0x1800357b6  call    cs:__imp_GetLastError
0x1800357bc  test    eax, eax
0x1800357be  jle     short loc_1800357C8
0x1800357c0  movzx   eax, ax
0x1800357c3  or      eax, 80070000h
0x1800357c8  mov     r9d, eax
0x1800357cb  lea     r8, aCertclosestore_0; "CertCloseStore"
0x1800357d2  lea     rdx, aRegistrationce_28; "RegistrationCertHelper::InstallCertific"...
0x1800357d9  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x1800357e0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800357e5  mov     r8d, ebx
0x1800357e8  lea     rdx, aRegistrationce_28; "RegistrationCertHelper::InstallCertific"...
0x1800357ef  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x1800357f6  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800357fb  mov     eax, ebx
0x1800357fd  add     rsp, 98h
0x180035804  pop     r15
0x180035806  pop     r14
0x180035808  pop     r13
0x18003580a  pop     r12
0x18003580c  pop     rdi
0x18003580d  pop     rsi
0x18003580e  pop     rbx
0x18003580f  pop     rbp
0x180035810  retn
```
