# VpnProfileLibInitialize

- ea: `0x1800e0e34`
- end: `0x1800e1f24`
- name: `VpnProfileLibInitialize`
- size: `4336`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `1`
- callee_count: `34`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800353b0`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000c37c`
- `0x18005bfd8`
- `0x180068a80`
- `0x1800aa728`
- `0x1800ab588`
- `0x1800ac87c`
- `0x1800b06e4`
- `0x1800c3d24`
- `0x1800c6be8`
- `0x1800c79cc`
- `0x1800c7af8`
- `0x1800cefbc`
- `0x1800cf12c`
- `0x1800cf290`
- `0x1800d278c`
- `0x1800d849c`
- `0x1800d8cb0`
- `0x1800da820`
- `0x1800db9cc`
- `0x1800de4c0`
- `0x1800de5f8`
- `0x1800dfbdc`
- `0x1800e0e34`
- `0x1800e2748`
- `0x1800e3ca0`
- `0x1800e3e00`
- `0x1800e3e30`
- `0x1800e3fac`
- `0x1800e4364`
- `0x1800e8e96`
- `0x1800e8ef0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800e1e6d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800e1e6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0ffc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e105b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e10ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e115e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1729`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e17b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e183b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e18c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0ffc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e105b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e10ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e115e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1729`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e17b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e183b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e18c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e0fd2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e1031`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e1090`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e111b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e0fd2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e1031`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e1090`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e111b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e1823`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e18ac`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e1823`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e18ac`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e1de0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e1de0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800e1679`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800e1711`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800e179a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800e1679`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800e1711`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800e179a`
- `fwpuclnt!FwpiVpnTriggerEventSubscribe0` at `0x1800e12b4`
- `fwpuclnt!FwpiVpnTriggerEventSubscribe0` at `0x1800e12b4`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800e1240`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800e1240`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasConnectionNotificationW` at `0x1800e139e`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasConnectionNotificationW` at `0x1800e139e`

## string_xrefs

- `0x1800e1278`: `FwpmEngineOpen0`
- `0x1800e1086`: `VpnSmCommsPluginsRoamToBestCostInterface`
- `0x1800e0fc8`: `VpnBrokerRegisterForPluginInstallations`
- `0x1800e1426`: `VpnBrokerRegisterForPluginInstallations`
- `0x1800e1027`: `VpnBrokerPluginIsInstalled`

## pseudocode

```c
__int64 __fastcall VpnProfileLibInitialize(HMODULE hModule, int a2, HMODULE a3, __int64 a4)
{
  int v4; // r14d
  bool v8; // r12
  int v9; // edi
  int v10; // eax
  int v11; // ecx
  unsigned int v12; // ebx
  struct _LIST_ENTRY *v13; // rcx
  __int64 v14; // r8
  unsigned int v15; // eax
  struct _LIST_ENTRY *v16; // rcx
  DWORD LastError; // eax
  DWORD v18; // eax
  DWORD v19; // eax
  DWORD v20; // eax
  int v21; // eax
  __int64 v22; // r9
  DWORD v23; // eax
  const char *v24; // rdx
  __int64 v25; // r8
  unsigned int v26; // eax
  unsigned int v27; // eax
  DWORD v28; // eax
  unsigned int v29; // eax
  struct tagRASNRPTRULELIST *v30; // rax
  __int64 v31; // rdx
  struct tagRASNRPTRULELIST *v32; // rax
  int v33; // eax
  unsigned int v34; // edi
  int v35; // eax
  unsigned int v36; // ecx
  unsigned int v37; // edx
  int v38; // eax
  unsigned int v39; // ecx
  DWORD v40; // eax
  struct _LIST_ENTRY *v41; // rcx
  __int64 v42; // rdx
  DWORD v43; // eax
  DWORD v44; // eax
  DWORD v45; // eax
  DWORD v46; // eax
  unsigned int ActiveUserTunnelRegistryContent; // eax
  char v48; // di
  struct _LIST_ENTRY *v49; // rcx
  __int64 v50; // rdx
  unsigned int ActiveDeviceTunnelRegistryContent; // eax
  char v52; // si
  struct _LIST_ENTRY *v53; // rcx
  __int64 v54; // rdx
  unsigned int v55; // eax
  unsigned int ActiveTokenAndSessionId; // eax
  struct _LIST_ENTRY *v57; // rcx
  __int64 v58; // rdx
  unsigned int LockdownNciNrptRule; // eax
  int v60; // r8d
  unsigned int v61; // eax
  struct _LIST_ENTRY *v62; // rcx
  unsigned int v63; // eax
  int v64; // r8d
  unsigned int v65; // eax
  struct _LIST_ENTRY *v66; // rcx
  unsigned int v67; // eax
  struct _LIST_ENTRY *v68; // rcx
  unsigned int v69; // eax
  bool engineHandle; // [rsp+20h] [rbp-99h]
  int v72; // [rsp+30h] [rbp-89h] BYREF
  __int64 v73; // [rsp+38h] [rbp-81h] BYREF
  DWORD ThreadId; // [rsp+40h] [rbp-79h] BYREF
  __int128 v75; // [rsp+48h] [rbp-71h] BYREF
  int v76; // [rsp+58h] [rbp-61h]
  FWPM_SESSION0 session; // [rsp+60h] [rbp-59h] BYREF
  char v78[16]; // [rsp+B0h] [rbp-9h] BYREF
  int *v79; // [rsp+C0h] [rbp+7h]
  __int64 v80; // [rsp+C8h] [rbp+Fh]

  v4 = a4;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    engineHandle = (_DWORD)a4 != 0;
    LOBYTE(a4) = a2 != 0;
    WPP_SF_cc(WPP_GLOBAL_Control[1].Flink, 807, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, a4, engineHandle);
  }
  v72 = 0;
  ThreadId = 0;
  v8 = 0;
  v73 = 0;
  session.sessionKey.Data1 = 0;
  memset_0(&session.sessionKey.Data2, 0, 0x44u);
  g_fLibInitializeCalled = 1;
  v75 = 0;
  v76 = 0;
  v9 = InitializeGlobalData();
  if ( v9 >= 0
    || WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
  {
    if ( v9 >= 0 )
      goto LABEL_16;
  }
  else
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 808, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, (unsigned int)v9);
  }
  v10 = (v9 >> 16) & 0x1FFF;
  if ( v10 == 7 )
    v11 = (unsigned __int16)v9;
  else
    v11 = v9;
  if ( !v11 )
  {
LABEL_16:
    v15 = InitializeCrmData();
    if ( v15 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
LABEL_21:
        if ( hModule && a2 )
        {
          g_VpnBrokerRegisterForPluginInstallations = (unsigned int (*)(void (__high *)(enum VPN_BROKER_PLUGIN_INSTALLATION_OPERATION_, void *, void *)))GetProcAddress(hModule, "VpnBrokerRegisterForPluginInstallations");
          if ( !g_VpnBrokerRegisterForPluginInstallations
            && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            LastError = GetLastError();
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 810, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, LastError);
          }
          g_VpnBrokerPluginIsInstalled = (unsigned int (*)(void *, void *, int *))GetProcAddress(
                                                                                    hModule,
                                                                                    "VpnBrokerPluginIsInstalled");
          if ( !g_VpnBrokerPluginIsInstalled
            && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            v18 = GetLastError();
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 811, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v18);
          }
          g_VpnPlugInRoamToBestCostInterface = (unsigned int (*)(void))GetProcAddress(
                                                                         hModule,
                                                                         "VpnSmCommsPluginsRoamToBestCostInterface");
          if ( g_VpnPlugInRoamToBestCostInterface )
          {
            v16 = WPP_GLOBAL_Control;
            goto LABEL_37;
          }
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            v19 = GetLastError();
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 812, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v19);
LABEL_35:
            v16 = WPP_GLOBAL_Control;
          }
        }
        else if ( v16 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v16[1].Blink) & 1) != 0 )
        {
          WPP_SF_(v16[1].Flink, 813, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
          goto LABEL_35;
        }
LABEL_37:
        if ( a3 && v4 )
        {
          g_VpnIkeRoamToBestCostInterface = (unsigned int (*)(void))GetProcAddress(a3, "VpnIkeRoamToBestCostInterface");
          if ( !g_VpnIkeRoamToBestCostInterface
            && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            v20 = GetLastError();
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 814, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v20);
          }
        }
        else if ( v16 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v16[1].Blink) & 1) != 0 )
        {
          WPP_SF_(v16[1].Flink, 815, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
        }
        v21 = IsDomainJoined();
        g_bIsDomainJoined = v21;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
        {
          LOBYTE(v22) = v21 != 0;
          WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 816, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v22);
        }
        session.flags = 1;
        v23 = FwpmEngineOpen0(0, 0xAu, 0, &session, &g_FwpEngineHandle);
        v12 = v23;
        if ( v23 )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 817, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v23);
          }
          v24 = "FwpmEngineOpen0";
LABEL_57:
          v25 = v12;
LABEL_58:
          VpnReportError("VpnProfileLibInitialize", v24, v25);
          goto LABEL_274;
        }
        v26 = FwpiVpnTriggerEventSubscribe0(
                g_FwpEngineHandle,
                &v75,
                int_AppTriggerEventCallback,
                0,
                &g_TriggerEventHandle);
        v12 = v26;
        if ( v26 )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 818, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v26);
          }
          v24 = "FwpiVpnTriggerEventSubscribe0";
          goto LABEL_57;
        }
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 819, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
        }
        int_VpnProfileCleanNRPTRule();
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 820, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
        }
        AppendDnsSuffixSearchListToGlobalList(0, 0);
        v27 = NlmHandlerInitialize();
        v12 = v27;
        if ( v27 )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 821, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v27);
          }
          v24 = "NlmHandlerInitialize";
          goto LABEL_57;
        }
        g_fNlmHandlerInitialized = 1;
        v28 = RasConnectionNotificationW((HRASCONN)0xFFFFFFFFFFFFFFFFLL, g_RasConnectionEvent, 2u);
        v12 = v28;
        if ( v28 )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 822, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v28);
          }
          v24 = "RasConnectionNotification";
          goto LABEL_57;
        }
        if ( g_VpnBrokerRegisterForPluginInstallations )
        {
          v29 = g_VpnBrokerRegisterForPluginInstallations((void (__high *)(enum VPN_BROKER_PLUGIN_INSTALLATION_OPERATION_, void *, void *))&int_VpnProfilePluginInstallationNotificationHandler);
          v12 = v29;
          if ( v29 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 823, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v29);
            }
            v24 = "VpnBrokerRegisterForPluginInstallations";
            goto LABEL_57;
          }
        }
        v30 = (struct tagRASNRPTRULELIST *)VpnAlloc(64);
        g_pNrptRuleListPersistentPrefixForUserTunnel = v30;
        if ( !v30 )
        {
          v12 = 14;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 824, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
            v30 = g_pNrptRuleListPersistentPrefixForUserTunnel;
          }
          if ( !v30 )
          {
            v12 = 14;
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
            {
              goto LABEL_274;
            }
            v31 = 825;
            goto LABEL_94;
          }
        }
        v32 = (struct tagRASNRPTRULELIST *)VpnAlloc(64);
        g_pNrptRuleListPersistentPrefixForDeviceTunnel = v32;
        if ( !v32 )
        {
          v12 = 14;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 826, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
            v32 = g_pNrptRuleListPersistentPrefixForDeviceTunnel;
          }
          if ( !v32 )
          {
            v12 = 14;
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
            {
              goto LABEL_274;
            }
            v31 = 827;
LABEL_94:
            WPP_SF_d(v13[1].Flink, v31, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
            goto LABEL_274;
          }
        }
        v33 = VpnStringBuild(&v73, L"VPN_PERSISTENT_", 0);
        v34 = v33;
        if ( v33 >= 0
          || WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
        {
          if ( v33 >= 0 )
            goto LABEL_115;
        }
        else
        {
          WPP_SF_d(
            WPP_GLOBAL_Control[1].Flink,
            828,
            &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
            (unsigned int)v33);
          v33 = v34;
        }
        v35 = (v33 >> 16) & 0x1FFF;
        if ( v35 == 7 )
          v36 = (unsigned __int16)v34;
        else
          v36 = v34;
        v37 = (unsigned __int16)v34;
        if ( v36 )
          goto LABEL_112;
LABEL_115:
        *((_QWORD *)g_pNrptRuleListPersistentPrefixForUserTunnel + 6) = v73;
        v38 = VpnStringBuild(&v73, L"VPN_PERSISTENT_", 0);
        v34 = v38;
        if ( v38 >= 0
          || WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
        {
          if ( v38 >= 0 )
            goto LABEL_124;
        }
        else
        {
          WPP_SF_d(
            WPP_GLOBAL_Control[1].Flink,
            829,
            &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
            (unsigned int)v38);
          v38 = v34;
        }
        v35 = (v38 >> 16) & 0x1FFF;
        if ( v35 == 7 )
          v39 = (unsigned __int16)v34;
        else
          v39 = v34;
        v37 = (unsigned __int16)v34;
        if ( v39 )
        {
LABEL_112:
          if ( v35 == 7 )
            v34 = v37;
          v24 = "VpnStringBuild for pNrptRulePersistentPrefix";
          v25 = v34;
          goto LABEL_58;
        }
LABEL_124:
        *((_QWORD *)g_pNrptRuleListPersistentPrefixForDeviceTunnel + 6) = v73;
        VpnCriticalSectionEnter(&g_LpCriticalSection);
        g_fDisconnectListInitialized = 1;
        qword_18010F508 = (__int64)&g_DisconnectList;
        g_DisconnectList = &g_DisconnectList;
        g_fDisconnectNotionsListInitialized = 1;
        qword_18010F4F8 = (__int64)&g_DisconnectNotificationsList;
        g_DisconnectNotificationsList = &g_DisconnectNotificationsList;
        g_RegistryReparse = CreateThreadpoolTimer(int_RegistryReparse, 0, 0);
        if ( !g_RegistryReparse )
        {
          v40 = GetLastError();
          v12 = v40;
          if ( v40 )
          {
            v41 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
            {
LABEL_130:
              if ( !g_RegistryReparse )
              {
                if ( v41 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v41[1].Blink) & 1) == 0 )
                  goto LABEL_273;
                v42 = 831;
LABEL_134:
                WPP_SF_d(v41[1].Flink, v42, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v12);
LABEL_273:
                VpnCriticalSectionLeave(&g_LpCriticalSection);
                goto LABEL_274;
              }
              g_SessionRetryTimeoutForUserTunnel = CreateThreadpoolTimer(int_SessionRetryConnectionForUserTunnel, 0, 0);
              if ( !g_SessionRetryTimeoutForUserTunnel )
              {
                v43 = GetLastError();
                v12 = v43;
                if ( v43 )
                {
                  v41 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
                  {
LABEL_141:
                    if ( !g_SessionRetryTimeoutForUserTunnel )
                    {
                      if ( v41 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v41[1].Blink) & 1) == 0 )
                        goto LABEL_273;
                      v42 = 833;
                      goto LABEL_134;
                    }
                    g_SessionRetryTimeoutForDeviceTunnel = CreateThreadpoolTimer(
                                                             int_SessionRetryConnectionForDeviceTunnel,
                                                             0,
                                                             0);
                    if ( !g_SessionRetryTimeoutForDeviceTunnel )
                    {
                      v44 = GetLastError();
                      v12 = v44;
                      if ( v44 )
                      {
                        v41 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
                        {
LABEL_151:
                          if ( !g_SessionRetryTimeoutForDeviceTunnel )
                          {
                            if ( v41 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v41[1].Blink) & 1) == 0 )
                              goto LABEL_273;
                            v42 = 835;
                            goto LABEL_134;
                          }
                          g_pDisconnectWorkItem = CreateThreadpoolWork(int_DisconnectPendingConnection, 0, 0);
                          if ( !g_pDisconnectWorkItem )
                          {
                            v45 = GetLastError();
                            v12 = v45;
                            if ( v45 )
                            {
                              v41 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
                              {
LABEL_161:
                                if ( !g_pDisconnectWorkItem )
                                {
                                  if ( v41 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                    || (BYTE4(v41[1].Blink) & 1) == 0 )
                                  {
                                    goto LABEL_273;
                                  }
                                  v42 = 837;
                                  goto LABEL_134;
                                }
                                g_pHandleNqmNotifyWorkItem = CreateThreadpoolWork(int_HandleNqmNotification, 0, 0);
                                if ( !g_pHandleNqmNotifyWorkItem )
                                {
                                  v46 = GetLastError();
                                  v12 = v46;
                                  if ( v46 )
                                  {
                                    v41 = WPP_GLOBAL_Control;
                                    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
                                    {
LABEL_171:
                                      if ( !g_pHandleNqmNotifyWorkItem )
                                      {
                                        if ( v41 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                          || (BYTE4(v41[1].Blink) & 1) == 0 )
                                        {
                                          goto LABEL_273;
                                        }
                                        v42 = 839;
                                        goto LABEL_134;
                                      }
                                      ActiveUserTunnelRegistryContent = int_ReadActiveUserTunnelRegistryContent(
                                                                          (unsigned __int16 **)&g_ActiveUserProfile,
                                                                          (unsigned __int16 **)&qword_18010EF48,
                                                                          &Sid);
                                      if ( !ActiveUserTunnelRegistryContent )
                                      {
                                        v48 = 1;
                                        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
                                        {
                                          WPP_SF_SS(
                                            WPP_GLOBAL_Control[1].Flink,
                                            842,
                                            (unsigned int)&WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                                            (_DWORD)g_ActiveUserProfile,
                                            (__int64)qword_18010EF48);
                                        }
LABEL_189:
                                        ActiveDeviceTunnelRegistryContent = int_ReadActiveDeviceTunnelRegistryContent(
                                                                              (unsigned __int16 **)&g_ActiveDeviceProfile,
                                                                              (unsigned __int16 **)&qword_18010F1A8,
                                                                              &qword_18010F1B0);
                                        v12 = ActiveDeviceTunnelRegistryContent;
                                        if ( !ActiveDeviceTunnelRegistryContent )
                                        {
                                          v52 = 1;
                                          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
                                          {
                                            WPP_SF_SS(
                                              WPP_GLOBAL_Control[1].Flink,
                                              845,
                                              (unsigned int)&WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                                              (_DWORD)g_ActiveDeviceProfile,
                                              (__int64)qword_18010F1A8);
                                          }
LABEL_200:
                                          if ( !v48 && !v52 )
                                            goto LABEL_251;
                                          if ( (unsigned int)IsDefaultTracingEnabled() )
                                            EnableAutoWPPTracingForSubComponent(0);
                                          v55 = VpnProfileSetRasManServiceState(1);
                                          v12 = v55;
                                          if ( v55
                                            && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                                          {
                                            WPP_SF_d(
                                              WPP_GLOBAL_Control[1].Flink,
                                              846,
                                              &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                                              v55);
                                          }
                                          if ( v48 )
                                          {
                                            ActiveTokenAndSessionId = VpnProfileActiveSettingsGet(
                                                                        g_ActiveUserProfile,
                                                                        qword_18010EF48);
                                            v12 = ActiveTokenAndSessionId;
                                            if ( ActiveTokenAndSessionId )
                                            {
                                              v57 = WPP_GLOBAL_Control;
                                              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                                              {
                                                v58 = 847;
LABEL_235:
                                                WPP_SF_d(
                                                  v57[1].Flink,
                                                  v58,
                                                  &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                                                  ActiveTokenAndSessionId);
                                              }
                                            }
                                            else
                                            {
                                              if ( *(_DWORD *)(qword_18010F190 + 132) )
                                              {
                                                LockdownNciNrptRule = int_VpnCreateLockdownNciNrptRule((unsigned __int16 *)qword_18010EF48);
                                                if ( LockdownNciNrptRule )
                                                {
                                                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                                    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                                                  {
                                                    WPP_SF_d(
                                                      WPP_GLOBAL_Control[1].Flink,
                                                      848,
                                                      &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                                                      LockdownNciNrptRule);
                                                  }
                                                }
                                              }
                                              ActiveTokenAndSessionId = GetActiveTokenAndSessionId(Sid);
                                              v12 = ActiveTokenAndSessionId;
                                              if ( !ActiveTokenAndSessionId )
                                              {
                                                v61 = RasAddNrptRulesEx(
                                                        *(_QWORD *)(qword_18010F190 + 8),
                                                        *(_DWORD *)qword_18010F190,
                                                        v60,
                                                        0,
                                                        1,
                                                        0);
                                                v12 = v61;
                                                if ( v61 )
                                                {
                                                  v62 = WPP_GLOBAL_Control;
                                                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                                    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                                                  {
                                                    WPP_SF_d(
                                                      WPP_GLOBAL_Control[1].Flink,
                                                      849,
                                                      &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                                                      v61);
                                                    v62 = WPP_GLOBAL_Control;
                                                  }
                                                  v12 = 0;
                                                }
                                                else
                                                {
                                                  v62 = WPP_GLOBAL_Control;
                                                }
                                                dword_18010EF58 = v72;
                                                if ( v62 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                                  && (BYTE4(v62[1].Blink) & 4) != 0 )
                                                {
                                                  WPP_SF_(
                                                    v62[1].Flink,
                                                    850,
                                                    &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
                                                }
                                                g_IsActiveUserProfile = 1;
                                                goto LABEL_236;
                                              }
                                              v57 = WPP_GLOBAL_Control;
                                              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                                              {
                                                v58 = 851;
                                                goto LABEL_235;
                                              }
                                            }
                                          }
LABEL_236:
                                          if ( v52 )
                                          {
                                            v63 = VpnProfileActiveSettingsGet(g_ActiveDeviceProfile, qword_18010F1A8);
                                            v12 = v63;
                                            if ( v63 )
                                            {
                                              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                                              {
                                                WPP_SF_d(
                                                  WPP_GLOBAL_Control[1].Flink,
                                                  852,
                                                  &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                                                  v63);
                                              }
                                            }
                                            else
                                            {
                                              v65 = RasAddNrptRulesEx(
                                                      *(_QWORD *)(qword_18010F3F0 + 8),
                                                      *(_DWORD *)qword_18010F3F0,
                                                      v64,
                                                      0,
                                                      1,
                                                      0);
                                              v12 = v65;
                                              if ( v65 )
                                              {
                                                v66 = WPP_GLOBAL_Control;
                                                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                                  && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                                                {
                                                  WPP_SF_d(
                                                    WPP_GLOBAL_Control[1].Flink,
                                                    853,
                                                    &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                                                    v65);
                                                  v66 = WPP_GLOBAL_Control;
                                                }
                                                v12 = 0;
                                              }
                                              else
                                              {
                                                v66 = WPP_GLOBAL_Control;
                                              }
                                              dword_18010F1B8 = v72;
                                              if ( v66 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                                && (BYTE4(v66[1].Blink) & 4) != 0 )
                                              {
                                                WPP_SF_(
                                                  v66[1].Flink,
                                                  854,
                                                  &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
                                              }
                                              g_IsActiveDeviceProfile = 1;
                                            }
                                          }
LABEL_251:
                                          v67 = SubscribeVpnConnectionStatusWnfNotifications();
                                          if ( v67 )
                                          {
                                            v68 = WPP_GLOBAL_Control;
                                            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                              || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
                                            {
                                              goto LABEL_256;
                                            }
                                            WPP_SF_d(
                                              WPP_GLOBAL_Control[1].Flink,
                                              855,
                                              &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                                              v67);
                                          }
                                          v68 = WPP_GLOBAL_Control;
LABEL_256:
                                          v8 = 1;
                                          if ( v68 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                            && (BYTE4(v68[1].Blink) & 4) != 0 )
                                          {
                                            WPP_SF_(v68[1].Flink, 856, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
                                            v68 = WPP_GLOBAL_Control;
                                          }
                                          if ( g_fConfigUserRegContentFailed || g_fConfigDeviceRegContentFailed )
                                          {
                                            StartRetryRegistryParsingWaitPeriod();
                                          }
                                          else if ( g_fIsDeviceTunnelAllowed )
                                          {
                                            SubmitThreadpoolWork(g_pDeviceTunnelConnectWorkItem);
                                          }
                                          else if ( v68 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                                 && (BYTE4(v68[1].Blink) & 4) != 0 )
                                          {
                                            WPP_SF_(v68[1].Flink, 857, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
                                          }
                                          v69 = SubscribeToSLAPIChanges();
                                          if ( v69
                                            && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                                          {
                                            WPP_SF_d(
                                              WPP_GLOBAL_Control[1].Flink,
                                              858,
                                              &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                                              v69);
                                          }
                                          if ( (unsigned int)int_IsRasMobileCore() )
                                            g_RasThreadSingleUserInitHandle = CreateThread(
                                                                                0,
                                                                                0,
                                                                                int_SingleUserInitThread,
                                                                                0,
                                                                                0,
                                                                                &ThreadId);
                                          goto LABEL_273;
                                        }
                                        v52 = 0;
                                        if ( ActiveDeviceTunnelRegistryContent - 2 <= 1
                                          || ActiveDeviceTunnelRegistryContent == 1168 )
                                        {
                                          v53 = WPP_GLOBAL_Control;
                                          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                            || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
                                          {
                                            goto LABEL_199;
                                          }
                                          v54 = 843;
                                        }
                                        else
                                        {
                                          v53 = WPP_GLOBAL_Control;
                                          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                            || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
                                          {
                                            goto LABEL_199;
                                          }
                                          v54 = 844;
                                        }
                                        WPP_SF_d(
                                          v53[1].Flink,
                                          v54,
                                          &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                                          ActiveDeviceTunnelRegistryContent);
LABEL_199:
                                        g_IsActiveDeviceProfile = 0;
                                        v12 = 0;
                                        goto LABEL_200;
                                      }
                                      v48 = 0;
                                      if ( ActiveUserTunnelRegistryContent - 2 <= 1
                                        || ActiveUserTunnelRegistryContent == 1168 )
                                      {
                                        v49 = WPP_GLOBAL_Control;
                                        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
                                        {
                                          goto LABEL_185;
                                        }
                                        v50 = 840;
                                      }
                                      else
                                      {
                                        v49 = WPP_GLOBAL_Control;
                                        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                                          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
                                        {
                                          goto LABEL_185;
                                        }
                                        v50 = 841;
                                      }
                                      WPP_SF_d(
                                        v49[1].Flink,
                                        v50,
                                        &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                                        ActiveUserTunnelRegistryContent);
LABEL_185:
                                      g_IsActiveUserProfile = 0;
                                      goto LABEL_189;
                                    }
                                    WPP_SF_d(
                                      WPP_GLOBAL_Control[1].Flink,
                                      838,
                                      &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                                      v46);
                                  }
                                }
                                v41 = WPP_GLOBAL_Control;
                                goto LABEL_171;
                              }
                              WPP_SF_d(
                                WPP_GLOBAL_Control[1].Flink,
                                836,
                                &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                                v45);
                            }
                          }
                          v41 = WPP_GLOBAL_Control;
                          goto LABEL_161;
                        }
                        WPP_SF_d(
                          WPP_GLOBAL_Control[1].Flink,
                          834,
                          &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                          v44);
                      }
                    }
                    v41 = WPP_GLOBAL_Control;
                    goto LABEL_151;
                  }
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 832, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v43);
                }
              }
              v41 = WPP_GLOBAL_Control;
              goto LABEL_141;
            }
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 830, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v40);
          }
        }
        v41 = WPP_GLOBAL_Control;
        goto LABEL_130;
      }
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 809, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v15);
    }
    v16 = WPP_GLOBAL_Control;
    goto LABEL_21;
  }
  v12 = 0;
  if ( v10 == 7 )
    v9 = (unsigned __int16)v9;
  VpnReportError("VpnProfileLibInitialize", "InitializeGlobalData", (unsigned int)v9);
LABEL_274:
  if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
  {
    v72 = v12;
    v79 = &v72;
    v80 = 4;
    McGenEventWrite_EventWriteTransfer(v13, VpnAutoTriggerLibInitializationStatus, v14, 2, v78);
  }
  g_fLibInitializeCompletedSuccessfully = v8;
  if ( (v12 & 0x80000000) != 0
    && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 859, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v12);
  }
  return v12;
}

```

## disassembly

```asm
0x1800e0e34  mov     [rsp-8+arg_8], rbx
0x1800e0e39  push    rbp
0x1800e0e3a  push    rsi
0x1800e0e3b  push    rdi
0x1800e0e3c  push    r12
0x1800e0e3e  push    r13
0x1800e0e40  push    r14
0x1800e0e42  push    r15
0x1800e0e44  lea     rbp, [rsp-27h]
0x1800e0e49  sub     rsp, 0E0h
0x1800e0e50  mov     rax, cs:__security_cookie
0x1800e0e57  xor     rax, rsp
0x1800e0e5a  mov     [rbp+57h+var_40], rax
0x1800e0e5e  mov     r14d, r9d
0x1800e0e61  mov     r15, r8
0x1800e0e64  mov     ebx, edx
0x1800e0e66  mov     rsi, rcx
0x1800e0e69  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0e70  lea     rax, WPP_GLOBAL_Control
0x1800e0e77  xor     r13d, r13d
0x1800e0e7a  cmp     rcx, rax
0x1800e0e7d  jz      short loc_1800E0EAA
0x1800e0e7f  test    byte ptr [rcx+1Ch], 8
0x1800e0e83  jz      short loc_1800E0EAA
0x1800e0e85  mov     rcx, [rcx+10h]
0x1800e0e89  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800e0e90  test    r9d, r9d
0x1800e0e93  setnz   al
0x1800e0e96  test    edx, edx
0x1800e0e98  mov     edx, 327h
0x1800e0e9d  mov     byte ptr [rsp+110h+engineHandle], al
0x1800e0ea1  setnz   r9b
0x1800e0ea5  call    WPP_SF_cc
0x1800e0eaa  xor     edx, edx; Val
0x1800e0eac  mov     [rsp+110h+var_E0], r13d
0x1800e0eb1  lea     rcx, [rbp+57h+session.sessionKey.Data2]; void *
0x1800e0eb5  mov     [rbp+57h+ThreadId], r13d
0x1800e0eb9  mov     r12b, r13b
0x1800e0ebc  mov     [rsp+110h+var_D8], r13
0x1800e0ec1  mov     [rbp+57h+session.sessionKey.Data1], r13d
0x1800e0ec5  lea     r8d, [rdx+44h]; Size
0x1800e0ec9  call    memset_0
0x1800e0ece  xorps   xmm0, xmm0
0x1800e0ed1  mov     cs:?g_fLibInitializeCalled@@3_NA, 1; bool g_fLibInitializeCalled
0x1800e0ed8  xor     eax, eax
0x1800e0eda  movups  [rbp+57h+var_C8], xmm0
0x1800e0ede  mov     [rbp+57h+var_B8], eax
0x1800e0ee1  call    ?InitializeGlobalData@@YAJXZ; InitializeGlobalData(void)
0x1800e0ee6  mov     edi, eax
0x1800e0ee8  test    eax, eax
0x1800e0eea  jns     short loc_1800E0F1F
0x1800e0eec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0ef3  lea     rax, WPP_GLOBAL_Control
0x1800e0efa  cmp     rcx, rax
0x1800e0efd  jz      short loc_1800E0F1F
0x1800e0eff  test    byte ptr [rcx+1Ch], 1
0x1800e0f03  jz      short loc_1800E0F1F
0x1800e0f05  mov     rcx, [rcx+10h]
0x1800e0f09  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800e0f10  mov     edx, 328h
0x1800e0f15  mov     r9d, edi
0x1800e0f18  call    WPP_SF_d
0x1800e0f1d  jmp     short loc_1800E0F23
0x1800e0f1f  test    edi, edi
0x1800e0f21  jns     short loc_1800E0F6D
0x1800e0f23  mov     eax, edi
0x1800e0f25  sar     eax, 10h
0x1800e0f28  and     eax, 1FFFh
0x1800e0f2d  cmp     eax, 7
0x1800e0f30  jnz     short loc_1800E0F39
0x1800e0f32  movzx   ecx, di
0x1800e0f35  mov     edx, ecx
0x1800e0f37  jmp     short loc_1800E0F3E
0x1800e0f39  mov     ecx, edi
0x1800e0f3b  movzx   edx, di
0x1800e0f3e  test    ecx, ecx
0x1800e0f40  jz      short loc_1800E0F6D
0x1800e0f42  cmp     eax, 7
0x1800e0f45  lea     rcx, aVpnprofilelibi; "VpnProfileLibInitialize"
0x1800e0f4c  mov     ebx, r13d
0x1800e0f4f  cmovz   edi, edx
0x1800e0f52  lea     rdx, aInitializeglob; "InitializeGlobalData"
0x1800e0f59  mov     r8d, edi
0x1800e0f5c  call    VpnReportError
0x1800e0f61  lea     r15, WPP_GLOBAL_Control
0x1800e0f68  jmp     loc_1800E1E8C
0x1800e0f6d  call    ?InitializeCrmData@@YAKXZ; InitializeCrmData(void)
0x1800e0f72  test    eax, eax
0x1800e0f74  jz      short loc_1800E0FA9
0x1800e0f76  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0f7d  lea     rdi, WPP_GLOBAL_Control
0x1800e0f84  cmp     rcx, rdi
0x1800e0f87  jz      short loc_1800E0FB7
0x1800e0f89  test    byte ptr [rcx+1Ch], 1
0x1800e0f8d  jz      short loc_1800E0FB7
0x1800e0f8f  mov     rcx, [rcx+10h]
0x1800e0f93  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800e0f9a  mov     edx, 329h
0x1800e0f9f  mov     r9d, eax
0x1800e0fa2  call    WPP_SF_d
0x1800e0fa7  jmp     short loc_1800E0FB0
0x1800e0fa9  lea     rdi, WPP_GLOBAL_Control
0x1800e0fb0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0fb7  test    rsi, rsi
0x1800e0fba  jz      loc_1800E1187
0x1800e0fc0  test    ebx, ebx
0x1800e0fc2  jz      loc_1800E1187
0x1800e0fc8  lea     rdx, aVpnbrokerregis; "VpnBrokerRegisterForPluginInstallations"
0x1800e0fcf  mov     rcx, rsi; hModule
0x1800e0fd2  call    cs:__imp_GetProcAddress
0x1800e0fd9  nop     dword ptr [rax+rax+00h]
0x1800e0fde  mov     cs:?g_VpnBrokerRegisterForPluginInstallations@@3P6AKP6AXW4VPN_BROKER_PLUGIN_INSTALLATION_OPERATION_@@PEAX1@Z@ZEA, rax; ulong (*g_VpnBrokerRegisterForPluginInstallations)(void (*)(VPN_BROKER_PLUGIN_INSTALLATION_OPERATION_,void *,void *))
0x1800e0fe5  test    rax, rax
0x1800e0fe8  jnz     short loc_1800E1027
0x1800e0fea  mov     rax, cs:WPP_GLOBAL_Control
0x1800e0ff1  cmp     rax, rdi
0x1800e0ff4  jz      short loc_1800E1027
0x1800e0ff6  test    byte ptr [rax+1Ch], 1
0x1800e0ffa  jz      short loc_1800E1027
0x1800e0ffc  call    cs:__imp_GetLastError
0x1800e1003  nop     dword ptr [rax+rax+00h]
0x1800e1008  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e100f  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800e1016  mov     edx, 32Ah
0x1800e101b  mov     r9d, eax
0x1800e101e  mov     rcx, [rcx+10h]
0x1800e1022  call    WPP_SF_d
0x1800e1027  lea     rdx, aVpnbrokerplugi; "VpnBrokerPluginIsInstalled"
0x1800e102e  mov     rcx, rsi; hModule
0x1800e1031  call    cs:__imp_GetProcAddress
0x1800e1038  nop     dword ptr [rax+rax+00h]
0x1800e103d  mov     cs:?g_VpnBrokerPluginIsInstalled@@3P6AKPEAX0PEAH@ZEA, rax; ulong (*g_VpnBrokerPluginIsInstalled)(void *,void *,int *)
0x1800e1044  test    rax, rax
0x1800e1047  jnz     short loc_1800E1086
0x1800e1049  mov     rax, cs:WPP_GLOBAL_Control
0x1800e1050  cmp     rax, rdi
0x1800e1053  jz      short loc_1800E1086
0x1800e1055  test    byte ptr [rax+1Ch], 1
0x1800e1059  jz      short loc_1800E1086
0x1800e105b  call    cs:__imp_GetLastError
0x1800e1062  nop     dword ptr [rax+rax+00h]
0x1800e1067  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e106e  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800e1075  mov     edx, 32Bh
0x1800e107a  mov     r9d, eax
0x1800e107d  mov     rcx, [rcx+10h]
0x1800e1081  call    WPP_SF_d
0x1800e1086  lea     rdx, aVpnsmcommsplug_0; "VpnSmCommsPluginsRoamToBestCostInterfac"...
0x1800e108d  mov     rcx, rsi; hModule
0x1800e1090  call    cs:__imp_GetProcAddress
0x1800e1097  nop     dword ptr [rax+rax+00h]
0x1800e109c  mov     cs:?g_VpnPlugInRoamToBestCostInterface@@3P6AKXZEA, rax; ulong (*g_VpnPlugInRoamToBestCostInterface)(void)
0x1800e10a3  test    rax, rax
0x1800e10a6  jnz     short loc_1800E10F1
0x1800e10a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e10af  cmp     rcx, rdi
0x1800e10b2  jz      short loc_1800E10F8
0x1800e10b4  test    byte ptr [rcx+1Ch], 1
0x1800e10b8  jz      short loc_1800E10F8
0x1800e10ba  call    cs:__imp_GetLastError
0x1800e10c1  nop     dword ptr [rax+rax+00h]
0x1800e10c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e10cd  lea     rsi, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800e10d4  mov     edx, 32Ch
0x1800e10d9  mov     r9d, eax
0x1800e10dc  mov     r8, rsi
0x1800e10df  mov     rcx, [rcx+10h]
0x1800e10e3  call    WPP_SF_d
0x1800e10e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e10ef  jmp     short loc_1800E10FF
0x1800e10f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e10f8  lea     rsi, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800e10ff  test    r15, r15
0x1800e1102  jz      loc_1800E11B7
0x1800e1108  test    r14d, r14d
0x1800e110b  jz      loc_1800E11B7
0x1800e1111  lea     rdx, aVpnikeroamtobe; "VpnIkeRoamToBestCostInterface"
0x1800e1118  mov     rcx, r15; hModule
0x1800e111b  call    cs:__imp_GetProcAddress
0x1800e1122  nop     dword ptr [rax+rax+00h]
0x1800e1127  mov     cs:?g_VpnIkeRoamToBestCostInterface@@3P6AKXZEA, rax; ulong (*g_VpnIkeRoamToBestCostInterface)(void)
0x1800e112e  test    rax, rax
0x1800e1131  jnz     loc_1800E11E2
0x1800e1137  mov     rax, cs:WPP_GLOBAL_Control
0x1800e113e  lea     r15, WPP_GLOBAL_Control
0x1800e1145  mov     r14d, 1
0x1800e114b  cmp     rax, r15
0x1800e114e  jz      loc_1800E11EF
0x1800e1154  test    [rax+1Ch], r14b
0x1800e1158  jz      loc_1800E11EF
0x1800e115e  call    cs:__imp_GetLastError
0x1800e1165  nop     dword ptr [rax+rax+00h]
0x1800e116a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1171  mov     edx, 32Eh
0x1800e1176  mov     r9d, eax
0x1800e1179  mov     r8, rsi
0x1800e117c  mov     rcx, [rcx+10h]
0x1800e1180  call    WPP_SF_d
0x1800e1185  jmp     short loc_1800E11EF
0x1800e1187  cmp     rcx, rdi
0x1800e118a  jz      loc_1800E10F8
0x1800e1190  test    byte ptr [rcx+1Ch], 1
0x1800e1194  lea     rsi, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800e119b  jz      loc_1800E10FF
0x1800e11a1  mov     rcx, [rcx+10h]
0x1800e11a5  mov     edx, 32Dh
0x1800e11aa  mov     r8, rsi
0x1800e11ad  call    WPP_SF_
0x1800e11b2  jmp     loc_1800E10E8
0x1800e11b7  lea     r15, WPP_GLOBAL_Control
0x1800e11be  mov     r14d, 1
0x1800e11c4  cmp     rcx, r15
0x1800e11c7  jz      short loc_1800E11EF
0x1800e11c9  test    [rcx+1Ch], r14b
0x1800e11cd  jz      short loc_1800E11EF
0x1800e11cf  mov     rcx, [rcx+10h]
0x1800e11d3  mov     edx, 32Fh
0x1800e11d8  mov     r8, rsi
0x1800e11db  call    WPP_SF_
0x1800e11e0  jmp     short loc_1800E11EF
0x1800e11e2  mov     r14d, 1
0x1800e11e8  lea     r15, WPP_GLOBAL_Control
0x1800e11ef  call    IsDomainJoined
0x1800e11f4  mov     cs:?g_bIsDomainJoined@@3HA, eax; int g_bIsDomainJoined
0x1800e11fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1201  cmp     rcx, r15
0x1800e1204  jz      short loc_1800E1223
0x1800e1206  test    byte ptr [rcx+1Ch], 4
0x1800e120a  jz      short loc_1800E1223
0x1800e120c  mov     rcx, [rcx+10h]
0x1800e1210  test    eax, eax
0x1800e1212  mov     edx, 330h
0x1800e1217  mov     r8, rsi
0x1800e121a  setnz   r9b
0x1800e121e  call    WPP_SF_c
0x1800e1223  xor     r8d, r8d; authIdentity
0x1800e1226  mov     [rbp+57h+session.flags], r14d
0x1800e122a  lea     rax, ?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800e1231  xor     ecx, ecx; serverName
0x1800e1233  lea     r9, [rbp+57h+session]; session
0x1800e1237  mov     [rsp+110h+engineHandle], rax; engineHandle
0x1800e123c  lea     edx, [r8+0Ah]; authnService
0x1800e1240  call    cs:__imp_FwpmEngineOpen0
0x1800e1247  nop     dword ptr [rax+rax+00h]
0x1800e124c  mov     ebx, eax
0x1800e124e  test    eax, eax
0x1800e1250  jz      short loc_1800E1293
0x1800e1252  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1259  cmp     rcx, r15
0x1800e125c  jz      short loc_1800E1278
0x1800e125e  test    [rcx+1Ch], r14b
0x1800e1262  jz      short loc_1800E1278
0x1800e1264  mov     rcx, [rcx+10h]
0x1800e1268  mov     edx, 331h
0x1800e126d  mov     r9d, eax
0x1800e1270  mov     r8, rsi
0x1800e1273  call    WPP_SF_d
0x1800e1278  lea     rdx, aFwpmengineopen; "FwpmEngineOpen0"
0x1800e127f  mov     r8d, ebx
0x1800e1282  lea     rcx, aVpnprofilelibi; "VpnProfileLibInitialize"
0x1800e1289  call    VpnReportError
0x1800e128e  jmp     loc_1800E1E8C
0x1800e1293  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800e129a  lea     rax, ?g_TriggerEventHandle@@3PEAXEA; void * g_TriggerEventHandle
0x1800e12a1  xor     r9d, r9d
0x1800e12a4  mov     [rsp+110h+engineHandle], rax
0x1800e12a9  lea     r8, ?int_AppTriggerEventCallback@@YAKPEAXPEBUFWPI_VPN_TRIGGER_EVENT0_@@@Z; int_AppTriggerEventCallback(void *,FWPI_VPN_TRIGGER_EVENT0_ const *)
0x1800e12b0  lea     rdx, [rbp+57h+var_C8]
0x1800e12b4  call    cs:__imp_FwpiVpnTriggerEventSubscribe0
0x1800e12bb  nop     dword ptr [rax+rax+00h]
0x1800e12c0  mov     ebx, eax
0x1800e12c2  test    eax, eax
0x1800e12c4  jz      short loc_1800E12F5
0x1800e12c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e12cd  cmp     rcx, r15
0x1800e12d0  jz      short loc_1800E12EC
0x1800e12d2  test    [rcx+1Ch], r14b
0x1800e12d6  jz      short loc_1800E12EC
0x1800e12d8  mov     rcx, [rcx+10h]
0x1800e12dc  mov     edx, 332h
0x1800e12e1  mov     r9d, eax
0x1800e12e4  mov     r8, rsi
0x1800e12e7  call    WPP_SF_d
0x1800e12ec  lea     rdx, aFwpivpntrigger_1; "FwpiVpnTriggerEventSubscribe0"
0x1800e12f3  jmp     short loc_1800E127F
0x1800e12f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e12fc  cmp     rcx, r15
0x1800e12ff  jz      short loc_1800E1318
0x1800e1301  test    byte ptr [rcx+1Ch], 4
0x1800e1305  jz      short loc_1800E1318
0x1800e1307  mov     rcx, [rcx+10h]
0x1800e130b  mov     edx, 333h
0x1800e1310  mov     r8, rsi
0x1800e1313  call    WPP_SF_
0x1800e1318  call    ?int_VpnProfileCleanNRPTRule@@YAXXZ; int_VpnProfileCleanNRPTRule(void)
0x1800e131d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1324  cmp     rcx, r15
0x1800e1327  jz      short loc_1800E1340
0x1800e1329  test    byte ptr [rcx+1Ch], 4
0x1800e132d  jz      short loc_1800E1340
  ... truncated ...
```
