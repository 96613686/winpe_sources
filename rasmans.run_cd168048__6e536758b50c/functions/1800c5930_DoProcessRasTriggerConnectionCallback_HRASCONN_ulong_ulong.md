# DoProcessRasTriggerConnectionCallback(HRASCONN__ *,ulong,ulong)

- ea: `0x1800c5930`
- end: `0x1800c61d1`
- name: `?DoProcessRasTriggerConnectionCallback@@YAKPEAUHRASCONN__@@KK@Z`
- size: `2209`
- prototype: `unsigned int __fastcall(HRASCONN, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d7ed0`
- `0x1800d81b0`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x180005c40`
- `0x180005cf8`
- `0x18000c37c`
- `0x180033b38`
- `0x18005bfd8`
- `0x1800c5464`
- `0x1800c5930`
- `0x1800c8b58`
- `0x1800cda80`
- `0x1800cdf70`
- `0x1800cef08`
- `0x1800cf050`
- `0x1800cfd18`
- `0x1800d0af0`
- `0x1800dc67c`
- `0x1800ddb70`
- `0x1800de658`
- `0x1800e30a4`
- `0x1800e3ca0`
- `0x1800e3e00`
- `0x1800e3e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c6117`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c6117`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800c5d2c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800c5e87`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800c5ea4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800c5d2c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800c5e87`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800c5ea4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c5d6f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c5d6f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800c5e32`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800c5e32`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800c60fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800c60fc`
- `fwpuclnt!FwpiVpnTriggerSetStateDisconnected` at `0x1800c5baf`
- `fwpuclnt!FwpiVpnTriggerSetStateDisconnected` at `0x1800c5baf`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasConnectionNotificationW` at `0x1800c6134`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasConnectionNotificationW` at `0x1800c6134`
- `nlaapi!NlaIndicateReprobe` at `0x1800c5b15`
- `nlaapi!NlaIndicateReprobe` at `0x1800c5b15`

## pseudocode

```c
__int64 __fastcall DoProcessRasTriggerConnectionCallback(HRASCONN a1, int a2, __int64 a3)
{
  int v3; // r14d
  int v4; // ebp
  int v6; // edi
  bool v7; // si
  bool v8; // r15
  LPCWSTR *v9; // rbx
  struct _LIST_ENTRY *v10; // rcx
  unsigned int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // r9
  struct _LIST_ENTRY *v14; // rcx
  struct _TP_WORK *v15; // rcx
  bool v16; // bl
  __int64 v17; // r9
  struct _LIST_ENTRY *v18; // rcx
  bool v19; // dl
  struct _LIST_ENTRY *v20; // rcx
  unsigned int InterfaceInfo; // eax
  __int64 v22; // rdx
  __int64 v23; // rdi
  struct _LIST_ENTRY *v24; // rcx
  __int64 *v25; // rax
  HANDLE v26; // rcx
  DWORD v27; // eax
  bool v29[4]; // [rsp+20h] [rbp-58h]

  v3 = a3;
  v4 = a2;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_qDD(WPP_GLOBAL_Control[1].Flink, 260, a3, a1, a2, a3);
  v6 = 0;
  v7 = v4 == 0;
  VpnCriticalSectionEnter(&g_LpCriticalSection);
  if ( a1 == (HRASCONN)qword_18010EF68 )
  {
    v9 = &g_ActiveUserProfile;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 262, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
    }
    v8 = 1;
  }
  else
  {
    if ( a1 != (HRASCONN)qword_18010F1C8 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 261, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
      }
      goto LABEL_127;
    }
    v8 = 0;
    v9 = &g_ActiveDeviceProfile;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 263, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
    }
  }
  StopNewRetryWaitPeriod(v8);
  if ( v4 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control[1].Flink,
          264,
          &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
          (unsigned int)v4,
          v3);
        v10 = WPP_GLOBAL_Control;
      }
      if ( v10 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v10[1].Blink) & 4) != 0 )
      {
        WPP_SF_ddd(
          v10[1].Flink,
          265,
          &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
          *((unsigned int *)v9 + 7),
          0,
          *((_DWORD *)v9 + 145));
        v10 = WPP_GLOBAL_Control;
      }
    }
    *((_DWORD *)v9 + 7) = 0;
    v9[5] = 0;
    v9[6] = 0;
    *((_DWORD *)v9 + 145) = 0;
    if ( v4 != 868 )
    {
LABEL_35:
      if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(v10, VpnAutoTriggerConnectionAttemptFailed, v9[1]);
        v10 = WPP_GLOBAL_Control;
      }
      if ( !v8 )
      {
        if ( v10 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v10[1].Blink) & 4) != 0 )
          WPP_SF_(v10[1].Flink, 272, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
        if ( !g_IsActiveDeviceProfile || !IsErrorRecoverable(v4, 0) )
        {
          v7 = 1;
          EventActivityIdControl(3u, &stru_18010F458);
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 274, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
          }
          StartNewRetryWaitPeriod(dword_18010F450, v19);
          goto LABEL_89;
        }
        if ( !*(_DWORD *)(qword_18010F3F0 + 128) )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 273, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
          }
          v7 = 1;
          AddVPNCanceledEvent(16, 0);
          EventActivityIdControl(3u, &stru_18010F458);
          goto LABEL_89;
        }
        v15 = g_pReConnectDeviceTunnelWorkItem;
        goto LABEL_80;
      }
      v12 = FwpiVpnTriggerSetStateDisconnected(g_FwpEngineHandle, 0);
      v6 = v12;
      if ( v12 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_46;
        if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
        {
LABEL_43:
          if ( v14 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v14[1].Blink) & 4) != 0 )
          {
            LOBYTE(v13) = g_IsActiveUserProfile != 0;
            WPP_SF_c(v14[1].Flink, 267, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v13);
          }
LABEL_46:
          if ( g_IsActiveUserProfile && IsErrorRecoverable(v4, 1) )
          {
            if ( !*(_DWORD *)(qword_18010F190 + 128) )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control[1].Flink, 269, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
              }
              VpnCriticalSectionEnter(&g_CsActiveTriggerPeriod);
              v16 = g_fIsActiveAppTriggerPeriod;
              VpnCriticalSectionLeave(&g_CsActiveTriggerPeriod);
              if ( !v16 || g_fIsInside )
              {
                LOBYTE(v18) = (_BYTE)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
                {
                  LOBYTE(v17) = v16;
                  v29[0] = g_fIsInside != 0;
                  WPP_SF_cc(
                    WPP_GLOBAL_Control[1].Flink,
                    270,
                    &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                    v17,
                    *(_DWORD *)v29);
                }
              }
              else
              {
                int_AttemptToConnect(1);
              }
              goto LABEL_89;
            }
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control[1].Flink, 268, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
            }
            v15 = g_pReConnectUserTunnelWorkItem;
LABEL_80:
            SubmitThreadpoolWork(v15);
LABEL_89:
            if ( v4 > 0 )
              v4 = (unsigned __int16)v4 | 0x80070000;
            goto LABEL_126;
          }
          v7 = 1;
          EventActivityIdControl(3u, &ActivityId);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce>::GetImpl'::`2'::impl) )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control[1].Flink, 10, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
            }
            qword_18010F800 = GetTickCount64();
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              goto LABEL_89;
            if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) == 0 )
              goto LABEL_70;
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 11, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
          }
          v18 = WPP_GLOBAL_Control;
LABEL_70:
          if ( v18 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v18[1].Blink) & 4) != 0 )
            WPP_SF_(v18[1].Flink, 271, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
          goto LABEL_89;
        }
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 266, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v12);
      }
      v14 = WPP_GLOBAL_Control;
      goto LABEL_43;
    }
    if ( v10 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v10[1].Blink) & 8) != 0 )
      WPP_SF_(v10[1].Flink, 249, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
    v11 = NlaIndicateReprobe(0);
    if ( v11 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_35;
      if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
        goto LABEL_32;
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 250, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v11);
    }
    v10 = WPP_GLOBAL_Control;
LABEL_32:
    if ( v10 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v10[1].Blink) & 8) != 0 )
    {
      WPP_SF_(v10[1].Flink, 251, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
    goto LABEL_35;
  }
  InitializeLastConnError(v8);
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
  {
    WPP_SF_ddd(
      WPP_GLOBAL_Control[1].Flink,
      275,
      &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
      *((unsigned int *)v9 + 7),
      1,
      *((_DWORD *)v9 + 145));
    v20 = WPP_GLOBAL_Control;
  }
  *((_DWORD *)v9 + 7) = 1;
  if ( v8 )
    g_fUserTunnelRetryAttempted = 0;
  else
    g_fDeviceTunnelRetryAttempted = 0;
  if ( v20 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v20[1].Blink) & 4) != 0 )
    WPP_SF_q(v20[1].Flink, 276, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v9[5]);
  if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(v20, VpnAutoTriggerConnectionConnected, v9[1]);
  InterfaceInfo = int_VpnProfileGetInterfaceInfo(
                    (wchar_t *)v9[1],
                    (unsigned int *)v9 + 145,
                    (unsigned __int16 *)v9 + 28);
  v6 = InterfaceInfo;
  if ( InterfaceInfo )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v22 = 277;
LABEL_111:
      WPP_SF_d(v18[1].Flink, v22, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, InterfaceInfo);
    }
  }
  else if ( *(_DWORD *)v9[74] )
  {
    InterfaceInfo = int_VpnProfilePlumbWfpFilter();
    v6 = InterfaceInfo;
    if ( InterfaceInfo )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v22 = 278;
        goto LABEL_111;
      }
    }
  }
  if ( !v9[5] )
  {
LABEL_126:
    LogEndPhysicalConnection((bool)v18, a1, v4, v8, v7);
    goto LABEL_127;
  }
  v23 = VpnAlloc(32);
  if ( v23 )
  {
    *(_QWORD *)(v23 + 16) = v9[5];
    *(_DWORD *)(v23 + 24) = 0;
    VpnCriticalSectionEnter(&g_CsDisconnectionNotifications);
    v25 = (__int64 *)qword_18010F4F8;
    if ( *(LPVOID **)qword_18010F4F8 != &g_DisconnectNotificationsList )
      __fastfail(3u);
    *(_QWORD *)v23 = &g_DisconnectNotificationsList;
    *(_QWORD *)(v23 + 8) = v25;
    *v25 = v23;
    qword_18010F4F8 = v23;
    VpnCriticalSectionLeave(&g_CsDisconnectionNotifications);
    SetThreadpoolWait(g_ConnectionDisconnectWait, g_ConnectionDisconnectEvent, 0);
    v26 = g_ConnectionDisconnectEvent;
    v9[6] = v9[5];
    ResetEvent(v26);
    v27 = RasConnectionNotificationW((HRASCONN)v9[5], g_ConnectionDisconnectEvent, 2u);
    v6 = v27;
    if ( v27 )
    {
      LOBYTE(v18) = (_BYTE)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 281, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v27);
      }
    }
    goto LABEL_126;
  }
  v24 = WPP_GLOBAL_Control;
  v6 = 14;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 279, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
      v24 = WPP_GLOBAL_Control;
    }
    if ( v24 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v24[1].Blink) & 1) != 0 )
      WPP_SF_d(v24[1].Flink, 280, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
  }
LABEL_127:
  VpnCriticalSectionLeave(&g_LpCriticalSection);
  if ( v6 < 0
    && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 282, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800c5930  push    rbx
0x1800c5932  push    rbp
0x1800c5933  push    rsi
0x1800c5934  push    rdi
0x1800c5935  push    r12
0x1800c5937  push    r13
0x1800c5939  push    r14
0x1800c593b  push    r15
0x1800c593d  sub     rsp, 38h
0x1800c5941  mov     r14d, r8d
0x1800c5944  mov     ebp, edx
0x1800c5946  mov     r12, rcx
0x1800c5949  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5950  lea     r15, WPP_GLOBAL_Control
0x1800c5957  cmp     rcx, r15
0x1800c595a  jz      short loc_1800C597C
0x1800c595c  test    byte ptr [rcx+1Ch], 8
0x1800c5960  jz      short loc_1800C597C
0x1800c5962  mov     rcx, [rcx+10h]
0x1800c5966  mov     edx, 104h
0x1800c596b  mov     [rsp+78h+var_50], r8d
0x1800c5970  mov     r9, r12
0x1800c5973  mov     dword ptr [rsp+78h+var_58], ebp
0x1800c5977  call    WPP_SF_qDD
0x1800c597c  xor     r13d, r13d
0x1800c597f  lea     rcx, ?g_LpCriticalSection@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_LpCriticalSection
0x1800c5986  test    ebp, ebp
0x1800c5988  mov     edi, r13d
0x1800c598b  setz    sil
0x1800c598f  call    VpnCriticalSectionEnter
0x1800c5994  cmp     r12, cs:qword_18010EF68
0x1800c599b  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c59a2  mov     dl, 4
0x1800c59a4  jz      short loc_1800C5A14
0x1800c59a6  cmp     r12, cs:qword_18010F1C8
0x1800c59ad  jz      short loc_1800C59E2
0x1800c59af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c59b6  lea     r14, WPP_GLOBAL_Control
0x1800c59bd  cmp     rcx, r14
0x1800c59c0  jz      loc_1800C6183
0x1800c59c6  test    [rcx+1Ch], dl
0x1800c59c9  jz      loc_1800C6183
0x1800c59cf  mov     rcx, [rcx+10h]
0x1800c59d3  mov     edx, 105h
0x1800c59d8  call    WPP_SF_
0x1800c59dd  jmp     loc_1800C6183
0x1800c59e2  mov     r15b, r13b
0x1800c59e5  lea     rbx, ?g_ActiveDeviceProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveDeviceProfile
0x1800c59ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c59f3  lea     rax, WPP_GLOBAL_Control
0x1800c59fa  cmp     rcx, rax
0x1800c59fd  jz      short loc_1800C5A3D
0x1800c59ff  test    [rcx+1Ch], dl
0x1800c5a02  jz      short loc_1800C5A3D
0x1800c5a04  mov     rcx, [rcx+10h]
0x1800c5a08  mov     edx, 107h
0x1800c5a0d  call    WPP_SF_
0x1800c5a12  jmp     short loc_1800C5A3D
0x1800c5a14  lea     rbx, ?g_ActiveUserProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveUserProfile
0x1800c5a1b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5a22  cmp     rcx, r15
0x1800c5a25  jz      short loc_1800C5A3A
0x1800c5a27  test    [rcx+1Ch], dl
0x1800c5a2a  jz      short loc_1800C5A3A
0x1800c5a2c  mov     rcx, [rcx+10h]
0x1800c5a30  mov     edx, 106h
0x1800c5a35  call    WPP_SF_
0x1800c5a3a  mov     r15b, 1
0x1800c5a3d  mov     cl, r15b; bool
0x1800c5a40  call    ?StopNewRetryWaitPeriod@@YAX_N@Z; StopNewRetryWaitPeriod(bool)
0x1800c5a45  test    ebp, ebp
0x1800c5a47  jz      loc_1800C5EF8
0x1800c5a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5a54  lea     rax, WPP_GLOBAL_Control
0x1800c5a5b  cmp     rcx, rax
0x1800c5a5e  jz      short loc_1800C5ACD
0x1800c5a60  test    byte ptr [rcx+1Ch], 1
0x1800c5a64  jz      short loc_1800C5A8A
0x1800c5a66  mov     rcx, [rcx+10h]
0x1800c5a6a  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c5a71  mov     edx, 108h
0x1800c5a76  mov     dword ptr [rsp+78h+var_58], r14d
0x1800c5a7b  mov     r9d, ebp
0x1800c5a7e  call    WPP_SF_Dd
0x1800c5a83  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5a8a  lea     r14, WPP_GLOBAL_Control
0x1800c5a91  cmp     rcx, r14
0x1800c5a94  jz      short loc_1800C5AD4
0x1800c5a96  test    byte ptr [rcx+1Ch], 4
0x1800c5a9a  jz      short loc_1800C5AD4
0x1800c5a9c  mov     eax, [rbx+244h]
0x1800c5aa2  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c5aa9  mov     r9d, [rbx+1Ch]
0x1800c5aad  mov     edx, 109h
0x1800c5ab2  mov     rcx, [rcx+10h]
0x1800c5ab6  mov     [rsp+78h+var_50], eax
0x1800c5aba  mov     dword ptr [rsp+78h+var_58], r13d
0x1800c5abf  call    WPP_SF_ddd
0x1800c5ac4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5acb  jmp     short loc_1800C5AD4
0x1800c5acd  lea     r14, WPP_GLOBAL_Control
0x1800c5ad4  mov     [rbx+1Ch], r13d
0x1800c5ad8  mov     [rbx+28h], r13
0x1800c5adc  mov     [rbx+30h], r13
0x1800c5ae0  mov     [rbx+244h], r13d
0x1800c5ae7  cmp     ebp, 364h
0x1800c5aed  jnz     loc_1800C5B7D
0x1800c5af3  cmp     rcx, r14
0x1800c5af6  jz      short loc_1800C5B13
0x1800c5af8  test    byte ptr [rcx+1Ch], 8
0x1800c5afc  jz      short loc_1800C5B13
0x1800c5afe  mov     rcx, [rcx+10h]
0x1800c5b02  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c5b09  mov     edx, 0F9h
0x1800c5b0e  call    WPP_SF_
0x1800c5b13  xor     ecx, ecx
0x1800c5b15  call    cs:__imp_NlaIndicateReprobe
0x1800c5b1c  nop     dword ptr [rax+rax+00h]
0x1800c5b21  test    eax, eax
0x1800c5b23  jz      short loc_1800C5B4F
0x1800c5b25  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5b2c  cmp     rcx, r14
0x1800c5b2f  jz      short loc_1800C5B7D
0x1800c5b31  test    byte ptr [rcx+1Ch], 1
0x1800c5b35  jz      short loc_1800C5B56
0x1800c5b37  mov     rcx, [rcx+10h]
0x1800c5b3b  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c5b42  mov     edx, 0FAh
0x1800c5b47  mov     r9d, eax
0x1800c5b4a  call    WPP_SF_d
0x1800c5b4f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5b56  cmp     rcx, r14
0x1800c5b59  jz      short loc_1800C5B7D
0x1800c5b5b  test    byte ptr [rcx+1Ch], 8
0x1800c5b5f  jz      short loc_1800C5B7D
0x1800c5b61  mov     rcx, [rcx+10h]
0x1800c5b65  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c5b6c  mov     edx, 0FBh
0x1800c5b71  call    WPP_SF_
0x1800c5b76  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5b7d  test    cs:Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits, 8
0x1800c5b84  jz      short loc_1800C5B9D
0x1800c5b86  mov     r8, [rbx+8]
0x1800c5b8a  lea     rdx, VpnAutoTriggerConnectionAttemptFailed
0x1800c5b91  call    McTemplateU0z_EventWriteTransfer
0x1800c5b96  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5b9d  test    r15b, r15b
0x1800c5ba0  jz      loc_1800C5DE1
0x1800c5ba6  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800c5bad  xor     edx, edx
0x1800c5baf  call    cs:__imp_FwpiVpnTriggerSetStateDisconnected
0x1800c5bb6  nop     dword ptr [rax+rax+00h]
0x1800c5bbb  mov     edi, eax
0x1800c5bbd  test    eax, eax
0x1800c5bbf  jz      short loc_1800C5BEB
0x1800c5bc1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5bc8  cmp     rcx, r14
0x1800c5bcb  jz      short loc_1800C5C1D
0x1800c5bcd  test    byte ptr [rcx+1Ch], 1
0x1800c5bd1  jz      short loc_1800C5BF2
0x1800c5bd3  mov     rcx, [rcx+10h]
0x1800c5bd7  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c5bde  mov     edx, 10Ah
0x1800c5be3  mov     r9d, eax
0x1800c5be6  call    WPP_SF_d
0x1800c5beb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5bf2  cmp     rcx, r14
0x1800c5bf5  jz      short loc_1800C5C1D
0x1800c5bf7  test    byte ptr [rcx+1Ch], 4
0x1800c5bfb  jz      short loc_1800C5C1D
0x1800c5bfd  cmp     cs:?g_IsActiveUserProfile@@3HA, r13d; int g_IsActiveUserProfile
0x1800c5c04  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c5c0b  mov     rcx, [rcx+10h]
0x1800c5c0f  mov     edx, 10Bh
0x1800c5c14  setnz   r9b
0x1800c5c18  call    WPP_SF_c
0x1800c5c1d  cmp     cs:?g_IsActiveUserProfile@@3HA, r13d; int g_IsActiveUserProfile
0x1800c5c24  jz      loc_1800C5D1D
0x1800c5c2a  mov     dl, 1; bool
0x1800c5c2c  mov     ecx, ebp; unsigned int
0x1800c5c2e  call    ?IsErrorRecoverable@@YA_NK_N@Z; IsErrorRecoverable(ulong,bool)
0x1800c5c33  test    al, al
0x1800c5c35  jz      loc_1800C5D1D
0x1800c5c3b  mov     rax, cs:qword_18010F190
0x1800c5c42  cmp     [rax+80h], r13d
0x1800c5c49  jz      short loc_1800C5C7E
0x1800c5c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5c52  cmp     rcx, r14
0x1800c5c55  jz      short loc_1800C5C72
0x1800c5c57  test    byte ptr [rcx+1Ch], 4
0x1800c5c5b  jz      short loc_1800C5C72
0x1800c5c5d  mov     rcx, [rcx+10h]
0x1800c5c61  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c5c68  mov     edx, 10Ch
0x1800c5c6d  call    WPP_SF_
0x1800c5c72  mov     rcx, cs:?g_pReConnectUserTunnelWorkItem@@3PEAU_TP_WORK@@EA; _TP_WORK * g_pReConnectUserTunnelWorkItem
0x1800c5c79  jmp     loc_1800C5E32
0x1800c5c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5c85  cmp     rcx, r14
0x1800c5c88  jz      short loc_1800C5CA5
0x1800c5c8a  test    byte ptr [rcx+1Ch], 4
0x1800c5c8e  jz      short loc_1800C5CA5
0x1800c5c90  mov     rcx, [rcx+10h]
0x1800c5c94  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c5c9b  mov     edx, 10Dh
0x1800c5ca0  call    WPP_SF_
0x1800c5ca5  lea     rcx, ?g_CsActiveTriggerPeriod@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_CsActiveTriggerPeriod
0x1800c5cac  call    VpnCriticalSectionEnter
0x1800c5cb1  mov     bl, cs:?g_fIsActiveAppTriggerPeriod@@3_NA; bool g_fIsActiveAppTriggerPeriod
0x1800c5cb7  lea     rcx, ?g_CsActiveTriggerPeriod@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_CsActiveTriggerPeriod
0x1800c5cbe  call    VpnCriticalSectionLeave
0x1800c5cc3  mov     eax, cs:?g_fIsInside@@3HA; int g_fIsInside
0x1800c5cc9  test    bl, bl
0x1800c5ccb  jz      short loc_1800C5CDD
0x1800c5ccd  test    eax, eax
0x1800c5ccf  jnz     short loc_1800C5CDD
0x1800c5cd1  mov     cl, 1; bool
0x1800c5cd3  call    ?int_AttemptToConnect@@YAX_N@Z; int_AttemptToConnect(bool)
0x1800c5cd8  jmp     loc_1800C5EE2
0x1800c5cdd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5ce4  cmp     rcx, r14
0x1800c5ce7  jz      loc_1800C5EE2
0x1800c5ced  test    byte ptr [rcx+1Ch], 4
0x1800c5cf1  jz      loc_1800C5EE2
0x1800c5cf7  mov     rcx, [rcx+10h]
0x1800c5cfb  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c5d02  test    eax, eax
0x1800c5d04  mov     edx, 10Eh
0x1800c5d09  mov     r9b, bl
0x1800c5d0c  setnz   al
0x1800c5d0f  mov     [rsp+78h+var_58], al
0x1800c5d13  call    WPP_SF_cc
0x1800c5d18  jmp     loc_1800C5EE2
0x1800c5d1d  lea     rdx, ActivityId; ActivityId
0x1800c5d24  mov     ecx, 3; ControlCode
0x1800c5d29  mov     sil, 1
0x1800c5d2c  call    cs:__imp_EventActivityIdControl
0x1800c5d33  nop     dword ptr [rax+rax+00h]
0x1800c5d38  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce> `wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce>::GetImpl(void)'::`2'::impl
0x1800c5d3f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce>::__private_IsEnabled(void)
0x1800c5d44  test    al, al
0x1800c5d46  jz      short loc_1800C5DAD
0x1800c5d48  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5d4f  cmp     rcx, r14
0x1800c5d52  jz      short loc_1800C5D6F
0x1800c5d54  test    byte ptr [rcx+1Ch], 8
0x1800c5d58  jz      short loc_1800C5D6F
0x1800c5d5a  mov     rcx, [rcx+10h]
0x1800c5d5e  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c5d65  mov     edx, 0Ah
0x1800c5d6a  call    WPP_SF_
0x1800c5d6f  call    cs:__imp_GetTickCount64
0x1800c5d76  nop     dword ptr [rax+rax+00h]
0x1800c5d7b  mov     cs:qword_18010F800, rax
0x1800c5d82  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5d89  cmp     rcx, r14
0x1800c5d8c  jz      loc_1800C5EE2
0x1800c5d92  test    byte ptr [rcx+1Ch], 8
0x1800c5d96  jz      short loc_1800C5DB4
0x1800c5d98  mov     rcx, [rcx+10h]
0x1800c5d9c  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c5da3  mov     edx, 0Bh
0x1800c5da8  call    WPP_SF_
0x1800c5dad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5db4  cmp     rcx, r14
0x1800c5db7  jz      loc_1800C5EE2
0x1800c5dbd  test    byte ptr [rcx+1Ch], 4
0x1800c5dc1  jz      loc_1800C5EE2
0x1800c5dc7  mov     rcx, [rcx+10h]
0x1800c5dcb  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c5dd2  mov     edx, 10Fh
0x1800c5dd7  call    WPP_SF_
0x1800c5ddc  jmp     loc_1800C5EE2
0x1800c5de1  cmp     rcx, r14
0x1800c5de4  jz      short loc_1800C5E01
0x1800c5de6  test    byte ptr [rcx+1Ch], 4
0x1800c5dea  jz      short loc_1800C5E01
0x1800c5dec  mov     rcx, [rcx+10h]
0x1800c5df0  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c5df7  mov     edx, 110h
0x1800c5dfc  call    WPP_SF_
0x1800c5e01  cmp     cs:?g_IsActiveDeviceProfile@@3HA, r13d; int g_IsActiveDeviceProfile
0x1800c5e08  jz      loc_1800C5E95
0x1800c5e0e  xor     edx, edx; bool
0x1800c5e10  mov     ecx, ebp; unsigned int
0x1800c5e12  call    ?IsErrorRecoverable@@YA_NK_N@Z; IsErrorRecoverable(ulong,bool)
0x1800c5e17  test    al, al
0x1800c5e19  jz      short loc_1800C5E95
0x1800c5e1b  mov     rax, cs:qword_18010F3F0
0x1800c5e22  cmp     [rax+80h], r13d
0x1800c5e29  jz      short loc_1800C5E43
0x1800c5e2b  mov     rcx, cs:?g_pReConnectDeviceTunnelWorkItem@@3PEAU_TP_WORK@@EA; pwk
0x1800c5e32  call    cs:__imp_SubmitThreadpoolWork
0x1800c5e39  nop     dword ptr [rax+rax+00h]
0x1800c5e3e  jmp     loc_1800C5EE2
0x1800c5e43  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5e4a  cmp     rcx, r14
0x1800c5e4d  jz      short loc_1800C5E6A
0x1800c5e4f  test    byte ptr [rcx+1Ch], 4
0x1800c5e53  jz      short loc_1800C5E6A
  ... truncated ...
```
