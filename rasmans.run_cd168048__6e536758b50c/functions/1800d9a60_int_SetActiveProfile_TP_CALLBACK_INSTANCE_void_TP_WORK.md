# int_SetActiveProfile(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1800d9a60`
- end: `0x1800da6c9`
- name: `?int_SetActiveProfile@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `3177`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x180068a80`
- `0x1800aa594`
- `0x1800aa728`
- `0x1800ab588`
- `0x1800ac87c`
- `0x1800acc68`
- `0x1800c5570`
- `0x1800c6b3c`
- `0x1800c6be8`
- `0x1800d9a60`
- `0x1800da820`
- `0x1800de658`
- `0x1800de7e0`
- `0x1800def90`
- `0x1800df9dc`
- `0x1800dfbdc`
- `0x1800e0a90`
- `0x1800e2748`
- `0x1800e2cd8`
- `0x1800e3e00`
- `0x1800e3e30`
- `0x1800e3fac`
- `0x1800e427c`
- `0x1800e4534`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x1800da0cd`
- `ntdll!RtlFreeSid` at `0x1800da0cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da28f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da28f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da66c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da66c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800da5ce`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800da5ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800da27f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800da27f`

## string_xrefs

- `0x1800da263`: `VpnStringCopy for pProfileName`
- `0x1800da1c9`: `VpnStringCopy for pProfilePhonebookPath `

## pseudocode

```c
void __fastcall int_SetActiveProfile(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)
{
  DWORD v3; // r13d
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v5; // r12
  struct _LIST_ENTRY *v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  struct _LIST_ENTRY *v9; // rcx
  __int64 v10; // rdx
  struct _LIST_ENTRY *v11; // rdi
  struct _LIST_ENTRY *Blink; // r14
  const WCHAR *v13; // r15
  int v14; // ebx
  unsigned int Blink_high; // ebp
  struct _LIST_ENTRY **v16; // rdx
  const char *v17; // r8
  const char *v18; // rax
  LPCWSTR *v19; // rsi
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned int v23; // eax
  struct _LIST_ENTRY *v24; // rcx
  __int64 v25; // rdx
  unsigned int v26; // eax
  int v27; // ebx
  unsigned int v28; // eax
  struct _LIST_ENTRY *v29; // rcx
  LPCWSTR v30; // rax
  int v31; // edx
  int v32; // r8d
  LPCWSTR v33; // rax
  int v34; // r8d
  int v35; // edx
  unsigned int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rdx
  LPCWSTR v39; // rax
  int v40; // edx
  int v41; // r8d
  LPCWSTR v42; // rax
  int v43; // r8d
  int v44; // edx
  WCHAR *v45; // rcx
  _DWORD **v46; // rdi
  int v47; // ebx
  int v48; // eax
  int v49; // ecx
  __int64 *v50; // rdi
  int v51; // eax
  unsigned int v52; // ebx
  int v53; // eax
  unsigned int v54; // ecx
  DWORD LastError; // eax
  DWORD v56; // ebx
  struct _LIST_ENTRY *v57; // rcx
  __int64 v58; // rdx
  DWORD v59; // eax
  struct _LIST_ENTRY *v60; // rcx
  DWORD v61; // eax
  int v62; // r8d
  __int64 v63; // r9
  unsigned int LockdownNciNrptRule; // eax
  DWORD ActiveTokenAndSessionId; // eax
  unsigned int v66; // eax
  __int64 v67; // r8
  __int64 v68; // r9
  struct _LIST_ENTRY *v69; // rcx
  __int64 v70; // rdx
  unsigned int v71; // eax
  struct _LIST_ENTRY *v72; // rcx
  bool v73; // di
  struct _TP_WORK *v74; // rcx
  PSID Sid; // [rsp+40h] [rbp-58h] BYREF
  DWORD v76; // [rsp+B8h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 597, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
  v3 = 0;
  Sid = 0;
  v76 = 0;
  VpnCriticalSectionEnter(&g_CsSetActiveProfileOperation);
  Flink = g_RasSetActiveList.Flink;
  if ( g_RasSetActiveList.Flink == &g_RasSetActiveList )
  {
    v5 = 0;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 598, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
    }
  }
  else
  {
    if ( g_RasSetActiveList.Flink->Blink != &g_RasSetActiveList
      || (v6 = g_RasSetActiveList.Flink->Flink, g_RasSetActiveList.Flink->Flink->Blink != g_RasSetActiveList.Flink) )
    {
      __fastfail(3u);
    }
    g_RasSetActiveList.Flink = g_RasSetActiveList.Flink->Flink;
    v5 = Flink - 2;
    v6->Blink = &g_RasSetActiveList;
  }
  VpnCriticalSectionLeave(&g_CsSetActiveProfileOperation);
  VpnCriticalSectionEnter(&g_LpCriticalSection);
  if ( !v5 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v10 = 599;
LABEL_231:
      WPP_SF_(v9[1].Flink, v10, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
      goto LABEL_232;
    }
    goto LABEL_232;
  }
  v11 = v5->Flink;
  Blink = v5->Blink;
  v13 = (const WCHAR *)v5[1].Flink;
  v14 = (int)v5[1].Blink;
  Blink_high = HIDWORD(v5[1].Blink);
  v9 = WPP_GLOBAL_Control;
  v16 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
  {
    v17 = L"<NULL>";
    v18 = L"<NULL>";
    if ( v13 )
      v17 = (const char *)v5[1].Flink;
    if ( Blink )
      v18 = (const char *)v5->Blink;
    WPP_SF_SSScc((TRACEHANDLE)WPP_GLOBAL_Control[1].Flink, (__int64)v18, (__int64)v17, v14 != 0, Blink_high != 0);
    v9 = WPP_GLOBAL_Control;
  }
  v19 = &g_ActiveUserProfile;
  if ( !Blink_high )
    v19 = &g_ActiveDeviceProfile;
  if ( !v14 )
    goto LABEL_50;
  if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v9[1].Blink) & 4) != 0 )
    WPP_SF_(v9[1].Flink, 601, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
  if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(v9, VpnAutoTriggerProfileDeleted, v19[1]);
  VpnProfileDeActivateAutoTrigger(1, Blink_high, 7);
  VpnProfileActiveFree(v19);
  if ( Blink_high )
    g_IsActiveUserProfile = 0;
  else
    g_IsActiveDeviceProfile = 0;
  DisableAutoWPPTracingForSubComponent(0);
  if ( Blink_high )
  {
    if ( !g_pNrptRuleListPersistentPrefixForUserTunnel )
      goto LABEL_45;
    v23 = RasRemoveNrptRules(g_pNrptRuleListPersistentPrefixForUserTunnel);
    if ( !v23 )
      goto LABEL_45;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_45;
    }
    v25 = 602;
  }
  else
  {
    if ( !g_pNrptRuleListPersistentPrefixForDeviceTunnel )
      goto LABEL_45;
    v23 = RasRemoveNrptRules(g_pNrptRuleListPersistentPrefixForDeviceTunnel);
    if ( !v23 )
      goto LABEL_45;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_45;
    }
    v25 = 603;
  }
  WPP_SF_d(v24[1].Flink, v25, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v23);
LABEL_45:
  v26 = VpnProfileSetRasManServiceState(0, v20, v21, v22);
  if ( !v26 )
  {
LABEL_49:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_50;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 604, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v26);
    goto LABEL_49;
  }
LABEL_50:
  if ( v11 && Blink && v13 )
  {
    v27 = 1;
    if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v9[1].Blink) & 4) != 0 )
      WPP_SF_(v9[1].Flink, 605, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
    v28 = VpnProfileSetRasManServiceState(1, (__int64)v16, v7, v8);
    if ( v28 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
LABEL_61:
        if ( Blink_high )
        {
          if ( g_IsActiveUserProfile )
          {
            if ( v29 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v29[1].Blink) & 4) != 0 )
            {
              WPP_SF_(v29[1].Flink, 607, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
              v29 = WPP_GLOBAL_Control;
            }
            v30 = g_ActiveUserProfile;
            do
            {
              v31 = *(LPCWSTR)((char *)v30 + (char *)v11 - (char *)g_ActiveUserProfile);
              v32 = *v30 - v31;
              if ( v32 )
                break;
              ++v30;
            }
            while ( v31 );
            if ( v32 )
              goto LABEL_76;
            v33 = qword_18010EF48;
            do
            {
              v34 = *(LPCWSTR)((char *)v33 + (char *)Blink - (char *)qword_18010EF48);
              v35 = *v33 - v34;
              if ( v35 )
                break;
              ++v33;
            }
            while ( v34 );
            if ( v35 )
            {
LABEL_76:
              if ( v29 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v29[1].Blink) & 4) != 0 )
                WPP_SF_(v29[1].Flink, 608, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
              VpnProfileDeActivateAutoTrigger(1, Blink_high, 7);
              VpnProfileActiveFree(&g_ActiveUserProfile);
              v29 = WPP_GLOBAL_Control;
              g_IsActiveUserProfile = 0;
            }
            else
            {
              v27 = 0;
            }
            if ( !g_pNrptRuleListPersistentPrefixForUserTunnel )
              goto LABEL_111;
            v36 = RasRemoveNrptRules(g_pNrptRuleListPersistentPrefixForUserTunnel);
            if ( v36 )
            {
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                v37 = 609;
LABEL_109:
                WPP_SF_d(v29[1].Flink, v37, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v36);
                goto LABEL_110;
              }
              goto LABEL_111;
            }
            goto LABEL_110;
          }
          if ( v29 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v29[1].Blink) & 4) != 0 )
          {
            v38 = 610;
LABEL_126:
            WPP_SF_(v29[1].Flink, v38, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
          }
        }
        else
        {
          if ( g_IsActiveDeviceProfile )
          {
            if ( v29 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v29[1].Blink) & 4) != 0 )
            {
              WPP_SF_(v29[1].Flink, 611, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
              v29 = WPP_GLOBAL_Control;
            }
            v39 = g_ActiveDeviceProfile;
            do
            {
              v40 = *(LPCWSTR)((char *)v39 + (char *)v11 - (char *)g_ActiveDeviceProfile);
              v41 = *v39 - v40;
              if ( v41 )
                break;
              ++v39;
            }
            while ( v40 );
            if ( v41 )
              goto LABEL_101;
            v42 = qword_18010F1A8;
            do
            {
              v43 = *(LPCWSTR)((char *)v42 + (char *)Blink - (char *)qword_18010F1A8);
              v44 = *v42 - v43;
              if ( v44 )
                break;
              ++v42;
            }
            while ( v43 );
            if ( v44 )
            {
LABEL_101:
              if ( v29 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v29[1].Blink) & 4) != 0 )
                WPP_SF_(v29[1].Flink, 612, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
              VpnProfileDeActivateAutoTrigger(1, 0, 7);
              VpnProfileActiveFree(&g_ActiveDeviceProfile);
              v29 = WPP_GLOBAL_Control;
              g_IsActiveDeviceProfile = 0;
            }
            else
            {
              v27 = 0;
            }
            if ( !g_pNrptRuleListPersistentPrefixForDeviceTunnel )
              goto LABEL_111;
            v36 = RasRemoveNrptRules(g_pNrptRuleListPersistentPrefixForDeviceTunnel);
            if ( v36 )
            {
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                v37 = 613;
                goto LABEL_109;
              }
LABEL_111:
              if ( !v27 )
              {
                if ( v29 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v29[1].Blink) & 4) != 0 )
                {
                  WPP_SF_(v29[1].Flink, 623, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
                  v29 = WPP_GLOBAL_Control;
                }
                if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
                {
                  McTemplateU0z_EventWriteTransfer(v29, VpnAutoTriggerProfileModified, v19[1]);
                  v29 = WPP_GLOBAL_Control;
                }
                if ( v29 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v29[1].Blink) & 4) != 0 )
                  WPP_SF_SS(
                    v29[1].Flink,
                    624,
                    (unsigned int)&WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                    (unsigned int)*v19,
                    (__int64)v19[1]);
                v45 = (WCHAR *)v19[73];
                if ( v45 )
                {
                  RtlFreeSid(v45);
                  v19[73] = 0;
                }
                v46 = (_DWORD **)(v19 + 74);
                VpnProfileActiveSettingsFree((LPVOID)v19[74]);
                v19[74] = 0;
                *((_DWORD *)v19 + 6) = 0;
                goto LABEL_178;
              }
LABEL_130:
              if ( v29 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v29[1].Blink) & 4) != 0 )
                WPP_SF_(v29[1].Flink, 615, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
              v47 = VpnStringCopy(v11);
              if ( v47 >= 0
                || WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
              {
                if ( v47 >= 0 )
                  goto LABEL_145;
              }
              else
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control[1].Flink,
                  616,
                  &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                  (unsigned int)v47);
              }
              v48 = (v47 >> 16) & 0x1FFF;
              if ( v48 == 7 )
                v49 = (unsigned __int16)v47;
              else
                v49 = v47;
              if ( v49 )
              {
                if ( v48 == 7 )
                  v47 = (unsigned __int16)v47;
                VpnReportError("int_SetActiveProfile", "VpnStringCopy for pProfilePhonebookPath ", (unsigned int)v47);
                goto LABEL_232;
              }
LABEL_145:
              v50 = (__int64 *)(v19 + 1);
              v51 = VpnStringCopy(Blink);
              v52 = v51;
              if ( v51 >= 0
                || WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
              {
                if ( v51 >= 0 )
                {
LABEL_157:
                  if ( ConvertStringSidToSidW(v13, &Sid) )
                  {
                    v59 = VpnSidCopy(Sid);
                    v56 = v59;
                    if ( v59 )
                    {
                      v57 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                        goto LABEL_232;
                      if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                      {
                        WPP_SF_d(
                          WPP_GLOBAL_Control[1].Flink,
                          620,
                          &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                          v59);
                        v57 = WPP_GLOBAL_Control;
                      }
                      if ( v57 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v57[1].Blink) & 1) == 0 )
                        goto LABEL_232;
                      v58 = 621;
                      goto LABEL_226;
                    }
                  }
                  else
                  {
                    LastError = GetLastError();
                    v56 = LastError;
                    if ( LastError )
                    {
                      v57 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                        goto LABEL_232;
                      if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                      {
                        WPP_SF_d(
                          WPP_GLOBAL_Control[1].Flink,
                          618,
                          &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                          LastError);
                        v57 = WPP_GLOBAL_Control;
                      }
                      if ( v57 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v57[1].Blink) & 1) == 0 )
                        goto LABEL_232;
                      v58 = 619;
                      goto LABEL_226;
                    }
                  }
                  v60 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
                  {
                    WPP_SF_SS(
                      WPP_GLOBAL_Control[1].Flink,
                      622,
                      (unsigned int)&WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                      (unsigned int)*v19,
                      *v50);
                  }
                  if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
                    McTemplateU0z_EventWriteTransfer(v60, VpnAutoTriggerProfileAdded, *v50);
                  v46 = (_DWORD **)(v19 + 74);
LABEL_178:
                  v61 = VpnProfileActiveSettingsGet(*v19, v19[1]);
                  v56 = v61;
                  if ( v61 )
                  {
                    v57 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
                    {
                      goto LABEL_232;
                    }
                    v58 = 625;
                    v63 = v61;
LABEL_227:
                    WPP_SF_d(v57[1].Flink, v58, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v63);
                    goto LABEL_232;
                  }
                  if ( (*v46)[33]
                    && (LockdownNciNrptRule = int_VpnCreateLockdownNciNrptRule((unsigned __int16 *)v19[1]),
                        (v56 = LockdownNciNrptRule) != 0) )
                  {
                    v57 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                    {
                      WPP_SF_d(
                        WPP_GLOBAL_Control[1].Flink,
                        626,
                        &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                        LockdownNciNrptRule);
                      v57 = WPP_GLOBAL_Control;
                    }
                    v56 = 0;
                  }
                  else
                  {
                    v57 = WPP_GLOBAL_Control;
                  }
                  if ( Blink_high )
                  {
                    ActiveTokenAndSessionId = GetActiveTokenAndSessionId((void *)v19[2], &v76, 0);
                    v57 = WPP_GLOBAL_Control;
                    v56 = ActiveTokenAndSessionId;
                    v3 = v76;
                  }
                  if ( !v56 )
                  {
                    v66 = RasAddNrptRulesEx(*((_QWORD *)*v46 + 1), **v46, v62, 0, 1, 0);
                    if ( v66 )
                    {
                      v69 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
                      {
LABEL_197:
                        *((_DWORD *)v19 + 6) = v3;
                        if ( Blink_high )
                        {
                          g_IsActiveUserProfile = 1;
                          if ( v69 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v69[1].Blink) & 4) == 0 )
                            goto LABEL_205;
                          v70 = 628;
                        }
                        else
                        {
                          g_IsActiveDeviceProfile = 1;
                          if ( v69 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v69[1].Blink) & 4) == 0 )
                            goto LABEL_205;
                          v70 = 629;
                        }
                        WPP_SF_(v69[1].Flink, v70, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
LABEL_205:
                        v71 = VpnProfileActivateAutoTrigger((__int64)v19, Blink_high, v67, v68);
                        if ( v71 )
                        {
                          v72 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                          {
                            WPP_SF_d(
                              WPP_GLOBAL_Control[1].Flink,
                              630,
                              &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                              v71);
                            v72 = WPP_GLOBAL_Control;
                          }
                        }
                        else
                        {
                          v72 = WPP_GLOBAL_Control;
                        }
                        if ( v72 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v72[1].Blink) & 4) != 0 )
                          WPP_SF_(v72[1].Flink, 631, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
                        VpnCriticalSectionEnter(&g_CsLogicalConnection);
                        v73 = g_fIsDeviceTunnelAllowed;
                        VpnCriticalSectionLeave(&g_CsLogicalConnection);
                        if ( Blink_high || v73 )
                        {
                          AddVPNTriggerEvent(7, Blink_high);
                          v74 = g_pReConnectUserTunnelWorkItem;
                          if ( !Blink_high )
                            v74 = g_pReConnectDeviceTunnelWorkItem;
                          SubmitThreadpoolWork(v74);
                        }
                        goto LABEL_232;
                      }
                      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 627, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v66);
                    }
                    v69 = WPP_GLOBAL_Control;
                    goto LABEL_197;
                  }
                  if ( v57 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                    goto LABEL_232;
                  if ( (BYTE4(v57[1].Blink) & 1) != 0 )
                  {
                    WPP_SF_d(v57[1].Flink, 632, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v56);
                    v57 = WPP_GLOBAL_Control;
                  }
                  if ( v57 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v57[1].Blink) & 1) == 0 )
                    goto LABEL_232;
                  v58 = 633;
LABEL_226:
                  v63 = v56;
                  goto LABEL_227;
                }
              }
              else
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control[1].Flink,
                  617,
                  &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                  (unsigned int)v51);
                v51 = v52;
              }
              v53 = (v51 >> 16) & 0x1FFF;
              if ( v53 == 7 )
                v54 = (unsigned __int16)v52;
              else
                v54 = v52;
              if ( v54 )
              {
                if ( v53 == 7 )
                  v52 = (unsigned __int16)v52;
                VpnReportError("int_SetActiveProfile", "VpnStringCopy for pProfileName", v52);
                goto LABEL_232;
              }
              goto LABEL_157;
            }
LABEL_110:
            v29 = WPP_GLOBAL_Control;
            goto LABEL_111;
          }
          if ( v29 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v29[1].Blink) & 4) != 0 )
          {
            v38 = 614;
            goto LABEL_126;
          }
        }
        if ( (unsigned int)IsDefaultTracingEnabled() )
          EnableAutoWPPTracingForSubComponent(0);
        v29 = WPP_GLOBAL_Control;
        goto LABEL_130;
      }
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 606, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v28);
    }
    v29 = WPP_GLOBAL_Control;
    goto LABEL_61;
  }
  if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v9[1].Blink) & 1) != 0 )
  {
    v10 = 634;
    goto LABEL_231;
  }
LABEL_232:
  VpnCriticalSectionLeave(&g_LpCriticalSection);
  if ( Sid )
  {
    LocalFree(Sid);
    Sid = 0;
  }
  FreeSetProfileContext((struct _SET_ACTIVE_PROFILE_WORK_CONTEXT *)v5);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 635, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
}

```

## disassembly

```asm
0x1800d9a60  push    rbx
0x1800d9a62  push    rbp
0x1800d9a63  push    rsi
0x1800d9a64  push    rdi
0x1800d9a65  push    r12
0x1800d9a67  push    r13
0x1800d9a69  push    r14
0x1800d9a6b  push    r15
0x1800d9a6d  sub     rsp, 58h
0x1800d9a71  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9a78  lea     r14, WPP_GLOBAL_Control
0x1800d9a7f  cmp     rcx, r14
0x1800d9a82  jz      short loc_1800D9A9F
0x1800d9a84  test    byte ptr [rcx+1Ch], 8
0x1800d9a88  jz      short loc_1800D9A9F
0x1800d9a8a  mov     rcx, [rcx+10h]
0x1800d9a8e  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d9a95  mov     edx, 255h
0x1800d9a9a  call    WPP_SF_
0x1800d9a9f  xor     r13d, r13d
0x1800d9aa2  mov     [rsp+98h+Sid], 0
0x1800d9aab  lea     rcx, ?g_CsSetActiveProfileOperation@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_CsSetActiveProfileOperation
0x1800d9ab2  mov     [rsp+98h+arg_18], r13d
0x1800d9aba  call    VpnCriticalSectionEnter
0x1800d9abf  mov     rax, cs:?g_RasSetActiveList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_RasSetActiveList
0x1800d9ac6  lea     rcx, ?g_RasSetActiveList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_RasSetActiveList
0x1800d9acd  cmp     rax, rcx
0x1800d9ad0  jnz     short loc_1800D9AFE
0x1800d9ad2  xor     r12d, r12d
0x1800d9ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9adc  cmp     rcx, r14
0x1800d9adf  jz      short loc_1800D9B24
0x1800d9ae1  test    byte ptr [rcx+1Ch], 1
0x1800d9ae5  jz      short loc_1800D9B24
0x1800d9ae7  mov     rcx, [rcx+10h]
0x1800d9aeb  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d9af2  mov     edx, 256h
0x1800d9af7  call    WPP_SF_
0x1800d9afc  jmp     short loc_1800D9B24
0x1800d9afe  cmp     [rax+8], rcx
0x1800d9b02  jnz     loc_1800DA6C2
0x1800d9b08  mov     rdx, [rax]
0x1800d9b0b  cmp     [rdx+8], rax
0x1800d9b0f  jnz     loc_1800DA6C2
0x1800d9b15  mov     cs:?g_RasSetActiveList@@3U_LIST_ENTRY@@A, rdx; _LIST_ENTRY g_RasSetActiveList
0x1800d9b1c  lea     r12, [rax-20h]
0x1800d9b20  mov     [rdx+8], rcx
0x1800d9b24  lea     rcx, ?g_CsSetActiveProfileOperation@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_CsSetActiveProfileOperation
0x1800d9b2b  call    VpnCriticalSectionLeave
0x1800d9b30  lea     rcx, ?g_LpCriticalSection@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_LpCriticalSection
0x1800d9b37  call    VpnCriticalSectionEnter
0x1800d9b3c  test    r12, r12
0x1800d9b3f  jnz     short loc_1800D9B65
0x1800d9b41  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9b48  cmp     rcx, r14
0x1800d9b4b  jz      loc_1800DA656
0x1800d9b51  test    byte ptr [rcx+1Ch], 1
0x1800d9b55  jz      loc_1800DA656
0x1800d9b5b  mov     edx, 257h
0x1800d9b60  jmp     loc_1800DA646
0x1800d9b65  mov     rdi, [r12]
0x1800d9b69  mov     r14, [r12+8]
0x1800d9b6e  mov     r15, [r12+10h]
0x1800d9b73  mov     ebx, [r12+18h]
0x1800d9b78  mov     ebp, [r12+1Ch]
0x1800d9b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9b84  lea     rdx, WPP_GLOBAL_Control
0x1800d9b8b  cmp     rcx, rdx
0x1800d9b8e  jz      short loc_1800D9BED
0x1800d9b90  test    byte ptr [rcx+1Ch], 4
0x1800d9b94  jz      short loc_1800D9BED
0x1800d9b96  mov     rcx, [rcx+10h]; LoggerHandle
0x1800d9b9a  lea     r9, aNull_4; "<NULL>"
0x1800d9ba1  test    ebp, ebp
0x1800d9ba3  mov     r8, r9
0x1800d9ba6  mov     rax, r9
0x1800d9ba9  mov     edx, 258h
0x1800d9bae  setnz   r11b
0x1800d9bb2  test    ebx, ebx
0x1800d9bb4  mov     [rsp+98h+var_60], r11b; char
0x1800d9bb9  setnz   r10b
0x1800d9bbd  test    r15, r15
0x1800d9bc0  mov     [rsp+98h+var_68], r10b; char
0x1800d9bc5  cmovnz  r8, r15
0x1800d9bc9  test    r14, r14
0x1800d9bcc  mov     [rsp+98h+var_70], r8; __int64
0x1800d9bd1  cmovnz  rax, r14
0x1800d9bd5  test    rdi, rdi
0x1800d9bd8  mov     [rsp+98h+var_78], rax; __int64
0x1800d9bdd  cmovnz  r9, rdi
0x1800d9be1  call    WPP_SF_SSScc
0x1800d9be6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9bed  test    ebp, ebp
0x1800d9bef  lea     rax, ?g_ActiveDeviceProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveDeviceProfile
0x1800d9bf6  lea     rsi, ?g_ActiveUserProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveUserProfile
0x1800d9bfd  cmovz   rsi, rax
0x1800d9c01  test    ebx, ebx
0x1800d9c03  jz      loc_1800D9D34
0x1800d9c09  lea     rbx, WPP_GLOBAL_Control
0x1800d9c10  cmp     rcx, rbx
0x1800d9c13  jz      short loc_1800D9C30
0x1800d9c15  test    byte ptr [rcx+1Ch], 4
0x1800d9c19  jz      short loc_1800D9C30
0x1800d9c1b  mov     rcx, [rcx+10h]
0x1800d9c1f  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d9c26  mov     edx, 259h
0x1800d9c2b  call    WPP_SF_
0x1800d9c30  test    cs:Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits, 8
0x1800d9c37  jz      short loc_1800D9C49
0x1800d9c39  mov     r8, [rsi+8]
0x1800d9c3d  lea     rdx, VpnAutoTriggerProfileDeleted
0x1800d9c44  call    McTemplateU0z_EventWriteTransfer
0x1800d9c49  mov     r8d, 7
0x1800d9c4f  mov     edx, ebp
0x1800d9c51  lea     ecx, [r8-6]
0x1800d9c55  call    VpnProfileDeActivateAutoTrigger
0x1800d9c5a  mov     rcx, rsi
0x1800d9c5d  call    VpnProfileActiveFree
0x1800d9c62  test    ebp, ebp
0x1800d9c64  jz      short loc_1800D9C6F
0x1800d9c66  mov     cs:?g_IsActiveUserProfile@@3HA, r13d; int g_IsActiveUserProfile
0x1800d9c6d  jmp     short loc_1800D9C76
0x1800d9c6f  mov     cs:?g_IsActiveDeviceProfile@@3HA, r13d; int g_IsActiveDeviceProfile
0x1800d9c76  xor     ecx, ecx
0x1800d9c78  call    DisableAutoWPPTracingForSubComponent
0x1800d9c7d  test    ebp, ebp
0x1800d9c7f  jz      short loc_1800D9CB4
0x1800d9c81  mov     rcx, cs:?g_pNrptRuleListPersistentPrefixForUserTunnel@@3PEAUtagRASNRPTRULELIST@@EA; tagRASNRPTRULELIST * g_pNrptRuleListPersistentPrefixForUserTunnel
0x1800d9c88  test    rcx, rcx
0x1800d9c8b  jz      short loc_1800D9CF8
0x1800d9c8d  mov     edx, 1
0x1800d9c92  call    RasRemoveNrptRules
0x1800d9c97  test    eax, eax
0x1800d9c99  jz      short loc_1800D9CF8
0x1800d9c9b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9ca2  cmp     rcx, rbx
0x1800d9ca5  jz      short loc_1800D9CF8
0x1800d9ca7  test    byte ptr [rcx+1Ch], 1
0x1800d9cab  jz      short loc_1800D9CF8
0x1800d9cad  mov     edx, 25Ah
0x1800d9cb2  jmp     short loc_1800D9CE5
0x1800d9cb4  mov     rcx, cs:?g_pNrptRuleListPersistentPrefixForDeviceTunnel@@3PEAUtagRASNRPTRULELIST@@EA; tagRASNRPTRULELIST * g_pNrptRuleListPersistentPrefixForDeviceTunnel
0x1800d9cbb  test    rcx, rcx
0x1800d9cbe  jz      short loc_1800D9CF8
0x1800d9cc0  mov     edx, 1
0x1800d9cc5  call    RasRemoveNrptRules
0x1800d9cca  test    eax, eax
0x1800d9ccc  jz      short loc_1800D9CF8
0x1800d9cce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9cd5  cmp     rcx, rbx
0x1800d9cd8  jz      short loc_1800D9CF8
0x1800d9cda  test    byte ptr [rcx+1Ch], 1
0x1800d9cde  jz      short loc_1800D9CF8
0x1800d9ce0  mov     edx, 25Bh
0x1800d9ce5  mov     rcx, [rcx+10h]
0x1800d9ce9  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d9cf0  mov     r9d, eax
0x1800d9cf3  call    WPP_SF_d
0x1800d9cf8  xor     ecx, ecx
0x1800d9cfa  call    VpnProfileSetRasManServiceState
0x1800d9cff  test    eax, eax
0x1800d9d01  jz      short loc_1800D9D2D
0x1800d9d03  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9d0a  cmp     rcx, rbx
0x1800d9d0d  jz      short loc_1800D9D34
0x1800d9d0f  test    byte ptr [rcx+1Ch], 1
0x1800d9d13  jz      short loc_1800D9D34
0x1800d9d15  mov     rcx, [rcx+10h]
0x1800d9d19  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d9d20  mov     edx, 25Ch
0x1800d9d25  mov     r9d, eax
0x1800d9d28  call    WPP_SF_d
0x1800d9d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9d34  test    rdi, rdi
0x1800d9d37  jz      loc_1800DA62F
0x1800d9d3d  test    r14, r14
0x1800d9d40  jz      loc_1800DA62F
0x1800d9d46  test    r15, r15
0x1800d9d49  jz      loc_1800DA62F
0x1800d9d4f  mov     ebx, 1
0x1800d9d54  lea     rax, WPP_GLOBAL_Control
0x1800d9d5b  cmp     rcx, rax
0x1800d9d5e  jz      short loc_1800D9D7B
0x1800d9d60  test    byte ptr [rcx+1Ch], 4
0x1800d9d64  jz      short loc_1800D9D7B
0x1800d9d66  mov     rcx, [rcx+10h]
0x1800d9d6a  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d9d71  mov     edx, 25Dh
0x1800d9d76  call    WPP_SF_
0x1800d9d7b  mov     ecx, ebx
0x1800d9d7d  call    VpnProfileSetRasManServiceState
0x1800d9d82  test    eax, eax
0x1800d9d84  jz      short loc_1800D9DB6
0x1800d9d86  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9d8d  lea     r10, WPP_GLOBAL_Control
0x1800d9d94  cmp     rcx, r10
0x1800d9d97  jz      short loc_1800D9DC4
0x1800d9d99  test    [rcx+1Ch], bl
0x1800d9d9c  jz      short loc_1800D9DC4
0x1800d9d9e  mov     rcx, [rcx+10h]
0x1800d9da2  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d9da9  mov     edx, 25Eh
0x1800d9dae  mov     r9d, eax
0x1800d9db1  call    WPP_SF_d
0x1800d9db6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9dbd  lea     r10, WPP_GLOBAL_Control
0x1800d9dc4  test    ebp, ebp
0x1800d9dc6  jz      loc_1800D9F10
0x1800d9dcc  cmp     cs:?g_IsActiveUserProfile@@3HA, r13d; int g_IsActiveUserProfile
0x1800d9dd3  jz      loc_1800D9EF3
0x1800d9dd9  cmp     rcx, r10
0x1800d9ddc  jz      short loc_1800D9E07
0x1800d9dde  test    byte ptr [rcx+1Ch], 4
0x1800d9de2  jz      short loc_1800D9E07
0x1800d9de4  mov     rcx, [rcx+10h]
0x1800d9de8  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d9def  mov     edx, 25Fh
0x1800d9df4  call    WPP_SF_
0x1800d9df9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9e00  lea     r10, WPP_GLOBAL_Control
0x1800d9e07  mov     rax, cs:?g_ActiveUserProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveUserProfile
0x1800d9e0e  mov     r9, rdi
0x1800d9e11  sub     r9, rax
0x1800d9e14  movzx   r8d, word ptr [rax]
0x1800d9e18  movzx   edx, word ptr [rax+r9]
0x1800d9e1d  sub     r8d, edx
0x1800d9e20  jnz     short loc_1800D9E2A
0x1800d9e22  add     rax, 2
0x1800d9e26  test    edx, edx
0x1800d9e28  jnz     short loc_1800D9E14
0x1800d9e2a  test    r8d, r8d
0x1800d9e2d  jnz     short loc_1800D9E5A
0x1800d9e2f  mov     rax, cs:qword_18010EF48
0x1800d9e36  mov     r9, r14
0x1800d9e39  sub     r9, rax
0x1800d9e3c  movzx   edx, word ptr [rax]
0x1800d9e3f  movzx   r8d, word ptr [rax+r9]
0x1800d9e44  sub     edx, r8d
0x1800d9e47  jnz     short loc_1800D9E52
0x1800d9e49  add     rax, 2
0x1800d9e4d  test    r8d, r8d
0x1800d9e50  jnz     short loc_1800D9E3C
0x1800d9e52  test    edx, edx
0x1800d9e54  jnz     short loc_1800D9E5A
0x1800d9e56  xor     ebx, ebx
0x1800d9e58  jmp     short loc_1800D9EA3
0x1800d9e5a  cmp     rcx, r10
0x1800d9e5d  jz      short loc_1800D9E7A
0x1800d9e5f  test    byte ptr [rcx+1Ch], 4
0x1800d9e63  jz      short loc_1800D9E7A
0x1800d9e65  mov     rcx, [rcx+10h]
0x1800d9e69  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d9e70  mov     edx, 260h
0x1800d9e75  call    WPP_SF_
0x1800d9e7a  mov     r8d, 7
0x1800d9e80  mov     edx, ebp
0x1800d9e82  mov     ecx, ebx
0x1800d9e84  call    VpnProfileDeActivateAutoTrigger
0x1800d9e89  lea     rcx, ?g_ActiveUserProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveUserProfile
0x1800d9e90  call    VpnProfileActiveFree
0x1800d9e95  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9e9c  mov     cs:?g_IsActiveUserProfile@@3HA, r13d; int g_IsActiveUserProfile
0x1800d9ea3  mov     rax, cs:?g_pNrptRuleListPersistentPrefixForUserTunnel@@3PEAUtagRASNRPTRULELIST@@EA; tagRASNRPTRULELIST * g_pNrptRuleListPersistentPrefixForUserTunnel
0x1800d9eaa  test    rax, rax
0x1800d9ead  jz      loc_1800DA03C
0x1800d9eb3  mov     edx, 1
0x1800d9eb8  mov     rcx, rax
0x1800d9ebb  call    RasRemoveNrptRules
0x1800d9ec0  test    eax, eax
0x1800d9ec2  jz      loc_1800DA035
0x1800d9ec8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9ecf  lea     rdx, WPP_GLOBAL_Control
0x1800d9ed6  cmp     rcx, rdx
0x1800d9ed9  jz      loc_1800DA03C
0x1800d9edf  test    byte ptr [rcx+1Ch], 1
0x1800d9ee3  jz      loc_1800DA03C
0x1800d9ee9  mov     edx, 261h
0x1800d9eee  jmp     loc_1800DA022
0x1800d9ef3  cmp     rcx, r10
0x1800d9ef6  jz      loc_1800DA117
0x1800d9efc  test    byte ptr [rcx+1Ch], 4
0x1800d9f00  jz      loc_1800DA117
0x1800d9f06  mov     edx, 262h
0x1800d9f0b  jmp     loc_1800DA107
0x1800d9f10  cmp     cs:?g_IsActiveDeviceProfile@@3HA, r13d; int g_IsActiveDeviceProfile
0x1800d9f17  jz      loc_1800DA0F7
0x1800d9f1d  cmp     rcx, r10
0x1800d9f20  jz      short loc_1800D9F4B
0x1800d9f22  test    byte ptr [rcx+1Ch], 4
0x1800d9f26  jz      short loc_1800D9F4B
0x1800d9f28  mov     rcx, [rcx+10h]
0x1800d9f2c  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d9f33  mov     edx, 263h
0x1800d9f38  call    WPP_SF_
0x1800d9f3d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9f44  lea     r10, WPP_GLOBAL_Control
0x1800d9f4b  mov     rax, cs:?g_ActiveDeviceProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveDeviceProfile
0x1800d9f52  mov     r9, rdi
0x1800d9f55  sub     r9, rax
0x1800d9f58  movzx   r8d, word ptr [rax]
  ... truncated ...
```
