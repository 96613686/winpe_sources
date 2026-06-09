# LsapAuApiDispatchLogonSystemManagedAdmin(_LUID,void * *)

- ea: `0x1800efdec`
- end: `0x1800f029c`
- name: `?LsapAuApiDispatchLogonSystemManagedAdmin@@YAJU_LUID@@PEAPEAX@Z`
- size: `1200`
- prototype: `int(struct _LUID, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800ddef0`

## callees

- `0x1800093b0`
- `0x180009410`
- `0x180024750`
- `0x1800b86d0`
- `0x1800efdec`
- `0x1800f579c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f012e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f012e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f0220`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f0220`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800eff0f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800eff0f`
- `ntdll!RtlSubAuthoritySid` at `0x1800eff67`
- `ntdll!RtlSubAuthoritySid` at `0x1800eff88`
- `ntdll!RtlSubAuthoritySid` at `0x1800effa5`
- `ntdll!RtlSubAuthoritySid` at `0x1800effdc`
- `ntdll!RtlSubAuthoritySid` at `0x1800eff67`
- `ntdll!RtlSubAuthoritySid` at `0x1800eff88`
- `ntdll!RtlSubAuthoritySid` at `0x1800effa5`
- `ntdll!RtlSubAuthoritySid` at `0x1800effdc`
- `ntdll!NtClose` at `0x1800f0266`
- `ntdll!NtClose` at `0x1800f0266`
- `ntdll!RtlInitializeSid` at `0x1800eff56`
- `ntdll!RtlInitializeSid` at `0x1800effcb`
- `ntdll!RtlInitializeSid` at `0x1800eff56`
- `ntdll!RtlInitializeSid` at `0x1800effcb`
- `ntdll!RtlLengthRequiredSid` at `0x1800efeea`
- `ntdll!RtlLengthRequiredSid` at `0x1800efefb`
- `ntdll!RtlLengthRequiredSid` at `0x1800eff33`
- `ntdll!RtlLengthRequiredSid` at `0x1800efeea`
- `ntdll!RtlLengthRequiredSid` at `0x1800efefb`
- `ntdll!RtlLengthRequiredSid` at `0x1800eff33`
- `ntdll!RtlInitString` at `0x1800f0005`
- `ntdll!RtlInitString` at `0x1800f003f`
- `ntdll!RtlInitString` at `0x1800f0005`
- `ntdll!RtlInitString` at `0x1800f003f`
- `ntdll!NtQueryInformationToken` at `0x1800f0161`
- `ntdll!NtQueryInformationToken` at `0x1800f0161`
- `SspiCli!LogonUserExExW` at `0x1800f011e`
- `SspiCli!LogonUserExExW` at `0x1800f011e`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800f0250`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800f0250`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800f00ae`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800f01ec`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800f00ae`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800f01ec`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800f0059`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800f0059`
- `SspiCli!LsaRegisterLogonProcess` at `0x1800f001e`
- `SspiCli!LsaRegisterLogonProcess` at `0x1800f001e`
- `SAMLIB!SamFreeMemory` at `0x1800f01fc`
- `SAMLIB!SamFreeMemory` at `0x1800f020c`
- `SAMLIB!SamFreeMemory` at `0x1800f01fc`
- `SAMLIB!SamFreeMemory` at `0x1800f020c`
- `SAMLIB!SamiFindOrCreateShadowAdminAccount` at `0x1800efecd`
- `SAMLIB!SamiFindOrCreateShadowAdminAccount` at `0x1800efecd`

## pseudocode

```c
__int64 __fastcall LsapAuApiDispatchLogonSystemManagedAdmin(struct _LUID a1, void **a2)
{
  struct _LSAP_LOGON_SESSION *LogonSession; // r15
  _QWORD *v4; // r12
  struct _LSAP_LOGON_SESSION *v5; // r14
  NTSTATUS updated; // ebx
  struct _LSAP_LOGON_SESSION *v7; // rax
  ULONG v8; // ebx
  ULONG v9; // eax
  char *v10; // rax
  char *v11; // rdi
  ULONG v12; // eax
  char *v13; // rsi
  ULONG v14; // ebx
  ULONG v15; // ebx
  int ProtocolStatus; // [rsp+60h] [rbp-A0h] BYREF
  ULONG AuthenticationPackage; // [rsp+64h] [rbp-9Ch] BYREF
  ULONG ReturnBufferLength; // [rsp+68h] [rbp-98h] BYREF
  void *LsaHandle; // [rsp+70h] [rbp-90h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp-88h] BYREF
  ULONG SecurityMode; // [rsp+80h] [rbp-80h] BYREF
  ULONG ReturnLength; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v24; // [rsp+88h] [rbp-78h] BYREF
  PVOID ProtocolReturnBuffer; // [rsp+90h] [rbp-70h] BYREF
  __int64 v26; // [rsp+98h] [rbp-68h] BYREF
  struct _STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  struct _LUID v28; // [rsp+B0h] [rbp-50h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+B8h] [rbp-48h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v30; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD ProtocolSubmitBuffer[2]; // [rsp+C8h] [rbp-38h] BYREF
  _OWORD TokenInformation[3]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v33; // [rsp+108h] [rbp+8h]

  v28 = a1;
  v24 = 0;
  v26 = 0;
  LogonSession = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v4 = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)v30.Value = 0;
  *(_WORD *)&v30.Value[4] = 512;
  ProtocolStatus = 0;
  AuthenticationPackage = 0;
  ReturnBufferLength = 0;
  ProtocolReturnBuffer = 0;
  LsaHandle = 0;
  SecurityMode = 0;
  TokenHandle = 0;
  ReturnLength = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v33 = 0;
  memset(ProtocolSubmitBuffer, 0, 12);
  DestinationString = 0;
  if ( !LsapShadowAdminEnabled )
  {
    v5 = 0;
LABEL_3:
    updated = -1073741637;
    goto LABEL_25;
  }
  v7 = LsapLocateLogonSession(&v28);
  v5 = v7;
  if ( v7 )
  {
    if ( !*((_QWORD *)v7 + 17) )
      goto LABEL_3;
    updated = SamiFindOrCreateShadowAdminAccount(*((_QWORD *)v7 + 28), &v24, &v26);
    if ( updated >= 0 )
    {
      v8 = RtlLengthRequiredSid(3u);
      v9 = RtlLengthRequiredSid(1u);
      v10 = (char *)LocalAlloc(0x40u, v8 + v9 + 40);
      v4 = v10;
      if ( v10 )
      {
        v11 = v10 + 40;
        v12 = RtlLengthRequiredSid(3u);
        *(_DWORD *)v4 = 2;
        v13 = &v11[v12];
        RtlInitializeSid(v11, &IdentifierAuthority, 3u);
        *RtlSubAuthoritySid(v11, 0) = 5;
        v14 = *((_DWORD *)v5 + 35);
        *RtlSubAuthoritySid(v11, 1u) = v14;
        v15 = *((_DWORD *)v5 + 34);
        *RtlSubAuthoritySid(v11, 2u) = v15;
        v4[1] = v11;
        *((_DWORD *)v4 + 4) = -1073741817;
        RtlInitializeSid(v13, &v30, 1u);
        *RtlSubAuthoritySid(v13, 0) = 0;
        v4[3] = v13;
        *((_DWORD *)v4 + 8) = 7;
        RtlInitString(&DestinationString, "SystemManagedAdminLogon");
        updated = LsaRegisterLogonProcess((PLSA_STRING)&DestinationString, &LsaHandle, &SecurityMode);
        if ( updated >= 0 )
        {
          RtlInitString(&DestinationString, "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0");
          updated = LsaLookupAuthenticationPackage(LsaHandle, (PLSA_STRING)&DestinationString, &AuthenticationPackage);
          if ( updated >= 0 )
          {
            *(_QWORD *)((char *)ProtocolSubmitBuffer + 4) = 3;
            LODWORD(ProtocolSubmitBuffer[0]) = 19;
            updated = LsaCallAuthenticationPackage(
                        LsaHandle,
                        AuthenticationPackage,
                        ProtocolSubmitBuffer,
                        0xCu,
                        &ProtocolReturnBuffer,
                        &ReturnBufferLength,
                        &ProtocolStatus);
            if ( updated >= 0 )
            {
              updated = ProtocolStatus;
              if ( ProtocolStatus >= 0 )
              {
                updated = LsapUpdateShadowAdminLogonAllowedList(1u);
                if ( updated >= 0 )
                {
                  if ( (unsigned int)LogonUserExExW(
                                       v24,
                                       L".",
                                       &cchOriginalDestLength,
                                       2,
                                       0,
                                       v4,
                                       &TokenHandle,
                                       0,
                                       0,
                                       0,
                                       0)
                    || !GetLastError() )
                  {
                    updated = NtQueryInformationToken(
                                TokenHandle,
                                TokenStatistics,
                                TokenInformation,
                                0x38u,
                                &ReturnLength);
                    if ( updated >= 0 )
                    {
                      LogonSession = LsapLocateLogonSession((struct _LUID *)TokenInformation + 1);
                      if ( LogonSession )
                      {
                        updated = LsapDuplicateHandle(TokenHandle, a2);
                        if ( updated >= 0 )
                        {
                          *((_DWORD *)LogonSession + 62) = *((_DWORD *)v5 + 62);
                          *((_QWORD *)LogonSession + 15) = *((_QWORD *)v5 + 14);
                        }
                      }
                      else
                      {
                        updated = -1073741729;
                      }
                    }
                  }
                  else
                  {
                    updated = -1073741637;
                  }
                  LsapUpdateShadowAdminLogonAllowedList(0);
                }
                BYTE1(ProtocolSubmitBuffer[1]) = 1;
                LsaCallAuthenticationPackage(
                  LsaHandle,
                  AuthenticationPackage,
                  ProtocolSubmitBuffer,
                  0xCu,
                  &ProtocolReturnBuffer,
                  &ReturnBufferLength,
                  &ProtocolStatus);
              }
            }
          }
        }
      }
      else
      {
        updated = -1073741801;
      }
    }
  }
  else
  {
    updated = -1073741729;
  }
LABEL_25:
  SamFreeMemory(v24);
  SamFreeMemory(v26);
  if ( v4 )
    LocalFree(v4);
  if ( v5 )
    LsapReleaseLogonSession(v5);
  if ( LogonSession )
    LsapReleaseLogonSession(LogonSession);
  if ( LsaHandle )
    LsaDeregisterLogonProcess(LsaHandle);
  if ( TokenHandle )
    NtClose(TokenHandle);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800efdec  mov     [rsp-8+arg_10], rbx
0x1800efdf1  push    rbp
0x1800efdf2  push    rsi
0x1800efdf3  push    rdi
0x1800efdf4  push    r12
0x1800efdf6  push    r13
0x1800efdf8  push    r14
0x1800efdfa  push    r15
0x1800efdfc  lea     rbp, [rsp-20h]
0x1800efe01  sub     rsp, 120h
0x1800efe08  mov     rax, cs:__security_cookie
0x1800efe0f  xor     rax, rsp
0x1800efe12  mov     [rbp+50h+var_40], rax
0x1800efe16  xor     edi, edi
0x1800efe18  mov     qword ptr [rbp+50h+var_A0.LowPart], rcx
0x1800efe1c  xor     eax, eax
0x1800efe1e  mov     [rbp+50h+var_C8], rdi
0x1800efe22  cmp     cs:?LsapShadowAdminEnabled@@3HA, edi; int LsapShadowAdminEnabled
0x1800efe28  xorps   xmm0, xmm0
0x1800efe2b  mov     r13, rdx
0x1800efe2e  mov     [rbp+50h+var_B8], rdi
0x1800efe32  mov     r15d, edi
0x1800efe35  mov     dword ptr [rbp+50h+IdentifierAuthority.Value], edi
0x1800efe38  mov     r12d, edi
0x1800efe3b  mov     word ptr [rbp+50h+IdentifierAuthority.Value+4], 500h
0x1800efe41  mov     dword ptr [rbp+50h+var_90.Value], edi
0x1800efe44  mov     word ptr [rbp+50h+var_90.Value+4], 200h
0x1800efe4a  mov     [rsp+150h+var_F0], edi
0x1800efe4e  mov     [rsp+150h+AuthenticationPackage], edi
0x1800efe52  mov     [rsp+150h+var_E8], edi
0x1800efe56  mov     [rbp+50h+var_C0], rdi
0x1800efe5a  mov     [rsp+150h+LsaHandle], rdi
0x1800efe5f  mov     [rbp+50h+SecurityMode], edi
0x1800efe62  mov     [rsp+150h+TokenHandle], rdi
0x1800efe67  mov     [rbp+50h+ReturnLength], edi
0x1800efe6a  movups  [rbp+50h+TokenInformation], xmm0
0x1800efe6e  mov     [rbp+50h+var_48], rax
0x1800efe72  movups  [rbp+50h+var_68], xmm0
0x1800efe76  mov     [rbp+50h+ProtocolSubmitBuffer], rax
0x1800efe7a  movups  [rbp+50h+var_58], xmm0
0x1800efe7e  mov     [rbp+50h+var_80], eax
0x1800efe81  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm0
0x1800efe85  jnz     short loc_1800EFE94
0x1800efe87  mov     r14d, edi
0x1800efe8a  mov     ebx, 0C00000BBh
0x1800efe8f  jmp     loc_1800F01F8
0x1800efe94  lea     rcx, [rbp+50h+var_A0]; struct _LUID *
0x1800efe98  call    ?LsapLocateLogonSession@@YAPEAU_LSAP_LOGON_SESSION@@PEAU_LUID@@@Z; LsapLocateLogonSession(_LUID *)
0x1800efe9d  mov     r14, rax
0x1800efea0  test    rax, rax
0x1800efea3  jnz     short loc_1800EFEAF
0x1800efea5  mov     ebx, 0C000005Fh
0x1800efeaa  jmp     loc_1800F01F8
0x1800efeaf  mov     eax, [rax+88h]
0x1800efeb5  or      eax, [r14+8Ch]
0x1800efebc  jz      short loc_1800EFE8A
0x1800efebe  mov     rcx, [r14+0E0h]
0x1800efec5  lea     r8, [rbp+50h+var_B8]
0x1800efec9  lea     rdx, [rbp+50h+var_C8]
0x1800efecd  call    cs:__imp_SamiFindOrCreateShadowAdminAccount
0x1800efed4  nop     dword ptr [rax+rax+00h]
0x1800efed9  mov     ebx, eax
0x1800efedb  test    eax, eax
0x1800efedd  js      loc_1800F01F8
0x1800efee3  mov     esi, 3
0x1800efee8  mov     ecx, esi; SubAuthorityCount
0x1800efeea  call    cs:__imp_RtlLengthRequiredSid
0x1800efef1  nop     dword ptr [rax+rax+00h]
0x1800efef6  lea     ecx, [rsi-2]; SubAuthorityCount
0x1800efef9  mov     ebx, eax
0x1800efefb  call    cs:__imp_RtlLengthRequiredSid
0x1800eff02  nop     dword ptr [rax+rax+00h]
0x1800eff07  lea     ecx, [rsi+3Dh]; uFlags
0x1800eff0a  lea     edx, [rax+28h]
0x1800eff0d  add     edx, ebx; uBytes
0x1800eff0f  call    cs:__imp_LocalAlloc
0x1800eff16  nop     dword ptr [rax+rax+00h]
0x1800eff1b  mov     r12, rax
0x1800eff1e  test    rax, rax
0x1800eff21  jnz     short loc_1800EFF2D
0x1800eff23  mov     ebx, 0C0000017h
0x1800eff28  jmp     loc_1800F01F8
0x1800eff2d  mov     ecx, esi; SubAuthorityCount
0x1800eff2f  lea     rdi, [rax+28h]
0x1800eff33  call    cs:__imp_RtlLengthRequiredSid
0x1800eff3a  nop     dword ptr [rax+rax+00h]
0x1800eff3f  mov     r8b, 3; SubAuthorityCount
0x1800eff42  mov     dword ptr [r12], 2
0x1800eff4a  mov     esi, eax
0x1800eff4c  lea     rdx, [rbp+50h+IdentifierAuthority]; IdentifierAuthority
0x1800eff50  mov     rcx, rdi; Sid
0x1800eff53  add     rsi, rdi
0x1800eff56  call    cs:__imp_RtlInitializeSid
0x1800eff5d  nop     dword ptr [rax+rax+00h]
0x1800eff62  xor     edx, edx; SubAuthority
0x1800eff64  mov     rcx, rdi; Sid
0x1800eff67  call    cs:__imp_RtlSubAuthoritySid
0x1800eff6e  nop     dword ptr [rax+rax+00h]
0x1800eff73  mov     edx, 1; SubAuthority
0x1800eff78  mov     rcx, rdi; Sid
0x1800eff7b  mov     dword ptr [rax], 5
0x1800eff81  mov     ebx, [r14+8Ch]
0x1800eff88  call    cs:__imp_RtlSubAuthoritySid
0x1800eff8f  nop     dword ptr [rax+rax+00h]
0x1800eff94  mov     edx, 2; SubAuthority
0x1800eff99  mov     rcx, rdi; Sid
0x1800eff9c  mov     [rax], ebx
0x1800eff9e  mov     ebx, [r14+88h]
0x1800effa5  call    cs:__imp_RtlSubAuthoritySid
0x1800effac  nop     dword ptr [rax+rax+00h]
0x1800effb1  mov     r8b, 1; SubAuthorityCount
0x1800effb4  lea     rdx, [rbp+50h+var_90]; IdentifierAuthority
0x1800effb8  mov     rcx, rsi; Sid
0x1800effbb  mov     [rax], ebx
0x1800effbd  mov     [r12+8], rdi
0x1800effc2  mov     dword ptr [r12+10h], 0C0000007h
0x1800effcb  call    cs:__imp_RtlInitializeSid
0x1800effd2  nop     dword ptr [rax+rax+00h]
0x1800effd7  xor     edx, edx; SubAuthority
0x1800effd9  mov     rcx, rsi; Sid
0x1800effdc  call    cs:__imp_RtlSubAuthoritySid
0x1800effe3  nop     dword ptr [rax+rax+00h]
0x1800effe8  xor     edi, edi
0x1800effea  lea     rdx, aSystemmanageda; "SystemManagedAdminLogon"
0x1800efff1  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x1800efff5  mov     [rax], edi
0x1800efff7  mov     [r12+18h], rsi
0x1800efffc  mov     dword ptr [r12+20h], 7
0x1800f0005  call    cs:__imp_RtlInitString
0x1800f000c  nop     dword ptr [rax+rax+00h]
0x1800f0011  lea     r8, [rbp+50h+SecurityMode]; SecurityMode
0x1800f0015  lea     rdx, [rsp+150h+LsaHandle]; LsaHandle
0x1800f001a  lea     rcx, [rbp+50h+DestinationString]; LogonProcessName
0x1800f001e  call    cs:__imp_LsaRegisterLogonProcess
0x1800f0025  nop     dword ptr [rax+rax+00h]
0x1800f002a  mov     ebx, eax
0x1800f002c  test    eax, eax
0x1800f002e  js      loc_1800F01F8
0x1800f0034  lea     rdx, aMicrosoftAuthe_0; "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0"
0x1800f003b  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x1800f003f  call    cs:__imp_RtlInitString
0x1800f0046  nop     dword ptr [rax+rax+00h]
0x1800f004b  mov     rcx, [rsp+150h+LsaHandle]; LsaHandle
0x1800f0050  lea     r8, [rsp+150h+AuthenticationPackage]; AuthenticationPackage
0x1800f0055  lea     rdx, [rbp+50h+DestinationString]; PackageName
0x1800f0059  call    cs:__imp_LsaLookupAuthenticationPackage
0x1800f0060  nop     dword ptr [rax+rax+00h]
0x1800f0065  mov     ebx, eax
0x1800f0067  test    eax, eax
0x1800f0069  js      loc_1800F01F8
0x1800f006f  mov     edx, [rsp+150h+AuthenticationPackage]; AuthenticationPackage
0x1800f0073  lea     rax, [rsp+150h+var_F0]
0x1800f0078  mov     rcx, [rsp+150h+LsaHandle]; LsaHandle
0x1800f007d  lea     esi, [rdi+0Ch]
0x1800f0080  mov     [rsp+150h+ProtocolStatus], rax; ProtocolStatus
0x1800f0085  lea     r8, [rbp+50h+ProtocolSubmitBuffer]; ProtocolSubmitBuffer
0x1800f0089  lea     rax, [rsp+150h+var_E8]
0x1800f008e  mov     [rbp+50h+ProtocolSubmitBuffer+4], 3
0x1800f0096  mov     [rsp+150h+ReturnBufferLength], rax; ReturnBufferLength
0x1800f009b  mov     r9d, esi; SubmitBufferLength
0x1800f009e  lea     rax, [rbp+50h+var_C0]
0x1800f00a2  mov     dword ptr [rbp+50h+ProtocolSubmitBuffer], 13h
0x1800f00a9  mov     [rsp+150h+ProtocolReturnBuffer], rax; ProtocolReturnBuffer
0x1800f00ae  call    cs:__imp_LsaCallAuthenticationPackage
0x1800f00b5  nop     dword ptr [rax+rax+00h]
0x1800f00ba  mov     ebx, eax
0x1800f00bc  test    eax, eax
0x1800f00be  js      loc_1800F01F8
0x1800f00c4  mov     ebx, [rsp+150h+var_F0]
0x1800f00c8  test    ebx, ebx
0x1800f00ca  js      loc_1800F01F8
0x1800f00d0  mov     cl, 1; unsigned __int8
0x1800f00d2  call    ?LsapUpdateShadowAdminLogonAllowedList@@YAJE@Z; LsapUpdateShadowAdminLogonAllowedList(uchar)
0x1800f00d7  mov     ebx, eax
0x1800f00d9  test    eax, eax
0x1800f00db  js      loc_1800F01BB
0x1800f00e1  mov     rcx, [rbp+50h+var_C8]
0x1800f00e5  lea     rax, [rsp+150h+TokenHandle]
0x1800f00ea  mov     [rsp+150h+var_100], rdi
0x1800f00ef  lea     r9d, [rdi+2]
0x1800f00f3  mov     [rsp+150h+var_108], rdi
0x1800f00f8  lea     r8, cchOriginalDestLength
0x1800f00ff  mov     [rsp+150h+var_110], rdi
0x1800f0104  lea     rdx, asc_18016BA48; "."
0x1800f010b  mov     [rsp+150h+var_118], rdi
0x1800f0110  mov     [rsp+150h+ProtocolStatus], rax
0x1800f0115  mov     [rsp+150h+ReturnBufferLength], r12
0x1800f011a  mov     dword ptr [rsp+150h+ProtocolReturnBuffer], edi
0x1800f011e  call    cs:__imp_LogonUserExExW
0x1800f0125  nop     dword ptr [rax+rax+00h]
0x1800f012a  test    eax, eax
0x1800f012c  jnz     short loc_1800F0145
0x1800f012e  call    cs:__imp_GetLastError
0x1800f0135  nop     dword ptr [rax+rax+00h]
0x1800f013a  test    eax, eax
0x1800f013c  jz      short loc_1800F0145
0x1800f013e  mov     ebx, 0C00000BBh
0x1800f0143  jmp     short loc_1800F01B4
0x1800f0145  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x1800f014a  lea     rax, [rbp+50h+ReturnLength]
0x1800f014e  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800f0154  mov     [rsp+150h+ProtocolReturnBuffer], rax; ReturnLength
0x1800f0159  lea     r8, [rbp+50h+TokenInformation]; TokenInformation
0x1800f015d  lea     edx, [r9-2Eh]; TokenInformationClass
0x1800f0161  call    cs:__imp_NtQueryInformationToken
0x1800f0168  nop     dword ptr [rax+rax+00h]
0x1800f016d  mov     ebx, eax
0x1800f016f  test    eax, eax
0x1800f0171  js      short loc_1800F01B4
0x1800f0173  lea     rcx, [rbp+50h+TokenInformation+8]; struct _LUID *
0x1800f0177  call    ?LsapLocateLogonSession@@YAPEAU_LSAP_LOGON_SESSION@@PEAU_LUID@@@Z; LsapLocateLogonSession(_LUID *)
0x1800f017c  mov     r15, rax
0x1800f017f  test    rax, rax
0x1800f0182  jnz     short loc_1800F018B
0x1800f0184  mov     ebx, 0C000005Fh
0x1800f0189  jmp     short loc_1800F01B4
0x1800f018b  mov     rcx, [rsp+150h+TokenHandle]; SourceHandle
0x1800f0190  mov     rdx, r13; TargetHandle
0x1800f0193  call    ?LsapDuplicateHandle@@YAJPEAXPEAPEAX@Z; LsapDuplicateHandle(void *,void * *)
0x1800f0198  mov     ebx, eax
0x1800f019a  test    eax, eax
0x1800f019c  js      short loc_1800F01B4
0x1800f019e  mov     eax, [r14+0F8h]
0x1800f01a5  mov     [r15+0F8h], eax
0x1800f01ac  mov     rax, [r14+70h]
0x1800f01b0  mov     [r15+78h], rax
0x1800f01b4  xor     ecx, ecx; unsigned __int8
0x1800f01b6  call    ?LsapUpdateShadowAdminLogonAllowedList@@YAJE@Z; LsapUpdateShadowAdminLogonAllowedList(uchar)
0x1800f01bb  mov     edx, [rsp+150h+AuthenticationPackage]; AuthenticationPackage
0x1800f01bf  lea     rax, [rsp+150h+var_F0]
0x1800f01c4  mov     rcx, [rsp+150h+LsaHandle]; LsaHandle
0x1800f01c9  lea     r8, [rbp+50h+ProtocolSubmitBuffer]; ProtocolSubmitBuffer
0x1800f01cd  mov     [rsp+150h+ProtocolStatus], rax; ProtocolStatus
0x1800f01d2  mov     r9d, esi; SubmitBufferLength
0x1800f01d5  lea     rax, [rsp+150h+var_E8]
0x1800f01da  mov     byte ptr [rbp+50h+var_80+1], 1
0x1800f01de  mov     [rsp+150h+ReturnBufferLength], rax; ReturnBufferLength
0x1800f01e3  lea     rax, [rbp+50h+var_C0]
0x1800f01e7  mov     [rsp+150h+ProtocolReturnBuffer], rax; ProtocolReturnBuffer
0x1800f01ec  call    cs:__imp_LsaCallAuthenticationPackage
0x1800f01f3  nop     dword ptr [rax+rax+00h]
0x1800f01f8  mov     rcx, [rbp+50h+var_C8]
0x1800f01fc  call    cs:__imp_SamFreeMemory
0x1800f0203  nop     dword ptr [rax+rax+00h]
0x1800f0208  mov     rcx, [rbp+50h+var_B8]
0x1800f020c  call    cs:__imp_SamFreeMemory
0x1800f0213  nop     dword ptr [rax+rax+00h]
0x1800f0218  test    r12, r12
0x1800f021b  jz      short loc_1800F022C
0x1800f021d  mov     rcx, r12; hMem
0x1800f0220  call    cs:__imp_LocalFree
0x1800f0227  nop     dword ptr [rax+rax+00h]
0x1800f022c  test    r14, r14
0x1800f022f  jz      short loc_1800F0239
0x1800f0231  mov     rcx, r14; struct _LSAP_LOGON_SESSION *
0x1800f0234  call    ?LsapReleaseLogonSession@@YAXPEAU_LSAP_LOGON_SESSION@@@Z; LsapReleaseLogonSession(_LSAP_LOGON_SESSION *)
0x1800f0239  test    r15, r15
0x1800f023c  jz      short loc_1800F0246
0x1800f023e  mov     rcx, r15; struct _LSAP_LOGON_SESSION *
0x1800f0241  call    ?LsapReleaseLogonSession@@YAXPEAU_LSAP_LOGON_SESSION@@@Z; LsapReleaseLogonSession(_LSAP_LOGON_SESSION *)
0x1800f0246  mov     rcx, [rsp+150h+LsaHandle]; LsaHandle
0x1800f024b  test    rcx, rcx
0x1800f024e  jz      short loc_1800F025C
0x1800f0250  call    cs:__imp_LsaDeregisterLogonProcess
0x1800f0257  nop     dword ptr [rax+rax+00h]
0x1800f025c  mov     rcx, [rsp+150h+TokenHandle]; Handle
0x1800f0261  test    rcx, rcx
0x1800f0264  jz      short loc_1800F0272
0x1800f0266  call    cs:__imp_NtClose
0x1800f026d  nop     dword ptr [rax+rax+00h]
0x1800f0272  mov     eax, ebx
0x1800f0274  mov     rcx, [rbp+50h+var_40]
0x1800f0278  xor     rcx, rsp; StackCookie
0x1800f027b  call    __security_check_cookie
0x1800f0280  mov     rbx, [rsp+150h+arg_10]
0x1800f0288  add     rsp, 120h
0x1800f028f  pop     r15
0x1800f0291  pop     r14
0x1800f0293  pop     r13
0x1800f0295  pop     r12
0x1800f0297  pop     rdi
0x1800f0298  pop     rsi
0x1800f0299  pop     rbp
0x1800f029a  retn
```
