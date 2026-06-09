# DynVCPluginLoader::InitPluginConfigurations(IWTSVirtualChannelConfig *)

- ea: `0x1801b9840`
- end: `0x1801ba73a`
- name: `?InitPluginConfigurations@DynVCPluginLoader@@UEAAJPEAVIWTSVirtualChannelConfig@@@Z`
- size: `3834`
- prototype: `__int64 __fastcall(DynVCPluginLoader *__hidden this, struct IWTSVirtualChannelConfig *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800186a0`
- `0x1800186d0`
- `0x18001e0d8`
- `0x18001e170`
- `0x18002a334`
- `0x18002a374`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x180109a50`
- `0x180112d30`
- `0x18012962c`
- `0x1801b866c`
- `0x1801b9840`
- `0x1801bc98c`
- `0x1801bc9c8`
- `0x1801c0318`
- `0x180234e98`
- `0x1802e648c`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1801b9b52`
- `OLEAUT32!__imp_VariantInit` at `0x1801b9bf9`
- `OLEAUT32!__imp_VariantInit` at `0x1801ba44a`
- `OLEAUT32!__imp_VariantInit` at `0x1801b9b52`
- `OLEAUT32!__imp_VariantInit` at `0x1801b9bf9`
- `OLEAUT32!__imp_VariantInit` at `0x1801ba44a`
- `OLEAUT32!__imp_VariantClear` at `0x1801b9bde`
- `OLEAUT32!__imp_VariantClear` at `0x1801b9bee`
- `OLEAUT32!__imp_VariantClear` at `0x1801b9c80`
- `OLEAUT32!__imp_VariantClear` at `0x1801b9c90`
- `OLEAUT32!__imp_VariantClear` at `0x1801ba4cf`
- `OLEAUT32!__imp_VariantClear` at `0x1801ba4df`
- `OLEAUT32!__imp_VariantClear` at `0x1801b9bde`
- `OLEAUT32!__imp_VariantClear` at `0x1801b9bee`
- `OLEAUT32!__imp_VariantClear` at `0x1801b9c80`
- `OLEAUT32!__imp_VariantClear` at `0x1801b9c90`
- `OLEAUT32!__imp_VariantClear` at `0x1801ba4cf`
- `OLEAUT32!__imp_VariantClear` at `0x1801ba4df`

## string_xrefs

- `0x1801b98cf`: `pDynVcConfigures`
- `0x1801ba38a`: `RdpGfxClientPluginConfig_CreateInstance failed!`
- `0x1801b9b42`: `CreateBasicPropertyBag failed`
- `0x1801b9a7b`: `m_spRdpDrConfig`
- `0x1801b9bb3`: `IPropertyBag::Write (Win32CoreApiPtr) failed`
- `0x1801ba4a4`: `IPropertyBag::Write (Win32CoreApiPtr) failed`
- `0x1801b9c55`: `IPropertyBag::Write (TSCoreApiPtr) failed`
- `0x1801b9d12`: `SetConfiguration failed for 'Microsoft::Windows::RDS::RAILV2'`
- `0x1801b9df8`: `SetConfiguration failed for 'Microsoft::Windows::RDS::RAIL'`
- `0x1801b9eb7`: `Failed to initialize PNP config`
- `0x1801ba074`: `SetConfiguration failed for BasicInput`
- `0x1801ba0d4`: `SetConfiguration failed for 'Microsoft::Windows::RDS::MouseCursor'`
- `0x1801ba13d`: `SetConfiguration failed for TSMM_VIDEO_BITMAP_CONTROL_VC_NAME`
- `0x1801ba1a8`: `SetConfiguration failed for FRAME_BUFFER_VC_NAME`
- `0x1801ba213`: `SetConfiguration failed for TSGEOMETRY_CHANNEL_NAME`
- `0x1801ba286`: `SetConfiguration failed for AUTH_REDIRECTION_CHANNEL_NAME`
- `0x1801ba2df`: `SetConfiguration failed for RDPREMOTEAPPGFXREDIRECTION_CHANNEL_NAME`
- `0x1801ba338`: `SetConfiguration failed for RDPREMOTEAPPAUXREDIRECTION_CHANNEL_NAME`
- `0x1801ba4ed`: `Microsoft::Windows::RDS::MonitorConfiguration`
- `0x1801ba3e4`: `SetConfiguration(RDPDISPLAYCONTROL_CHANNEL_NAME) failed!`
- `0x1801ba534`: `SetConfiguration(RDP_MONITORCONFIG_CHANNEL_NAME) failed!`
- `0x1801ba58d`: `SetConfiguration (RDPNAMEDPIPE_CHANNEL_NAME) failed`
- `0x1801ba5e6`: `SetConfiguration (REMOTETOLOCAL_DVC_NAME) failed`
- `0x1801ba643`: `SetConfiguration (LOCALTOREMOTE_DVC_NAME) failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall DynVCPluginLoader::InitPluginConfigurations(
        struct ITSWin32CoreApi **this,
        struct IWTSVirtualChannelConfig *a2,
        __int64 a3)
{
  CRdpAudioClientPluginConfig *v5; // r13
  struct IPropertyBag *v6; // rbx
  struct ITSPropertySet *v7; // rdi
  int ActivityIdPrefix; // eax
  int v9; // edx
  const char *v10; // rcx
  int v11; // esi
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  int v15; // eax
  int v16; // edx
  const char *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rsi
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rsi
  __int64 v25; // r8
  __int64 *v26; // r15
  CPnpRdrConfig *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  int v41; // eax
  bool v42; // zf
  void (__fastcall *v43)(struct IWTSVirtualChannelConfig *, const char *, struct IPropertyBag *); // rax
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r8
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // r8
  CPnpRdrConfig *v53; // rax
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // r8
  CPnpRdrConfig *v57; // rsi
  struct ITSWin32CoreApi *v58; // rsi
  struct ITSInstance *v59; // rax
  struct ITSPropertySet *v60; // r8
  CPnpRdrConfig *v61; // rdi
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // r8
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // r8
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // r8
  char *v71; // r13
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // r8
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // r8
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // r8
  int v81; // eax
  __int64 v82; // rdx
  __int64 v83; // r8
  char v84; // si
  int v85; // eax
  int v86; // eax
  __int64 v87; // rdx
  __int64 v88; // r8
  char v89; // si
  int v90; // eax
  int v91; // eax
  __int64 v92; // rdx
  __int64 v93; // r8
  char v94; // si
  int v95; // eax
  __int64 v96; // rdx
  __int64 v97; // rcx
  __int64 v98; // r8
  __int64 v99; // rdx
  __int64 v100; // rcx
  __int64 v101; // r8
  __int64 v102; // rdx
  __int64 v103; // rcx
  const struct _GUID *v104; // r8
  __int64 v105; // rdx
  __int64 v106; // rcx
  __int64 v107; // r8
  __int64 v108; // rdx
  __int64 v109; // rcx
  __int64 v110; // r8
  __int64 v111; // rdx
  __int64 v112; // rcx
  __int64 v113; // r8
  __int64 v114; // rdx
  __int64 v115; // rcx
  __int64 v116; // r8
  int v117; // eax
  __int64 v118; // rdx
  __int64 v119; // rcx
  __int64 v120; // r8
  __int64 v121; // rdx
  __int64 v122; // rcx
  __int64 v123; // r8
  __int64 v124; // rdx
  __int64 v125; // rcx
  __int64 v126; // r8
  __int64 v127; // rdx
  __int64 v128; // rcx
  __int64 v129; // r8
  unsigned int v130; // eax
  __int64 v131; // rdx
  struct ITSCoreApi *v133; // [rsp+38h] [rbp-59h] BYREF
  struct IPropertyBag *v134; // [rsp+40h] [rbp-51h] BYREF
  CRdpAudioClientPluginConfig *v135; // [rsp+48h] [rbp-49h] BYREF
  CPnpRdrConfig *v136; // [rsp+50h] [rbp-41h] BYREF
  struct ITSCLX *v137; // [rsp+58h] [rbp-39h] BYREF
  __int64 v138; // [rsp+60h] [rbp-31h] BYREF
  void *v139; // [rsp+68h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-21h] BYREF
  CPnpRdrConfig *v141; // [rsp+88h] [rbp-9h]
  _QWORD v142[2]; // [rsp+90h] [rbp-1h] BYREF
  char v143[8]; // [rsp+A0h] [rbp+Fh] BYREF

  v142[1] = -2;
  v5 = 0;
  v139 = 0;
  v142[0] = 0;
  v136 = 0;
  v135 = 0;
  v6 = 0;
  v134 = 0;
  v133 = 0;
  v7 = 0;
  v138 = 0;
  v137 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(this, 0, a3);
    v9 = 16;
    v10 = "pDynVcConfigures";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
      ActivityIdPrefix,
      (__int64)v10);
LABEL_7:
    v11 = -2147467261;
    goto LABEL_185;
  }
  v11 = (*(__int64 (__fastcall **)(struct ITSWin32CoreApi *, struct ITSCoreApi **))(*(_QWORD *)this[5] + 64LL))(
          this[5],
          &v133);
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpX_GetActivityIdPrefix(v13, v12, v14);
      v16 = 17;
      v17 = "Failed to retrieve CoreAPI";
LABEL_13:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        (unsigned int)WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
        v15,
        (__int64)v17,
        v11);
      goto LABEL_185;
    }
    goto LABEL_185;
  }
  v11 = (*(__int64 (__fastcall **)(struct ITSCoreApi *, struct ITSCLX **))(*(_QWORD *)v133 + 152LL))(v133, &v137);
  if ( v11 >= 0 )
  {
    v21 = (*(__int64 (__fastcall **)(struct ITSWin32CoreApi *))(*(_QWORD *)this[5] + 56LL))(this[5]);
    if ( v21 )
    {
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v138);
      v7 = (struct ITSPropertySet *)v21;
      v138 = v21;
      TCntPtr<IPin>::SafeAddRef(&v138);
    }
    v24 = (*(__int64 (__fastcall **)(struct ITSWin32CoreApi *))(*(_QWORD *)this[5] + 256LL))(this[5]);
    v26 = (__int64 *)(this + 7);
    if ( (struct ITSWin32CoreApi *)v24 != this[7] )
    {
      TCntPtr<ITSViewerRecorder>::SafeRelease(this + 7);
      *v26 = v24;
      TCntPtr<IPin>::SafeAddRef(this + 7);
    }
    if ( !*v26 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_7;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(v23, v22, v25);
      v9 = 19;
      v10 = "m_spRdpDrConfig";
      goto LABEL_6;
    }
    v27 = (CPnpRdrConfig *)operator new(0x70u);
    v141 = v27;
    if ( v27 )
      v5 = CRdpAudioClientPluginConfig::CRdpAudioClientPluginConfig(v27, this[5], this[6], v133, v137);
    if ( v5 )
    {
      TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v135);
      v135 = v5;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v5 + 4) + 8LL))(*((_QWORD *)v5 + 4));
      CRdpAudioClientPluginConfig::PopulateConfig(v5);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl'::`2'::impl) )
      {
        v11 = CreateBasicPropertyBag(&v134);
        if ( v11 < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_185;
          }
          v15 = RdpX_GetActivityIdPrefix(v32, v31, v33);
          v16 = 21;
          goto LABEL_37;
        }
        VariantInit(&pvarg);
        pvarg.llVal = (LONGLONG)this[5];
        v6 = v134;
        v11 = ((__int64 (__fastcall *)(struct IPropertyBag *, const wchar_t *, VARIANTARG *))v134->lpVtbl->Write)(
                v134,
                L"Win32CoreApiPtr",
                &pvarg);
        if ( v11 < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v37 = RdpX_GetActivityIdPrefix(v35, v34, v36);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              22,
              (unsigned int)WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
              v37,
              (__int64)"IPropertyBag::Write (Win32CoreApiPtr) failed",
              v11);
          }
LABEL_153:
          VariantClear(&pvarg);
          goto LABEL_185;
        }
        VariantClear(&pvarg);
        VariantInit(&pvarg);
        pvarg.llVal = (LONGLONG)v133;
        v11 = ((__int64 (__fastcall *)(struct IPropertyBag *, const wchar_t *, VARIANTARG *))v6->lpVtbl->Write)(
                v6,
                L"TSCoreApiPtr",
                &pvarg);
        if ( v11 < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v41 = RdpX_GetActivityIdPrefix(v39, v38, v40);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              (unsigned int)WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
              v41,
              (__int64)"IPropertyBag::Write (TSCoreApiPtr) failed",
              v11);
          }
          goto LABEL_153;
        }
        VariantClear(&pvarg);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl'::`2'::impl) )
      {
        v42 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeprecateRailV1DVC>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeprecateRailV1DVC>::GetImpl'::`2'::impl) == 0;
        v43 = *(void (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, struct IPropertyBag *))(*(_QWORD *)a2 + 32LL);
        if ( v42 )
        {
          v43(a2, "Microsoft::Windows::RDS::RAIL", v6);
        }
        else
        {
          v11 = ((__int64 (__fastcall *)(struct IWTSVirtualChannelConfig *, const char *, struct IPropertyBag *))v43)(
                  a2,
                  "Microsoft::Windows::RDS::RAILV2",
                  v6);
          if ( v11 < 0 )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v15 = RdpX_GetActivityIdPrefix(v45, v44, v46);
              v16 = 25;
              v17 = "SetConfiguration failed for 'Microsoft::Windows::RDS::RAILV2'";
              goto LABEL_13;
            }
            goto LABEL_185;
          }
        }
      }
      else
      {
        v11 = (*(__int64 (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, __int64))(*(_QWORD *)a2 + 32LL))(
                a2,
                "Microsoft::Windows::RDS::RAIL",
                (__int64)v5 + 56);
        if ( v11 < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = RdpX_GetActivityIdPrefix(v51, v50, v52);
            v16 = 26;
            v17 = "SetConfiguration failed for 'Microsoft::Windows::RDS::RAIL'";
            goto LABEL_13;
          }
          goto LABEL_185;
        }
      }
      strcpy(v143, "XPSRD");
      v11 = (*(__int64 (__fastcall **)(struct IWTSVirtualChannelConfig *, char *, __int64))(*(_QWORD *)a2 + 32LL))(
              a2,
              v143,
              *v26);
      if ( v11 < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = RdpX_GetActivityIdPrefix(v48, v47, v49);
          v16 = 27;
          v17 = "Failed to register the properties for XPS";
          goto LABEL_13;
        }
        goto LABEL_185;
      }
      v53 = (CPnpRdrConfig *)operator new(0x70u);
      v141 = v53;
      if ( v53 )
      {
        v57 = CPnpRdrConfig::CPnpRdrConfig(v53);
        v141 = v57;
        if ( v57 )
        {
          TCntPtr<CTSClientPrintTicket>::SafeRelease(&v136);
          v136 = v57;
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v57 + 5) + 8LL))(*((_QWORD *)v57 + 5));
          v58 = this[5];
          v59 = (struct ITSInstance *)(*(__int64 (__fastcall **)(struct ITSWin32CoreApi *))(*(_QWORD *)v58 + 88LL))(v58);
          v60 = v7;
          v61 = v141;
          v11 = CPnpRdrConfig::Initialize(v141, v59, v60, v58);
          if ( v11 < 0 )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v15 = RdpX_GetActivityIdPrefix(v63, v62, v64);
              v16 = 29;
              v17 = "Failed to initialize PNP config";
              goto LABEL_13;
            }
            goto LABEL_185;
          }
          v11 = (*(__int64 (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, CPnpRdrConfig *))(*(_QWORD *)a2 + 32LL))(
                  a2,
                  "PNPDR",
                  v61);
          if ( v11 >= 0 )
          {
            v11 = (*(__int64 (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, CPnpRdrConfig *))(*(_QWORD *)a2 + 32LL))(
                    a2,
                    "URBDRC",
                    v61);
            if ( v11 >= 0 )
            {
              TCntPtr<CTSClientPrintTicket>::SafeRelease(&v136);
              v136 = 0;
              v71 = (char *)v5 + 56;
              v11 = (*(__int64 (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, char *))(*(_QWORD *)a2 + 32LL))(
                      a2,
                      "RDPAUDIO_DEVICE_ENUMERATOR",
                      v71);
              if ( v11 < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v15 = RdpX_GetActivityIdPrefix(v73, v72, v74);
                  v16 = 32;
                  v17 = "Failed to register the properties for [RDP_AUDIO_DEVICE_ENUMERATOR]";
                  goto LABEL_13;
                }
                goto LABEL_185;
              }
              (*(void (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, __int64))(*(_QWORD *)a2 + 32LL))(
                a2,
                "AUDIO_INPUT",
                *v26);
              (*(void (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, __int64))(*(_QWORD *)a2 + 32LL))(
                a2,
                "TSMF",
                *v26);
              v11 = (*(__int64 (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, char *))(*(_QWORD *)a2 + 32LL))(
                      a2,
                      "Microsoft::Windows::RDS::CoreInput",
                      v71);
              if ( v11 < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v15 = RdpX_GetActivityIdPrefix(v76, v75, v77);
                  v16 = 33;
                  v17 = "SetConfiguration failed for BasicInput";
                  goto LABEL_13;
                }
                goto LABEL_185;
              }
              v11 = (*(__int64 (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, char *))(*(_QWORD *)a2 + 32LL))(
                      a2,
                      "Microsoft::Windows::RDS::MouseCursor",
                      v71);
              if ( v11 < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v15 = RdpX_GetActivityIdPrefix(v79, v78, v80);
                  v16 = 34;
                  v17 = "SetConfiguration failed for 'Microsoft::Windows::RDS::MouseCursor'";
                  goto LABEL_13;
                }
                goto LABEL_185;
              }
              TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v135);
              v135 = 0;
              v81 = (*(__int64 (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, __int64))(*(_QWORD *)a2 + 32LL))(
                      a2,
                      "Microsoft::Windows::RDS::Video::Control::v08.01",
                      *v26);
              v84 = v81;
              if ( v81 < 0
                && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v85 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v82, v83);
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  35,
                  (unsigned int)WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
                  v85,
                  (__int64)"SetConfiguration failed for TSMM_VIDEO_BITMAP_CONTROL_VC_NAME",
                  v84);
              }
              v86 = (*(__int64 (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, __int64))(*(_QWORD *)a2 + 32LL))(
                      a2,
                      "Microsoft::Windows::RDS::Frame_Buffer::Control::v08.01",
                      *v26);
              v89 = v86;
              if ( v86 < 0
                && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v90 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v87, v88);
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  36,
                  (unsigned int)WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
                  v90,
                  (__int64)"SetConfiguration failed for FRAME_BUFFER_VC_NAME",
                  v89);
              }
              v91 = (*(__int64 (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, __int64))(*(_QWORD *)a2 + 32LL))(
                      a2,
                      "Microsoft::Windows::RDS::Geometry::v08.01",
                      *v26);
              v94 = v91;
              if ( v91 < 0
                && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v95 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v92, v93);
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  37,
                  (unsigned int)WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
                  v95,
                  (__int64)"SetConfiguration failed for TSGEOMETRY_CHANNEL_NAME",
                  v94);
              }
              v11 = (*(__int64 (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, __int64))(*(_QWORD *)a2 + 32LL))(
                      a2,
                      "Microsoft::Windows::RDS::AuthRedirection",
                      *v26);
              if ( v11 < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v15 = RdpX_GetActivityIdPrefix(v97, v96, v98);
                  v16 = 38;
                  v17 = "SetConfiguration failed for AUTH_REDIRECTION_CHANNEL_NAME";
                  goto LABEL_13;
                }
                goto LABEL_185;
              }
              v11 = (*(__int64 (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, __int64))(*(_QWORD *)a2 + 32LL))(
                      a2,
                      "Microsoft::Windows::RDS::RemoteAppGraphicsRedirection",
                      *v26);
              if ( v11 < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v15 = RdpX_GetActivityIdPrefix(v100, v99, v101);
                  v16 = 39;
                  v17 = "SetConfiguration failed for RDPREMOTEAPPGFXREDIRECTION_CHANNEL_NAME";
                  goto LABEL_13;
                }
                goto LABEL_185;
              }
              v11 = (*(__int64 (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, __int64))(*(_QWORD *)a2 + 32LL))(
                      a2,
                      "Microsoft::Windows::RDS::RemoteAppAuxRedirection",
                      *v26);
              if ( v11 < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v15 = RdpX_GetActivityIdPrefix(v103, v102, v104);
                  v16 = 40;
                  v17 = "SetConfiguration failed for RDPREMOTEAPPAUXREDIRECTION_CHANNEL_NAME";
                  goto LABEL_13;
                }
                goto LABEL_185;
              }
              v11 = RdpGfxClientPluginConfig_CreateInstance(this[6], v137, v104, &v139);
              if ( v11 < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v15 = RdpX_GetActivityIdPrefix(v106, v105, v107);
                  v16 = 42;
                  v17 = "RdpGfxClientPluginConfig_CreateInstance failed!";
                  goto LABEL_13;
                }
                goto LABEL_185;
              }
              v11 = (*(__int64 (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, void *))(*(_QWORD *)a2 + 32LL))(
                      a2,
                      "Microsoft::Windows::RDS::DisplayControl",
                      v139);
              if ( v11 < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v15 = RdpX_GetActivityIdPrefix(v109, v108, v110);
                  v16 = 43;
                  v17 = "SetConfiguration(RDPDISPLAYCONTROL_CHANNEL_NAME) failed!";
                  goto LABEL_13;
                }
                goto LABEL_185;
              }
              if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl'::`2'::impl) )
              {
                v11 = CreateBasicPropertyBag(&v134);
                if ( v11 < 0 )
                {
                  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_185;
                  }
                  v15 = RdpX_GetActivityIdPrefix(v112, v111, v113);
                  v16 = 44;
LABEL_37:
                  v17 = "CreateBasicPropertyBag failed";
                  goto LABEL_13;
                }
                VariantInit(&pvarg);
                pvarg.llVal = (LONGLONG)this[5];
                v6 = v134;
                v11 = ((__int64 (__fastcall *)(struct IPropertyBag *, const wchar_t *, VARIANTARG *))v134->lpVtbl->Write)(
                        v134,
                        L"Win32CoreApiPtr",
                        &pvarg);
                if ( v11 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v117 = RdpX_GetActivityIdPrefix(v115, v114, v116);
                    WPP_SF_DsD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      45,
                      (unsigned int)WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids,
                      v117,
                      (__int64)"IPropertyBag::Write (Win32CoreApiPtr) failed",
                      v11);
                  }
                  goto LABEL_153;
                }
                VariantClear(&pvarg);
              }
              v11 = (*(__int64 (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, void *))(*(_QWORD *)a2 + 32LL))(
                      a2,
                      "Microsoft::Windows::RDS::MonitorConfiguration",
                      v139);
              if ( v11 >= 0 )
              {
                v11 = (*(__int64 (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, struct IPropertyBag *))(*(_QWORD *)a2 + 32LL))(
                        a2,
                        "Microsoft::Windows::RDS::NamedPipe",
                        v6);
                if ( v11 >= 0 )
                {
                  v11 = (*(__int64 (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, struct IPropertyBag *))(*(_QWORD *)a2 + 32LL))(
                          a2,
                          "TextInput_ServerToClientDVC",
                          v6);
                  if ( v11 >= 0 )
                  {
                    v11 = (*(__int64 (__fastcall **)(struct IWTSVirtualChannelConfig *, const char *, struct IPropertyBag *))(*(_QWORD *)a2 + 32LL))(
                            a2,
                            "TextInput_ClientToServerDVC",
                            v6);
                    if ( v11 < 0
                      && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v15 = RdpX_GetActivityIdPrefix(v128, v127, v129);
                      v16 = 49;
                      v17 = "SetConfiguration (LOCALTOREMOTE_DVC_NAME) failed";
                      goto LABEL_13;
                    }
                  }
                  else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                         && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v15 = RdpX_GetActivityIdPrefix(v125, v124, v126);
                    v16 = 48;
                    v17 = "SetConfiguration (REMOTETOLOCAL_DVC_NAME) failed";
                    goto LABEL_13;
                  }
                }
                else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                       && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v15 = RdpX_GetActivityIdPrefix(v122, v121, v123);
                  v16 = 47;
                  v17 = "SetConfiguration (RDPNAMEDPIPE_CHANNEL_NAME) failed";
                  goto LABEL_13;
                }
              }
              else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                     && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v15 = RdpX_GetActivityIdPrefix(v119, v118, v120);
                v16 = 46;
                v17 = "SetConfiguration(RDP_MONITORCONFIG_CHANNEL_NAME) failed!";
                goto LABEL_13;
              }
              goto LABEL_185;
            }
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_185;
            }
            v15 = RdpX_GetActivityIdPrefix(v69, v68, v70);
            v16 = 31;
          }
          else
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_185;
            }
            v15 = RdpX_GetActivityIdPrefix(v66, v65, v67);
            v16 = 30;
          }
          v17 = "Failed to register the properties for PNPDR";
          goto LABEL_13;
        }
      }
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_184:
        v11 = -2147024882;
        goto LABEL_185;
      }
      v130 = RdpX_GetActivityIdPrefix(v55, v54, v56);
      v131 = 28;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_184;
      }
      v130 = RdpX_GetActivityIdPrefix(v29, v28, v30);
      v131 = 20;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v131, WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids, v130);
    goto LABEL_184;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = RdpX_GetActivityIdPrefix(v19, v18, v20);
    v16 = 18;
    v17 = "Failed to retrieve CLX object";
    goto LABEL_13;
  }
LABEL_185:
  TCntPtr<ITSViewerRecorder>::SafeRelease(&v137);
  TCntPtr<ITSViewerRecorder>::SafeRelease(&v138);
  TCntPtr<ITSViewerRecorder>::SafeRelease(&v133);
  TCntPtr<ITSViewerRecorder>::SafeRelease(&v134);
  TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v135);
  TCntPtr<CTSClientPrintTicket>::SafeRelease(&v136);
  TCntPtr<ITSViewerRecorder>::SafeRelease(v142);
  TCntPtr<ITSViewerRecorder>::SafeRelease(&v139);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1801b9840  mov     rax, rsp
0x1801b9843  push    rbp
0x1801b9844  push    rsi
0x1801b9845  push    rdi
0x1801b9846  push    r12
0x1801b9848  push    r13
0x1801b984a  push    r14
0x1801b984c  push    r15
0x1801b984e  lea     rbp, [rax-5Fh]
0x1801b9852  sub     rsp, 0B0h
0x1801b9859  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x1801b9861  mov     [rax+18h], rbx
0x1801b9865  mov     rax, cs:__security_cookie
0x1801b986c  xor     rax, rsp
0x1801b986f  mov     [rbp+57h+var_40], rax
0x1801b9873  mov     r14, rdx
0x1801b9876  mov     r12, rcx
0x1801b9879  xor     r13d, r13d
0x1801b987c  mov     [rbp+57h+var_80], r13
0x1801b9880  mov     [rbp+57h+var_58], r13
0x1801b9884  mov     [rbp+57h+var_98], r13
0x1801b9888  mov     [rbp+57h+var_A0], r13
0x1801b988c  mov     ebx, r13d
0x1801b988f  mov     [rbp+57h+var_A8], rbx
0x1801b9893  mov     [rbp+57h+var_B0], r13
0x1801b9897  mov     edi, r13d
0x1801b989a  mov     [rbp+57h+var_88], r13
0x1801b989e  mov     [rbp+57h+var_90], r13
0x1801b98a2  test    rdx, rdx
0x1801b98a5  jnz     short loc_1801B98FF
0x1801b98a7  lea     rdi, WPP_GLOBAL_Control
0x1801b98ae  mov     rax, cs:WPP_GLOBAL_Control
0x1801b98b5  cmp     rax, rdi
0x1801b98b8  jz      short loc_1801B98F5
0x1801b98ba  test    byte ptr [rax+1Ch], 8
0x1801b98be  jz      short loc_1801B98F5
0x1801b98c0  cmp     byte ptr [rax+19h], 2
0x1801b98c4  jb      short loc_1801B98F5
0x1801b98c6  call    RdpX_GetActivityIdPrefix
0x1801b98cb  lea     edx, [r14+10h]
0x1801b98cf  lea     rcx, aPdynvcconfigur; "pDynVcConfigures"
0x1801b98d6  mov     [rsp+0E0h+var_C0], rcx
0x1801b98db  mov     r9d, eax
0x1801b98de  lea     r8, WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids
0x1801b98e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b98ec  mov     rcx, [rcx+10h]
0x1801b98f0  call    WPP_SF_Ds
0x1801b98f5  mov     esi, 80004003h
0x1801b98fa  jmp     loc_1801BA6C2
0x1801b98ff  mov     rcx, [rcx+28h]
0x1801b9903  mov     rax, [rcx]
0x1801b9906  lea     rdx, [rbp+57h+var_B0]
0x1801b990a  mov     rax, [rax+40h]
0x1801b990e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b9913  mov     esi, eax
0x1801b9915  test    eax, eax
0x1801b9917  jns     short loc_1801B997D
0x1801b9919  lea     rdi, WPP_GLOBAL_Control
0x1801b9920  mov     rax, cs:WPP_GLOBAL_Control
0x1801b9927  cmp     rax, rdi
0x1801b992a  jz      loc_1801BA6C2
0x1801b9930  test    byte ptr [rax+1Ch], 8
0x1801b9934  jz      loc_1801BA6C2
0x1801b993a  cmp     byte ptr [rax+19h], 2
0x1801b993e  jb      loc_1801BA6C2
0x1801b9944  call    RdpX_GetActivityIdPrefix
0x1801b9949  mov     edx, 11h
0x1801b994e  lea     rcx, aFailedToRetrie_0; "Failed to retrieve CoreAPI"
0x1801b9955  mov     [rsp+28h], esi
0x1801b9959  mov     [rsp+0E0h+var_C0], rcx
0x1801b995e  mov     r9d, eax
0x1801b9961  lea     r8, WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids
0x1801b9968  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b996f  mov     rcx, [rcx+10h]
0x1801b9973  call    WPP_SF_DsD
0x1801b9978  jmp     loc_1801BA6C2
0x1801b997d  mov     rcx, [rbp+57h+var_B0]
0x1801b9981  mov     rax, [rcx]
0x1801b9984  lea     rdx, [rbp+57h+var_90]
0x1801b9988  mov     rax, [rax+98h]
0x1801b998f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b9994  mov     esi, eax
0x1801b9996  test    eax, eax
0x1801b9998  jns     short loc_1801B99DB
0x1801b999a  lea     rdi, WPP_GLOBAL_Control
0x1801b99a1  mov     rax, cs:WPP_GLOBAL_Control
0x1801b99a8  cmp     rax, rdi
0x1801b99ab  jz      loc_1801BA6C2
0x1801b99b1  test    byte ptr [rax+1Ch], 8
0x1801b99b5  jz      loc_1801BA6C2
0x1801b99bb  cmp     byte ptr [rax+19h], 2
0x1801b99bf  jb      loc_1801BA6C2
0x1801b99c5  call    RdpX_GetActivityIdPrefix
0x1801b99ca  mov     edx, 12h
0x1801b99cf  lea     rcx, aFailedToRetrie_7; "Failed to retrieve CLX object"
0x1801b99d6  jmp     loc_1801B9955
0x1801b99db  mov     rcx, [r12+28h]
0x1801b99e0  mov     rax, [rcx]
0x1801b99e3  mov     rax, [rax+38h]
0x1801b99e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b99ec  mov     rsi, rax
0x1801b99ef  test    rax, rax
0x1801b99f2  jz      short loc_1801B9A0D
0x1801b99f4  lea     rcx, [rbp+57h+var_88]; void *
0x1801b99f8  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x1801b99fd  mov     rdi, rsi
0x1801b9a00  mov     [rbp+57h+var_88], rsi
0x1801b9a04  lea     rcx, [rbp+57h+var_88]
0x1801b9a08  call    ?SafeAddRef@?$TCntPtr@UIPin@@@@AEAAXXZ; TCntPtr<IPin>::SafeAddRef(void)
0x1801b9a0d  mov     rcx, [r12+28h]
0x1801b9a12  mov     rax, [rcx]
0x1801b9a15  mov     rax, [rax+100h]
0x1801b9a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b9a21  mov     rsi, rax
0x1801b9a24  lea     r15, [r12+38h]
0x1801b9a29  cmp     rax, [r15]
0x1801b9a2c  jz      short loc_1801B9A41
0x1801b9a2e  mov     rcx, r15; void *
0x1801b9a31  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x1801b9a36  mov     [r15], rsi
0x1801b9a39  mov     rcx, r15
0x1801b9a3c  call    ?SafeAddRef@?$TCntPtr@UIPin@@@@AEAAXXZ; TCntPtr<IPin>::SafeAddRef(void)
0x1801b9a41  cmp     [r15], r13
0x1801b9a44  jnz     short loc_1801B9A87
0x1801b9a46  lea     rdi, WPP_GLOBAL_Control
0x1801b9a4d  mov     rax, cs:WPP_GLOBAL_Control
0x1801b9a54  cmp     rax, rdi
0x1801b9a57  jz      loc_1801B98F5
0x1801b9a5d  test    byte ptr [rax+1Ch], 8
0x1801b9a61  jz      loc_1801B98F5
0x1801b9a67  cmp     byte ptr [rax+19h], 2
0x1801b9a6b  jb      loc_1801B98F5
0x1801b9a71  call    RdpX_GetActivityIdPrefix
0x1801b9a76  mov     edx, 13h
0x1801b9a7b  lea     rcx, aMSprdpdrconfig; "m_spRdpDrConfig"
0x1801b9a82  jmp     loc_1801B98D6
0x1801b9a87  mov     ecx, 70h ; 'p'; Size
0x1801b9a8c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801b9a91  mov     [rbp+57h+var_60], rax
0x1801b9a95  test    rax, rax
0x1801b9a98  jz      short loc_1801B9ABC
0x1801b9a9a  mov     rcx, [rbp+57h+var_90]
0x1801b9a9e  mov     [rsp+0E0h+var_C0], rcx; struct ITSCLX *
0x1801b9aa3  mov     r9, [rbp+57h+var_B0]; struct ITSCoreApi *
0x1801b9aa7  mov     r8, [r12+30h]; struct IRdpBaseCoreApi *
0x1801b9aac  mov     rdx, [r12+28h]; struct ITSWin32CoreApi *
0x1801b9ab1  mov     rcx, rax; this
0x1801b9ab4  call    ??0CRdpAudioClientPluginConfig@@QEAA@PEAVITSWin32CoreApi@@PEAVIRdpBaseCoreApi@@PEAVITSCoreApi@@PEAVITSCLX@@@Z; CRdpAudioClientPluginConfig::CRdpAudioClientPluginConfig(ITSWin32CoreApi *,IRdpBaseCoreApi *,ITSCoreApi *,ITSCLX *)
0x1801b9ab9  mov     r13, rax
0x1801b9abc  test    r13, r13
0x1801b9abf  jz      loc_1801BA67A
0x1801b9ac5  lea     rcx, [rbp+57h+var_A0]
0x1801b9ac9  call    ?SafeRelease@?$TCntPtr@V?$SlidingStats@N$04$00@@@@AEAAXXZ; TCntPtr<SlidingStats<double,5,1>>::SafeRelease(void)
0x1801b9ace  mov     [rbp+57h+var_A0], r13
0x1801b9ad2  mov     rcx, [r13+20h]
0x1801b9ad6  mov     rax, [rcx]
0x1801b9ad9  mov     rax, [rax+8]
0x1801b9add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b9ae2  mov     rcx, r13; this
0x1801b9ae5  call    ?PopulateConfig@CRdpAudioClientPluginConfig@@QEAAXXZ; CRdpAudioClientPluginConfig::PopulateConfig(void)
0x1801b9aea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableRailV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRailV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2> `wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl(void)'::`2'::impl
0x1801b9af1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRailV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2>::__private_IsEnabled(void)
0x1801b9af6  test    al, al
0x1801b9af8  jz      loc_1801B9C97
0x1801b9afe  lea     rcx, [rbp+57h+var_A8]; struct IPropertyBag **
0x1801b9b02  call    ?CreateBasicPropertyBag@@YAJPEAPEAUIPropertyBag@@@Z; CreateBasicPropertyBag(IPropertyBag * *)
0x1801b9b07  mov     esi, eax
0x1801b9b09  test    eax, eax
0x1801b9b0b  jns     short loc_1801B9B4E
0x1801b9b0d  lea     rdi, WPP_GLOBAL_Control
0x1801b9b14  mov     rax, cs:WPP_GLOBAL_Control
0x1801b9b1b  cmp     rax, rdi
0x1801b9b1e  jz      loc_1801BA6C2
0x1801b9b24  test    byte ptr [rax+1Ch], 8
0x1801b9b28  jz      loc_1801BA6C2
0x1801b9b2e  cmp     byte ptr [rax+19h], 2
0x1801b9b32  jb      loc_1801BA6C2
0x1801b9b38  call    RdpX_GetActivityIdPrefix
0x1801b9b3d  mov     edx, 15h
0x1801b9b42  lea     rcx, aCreatebasicpro; "CreateBasicPropertyBag failed"
0x1801b9b49  jmp     loc_1801B9955
0x1801b9b4e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1801b9b52  call    cs:__imp_VariantInit
0x1801b9b58  nop
0x1801b9b59  mov     rax, [r12+28h]
0x1801b9b5e  mov     qword ptr [rbp+57h+pvarg+8], rax
0x1801b9b62  mov     rbx, [rbp+57h+var_A8]
0x1801b9b66  mov     rax, [rbx]
0x1801b9b69  lea     r8, [rbp+57h+pvarg]
0x1801b9b6d  lea     rdx, aWin32coreapipt; "Win32CoreApiPtr"
0x1801b9b74  mov     rcx, rbx
0x1801b9b77  mov     rax, [rax+20h]
0x1801b9b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b9b80  mov     esi, eax
0x1801b9b82  test    eax, eax
0x1801b9b84  jns     short loc_1801B9BEA
0x1801b9b86  lea     rdi, WPP_GLOBAL_Control
0x1801b9b8d  mov     rax, cs:WPP_GLOBAL_Control
0x1801b9b94  cmp     rax, rdi
0x1801b9b97  jz      short loc_1801B9BDA
0x1801b9b99  test    byte ptr [rax+1Ch], 8
0x1801b9b9d  jz      short loc_1801B9BDA
0x1801b9b9f  cmp     byte ptr [rax+19h], 2
0x1801b9ba3  jb      short loc_1801B9BDA
0x1801b9ba5  call    RdpX_GetActivityIdPrefix
0x1801b9baa  mov     edx, 16h
0x1801b9baf  mov     [rsp+28h], esi
0x1801b9bb3  lea     rcx, aIpropertybagWr_0; "IPropertyBag::Write (Win32CoreApiPtr) f"...
0x1801b9bba  mov     [rsp+0E0h+var_C0], rcx
0x1801b9bbf  mov     r9d, eax
0x1801b9bc2  lea     r8, WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids
0x1801b9bc9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b9bd0  mov     rcx, [rcx+10h]
0x1801b9bd4  call    WPP_SF_DsD
0x1801b9bd9  nop
0x1801b9bda  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1801b9bde  call    cs:__imp_VariantClear
0x1801b9be4  nop
0x1801b9be5  jmp     loc_1801BA6C2
0x1801b9bea  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1801b9bee  call    cs:__imp_VariantClear
0x1801b9bf4  nop
0x1801b9bf5  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1801b9bf9  call    cs:__imp_VariantInit
0x1801b9bff  nop
0x1801b9c00  mov     rax, [rbp+57h+var_B0]
0x1801b9c04  mov     qword ptr [rbp+57h+pvarg+8], rax
0x1801b9c08  mov     rax, [rbx]
0x1801b9c0b  lea     r8, [rbp+57h+pvarg]
0x1801b9c0f  lea     rdx, aTscoreapiptr; "TSCoreApiPtr"
0x1801b9c16  mov     rcx, rbx
0x1801b9c19  mov     rax, [rax+20h]
0x1801b9c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b9c22  mov     esi, eax
0x1801b9c24  test    eax, eax
0x1801b9c26  jns     short loc_1801B9C8C
0x1801b9c28  lea     rdi, WPP_GLOBAL_Control
0x1801b9c2f  mov     rax, cs:WPP_GLOBAL_Control
0x1801b9c36  cmp     rax, rdi
0x1801b9c39  jz      short loc_1801B9C7C
0x1801b9c3b  test    byte ptr [rax+1Ch], 8
0x1801b9c3f  jz      short loc_1801B9C7C
0x1801b9c41  cmp     byte ptr [rax+19h], 2
0x1801b9c45  jb      short loc_1801B9C7C
0x1801b9c47  call    RdpX_GetActivityIdPrefix
0x1801b9c4c  mov     edx, 17h
0x1801b9c51  mov     [rsp+28h], esi
0x1801b9c55  lea     rcx, aIpropertybagWr; "IPropertyBag::Write (TSCoreApiPtr) fail"...
0x1801b9c5c  mov     [rsp+0E0h+var_C0], rcx
0x1801b9c61  mov     r9d, eax
0x1801b9c64  lea     r8, WPP_01c0a3dc71123b7c4b1c5d094544e0e1_Traceguids
0x1801b9c6b  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b9c72  mov     rcx, [rcx+10h]
0x1801b9c76  call    WPP_SF_DsD
0x1801b9c7b  nop
0x1801b9c7c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1801b9c80  call    cs:__imp_VariantClear
0x1801b9c86  nop
0x1801b9c87  jmp     loc_1801BA6C2
0x1801b9c8c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1801b9c90  call    cs:__imp_VariantClear
0x1801b9c96  nop
0x1801b9c97  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableRailV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRailV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2> `wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl(void)'::`2'::impl
0x1801b9c9e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRailV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2>::__private_IsEnabled(void)
0x1801b9ca3  test    al, al
0x1801b9ca5  jz      loc_1801B9D9F
0x1801b9cab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeprecateRailV1DVC@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeprecateRailV1DVC@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeprecateRailV1DVC> `wil::Feature<__WilFeatureTraits_Feature_DeprecateRailV1DVC>::GetImpl(void)'::`2'::impl
0x1801b9cb2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeprecateRailV1DVC@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeprecateRailV1DVC>::__private_IsEnabled(void)
0x1801b9cb7  mov     rcx, [r14]
0x1801b9cba  mov     r9, [rcx+20h]
0x1801b9cbe  mov     r8, rbx
0x1801b9cc1  mov     rcx, r14
0x1801b9cc4  test    al, al
0x1801b9cc6  mov     rax, r9
0x1801b9cc9  jz      short loc_1801B9D1E
0x1801b9ccb  lea     rdx, aMicrosoftWindo_1; "Microsoft::Windows::RDS::RAILV2"
0x1801b9cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b9cd7  mov     esi, eax
0x1801b9cd9  test    eax, eax
0x1801b9cdb  jns     short loc_1801B9D2A
0x1801b9cdd  lea     rdi, WPP_GLOBAL_Control
0x1801b9ce4  mov     rax, cs:WPP_GLOBAL_Control
0x1801b9ceb  cmp     rax, rdi
0x1801b9cee  jz      loc_1801BA6C2
0x1801b9cf4  test    byte ptr [rax+1Ch], 8
0x1801b9cf8  jz      loc_1801BA6C2
0x1801b9cfe  cmp     byte ptr [rax+19h], 2
0x1801b9d02  jb      loc_1801BA6C2
0x1801b9d08  call    RdpX_GetActivityIdPrefix
0x1801b9d0d  mov     edx, 19h
0x1801b9d12  lea     rcx, aSetconfigurati_17; "SetConfiguration failed for 'Microsoft:"...
0x1801b9d19  jmp     loc_1801B9955
0x1801b9d1e  lea     rdx, aMicrosoftWindo_14; "Microsoft::Windows::RDS::RAIL"
0x1801b9d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b9d2a  mov     eax, dword ptr cs:aXpsrd; "XPSRD"
0x1801b9d30  mov     dword ptr [rbp+57h+var_48], eax
0x1801b9d33  movzx   eax, word ptr cs:aXpsrd+4; "D"
0x1801b9d3a  mov     word ptr [rbp+57h+var_48+4], ax
0x1801b9d3e  mov     rax, [r14]
0x1801b9d41  mov     r8, [r15]
  ... truncated ...
```
