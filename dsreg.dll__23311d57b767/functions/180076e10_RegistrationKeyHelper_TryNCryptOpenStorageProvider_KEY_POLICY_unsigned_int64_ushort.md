# RegistrationKeyHelper::TryNCryptOpenStorageProvider(_KEY_POLICY,unsigned __int64 *,ushort * *)

- ea: `0x180076e10`
- end: `0x18007703f`
- name: `?TryNCryptOpenStorageProvider@RegistrationKeyHelper@@CAJW4_KEY_POLICY@@PEA_KPEAPEAG@Z`
- size: `559`
- prototype: `static int __high(enum _KEY_POLICY, unsigned __int64 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007491c`
- `0x180076658`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x18000ddf0`
- `0x180012948`
- `0x1800307c4`
- `0x180076b8c`
- `0x180076bd8`
- `0x180076e10`

## import_xrefs

- `ncrypt!NCryptGetProperty` at `0x180076f45`
- `ncrypt!NCryptGetProperty` at `0x180076f45`
- `ncrypt!NCryptFreeObject` at `0x180077000`
- `ncrypt!NCryptFreeObject` at `0x180077000`

## string_xrefs

- `0x180076fad`: `CopyStringW`
- `0x180076e24`: `RegistrationKeyHelper::TryNCryptOpenStorageProvider`
- `0x180076eb6`: `%s: Trying to open hardware provider '%s'.`
- `0x180076ed9`: `%s: OpenNCryptStorageProvider failed with error code 0x%08x. Provider name = %s`
- `0x18007702b`: `%s: OpenNCryptStorageProvider failed with error code 0x%08x. Provider name = %s`
- `0x180076fec`: `%s: Trying to open software provider.`

## pseudocode

```c
__int64 __fastcall RegistrationKeyHelper::TryNCryptOpenStorageProvider(
        int a1,
        NCRYPT_PROV_HANDLE *a2,
        unsigned __int16 **a3)
{
  int v6; // ebx
  const unsigned __int16 *v7; // rdx
  const unsigned __int16 *v8; // rbp
  int v9; // eax
  int IsTpmProvider; // eax
  const wchar_t *v11; // r8
  SECURITY_STATUS Property; // eax
  __int64 v13; // rdx
  int v15; // eax
  int v16; // [rsp+70h] [rbp+8h] BYREF
  int pbOutput; // [rsp+80h] [rbp+18h] BYREF
  DWORD pcbResult; // [rsp+88h] [rbp+20h] BYREF

  pbOutput = 0;
  pcbResult = 0;
  if ( !a3 )
  {
    v6 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationKeyHelper::TryNCryptOpenStorageProvider",
      L"ppszProviderName");
    v7 = L"ppszProviderName";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationKeyHelper::TryNCryptOpenStorageProvider", v7);
    goto LABEL_23;
  }
  *a3 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationKeyHelper::TryNCryptOpenStorageProvider",
      L"phProvider");
    v7 = L"phProvider";
    goto LABEL_3;
  }
  *a2 = 0;
  if ( a1 == 3 )
    goto LABEL_24;
  v8 = L"Microsoft Platform Crypto Provider";
  Logger::TraceInformation(
    L"%s: Trying to open hardware provider '%s'.",
    L"RegistrationKeyHelper::TryNCryptOpenStorageProvider",
    L"Microsoft Platform Crypto Provider");
  v9 = RegistrationKeyHelper::OpenNCryptStorageProvider(L"Microsoft Platform Crypto Provider", a2, 0);
  v6 = v9;
  if ( v9 < 0 )
  {
    Logger::TraceInformation(
      L"%s: OpenNCryptStorageProvider failed with error code 0x%08x. Provider name = %s",
      L"RegistrationKeyHelper::TryNCryptOpenStorageProvider",
      (unsigned int)v9,
      L"Microsoft Platform Crypto Provider");
    goto LABEL_16;
  }
  v16 = 0;
  IsTpmProvider = RegistrationKeyHelper::IsTpmProvider(L"Microsoft Platform Crypto Provider", &v16);
  v6 = IsTpmProvider;
  if ( IsTpmProvider < 0 )
  {
    v11 = L"IsTpmProvider";
LABEL_22:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationKeyHelper::TryNCryptOpenStorageProvider",
      v11,
      (unsigned int)IsTpmProvider);
    goto LABEL_23;
  }
  if ( v16 )
  {
    Property = NCryptGetProperty(*a2, L"PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY", (PBYTE)&pbOutput, 4u, &pcbResult, 0);
    v6 = Property;
    if ( Property >= 0 )
    {
      if ( !pbOutput )
        goto LABEL_18;
      Logger::TraceWarning(
        (wchar_t *)L"%s: The TPM has known RSA keygen vulnerability. Will fallback to software KSP if policy allows.",
        L"RegistrationKeyHelper::TryNCryptOpenStorageProvider");
      v6 = -2145648564;
    }
    else
    {
      Logger::TraceWarning(
        (wchar_t *)L"%s: NCryptGetProperty(NCRYPT_PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY_PROPERTY) failed with 0x%08x",
        L"RegistrationKeyHelper::TryNCryptOpenStorageProvider",
        (unsigned int)Property);
    }
LABEL_16:
    if ( a1 == 2 )
    {
      if ( v6 < 0 )
        goto LABEL_23;
      goto LABEL_18;
    }
LABEL_24:
    Logger::TraceVerbose(
      (wchar_t *)L"%s: Trying to open software provider.",
      L"RegistrationKeyHelper::TryNCryptOpenStorageProvider");
    if ( *a2 )
    {
      NCryptFreeObject(*a2);
      *a2 = 0;
    }
    v8 = L"Microsoft Software Key Storage Provider";
    v15 = RegistrationKeyHelper::OpenNCryptStorageProvider(L"Microsoft Software Key Storage Provider", a2, 0);
    v6 = v15;
    if ( v15 < 0 )
    {
      Logger::TraceError(
        L"%s: OpenNCryptStorageProvider failed with error code 0x%08x. Provider name = %s",
        L"RegistrationKeyHelper::TryNCryptOpenStorageProvider",
        (unsigned int)v15,
        L"Microsoft Software Key Storage Provider");
      goto LABEL_23;
    }
  }
LABEL_18:
  v13 = -1;
  do
    ++v13;
  while ( v8[v13] );
  IsTpmProvider = CopyStringW(v8, v13, a3);
  v6 = IsTpmProvider;
  if ( IsTpmProvider < 0 )
  {
    v11 = L"CopyStringW";
    goto LABEL_22;
  }
LABEL_23:
  Logger::TraceVerbose(
    (wchar_t *)L"%s - hr: 0x%08x",
    L"RegistrationKeyHelper::TryNCryptOpenStorageProvider",
    (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180076e10  mov     rax, rsp
0x180076e13  push    rbx
0x180076e14  push    rbp
0x180076e15  push    rsi
0x180076e16  push    rdi
0x180076e17  push    r12
0x180076e19  push    r14
0x180076e1b  push    r15
0x180076e1d  sub     rsp, 30h
0x180076e21  xor     r12d, r12d
0x180076e24  lea     rdi, aRegistrationke; "RegistrationKeyHelper::TryNCryptOpenSto"...
0x180076e2b  mov     [rax+18h], r12d
0x180076e2f  mov     r14, r8
0x180076e32  mov     [rax+20h], r12d
0x180076e36  mov     rsi, rdx
0x180076e39  mov     r15d, ecx
0x180076e3c  test    r8, r8
0x180076e3f  jnz     short loc_180076E70
0x180076e41  lea     r8, aPpszproviderna; "ppszProviderName"
0x180076e48  mov     rdx, rdi
0x180076e4b  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180076e52  mov     ebx, 80070057h
0x180076e57  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180076e5c  lea     rdx, aPpszproviderna; "ppszProviderName"
0x180076e63  mov     rcx, rdi; unsigned __int16 *
0x180076e66  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180076e6b  jmp     loc_180076FC6
0x180076e70  mov     [r8], r12
0x180076e73  test    rsi, rsi
0x180076e76  jnz     short loc_180076E9C
0x180076e78  lea     r8, aPhprovider; "phProvider"
0x180076e7f  mov     rdx, rdi
0x180076e82  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180076e89  mov     ebx, 80070057h
0x180076e8e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180076e93  lea     rdx, aPhprovider; "phProvider"
0x180076e9a  jmp     short loc_180076E63
0x180076e9c  mov     [rdx], r12
0x180076e9f  cmp     r15d, 3
0x180076ea3  jz      loc_180076FE9
0x180076ea9  lea     rbp, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180076eb0  mov     rdx, rdi
0x180076eb3  mov     r8, rbp
0x180076eb6  lea     rcx, aSTryingToOpenH; "%s: Trying to open hardware provider '%"...
0x180076ebd  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180076ec2  xor     r8d, r8d; int
0x180076ec5  mov     rdx, rsi; phProvider
0x180076ec8  mov     rcx, rbp; unsigned __int16 *
0x180076ecb  call    ?OpenNCryptStorageProvider@RegistrationKeyHelper@@SAJPEBGPEA_KH@Z; RegistrationKeyHelper::OpenNCryptStorageProvider(ushort const *,unsigned __int64 *,int)
0x180076ed0  mov     ebx, eax
0x180076ed2  test    eax, eax
0x180076ed4  jns     short loc_180076EF0
0x180076ed6  mov     r9, rbp
0x180076ed9  lea     rcx, aSOpenncryptsto; "%s: OpenNCryptStorageProvider failed wi"...
0x180076ee0  mov     r8d, eax
0x180076ee3  mov     rdx, rdi
0x180076ee6  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180076eeb  jmp     loc_180076F83
0x180076ef0  lea     rdx, [rsp+68h+arg_0]; int *
0x180076ef5  mov     [rsp+68h+arg_0], r12d
0x180076efa  mov     rcx, rbp; unsigned __int16 *
0x180076efd  call    ?IsTpmProvider@RegistrationKeyHelper@@SAJPEBGAEAH@Z; RegistrationKeyHelper::IsTpmProvider(ushort const *,int &)
0x180076f02  mov     ebx, eax
0x180076f04  test    eax, eax
0x180076f06  jns     short loc_180076F14
0x180076f08  lea     r8, aIstpmprovider; "IsTpmProvider"
0x180076f0f  jmp     loc_180076FB4
0x180076f14  cmp     [rsp+68h+arg_0], r12d
0x180076f19  jz      short loc_180076F8D
0x180076f1b  mov     rcx, [rsi]; hObject
0x180076f1e  lea     rax, [rsp+68h+arg_18]
0x180076f26  mov     [rsp+68h+dwFlags], r12d; dwFlags
0x180076f2b  lea     r8, [rsp+68h+pbOutput]; pbOutput
0x180076f33  mov     r9d, 4; cbOutput
0x180076f39  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180076f3e  lea     rdx, aPcpTpmIfxRsaKe; "PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY"
0x180076f45  call    cs:__imp_NCryptGetProperty
0x180076f4b  mov     ebx, eax
0x180076f4d  test    eax, eax
0x180076f4f  jns     short loc_180076F65
0x180076f51  mov     r8d, eax
0x180076f54  lea     rcx, aSNcryptgetprop; "%s: NCryptGetProperty(NCRYPT_PCP_TPM_IF"...
0x180076f5b  mov     rdx, rdi
0x180076f5e  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180076f63  jmp     short loc_180076F83
0x180076f65  cmp     [rsp+68h+pbOutput], r12d
0x180076f6d  jz      short loc_180076F8D
0x180076f6f  mov     rdx, rdi
0x180076f72  lea     rcx, aSTheTpmHasKnow; "%s: The TPM has known RSA keygen vulner"...
0x180076f79  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180076f7e  mov     ebx, 801C004Ch
0x180076f83  cmp     r15d, 2
0x180076f87  jnz     short loc_180076FE9
0x180076f89  test    ebx, ebx
0x180076f8b  js      short loc_180076FC6
0x180076f8d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180076f91  inc     rdx; unsigned __int64
0x180076f94  cmp     [rbp+rdx*2+0], r12w
0x180076f9a  jnz     short loc_180076F91
0x180076f9c  mov     r8, r14; unsigned __int16 **
0x180076f9f  mov     rcx, rbp; Source
0x180076fa2  call    ?CopyStringW@@YAJPEBG_KPEAPEAG@Z; CopyStringW(ushort const *,unsigned __int64,ushort * *)
0x180076fa7  mov     ebx, eax
0x180076fa9  test    eax, eax
0x180076fab  jns     short loc_180076FC6
0x180076fad  lea     r8, aCopystringw; "CopyStringW"
0x180076fb4  mov     r9d, eax
0x180076fb7  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180076fbe  mov     rdx, rdi
0x180076fc1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180076fc6  mov     r8d, ebx
0x180076fc9  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180076fd0  mov     rdx, rdi
0x180076fd3  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180076fd8  mov     eax, ebx
0x180076fda  add     rsp, 30h
0x180076fde  pop     r15
0x180076fe0  pop     r14
0x180076fe2  pop     r12
0x180076fe4  pop     rdi
0x180076fe5  pop     rsi
0x180076fe6  pop     rbp
0x180076fe7  pop     rbx
0x180076fe8  retn
0x180076fe9  mov     rdx, rdi
0x180076fec  lea     rcx, aSTryingToOpenS; "%s: Trying to open software provider."
0x180076ff3  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180076ff8  mov     rcx, [rsi]; hObject
0x180076ffb  test    rcx, rcx
0x180076ffe  jz      short loc_180077009
0x180077000  call    cs:__imp_NCryptFreeObject
0x180077006  mov     [rsi], r12
0x180077009  lea     rbp, aMicrosoftSoftw; "Microsoft Software Key Storage Provider"
0x180077010  xor     r8d, r8d; int
0x180077013  mov     rcx, rbp; unsigned __int16 *
0x180077016  mov     rdx, rsi; phProvider
0x180077019  call    ?OpenNCryptStorageProvider@RegistrationKeyHelper@@SAJPEBGPEA_KH@Z; RegistrationKeyHelper::OpenNCryptStorageProvider(ushort const *,unsigned __int64 *,int)
0x18007701e  mov     ebx, eax
0x180077020  test    eax, eax
0x180077022  jns     loc_180076F8D
0x180077028  mov     r9, rbp
0x18007702b  lea     rcx, aSOpenncryptsto; "%s: OpenNCryptStorageProvider failed wi"...
0x180077032  mov     r8d, eax
0x180077035  mov     rdx, rdi
0x180077038  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007703d  jmp     short loc_180076FC6
```
