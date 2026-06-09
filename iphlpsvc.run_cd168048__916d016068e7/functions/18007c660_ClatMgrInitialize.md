# ClatMgrInitialize

- ea: `0x18007c660`
- end: `0x18007c980`
- name: `ClatMgrInitialize`
- size: `800`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180004f50`
- `0x18000d7b0`
- `0x18007c660`
- `0x18007ce0c`
- `0x18007cef4`
- `0x18007d170`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007c94b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007c94b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c7bb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c856`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c890`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c7bb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c856`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c890`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18007c67c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18007c67c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c7d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c81c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c86e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c8a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c8f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c7d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c81c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c86e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c8a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c8f8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18007c80c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18007c8e8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18007c80c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18007c8e8`
- `IPXLATCFG!IPxlatPolicyMgrInitialize` at `0x18007c760`
- `IPXLATCFG!IPxlatPolicyMgrInitialize` at `0x18007c760`
- `IPXLATCFG!IPxlatPolicyMgrRegisterChangeNotifications` at `0x18007c793`
- `IPXLATCFG!IPxlatPolicyMgrRegisterChangeNotifications` at `0x18007c793`

## string_xrefs

- `0x18007c7df`: `Update event creation failed: Status = %d`
- `0x18007c828`: `Failed to register update callback. Status = %d`
- `0x18007c834`: `Update callback registered successfully.`
- `0x18007c904`: `Failed to register service exit callback. Status = %d`
- `0x18007c910`: `Service exit callback registered successfully.`

## pseudocode

```c
void __fastcall ClatMgrInitialize(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  __int64 v2; // rcx
  unsigned int v3; // eax
  int v4; // eax
  HANDLE EventW; // rax
  DWORD v6; // eax
  DWORD v7; // eax
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD LastError; // eax
  unsigned int v11; // eax
  __int128 v12; // [rsp+30h] [rbp-9h]
  __int128 v13; // [rsp+40h] [rbp+7h]
  __int128 v14; // [rsp+50h] [rbp+17h]
  __int128 v15; // [rsp+60h] [rbp+27h]
  __int128 v16; // [rsp+70h] [rbp+37h]
  __int128 v17; // [rsp+80h] [rbp+47h]

  InitializeCriticalSection(&::Context);
  DWORD2(v12) = 33;
  qword_1800CBFC8 = (__int64)&qword_1800CBFC0;
  qword_1800CBFC0 = (__int64)&qword_1800CBFC0;
  *(_QWORD *)&v12 = &NPI_MS_IPV6_MODULEID;
  *((_QWORD *)&v13 + 1) = ClatMgrOnIpv6RouterInformationChange;
  *((_QWORD *)&v15 + 1) = ClatMgrOnIpv4InterfaceChange;
  xmmword_1800CBFE0 = v12;
  *(_QWORD *)&v13 = 0;
  xmmword_1800CBFF0 = v13;
  *(_QWORD *)&v14 = &NPI_MS_IPV4_MODULEID;
  DWORD2(v14) = 7;
  *(_QWORD *)&v15 = 0;
  *((_QWORD *)&v17 + 1) = ClatMgrOnIpv4AddressChange;
  xmmword_1800CC010 = v15;
  *(_QWORD *)&v16 = &NPI_MS_IPV4_MODULEID;
  DWORD2(v16) = 10;
  *(_QWORD *)&v17 = 0;
  xmmword_1800CC000 = v14;
  xmmword_1800CC030 = v17;
  word_1800CBFB9 = 257;
  byte_1800CBFBB = 1;
  xmmword_1800CC020 = v16;
  if ( (unsigned int)Feature_CLAT_Preview2_GPO__private_IsEnabledDeviceUsageNoInline() )
  {
    v3 = IPxlatPolicyMgrInitialize();
    if ( v3 )
    {
      EventWrite0(0x4000000, L"Initializing IPxlatPolicyMgr failed: Status = %d", v3);
      goto LABEL_21;
    }
    v4 = IPxlatPolicyMgrRegisterChangeNotifications(ClatMgrPolicyChangeCallback, &::Context);
  }
  else
  {
    v4 = ClatMgrRegisterRegistryChangeNotification(v2, &::Context);
  }
  if ( !v4 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    qword_1800CBFA8 = EventW;
    if ( EventW )
    {
      if ( RegisterWaitForSingleObject(&phNewWaitObject, EventW, ClatMgrUpdateCallback, &::Context, 0xFFFFFFFF, 0) )
      {
        EventWrite0(0x4000000, L"Update callback registered successfully.");
        byte_1800CBF90 = 0;
        qword_1800CBF78 = CreateEventW(0, 0, 0, 0);
        if ( qword_1800CBF78 )
        {
          qword_1800CBF88 = CreateEventW(0, 0, 0, 0);
          if ( qword_1800CBF88 )
          {
            if ( RegisterWaitForSingleObject(
                   &qword_1800CBF80,
                   qword_1800CBF78,
                   ClatMgrExitCallback,
                   &::Context,
                   0xFFFFFFFF,
                   0) )
            {
              EventWrite0(0x4000000, L"Service exit callback registered successfully.");
              v11 = ClatMgrRegisterNotificationHandlers(&xmmword_1800CBFE0);
              if ( v11 )
                EventWrite0(0x4000000, L"ClatMgrRegisterNotificationHandlers failed: Status = %d", v11);
              else
                byte_1800CBFD8 = 1;
            }
            else
            {
              LastError = GetLastError();
              EventWrite0(0x4000000, L"Failed to register service exit callback. Status = %d", LastError);
            }
          }
          else
          {
            v9 = GetLastError();
            EventWrite0(0x4000000, L"Exit cleanup event creation failed: Status = %d", v9);
          }
        }
        else
        {
          v8 = GetLastError();
          EventWrite0(0x4000000, L"Exit event creation failed: Status = %d", v8);
        }
      }
      else
      {
        v7 = GetLastError();
        EventWrite0(0x4000000, L"Failed to register update callback. Status = %d", v7);
      }
    }
    else
    {
      v6 = GetLastError();
      EventWrite0(0x4000000, L"Update event creation failed: Status = %d", v6);
    }
  }
LABEL_21:
  SetEvent(g_ClatMgrStartCompleteEvent);
  DereferenceServiceEx("ClatMgrInitialize", L"onecoreuap\\net\\netio\\iphlpsvc\\clatmgr\\clatmgr.c", 1460);
}

```

## disassembly

```asm
0x18007c660  mov     [rsp-8+arg_0], rsi
0x18007c665  push    rbp
0x18007c666  lea     rbp, [rsp-57h]
0x18007c66b  sub     rsp, 90h
0x18007c672  lea     rsi, Context
0x18007c679  mov     rcx, rsi; lpCriticalSection
0x18007c67c  call    cs:__imp_InitializeCriticalSection
0x18007c683  nop     dword ptr [rax+rax+00h]
0x18007c688  lea     rax, qword_1800CBFC0
0x18007c68f  mov     dword ptr [rbp+57h+var_60+8], 21h ; '!'
0x18007c696  mov     cs:qword_1800CBFC8, rax
0x18007c69d  lea     rcx, NPI_MS_IPV4_MODULEID
0x18007c6a4  mov     cs:qword_1800CBFC0, rax
0x18007c6ab  lea     rax, NPI_MS_IPV6_MODULEID
0x18007c6b2  mov     qword ptr [rbp+57h+var_60], rax
0x18007c6b6  lea     rax, ClatMgrOnIpv6RouterInformationChange
0x18007c6bd  movaps  xmm0, [rbp+57h+var_60]
0x18007c6c1  mov     qword ptr [rbp+57h+var_50+8], rax
0x18007c6c5  lea     rax, ClatMgrOnIpv4InterfaceChange
0x18007c6cc  mov     qword ptr [rbp+57h+var_30+8], rax
0x18007c6d0  lea     rax, ClatMgrOnIpv4AddressChange
0x18007c6d7  movaps  cs:xmmword_1800CBFE0, xmm0
0x18007c6de  mov     qword ptr [rbp+57h+var_50], 0
0x18007c6e6  movaps  xmm1, [rbp+57h+var_50]
0x18007c6ea  movaps  cs:xmmword_1800CBFF0, xmm1
0x18007c6f1  mov     qword ptr [rbp+57h+var_40], rcx
0x18007c6f5  mov     dword ptr [rbp+57h+var_40+8], 7
0x18007c6fc  movaps  xmm0, [rbp+57h+var_40]
0x18007c700  mov     qword ptr [rbp+57h+var_30], 0
0x18007c708  movaps  xmm1, [rbp+57h+var_30]
0x18007c70c  mov     qword ptr [rbp+57h+var_10+8], rax
0x18007c710  movaps  cs:xmmword_1800CC010, xmm1
0x18007c717  mov     qword ptr [rbp+57h+var_20], rcx
0x18007c71b  mov     dword ptr [rbp+57h+var_20+8], 0Ah
0x18007c722  mov     qword ptr [rbp+57h+var_10], 0
0x18007c72a  movaps  xmm1, [rbp+57h+var_10]
0x18007c72e  movaps  cs:xmmword_1800CC000, xmm0
0x18007c735  movaps  xmm0, [rbp+57h+var_20]
0x18007c739  movaps  cs:xmmword_1800CC030, xmm1
0x18007c740  mov     cs:word_1800CBFB9, 101h
0x18007c749  mov     cs:byte_1800CBFBB, 1
0x18007c750  movaps  cs:xmmword_1800CC020, xmm0
0x18007c757  call    Feature_CLAT_Preview2_GPO__private_IsEnabledDeviceUsageNoInline
0x18007c75c  test    eax, eax
0x18007c75e  jz      short loc_18007C7A1
0x18007c760  call    cs:__imp_IPxlatPolicyMgrInitialize
0x18007c767  nop     dword ptr [rax+rax+00h]
0x18007c76c  test    eax, eax
0x18007c76e  jz      short loc_18007C789
0x18007c770  lea     rdx, aInitializingIp; "Initializing IPxlatPolicyMgr failed: St"...
0x18007c777  mov     r8d, eax
0x18007c77a  mov     ecx, 4000000h
0x18007c77f  call    EventWrite0
0x18007c784  jmp     loc_18007C944
0x18007c789  mov     rdx, rsi
0x18007c78c  lea     rcx, ClatMgrPolicyChangeCallback
0x18007c793  call    cs:__imp_IPxlatPolicyMgrRegisterChangeNotifications
0x18007c79a  nop     dword ptr [rax+rax+00h]
0x18007c79f  jmp     short loc_18007C7A9
0x18007c7a1  mov     rdx, rsi
0x18007c7a4  call    ClatMgrRegisterRegistryChangeNotification
0x18007c7a9  test    eax, eax
0x18007c7ab  jnz     loc_18007C944
0x18007c7b1  xor     r9d, r9d; lpName
0x18007c7b4  xor     r8d, r8d; bInitialState
0x18007c7b7  xor     edx, edx; bManualReset
0x18007c7b9  xor     ecx, ecx; lpEventAttributes
0x18007c7bb  call    cs:__imp_CreateEventW
0x18007c7c2  nop     dword ptr [rax+rax+00h]
0x18007c7c7  mov     cs:qword_1800CBFA8, rax
0x18007c7ce  test    rax, rax
0x18007c7d1  jnz     short loc_18007C7E8
0x18007c7d3  call    cs:__imp_GetLastError
0x18007c7da  nop     dword ptr [rax+rax+00h]
0x18007c7df  lea     rdx, aUpdateEventCre; "Update event creation failed: Status = "...
0x18007c7e6  jmp     short loc_18007C777
0x18007c7e8  mov     [rsp+90h+dwFlags], 0; dwFlags
0x18007c7f0  lea     r8, ClatMgrUpdateCallback; Callback
0x18007c7f7  mov     r9, rsi; Context
0x18007c7fa  mov     [rsp+90h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18007c802  mov     rdx, rax; hObject
0x18007c805  lea     rcx, phNewWaitObject; phNewWaitObject
0x18007c80c  call    cs:__imp_RegisterWaitForSingleObject
0x18007c813  nop     dword ptr [rax+rax+00h]
0x18007c818  test    eax, eax
0x18007c81a  jnz     short loc_18007C834
0x18007c81c  call    cs:__imp_GetLastError
0x18007c823  nop     dword ptr [rax+rax+00h]
0x18007c828  lea     rdx, aFailedToRegist; "Failed to register update callback. Sta"...
0x18007c82f  jmp     loc_18007C777
0x18007c834  lea     rdx, aUpdateCallback; "Update callback registered successfully"...
0x18007c83b  mov     ecx, 4000000h
0x18007c840  call    EventWrite0
0x18007c845  xor     r9d, r9d; lpName
0x18007c848  mov     cs:byte_1800CBF90, 0
0x18007c84f  xor     r8d, r8d; bInitialState
0x18007c852  xor     edx, edx; bManualReset
0x18007c854  xor     ecx, ecx; lpEventAttributes
0x18007c856  call    cs:__imp_CreateEventW
0x18007c85d  nop     dword ptr [rax+rax+00h]
0x18007c862  mov     cs:qword_1800CBF78, rax
0x18007c869  test    rax, rax
0x18007c86c  jnz     short loc_18007C886
0x18007c86e  call    cs:__imp_GetLastError
0x18007c875  nop     dword ptr [rax+rax+00h]
0x18007c87a  lea     rdx, aExitEventCreat; "Exit event creation failed: Status = %d"
0x18007c881  jmp     loc_18007C777
0x18007c886  xor     r9d, r9d; lpName
0x18007c889  xor     r8d, r8d; bInitialState
0x18007c88c  xor     edx, edx; bManualReset
0x18007c88e  xor     ecx, ecx; lpEventAttributes
0x18007c890  call    cs:__imp_CreateEventW
0x18007c897  nop     dword ptr [rax+rax+00h]
0x18007c89c  mov     cs:qword_1800CBF88, rax
0x18007c8a3  test    rax, rax
0x18007c8a6  jnz     short loc_18007C8C0
0x18007c8a8  call    cs:__imp_GetLastError
0x18007c8af  nop     dword ptr [rax+rax+00h]
0x18007c8b4  lea     rdx, aExitCleanupEve; "Exit cleanup event creation failed: Sta"...
0x18007c8bb  jmp     loc_18007C777
0x18007c8c0  mov     rdx, cs:qword_1800CBF78; hObject
0x18007c8c7  lea     r8, ClatMgrExitCallback; Callback
0x18007c8ce  mov     [rsp+90h+dwFlags], 0; dwFlags
0x18007c8d6  lea     rcx, qword_1800CBF80; phNewWaitObject
0x18007c8dd  mov     r9, rsi; Context
0x18007c8e0  mov     [rsp+90h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18007c8e8  call    cs:__imp_RegisterWaitForSingleObject
0x18007c8ef  nop     dword ptr [rax+rax+00h]
0x18007c8f4  test    eax, eax
0x18007c8f6  jnz     short loc_18007C910
0x18007c8f8  call    cs:__imp_GetLastError
0x18007c8ff  nop     dword ptr [rax+rax+00h]
0x18007c904  lea     rdx, aFailedToRegist_3; "Failed to register service exit callbac"...
0x18007c90b  jmp     loc_18007C777
0x18007c910  lea     rdx, aServiceExitCal; "Service exit callback registered succes"...
0x18007c917  mov     ecx, 4000000h
0x18007c91c  call    EventWrite0
0x18007c921  lea     rcx, xmmword_1800CBFE0
0x18007c928  call    ClatMgrRegisterNotificationHandlers
0x18007c92d  test    eax, eax
0x18007c92f  jz      short loc_18007C93D
0x18007c931  lea     rdx, aClatmgrregiste_0; "ClatMgrRegisterNotificationHandlers fai"...
0x18007c938  jmp     loc_18007C777
0x18007c93d  mov     cs:byte_1800CBFD8, 1
0x18007c944  mov     rcx, cs:g_ClatMgrStartCompleteEvent; hEvent
0x18007c94b  call    cs:__imp_SetEvent
0x18007c952  nop     dword ptr [rax+rax+00h]
0x18007c957  mov     r8d, 5B4h
0x18007c95d  lea     rdx, aOnecoreuapNetN_12; "onecoreuap\\net\\netio\\iphlpsvc\\clatm"...
0x18007c964  lea     rcx, aClatmgrinitial; "ClatMgrInitialize"
0x18007c96b  mov     rsi, [rsp+90h+arg_0]
0x18007c973  add     rsp, 90h
0x18007c97a  pop     rbp
0x18007c97b  jmp     DereferenceServiceEx
```
