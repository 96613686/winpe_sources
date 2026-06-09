# InitializeGfxSettings(ulong,IRDPCollection * *)

- ea: `0x18006233c`
- end: `0x180063091`
- name: `?InitializeGfxSettings@@YAJKPEAPEAUIRDPCollection@@@Z`
- size: `3413`
- prototype: `__int64 __fastcall(unsigned int, struct IRDPCollection **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004ae90`

## callees

- `0x180003838`
- `0x180003958`
- `0x1800071c0`
- `0x1800091a8`
- `0x18000db60`
- `0x18000e458`
- `0x180011838`
- `0x180017220`
- `0x18001e49c`
- `0x18002e600`
- `0x180032f60`
- `0x180033da0`
- `0x18006233c`
- `0x180063124`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800623fd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800623fd`
- `ntdll!NtQuerySystemInformation` at `0x180062421`
- `ntdll!NtQuerySystemInformation` at `0x180062421`
- `OLEAUT32!__imp_VariantInit` at `0x180062f31`
- `OLEAUT32!__imp_VariantInit` at `0x180062f31`
- `OLEAUT32!__imp_VariantClear` at `0x180063021`
- `OLEAUT32!__imp_VariantClear` at `0x180063021`

## string_xrefs

- `0x180062516`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x18006250a`: `MaxCompressionLevel`
- `0x1800623ce`: `CRDPCollection::CreateInstance failed!`
- `0x180062499`: `Failed to read the recording property`
- `0x180062573`: `Failed to read the compression level policy`
- `0x1800625e8`: `Failed to read the AVC444 mode preferred policy`
- `0x1800626cf`: `Failed to read the AVCMM mode preferred policy`
- `0x180062748`: `Failed to read the In-driver encoding preferred policy`
- `0x180062887`: `Failed to read the HEVC mode preferred policy`
- `0x180062afd`: `Failed to read the AVC444 HW mode preferred policy`
- `0x180062b71`: `Failed to read the graphics profile policy`
- `0x180062be9`: `Failed to read the image quality policy`
- `0x180062c63`: `GfxPipeline::RemoteFXCompressionEnabled`
- `0x180062cc4`: `Failed to read the remotefx compression policy`
- `0x180062cd4`: `RCM::Services::Graphics::RemoteFXTestMode`
- `0x180062d35`: `Failed to read the remotefx test setting`
- `0x180062daa`: `Failed to read the target frame interval setting`

## pseudocode

```c
__int64 __fastcall InitializeGfxSettings(const struct _GUID *a1, struct IRDPCollection **a2)
{
  unsigned int v2; // r14d
  PVOID v3; // rdx
  int Instance; // ebx
  __int64 v5; // r8
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  struct _GUID *CurrentActivityId; // rax
  struct _GUID v10; // xmm0
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  struct _GUID v14; // xmm0
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  struct _GUID v18; // xmm0
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v22; // r14d
  unsigned int v23; // eax
  int v24; // edi
  int v25; // r8d
  int v26; // r9d
  LONG vt; // ecx
  __int64 *v28; // rdx
  struct IRDPCollection *v29; // rcx
  __int64 v30; // rcx
  int v32[2]; // [rsp+28h] [rbp-91h]
  struct IRDPCollection *v33; // [rsp+50h] [rbp-69h] BYREF
  int v34[2]; // [rsp+58h] [rbp-61h] BYREF
  int lVal; // [rsp+60h] [rbp-59h] BYREF
  __int16 SystemInformation; // [rsp+64h] [rbp-55h] BYREF
  int v37; // [rsp+68h] [rbp-51h] BYREF
  __int64 v38; // [rsp+70h] [rbp-49h] BYREF
  const unsigned __int16 *bstrVal; // [rsp+78h] [rbp-41h] BYREF
  const char *v40; // [rsp+80h] [rbp-39h] BYREF
  __int64 v41; // [rsp+88h] [rbp-31h] BYREF
  __int64 v42; // [rsp+90h] [rbp-29h] BYREF
  const char *v43; // [rsp+98h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-19h] BYREF
  struct IRDPCollection **v45; // [rsp+B8h] [rbp-1h]
  struct _GUID v46; // [rsp+C0h] [rbp+7h] BYREF

  v45 = a2;
  lVal = 0;
  v37 = 0;
  v2 = (unsigned int)a1;
  v34[0] = 0;
  v33 = 0;
  v41 = 0;
  Instance = CRDPCollection::CreateInstance(a1, (void **)&v33);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 14;
      v8 = "CRDPCollection::CreateInstance failed!";
LABEL_6:
      v32[0] = Instance;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        (unsigned int)WPP_5a582c1ff5bf36125383cd1c3d5e99aa_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v8,
        *(_QWORD *)v32);
      goto LABEL_135;
    }
    goto LABEL_135;
  }
  if ( !IsDebuggerPresent()
    && ((SystemInformation = 0, NtQuerySystemInformation(SystemKernelDebuggerInformation, &SystemInformation, 2u, 0) < 0)
     || !(_BYTE)SystemInformation)
    || (Instance = ReadPolicyToProperties(
                     v33,
                     L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
                     L"RecordGFXData",
                     L"RecordingEnabled",
                     8u,
                     0,
                     0),
        Instance >= 0) )
  {
    Instance = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, _QWORD))(*(_QWORD *)v33 + 72LL))(
                 v33,
                 L"ConnectionID",
                 v2);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 16;
        v8 = "Failed to set the connection id property";
        goto LABEL_6;
      }
      goto LABEL_135;
    }
    Instance = ReadPolicyToProperties(
                 v33,
                 L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
                 L"MaxCompressionLevel",
                 L"MaxCompressionLevel",
                 0x13u,
                 0,
                 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 17;
        v8 = "Failed to read the compression level policy";
        goto LABEL_6;
      }
      goto LABEL_135;
    }
    Instance = ReadPolicyToProperties(
                 v33,
                 L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
                 L"AVC444ModePreferred",
                 L"GfxPipeline::AVC444ModePreferred",
                 0xBu,
                 1,
                 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 18;
        v8 = "Failed to read the AVC444 mode preferred policy";
        goto LABEL_6;
      }
      goto LABEL_135;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AVCMM>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AVCMM>::GetImpl'::`2'::impl) )
    {
      Instance = (*(__int64 (__fastcall **)(struct IRDPCollection *, const unsigned __int16 *, __int64))(*(_QWORD *)v33 + 64LL))(
                   v33,
                   L"GfxPipeline::AVCMixedModePreferred",
                   1);
      if ( Instance < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v7 = 19;
          v8 = "Failed to set AVC Mixedmode property";
          goto LABEL_6;
        }
        goto LABEL_135;
      }
    }
    Instance = ReadPolicyToProperties(
                 v33,
                 L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
                 L"AVCMixedModePreferred",
                 L"GfxPipeline::AVCMixedModePreferred",
                 0xBu,
                 1,
                 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 20;
        v8 = "Failed to read the AVCMM mode preferred policy";
        goto LABEL_6;
      }
      goto LABEL_135;
    }
    Instance = ReadPolicyToProperties(
                 v33,
                 L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
                 L"InDriverEncodingPreferred",
                 L"GfxPipeline::InDriverEncodingPreferred",
                 0xBu,
                 1,
                 v34);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 21;
        v8 = "Failed to read the In-driver encoding preferred policy";
        goto LABEL_6;
      }
      goto LABEL_135;
    }
    if ( v34[0]
      && (unsigned int)dword_1801B76C8 > 4
      && (unsigned __int8)tlgKeywordOn(&dword_1801B76C8, 0x470000000000LL) )
    {
      *(_QWORD *)v34 = L"InDriverEncodingPreferred";
      CurrentActivityId = RdpActivityId::GetCurrentActivityId((LPGUID)&pvarg);
      v43 = "GfxProps";
      v10 = *CurrentActivityId;
      v38 = 0x1000000;
      v42 = (__int64)&v46;
      v40 = "Stack";
      bstrVal = (const unsigned __int16 *)"Checkpoint";
      v46 = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
        v11,
        (unsigned int)word_18019BC8A,
        v12,
        v13,
        (__int64)&bstrVal,
        (__int64)&v38,
        (__int64)&v40,
        (__int64)&v43,
        (__int64)&v42,
        (__int64)v34);
    }
    Instance = ReadPolicyToProperties(
                 v33,
                 L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
                 L"HEVCModePreferred",
                 L"GfxPipeline::HEVCHardwareEncodePreferred",
                 0xBu,
                 1,
                 &v37);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_135;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 22;
      goto LABEL_55;
    }
    if ( v37 && (unsigned int)dword_1801B76C8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801B76C8, 0x470000000000LL) )
    {
      bstrVal = L"HEVCModePreferred";
      v14 = *RdpActivityId::GetCurrentActivityId((LPGUID)&pvarg);
      v42 = 0x1000000;
      v38 = (__int64)&v46;
      v40 = "GfxProps";
      v43 = "Stack";
      *(_QWORD *)v34 = "Checkpoint";
      v46 = v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
        v15,
        (unsigned int)byte_18019BC1D,
        v16,
        v17,
        (__int64)v34,
        (__int64)&v42,
        (__int64)&v43,
        (__int64)&v40,
        (__int64)&v38,
        (__int64)&bstrVal);
    }
    v37 = 0;
    Instance = ReadPolicyToProperties(
                 v33,
                 L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
                 L"HEVCHardwareEncodePreferred",
                 L"GfxPipeline::HEVCHardwareEncodePreferred",
                 0xBu,
                 1,
                 &v37);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_135;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 23;
LABEL_55:
      v8 = "Failed to read the HEVC mode preferred policy";
      goto LABEL_6;
    }
    if ( v37 && (unsigned int)dword_1801B76C8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801B76C8, 0x470000000000LL) )
    {
      bstrVal = L"HEVCHardwareEncodePreferred";
      v18 = *RdpActivityId::GetCurrentActivityId((LPGUID)&pvarg);
      v42 = 0x1000000;
      v38 = (__int64)&v46;
      v40 = "GfxProps";
      v43 = "Stack";
      *(_QWORD *)v34 = "Checkpoint";
      v46 = v18;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
        v19,
        (unsigned int)qword_18019BBB0,
        v20,
        v21,
        (__int64)v34,
        (__int64)&v42,
        (__int64)&v43,
        (__int64)&v40,
        (__int64)&v38,
        (__int64)&bstrVal);
    }
    Instance = ReadPolicyToProperties(
                 v33,
                 L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
                 L"AVCHardwareEncodePreferred",
                 L"GfxPipeline::AVCHwEncodePreferred",
                 0x13u,
                 1,
                 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 24;
        v8 = "Failed to read the AVC444 HW mode preferred policy";
        goto LABEL_6;
      }
      goto LABEL_135;
    }
    Instance = ReadPolicyToProperties(
                 v33,
                 L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
                 L"GraphicsProfile",
                 L"GfxPipeline::ProfilePolicy",
                 0x13u,
                 1,
                 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 25;
        v8 = "Failed to read the graphics profile policy";
        goto LABEL_6;
      }
      goto LABEL_135;
    }
    Instance = ReadPolicyToProperties(
                 v33,
                 L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
                 L"ImageQuality",
                 L"GfxPipeline::ImageQualityPolicy",
                 0x13u,
                 1,
                 &lVal);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 26;
        v8 = "Failed to read the image quality policy";
        goto LABEL_6;
      }
      goto LABEL_135;
    }
    if ( !lVal )
    {
      Instance = (*(__int64 (__fastcall **)(struct IRDPCollection *, const unsigned __int16 *, __int64))(*(_QWORD *)v33 + 72LL))(
                   v33,
                   L"GfxPipeline::ImageQualityPolicy",
                   3);
      if ( Instance < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v7 = 27;
          v8 = "Failed to set default image quality";
          goto LABEL_6;
        }
        goto LABEL_135;
      }
    }
    Instance = ReadPolicyToProperties(
                 v33,
                 L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
                 L"fEnableVirtualizedGraphics",
                 L"GfxPipeline::RemoteFXCompressionEnabled",
                 0x13u,
                 0,
                 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 28;
        v8 = "Failed to read the remotefx compression policy";
        goto LABEL_6;
      }
      goto LABEL_135;
    }
    Instance = ReadPolicyToProperties(
                 v33,
                 L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
                 L"fRemoteFXGraphicsAPITestMode",
                 L"RCM::Services::Graphics::RemoteFXTestMode",
                 0x13u,
                 0,
                 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 29;
        v8 = "Failed to read the remotefx test setting";
        goto LABEL_6;
      }
      goto LABEL_135;
    }
    Instance = ReadPolicyToProperties(
                 v33,
                 L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
                 L"DWMFRAMEINTERVAL",
                 L"GfxPipelineTst::TargetFrameInterval",
                 0x13u,
                 0,
                 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_135;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 30;
      goto LABEL_105;
    }
    Instance = ReadPolicyToProperties(
                 v33,
                 L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
                 L"DisplayRefreshRate",
                 L"GfxPipeline::DisplayRefreshRate",
                 0x13u,
                 0,
                 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_135;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 31;
LABEL_105:
      v8 = "Failed to read the target frame interval setting";
      goto LABEL_6;
    }
    Instance = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, __int64))(*(_QWORD *)v33 + 64LL))(
                 v33,
                 L"GfxPipeline::EnableFBR",
                 1);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 32;
        v8 = "Failed to set the enable FBR property";
        goto LABEL_6;
      }
      goto LABEL_135;
    }
    v22 = (**(__int64 (__fastcall ***)(struct IRDPCollection *, GUID *, __int64 *))v33)(
            v33,
            &IID_IRDPCollectionIterator,
            &v41);
    if ( v22 < 0 )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v23 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_5a582c1ff5bf36125383cd1c3d5e99aa_Traceguids, v23, v22);
      }
      goto LABEL_135;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 24LL))(v41);
    while ( 1 )
    {
      *(_QWORD *)v34 = 0;
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v24 = (*(__int64 (__fastcall **)(__int64, int *, VARIANTARG *))(*(_QWORD *)v41 + 32LL))(v41, v34, &pvarg);
      if ( v24 >= 0 )
      {
        vt = pvarg.vt;
        if ( pvarg.vt == 19 )
        {
          if ( (unsigned int)dword_1801B76C8 > 4 )
          {
            vt = pvarg.lVal;
            v28 = qword_18019BB78;
            lVal = pvarg.lVal;
LABEL_129:
            bstrVal = *(const unsigned __int16 **)v34;
            v38 = (__int64)"Connection Properties contains";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              vt,
              (_DWORD)v28,
              v25,
              v26,
              (__int64)&v38,
              (__int64)&bstrVal,
              (__int64)&lVal);
          }
        }
        else
        {
          if ( pvarg.vt != 11 )
          {
            if ( pvarg.vt == 8 && (unsigned int)dword_1801B76C8 > 4 )
            {
              bstrVal = pvarg.bstrVal;
              v38 = *(_QWORD *)v34;
              v40 = "Connection Properties contains";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                pvarg.vt,
                (unsigned int)qword_18019BB08,
                v25,
                v26,
                (__int64)&v40,
                (__int64)&v38,
                (__int64)&bstrVal);
            }
            goto LABEL_133;
          }
          if ( (unsigned int)dword_1801B76C8 > 4 )
          {
            v28 = qword_18019BB40;
            lVal = pvarg.iVal;
            goto LABEL_129;
          }
        }
      }
LABEL_133:
      VariantClear(&pvarg);
      if ( v24 < 0 )
      {
        v29 = v33;
        *v45 = v33;
        (*(void (__fastcall **)(struct IRDPCollection *))(*(_QWORD *)v29 + 8LL))(v29);
        goto LABEL_135;
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 15;
    v8 = "Failed to read the recording property";
    goto LABEL_6;
  }
LABEL_135:
  v30 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v33, v3, v5);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18006233c  mov     [rsp-8+arg_10], rbx
0x180062341  push    rbp
0x180062342  push    rsi
0x180062343  push    rdi
0x180062344  push    r12
0x180062346  push    r13
0x180062348  push    r14
0x18006234a  push    r15
0x18006234c  lea     rbp, [rsp-27h]
0x180062351  sub     rsp, 0E0h
0x180062358  mov     rax, cs:__security_cookie
0x18006235f  xor     rax, rsp
0x180062362  mov     [rbp+57h+var_40], rax
0x180062366  xor     r12d, r12d
0x180062369  mov     [rbp+57h+var_58], rdx
0x18006236d  lea     rdx, [rbp+57h+var_C0]; void **
0x180062371  mov     [rbp+57h+var_B0], r12d
0x180062375  mov     [rbp+57h+var_A8], r12d
0x180062379  mov     r14d, ecx
0x18006237c  mov     [rbp+57h+var_B8], r12d
0x180062380  mov     [rbp+57h+var_C0], r12
0x180062384  mov     [rbp+57h+var_88], r12
0x180062388  call    ?CreateInstance@CRDPCollection@@SAJAEBU_GUID@@PEAPEAX@Z; CRDPCollection::CreateInstance(_GUID const &,void * *)
0x18006238d  mov     ebx, eax
0x18006238f  test    eax, eax
0x180062391  jns     short loc_1800623FD
0x180062393  mov     rax, cs:WPP_GLOBAL_Control
0x18006239a  lea     rcx, WPP_GLOBAL_Control
0x1800623a1  cmp     rax, rcx
0x1800623a4  jz      loc_180063046
0x1800623aa  lea     esi, [r12+8]
0x1800623af  test    [rax+1Ch], sil
0x1800623b3  jz      loc_180063046
0x1800623b9  lea     edi, [rsi-6]
0x1800623bc  cmp     [rax+19h], dil
0x1800623c0  jb      loc_180063046
0x1800623c6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800623cb  lea     edx, [rsi+6]
0x1800623ce  lea     rcx, aCrdpcollection; "CRDPCollection::CreateInstance failed!"
0x1800623d5  mov     [rsp+110h+var_E8], ebx
0x1800623d9  lea     r8, WPP_5a582c1ff5bf36125383cd1c3d5e99aa_Traceguids
0x1800623e0  mov     qword ptr [rsp+110h+var_F0], rcx
0x1800623e5  mov     r9d, eax
0x1800623e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800623ef  mov     rcx, [rcx+10h]
0x1800623f3  call    WPP_SF_DsD
0x1800623f8  jmp     loc_180063046
0x1800623fd  call    cs:__imp_IsDebuggerPresent
0x180062403  mov     esi, 8
0x180062408  lea     edi, [rsi-6]
0x18006240b  test    eax, eax
0x18006240d  jnz     short loc_180062431
0x18006240f  xor     r9d, r9d; ReturnLength
0x180062412  mov     [rbp+57h+SystemInformation], r12w
0x180062417  mov     r8d, edi; SystemInformationLength
0x18006241a  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x18006241e  lea     ecx, [rsi+1Bh]; SystemInformationClass
0x180062421  call    cs:__imp_NtQuerySystemInformation
0x180062427  test    eax, eax
0x180062429  js      short loc_1800624A5
0x18006242b  cmp     byte ptr [rbp+57h+SystemInformation], r12b
0x18006242f  jz      short loc_1800624A5
0x180062431  mov     rcx, [rbp+57h+var_C0]; struct IRDPCollection *
0x180062435  lea     r9, aRecordingenabl; "RecordingEnabled"
0x18006243c  mov     [rsp+110h+var_E0], r12; int *
0x180062441  lea     r8, aRecordgfxdata; "RecordGFXData"
0x180062448  mov     [rsp+110h+var_E8], r12d; int
0x18006244d  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Control\\Ter"...
0x180062454  mov     [rsp+110h+var_F0], si; unsigned __int16
0x180062459  call    ?ReadPolicyToProperties@@YAJPEAUIRDPCollection@@PEBG11GHPEAH@Z; ReadPolicyToProperties(IRDPCollection *,ushort const *,ushort const *,ushort const *,ushort,int,int *)
0x18006245e  mov     ebx, eax
0x180062460  test    eax, eax
0x180062462  jns     short loc_1800624A5
0x180062464  mov     rax, cs:WPP_GLOBAL_Control
0x18006246b  lea     rcx, WPP_GLOBAL_Control
0x180062472  cmp     rax, rcx
0x180062475  jz      loc_180063046
0x18006247b  test    [rax+1Ch], sil
0x18006247f  jz      loc_180063046
0x180062485  cmp     [rax+19h], dil
0x180062489  jb      loc_180063046
0x18006248f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180062494  mov     edx, 0Fh
0x180062499  lea     rcx, aFailedToReadTh_5; "Failed to read the recording property"
0x1800624a0  jmp     loc_1800623D5
0x1800624a5  mov     rcx, [rbp+57h+var_C0]
0x1800624a9  lea     rdx, aConnectionid; "ConnectionID"
0x1800624b0  mov     r8d, r14d
0x1800624b3  mov     rax, [rcx]
0x1800624b6  mov     rax, [rax+48h]
0x1800624ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800624bf  mov     ebx, eax
0x1800624c1  test    eax, eax
0x1800624c3  jns     short loc_180062506
0x1800624c5  mov     rax, cs:WPP_GLOBAL_Control
0x1800624cc  lea     rcx, WPP_GLOBAL_Control
0x1800624d3  cmp     rax, rcx
0x1800624d6  jz      loc_180063046
0x1800624dc  test    [rax+1Ch], sil
0x1800624e0  jz      loc_180063046
0x1800624e6  cmp     [rax+19h], dil
0x1800624ea  jb      loc_180063046
0x1800624f0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800624f5  mov     edx, 10h
0x1800624fa  lea     rcx, aFailedToSetThe_0; "Failed to set the connection id propert"...
0x180062501  jmp     loc_1800623D5
0x180062506  mov     rcx, [rbp+57h+var_C0]; struct IRDPCollection *
0x18006250a  lea     r8, aMaxcompression; "MaxCompressionLevel"
0x180062511  mov     [rsp+110h+var_E0], r12; int *
0x180062516  lea     r14, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows "...
0x18006251d  mov     r13d, 13h
0x180062523  mov     [rsp+110h+var_E8], r12d; int
0x180062528  mov     r9, r8; unsigned __int16 *
0x18006252b  mov     [rsp+110h+var_F0], r13w; unsigned __int16
0x180062531  mov     rdx, r14; unsigned __int16 *
0x180062534  call    ?ReadPolicyToProperties@@YAJPEAUIRDPCollection@@PEBG11GHPEAH@Z; ReadPolicyToProperties(IRDPCollection *,ushort const *,ushort const *,ushort const *,ushort,int,int *)
0x180062539  mov     ebx, eax
0x18006253b  test    eax, eax
0x18006253d  jns     short loc_18006257F
0x18006253f  mov     rax, cs:WPP_GLOBAL_Control
0x180062546  lea     rcx, WPP_GLOBAL_Control
0x18006254d  cmp     rax, rcx
0x180062550  jz      loc_180063046
0x180062556  test    [rax+1Ch], sil
0x18006255a  jz      loc_180063046
0x180062560  cmp     [rax+19h], dil
0x180062564  jb      loc_180063046
0x18006256a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006256f  lea     edx, [r13-2]
0x180062573  lea     rcx, aFailedToReadTh_8; "Failed to read the compression level po"...
0x18006257a  jmp     loc_1800623D5
0x18006257f  mov     rcx, [rbp+57h+var_C0]; struct IRDPCollection *
0x180062583  lea     r9, aGfxpipelineAvc_1; "GfxPipeline::AVC444ModePreferred"
0x18006258a  mov     [rsp+110h+var_E0], r12; int *
0x18006258f  lea     r8, aAvc444modepref; "AVC444ModePreferred"
0x180062596  mov     [rsp+110h+var_E8], 1; int
0x18006259e  mov     rdx, r14; unsigned __int16 *
0x1800625a1  mov     [rsp+110h+var_F0], 0Bh; unsigned __int16
0x1800625a8  call    ?ReadPolicyToProperties@@YAJPEAUIRDPCollection@@PEBG11GHPEAH@Z; ReadPolicyToProperties(IRDPCollection *,ushort const *,ushort const *,ushort const *,ushort,int,int *)
0x1800625ad  mov     ebx, eax
0x1800625af  test    eax, eax
0x1800625b1  jns     short loc_1800625F4
0x1800625b3  mov     rax, cs:WPP_GLOBAL_Control
0x1800625ba  lea     rcx, WPP_GLOBAL_Control
0x1800625c1  cmp     rax, rcx
0x1800625c4  jz      loc_180063046
0x1800625ca  test    [rax+1Ch], sil
0x1800625ce  jz      loc_180063046
0x1800625d4  cmp     [rax+19h], dil
0x1800625d8  jb      loc_180063046
0x1800625de  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800625e3  mov     edx, 12h
0x1800625e8  lea     rcx, aFailedToReadTh; "Failed to read the AVC444 mode preferre"...
0x1800625ef  jmp     loc_1800623D5
0x1800625f4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AVCMM@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AVCMM@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AVCMM> `wil::Feature<__WilFeatureTraits_Feature_AVCMM>::GetImpl(void)'::`2'::impl
0x1800625fb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AVCMM@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AVCMM>::__private_IsEnabled(void)
0x180062600  test    al, al
0x180062602  jz      short loc_180062666
0x180062604  mov     rcx, [rbp+57h+var_C0]
0x180062608  lea     rdx, aGfxpipelineAvc_0; "GfxPipeline::AVCMixedModePreferred"
0x18006260f  mov     r8d, 1
0x180062615  mov     rax, [rcx]
0x180062618  mov     rax, [rax+40h]
0x18006261c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062621  mov     ebx, eax
0x180062623  test    eax, eax
0x180062625  jns     short loc_180062666
0x180062627  mov     rax, cs:WPP_GLOBAL_Control
0x18006262e  lea     rcx, WPP_GLOBAL_Control
0x180062635  cmp     rax, rcx
0x180062638  jz      loc_180063046
0x18006263e  test    [rax+1Ch], sil
0x180062642  jz      loc_180063046
0x180062648  cmp     [rax+19h], dil
0x18006264c  jb      loc_180063046
0x180062652  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180062657  mov     edx, r13d
0x18006265a  lea     rcx, aFailedToSetAvc; "Failed to set AVC Mixedmode property"
0x180062661  jmp     loc_1800623D5
0x180062666  mov     rcx, [rbp+57h+var_C0]; struct IRDPCollection *
0x18006266a  lea     r9, aGfxpipelineAvc_0; "GfxPipeline::AVCMixedModePreferred"
0x180062671  mov     [rsp+110h+var_E0], r12; int *
0x180062676  lea     r8, aAvcmixedmodepr; "AVCMixedModePreferred"
0x18006267d  mov     [rsp+110h+var_E8], 1; int
0x180062685  mov     rdx, r14; unsigned __int16 *
0x180062688  mov     [rsp+110h+var_F0], 0Bh; unsigned __int16
0x18006268f  call    ?ReadPolicyToProperties@@YAJPEAUIRDPCollection@@PEBG11GHPEAH@Z; ReadPolicyToProperties(IRDPCollection *,ushort const *,ushort const *,ushort const *,ushort,int,int *)
0x180062694  mov     ebx, eax
0x180062696  test    eax, eax
0x180062698  jns     short loc_1800626DB
0x18006269a  mov     rax, cs:WPP_GLOBAL_Control
0x1800626a1  lea     rcx, WPP_GLOBAL_Control
0x1800626a8  cmp     rax, rcx
0x1800626ab  jz      loc_180063046
0x1800626b1  test    [rax+1Ch], sil
0x1800626b5  jz      loc_180063046
0x1800626bb  cmp     [rax+19h], dil
0x1800626bf  jb      loc_180063046
0x1800626c5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800626ca  mov     edx, 14h
0x1800626cf  lea     rcx, aFailedToReadTh_2; "Failed to read the AVCMM mode preferred"...
0x1800626d6  jmp     loc_1800623D5
0x1800626db  mov     rcx, [rbp+57h+var_C0]; struct IRDPCollection *
0x1800626df  lea     rax, [rbp+57h+var_B8]
0x1800626e3  mov     [rsp+110h+var_E0], rax; int *
0x1800626e8  lea     r9, aGfxpipelineInd; "GfxPipeline::InDriverEncodingPreferred"
0x1800626ef  mov     [rsp+110h+var_E8], 1; int
0x1800626f7  lea     r8, aIndriverencodi; "InDriverEncodingPreferred"
0x1800626fe  mov     rdx, r14; unsigned __int16 *
0x180062701  mov     [rsp+110h+var_F0], 0Bh; unsigned __int16
0x180062708  call    ?ReadPolicyToProperties@@YAJPEAUIRDPCollection@@PEBG11GHPEAH@Z; ReadPolicyToProperties(IRDPCollection *,ushort const *,ushort const *,ushort const *,ushort,int,int *)
0x18006270d  mov     ebx, eax
0x18006270f  test    eax, eax
0x180062711  jns     short loc_180062754
0x180062713  mov     rax, cs:WPP_GLOBAL_Control
0x18006271a  lea     rcx, WPP_GLOBAL_Control
0x180062721  cmp     rax, rcx
0x180062724  jz      loc_180063046
0x18006272a  test    [rax+1Ch], sil
0x18006272e  jz      loc_180063046
0x180062734  cmp     [rax+19h], dil
0x180062738  jb      loc_180063046
0x18006273e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180062743  mov     edx, 15h
0x180062748  lea     rcx, aFailedToReadTh_1; "Failed to read the In-driver encoding p"...
0x18006274f  jmp     loc_1800623D5
0x180062754  lea     rbx, aGfxprops; "GfxProps"
0x18006275b  cmp     [rbp+57h+var_B8], r12d
0x18006275f  jz      loc_18006281A
0x180062765  mov     eax, cs:dword_1801B76C8
0x18006276b  cmp     eax, 4
0x18006276e  jbe     loc_18006281A
0x180062774  mov     rdx, 470000000000h
0x18006277e  lea     rcx, dword_1801B76C8
0x180062785  call    _tlgKeywordOn
0x18006278a  test    al, al
0x18006278c  jz      loc_18006281A
0x180062792  lea     rax, aIndriverencodi; "InDriverEncodingPreferred"
0x180062799  lea     rcx, [rbp+57h+pvarg]; ActivityId
0x18006279d  mov     qword ptr [rbp+57h+var_B8], rax
0x1800627a1  call    ?GetCurrentActivityId@RdpActivityId@@SA?AU_GUID@@XZ; RdpActivityId::GetCurrentActivityId(void)
0x1800627a6  lea     rdx, word_18019BC8A
0x1800627ad  mov     [rbp+57h+var_78], rbx
0x1800627b1  movups  xmm0, xmmword ptr [rax]
0x1800627b4  lea     rax, [rbp+57h+var_50]
0x1800627b8  mov     [rbp+57h+var_A0], 1000000h
0x1800627c0  mov     [rbp+57h+var_80], rax
0x1800627c4  lea     rax, aStack; "Stack"
0x1800627cb  mov     [rbp+57h+var_90], rax
0x1800627cf  lea     rax, aCheckpoint; "Checkpoint"
0x1800627d6  mov     [rbp+57h+var_98], rax
0x1800627da  lea     rax, [rbp+57h+var_B8]
0x1800627de  mov     [rsp+110h+var_C8], rax
0x1800627e3  lea     rax, [rbp+57h+var_80]
0x1800627e7  mov     [rsp+110h+var_D0], rax
0x1800627ec  lea     rax, [rbp+57h+var_78]
0x1800627f0  mov     [rsp+110h+var_D8], rax
0x1800627f5  lea     rax, [rbp+57h+var_90]
0x1800627f9  mov     [rsp+110h+var_E0], rax
0x1800627fe  lea     rax, [rbp+57h+var_A0]
0x180062802  mov     qword ptr [rsp+110h+var_E8], rax
0x180062807  lea     rax, [rbp+57h+var_98]
0x18006280b  mov     qword ptr [rsp+110h+var_F0], rax
0x180062810  movdqu  [rbp+57h+var_50], xmm0
0x180062815  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &)
0x18006281a  mov     rcx, [rbp+57h+var_C0]; struct IRDPCollection *
0x18006281e  lea     rax, [rbp+57h+var_A8]
0x180062822  mov     [rsp+110h+var_E0], rax; int *
0x180062827  lea     r9, aGfxpipelineHev; "GfxPipeline::HEVCHardwareEncodePreferre"...
0x18006282e  mov     [rsp+110h+var_E8], 1; int
0x180062836  lea     r8, aHevcmodeprefer; "HEVCModePreferred"
0x18006283d  mov     rdx, r14; unsigned __int16 *
0x180062840  mov     [rsp+110h+var_F0], 0Bh; unsigned __int16
0x180062847  call    ?ReadPolicyToProperties@@YAJPEAUIRDPCollection@@PEBG11GHPEAH@Z; ReadPolicyToProperties(IRDPCollection *,ushort const *,ushort const *,ushort const *,ushort,int,int *)
0x18006284c  mov     ebx, eax
0x18006284e  test    eax, eax
0x180062850  jns     short loc_180062893
0x180062852  mov     rax, cs:WPP_GLOBAL_Control
0x180062859  lea     rcx, WPP_GLOBAL_Control
0x180062860  cmp     rax, rcx
0x180062863  jz      loc_180063046
0x180062869  test    [rax+1Ch], sil
0x18006286d  jz      loc_180063046
0x180062873  cmp     [rax+19h], dil
0x180062877  jb      loc_180063046
0x18006287d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180062882  mov     edx, 16h
0x180062887  lea     rcx, aFailedToReadTh_9; "Failed to read the HEVC mode preferred "...
0x18006288e  jmp     loc_1800623D5
0x180062893  cmp     [rbp+57h+var_A8], r12d
0x180062897  jz      loc_180062959
0x18006289d  mov     eax, cs:dword_1801B76C8
0x1800628a3  cmp     eax, 4
0x1800628a6  jbe     loc_180062959
0x1800628ac  mov     rdx, 470000000000h
0x1800628b6  lea     rcx, dword_1801B76C8
0x1800628bd  call    _tlgKeywordOn
0x1800628c2  test    al, al
0x1800628c4  jz      loc_180062959
0x1800628ca  lea     rax, aHevcmodeprefer; "HEVCModePreferred"
  ... truncated ...
```
