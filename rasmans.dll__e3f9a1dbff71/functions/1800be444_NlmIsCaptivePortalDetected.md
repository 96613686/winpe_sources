# NlmIsCaptivePortalDetected

- ea: `0x1800be444`
- end: `0x1800be8a5`
- name: `NlmIsCaptivePortalDetected`
- size: `1121`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b2e60`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x1800b81fc`
- `0x1800be444`
- `0x1800e2d24`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800be538`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800be538`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800be49c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800be49c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800be807`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800be807`
- `OLEAUT32!__imp_VariantInit` at `0x1800be662`
- `OLEAUT32!__imp_VariantInit` at `0x1800be68a`
- `OLEAUT32!__imp_VariantInit` at `0x1800be662`
- `OLEAUT32!__imp_VariantInit` at `0x1800be68a`
- `OLEAUT32!__imp_VariantClear` at `0x1800be6be`
- `OLEAUT32!__imp_VariantClear` at `0x1800be6c8`
- `OLEAUT32!__imp_VariantClear` at `0x1800be718`
- `OLEAUT32!__imp_VariantClear` at `0x1800be722`
- `OLEAUT32!__imp_VariantClear` at `0x1800be6be`
- `OLEAUT32!__imp_VariantClear` at `0x1800be6c8`
- `OLEAUT32!__imp_VariantClear` at `0x1800be718`
- `OLEAUT32!__imp_VariantClear` at `0x1800be722`

## string_xrefs

- `0x1800be4ef`: `onecoreuap\net\netio\vpnplugin\profilemgmt\nlm_handler.cpp`
- `0x1800be58d`: `onecoreuap\net\netio\vpnplugin\profilemgmt\nlm_handler.cpp`
- `0x1800be78d`: `onecoreuap\net\netio\vpnplugin\profilemgmt\nlm_handler.cpp`
- `0x1800be7e0`: `onecoreuap\net\netio\vpnplugin\profilemgmt\nlm_handler.cpp`
- `0x1800be854`: `onecoreuap\net\netio\vpnplugin\profilemgmt\nlm_handler.cpp`

## pseudocode

```c
__int64 __fastcall NlmIsCaptivePortalDetected(_DWORD *a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  LPVOID v4; // rcx
  HRESULT v5; // eax
  __int64 v6; // r8
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rcx
  __int64 (__fastcall ***v11)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v12; // rcx
  __int64 (__fastcall ***v13)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v14; // rcx
  LPVOID v15; // rcx
  __int64 v17; // [rsp+30h] [rbp-48h] BYREF
  VARIANTARG v18; // [rsp+38h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-28h] BYREF
  int v20; // [rsp+B0h] [rbp+38h] BYREF
  __int64 (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // [rsp+B8h] [rbp+40h] BYREF
  __int64 v22; // [rsp+C0h] [rbp+48h] BYREF
  LPVOID ppv; // [rsp+C8h] [rbp+50h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 203, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids);
  ppv = 0;
  v17 = 0;
  *a1 = 0;
  v2 = CoInitializeEx(0, 0);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v4 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
    }
    v5 = CoCreateInstance(
           &GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b,
           0,
           1u,
           &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b,
           &ppv);
    v3 = v5;
    if ( v5 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, 1, &v17);
      v3 = v7;
      if ( v7 >= 0 )
      {
        while ( 1 )
        {
          v20 = 0;
          v21 = 0;
          v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v17 + 64LL))(
                 v17,
                 1,
                 &v21,
                 &v20);
          v3 = v8;
          if ( v8 < 0 )
            break;
          if ( !v8 )
          {
            v22 = 0;
            v9 = (**v21)(v21, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, &v22);
            v3 = v9;
            if ( v9 < 0 )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control[1].Flink,
                  208,
                  &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids,
                  (unsigned int)v9);
              }
              if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
                TraceVpnWppErrorHRImpl(
                  v3,
                  L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\nlm_handler.cpp",
                  2340,
                  "NlmIsCaptivePortalDetected");
              goto LABEL_37;
            }
            VariantInit(&pvarg);
            (*(void (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v22 + 24LL))(
              v22,
              L"NA_InternetConnectivityV4",
              &pvarg,
              0);
            VariantInit(&v18);
            (*(void (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v22 + 24LL))(
              v22,
              L"NA_InternetConnectivityV6",
              &v18,
              0);
            if ( (pvarg.bVal & 1) != 0 || (v18.bVal & 1) != 0 )
            {
              *a1 = 1;
              VariantClear(&v18);
              VariantClear(&pvarg);
LABEL_37:
              v12 = v22;
              if ( v22 )
              {
                v22 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
              }
              goto LABEL_49;
            }
            VariantClear(&v18);
            VariantClear(&pvarg);
            v10 = v22;
            if ( v22 )
            {
              v22 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
            }
          }
          v11 = v21;
          if ( v21 )
          {
            v21 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v11)[2])(v11);
          }
          if ( v3 )
            goto LABEL_51;
        }
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 207, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, (unsigned int)v8);
        }
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorHRImpl(
            v3,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\nlm_handler.cpp",
            2330,
            "NlmIsCaptivePortalDetected");
LABEL_49:
        v13 = v21;
        if ( v21 )
        {
          v21 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v13)[2])(v13);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 206, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, (unsigned int)v7);
        }
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        {
          v6 = 2318;
          goto LABEL_18;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 205, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, (unsigned int)v5);
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      {
        v6 = 2309;
LABEL_18:
        TraceVpnWppErrorHRImpl(
          v3,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\nlm_handler.cpp",
          v6,
          "NlmIsCaptivePortalDetected");
      }
    }
LABEL_51:
    CoUninitialize();
    if ( (v3 & 0x80000000) == 0 )
      goto LABEL_57;
    goto LABEL_52;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 204, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, (unsigned int)v2);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    TraceVpnWppErrorHRImpl(
      v3,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\nlm_handler.cpp",
      2296,
      "NlmIsCaptivePortalDetected");
LABEL_52:
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 209, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v3);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    TraceVpnWppErrorHRImpl(
      v3,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\nlm_handler.cpp",
      2367,
      "NlmIsCaptivePortalDetected");
LABEL_57:
  v14 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return v3;
}

```

## disassembly

```asm
0x1800be444  push    rbp
0x1800be446  push    rbx
0x1800be447  push    r12
0x1800be449  push    r13
0x1800be44b  push    r14
0x1800be44d  push    r15
0x1800be44f  mov     rbp, rsp
0x1800be452  sub     rsp, 78h
0x1800be456  mov     r14, rcx
0x1800be459  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be460  lea     r12, WPP_GLOBAL_Control
0x1800be467  lea     r13, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800be46e  cmp     rcx, r12
0x1800be471  jz      short loc_1800BE48A
0x1800be473  test    byte ptr [rcx+1Ch], 8
0x1800be477  jz      short loc_1800BE48A
0x1800be479  mov     rcx, [rcx+10h]
0x1800be47d  mov     edx, 0CBh
0x1800be482  mov     r8, r13
0x1800be485  call    WPP_SF_
0x1800be48a  xor     r15d, r15d
0x1800be48d  xor     edx, edx; dwCoInit
0x1800be48f  xor     ecx, ecx; pvReserved
0x1800be491  mov     [rbp+arg_18], r15
0x1800be495  mov     [rbp+var_48], r15
0x1800be499  mov     [r14], r15d
0x1800be49c  call    cs:__imp_CoInitializeEx
0x1800be4a2  mov     ebx, eax
0x1800be4a4  test    eax, eax
0x1800be4a6  jns     short loc_1800BE502
0x1800be4a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be4af  cmp     rcx, r12
0x1800be4b2  jz      short loc_1800BE4CE
0x1800be4b4  test    byte ptr [rcx+1Ch], 1
0x1800be4b8  jz      short loc_1800BE4CE
0x1800be4ba  mov     rcx, [rcx+10h]
0x1800be4be  mov     edx, 0CCh
0x1800be4c3  mov     r9d, eax
0x1800be4c6  mov     r8, r13
0x1800be4c9  call    WPP_SF_d
0x1800be4ce  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800be4d5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800be4da  test    al, al
0x1800be4dc  jz      loc_1800BE811
0x1800be4e2  lea     r9, aNlmiscaptivepo; "NlmIsCaptivePortalDetected"
0x1800be4e9  mov     r8d, 8F8h
0x1800be4ef  lea     rdx, aOnecoreuapNetN; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800be4f6  mov     ecx, ebx
0x1800be4f8  call    TraceVpnWppErrorHRImpl
0x1800be4fd  jmp     loc_1800BE811
0x1800be502  mov     rcx, [rbp+arg_18]
0x1800be506  test    rcx, rcx
0x1800be509  jz      short loc_1800BE51B
0x1800be50b  mov     [rbp+arg_18], r15
0x1800be50f  mov     rax, [rcx]
0x1800be512  mov     rax, [rax+10h]
0x1800be516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be51b  xor     edx, edx; pUnkOuter
0x1800be51d  lea     rax, [rbp+arg_18]
0x1800be521  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x1800be528  mov     [rsp+78h+ppv], rax; ppv
0x1800be52d  lea     rcx, _GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b; rclsid
0x1800be534  lea     r8d, [rdx+1]; dwClsContext
0x1800be538  call    cs:__imp_CoCreateInstance
0x1800be53e  mov     ebx, eax
0x1800be540  test    eax, eax
0x1800be542  jns     short loc_1800BE59E
0x1800be544  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be54b  cmp     rcx, r12
0x1800be54e  jz      short loc_1800BE56A
0x1800be550  test    byte ptr [rcx+1Ch], 1
0x1800be554  jz      short loc_1800BE56A
0x1800be556  mov     rcx, [rcx+10h]
0x1800be55a  mov     edx, 0CDh
0x1800be55f  mov     r9d, eax
0x1800be562  mov     r8, r13
0x1800be565  call    WPP_SF_d
0x1800be56a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800be571  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800be576  test    al, al
0x1800be578  jz      loc_1800BE807
0x1800be57e  mov     r8d, 905h
0x1800be584  lea     r9, aNlmiscaptivepo; "NlmIsCaptivePortalDetected"
0x1800be58b  mov     ecx, ebx
0x1800be58d  lea     rdx, aOnecoreuapNetN; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800be594  call    TraceVpnWppErrorHRImpl
0x1800be599  jmp     loc_1800BE807
0x1800be59e  mov     rcx, [rbp+arg_18]
0x1800be5a2  lea     r8, [rbp+var_48]
0x1800be5a6  mov     edx, 1
0x1800be5ab  mov     rax, [rcx]
0x1800be5ae  mov     rax, [rax+38h]
0x1800be5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be5b7  mov     ebx, eax
0x1800be5b9  test    eax, eax
0x1800be5bb  jns     short loc_1800BE5FF
0x1800be5bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be5c4  cmp     rcx, r12
0x1800be5c7  jz      short loc_1800BE5E3
0x1800be5c9  test    byte ptr [rcx+1Ch], 1
0x1800be5cd  jz      short loc_1800BE5E3
0x1800be5cf  mov     rcx, [rcx+10h]
0x1800be5d3  mov     edx, 0CEh
0x1800be5d8  mov     r9d, eax
0x1800be5db  mov     r8, r13
0x1800be5de  call    WPP_SF_d
0x1800be5e3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800be5ea  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800be5ef  test    al, al
0x1800be5f1  jz      loc_1800BE807
0x1800be5f7  mov     r8d, 90Eh
0x1800be5fd  jmp     short loc_1800BE584
0x1800be5ff  mov     rcx, [rbp+var_48]
0x1800be603  lea     r9, [rbp+arg_0]
0x1800be607  mov     [rbp+arg_0], r15d
0x1800be60b  lea     r8, [rbp+arg_8]
0x1800be60f  mov     [rbp+arg_8], r15
0x1800be613  mov     edx, 1
0x1800be618  mov     rax, [rcx]
0x1800be61b  mov     rax, [rax+40h]
0x1800be61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be624  mov     ebx, eax
0x1800be626  test    eax, eax
0x1800be628  js      loc_1800BE79D
0x1800be62e  test    eax, eax
0x1800be630  jnz     loc_1800BE6E7
0x1800be636  mov     rcx, [rbp+arg_8]
0x1800be63a  lea     r8, [rbp+arg_10]
0x1800be63e  mov     [rbp+arg_10], r15
0x1800be642  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x1800be649  mov     rax, [rcx]
0x1800be64c  mov     rax, [rax]
0x1800be64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be654  mov     ebx, eax
0x1800be656  test    eax, eax
0x1800be658  js      loc_1800BE74A
0x1800be65e  lea     rcx, [rbp+pvarg]; pvarg
0x1800be662  call    cs:__imp_VariantInit
0x1800be668  mov     rcx, [rbp+arg_10]
0x1800be66c  lea     r8, [rbp+pvarg]
0x1800be670  xor     r9d, r9d
0x1800be673  lea     rdx, aNaInternetconn_0; "NA_InternetConnectivityV4"
0x1800be67a  mov     rax, [rcx]
0x1800be67d  mov     rax, [rax+18h]
0x1800be681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be686  lea     rcx, [rbp+var_40]; pvarg
0x1800be68a  call    cs:__imp_VariantInit
0x1800be690  mov     rcx, [rbp+arg_10]
0x1800be694  lea     r8, [rbp+var_40]
0x1800be698  xor     r9d, r9d
0x1800be69b  lea     rdx, aNaInternetconn; "NA_InternetConnectivityV6"
0x1800be6a2  mov     rax, [rcx]
0x1800be6a5  mov     rax, [rax+18h]
0x1800be6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be6ae  test    byte ptr [rbp+pvarg+8], 1
0x1800be6b2  jnz     short loc_1800BE70D
0x1800be6b4  test    byte ptr [rbp+var_40+8], 1
0x1800be6b8  jnz     short loc_1800BE70D
0x1800be6ba  lea     rcx, [rbp+var_40]; pvarg
0x1800be6be  call    cs:__imp_VariantClear
0x1800be6c4  lea     rcx, [rbp+pvarg]; pvarg
0x1800be6c8  call    cs:__imp_VariantClear
0x1800be6ce  mov     rcx, [rbp+arg_10]
0x1800be6d2  test    rcx, rcx
0x1800be6d5  jz      short loc_1800BE6E7
0x1800be6d7  mov     [rbp+arg_10], r15
0x1800be6db  mov     rax, [rcx]
0x1800be6de  mov     rax, [rax+10h]
0x1800be6e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be6e7  mov     rcx, [rbp+arg_8]
0x1800be6eb  test    rcx, rcx
0x1800be6ee  jz      short loc_1800BE700
0x1800be6f0  mov     [rbp+arg_8], r15
0x1800be6f4  mov     rax, [rcx]
0x1800be6f7  mov     rax, [rax+10h]
0x1800be6fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be700  test    ebx, ebx
0x1800be702  jz      loc_1800BE5FF
0x1800be708  jmp     loc_1800BE807
0x1800be70d  lea     rcx, [rbp+var_40]; pvarg
0x1800be711  mov     dword ptr [r14], 1
0x1800be718  call    cs:__imp_VariantClear
0x1800be71e  lea     rcx, [rbp+pvarg]; pvarg
0x1800be722  call    cs:__imp_VariantClear
0x1800be728  mov     rcx, [rbp+arg_10]
0x1800be72c  test    rcx, rcx
0x1800be72f  jz      loc_1800BE7EE
0x1800be735  mov     [rbp+arg_10], r15
0x1800be739  mov     rax, [rcx]
0x1800be73c  mov     rax, [rax+10h]
0x1800be740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be745  jmp     loc_1800BE7EE
0x1800be74a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be751  cmp     rcx, r12
0x1800be754  jz      short loc_1800BE770
0x1800be756  test    byte ptr [rcx+1Ch], 1
0x1800be75a  jz      short loc_1800BE770
0x1800be75c  mov     rcx, [rcx+10h]
0x1800be760  mov     edx, 0D0h
0x1800be765  mov     r9d, ebx
0x1800be768  mov     r8, r13
0x1800be76b  call    WPP_SF_d
0x1800be770  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800be777  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800be77c  test    al, al
0x1800be77e  jz      short loc_1800BE728
0x1800be780  lea     r9, aNlmiscaptivepo; "NlmIsCaptivePortalDetected"
0x1800be787  mov     r8d, 924h
0x1800be78d  lea     rdx, aOnecoreuapNetN; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800be794  mov     ecx, ebx
0x1800be796  call    TraceVpnWppErrorHRImpl
0x1800be79b  jmp     short loc_1800BE728
0x1800be79d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be7a4  cmp     rcx, r12
0x1800be7a7  jz      short loc_1800BE7C3
0x1800be7a9  test    byte ptr [rcx+1Ch], 1
0x1800be7ad  jz      short loc_1800BE7C3
0x1800be7af  mov     rcx, [rcx+10h]
0x1800be7b3  mov     edx, 0CFh
0x1800be7b8  mov     r9d, ebx
0x1800be7bb  mov     r8, r13
0x1800be7be  call    WPP_SF_d
0x1800be7c3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800be7ca  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800be7cf  test    al, al
0x1800be7d1  jz      short loc_1800BE7EE
0x1800be7d3  lea     r9, aNlmiscaptivepo; "NlmIsCaptivePortalDetected"
0x1800be7da  mov     r8d, 91Ah
0x1800be7e0  lea     rdx, aOnecoreuapNetN; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800be7e7  mov     ecx, ebx
0x1800be7e9  call    TraceVpnWppErrorHRImpl
0x1800be7ee  mov     rcx, [rbp+arg_8]
0x1800be7f2  test    rcx, rcx
0x1800be7f5  jz      short loc_1800BE807
0x1800be7f7  mov     [rbp+arg_8], r15
0x1800be7fb  mov     rax, [rcx]
0x1800be7fe  mov     rax, [rax+10h]
0x1800be802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be807  call    cs:__imp_CoUninitialize
0x1800be80d  test    ebx, ebx
0x1800be80f  jns     short loc_1800BE862
0x1800be811  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be818  cmp     rcx, r12
0x1800be81b  jz      short loc_1800BE837
0x1800be81d  test    byte ptr [rcx+1Ch], 8
0x1800be821  jz      short loc_1800BE837
0x1800be823  mov     rcx, [rcx+10h]
0x1800be827  mov     edx, 0D1h
0x1800be82c  mov     r9d, ebx
0x1800be82f  mov     r8, r13
0x1800be832  call    WPP_SF_d
0x1800be837  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800be83e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800be843  test    al, al
0x1800be845  jz      short loc_1800BE862
0x1800be847  lea     r9, aNlmiscaptivepo; "NlmIsCaptivePortalDetected"
0x1800be84e  mov     r8d, 93Fh
0x1800be854  lea     rdx, aOnecoreuapNetN; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800be85b  mov     ecx, ebx
0x1800be85d  call    TraceVpnWppErrorHRImpl
0x1800be862  mov     rcx, [rbp+var_48]
0x1800be866  test    rcx, rcx
0x1800be869  jz      short loc_1800BE87B
0x1800be86b  mov     [rbp+var_48], r15
0x1800be86f  mov     rax, [rcx]
0x1800be872  mov     rax, [rax+10h]
0x1800be876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be87b  mov     rcx, [rbp+arg_18]
0x1800be87f  test    rcx, rcx
0x1800be882  jz      short loc_1800BE894
0x1800be884  mov     [rbp+arg_18], r15
0x1800be888  mov     rax, [rcx]
0x1800be88b  mov     rax, [rax+10h]
0x1800be88f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be894  mov     eax, ebx
0x1800be896  add     rsp, 78h
0x1800be89a  pop     r15
0x1800be89c  pop     r14
0x1800be89e  pop     r13
0x1800be8a0  pop     r12
0x1800be8a2  pop     rbx
0x1800be8a3  pop     rbp
0x1800be8a4  retn
```
