# VpnProfileDeActivateAutoTrigger

- ea: `0x1800dde2c`
- end: `0x1800de2d1`
- name: `VpnProfileDeActivateAutoTrigger`
- size: `1189`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c9f1c`
- `0x1800d4f20`
- `0x1800d8e74`
- `0x1800d9cf0`
- `0x1800dbf40`
- `0x1800df9c0`

## callees

- `0x180005e34`
- `0x180032508`
- `0x1800593d0`
- `0x1800a6cbc`
- `0x1800aa6e0`
- `0x1800b81fc`
- `0x1800d4be4`
- `0x1800da78c`
- `0x1800daba4`
- `0x1800dde2c`
- `0x1800e2d24`
- `0x1800e2dbc`

## import_xrefs

- `fwpuclnt!FwpiVpnTriggerResetNrptTriggering` at `0x1800de1a5`
- `fwpuclnt!FwpiVpnTriggerResetNrptTriggering` at `0x1800de1a5`
- `fwpuclnt!FwpiVpnTriggerSetStateDisconnected` at `0x1800ddf57`
- `fwpuclnt!FwpiVpnTriggerSetStateDisconnected` at `0x1800ddf57`
- `fwpuclnt!FwpiVpnTriggerRemoveAppSids` at `0x1800ddff3`
- `fwpuclnt!FwpiVpnTriggerRemoveAppSids` at `0x1800ddff3`
- `fwpuclnt!FwpiVpnTriggerRemoveSecurityDescriptor` at `0x1800de0bb`
- `fwpuclnt!FwpiVpnTriggerRemoveSecurityDescriptor` at `0x1800de0bb`
- `fwpuclnt!FwpiVpnTriggerRemoveFilePaths` at `0x1800de05b`
- `fwpuclnt!FwpiVpnTriggerRemoveFilePaths` at `0x1800de05b`

## string_xrefs

- `0x1800ddfa2`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800de03e`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800de0a6`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800de106`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800de187`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800de1f0`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800de262`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800de2b3`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`

## pseudocode

```c
__int64 __fastcall VpnProfileDeActivateAutoTrigger(int a1, int a2, unsigned int a3, __int64 a4)
{
  __int64 *v7; // rcx
  int v8; // eax
  int v9; // eax
  __int64 v10; // r9
  int *v11; // rax
  __int64 *v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rax
  LPCWSTR v16; // r8
  unsigned int v17; // eax
  unsigned int v18; // ebx
  unsigned int v19; // eax
  unsigned int v20; // ebx
  unsigned int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rcx
  unsigned int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // rax
  unsigned int appended; // eax

  v7 = (__int64 *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    LOBYTE(a4) = a1 != 0;
    WPP_SF_cc(WPP_GLOBAL_Control[1].Flink, 681, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, a4, a2 != 0);
  }
  if ( a1 )
  {
    v8 = dword_18010DFF0;
    if ( !a2 )
      v8 = dword_18010E250;
    if ( v8 == 1 )
    {
      v7 = (__int64 *)qword_18010DFF8;
      if ( !a2 )
        v7 = (__int64 *)qword_18010E258;
      if ( v7 )
      {
        int_ScheduleDisconnect((__int64)v7, 0, a3);
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
        {
          v9 = InterfaceIndex;
          v10 = (unsigned int)dword_18010DFF0;
          if ( !a2 )
          {
            v9 = dword_18010E474;
            v10 = (unsigned int)dword_18010E250;
          }
          WPP_SF_ddd(WPP_GLOBAL_Control[1].Flink, 682, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v10, 0, v9);
        }
        v11 = &dword_18010DFF0;
        if ( !a2 )
          v11 = &dword_18010E250;
        v7 = &qword_18010E258;
        *v11 = 0;
        v12 = &qword_18010DFF8;
        if ( !a2 )
          v12 = &qword_18010E258;
        *v12 = 0;
        if ( a2 )
        {
          v13 = FwpiVpnTriggerSetStateDisconnected(g_FwpEngineHandle, 0);
          v14 = v13;
          if ( v13 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 683, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v13);
            }
            if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              TraceVpnWppErrorW32Impl(
                v14,
                L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                6693,
                "VpnProfileDeActivateAutoTrigger");
          }
        }
      }
    }
  }
  v15 = qword_18010E220;
  if ( !a2 )
    v15 = qword_18010E480;
  if ( v15 && (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
  {
    v16 = qword_18010DFD8;
    if ( !a2 )
      v16 = qword_18010E238;
    McTemplateU0z_EventWriteTransfer(v7, VpnAutoTriggerProfileDeactivated, v16);
  }
  v17 = FwpiVpnTriggerRemoveAppSids(g_FwpEngineHandle);
  v18 = v17;
  if ( v17 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 684, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v17);
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        v18,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        6706,
        "VpnProfileDeActivateAutoTrigger");
  }
  if ( a2 )
  {
    v19 = FwpiVpnTriggerRemoveFilePaths(g_FwpEngineHandle);
    v20 = v19;
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 685, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v19);
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v20,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          6715,
          "VpnProfileDeActivateAutoTrigger");
    }
    v21 = FwpiVpnTriggerRemoveSecurityDescriptor(g_FwpEngineHandle);
    v18 = v21;
    if ( v21 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 686, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v21);
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v18,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          6722,
          "VpnProfileDeActivateAutoTrigger");
    }
    int_VpnProfileUnPlumbWfpFilter();
  }
  v22 = qword_18010E220;
  if ( !a2 )
    v22 = qword_18010E480;
  if ( v22 )
  {
    v23 = *(_QWORD *)(v22 + 16);
    if ( v23 )
    {
      v24 = RasRemoveNrptRules(v23, 1);
      v18 = v24;
      if ( v24 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 687, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v24);
        }
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            v18,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            6735,
            "VpnProfileDeActivateAutoTrigger");
      }
    }
  }
  if ( a2 )
  {
    int_VpnProfileUnPlumbWfpFilter();
    v25 = FwpiVpnTriggerResetNrptTriggering(g_FwpEngineHandle);
    v18 = v25;
    if ( v25 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 688, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v25);
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v18,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          6746,
          "VpnProfileDeActivateAutoTrigger");
    }
  }
  v26 = qword_18010E220;
  if ( !a2 )
    v26 = qword_18010E480;
  if ( v26 )
  {
    appended = AppendDnsSuffixSearchListToGlobalList(0, 0);
    v18 = appended;
    if ( appended )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 689, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, appended);
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v18,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          6756,
          "VpnProfileDeActivateAutoTrigger");
    }
  }
  if ( (v18 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 690, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v18);
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        v18,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        6760,
        "VpnProfileDeActivateAutoTrigger");
  }
  return v18;
}

```

## disassembly

```asm
0x1800dde2c  push    rbx
0x1800dde2e  push    rsi
0x1800dde2f  push    rdi
0x1800dde30  push    r12
0x1800dde32  push    r13
0x1800dde34  push    r15
0x1800dde36  sub     rsp, 38h
0x1800dde3a  mov     esi, r8d
0x1800dde3d  mov     edi, edx
0x1800dde3f  mov     ebx, ecx
0x1800dde41  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dde48  lea     r15, WPP_GLOBAL_Control
0x1800dde4f  lea     r13, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800dde56  cmp     rcx, r15
0x1800dde59  jz      short loc_1800DDE81
0x1800dde5b  test    byte ptr [rcx+1Ch], 8
0x1800dde5f  jz      short loc_1800DDE81
0x1800dde61  mov     rcx, [rcx+10h]
0x1800dde65  test    edx, edx
0x1800dde67  mov     edx, 2A9h
0x1800dde6c  mov     r8, r13
0x1800dde6f  setnz   al
0x1800dde72  test    ebx, ebx
0x1800dde74  mov     byte ptr [rsp+68h+var_48], al
0x1800dde78  setnz   r9b
0x1800dde7c  call    WPP_SF_cc
0x1800dde81  lea     r12, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800dde88  test    ebx, ebx
0x1800dde8a  jz      loc_1800DDFB0
0x1800dde90  mov     eax, cs:dword_18010DFF0
0x1800dde96  test    edi, edi
0x1800dde98  cmovz   eax, cs:dword_18010E250
0x1800dde9f  cmp     eax, 1
0x1800ddea2  jnz     loc_1800DDFB0
0x1800ddea8  mov     rcx, cs:qword_18010DFF8
0x1800ddeaf  test    edi, edi
0x1800ddeb1  cmovz   rcx, cs:qword_18010E258
0x1800ddeb9  test    rcx, rcx
0x1800ddebc  jz      loc_1800DDFB0
0x1800ddec2  mov     r8d, esi
0x1800ddec5  xor     edx, edx
0x1800ddec7  call    ?int_ScheduleDisconnect@@YAKPEAUHRASCONN__@@HW4_SCHEDULED_DISCONNECT_REASON@@@Z; int_ScheduleDisconnect(HRASCONN__ *,int,_SCHEDULED_DISCONNECT_REASON)
0x1800ddecc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dded3  cmp     rcx, r15
0x1800dded6  jz      short loc_1800DDF19
0x1800dded8  test    byte ptr [rcx+1Ch], 4
0x1800ddedc  jz      short loc_1800DDF19
0x1800ddede  mov     eax, cs:InterfaceIndex
0x1800ddee4  test    edi, edi
0x1800ddee6  mov     r9d, cs:dword_18010DFF0
0x1800ddeed  mov     edx, 2AAh
0x1800ddef2  cmovz   eax, cs:dword_18010E474
0x1800ddef9  mov     r8, r13
0x1800ddefc  cmovz   r9d, cs:dword_18010E250
0x1800ddf04  mov     rcx, [rcx+10h]
0x1800ddf08  mov     [rsp+68h+var_40], eax
0x1800ddf0c  mov     [rsp+68h+var_48], 0
0x1800ddf14  call    WPP_SF_ddd
0x1800ddf19  test    edi, edi
0x1800ddf1b  lea     rcx, dword_18010E250
0x1800ddf22  lea     rax, dword_18010DFF0
0x1800ddf29  cmovz   rax, rcx
0x1800ddf2d  lea     rcx, qword_18010E258
0x1800ddf34  mov     dword ptr [rax], 0
0x1800ddf3a  lea     rax, qword_18010DFF8
0x1800ddf41  cmovz   rax, rcx
0x1800ddf45  mov     qword ptr [rax], 0
0x1800ddf4c  jz      short loc_1800DDFB0
0x1800ddf4e  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800ddf55  xor     edx, edx
0x1800ddf57  call    cs:__imp_FwpiVpnTriggerSetStateDisconnected
0x1800ddf5d  mov     ebx, eax
0x1800ddf5f  test    eax, eax
0x1800ddf61  jz      short loc_1800DDFB0
0x1800ddf63  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ddf6a  cmp     rcx, r15
0x1800ddf6d  jz      short loc_1800DDF89
0x1800ddf6f  test    byte ptr [rcx+1Ch], 1
0x1800ddf73  jz      short loc_1800DDF89
0x1800ddf75  mov     rcx, [rcx+10h]
0x1800ddf79  mov     edx, 2ABh
0x1800ddf7e  mov     r9d, eax
0x1800ddf81  mov     r8, r13
0x1800ddf84  call    WPP_SF_d
0x1800ddf89  mov     rcx, r12
0x1800ddf8c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800ddf91  test    al, al
0x1800ddf93  jz      short loc_1800DDFB0
0x1800ddf95  lea     r9, aVpnprofiledeac; "VpnProfileDeActivateAutoTrigger"
0x1800ddf9c  mov     r8d, 1A25h
0x1800ddfa2  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800ddfa9  mov     ecx, ebx
0x1800ddfab  call    TraceVpnWppErrorW32Impl
0x1800ddfb0  mov     rax, cs:qword_18010E220
0x1800ddfb7  test    edi, edi
0x1800ddfb9  cmovz   rax, cs:qword_18010E480
0x1800ddfc1  test    rax, rax
0x1800ddfc4  jz      short loc_1800DDFEC
0x1800ddfc6  test    cs:Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits, 8
0x1800ddfcd  jz      short loc_1800DDFEC
0x1800ddfcf  mov     r8, cs:qword_18010DFD8
0x1800ddfd6  lea     rdx, VpnAutoTriggerProfileDeactivated
0x1800ddfdd  test    edi, edi
0x1800ddfdf  cmovz   r8, cs:qword_18010E238
0x1800ddfe7  call    McTemplateU0z_EventWriteTransfer
0x1800ddfec  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800ddff3  call    cs:__imp_FwpiVpnTriggerRemoveAppSids
0x1800ddff9  mov     ebx, eax
0x1800ddffb  test    eax, eax
0x1800ddffd  jz      short loc_1800DE04C
0x1800ddfff  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de006  cmp     rcx, r15
0x1800de009  jz      short loc_1800DE025
0x1800de00b  test    byte ptr [rcx+1Ch], 1
0x1800de00f  jz      short loc_1800DE025
0x1800de011  mov     rcx, [rcx+10h]
0x1800de015  mov     edx, 2ACh
0x1800de01a  mov     r9d, eax
0x1800de01d  mov     r8, r13
0x1800de020  call    WPP_SF_d
0x1800de025  mov     rcx, r12
0x1800de028  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800de02d  test    al, al
0x1800de02f  jz      short loc_1800DE04C
0x1800de031  lea     r9, aVpnprofiledeac; "VpnProfileDeActivateAutoTrigger"
0x1800de038  mov     r8d, 1A32h
0x1800de03e  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800de045  mov     ecx, ebx
0x1800de047  call    TraceVpnWppErrorW32Impl
0x1800de04c  test    edi, edi
0x1800de04e  jz      loc_1800DE119
0x1800de054  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800de05b  call    cs:__imp_FwpiVpnTriggerRemoveFilePaths
0x1800de061  mov     ebx, eax
0x1800de063  test    eax, eax
0x1800de065  jz      short loc_1800DE0B4
0x1800de067  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de06e  cmp     rcx, r15
0x1800de071  jz      short loc_1800DE08D
0x1800de073  test    byte ptr [rcx+1Ch], 1
0x1800de077  jz      short loc_1800DE08D
0x1800de079  mov     rcx, [rcx+10h]
0x1800de07d  mov     edx, 2ADh
0x1800de082  mov     r9d, eax
0x1800de085  mov     r8, r13
0x1800de088  call    WPP_SF_d
0x1800de08d  mov     rcx, r12
0x1800de090  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800de095  test    al, al
0x1800de097  jz      short loc_1800DE0B4
0x1800de099  lea     r9, aVpnprofiledeac; "VpnProfileDeActivateAutoTrigger"
0x1800de0a0  mov     r8d, 1A3Bh
0x1800de0a6  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800de0ad  mov     ecx, ebx
0x1800de0af  call    TraceVpnWppErrorW32Impl
0x1800de0b4  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800de0bb  call    cs:__imp_FwpiVpnTriggerRemoveSecurityDescriptor
0x1800de0c1  mov     ebx, eax
0x1800de0c3  test    eax, eax
0x1800de0c5  jz      short loc_1800DE114
0x1800de0c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de0ce  cmp     rcx, r15
0x1800de0d1  jz      short loc_1800DE0ED
0x1800de0d3  test    byte ptr [rcx+1Ch], 1
0x1800de0d7  jz      short loc_1800DE0ED
0x1800de0d9  mov     rcx, [rcx+10h]
0x1800de0dd  mov     edx, 2AEh
0x1800de0e2  mov     r9d, eax
0x1800de0e5  mov     r8, r13
0x1800de0e8  call    WPP_SF_d
0x1800de0ed  mov     rcx, r12
0x1800de0f0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800de0f5  test    al, al
0x1800de0f7  jz      short loc_1800DE114
0x1800de0f9  lea     r9, aVpnprofiledeac; "VpnProfileDeActivateAutoTrigger"
0x1800de100  mov     r8d, 1A42h
0x1800de106  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800de10d  mov     ecx, ebx
0x1800de10f  call    TraceVpnWppErrorW32Impl
0x1800de114  call    ?int_VpnProfileUnPlumbWfpFilter@@YAXXZ; int_VpnProfileUnPlumbWfpFilter(void)
0x1800de119  mov     rax, cs:qword_18010E220
0x1800de120  test    edi, edi
0x1800de122  cmovz   rax, cs:qword_18010E480
0x1800de12a  test    rax, rax
0x1800de12d  jz      short loc_1800DE195
0x1800de12f  mov     rcx, [rax+10h]
0x1800de133  test    rcx, rcx
0x1800de136  jz      short loc_1800DE195
0x1800de138  mov     edx, 1
0x1800de13d  call    RasRemoveNrptRules
0x1800de142  mov     ebx, eax
0x1800de144  test    eax, eax
0x1800de146  jz      short loc_1800DE195
0x1800de148  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de14f  cmp     rcx, r15
0x1800de152  jz      short loc_1800DE16E
0x1800de154  test    byte ptr [rcx+1Ch], 1
0x1800de158  jz      short loc_1800DE16E
0x1800de15a  mov     rcx, [rcx+10h]
0x1800de15e  mov     edx, 2AFh
0x1800de163  mov     r9d, eax
0x1800de166  mov     r8, r13
0x1800de169  call    WPP_SF_d
0x1800de16e  mov     rcx, r12
0x1800de171  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800de176  test    al, al
0x1800de178  jz      short loc_1800DE195
0x1800de17a  lea     r9, aVpnprofiledeac; "VpnProfileDeActivateAutoTrigger"
0x1800de181  mov     r8d, 1A4Fh
0x1800de187  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800de18e  mov     ecx, ebx
0x1800de190  call    TraceVpnWppErrorW32Impl
0x1800de195  test    edi, edi
0x1800de197  jz      short loc_1800DE1FE
0x1800de199  call    ?int_VpnProfileUnPlumbWfpFilter@@YAXXZ; int_VpnProfileUnPlumbWfpFilter(void)
0x1800de19e  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800de1a5  call    cs:__imp_FwpiVpnTriggerResetNrptTriggering
0x1800de1ab  mov     ebx, eax
0x1800de1ad  test    eax, eax
0x1800de1af  jz      short loc_1800DE1FE
0x1800de1b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de1b8  cmp     rcx, r15
0x1800de1bb  jz      short loc_1800DE1D7
0x1800de1bd  test    byte ptr [rcx+1Ch], 1
0x1800de1c1  jz      short loc_1800DE1D7
0x1800de1c3  mov     rcx, [rcx+10h]
0x1800de1c7  mov     edx, 2B0h
0x1800de1cc  mov     r9d, eax
0x1800de1cf  mov     r8, r13
0x1800de1d2  call    WPP_SF_d
0x1800de1d7  mov     rcx, r12
0x1800de1da  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800de1df  test    al, al
0x1800de1e1  jz      short loc_1800DE1FE
0x1800de1e3  lea     r9, aVpnprofiledeac; "VpnProfileDeActivateAutoTrigger"
0x1800de1ea  mov     r8d, 1A5Ah
0x1800de1f0  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800de1f7  mov     ecx, ebx
0x1800de1f9  call    TraceVpnWppErrorW32Impl
0x1800de1fe  mov     rax, cs:qword_18010E220
0x1800de205  test    edi, edi
0x1800de207  cmovz   rax, cs:qword_18010E480
0x1800de20f  test    rax, rax
0x1800de212  jz      short loc_1800DE270
0x1800de214  xor     edx, edx
0x1800de216  xor     ecx, ecx
0x1800de218  call    AppendDnsSuffixSearchListToGlobalList
0x1800de21d  mov     ebx, eax
0x1800de21f  test    eax, eax
0x1800de221  jz      short loc_1800DE270
0x1800de223  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de22a  cmp     rcx, r15
0x1800de22d  jz      short loc_1800DE249
0x1800de22f  test    byte ptr [rcx+1Ch], 1
0x1800de233  jz      short loc_1800DE249
0x1800de235  mov     rcx, [rcx+10h]
0x1800de239  mov     edx, 2B1h
0x1800de23e  mov     r9d, eax
0x1800de241  mov     r8, r13
0x1800de244  call    WPP_SF_d
0x1800de249  mov     rcx, r12
0x1800de24c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800de251  test    al, al
0x1800de253  jz      short loc_1800DE270
0x1800de255  lea     r9, aVpnprofiledeac; "VpnProfileDeActivateAutoTrigger"
0x1800de25c  mov     r8d, 1A64h
0x1800de262  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800de269  mov     ecx, ebx
0x1800de26b  call    TraceVpnWppErrorW32Impl
0x1800de270  test    ebx, ebx
0x1800de272  jns     short loc_1800DE2C1
0x1800de274  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de27b  cmp     rcx, r15
0x1800de27e  jz      short loc_1800DE29A
0x1800de280  test    byte ptr [rcx+1Ch], 8
0x1800de284  jz      short loc_1800DE29A
0x1800de286  mov     rcx, [rcx+10h]
0x1800de28a  mov     edx, 2B2h
0x1800de28f  mov     r9d, ebx
0x1800de292  mov     r8, r13
0x1800de295  call    WPP_SF_d
0x1800de29a  mov     rcx, r12
0x1800de29d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800de2a2  test    al, al
0x1800de2a4  jz      short loc_1800DE2C1
0x1800de2a6  lea     r9, aVpnprofiledeac; "VpnProfileDeActivateAutoTrigger"
0x1800de2ad  mov     r8d, 1A68h
0x1800de2b3  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800de2ba  mov     ecx, ebx
0x1800de2bc  call    TraceVpnWppErrorHRImpl
0x1800de2c1  mov     eax, ebx
0x1800de2c3  add     rsp, 38h
0x1800de2c7  pop     r15
0x1800de2c9  pop     r13
0x1800de2cb  pop     r12
0x1800de2cd  pop     rdi
0x1800de2ce  pop     rsi
0x1800de2cf  pop     rbx
0x1800de2d0  retn
```
