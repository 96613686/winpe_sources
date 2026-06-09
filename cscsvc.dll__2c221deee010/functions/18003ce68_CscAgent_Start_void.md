# CscAgent_Start(void)

- ea: `0x18003ce68`
- end: `0x18003cfee`
- name: `?CscAgent_Start@@YAJXZ`
- size: `390`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180055248`

## callees

- `0x18002f10c`
- `0x180033c88`
- `0x180036098`
- `0x180036394`
- `0x18003ce68`
- `0x18003db90`
- `0x18003de40`
- `0x18003e1d4`
- `0x18003e2d4`
- `0x18003e4d4`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x18003ceab`
- `ntdll!RtlInitializeResource` at `0x18003ceab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003cfa5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003cfa5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003ce7c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003cf26`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003ce7c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003cf26`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18003cf79`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18003cf79`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18003cf0d`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18003cf0d`
- `SspiCli!LsaConnectUntrusted` at `0x18003ced1`
- `SspiCli!LsaConnectUntrusted` at `0x18003ced1`

## pseudocode

```c
__int64 CscAgent_Start(void)
{
  int Error; // ebx
  NTSTATUS v1; // eax
  NTSTATUS v2; // eax
  _LSA_STRING PackageName; // [rsp+20h] [rbp-18h] BYREF

  CscAgentp_ExcludeCscCacheFromBackup();
  if ( !InitializeCriticalSectionAndSpinCount(&g_AgentCritSec, 0) )
  {
    Error = ResultFromLastError();
    if ( Error >= 0 )
      return (unsigned int)Error;
    goto LABEL_17;
  }
  g_bAgentCritSecInitialized = 1;
  RtlInitializeResource(&g_swmrAgentSettingsLock);
  dword_1800B8530 = 1;
  Error = CscAgentp_InitializeSettings();
  if ( Error >= 0 )
  {
    v1 = LsaConnectUntrusted(&g_LsaHandle);
    Error = v1 | 0x10000000;
    if ( v1 >= 0 )
    {
      PackageName.Buffer = "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0";
      *(_QWORD *)&PackageName.Length = 2490405;
      v2 = LsaLookupAuthenticationPackage(g_LsaHandle, &PackageName, &g_LsaNtLmPackageId);
      Error = v2 | 0x10000000;
      if ( v2 >= 0 )
      {
        if ( InitializeCriticalSectionAndSpinCount(&stru_1800B6A68, 0) )
        {
          g_AgentAuthInfo = 1;
LABEL_10:
          Error = CscAgentp_StartAgentThread();
          if ( Error >= 0 )
          {
            Error = CscAgentp_RegisterDriverUpcalls();
            if ( Error >= 0 )
              return (unsigned int)Error;
            CscAgentp_StopAgentThread();
          }
          CAuthInfoList::_Destroy((CAuthInfoList *)&g_AgentAuthInfo);
          goto LABEL_14;
        }
        Error = ResultFromLastError();
        if ( Error >= 0 )
          goto LABEL_10;
      }
LABEL_14:
      LsaDeregisterLogonProcess(g_LsaHandle);
      g_LsaHandle = 0;
      if ( Error >= 0 )
        return (unsigned int)Error;
    }
  }
  CSingleWriterMultiReaderLock::Destroy((CSingleWriterMultiReaderLock *)&g_swmrAgentSettingsLock);
  if ( Error >= 0 )
    return (unsigned int)Error;
  DeleteCriticalSection(&g_AgentCritSec);
  g_bAgentCritSecInitialized = 0;
LABEL_17:
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      WPP_ef399ae69b0439092b78fa9bd8d7e9cf_Traceguids,
      (unsigned int)Error);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18003ce68  push    rbx
0x18003ce6a  sub     rsp, 30h
0x18003ce6e  call    ?CscAgentp_ExcludeCscCacheFromBackup@@YAJXZ; CscAgentp_ExcludeCscCacheFromBackup(void)
0x18003ce73  xor     edx, edx; dwSpinCount
0x18003ce75  lea     rcx, ?g_AgentCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003ce7c  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003ce82  test    eax, eax
0x18003ce84  jnz     short loc_18003CE9A
0x18003ce86  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18003ce8b  mov     ebx, eax
0x18003ce8d  test    eax, eax
0x18003ce8f  jns     loc_18003CFE6
0x18003ce95  jmp     loc_18003CFB5
0x18003ce9a  lea     rcx, ?g_swmrAgentSettingsLock@@3VCSingleWriterMultiReaderLock@@A; Resource
0x18003cea1  mov     cs:?g_bAgentCritSecInitialized@@3HA, 1; int g_bAgentCritSecInitialized
0x18003ceab  call    cs:__imp_RtlInitializeResource
0x18003ceb1  mov     cs:dword_1800B8530, 1
0x18003cebb  call    ?CscAgentp_InitializeSettings@@YAJXZ; CscAgentp_InitializeSettings(void)
0x18003cec0  mov     ebx, eax
0x18003cec2  test    eax, eax
0x18003cec4  js      loc_18003CF8E
0x18003ceca  lea     rcx, ?g_LsaHandle@@3PEAXEA; LsaHandle
0x18003ced1  call    cs:__imp_LsaConnectUntrusted
0x18003ced7  mov     ebx, eax
0x18003ced9  or      ebx, 10000000h
0x18003cedf  jl      loc_18003CF8E
0x18003cee5  mov     rcx, cs:?g_LsaHandle@@3PEAXEA; LsaHandle
0x18003ceec  lea     rax, aMicrosoftAuthe; "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0"
0x18003cef3  lea     r8, ?g_LsaNtLmPackageId@@3KA; AuthenticationPackage
0x18003cefa  mov     [rsp+38h+PackageName.Buffer], rax
0x18003ceff  lea     rdx, [rsp+38h+PackageName]; PackageName
0x18003cf04  mov     qword ptr [rsp+38h+PackageName.Length], 260025h
0x18003cf0d  call    cs:__imp_LsaLookupAuthenticationPackage
0x18003cf13  mov     ebx, eax
0x18003cf15  or      ebx, 10000000h
0x18003cf1b  jl      short loc_18003CF72
0x18003cf1d  xor     edx, edx; dwSpinCount
0x18003cf1f  lea     rcx, stru_1800B6A68; lpCriticalSection
0x18003cf26  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003cf2c  test    eax, eax
0x18003cf2e  jz      short loc_18003CF3C
0x18003cf30  mov     cs:?g_AgentAuthInfo@@3VCAuthInfoList@@A, 1; CAuthInfoList g_AgentAuthInfo
0x18003cf3a  jmp     short loc_18003CF47
0x18003cf3c  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18003cf41  mov     ebx, eax
0x18003cf43  test    eax, eax
0x18003cf45  js      short loc_18003CF72
0x18003cf47  call    ?CscAgentp_StartAgentThread@@YAJXZ; CscAgentp_StartAgentThread(void)
0x18003cf4c  mov     ebx, eax
0x18003cf4e  test    eax, eax
0x18003cf50  js      short loc_18003CF66
0x18003cf52  call    ?CscAgentp_RegisterDriverUpcalls@@YAJXZ; CscAgentp_RegisterDriverUpcalls(void)
0x18003cf57  mov     ebx, eax
0x18003cf59  test    eax, eax
0x18003cf5b  jns     loc_18003CFE6
0x18003cf61  call    ?CscAgentp_StopAgentThread@@YAJXZ; CscAgentp_StopAgentThread(void)
0x18003cf66  lea     rcx, ?g_AgentAuthInfo@@3VCAuthInfoList@@A; this
0x18003cf6d  call    ?_Destroy@CAuthInfoList@@AEAAJXZ; CAuthInfoList::_Destroy(void)
0x18003cf72  mov     rcx, cs:?g_LsaHandle@@3PEAXEA; LsaHandle
0x18003cf79  call    cs:__imp_LsaDeregisterLogonProcess
0x18003cf7f  mov     cs:?g_LsaHandle@@3PEAXEA, 0; void * g_LsaHandle
0x18003cf8a  test    ebx, ebx
0x18003cf8c  jns     short loc_18003CFE6
0x18003cf8e  lea     rcx, ?g_swmrAgentSettingsLock@@3VCSingleWriterMultiReaderLock@@A; this
0x18003cf95  call    ?Destroy@CSingleWriterMultiReaderLock@@QEAAXXZ; CSingleWriterMultiReaderLock::Destroy(void)
0x18003cf9a  test    ebx, ebx
0x18003cf9c  jns     short loc_18003CFE6
0x18003cf9e  lea     rcx, ?g_AgentCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003cfa5  call    cs:__imp_DeleteCriticalSection
0x18003cfab  mov     cs:?g_bAgentCritSecInitialized@@3HA, 0; int g_bAgentCritSecInitialized
0x18003cfb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cfbc  lea     rax, WPP_GLOBAL_Control
0x18003cfc3  cmp     rcx, rax
0x18003cfc6  jz      short loc_18003CFE6
0x18003cfc8  test    byte ptr [rcx+1Ch], 2
0x18003cfcc  jz      short loc_18003CFE6
0x18003cfce  mov     rcx, [rcx+10h]
0x18003cfd2  lea     r8, WPP_ef399ae69b0439092b78fa9bd8d7e9cf_Traceguids
0x18003cfd9  mov     edx, 2Bh ; '+'
0x18003cfde  mov     r9d, ebx
0x18003cfe1  call    WPP_SF_d
0x18003cfe6  mov     eax, ebx
0x18003cfe8  add     rsp, 30h
0x18003cfec  pop     rbx
0x18003cfed  retn
```
