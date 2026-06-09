# NlmHandlerShutdown

- ea: `0x1800be258`
- end: `0x1800be43d`
- name: `NlmHandlerShutdown`
- size: `485`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800bdd04`
- `0x1800df9c0`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x1800b40a0`
- `0x1800be258`
- `0x1800e1c7c`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800be2dd`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800be2dd`
- `ntdll!RtlNtStatusToDosError` at `0x1800be2e5`
- `ntdll!RtlNtStatusToDosError` at `0x1800be2e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be375`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be3de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be375`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be3de`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800be358`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800be358`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800be368`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800be368`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800be3b4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800be3b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800be3c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800be3c1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800be290`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800be290`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800be400`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800be400`

## pseudocode

```c
double NlmHandlerShutdown()
{
  double result; // xmm0_8
  HRESULT v1; // eax
  struct _LIST_ENTRY *v2; // rcx
  NTSTATUS v3; // eax
  signed int v4; // eax
  bool v5; // sf
  struct _LIST_ENTRY *v6; // rcx

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    result = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 199, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids);
  v1 = CoInitializeEx(0, 0);
  if ( v1 >= 0 )
  {
    if ( !g_WnfSubscription )
      goto LABEL_15;
    v3 = RtlUnsubscribeWnfNotificationWaitForCompletion();
    v4 = RtlNtStatusToDosError(v3);
    v5 = v4 < 0;
    if ( v4 > 0 )
    {
      v4 = (unsigned __int16)v4 | 0x80070000;
      v5 = v4 < 0;
    }
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        result = WPP_SF_d(
                   WPP_GLOBAL_Control[1].Flink,
                   201,
                   &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids,
                   (unsigned int)v4);
      }
    }
    else
    {
LABEL_15:
      g_WnfSubscription = 0;
      g_CostedNetworkSettingsInitialized = 0;
      if ( g_hNotifySinkThread )
      {
        SetEvent(g_hNotifyThreadStopEvent);
        WaitForSingleObject(g_hNotifySinkThread, 0xFFFFFFFF);
        CloseHandle(g_hNotifySinkThread);
        g_hNotifySinkThread = 0;
      }
      if ( g_hNotifyThreadStopEvent )
      {
        CloseHandle(g_hNotifyThreadStopEvent);
        g_hNotifyThreadStopEvent = 0;
      }
      if ( g_tpNetworkChangeWait )
      {
        WaitForThreadpoolWaitCallbacks(g_tpNetworkChangeWait, 1);
        CloseThreadpoolWait(g_tpNetworkChangeWait);
        g_tpNetworkChangeWait = 0;
      }
      v6 = (struct _LIST_ENTRY *)g_NetworkChangeEvent;
      if ( g_NetworkChangeEvent )
      {
        CloseHandle(g_NetworkChangeEvent);
        g_NetworkChangeEvent = 0;
      }
      NlmNetworkListFree(v6);
      VpnCriticalSectionDestroy(&g_CsNlmNetwork);
    }
    CoUninitialize();
    goto LABEL_25;
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    result = WPP_SF_d(
               WPP_GLOBAL_Control[1].Flink,
               200,
               &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids,
               (unsigned int)v1);
LABEL_25:
    v2 = WPP_GLOBAL_Control;
  }
  g_NlmHandlerInitialized = 0;
  if ( v2 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v2[1].Blink) & 8) != 0 )
    return WPP_SF_(v2[1].Flink, 202, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1800be258  push    rdi
0x1800be25a  sub     rsp, 20h
0x1800be25e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be265  lea     rdi, WPP_GLOBAL_Control
0x1800be26c  cmp     rcx, rdi
0x1800be26f  jz      short loc_1800BE28C
0x1800be271  test    byte ptr [rcx+1Ch], 8
0x1800be275  jz      short loc_1800BE28C
0x1800be277  mov     rcx, [rcx+10h]
0x1800be27b  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800be282  mov     edx, 0C7h
0x1800be287  call    WPP_SF_
0x1800be28c  xor     edx, edx; dwCoInit
0x1800be28e  xor     ecx, ecx; pvReserved
0x1800be290  call    cs:__imp_CoInitializeEx
0x1800be296  test    eax, eax
0x1800be298  jns     short loc_1800BE2D1
0x1800be29a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be2a1  cmp     rcx, rdi
0x1800be2a4  jz      loc_1800BE40D
0x1800be2aa  test    byte ptr [rcx+1Ch], 1
0x1800be2ae  jz      loc_1800BE40D
0x1800be2b4  mov     rcx, [rcx+10h]
0x1800be2b8  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800be2bf  mov     edx, 0C8h
0x1800be2c4  mov     r9d, eax
0x1800be2c7  call    WPP_SF_d
0x1800be2cc  jmp     loc_1800BE406
0x1800be2d1  mov     rcx, cs:?g_WnfSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * g_WnfSubscription
0x1800be2d8  test    rcx, rcx
0x1800be2db  jz      short loc_1800BE332
0x1800be2dd  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800be2e3  mov     ecx, eax; Status
0x1800be2e5  call    cs:__imp_RtlNtStatusToDosError
0x1800be2eb  test    eax, eax
0x1800be2ed  jle     short loc_1800BE2F9
0x1800be2ef  movzx   eax, ax
0x1800be2f2  or      eax, 80070000h
0x1800be2f7  test    eax, eax
0x1800be2f9  jns     short loc_1800BE332
0x1800be2fb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be302  cmp     rcx, rdi
0x1800be305  jz      loc_1800BE400
0x1800be30b  test    byte ptr [rcx+1Ch], 1
0x1800be30f  jz      loc_1800BE400
0x1800be315  mov     rcx, [rcx+10h]
0x1800be319  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800be320  mov     edx, 0C9h
0x1800be325  mov     r9d, eax
0x1800be328  call    WPP_SF_d
0x1800be32d  jmp     loc_1800BE400
0x1800be332  cmp     cs:?g_hNotifySinkThread@@3PEAXEA, 0; void * g_hNotifySinkThread
0x1800be33a  mov     cs:?g_WnfSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, 0; _WNF_USER_SUBSCRIPTION * g_WnfSubscription
0x1800be345  mov     cs:?g_CostedNetworkSettingsInitialized@@3HA, 0; int g_CostedNetworkSettingsInitialized
0x1800be34f  jz      short loc_1800BE386
0x1800be351  mov     rcx, cs:?g_hNotifyThreadStopEvent@@3PEAXEA; hEvent
0x1800be358  call    cs:__imp_SetEvent
0x1800be35e  mov     rcx, cs:?g_hNotifySinkThread@@3PEAXEA; hHandle
0x1800be365  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800be368  call    cs:__imp_WaitForSingleObject
0x1800be36e  mov     rcx, cs:?g_hNotifySinkThread@@3PEAXEA; hObject
0x1800be375  call    cs:__imp_CloseHandle
0x1800be37b  mov     cs:?g_hNotifySinkThread@@3PEAXEA, 0; void * g_hNotifySinkThread
0x1800be386  mov     rcx, cs:?g_hNotifyThreadStopEvent@@3PEAXEA; hObject
0x1800be38d  test    rcx, rcx
0x1800be390  jz      short loc_1800BE3A3
0x1800be392  call    cs:__imp_CloseHandle
0x1800be398  mov     cs:?g_hNotifyThreadStopEvent@@3PEAXEA, 0; void * g_hNotifyThreadStopEvent
0x1800be3a3  mov     rcx, cs:?g_tpNetworkChangeWait@@3PEAU_TP_WAIT@@EA; pwa
0x1800be3aa  test    rcx, rcx
0x1800be3ad  jz      short loc_1800BE3D2
0x1800be3af  mov     edx, 1; fCancelPendingCallbacks
0x1800be3b4  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800be3ba  mov     rcx, cs:?g_tpNetworkChangeWait@@3PEAU_TP_WAIT@@EA; pwa
0x1800be3c1  call    cs:__imp_CloseThreadpoolWait
0x1800be3c7  mov     cs:?g_tpNetworkChangeWait@@3PEAU_TP_WAIT@@EA, 0; _TP_WAIT * g_tpNetworkChangeWait
0x1800be3d2  mov     rcx, cs:?g_NetworkChangeEvent@@3PEAXEA; hObject
0x1800be3d9  test    rcx, rcx
0x1800be3dc  jz      short loc_1800BE3EF
0x1800be3de  call    cs:__imp_CloseHandle
0x1800be3e4  mov     cs:?g_NetworkChangeEvent@@3PEAXEA, 0; void * g_NetworkChangeEvent
0x1800be3ef  call    ?NlmNetworkListFree@@YAXPEAU_LIST_ENTRY@@@Z; NlmNetworkListFree(_LIST_ENTRY *)
0x1800be3f4  lea     rcx, ?g_CsNlmNetwork@@3UVPN_CRITICAL_SECTION_@@A; lpCriticalSection
0x1800be3fb  call    VpnCriticalSectionDestroy
0x1800be400  call    cs:__imp_CoUninitialize
0x1800be406  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be40d  mov     cs:?g_NlmHandlerInitialized@@3HA, 0; int g_NlmHandlerInitialized
0x1800be417  cmp     rcx, rdi
0x1800be41a  jz      short loc_1800BE437
0x1800be41c  test    byte ptr [rcx+1Ch], 8
0x1800be420  jz      short loc_1800BE437
0x1800be422  mov     rcx, [rcx+10h]
0x1800be426  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800be42d  mov     edx, 0CAh
0x1800be432  call    WPP_SF_
0x1800be437  add     rsp, 20h
0x1800be43b  pop     rdi
0x1800be43c  retn
```
