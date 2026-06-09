# Dhcpv6Cleanup

- ea: `0x18001b314`
- end: `0x18001b7c1`
- name: `Dhcpv6Cleanup`
- size: `1197`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001bbe0`

## callees

- `0x180001ca4`
- `0x180001d8c`
- `0x180004a8c`
- `0x180004c3c`
- `0x1800075b0`
- `0x18000bb2c`
- `0x18000c740`
- `0x18000db5c`
- `0x18000e190`
- `0x180019250`
- `0x1800192e4`
- `0x180019ad0`
- `0x18001a3ee`
- `0x18001b314`
- `0x18001b7c8`
- `0x1800216a4`
- `0x18002a3a8`
- `0x18002dff4`
- `0x18002e32c`
- `0x18002ed94`
- `0x1800338c0`
- `0x180033a9c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b400`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b4df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b65f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b67e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b69d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b6bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b400`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b4df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b65f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b67e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b69d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b6bc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001b5e7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001b5e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b41a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b6d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b41a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b6d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b61f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b711`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b61f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b711`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001b49e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001b49e`
- `WS2_32!WSACloseEvent` at `0x18001b4fe`
- `WS2_32!WSACloseEvent` at `0x18001b4fe`
- `WS2_32!__imp_WSACleanup` at `0x18001b768`
- `WS2_32!__imp_WSACleanup` at `0x18001b768`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001b733`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001b733`

## pseudocode

```c
BOOL __fastcall Dhcpv6Cleanup(unsigned int a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  unsigned int *v4; // rbx
  __int64 v5; // rax
  int v6; // edi
  void *v7; // rcx
  void *v8; // rcx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 i; // rbx
  _QWORD *v14; // rdx
  __int64 v15; // rcx
  BOOL result; // eax
  _DWORD v17[80]; // [rsp+30h] [rbp-178h] BYREF

  memset_0(v17, 0, sizeof(v17));
  if ( (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_D(1025, 77, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, a1);
  if ( a1 )
  {
    if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 0x200) != 0 )
      McTemplateU0qq_EtwEventWriteTransfer(
        v2,
        ErrorServiceStop,
        a1,
        (unsigned int)**(_DWORD **)&pDhcpv6GlobalIsShuttingDown);
    InitializeTraceElementFromContext(v17, 0, a1, 130);
    v17[38] = **(_DWORD **)&pDhcpv6GlobalIsShuttingDown;
    TraceLogEx(v17);
  }
  else if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 0x10) != 0 )
  {
    McTemplateU0q_EtwEventWriteTransfer(v2, ServiceStop, (unsigned int)**(_DWORD **)&pDhcpv6GlobalIsShuttingDown);
  }
  if ( !**(_DWORD **)&pDhcpv6GlobalIsShuttingDown && Dhcpv6GlobalWaitableTimerHandle )
  {
    Dhcpv6CancelWaitableTimer();
    CloseHandle(Dhcpv6GlobalWaitableTimerHandle);
    Dhcpv6GlobalWaitableTimerHandle = 0;
  }
  EnterCriticalSection(&Dhcpv6GlobalNicListCritSect);
  while ( 1 )
  {
    v4 = (unsigned int *)Dhcpv6GlobalNICList;
    if ( Dhcpv6GlobalNICList == &Dhcpv6GlobalNICList )
      break;
    if ( *((LPVOID **)Dhcpv6GlobalNICList + 1) != &Dhcpv6GlobalNICList
      || (v5 = *(_QWORD *)Dhcpv6GlobalNICList, *(LPVOID *)(*(_QWORD *)Dhcpv6GlobalNICList + 8LL) != Dhcpv6GlobalNICList) )
    {
      __fastfail(3u);
    }
    Dhcpv6GlobalNICList = *(LPVOID *)Dhcpv6GlobalNICList;
    v6 = 2000;
    *(_QWORD *)(v5 + 8) = &Dhcpv6GlobalNICList;
    _InterlockedDecrement(&Dhcpv6GlobalAdaptersCount);
    *((_QWORD *)v4 + 1) = v4;
    *(_QWORD *)v4 = v4;
    v4[150] = 0;
    *((_QWORD *)v4 + 68) = 0x7FFFFFFFFFFFFFFFLL;
    do
    {
      if ( v4[4] == 1 )
        break;
      CancelRenew(v4);
      Sleep(0x64u);
      v6 -= 100;
    }
    while ( v6 );
    if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 0x10) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v3, ServiceStopCompleted, v4[4]);
    if ( !**(_DWORD **)&pDhcpv6GlobalIsShuttingDown )
    {
      v7 = (void *)*((_QWORD *)v4 + 73);
      if ( v7 )
      {
        CloseHandle(v7);
        *((_QWORD *)v4 + 73) = 0;
      }
      v8 = (void *)*((_QWORD *)v4 + 1113);
      if ( v8 )
      {
        WSACloseEvent(v8);
        *((_QWORD *)v4 + 1113) = 0;
      }
    }
    v3 = (unsigned int)g_fVelocityDhcpv6ContextBitfieldUpdate;
    if ( g_fVelocityDhcpv6ContextBitfieldUpdate )
    {
      v9 = v4[2219];
      v3 = (unsigned int)g_fVelocityDhcpv6ContextBitfieldUpdate;
    }
    else
    {
      v9 = (v4[2215] >> 4) & 1;
    }
    if ( v9 )
    {
      if ( (_DWORD)v3 )
      {
        v10 = v4[2220];
        v3 = (unsigned int)g_fVelocityDhcpv6ContextBitfieldUpdate;
      }
      else
      {
        v10 = (v4[2215] >> 5) & 1;
      }
      if ( !v10 )
      {
        if ( !**(_DWORD **)&pDhcpv6GlobalIsShuttingDown )
          goto LABEL_44;
        if ( (_DWORD)v3 )
          v11 = v4[2216];
        else
          v11 = v4[2215] & 1;
        if ( v11 )
        {
          if ( (v4[142] & 0xFFFFFFFD) != 0 )
          {
            v12 = ReleaseIpv6Addresses((__int64)v4);
            if ( v12 )
            {
              if ( (xmmword_1800423E0 & 2) != 0 )
                WPP_SF_DS(
                  1025,
                  78,
                  (unsigned int)WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids,
                  v12,
                  *((_QWORD *)v4 + 7));
            }
          }
        }
      }
    }
    if ( !**(_DWORD **)&pDhcpv6GlobalIsShuttingDown )
    {
LABEL_44:
      Dhcpv6DestroyLease((__int64)v4);
      RegDeleteValueW(*((HKEY *)v4 + 81), L"Dhcpv6Iaid");
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 4, 0xFFFFFFFF) == 1 )
      Dhcpv6DestroyContextEx(v4);
  }
  LeaveCriticalSection(&Dhcpv6GlobalNicListCritSect);
  if ( !**(_DWORD **)&pDhcpv6GlobalIsShuttingDown )
  {
    if ( !(unsigned int)DhcpIsFSEGuestSystem() )
      Dhcpv6CleanupRegistry();
    if ( !**(_DWORD **)&pDhcpv6GlobalIsShuttingDown )
    {
      if ( Dhcpv6GlobalRecomputeTimerEvent )
      {
        CloseHandle(Dhcpv6GlobalRecomputeTimerEvent);
        Dhcpv6GlobalRecomputeTimerEvent = 0;
      }
      if ( Dhcpv6GlobalRefreshEvent )
      {
        CloseHandle(Dhcpv6GlobalRefreshEvent);
        Dhcpv6GlobalRefreshEvent = 0;
      }
      if ( Dhcpv6OperationCancelEvent )
      {
        CloseHandle(Dhcpv6OperationCancelEvent);
        Dhcpv6OperationCancelEvent = 0;
      }
      if ( Dhcpv6GlobalFirewallReadyEvent )
      {
        CloseHandle(Dhcpv6GlobalFirewallReadyEvent);
        Dhcpv6GlobalFirewallReadyEvent = 0;
      }
    }
  }
  EnterCriticalSection(&Dhcpv6GlobalIaidListCritSect);
  for ( i = Dhcpv6IaidLists; i; Dhcpv6IaidLists = i )
  {
    i = *(_QWORD *)(i + 4096);
    DhcpFree((LPVOID *)&Dhcpv6IaidLists);
  }
  LeaveCriticalSection(&Dhcpv6GlobalIaidListCritSect);
  DhcpFirewallCleanup();
  PdcUnInitialize();
  if ( Dhcpv6GlobalCSNotificationHandle )
  {
    PowerSettingUnregisterNotification(Dhcpv6GlobalCSNotificationHandle);
    Dhcpv6GlobalCSNotificationHandle = 0;
  }
  DhcpCRMPowerUnregistrationAndClean(
    &Dhcpv6GlobalCrmNotificationHandle,
    &Dhcpv6GlobalCrmActivity,
    (unsigned int)Dhcpv6GlobalIsCrmRegistered);
  if ( Dhcpv6GlobalWinSockInitialized )
  {
    WSACleanup();
    Dhcpv6GlobalWinSockInitialized = 0;
  }
  Dhcpv6FreeAllOptionDefs(v15, v14);
  Dhcpv6FreeAllClasses();
  result = DhcpFree((LPVOID *)&Dhcpv6GlobalTraceExArray);
  if ( g_fVelocityDhcpMainThreadSleepTracing )
    return DhcpFree((LPVOID *)&g_pDhcpv6MainThreadTraceArray);
  return result;
}

```

## disassembly

```asm
0x18001b314  push    rbx
0x18001b316  push    rbp
0x18001b317  push    rsi
0x18001b318  push    rdi
0x18001b319  sub     rsp, 188h
0x18001b320  mov     rax, cs:__security_cookie
0x18001b327  xor     rax, rsp
0x18001b32a  mov     [rsp+1A8h+var_38], rax
0x18001b332  mov     ebx, ecx
0x18001b334  xor     edx, edx; Val
0x18001b336  lea     rcx, [rsp+1A8h+var_178]; void *
0x18001b33b  mov     r8d, 140h; Size
0x18001b341  call    memset_0
0x18001b346  test    byte ptr cs:xmmword_1800423E0, 2
0x18001b34d  jz      short loc_18001B368
0x18001b34f  mov     edx, 4Dh ; 'M'
0x18001b354  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18001b35b  mov     ecx, 401h
0x18001b360  mov     r9d, ebx
0x18001b363  call    WPP_SF_D
0x18001b368  xor     esi, esi
0x18001b36a  test    ebx, ebx
0x18001b36c  jz      short loc_18001B3C1
0x18001b36e  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits+1, 2
0x18001b375  jz      short loc_18001B390
0x18001b377  mov     r9, cs:pDhcpv6GlobalIsShuttingDown
0x18001b37e  lea     rdx, ErrorServiceStop
0x18001b385  mov     r8d, ebx
0x18001b388  mov     r9d, [r9]
0x18001b38b  call    McTemplateU0qq_EtwEventWriteTransfer
0x18001b390  mov     r9d, 82h
0x18001b396  lea     rcx, [rsp+1A8h+var_178]
0x18001b39b  mov     r8d, ebx
0x18001b39e  xor     edx, edx
0x18001b3a0  call    InitializeTraceElementFromContext
0x18001b3a5  mov     rax, cs:pDhcpv6GlobalIsShuttingDown
0x18001b3ac  mov     ecx, [rax]
0x18001b3ae  mov     [rsp+1A8h+var_E0], ecx
0x18001b3b5  lea     rcx, [rsp+1A8h+var_178]
0x18001b3ba  call    TraceLogEx
0x18001b3bf  jmp     short loc_18001B3E0
0x18001b3c1  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 10h
0x18001b3c8  jz      short loc_18001B3E0
0x18001b3ca  mov     r8, cs:pDhcpv6GlobalIsShuttingDown
0x18001b3d1  lea     rdx, ServiceStop
0x18001b3d8  mov     r8d, [r8]
0x18001b3db  call    McTemplateU0q_EtwEventWriteTransfer
0x18001b3e0  mov     rax, cs:pDhcpv6GlobalIsShuttingDown
0x18001b3e7  cmp     [rax], esi
0x18001b3e9  jnz     short loc_18001B413
0x18001b3eb  cmp     cs:Dhcpv6GlobalWaitableTimerHandle, rsi
0x18001b3f2  jz      short loc_18001B413
0x18001b3f4  call    Dhcpv6CancelWaitableTimer
0x18001b3f9  mov     rcx, cs:Dhcpv6GlobalWaitableTimerHandle; hObject
0x18001b400  call    cs:__imp_CloseHandle
0x18001b407  nop     dword ptr [rax+rax+00h]
0x18001b40c  mov     cs:Dhcpv6GlobalWaitableTimerHandle, rsi
0x18001b413  lea     rcx, Dhcpv6GlobalNicListCritSect; lpCriticalSection
0x18001b41a  call    cs:__imp_EnterCriticalSection
0x18001b421  nop     dword ptr [rax+rax+00h]
0x18001b426  lea     rbp, Dhcpv6GlobalNICList
0x18001b42d  mov     rbx, cs:Dhcpv6GlobalNICList
0x18001b434  cmp     rbx, rbp
0x18001b437  jz      loc_18001B618
0x18001b43d  cmp     [rbx+8], rbp
0x18001b441  jnz     loc_18001B611
0x18001b447  mov     rax, [rbx]
0x18001b44a  cmp     [rax+8], rbx
0x18001b44e  jnz     loc_18001B611
0x18001b454  mov     cs:Dhcpv6GlobalNICList, rax
0x18001b45b  mov     edi, 7D0h
0x18001b460  mov     [rax+8], rbp
0x18001b464  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001b46e  lock dec cs:Dhcpv6GlobalAdaptersCount
0x18001b475  mov     [rbx+8], rbx
0x18001b479  mov     [rbx], rbx
0x18001b47c  mov     [rbx+258h], esi
0x18001b482  mov     [rbx+220h], rax
0x18001b489  mov     eax, [rbx+10h]
0x18001b48c  cmp     eax, 1
0x18001b48f  jz      short loc_18001B4AF
0x18001b491  mov     rcx, rbx
0x18001b494  call    CancelRenew
0x18001b499  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18001b49e  call    cs:__imp_Sleep
0x18001b4a5  nop     dword ptr [rax+rax+00h]
0x18001b4aa  add     edi, 0FFFFFF9Ch
0x18001b4ad  jnz     short loc_18001B489
0x18001b4af  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 10h
0x18001b4b6  jz      short loc_18001B4C8
0x18001b4b8  mov     r8d, [rbx+10h]
0x18001b4bc  lea     rdx, ServiceStopCompleted
0x18001b4c3  call    McTemplateU0q_EtwEventWriteTransfer
0x18001b4c8  mov     rax, cs:pDhcpv6GlobalIsShuttingDown
0x18001b4cf  cmp     [rax], esi
0x18001b4d1  jnz     short loc_18001B511
0x18001b4d3  mov     rcx, [rbx+248h]; hObject
0x18001b4da  test    rcx, rcx
0x18001b4dd  jz      short loc_18001B4F2
0x18001b4df  call    cs:__imp_CloseHandle
0x18001b4e6  nop     dword ptr [rax+rax+00h]
0x18001b4eb  mov     [rbx+248h], rsi
0x18001b4f2  mov     rcx, [rbx+22C8h]; hEvent
0x18001b4f9  test    rcx, rcx
0x18001b4fc  jz      short loc_18001B511
0x18001b4fe  call    cs:__imp_WSACloseEvent
0x18001b505  nop     dword ptr [rax+rax+00h]
0x18001b50a  mov     [rbx+22C8h], rsi
0x18001b511  mov     ecx, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x18001b517  test    ecx, ecx
0x18001b519  jz      short loc_18001B529
0x18001b51b  mov     eax, [rbx+22ACh]
0x18001b521  mov     ecx, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x18001b527  jmp     short loc_18001B535
0x18001b529  mov     eax, [rbx+229Ch]
0x18001b52f  shr     eax, 4
0x18001b532  and     eax, 1
0x18001b535  test    eax, eax
0x18001b537  jz      loc_18001B5C6
0x18001b53d  test    ecx, ecx
0x18001b53f  jz      short loc_18001B54F
0x18001b541  mov     eax, [rbx+22B0h]
0x18001b547  mov     ecx, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x18001b54d  jmp     short loc_18001B55B
0x18001b54f  mov     eax, [rbx+229Ch]
0x18001b555  shr     eax, 5
0x18001b558  and     eax, 1
0x18001b55b  test    eax, eax
0x18001b55d  jnz     short loc_18001B5C6
0x18001b55f  mov     rax, cs:pDhcpv6GlobalIsShuttingDown
0x18001b566  cmp     [rax], esi
0x18001b568  jz      short loc_18001B5D1
0x18001b56a  test    ecx, ecx
0x18001b56c  jz      short loc_18001B576
0x18001b56e  mov     eax, [rbx+22A0h]
0x18001b574  jmp     short loc_18001B57F
0x18001b576  mov     eax, [rbx+229Ch]
0x18001b57c  and     eax, 1
0x18001b57f  test    eax, eax
0x18001b581  jz      short loc_18001B5C6
0x18001b583  test    dword ptr [rbx+238h], 0FFFFFFFDh
0x18001b58d  jz      short loc_18001B5C6
0x18001b58f  mov     rcx, rbx; int
0x18001b592  call    ReleaseIpv6Addresses
0x18001b597  test    eax, eax
0x18001b599  jz      short loc_18001B5C6
0x18001b59b  test    byte ptr cs:xmmword_1800423E0, 2
0x18001b5a2  jz      short loc_18001B5C6
0x18001b5a4  mov     r8, [rbx+38h]
0x18001b5a8  mov     edx, 4Eh ; 'N'
0x18001b5ad  mov     [rsp+1A8h+var_188], r8
0x18001b5b2  mov     ecx, 401h
0x18001b5b7  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18001b5be  mov     r9d, eax
0x18001b5c1  call    WPP_SF_DS
0x18001b5c6  mov     rax, cs:pDhcpv6GlobalIsShuttingDown
0x18001b5cd  cmp     [rax], esi
0x18001b5cf  jnz     short loc_18001B5F3
0x18001b5d1  mov     rcx, rbx
0x18001b5d4  call    Dhcpv6DestroyLease
0x18001b5d9  mov     rcx, [rbx+288h]; hKey
0x18001b5e0  lea     rdx, aDhcpv6iaid; "Dhcpv6Iaid"
0x18001b5e7  call    cs:__imp_RegDeleteValueW
0x18001b5ee  nop     dword ptr [rax+rax+00h]
0x18001b5f3  or      eax, 0FFFFFFFFh
0x18001b5f6  lock xadd [rbx+10h], eax
0x18001b5fb  cmp     eax, 1
0x18001b5fe  jnz     loc_18001B42D
0x18001b604  mov     rcx, rbx
0x18001b607  call    Dhcpv6DestroyContextEx
0x18001b60c  jmp     loc_18001B42D
0x18001b611  mov     ecx, 3
0x18001b616  int     29h; Win8: RtlFailFast(ecx)
0x18001b618  lea     rcx, Dhcpv6GlobalNicListCritSect; lpCriticalSection
0x18001b61f  call    cs:__imp_LeaveCriticalSection
0x18001b626  nop     dword ptr [rax+rax+00h]
0x18001b62b  mov     rax, cs:pDhcpv6GlobalIsShuttingDown
0x18001b632  cmp     [rax], esi
0x18001b634  jnz     loc_18001B6CF
0x18001b63a  call    DhcpIsFSEGuestSystem
0x18001b63f  test    eax, eax
0x18001b641  jnz     short loc_18001B648
0x18001b643  call    Dhcpv6CleanupRegistry
0x18001b648  mov     rax, cs:pDhcpv6GlobalIsShuttingDown
0x18001b64f  cmp     [rax], esi
0x18001b651  jnz     short loc_18001B6CF
0x18001b653  mov     rcx, cs:Dhcpv6GlobalRecomputeTimerEvent; hObject
0x18001b65a  test    rcx, rcx
0x18001b65d  jz      short loc_18001B672
0x18001b65f  call    cs:__imp_CloseHandle
0x18001b666  nop     dword ptr [rax+rax+00h]
0x18001b66b  mov     cs:Dhcpv6GlobalRecomputeTimerEvent, rsi
0x18001b672  mov     rcx, cs:Dhcpv6GlobalRefreshEvent; hObject
0x18001b679  test    rcx, rcx
0x18001b67c  jz      short loc_18001B691
0x18001b67e  call    cs:__imp_CloseHandle
0x18001b685  nop     dword ptr [rax+rax+00h]
0x18001b68a  mov     cs:Dhcpv6GlobalRefreshEvent, rsi
0x18001b691  mov     rcx, cs:Dhcpv6OperationCancelEvent; hObject
0x18001b698  test    rcx, rcx
0x18001b69b  jz      short loc_18001B6B0
0x18001b69d  call    cs:__imp_CloseHandle
0x18001b6a4  nop     dword ptr [rax+rax+00h]
0x18001b6a9  mov     cs:Dhcpv6OperationCancelEvent, rsi
0x18001b6b0  mov     rcx, cs:Dhcpv6GlobalFirewallReadyEvent; hObject
0x18001b6b7  test    rcx, rcx
0x18001b6ba  jz      short loc_18001B6CF
0x18001b6bc  call    cs:__imp_CloseHandle
0x18001b6c3  nop     dword ptr [rax+rax+00h]
0x18001b6c8  mov     cs:Dhcpv6GlobalFirewallReadyEvent, rsi
0x18001b6cf  lea     rcx, Dhcpv6GlobalIaidListCritSect; lpCriticalSection
0x18001b6d6  call    cs:__imp_EnterCriticalSection
0x18001b6dd  nop     dword ptr [rax+rax+00h]
0x18001b6e2  mov     rbx, cs:Dhcpv6IaidLists
0x18001b6e9  jmp     short loc_18001B705
0x18001b6eb  mov     rbx, [rbx+1000h]
0x18001b6f2  lea     rcx, Dhcpv6IaidLists
0x18001b6f9  call    DhcpFree
0x18001b6fe  mov     cs:Dhcpv6IaidLists, rbx
0x18001b705  test    rbx, rbx
0x18001b708  jnz     short loc_18001B6EB
0x18001b70a  lea     rcx, Dhcpv6GlobalIaidListCritSect; lpCriticalSection
0x18001b711  call    cs:__imp_LeaveCriticalSection
0x18001b718  nop     dword ptr [rax+rax+00h]
0x18001b71d  call    DhcpFirewallCleanup
0x18001b722  call    PdcUnInitialize
0x18001b727  mov     rcx, cs:Dhcpv6GlobalCSNotificationHandle; RegistrationHandle
0x18001b72e  test    rcx, rcx
0x18001b731  jz      short loc_18001B746
0x18001b733  call    cs:__imp_PowerSettingUnregisterNotification
0x18001b73a  nop     dword ptr [rax+rax+00h]
0x18001b73f  mov     cs:Dhcpv6GlobalCSNotificationHandle, rsi
0x18001b746  mov     r8d, cs:Dhcpv6GlobalIsCrmRegistered
0x18001b74d  lea     rdx, Dhcpv6GlobalCrmActivity
0x18001b754  lea     rcx, Dhcpv6GlobalCrmNotificationHandle
0x18001b75b  call    DhcpCRMPowerUnregistrationAndClean
0x18001b760  cmp     cs:Dhcpv6GlobalWinSockInitialized, esi
0x18001b766  jz      short loc_18001B77A
0x18001b768  call    cs:__imp_WSACleanup
0x18001b76f  nop     dword ptr [rax+rax+00h]
0x18001b774  mov     cs:Dhcpv6GlobalWinSockInitialized, esi
0x18001b77a  call    Dhcpv6FreeAllOptionDefs
0x18001b77f  call    Dhcpv6FreeAllClasses
0x18001b784  lea     rcx, Dhcpv6GlobalTraceExArray
0x18001b78b  call    DhcpFree
0x18001b790  cmp     cs:g_fVelocityDhcpMainThreadSleepTracing, esi
0x18001b796  jz      short loc_18001B7A4
0x18001b798  lea     rcx, g_pDhcpv6MainThreadTraceArray
0x18001b79f  call    DhcpFree
0x18001b7a4  mov     rcx, [rsp+1A8h+var_38]
0x18001b7ac  xor     rcx, rsp; StackCookie
0x18001b7af  call    __security_check_cookie
0x18001b7b4  add     rsp, 188h
0x18001b7bb  pop     rdi
0x18001b7bc  pop     rsi
0x18001b7bd  pop     rbp
0x18001b7be  pop     rbx
0x18001b7bf  retn
```
