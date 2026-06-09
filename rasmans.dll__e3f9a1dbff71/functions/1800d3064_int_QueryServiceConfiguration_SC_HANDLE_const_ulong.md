# int_QueryServiceConfiguration(SC_HANDLE__ * const,ulong *)

- ea: `0x1800d3064`
- end: `0x1800d3255`
- name: `?int_QueryServiceConfiguration@@YAHQEAUSC_HANDLE__@@PEAK@Z`
- size: `497`
- prototype: `__int64 __fastcall(SC_HANDLE hService, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e014c`

## callees

- `0x180005e34`
- `0x18007b2ec`
- `0x1800a5770`
- `0x1800b81fc`
- `0x1800d3064`
- `0x1800e1b9c`
- `0x1800e2dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d309e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3155`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d309e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3155`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800d3089`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800d3139`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800d3089`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800d3139`

## string_xrefs

- `0x1800d3115`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d31f8`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d3108`: `int_QueryServiceConfiguration`
- `0x1800d31ef`: `int_QueryServiceConfiguration`

## pseudocode

```c
__int64 __fastcall int_QueryServiceConfiguration(SC_HANDLE hService, unsigned int *a2)
{
  DWORD LastError; // eax
  unsigned int v5; // ebx
  DWORD v6; // edi
  struct _QUERY_SERVICE_CONFIGW *v7; // rax
  struct _QUERY_SERVICE_CONFIGW *v8; // rsi
  unsigned int v9; // edi
  DWORD v10; // eax
  __int64 v11; // r8
  DWORD cbBufSize; // [rsp+80h] [rbp+18h] BYREF

  cbBufSize = 0;
  if ( QueryServiceConfigW(hService, 0, 0, &cbBufSize) )
  {
    v5 = 0;
    v9 = 0;
    goto LABEL_27;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError == 122 )
  {
    v6 = cbBufSize;
    v7 = (struct _QUERY_SERVICE_CONFIGW *)VpnAlloc(cbBufSize);
    v8 = v7;
    if ( !v7 )
    {
      v9 = 0;
      v5 = 14;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 994, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          14,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          9583,
          "int_QueryServiceConfiguration");
      goto LABEL_27;
    }
    if ( QueryServiceConfigW(hService, v7, v6, &cbBufSize) )
    {
      v9 = 1;
      *a2 = v8->dwStartType;
      goto LABEL_24;
    }
    v9 = 0;
    v10 = GetLastError();
    v5 = v10;
    if ( !v10 )
      goto LABEL_24;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 995, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v10);
    }
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      goto LABEL_24;
    v11 = 9595;
LABEL_23:
    TraceVpnWppErrorW32Impl(
      v5,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      v11,
      "int_QueryServiceConfiguration");
LABEL_24:
    if ( v8 )
      MprCommonFree(v8);
    goto LABEL_27;
  }
  v9 = 0;
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 996, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, LastError);
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    {
      v8 = 0;
      v11 = 9602;
      goto LABEL_23;
    }
  }
LABEL_27:
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_Dc(WPP_GLOBAL_Control[1].Flink, 997, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v5);
  return v9;
}

```

## disassembly

```asm
0x1800d3064  mov     rax, rsp
0x1800d3067  push    rbx
0x1800d3068  push    rbp
0x1800d3069  push    rsi
0x1800d306a  push    rdi
0x1800d306b  push    r14
0x1800d306d  push    r15
0x1800d306f  sub     rsp, 38h
0x1800d3073  mov     r14, rdx
0x1800d3076  mov     dword ptr [rax+18h], 0
0x1800d307d  xor     edx, edx; lpServiceConfig
0x1800d307f  lea     r9, [rax+18h]; pcbBytesNeeded
0x1800d3083  xor     r8d, r8d; cbBufSize
0x1800d3086  mov     rbp, rcx
0x1800d3089  call    cs:__imp_QueryServiceConfigW
0x1800d308f  lea     r15, WPP_GLOBAL_Control
0x1800d3096  test    eax, eax
0x1800d3098  jnz     loc_1800D3213
0x1800d309e  call    cs:__imp_GetLastError
0x1800d30a4  mov     ebx, eax
0x1800d30a6  cmp     eax, 7Ah ; 'z'
0x1800d30a9  jnz     loc_1800D31A7
0x1800d30af  mov     edi, [rsp+68h+cbBufSize]
0x1800d30b6  mov     ecx, edi
0x1800d30b8  call    VpnAlloc
0x1800d30bd  mov     rsi, rax
0x1800d30c0  test    rax, rax
0x1800d30c3  jnz     short loc_1800D3128
0x1800d30c5  xor     edi, edi
0x1800d30c7  lea     ebx, [rax+0Eh]
0x1800d30ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d30d1  cmp     rcx, r15
0x1800d30d4  jz      short loc_1800D30F4
0x1800d30d6  test    byte ptr [rcx+1Ch], 1
0x1800d30da  jz      short loc_1800D30F4
0x1800d30dc  mov     rcx, [rcx+10h]
0x1800d30e0  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d30e7  mov     edx, 3E2h
0x1800d30ec  mov     r9d, ebx
0x1800d30ef  call    WPP_SF_d
0x1800d30f4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d30fb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d3100  test    al, al
0x1800d3102  jz      loc_1800D3217
0x1800d3108  lea     r9, aIntQueryservic; "int_QueryServiceConfiguration"
0x1800d310f  mov     r8d, 256Fh
0x1800d3115  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d311c  mov     ecx, ebx
0x1800d311e  call    TraceVpnWppErrorW32Impl
0x1800d3123  jmp     loc_1800D3217
0x1800d3128  lea     r9, [rsp+68h+cbBufSize]; pcbBytesNeeded
0x1800d3130  mov     r8d, edi; cbBufSize
0x1800d3133  mov     rdx, rsi; lpServiceConfig
0x1800d3136  mov     rcx, rbp; hService
0x1800d3139  call    cs:__imp_QueryServiceConfigW
0x1800d313f  test    eax, eax
0x1800d3141  jz      short loc_1800D3153
0x1800d3143  mov     eax, [rsi+4]
0x1800d3146  mov     edi, 1
0x1800d314b  mov     [r14], eax
0x1800d314e  jmp     loc_1800D3204
0x1800d3153  xor     edi, edi
0x1800d3155  call    cs:__imp_GetLastError
0x1800d315b  mov     ebx, eax
0x1800d315d  test    eax, eax
0x1800d315f  jz      loc_1800D3204
0x1800d3165  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d316c  cmp     rcx, r15
0x1800d316f  jz      short loc_1800D318F
0x1800d3171  test    byte ptr [rcx+1Ch], 1
0x1800d3175  jz      short loc_1800D318F
0x1800d3177  mov     rcx, [rcx+10h]
0x1800d317b  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d3182  mov     edx, 3E3h
0x1800d3187  mov     r9d, eax
0x1800d318a  call    WPP_SF_d
0x1800d318f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d3196  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d319b  test    al, al
0x1800d319d  jz      short loc_1800D3204
0x1800d319f  mov     r8d, 257Bh
0x1800d31a5  jmp     short loc_1800D31EF
0x1800d31a7  xor     edi, edi
0x1800d31a9  test    ebx, ebx
0x1800d31ab  jz      short loc_1800D3217
0x1800d31ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d31b4  cmp     rcx, r15
0x1800d31b7  jz      short loc_1800D31D7
0x1800d31b9  test    byte ptr [rcx+1Ch], 1
0x1800d31bd  jz      short loc_1800D31D7
0x1800d31bf  mov     rcx, [rcx+10h]
0x1800d31c3  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d31ca  mov     edx, 3E4h
0x1800d31cf  mov     r9d, ebx
0x1800d31d2  call    WPP_SF_d
0x1800d31d7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d31de  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d31e3  test    al, al
0x1800d31e5  jz      short loc_1800D3217
0x1800d31e7  xor     esi, esi
0x1800d31e9  mov     r8d, 2582h
0x1800d31ef  lea     r9, aIntQueryservic; "int_QueryServiceConfiguration"
0x1800d31f6  mov     ecx, ebx
0x1800d31f8  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d31ff  call    TraceVpnWppErrorW32Impl
0x1800d3204  test    rsi, rsi
0x1800d3207  jz      short loc_1800D3217
0x1800d3209  mov     rcx, rsi; lpMem
0x1800d320c  call    MprCommonFree
0x1800d3211  jmp     short loc_1800D3217
0x1800d3213  xor     ebx, ebx
0x1800d3215  xor     edi, edi
0x1800d3217  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d321e  cmp     rcx, r15
0x1800d3221  jz      short loc_1800D3246
0x1800d3223  test    byte ptr [rcx+1Ch], 8
0x1800d3227  jz      short loc_1800D3246
0x1800d3229  mov     rcx, [rcx+10h]
0x1800d322d  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d3234  mov     edx, 3E5h
0x1800d3239  mov     [rsp+68h+var_48], dil
0x1800d323e  mov     r9d, ebx
0x1800d3241  call    WPP_SF_Dc
0x1800d3246  mov     eax, edi
0x1800d3248  add     rsp, 38h
0x1800d324c  pop     r15
0x1800d324e  pop     r14
0x1800d3250  pop     rdi
0x1800d3251  pop     rsi
0x1800d3252  pop     rbp
0x1800d3253  pop     rbx
0x1800d3254  retn
```
