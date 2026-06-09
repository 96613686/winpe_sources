# ComThreadProc(void *)

- ea: `0x1800af660`
- end: `0x1800b031e`
- name: `?ComThreadProc@@YAKPEAX@Z`
- size: `3262`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003c5c`
- `0x180005e0c`
- `0x180005e34`
- `0x180032508`
- `0x1800af660`
- `0x1800b249c`
- `0x1800b414c`
- `0x1800b81fc`
- `0x1800e2d24`
- `0x1800e7206`
- `0x1800e7260`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af7a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af83d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af8d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0123`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af7a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af83d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af8d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0123`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800afd49`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800b00d5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800afd49`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800b00d5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b0089`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b0089`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800af97d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800afe62`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800af97d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800afe62`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800af735`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800af735`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800b02b7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800b02b7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b029e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b02ac`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b029e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800b02ac`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800af792`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800af792`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800af82e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800af82e`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800af8c6`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800b00bd`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800af8c6`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800b00bd`

## string_xrefs

- `0x1800af808`: `onecoreuap\net\netio\vpnplugin\profilemgmt\nlm_handler.cpp`
- `0x1800af8a4`: `onecoreuap\net\netio\vpnplugin\profilemgmt\nlm_handler.cpp`
- `0x1800af93a`: `onecoreuap\net\netio\vpnplugin\profilemgmt\nlm_handler.cpp`
- `0x1800b0186`: `onecoreuap\net\netio\vpnplugin\profilemgmt\nlm_handler.cpp`
- `0x1800af782`: `ServicesActive`
- `0x1800af7fb`: `ComThreadProc`
- `0x1800af897`: `ComThreadProc`
- `0x1800af92d`: `ComThreadProc`
- `0x1800b0179`: `ComThreadProc`

## pseudocode

```c
__int64 __fastcall ComThreadProc(PVOID Parameter)
{
  SC_HANDLE v1; // r14
  struct IConnectionPoint *v2; // rsi
  struct IConnectionPoint *v3; // r13
  struct IConnectionPoint *v4; // r15
  _DWORD *v5; // rdi
  _DWORD *v6; // r12
  _DWORD *v7; // rbx
  HRESULT v8; // eax
  SC_HANDLE v9; // rax
  signed int LastError; // eax
  unsigned int v11; // ebx
  SC_HANDLE v12; // rax
  signed int v13; // eax
  unsigned int v14; // ebx
  int v15; // r14d
  signed int v16; // eax
  unsigned int v17; // ebx
  HRESULT Instance; // eax
  struct _LIST_ENTRY *v19; // rcx
  __int64 v20; // rdx
  int v21; // eax
  struct _LIST_ENTRY *v22; // rcx
  __int64 v23; // rdx
  int v24; // eax
  struct _LIST_ENTRY *v25; // rcx
  __int64 v26; // rdx
  struct _LIST_ENTRY *v27; // rcx
  _QWORD *v28; // rax
  int v29; // ebx
  int v30; // ebx
  HRESULT v31; // eax
  unsigned int ConnectionPoints; // eax
  unsigned int v33; // r14d
  struct _LIST_ENTRY *v34; // rcx
  __int64 v35; // rdx
  unsigned int v36; // eax
  unsigned int v37; // ebx
  struct _LIST_ENTRY *v38; // rcx
  __int64 v39; // rdx
  unsigned int v40; // eax
  unsigned int v41; // esi
  unsigned int v42; // eax
  struct _LIST_ENTRY *v43; // rcx
  __int64 v44; // rdx
  unsigned int v45; // eax
  unsigned int v46; // ebx
  signed int v47; // eax
  unsigned int v48; // ebx
  SC_HANDLE v50; // [rsp+38h] [rbp-C8h]
  _DWORD *v51; // [rsp+40h] [rbp-C0h]
  int v52; // [rsp+48h] [rbp-B8h]
  __int16 v53; // [rsp+4Ch] [rbp-B4h] BYREF
  struct INetworkListManager *ppv; // [rsp+50h] [rbp-B0h] BYREF
  int v55; // [rsp+58h] [rbp-A8h]
  int v56; // [rsp+5Ch] [rbp-A4h]
  unsigned int v57; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v58; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v59; // [rsp+68h] [rbp-98h] BYREF
  struct IConnectionPoint *v60; // [rsp+70h] [rbp-90h] BYREF
  int v61; // [rsp+78h] [rbp-88h] BYREF
  struct IConnectionPoint *v62; // [rsp+80h] [rbp-80h] BYREF
  struct IConnectionPoint *v63; // [rsp+88h] [rbp-78h] BYREF
  SC_HANDLE hService; // [rsp+90h] [rbp-70h]
  __int64 v65; // [rsp+98h] [rbp-68h] BYREF
  __int64 v66; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v67; // [rsp+A8h] [rbp-58h] BYREF
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+B0h] [rbp-50h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 152, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids);
  v1 = 0;
  v53 = 0;
  v2 = 0;
  v60 = 0;
  v3 = 0;
  v62 = 0;
  v63 = 0;
  v4 = 0;
  ppv = 0;
  v5 = 0;
  v65 = 0;
  v6 = 0;
  v66 = 0;
  v7 = 0;
  v67 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  hService = 0;
  memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  pNotifyBuffer.pContext = 0;
  v61 = 1;
  pNotifyBuffer.dwVersion = 1;
  g_NlmHandlerInitialized = 1;
  pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)NlmTriggerSvcNotify;
  v8 = CoInitializeEx(0, 4u);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 153, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, (unsigned int)v8);
    }
    goto LABEL_185;
  }
  v9 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v50 = v9;
  v1 = v9;
  if ( !v9 )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 154, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v11);
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        v11,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\nlm_handler.cpp",
        1683,
        "ComThreadProc");
    goto LABEL_16;
  }
  v12 = OpenServiceW(v9, L"NetProfm", 4u);
  hService = v12;
  if ( !v12 )
  {
    v13 = GetLastError();
    v14 = v13;
    if ( v13 > 0 )
      v14 = (unsigned __int16)v13 | 0x80070000;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 155, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v14);
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    {
      TraceVpnWppErrorHRImpl(
        v14,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\nlm_handler.cpp",
        1686,
        "ComThreadProc");
      v7 = 0;
      goto LABEL_184;
    }
LABEL_16:
    v7 = 0;
    goto LABEL_184;
  }
  v15 = 0;
  if ( NotifyServiceStatusChangeW(v12, 0xCu, &pNotifyBuffer) )
  {
    v16 = GetLastError();
    v17 = v16;
    if ( v16 > 0 )
      v17 = (unsigned __int16)v16 | 0x80070000;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 156, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v17);
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    {
      TraceVpnWppErrorHRImpl(
        v17,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\nlm_handler.cpp",
        1690,
        "ComThreadProc");
      v7 = 0;
      goto LABEL_183;
    }
    v1 = v50;
    goto LABEL_16;
  }
  Instance = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &IID_INetworkListManager, (LPVOID *)&ppv);
  if ( Instance < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_183;
    }
    v20 = 157;
    goto LABEL_39;
  }
  v21 = ((__int64 (__fastcall *)(struct INetworkListManager *, __int16 *))ppv->lpVtbl->get_IsConnectedToInternet)(
          ppv,
          &v53);
  if ( v21 >= 0 )
  {
    if ( !v21 && v53 == -1 )
      g_IsNlmInternetConnected = 1;
  }
  else if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
         && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 158, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, (unsigned int)v21);
  }
  NlmNetworksEnum(&g_NlmNetwork, &v61);
  if ( g_lpfnNetworkChangeHandler )
  {
    LODWORD(v7) = g_lpfnNetworkChangeHandler(&g_NlmNetwork);
LABEL_52:
    v22 = WPP_GLOBAL_Control;
    goto LABEL_53;
  }
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 159, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids);
    goto LABEL_52;
  }
LABEL_53:
  if ( !g_lpfnNetworkConnectivityChangeHandler )
  {
    if ( v22 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v22[1].Blink) & 4) == 0 )
      goto LABEL_63;
    v23 = 161;
LABEL_62:
    WPP_SF_(v22[1].Flink, v23, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids);
    goto LABEL_63;
  }
  if ( (_DWORD)v7 )
  {
    if ( v22 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v22[1].Blink) & 4) == 0 )
      goto LABEL_63;
    v23 = 160;
    goto LABEL_62;
  }
  g_lpfnNetworkConnectivityChangeHandler();
LABEL_63:
  v5 = operator new(0x10u);
  if ( !v5 )
  {
    v5 = 0;
    goto LABEL_75;
  }
  *(_QWORD *)v5 = &CNetListManagerEventSink::`vftable';
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 210, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids);
  v5[2] = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 211, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids);
  v24 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, __int64 *))v5)(v5, &IID_IUnknown, &v65);
  if ( v24 < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_75;
    }
    v26 = 162;
    goto LABEL_74;
  }
  v6 = operator new(0x10u);
  if ( !v6 )
  {
    v6 = 0;
    goto LABEL_75;
  }
  v6[2] = 0;
  *(_QWORD *)v6 = &CNetCostManagerEventSink::`vftable';
  v27 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 225, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids);
      v27 = WPP_GLOBAL_Control;
    }
    if ( v27 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v27[1].Blink) & 8) != 0 )
      WPP_SF_(v27[1].Flink, 226, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids);
  }
  v24 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, __int64 *))v6)(v6, &IID_IUnknown, &v66);
  if ( v24 < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_75;
    }
    v26 = 163;
LABEL_74:
    WPP_SF_d(v25[1].Flink, v26, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, (unsigned int)v24);
LABEL_75:
    v7 = 0;
    goto LABEL_183;
  }
  v28 = operator new(0x10u);
  v51 = v28;
  v7 = v28;
  if ( !v28 )
  {
    v7 = 0;
    goto LABEL_183;
  }
  *v28 = &CNetProfileEventSink::`vftable';
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 240, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids);
  v7[2] = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 241, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids);
  Instance = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, __int64 *))v7)(v7, &IID_IUnknown, &v67);
  if ( Instance < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_183;
    }
    v20 = 164;
LABEL_39:
    WPP_SF_d(v19[1].Flink, v20, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, (unsigned int)Instance);
    goto LABEL_183;
  }
  v29 = 0;
  v55 = 0;
  v52 = 0;
  v56 = 0;
  if ( !WaitForSingleObjectEx(g_hNotifyThreadStopEvent, 0xFFFFFFFF, 1) )
    goto LABEL_182;
  while ( pNotifyBuffer.ServiceStatus.dwCurrentState != 4 )
  {
LABEL_156:
    if ( NotifyServiceStatusChangeW(hService, 0xCu, &pNotifyBuffer) )
    {
      v47 = GetLastError();
      v48 = v47;
      if ( v47 > 0 )
        v48 = (unsigned __int16)v47 | 0x80070000;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 173, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v48);
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorHRImpl(
          v48,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\nlm_handler.cpp",
          1904,
          "ComThreadProc");
LABEL_169:
      v30 = v52;
      goto LABEL_170;
    }
    if ( !WaitForSingleObjectEx(g_hNotifyThreadStopEvent, 0xFFFFFFFF, 1) )
      goto LABEL_169;
  }
  while ( 1 )
  {
    if ( ppv )
    {
      ((void (__fastcall *)(struct INetworkListManager *))ppv->lpVtbl->Release)(ppv);
      ppv = 0;
    }
    if ( v15 == 1 )
    {
      ((void (__fastcall *)(struct IConnectionPoint *, _QWORD))v2->lpVtbl->Unadvise)(v2, v57);
      v15 = 0;
      v55 = 0;
    }
    if ( v2 )
    {
      ((void (__fastcall *)(struct IConnectionPoint *))v2->lpVtbl->Release)(v2);
      v2 = 0;
      v60 = 0;
    }
    if ( v29 == 1 )
    {
      ((void (__fastcall *)(struct IConnectionPoint *, _QWORD))v3->lpVtbl->Unadvise)(v3, v58);
      v30 = 0;
      v52 = 0;
    }
    else
    {
      v30 = v52;
    }
    if ( v3 )
    {
      ((void (__fastcall *)(struct IConnectionPoint *))v3->lpVtbl->Release)(v3);
      v3 = 0;
      v62 = 0;
    }
    if ( v56 == 1 )
    {
      ((void (__fastcall *)(struct IConnectionPoint *, _QWORD))v4->lpVtbl->Unadvise)(v4, v59);
      v56 = 0;
    }
    if ( v4 )
    {
      ((void (__fastcall *)(struct IConnectionPoint *))v4->lpVtbl->Release)(v4);
      v4 = 0;
      v63 = 0;
    }
    v31 = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &IID_INetworkListManager, (LPVOID *)&ppv);
    if ( v31 < 0 )
      break;
    ConnectionPoints = HrGetConnectionPoints(ppv, &IID_INetworkListManagerEvents, &v60);
    v33 = ConnectionPoints;
    if ( ConnectionPoints )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 2) != 0 )
      {
        v35 = 167;
        goto LABEL_125;
      }
    }
    else
    {
      ConnectionPoints = ((__int64 (__fastcall *)(struct IConnectionPoint *, __int64, unsigned int *))v60->lpVtbl->Advise)(
                           v60,
                           v65,
                           &v57);
      v33 = ConnectionPoints;
      if ( !ConnectionPoints )
      {
        v55 = 1;
        goto LABEL_126;
      }
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 2) != 0 )
      {
        v35 = 166;
LABEL_125:
        WPP_SF_d(v34[1].Flink, v35, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, ConnectionPoints);
      }
    }
LABEL_126:
    v36 = HrGetConnectionPoints(ppv, &IID_INetworkCostManagerEvents, &v62);
    v3 = v62;
    v37 = v36;
    if ( v36 )
    {
      v38 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 2) != 0 )
      {
        v39 = 169;
        goto LABEL_135;
      }
    }
    else
    {
      v36 = ((__int64 (__fastcall *)(struct IConnectionPoint *, __int64, unsigned int *))v62->lpVtbl->Advise)(
              v62,
              v66,
              &v58);
      v37 = v36;
      if ( !v36 )
      {
        v52 = 1;
        goto LABEL_136;
      }
      v38 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 2) != 0 )
      {
        v39 = 168;
LABEL_135:
        WPP_SF_d(v38[1].Flink, v39, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v36);
      }
    }
LABEL_136:
    v40 = HrGetConnectionPoints(ppv, &IID_INetworkEvents, &v63);
    v4 = v63;
    v41 = v40;
    if ( v40 )
    {
      v43 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 2) != 0 )
      {
        v44 = 171;
        goto LABEL_145;
      }
    }
    else
    {
      v42 = ((__int64 (__fastcall *)(struct IConnectionPoint *, __int64, unsigned int *))v63->lpVtbl->Advise)(
              v63,
              v67,
              &v59);
      v43 = WPP_GLOBAL_Control;
      v41 = v42;
      if ( !v42 )
      {
        v56 = 1;
        goto LABEL_146;
      }
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 2) != 0 )
      {
        v44 = 170;
LABEL_145:
        WPP_SF_d(v43[1].Flink, v44, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v41);
        v43 = WPP_GLOBAL_Control;
      }
    }
LABEL_146:
    v45 = v33;
    if ( v33 != -2147483638 )
      v45 = v37;
    v46 = v41;
    if ( v41 != -2147483638 )
      v46 = v45;
    if ( v43 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v43[1].Blink) & 4) != 0 )
      WPP_SF_ddd(v43[1].Flink, 172, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v46, v33, v41);
    if ( v46 != -2147483638 )
    {
      v2 = v60;
      v15 = v55;
      v29 = v52;
      goto LABEL_156;
    }
    Sleep(0xFAu);
    v2 = v60;
    v15 = v55;
    v29 = v52;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 165, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, (unsigned int)v31);
LABEL_170:
  if ( v15 == 1 )
    ((void (__fastcall *)(struct IConnectionPoint *, _QWORD))v2->lpVtbl->Unadvise)(v2, v57);
  if ( v2 )
    ((void (__fastcall *)(struct IConnectionPoint *))v2->lpVtbl->Release)(v2);
  if ( v30 == 1 )
    ((void (__fastcall *)(struct IConnectionPoint *, _QWORD))v3->lpVtbl->Unadvise)(v3, v58);
  if ( v3 )
    ((void (__fastcall *)(struct IConnectionPoint *))v3->lpVtbl->Release)(v3);
  if ( v56 == 1 )
    ((void (__fastcall *)(struct IConnectionPoint *, _QWORD))v4->lpVtbl->Unadvise)(v4, v59);
  if ( v4 )
    ((void (__fastcall *)(struct IConnectionPoint *))v4->lpVtbl->Release)(v4);
LABEL_182:
  v7 = v51;
LABEL_183:
  v1 = v50;
LABEL_184:
  LODWORD(v2) = 1;
LABEL_185:
  if ( ppv )
  {
    ((void (__fastcall *)(struct INetworkListManager *))ppv->lpVtbl->Release)(ppv);
    ppv = 0;
  }
  if ( v5 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v6 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v7 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( hService )
    CloseServiceHandle(hService);
  if ( v1 )
    CloseServiceHandle(v1);
  if ( (_DWORD)v2 == 1 )
    CoUninitialize();
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 174, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1800af660  push    rbp
0x1800af662  push    rbx
0x1800af663  push    rsi
0x1800af664  push    rdi
0x1800af665  push    r12
0x1800af667  push    r13
0x1800af669  push    r14
0x1800af66b  push    r15
0x1800af66d  lea     rbp, [rsp-18h]
0x1800af672  sub     rsp, 118h
0x1800af679  mov     rax, cs:__security_cookie
0x1800af680  xor     rax, rsp
0x1800af683  mov     [rbp+50h+var_50], rax
0x1800af687  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af68e  lea     rax, WPP_GLOBAL_Control
0x1800af695  cmp     rcx, rax
0x1800af698  jz      short loc_1800AF6B5
0x1800af69a  test    byte ptr [rcx+1Ch], 8
0x1800af69e  jz      short loc_1800AF6B5
0x1800af6a0  mov     rcx, [rcx+10h]
0x1800af6a4  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800af6ab  mov     edx, 98h
0x1800af6b0  call    WPP_SF_
0x1800af6b5  xor     r14d, r14d
0x1800af6b8  lea     rcx, [rbp+50h+pNotifyBuffer]; void *
0x1800af6bc  xor     edx, edx; Val
0x1800af6be  mov     [rsp+150h+var_104], r14w
0x1800af6c4  mov     esi, r14d
0x1800af6c7  mov     [rsp+150h+var_E0], r14
0x1800af6cc  mov     r13d, r14d
0x1800af6cf  mov     [rbp+50h+var_D0], r14
0x1800af6d3  lea     r8d, [r14+50h]; Size
0x1800af6d7  mov     [rbp+50h+var_C8], r14
0x1800af6db  mov     r15d, r14d
0x1800af6de  mov     [rsp+150h+var_100], r14
0x1800af6e3  mov     edi, r14d
0x1800af6e6  mov     [rbp+50h+var_B8], r14
0x1800af6ea  mov     r12d, r14d
0x1800af6ed  mov     [rbp+50h+var_B0], r14
0x1800af6f1  mov     ebx, r14d
0x1800af6f4  mov     [rbp+50h+var_A8], r14
0x1800af6f8  mov     [rsp+150h+var_F0], r14d
0x1800af6fd  mov     [rsp+150h+var_EC], r14d
0x1800af702  mov     [rsp+150h+var_E8], r14d
0x1800af707  mov     [rbp+50h+hService], r14
0x1800af70b  call    memset_0
0x1800af710  lea     ecx, [r14+1]
0x1800af714  mov     [rbp+50h+pNotifyBuffer.pContext], r14
0x1800af718  mov     [rsp+150h+var_D8], ecx
0x1800af71c  lea     rax, ?NlmTriggerSvcNotify@@YAXPEAX@Z; NlmTriggerSvcNotify(void *)
0x1800af723  mov     [rbp+50h+pNotifyBuffer.dwVersion], ecx
0x1800af726  lea     edx, [rcx+3]; dwCoInit
0x1800af729  mov     cs:?g_NlmHandlerInitialized@@3HA, ecx; int g_NlmHandlerInitialized
0x1800af72f  xor     ecx, ecx; pvReserved
0x1800af731  mov     [rbp+50h+pNotifyBuffer.pfnNotifyCallback], rax
0x1800af735  call    cs:__imp_CoInitializeEx
0x1800af73b  test    eax, eax
0x1800af73d  jns     short loc_1800AF77D
0x1800af73f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af746  lea     r15, WPP_GLOBAL_Control
0x1800af74d  cmp     rcx, r15
0x1800af750  jz      loc_1800B0236
0x1800af756  test    byte ptr [rcx+1Ch], 1
0x1800af75a  jz      loc_1800B0236
0x1800af760  mov     rcx, [rcx+10h]
0x1800af764  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800af76b  mov     edx, 99h
0x1800af770  mov     r9d, eax
0x1800af773  call    WPP_SF_d
0x1800af778  jmp     loc_1800B0236
0x1800af77d  mov     eax, 1
0x1800af782  lea     rdx, aServicesactive_0; "ServicesActive"
0x1800af789  mov     r8d, eax; dwDesiredAccess
0x1800af78c  mov     [rsp+150h+var_120], eax
0x1800af790  xor     ecx, ecx; lpMachineName
0x1800af792  call    cs:__imp_OpenSCManagerW
0x1800af798  mov     [rsp+150h+var_118], rax
0x1800af79d  mov     r14, rax
0x1800af7a0  test    rax, rax
0x1800af7a3  jnz     short loc_1800AF81E
0x1800af7a5  call    cs:__imp_GetLastError
0x1800af7ab  mov     ebx, eax
0x1800af7ad  test    eax, eax
0x1800af7af  jle     short loc_1800AF7BA
0x1800af7b1  movzx   ebx, ax
0x1800af7b4  or      ebx, 80070000h
0x1800af7ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af7c1  lea     r15, WPP_GLOBAL_Control
0x1800af7c8  cmp     rcx, r15
0x1800af7cb  jz      short loc_1800AF7EB
0x1800af7cd  test    byte ptr [rcx+1Ch], 1
0x1800af7d1  jz      short loc_1800AF7EB
0x1800af7d3  mov     rcx, [rcx+10h]
0x1800af7d7  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800af7de  mov     edx, 9Ah
0x1800af7e3  mov     r9d, ebx
0x1800af7e6  call    WPP_SF_d
0x1800af7eb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800af7f2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800af7f7  test    al, al
0x1800af7f9  jz      short loc_1800AF816
0x1800af7fb  lea     r9, aComthreadproc; "ComThreadProc"
0x1800af802  mov     r8d, 693h
0x1800af808  lea     rdx, aOnecoreuapNetN; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800af80f  mov     ecx, ebx
0x1800af811  call    TraceVpnWppErrorHRImpl
0x1800af816  mov     rbx, rsi
0x1800af819  jmp     loc_1800B0232
0x1800af81e  mov     r8d, 4; dwDesiredAccess
0x1800af824  lea     rdx, aNetprofm; "NetProfm"
0x1800af82b  mov     rcx, rax; hSCManager
0x1800af82e  call    cs:__imp_OpenServiceW
0x1800af834  mov     [rbp+50h+hService], rax
0x1800af838  test    rax, rax
0x1800af83b  jnz     short loc_1800AF8BA
0x1800af83d  call    cs:__imp_GetLastError
0x1800af843  mov     ebx, eax
0x1800af845  test    eax, eax
0x1800af847  jle     short loc_1800AF852
0x1800af849  movzx   ebx, ax
0x1800af84c  or      ebx, 80070000h
0x1800af852  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af859  lea     r15, WPP_GLOBAL_Control
0x1800af860  cmp     rcx, r15
0x1800af863  jz      short loc_1800AF883
0x1800af865  test    byte ptr [rcx+1Ch], 1
0x1800af869  jz      short loc_1800AF883
0x1800af86b  mov     rcx, [rcx+10h]
0x1800af86f  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800af876  mov     edx, 9Bh
0x1800af87b  mov     r9d, ebx
0x1800af87e  call    WPP_SF_d
0x1800af883  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800af88a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800af88f  test    al, al
0x1800af891  jz      loc_1800AF95A
0x1800af897  lea     r9, aComthreadproc; "ComThreadProc"
0x1800af89e  mov     r8d, 696h
0x1800af8a4  lea     rdx, aOnecoreuapNetN; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800af8ab  mov     ecx, ebx
0x1800af8ad  call    TraceVpnWppErrorHRImpl
0x1800af8b2  mov     rbx, rsi
0x1800af8b5  jmp     loc_1800B0232
0x1800af8ba  lea     r8, [rbp+50h+pNotifyBuffer]; pNotifyBuffer
0x1800af8be  mov     edx, 0Ch; dwNotifyMask
0x1800af8c3  mov     rcx, rax; hService
0x1800af8c6  call    cs:__imp_NotifyServiceStatusChangeW
0x1800af8cc  xor     r14d, r14d
0x1800af8cf  test    eax, eax
0x1800af8d1  jz      loc_1800AF95F
0x1800af8d7  call    cs:__imp_GetLastError
0x1800af8dd  mov     ebx, eax
0x1800af8df  test    eax, eax
0x1800af8e1  jle     short loc_1800AF8EC
0x1800af8e3  movzx   ebx, ax
0x1800af8e6  or      ebx, 80070000h
0x1800af8ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af8f3  lea     r15, WPP_GLOBAL_Control
0x1800af8fa  cmp     rcx, r15
0x1800af8fd  jz      short loc_1800AF91D
0x1800af8ff  test    byte ptr [rcx+1Ch], 1
0x1800af903  jz      short loc_1800AF91D
0x1800af905  mov     rcx, [rcx+10h]
0x1800af909  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800af910  mov     edx, 9Ch
0x1800af915  mov     r9d, ebx
0x1800af918  call    WPP_SF_d
0x1800af91d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800af924  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800af929  test    al, al
0x1800af92b  jz      short loc_1800AF950
0x1800af92d  lea     r9, aComthreadproc; "ComThreadProc"
0x1800af934  mov     r8d, 69Ah
0x1800af93a  lea     rdx, aOnecoreuapNetN; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800af941  mov     ecx, ebx
0x1800af943  call    TraceVpnWppErrorHRImpl
0x1800af948  mov     rbx, rsi
0x1800af94b  jmp     loc_1800B022D
0x1800af950  mov     r14, [rsp+150h+var_118]
0x1800af955  jmp     loc_1800AF816
0x1800af95a  jmp     loc_1800AF816
0x1800af95f  xor     edx, edx; pUnkOuter
0x1800af961  lea     rax, [rsp+150h+var_100]
0x1800af966  lea     r9, IID_INetworkListManager; riid
0x1800af96d  mov     [rsp+150h+ppv], rax; ppv
0x1800af972  lea     rcx, CLSID_NetworkListManager; rclsid
0x1800af979  lea     r8d, [rdx+1]; dwClsContext
0x1800af97d  call    cs:__imp_CoCreateInstance
0x1800af983  test    eax, eax
0x1800af985  jns     short loc_1800AF9C5
0x1800af987  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af98e  lea     r15, WPP_GLOBAL_Control
0x1800af995  cmp     rcx, r15
0x1800af998  jz      loc_1800B022D
0x1800af99e  test    byte ptr [rcx+1Ch], 1
0x1800af9a2  jz      loc_1800B022D
0x1800af9a8  mov     edx, 9Dh
0x1800af9ad  mov     rcx, [rcx+10h]
0x1800af9b1  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800af9b8  mov     r9d, eax
0x1800af9bb  call    WPP_SF_d
0x1800af9c0  jmp     loc_1800B022D
0x1800af9c5  mov     rcx, [rsp+150h+var_100]
0x1800af9ca  lea     rdx, [rsp+150h+var_104]
0x1800af9cf  mov     rax, [rcx]
0x1800af9d2  mov     rax, [rax+58h]
0x1800af9d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af9db  test    eax, eax
0x1800af9dd  jns     short loc_1800AFA12
0x1800af9df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af9e6  lea     rdi, WPP_GLOBAL_Control
0x1800af9ed  cmp     rcx, rdi
0x1800af9f0  jz      short loc_1800AFA2D
0x1800af9f2  test    byte ptr [rcx+1Ch], 1
0x1800af9f6  jz      short loc_1800AFA2D
0x1800af9f8  mov     rcx, [rcx+10h]
0x1800af9fc  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800afa03  mov     edx, 9Eh
0x1800afa08  mov     r9d, eax
0x1800afa0b  call    WPP_SF_d
0x1800afa10  jmp     short loc_1800AFA2D
0x1800afa12  lea     rdi, WPP_GLOBAL_Control
0x1800afa19  jnz     short loc_1800AFA2D
0x1800afa1b  cmp     [rsp+150h+var_104], 0FFFFh
0x1800afa21  jnz     short loc_1800AFA2D
0x1800afa23  mov     cs:?g_IsNlmInternetConnected@@3HA, 1; int g_IsNlmInternetConnected
0x1800afa2d  lea     rdx, [rsp+150h+var_D8]; int *
0x1800afa32  lea     rcx, ?g_NlmNetwork@@3U_LIST_ENTRY@@A; struct _LIST_ENTRY *
0x1800afa39  call    ?NlmNetworksEnum@@YAJPEAU_LIST_ENTRY@@PEAH@Z; NlmNetworksEnum(_LIST_ENTRY *,int *)
0x1800afa3e  mov     rax, cs:?g_lpfnNetworkChangeHandler@@3P6AHPEAU_LIST_ENTRY@@@ZEA; int (*g_lpfnNetworkChangeHandler)(_LIST_ENTRY *)
0x1800afa45  test    rax, rax
0x1800afa48  jz      short loc_1800AFA5A
0x1800afa4a  lea     rcx, ?g_NlmNetwork@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_NlmNetwork
0x1800afa51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afa56  mov     ebx, eax
0x1800afa58  jmp     short loc_1800AFA81
0x1800afa5a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afa61  cmp     rcx, rdi
0x1800afa64  jz      short loc_1800AFA88
0x1800afa66  test    byte ptr [rcx+1Ch], 4
0x1800afa6a  jz      short loc_1800AFA88
0x1800afa6c  mov     rcx, [rcx+10h]
0x1800afa70  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800afa77  mov     edx, 9Fh
0x1800afa7c  call    WPP_SF_
0x1800afa81  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afa88  mov     rax, cs:?g_lpfnNetworkConnectivityChangeHandler@@3P6AXXZEA; void (*g_lpfnNetworkConnectivityChangeHandler)(void)
0x1800afa8f  test    rax, rax
0x1800afa92  jz      short loc_1800AFABF
0x1800afa94  test    ebx, ebx
0x1800afa96  jnz     short loc_1800AFAA6
0x1800afa98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afa9d  lea     rbx, WPP_GLOBAL_Control
0x1800afaa4  jmp     short loc_1800AFAE6
0x1800afaa6  lea     rbx, WPP_GLOBAL_Control
0x1800afaad  cmp     rcx, rbx
0x1800afab0  jz      short loc_1800AFAE6
0x1800afab2  test    byte ptr [rcx+1Ch], 4
0x1800afab6  jz      short loc_1800AFAE6
0x1800afab8  mov     edx, 0A0h
0x1800afabd  jmp     short loc_1800AFAD6
0x1800afabf  lea     rbx, WPP_GLOBAL_Control
0x1800afac6  cmp     rcx, rbx
0x1800afac9  jz      short loc_1800AFAE6
0x1800afacb  test    byte ptr [rcx+1Ch], 4
0x1800afacf  jz      short loc_1800AFAE6
0x1800afad1  mov     edx, 0A1h
0x1800afad6  mov     rcx, [rcx+10h]
0x1800afada  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800afae1  call    WPP_SF_
0x1800afae6  mov     ecx, 10h; Size
0x1800afaeb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800afaf0  mov     rdi, rax
0x1800afaf3  test    rax, rax
0x1800afaf6  jz      loc_1800B0316
0x1800afafc  lea     rax, ??_7CNetListManagerEventSink@@6B@; const CNetListManagerEventSink::`vftable'
0x1800afb03  mov     [rdi], rax
0x1800afb06  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afb0d  cmp     rcx, rbx
0x1800afb10  jz      short loc_1800AFB2D
0x1800afb12  test    byte ptr [rcx+1Ch], 8
0x1800afb16  jz      short loc_1800AFB2D
0x1800afb18  mov     rcx, [rcx+10h]
0x1800afb1c  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800afb23  mov     edx, 0D2h
0x1800afb28  call    WPP_SF_
0x1800afb2d  mov     [rdi+8], r14d
0x1800afb31  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afb38  cmp     rcx, rbx
0x1800afb3b  jz      short loc_1800AFB58
0x1800afb3d  test    byte ptr [rcx+1Ch], 8
0x1800afb41  jz      short loc_1800AFB58
0x1800afb43  mov     rcx, [rcx+10h]
0x1800afb47  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800afb4e  mov     edx, 0D3h
0x1800afb53  call    WPP_SF_
0x1800afb58  mov     rax, [rdi]
0x1800afb5b  lea     r8, [rbp+50h+var_B8]
0x1800afb5f  lea     rdx, IID_IUnknown
0x1800afb66  mov     rcx, rdi
  ... truncated ...
```
