# Hevc420Compressor::Compress(RdpSurface *,PixelMap *,IRdpBoundsAccumulator *,int,ulong,ulong,uchar *,uint *,RdpRect *,uint)

- ea: `0x180092110`
- end: `0x180092c50`
- name: `?Compress@Hevc420Compressor@@UEAAJPEAVRdpSurface@@PEAVPixelMap@@PEAVIRdpBoundsAccumulator@@HKKPEAEPEAIPEAURdpRect@@I@Z`
- size: `2880`
- prototype: `__int64 __usercall@<rax>(Hevc420Compressor *__hidden this@<rcx>, struct RdpSurface *@<rdx>, struct PixelMap *@<r8>, struct IRdpBoundsAccumulator *@<r9>, int, unsigned int, unsigned int, unsigned __int8 *, unsigned int *, struct RdpRect *, unsigned int)`
- caller_count: `0`
- callee_count: `26`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004098`
- `0x1800065c0`
- `0x1800071c0`
- `0x1800071f0`
- `0x1800093f0`
- `0x180009628`
- `0x18000ee00`
- `0x180017890`
- `0x180017928`
- `0x18002e600`
- `0x180033da0`
- `0x180059838`
- `0x1800598d0`
- `0x18007a800`
- `0x18008f5d0`
- `0x180091800`
- `0x180091a90`
- `0x180092110`
- `0x180092c60`
- `0x1800936f8`
- `0x1800b8804`
- `0x1800d9770`
- `0x1800d9cc0`
- `0x1800d9cf4`
- `0x1800d9de0`
- `0x18014d010`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092217`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092287`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800922ee`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800924b3`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092510`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092587`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800925e3`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092647`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800926e2`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092734`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800927ab`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092854`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092891`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800928ea`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009293b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092a28`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092acf`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092217`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092287`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800922ee`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800924b3`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092510`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092587`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800925e3`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092647`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800926e2`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092734`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800927ab`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092854`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092891`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800928ea`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009293b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092a28`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180092acf`

## string_xrefs

- `0x180092222`: `GetSourceForCompress failed`
- `0x180092a33`: `Compress using MFT encoder failed`
- `0x180092b32`: `Compress`
- `0x180092b45`: `onecoreuap\termsrv\rdp\win\codecs\hevccodec\hevc420compressor.cpp`
- `0x180092539`: `Successfully created IMF sample with color conversion disabled.`
- `0x18009251b`: `CopyPixelMapToMFSample failed`

## pseudocode

```c
__int64 __fastcall Hevc420Compressor::Compress(
        Hevc420Compressor *this,
        struct RdpSurface *a2,
        struct PixelMap *a3,
        struct IRdpBoundsAccumulator *a4,
        unsigned int a5,
        int a6,
        signed int a7,
        unsigned __int8 *a8,
        unsigned __int8 *a9,
        struct RdpRect *a10,
        unsigned int a11)
{
  struct ID3D11ShaderResourceView *v14; // rdi
  struct ID3D11Texture2D *v15; // rbx
  int v16; // r13d
  PipelineClock *Instance; // rax
  struct PixelMap *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rcx
  int SourceForCompress; // ebx
  int ActivityIdPrefix; // eax
  int v23; // edx
  const char *v24; // rcx
  int v25; // eax
  int v26; // edx
  const char *v27; // rcx
  OutputAvc *v28; // rcx
  QueryCPUPerformance *v29; // rcx
  int v30; // r9d
  double v31; // xmm1_8
  int v32; // r15d
  double v33; // xmm2_8
  __int64 v34; // r14
  __int64 v35; // rax
  __int64 v36; // rcx
  int v37; // r9d
  __int64 v38; // rcx
  __int64 v39; // rcx
  int v40; // ebx
  int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // rdx
  int v45; // ebx
  __int64 v46; // r8
  PVOID *v47; // rcx
  int v48; // eax
  struct IMFSample *v49; // rdi
  unsigned int v50; // eax
  __int64 v51; // rcx
  __int64 v52; // rcx
  int v53; // ebx
  int v54; // eax
  OutputAvc *v55; // rcx
  __int64 v56; // rdi
  __int64 (__fastcall *v57)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, struct IMFSample **, unsigned __int8 *, unsigned __int8 *, char *, _DWORD, _DWORD); // rbx
  unsigned __int8 *v58; // r13
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  unsigned __int64 v62; // rax
  int v63; // r9d
  unsigned __int64 v64; // rax
  OutputAvc *v65; // rcx
  OutputAvc *v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // rdx
  __int64 v70; // r8
  __int64 v72; // [rsp+28h] [rbp-D8h]
  struct IMFSample *v73; // [rsp+60h] [rbp-A0h] BYREF
  int v74; // [rsp+68h] [rbp-98h] BYREF
  struct ID3D11ShaderResourceView *v75; // [rsp+70h] [rbp-90h] BYREF
  struct IMFSample *v76; // [rsp+78h] [rbp-88h] BYREF
  struct PixelMap *v77; // [rsp+80h] [rbp-80h] BYREF
  struct IRdpBoundsAccumulator *v78; // [rsp+88h] [rbp-78h]
  unsigned int v79; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v80; // [rsp+94h] [rbp-6Ch] BYREF
  struct IMFSample *v81; // [rsp+98h] [rbp-68h] BYREF
  const char *v82; // [rsp+A0h] [rbp-60h] BYREF
  struct ID3D11Texture2D *v83; // [rsp+A8h] [rbp-58h] BYREF
  const char *MillisecondCount64; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v85; // [rsp+B8h] [rbp-48h]
  __int64 v86; // [rsp+C0h] [rbp-40h]
  unsigned __int8 *v87; // [rsp+C8h] [rbp-38h] BYREF
  PipelineClock *v88; // [rsp+D0h] [rbp-30h]
  unsigned __int8 *v89; // [rsp+D8h] [rbp-28h]
  unsigned __int8 v90[8]; // [rsp+E0h] [rbp-20h] BYREF
  int v91; // [rsp+E8h] [rbp-18h]

  v89 = a8;
  v87 = a9;
  *(_QWORD *)v90 = a10;
  v14 = 0;
  v78 = a4;
  v80 = 0;
  v79 = 0;
  v75 = 0;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v75);
  v15 = 0;
  v83 = 0;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v83);
  v16 = *((_DWORD *)this + 26);
  LODWORD(v76) = *((_DWORD *)this + 27);
  v81 = 0;
  v73 = 0;
  v77 = 0;
  Instance = PipelineClock::GetInstance();
  v20 = a11;
  *((_DWORD *)this + 8) = a11;
  v88 = Instance;
  if ( a2 )
  {
    SourceForCompress = HevcCompressor::GetSourceForCompress(
                          (Hevc420Compressor *)((char *)this - 48),
                          a2,
                          &v83,
                          &v75,
                          &v77);
    if ( SourceForCompress < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_134;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(v20);
      v23 = 21;
      v24 = "GetSourceForCompress failed";
      goto LABEL_7;
    }
    v14 = v75;
    v15 = v83;
    a3 = v77;
  }
  else
  {
    if ( !a3 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_15;
      }
      v25 = RdpX_GetActivityIdPrefix(a11);
      v26 = 22;
      v27 = "pSrcImg";
      goto LABEL_14;
    }
    v77 = a3;
  }
  if ( !*((_QWORD *)this + 2) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_15;
    }
    v25 = RdpX_GetActivityIdPrefix(v20);
    v26 = 23;
    v27 = "m_pHevcCodec";
LABEL_14:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v26,
      (unsigned int)WPP_aab7a5461dc13649fd3f10dadf3c6014_Traceguids,
      v25,
      (__int64)v27);
LABEL_15:
    SourceForCompress = -2147467261;
    goto LABEL_134;
  }
  ++*((_QWORD *)this + 10);
  v28 = (OutputAvc *)*((_QWORD *)this + 3);
  MillisecondCount64 = 0;
  if ( v28 && a3 )
    OutputAvc::OutputRGB(v28, a3);
  if ( (unsigned int)HevcCompressor::IsHardwareEncode(this, 0) && *((_DWORD *)this + 79) != 2 )
    MillisecondCount64 = (const char *)PipelineClock::GetMillisecondCount64(v88);
  AdvanceFeatureMap::CountUpdatingBlocks((Hevc420Compressor *)((char *)this + 168), &v79, &v80);
  v31 = *((double *)this + 12);
  if ( *((_DWORD *)this + 29) )
  {
    v29 = (QueryCPUPerformance *)(unsigned int)a7;
    v32 = (int)((double)a7 * *((double *)this + 9) / v31);
    v85 = (unsigned int)v32;
    v86 = (unsigned int)(int)((double)v32 * *((double *)this + 9) / v31);
    if ( (unsigned int)dword_1801B76C8 > 5 )
    {
      v74 = v32;
      v82 = "Bandwidth:";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        a7,
        (unsigned int)&word_1801A23AE,
        v19,
        v30,
        (__int64)&v82,
        (__int64)&v74);
    }
  }
  else
  {
    LODWORD(v86) = 0;
    if ( v31 <= 0.0 )
    {
      v85 = (unsigned int)a7;
    }
    else
    {
      v33 = *((double *)this + 9);
      LODWORD(v86) = (int)((double)a6 * v33 / 125.0);
      LODWORD(v85) = (int)((double)a7 * *((double *)this + 9) / v31);
      Helper::TracePipelineBitrate(a6, v31, v33);
    }
  }
  v34 = *(_QWORD *)(*((_QWORD *)this + 2) + 152LL);
  if ( v34 )
    *(_QWORD *)(v34 + 120) = QueryCPUPerformance::QueryCounter(v29);
  if ( *((_DWORD *)this + 80) )
  {
    v42 = *((_QWORD *)this + 11) * *((_QWORD *)this + 10);
    if ( !v14 )
    {
      if ( !(_DWORD)v76 )
        goto LABEL_109;
      if ( v15 )
      {
        SourceForCompress = (*(__int64 (__fastcall **)(_QWORD, struct ID3D11Texture2D *, _QWORD, struct IRdpBoundsAccumulator *, __int64, struct IMFSample **))(**((_QWORD **)this + 1) + 8LL))(
                              *((_QWORD *)this + 1),
                              v15,
                              0,
                              v78,
                              v42,
                              &v81);
        if ( SourceForCompress < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_134;
          }
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(v51);
          v23 = 29;
LABEL_72:
          v24 = "m_pColorConversion->Execute (using HW XVP converter) failed";
          goto LABEL_7;
        }
      }
      else
      {
        v18 = v77;
        if ( !v77 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_15;
          }
          v25 = RdpX_GetActivityIdPrefix(v29);
          v26 = 30;
          v27 = "pFrameImg";
          goto LABEL_14;
        }
        SourceForCompress = (*(__int64 (__fastcall **)(_QWORD, struct PixelMap *, struct IRdpBoundsAccumulator *, struct IMFSample **))(**((_QWORD **)this + 1) + 24LL))(
                              *((_QWORD *)this + 1),
                              v77,
                              v78,
                              &v81);
        if ( SourceForCompress < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_134;
          }
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(v52);
          v23 = 31;
          v24 = "m_pColorConversion->Execute (HW Shader, PixelMap input) failed";
          goto LABEL_7;
        }
      }
      v53 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD))v81->lpVtbl->SetSampleTime)(
              v81,
              *((_QWORD *)this + 11) * *((_QWORD *)this + 10));
      if ( v53 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v54 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        LODWORD(v72) = v53;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          (unsigned int)WPP_aab7a5461dc13649fd3f10dadf3c6014_Traceguids,
          v54,
          (__int64)"spInputSample->SetSampleTime() failed.  Non-Fatal.",
          v72);
      }
      v73 = v81;
      goto LABEL_109;
    }
    SourceForCompress = (*(__int64 (__fastcall **)(_QWORD, struct ID3D11Texture2D *, struct ID3D11ShaderResourceView *, struct IRdpBoundsAccumulator *, __int64, struct IMFSample **))(**((_QWORD **)this + 1) + 8LL))(
                          *((_QWORD *)this + 1),
                          v15,
                          v14,
                          v78,
                          v42,
                          &v73);
    if ( SourceForCompress < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_134;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(v43);
      v23 = 26;
      goto LABEL_72;
    }
    v45 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD))v73->lpVtbl->SetSampleTime)(
            v73,
            *((_QWORD *)this + 11) * *((_QWORD *)this + 10));
    if ( v45 < 0 )
    {
      v47 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_79;
      }
      v48 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(v72) = v45;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        (unsigned int)WPP_aab7a5461dc13649fd3f10dadf3c6014_Traceguids,
        v48,
        (__int64)"spInputSample->SetSampleTime() failed.  Non-Fatal.",
        v72);
    }
    v47 = (PVOID *)WPP_GLOBAL_Control;
LABEL_79:
    v49 = v73;
    if ( v73 != *((struct IMFSample **)this + 33) )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 264, v44, v46);
      *((_QWORD *)this + 33) = v49;
      TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 264);
      v47 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v47 != &WPP_GLOBAL_Control && (*((_DWORD *)v47 + 7) & 0x100) != 0 && *((_BYTE *)v47 + 25) >= 5u )
    {
      v50 = RdpX_GetActivityIdPrefix(v47);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_aab7a5461dc13649fd3f10dadf3c6014_Traceguids, v50);
    }
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v75, v44, v46);
    v75 = 0;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v75);
    goto LABEL_109;
  }
  v35 = *((_QWORD *)this + 33);
  if ( !v16 )
  {
    if ( !v35 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_15;
      }
      v25 = RdpX_GetActivityIdPrefix(v29);
      v26 = 33;
LABEL_43:
      v27 = "m_spInputSample";
      goto LABEL_14;
    }
    v38 = *((_QWORD *)this + 1);
    v73 = (struct IMFSample *)*((_QWORD *)this + 33);
    SourceForCompress = (*(__int64 (__fastcall **)(__int64, struct PixelMap *, struct IRdpBoundsAccumulator *, struct IMFSample **))(*(_QWORD *)v38 + 24LL))(
                          v38,
                          v77,
                          v78,
                          &v73);
    if ( SourceForCompress >= 0 )
    {
      v40 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 33) + 288LL))(
              *((_QWORD *)this + 33),
              *((_QWORD *)this + 10) * *((_QWORD *)this + 11));
      if ( v40 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v41 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        LODWORD(v72) = v40;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          (unsigned int)WPP_aab7a5461dc13649fd3f10dadf3c6014_Traceguids,
          v41,
          (__int64)"spInputSample->SetSampleTime() failed.  Non-Fatal.",
          v72);
      }
      goto LABEL_109;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_134;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(v39);
    v23 = 34;
    v24 = "m_pColorConversion->Execute (IMFSample) failed";
LABEL_7:
    LODWORD(v72) = SourceForCompress;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v23,
      (unsigned int)WPP_aab7a5461dc13649fd3f10dadf3c6014_Traceguids,
      ActivityIdPrefix,
      (__int64)v24,
      v72);
LABEL_134:
    v66 = (OutputAvc *)*((_QWORD *)this + 3);
    if ( v66 )
      OutputAvc::`scalar deleting destructor'(v66, (unsigned int)v18);
    *((_QWORD *)this + 3) = 0;
    goto LABEL_137;
  }
  if ( !v35 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_15;
    }
    v25 = RdpX_GetActivityIdPrefix(v29);
    v26 = 24;
    goto LABEL_43;
  }
  v73 = (struct IMFSample *)*((_QWORD *)this + 33);
  SourceForCompress = Hevc420Compressor::CopyPixelMapToMFSample((Hevc420Compressor *)((char *)this - 48), v77, v78, v73);
  if ( SourceForCompress < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_134;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(v36);
    v23 = 25;
    v24 = "CopyPixelMapToMFSample failed";
    goto LABEL_7;
  }
  if ( (unsigned int)dword_1801B76C8 > 5 )
  {
    v82 = "Successfully created IMF sample with color conversion disabled.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v36,
      (unsigned int)&word_1801A2356,
      v19,
      v37,
      (__int64)&v82);
  }
LABEL_109:
  v55 = *(OutputAvc **)(*((_QWORD *)this + 2) + 152LL);
  if ( v55 )
    OutputAvc::GetCVTPerfCount(v55);
  v56 = *((_QWORD *)this + 2);
  v57 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, struct IMFSample **, unsigned __int8 *, unsigned __int8 *, char *, _DWORD, _DWORD))(*(_QWORD *)v56 + 32LL);
  v76 = v73;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v76);
  v58 = v87;
  SourceForCompress = v57(v56, a5, 0, (unsigned int)v86, v85, &v76, v89, v87, (char *)this + 168, 0, 0);
  if ( SourceForCompress < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_134;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(v59);
    v23 = 36;
    v24 = "Compress using MFT encoder failed";
    goto LABEL_7;
  }
  v60 = *((_QWORD *)this + 37);
  if ( v60 )
    (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v60 + 328LL))(
      v60,
      *((unsigned int *)this + 20),
      (char *)this + 168);
  Hevc420Compressor::UpdateFeatureMap((Hevc420Compressor *)((char *)this - 48));
  AdvanceFeatureMap::ClearDirty((Hevc420Compressor *)((char *)this + 168));
  HevcCompressor::UpdateCompressionEstimationState((Hevc420Compressor *)((char *)this - 48), *(_DWORD *)v58, v80, v79);
  SourceForCompress = (*(__int64 (__fastcall **)(struct IRdpBoundsAccumulator *, _QWORD))(*(_QWORD *)v78 + 152LL))(
                        v78,
                        *(_QWORD *)v90);
  if ( SourceForCompress < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_134;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(v61);
    v23 = 37;
    v24 = "GetBoundingBox failed";
    goto LABEL_7;
  }
  if ( (unsigned int)HevcCompressor::IsHardwareEncode(this, 0) )
  {
    if ( *((_DWORD *)this + 79) != 2 )
    {
      v62 = PipelineClock::GetMillisecondCount64(v88);
      v64 = v62 - (_QWORD)MillisecondCount64;
      if ( v64 > 0x64 && (unsigned int)dword_1801B76C8 > 2 )
      {
        *(_QWORD *)v90 = v64;
        LODWORD(v76) = 459;
        v87 = "Compress";
        v82 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\hevccodec\\hevc420compressor.cpp";
        MillisecondCount64 = "HW encode took long time. (Non-fatal)";
        v74 = SourceForCompress;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          dword_1801B76C8,
          (unsigned int)&dword_1801A22F4,
          v19,
          v63,
          (__int64)&MillisecondCount64,
          (__int64)&v74,
          (__int64)&v82,
          (__int64)&v76,
          (__int64)&v87,
          (__int64)v90);
      }
    }
  }
  v65 = (OutputAvc *)*((_QWORD *)this + 3);
  if ( v65 && *(_DWORD *)v58 )
  {
    if ( *((_QWORD *)this + 10) == 1 )
    {
      *(_DWORD *)&v90[4] = *((_DWORD *)this + 13);
      v91 = *((_DWORD *)this + 14);
      *(_DWORD *)v90 = 0;
      OutputAvc::OutputRdpAvcStreams(v65, v90, 12);
    }
    OutputAvc::OutputRdpAvcStreams(*((OutputAvc **)this + 3), v58, 4);
    OutputAvc::OutputRdpAvcStreams(*((OutputAvc **)this + 3), v89, *(_DWORD *)v58);
  }
  if ( SourceForCompress )
    goto LABEL_134;
LABEL_137:
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v81, v18, v19);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v83, v67, v68);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v75, v69, v70);
  return (unsigned int)SourceForCompress;
}

```

## disassembly

```asm
0x180092110  push    rbp
0x180092112  push    rbx
0x180092113  push    rsi
0x180092114  push    rdi
0x180092115  push    r12
0x180092117  push    r13
0x180092119  push    r14
0x18009211b  push    r15
0x18009211d  lea     rbp, [rsp-8]
0x180092122  sub     rsp, 108h
0x180092129  mov     rax, cs:__security_cookie
0x180092130  xor     rax, rsp
0x180092133  mov     [rbp+40h+var_50], rax
0x180092137  mov     rax, [rbp+40h+arg_38]
0x18009213e  xor     r12d, r12d
0x180092141  mov     [rbp+40h+var_68], rax
0x180092145  mov     rsi, rcx
0x180092148  mov     rax, [rbp+40h+arg_40]
0x18009214f  lea     rcx, [rsp+140h+var_D0]
0x180092154  mov     [rbp+40h+var_78], rax
0x180092158  mov     r14, r8
0x18009215b  mov     rax, [rbp+40h+arg_48]
0x180092162  mov     r15, rdx
0x180092165  mov     qword ptr [rbp+40h+var_60], rax
0x180092169  mov     edi, r12d
0x18009216c  mov     [rbp+40h+var_B8], r9
0x180092170  mov     [rbp+40h+var_AC], r12d
0x180092174  mov     [rbp+40h+var_B0], r12d
0x180092178  mov     [rsp+140h+var_D0], r12
0x18009217d  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180092182  mov     ebx, r12d
0x180092185  lea     rcx, [rbp+40h+var_98]
0x180092189  mov     [rbp+40h+var_98], rbx
0x18009218d  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180092192  mov     eax, [rsi+6Ch]
0x180092195  mov     r13d, [rsi+68h]
0x180092199  mov     dword ptr [rsp+140h+var_C8], eax
0x18009219d  mov     [rbp+40h+var_A8], r12
0x1800921a1  mov     [rsp+140h+var_E0], r12
0x1800921a6  mov     [rbp+40h+var_C0], r12
0x1800921aa  call    ?GetInstance@PipelineClock@@SAAEAV1@XZ; PipelineClock::GetInstance(void)
0x1800921af  mov     ecx, [rbp+40h+arg_50]
0x1800921b5  mov     [rsi+20h], ecx
0x1800921b8  mov     [rbp+40h+var_70], rax
0x1800921bc  test    r15, r15
0x1800921bf  jz      loc_180092260
0x1800921c5  lea     rax, [rbp+40h+var_C0]
0x1800921c9  mov     rdx, r15; struct RdpSurface *
0x1800921cc  lea     r9, [rsp+140h+var_D0]; struct ID3D11ShaderResourceView **
0x1800921d1  mov     [rsp+140h+var_120], rax; struct PixelMap **
0x1800921d6  lea     r8, [rbp+40h+var_98]; struct ID3D11Texture2D **
0x1800921da  lea     rcx, [rsi-30h]; this
0x1800921de  call    ?GetSourceForCompress@HevcCompressor@@IEAAJPEAVRdpSurface@@PEAPEAUID3D11Texture2D@@PEAPEAUID3D11ShaderResourceView@@PEAPEAVPixelMap@@@Z; HevcCompressor::GetSourceForCompress(RdpSurface *,ID3D11Texture2D * *,ID3D11ShaderResourceView * *,PixelMap * *)
0x1800921e3  mov     ebx, eax
0x1800921e5  test    eax, eax
0x1800921e7  jns     short loc_180092251
0x1800921e9  mov     rax, cs:WPP_GLOBAL_Control
0x1800921f0  lea     r14, WPP_GLOBAL_Control
0x1800921f7  cmp     rax, r14
0x1800921fa  jz      loc_180092BFC
0x180092200  mov     r15b, 8
0x180092203  test    [rax+1Ch], r15b
0x180092207  jz      loc_180092BFC
0x18009220d  cmp     byte ptr [rax+19h], 2
0x180092211  jb      loc_180092BFC
0x180092217  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18009221d  lea     edx, [r12+15h]
0x180092222  lea     rcx, aGetsourceforco; "GetSourceForCompress failed"
0x180092229  lea     r8, WPP_aab7a5461dc13649fd3f10dadf3c6014_Traceguids
0x180092230  mov     dword ptr [rsp+140h+var_118], ebx
0x180092234  mov     r9d, eax
0x180092237  mov     [rsp+140h+var_120], rcx
0x18009223c  mov     rcx, cs:WPP_GLOBAL_Control
0x180092243  mov     rcx, [rcx+10h]
0x180092247  call    WPP_SF_DsD
0x18009224c  jmp     loc_180092BFC
0x180092251  mov     rdi, [rsp+140h+var_D0]
0x180092256  mov     rbx, [rbp+40h+var_98]
0x18009225a  mov     r14, [rbp+40h+var_C0]
0x18009225e  jmp     short loc_1800922C6
0x180092260  test    r14, r14
0x180092263  jnz     short loc_1800922C2
0x180092265  mov     rax, cs:WPP_GLOBAL_Control
0x18009226c  lea     r14, WPP_GLOBAL_Control
0x180092273  cmp     rax, r14
0x180092276  jz      short loc_1800922B8
0x180092278  mov     r15b, 8
0x18009227b  test    [rax+1Ch], r15b
0x18009227f  jz      short loc_1800922B8
0x180092281  cmp     byte ptr [rax+19h], 2
0x180092285  jb      short loc_1800922B8
0x180092287  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18009228d  mov     edx, 16h
0x180092292  lea     rcx, aPsrcimg; "pSrcImg"
0x180092299  lea     r8, WPP_aab7a5461dc13649fd3f10dadf3c6014_Traceguids
0x1800922a0  mov     [rsp+140h+var_120], rcx
0x1800922a5  mov     r9d, eax
0x1800922a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800922af  mov     rcx, [rcx+10h]
0x1800922b3  call    WPP_SF_Ds
0x1800922b8  mov     ebx, 80004003h
0x1800922bd  jmp     loc_180092BFC
0x1800922c2  mov     [rbp+40h+var_C0], r14
0x1800922c6  cmp     [rsi+10h], r12
0x1800922ca  jnz     short loc_180092302
0x1800922cc  mov     rax, cs:WPP_GLOBAL_Control
0x1800922d3  lea     r14, WPP_GLOBAL_Control
0x1800922da  cmp     rax, r14
0x1800922dd  jz      short loc_1800922B8
0x1800922df  mov     r15b, 8
0x1800922e2  test    [rax+1Ch], r15b
0x1800922e6  jz      short loc_1800922B8
0x1800922e8  cmp     byte ptr [rax+19h], 2
0x1800922ec  jb      short loc_1800922B8
0x1800922ee  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800922f4  mov     edx, 17h
0x1800922f9  lea     rcx, aMPhevccodec; "m_pHevcCodec"
0x180092300  jmp     short loc_180092299
0x180092302  inc     qword ptr [rsi+50h]
0x180092306  mov     rcx, [rsi+18h]; this
0x18009230a  mov     [rbp+40h+var_90], r12
0x18009230e  test    rcx, rcx
0x180092311  jz      short loc_180092320
0x180092313  test    r14, r14
0x180092316  jz      short loc_180092320
0x180092318  mov     rdx, r14; struct PixelMap *
0x18009231b  call    ?OutputRGB@OutputAvc@@QEAAXPEAVPixelMap@@@Z; OutputAvc::OutputRGB(PixelMap *)
0x180092320  xor     edx, edx; unsigned __int16 **
0x180092322  mov     rcx, rsi; this
0x180092325  call    ?IsHardwareEncode@HevcCompressor@@UEAAHPEAPEAG@Z; HevcCompressor::IsHardwareEncode(ushort * *)
0x18009232a  test    eax, eax
0x18009232c  jz      short loc_180092344
0x18009232e  cmp     dword ptr [rsi+13Ch], 2
0x180092335  jz      short loc_180092344
0x180092337  mov     rcx, [rbp+40h+var_70]; this
0x18009233b  call    ?GetMillisecondCount64@PipelineClock@@QEAA_KXZ; PipelineClock::GetMillisecondCount64(void)
0x180092340  mov     [rbp+40h+var_90], rax
0x180092344  lea     rcx, [rsi+0A8h]; this
0x18009234b  lea     r8, [rbp+40h+var_AC]; unsigned int *
0x18009234f  lea     rdx, [rbp+40h+var_B0]; unsigned int *
0x180092353  call    ?CountUpdatingBlocks@AdvanceFeatureMap@@QEAAXPEAI0@Z; AdvanceFeatureMap::CountUpdatingBlocks(uint *,uint *)
0x180092358  movsd   xmm1, qword ptr [rsi+60h]; double
0x18009235d  cmp     [rsi+74h], r12d
0x180092361  jz      short loc_1800923E0
0x180092363  mov     ecx, [rbp+40h+arg_30]
0x180092369  xorps   xmm0, xmm0
0x18009236c  cvtsi2sd xmm0, rcx
0x180092371  mulsd   xmm0, qword ptr [rsi+48h]
0x180092376  divsd   xmm0, xmm1
0x18009237a  cvttsd2si r15, xmm0
0x18009237f  xorps   xmm0, xmm0
0x180092382  mov     eax, r15d
0x180092385  mov     [rbp+40h+var_88], r15
0x180092389  cvtsi2sd xmm0, rax
0x18009238e  mov     eax, cs:dword_1801B76C8
0x180092394  mulsd   xmm0, qword ptr [rsi+48h]
0x180092399  divsd   xmm0, xmm1
0x18009239d  cvttsd2si r12, xmm0
0x1800923a2  mov     [rbp+40h+var_80], r12
0x1800923a6  cmp     eax, 5
0x1800923a9  jbe     loc_180092443
0x1800923af  lea     rax, aBandwidth; "Bandwidth:"
0x1800923b6  mov     [rsp+140h+var_D8], r15d
0x1800923bb  mov     [rbp+40h+var_A0], rax
0x1800923bf  lea     rdx, word_1801A23AE
0x1800923c6  lea     rax, [rsp+140h+var_D8]
0x1800923cb  mov     [rsp+140h+var_118], rax
0x1800923d0  lea     rax, [rbp+40h+var_A0]
0x1800923d4  mov     [rsp+140h+var_120], rax
0x1800923d9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800923de  jmp     short loc_180092443
0x1800923e0  comisd  xmm1, cs:__real@0000000000000000
0x1800923e8  mov     dword ptr [rbp+40h+var_80], r12d
0x1800923ec  jbe     short loc_180092439
0x1800923ee  mov     ecx, [rbp+40h+arg_28]; unsigned int
0x1800923f1  xorps   xmm0, xmm0
0x1800923f4  movsd   xmm2, qword ptr [rsi+48h]; double
0x1800923f9  cvtsi2sd xmm0, rcx
0x1800923fe  mulsd   xmm0, qword ptr [rsi+48h]
0x180092403  divsd   xmm0, cs:__real@405f400000000000
0x18009240b  cvttsd2si rax, xmm0
0x180092410  xorps   xmm0, xmm0
0x180092413  mov     dword ptr [rbp+40h+var_80], eax
0x180092416  mov     eax, [rbp+40h+arg_30]
0x18009241c  cvtsi2sd xmm0, rax
0x180092421  mulsd   xmm0, qword ptr [rsi+48h]
0x180092426  divsd   xmm0, xmm1
0x18009242a  cvttsd2si rax, xmm0
0x18009242f  mov     dword ptr [rbp+40h+var_88], eax
0x180092432  call    ?TracePipelineBitrate@Helper@@SAXKNN@Z; Helper::TracePipelineBitrate(ulong,double,double)
0x180092437  jmp     short loc_180092443
0x180092439  mov     eax, [rbp+40h+arg_30]
0x18009243f  mov     [rbp+40h+var_88], rax
0x180092443  mov     rax, [rsi+10h]
0x180092447  mov     r14, [rax+98h]
0x18009244e  test    r14, r14
0x180092451  jz      short loc_18009245C
0x180092453  call    ?QueryCounter@QueryCPUPerformance@@QEAA_JXZ; QueryCPUPerformance::QueryCounter(void)
0x180092458  mov     [r14+78h], rax
0x18009245c  cmp     dword ptr [rsi+140h], 0
0x180092463  lea     r12, WPP_aab7a5461dc13649fd3f10dadf3c6014_Traceguids
0x18009246a  mov     r15b, 8
0x18009246d  lea     r14, WPP_GLOBAL_Control
0x180092474  jnz     loc_18009267D
0x18009247a  mov     rax, [rsi+108h]
0x180092481  test    r13d, r13d
0x180092484  jz      loc_18009255E
0x18009248a  test    rax, rax
0x18009248d  jnz     short loc_1800924CD
0x18009248f  mov     rax, cs:WPP_GLOBAL_Control
0x180092496  cmp     rax, r14
0x180092499  jz      loc_1800922B8
0x18009249f  test    [rax+1Ch], r15b
0x1800924a3  jz      loc_1800922B8
0x1800924a9  cmp     byte ptr [rax+19h], 2
0x1800924ad  jb      loc_1800922B8
0x1800924b3  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800924b9  mov     edx, 18h
0x1800924be  lea     rcx, aMSpinputsample_0; "m_spInputSample"
0x1800924c5  mov     r8, r12
0x1800924c8  jmp     loc_1800922A0
0x1800924cd  mov     r8, [rbp+40h+var_B8]; struct IRdpBoundsAccumulator *
0x1800924d1  lea     rcx, [rsi-30h]; this
0x1800924d5  mov     rdx, [rbp+40h+var_C0]; struct PixelMap *
0x1800924d9  mov     r9, rax; struct IMFSample *
0x1800924dc  mov     [rsp+140h+var_E0], rax
0x1800924e1  call    ?CopyPixelMapToMFSample@Hevc420Compressor@@AEAAJPEAVPixelMap@@PEAVIRdpBoundsAccumulator@@PEAUIMFSample@@@Z; Hevc420Compressor::CopyPixelMapToMFSample(PixelMap *,IRdpBoundsAccumulator *,IMFSample *)
0x1800924e6  mov     ebx, eax
0x1800924e8  test    eax, eax
0x1800924ea  jns     short loc_18009252A
0x1800924ec  mov     rax, cs:WPP_GLOBAL_Control
0x1800924f3  cmp     rax, r14
0x1800924f6  jz      loc_180092BFC
0x1800924fc  test    [rax+1Ch], r15b
0x180092500  jz      loc_180092BFC
0x180092506  cmp     byte ptr [rax+19h], 2
0x18009250a  jb      loc_180092BFC
0x180092510  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180092516  mov     edx, 19h
0x18009251b  lea     rcx, aCopypixelmapto; "CopyPixelMapToMFSample failed"
0x180092522  mov     r8, r12
0x180092525  jmp     loc_180092230
0x18009252a  mov     eax, cs:dword_1801B76C8
0x180092530  cmp     eax, 5
0x180092533  jbe     loc_180092975
0x180092539  lea     rax, aSuccessfullyCr; "Successfully created IMF sample with co"...
0x180092540  mov     [rbp+40h+var_A0], rax
0x180092544  lea     rdx, word_1801A2356
0x18009254b  lea     rax, [rbp+40h+var_A0]
0x18009254f  mov     [rsp+140h+var_120], rax
0x180092554  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180092559  jmp     loc_180092975
0x18009255e  test    rax, rax
0x180092561  jnz     short loc_180092597
0x180092563  mov     rax, cs:WPP_GLOBAL_Control
0x18009256a  cmp     rax, r14
0x18009256d  jz      loc_1800922B8
0x180092573  test    [rax+1Ch], r15b
0x180092577  jz      loc_1800922B8
0x18009257d  cmp     byte ptr [rax+19h], 2
0x180092581  jb      loc_1800922B8
0x180092587  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18009258d  mov     edx, 21h ; '!'
0x180092592  jmp     loc_1800924BE
0x180092597  mov     rcx, [rsi+8]
0x18009259b  lea     r9, [rsp+140h+var_E0]
0x1800925a0  mov     r8, [rbp+40h+var_B8]
0x1800925a4  mov     rdx, [rbp+40h+var_C0]
0x1800925a8  mov     [rsp+140h+var_E0], rax
0x1800925ad  mov     rax, [rcx]
0x1800925b0  mov     rax, [rax+18h]
0x1800925b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800925b9  mov     ebx, eax
0x1800925bb  test    eax, eax
0x1800925bd  jns     short loc_1800925FA
0x1800925bf  mov     rax, cs:WPP_GLOBAL_Control
0x1800925c6  cmp     rax, r14
0x1800925c9  jz      loc_180092BFC
0x1800925cf  test    [rax+1Ch], r15b
0x1800925d3  jz      loc_180092BFC
0x1800925d9  cmp     byte ptr [rax+19h], 2
0x1800925dd  jb      loc_180092BFC
0x1800925e3  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800925e9  mov     edx, 22h ; '"'
0x1800925ee  lea     rcx, aMPcolorconvers_1; "m_pColorConversion->Execute (IMFSample)"...
0x1800925f5  jmp     loc_180092522
0x1800925fa  mov     rdx, [rsi+58h]
0x1800925fe  mov     rcx, [rsi+108h]
0x180092605  imul    rdx, [rsi+50h]
0x18009260a  mov     rax, [rcx]
0x18009260d  mov     rax, [rax+120h]
0x180092614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092619  mov     ebx, eax
0x18009261b  test    eax, eax
0x18009261d  jns     loc_180092975
0x180092623  mov     rcx, cs:WPP_GLOBAL_Control
0x18009262a  cmp     rcx, r14
0x18009262d  jz      loc_180092975
0x180092633  test    [rcx+1Ch], r15b
0x180092637  jz      loc_180092975
  ... truncated ...
```
