# int_ConnectedToMdmProvisionedWifi(_GUID,int *)

- ea: `0x1800cbf38`
- end: `0x1800cc42c`
- name: `?int_ConnectedToMdmProvisionedWifi@@YAKU_GUID@@PEAH@Z`
- size: `1268`
- prototype: `__int64 __fastcall(GUID *pInterfaceGuid, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x1800d8e74`

## callees

- `0x1800039ec`
- `0x180005e0c`
- `0x180005e34`
- `0x18000bf38`
- `0x18000bf70`
- `0x1800b81fc`
- `0x1800cbf38`
- `0x1800e2d24`
- `0x1800e2dbc`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanQueryInterface` at `0x1800cc117`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanQueryInterface` at `0x1800cc117`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanCloseHandle` at `0x1800cc37e`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanCloseHandle` at `0x1800cc37e`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x1800cc34a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x1800cc363`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x1800cc34a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x1800cc363`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfileMetadata` at `0x1800cc266`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfileMetadata` at `0x1800cc266`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x1800cc031`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x1800cc031`

## string_xrefs

- `0x1800cc087`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800cc0da`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800cc166`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800cc2b5`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800cc3f1`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`

## pseudocode

```c
__int64 __fastcall int_ConnectedToMdmProvisionedWifi(GUID *pInterfaceGuid, int *a2)
{
  DWORD v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // r8
  DWORD v9; // eax
  _OWORD *v10; // rax
  _OWORD *v11; // rdx
  __int64 v12; // rcx
  __int128 v13; // xmm1
  unsigned int ProfileMetadata; // eax
  PVOID v15; // [rsp+40h] [rbp-C0h] BYREF
  PVOID pMemory; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pdwDataSize; // [rsp+54h] [rbp-ACh] BYREF
  int v19; // [rsp+58h] [rbp-A8h] BYREF
  void *phClientHandle; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v21[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v22[600]; // [rsp+78h] [rbp-88h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF__guid_(WPP_GLOBAL_Control[1].Flink, 453, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, pInterfaceGuid);
  phClientHandle = 0;
  pdwNegotiatedVersion = 0;
  memset_0(v21, 0, 0x25Cu);
  pMemory = 0;
  pdwDataSize = 0;
  v15 = 0;
  v19 = 0;
  if ( !(unsigned __int8)IsWlanQueryInterfacePresent() )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 454, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    }
    return 0;
  }
  *a2 = 0;
  v5 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  v6 = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 456, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v5);
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        v6,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        4374,
        "int_ConnectedToMdmProvisionedWifi");
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 457, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v6);
    }
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      goto LABEL_51;
    v8 = 4375;
    goto LABEL_20;
  }
  v9 = WlanQueryInterface(
         phClientHandle,
         pInterfaceGuid,
         wlan_intf_opcode_current_connection,
         0,
         &pdwDataSize,
         &pMemory,
         0);
  v6 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 458, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v9);
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        v6,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        4385,
        "int_ConnectedToMdmProvisionedWifi");
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 459, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v6);
    }
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      goto LABEL_51;
    v8 = 4386;
    goto LABEL_20;
  }
  v10 = pMemory;
  v11 = v21;
  v12 = 4;
  do
  {
    *v11 = *v10;
    v11[1] = v10[1];
    v11[2] = v10[2];
    v11[3] = v10[3];
    v11[4] = v10[4];
    v11[5] = v10[5];
    v11[6] = v10[6];
    v13 = v10[7];
    v10 += 8;
    v11[7] = v13;
    v11 += 8;
    --v12;
  }
  while ( v12 );
  *v11 = *v10;
  v11[1] = v10[1];
  v11[2] = v10[2];
  v11[3] = v10[3];
  v11[4] = v10[4];
  *(_OWORD *)((char *)v11 + 76) = *(_OWORD *)((char *)v10 + 76);
  ProfileMetadata = WlanGetProfileMetadata(pInterfaceGuid, v22, 0, L"Connection Type", &v19, &v15);
  v6 = ProfileMetadata;
  if ( !ProfileMetadata )
  {
    v7 = *(unsigned int *)v15;
    if ( (_DWORD)v7 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 462, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v7);
      }
      if ( *(_DWORD *)v15 == 8 )
        *a2 = 1;
    }
    goto LABEL_51;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 460, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, ProfileMetadata);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    TraceVpnWppErrorW32Impl(
      v6,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      4397,
      "int_ConnectedToMdmProvisionedWifi");
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 461, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v6);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
  {
    v8 = 4398;
LABEL_20:
    TraceVpnWppErrorW32Impl(
      v6,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      v8,
      "int_ConnectedToMdmProvisionedWifi");
  }
LABEL_51:
  if ( pMemory )
  {
    WlanFreeMemory(pMemory);
    pMemory = 0;
  }
  if ( v15 )
  {
    WlanFreeMemory(v15);
    v15 = 0;
  }
  if ( phClientHandle )
    WlanCloseHandle(phClientHandle, 0);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
  {
    LOBYTE(v7) = *a2 != 0;
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 463, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v7);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 464, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v6);
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        v6,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        4429,
        "int_ConnectedToMdmProvisionedWifi");
  }
  return v6;
}

```

## disassembly

```asm
0x1800cbf38  mov     [rsp-8+arg_10], rbx
0x1800cbf3d  mov     [rsp-8+arg_18], rsi
0x1800cbf42  push    rbp
0x1800cbf43  push    rdi
0x1800cbf44  push    r12
0x1800cbf46  push    r13
0x1800cbf48  push    r15
0x1800cbf4a  lea     rbp, [rsp-1E0h]
0x1800cbf52  sub     rsp, 2E0h
0x1800cbf59  mov     rax, cs:__security_cookie
0x1800cbf60  xor     rax, rsp
0x1800cbf63  mov     [rbp+200h+var_30], rax
0x1800cbf6a  mov     rsi, rdx
0x1800cbf6d  mov     rdi, rcx
0x1800cbf70  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbf77  lea     r15, WPP_GLOBAL_Control
0x1800cbf7e  lea     r12, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800cbf85  cmp     rcx, r15
0x1800cbf88  jz      short loc_1800CBFA4
0x1800cbf8a  test    byte ptr [rcx+1Ch], 8
0x1800cbf8e  jz      short loc_1800CBFA4
0x1800cbf90  mov     rcx, [rcx+10h]
0x1800cbf94  mov     edx, 1C5h
0x1800cbf99  mov     r9, rdi
0x1800cbf9c  mov     r8, r12
0x1800cbf9f  call    WPP_SF__guid_
0x1800cbfa4  xor     edx, edx; Val
0x1800cbfa6  mov     [rsp+300h+phClientHandle], 0
0x1800cbfaf  mov     r8d, 25Ch; Size
0x1800cbfb5  mov     [rsp+300h+pdwNegotiatedVersion], 0
0x1800cbfbd  lea     rcx, [rsp+300h+var_290]; void *
0x1800cbfc2  call    memset_0
0x1800cbfc7  mov     [rsp+300h+pMemory], 0
0x1800cbfd0  mov     [rsp+300h+var_2AC], 0
0x1800cbfd8  mov     [rsp+300h+var_2C0], 0
0x1800cbfe1  mov     [rsp+300h+var_2A8], 0
0x1800cbfe9  call    IsWlanQueryInterfacePresent
0x1800cbfee  test    al, al
0x1800cbff0  jnz     short loc_1800CC01C
0x1800cbff2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbff9  cmp     rcx, r15
0x1800cbffc  jz      short loc_1800CC015
0x1800cbffe  test    byte ptr [rcx+1Ch], 4
0x1800cc002  jz      short loc_1800CC015
0x1800cc004  mov     rcx, [rcx+10h]
0x1800cc008  mov     edx, 1C6h
0x1800cc00d  mov     r8, r12
0x1800cc010  call    WPP_SF_
0x1800cc015  xor     eax, eax
0x1800cc017  jmp     loc_1800CC401
0x1800cc01c  xor     edx, edx; pReserved
0x1800cc01e  mov     dword ptr [rsi], 0
0x1800cc024  lea     r9, [rsp+300h+phClientHandle]; phClientHandle
0x1800cc029  lea     r8, [rsp+300h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x1800cc02e  lea     ecx, [rdx+2]; dwClientVersion
0x1800cc031  call    cs:__imp_WlanOpenHandle
0x1800cc037  lea     r13, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800cc03e  mov     ebx, eax
0x1800cc040  test    eax, eax
0x1800cc042  jz      loc_1800CC0EB
0x1800cc048  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc04f  cmp     rcx, r15
0x1800cc052  jz      short loc_1800CC06E
0x1800cc054  test    byte ptr [rcx+1Ch], 1
0x1800cc058  jz      short loc_1800CC06E
0x1800cc05a  mov     rcx, [rcx+10h]
0x1800cc05e  mov     edx, 1C8h
0x1800cc063  mov     r9d, eax
0x1800cc066  mov     r8, r12
0x1800cc069  call    WPP_SF_d
0x1800cc06e  mov     rcx, r13
0x1800cc071  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800cc076  test    al, al
0x1800cc078  jz      short loc_1800CC095
0x1800cc07a  lea     r9, aIntConnectedto; "int_ConnectedToMdmProvisionedWifi"
0x1800cc081  mov     r8d, 1116h
0x1800cc087  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800cc08e  mov     ecx, ebx
0x1800cc090  call    TraceVpnWppErrorW32Impl
0x1800cc095  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc09c  cmp     rcx, r15
0x1800cc09f  jz      short loc_1800CC0BB
0x1800cc0a1  test    byte ptr [rcx+1Ch], 1
0x1800cc0a5  jz      short loc_1800CC0BB
0x1800cc0a7  mov     rcx, [rcx+10h]
0x1800cc0ab  mov     edx, 1C9h
0x1800cc0b0  mov     r9d, ebx
0x1800cc0b3  mov     r8, r12
0x1800cc0b6  call    WPP_SF_d
0x1800cc0bb  mov     rcx, r13
0x1800cc0be  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800cc0c3  test    al, al
0x1800cc0c5  jz      loc_1800CC340
0x1800cc0cb  mov     r8d, 1117h
0x1800cc0d1  lea     r9, aIntConnectedto; "int_ConnectedToMdmProvisionedWifi"
0x1800cc0d8  mov     ecx, ebx
0x1800cc0da  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800cc0e1  call    TraceVpnWppErrorW32Impl
0x1800cc0e6  jmp     loc_1800CC340
0x1800cc0eb  mov     rcx, [rsp+300h+phClientHandle]; hClientHandle
0x1800cc0f0  lea     rax, [rsp+300h+pMemory]
0x1800cc0f5  xor     r9d, r9d; pReserved
0x1800cc0f8  mov     [rsp+300h+pWlanOpcodeValueType], 0; pWlanOpcodeValueType
0x1800cc101  mov     [rsp+300h+ppData], rax; ppData
0x1800cc106  mov     rdx, rdi; pInterfaceGuid
0x1800cc109  lea     rax, [rsp+300h+var_2AC]
0x1800cc10e  mov     [rsp+300h+pdwDataSize], rax; pdwDataSize
0x1800cc113  lea     r8d, [r9+7]; OpCode
0x1800cc117  call    cs:__imp_WlanQueryInterface
0x1800cc11d  mov     ebx, eax
0x1800cc11f  test    eax, eax
0x1800cc121  jz      loc_1800CC1B5
0x1800cc127  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc12e  cmp     rcx, r15
0x1800cc131  jz      short loc_1800CC14D
0x1800cc133  test    byte ptr [rcx+1Ch], 1
0x1800cc137  jz      short loc_1800CC14D
0x1800cc139  mov     rcx, [rcx+10h]
0x1800cc13d  mov     edx, 1CAh
0x1800cc142  mov     r9d, eax
0x1800cc145  mov     r8, r12
0x1800cc148  call    WPP_SF_d
0x1800cc14d  mov     rcx, r13
0x1800cc150  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800cc155  test    al, al
0x1800cc157  jz      short loc_1800CC174
0x1800cc159  lea     r9, aIntConnectedto; "int_ConnectedToMdmProvisionedWifi"
0x1800cc160  mov     r8d, 1121h
0x1800cc166  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800cc16d  mov     ecx, ebx
0x1800cc16f  call    TraceVpnWppErrorW32Impl
0x1800cc174  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc17b  cmp     rcx, r15
0x1800cc17e  jz      short loc_1800CC19A
0x1800cc180  test    byte ptr [rcx+1Ch], 1
0x1800cc184  jz      short loc_1800CC19A
0x1800cc186  mov     rcx, [rcx+10h]
0x1800cc18a  mov     edx, 1CBh
0x1800cc18f  mov     r9d, ebx
0x1800cc192  mov     r8, r12
0x1800cc195  call    WPP_SF_d
0x1800cc19a  mov     rcx, r13
0x1800cc19d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800cc1a2  test    al, al
0x1800cc1a4  jz      loc_1800CC340
0x1800cc1aa  mov     r8d, 1122h
0x1800cc1b0  jmp     loc_1800CC0D1
0x1800cc1b5  mov     rax, [rsp+300h+pMemory]
0x1800cc1ba  lea     rdx, [rsp+300h+var_290]
0x1800cc1bf  mov     ecx, 4
0x1800cc1c4  lea     r8d, [rcx+7Ch]
0x1800cc1c8  movups  xmm0, xmmword ptr [rax]
0x1800cc1cb  movups  xmmword ptr [rdx], xmm0
0x1800cc1ce  movups  xmm1, xmmword ptr [rax+10h]
0x1800cc1d2  movups  xmmword ptr [rdx+10h], xmm1
0x1800cc1d6  movups  xmm0, xmmword ptr [rax+20h]
0x1800cc1da  movups  xmmword ptr [rdx+20h], xmm0
0x1800cc1de  movups  xmm1, xmmword ptr [rax+30h]
0x1800cc1e2  movups  xmmword ptr [rdx+30h], xmm1
0x1800cc1e6  movups  xmm0, xmmword ptr [rax+40h]
0x1800cc1ea  movups  xmmword ptr [rdx+40h], xmm0
0x1800cc1ee  movups  xmm1, xmmword ptr [rax+50h]
0x1800cc1f2  movups  xmmword ptr [rdx+50h], xmm1
0x1800cc1f6  movups  xmm0, xmmword ptr [rax+60h]
0x1800cc1fa  movups  xmmword ptr [rdx+60h], xmm0
0x1800cc1fe  movups  xmm1, xmmword ptr [rax+70h]
0x1800cc202  add     rax, r8
0x1800cc205  movups  xmmword ptr [rdx+70h], xmm1
0x1800cc209  add     rdx, r8
0x1800cc20c  sub     rcx, 1
0x1800cc210  jnz     short loc_1800CC1C8
0x1800cc212  movups  xmm0, xmmword ptr [rax]
0x1800cc215  lea     r9, aConnectionType; "Connection Type"
0x1800cc21c  xor     r8d, r8d
0x1800cc21f  mov     rcx, rdi
0x1800cc222  movups  xmmword ptr [rdx], xmm0
0x1800cc225  movups  xmm1, xmmword ptr [rax+10h]
0x1800cc229  movups  xmmword ptr [rdx+10h], xmm1
0x1800cc22d  movups  xmm0, xmmword ptr [rax+20h]
0x1800cc231  movups  xmmword ptr [rdx+20h], xmm0
0x1800cc235  movups  xmm1, xmmword ptr [rax+30h]
0x1800cc239  movups  xmmword ptr [rdx+30h], xmm1
0x1800cc23d  movups  xmm0, xmmword ptr [rax+40h]
0x1800cc241  movups  xmmword ptr [rdx+40h], xmm0
0x1800cc245  movups  xmm1, xmmword ptr [rax+4Ch]
0x1800cc249  lea     rax, [rsp+300h+var_2C0]
0x1800cc24e  mov     [rsp+300h+ppData], rax
0x1800cc253  lea     rax, [rsp+300h+var_2A8]
0x1800cc258  movups  xmmword ptr [rdx+4Ch], xmm1
0x1800cc25c  lea     rdx, [rsp+300h+var_288]
0x1800cc261  mov     [rsp+300h+pdwDataSize], rax
0x1800cc266  call    cs:__imp_WlanGetProfileMetadata
0x1800cc26c  mov     ebx, eax
0x1800cc26e  test    eax, eax
0x1800cc270  jz      loc_1800CC300
0x1800cc276  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc27d  cmp     rcx, r15
0x1800cc280  jz      short loc_1800CC29C
0x1800cc282  test    byte ptr [rcx+1Ch], 1
0x1800cc286  jz      short loc_1800CC29C
0x1800cc288  mov     rcx, [rcx+10h]
0x1800cc28c  mov     edx, 1CCh
0x1800cc291  mov     r9d, eax
0x1800cc294  mov     r8, r12
0x1800cc297  call    WPP_SF_d
0x1800cc29c  mov     rcx, r13
0x1800cc29f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800cc2a4  test    al, al
0x1800cc2a6  jz      short loc_1800CC2C3
0x1800cc2a8  lea     r9, aIntConnectedto; "int_ConnectedToMdmProvisionedWifi"
0x1800cc2af  mov     r8d, 112Dh
0x1800cc2b5  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800cc2bc  mov     ecx, ebx
0x1800cc2be  call    TraceVpnWppErrorW32Impl
0x1800cc2c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc2ca  cmp     rcx, r15
0x1800cc2cd  jz      short loc_1800CC2E9
0x1800cc2cf  test    byte ptr [rcx+1Ch], 1
0x1800cc2d3  jz      short loc_1800CC2E9
0x1800cc2d5  mov     rcx, [rcx+10h]
0x1800cc2d9  mov     edx, 1CDh
0x1800cc2de  mov     r9d, ebx
0x1800cc2e1  mov     r8, r12
0x1800cc2e4  call    WPP_SF_d
0x1800cc2e9  mov     rcx, r13
0x1800cc2ec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800cc2f1  test    al, al
0x1800cc2f3  jz      short loc_1800CC340
0x1800cc2f5  mov     r8d, 112Eh
0x1800cc2fb  jmp     loc_1800CC0D1
0x1800cc300  mov     rax, [rsp+300h+var_2C0]
0x1800cc305  mov     r9d, [rax]
0x1800cc308  test    r9d, r9d
0x1800cc30b  jz      short loc_1800CC340
0x1800cc30d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc314  cmp     rcx, r15
0x1800cc317  jz      short loc_1800CC330
0x1800cc319  test    byte ptr [rcx+1Ch], 4
0x1800cc31d  jz      short loc_1800CC330
0x1800cc31f  mov     rcx, [rcx+10h]
0x1800cc323  mov     edx, 1CEh
0x1800cc328  mov     r8, r12
0x1800cc32b  call    WPP_SF_d
0x1800cc330  mov     rax, [rsp+300h+var_2C0]
0x1800cc335  cmp     dword ptr [rax], 8
0x1800cc338  jnz     short loc_1800CC340
0x1800cc33a  mov     dword ptr [rsi], 1
0x1800cc340  mov     rcx, [rsp+300h+pMemory]; pMemory
0x1800cc345  test    rcx, rcx
0x1800cc348  jz      short loc_1800CC359
0x1800cc34a  call    cs:__imp_WlanFreeMemory
0x1800cc350  mov     [rsp+300h+pMemory], 0
0x1800cc359  mov     rcx, [rsp+300h+var_2C0]; pMemory
0x1800cc35e  test    rcx, rcx
0x1800cc361  jz      short loc_1800CC372
0x1800cc363  call    cs:__imp_WlanFreeMemory
0x1800cc369  mov     [rsp+300h+var_2C0], 0
0x1800cc372  mov     rcx, [rsp+300h+phClientHandle]; hClientHandle
0x1800cc377  test    rcx, rcx
0x1800cc37a  jz      short loc_1800CC384
0x1800cc37c  xor     edx, edx; pReserved
0x1800cc37e  call    cs:__imp_WlanCloseHandle
0x1800cc384  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc38b  cmp     rcx, r15
0x1800cc38e  jz      short loc_1800CC3AE
0x1800cc390  test    byte ptr [rcx+1Ch], 4
0x1800cc394  jz      short loc_1800CC3AE
0x1800cc396  cmp     dword ptr [rsi], 0
0x1800cc399  mov     edx, 1CFh
0x1800cc39e  mov     rcx, [rcx+10h]
0x1800cc3a2  mov     r8, r12
0x1800cc3a5  setnz   r9b
0x1800cc3a9  call    WPP_SF_c
0x1800cc3ae  test    ebx, ebx
0x1800cc3b0  jns     short loc_1800CC3FF
0x1800cc3b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc3b9  cmp     rcx, r15
0x1800cc3bc  jz      short loc_1800CC3D8
0x1800cc3be  test    byte ptr [rcx+1Ch], 8
0x1800cc3c2  jz      short loc_1800CC3D8
0x1800cc3c4  mov     rcx, [rcx+10h]
0x1800cc3c8  mov     edx, 1D0h
0x1800cc3cd  mov     r9d, ebx
0x1800cc3d0  mov     r8, r12
0x1800cc3d3  call    WPP_SF_d
0x1800cc3d8  mov     rcx, r13
0x1800cc3db  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800cc3e0  test    al, al
0x1800cc3e2  jz      short loc_1800CC3FF
0x1800cc3e4  lea     r9, aIntConnectedto; "int_ConnectedToMdmProvisionedWifi"
0x1800cc3eb  mov     r8d, 114Dh
0x1800cc3f1  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800cc3f8  mov     ecx, ebx
0x1800cc3fa  call    TraceVpnWppErrorHRImpl
0x1800cc3ff  mov     eax, ebx
0x1800cc401  mov     rcx, [rbp+200h+var_30]
0x1800cc408  xor     rcx, rsp; StackCookie
0x1800cc40b  call    __security_check_cookie
0x1800cc410  lea     r11, [rsp+300h+var_20]
0x1800cc418  mov     rbx, [r11+40h]
  ... truncated ...
```
