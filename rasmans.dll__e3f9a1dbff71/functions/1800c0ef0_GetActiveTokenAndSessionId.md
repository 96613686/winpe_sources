# GetActiveTokenAndSessionId

- ea: `0x1800c0ef0`
- end: `0x1800c14eb`
- name: `GetActiveTokenAndSessionId`
- size: `1531`
- prototype: `__int64 __fastcall(void *Buf2)`
- caller_count: `6`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800c945c`
- `0x1800cb420`
- `0x1800d4f20`
- `0x1800d67a8`
- `0x1800dad5c`
- `0x1800de2d8`

## callees

- `0x180003404`
- `0x180003594`
- `0x180005e0c`
- `0x180005e34`
- `0x180032118`
- `0x1800a5770`
- `0x1800b81fc`
- `0x1800c0ef0`
- `0x1800e0f4c`
- `0x1800e1d30`
- `0x1800e2d24`
- `0x1800e2dbc`
- `0x1800e71e2`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800c10c7`
- `ntdll!RtlLengthSid` at `0x1800c10ea`
- `ntdll!RtlLengthSid` at `0x1800c10c7`
- `ntdll!RtlLengthSid` at `0x1800c10ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c1119`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c145b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c1119`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c145b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c126a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c126a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x1800c0fee`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x1800c0fee`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800c146a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800c146a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800c108b`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800c108b`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800c137c`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800c137c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800c1369`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800c1369`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1800c1357`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1800c1357`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800c133c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800c133c`

## string_xrefs

- `0x1800c0fc0`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800c117f`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800c1246`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800c12bd`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800c142a`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800c14c3`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800c0fb3`: `GetActiveTokenAndSessionId`
- `0x1800c1172`: `GetActiveTokenAndSessionId`
- `0x1800c1239`: `GetActiveTokenAndSessionId`
- `0x1800c12b0`: `GetActiveTokenAndSessionId`
- `0x1800c141d`: `GetActiveTokenAndSessionId`
- `0x1800c14b6`: `GetActiveTokenAndSessionId`

## pseudocode

```c
__int64 __fastcall GetActiveTokenAndSessionId(void *Buf2, DWORD *a2, void **a3)
{
  void **v3; // rax
  DWORD *v4; // rdi
  struct _LIST_ENTRY *v6; // rcx
  const void **v7; // r15
  DWORD v8; // ebx
  int v9; // r14d
  DWORD SessionId; // r12d
  int v11; // r8d
  struct _LIST_ENTRY *v12; // r10
  __int64 v13; // rsi
  int TokenInformation; // eax
  ULONG v15; // eax
  ULONG v16; // eax
  DWORD LastError; // eax
  __int64 v18; // rbx
  int v19; // eax
  void *phToken; // [rsp+30h] [rbp-20h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+38h] [rbp-18h] BYREF
  LPVOID lpMem[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD *v24; // [rsp+98h] [rbp+48h] BYREF
  void **v25; // [rsp+A0h] [rbp+50h]
  DWORD pCount; // [rsp+A8h] [rbp+58h] BYREF

  v25 = a3;
  v24 = a2;
  v3 = a3;
  v4 = a2;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 180, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    v6 = WPP_GLOBAL_Control;
    v3 = v25;
  }
  v7 = 0;
  phToken = 0;
  ppSessionInfo = 0;
  pCount = 0;
  lpMem[0] = 0;
  if ( !v4 && !v3 )
  {
    v8 = 87;
    if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v6[1].Blink) & 1) != 0 )
      WPP_SF_d(v6[1].Flink, 181, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 87);
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        87,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        1921,
        "GetActiveTokenAndSessionId");
    goto LABEL_85;
  }
  v9 = 0;
  SessionId = 0;
  if ( !WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 187, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, LastError);
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v8,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          1966,
          "GetActiveTokenAndSessionId");
    }
    v12 = WPP_GLOBAL_Control;
LABEL_51:
    if ( v8 == 1626 || v8 == 127 )
    {
      if ( v12 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v12[1].Blink) & 4) != 0 )
        WPP_SF_(v12[1].Flink, 188, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      if ( !(unsigned __int8)IsQueryUserTokenPresent() )
        goto LABEL_77;
      if ( !(unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
        goto LABEL_67;
      LODWORD(v24) = 0;
      lpMem[0] = 0;
      v18 = 0;
      if ( (int)UMgrEnumerateSessionUsers(&v24, lpMem) >= 0 && (_DWORD)v24 )
        v18 = *(_QWORD *)lpMem[0];
      if ( lpMem[0] )
        UMgrFreeSessionUsers(lpMem[0]);
      if ( v18 )
        v19 = (int)UMgrQueryUserToken(v18, &phToken) >= 0;
      else
LABEL_67:
        v19 = QueryUserToken(0, &phToken);
      if ( !v19 )
      {
LABEL_77:
        v8 = 1008;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 189, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 1008);
        }
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            1008,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            1980,
            "GetActiveTokenAndSessionId");
LABEL_82:
        if ( v9 < 0 )
          goto LABEL_83;
        goto LABEL_85;
      }
      v12 = WPP_GLOBAL_Control;
      SessionId = 0;
      v8 = 0;
    }
    else if ( v8 )
    {
      goto LABEL_82;
    }
LABEL_70:
    if ( v12 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v12[1].Blink) & 4) != 0 )
      WPP_SF_qD(v12[1].Flink, 190, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, phToken, SessionId);
    if ( v4 )
      *v4 = SessionId;
    if ( v25 )
    {
      *v25 = phToken;
      phToken = 0;
    }
    goto LABEL_82;
  }
  v8 = 0;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 182, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, pCount);
    v12 = WPP_GLOBAL_Control;
  }
  v13 = 0;
  if ( !pCount )
    goto LABEL_70;
  while ( 1 )
  {
    if ( v12 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v12[1].Blink) & 4) != 0 )
      WPP_SF_ddS(
        v12[1].Flink,
        183,
        v11,
        ppSessionInfo[v13].SessionId,
        ppSessionInfo[v13].State,
        (__int64)ppSessionInfo[v13].pWinStationName);
    if ( !WTSQueryUserToken(ppSessionInfo[v13].SessionId, &phToken) )
    {
      v8 = GetLastError();
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 186, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v8);
        }
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            v8,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            1958,
            "GetActiveTokenAndSessionId");
      }
      goto LABEL_31;
    }
    TokenInformation = VpnGetTokenInformation(phToken);
    v9 = TokenInformation;
    if ( TokenInformation < 0 )
      break;
    v7 = (const void **)lpMem[0];
    if ( ppSessionInfo[v13].State == WTSActive && (v15 = RtlLengthSid(&g_WorldSid), !memcmp_0(&g_WorldSid, Buf2, v15))
      || (v16 = RtlLengthSid(Buf2), !memcmp_0(*v7, Buf2, v16)) )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 185, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
        v12 = WPP_GLOBAL_Control;
      }
      v8 = 0;
      SessionId = ppSessionInfo[v13].SessionId;
      v4 = v24;
      goto LABEL_51;
    }
    MprCommonFree(v7);
    v7 = 0;
    lpMem[0] = 0;
    CloseHandle(phToken);
    phToken = 0;
LABEL_31:
    v12 = WPP_GLOBAL_Control;
    v13 = (unsigned int)(v13 + 1);
    if ( (unsigned int)v13 >= pCount )
    {
      v4 = v24;
      goto LABEL_51;
    }
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control[1].Flink,
      184,
      &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
      (unsigned int)TokenInformation);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    TraceVpnWppErrorHRImpl(
      (unsigned int)v9,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      1935,
      "GetActiveTokenAndSessionId");
  v7 = (const void **)lpMem[0];
LABEL_83:
  v8 = (unsigned __int16)v9;
  if ( (v9 & 0x1FFF0000) != 0x70000 )
    v8 = v9;
LABEL_85:
  if ( phToken )
    CloseHandle(phToken);
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
  MprCommonFree(v7);
  if ( (v8 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 191, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v8);
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        v8,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        2021,
        "GetActiveTokenAndSessionId");
  }
  return v8;
}

```

## disassembly

```asm
0x1800c0ef0  mov     [rsp-38h+arg_0], rbx
0x1800c0ef5  mov     [rsp-38h+arg_10], r8
0x1800c0efa  mov     [rsp-38h+arg_8], rdx
0x1800c0eff  push    rbp
0x1800c0f00  push    rsi
0x1800c0f01  push    rdi
0x1800c0f02  push    r12
0x1800c0f04  push    r13
0x1800c0f06  push    r14
0x1800c0f08  push    r15
0x1800c0f0a  mov     rbp, rsp
0x1800c0f0d  sub     rsp, 50h
0x1800c0f11  mov     rax, r8
0x1800c0f14  mov     rdi, rdx
0x1800c0f17  mov     r13, rcx
0x1800c0f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0f21  lea     rsi, WPP_GLOBAL_Control
0x1800c0f28  cmp     rcx, rsi
0x1800c0f2b  jz      short loc_1800C0F53
0x1800c0f2d  test    byte ptr [rcx+1Ch], 8
0x1800c0f31  jz      short loc_1800C0F53
0x1800c0f33  mov     rcx, [rcx+10h]
0x1800c0f37  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800c0f3e  mov     edx, 0B4h
0x1800c0f43  call    WPP_SF_
0x1800c0f48  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0f4f  mov     rax, [rbp+arg_10]
0x1800c0f53  xor     r15d, r15d
0x1800c0f56  mov     [rbp+phToken], 0
0x1800c0f5e  mov     [rbp+ppSessionInfo], 0
0x1800c0f66  mov     [rbp+arg_18], 0
0x1800c0f6d  mov     [rbp+lpMem], r15
0x1800c0f71  test    rdi, rdi
0x1800c0f74  jnz     short loc_1800C0FD3
0x1800c0f76  test    rax, rax
0x1800c0f79  jnz     short loc_1800C0FD3
0x1800c0f7b  lea     ebx, [rdi+57h]
0x1800c0f7e  cmp     rcx, rsi
0x1800c0f81  jz      short loc_1800C0F9F
0x1800c0f83  test    byte ptr [rcx+1Ch], 1
0x1800c0f87  jz      short loc_1800C0F9F
0x1800c0f89  mov     rcx, [rcx+10h]
0x1800c0f8d  lea     edx, [rbx+5Eh]
0x1800c0f90  mov     r9d, ebx
0x1800c0f93  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800c0f9a  call    WPP_SF_d
0x1800c0f9f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800c0fa6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800c0fab  test    al, al
0x1800c0fad  jz      loc_1800C1452
0x1800c0fb3  lea     r9, aGetactivetoken; "GetActiveTokenAndSessionId"
0x1800c0fba  mov     r8d, 781h
0x1800c0fc0  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800c0fc7  mov     ecx, ebx
0x1800c0fc9  call    TraceVpnWppErrorW32Impl
0x1800c0fce  jmp     loc_1800C1452
0x1800c0fd3  lea     rax, [rbp+arg_18]
0x1800c0fd7  xor     r14d, r14d
0x1800c0fda  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x1800c0fde  mov     [rsp+50h+pCount], rax; pCount
0x1800c0fe3  xor     edx, edx; Reserved
0x1800c0fe5  xor     ecx, ecx; hServer
0x1800c0fe7  xor     r12d, r12d
0x1800c0fea  lea     r8d, [r14+1]; Version
0x1800c0fee  call    cs:__imp_WTSEnumerateSessionsW
0x1800c0ff4  test    eax, eax
0x1800c0ff6  jz      loc_1800C126A
0x1800c0ffc  xor     ebx, ebx
0x1800c0ffe  mov     r10, cs:WPP_GLOBAL_Control
0x1800c1005  cmp     r10, rsi
0x1800c1008  jz      short loc_1800C1031
0x1800c100a  test    byte ptr [r10+1Ch], 4
0x1800c100f  jz      short loc_1800C1031
0x1800c1011  mov     r9d, [rbp+arg_18]
0x1800c1015  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800c101c  mov     rcx, [r10+10h]
0x1800c1020  mov     edx, 0B6h
0x1800c1025  call    WPP_SF_d
0x1800c102a  mov     r10, cs:WPP_GLOBAL_Control
0x1800c1031  xor     esi, esi
0x1800c1033  cmp     [rbp+arg_18], ebx
0x1800c1036  jbe     loc_1800C125E
0x1800c103c  lea     rax, WPP_GLOBAL_Control
0x1800c1043  cmp     r10, rax
0x1800c1046  jz      short loc_1800C107C
0x1800c1048  test    byte ptr [r10+1Ch], 4
0x1800c104d  jz      short loc_1800C107C
0x1800c104f  mov     r9, [rbp+ppSessionInfo]
0x1800c1053  lea     rcx, [rsi+rsi*2]
0x1800c1057  mov     edx, 0B7h
0x1800c105c  mov     rax, [r9+rcx*8+8]
0x1800c1061  mov     [rsp+50h+var_28], rax
0x1800c1066  mov     eax, [r9+rcx*8+10h]
0x1800c106b  mov     r9d, [r9+rcx*8]
0x1800c106f  mov     rcx, [r10+10h]
0x1800c1073  mov     dword ptr [rsp+50h+pCount], eax
0x1800c1077  call    WPP_SF_ddS
0x1800c107c  mov     rcx, [rbp+ppSessionInfo]
0x1800c1080  lea     rdi, [rsi+rsi*2]
0x1800c1084  lea     rdx, [rbp+phToken]; phToken
0x1800c1088  mov     ecx, [rcx+rdi*8]; SessionId
0x1800c108b  call    cs:__imp_WTSQueryUserToken
0x1800c1091  test    eax, eax
0x1800c1093  jz      loc_1800C1125
0x1800c1099  mov     rcx, [rbp+phToken]; TokenHandle
0x1800c109d  lea     r8, [rbp+lpMem]
0x1800c10a1  call    VpnGetTokenInformation
0x1800c10a6  mov     r14d, eax
0x1800c10a9  test    eax, eax
0x1800c10ab  js      loc_1800C11F8
0x1800c10b1  mov     rcx, [rbp+ppSessionInfo]
0x1800c10b5  mov     r15, [rbp+lpMem]
0x1800c10b9  cmp     [rcx+rdi*8+10h], r12d
0x1800c10be  jnz     short loc_1800C10E7
0x1800c10c0  lea     rcx, ?g_WorldSid@@3U_SID@@A; Sid
0x1800c10c7  call    cs:__imp_RtlLengthSid
0x1800c10cd  mov     r8d, eax; Size
0x1800c10d0  mov     rdx, r13; Buf2
0x1800c10d3  lea     rcx, ?g_WorldSid@@3U_SID@@A; Buf1
0x1800c10da  call    memcmp_0
0x1800c10df  test    eax, eax
0x1800c10e1  jz      loc_1800C11AF
0x1800c10e7  mov     rcx, r13; Sid
0x1800c10ea  call    cs:__imp_RtlLengthSid
0x1800c10f0  mov     rcx, [r15]; Buf1
0x1800c10f3  mov     rdx, r13; Buf2
0x1800c10f6  mov     r8d, eax; Size
0x1800c10f9  call    memcmp_0
0x1800c10fe  test    eax, eax
0x1800c1100  jz      loc_1800C11AF
0x1800c1106  mov     rcx, r15; lpMem
0x1800c1109  call    MprCommonFree
0x1800c110e  mov     rcx, [rbp+phToken]; hObject
0x1800c1112  xor     r15d, r15d
0x1800c1115  mov     [rbp+lpMem], r15
0x1800c1119  call    cs:__imp_CloseHandle
0x1800c111f  mov     [rbp+phToken], r12
0x1800c1123  jmp     short loc_1800C118D
0x1800c1125  call    cs:__imp_GetLastError
0x1800c112b  mov     ebx, eax
0x1800c112d  test    eax, eax
0x1800c112f  jz      short loc_1800C118D
0x1800c1131  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c1138  lea     rax, WPP_GLOBAL_Control
0x1800c113f  cmp     rcx, rax
0x1800c1142  jz      short loc_1800C1162
0x1800c1144  test    byte ptr [rcx+1Ch], 1
0x1800c1148  jz      short loc_1800C1162
0x1800c114a  mov     rcx, [rcx+10h]
0x1800c114e  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800c1155  mov     edx, 0BAh
0x1800c115a  mov     r9d, ebx
0x1800c115d  call    WPP_SF_d
0x1800c1162  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800c1169  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800c116e  test    al, al
0x1800c1170  jz      short loc_1800C118D
0x1800c1172  lea     r9, aGetactivetoken; "GetActiveTokenAndSessionId"
0x1800c1179  mov     r8d, 7A6h
0x1800c117f  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800c1186  mov     ecx, ebx
0x1800c1188  call    TraceVpnWppErrorW32Impl
0x1800c118d  mov     r10, cs:WPP_GLOBAL_Control
0x1800c1194  inc     esi
0x1800c1196  cmp     esi, [rbp+arg_18]
0x1800c1199  jb      loc_1800C103C
0x1800c119f  mov     rdi, [rbp+arg_8]
0x1800c11a3  lea     rsi, WPP_GLOBAL_Control
0x1800c11aa  jmp     loc_1800C12D2
0x1800c11af  mov     r10, cs:WPP_GLOBAL_Control
0x1800c11b6  lea     rsi, WPP_GLOBAL_Control
0x1800c11bd  cmp     r10, rsi
0x1800c11c0  jz      short loc_1800C11E5
0x1800c11c2  test    byte ptr [r10+1Ch], 4
0x1800c11c7  jz      short loc_1800C11E5
0x1800c11c9  mov     rcx, [r10+10h]
0x1800c11cd  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800c11d4  mov     edx, 0B9h
0x1800c11d9  call    WPP_SF_
0x1800c11de  mov     r10, cs:WPP_GLOBAL_Control
0x1800c11e5  mov     rax, [rbp+ppSessionInfo]
0x1800c11e9  xor     ebx, ebx
0x1800c11eb  mov     r12d, [rax+rdi*8]
0x1800c11ef  mov     rdi, [rbp+arg_8]
0x1800c11f3  jmp     loc_1800C12D2
0x1800c11f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c11ff  lea     rsi, WPP_GLOBAL_Control
0x1800c1206  cmp     rcx, rsi
0x1800c1209  jz      short loc_1800C1229
0x1800c120b  test    byte ptr [rcx+1Ch], 1
0x1800c120f  jz      short loc_1800C1229
0x1800c1211  mov     rcx, [rcx+10h]
0x1800c1215  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800c121c  mov     edx, 0B8h
0x1800c1221  mov     r9d, r14d
0x1800c1224  call    WPP_SF_d
0x1800c1229  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800c1230  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800c1235  test    al, al
0x1800c1237  jz      short loc_1800C1255
0x1800c1239  lea     r9, aGetactivetoken; "GetActiveTokenAndSessionId"
0x1800c1240  mov     r8d, 78Fh
0x1800c1246  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800c124d  mov     ecx, r14d
0x1800c1250  call    TraceVpnWppErrorHRImpl
0x1800c1255  mov     r15, [rbp+lpMem]
0x1800c1259  jmp     loc_1800C143D
0x1800c125e  lea     rsi, WPP_GLOBAL_Control
0x1800c1265  jmp     loc_1800C1392
0x1800c126a  call    cs:__imp_GetLastError
0x1800c1270  mov     ebx, eax
0x1800c1272  test    eax, eax
0x1800c1274  jz      short loc_1800C12CB
0x1800c1276  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c127d  cmp     rcx, rsi
0x1800c1280  jz      short loc_1800C12A0
0x1800c1282  test    byte ptr [rcx+1Ch], 1
0x1800c1286  jz      short loc_1800C12A0
0x1800c1288  mov     rcx, [rcx+10h]
0x1800c128c  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800c1293  mov     edx, 0BBh
0x1800c1298  mov     r9d, eax
0x1800c129b  call    WPP_SF_d
0x1800c12a0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800c12a7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800c12ac  test    al, al
0x1800c12ae  jz      short loc_1800C12CB
0x1800c12b0  lea     r9, aGetactivetoken; "GetActiveTokenAndSessionId"
0x1800c12b7  mov     r8d, 7AEh
0x1800c12bd  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800c12c4  mov     ecx, ebx
0x1800c12c6  call    TraceVpnWppErrorW32Impl
0x1800c12cb  mov     r10, cs:WPP_GLOBAL_Control
0x1800c12d2  cmp     ebx, 65Ah
0x1800c12d8  jz      short loc_1800C12EC
0x1800c12da  cmp     ebx, 7Fh
0x1800c12dd  jz      short loc_1800C12EC
0x1800c12df  test    ebx, ebx
0x1800c12e1  jnz     loc_1800C1438
0x1800c12e7  jmp     loc_1800C1392
0x1800c12ec  cmp     r10, rsi
0x1800c12ef  jz      short loc_1800C130D
0x1800c12f1  test    byte ptr [r10+1Ch], 4
0x1800c12f6  jz      short loc_1800C130D
0x1800c12f8  mov     rcx, [r10+10h]
0x1800c12fc  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800c1303  mov     edx, 0BCh
0x1800c1308  call    WPP_SF_
0x1800c130d  call    IsQueryUserTokenPresent
0x1800c1312  test    al, al
0x1800c1314  jz      loc_1800C13DE
0x1800c131a  call    IsUMgrEnumerateSessionUsersPresent
0x1800c131f  test    al, al
0x1800c1321  jz      short loc_1800C1376
0x1800c1323  lea     rdx, [rbp+lpMem]
0x1800c1327  mov     dword ptr [rbp+arg_8], 0
0x1800c132e  lea     rcx, [rbp+arg_8]
0x1800c1332  mov     [rbp+lpMem], 0
0x1800c133a  xor     ebx, ebx
0x1800c133c  call    cs:__imp_UMgrEnumerateSessionUsers
0x1800c1342  mov     rcx, [rbp+lpMem]
0x1800c1346  test    eax, eax
0x1800c1348  js      short loc_1800C1352
0x1800c134a  cmp     dword ptr [rbp+arg_8], ebx
0x1800c134d  jbe     short loc_1800C1352
0x1800c134f  mov     rbx, [rcx]
0x1800c1352  test    rcx, rcx
0x1800c1355  jz      short loc_1800C135D
0x1800c1357  call    cs:__imp_UMgrFreeSessionUsers
0x1800c135d  lea     rdx, [rbp+phToken]
0x1800c1361  test    rbx, rbx
0x1800c1364  jz      short loc_1800C137A
0x1800c1366  mov     rcx, rbx
0x1800c1369  call    cs:__imp_UMgrQueryUserToken
0x1800c136f  not     eax
0x1800c1371  shr     eax, 1Fh
0x1800c1374  jmp     short loc_1800C1382
0x1800c1376  lea     rdx, [rbp+phToken]
0x1800c137a  xor     ecx, ecx
0x1800c137c  call    cs:__imp_QueryUserToken
0x1800c1382  test    eax, eax
0x1800c1384  jz      short loc_1800C13DE
0x1800c1386  mov     r10, cs:WPP_GLOBAL_Control
0x1800c138d  xor     r12d, r12d
0x1800c1390  xor     ebx, ebx
0x1800c1392  cmp     r10, rsi
0x1800c1395  jz      short loc_1800C13BC
0x1800c1397  test    byte ptr [r10+1Ch], 4
0x1800c139c  jz      short loc_1800C13BC
0x1800c139e  mov     r9, [rbp+phToken]
0x1800c13a2  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800c13a9  mov     rcx, [r10+10h]
0x1800c13ad  mov     edx, 0BEh
0x1800c13b2  mov     dword ptr [rsp+50h+pCount], r12d
0x1800c13b7  call    WPP_SF_qD
0x1800c13bc  test    rdi, rdi
0x1800c13bf  jz      short loc_1800C13C4
0x1800c13c1  mov     [rdi], r12d
0x1800c13c4  mov     rcx, [rbp+arg_10]
0x1800c13c8  test    rcx, rcx
  ... truncated ...
```
