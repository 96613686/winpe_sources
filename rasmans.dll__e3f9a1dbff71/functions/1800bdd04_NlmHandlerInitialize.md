# NlmHandlerInitialize

- ea: `0x1800bdd04`
- end: `0x1800be250`
- name: `NlmHandlerInitialize`
- size: `1356`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800de2d8`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x1800b81fc`
- `0x1800bdd04`
- `0x1800be258`
- `0x1800e1be4`
- `0x1800e1e64`
- `0x1800e2d24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800bde7a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800bde7a`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800be189`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800be189`
- `ntdll!RtlNtStatusToDosError` at `0x1800be191`
- `ntdll!RtlNtStatusToDosError` at `0x1800be191`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bddf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bde8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdf79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdfed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be0e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bddf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bde8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdf79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdfed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be0e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bddce`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bdf67`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800be060`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bddce`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bdf67`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800be060`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800be050`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800be149`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800be050`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800be149`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800bdfdb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800be0d4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800bdfdb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800be0d4`

## string_xrefs

- `0x1800bdde2`: `onecoreuap\net\netio\vpnplugin\profilemgmt\nlm_handler.cpp`
- `0x1800bdf4c`: `VpnCriticalSectionCreate`

## pseudocode

```c
__int64 NlmHandlerInitialize()
{
  struct _LIST_ENTRY *v0; // rcx
  signed int LastError; // eax
  unsigned int v3; // ebx
  __int64 v4; // r8
  signed int v5; // eax
  int v6; // eax
  int v7; // eax
  unsigned int v8; // ecx
  __int64 v9; // r8
  signed int v10; // eax
  struct _TP_WAIT *ThreadpoolWait; // rax
  signed int v12; // eax
  signed int v13; // eax
  struct _TP_WAIT *v14; // rax
  signed int v15; // eax
  NTSTATUS v16; // eax
  signed int v17; // eax

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 188, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  if ( g_NlmHandlerInitialized != 1 )
  {
    g_NlmNetwork.Blink = &g_NlmNetwork;
    g_NlmNetwork.Flink = &g_NlmNetwork;
    g_lpfnConnChangeHandlerCB = (void (*)(enum NLM_CONNECTIVITY))int_NLMConnNotificationHandler;
    g_lpfnCostChangeHandlerCB = (void (*)(unsigned int))int_NLMCostNotificationHandler;
    g_lpfnNetworkChangeHandler = (int (*)(struct _LIST_ENTRY *))int_NetworkChangeHandlerCallback;
    g_lpfnNetworkConnectivityChangeHandler = int_NetworkConnectivityChangeHandlerCallback;
    g_hNotifyThreadStopEvent = CreateEventW(0, 0, 0, 0);
    if ( !g_hNotifyThreadStopEvent )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 190, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v3);
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      {
        v4 = 2142;
LABEL_17:
        TraceVpnWppErrorHRImpl(
          v3,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\nlm_handler.cpp",
          v4,
          "NlmHandlerInitialize");
        goto LABEL_77;
      }
      goto LABEL_77;
    }
    g_hNotifySinkThread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)ComThreadProc, 0, 0, &g_NotifySinkThreadId);
    if ( !g_hNotifySinkThread )
    {
      v5 = GetLastError();
      v3 = v5;
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 191, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v3);
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      {
        v4 = 2150;
        goto LABEL_17;
      }
LABEL_77:
      if ( (v3 & 0x80000000) == 0 )
        return 0;
LABEL_78:
      NlmHandlerShutdown();
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 198, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v3);
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorHRImpl(
          v3,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\nlm_handler.cpp",
          2202,
          "NlmHandlerInitialize");
      if ( (v3 & 0x1FFF0000) == 0x70000 )
        return (unsigned __int16)v3;
      return v3;
    }
    v6 = VpnCriticalSectionCreate(&g_CsNlmNetwork);
    v3 = v6;
    if ( v6 >= 0
      || WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      if ( v6 >= 0 )
        goto LABEL_38;
    }
    else
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 192, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, (unsigned int)v6);
      v6 = v3;
    }
    v7 = (v6 >> 16) & 0x1FFF;
    if ( v7 == 7 )
      v8 = (unsigned __int16)v3;
    else
      v8 = v3;
    if ( v8 )
    {
      v9 = v3;
      if ( v7 == 7 )
        v9 = (unsigned __int16)v3;
      VpnReportError("NlmHandlerInitialize", "VpnCriticalSectionCreate", v9);
      goto LABEL_78;
    }
LABEL_38:
    g_NetworkChangeEvent = CreateEventW(0, 0, 0, 0);
    if ( g_NetworkChangeEvent )
    {
      ThreadpoolWait = CreateThreadpoolWait((PTP_WAIT_CALLBACK)int_NlmNetworkChangeHandler, 0, 0);
      g_tpNetworkChangeWait = ThreadpoolWait;
      if ( ThreadpoolWait )
      {
        SetThreadpoolWait(ThreadpoolWait, g_NetworkChangeEvent, 0);
        g_NetworkConnectivityChangeEvent = CreateEventW(0, 0, 0, 0);
        if ( g_NetworkConnectivityChangeEvent )
        {
          v14 = CreateThreadpoolWait((PTP_WAIT_CALLBACK)int_NlmNetworkConnectivityChangeHandler, 0, 0);
          g_tpNetworkConnectivityChangeWait = v14;
          if ( v14 )
          {
            SetThreadpoolWait(v14, g_NetworkConnectivityChangeEvent, 0);
            v16 = RtlSubscribeWnfStateChangeNotification(
                    &g_WnfSubscription,
                    WNF_ENTR_CONNECTIVITY_POLICY_VALUE_CHANGED,
                    0,
                    NlmHandlerCostPolicyUpdate,
                    0,
                    0,
                    0,
                    0);
            v17 = RtlNtStatusToDosError(v16);
            v3 = v17;
            if ( v17 > 0 )
              v3 = (unsigned __int16)v17 | 0x80070000;
            if ( (v3 & 0x80000000) != 0 )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 197, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v3);
              }
              goto LABEL_78;
            }
            g_CostedNetworkSettingsInitialized = 0;
            goto LABEL_77;
          }
          v15 = GetLastError();
          v3 = v15;
          if ( v15 > 0 )
            v3 = (unsigned __int16)v15 | 0x80070000;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 196, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v3);
          }
          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          {
            v4 = 2175;
            goto LABEL_17;
          }
        }
        else
        {
          v13 = GetLastError();
          v3 = v13;
          if ( v13 > 0 )
            v3 = (unsigned __int16)v13 | 0x80070000;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 195, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v3);
          }
          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          {
            v4 = 2170;
            goto LABEL_17;
          }
        }
      }
      else
      {
        v12 = GetLastError();
        v3 = v12;
        if ( v12 > 0 )
          v3 = (unsigned __int16)v12 | 0x80070000;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 194, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v3);
        }
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        {
          v4 = 2165;
          goto LABEL_17;
        }
      }
    }
    else
    {
      v10 = GetLastError();
      v3 = v10;
      if ( v10 > 0 )
        v3 = (unsigned __int16)v10 | 0x80070000;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 193, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v3);
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      {
        v4 = 2160;
        goto LABEL_17;
      }
    }
    goto LABEL_77;
  }
  if ( v0 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v0[1].Blink) & 8) != 0 )
    WPP_SF_(v0[1].Flink, 189, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1800bdd04  push    rbx
0x1800bdd06  push    rbp
0x1800bdd07  push    r12
0x1800bdd09  push    r13
0x1800bdd0b  push    r14
0x1800bdd0d  push    r15
0x1800bdd0f  sub     rsp, 48h
0x1800bdd13  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdd1a  lea     rbp, WPP_GLOBAL_Control
0x1800bdd21  lea     r14, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800bdd28  cmp     rcx, rbp
0x1800bdd2b  jz      short loc_1800BDD4B
0x1800bdd2d  test    byte ptr [rcx+1Ch], 8
0x1800bdd31  jz      short loc_1800BDD4B
0x1800bdd33  mov     rcx, [rcx+10h]
0x1800bdd37  mov     edx, 0BCh
0x1800bdd3c  mov     r8, r14
0x1800bdd3f  call    WPP_SF_
0x1800bdd44  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdd4b  cmp     cs:?g_NlmHandlerInitialized@@3HA, 1; int g_NlmHandlerInitialized
0x1800bdd52  jnz     short loc_1800BDD77
0x1800bdd54  cmp     rcx, rbp
0x1800bdd57  jz      short loc_1800BDD70
0x1800bdd59  test    byte ptr [rcx+1Ch], 8
0x1800bdd5d  jz      short loc_1800BDD70
0x1800bdd5f  mov     rcx, [rcx+10h]
0x1800bdd63  mov     edx, 0BDh
0x1800bdd68  mov     r8, r14
0x1800bdd6b  call    WPP_SF_
0x1800bdd70  xor     eax, eax
0x1800bdd72  jmp     loc_1800BE241
0x1800bdd77  lea     rax, ?g_NlmNetwork@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_NlmNetwork
0x1800bdd7e  xor     r9d, r9d; lpName
0x1800bdd81  mov     cs:?g_NlmNetwork@@3U_LIST_ENTRY@@A.Blink, rax; _LIST_ENTRY g_NlmNetwork ...
0x1800bdd88  xor     r8d, r8d; bInitialState
0x1800bdd8b  mov     cs:?g_NlmNetwork@@3U_LIST_ENTRY@@A.Flink, rax; _LIST_ENTRY g_NlmNetwork ...
0x1800bdd92  xor     edx, edx; bManualReset
0x1800bdd94  lea     rax, ?int_NLMConnNotificationHandler@@YAXW4NLM_CONNECTIVITY@@@Z; int_NLMConnNotificationHandler(NLM_CONNECTIVITY)
0x1800bdd9b  xor     ecx, ecx; lpEventAttributes
0x1800bdd9d  mov     cs:?g_lpfnConnChangeHandlerCB@@3P6AXW4NLM_CONNECTIVITY@@@ZEA, rax; void (*g_lpfnConnChangeHandlerCB)(NLM_CONNECTIVITY)
0x1800bdda4  lea     rax, ?int_NLMCostNotificationHandler@@YAXK@Z; int_NLMCostNotificationHandler(ulong)
0x1800bddab  mov     cs:?g_lpfnCostChangeHandlerCB@@3P6AXK@ZEA, rax; void (*g_lpfnCostChangeHandlerCB)(ulong)
0x1800bddb2  lea     rax, ?int_NetworkChangeHandlerCallback@@YAHPEAU_LIST_ENTRY@@@Z; int_NetworkChangeHandlerCallback(_LIST_ENTRY *)
0x1800bddb9  mov     cs:?g_lpfnNetworkChangeHandler@@3P6AHPEAU_LIST_ENTRY@@@ZEA, rax; int (*g_lpfnNetworkChangeHandler)(_LIST_ENTRY *)
0x1800bddc0  lea     rax, ?int_NetworkConnectivityChangeHandlerCallback@@YAXXZ; int_NetworkConnectivityChangeHandlerCallback(void)
0x1800bddc7  mov     cs:?g_lpfnNetworkConnectivityChangeHandler@@3P6AXXZEA, rax; void (*g_lpfnNetworkConnectivityChangeHandler)(void)
0x1800bddce  call    cs:__imp_CreateEventW
0x1800bddd4  mov     cs:?g_hNotifyThreadStopEvent@@3PEAXEA, rax; void * g_hNotifyThreadStopEvent
0x1800bdddb  lea     r12, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800bdde2  lea     r13, aOnecoreuapNetN; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800bdde9  lea     r15, aNlmhandlerinit; "NlmHandlerInitialize"
0x1800bddf0  test    rax, rax
0x1800bddf3  jnz     short loc_1800BDE58
0x1800bddf5  call    cs:__imp_GetLastError
0x1800bddfb  mov     ebx, eax
0x1800bddfd  test    eax, eax
0x1800bddff  jle     short loc_1800BDE0A
0x1800bde01  movzx   ebx, ax
0x1800bde04  or      ebx, 80070000h
0x1800bde0a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bde11  cmp     rcx, rbp
0x1800bde14  jz      short loc_1800BDE30
0x1800bde16  test    byte ptr [rcx+1Ch], 1
0x1800bde1a  jz      short loc_1800BDE30
0x1800bde1c  mov     rcx, [rcx+10h]
0x1800bde20  mov     edx, 0BEh
0x1800bde25  mov     r9d, ebx
0x1800bde28  mov     r8, r14
0x1800bde2b  call    WPP_SF_d
0x1800bde30  mov     rcx, r12
0x1800bde33  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800bde38  test    al, al
0x1800bde3a  jz      loc_1800BE1DC
0x1800bde40  mov     r8d, 85Eh
0x1800bde46  mov     r9, r15
0x1800bde49  mov     rdx, r13
0x1800bde4c  mov     ecx, ebx
0x1800bde4e  call    TraceVpnWppErrorHRImpl
0x1800bde53  jmp     loc_1800BE1DC
0x1800bde58  lea     rax, ?g_NotifySinkThreadId@@3KA; ulong g_NotifySinkThreadId
0x1800bde5f  xor     r9d, r9d; lpParameter
0x1800bde62  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x1800bde67  lea     r8, ?ComThreadProc@@YAKPEAX@Z; lpStartAddress
0x1800bde6e  xor     edx, edx; dwStackSize
0x1800bde70  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x1800bde78  xor     ecx, ecx; lpThreadAttributes
0x1800bde7a  call    cs:__imp_CreateThread
0x1800bde80  mov     cs:?g_hNotifySinkThread@@3PEAXEA, rax; void * g_hNotifySinkThread
0x1800bde87  test    rax, rax
0x1800bde8a  jnz     short loc_1800BDEE2
0x1800bde8c  call    cs:__imp_GetLastError
0x1800bde92  mov     ebx, eax
0x1800bde94  test    eax, eax
0x1800bde96  jle     short loc_1800BDEA1
0x1800bde98  movzx   ebx, ax
0x1800bde9b  or      ebx, 80070000h
0x1800bdea1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdea8  cmp     rcx, rbp
0x1800bdeab  jz      short loc_1800BDEC7
0x1800bdead  test    byte ptr [rcx+1Ch], 1
0x1800bdeb1  jz      short loc_1800BDEC7
0x1800bdeb3  mov     rcx, [rcx+10h]
0x1800bdeb7  mov     edx, 0BFh
0x1800bdebc  mov     r9d, ebx
0x1800bdebf  mov     r8, r14
0x1800bdec2  call    WPP_SF_d
0x1800bdec7  mov     rcx, r12
0x1800bdeca  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800bdecf  test    al, al
0x1800bded1  jz      loc_1800BE1DC
0x1800bded7  mov     r8d, 866h
0x1800bdedd  jmp     loc_1800BDE46
0x1800bdee2  lea     rcx, ?g_CsNlmNetwork@@3UVPN_CRITICAL_SECTION_@@A; lpCriticalSection
0x1800bdee9  call    VpnCriticalSectionCreate
0x1800bdeee  mov     ebx, eax
0x1800bdef0  test    eax, eax
0x1800bdef2  jns     short loc_1800BDF1E
0x1800bdef4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdefb  cmp     rcx, rbp
0x1800bdefe  jz      short loc_1800BDF1E
0x1800bdf00  test    byte ptr [rcx+1Ch], 1
0x1800bdf04  jz      short loc_1800BDF1E
0x1800bdf06  mov     rcx, [rcx+10h]
0x1800bdf0a  mov     edx, 0C0h
0x1800bdf0f  mov     r9d, eax
0x1800bdf12  mov     r8, r14
0x1800bdf15  call    WPP_SF_d
0x1800bdf1a  mov     eax, ebx
0x1800bdf1c  jmp     short loc_1800BDF22
0x1800bdf1e  test    ebx, ebx
0x1800bdf20  jns     short loc_1800BDF5D
0x1800bdf22  sar     eax, 10h
0x1800bdf25  and     eax, 1FFFh
0x1800bdf2a  cmp     eax, 7
0x1800bdf2d  jnz     short loc_1800BDF36
0x1800bdf2f  movzx   ecx, bx
0x1800bdf32  mov     edx, ecx
0x1800bdf34  jmp     short loc_1800BDF3B
0x1800bdf36  mov     ecx, ebx
0x1800bdf38  movzx   edx, bx
0x1800bdf3b  test    ecx, ecx
0x1800bdf3d  jz      short loc_1800BDF5D
0x1800bdf3f  cmp     eax, 7
0x1800bdf42  mov     r8d, ebx
0x1800bdf45  mov     rcx, r15
0x1800bdf48  cmovz   r8d, edx
0x1800bdf4c  lea     rdx, aVpncriticalsec_4; "VpnCriticalSectionCreate"
0x1800bdf53  call    VpnReportError
0x1800bdf58  jmp     loc_1800BE1E0
0x1800bdf5d  xor     r9d, r9d; lpName
0x1800bdf60  xor     r8d, r8d; bInitialState
0x1800bdf63  xor     edx, edx; bManualReset
0x1800bdf65  xor     ecx, ecx; lpEventAttributes
0x1800bdf67  call    cs:__imp_CreateEventW
0x1800bdf6d  mov     cs:?g_NetworkChangeEvent@@3PEAXEA, rax; void * g_NetworkChangeEvent
0x1800bdf74  test    rax, rax
0x1800bdf77  jnz     short loc_1800BDFCF
0x1800bdf79  call    cs:__imp_GetLastError
0x1800bdf7f  mov     ebx, eax
0x1800bdf81  test    eax, eax
0x1800bdf83  jle     short loc_1800BDF8E
0x1800bdf85  movzx   ebx, ax
0x1800bdf88  or      ebx, 80070000h
0x1800bdf8e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdf95  cmp     rcx, rbp
0x1800bdf98  jz      short loc_1800BDFB4
0x1800bdf9a  test    byte ptr [rcx+1Ch], 1
0x1800bdf9e  jz      short loc_1800BDFB4
0x1800bdfa0  mov     rcx, [rcx+10h]
0x1800bdfa4  mov     edx, 0C1h
0x1800bdfa9  mov     r9d, ebx
0x1800bdfac  mov     r8, r14
0x1800bdfaf  call    WPP_SF_d
0x1800bdfb4  mov     rcx, r12
0x1800bdfb7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800bdfbc  test    al, al
0x1800bdfbe  jz      loc_1800BE1DC
0x1800bdfc4  mov     r8d, 870h
0x1800bdfca  jmp     loc_1800BDE46
0x1800bdfcf  xor     r8d, r8d; pcbe
0x1800bdfd2  lea     rcx, ?int_NlmNetworkChangeHandler@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800bdfd9  xor     edx, edx; pv
0x1800bdfdb  call    cs:__imp_CreateThreadpoolWait
0x1800bdfe1  mov     cs:?g_tpNetworkChangeWait@@3PEAU_TP_WAIT@@EA, rax; _TP_WAIT * g_tpNetworkChangeWait
0x1800bdfe8  test    rax, rax
0x1800bdfeb  jnz     short loc_1800BE043
0x1800bdfed  call    cs:__imp_GetLastError
0x1800bdff3  mov     ebx, eax
0x1800bdff5  test    eax, eax
0x1800bdff7  jle     short loc_1800BE002
0x1800bdff9  movzx   ebx, ax
0x1800bdffc  or      ebx, 80070000h
0x1800be002  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be009  cmp     rcx, rbp
0x1800be00c  jz      short loc_1800BE028
0x1800be00e  test    byte ptr [rcx+1Ch], 1
0x1800be012  jz      short loc_1800BE028
0x1800be014  mov     rcx, [rcx+10h]
0x1800be018  mov     edx, 0C2h
0x1800be01d  mov     r9d, ebx
0x1800be020  mov     r8, r14
0x1800be023  call    WPP_SF_d
0x1800be028  mov     rcx, r12
0x1800be02b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800be030  test    al, al
0x1800be032  jz      loc_1800BE1DC
0x1800be038  mov     r8d, 875h
0x1800be03e  jmp     loc_1800BDE46
0x1800be043  mov     rdx, cs:?g_NetworkChangeEvent@@3PEAXEA; h
0x1800be04a  xor     r8d, r8d; pftTimeout
0x1800be04d  mov     rcx, rax; pwa
0x1800be050  call    cs:__imp_SetThreadpoolWait
0x1800be056  xor     r9d, r9d; lpName
0x1800be059  xor     r8d, r8d; bInitialState
0x1800be05c  xor     edx, edx; bManualReset
0x1800be05e  xor     ecx, ecx; lpEventAttributes
0x1800be060  call    cs:__imp_CreateEventW
0x1800be066  mov     cs:?g_NetworkConnectivityChangeEvent@@3PEAXEA, rax; void * g_NetworkConnectivityChangeEvent
0x1800be06d  test    rax, rax
0x1800be070  jnz     short loc_1800BE0C8
0x1800be072  call    cs:__imp_GetLastError
0x1800be078  mov     ebx, eax
0x1800be07a  test    eax, eax
0x1800be07c  jle     short loc_1800BE087
0x1800be07e  movzx   ebx, ax
0x1800be081  or      ebx, 80070000h
0x1800be087  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be08e  cmp     rcx, rbp
0x1800be091  jz      short loc_1800BE0AD
0x1800be093  test    byte ptr [rcx+1Ch], 1
0x1800be097  jz      short loc_1800BE0AD
0x1800be099  mov     rcx, [rcx+10h]
0x1800be09d  mov     edx, 0C3h
0x1800be0a2  mov     r9d, ebx
0x1800be0a5  mov     r8, r14
0x1800be0a8  call    WPP_SF_d
0x1800be0ad  mov     rcx, r12
0x1800be0b0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800be0b5  test    al, al
0x1800be0b7  jz      loc_1800BE1DC
0x1800be0bd  mov     r8d, 87Ah
0x1800be0c3  jmp     loc_1800BDE46
0x1800be0c8  xor     r8d, r8d; pcbe
0x1800be0cb  lea     rcx, ?int_NlmNetworkConnectivityChangeHandler@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800be0d2  xor     edx, edx; pv
0x1800be0d4  call    cs:__imp_CreateThreadpoolWait
0x1800be0da  mov     cs:?g_tpNetworkConnectivityChangeWait@@3PEAU_TP_WAIT@@EA, rax; _TP_WAIT * g_tpNetworkConnectivityChangeWait
0x1800be0e1  test    rax, rax
0x1800be0e4  jnz     short loc_1800BE13C
0x1800be0e6  call    cs:__imp_GetLastError
0x1800be0ec  mov     ebx, eax
0x1800be0ee  test    eax, eax
0x1800be0f0  jle     short loc_1800BE0FB
0x1800be0f2  movzx   ebx, ax
0x1800be0f5  or      ebx, 80070000h
0x1800be0fb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be102  cmp     rcx, rbp
0x1800be105  jz      short loc_1800BE121
0x1800be107  test    byte ptr [rcx+1Ch], 1
0x1800be10b  jz      short loc_1800BE121
0x1800be10d  mov     rcx, [rcx+10h]
0x1800be111  mov     edx, 0C4h
0x1800be116  mov     r9d, ebx
0x1800be119  mov     r8, r14
0x1800be11c  call    WPP_SF_d
0x1800be121  mov     rcx, r12
0x1800be124  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800be129  test    al, al
0x1800be12b  jz      loc_1800BE1DC
0x1800be131  mov     r8d, 87Fh
0x1800be137  jmp     loc_1800BDE46
0x1800be13c  mov     rdx, cs:?g_NetworkConnectivityChangeEvent@@3PEAXEA; h
0x1800be143  xor     r8d, r8d; pftTimeout
0x1800be146  mov     rcx, rax; pwa
0x1800be149  call    cs:__imp_SetThreadpoolWait
0x1800be14f  mov     rdx, cs:WNF_ENTR_CONNECTIVITY_POLICY_VALUE_CHANGED
0x1800be156  lea     r9, NlmHandlerCostPolicyUpdate
0x1800be15d  mov     [rsp+78h+var_40], 0
0x1800be165  lea     rcx, ?g_WnfSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * g_WnfSubscription
0x1800be16c  mov     [rsp+78h+var_48], 0
0x1800be174  xor     r8d, r8d
0x1800be177  mov     [rsp+78h+lpThreadId], 0
0x1800be180  mov     qword ptr [rsp+78h+dwCreationFlags], 0
0x1800be189  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800be18f  mov     ecx, eax; Status
0x1800be191  call    cs:__imp_RtlNtStatusToDosError
0x1800be197  mov     ebx, eax
0x1800be199  test    eax, eax
0x1800be19b  jle     short loc_1800BE1A6
0x1800be19d  movzx   ebx, ax
0x1800be1a0  or      ebx, 80070000h
0x1800be1a6  test    ebx, ebx
0x1800be1a8  jns     short loc_1800BE1D2
0x1800be1aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be1b1  cmp     rcx, rbp
0x1800be1b4  jz      short loc_1800BE1E0
0x1800be1b6  test    byte ptr [rcx+1Ch], 1
0x1800be1ba  jz      short loc_1800BE1E0
0x1800be1bc  mov     rcx, [rcx+10h]
0x1800be1c0  mov     edx, 0C5h
  ... truncated ...
```
