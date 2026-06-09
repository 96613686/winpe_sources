# HevcCompressor::InitializeHelper(uint,uint,QPSettings &,int,ulong,int,int,AvcEncodeSettings::MftSetting &,int,RdpSurface *)

- ea: `0x18008f990`
- end: `0x1800908dd`
- name: `?InitializeHelper@HevcCompressor@@MEAAJIIAEAUQPSettings@@HKHHAEAW4MftSetting@AvcEncodeSettings@@HPEAVRdpSurface@@@Z`
- size: `3917`
- prototype: `__int64 __fastcall(HevcCompressor *__hidden this, unsigned int, unsigned int, struct QPSettings *, int, unsigned int, int, int, enum AvcEncodeSettings::MftSetting *, int, struct RdpSurface *)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180092eb0`

## callees

- `0x180002d8c`
- `0x1800071c0`
- `0x1800071f0`
- `0x180009628`
- `0x18000a93c`
- `0x18000c8c0`
- `0x18000ee00`
- `0x1800100d4`
- `0x180012228`
- `0x18001e49c`
- `0x18002e600`
- `0x180033964`
- `0x180033da0`
- `0x1800598d0`
- `0x18007d290`
- `0x18008d1c0`
- `0x18008d930`
- `0x18008dbbc`
- `0x18008e0d0`
- `0x18008e730`
- `0x18008f990`
- `0x1800b8334`
- `0x1800d9f14`
- `0x1800db044`
- `0x1800dc2c8`
- `0x1800e5410`
- `0x18014d010`

## import_xrefs

- `RDPBASE!RgnlibBA_CreateInstance` at `0x180090713`
- `RDPBASE!RgnlibBA_CreateInstance` at `0x180090713`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008fafa`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008fb9c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008fc0d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008fc6c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008fea9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009027f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180090362`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180090408`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180090481`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800904ed`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009057d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180090618`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009068c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800906f1`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009074a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800907e0`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008fafa`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008fb9c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008fc0d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008fc6c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008fea9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009027f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180090362`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180090408`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180090481`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800904ed`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009057d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180090618`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009068c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800906f1`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009074a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800907e0`

## string_xrefs

- `0x180090371`: `CreateMediaType( RGB ) failed`
- `0x18009069b`: `CreateSample failed on YUV sample`
- `0x180090759`: `RgnlibBA_CreateInstance failed`
- `0x18008fcab`: `DX texture not found during initialization, non-fatal`
- `0x18008fd26`: `ShaderResourceView not found during initialization, non-fatal`
- `0x180090417`: `CreateMediaType(YUV) failed`
- `0x18009058c`: `CreateMediaType( H265 ) failed`
- `0x180090627`: `CreateColorConverter failed`
- `0x180090846`: `HEVCCompressor`

## pseudocode

```c
__int64 __fastcall HevcCompressor::InitializeHelper(
        HevcCompressor *this,
        unsigned int a2,
        int a3,
        struct QPSettings *a4,
        int a5,
        unsigned int a6,
        int a7,
        int a8,
        enum AvcEncodeSettings::MftSetting *a9,
        unsigned int a10,
        struct RdpSurface *a11)
{
  struct ID3D11Texture2D *v11; // rbx
  const char *v13; // rdi
  const struct _GUID *v16; // rdx
  int v17; // ecx
  __int64 v18; // r8
  int v19; // r9d
  HevcCompressor *v20; // rcx
  int ImageMediaType; // esi
  int ActivityIdPrefix; // eax
  CMFApi *v23; // rax
  CMFApi *v24; // rsi
  CMFApi **v25; // r15
  int v26; // eax
  int v27; // edx
  const char *v28; // rcx
  int v29; // eax
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  int v33; // r9d
  __int64 v34; // rdx
  __int64 v35; // r8
  int v36; // r9d
  int SupportedSSELevel; // eax
  int v38; // r8d
  int v39; // r9d
  unsigned int v40; // r12d
  int *v41; // r10
  int *v42; // r15
  bool v43; // zf
  unsigned int v44; // eax
  int v45; // r8d
  unsigned int v46; // r9d
  int v47; // eax
  int v48; // edx
  int v49; // ecx
  __int64 CompressorOutputAvc_0; // rax
  unsigned int v51; // r8d
  unsigned int v52; // edx
  int v53; // eax
  int v54; // r9d
  int v55; // eax
  unsigned int v56; // eax
  unsigned int v57; // ecx
  __m128i si128; // xmm1
  double v59; // xmm2_8
  __m128i v60; // xmm0
  double v61; // xmm0_8
  double v62; // xmm6_8
  int (__fastcall ***v63)(_QWORD, GUID *, char *); // rcx
  _QWORD *v64; // rsi
  int v65; // ecx
  int v66; // r8d
  int v67; // r9d
  double v68; // xmm0_8
  __int64 v69; // rsi
  __int64 v70; // r13
  struct ID3D11Texture2D *v71; // rax
  int v72; // r12d
  int v73; // r15d
  int v74; // eax
  struct _GUID v75; // xmm0
  __int64 v76; // rcx
  int v77; // r15d
  unsigned int v78; // r9d
  unsigned int *v79; // rcx
  int v80; // eax
  double v81; // xmm6_8
  _QWORD *v82; // r12
  unsigned int v83; // r15d
  int v84; // eax
  int v85; // eax
  int v86; // eax
  int v87; // eax
  int v88; // eax
  int v89; // eax
  int v90; // eax
  int v91; // eax
  unsigned int v92; // edi
  void *v93; // rax
  void *v94; // rbx
  int v95; // ecx
  int v96; // r9d
  __int64 v97; // rdx
  __int64 v98; // r8
  unsigned int v100; // [rsp+20h] [rbp-E0h]
  unsigned int v101; // [rsp+20h] [rbp-E0h]
  unsigned int v102; // [rsp+20h] [rbp-E0h]
  struct IMFMediaType **v103; // [rsp+28h] [rbp-D8h]
  struct IMFMediaType **v104; // [rsp+28h] [rbp-D8h]
  struct IMFMediaType **v105; // [rsp+28h] [rbp-D8h]
  struct IMFMediaType **v106; // [rsp+28h] [rbp-D8h]
  const char *v107; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v108[2]; // [rsp+78h] [rbp-88h] BYREF
  struct ID3D11Texture2D *v109; // [rsp+80h] [rbp-80h] BYREF
  const char *v110; // [rsp+88h] [rbp-78h] BYREF
  const char *v111; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v112; // [rsp+98h] [rbp-68h] BYREF
  int v113; // [rsp+9Ch] [rbp-64h]
  int v114; // [rsp+A0h] [rbp-60h]
  unsigned int v115[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v116; // [rsp+B0h] [rbp-50h] BYREF
  const char *v117; // [rsp+B8h] [rbp-48h] BYREF
  const char *v118; // [rsp+C0h] [rbp-40h] BYREF
  __int64 (__fastcall *v119)(__int64, __int64 *, const char *, const char *); // [rsp+C8h] [rbp-38h] BYREF
  __int64 v120; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v121; // [rsp+D8h] [rbp-28h]
  __int64 v122; // [rsp+E8h] [rbp-18h]
  __int64 v123; // [rsp+F0h] [rbp-10h]
  int v124; // [rsp+F8h] [rbp-8h]
  int v125; // [rsp+FCh] [rbp-4h]
  int v126; // [rsp+100h] [rbp+0h]
  int v127; // [rsp+104h] [rbp+4h]
  unsigned int v128; // [rsp+108h] [rbp+8h]
  __int64 v129; // [rsp+110h] [rbp+10h] BYREF
  _OWORD v130[2]; // [rsp+118h] [rbp+18h]
  struct _GUID v131; // [rsp+138h] [rbp+38h] BYREF

  v11 = 0;
  v117 = (const char *)a9;
  v120 = 0;
  v121 = 0;
  v122 = 0;
  v13 = 0;
  v123 = 0;
  v124 = 0;
  v128 = 0;
  v111 = 0;
  v118 = (const char *)a4;
  v108[0] = a2;
  v125 = 800;
  v126 = 300000000;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v111);
  v109 = 0;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v109);
  *((_DWORD *)this + 108) = a7;
  v131 = 0;
  if ( a7 )
    *((_DWORD *)this + 39) = 1;
  if ( !a2 || !a3 )
  {
    ImageMediaType = -2147024809;
    goto LABEL_164;
  }
  v114 = *((_DWORD *)this + 38);
  v113 = *((_DWORD *)this + 39);
  if ( *((_DWORD *)this + 42) )
  {
    if ( (unsigned int)dword_1801B76C8 > 4 )
    {
      v107 = "AvcMftEncodeSetting GP overruled by test key; is now AvcMftHwEncodeRequired";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v17,
        (unsigned int)byte_1801A1C41,
        v18,
        v19,
        (__int64)&v107);
    }
    *(_DWORD *)a9 = 2;
  }
  v20 = (HevcCompressor *)*(unsigned int *)a9;
  if ( (unsigned int)((_DWORD)v20 - 1) > 1 )
  {
    if ( (_DWORD)v20 != 3 )
      goto LABEL_51;
    if ( !*((_DWORD *)this + 110) )
    {
      ImageMediaType = -2147024846;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
          ActivityIdPrefix,
          (__int64)"HEVC software encoding is currently not supported",
          -2147024846);
      }
      goto LABEL_164;
    }
  }
  v23 = (CMFApi *)operator new(0xB0u);
  if ( v23 )
    v24 = CMFApi::CMFApi(v23);
  else
    v24 = 0;
  v25 = (CMFApi **)((char *)this + 320);
  if ( v24 != *((CMFApi **)this + 40) )
  {
    TCntPtr<CWppAutoTrace>::SafeRelease((char *)this + 320);
    *v25 = v24;
    TCntPtr<CTermInputMgr>::SafeAddRef((char *)this + 320);
  }
  if ( !*v25 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_27;
    }
    v26 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v27 = 37;
    v28 = "CMFApi";
LABEL_26:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v27,
      (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
      v26,
      (__int64)v28);
LABEL_27:
    ImageMediaType = -2147024882;
    goto LABEL_164;
  }
  ImageMediaType = CMFApi::Init(*v25);
  if ( ImageMediaType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v29 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
        v29,
        (__int64)"Failed to init MF API. Cannot use HEVC encoding",
        ImageMediaType);
    }
    goto LABEL_164;
  }
  ImageMediaType = (*((__int64 (__fastcall **)(__int64, _QWORD))*v25 + 7))(131184, 0);
  if ( ImageMediaType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v30 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
        v30,
        (__int64)"MFStartup failed. Cannot use HEVC encoding",
        ImageMediaType);
    }
    goto LABEL_164;
  }
  if ( a11 )
  {
    if ( (int)HevcCompressor::GetInputDXTextureFromGfxProvider(v20, a11, &v109) >= 0 )
    {
      v11 = v109;
      if ( !v113 )
      {
        *(_QWORD *)v115 = v109;
        TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(v115);
        if ( (int)CD3D11Api::CreateSRVFromDXTexture(v115, &v111) >= 0 )
        {
          v13 = v111;
        }
        else
        {
          if ( (unsigned int)dword_1801B76C8 > 4 )
          {
            v107 = "ShaderResourceView not found during initialization, non-fatal";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              (_DWORD)v20,
              (unsigned int)byte_1801A1BE5,
              v35,
              v36,
              (__int64)&v107);
          }
          v13 = v111;
          if ( v111 )
          {
            TCntPtr<IRdpSQMLogger>::SafeRelease(&v111, v34, v35);
            v13 = 0;
            v111 = 0;
            TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v111);
          }
        }
      }
    }
    else
    {
      if ( (unsigned int)dword_1801B76C8 > 4 )
      {
        v107 = "DX texture not found during initialization, non-fatal";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (_DWORD)v20,
          (unsigned int)word_1801A1C6A,
          v32,
          v33,
          (__int64)&v107);
      }
      v11 = v109;
      if ( v109 )
      {
        TCntPtr<IRdpSQMLogger>::SafeRelease(&v109, v31, v32);
        v11 = 0;
        v109 = 0;
        TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v109);
      }
    }
  }
LABEL_51:
  SupportedSSELevel = GetSupportedSSELevel(v20);
  v40 = v108[0];
  v41 = (int *)((char *)this + 84);
  *((_DWORD *)this + 107) = 2592000;
  *((_DWORD *)this + 21) = v40;
  *((_DWORD *)this + 22) = a3;
  v42 = (int *)((char *)this + 100);
  v43 = *((_DWORD *)this + 109) == 0;
  *((_DWORD *)this + 90) = SupportedSSELevel >= 2;
  if ( v43 )
    v44 = (v40 + 15) & 0xFFFFFFF0;
  else
    v44 = (v40 + 31) & 0xFFFFFFE0;
  *v42 = v44;
  *((_DWORD *)this + 93) = a10;
  if ( (unsigned int)dword_1801B76C8 > 5 )
  {
    v108[0] = a10;
    v107 = "Delta reduction in Color Conversion is ";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a10,
      (unsigned int)&word_1801A1C0E,
      v38,
      v39,
      (__int64)&v107,
      (__int64)v108);
    v41 = (int *)((char *)this + 84);
  }
  v45 = *v42;
  v46 = (a3 + 15) & 0xFFFFFFF0;
  *((_DWORD *)this + 23) = *v42;
  *((_DWORD *)this + 26) = v46;
  *((_DWORD *)this + 27) = 4 * v46 * v45;
  *((_DWORD *)this + 28) = (3 * v46 * v45) >> 1;
  v47 = a3;
  if ( (a3 & 1) != 0 )
    v47 = a3 + 1;
  v48 = *((_DWORD *)this + 22);
  v49 = *v41;
  *((_DWORD *)this + 24) = v47;
  CompressorOutputAvc_0 = anonymous_namespace_::CreateCompressorOutputAvc_0(v49, v48, v45, v46);
  v51 = *((_DWORD *)this + 26);
  v52 = *v42;
  *((_QWORD *)this + 9) = CompressorOutputAvc_0;
  v53 = AdvanceFeatureMap::Initialize((HevcCompressor *)((char *)this + 216), v52, v51, 0);
  v18 = 0;
  ImageMediaType = v53;
  if ( v53 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v55 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v103) = ImageMediaType;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
        v55,
        (__int64)"m_featureMap.Initialize() failed",
        v103);
    }
    goto LABEL_164;
  }
  v56 = *v42 * *((_DWORD *)this + 26);
  v57 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  *((_QWORD *)this + 16) = 0;
  v130[1] = si128;
  v59 = 805306368.0 / (double)(v56 >> 8);
  v60 = _mm_load_si128((const __m128i *)&_xmm);
  *((double *)this + 15) = v59;
  v130[0] = v60;
  while ( 1 )
  {
    v61 = *((double *)v130 + v57);
    if ( v59 > v61 )
      break;
    if ( ++v57 >= 4 )
      goto LABEL_68;
  }
  *((double *)this + 15) = v61;
LABEL_68:
  if ( *((double *)this + 15) >= 30.0 )
    *((_QWORD *)this + 15) = 0x403E000000000000LL;
  if ( (unsigned int)dword_1801B76C8 > 4 )
  {
    v107 = (const char *)*((_QWORD *)this + 15);
    v110 = "HEVC frame rate is set to";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      v57,
      (unsigned int)&dword_1801A1B74,
      0,
      v54,
      (__int64)&v110,
      (__int64)&v107);
  }
  v62 = *((double *)this + 15);
  *((_DWORD *)this + 95) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_DWORD *)this + 100) = 100;
  *((_DWORD *)this + 106) = 0;
  *(_QWORD *)v115 = 30000;
  *((_QWORD *)this + 17) = 10000000LL / (unsigned int)(int)v62;
  *((_QWORD *)this + 48) = 1065353216;
  *((_DWORD *)this + 102) = 1065353216;
  *((_DWORD *)this + 103) = 1065353216;
  *((_QWORD *)this + 52) = 1065353216;
  if ( a6 < 0x7530 )
  {
    *(_QWORD *)v115 = 400;
    if ( a6 >= 0x190 )
      *(_QWORD *)v115 = (unsigned int)(int)((double)(int)a6 * v62 / *((double *)this + 18));
  }
  v63 = (int (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 42);
  v64 = (_QWORD *)((char *)this + 352);
  v112 = 0;
  v116 = 0;
  if ( (**v63)(v63, &IID_IRDPENCPlatformContext, (char *)this + 352) >= 0 )
  {
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, unsigned int *))(*(_QWORD *)*v64 + 32LL))(
           *v64,
           L"HevcKeyFrameHeader",
           &v112) >= 0
      && (unsigned int)dword_1801B76C8 > 4 )
    {
      v108[0] = v112;
      v107 = "EnableHevcKeyframeHeader (0=Off, 1=On)";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v65,
        (unsigned int)&unk_1801A1BA8,
        v66,
        v67,
        (__int64)&v107,
        (__int64)v108);
    }
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, int *))(*(_QWORD *)*v64 + 32LL))(
           *v64,
           L"WVD::EnableColorConverterAVXOptimization",
           &v116) >= 0 )
      *((_DWORD *)this + 94) = v116;
  }
  v43 = *((_DWORD *)this + 43) == 1;
  v68 = *((double *)this + 15);
  v69 = *((_QWORD *)this + 42);
  *((_QWORD *)&v121 + 1) = *(_QWORD *)((char *)this + 92);
  HIDWORD(v122) = a8;
  LODWORD(v123) = a5;
  HIDWORD(v123) = *((_DWORD *)this + 44);
  v124 = *((_DWORD *)this + 46);
  v125 = *((_DWORD *)this + 48);
  v126 = *((_DWORD *)this + 49);
  v127 = *((_DWORD *)this + 93);
  DWORD1(v121) = a3;
  v70 = *((_QWORD *)this + 8);
  v128 = v112;
  v120 = v69;
  LODWORD(v121) = v40;
  *(float *)&v122 = v68;
  v119 = *(__int64 (__fastcall **)(__int64, __int64 *, const char *, const char *))(*(_QWORD *)v70 + 16LL);
  if ( v43 )
  {
    v107 = 0;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v107);
    v71 = 0;
    v72 = 0;
    v73 = 1;
  }
  else
  {
    v110 = (const char *)v11;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v110);
    v73 = 0;
    v71 = v11;
    v72 = 2;
  }
  *(_QWORD *)v108 = v71;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(v108);
  v129 = *((_QWORD *)this + 40);
  TCntPtr<CTermInputMgr>::SafeAddRef(&v129);
  v100 = v115[0];
  ImageMediaType = v119(v70, &v120, v118, v117);
  if ( v72 )
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v110, v16, v18);
  if ( v73 )
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v107, v16, v18);
  if ( ImageMediaType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v74 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v103) = ImageMediaType;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
        v74,
        (__int64)"Failed to initialize the HEVC Encoder",
        v103);
    }
    goto LABEL_164;
  }
  if ( v114 )
  {
    v75 = MFVideoFormat_ARGB32;
    v108[0] = *((_DWORD *)this + 27);
LABEL_100:
    v77 = a7;
    goto LABEL_101;
  }
  v76 = *((_QWORD *)this + 8);
  v108[0] = *((_DWORD *)this + 28);
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v76 + 88LL))(v76) )
  {
    v75 = MFVideoFormat_IYUV;
    goto LABEL_100;
  }
  v77 = a7;
  if ( a7 )
    v75 = MFVideoFormat_AYUV;
  else
    v75 = MFVideoFormat_NV12;
LABEL_101:
  v131 = v75;
  if ( v113 )
  {
    v78 = *((_DWORD *)this + 22);
    v79 = (unsigned int *)((char *)this + 84);
  }
  else
  {
    v78 = *((_DWORD *)this + 26);
    v79 = (unsigned int *)((char *)this + 100);
  }
  ImageMediaType = HevcCompressor::CreateImageMediaType(
                     *((const struct CMFApi **)this + 40),
                     v16,
                     *v79,
                     v78,
                     v100,
                     (struct IMFMediaType **)this + 35);
  if ( ImageMediaType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v80 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v104) = ImageMediaType;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
        v80,
        (__int64)"CreateMediaType( RGB ) failed",
        v104);
    }
    goto LABEL_164;
  }
  v81 = v62 * 10000000.0;
  v82 = (_QWORD *)((char *)this + 288);
  v83 = v77 != 0 ? 6 : 1;
  ImageMediaType = HevcCompressor::CreateEncMediaType(
                     *((const struct CMFApi **)this + 40),
                     &v131,
                     *((_DWORD *)this + 25),
                     *((_DWORD *)this + 26),
                     v101,
                     (int)v81,
                     0x989680u,
                     v83,
                     0,
                     (struct IMFMediaType **)this + 36);
  if ( ImageMediaType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v84 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v105) = ImageMediaType;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
        v84,
        (__int64)"CreateMediaType(YUV) failed",
        v105);
    }
    goto LABEL_164;
  }
  if ( a7 )
  {
    ImageMediaType = (*(__int64 (__fastcall **)(_QWORD, const GUID *, __int64))(*(_QWORD *)*v82 + 168LL))(
                       *v82,
                       &MF_MT_TRANSFER_FUNCTION,
                       5);
    if ( ImageMediaType < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v85 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        LODWORD(v105) = ImageMediaType;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          44,
          (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
          v85,
          (__int64)"MF_MT_TRANSFER_FUNCTION failed",
          v105);
      }
      goto LABEL_164;
    }
    ImageMediaType = (*(__int64 (__fastcall **)(_QWORD, const GUID *, __int64))(*(_QWORD *)*v82 + 168LL))(
                       *v82,
                       &MF_MT_VIDEO_CHROMA_SITING,
                       1);
    if ( ImageMediaType < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v86 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        LODWORD(v105) = ImageMediaType;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
          v86,
          (__int64)"MF_MT_VIDEO_CHROMA_SITING failed",
          v105);
      }
      goto LABEL_164;
    }
  }
  ImageMediaType = HevcCompressor::CreateEncMediaType(
                     *((const struct CMFApi **)this + 40),
                     &MFVideoFormat_HEVC,
                     *((_DWORD *)this + 25),
                     *((_DWORD *)this + 26),
                     v102,
                     (int)v81,
                     0x989680u,
                     v83,
                     1000 * v115[0],
                     (struct IMFMediaType **)this + 37);
  if ( ImageMediaType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v87 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v106) = ImageMediaType;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
        v87,
        (__int64)"CreateMediaType( H265 ) failed",
        v106);
    }
    goto LABEL_164;
  }
  if ( v114 )
    goto LABEL_147;
  v107 = v13;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v107);
  v110 = (const char *)v11;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v110);
  ImageMediaType = HevcCompressor::CreateColorConverter(
                     (_DWORD)this,
                     (unsigned int)&v110,
                     (unsigned int)&v107,
                     v113,
                     a7,
                     a8);
  if ( ImageMediaType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v88 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v106) = ImageMediaType;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
        v88,
        (__int64)"CreateColorConverter failed",
        v106);
    }
    goto LABEL_164;
  }
  if ( *((_DWORD *)this + 92) )
    goto LABEL_147;
  ImageMediaType = CMFApi::CreateSample(*((CMFApi **)this + 40), v108[0], (struct IMFSample **)this + 39);
  if ( ImageMediaType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v89 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v106) = ImageMediaType;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
        v89,
        (__int64)"CreateSample failed on YUV sample",
        v106);
    }
    goto LABEL_164;
  }
  ImageMediaType = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 39) + 304LL))(
                     *((_QWORD *)this + 39),
                     *((_QWORD *)this + 17));
  if ( ImageMediaType >= 0 )
  {
LABEL_147:
    ImageMediaType = RgnlibBA_CreateInstance((char *)this + 328);
    if ( ImageMediaType >= 0 )
    {
      v92 = *((_DWORD *)this + 56);
      v93 = operator new(saturated_mul(v92, 0x10u));
      v94 = v93;
      if ( v93 )
        `vector constructor iterator'(v93, 0x10u, v92, (void *(*)(void *))RdpRect::RdpRect);
      else
        v94 = 0;
      *((_QWORD *)this + 58) = v94;
      if ( !v94 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_27;
        }
        v26 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        v27 = 51;
        v28 = "\"RdpRect array\"";
        goto LABEL_26;
      }
      *((_DWORD *)this + 91) = *(_DWORD *)v117;
      if ( (unsigned int)dword_1801B76C8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801B76C8, 0x470000000000LL) )
      {
        v107 = (const char *)0x1000000;
        v119 = (__int64 (__fastcall *)(__int64, __int64 *, const char *, const char *))((char *)this + 476);
        v118 = "HEVCCompressor";
        v117 = "Stack";
        v110 = "Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
          v95,
          (unsigned int)byte_1801A1B0D,
          v18,
          v96,
          (__int64)&v110,
          (__int64)&v107,
          (__int64)&v117,
          (__int64)&v118,
          (__int64)&v119);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v91 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v106) = ImageMediaType;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
        v91,
        (__int64)"RgnlibBA_CreateInstance failed",
        v106);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v90 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    LODWORD(v106) = ImageMediaType;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      49,
      (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
      v90,
      (__int64)"m_spInputSample->SetSampleDuration() failed.",
      v106);
  }
LABEL_164:
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v109, v16, v18);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v111, v97, v98);
  return (unsigned int)ImageMediaType;
}

```

## disassembly

```asm
0x18008f990  mov     rax, rsp
0x18008f993  push    rbp
0x18008f994  push    rbx
0x18008f995  push    rsi
0x18008f996  push    rdi
0x18008f997  push    r12
0x18008f999  push    r13
0x18008f99b  push    r14
0x18008f99d  push    r15
0x18008f99f  lea     rbp, [rsp-68h]
0x18008f9a4  sub     rsp, 168h
0x18008f9ab  movaps  xmmword ptr [rax-58h], xmm6
0x18008f9af  mov     rax, cs:__security_cookie
0x18008f9b6  xor     rax, rsp
0x18008f9b9  mov     [rbp+0A0h+var_58], rax
0x18008f9bd  mov     r15, [rbp+0A0h+arg_40]
0x18008f9c4  xor     ebx, ebx
0x18008f9c6  mov     r12, [rbp+0A0h+arg_50]
0x18008f9cd  mov     r14, rcx
0x18008f9d0  xorps   xmm0, xmm0
0x18008f9d3  mov     [rbp+0A0h+var_E8], r15
0x18008f9d7  lea     rcx, [rbp+0A0h+var_110]
0x18008f9db  mov     [rbp+0A0h+var_D0], rbx
0x18008f9df  movups  [rbp+0A0h+var_C8], xmm0
0x18008f9e3  mov     [rbp+0A0h+var_B8], rbx
0x18008f9e7  mov     edi, ebx
0x18008f9e9  mov     [rbp+0A0h+var_B0], rbx
0x18008f9ed  mov     r13d, r8d
0x18008f9f0  mov     [rbp+0A0h+var_A8], ebx
0x18008f9f3  mov     esi, edx
0x18008f9f5  mov     [rbp+0A0h+var_98], ebx
0x18008f9f8  mov     [rbp+0A0h+var_110], rbx
0x18008f9fc  mov     [rbp+0A0h+var_E0], r9
0x18008fa00  mov     [rsp+1A0h+var_128], edx
0x18008fa04  mov     [rbp+0A0h+var_A4], 320h
0x18008fa0b  mov     [rbp+0A0h+var_A0], 11E1A300h
0x18008fa12  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18008fa17  lea     rcx, [rbp+0A0h+var_120]
0x18008fa1b  mov     [rbp+0A0h+var_120], rbx
0x18008fa1f  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18008fa24  mov     eax, [rbp+0A0h+arg_30]
0x18008fa2a  xorps   xmm0, xmm0
0x18008fa2d  mov     [r14+1B0h], eax
0x18008fa34  movups  xmmword ptr [rbp+0A0h+var_68.Data1], xmm0
0x18008fa38  test    eax, eax
0x18008fa3a  jz      short loc_18008FA47
0x18008fa3c  mov     dword ptr [r14+9Ch], 1
0x18008fa47  test    esi, esi
0x18008fa49  jz      loc_18009089C
0x18008fa4f  test    r13d, r13d
0x18008fa52  jz      loc_18009089C
0x18008fa58  mov     eax, [r14+98h]
0x18008fa5f  mov     [rbp+0A0h+var_100], eax
0x18008fa62  mov     eax, [r14+9Ch]
0x18008fa69  mov     [rbp+0A0h+var_104], eax
0x18008fa6c  cmp     [r14+0A8h], ebx
0x18008fa73  jz      short loc_18008FAA9
0x18008fa75  mov     eax, cs:dword_1801B76C8
0x18008fa7b  cmp     eax, 4
0x18008fa7e  jbe     short loc_18008FAA2
0x18008fa80  lea     rax, aAvcmftencodese; "AvcMftEncodeSetting GP overruled by tes"...
0x18008fa87  mov     [rsp+1A0h+var_130], rax
0x18008fa8c  lea     rdx, byte_1801A1C41
0x18008fa93  lea     rax, [rsp+1A0h+var_130]
0x18008fa98  mov     qword ptr [rsp+1A0h+var_180], rax
0x18008fa9d  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18008faa2  mov     dword ptr [r15], 2
0x18008faa9  mov     ecx, [r15]
0x18008faac  lea     eax, [rcx-1]
0x18008faaf  cmp     eax, 1
0x18008fab2  jbe     loc_18008FB38
0x18008fab8  cmp     ecx, 3
0x18008fabb  jnz     loc_18008FD6F
0x18008fac1  cmp     [r14+1B8h], ebx
0x18008fac8  jnz     short loc_18008FB38
0x18008faca  mov     esi, 80070032h
0x18008facf  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fad6  lea     rax, WPP_GLOBAL_Control
0x18008fadd  cmp     rcx, rax
0x18008fae0  jz      loc_1800908A1
0x18008fae6  test    byte ptr [rcx+1Ch], 8
0x18008faea  jz      loc_1800908A1
0x18008faf0  cmp     byte ptr [rcx+19h], 2
0x18008faf4  jb      loc_1800908A1
0x18008fafa  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18008fb00  mov     edx, 24h ; '$'
0x18008fb05  mov     dword ptr [rsp+1A0h+var_178], 80070032h
0x18008fb0d  lea     rcx, aHevcSoftwareEn; "HEVC software encoding is currently not"...
0x18008fb14  mov     qword ptr [rsp+1A0h+var_180], rcx
0x18008fb19  lea     r8, WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids
0x18008fb20  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fb27  mov     r9d, eax
0x18008fb2a  mov     rcx, [rcx+10h]
0x18008fb2e  call    WPP_SF_DsD
0x18008fb33  jmp     loc_1800908A1
0x18008fb38  mov     ecx, 0B0h; Size
0x18008fb3d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008fb42  test    rax, rax
0x18008fb45  jz      short loc_18008FB54
0x18008fb47  mov     rcx, rax; this
0x18008fb4a  call    ??0CMFApi@@QEAA@XZ; CMFApi::CMFApi(void)
0x18008fb4f  mov     rsi, rax
0x18008fb52  jmp     short loc_18008FB56
0x18008fb54  xor     esi, esi
0x18008fb56  lea     r15, [r14+140h]
0x18008fb5d  cmp     rsi, [r15]
0x18008fb60  jz      short loc_18008FB75
0x18008fb62  mov     rcx, r15
0x18008fb65  call    ?SafeRelease@?$TCntPtr@VCWppAutoTrace@@@@AEAAXXZ; TCntPtr<CWppAutoTrace>::SafeRelease(void)
0x18008fb6a  mov     rcx, r15
0x18008fb6d  mov     [r15], rsi
0x18008fb70  call    ?SafeAddRef@?$TCntPtr@VCTermInputMgr@@@@AEAAXXZ; TCntPtr<CTermInputMgr>::SafeAddRef(void)
0x18008fb75  mov     rcx, [r15]; this
0x18008fb78  test    rcx, rcx
0x18008fb7b  jnz     short loc_18008FBD7
0x18008fb7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fb84  lea     rax, WPP_GLOBAL_Control
0x18008fb8b  cmp     rcx, rax
0x18008fb8e  jz      short loc_18008FBCD
0x18008fb90  test    byte ptr [rcx+1Ch], 8
0x18008fb94  jz      short loc_18008FBCD
0x18008fb96  cmp     byte ptr [rcx+19h], 2
0x18008fb9a  jb      short loc_18008FBCD
0x18008fb9c  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18008fba2  mov     edx, 25h ; '%'
0x18008fba7  lea     rcx, aCmfapi; "CMFApi"
0x18008fbae  mov     qword ptr [rsp+1A0h+var_180], rcx
0x18008fbb3  lea     r8, WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids
0x18008fbba  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fbc1  mov     r9d, eax
0x18008fbc4  mov     rcx, [rcx+10h]
0x18008fbc8  call    WPP_SF_Ds
0x18008fbcd  mov     esi, 8007000Eh
0x18008fbd2  jmp     loc_1800908A1
0x18008fbd7  call    ?Init@CMFApi@@QEAAJXZ; CMFApi::Init(void)
0x18008fbdc  mov     esi, eax
0x18008fbde  test    eax, eax
0x18008fbe0  jns     short loc_18008FC28
0x18008fbe2  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fbe9  lea     rax, WPP_GLOBAL_Control
0x18008fbf0  cmp     rcx, rax
0x18008fbf3  jz      loc_1800908A1
0x18008fbf9  test    byte ptr [rcx+1Ch], 8
0x18008fbfd  jz      loc_1800908A1
0x18008fc03  cmp     byte ptr [rcx+19h], 2
0x18008fc07  jb      loc_1800908A1
0x18008fc0d  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18008fc13  mov     edx, 26h ; '&'
0x18008fc18  mov     dword ptr [rsp+1A0h+var_178], esi
0x18008fc1c  lea     rcx, aFailedToInitMf_0; "Failed to init MF API. Cannot use HEVC "...
0x18008fc23  jmp     loc_18008FB14
0x18008fc28  mov     rax, [r15]
0x18008fc2b  xor     edx, edx
0x18008fc2d  mov     ecx, 20070h
0x18008fc32  mov     rax, [rax+38h]
0x18008fc36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fc3b  mov     esi, eax
0x18008fc3d  test    eax, eax
0x18008fc3f  jns     short loc_18008FC87
0x18008fc41  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fc48  lea     rax, WPP_GLOBAL_Control
0x18008fc4f  cmp     rcx, rax
0x18008fc52  jz      loc_1800908A1
0x18008fc58  test    byte ptr [rcx+1Ch], 8
0x18008fc5c  jz      loc_1800908A1
0x18008fc62  cmp     byte ptr [rcx+19h], 2
0x18008fc66  jb      loc_1800908A1
0x18008fc6c  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18008fc72  mov     edx, 27h ; '''
0x18008fc77  mov     dword ptr [rsp+1A0h+var_178], esi
0x18008fc7b  lea     rcx, aMfstartupFaile; "MFStartup failed. Cannot use HEVC encod"...
0x18008fc82  jmp     loc_18008FB14
0x18008fc87  test    r12, r12
0x18008fc8a  jz      loc_18008FD6F
0x18008fc90  lea     r8, [rbp+0A0h+var_120]; struct ID3D11Texture2D **
0x18008fc94  mov     rdx, r12; struct RdpSurface *
0x18008fc97  call    ?GetInputDXTextureFromGfxProvider@HevcCompressor@@IEAAJPEAVRdpSurface@@PEAPEAUID3D11Texture2D@@@Z; HevcCompressor::GetInputDXTextureFromGfxProvider(RdpSurface *,ID3D11Texture2D * *)
0x18008fc9c  test    eax, eax
0x18008fc9e  jns     short loc_18008FCF4
0x18008fca0  mov     eax, cs:dword_1801B76C8
0x18008fca6  cmp     eax, 4
0x18008fca9  jbe     short loc_18008FCCD
0x18008fcab  lea     rax, aDxTextureNotFo; "DX texture not found during initializat"...
0x18008fcb2  mov     [rsp+1A0h+var_130], rax
0x18008fcb7  lea     rdx, word_1801A1C6A
0x18008fcbe  lea     rax, [rsp+1A0h+var_130]
0x18008fcc3  mov     qword ptr [rsp+1A0h+var_180], rax
0x18008fcc8  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18008fccd  mov     rbx, [rbp+0A0h+var_120]
0x18008fcd1  test    rbx, rbx
0x18008fcd4  jz      loc_18008FD6F
0x18008fcda  lea     rcx, [rbp+0A0h+var_120]
0x18008fcde  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18008fce3  xor     ebx, ebx
0x18008fce5  lea     rcx, [rbp+0A0h+var_120]
0x18008fce9  mov     [rbp+0A0h+var_120], rbx
0x18008fced  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18008fcf2  jmp     short loc_18008FD6F
0x18008fcf4  cmp     [rbp+0A0h+var_104], ebx
0x18008fcf7  mov     rbx, [rbp+0A0h+var_120]
0x18008fcfb  jnz     short loc_18008FD6F
0x18008fcfd  lea     rcx, [rbp+0A0h+var_F8]
0x18008fd01  mov     qword ptr [rbp+0A0h+var_F8], rbx
0x18008fd05  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18008fd0a  lea     rdx, [rbp+0A0h+var_110]
0x18008fd0e  lea     rcx, [rbp+0A0h+var_F8]
0x18008fd12  call    ?CreateSRVFromDXTexture@CD3D11Api@@SAJV?$ComPlainSmartPtr@UID3D11Texture2D@@@@PEAPEAUID3D11ShaderResourceView@@@Z; CD3D11Api::CreateSRVFromDXTexture(ComPlainSmartPtr<ID3D11Texture2D>,ID3D11ShaderResourceView * *)
0x18008fd17  test    eax, eax
0x18008fd19  jns     short loc_18008FD6B
0x18008fd1b  mov     eax, cs:dword_1801B76C8
0x18008fd21  cmp     eax, 4
0x18008fd24  jbe     short loc_18008FD48
0x18008fd26  lea     rax, aShaderresource; "ShaderResourceView not found during ini"...
0x18008fd2d  mov     [rsp+1A0h+var_130], rax
0x18008fd32  lea     rdx, byte_1801A1BE5
0x18008fd39  lea     rax, [rsp+1A0h+var_130]
0x18008fd3e  mov     qword ptr [rsp+1A0h+var_180], rax
0x18008fd43  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18008fd48  mov     rdi, [rbp+0A0h+var_110]
0x18008fd4c  test    rdi, rdi
0x18008fd4f  jz      short loc_18008FD6F
0x18008fd51  lea     rcx, [rbp+0A0h+var_110]
0x18008fd55  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18008fd5a  xor     edi, edi
0x18008fd5c  lea     rcx, [rbp+0A0h+var_110]
0x18008fd60  mov     [rbp+0A0h+var_110], rdi
0x18008fd64  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18008fd69  jmp     short loc_18008FD6F
0x18008fd6b  mov     rdi, [rbp+0A0h+var_110]
0x18008fd6f  call    ?GetSupportedSSELevel@@YA?AW4SSELevel@@XZ; GetSupportedSSELevel(void)
0x18008fd74  mov     r12d, [rsp+1A0h+var_128]
0x18008fd79  lea     r10, [r14+54h]
0x18008fd7d  xor     ecx, ecx
0x18008fd7f  mov     dword ptr [r14+1ACh], 278D00h
0x18008fd8a  cmp     eax, 2
0x18008fd8d  mov     [r10], r12d
0x18008fd90  mov     [r14+58h], r13d
0x18008fd94  lea     r15, [r14+64h]
0x18008fd98  setnl   cl
0x18008fd9b  mov     esi, 0FFFFFFF0h
0x18008fda0  cmp     dword ptr [r14+1B4h], 0
0x18008fda8  mov     [r14+168h], ecx
0x18008fdaf  jz      short loc_18008FDBB
0x18008fdb1  lea     eax, [r12+1Fh]
0x18008fdb6  and     eax, 0FFFFFFE0h
0x18008fdb9  jmp     short loc_18008FDC2
0x18008fdbb  lea     eax, [r12+0Fh]
0x18008fdc0  and     eax, esi
0x18008fdc2  mov     ecx, [rbp+0A0h+arg_48]
0x18008fdc8  mov     [r15], eax
0x18008fdcb  mov     [r14+174h], ecx
0x18008fdd2  mov     eax, cs:dword_1801B76C8
0x18008fdd8  cmp     eax, 5
0x18008fddb  jbe     short loc_18008FE11
0x18008fddd  lea     rax, aDeltaReduction; "Delta reduction in Color Conversion is "
0x18008fde4  mov     [rsp+1A0h+var_128], ecx
0x18008fde8  mov     [rsp+1A0h+var_130], rax
0x18008fded  lea     rdx, word_1801A1C0E
0x18008fdf4  lea     rax, [rsp+1A0h+var_128]
0x18008fdf9  mov     [rsp+1A0h+var_178], rax
0x18008fdfe  lea     rax, [rsp+1A0h+var_130]
0x18008fe03  mov     qword ptr [rsp+1A0h+var_180], rax
0x18008fe08  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008fe0d  lea     r10, [r14+54h]
0x18008fe11  mov     r8d, [r15]; int
0x18008fe14  lea     r9d, [r13+0Fh]
0x18008fe18  and     r9d, esi; int
0x18008fe1b  mov     [r14+5Ch], r8d
0x18008fe1f  mov     ecx, r8d
0x18008fe22  mov     [r14+68h], r9d
0x18008fe26  imul    ecx, r9d
0x18008fe2a  lea     eax, ds:0[rcx*4]
0x18008fe31  mov     [r14+6Ch], eax
0x18008fe35  lea     eax, [rcx+rcx*2]
0x18008fe38  shr     eax, 1
0x18008fe3a  mov     [r14+70h], eax
0x18008fe3e  mov     eax, r13d
0x18008fe41  test    r13b, 1
0x18008fe45  jz      short loc_18008FE4B
0x18008fe47  lea     eax, [r13+1]
0x18008fe4b  mov     edx, [r14+58h]; int
0x18008fe4f  mov     ecx, [r10]; int
0x18008fe52  mov     [r14+60h], eax
0x18008fe56  call    _anonymous_namespace___CreateCompressorOutputAvc_0
0x18008fe5b  mov     r8d, [r14+68h]; unsigned int
0x18008fe5f  lea     rcx, [r14+0D8h]; this
0x18008fe66  mov     edx, [r15]; unsigned int
0x18008fe69  xor     r9d, r9d; int
0x18008fe6c  mov     [r14+48h], rax
0x18008fe70  call    ?Initialize@AdvanceFeatureMap@@QEAAJIIH@Z; AdvanceFeatureMap::Initialize(uint,uint,int)
0x18008fe75  xor     r8d, r8d
0x18008fe78  mov     esi, eax
0x18008fe7a  test    eax, eax
0x18008fe7c  jns     short loc_18008FEC4
0x18008fe7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fe85  lea     rax, WPP_GLOBAL_Control
0x18008fe8c  cmp     rcx, rax
0x18008fe8f  jz      loc_1800908A1
0x18008fe95  test    byte ptr [rcx+1Ch], 8
0x18008fe99  jz      loc_1800908A1
  ... truncated ...
```
