# RegistrationKeyHelper::OpenNCryptStorageProvider(ushort const *,unsigned __int64 *,int)

- ea: `0x180076bd8`
- end: `0x180076e09`
- name: `?OpenNCryptStorageProvider@RegistrationKeyHelper@@SAJPEBGPEA_KH@Z`
- size: `561`
- prototype: `__int64 __fastcall(const unsigned __int16 *, NCRYPT_PROV_HANDLE *phProvider, int)`
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180074c58`
- `0x1800760f0`
- `0x18007683c`
- `0x180076e10`
- `0x1800b26e4`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x1800307c4`
- `0x180044300`
- `0x180076b8c`
- `0x180076bd8`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x180076d3a`
- `ncrypt!NCryptSetProperty` at `0x180076d3a`
- `ncrypt!NCryptGetProperty` at `0x180076d8e`
- `ncrypt!NCryptGetProperty` at `0x180076d8e`
- `ncrypt!NCryptOpenStorageProvider` at `0x180076cb3`
- `ncrypt!NCryptOpenStorageProvider` at `0x180076cb3`
- `ncrypt!NCryptFreeObject` at `0x180076dc8`
- `ncrypt!NCryptFreeObject` at `0x180076dc8`

## string_xrefs

- `0x180076c11`: `RegistrationKeyHelper::OpenNCryptStorageProvider`
- `0x180076cbf`: `NCryptOpenStorageProvider`
- `0x180076daf`: `%s: The TPM has known RSA keygen vulnerability and cannot be used to create keys.`

## pseudocode

```c
__int64 __fastcall RegistrationKeyHelper::OpenNCryptStorageProvider(
        const unsigned __int16 *a1,
        NCRYPT_PROV_HANDLE *phProvider,
        int a3)
{
  const wchar_t *v4; // r9
  unsigned int v7; // ebx
  SECURITY_STATUS IsTpmProvider; // eax
  const wchar_t *v9; // r8
  NCRYPT_HANDLE v10; // rcx
  SECURITY_STATUS v11; // eax
  NCRYPT_HANDLE v12; // rcx
  BYTE pbOutput[4]; // [rsp+30h] [rbp-20h] BYREF
  DWORD pcbResult; // [rsp+34h] [rbp-1Ch] BYREF
  BYTE pbInput[4]; // [rsp+38h] [rbp-18h] BYREF
  int v17; // [rsp+3Ch] [rbp-14h]
  int v18; // [rsp+40h] [rbp-10h]
  int v19; // [rsp+44h] [rbp-Ch]

  *(_DWORD *)pbOutput = 0;
  v4 = L"<NULL>";
  if ( a1 )
    v4 = a1;
  Logger::TraceVerbose(
    (wchar_t *)L"%s started. %s: %s.",
    L"RegistrationKeyHelper::OpenNCryptStorageProvider",
    L"providerName",
    v4);
  if ( !phProvider )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationKeyHelper::OpenNCryptStorageProvider",
      L"handle");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationKeyHelper::OpenNCryptStorageProvider", L"handle");
    goto LABEL_22;
  }
  *phProvider = 0;
  if ( (unsigned int)IsEmptyString(a1) )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null or empty.",
      L"RegistrationKeyHelper::OpenNCryptStorageProvider",
      L"providerName");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationKeyHelper::OpenNCryptStorageProvider", L"providerName");
    goto LABEL_20;
  }
  IsTpmProvider = NCryptOpenStorageProvider(phProvider, a1, 0);
  v7 = IsTpmProvider;
  if ( IsTpmProvider < 0 )
  {
    v9 = L"NCryptOpenStorageProvider";
LABEL_9:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationKeyHelper::OpenNCryptStorageProvider",
      v9,
      (unsigned int)IsTpmProvider);
LABEL_20:
    if ( *phProvider )
    {
      NCryptFreeObject(*phProvider);
      *phProvider = 0;
    }
    goto LABEL_22;
  }
  IsTpmProvider = RegistrationKeyHelper::IsTpmProvider(a1, (int *)pbOutput);
  v7 = IsTpmProvider;
  if ( IsTpmProvider < 0 )
  {
    v9 = L"IsTpmProvider";
    goto LABEL_9;
  }
  if ( *(_DWORD *)pbOutput )
  {
    v10 = *phProvider;
    *(_DWORD *)pbInput = -1429209087;
    v17 = 1180574512;
    v18 = -327497080;
    v19 = -2029071512;
    v11 = NCryptSetProperty(v10, L"PCP_SESSIONID", pbInput, 0x10u, 0);
    if ( v11 < 0 )
      Logger::TraceWarning(
        (wchar_t *)L"%s: NCryptSetProperty(NCRYPT_PCP_SESSIONID_PROPERTY) failed with 0x%08x",
        L"RegistrationKeyHelper::OpenNCryptStorageProvider",
        (unsigned int)v11);
    if ( a3 )
    {
      v12 = *phProvider;
      *(_DWORD *)pbOutput = 0;
      pcbResult = 0;
      IsTpmProvider = NCryptGetProperty(v12, L"PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY", pbOutput, 4u, &pcbResult, 0);
      v7 = IsTpmProvider;
      if ( IsTpmProvider >= 0 )
      {
        if ( !*(_DWORD *)pbOutput )
          goto LABEL_22;
        Logger::TraceWarning(
          (wchar_t *)L"%s: The TPM has known RSA keygen vulnerability and cannot be used to create keys.",
          L"RegistrationKeyHelper::OpenNCryptStorageProvider");
        v7 = -2145648564;
        goto LABEL_20;
      }
      v9 = L"NCryptGetProperty(NCRYPT_PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY_PROPERTY)";
      goto LABEL_9;
    }
  }
LABEL_22:
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationKeyHelper::OpenNCryptStorageProvider", v7);
  return v7;
}

```

## disassembly

```asm
0x180076bd8  mov     [rsp-28h+arg_10], rbx
0x180076bdd  push    rbp
0x180076bde  push    rsi
0x180076bdf  push    rdi
0x180076be0  push    r12
0x180076be2  push    r14
0x180076be4  mov     rbp, rsp
0x180076be7  sub     rsp, 50h
0x180076beb  mov     rax, cs:__security_cookie
0x180076bf2  xor     rax, rsp
0x180076bf5  mov     [rbp+var_8], rax
0x180076bf9  test    rcx, rcx
0x180076bfc  mov     dword ptr [rbp+pbOutput], 0
0x180076c03  mov     r14d, r8d
0x180076c06  lea     r9, aNull_2; "<NULL>"
0x180076c0d  cmovnz  r9, rcx
0x180076c11  lea     r12, aRegistrationke_9; "RegistrationKeyHelper::OpenNCryptStorag"...
0x180076c18  mov     rdi, rdx
0x180076c1b  lea     r8, aProvidername; "providerName"
0x180076c22  mov     rsi, rcx
0x180076c25  mov     rdx, r12
0x180076c28  lea     rcx, aSStartedSS; "%s started. %s: %s."
0x180076c2f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180076c34  test    rdi, rdi
0x180076c37  jnz     short loc_180076C68
0x180076c39  lea     r8, aHandle; "handle"
0x180076c40  mov     rdx, r12
0x180076c43  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180076c4a  mov     ebx, 80070057h
0x180076c4f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180076c54  lea     rdx, aHandle; "handle"
0x180076c5b  mov     rcx, r12; unsigned __int16 *
0x180076c5e  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180076c63  jmp     loc_180076DD5
0x180076c68  mov     rcx, rsi; unsigned __int16 *
0x180076c6b  mov     qword ptr [rdi], 0
0x180076c72  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180076c77  test    eax, eax
0x180076c79  jz      short loc_180076CAA
0x180076c7b  lea     r8, aProvidername; "providerName"
0x180076c82  mov     rdx, r12
0x180076c85  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null or empty."
0x180076c8c  mov     ebx, 80070057h
0x180076c91  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180076c96  lea     rdx, aProvidername; "providerName"
0x180076c9d  mov     rcx, r12; unsigned __int16 *
0x180076ca0  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180076ca5  jmp     loc_180076DC0
0x180076caa  xor     r8d, r8d; dwFlags
0x180076cad  mov     rdx, rsi; pszProviderName
0x180076cb0  mov     rcx, rdi; phProvider
0x180076cb3  call    cs:__imp_NCryptOpenStorageProvider
0x180076cb9  mov     ebx, eax
0x180076cbb  test    eax, eax
0x180076cbd  jns     short loc_180076CDD
0x180076cbf  lea     r8, aNcryptopenstor_0; "NCryptOpenStorageProvider"
0x180076cc6  mov     r9d, eax
0x180076cc9  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180076cd0  mov     rdx, r12
0x180076cd3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180076cd8  jmp     loc_180076DC0
0x180076cdd  lea     rdx, [rbp+pbOutput]; int *
0x180076ce1  mov     rcx, rsi; unsigned __int16 *
0x180076ce4  call    ?IsTpmProvider@RegistrationKeyHelper@@SAJPEBGAEAH@Z; RegistrationKeyHelper::IsTpmProvider(ushort const *,int &)
0x180076ce9  mov     ebx, eax
0x180076ceb  test    eax, eax
0x180076ced  jns     short loc_180076CF8
0x180076cef  lea     r8, aIstpmprovider; "IsTpmProvider"
0x180076cf6  jmp     short loc_180076CC6
0x180076cf8  cmp     dword ptr [rbp+pbOutput], 0
0x180076cfc  jz      loc_180076DD5
0x180076d02  mov     rcx, [rdi]; hObject
0x180076d05  lea     r8, [rbp+pbInput]; pbInput
0x180076d09  mov     r9d, 10h; cbInput
0x180076d0f  mov     dword ptr [rbp+pbInput], 0AAD00001h
0x180076d16  lea     rdx, aPcpSessionid; "PCP_SESSIONID"
0x180076d1d  mov     [rbp+var_14], 465E2330h
0x180076d24  mov     [rbp+var_10], 0EC7ACA88h
0x180076d2b  mov     [rbp+var_C], 870ED368h
0x180076d32  mov     [rsp+50h+dwFlags], 0; dwFlags
0x180076d3a  call    cs:__imp_NCryptSetProperty
0x180076d40  test    eax, eax
0x180076d42  jns     short loc_180076D56
0x180076d44  mov     r8d, eax
0x180076d47  lea     rcx, aSNcryptsetprop; "%s: NCryptSetProperty(NCRYPT_PCP_SESSIO"...
0x180076d4e  mov     rdx, r12
0x180076d51  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180076d56  test    r14d, r14d
0x180076d59  jz      short loc_180076DD5
0x180076d5b  mov     rcx, [rdi]; hObject
0x180076d5e  lea     rax, [rbp+pcbResult]
0x180076d62  mov     [rsp+50h+var_28], 0; dwFlags
0x180076d6a  lea     r8, [rbp+pbOutput]; pbOutput
0x180076d6e  mov     r9d, 4; cbOutput
0x180076d74  mov     qword ptr [rsp+50h+dwFlags], rax; pcbResult
0x180076d79  lea     rdx, aPcpTpmIfxRsaKe; "PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY"
0x180076d80  mov     dword ptr [rbp+pbOutput], 0
0x180076d87  mov     [rbp+pcbResult], 0
0x180076d8e  call    cs:__imp_NCryptGetProperty
0x180076d94  mov     ebx, eax
0x180076d96  test    eax, eax
0x180076d98  jns     short loc_180076DA6
0x180076d9a  lea     r8, aNcryptgetprope_0; "NCryptGetProperty(NCRYPT_PCP_TPM_IFX_RS"...
0x180076da1  jmp     loc_180076CC6
0x180076da6  cmp     dword ptr [rbp+pbOutput], 0
0x180076daa  jz      short loc_180076DD5
0x180076dac  mov     rdx, r12
0x180076daf  lea     rcx, aSTheTpmHasKnow_0; "%s: The TPM has known RSA keygen vulner"...
0x180076db6  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180076dbb  mov     ebx, 801C004Ch
0x180076dc0  mov     rcx, [rdi]; hObject
0x180076dc3  test    rcx, rcx
0x180076dc6  jz      short loc_180076DD5
0x180076dc8  call    cs:__imp_NCryptFreeObject
0x180076dce  mov     qword ptr [rdi], 0
0x180076dd5  mov     r8d, ebx
0x180076dd8  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180076ddf  mov     rdx, r12
0x180076de2  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180076de7  mov     eax, ebx
0x180076de9  mov     rcx, [rbp+var_8]
0x180076ded  xor     rcx, rsp; StackCookie
0x180076df0  call    __security_check_cookie
0x180076df5  mov     rbx, [rsp+50h+arg_10]
0x180076dfd  add     rsp, 50h
0x180076e01  pop     r14
0x180076e03  pop     r12
0x180076e05  pop     rdi
0x180076e06  pop     rsi
0x180076e07  pop     rbp
0x180076e08  retn
```
