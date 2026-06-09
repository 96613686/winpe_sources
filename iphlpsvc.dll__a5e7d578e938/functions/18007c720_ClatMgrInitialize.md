# ClatMgrInitialize

- ea: `0x18007c720`
- end: `0x18007ca98`
- name: `ClatMgrInitialize`
- size: `888`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180004f60`
- `0x18000d7c0`
- `0x18007c48c`
- `0x18007c720`
- `0x18007cf2c`
- `0x18007d014`
- `0x18007d1cc`
- `0x18007d350`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007c88f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007c88f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c8fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c99c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c9d6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c8fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c99c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c9d6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18007c763`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18007c763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c9b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c9ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ca42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c9b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c9ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ca42`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18007c952`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18007ca32`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18007c952`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18007ca32`
- `IPXLATCFG!IPxlatPolicyMgrInitialize` at `0x18007c852`
- `IPXLATCFG!IPxlatPolicyMgrInitialize` at `0x18007c852`
- `IPXLATCFG!IPxlatPolicyMgrRegisterChangeNotifications` at `0x18007c8d2`
- `IPXLATCFG!IPxlatPolicyMgrRegisterChangeNotifications` at `0x18007c8d2`

## string_xrefs

- `0x18007c91e`: `Update event creation failed: Status = %d`
- `0x18007c96e`: `Failed to register update callback. Status = %d`
- `0x18007c97a`: `Update callback registered successfully.`
- `0x18007ca4e`: `Failed to register service exit callback. Status = %d`
- `0x18007ca5a`: `Service exit callback registered successfully.`

## pseudocode

```c
void __fastcall ClatMgrInitialize(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  unsigned __int32 v2; // eax
  __int64 v3; // rcx
  unsigned int v4; // eax
  __int32 v5; // eax
  int v6; // eax
  HANDLE EventW; // rax
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  DWORD LastError; // eax
  unsigned int v13; // eax
  __int128 v14; // [rsp+30h] [rbp-9h]
  __int128 v15; // [rsp+40h] [rbp+7h]
  __int128 v16; // [rsp+50h] [rbp+17h]
  __int128 v17; // [rsp+60h] [rbp+27h]
  __int128 v18; // [rsp+70h] [rbp+37h]
  __int128 v19; // [rsp+80h] [rbp+47h]

  v2 = _InterlockedCompareExchange(&dword_1800CBF50, 1, 0);
  if ( !v2 )
  {
    InitializeCriticalSection(&stru_1800CBF58);
    DWORD2(v14) = 33;
    qword_1800CBFD8 = (__int64)&qword_1800CBFD0;
    qword_1800CBFD0 = (__int64)&qword_1800CBFD0;
    *(_QWORD *)&v14 = &NPI_MS_IPV6_MODULEID;
    *((_QWORD *)&v15 + 1) = ClatMgrOnIpv6RouterInformationChange;
    *((_QWORD *)&v17 + 1) = ClatMgrOnIpv4InterfaceChange;
    xmmword_1800CBFF0 = v14;
    *(_QWORD *)&v15 = 0;
    xmmword_1800CC000 = v15;
    *(_QWORD *)&v16 = &NPI_MS_IPV4_MODULEID;
    DWORD2(v16) = 7;
    *(_QWORD *)&v17 = 0;
    *((_QWORD *)&v19 + 1) = ClatMgrOnIpv4AddressChange;
    xmmword_1800CC020 = v17;
    *(_QWORD *)&v18 = &NPI_MS_IPV4_MODULEID;
    DWORD2(v18) = 10;
    *(_QWORD *)&v19 = 0;
    xmmword_1800CC010 = v16;
    xmmword_1800CC040 = v19;
    byte_1800CBF80 = 1;
    word_1800CBFC9 = 257;
    byte_1800CBFCB = 1;
    xmmword_1800CC030 = v18;
    if ( (unsigned int)Feature_CLAT_Preview2_GPO__private_IsEnabledDeviceUsageNoInline() )
    {
      v4 = IPxlatPolicyMgrInitialize();
      if ( v4 )
      {
        EventWrite0(0x4000000, L"Initializing IPxlatPolicyMgr failed: Status = %d", v4);
        goto LABEL_6;
      }
      v6 = IPxlatPolicyMgrRegisterChangeNotifications(ClatMgrPolicyChangeCallback, &dword_1800CBF50);
    }
    else
    {
      v6 = ClatMgrRegisterRegistryChangeNotification(v3, &dword_1800CBF50);
    }
    if ( !v6 )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      qword_1800CBFB8 = EventW;
      if ( EventW )
      {
        if ( RegisterWaitForSingleObject(
               &phNewWaitObject,
               EventW,
               ClatMgrUpdateCallback,
               &dword_1800CBF50,
               0xFFFFFFFF,
               0) )
        {
          EventWrite0(0x4000000, L"Update callback registered successfully.");
          byte_1800CBFA0 = 0;
          qword_1800CBF88 = CreateEventW(0, 0, 0, 0);
          if ( qword_1800CBF88 )
          {
            qword_1800CBF98 = CreateEventW(0, 0, 0, 0);
            if ( qword_1800CBF98 )
            {
              if ( RegisterWaitForSingleObject(
                     &qword_1800CBF90,
                     qword_1800CBF88,
                     ClatMgrExitCallback,
                     &dword_1800CBF50,
                     0xFFFFFFFF,
                     0) )
              {
                EventWrite0(0x4000000, L"Service exit callback registered successfully.");
                v13 = ClatMgrRegisterNotificationHandlers(&xmmword_1800CBFF0);
                if ( !v13 )
                {
                  byte_1800CBFE8 = 1;
                  v5 = 2;
                  goto LABEL_7;
                }
                EventWrite0(0x4000000, L"ClatMgrRegisterNotificationHandlers failed: Status = %d", v13);
              }
              else
              {
                LastError = GetLastError();
                EventWrite0(0x4000000, L"Failed to register service exit callback. Status = %d", LastError);
              }
            }
            else
            {
              v11 = GetLastError();
              EventWrite0(0x4000000, L"Exit cleanup event creation failed: Status = %d", v11);
            }
          }
          else
          {
            v10 = GetLastError();
            EventWrite0(0x4000000, L"Exit event creation failed: Status = %d", v10);
          }
        }
        else
        {
          v9 = GetLastError();
          EventWrite0(0x4000000, L"Failed to register update callback. Status = %d", v9);
        }
      }
      else
      {
        v8 = GetLastError();
        EventWrite0(0x4000000, L"Update event creation failed: Status = %d", v8);
      }
    }
LABEL_6:
    ClatMgrUninitializeCore();
    ClatMgrCleanupCore();
    v5 = 0;
LABEL_7:
    _InterlockedExchange(&dword_1800CBF50, v5);
    goto LABEL_8;
  }
  EventWrite0(0x4000000, L"Invalid state. State = %d", v2);
LABEL_8:
  SetEvent(g_ClatMgrStartCompleteEvent);
  DereferenceServiceEx("ClatMgrInitialize", L"onecoreuap\\net\\netio\\iphlpsvc\\clatmgr\\clatmgr.c", 1615);
}

```

## disassembly

```asm
0x18007c720  mov     [rsp-8+arg_0], rsi
0x18007c725  push    rbp
0x18007c726  lea     rbp, [rsp-57h]
0x18007c72b  sub     rsp, 90h
0x18007c732  mov     esi, 1
0x18007c737  xor     eax, eax
0x18007c739  lock cmpxchg cs:dword_1800CBF50, esi
0x18007c741  jz      short loc_18007C75C
0x18007c743  mov     r8d, eax
0x18007c746  lea     rdx, aInvalidStateSt; "Invalid state. State = %d"
0x18007c74d  mov     ecx, 4000000h
0x18007c752  call    EventWrite0
0x18007c757  jmp     loc_18007C888
0x18007c75c  lea     rcx, stru_1800CBF58; lpCriticalSection
0x18007c763  call    cs:__imp_InitializeCriticalSection
0x18007c76a  nop     dword ptr [rax+rax+00h]
0x18007c76f  lea     rax, qword_1800CBFD0
0x18007c776  mov     dword ptr [rbp+57h+var_60+8], 21h ; '!'
0x18007c77d  mov     cs:qword_1800CBFD8, rax
0x18007c784  lea     rcx, NPI_MS_IPV4_MODULEID
0x18007c78b  mov     cs:qword_1800CBFD0, rax
0x18007c792  lea     rax, NPI_MS_IPV6_MODULEID
0x18007c799  mov     qword ptr [rbp+57h+var_60], rax
0x18007c79d  lea     rax, ClatMgrOnIpv6RouterInformationChange
0x18007c7a4  movaps  xmm0, [rbp+57h+var_60]
0x18007c7a8  mov     qword ptr [rbp+57h+var_50+8], rax
0x18007c7ac  lea     rax, ClatMgrOnIpv4InterfaceChange
0x18007c7b3  mov     qword ptr [rbp+57h+var_30+8], rax
0x18007c7b7  lea     rax, ClatMgrOnIpv4AddressChange
0x18007c7be  movaps  cs:xmmword_1800CBFF0, xmm0
0x18007c7c5  mov     qword ptr [rbp+57h+var_50], 0
0x18007c7cd  movaps  xmm1, [rbp+57h+var_50]
0x18007c7d1  movaps  cs:xmmword_1800CC000, xmm1
0x18007c7d8  mov     qword ptr [rbp+57h+var_40], rcx
0x18007c7dc  mov     dword ptr [rbp+57h+var_40+8], 7
0x18007c7e3  movaps  xmm0, [rbp+57h+var_40]
0x18007c7e7  mov     qword ptr [rbp+57h+var_30], 0
0x18007c7ef  movaps  xmm1, [rbp+57h+var_30]
0x18007c7f3  mov     qword ptr [rbp+57h+var_10+8], rax
0x18007c7f7  movaps  cs:xmmword_1800CC020, xmm1
0x18007c7fe  mov     qword ptr [rbp+57h+var_20], rcx
0x18007c802  mov     dword ptr [rbp+57h+var_20+8], 0Ah
0x18007c809  mov     qword ptr [rbp+57h+var_10], 0
0x18007c811  movaps  xmm1, [rbp+57h+var_10]
0x18007c815  movaps  cs:xmmword_1800CC010, xmm0
0x18007c81c  movaps  xmm0, [rbp+57h+var_20]
0x18007c820  movaps  cs:xmmword_1800CC040, xmm1
0x18007c827  mov     cs:byte_1800CBF80, sil
0x18007c82e  mov     cs:word_1800CBFC9, 101h
0x18007c837  mov     cs:byte_1800CBFCB, sil
0x18007c83e  movaps  cs:xmmword_1800CC030, xmm0
0x18007c845  call    Feature_CLAT_Preview2_GPO__private_IsEnabledDeviceUsageNoInline
0x18007c84a  test    eax, eax
0x18007c84c  jz      loc_18007C8E0
0x18007c852  call    cs:__imp_IPxlatPolicyMgrInitialize
0x18007c859  nop     dword ptr [rax+rax+00h]
0x18007c85e  test    eax, eax
0x18007c860  jz      short loc_18007C8C4
0x18007c862  lea     rdx, aInitializingIp; "Initializing IPxlatPolicyMgr failed: St"...
0x18007c869  mov     r8d, eax
0x18007c86c  mov     ecx, 4000000h
0x18007c871  call    EventWrite0
0x18007c876  call    ClatMgrUninitializeCore
0x18007c87b  call    ClatMgrCleanupCore
0x18007c880  xor     eax, eax
0x18007c882  xchg    eax, cs:dword_1800CBF50
0x18007c888  mov     rcx, cs:g_ClatMgrStartCompleteEvent; hEvent
0x18007c88f  call    cs:__imp_SetEvent
0x18007c896  nop     dword ptr [rax+rax+00h]
0x18007c89b  mov     r8d, 64Fh
0x18007c8a1  lea     rdx, aOnecoreuapNetN_12; "onecoreuap\\net\\netio\\iphlpsvc\\clatm"...
0x18007c8a8  lea     rcx, aClatmgrinitial; "ClatMgrInitialize"
0x18007c8af  mov     rsi, [rsp+90h+arg_0]
0x18007c8b7  add     rsp, 90h
0x18007c8be  pop     rbp
0x18007c8bf  jmp     DereferenceServiceEx
0x18007c8c4  lea     rdx, dword_1800CBF50
0x18007c8cb  lea     rcx, ClatMgrPolicyChangeCallback
0x18007c8d2  call    cs:__imp_IPxlatPolicyMgrRegisterChangeNotifications
0x18007c8d9  nop     dword ptr [rax+rax+00h]
0x18007c8de  jmp     short loc_18007C8EC
0x18007c8e0  lea     rdx, dword_1800CBF50
0x18007c8e7  call    ClatMgrRegisterRegistryChangeNotification
0x18007c8ec  test    eax, eax
0x18007c8ee  jnz     short loc_18007C876
0x18007c8f0  xor     r9d, r9d; lpName
0x18007c8f3  xor     r8d, r8d; bInitialState
0x18007c8f6  xor     edx, edx; bManualReset
0x18007c8f8  xor     ecx, ecx; lpEventAttributes
0x18007c8fa  call    cs:__imp_CreateEventW
0x18007c901  nop     dword ptr [rax+rax+00h]
0x18007c906  mov     cs:qword_1800CBFB8, rax
0x18007c90d  test    rax, rax
0x18007c910  jnz     short loc_18007C92A
0x18007c912  call    cs:__imp_GetLastError
0x18007c919  nop     dword ptr [rax+rax+00h]
0x18007c91e  lea     rdx, aUpdateEventCre; "Update event creation failed: Status = "...
0x18007c925  jmp     loc_18007C869
0x18007c92a  mov     [rsp+90h+dwFlags], 0; dwFlags
0x18007c932  lea     r9, dword_1800CBF50; Context
0x18007c939  lea     r8, ClatMgrUpdateCallback; Callback
0x18007c940  mov     [rsp+90h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18007c948  mov     rdx, rax; hObject
0x18007c94b  lea     rcx, phNewWaitObject; phNewWaitObject
0x18007c952  call    cs:__imp_RegisterWaitForSingleObject
0x18007c959  nop     dword ptr [rax+rax+00h]
0x18007c95e  test    eax, eax
0x18007c960  jnz     short loc_18007C97A
0x18007c962  call    cs:__imp_GetLastError
0x18007c969  nop     dword ptr [rax+rax+00h]
0x18007c96e  lea     rdx, aFailedToRegist; "Failed to register update callback. Sta"...
0x18007c975  jmp     loc_18007C869
0x18007c97a  lea     rdx, aUpdateCallback; "Update callback registered successfully"...
0x18007c981  mov     ecx, 4000000h
0x18007c986  call    EventWrite0
0x18007c98b  xor     r9d, r9d; lpName
0x18007c98e  mov     cs:byte_1800CBFA0, 0
0x18007c995  xor     r8d, r8d; bInitialState
0x18007c998  xor     edx, edx; bManualReset
0x18007c99a  xor     ecx, ecx; lpEventAttributes
0x18007c99c  call    cs:__imp_CreateEventW
0x18007c9a3  nop     dword ptr [rax+rax+00h]
0x18007c9a8  mov     cs:qword_1800CBF88, rax
0x18007c9af  test    rax, rax
0x18007c9b2  jnz     short loc_18007C9CC
0x18007c9b4  call    cs:__imp_GetLastError
0x18007c9bb  nop     dword ptr [rax+rax+00h]
0x18007c9c0  lea     rdx, aExitEventCreat; "Exit event creation failed: Status = %d"
0x18007c9c7  jmp     loc_18007C869
0x18007c9cc  xor     r9d, r9d; lpName
0x18007c9cf  xor     r8d, r8d; bInitialState
0x18007c9d2  xor     edx, edx; bManualReset
0x18007c9d4  xor     ecx, ecx; lpEventAttributes
0x18007c9d6  call    cs:__imp_CreateEventW
0x18007c9dd  nop     dword ptr [rax+rax+00h]
0x18007c9e2  mov     cs:qword_1800CBF98, rax
0x18007c9e9  test    rax, rax
0x18007c9ec  jnz     short loc_18007CA06
0x18007c9ee  call    cs:__imp_GetLastError
0x18007c9f5  nop     dword ptr [rax+rax+00h]
0x18007c9fa  lea     rdx, aExitCleanupEve; "Exit cleanup event creation failed: Sta"...
0x18007ca01  jmp     loc_18007C869
0x18007ca06  mov     rdx, cs:qword_1800CBF88; hObject
0x18007ca0d  lea     r9, dword_1800CBF50; Context
0x18007ca14  mov     [rsp+90h+dwFlags], 0; dwFlags
0x18007ca1c  lea     r8, ClatMgrExitCallback; Callback
0x18007ca23  lea     rcx, qword_1800CBF90; phNewWaitObject
0x18007ca2a  mov     [rsp+90h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18007ca32  call    cs:__imp_RegisterWaitForSingleObject
0x18007ca39  nop     dword ptr [rax+rax+00h]
0x18007ca3e  test    eax, eax
0x18007ca40  jnz     short loc_18007CA5A
0x18007ca42  call    cs:__imp_GetLastError
0x18007ca49  nop     dword ptr [rax+rax+00h]
0x18007ca4e  lea     rdx, aFailedToRegist_3; "Failed to register service exit callbac"...
0x18007ca55  jmp     loc_18007C869
0x18007ca5a  lea     rdx, aServiceExitCal; "Service exit callback registered succes"...
0x18007ca61  mov     ecx, 4000000h
0x18007ca66  call    EventWrite0
0x18007ca6b  lea     rcx, xmmword_1800CBFF0
0x18007ca72  call    ClatMgrRegisterNotificationHandlers
0x18007ca77  test    eax, eax
0x18007ca79  jz      short loc_18007CA87
0x18007ca7b  lea     rdx, aClatmgrregiste_0; "ClatMgrRegisterNotificationHandlers fai"...
0x18007ca82  jmp     loc_18007C869
0x18007ca87  mov     cs:byte_1800CBFE8, sil
0x18007ca8e  mov     eax, 2
0x18007ca93  jmp     loc_18007C882
```
