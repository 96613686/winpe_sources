# DhcpInitData

- ea: `0x180021420`
- end: `0x1800217c1`
- name: `DhcpInitData`
- size: `929`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180025350`

## callees

- `0x180006440`
- `0x180009580`
- `0x18000b650`
- `0x18000eafc`
- `0x1800149e8`
- `0x18001cef0`
- `0x180021420`
- `0x18003619c`
- `0x180044ec0`
- `0x180045044`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800215cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800215cc`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800215ff`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800215ff`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180021612`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180021612`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002163b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021657`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021673`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002168f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800216ab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002163b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021657`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021673`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002168f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800216ab`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800214e1`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800214e1`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18002174a`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18002174a`

## string_xrefs

- `0x1800216ee`: `wcmapi.dll`
- `0x1800216fe`: `wcmsvc.dll`

## pseudocode

```c
__int64 DhcpInitData()
{
  _DWORD *v0; // rax
  DWORD inited; // ebx
  bool v3; // zf
  _DWORD *v4; // rax
  int v5; // ecx
  int v6; // r8d
  DWORD LastError; // eax
  int v8; // ecx
  int v9; // r8d
  unsigned int v10; // eax
  DWORD v11; // eax
  DWORD v12; // eax
  unsigned int v13; // eax
  DWORD cbData; // [rsp+40h] [rbp-48h] BYREF
  _QWORD Recipient[2]; // [rsp+48h] [rbp-40h] BYREF

  cbData = 0;
  v0 = DhcpAlloc(0xA008u);
  DhcpGlobalTraceExArray = (__int64)v0;
  if ( !v0 )
    goto LABEL_2;
  v3 = g_fVelocityDhcpMainThreadSleepTracing == 0;
  *v0 = -1;
  if ( !v3 )
  {
    v4 = DhcpAlloc(0xE04u);
    g_pDhcpMainThreadTraceArray = (__int64)v4;
    if ( !v4 )
    {
LABEL_2:
      inited = 8;
LABEL_3:
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_D(1025, 109, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, inited);
      return inited;
    }
    *v4 = -1;
  }
  DhcpGlobalServiceStatus.dwCurrentState = 2;
  DhcpGlobalServiceStatusHandle = RegisterServiceCtrlHandlerExW(L"DHCP", ServiceControlHandler, 0);
  if ( !DhcpGlobalServiceStatusHandle )
  {
    LastError = GetLastError();
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 103, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, LastError);
  }
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 0x20) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v5, (unsigned int)ServiceRegistersForShutdown, v6, 1, (__int64)Recipient);
  UpdateStatus();
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 104, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 0x20) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v8, (unsigned int)ServiceStart, v9, 1, (__int64)Recipient);
  TraceLogErrorv4(0, 0, 13);
  inited = DhcpInitRegistry();
  if ( inited )
    goto LABEL_3;
  cbData = 4;
  v10 = RegQueryValueExW(DhcpGlobalInterfacesKey, L"UseNetworkHint", 0, 0, &DhcpGlobalUseNetworkHint, &cbData);
  if ( v10 )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_D(1028, inited + 105, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v10);
    *(_DWORD *)&DhcpGlobalUseNetworkHint = 1;
  }
  QueryPerformanceFrequency(&DhcpGlobalPerformanceFrequency);
  DhcpGlobalWaitableTimerHandle = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
  if ( !DhcpGlobalWaitableTimerHandle
    || (DhcpGlobalRecomputeTimerEvent = CreateEventW(0, 0, 1, 0)) == 0
    || (DhcpGlobalTerminateEvent = CreateEventW(0, 1, 0, 0)) == 0
    || (DhcpGlobalServiceSyncEvent = CreateEventW(0, 0, 0, 0)) == 0
    || (DhcpGlobalRefreshEvent = CreateEventW(0, 1, 0, 0)) == 0 )
  {
    inited = GetLastError();
    goto LABEL_32;
  }
  DhcpGlobalFirewallReadyEvent = CreateEventW(0, 1, 0, 0);
  if ( !DhcpGlobalFirewallReadyEvent )
  {
    v11 = GetLastError();
    inited = v11;
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 106, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v11);
LABEL_32:
    if ( !inited )
      return inited;
    goto LABEL_3;
  }
  if ( (unsigned int)IsBinaryPresent(L"wcmapi.dll")
    && (unsigned int)IsBinaryPresent(L"wcmsvc.dll")
    && !DhcpGlobalDisableDs )
  {
    DhcpGlobalDsFeatureEnabled = 1;
  }
  Recipient[1] = 0;
  Recipient[0] = DhcpPowerStateChangeCallback;
  v12 = PowerSettingRegisterNotification(&GUID_LOW_POWER_EPOCH, 2u, Recipient, &DhcpGlobalCSNotificationHandle);
  if ( v12 )
  {
    DhcpGlobalCSNotificationHandle = 0;
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 107, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v12);
  }
  v13 = DhcpCRMPowerRegistration();
  if ( v13 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 108, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v13);
    DhcpCRMPowerUnregistrationAndClean(
      &DhcpGlobalCrmNotificationHandle,
      &DhcpGlobalCrmActivity,
      (unsigned int)DhcpGlobalIsCrmRegistered);
  }
  return 0;
}

```

## disassembly

```asm
0x180021420  push    rbx
0x180021422  push    rsi
0x180021423  push    r14
0x180021425  push    r15
0x180021427  sub     rsp, 68h
0x18002142b  mov     rax, cs:__security_cookie
0x180021432  xor     rax, rsp
0x180021435  mov     [rsp+88h+var_30], rax
0x18002143a  mov     ecx, 0A008h
0x18002143f  mov     [rsp+88h+cbData], 0
0x180021447  call    DhcpAlloc
0x18002144c  mov     cs:DhcpGlobalTraceExArray, rax
0x180021453  mov     r15d, 401h
0x180021459  lea     r14, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180021460  test    rax, rax
0x180021463  jnz     short loc_1800214A0
0x180021465  mov     ebx, 8
0x18002146a  test    byte ptr cs:xmmword_1800616A0, 2
0x180021471  jz      short loc_180021486
0x180021473  mov     edx, 6Dh ; 'm'
0x180021478  mov     ecx, r15d
0x18002147b  mov     r9d, ebx
0x18002147e  mov     r8, r14
0x180021481  call    WPP_SF_D
0x180021486  mov     eax, ebx
0x180021488  mov     rcx, [rsp+88h+var_30]
0x18002148d  xor     rcx, rsp; StackCookie
0x180021490  call    __security_check_cookie
0x180021495  add     rsp, 68h
0x180021499  pop     r15
0x18002149b  pop     r14
0x18002149d  pop     rsi
0x18002149e  pop     rbx
0x18002149f  retn
0x1800214a0  or      ebx, 0FFFFFFFFh
0x1800214a3  cmp     cs:g_fVelocityDhcpMainThreadSleepTracing, 0
0x1800214aa  mov     [rax], ebx
0x1800214ac  jz      short loc_1800214C6
0x1800214ae  mov     ecx, 0E04h
0x1800214b3  call    DhcpAlloc
0x1800214b8  mov     cs:g_pDhcpMainThreadTraceArray, rax
0x1800214bf  test    rax, rax
0x1800214c2  jz      short loc_180021465
0x1800214c4  mov     [rax], ebx
0x1800214c6  xor     r8d, r8d; lpContext
0x1800214c9  mov     cs:DhcpGlobalServiceStatus.dwCurrentState, 2
0x1800214d3  lea     rdx, ServiceControlHandler; lpHandlerProc
0x1800214da  lea     rcx, ServiceName; "DHCP"
0x1800214e1  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800214e7  mov     cs:DhcpGlobalServiceStatusHandle, rax
0x1800214ee  test    rax, rax
0x1800214f1  jnz     short loc_180021515
0x1800214f3  call    cs:__imp_GetLastError
0x1800214f9  test    byte ptr cs:xmmword_1800616A0, 2
0x180021500  jz      short loc_180021515
0x180021502  mov     edx, 67h ; 'g'
0x180021507  mov     ecx, r15d
0x18002150a  mov     r9d, eax
0x18002150d  mov     r8, r14
0x180021510  call    WPP_SF_D
0x180021515  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 20h
0x18002151c  mov     esi, 1
0x180021521  jz      short loc_18002153C
0x180021523  lea     rax, [rsp+88h+Recipient]
0x180021528  mov     r9d, esi
0x18002152b  lea     rdx, ServiceRegistersForShutdown
0x180021532  mov     [rsp+88h+lpData], rax
0x180021537  call    McGenEventWrite_EtwEventWriteTransfer
0x18002153c  call    UpdateStatus
0x180021541  test    byte ptr cs:xmmword_1800616A0, 10h
0x180021548  jz      short loc_18002155C
0x18002154a  mov     edx, 68h ; 'h'
0x18002154f  mov     ecx, 404h
0x180021554  mov     r8, r14
0x180021557  call    WPP_SF_
0x18002155c  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 20h
0x180021563  jz      short loc_18002157E
0x180021565  lea     rax, [rsp+88h+Recipient]
0x18002156a  mov     r9d, esi
0x18002156d  lea     rdx, ServiceStart
0x180021574  mov     [rsp+88h+lpData], rax
0x180021579  call    McGenEventWrite_EtwEventWriteTransfer
0x18002157e  xor     edx, edx
0x180021580  xor     ecx, ecx
0x180021582  lea     r8d, [rdx+0Dh]
0x180021586  call    TraceLogErrorv4
0x18002158b  call    DhcpInitRegistry
0x180021590  mov     ebx, eax
0x180021592  test    eax, eax
0x180021594  jnz     loc_18002146A
0x18002159a  mov     rcx, cs:DhcpGlobalInterfacesKey; hKey
0x1800215a1  lea     rax, [rsp+88h+cbData]
0x1800215a6  mov     [rsp+88h+lpcbData], rax; lpcbData
0x1800215ab  lea     rdx, aUsenetworkhint; "UseNetworkHint"
0x1800215b2  lea     rax, DhcpGlobalUseNetworkHint
0x1800215b9  mov     [rsp+88h+cbData], 4
0x1800215c1  xor     r9d, r9d; lpType
0x1800215c4  mov     [rsp+88h+lpData], rax; lpData
0x1800215c9  xor     r8d, r8d; lpReserved
0x1800215cc  call    cs:__imp_RegQueryValueExW
0x1800215d2  test    eax, eax
0x1800215d4  jz      short loc_1800215F8
0x1800215d6  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800215dd  jz      short loc_1800215F2
0x1800215df  lea     edx, [rbx+69h]
0x1800215e2  mov     ecx, 404h
0x1800215e7  mov     r9d, eax
0x1800215ea  mov     r8, r14
0x1800215ed  call    WPP_SF_D
0x1800215f2  mov     cs:DhcpGlobalUseNetworkHint, esi
0x1800215f8  lea     rcx, DhcpGlobalPerformanceFrequency; lpFrequency
0x1800215ff  call    cs:__imp_QueryPerformanceFrequency
0x180021605  mov     r9d, 1F0003h; dwDesiredAccess
0x18002160b  xor     r8d, r8d; dwFlags
0x18002160e  xor     edx, edx; lpTimerName
0x180021610  xor     ecx, ecx; lpTimerAttributes
0x180021612  call    cs:__imp_CreateWaitableTimerExW
0x180021618  mov     cs:DhcpGlobalWaitableTimerHandle, rax
0x18002161f  test    rax, rax
0x180021622  jnz     short loc_180021631
0x180021624  call    cs:__imp_GetLastError
0x18002162a  mov     ebx, eax
0x18002162c  jmp     loc_1800216E1
0x180021631  xor     r9d, r9d; lpName
0x180021634  mov     r8d, esi; bInitialState
0x180021637  xor     edx, edx; bManualReset
0x180021639  xor     ecx, ecx; lpEventAttributes
0x18002163b  call    cs:__imp_CreateEventW
0x180021641  mov     cs:DhcpGlobalRecomputeTimerEvent, rax
0x180021648  test    rax, rax
0x18002164b  jz      short loc_180021624
0x18002164d  xor     r9d, r9d; lpName
0x180021650  xor     r8d, r8d; bInitialState
0x180021653  mov     edx, esi; bManualReset
0x180021655  xor     ecx, ecx; lpEventAttributes
0x180021657  call    cs:__imp_CreateEventW
0x18002165d  mov     cs:DhcpGlobalTerminateEvent, rax
0x180021664  test    rax, rax
0x180021667  jz      short loc_180021624
0x180021669  xor     r9d, r9d; lpName
0x18002166c  xor     r8d, r8d; bInitialState
0x18002166f  xor     edx, edx; bManualReset
0x180021671  xor     ecx, ecx; lpEventAttributes
0x180021673  call    cs:__imp_CreateEventW
0x180021679  mov     cs:DhcpGlobalServiceSyncEvent, rax
0x180021680  test    rax, rax
0x180021683  jz      short loc_180021624
0x180021685  xor     r9d, r9d; lpName
0x180021688  xor     r8d, r8d; bInitialState
0x18002168b  mov     edx, esi; bManualReset
0x18002168d  xor     ecx, ecx; lpEventAttributes
0x18002168f  call    cs:__imp_CreateEventW
0x180021695  mov     cs:DhcpGlobalRefreshEvent, rax
0x18002169c  test    rax, rax
0x18002169f  jz      short loc_180021624
0x1800216a1  xor     r9d, r9d; lpName
0x1800216a4  xor     r8d, r8d; bInitialState
0x1800216a7  mov     edx, esi; bManualReset
0x1800216a9  xor     ecx, ecx; lpEventAttributes
0x1800216ab  call    cs:__imp_CreateEventW
0x1800216b1  mov     cs:DhcpGlobalFirewallReadyEvent, rax
0x1800216b8  test    rax, rax
0x1800216bb  jnz     short loc_1800216EE
0x1800216bd  call    cs:__imp_GetLastError
0x1800216c3  mov     ebx, eax
0x1800216c5  test    byte ptr cs:xmmword_1800616A0, 2
0x1800216cc  jz      short loc_1800216E1
0x1800216ce  mov     edx, 6Ah ; 'j'
0x1800216d3  mov     ecx, r15d
0x1800216d6  mov     r9d, eax
0x1800216d9  mov     r8, r14
0x1800216dc  call    WPP_SF_D
0x1800216e1  test    ebx, ebx
0x1800216e3  jz      loc_180021486
0x1800216e9  jmp     loc_18002146A
0x1800216ee  lea     rcx, aWcmapiDll; "wcmapi.dll"
0x1800216f5  call    IsBinaryPresent
0x1800216fa  test    eax, eax
0x1800216fc  jz      short loc_18002171D
0x1800216fe  lea     rcx, aWcmsvcDll; "wcmsvc.dll"
0x180021705  call    IsBinaryPresent
0x18002170a  test    eax, eax
0x18002170c  jz      short loc_18002171D
0x18002170e  cmp     cs:DhcpGlobalDisableDs, 0
0x180021715  jnz     short loc_18002171D
0x180021717  mov     cs:DhcpGlobalDsFeatureEnabled, esi
0x18002171d  lea     rax, DhcpPowerStateChangeCallback
0x180021724  mov     [rsp+88h+var_38], 0
0x18002172d  lea     r9, DhcpGlobalCSNotificationHandle; RegistrationHandle
0x180021734  mov     [rsp+88h+Recipient], rax
0x180021739  lea     r8, [rsp+88h+Recipient]; Recipient
0x18002173e  mov     edx, 2; Flags
0x180021743  lea     rcx, GUID_LOW_POWER_EPOCH; SettingGuid
0x18002174a  call    cs:__imp_PowerSettingRegisterNotification
0x180021750  test    eax, eax
0x180021752  jz      short loc_18002177B
0x180021754  mov     cs:DhcpGlobalCSNotificationHandle, 0
0x18002175f  test    byte ptr cs:xmmword_1800616A0, 2
0x180021766  jz      short loc_18002177B
0x180021768  mov     edx, 6Bh ; 'k'
0x18002176d  mov     ecx, r15d
0x180021770  mov     r9d, eax
0x180021773  mov     r8, r14
0x180021776  call    WPP_SF_D
0x18002177b  call    DhcpCRMPowerRegistration
0x180021780  test    eax, eax
0x180021782  jz      short loc_1800217BA
0x180021784  test    byte ptr cs:xmmword_1800616A0, 2
0x18002178b  jz      short loc_1800217A0
0x18002178d  mov     edx, 6Ch ; 'l'
0x180021792  mov     ecx, r15d
0x180021795  mov     r9d, eax
0x180021798  mov     r8, r14
0x18002179b  call    WPP_SF_D
0x1800217a0  mov     r8d, cs:DhcpGlobalIsCrmRegistered
0x1800217a7  lea     rdx, DhcpGlobalCrmActivity
0x1800217ae  lea     rcx, DhcpGlobalCrmNotificationHandle
0x1800217b5  call    DhcpCRMPowerUnregistrationAndClean
0x1800217ba  xor     ebx, ebx
0x1800217bc  jmp     loc_180021486
```
