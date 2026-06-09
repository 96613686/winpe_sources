# Dhcpv6InitData

- ea: `0x18001b808`
- end: `0x18001bba7`
- name: `Dhcpv6InitData`
- size: `927`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bbe0`

## callees

- `0x180007564`
- `0x180008e50`
- `0x180017438`
- `0x18001b808`
- `0x18002de64`
- `0x18002dff4`
- `0x18002e06c`
- `0x1800338c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba27`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ba83`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ba83`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001babe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001babe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b895`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b895`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b8c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b939`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b8c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b939`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18001b98a`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18001b98a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b9b0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b9d2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ba0f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b9b0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b9d2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ba0f`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18001bb26`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18001bb26`

## string_xrefs

- `0x18001baca`: `wcmapi.dll`
- `0x18001bada`: `wcmsvc.dll`

## pseudocode

```c
__int64 Dhcpv6InitData()
{
  _DWORD *v0; // rax
  DWORD inited; // ebx
  bool v3; // zf
  _DWORD *v4; // rax
  __int64 v5; // rax
  unsigned int i; // ecx
  __int64 v7; // rdx
  __int64 v8; // r9
  unsigned int UseOfWakeUpPattern; // eax
  DWORD LastError; // eax
  unsigned int v11; // eax
  DWORD v12; // eax
  unsigned int v13; // eax
  _QWORD Recipient[3]; // [rsp+40h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+8h] BYREF

  cbData = 0;
  v0 = (_DWORD *)DhcpAlloc(40968);
  Dhcpv6GlobalTraceExArray = (__int64)v0;
  if ( !v0 )
    goto LABEL_2;
  v3 = g_fVelocityDhcpMainThreadSleepTracing == 0;
  *v0 = -1;
  if ( !v3 )
  {
    v4 = (_DWORD *)DhcpAlloc(3588);
    g_pDhcpv6MainThreadTraceArray = (__int64)v4;
    if ( !v4 )
    {
LABEL_2:
      inited = 8;
      goto LABEL_3;
    }
    *v4 = -1;
  }
  EnterCriticalSection(&Dhcpv6GlobalIaidListCritSect);
  v5 = DhcpAlloc(4104);
  Dhcpv6IaidLists = v5;
  if ( !v5 )
  {
    inited = 8;
    LeaveCriticalSection(&Dhcpv6GlobalIaidListCritSect);
LABEL_3:
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_D(1025, 76, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, inited);
    return inited;
  }
  *(_QWORD *)(v5 + 4096) = 0;
  for ( i = 0; i < 0xFF; ++i )
  {
    v7 = 2LL * i;
    v8 = 2LL * (i + 1);
    *(_DWORD *)(Dhcpv6IaidLists + 8 * v7) = i + 1;
    *(_QWORD *)(Dhcpv6IaidLists + 8 * v7 + 8) = Dhcpv6IaidLists + 16LL * (i + 1);
  }
  *(_DWORD *)(Dhcpv6IaidLists + 8 * v8) = i + 1;
  *(_QWORD *)(Dhcpv6IaidLists + 8 * v8 + 8) = 0;
  LeaveCriticalSection(&Dhcpv6GlobalIaidListCritSect);
  UseOfWakeUpPattern = Dhcpv6ReadUseOfWakeUpPattern();
  Dhcpv6GlobalUseWakeUpPattern = UseOfWakeUpPattern;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 71, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, UseOfWakeUpPattern);
  inited = Dhcpv6InitRegistry();
  if ( inited )
    goto LABEL_3;
  Dhcpv6GlobalWaitableTimerHandle = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
  if ( !Dhcpv6GlobalWaitableTimerHandle
    || (Dhcpv6GlobalRecomputeTimerEvent = CreateEventW(0, 0, 1, 0)) == 0
    || (Dhcpv6GlobalRefreshEvent = CreateEventW(0, 1, 0, 0)) == 0 )
  {
    inited = GetLastError();
    if ( !inited )
      return inited;
    goto LABEL_3;
  }
  Dhcpv6OperationCancelEvent = CreateEventW(0, 1, 0, 0);
  if ( !Dhcpv6OperationCancelEvent )
  {
    LastError = GetLastError();
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_D(1025, 72, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, LastError);
  }
  cbData = 4;
  v11 = RegQueryValueExW(Dhcpv6GlobalInterfacesKey, L"UseNetworkHint", 0, 0, &Dhcpv6GlobalUseNetworkHint, &cbData);
  if ( v11 )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_D(1028, 73, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, v11);
    *(_DWORD *)&Dhcpv6GlobalUseNetworkHint = 1;
  }
  QueryPerformanceFrequency(&Dhcpv6GlobalPerformanceFrequency);
  if ( (unsigned int)IsBinaryPresent(L"wcmapi.dll")
    && (unsigned int)IsBinaryPresent(L"wcmsvc.dll")
    && !Dhcpv6GlobalDisableDs )
  {
    Dhcpv6GlobalDsFeatureEnabled = 1;
  }
  Recipient[1] = 0;
  Recipient[0] = Dhcpv6PowerStateChangeCallback;
  v12 = PowerSettingRegisterNotification(&GUID_LOW_POWER_EPOCH, 2u, Recipient, &Dhcpv6GlobalCSNotificationHandle);
  if ( v12 )
  {
    Dhcpv6GlobalCSNotificationHandle = 0;
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_D(1025, 74, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, v12);
  }
  v13 = DhcpCRMPowerRegistration();
  if ( v13 )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_D(1025, 75, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, v13);
    DhcpCRMPowerUnregistrationAndClean(
      &Dhcpv6GlobalCrmNotificationHandle,
      &Dhcpv6GlobalCrmActivity,
      (unsigned int)Dhcpv6GlobalIsCrmRegistered);
  }
  return 0;
}

```

## disassembly

```asm
0x18001b808  mov     [rsp+arg_8], rbx
0x18001b80d  push    rbp
0x18001b80e  sub     rsp, 50h
0x18001b812  mov     ecx, 0A008h
0x18001b817  mov     [rsp+58h+cbData], 0
0x18001b81f  call    DhcpAlloc
0x18001b824  mov     cs:Dhcpv6GlobalTraceExArray, rax
0x18001b82b  lea     rbp, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18001b832  test    rax, rax
0x18001b835  jnz     short loc_18001B868
0x18001b837  mov     ebx, 8
0x18001b83c  test    byte ptr cs:xmmword_1800423E0, 2
0x18001b843  jz      short loc_18001B85A
0x18001b845  mov     edx, 4Ch ; 'L'
0x18001b84a  mov     ecx, 401h
0x18001b84f  mov     r9d, ebx
0x18001b852  mov     r8, rbp
0x18001b855  call    WPP_SF_D
0x18001b85a  mov     eax, ebx
0x18001b85c  mov     rbx, [rsp+58h+arg_8]
0x18001b861  add     rsp, 50h
0x18001b865  pop     rbp
0x18001b866  retn
0x18001b868  or      ebx, 0FFFFFFFFh
0x18001b86b  cmp     cs:g_fVelocityDhcpMainThreadSleepTracing, 0
0x18001b872  mov     [rax], ebx
0x18001b874  jz      short loc_18001B88E
0x18001b876  mov     ecx, 0E04h
0x18001b87b  call    DhcpAlloc
0x18001b880  mov     cs:g_pDhcpv6MainThreadTraceArray, rax
0x18001b887  test    rax, rax
0x18001b88a  jz      short loc_18001B837
0x18001b88c  mov     [rax], ebx
0x18001b88e  lea     rcx, Dhcpv6GlobalIaidListCritSect; lpCriticalSection
0x18001b895  call    cs:__imp_EnterCriticalSection
0x18001b89c  nop     dword ptr [rax+rax+00h]
0x18001b8a1  mov     ecx, 1008h
0x18001b8a6  call    DhcpAlloc
0x18001b8ab  mov     cs:Dhcpv6IaidLists, rax
0x18001b8b2  test    rax, rax
0x18001b8b5  jnz     short loc_18001B8D2
0x18001b8b7  lea     rcx, Dhcpv6GlobalIaidListCritSect; lpCriticalSection
0x18001b8be  lea     ebx, [rax+8]
0x18001b8c1  call    cs:__imp_LeaveCriticalSection
0x18001b8c8  nop     dword ptr [rax+rax+00h]
0x18001b8cd  jmp     loc_18001B83C
0x18001b8d2  mov     qword ptr [rax+1000h], 0
0x18001b8dd  xor     ecx, ecx
0x18001b8df  mov     rax, cs:Dhcpv6IaidLists
0x18001b8e6  lea     r8d, [rcx+1]
0x18001b8ea  mov     edx, ecx
0x18001b8ec  add     rdx, rdx
0x18001b8ef  mov     r9d, r8d
0x18001b8f2  add     r9, r9
0x18001b8f5  mov     [rax+rdx*8], r8d
0x18001b8f9  mov     rcx, cs:Dhcpv6IaidLists
0x18001b900  lea     rax, [rcx+r9*8]
0x18001b904  mov     [rcx+rdx*8+8], rax
0x18001b909  mov     ecx, r8d
0x18001b90c  cmp     r8d, 0FFh
0x18001b913  jb      short loc_18001B8DF
0x18001b915  mov     rax, cs:Dhcpv6IaidLists
0x18001b91c  inc     ecx
0x18001b91e  mov     [rax+r9*8], ecx
0x18001b922  lea     rcx, Dhcpv6GlobalIaidListCritSect; lpCriticalSection
0x18001b929  mov     rax, cs:Dhcpv6IaidLists
0x18001b930  mov     qword ptr [rax+r9*8+8], 0
0x18001b939  call    cs:__imp_LeaveCriticalSection
0x18001b940  nop     dword ptr [rax+rax+00h]
0x18001b945  call    Dhcpv6ReadUseOfWakeUpPattern
0x18001b94a  mov     cs:Dhcpv6GlobalUseWakeUpPattern, eax
0x18001b950  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001b957  jz      short loc_18001B96E
0x18001b959  mov     edx, 47h ; 'G'
0x18001b95e  mov     ecx, 404h
0x18001b963  mov     r9d, eax
0x18001b966  mov     r8, rbp
0x18001b969  call    WPP_SF_D
0x18001b96e  call    Dhcpv6InitRegistry
0x18001b973  mov     ebx, eax
0x18001b975  test    eax, eax
0x18001b977  jnz     loc_18001B83C
0x18001b97d  mov     r9d, 1F0003h; dwDesiredAccess
0x18001b983  xor     r8d, r8d; dwFlags
0x18001b986  xor     edx, edx; lpTimerName
0x18001b988  xor     ecx, ecx; lpTimerAttributes
0x18001b98a  call    cs:__imp_CreateWaitableTimerExW
0x18001b991  nop     dword ptr [rax+rax+00h]
0x18001b996  mov     cs:Dhcpv6GlobalWaitableTimerHandle, rax
0x18001b99d  test    rax, rax
0x18001b9a0  jz      short loc_18001B9EA
0x18001b9a2  xor     r9d, r9d; lpName
0x18001b9a5  xor     edx, edx; bManualReset
0x18001b9a7  xor     ecx, ecx; lpEventAttributes
0x18001b9a9  lea     ebx, [r9+1]
0x18001b9ad  mov     r8d, ebx; bInitialState
0x18001b9b0  call    cs:__imp_CreateEventW
0x18001b9b7  nop     dword ptr [rax+rax+00h]
0x18001b9bc  mov     cs:Dhcpv6GlobalRecomputeTimerEvent, rax
0x18001b9c3  test    rax, rax
0x18001b9c6  jz      short loc_18001B9EA
0x18001b9c8  xor     r9d, r9d; lpName
0x18001b9cb  xor     r8d, r8d; bInitialState
0x18001b9ce  mov     edx, ebx; bManualReset
0x18001b9d0  xor     ecx, ecx; lpEventAttributes
0x18001b9d2  call    cs:__imp_CreateEventW
0x18001b9d9  nop     dword ptr [rax+rax+00h]
0x18001b9de  mov     cs:Dhcpv6GlobalRefreshEvent, rax
0x18001b9e5  test    rax, rax
0x18001b9e8  jnz     short loc_18001BA05
0x18001b9ea  call    cs:__imp_GetLastError
0x18001b9f1  nop     dword ptr [rax+rax+00h]
0x18001b9f6  mov     ebx, eax
0x18001b9f8  test    eax, eax
0x18001b9fa  jz      loc_18001B85A
0x18001ba00  jmp     loc_18001B83C
0x18001ba05  xor     r9d, r9d; lpName
0x18001ba08  xor     r8d, r8d; bInitialState
0x18001ba0b  mov     edx, ebx; bManualReset
0x18001ba0d  xor     ecx, ecx; lpEventAttributes
0x18001ba0f  call    cs:__imp_CreateEventW
0x18001ba16  nop     dword ptr [rax+rax+00h]
0x18001ba1b  mov     cs:Dhcpv6OperationCancelEvent, rax
0x18001ba22  test    rax, rax
0x18001ba25  jnz     short loc_18001BA51
0x18001ba27  call    cs:__imp_GetLastError
0x18001ba2e  nop     dword ptr [rax+rax+00h]
0x18001ba33  test    byte ptr cs:xmmword_1800423E0, 2
0x18001ba3a  jz      short loc_18001BA51
0x18001ba3c  mov     edx, 48h ; 'H'
0x18001ba41  mov     ecx, 401h
0x18001ba46  mov     r9d, eax
0x18001ba49  mov     r8, rbp
0x18001ba4c  call    WPP_SF_D
0x18001ba51  mov     rcx, cs:Dhcpv6GlobalInterfacesKey; hKey
0x18001ba58  lea     rax, [rsp+58h+cbData]
0x18001ba5d  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18001ba62  lea     rdx, aUsenetworkhint; "UseNetworkHint"
0x18001ba69  lea     rax, Dhcpv6GlobalUseNetworkHint
0x18001ba70  mov     [rsp+58h+cbData], 4
0x18001ba78  xor     r9d, r9d; lpType
0x18001ba7b  mov     [rsp+58h+lpData], rax; lpData
0x18001ba80  xor     r8d, r8d; lpReserved
0x18001ba83  call    cs:__imp_RegQueryValueExW
0x18001ba8a  nop     dword ptr [rax+rax+00h]
0x18001ba8f  test    eax, eax
0x18001ba91  jz      short loc_18001BAB7
0x18001ba93  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001ba9a  jz      short loc_18001BAB1
0x18001ba9c  mov     edx, 49h ; 'I'
0x18001baa1  mov     ecx, 404h
0x18001baa6  mov     r9d, eax
0x18001baa9  mov     r8, rbp
0x18001baac  call    WPP_SF_D
0x18001bab1  mov     cs:Dhcpv6GlobalUseNetworkHint, ebx
0x18001bab7  lea     rcx, Dhcpv6GlobalPerformanceFrequency; lpFrequency
0x18001babe  call    cs:__imp_QueryPerformanceFrequency
0x18001bac5  nop     dword ptr [rax+rax+00h]
0x18001baca  lea     rcx, aWcmapiDll; "wcmapi.dll"
0x18001bad1  call    IsBinaryPresent
0x18001bad6  test    eax, eax
0x18001bad8  jz      short loc_18001BAF9
0x18001bada  lea     rcx, aWcmsvcDll; "wcmsvc.dll"
0x18001bae1  call    IsBinaryPresent
0x18001bae6  test    eax, eax
0x18001bae8  jz      short loc_18001BAF9
0x18001baea  cmp     cs:Dhcpv6GlobalDisableDs, 0
0x18001baf1  jnz     short loc_18001BAF9
0x18001baf3  mov     cs:Dhcpv6GlobalDsFeatureEnabled, ebx
0x18001baf9  lea     rax, Dhcpv6PowerStateChangeCallback
0x18001bb00  mov     [rsp+58h+var_10], 0
0x18001bb09  lea     r9, Dhcpv6GlobalCSNotificationHandle; RegistrationHandle
0x18001bb10  mov     [rsp+58h+Recipient], rax
0x18001bb15  lea     r8, [rsp+58h+Recipient]; Recipient
0x18001bb1a  mov     edx, 2; Flags
0x18001bb1f  lea     rcx, GUID_LOW_POWER_EPOCH; SettingGuid
0x18001bb26  call    cs:__imp_PowerSettingRegisterNotification
0x18001bb2d  nop     dword ptr [rax+rax+00h]
0x18001bb32  test    eax, eax
0x18001bb34  jz      short loc_18001BB5F
0x18001bb36  mov     cs:Dhcpv6GlobalCSNotificationHandle, 0
0x18001bb41  test    byte ptr cs:xmmword_1800423E0, 2
0x18001bb48  jz      short loc_18001BB5F
0x18001bb4a  mov     edx, 4Ah ; 'J'
0x18001bb4f  mov     ecx, 401h
0x18001bb54  mov     r9d, eax
0x18001bb57  mov     r8, rbp
0x18001bb5a  call    WPP_SF_D
0x18001bb5f  call    DhcpCRMPowerRegistration
0x18001bb64  test    eax, eax
0x18001bb66  jz      short loc_18001BBA0
0x18001bb68  test    byte ptr cs:xmmword_1800423E0, 2
0x18001bb6f  jz      short loc_18001BB86
0x18001bb71  mov     edx, 4Bh ; 'K'
0x18001bb76  mov     ecx, 401h
0x18001bb7b  mov     r9d, eax
0x18001bb7e  mov     r8, rbp
0x18001bb81  call    WPP_SF_D
0x18001bb86  mov     r8d, cs:Dhcpv6GlobalIsCrmRegistered
0x18001bb8d  lea     rdx, Dhcpv6GlobalCrmActivity
0x18001bb94  lea     rcx, Dhcpv6GlobalCrmNotificationHandle
0x18001bb9b  call    DhcpCRMPowerUnregistrationAndClean
0x18001bba0  xor     ebx, ebx
0x18001bba2  jmp     loc_18001B85A
```
