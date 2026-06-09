# LsapLogonUserWithCred(void *,uchar *,ulong,void * *,_LUID *)

- ea: `0x180127bf4`
- end: `0x180127ea5`
- name: `?LsapLogonUserWithCred@@YAJPEAXPEAEKPEAPEAXPEAU_LUID@@@Z`
- size: `689`
- prototype: `int(void *, unsigned __int8 *, unsigned int, void **, struct _LUID *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18012535c`
- `0x180125c28`

## callees

- `0x1800040d0`
- `0x1800284d4`
- `0x18005fecc`
- `0x180060cb0`
- `0x1800b86d0`
- `0x180127bf4`

## import_xrefs

- `ntdll!RtlInitString` at `0x180127c8f`
- `ntdll!RtlInitString` at `0x180127d2f`
- `ntdll!RtlInitString` at `0x180127c8f`
- `ntdll!RtlInitString` at `0x180127d2f`
- `ntdll!NtSetInformationThread` at `0x180127cb0`
- `ntdll!NtSetInformationThread` at `0x180127e36`
- `ntdll!NtSetInformationThread` at `0x180127cb0`
- `ntdll!NtSetInformationThread` at `0x180127e36`
- `SspiCli!LsaConnectUntrusted` at `0x180127ce0`
- `SspiCli!LsaConnectUntrusted` at `0x180127ce0`
- `SspiCli!LsaLogonUser` at `0x180127d9e`
- `SspiCli!LsaLogonUser` at `0x180127d9e`
- `SspiCli!LsaFreeReturnBuffer` at `0x180127e64`
- `SspiCli!LsaFreeReturnBuffer` at `0x180127e64`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180127e08`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180127e08`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180127d09`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180127d09`

## string_xrefs

- `0x180127cc5`: `NtSetInformationThread(Impersonate)`
- `0x180127e4a`: `NtSetInformationThread(Unimpersonate)`
- `0x180127d24`: `LsaConnectBroker`

## pseudocode

```c
__int64 __fastcall LsapLogonUserWithCred(void *a1, unsigned __int8 *a2, ULONG a3, void **a4, struct _LUID *a5)
{
  NTSTATUS v8; // eax
  NTSTATUS v9; // ebx
  char v10; // di
  const char *v11; // rcx
  NTSTATUS v12; // eax
  NTSTATUS v13; // edi
  int SubStatus; // [rsp+70h] [rbp-90h] BYREF
  ULONG AuthenticationPackage; // [rsp+74h] [rbp-8Ch] BYREF
  void *LsaHandle; // [rsp+78h] [rbp-88h] BYREF
  ULONG ProfileBufferLength; // [rsp+80h] [rbp-80h] BYREF
  struct _LUID LogonId; // [rsp+88h] [rbp-78h] BYREF
  PVOID Buffer; // [rsp+90h] [rbp-70h] BYREF
  void *ThreadInformation; // [rsp+98h] [rbp-68h] BYREF
  __int64 v22; // [rsp+A0h] [rbp-60h] BYREF
  struct _STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  struct _STRING v24; // [rsp+B8h] [rbp-48h] BYREF
  struct _TOKEN_SOURCE SourceContext; // [rsp+C8h] [rbp-38h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+D8h] [rbp-28h] BYREF

  ThreadInformation = a1;
  Buffer = 0;
  v24 = 0;
  memset(&Quotas, 0, sizeof(Quotas));
  ProfileBufferLength = 0;
  SubStatus = 0;
  LsaHandle = 0;
  SourceContext = 0;
  LogonId = 0;
  DestinationString = 0;
  AuthenticationPackage = 0;
  CONNECTED_TRACE_ENTER("LsapLogonUserWithCred");
  RtlInitString(&DestinationString, "Negotiate");
  v8 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 0;
    v11 = "NtSetInformationThread(Impersonate)";
LABEL_3:
    CONNECTED_TRACE_ERROR(v11, (unsigned int)v8);
    goto LABEL_16;
  }
  v10 = 1;
  v8 = LsaConnectUntrusted(&LsaHandle);
  v9 = v8;
  if ( v8 < 0 )
  {
    v11 = "LsaConnectUntrusted";
    goto LABEL_3;
  }
  v8 = LsaLookupAuthenticationPackage(LsaHandle, (PLSA_STRING)&DestinationString, &AuthenticationPackage);
  v9 = v8;
  if ( v8 < 0 )
  {
    v11 = "LsaLookupAuthenticationPackage";
    goto LABEL_3;
  }
  RtlInitString(&v24, "LsaConnectBroker");
  v9 = LsaLogonUser(
         LsaHandle,
         (PLSA_STRING)&v24,
         Interactive,
         AuthenticationPackage,
         a2,
         a3,
         0,
         &SourceContext,
         &Buffer,
         &ProfileBufferLength,
         &LogonId,
         a4,
         &Quotas,
         &SubStatus);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        WPP_da3d202165313132ccfab67d2692d0fe_Traceguids,
        (unsigned int)v9,
        SubStatus);
    if ( SubStatus < 0 )
      v9 = SubStatus;
  }
  if ( a5 )
    *a5 = LogonId;
LABEL_16:
  if ( LsaHandle )
    LsaDeregisterLogonProcess(LsaHandle);
  if ( v10 )
  {
    v22 = 0;
    v12 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &v22, 8u);
    v13 = v12;
    if ( v12 < 0 )
    {
      CONNECTED_TRACE_ERROR("NtSetInformationThread(Unimpersonate)", (unsigned int)v12);
      if ( v9 >= 0 )
        v9 = v13;
    }
  }
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  CONNECTED_TRACE_EXIT_EX(1, "LsapLogonUserWithCred", (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180127bf4  push    rbp
0x180127bf6  push    rbx
0x180127bf7  push    rsi
0x180127bf8  push    rdi
0x180127bf9  push    r12
0x180127bfb  push    r14
0x180127bfd  push    r15
0x180127bff  lea     rbp, [rsp-10h]
0x180127c04  sub     rsp, 110h
0x180127c0b  mov     rax, cs:__security_cookie
0x180127c12  xor     rax, rsp
0x180127c15  mov     [rbp+40h+var_38], rax
0x180127c19  mov     rsi, [rbp+40h+arg_20]
0x180127c1d  xorps   xmm0, xmm0
0x180127c20  xorps   xmm1, xmm1
0x180127c23  mov     [rbp+40h+ThreadInformation], rcx
0x180127c27  lea     rcx, aLsaplogonuserw; "LsapLogonUserWithCred"
0x180127c2e  mov     [rbp+40h+Buffer], 0
0x180127c36  movups  xmmword ptr [rbp+40h+var_88.Length], xmm0
0x180127c3a  mov     r12, r9
0x180127c3d  mov     r15d, r8d
0x180127c40  movups  xmmword ptr [rbp+40h+var_68.PagedPoolLimit], xmm1
0x180127c44  mov     r14, rdx
0x180127c47  mov     [rbp+40h+var_C0], 0
0x180127c4e  movups  xmmword ptr [rbp+40h+var_68.MinimumWorkingSetSize], xmm1
0x180127c52  mov     [rsp+140h+var_D0], 0
0x180127c5a  movups  xmmword ptr [rbp+40h+var_68.PagefileLimit], xmm1
0x180127c5e  mov     [rsp+140h+LsaHandle], 0
0x180127c67  movups  xmmword ptr [rbp+40h+var_78.SourceName], xmm0
0x180127c6b  mov     qword ptr [rbp+40h+var_B8.LowPart], 0
0x180127c73  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x180127c77  mov     [rsp+140h+AuthenticationPackage], 0
0x180127c7f  call    CONNECTED_TRACE_ENTER
0x180127c84  lea     rdx, aNegotiate_0; "Negotiate"
0x180127c8b  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x180127c8f  call    cs:__imp_RtlInitString
0x180127c96  nop     dword ptr [rax+rax+00h]
0x180127c9b  mov     r9d, 8; ThreadInformationLength
0x180127ca1  lea     r8, [rbp+40h+ThreadInformation]; ThreadInformation
0x180127ca5  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180127cac  lea     edx, [r9-3]; ThreadInformationClass
0x180127cb0  call    cs:__imp_NtSetInformationThread
0x180127cb7  nop     dword ptr [rax+rax+00h]
0x180127cbc  mov     ebx, eax
0x180127cbe  test    eax, eax
0x180127cc0  jns     short loc_180127CD8
0x180127cc2  xor     dil, dil
0x180127cc5  lea     rcx, aNtsetinformati_0; "NtSetInformationThread(Impersonate)"
0x180127ccc  mov     edx, eax
0x180127cce  call    CONNECTED_TRACE_ERROR
0x180127cd3  jmp     loc_180127DFE
0x180127cd8  lea     rcx, [rsp+140h+LsaHandle]; LsaHandle
0x180127cdd  mov     dil, 1
0x180127ce0  call    cs:__imp_LsaConnectUntrusted
0x180127ce7  nop     dword ptr [rax+rax+00h]
0x180127cec  mov     ebx, eax
0x180127cee  test    eax, eax
0x180127cf0  jns     short loc_180127CFB
0x180127cf2  lea     rcx, aLsaconnectuntr_0; "LsaConnectUntrusted"
0x180127cf9  jmp     short loc_180127CCC
0x180127cfb  mov     rcx, [rsp+140h+LsaHandle]; LsaHandle
0x180127d00  lea     r8, [rsp+140h+AuthenticationPackage]; AuthenticationPackage
0x180127d05  lea     rdx, [rbp+40h+DestinationString]; PackageName
0x180127d09  call    cs:__imp_LsaLookupAuthenticationPackage
0x180127d10  nop     dword ptr [rax+rax+00h]
0x180127d15  mov     ebx, eax
0x180127d17  test    eax, eax
0x180127d19  jns     short loc_180127D24
0x180127d1b  lea     rcx, aLsalookupauthe_0; "LsaLookupAuthenticationPackage"
0x180127d22  jmp     short loc_180127CCC
0x180127d24  lea     rdx, aLsaconnectbrok; "LsaConnectBroker"
0x180127d2b  lea     rcx, [rbp+40h+var_88]; DestinationString
0x180127d2f  call    cs:__imp_RtlInitString
0x180127d36  nop     dword ptr [rax+rax+00h]
0x180127d3b  mov     r9d, [rsp+140h+AuthenticationPackage]; AuthenticationPackage
0x180127d40  lea     rax, [rsp+140h+var_D0]
0x180127d45  mov     rcx, [rsp+140h+LsaHandle]; LsaHandle
0x180127d4a  lea     rdx, [rbp+40h+var_88]; OriginName
0x180127d4e  mov     [rsp+140h+SubStatus], rax; SubStatus
0x180127d53  mov     r8d, 2; LogonType
0x180127d59  lea     rax, [rbp+40h+var_68]
0x180127d5d  mov     [rsp+140h+Quotas], rax; Quotas
0x180127d62  lea     rax, [rbp+40h+var_B8]
0x180127d66  mov     [rsp+140h+Token], r12; Token
0x180127d6b  mov     [rsp+140h+LogonId], rax; LogonId
0x180127d70  lea     rax, [rbp+40h+var_C0]
0x180127d74  mov     [rsp+140h+ProfileBufferLength], rax; ProfileBufferLength
0x180127d79  lea     rax, [rbp+40h+Buffer]
0x180127d7d  mov     [rsp+140h+ProfileBuffer], rax; ProfileBuffer
0x180127d82  lea     rax, [rbp+40h+var_78]
0x180127d86  mov     [rsp+140h+SourceContext], rax; SourceContext
0x180127d8b  mov     [rsp+140h+LocalGroups], 0; LocalGroups
0x180127d94  mov     [rsp+140h+AuthenticationInformationLength], r15d; AuthenticationInformationLength
0x180127d99  mov     [rsp+140h+AuthenticationInformation], r14; AuthenticationInformation
0x180127d9e  call    cs:__imp_LsaLogonUser
0x180127da5  nop     dword ptr [rax+rax+00h]
0x180127daa  mov     ebx, eax
0x180127dac  test    eax, eax
0x180127dae  jns     short loc_180127DF2
0x180127db0  mov     rcx, cs:WPP_GLOBAL_Control
0x180127db7  lea     rax, WPP_GLOBAL_Control
0x180127dbe  cmp     rcx, rax
0x180127dc1  jz      short loc_180127DE9
0x180127dc3  test    [rcx+1Ch], dil
0x180127dc7  jz      short loc_180127DE9
0x180127dc9  mov     eax, [rsp+140h+var_D0]
0x180127dcd  lea     r8, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids
0x180127dd4  mov     rcx, [rcx+10h]
0x180127dd8  mov     edx, 24h ; '$'
0x180127ddd  mov     r9d, ebx
0x180127de0  mov     dword ptr [rsp+140h+AuthenticationInformation], eax
0x180127de4  call    WPP_SF_Dd
0x180127de9  mov     eax, [rsp+140h+var_D0]
0x180127ded  test    eax, eax
0x180127def  cmovs   ebx, eax
0x180127df2  test    rsi, rsi
0x180127df5  jz      short loc_180127DFE
0x180127df7  mov     rax, qword ptr [rbp+40h+var_B8.LowPart]
0x180127dfb  mov     [rsi], rax
0x180127dfe  mov     rcx, [rsp+140h+LsaHandle]; LsaHandle
0x180127e03  test    rcx, rcx
0x180127e06  jz      short loc_180127E14
0x180127e08  call    cs:__imp_LsaDeregisterLogonProcess
0x180127e0f  nop     dword ptr [rax+rax+00h]
0x180127e14  test    dil, dil
0x180127e17  jz      short loc_180127E5B
0x180127e19  mov     r9d, 8; ThreadInformationLength
0x180127e1f  mov     [rbp+40h+var_A0], 0
0x180127e27  lea     r8, [rbp+40h+var_A0]; ThreadInformation
0x180127e2b  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180127e32  lea     edx, [r9-3]; ThreadInformationClass
0x180127e36  call    cs:__imp_NtSetInformationThread
0x180127e3d  nop     dword ptr [rax+rax+00h]
0x180127e42  mov     edi, eax
0x180127e44  test    eax, eax
0x180127e46  jns     short loc_180127E5B
0x180127e48  mov     edx, eax
0x180127e4a  lea     rcx, aNtsetinformati; "NtSetInformationThread(Unimpersonate)"
0x180127e51  call    CONNECTED_TRACE_ERROR
0x180127e56  test    ebx, ebx
0x180127e58  cmovns  ebx, edi
0x180127e5b  mov     rcx, [rbp+40h+Buffer]; Buffer
0x180127e5f  test    rcx, rcx
0x180127e62  jz      short loc_180127E70
0x180127e64  call    cs:__imp_LsaFreeReturnBuffer
0x180127e6b  nop     dword ptr [rax+rax+00h]
0x180127e70  mov     r8d, ebx
0x180127e73  lea     rdx, aLsaplogonuserw; "LsapLogonUserWithCred"
0x180127e7a  mov     ecx, 1
0x180127e7f  call    CONNECTED_TRACE_EXIT_EX
0x180127e84  mov     eax, ebx
0x180127e86  mov     rcx, [rbp+40h+var_38]
0x180127e8a  xor     rcx, rsp; StackCookie
0x180127e8d  call    __security_check_cookie
0x180127e92  add     rsp, 110h
0x180127e99  pop     r15
0x180127e9b  pop     r14
0x180127e9d  pop     r12
0x180127e9f  pop     rdi
0x180127ea0  pop     rsi
0x180127ea1  pop     rbx
0x180127ea2  pop     rbp
0x180127ea3  retn
```
