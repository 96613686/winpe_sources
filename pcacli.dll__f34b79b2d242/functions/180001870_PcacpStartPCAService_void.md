# PcacpStartPCAService(void)

- ea: `0x180001870`
- end: `0x180001bae`
- name: `?PcacpStartPCAService@@YAKXZ`
- size: `830`
- prototype: `unsigned int(void)`
- caller_count: `6`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800012c0`
- `0x180001430`
- `0x180001bd0`
- `0x180007040`
- `0x1800082c0`
- `0x180008480`

## callees

- `0x180001870`
- `0x180002180`
- `0x180002ee8`
- `0x180002f20`
- `0x180007738`
- `0x18000bffe`
- `0x18000c030`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180001a26`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180001a26`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800019a1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800019a1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180001b36`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180001b44`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180001b36`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180001b44`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800019ee`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800019ee`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x180001a72`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x180001a72`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x180001a9a`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x180001a9a`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180001913`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180001913`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001955`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001921`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001921`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001b28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001b28`

## string_xrefs

- `0x180001b12`: `PcaClient`
- `0x180001934`: `PcacpStartPCAService`
- `0x180001977`: `PcacpStartPCAService`
- `0x1800019c8`: `PcacpStartPCAService`
- `0x180001ab9`: `PcacpStartPCAService`
- `0x180001aad`: `Timeout while starting service`
- `0x1800019b5`: `Failed to OpenSCManager [%d]`
- `0x180001905`: `Global\SC_AutoStartComplete`
- `0x180001964`: `Auto-start services not ready [%d]`
- `0x180001a0f`: `Failed to OpenService [%d]`
- `0x180001a3f`: `Failed to start the service [%d]`
- `0x180001a7e`: `NotifyServiceStatusChange failed [%d]`
- `0x180001ad8`: `Service failed to start [%d]`
- `0x180001b01`: `ServiceStartup,Time,%llu`

## pseudocode

```c
__int64 PcacpStartPCAService(void)
{
  int v0; // ecx
  int v1; // r8d
  int v2; // r9d
  unsigned __int64 v3; // r14
  SC_HANDLE v4; // rbx
  void *v5; // rbp
  HANDLE v6; // rax
  DWORD LastError; // esi
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  SC_HANDLE v11; // rdi
  SC_HANDLE v12; // rax
  DWORD v13; // eax
  const char *v14; // r9
  __int64 v15; // r8
  SC_HANDLE v16; // rax
  __int64 v17; // r8
  unsigned __int64 v18; // rax
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v21[16]; // [rsp+80h] [rbp-28h] BYREF

  memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  v3 = PcaTimeStart();
  if ( (Microsoft_Windows_Program_Compatibility_AssistantEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v0, (unsigned int)"e", v1, v2, (__int64)v21);
  v4 = 0;
  v5 = 0;
  memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  if ( !AutoStartServicesReady )
  {
    v6 = OpenEventW(0x100000u, 0, L"Global\\SC_AutoStartComplete");
    v5 = v6;
    if ( !v6 )
    {
      LastError = GetLastError();
      AslLogCallPrintf(1, "PcacpStartPCAService", 215, "Failed to get AutoStartEvent [%d]", LastError);
      goto LABEL_34;
    }
    if ( WaitForSingleObject(v6, 0) )
    {
      LastError = 21;
      v11 = 0;
      AslLogCallPrintf(1, "PcacpStartPCAService", 226, "Auto-start services not ready [%d]", 21);
LABEL_29:
      CloseHandle(v5);
      goto LABEL_30;
    }
    AutoStartServicesReady = 1;
  }
  v12 = OpenSCManagerW(0, 0, 1u);
  v11 = v12;
  if ( !v12 )
  {
    v13 = GetLastError();
    v14 = "Failed to OpenSCManager [%d]";
    v15 = 244;
    LastError = v13;
LABEL_11:
    AslLogCallPrintf(1, "PcacpStartPCAService", v15, v14);
    goto LABEL_28;
  }
  v16 = OpenServiceW(v12, L"PcaSvc", 0x14u);
  v4 = v16;
  if ( v16 )
  {
    if ( !StartServiceW(v16, 0, 0) )
    {
      LastError = GetLastError();
      if ( LastError != 1056 )
      {
        v14 = "Failed to start the service [%d]";
        v15 = 274;
        goto LABEL_11;
      }
    }
    pNotifyBuffer.dwVersion = 2;
    pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)PcaApiSamplingStop;
    LastError = NotifyServiceStatusChangeW(v4, 8u, &pNotifyBuffer);
    if ( LastError )
    {
      v14 = "NotifyServiceStatusChange failed [%d]";
      v15 = 286;
      goto LABEL_11;
    }
    if ( SleepEx(0x1388u, 1) == 192 )
    {
      LastError = pNotifyBuffer.dwNotificationStatus;
      if ( pNotifyBuffer.dwNotificationStatus )
      {
        v14 = "Service failed to start [%d]";
        v15 = 299;
        goto LABEL_11;
      }
      if ( pNotifyBuffer.ServiceStatus.dwCurrentState == 4 )
      {
        v18 = PcaTimeStart();
        PcaTracePrintf("PcaClient", 0, 0, "ServiceStartup,Time,%llu", v18 - v3);
        LastError = 0;
        goto LABEL_28;
      }
      v17 = 305;
    }
    else
    {
      v17 = 293;
    }
    LastError = 1460;
    AslLogCallPrintf(1, "PcacpStartPCAService", v17, "Timeout while starting service");
    goto LABEL_28;
  }
  LastError = GetLastError();
  if ( LastError != 1060 )
  {
    v14 = "Failed to OpenService [%d]";
    v15 = 254;
    goto LABEL_11;
  }
LABEL_28:
  if ( v5 )
    goto LABEL_29;
LABEL_30:
  if ( v4 )
    CloseServiceHandle(v4);
  if ( v11 )
    CloseServiceHandle(v11);
LABEL_34:
  if ( (Microsoft_Windows_Program_Compatibility_AssistantEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v8, (unsigned int)AE_PCA_ServiceStartup_Stop, v9, v10, (__int64)v21);
  return LastError;
}

```

## disassembly

```asm
0x180001870  mov     r11, rsp
0x180001873  sub     rsp, 0A8h
0x18000187a  mov     rax, cs:__security_cookie
0x180001881  xor     rax, rsp
0x180001884  mov     [rsp+0A8h+var_18], rax
0x18000188c  mov     [r11+8], rbx
0x180001890  lea     rcx, [r11-78h]; void *
0x180001894  mov     [r11+10h], rbp
0x180001898  xor     edx, edx; Val
0x18000189a  mov     r8d, 50h ; 'P'; Size
0x1800018a0  mov     [r11-8], r14
0x1800018a4  call    memset_0
0x1800018a9  call    ?PcaTimeStart@@YA_KXZ; PcaTimeStart(void)
0x1800018ae  test    cs:Microsoft_Windows_Program_Compatibility_AssistantEnableBits, 1
0x1800018b5  mov     r14, rax
0x1800018b8  jz      short loc_1800018D3
0x1800018ba  lea     rax, [rsp+0A8h+var_28]
0x1800018c2  lea     rdx, AE_PCA_ServiceStartup_Start; "e"
0x1800018c9  mov     [rsp+0A8h+var_88], rax
0x1800018ce  call    McGenEventWrite_EtwEventWriteTransfer
0x1800018d3  mov     [rsp+0A8h+arg_10], rsi
0x1800018db  lea     rcx, [rsp+0A8h+pNotifyBuffer]; void *
0x1800018e0  xor     edx, edx; Val
0x1800018e2  mov     [rsp+0A8h+arg_18], rdi
0x1800018ea  mov     r8d, 50h ; 'P'; Size
0x1800018f0  xor     ebx, ebx
0x1800018f2  xor     ebp, ebp
0x1800018f4  call    memset_0
0x1800018f9  cmp     cs:?AutoStartServicesReady@@3HA, ebx; int AutoStartServicesReady
0x1800018ff  jnz     loc_180001997
0x180001905  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x18000190c  xor     edx, edx; bInheritHandle
0x18000190e  mov     ecx, 100000h; dwDesiredAccess
0x180001913  call    cs:__imp_OpenEventW
0x180001919  mov     rbp, rax
0x18000191c  test    rax, rax
0x18000191f  jnz     short loc_180001950
0x180001921  call    cs:__imp_GetLastError
0x180001927  lea     r9, aFailedToGetAut; "Failed to get AutoStartEvent [%d]"
0x18000192e  mov     r8d, 0D7h
0x180001934  lea     rdx, aPcacpstartpcas; "PcacpStartPCAService"
0x18000193b  mov     dword ptr [rsp+0A8h+var_88], eax
0x18000193f  mov     ecx, 1
0x180001944  mov     esi, eax
0x180001946  call    AslLogCallPrintf
0x18000194b  jmp     loc_180001B4A
0x180001950  xor     edx, edx; dwMilliseconds
0x180001952  mov     rcx, rax; hHandle
0x180001955  call    cs:__imp_WaitForSingleObject
0x18000195b  test    eax, eax
0x18000195d  jz      short loc_18000198D
0x18000195f  mov     esi, 15h
0x180001964  lea     r9, aAutoStartServi; "Auto-start services not ready [%d]"
0x18000196b  xor     edi, edi
0x18000196d  mov     dword ptr [rsp+0A8h+var_88], esi
0x180001971  mov     r8d, 0E2h
0x180001977  lea     rdx, aPcacpstartpcas; "PcacpStartPCAService"
0x18000197e  mov     ecx, 1
0x180001983  call    AslLogCallPrintf
0x180001988  jmp     loc_180001B25
0x18000198d  mov     cs:?AutoStartServicesReady@@3HA, 1; int AutoStartServicesReady
0x180001997  xor     edx, edx; lpDatabaseName
0x180001999  xor     ecx, ecx; lpMachineName
0x18000199b  mov     r8d, 1; dwDesiredAccess
0x1800019a1  call    cs:__imp_OpenSCManagerW
0x1800019a7  mov     rdi, rax
0x1800019aa  test    rax, rax
0x1800019ad  jnz     short loc_1800019DE
0x1800019af  call    cs:__imp_GetLastError
0x1800019b5  lea     r9, aFailedToOpensc; "Failed to OpenSCManager [%d]"
0x1800019bc  mov     r8d, 0F4h
0x1800019c2  mov     esi, eax
0x1800019c4  mov     dword ptr [rsp+0A8h+var_88], eax
0x1800019c8  lea     rdx, aPcacpstartpcas; "PcacpStartPCAService"
0x1800019cf  mov     ecx, 1
0x1800019d4  call    AslLogCallPrintf
0x1800019d9  jmp     loc_180001B20
0x1800019de  mov     r8d, 14h; dwDesiredAccess
0x1800019e4  lea     rdx, ServiceName; "PcaSvc"
0x1800019eb  mov     rcx, rax; hSCManager
0x1800019ee  call    cs:__imp_OpenServiceW
0x1800019f4  mov     rbx, rax
0x1800019f7  test    rax, rax
0x1800019fa  jnz     short loc_180001A1E
0x1800019fc  call    cs:__imp_GetLastError
0x180001a02  mov     esi, eax
0x180001a04  cmp     eax, 424h
0x180001a09  jz      loc_180001B20
0x180001a0f  lea     r9, aFailedToOpense; "Failed to OpenService [%d]"
0x180001a16  mov     r8d, 0FEh
0x180001a1c  jmp     short loc_1800019C4
0x180001a1e  xor     r8d, r8d; lpServiceArgVectors
0x180001a21  xor     edx, edx; dwNumServiceArgs
0x180001a23  mov     rcx, rbx; hService
0x180001a26  call    cs:__imp_StartServiceW
0x180001a2c  test    eax, eax
0x180001a2e  jnz     short loc_180001A51
0x180001a30  call    cs:__imp_GetLastError
0x180001a36  mov     esi, eax
0x180001a38  cmp     eax, 420h
0x180001a3d  jz      short loc_180001A51
0x180001a3f  lea     r9, aFailedToStartT; "Failed to start the service [%d]"
0x180001a46  mov     r8d, 112h
0x180001a4c  jmp     loc_1800019C4
0x180001a51  lea     rax, ?PcaApiSamplingStop@@YAXXZ; PcaApiSamplingStop(void)
0x180001a58  mov     [rsp+0A8h+pNotifyBuffer.dwVersion], 2
0x180001a60  lea     r8, [rsp+0A8h+pNotifyBuffer]; pNotifyBuffer
0x180001a65  mov     [rsp+0A8h+pNotifyBuffer.pfnNotifyCallback], rax
0x180001a6a  mov     edx, 8; dwNotifyMask
0x180001a6f  mov     rcx, rbx; hService
0x180001a72  call    cs:__imp_NotifyServiceStatusChangeW
0x180001a78  mov     esi, eax
0x180001a7a  test    eax, eax
0x180001a7c  jz      short loc_180001A90
0x180001a7e  lea     r9, aNotifyservices; "NotifyServiceStatusChange failed [%d]"
0x180001a85  mov     r8d, 11Eh
0x180001a8b  jmp     loc_1800019C4
0x180001a90  mov     edx, 1; bAlertable
0x180001a95  mov     ecx, 1388h; dwMilliseconds
0x180001a9a  call    cs:__imp_SleepEx
0x180001aa0  cmp     eax, 0C0h
0x180001aa5  jz      short loc_180001ACC
0x180001aa7  mov     r8d, 125h
0x180001aad  lea     r9, aTimeoutWhileSt; "Timeout while starting service"
0x180001ab4  mov     ecx, 1
0x180001ab9  lea     rdx, aPcacpstartpcas; "PcacpStartPCAService"
0x180001ac0  mov     esi, 5B4h
0x180001ac5  call    AslLogCallPrintf
0x180001aca  jmp     short loc_180001B20
0x180001acc  mov     esi, [rsp+0A8h+pNotifyBuffer.dwNotificationStatus]
0x180001ad0  test    esi, esi
0x180001ad2  jz      short loc_180001AEA
0x180001ad4  mov     dword ptr [rsp+0A8h+var_88], esi
0x180001ad8  lea     r9, aServiceFailedT; "Service failed to start [%d]"
0x180001adf  mov     r8d, 12Bh
0x180001ae5  jmp     loc_1800019C8
0x180001aea  cmp     [rsp+0A8h+pNotifyBuffer.ServiceStatus.dwCurrentState], 4
0x180001aef  jz      short loc_180001AF9
0x180001af1  mov     r8d, 131h
0x180001af7  jmp     short loc_180001AAD
0x180001af9  call    ?PcaTimeStart@@YA_KXZ; PcaTimeStart(void)
0x180001afe  sub     rax, r14
0x180001b01  lea     r9, aServicestartup; "ServiceStartup,Time,%llu"
0x180001b08  xor     r8d, r8d; unsigned int
0x180001b0b  mov     [rsp+0A8h+var_88], rax
0x180001b10  xor     edx, edx; unsigned int
0x180001b12  lea     rcx, aPcaclient; "PcaClient"
0x180001b19  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x180001b1e  xor     esi, esi
0x180001b20  test    rbp, rbp
0x180001b23  jz      short loc_180001B2E
0x180001b25  mov     rcx, rbp; hObject
0x180001b28  call    cs:__imp_CloseHandle
0x180001b2e  test    rbx, rbx
0x180001b31  jz      short loc_180001B3C
0x180001b33  mov     rcx, rbx; hSCObject
0x180001b36  call    cs:__imp_CloseServiceHandle
0x180001b3c  test    rdi, rdi
0x180001b3f  jz      short loc_180001B4A
0x180001b41  mov     rcx, rdi; hSCObject
0x180001b44  call    cs:__imp_CloseServiceHandle
0x180001b4a  test    cs:Microsoft_Windows_Program_Compatibility_AssistantEnableBits, 1
0x180001b51  mov     r14, [rsp+0A8h+var_8]
0x180001b59  mov     rdi, [rsp+0A8h+arg_18]
0x180001b61  mov     rbp, [rsp+0A8h+arg_8]
0x180001b69  mov     rbx, [rsp+0A8h+arg_0]
0x180001b71  jz      short loc_180001B8C
0x180001b73  lea     rax, [rsp+0A8h+var_28]
0x180001b7b  lea     rdx, AE_PCA_ServiceStartup_Stop
0x180001b82  mov     [rsp+0A8h+var_88], rax
0x180001b87  call    McGenEventWrite_EtwEventWriteTransfer
0x180001b8c  mov     eax, esi
0x180001b8e  mov     rsi, [rsp+0A8h+arg_10]
0x180001b96  mov     rcx, [rsp+0A8h+var_18]
0x180001b9e  xor     rcx, rsp; StackCookie
0x180001ba1  call    __security_check_cookie
0x180001ba6  add     rsp, 0A8h
0x180001bad  retn
```
