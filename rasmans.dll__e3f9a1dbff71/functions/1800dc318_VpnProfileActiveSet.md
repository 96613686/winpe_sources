# VpnProfileActiveSet

- ea: `0x1800dc318`
- end: `0x1800dc766`
- name: `VpnProfileActiveSet`
- size: `1102`
- prototype: `__int64 __fastcall(void *Src, char *, const char *, int, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002f250`
- `0x180030340`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x1800b81fc`
- `0x1800c0e48`
- `0x1800dc318`
- `0x1800e0b3c`
- `0x1800e1cd8`
- `0x1800e1d04`
- `0x1800e1e64`
- `0x1800e2464`
- `0x1800e2d24`
- `0x1800e2dbc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800dc3ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800dc3ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800dc3be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800dc3be`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dc750`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dc750`

## string_xrefs

- `0x1800dc417`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800dc46f`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800dc50c`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800dc5b6`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800dc655`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800dc68e`: `VpnStringCopy for Context.userSid`
- `0x1800dc545`: `VpnStringCopy for Context.phonebookPath`
- `0x1800dc5ef`: `VpnStringCopy for Context.entryName`

## pseudocode

```c
__int64 __fastcall VpnProfileActiveSet(void *Src, char *a2, const char *a3, int a4, int a5)
{
  char *v5; // r13
  const char *v8; // rax
  HANDLE ProcessHeap; // rax
  _DWORD *v10; // r14
  unsigned int v11; // esi
  int v12; // ebx
  int v13; // eax
  const char *v15; // rdx
  int v16; // eax
  int v17; // eax
  int v19; // eax
  int v20; // eax
  _QWORD *v22; // rcx

  v5 = (char *)a3;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    v8 = a2;
    if ( !a3 )
      a3 = L"<NULL>";
    if ( !a2 )
      v8 = L"<NULL>";
    WPP_SF_SSScc((TRACEHANDLE)WPP_GLOBAL_Control[1].Flink, (__int64)v8, (__int64)a3, a4 != 0, a5 != 0);
  }
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 8u, 0x30u);
  if ( !v10 )
  {
    v11 = 14;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 658, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        14,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        6467,
        "VpnProfileActiveSet");
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 659, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        14,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        6469,
        "VpnProfileActiveSet");
    FreeSetProfileContext(0);
    return v11;
  }
  v11 = 0;
  if ( Src && a2 && v5 )
  {
    v12 = VpnStringCopy(Src);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 660, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, (unsigned int)v12);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorHRImpl(
          (unsigned int)v12,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          6474,
          "VpnProfileActiveSet");
      v13 = (v12 >> 16) & 0x1FFF;
      if ( v13 == 7 ? (unsigned __int16)v12 : v12 )
      {
        if ( v13 == 7 )
          v12 = (unsigned __int16)v12;
        v15 = "VpnStringCopy for Context.phonebookPath";
LABEL_36:
        VpnReportError("VpnProfileActiveSet", v15, (unsigned int)v12);
        return v11;
      }
    }
    v16 = VpnStringCopy(a2);
    v12 = v16;
    if ( v16 < 0 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 661, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, (unsigned int)v16);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorHRImpl(
          (unsigned int)v12,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          6478,
          "VpnProfileActiveSet");
      v17 = (v12 >> 16) & 0x1FFF;
      if ( v17 == 7 ? (unsigned __int16)v12 : v12 )
      {
        if ( v17 == 7 )
          v12 = (unsigned __int16)v12;
        v15 = "VpnStringCopy for Context.entryName";
        goto LABEL_36;
      }
    }
    v19 = VpnStringCopy(v5);
    v12 = v19;
    if ( v19 < 0 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 662, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, (unsigned int)v19);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorHRImpl(
          (unsigned int)v12,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          6482,
          "VpnProfileActiveSet");
      v20 = (v12 >> 16) & 0x1FFF;
      if ( v20 == 7 ? (unsigned __int16)v12 : v12 )
      {
        if ( v20 == 7 )
          v12 = (unsigned __int16)v12;
        v15 = "VpnStringCopy for Context.userSid";
        goto LABEL_36;
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
         && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 663, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
  }
  v10[6] = a4;
  v10[7] = a5;
  VpnCriticalSectionEnter(&g_CsSetActiveProfileOperation);
  v22 = (_QWORD *)qword_18010E770;
  if ( *(struct _LIST_ENTRY **)qword_18010E770 != &g_RasSetActiveList )
    __fastfail(3u);
  *((_QWORD *)v10 + 5) = qword_18010E770;
  *((_QWORD *)v10 + 4) = &g_RasSetActiveList;
  *v22 = v10 + 8;
  qword_18010E770 = (__int64)(v10 + 8);
  VpnCriticalSectionLeave(&g_CsSetActiveProfileOperation);
  VpnCriticalSectionEnter(&g_connMonitorCs);
  if ( g_pMonitor )
  {
    *((_DWORD *)g_pMonitor + 5) = 1;
    VpnCriticalSectionLeave(&g_connMonitorCs);
  }
  SubmitThreadpoolWork(g_pSetActiveProfileWorkItem);
  return v11;
}

```

## disassembly

```asm
0x1800dc318  mov     [rsp+arg_18], r9d
0x1800dc31d  push    rbx
0x1800dc31e  push    rsi
0x1800dc31f  push    rdi
0x1800dc320  push    r12
0x1800dc322  push    r13
0x1800dc324  push    r14
0x1800dc326  sub     rsp, 48h
0x1800dc32a  mov     eax, r9d
0x1800dc32d  mov     r13, r8
0x1800dc330  mov     r12, rdx
0x1800dc333  mov     rbx, rcx
0x1800dc336  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc33d  lea     rdi, WPP_GLOBAL_Control
0x1800dc344  cmp     rcx, rdi
0x1800dc347  jz      short loc_1800DC3AC
0x1800dc349  test    byte ptr [rcx+1Ch], 8
0x1800dc34d  jz      short loc_1800DC3AC
0x1800dc34f  cmp     [rsp+78h+arg_20], 0
0x1800dc357  lea     rdi, aNull_5; "<NULL>"
0x1800dc35e  mov     rcx, [rcx+10h]; LoggerHandle
0x1800dc362  mov     r9, rbx
0x1800dc365  setnz   r11b
0x1800dc369  test    eax, eax
0x1800dc36b  mov     [rsp+78h+var_40], r11b; char
0x1800dc370  mov     rax, rdx
0x1800dc373  setnz   r10b
0x1800dc377  test    r8, r8
0x1800dc37a  mov     [rsp+78h+var_48], r10b; char
0x1800dc37f  cmovz   r8, rdi
0x1800dc383  test    rdx, rdx
0x1800dc386  mov     [rsp+78h+var_50], r8; __int64
0x1800dc38b  mov     edx, 291h
0x1800dc390  cmovz   rax, rdi
0x1800dc394  test    rbx, rbx
0x1800dc397  mov     [rsp+78h+var_58], rax; __int64
0x1800dc39c  cmovz   r9, rdi
0x1800dc3a0  call    WPP_SF_SSScc
0x1800dc3a5  lea     rdi, WPP_GLOBAL_Control
0x1800dc3ac  call    cs:__imp_GetProcessHeap
0x1800dc3b2  mov     edx, 8; dwFlags
0x1800dc3b7  mov     rcx, rax; hHeap
0x1800dc3ba  lea     r8d, [rdx+28h]; dwBytes
0x1800dc3be  call    cs:__imp_HeapAlloc
0x1800dc3c4  mov     r14, rax
0x1800dc3c7  test    rax, rax
0x1800dc3ca  jnz     loc_1800DC48F
0x1800dc3d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc3d7  lea     esi, [rax+0Eh]
0x1800dc3da  cmp     rcx, rdi
0x1800dc3dd  jz      short loc_1800DC3FD
0x1800dc3df  test    byte ptr [rcx+1Ch], 1
0x1800dc3e3  jz      short loc_1800DC3FD
0x1800dc3e5  mov     rcx, [rcx+10h]
0x1800dc3e9  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800dc3f0  mov     edx, 292h
0x1800dc3f5  mov     r9d, esi
0x1800dc3f8  call    WPP_SF_d
0x1800dc3fd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800dc404  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800dc409  lea     rdi, aVpnprofileacti_1; "VpnProfileActiveSet"
0x1800dc410  test    al, al
0x1800dc412  jz      short loc_1800DC42B
0x1800dc414  mov     r9, rdi
0x1800dc417  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800dc41e  mov     r8d, 1943h
0x1800dc424  mov     ecx, esi
0x1800dc426  call    TraceVpnWppErrorW32Impl
0x1800dc42b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc432  lea     rax, WPP_GLOBAL_Control
0x1800dc439  cmp     rcx, rax
0x1800dc43c  jz      short loc_1800DC45C
0x1800dc43e  test    byte ptr [rcx+1Ch], 1
0x1800dc442  jz      short loc_1800DC45C
0x1800dc444  mov     rcx, [rcx+10h]
0x1800dc448  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800dc44f  mov     edx, 293h
0x1800dc454  mov     r9d, esi
0x1800dc457  call    WPP_SF_d
0x1800dc45c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800dc463  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800dc468  test    al, al
0x1800dc46a  jz      short loc_1800DC483
0x1800dc46c  mov     r9, rdi
0x1800dc46f  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800dc476  mov     r8d, 1945h
0x1800dc47c  mov     ecx, esi
0x1800dc47e  call    TraceVpnWppErrorW32Impl
0x1800dc483  xor     ecx, ecx; lpMem
0x1800dc485  call    ?FreeSetProfileContext@@YAXPEAU_SET_ACTIVE_PROFILE_WORK_CONTEXT@@@Z; FreeSetProfileContext(_SET_ACTIVE_PROFILE_WORK_CONTEXT *)
0x1800dc48a  jmp     loc_1800DC756
0x1800dc48f  xor     esi, esi
0x1800dc491  test    rbx, rbx
0x1800dc494  jz      loc_1800DC69A
0x1800dc49a  test    r12, r12
0x1800dc49d  jz      loc_1800DC69A
0x1800dc4a3  test    r13, r13
0x1800dc4a6  jz      loc_1800DC69A
0x1800dc4ac  mov     rdx, r14
0x1800dc4af  mov     rcx, rbx; Src
0x1800dc4b2  call    VpnStringCopy
0x1800dc4b7  lea     rdi, aVpnprofileacti_1; "VpnProfileActiveSet"
0x1800dc4be  mov     ebx, eax
0x1800dc4c0  test    eax, eax
0x1800dc4c2  jns     loc_1800DC55C
0x1800dc4c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc4cf  lea     rax, WPP_GLOBAL_Control
0x1800dc4d6  cmp     rcx, rax
0x1800dc4d9  jz      short loc_1800DC4F9
0x1800dc4db  test    byte ptr [rcx+1Ch], 1
0x1800dc4df  jz      short loc_1800DC4F9
0x1800dc4e1  mov     rcx, [rcx+10h]
0x1800dc4e5  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800dc4ec  mov     edx, 294h
0x1800dc4f1  mov     r9d, ebx
0x1800dc4f4  call    WPP_SF_d
0x1800dc4f9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800dc500  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800dc505  test    al, al
0x1800dc507  jz      short loc_1800DC520
0x1800dc509  mov     r9, rdi
0x1800dc50c  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800dc513  mov     r8d, 194Ah
0x1800dc519  mov     ecx, ebx
0x1800dc51b  call    TraceVpnWppErrorHRImpl
0x1800dc520  mov     eax, ebx
0x1800dc522  sar     eax, 10h
0x1800dc525  and     eax, 1FFFh
0x1800dc52a  cmp     eax, 7
0x1800dc52d  jnz     short loc_1800DC536
0x1800dc52f  movzx   ecx, bx
0x1800dc532  mov     edx, ecx
0x1800dc534  jmp     short loc_1800DC53B
0x1800dc536  mov     ecx, ebx
0x1800dc538  movzx   edx, bx
0x1800dc53b  test    ecx, ecx
0x1800dc53d  jz      short loc_1800DC55C
0x1800dc53f  cmp     eax, 7
0x1800dc542  cmovz   ebx, edx
0x1800dc545  lea     rdx, aVpnstringcopyF_7; "VpnStringCopy for Context.phonebookPath"
0x1800dc54c  mov     r8d, ebx
0x1800dc54f  mov     rcx, rdi
0x1800dc552  call    VpnReportError
0x1800dc557  jmp     loc_1800DC756
0x1800dc55c  lea     rdx, [r14+8]
0x1800dc560  mov     rcx, r12; Src
0x1800dc563  call    VpnStringCopy
0x1800dc568  mov     ebx, eax
0x1800dc56a  test    eax, eax
0x1800dc56c  jns     loc_1800DC5FB
0x1800dc572  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc579  lea     r12, WPP_GLOBAL_Control
0x1800dc580  cmp     rcx, r12
0x1800dc583  jz      short loc_1800DC5A3
0x1800dc585  test    byte ptr [rcx+1Ch], 1
0x1800dc589  jz      short loc_1800DC5A3
0x1800dc58b  mov     rcx, [rcx+10h]
0x1800dc58f  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800dc596  mov     edx, 295h
0x1800dc59b  mov     r9d, eax
0x1800dc59e  call    WPP_SF_d
0x1800dc5a3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800dc5aa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800dc5af  test    al, al
0x1800dc5b1  jz      short loc_1800DC5CA
0x1800dc5b3  mov     r9, rdi
0x1800dc5b6  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800dc5bd  mov     r8d, 194Eh
0x1800dc5c3  mov     ecx, ebx
0x1800dc5c5  call    TraceVpnWppErrorHRImpl
0x1800dc5ca  mov     eax, ebx
0x1800dc5cc  sar     eax, 10h
0x1800dc5cf  and     eax, 1FFFh
0x1800dc5d4  cmp     eax, 7
0x1800dc5d7  jnz     short loc_1800DC5E0
0x1800dc5d9  movzx   ecx, bx
0x1800dc5dc  mov     edx, ecx
0x1800dc5de  jmp     short loc_1800DC5E5
0x1800dc5e0  mov     ecx, ebx
0x1800dc5e2  movzx   edx, bx
0x1800dc5e5  test    ecx, ecx
0x1800dc5e7  jz      short loc_1800DC602
0x1800dc5e9  cmp     eax, 7
0x1800dc5ec  cmovz   ebx, edx
0x1800dc5ef  lea     rdx, aVpnstringcopyF_1; "VpnStringCopy for Context.entryName"
0x1800dc5f6  jmp     loc_1800DC54C
0x1800dc5fb  lea     r12, WPP_GLOBAL_Control
0x1800dc602  lea     rdx, [r14+10h]
0x1800dc606  mov     rcx, r13; Src
0x1800dc609  call    VpnStringCopy
0x1800dc60e  mov     ebx, eax
0x1800dc610  test    eax, eax
0x1800dc612  jns     loc_1800DC6C1
0x1800dc618  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc61f  cmp     rcx, r12
0x1800dc622  jz      short loc_1800DC642
0x1800dc624  test    byte ptr [rcx+1Ch], 1
0x1800dc628  jz      short loc_1800DC642
0x1800dc62a  mov     rcx, [rcx+10h]
0x1800dc62e  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800dc635  mov     edx, 296h
0x1800dc63a  mov     r9d, eax
0x1800dc63d  call    WPP_SF_d
0x1800dc642  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800dc649  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800dc64e  test    al, al
0x1800dc650  jz      short loc_1800DC669
0x1800dc652  mov     r9, rdi
0x1800dc655  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800dc65c  mov     r8d, 1952h
0x1800dc662  mov     ecx, ebx
0x1800dc664  call    TraceVpnWppErrorHRImpl
0x1800dc669  mov     eax, ebx
0x1800dc66b  sar     eax, 10h
0x1800dc66e  and     eax, 1FFFh
0x1800dc673  cmp     eax, 7
0x1800dc676  jnz     short loc_1800DC67F
0x1800dc678  movzx   ecx, bx
0x1800dc67b  mov     edx, ecx
0x1800dc67d  jmp     short loc_1800DC684
0x1800dc67f  mov     ecx, ebx
0x1800dc681  movzx   edx, bx
0x1800dc684  test    ecx, ecx
0x1800dc686  jz      short loc_1800DC6C1
0x1800dc688  cmp     eax, 7
0x1800dc68b  cmovz   ebx, edx
0x1800dc68e  lea     rdx, aVpnstringcopyF; "VpnStringCopy for Context.userSid"
0x1800dc695  jmp     loc_1800DC54C
0x1800dc69a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc6a1  cmp     rcx, rdi
0x1800dc6a4  jz      short loc_1800DC6C1
0x1800dc6a6  test    byte ptr [rcx+1Ch], 4
0x1800dc6aa  jz      short loc_1800DC6C1
0x1800dc6ac  mov     rcx, [rcx+10h]
0x1800dc6b0  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800dc6b7  mov     edx, 297h
0x1800dc6bc  call    WPP_SF_
0x1800dc6c1  mov     eax, [rsp+78h+arg_18]
0x1800dc6c8  lea     rcx, ?g_CsSetActiveProfileOperation@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_CsSetActiveProfileOperation
0x1800dc6cf  mov     [r14+18h], eax
0x1800dc6d3  mov     eax, [rsp+78h+arg_20]
0x1800dc6da  mov     [r14+1Ch], eax
0x1800dc6de  call    VpnCriticalSectionEnter
0x1800dc6e3  mov     rcx, cs:qword_18010E770
0x1800dc6ea  lea     rdx, ?g_RasSetActiveList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_RasSetActiveList
0x1800dc6f1  cmp     [rcx], rdx
0x1800dc6f4  jz      short loc_1800DC6FD
0x1800dc6f6  mov     ecx, 3
0x1800dc6fb  int     29h; Win8: RtlFailFast(ecx)
0x1800dc6fd  lea     rax, [r14+20h]
0x1800dc701  mov     [rax+8], rcx
0x1800dc705  mov     [rax], rdx
0x1800dc708  mov     [rcx], rax
0x1800dc70b  lea     rcx, ?g_CsSetActiveProfileOperation@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_CsSetActiveProfileOperation
0x1800dc712  mov     cs:qword_18010E770, rax
0x1800dc719  call    VpnCriticalSectionLeave
0x1800dc71e  lea     rcx, ?g_connMonitorCs@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_connMonitorCs
0x1800dc725  call    VpnCriticalSectionEnter
0x1800dc72a  mov     rdx, cs:?g_pMonitor@@3PEAU_CONNECTION_MONITOR@@EA; _CONNECTION_MONITOR * g_pMonitor
0x1800dc731  test    rdx, rdx
0x1800dc734  jz      short loc_1800DC749
0x1800dc736  lea     rcx, ?g_connMonitorCs@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_connMonitorCs
0x1800dc73d  mov     dword ptr [rdx+14h], 1
0x1800dc744  call    VpnCriticalSectionLeave
0x1800dc749  mov     rcx, cs:?g_pSetActiveProfileWorkItem@@3PEAU_TP_WORK@@EA; pwk
0x1800dc750  call    cs:__imp_SubmitThreadpoolWork
0x1800dc756  mov     eax, esi
0x1800dc758  add     rsp, 48h
0x1800dc75c  pop     r14
0x1800dc75e  pop     r13
0x1800dc760  pop     r12
0x1800dc762  pop     rdi
0x1800dc763  pop     rsi
0x1800dc764  pop     rbx
0x1800dc765  retn
```
