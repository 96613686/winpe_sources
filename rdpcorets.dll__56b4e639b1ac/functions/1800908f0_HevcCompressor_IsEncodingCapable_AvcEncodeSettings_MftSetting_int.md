# HevcCompressor::IsEncodingCapable(AvcEncodeSettings::MftSetting,int)

- ea: `0x1800908f0`
- end: `0x1800917fa`
- name: `?IsEncodingCapable@HevcCompressor@@UEAAHW4MftSetting@AvcEncodeSettings@@H@Z`
- size: `3850`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x180003ee0`
- `0x180003fd4`
- `0x180009628`
- `0x180010960`
- `0x18002e600`
- `0x18003394c`
- `0x180033964`
- `0x180033da0`
- `0x1800348e0`
- `0x180034940`
- `0x180034970`
- `0x180034a70`
- `0x1800598d0`
- `0x1800908f0`
- `0x1800d9f14`
- `0x1800da1b0`
- `0x1800da760`
- `0x1800dc2c8`
- `0x1800e1bd0`
- `0x1800e3c50`
- `0x1800e3ff0`
- `0x1800e47c0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180090c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009136e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800913a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180090c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009136e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800913a1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18009131a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18009131a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180090a2d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180090aa8`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180091117`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180091763`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800917c4`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180090a2d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180090aa8`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180091117`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180091763`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800917c4`
- `OLEAUT32!__imp_VariantInit` at `0x18009099c`
- `OLEAUT32!__imp_VariantInit` at `0x180090da4`
- `OLEAUT32!__imp_VariantInit` at `0x18009099c`
- `OLEAUT32!__imp_VariantInit` at `0x180090da4`
- `OLEAUT32!__imp_VariantClear` at `0x180090c5d`
- `OLEAUT32!__imp_VariantClear` at `0x180090e96`
- `OLEAUT32!__imp_VariantClear` at `0x180090ea4`
- `OLEAUT32!__imp_VariantClear` at `0x180090c5d`
- `OLEAUT32!__imp_VariantClear` at `0x180090e96`
- `OLEAUT32!__imp_VariantClear` at `0x180090ea4`
- `dxgi!CreateDXGIFactory2` at `0x180090ebb`
- `dxgi!CreateDXGIFactory2` at `0x180090ebb`

## string_xrefs

- `0x180090beb`: `onecoreuap\termsrv\rdp\win\codecs\hevccodec\hevccompressor.cpp`
- `0x180090f03`: `onecoreuap\termsrv\rdp\win\codecs\hevccodec\hevccompressor.cpp`
- `0x18009150a`: `onecoreuap\termsrv\rdp\win\codecs\hevccodec\hevccompressor.cpp`
- `0x1800915a2`: `onecoreuap\termsrv\rdp\win\codecs\hevccodec\hevccompressor.cpp`
- `0x18009163a`: `onecoreuap\termsrv\rdp\win\codecs\hevccodec\hevccompressor.cpp`
- `0x1800916dd`: `onecoreuap\termsrv\rdp\win\codecs\hevccodec\hevccompressor.cpp`
- `0x180090e62`: `Failed to copy AMD driver version from WVD_PROPERTY_HEVC_MIN_AMD_DRIVER_VERSION property`
- `0x180090eda`: `Failed to create DXGI factory.`
- `0x180091400`: `Created MFTEncoder from vendor`
- `0x180091455`: `Created MFTEncoder from the adapter LUID of HEVC capable device`
- `0x1800916ec`: `_pfnMFShutdown failed during HEVC capability check.`

## pseudocode

```c
__int64 __fastcall HevcCompressor::IsEncodingCapable(__int64 a1, int a2, int a3)
{
  unsigned int v4; // r14d
  CD3DKmThkApi *v5; // rdi
  CMFApi *v7; // rbx
  bool v8; // zf
  unsigned int v9; // esi
  CMFApi *v10; // rax
  CMFApi *v11; // rax
  struct CMFApi *v12; // r13
  int v13; // eax
  char v14; // si
  int v15; // eax
  int v16; // edx
  const char *v17; // rcx
  int v18; // eax
  CD3DKmThkApi *v19; // rax
  CD3DKmThkApi *v20; // r12
  unsigned __int16 *bstrVal; // rsi
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  _QWORD **v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  void *v28; // rcx
  __int64 (__fastcall ***v29)(_QWORD, GUID *, struct IDXGIAdapter4 **); // rcx
  struct IDXGIAdapter4 *v30; // rcx
  unsigned __int16 *v32; // rsi
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  const char *v36; // rax
  __int16 *v37; // rdx
  HRESULT v38; // ecx
  int v39; // r8d
  int v40; // r9d
  __int64 v41; // rdx
  CMFApi *v42; // rsi
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  int v46; // ecx
  int v47; // r8d
  int v48; // r9d
  unsigned int v49; // r13d
  int v50; // ecx
  int v51; // r8d
  int v52; // r9d
  int AdapterDriverVersion; // ecx
  int v54; // r8d
  int v55; // r9d
  __int64 v56; // r12
  __int64 v57; // rsi
  char v58; // si
  unsigned __int64 v59; // r15
  int v60; // eax
  unsigned __int64 v61; // r14
  unsigned int v62; // r12d
  const WCHAR *v63; // rcx
  __int64 v64; // rax
  int v65; // eax
  __int64 v66; // rax
  bool v67; // cf
  int IsDriverVersionBlocked; // eax
  int v69; // ecx
  int v70; // r8d
  int v71; // r9d
  int v72; // r14d
  int v73; // ecx
  int v74; // r8d
  int v75; // r9d
  int v76; // eax
  int ActivityIdPrefix; // eax
  ULONG UserDataCount[2]; // [rsp+28h] [rbp-E0h]
  PEVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-D8h]
  __int64 v80; // [rsp+38h] [rbp-D0h]
  unsigned __int64 v81; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v82; // [rsp+68h] [rbp-A0h] BYREF
  const char *v83; // [rsp+70h] [rbp-98h] BYREF
  __int64 v84; // [rsp+78h] [rbp-90h] BYREF
  const char *v85; // [rsp+80h] [rbp-88h] BYREF
  const char *v86; // [rsp+88h] [rbp-80h] BYREF
  const char *v87; // [rsp+90h] [rbp-78h] BYREF
  int v88; // [rsp+98h] [rbp-70h] BYREF
  const char *v89; // [rsp+A0h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-60h] BYREF
  struct IDXGIAdapter4 *v91; // [rsp+B0h] [rbp-58h] BYREF
  const char *Destination; // [rsp+B8h] [rbp-50h] BYREF
  void *ppFactory; // [rsp+C0h] [rbp-48h] BYREF
  __int64 (__fastcall ***v94)(_QWORD, GUID *, struct IDXGIAdapter4 **); // [rsp+C8h] [rbp-40h] BYREF
  struct IMFTransform *v95; // [rsp+D0h] [rbp-38h] BYREF
  VARIANTARG v96; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v97; // [rsp+F0h] [rbp-18h] BYREF
  void *Block[2]; // [rsp+100h] [rbp-8h]
  __m128i si128; // [rsp+110h] [rbp+8h]
  VARIANTARG pvarg; // [rsp+120h] [rbp+18h] BYREF
  _OWORD v101[2]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v102[256]; // [rsp+158h] [rbp+50h] BYREF
  unsigned int v103; // [rsp+258h] [rbp+150h]
  char Source[24]; // [rsp+280h] [rbp+178h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v105; // [rsp+298h] [rbp+190h] BYREF
  __int16 *v106; // [rsp+2A8h] [rbp+1A0h]
  int v107; // [rsp+2B0h] [rbp+1A8h]
  int v108; // [rsp+2B4h] [rbp+1ACh]
  const char *v109; // [rsp+2B8h] [rbp+1B0h]
  __int64 v110; // [rsp+2C0h] [rbp+1B8h]
  wchar_t *v111; // [rsp+2C8h] [rbp+1C0h]
  int v112; // [rsp+2D0h] [rbp+1C8h]
  int v113; // [rsp+2D4h] [rbp+1CCh]
  const WCHAR *v114; // [rsp+2D8h] [rbp+1D0h]
  int v115; // [rsp+2E0h] [rbp+1D8h]
  int v116; // [rsp+2E4h] [rbp+1DCh]
  __int64 *v117; // [rsp+2E8h] [rbp+1E0h]
  __int64 v118; // [rsp+2F0h] [rbp+1E8h]
  wchar_t Buffer[104]; // [rsp+2F8h] [rbp+1F0h] BYREF

  v4 = 0;
  v5 = 0;
  v88 = a3;
  pv = 0;
  v91 = 0;
  v94 = 0;
  ppFactory = 0;
  memset_0(v102, 0, 0x140u);
  Destination = 0;
  v7 = 0;
  v95 = 0;
  v101[0] = MFMediaType_Video;
  v97 = 0;
  v101[1] = MFVideoFormat_HEVC;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  *(__m128i *)Block = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffff0000000000000000);
  VariantInit(&pvarg);
  v8 = a2 == 0;
  v9 = 0;
  if ( v8 )
    goto LABEL_24;
  v10 = (CMFApi *)operator new(0xB0u);
  if ( !v10 || (v11 = CMFApi::CMFApi(v10), (v12 = v11) == 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
        ActivityIdPrefix,
        (__int64)"CMFApi");
    }
    goto LABEL_24;
  }
  v7 = v11;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v11 + 4) + 8LL))(*((_QWORD *)v11 + 4));
  v13 = CMFApi::Init(v7);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_23;
    }
    v15 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v16 = 32;
    v17 = "Failed to init MF API. Cannot use HEVC encoding";
LABEL_9:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
      v15,
      (__int64)v17,
      v14);
LABEL_23:
    v9 = 0;
    goto LABEL_24;
  }
  v18 = (*((__int64 (__fastcall **)(__int64, _QWORD))v12 + 7))(131184, 0);
  v14 = v18;
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_23;
    }
    v15 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v16 = 33;
    v17 = "MFStartup failed. Cannot use HEVC encoding";
    goto LABEL_9;
  }
  v19 = (CD3DKmThkApi *)operator new(0x50u);
  v20 = v19;
  if ( !v19 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v76 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
        v76,
        (__int64)"CD3DKmThkApi");
    }
    goto LABEL_23;
  }
  *((_DWORD *)v19 + 6) = -607474739;
  *((_QWORD *)v19 + 2) = "CD3DKmThkApi";
  v5 = v19;
  *((_DWORD *)v19 + 7) = 1;
  *(_QWORD *)v19 = &CClipLevelCallback::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)v19 + 1) = &CTSUnknown::`vftable'{for `CTSObject'};
  *(_QWORD *)v19 = &CClipLevelCallback::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)v19 + 1) = &CD3DKmThkApi::`vftable'{for `CTSObject'};
  *((_DWORD *)v19 + 10) = 0;
  *((_QWORD *)v19 + 4) = v19;
  *((_QWORD *)v19 + 6) = 0;
  *((_QWORD *)v19 + 7) = 0;
  *((_QWORD *)v19 + 8) = 0;
  *((_QWORD *)v19 + 9) = 0;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v19 + 4) + 8LL))(*((_QWORD *)v19 + 4));
  bstrVal = 0;
  if ( (***(int (__fastcall ****)(_QWORD, GUID *, __int64))(a1 + 288))(
         *(_QWORD *)(a1 + 288),
         &IID_IRDPENCPlatformContext,
         a1 + 304) >= 0
    && (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**(_QWORD **)(a1 + 304) + 24LL))(
         *(_QWORD *)(a1 + 304),
         L"WVD::HEVCDriverVersionBlock",
         &pvarg) >= 0
    && pvarg.vt == 8 )
  {
    bstrVal = pvarg.bstrVal;
  }
  v22 = AdapterToEncoderCreator::Initialize((AdapterToEncoderCreator *)&v97, v12, bstrVal);
  if ( v22 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v88 = 571;
      v85 = "AdapterToEncoderCreator::Initialize failed";
      LODWORD(v84) = v22;
      v87 = "IsEncodingCapable";
      v89 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\hevccodec\\hevccompressor.cpp";
      v81 = (unsigned __int64)"Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v22,
        (unsigned int)byte_1801A219B,
        v23,
        v24,
        (__int64)&v81,
        (__int64)&v84,
        (__int64)&v89,
        (__int64)&v88,
        (__int64)&v87,
        (__int64)&v85);
    }
    goto LABEL_23;
  }
  if ( !v88 )
  {
    VariantInit(&v96);
    if ( (***(int (__fastcall ****)(_QWORD, GUID *, __int64))(a1 + 288))(
           *(_QWORD *)(a1 + 288),
           &IID_IRDPENCPlatformContext,
           a1 + 304) >= 0
      && (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**(_QWORD **)(a1 + 304) + 24LL))(
           *(_QWORD *)(a1 + 304),
           L"WVD::MinAMDDriverVersionForHEVC",
           &v96) >= 0
      && v96.vt == 8 )
    {
      v32 = v96.bstrVal;
      if ( wcscpy_s(&::Destination, 0x64u, v96.bstrVal) || !::Destination )
      {
        if ( (unsigned int)dword_1801B76C8 > 3 )
        {
          v36 = "Failed to copy AMD driver version from WVD_PROPERTY_HEVC_MIN_AMD_DRIVER_VERSION property";
          v37 = word_1801A2172;
          goto LABEL_56;
        }
LABEL_57:
        qword_1801B7E38 = 0;
        ::Destination = 0;
        VariantClear(&v96);
        goto LABEL_59;
      }
      if ( UMD_DISPLAYDRIVER::ConvertDriverVersionStringToLI((UMD_DISPLAYDRIVER *)&qword_1801B7E30, v32) < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 3 )
        {
          v36 = "Failed to convert AMD driver version from string to LARGE_INTEGER";
          v37 = (__int16 *)byte_1801A2149;
LABEL_56:
          v89 = v36;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v33,
            (_DWORD)v37,
            v34,
            v35,
            (__int64)&v89);
          goto LABEL_57;
        }
        goto LABEL_57;
      }
    }
    VariantClear(&v96);
  }
LABEL_59:
  v38 = CreateDXGIFactory2(0, &GUID_50c83a1c_e072_4c48_87b0_3630fa36a6d0, &ppFactory);
  if ( v38 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v88 = 625;
      v85 = "Failed to create DXGI factory.";
      LODWORD(v84) = v38;
      v87 = "IsEncodingCapable";
      v89 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\hevccodec\\hevccompressor.cpp";
      v81 = (unsigned __int64)"Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v38,
        (unsigned int)&dword_1801A20F4,
        v39,
        v40,
        (__int64)&v81,
        (__int64)&v84,
        (__int64)&v89,
        (__int64)&v88,
        (__int64)&v87,
        (__int64)&v85);
    }
    goto LABEL_23;
  }
  v41 = 0;
  LODWORD(v89) = 0;
  LODWORD(v84) = 0;
  v42 = v7;
LABEL_64:
  if ( (*(unsigned int (__fastcall **)(void *, __int64, _QWORD))(*(_QWORD *)ppFactory + 96LL))(ppFactory, v41, &v94) == -2005270526 )
  {
    v72 = (int)v89;
    goto LABEL_109;
  }
  memset_0(Buffer, 0, 0xC8u);
  v81 = 0;
  v43 = (**v94)(v94, &GUID_3c8d99d1_4fbf_4181_a82c_af66bf7bd24e, &v91);
  if ( v43 >= 0 )
  {
    v46 = ((__int64 (__fastcall *)(struct IDXGIAdapter4 *, _BYTE *))v91->lpVtbl->GetDesc3)(v91, v102);
    if ( v46 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_107;
      LODWORD(v81) = 639;
      v83 = "Failed to get description from DXGI adapter.";
      LODWORD(v82) = v46;
      v86 = "IsEncodingCapable";
      v85 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\hevccodec\\hevccompressor.cpp";
      v87 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v46,
        (unsigned int)&byte_1801A209F,
        v47,
        v48,
        (__int64)&v87,
        (__int64)&v82,
        (__int64)&v85,
        (__int64)&v81,
        (__int64)&v86,
        (__int64)&v83);
      v9 = 0;
      goto LABEL_24;
    }
    v49 = v103;
    memcpy_s_0(&Destination, 8u, Source, 8u);
    if ( (unsigned int)dword_1801B76C8 > 5 )
    {
      v86 = Destination;
      v83 = "Device driver information";
      LODWORD(v82) = v49;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v50,
        (unsigned int)&unk_1801A2008,
        v51,
        v52,
        (__int64)&v83,
        (__int64)&v86,
        (__int64)&v82);
    }
    AdapterDriverVersion = CD3DKmThkApi::GetAdapterDriverVersion(v20, v91, &v81);
    if ( AdapterDriverVersion < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_107;
      LODWORD(v81) = 652;
      v83 = "GetAdapterDriverVersion failed.";
      LODWORD(v82) = AdapterDriverVersion;
      v86 = "IsEncodingCapable";
      v85 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\hevccodec\\hevccompressor.cpp";
      v87 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        AdapterDriverVersion,
        (unsigned int)word_1801A1F8A,
        v54,
        v55,
        (__int64)&v87,
        (__int64)&v82,
        (__int64)&v85,
        (__int64)&v81,
        (__int64)&v86,
        (__int64)&v83);
      v9 = 0;
      goto LABEL_24;
    }
    v56 = v88 != 0 ? 2 : 0;
    while ( 1 )
    {
      v57 = 224 * (v56 + v4);
      if ( v49 == *(_DWORD *)((char *)&HevcCompressor::m_hevcCapableDriverMinRequirement + v57) )
      {
        v59 = *(unsigned __int64 *)((char *)&HevcCompressor::m_hevcCapableDriverMinRequirement + v57 + 8);
        if ( v59 )
        {
          v61 = v81;
          v62 = *(_DWORD *)((char *)&HevcCompressor::m_hevcCapableDriverMinRequirement + v57 + 216);
          LODWORD(v80) = (unsigned __int16)v81;
          LODWORD(UserData) = WORD1(v81);
          UserDataCount[0] = WORD2(v81);
          swprintf_s(Buffer, 0x64u, L"%d.%d.%d.%d", HIWORD(v81), *(_QWORD *)UserDataCount, UserData, v80);
          if ( (unsigned int)dword_1801B76C8 > 4 )
          {
            LODWORD(v82) = v49;
            v118 = 4;
            v63 = (const WCHAR *)((char *)&HevcCompressor::m_hevcCapableDriverMinRequirement + v57 + 16);
            v117 = &v82;
            if ( v63 )
            {
              v64 = -1;
              do
                v8 = v63[++v64] == 0;
              while ( !v8 );
              v65 = 2 * v64 + 2;
            }
            else
            {
              v63 = &WindowName;
              v65 = 2;
            }
            v114 = v63;
            v115 = v65;
            v66 = -1;
            v116 = 0;
            do
              v8 = Buffer[++v66] == 0;
            while ( !v8 );
            v113 = 0;
            v112 = 2 * v66 + 2;
            v111 = Buffer;
            v109 = "Display driver version";
            v105.Ptr = (ULONGLONG)off_1801B76D0;
            v110 = 23;
            *(_OWORD *)&v96.vt = 0x40B000000uLL;
            v105.Size = *(unsigned __int16 *)off_1801B76D0;
            v106 = &word_1801A1F16;
            v105.Reserved = 2;
            v107 = 115;
            v108 = 1;
            LODWORD(v81) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(qword_1801B76E8, (PCEVENT_DESCRIPTOR)&v96, 0, 0, 6u, &v105);
          }
          v42 = v7;
          v41 = (unsigned int)(v84 + 1);
          v67 = v61 < v59;
          LODWORD(v84) = v84 + 1;
          v4 = 0;
          if ( v67 )
            goto LABEL_63;
          IsDriverVersionBlocked = AdapterToEncoderCreator::IsDriverVersionBlocked(
                                     (AdapterToEncoderCreator *)&v97,
                                     v91,
                                     (unsigned __int64)Destination,
                                     v49);
          v41 = (unsigned int)v84;
          if ( IsDriverVersionBlocked )
            goto LABEL_63;
          CoTaskMemFree(pv);
          pv = 0;
          if ( CMFApi::CreateHWEncoderByLuid(
                 v7,
                 (unsigned __int64)Destination,
                 (const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *)v101,
                 &v95,
                 (unsigned __int16 **)&pv) >= 0 )
          {
            v72 = 1;
            if ( (unsigned int)dword_1801B76C8 > 4 )
            {
              v83 = (const char *)pv;
              v86 = "Created MFTEncoder from the adapter LUID of HEVC capable device";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                v69,
                (unsigned int)&word_1801A1ECE,
                v70,
                v71,
                (__int64)&v86,
                (__int64)&v83);
            }
          }
          else
          {
            CoTaskMemFree(pv);
            pv = 0;
            if ( (int)CMFApi::CreateHWEncoderByPreferredVendor(v7, v62, v101, &v95, &pv) < 0 )
            {
              v41 = (unsigned int)v84;
LABEL_63:
              v20 = v5;
              goto LABEL_64;
            }
            v72 = 1;
            if ( (unsigned int)dword_1801B76C8 > 4 )
            {
              v83 = (const char *)pv;
              v86 = "Created MFTEncoder from vendor";
              LODWORD(v81) = 1;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                v69,
                (unsigned int)byte_1801A1E15,
                v70,
                v71,
                (__int64)&v86,
                (__int64)&v81,
                (__int64)&v83);
            }
          }
          if ( (unsigned int)dword_1801B76C8 > 4 )
          {
            LODWORD(v81) = v49;
            v83 = (const char *)Buffer;
            v86 = "At least one D3D adapter is HEVC Capable";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
              v69,
              (unsigned int)byte_1801A1E73,
              v70,
              v71,
              (__int64)&v86,
              (__int64)&v81,
              (__int64)&v83);
          }
LABEL_109:
          v73 = (*((__int64 (**)(void))v42 + 8))();
          if ( v73 < 0 && (unsigned int)dword_1801B76C8 > 2 )
          {
            LODWORD(v89) = 774;
            v83 = "IsEncodingCapable";
            LODWORD(v81) = v73;
            v86 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\hevccodec\\hevccompressor.cpp";
            v85 = "_pfnMFShutdown failed during HEVC capability check.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v73,
              (unsigned int)byte_1801A1D7B,
              v74,
              v75,
              (__int64)&v85,
              (__int64)&v81,
              (__int64)&v86,
              (__int64)&v89,
              (__int64)&v83);
          }
          v9 = v72;
          goto LABEL_24;
        }
        v58 = 87;
        if ( (unsigned int)dword_1801B76C8 > 3 )
        {
          v83 = "Minimum supported driver version is 0 - invalid driver version";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            AdapterDriverVersion,
            (unsigned int)&byte_1801A1FDF,
            v54,
            v55,
            (__int64)&v83);
        }
      }
      else
      {
        v58 = 50;
      }
      if ( (int)++v4 >= 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v60 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
            v60,
            (__int64)"No supported vendor found for HEVC encoding",
            v58);
          v9 = 0;
          goto LABEL_24;
        }
LABEL_107:
        v9 = 0;
        goto LABEL_24;
      }
    }
  }
  if ( (unsigned int)dword_1801B76C8 <= 2 )
    goto LABEL_107;
  LODWORD(v81) = 636;
  v83 = "Failed to QI DXGI Adapter.";
  LODWORD(v82) = v43;
  v86 = "IsEncodingCapable";
  v85 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\hevccodec\\hevccompressor.cpp";
  v87 = "Error HResult failed";
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
    v43,
    (unsigned int)word_1801A204A,
    v44,
    v45,
    (__int64)&v87,
    (__int64)&v82,
    (__int64)&v85,
    (__int64)&v81,
    (__int64)&v86,
    (__int64)&v83);
  v9 = 0;
LABEL_24:
  CoTaskMemFree(pv);
  pv = 0;
  VariantClear(&pvarg);
  if ( Block[1] != (void *)-1LL )
  {
    si128.m128i_i64[0] = (__int64)Block[1];
    operator delete(Block[1]);
  }
  v25 = (_QWORD **)Block[0];
  if ( Block[0] )
  {
    Block[0] = 0;
    (*(void (__fastcall **)(_QWORD *))(*v25[4] + 16LL))(v25[4]);
  }
  v26 = *((_QWORD *)&v97 + 1);
  if ( *((_QWORD *)&v97 + 1) )
  {
    *((_QWORD *)&v97 + 1) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v27 = v97;
  if ( (_QWORD)v97 )
  {
    *(_QWORD *)&v97 = 0;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v27 + 32) + 16LL))(*(_QWORD *)(v27 + 32));
  }
  if ( v95 )
    ((void (__fastcall *)(struct IMFTransform *))v95->lpVtbl->Release)(v95);
  if ( v7 )
    (*(void (__fastcall **)(_QWORD *))(**((_QWORD **)v7 + 4) + 16LL))(*((_QWORD **)v7 + 4));
  v28 = ppFactory;
  if ( ppFactory )
  {
    ppFactory = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v29 = v94;
  if ( v94 )
  {
    v94 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct IDXGIAdapter4 **)))(*v29)[2])(v29);
  }
  v30 = v91;
  if ( v91 )
  {
    v91 = 0;
    ((void (__fastcall *)(struct IDXGIAdapter4 *))v30->lpVtbl->Release)(v30);
  }
  if ( v5 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v5 + 4) + 16LL))(*((_QWORD *)v5 + 4));
  return v9;
}

```

## disassembly

```asm
0x1800908f0  mov     r11, rsp
0x1800908f3  push    rbp
0x1800908f4  push    rsi
0x1800908f5  push    rdi
0x1800908f6  lea     rbp, [r11-2F8h]
0x1800908fd  sub     rsp, 3E0h
0x180090904  mov     rax, cs:__security_cookie
0x18009090b  xor     rax, rsp
0x18009090e  mov     [rbp+2F0h+var_30], rax
0x180090915  mov     [r11+10h], rbx
0x180090919  mov     esi, edx
0x18009091b  mov     [r11+18h], r12
0x18009091f  xor     edx, edx; Val
0x180090921  mov     [r11-20h], r14
0x180090925  xor     r14d, r14d
0x180090928  mov     [r11-28h], r15
0x18009092c  mov     edi, r14d
0x18009092f  mov     r15, rcx
0x180090932  mov     [rbp+2F0h+var_360], r8d
0x180090936  lea     rcx, [rbp+2F0h+var_2A0]; void *
0x18009093a  mov     [rbp+2F0h+pv], r14
0x18009093e  mov     r8d, 140h; Size
0x180090944  mov     [rbp+2F0h+var_348], r14
0x180090948  mov     [rbp+2F0h+var_330], r14
0x18009094c  mov     [rbp+2F0h+ppFactory], r14
0x180090950  call    memset_0
0x180090955  movups  xmm0, xmmword ptr cs:MFMediaType_Video.Data1
0x18009095c  lea     rcx, [rbp+2F0h+pvarg]; pvarg
0x180090960  mov     [rbp+2F0h+Destination], r14
0x180090964  movups  xmm1, xmmword ptr cs:MFVideoFormat_HEVC.Data1
0x18009096b  mov     ebx, r14d
0x18009096e  mov     [rbp+2F0h+var_328], r14
0x180090972  movups  [rbp+2F0h+var_2C0], xmm0
0x180090976  xorps   xmm0, xmm0
0x180090979  movdqu  [rbp+2F0h+var_308], xmm0
0x18009097e  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180090986  movups  [rbp+2F0h+var_2B0], xmm1
0x18009098a  movdqa  xmm1, cs:__xmm@ffffffffffffffff0000000000000000
0x180090992  movdqu  [rbp+2F0h+var_2E8], xmm0
0x180090997  movdqu  xmmword ptr [rbp+2F0h+Block], xmm1
0x18009099c  call    cs:__imp_VariantInit
0x1800909a2  test    esi, esi
0x1800909a4  mov     esi, r14d
0x1800909a7  jz      loc_180090C4B
0x1800909ad  mov     ecx, 0B0h; Size
0x1800909b2  mov     [rsp+3F0h+arg_18], r13
0x1800909ba  mov     dword ptr [rsp+3F0h+var_3A0], r14d
0x1800909bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800909c4  test    rax, rax
0x1800909c7  jz      loc_180091799
0x1800909cd  mov     rcx, rax; this
0x1800909d0  call    ??0CMFApi@@QEAA@XZ; CMFApi::CMFApi(void)
0x1800909d5  mov     r13, rax
0x1800909d8  test    rax, rax
0x1800909db  jz      loc_180091799
0x1800909e1  mov     rcx, [rax+20h]
0x1800909e5  mov     rbx, rax
0x1800909e8  mov     rax, [rcx]
0x1800909eb  mov     rax, [rax+8]
0x1800909ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800909f4  mov     rcx, rbx; this
0x1800909f7  call    ?Init@CMFApi@@QEAAJXZ; CMFApi::Init(void)
0x1800909fc  mov     esi, eax
0x1800909fe  test    eax, eax
0x180090a00  jns     short loc_180090A67
0x180090a02  mov     rcx, cs:WPP_GLOBAL_Control
0x180090a09  lea     rax, WPP_GLOBAL_Control
0x180090a10  cmp     rcx, rax
0x180090a13  jz      loc_180090C40
0x180090a19  test    byte ptr [rcx+1Ch], 8
0x180090a1d  jz      loc_180090C40
0x180090a23  cmp     byte ptr [rcx+19h], 2
0x180090a27  jb      loc_180090C40
0x180090a2d  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180090a33  mov     edx, 20h ; ' '
0x180090a38  lea     rcx, aFailedToInitMf_0; "Failed to init MF API. Cannot use HEVC "...
0x180090a3f  mov     dword ptr [rsp+3F0h+UserData], esi
0x180090a43  lea     r8, WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids
0x180090a4a  mov     qword ptr [rsp+3F0h+UserDataCount], rcx
0x180090a4f  mov     r9d, eax
0x180090a52  mov     rcx, cs:WPP_GLOBAL_Control
0x180090a59  mov     rcx, [rcx+10h]
0x180090a5d  call    WPP_SF_DsD
0x180090a62  jmp     loc_180090C40
0x180090a67  mov     rax, [r13+38h]
0x180090a6b  xor     edx, edx
0x180090a6d  mov     ecx, 20070h
0x180090a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090a77  mov     esi, eax
0x180090a79  test    eax, eax
0x180090a7b  jns     short loc_180090ABC
0x180090a7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180090a84  lea     rax, WPP_GLOBAL_Control
0x180090a8b  cmp     rcx, rax
0x180090a8e  jz      loc_180090C40
0x180090a94  test    byte ptr [rcx+1Ch], 8
0x180090a98  jz      loc_180090C40
0x180090a9e  cmp     byte ptr [rcx+19h], 2
0x180090aa2  jb      loc_180090C40
0x180090aa8  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180090aae  mov     edx, 21h ; '!'
0x180090ab3  lea     rcx, aMfstartupFaile; "MFStartup failed. Cannot use HEVC encod"...
0x180090aba  jmp     short loc_180090A3F
0x180090abc  mov     ecx, 50h ; 'P'; Size
0x180090ac1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180090ac6  mov     r12, rax
0x180090ac9  test    rax, rax
0x180090acc  jz      loc_180091738
0x180090ad2  mov     dword ptr [rax+18h], 0DBCAABCDh
0x180090ad9  lea     rcx, aCd3dkmthkapi; "CD3DKmThkApi"
0x180090ae0  mov     [rax+10h], rcx
0x180090ae4  mov     rdi, r12
0x180090ae7  mov     dword ptr [rax+1Ch], 1
0x180090aee  lea     rax, ??_7CClipLevelCallback@@6BINonDelegatingUnknown@@@; const CClipLevelCallback::`vftable'{for `INonDelegatingUnknown'}
0x180090af5  mov     [r12], rax
0x180090af9  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x180090b00  mov     [r12+8], rax
0x180090b05  lea     rax, ??_7CClipLevelCallback@@6BINonDelegatingUnknown@@@; const CClipLevelCallback::`vftable'{for `INonDelegatingUnknown'}
0x180090b0c  mov     [r12], rax
0x180090b10  lea     rax, ??_7CD3DKmThkApi@@6BCTSObject@@@; const CD3DKmThkApi::`vftable'{for `CTSObject'}
0x180090b17  mov     [r12+8], rax
0x180090b1c  mov     [r12+28h], r14d
0x180090b21  mov     [r12+20h], r12
0x180090b26  mov     [r12+30h], r14
0x180090b2b  mov     [r12+38h], r14
0x180090b30  mov     [r12+40h], r14
0x180090b35  mov     [r12+48h], r14
0x180090b3a  mov     rcx, [r12+20h]
0x180090b3f  mov     rax, [rcx]
0x180090b42  mov     rax, [rax+8]
0x180090b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090b4b  mov     rcx, [r15+120h]
0x180090b52  lea     r8, [r15+130h]
0x180090b59  lea     rdx, IID_IRDPENCPlatformContext
0x180090b60  mov     rsi, r14
0x180090b63  mov     rax, [rcx]
0x180090b66  mov     rax, [rax]
0x180090b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090b6e  test    eax, eax
0x180090b70  js      short loc_180090B9E
0x180090b72  mov     rcx, [r15+130h]
0x180090b79  lea     r8, [rbp+2F0h+pvarg]
0x180090b7d  lea     rdx, aWvdHevcdriverv; "WVD::HEVCDriverVersionBlock"
0x180090b84  mov     rax, [rcx]
0x180090b87  mov     rax, [rax+18h]
0x180090b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090b90  test    eax, eax
0x180090b92  js      short loc_180090B9E
0x180090b94  cmp     word ptr [rbp+2F0h+pvarg], 8
0x180090b99  cmovz   rsi, qword ptr [rbp+2F0h+pvarg+8]
0x180090b9e  mov     r8, rsi; unsigned __int16 *
0x180090ba1  lea     rcx, [rbp+2F0h+var_308]; this
0x180090ba5  mov     rdx, r13; struct CMFApi *
0x180090ba8  call    ?Initialize@AdapterToEncoderCreator@@QEAAJPEAVCMFApi@@PEAG@Z; AdapterToEncoderCreator::Initialize(CMFApi *,ushort *)
0x180090bad  mov     ecx, eax
0x180090baf  test    eax, eax
0x180090bb1  jns     loc_180090D96
0x180090bb7  mov     eax, cs:dword_1801B76C8
0x180090bbd  cmp     eax, 2
0x180090bc0  jbe     short loc_180090C40
0x180090bc2  lea     rax, aAdaptertoencod; "AdapterToEncoderCreator::Initialize fai"...
0x180090bc9  mov     [rbp+2F0h+var_360], 23Bh
0x180090bd0  mov     [rsp+3F0h+var_378], rax
0x180090bd5  lea     rdx, byte_1801A219B
0x180090bdc  lea     rax, aIsencodingcapa; "IsEncodingCapable"
0x180090be3  mov     dword ptr [rsp+3F0h+var_380], ecx
0x180090be7  mov     [rbp+2F0h+var_368], rax
0x180090beb  lea     rax, aOnecoreuapTerm_4; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x180090bf2  mov     [rbp+2F0h+var_358], rax
0x180090bf6  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180090bfd  mov     [rsp+3F0h+var_398], rax
0x180090c02  lea     rax, [rsp+3F0h+var_378]
0x180090c07  mov     qword ptr [rsp+3F0h+var_3A8], rax
0x180090c0c  lea     rax, [rbp+2F0h+var_368]
0x180090c10  mov     [rsp+3F0h+var_3B0], rax
0x180090c15  lea     rax, [rbp+2F0h+var_360]
0x180090c19  mov     [rsp+3F0h+var_3B8], rax
0x180090c1e  lea     rax, [rbp+2F0h+var_358]
0x180090c22  mov     [rsp+3F0h+var_3C0], rax
0x180090c27  lea     rax, [rsp+3F0h+var_380]
0x180090c2c  mov     [rsp+3F0h+UserData], rax
0x180090c31  lea     rax, [rsp+3F0h+var_398]
0x180090c36  mov     qword ptr [rsp+3F0h+UserDataCount], rax
0x180090c3b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180090c40  mov     esi, r14d
0x180090c43  mov     r13, [rsp+3F0h+arg_18]
0x180090c4b  mov     rcx, [rbp+2F0h+pv]; pv
0x180090c4f  call    cs:__imp_CoTaskMemFree
0x180090c55  lea     rcx, [rbp+2F0h+pvarg]; pvarg
0x180090c59  mov     [rbp+2F0h+pv], r14
0x180090c5d  call    cs:__imp_VariantClear
0x180090c63  mov     rcx, [rbp+2F0h+Block+8]; Block
0x180090c67  mov     r15, [rsp+3F0h+var_20]
0x180090c6f  mov     r12, [rsp+3F0h+arg_10]
0x180090c77  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180090c7b  jz      short loc_180090C8D
0x180090c7d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180090c84  mov     qword ptr [rbp+2F0h+var_2E8], rcx
0x180090c88  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180090c8d  mov     rcx, [rbp+2F0h+Block]
0x180090c91  test    rcx, rcx
0x180090c94  jz      short loc_180090CAA
0x180090c96  mov     [rbp+2F0h+Block], r14
0x180090c9a  mov     rcx, [rcx+20h]
0x180090c9e  mov     rax, [rcx]
0x180090ca1  mov     rax, [rax+10h]
0x180090ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090caa  mov     rcx, qword ptr [rbp+2F0h+var_308+8]
0x180090cae  test    rcx, rcx
0x180090cb1  jz      short loc_180090CC3
0x180090cb3  mov     qword ptr [rbp+2F0h+var_308+8], r14
0x180090cb7  mov     rax, [rcx]
0x180090cba  mov     rax, [rax+10h]
0x180090cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090cc3  mov     rcx, qword ptr [rbp+2F0h+var_308]
0x180090cc7  test    rcx, rcx
0x180090cca  jz      short loc_180090CE0
0x180090ccc  mov     qword ptr [rbp+2F0h+var_308], r14
0x180090cd0  mov     rcx, [rcx+20h]
0x180090cd4  mov     rax, [rcx]
0x180090cd7  mov     rax, [rax+10h]
0x180090cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090ce0  mov     rcx, [rbp+2F0h+var_328]
0x180090ce4  test    rcx, rcx
0x180090ce7  jz      short loc_180090CF5
0x180090ce9  mov     rax, [rcx]
0x180090cec  mov     rax, [rax+10h]
0x180090cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090cf5  test    rbx, rbx
0x180090cf8  jz      short loc_180090D0A
0x180090cfa  mov     rcx, [rbx+20h]
0x180090cfe  mov     rax, [rcx]
0x180090d01  mov     rax, [rax+10h]
0x180090d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090d0a  mov     rcx, [rbp+2F0h+ppFactory]
0x180090d0e  mov     rbx, [rsp+3F0h+arg_8]
0x180090d16  test    rcx, rcx
0x180090d19  jz      short loc_180090D2B
0x180090d1b  mov     [rbp+2F0h+ppFactory], r14
0x180090d1f  mov     rax, [rcx]
0x180090d22  mov     rax, [rax+10h]
0x180090d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090d2b  mov     rcx, [rbp+2F0h+var_330]
0x180090d2f  test    rcx, rcx
0x180090d32  jz      short loc_180090D44
0x180090d34  mov     [rbp+2F0h+var_330], r14
0x180090d38  mov     rax, [rcx]
0x180090d3b  mov     rax, [rax+10h]
0x180090d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090d44  mov     rcx, [rbp+2F0h+var_348]
0x180090d48  test    rcx, rcx
0x180090d4b  jz      short loc_180090D5D
0x180090d4d  mov     [rbp+2F0h+var_348], r14
0x180090d51  mov     rax, [rcx]
0x180090d54  mov     rax, [rax+10h]
0x180090d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090d5d  mov     r14, [rsp+3D8h]
0x180090d65  test    rdi, rdi
0x180090d68  jz      short loc_180090D7A
0x180090d6a  mov     rcx, [rdi+20h]
0x180090d6e  mov     rdx, [rcx]
0x180090d71  mov     rax, [rdx+10h]
0x180090d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090d7a  mov     eax, esi
0x180090d7c  mov     rcx, [rbp+2F0h+var_30]
0x180090d83  xor     rcx, rsp; StackCookie
0x180090d86  call    __security_check_cookie
0x180090d8b  add     rsp, 3E0h
0x180090d92  pop     rdi
0x180090d93  pop     rsi
0x180090d94  pop     rbp
0x180090d95  retn
0x180090d96  cmp     [rbp+2F0h+var_360], r14d
0x180090d9a  jnz     loc_180090EAC
0x180090da0  lea     rcx, [rbp+2F0h+var_320]; pvarg
0x180090da4  call    cs:__imp_VariantInit
0x180090daa  mov     rcx, [r15+120h]
0x180090db1  lea     r8, [r15+130h]
0x180090db8  lea     rdx, IID_IRDPENCPlatformContext
0x180090dbf  mov     rax, [rcx]
0x180090dc2  mov     rax, [rax]
0x180090dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090dca  test    eax, eax
0x180090dcc  js      loc_180090E9E
0x180090dd2  mov     rcx, [r15+130h]
0x180090dd9  lea     r8, [rbp+2F0h+var_320]
0x180090ddd  lea     rdx, aWvdMinamddrive; "WVD::MinAMDDriverVersionForHEVC"
0x180090de4  mov     rax, [rcx]
0x180090de7  mov     rax, [rax+18h]
0x180090deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090df0  test    eax, eax
0x180090df2  js      loc_180090E9E
0x180090df8  cmp     word ptr [rbp+2F0h+var_320], 8
0x180090dfd  jnz     loc_180090E9E
0x180090e03  mov     rsi, qword ptr [rbp+2F0h+var_320+8]
0x180090e07  lea     rcx, Destination; Destination
0x180090e0e  mov     r8, rsi; Source
0x180090e11  mov     edx, 64h ; 'd'; SizeInWords
0x180090e16  call    wcscpy_s
0x180090e1b  test    eax, eax
  ... truncated ...
```
