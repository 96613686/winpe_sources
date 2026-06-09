# PerformLSALogonForConnection(void *,uchar *,ulong,void * *,long *)

- ea: `0x180055acc`
- end: `0x180055ea9`
- name: `?PerformLSALogonForConnection@@YAJPEAXPEAEKPEAPEAXPEAJ@Z`
- size: `989`
- prototype: `int(void *, unsigned __int8 *, unsigned int, void **, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800571b0`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180042410`
- `0x180055acc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055bc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055bc7`
- `USERENV!GetProfileType` at `0x180055bb9`
- `USERENV!GetProfileType` at `0x180055bb9`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180055e0a`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180055e0a`
- `SspiCli!SeciFreeCallContext` at `0x180055dfb`
- `SspiCli!SeciFreeCallContext` at `0x180055dfb`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180055c9a`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180055c9a`
- `SspiCli!SeciAllocateAndSetCallFlags` at `0x180055ce4`
- `SspiCli!SeciAllocateAndSetCallFlags` at `0x180055ce4`
- `SspiCli!LsaFreeReturnBuffer` at `0x180055e81`
- `SspiCli!LsaFreeReturnBuffer` at `0x180055e81`
- `SspiCli!LsaLogonUser` at `0x180055d59`
- `SspiCli!LsaLogonUser` at `0x180055d59`
- `SspiCli!LsaConnectUntrusted` at `0x180055c4d`
- `SspiCli!LsaConnectUntrusted` at `0x180055c4d`
- `ntdll!RtlInitString` at `0x180055b56`
- `ntdll!RtlInitString` at `0x180055cf5`
- `ntdll!RtlInitString` at `0x180055b56`
- `ntdll!RtlInitString` at `0x180055cf5`
- `ntdll!NtSetInformationThread` at `0x180055b6f`
- `ntdll!NtSetInformationThread` at `0x180055e2e`
- `ntdll!NtSetInformationThread` at `0x180055b6f`
- `ntdll!NtSetInformationThread` at `0x180055e2e`

## string_xrefs

- `0x180055b82`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180055bcd`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180055c0d`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180055c59`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180055ca6`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180055d72`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180055dac`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180055e3a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180055b75`: `NtSetInformationThread`
- `0x180055e4e`: `NtSetInformationThread`
- `0x180055cea`: `LsaConnectBroker`

## pseudocode

```c
__int64 __fastcall PerformLSALogonForConnection(void *a1, unsigned __int8 *a2, ULONG a3, void **a4, int *a5)
{
  NTSTATUS v8; // ebx
  char v9; // si
  const char *v10; // r9
  __int64 v11; // r8
  const char *v12; // rax
  __int64 v13; // r8
  const char *v14; // rax
  const char *v15; // r9
  const char *v16; // r9
  const char *v17; // rax
  __int64 v18; // r8
  bool v19; // sf
  const char *v20; // r9
  NTSTATUS v21; // esi
  const char *v22; // rax
  PVOID AuthenticationInformation; // [rsp+20h] [rbp-E0h]
  PVOID AuthenticationInformationa; // [rsp+20h] [rbp-E0h]
  int SubStatus; // [rsp+70h] [rbp-90h] BYREF
  ULONG AuthenticationPackage; // [rsp+74h] [rbp-8Ch] BYREF
  int v28; // [rsp+78h] [rbp-88h] BYREF
  void *LsaHandle; // [rsp+80h] [rbp-80h] BYREF
  DWORD dwFlags; // [rsp+88h] [rbp-78h] BYREF
  ULONG ProfileBufferLength; // [rsp+8Ch] [rbp-74h] BYREF
  PVOID Buffer; // [rsp+90h] [rbp-70h] BYREF
  void *ThreadInformation; // [rsp+98h] [rbp-68h] BYREF
  struct _LUID LogonId; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-58h] BYREF
  struct _STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  struct _STRING v37; // [rsp+C0h] [rbp-40h] BYREF
  struct _TOKEN_SOURCE SourceContext; // [rsp+D0h] [rbp-30h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+E0h] [rbp-20h] BYREF

  ThreadInformation = a1;
  SubStatus = 0;
  dwFlags = 0;
  Buffer = 0;
  ProfileBufferLength = 0;
  v37 = 0;
  LsaHandle = 0;
  memset(&Quotas, 0, sizeof(Quotas));
  LogonId = 0;
  AuthenticationPackage = 0;
  v28 = 0;
  SourceContext = 0;
  DestinationString = 0;
  RtlInitString(&DestinationString, "Negotiate");
  *a4 = 0;
  v8 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  if ( v8 )
  {
    v9 = 0;
    v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v8, v10, 9294, v11, &Class);
  }
  else
  {
    v9 = 1;
    if ( !GetProfileType(&dwFlags) )
    {
      GetLastError();
      v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v12, 9302, "GetProfileType", &Class);
      v8 = -1073282572;
      v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(AuthenticationInformationa) = 9304;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221684724LL, v14, AuthenticationInformationa, "GetProfileType", &Class);
      goto LABEL_16;
    }
    v8 = LsaConnectUntrusted(&LsaHandle);
    if ( v8 )
    {
      v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v8, v15, 9308, "LsaConnectUntrusted", &Class);
    }
    else
    {
      v8 = LsaLookupAuthenticationPackage(LsaHandle, (PLSA_STRING)&DestinationString, &AuthenticationPackage);
      if ( v8 )
      {
        v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v8, v16, 9314, "LsaLookupAuthenticationPackage", &Class);
      }
      else
      {
        SeciAllocateAndSetCallFlags(0x4000, &v28);
        RtlInitString(&v37, "LsaConnectBroker");
        v8 = LsaLogonUser(
               LsaHandle,
               (PLSA_STRING)&v37,
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
        if ( SubStatus )
        {
          v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(AuthenticationInformation) = 9338;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            v18,
            v17,
            AuthenticationInformation,
            "LsaLogonUser(subStatus)",
            &Class);
        }
        v19 = v8 < 0;
        if ( !v8 )
          goto LABEL_14;
        v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(AuthenticationInformation) = 9339;
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          (unsigned int)v8,
          v20,
          AuthenticationInformation,
          "LsaLogonUser(status)",
          &Class);
      }
    }
  }
  v19 = v8 < 0;
LABEL_14:
  if ( !v19 )
    v8 = SubStatus;
LABEL_16:
  *a5 = SubStatus;
  if ( v28 )
    SeciFreeCallContext();
  if ( LsaHandle )
    LsaDeregisterLogonProcess(LsaHandle);
  if ( v9 )
  {
    v35 = 0;
    v21 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &v35, 8u);
    if ( v21 < 0 )
    {
      v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(AuthenticationInformation) = 9369;
      WPPTraceLogA(
        0,
        "0x%08x %s:%u : %s:%ws",
        (unsigned int)v21,
        v22,
        AuthenticationInformation,
        "NtSetInformationThread",
        &Class);
      if ( v8 >= 0 )
        v8 = v21;
    }
  }
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180055acc  push    rbp
0x180055ace  push    rbx
0x180055acf  push    rsi
0x180055ad0  push    rdi
0x180055ad1  push    r12
0x180055ad3  push    r13
0x180055ad5  push    r14
0x180055ad7  push    r15
0x180055ad9  lea     rbp, [rsp-28h]
0x180055ade  sub     rsp, 128h
0x180055ae5  mov     rax, cs:__security_cookie
0x180055aec  xor     rax, rsp
0x180055aef  mov     [rbp+60h+var_50], rax
0x180055af3  mov     r12, [rbp+60h+arg_20]
0x180055afa  xor     r13d, r13d
0x180055afd  xorps   xmm0, xmm0
0x180055b00  mov     [rbp+60h+ThreadInformation], rcx
0x180055b04  xorps   xmm1, xmm1
0x180055b07  mov     [rsp+160h+var_F0], r13d
0x180055b0c  mov     r14, rdx
0x180055b0f  mov     [rbp+60h+dwFlags], r13d
0x180055b13  lea     rdx, aNegotiate_0; "Negotiate"
0x180055b1a  mov     [rbp+60h+Buffer], r13
0x180055b1e  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x180055b22  mov     [rbp+60h+var_D4], r13d
0x180055b26  movups  xmmword ptr [rbp+60h+var_A0.Length], xmm0
0x180055b2a  mov     [rbp+60h+LsaHandle], r13
0x180055b2e  mov     rdi, r9
0x180055b31  movups  xmmword ptr [rbp+60h+var_80.PagedPoolLimit], xmm1
0x180055b35  mov     qword ptr [rbp+60h+var_C0.LowPart], r13
0x180055b39  mov     r15d, r8d
0x180055b3c  movups  xmmword ptr [rbp+60h+var_80.MinimumWorkingSetSize], xmm1
0x180055b40  mov     [rsp+160h+AuthenticationPackage], r13d
0x180055b45  movups  xmmword ptr [rbp+60h+var_80.PagefileLimit], xmm1
0x180055b49  mov     [rsp+160h+var_E8], r13d
0x180055b4e  movups  xmmword ptr [rbp+60h+var_90.SourceName], xmm0
0x180055b52  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x180055b56  call    cs:__imp_RtlInitString
0x180055b5c  lea     r9d, [r13+8]; ThreadInformationLength
0x180055b60  mov     [rdi], r13
0x180055b63  lea     r8, [rbp+60h+ThreadInformation]; ThreadInformation
0x180055b67  lea     edx, [r13+5]; ThreadInformationClass
0x180055b6b  lea     rcx, [r13-2]; ThreadHandle
0x180055b6f  call    cs:__imp_NtSetInformationThread
0x180055b75  lea     r8, aNtsetinformati; "NtSetInformationThread"
0x180055b7c  mov     ebx, eax
0x180055b7e  test    eax, eax
0x180055b80  jz      short loc_180055BB2
0x180055b82  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180055b89  mov     sil, r13b
0x180055b8c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180055b91  lea     rdi, Class
0x180055b98  mov     r9, rax
0x180055b9b  mov     [rsp+160h+LocalGroups], rdi
0x180055ba0  mov     qword ptr [rsp+160h+AuthenticationInformationLength], r8
0x180055ba5  mov     dword ptr [rsp+160h+AuthenticationInformation], 244Eh
0x180055bad  jmp     loc_180055DD4
0x180055bb2  lea     rcx, [rbp+60h+dwFlags]; dwFlags
0x180055bb6  mov     sil, 1
0x180055bb9  call    cs:__imp_GetProfileType
0x180055bbf  test    eax, eax
0x180055bc1  jnz     loc_180055C49
0x180055bc7  call    cs:__imp_GetLastError
0x180055bcd  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180055bd4  mov     r8d, eax
0x180055bd7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180055bdc  lea     rdi, Class
0x180055be3  mov     r9, rax
0x180055be6  mov     [rsp+160h+LocalGroups], rdi
0x180055beb  lea     r14, aGetprofiletype; "GetProfileType"
0x180055bf2  mov     qword ptr [rsp+160h+AuthenticationInformationLength], r14
0x180055bf7  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180055bfe  xor     ecx, ecx
0x180055c00  mov     dword ptr [rsp+160h+AuthenticationInformation], 2456h
0x180055c08  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180055c0d  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180055c14  mov     ebx, 0C00701F4h
0x180055c19  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180055c1e  mov     [rsp+160h+LocalGroups], rdi
0x180055c23  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180055c2a  mov     r9, rax
0x180055c2d  mov     qword ptr [rsp+160h+AuthenticationInformationLength], r14
0x180055c32  mov     r8d, ebx
0x180055c35  mov     dword ptr [rsp+160h+AuthenticationInformation], 2458h
0x180055c3d  xor     ecx, ecx
0x180055c3f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180055c44  jmp     loc_180055DEC
0x180055c49  lea     rcx, [rbp+60h+LsaHandle]; LsaHandle
0x180055c4d  call    cs:__imp_LsaConnectUntrusted
0x180055c53  mov     ebx, eax
0x180055c55  test    eax, eax
0x180055c57  jz      short loc_180055C8D
0x180055c59  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180055c60  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180055c65  mov     r9, rax
0x180055c68  lea     rdi, Class
0x180055c6f  mov     [rsp+160h+LocalGroups], rdi
0x180055c74  lea     rax, aLsaconnectuntr; "LsaConnectUntrusted"
0x180055c7b  mov     qword ptr [rsp+160h+AuthenticationInformationLength], rax
0x180055c80  mov     dword ptr [rsp+160h+AuthenticationInformation], 245Ch
0x180055c88  jmp     loc_180055DD4
0x180055c8d  mov     rcx, [rbp+60h+LsaHandle]; LsaHandle
0x180055c91  lea     r8, [rsp+160h+AuthenticationPackage]; AuthenticationPackage
0x180055c96  lea     rdx, [rbp+60h+DestinationString]; PackageName
0x180055c9a  call    cs:__imp_LsaLookupAuthenticationPackage
0x180055ca0  mov     ebx, eax
0x180055ca2  test    eax, eax
0x180055ca4  jz      short loc_180055CDA
0x180055ca6  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180055cad  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180055cb2  mov     r9, rax
0x180055cb5  lea     rdi, Class
0x180055cbc  mov     [rsp+160h+LocalGroups], rdi
0x180055cc1  lea     rax, aLsalookupauthe; "LsaLookupAuthenticationPackage"
0x180055cc8  mov     qword ptr [rsp+160h+AuthenticationInformationLength], rax
0x180055ccd  mov     dword ptr [rsp+160h+AuthenticationInformation], 2462h
0x180055cd5  jmp     loc_180055DD4
0x180055cda  lea     rdx, [rsp+160h+var_E8]
0x180055cdf  mov     ecx, 4000h
0x180055ce4  call    cs:__imp_SeciAllocateAndSetCallFlags
0x180055cea  lea     rdx, aLsaconnectbrok; "LsaConnectBroker"
0x180055cf1  lea     rcx, [rbp+60h+var_A0]; DestinationString
0x180055cf5  call    cs:__imp_RtlInitString
0x180055cfb  mov     r9d, [rsp+160h+AuthenticationPackage]; AuthenticationPackage
0x180055d00  lea     rax, [rsp+160h+var_F0]
0x180055d05  mov     rcx, [rbp+60h+LsaHandle]; LsaHandle
0x180055d09  lea     rdx, [rbp+60h+var_A0]; OriginName
0x180055d0d  mov     [rsp+160h+SubStatus], rax; SubStatus
0x180055d12  mov     r8d, 2; LogonType
0x180055d18  lea     rax, [rbp+60h+var_80]
0x180055d1c  mov     [rsp+160h+Quotas], rax; Quotas
0x180055d21  lea     rax, [rbp+60h+var_C0]
0x180055d25  mov     [rsp+160h+Token], rdi; Token
0x180055d2a  mov     [rsp+160h+LogonId], rax; LogonId
0x180055d2f  lea     rax, [rbp+60h+var_D4]
0x180055d33  mov     [rsp+160h+ProfileBufferLength], rax; ProfileBufferLength
0x180055d38  lea     rax, [rbp+60h+Buffer]
0x180055d3c  mov     [rsp+160h+ProfileBuffer], rax; ProfileBuffer
0x180055d41  lea     rax, [rbp+60h+var_90]
0x180055d45  mov     [rsp+160h+SourceContext], rax; SourceContext
0x180055d4a  mov     [rsp+160h+LocalGroups], r13; LocalGroups
0x180055d4f  mov     [rsp+160h+AuthenticationInformationLength], r15d; AuthenticationInformationLength
0x180055d54  mov     [rsp+160h+AuthenticationInformation], r14; AuthenticationInformation
0x180055d59  call    cs:__imp_LsaLogonUser
0x180055d5f  mov     r8d, [rsp+160h+var_F0]
0x180055d64  lea     rdi, Class
0x180055d6b  mov     ebx, eax
0x180055d6d  test    r8d, r8d
0x180055d70  jz      short loc_180055DA8
0x180055d72  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180055d79  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180055d7e  lea     rcx, aLsalogonuserSu; "LsaLogonUser(subStatus)"
0x180055d85  mov     [rsp+160h+LocalGroups], rdi
0x180055d8a  mov     qword ptr [rsp+160h+AuthenticationInformationLength], rcx
0x180055d8f  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180055d96  xor     ecx, ecx
0x180055d98  mov     dword ptr [rsp+160h+AuthenticationInformation], 247Ah
0x180055da0  mov     r9, rax
0x180055da3  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180055da8  test    ebx, ebx
0x180055daa  jz      short loc_180055DE7
0x180055dac  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180055db3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180055db8  mov     [rsp+160h+LocalGroups], rdi
0x180055dbd  mov     r9, rax
0x180055dc0  lea     rax, aLsalogonuserSt; "LsaLogonUser(status)"
0x180055dc7  mov     qword ptr [rsp+160h+AuthenticationInformationLength], rax
0x180055dcc  mov     dword ptr [rsp+160h+AuthenticationInformation], 247Bh
0x180055dd4  mov     r8d, ebx
0x180055dd7  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180055dde  xor     ecx, ecx
0x180055de0  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180055de5  test    ebx, ebx
0x180055de7  cmovns  ebx, [rsp+160h+var_F0]
0x180055dec  mov     eax, [rsp+160h+var_F0]
0x180055df0  mov     [r12], eax
0x180055df4  cmp     [rsp+160h+var_E8], r13d
0x180055df9  jz      short loc_180055E01
0x180055dfb  call    cs:__imp_SeciFreeCallContext
0x180055e01  mov     rcx, [rbp+60h+LsaHandle]; LsaHandle
0x180055e05  test    rcx, rcx
0x180055e08  jz      short loc_180055E10
0x180055e0a  call    cs:__imp_LsaDeregisterLogonProcess
0x180055e10  test    sil, sil
0x180055e13  jz      short loc_180055E78
0x180055e15  mov     r9d, 8; ThreadInformationLength
0x180055e1b  mov     [rbp+60h+var_B8], r13
0x180055e1f  lea     r8, [rbp+60h+var_B8]; ThreadInformation
0x180055e23  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180055e2a  lea     edx, [r9-3]; ThreadInformationClass
0x180055e2e  call    cs:__imp_NtSetInformationThread
0x180055e34  mov     esi, eax
0x180055e36  test    eax, eax
0x180055e38  jns     short loc_180055E78
0x180055e3a  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180055e41  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180055e46  mov     r9, rax
0x180055e49  mov     [rsp+160h+LocalGroups], rdi
0x180055e4e  lea     rax, aNtsetinformati; "NtSetInformationThread"
0x180055e55  mov     r8d, esi
0x180055e58  mov     qword ptr [rsp+160h+AuthenticationInformationLength], rax
0x180055e5d  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180055e64  xor     ecx, ecx
0x180055e66  mov     dword ptr [rsp+160h+AuthenticationInformation], 2499h
0x180055e6e  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180055e73  test    ebx, ebx
0x180055e75  cmovns  ebx, esi
0x180055e78  mov     rcx, [rbp+60h+Buffer]; Buffer
0x180055e7c  test    rcx, rcx
0x180055e7f  jz      short loc_180055E87
0x180055e81  call    cs:__imp_LsaFreeReturnBuffer
0x180055e87  mov     eax, ebx
0x180055e89  mov     rcx, [rbp+60h+var_50]
0x180055e8d  xor     rcx, rsp; StackCookie
0x180055e90  call    __security_check_cookie
0x180055e95  add     rsp, 128h
0x180055e9c  pop     r15
0x180055e9e  pop     r14
0x180055ea0  pop     r13
0x180055ea2  pop     r12
0x180055ea4  pop     rdi
0x180055ea5  pop     rsi
0x180055ea6  pop     rbx
0x180055ea7  pop     rbp
0x180055ea8  retn
```
