# RegistrationCertHelper::DeleteDeviceUserCertificates(_CERTFICATE_LOCATION,ushort const *,ushort const *,ushort const *,ushort const *,ulong &)

- ea: `0x18005d0f0`
- end: `0x18005d41e`
- name: `?DeleteDeviceUserCertificates@RegistrationCertHelper@@CAJW4_CERTFICATE_LOCATION@@PEBG111AEAK@Z`
- size: `814`
- prototype: `static int __high(enum _CERTFICATE_LOCATION, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18005ce14`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x1800307c4`
- `0x18005d0f0`
- `0x1800966a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d1c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d26e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d32f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d3ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d1c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d26e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d32f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d3ef`
- `CRYPT32!CertOpenStore` at `0x18005d1b8`
- `CRYPT32!CertOpenStore` at `0x18005d1b8`
- `CRYPT32!CertFindCertificateInStore` at `0x18005d224`
- `CRYPT32!CertFindCertificateInStore` at `0x18005d224`
- `CRYPT32!CertCloseStore` at `0x18005d3e5`
- `CRYPT32!CertCloseStore` at `0x18005d3e5`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18005d260`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18005d260`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18005d31c`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18005d31c`
- `CRYPT32!CertFreeCertificateContext` at `0x18005d34e`
- `CRYPT32!CertFreeCertificateContext` at `0x18005d3c5`
- `CRYPT32!CertFreeCertificateContext` at `0x18005d3d3`
- `CRYPT32!CertFreeCertificateContext` at `0x18005d34e`
- `CRYPT32!CertFreeCertificateContext` at `0x18005d3c5`
- `CRYPT32!CertFreeCertificateContext` at `0x18005d3d3`

## string_xrefs

- `0x18005d1d6`: `CertOpenStore`
- `0x18005d33b`: `CertDeleteCertificateFromStore`
- `0x18005d129`: `RegistrationCertHelper::DeleteDeviceUserCertificates`
- `0x18005d164`: `RegistrationCertHelper::DeleteDeviceUserCertificates`
- `0x18005d1dd`: `RegistrationCertHelper::DeleteDeviceUserCertificates`
- `0x18005d202`: `RegistrationCertHelper::DeleteDeviceUserCertificates`
- `0x18005d251`: `%s: Found Certificate from the Issuer = %s to delete.`
- `0x18005d301`: `%s: Found Certificate with Issuer '%s', Tenant ID '%s' and Device ID '%s' to delete.`

## pseudocode

```c
__int64 __fastcall RegistrationCertHelper::DeleteDeviceUserCertificates(
        int a1,
        const void *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        _DWORD *a6)
{
  _DWORD *v6; // r13
  unsigned int v8; // esi
  const unsigned __int16 *v9; // rdx
  int v10; // ebx
  const CERT_CONTEXT *pPrevCertContext; // r14
  HCERTSTORE v12; // rax
  DWORD LastError; // eax
  PCCERT_CONTEXT v14; // rbp
  const wchar_t *v15; // r8
  char v16; // r15
  int v17; // eax
  unsigned __int16 *v18; // rcx
  const wchar_t *v19; // rax
  bool v20; // zf
  DWORD v21; // eax
  HCERTSTORE hCertStore; // [rsp+78h] [rbp+10h]
  __int64 v24; // [rsp+80h] [rbp+18h] BYREF
  unsigned __int16 *v25; // [rsp+88h] [rbp+20h]

  v25 = a4;
  v24 = a3;
  v6 = a6;
  *a6 = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationCertHelper::DeleteDeviceUserCertificates",
      L"issuer");
    v9 = L"issuer";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationCertHelper::DeleteDeviceUserCertificates", v9);
    return v8;
  }
  if ( !a4 )
  {
    v8 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationCertHelper::DeleteDeviceUserCertificates",
      L"tenantId");
    v9 = L"tenantId";
    goto LABEL_3;
  }
  v10 = 0;
  pPrevCertContext = 0;
  v12 = CertOpenStore((LPCSTR)0xA, 0, 0, a1 != 0 ? 0x20000 : 0x10000, L"My");
  hCertStore = v12;
  if ( v12 )
    goto LABEL_11;
  LastError = GetLastError();
  v10 = LastError;
  if ( !LastError )
  {
    v12 = 0;
LABEL_11:
    v8 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        v14 = 0;
        pPrevCertContext = CertFindCertificateInStore(v12, 0x10001u, 0, 0x80004u, a2, pPrevCertContext);
        if ( !pPrevCertContext )
        {
LABEL_32:
          if ( v10 )
            goto LABEL_33;
          goto LABEL_36;
        }
        v16 = 1;
        LOBYTE(a6) = 0;
        LOBYTE(v24) = 1;
        Logger::TraceVerbose(
          (wchar_t *)L"%s: Found Certificate from the Issuer = %s to delete.",
          L"RegistrationCertHelper::DeleteDeviceUserCertificates",
          a2);
        v14 = CertDuplicateCertificateContext(pPrevCertContext);
        if ( !v14 )
        {
          LastError = GetLastError();
          v10 = LastError;
          if ( LastError )
          {
            v15 = L"CertDuplicateCertificateContext";
            goto LABEL_9;
          }
        }
        v17 = CertificateUtil::CertificateSubjectContains(v14, v25, (bool *)&a6);
        v8 = v17;
        if ( v17 < 0 )
        {
LABEL_31:
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"RegistrationCertHelper::DeleteDeviceUserCertificates",
            L"CertificateSubjectContains",
            (unsigned int)v17);
          goto LABEL_32;
        }
        v18 = a5;
        if ( a5 )
        {
          v17 = CertificateUtil::CertificateSubjectContains(v14, a5, (bool *)&v24);
          v8 = v17;
          if ( v17 < 0 )
            goto LABEL_31;
          v16 = v24;
          v18 = a5;
        }
        if ( !(_BYTE)a6 || !v16 )
          break;
        v19 = v18;
        if ( !v18 )
          v19 = L"N/A";
        Logger::TraceVerbose(
          (wchar_t *)L"%s: Found Certificate with Issuer '%s', Tenant ID '%s' and Device ID '%s' to delete.",
          L"RegistrationCertHelper::DeleteDeviceUserCertificates",
          a2,
          v25,
          v19);
        v20 = !CertDeleteCertificateFromStore(v14);
        v12 = hCertStore;
        if ( v20 )
        {
          LastError = GetLastError();
          v10 = LastError;
          if ( LastError )
          {
            v15 = L"CertDeleteCertificateFromStore";
            goto LABEL_9;
          }
          goto LABEL_28;
        }
      }
      ++*v6;
      v20 = !CertFreeCertificateContext(v14);
      v12 = hCertStore;
      if ( v20 )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError )
        {
          v15 = L"CertFreeCertificateContext";
          goto LABEL_9;
        }
LABEL_28:
        v12 = hCertStore;
      }
    }
  }
  v14 = 0;
  v15 = L"CertOpenStore";
LABEL_9:
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"RegistrationCertHelper::DeleteDeviceUserCertificates",
    v15,
    LastError);
LABEL_33:
  if ( v10 > 0 )
    v8 = (unsigned __int16)v10 | 0x80070000;
  else
    v8 = v10;
LABEL_36:
  if ( v14 )
    CertFreeCertificateContext(v14);
  if ( pPrevCertContext )
    CertFreeCertificateContext(pPrevCertContext);
  if ( hCertStore && !CertCloseStore(hCertStore, 0) )
  {
    v21 = GetLastError();
    Logger::TraceWarning(
      (wchar_t *)L"%s: CertCloseStore failed with error code: 0x%08x. Igored.",
      L"RegistrationCertHelper::DeleteDeviceUserCertificates",
      v21);
  }
  return v8;
}

```

## disassembly

```asm
0x18005d0f0  mov     [rsp+arg_0], rbx
0x18005d0f5  mov     [rsp+arg_18], r9
0x18005d0fa  mov     [rsp+arg_10], r8
0x18005d0ff  push    rbp
0x18005d100  push    rsi
0x18005d101  push    rdi
0x18005d102  push    r12
0x18005d104  push    r13
0x18005d106  push    r14
0x18005d108  push    r15
0x18005d10a  sub     rsp, 30h
0x18005d10e  mov     r13, [rsp+68h+arg_28]
0x18005d116  mov     rax, r9
0x18005d119  mov     r12, rdx
0x18005d11c  mov     dword ptr [r13+0], 0
0x18005d124  test    rdx, rdx
0x18005d127  jnz     short loc_18005D15F
0x18005d129  lea     rdi, aRegistrationce_23; "RegistrationCertHelper::DeleteDeviceUse"...
0x18005d130  mov     esi, 80070057h
0x18005d135  mov     rdx, rdi
0x18005d138  lea     r8, aIssuer; "issuer"
0x18005d13f  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18005d146  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005d14b  lea     rdx, aIssuer; "issuer"
0x18005d152  mov     rcx, rdi; unsigned __int16 *
0x18005d155  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18005d15a  jmp     loc_18005D407
0x18005d15f  test    rax, rax
0x18005d162  jnz     short loc_18005D18F
0x18005d164  lea     rdi, aRegistrationce_23; "RegistrationCertHelper::DeleteDeviceUse"...
0x18005d16b  mov     esi, 80070057h
0x18005d170  mov     rdx, rdi
0x18005d173  lea     r8, aTenantid_1; "tenantId"
0x18005d17a  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18005d181  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005d186  lea     rdx, aTenantid_1; "tenantId"
0x18005d18d  jmp     short loc_18005D152
0x18005d18f  mov     eax, 10000h
0x18005d194  xor     ebx, ebx
0x18005d196  xor     r14d, r14d
0x18005d199  neg     ecx
0x18005d19b  sbb     r9d, r9d
0x18005d19e  lea     ecx, [rbx+0Ah]; lpszStoreProvider
0x18005d1a1  and     r9d, eax
0x18005d1a4  xor     r8d, r8d; hCryptProv
0x18005d1a7  add     r9d, eax; dwFlags
0x18005d1aa  xor     edx, edx; dwEncodingType
0x18005d1ac  lea     rax, aMy; "My"
0x18005d1b3  mov     [rsp+68h+pvPara], rax; pvPara
0x18005d1b8  call    cs:__imp_CertOpenStore
0x18005d1be  mov     [rsp+68h+hCertStore], rax
0x18005d1c3  test    rax, rax
0x18005d1c6  jnz     short loc_18005D200
0x18005d1c8  call    cs:__imp_GetLastError
0x18005d1ce  mov     ebx, eax
0x18005d1d0  test    eax, eax
0x18005d1d2  jz      short loc_18005D1FB
0x18005d1d4  xor     ebp, ebp
0x18005d1d6  lea     r8, aCertopenstore_0; "CertOpenStore"
0x18005d1dd  lea     rdi, aRegistrationce_23; "RegistrationCertHelper::DeleteDeviceUse"...
0x18005d1e4  mov     r9d, eax
0x18005d1e7  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18005d1ee  mov     rdx, rdi
0x18005d1f1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005d1f6  jmp     loc_18005D3AC
0x18005d1fb  mov     rax, [rsp+68h+hCertStore]
0x18005d200  xor     esi, esi
0x18005d202  lea     rdi, aRegistrationce_23; "RegistrationCertHelper::DeleteDeviceUse"...
0x18005d209  mov     [rsp+68h+pPrevCertContext], r14; pPrevCertContext
0x18005d20e  mov     r9d, 80004h; dwFindType
0x18005d214  xor     r8d, r8d; dwFindFlags
0x18005d217  mov     [rsp+68h+pvPara], r12; pvFindPara
0x18005d21c  mov     edx, 10001h; dwCertEncodingType
0x18005d221  mov     rcx, rax; hCertStore
0x18005d224  call    cs:__imp_CertFindCertificateInStore
0x18005d22a  xor     ebp, ebp
0x18005d22c  mov     r14, rax
0x18005d22f  test    rax, rax
0x18005d232  jz      loc_18005D3A8
0x18005d238  mov     r15b, 1
0x18005d23b  mov     byte ptr [rsp+68h+arg_28], bpl
0x18005d243  mov     r8, r12
0x18005d246  mov     byte ptr [rsp+68h+arg_10], r15b
0x18005d24e  mov     rdx, rdi
0x18005d251  lea     rcx, aSFoundCertific_1; "%s: Found Certificate from the Issuer ="...
0x18005d258  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005d25d  mov     rcx, r14; pCertContext
0x18005d260  call    cs:__imp_CertDuplicateCertificateContext
0x18005d266  mov     rbp, rax
0x18005d269  test    rax, rax
0x18005d26c  jnz     short loc_18005D27E
0x18005d26e  call    cs:__imp_GetLastError
0x18005d274  mov     ebx, eax
0x18005d276  test    eax, eax
0x18005d278  jnz     loc_18005D377
0x18005d27e  mov     rdx, [rsp+68h+arg_18]; unsigned __int16 *
0x18005d286  lea     r8, [rsp+68h+arg_28]; bool *
0x18005d28e  mov     rcx, rbp; struct _CERT_CONTEXT *
0x18005d291  call    ?CertificateSubjectContains@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEBGPEA_N@Z; CertificateUtil::CertificateSubjectContains(_CERT_CONTEXT const *,ushort const *,bool *)
0x18005d296  mov     esi, eax
0x18005d298  test    eax, eax
0x18005d29a  js      loc_18005D38F
0x18005d2a0  mov     rcx, [rsp+68h+arg_20]
0x18005d2a8  test    rcx, rcx
0x18005d2ab  jz      short loc_18005D2DA
0x18005d2ad  mov     rdx, rcx; unsigned __int16 *
0x18005d2b0  lea     r8, [rsp+68h+arg_10]; bool *
0x18005d2b8  mov     rcx, rbp; struct _CERT_CONTEXT *
0x18005d2bb  call    ?CertificateSubjectContains@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEBGPEA_N@Z; CertificateUtil::CertificateSubjectContains(_CERT_CONTEXT const *,ushort const *,bool *)
0x18005d2c0  mov     esi, eax
0x18005d2c2  test    eax, eax
0x18005d2c4  js      loc_18005D38F
0x18005d2ca  mov     r15b, byte ptr [rsp+68h+arg_10]
0x18005d2d2  mov     rcx, [rsp+68h+arg_20]
0x18005d2da  cmp     byte ptr [rsp+68h+arg_28], 0
0x18005d2e2  jz      short loc_18005D347
0x18005d2e4  test    r15b, r15b
0x18005d2e7  jz      short loc_18005D347
0x18005d2e9  mov     r9, [rsp+68h+arg_18]
0x18005d2f1  lea     rdx, aNA; "N/A"
0x18005d2f8  test    rcx, rcx
0x18005d2fb  mov     rax, rcx
0x18005d2fe  mov     r8, r12
0x18005d301  lea     rcx, aSFoundCertific_0; "%s: Found Certificate with Issuer '%s',"...
0x18005d308  cmovz   rax, rdx
0x18005d30c  mov     rdx, rdi
0x18005d30f  mov     [rsp+68h+pvPara], rax
0x18005d314  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005d319  mov     rcx, rbp; pCertContext
0x18005d31c  call    cs:__imp_CertDeleteCertificateFromStore
0x18005d322  test    eax, eax
0x18005d324  mov     rax, [rsp+68h+hCertStore]
0x18005d329  jnz     loc_18005D209
0x18005d32f  call    cs:__imp_GetLastError
0x18005d335  mov     ebx, eax
0x18005d337  test    eax, eax
0x18005d339  jz      short loc_18005D36D
0x18005d33b  lea     r8, aCertdeletecert_0; "CertDeleteCertificateFromStore"
0x18005d342  jmp     loc_18005D1E4
0x18005d347  inc     dword ptr [r13+0]
0x18005d34b  mov     rcx, rbp; pCertContext
0x18005d34e  call    cs:__imp_CertFreeCertificateContext
0x18005d354  test    eax, eax
0x18005d356  mov     rax, [rsp+68h+hCertStore]
0x18005d35b  jnz     loc_18005D209
0x18005d361  call    cs:__imp_GetLastError
0x18005d367  mov     ebx, eax
0x18005d369  test    eax, eax
0x18005d36b  jnz     short loc_18005D383
0x18005d36d  mov     rax, [rsp+68h+hCertStore]
0x18005d372  jmp     loc_18005D209
0x18005d377  lea     r8, aCertduplicatec_0; "CertDuplicateCertificateContext"
0x18005d37e  jmp     loc_18005D1E4
0x18005d383  lea     r8, aCertfreecertif_0; "CertFreeCertificateContext"
0x18005d38a  jmp     loc_18005D1E4
0x18005d38f  mov     r9d, eax
0x18005d392  lea     r8, aCertificatesub; "CertificateSubjectContains"
0x18005d399  mov     rdx, rdi
0x18005d39c  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005d3a3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005d3a8  test    ebx, ebx
0x18005d3aa  jz      short loc_18005D3BD
0x18005d3ac  test    ebx, ebx
0x18005d3ae  jg      short loc_18005D3B4
0x18005d3b0  mov     esi, ebx
0x18005d3b2  jmp     short loc_18005D3BD
0x18005d3b4  movzx   esi, bx
0x18005d3b7  or      esi, 80070000h
0x18005d3bd  test    rbp, rbp
0x18005d3c0  jz      short loc_18005D3CB
0x18005d3c2  mov     rcx, rbp; pCertContext
0x18005d3c5  call    cs:__imp_CertFreeCertificateContext
0x18005d3cb  test    r14, r14
0x18005d3ce  jz      short loc_18005D3D9
0x18005d3d0  mov     rcx, r14; pCertContext
0x18005d3d3  call    cs:__imp_CertFreeCertificateContext
0x18005d3d9  mov     rcx, [rsp+68h+hCertStore]; hCertStore
0x18005d3de  test    rcx, rcx
0x18005d3e1  jz      short loc_18005D407
0x18005d3e3  xor     edx, edx; dwFlags
0x18005d3e5  call    cs:__imp_CertCloseStore
0x18005d3eb  test    eax, eax
0x18005d3ed  jnz     short loc_18005D407
0x18005d3ef  call    cs:__imp_GetLastError
0x18005d3f5  mov     rdx, rdi
0x18005d3f8  lea     rcx, aSCertclosestor; "%s: CertCloseStore failed with error co"...
0x18005d3ff  mov     r8d, eax
0x18005d402  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18005d407  mov     rbx, [rsp+68h+arg_0]
0x18005d40c  mov     eax, esi
0x18005d40e  add     rsp, 30h
0x18005d412  pop     r15
0x18005d414  pop     r14
0x18005d416  pop     r13
0x18005d418  pop     r12
0x18005d41a  pop     rdi
0x18005d41b  pop     rsi
0x18005d41c  pop     rbp
0x18005d41d  retn
```
