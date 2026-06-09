# GetCloudKerbTicket(ushort const *,uchar * *,ulong *)

- ea: `0x140003850`
- end: `0x140003b7a`
- name: `?GetCloudKerbTicket@@YAJPEBGPEAPEAEPEAK@Z`
- size: `810`
- prototype: `__int64 __fastcall(SEC_WCHAR *pszTargetName, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001b60`
- `0x140003850`
- `0x140004f54`
- `0x140004f90`
- `0x140005004`
- `0x14000507c`
- `0x1400053e4`
- `0x140005410`

## import_xrefs

- `Secur32!FreeCredentialsHandle` at `0x140003b2b`
- `Secur32!FreeCredentialsHandle` at `0x140003b2b`
- `Secur32!InitializeSecurityContextW` at `0x140003ac8`
- `Secur32!InitializeSecurityContextW` at `0x140003ac8`
- `Secur32!AcquireCredentialsHandleW` at `0x1400039c3`
- `Secur32!AcquireCredentialsHandleW` at `0x1400039c3`
- `Secur32!DeleteSecurityContext` at `0x140003b35`
- `Secur32!DeleteSecurityContext` at `0x140003b35`
- `Secur32!QuerySecurityPackageInfoW` at `0x140003933`
- `Secur32!QuerySecurityPackageInfoW` at `0x140003933`
- `Secur32!FreeContextBuffer` at `0x140003b21`
- `Secur32!FreeContextBuffer` at `0x140003b21`
- `Secur32!SetCredentialsAttributesW` at `0x140003a09`
- `Secur32!SetCredentialsAttributesW` at `0x140003a09`

## string_xrefs

- `0x140003946`: `QuerySecurityPackageInfoW`
- `0x140003ad7`: `InitializeSecurityContextW`

## pseudocode

```c
__int64 __fastcall GetCloudKerbTicket(SEC_WCHAR *pszTargetName, unsigned __int8 **a2, unsigned int *a3)
{
  const wchar_t *v3; // r9
  unsigned __int8 *v7; // rdi
  unsigned int v8; // ebx
  SECURITY_STATUS v9; // eax
  const wchar_t *v10; // r9
  const wchar_t *v11; // r8
  PSecPkgInfoW v12; // rdx
  unsigned int v13; // r12d
  __int64 v14; // r9
  void *pAuthData; // [rsp+20h] [rbp-99h]
  PSecPkgInfoW ppPackageInfo; // [rsp+60h] [rbp-59h] BYREF
  unsigned int pfContextAttr; // [rsp+68h] [rbp-51h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+70h] [rbp-49h] BYREF
  __int128 v20; // [rsp+78h] [rbp-41h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+88h] [rbp-31h] BYREF
  struct _SecHandle phCredential; // [rsp+98h] [rbp-21h] BYREF
  __int128 pBuffer; // [rsp+A8h] [rbp-11h] BYREF
  unsigned int v24; // [rsp+B8h] [rbp-1h]
  struct _SecHandle phNewContext; // [rsp+C0h] [rbp+7h] BYREF

  v3 = L"<NULL>";
  ppPackageInfo = 0;
  ptsExpiry.QuadPart = 0;
  pfContextAttr = 0;
  v24 = 0;
  if ( pszTargetName )
    v3 = pszTargetName;
  v7 = 0;
  phCredential = 0;
  phNewContext = 0;
  pOutput = 0;
  v20 = 0;
  pBuffer = 0;
  Logger::TraceVerbose(L"%s started. %s: %s.", L"GetCloudKerbTicket", L"SPN", v3);
  if ( !pszTargetName )
  {
    v8 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"GetCloudKerbTicket", L"spn");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"GetCloudKerbTicket", L"spn");
    goto LABEL_27;
  }
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  v9 = QuerySecurityPackageInfoW((LPWSTR)L"Kerberos", &ppPackageInfo);
  v8 = v9;
  if ( v9 < 0 )
  {
    v10 = L"Kerberos";
    v11 = L"QuerySecurityPackageInfoW";
LABEL_11:
    LODWORD(pAuthData) = v9;
    Logger::TraceError(L"%s: %s(%s) failed with error code: 0x%08x.", L"GetCloudKerbTicket", v11, v10, pAuthData);
    goto LABEL_27;
  }
  v12 = ppPackageInfo;
  v13 = 2;
  if ( SLOBYTE(ppPackageInfo->fCapabilities) < 0 )
  {
    Logger::TraceVerbose(L"%s: Kerberos supports extended error", L"GetCloudKerbTicket");
    v12 = ppPackageInfo;
    v13 = 16386;
  }
  v9 = AcquireCredentialsHandleW(0, v12->Name, 0x42u, 0, 0, 0, 0, &phCredential, &ptsExpiry);
  v8 = v9;
  if ( v9 < 0 )
  {
    v10 = L"SECPKG_CRED_OUTBOUND";
    v11 = L"AcquireCredentialsHandleW";
    goto LABEL_11;
  }
  *(_QWORD *)&pBuffer = 0x4000000000000002LL;
  v24 = 0x80000000;
  v9 = SetCredentialsAttributesW(&phCredential, 3u, &pBuffer, 0x14u);
  v8 = v9;
  if ( v9 < 0 )
  {
    v10 = L"SECPKG_CRED_ATTR_KDC_NETWORK_SETTINGS";
    v11 = L"SetCredentialsAttributesW";
    goto LABEL_11;
  }
  v7 = (unsigned __int8 *)SafeAlloc(ppPackageInfo->cbMaxToken);
  if ( v7 )
  {
    pOutput.ulVersion = 0;
    pOutput.pBuffers = (PSecBuffer)&v20;
    pOutput.cBuffers = 1;
    LODWORD(v20) = ppPackageInfo->cbMaxToken;
    DWORD1(v20) = 2;
    *((_QWORD *)&v20 + 1) = v7;
    v9 = InitializeSecurityContextW(
           &phCredential,
           0,
           pszTargetName,
           v13,
           0,
           0x10u,
           0,
           0,
           &phNewContext,
           &pOutput,
           &pfContextAttr,
           &ptsExpiry);
    v8 = v9;
    if ( v9 < 0 )
    {
      v10 = pszTargetName;
      v11 = L"InitializeSecurityContextW";
      goto LABEL_11;
    }
    if ( a2 )
    {
      *a2 = v7;
      v7 = 0;
    }
    v14 = (unsigned int)v20;
    if ( a3 )
      *a3 = v20;
    Logger::TraceVerbose(
      L"%s: Kerberos ticket for SPN \"%s\" acquired. Length: %lu bytes.",
      L"GetCloudKerbTicket",
      pszTargetName,
      v14);
  }
  else
  {
    v8 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"GetCloudKerbTicket");
  }
LABEL_27:
  SafeFree(v7);
  if ( ppPackageInfo )
    FreeContextBuffer(ppPackageInfo);
  FreeCredentialsHandle(&phCredential);
  DeleteSecurityContext(&phNewContext);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"GetCloudKerbTicket", v8);
  return v8;
}

```

## disassembly

```asm
0x140003850  mov     [rsp-8+arg_18], rbx
0x140003855  push    rbp
0x140003856  push    rsi
0x140003857  push    rdi
0x140003858  push    r12
0x14000385a  push    r13
0x14000385c  push    r14
0x14000385e  push    r15
0x140003860  lea     rbp, [rsp-27h]
0x140003865  sub     rsp, 0E0h
0x14000386c  mov     rax, cs:__security_cookie
0x140003873  xor     rax, rsp
0x140003876  mov     [rbp+57h+var_40], rax
0x14000387a  xor     r13d, r13d
0x14000387d  lea     r9, aNull_1; "<NULL>"
0x140003884  xorps   xmm0, xmm0
0x140003887  mov     [rbp+57h+ppPackageInfo], r13
0x14000388b  xor     eax, eax
0x14000388d  mov     qword ptr [rbp+57h+var_A0], r13
0x140003891  test    rcx, rcx
0x140003894  mov     [rbp+57h+var_A8], r13d
0x140003898  xorps   xmm1, xmm1
0x14000389b  mov     [rbp+57h+var_58], eax
0x14000389e  cmovnz  r9, rcx
0x1400038a2  mov     r14, r8
0x1400038a5  mov     rsi, rdx
0x1400038a8  lea     r8, aSpn; "SPN"
0x1400038af  mov     r15, rcx
0x1400038b2  lea     rdx, aGetcloudkerbti; "GetCloudKerbTicket"
0x1400038b9  lea     rcx, aSStartedSS; "%s started. %s: %s."
0x1400038c0  mov     edi, r13d
0x1400038c3  movups  xmmword ptr [rbp+57h+var_78.dwLower], xmm0
0x1400038c7  movups  xmmword ptr [rbp+57h+phNewContext.dwLower], xmm1
0x1400038cb  movups  xmmword ptr [rbp+57h+var_88.ulVersion], xmm0
0x1400038cf  movups  [rbp+57h+var_98], xmm1
0x1400038d3  movups  [rbp+57h+pBuffer], xmm0
0x1400038d7  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1400038dc  test    r15, r15
0x1400038df  jnz     short loc_140003918
0x1400038e1  lea     r8, aSpn_0; "spn"
0x1400038e8  mov     ebx, 80070057h
0x1400038ed  lea     rdx, aGetcloudkerbti; "GetCloudKerbTicket"
0x1400038f4  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1400038fb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x140003900  lea     rdx, aSpn_0; "spn"
0x140003907  lea     rcx, aGetcloudkerbti; "GetCloudKerbTicket"
0x14000390e  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x140003913  jmp     loc_140003B10
0x140003918  test    rsi, rsi
0x14000391b  jz      short loc_140003920
0x14000391d  mov     [rsi], r13
0x140003920  test    r14, r14
0x140003923  jz      short loc_140003928
0x140003925  mov     [r14], r13d
0x140003928  lea     rdx, [rbp+57h+ppPackageInfo]; ppPackageInfo
0x14000392c  lea     rcx, pszPackageName; "Kerberos"
0x140003933  call    cs:__imp_QuerySecurityPackageInfoW
0x140003939  mov     ebx, eax
0x14000393b  test    eax, eax
0x14000393d  jns     short loc_140003969
0x14000393f  lea     r9, pszPackageName; "Kerberos"
0x140003946  lea     r8, aQuerysecurityp; "QuerySecurityPackageInfoW"
0x14000394d  lea     rdx, aGetcloudkerbti; "GetCloudKerbTicket"
0x140003954  mov     dword ptr [rsp+110h+pAuthData], eax
0x140003958  lea     rcx, aSSSFailedWithE; "%s: %s(%s) failed with error code: 0x%0"...
0x14000395f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x140003964  jmp     loc_140003B10
0x140003969  mov     rdx, [rbp+57h+ppPackageInfo]
0x14000396d  mov     r12d, 2
0x140003973  test    byte ptr [rdx], 80h
0x140003976  jz      short loc_140003995
0x140003978  lea     rdx, aGetcloudkerbti; "GetCloudKerbTicket"
0x14000397f  lea     rcx, aSKerberosSuppo; "%s: Kerberos supports extended error"
0x140003986  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x14000398b  mov     rdx, [rbp+57h+ppPackageInfo]
0x14000398f  mov     r12d, 4002h
0x140003995  mov     rdx, [rdx+10h]; pszPackage
0x140003999  lea     rax, [rbp+57h+var_A0]
0x14000399d  mov     [rsp+110h+ptsExpiry], rax; ptsExpiry
0x1400039a2  xor     r9d, r9d; pvLogonId
0x1400039a5  lea     rax, [rbp+57h+var_78]
0x1400039a9  xor     ecx, ecx; pszPrincipal
0x1400039ab  mov     [rsp+110h+phCredential], rax; phCredential
0x1400039b0  mov     [rsp+110h+pvGetKeyArgument], r13; pvGetKeyArgument
0x1400039b5  mov     [rsp+110h+pGetKeyFn], r13; pGetKeyFn
0x1400039ba  lea     r8d, [r9+42h]; fCredentialUse
0x1400039be  mov     [rsp+110h+pAuthData], r13; pAuthData
0x1400039c3  call    cs:__imp_AcquireCredentialsHandleW
0x1400039c9  mov     ebx, eax
0x1400039cb  test    eax, eax
0x1400039cd  jns     short loc_1400039E2
0x1400039cf  lea     r9, aSecpkgCredOutb; "SECPKG_CRED_OUTBOUND"
0x1400039d6  lea     r8, aAcquirecredent; "AcquireCredentialsHandleW"
0x1400039dd  jmp     loc_14000394D
0x1400039e2  mov     r9d, 14h; cbBuffer
0x1400039e8  mov     dword ptr [rbp+57h+pBuffer], 2
0x1400039ef  lea     r8, [rbp+57h+pBuffer]; pBuffer
0x1400039f3  mov     dword ptr [rbp+57h+pBuffer+4], 40000000h
0x1400039fa  lea     rcx, [rbp+57h+var_78]; phCredential
0x1400039fe  mov     [rbp+57h+var_58], 80000000h
0x140003a05  lea     edx, [r9-11h]; ulAttribute
0x140003a09  call    cs:__imp_SetCredentialsAttributesW
0x140003a0f  mov     ebx, eax
0x140003a11  test    eax, eax
0x140003a13  jns     short loc_140003A28
0x140003a15  lea     r9, aSecpkgCredAttr; "SECPKG_CRED_ATTR_KDC_NETWORK_SETTINGS"
0x140003a1c  lea     r8, aSetcredentials; "SetCredentialsAttributesW"
0x140003a23  jmp     loc_14000394D
0x140003a28  mov     rax, [rbp+57h+ppPackageInfo]
0x140003a2c  mov     ecx, [rax+8]; unsigned __int64
0x140003a2f  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x140003a34  mov     rdi, rax
0x140003a37  test    rax, rax
0x140003a3a  jnz     short loc_140003A59
0x140003a3c  lea     rdx, aGetcloudkerbti; "GetCloudKerbTicket"
0x140003a43  mov     ebx, 8007000Eh
0x140003a48  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x140003a4f  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x140003a54  jmp     loc_140003B10
0x140003a59  lea     rax, [rbp+57h+var_98]
0x140003a5d  mov     [rbp+57h+var_88.ulVersion], r13d
0x140003a61  mov     [rbp+57h+var_88.pBuffers], rax
0x140003a65  mov     r9d, r12d; fContextReq
0x140003a68  mov     rax, [rbp+57h+ppPackageInfo]
0x140003a6c  mov     r8, r15; pszTargetName
0x140003a6f  mov     [rbp+57h+var_88.cBuffers], 1
0x140003a76  xor     edx, edx; phContext
0x140003a78  mov     ecx, [rax+8]
0x140003a7b  lea     rax, [rbp+57h+var_A0]
0x140003a7f  mov     [rsp+110h+var_B8], rax; ptsExpiry
0x140003a84  lea     rax, [rbp+57h+var_A8]
0x140003a88  mov     [rsp+110h+pfContextAttr], rax; pfContextAttr
0x140003a8d  lea     rax, [rbp+57h+var_88]
0x140003a91  mov     [rsp+110h+pOutput], rax; pOutput
0x140003a96  lea     rax, [rbp+57h+phNewContext]
0x140003a9a  mov     [rsp+110h+ptsExpiry], rax; phNewContext
0x140003a9f  mov     dword ptr [rsp+110h+phCredential], r13d; Reserved2
0x140003aa4  mov     [rsp+110h+pvGetKeyArgument], r13; pInput
0x140003aa9  mov     dword ptr [rbp+57h+var_98], ecx
0x140003aac  lea     rcx, [rbp+57h+var_78]; phCredential
0x140003ab0  mov     dword ptr [rsp+110h+pGetKeyFn], 10h; TargetDataRep
0x140003ab8  mov     dword ptr [rsp+110h+pAuthData], r13d; Reserved1
0x140003abd  mov     dword ptr [rbp+57h+var_98+4], 2
0x140003ac4  mov     qword ptr [rbp+57h+var_98+8], rdi
0x140003ac8  call    cs:__imp_InitializeSecurityContextW
0x140003ace  mov     ebx, eax
0x140003ad0  test    eax, eax
0x140003ad2  jns     short loc_140003AE3
0x140003ad4  mov     r9, r15
0x140003ad7  lea     r8, aInitializesecu; "InitializeSecurityContextW"
0x140003ade  jmp     loc_14000394D
0x140003ae3  test    rsi, rsi
0x140003ae6  jz      short loc_140003AEE
0x140003ae8  mov     [rsi], rdi
0x140003aeb  mov     rdi, r13
0x140003aee  mov     r9d, dword ptr [rbp+57h+var_98]
0x140003af2  test    r14, r14
0x140003af5  jz      short loc_140003AFA
0x140003af7  mov     [r14], r9d
0x140003afa  mov     r8, r15
0x140003afd  lea     rdx, aGetcloudkerbti; "GetCloudKerbTicket"
0x140003b04  lea     rcx, aSKerberosTicke; "%s: Kerberos ticket for SPN \"%s\" acqu"...
0x140003b0b  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x140003b10  mov     rcx, rdi; void *
0x140003b13  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x140003b18  mov     rcx, [rbp+57h+ppPackageInfo]; pvContextBuffer
0x140003b1c  test    rcx, rcx
0x140003b1f  jz      short loc_140003B27
0x140003b21  call    cs:__imp_FreeContextBuffer
0x140003b27  lea     rcx, [rbp+57h+var_78]; phCredential
0x140003b2b  call    cs:__imp_FreeCredentialsHandle
0x140003b31  lea     rcx, [rbp+57h+phNewContext]; phContext
0x140003b35  call    cs:__imp_DeleteSecurityContext
0x140003b3b  mov     r8d, ebx
0x140003b3e  lea     rdx, aGetcloudkerbti; "GetCloudKerbTicket"
0x140003b45  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x140003b4c  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x140003b51  mov     eax, ebx
0x140003b53  mov     rcx, [rbp+57h+var_40]
0x140003b57  xor     rcx, rsp; StackCookie
0x140003b5a  call    __security_check_cookie
0x140003b5f  mov     rbx, [rsp+110h+arg_18]
0x140003b67  add     rsp, 0E0h
0x140003b6e  pop     r15
0x140003b70  pop     r14
0x140003b72  pop     r13
0x140003b74  pop     r12
0x140003b76  pop     rdi
0x140003b77  pop     rsi
0x140003b78  pop     rbp
0x140003b79  retn
```
