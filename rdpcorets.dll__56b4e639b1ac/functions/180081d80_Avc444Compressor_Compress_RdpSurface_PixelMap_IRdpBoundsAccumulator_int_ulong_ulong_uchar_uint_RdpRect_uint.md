# Avc444Compressor::Compress(RdpSurface *,PixelMap *,IRdpBoundsAccumulator *,int,ulong,ulong,uchar *,uint *,RdpRect *,uint)

- ea: `0x180081d80`
- end: `0x180082efd`
- name: `?Compress@Avc444Compressor@@UEAAJPEAVRdpSurface@@PEAVPixelMap@@PEAVIRdpBoundsAccumulator@@HKKPEAEPEAIPEAURdpRect@@I@Z`
- size: `4477`
- prototype: `int(Avc444Compressor *__hidden this, struct RdpSurface *, struct PixelMap *, struct IRdpBoundsAccumulator *, int, unsigned int, unsigned int, unsigned __int8 *, unsigned int *, struct RdpRect *, unsigned int)`
- caller_count: `0`
- callee_count: `28`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800015f0`
- `0x180003aac`
- `0x1800071c0`
- `0x1800071f0`
- `0x1800093f0`
- `0x1800144dc`
- `0x180014b30`
- `0x180017890`
- `0x180017928`
- `0x1800194b0`
- `0x180019758`
- `0x180025b80`
- `0x18002c1b0`
- `0x18002c29c`
- `0x180032f60`
- `0x180033da0`
- `0x180059838`
- `0x18007a800`
- `0x18007d060`
- `0x180081d80`
- `0x1800836fc`
- `0x180083b48`
- `0x180083bac`
- `0x1800b8804`
- `0x1800d9cc0`
- `0x1800d9cf4`
- `0x1800d9de0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082eb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082eb2`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180081ee6`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008211f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800823ba`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800827e6`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180082c66`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180082df5`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180081ee6`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008211f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800823ba`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800827e6`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180082c66`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180082df5`

## string_xrefs

- `0x180081e41`: `GetSourceForCompress failed`
- `0x180081e5f`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avc444compressor.cpp`
- `0x180081f5b`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avc444compressor.cpp`
- `0x180082005`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avc444compressor.cpp`
- `0x18008232c`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avc444compressor.cpp`
- `0x180082493`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avc444compressor.cpp`
- `0x180082568`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avc444compressor.cpp`
- `0x1800825f4`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avc444compressor.cpp`
- `0x18008267a`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avc444compressor.cpp`
- `0x180082752`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avc444compressor.cpp`
- `0x180082851`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avc444compressor.cpp`
- `0x18008298b`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avc444compressor.cpp`
- `0x180082adc`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avc444compressor.cpp`
- `0x180082d4a`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avc444compressor.cpp`
- `0x180081ea9`: `Compress`
- `0x180081f54`: `Compress`
- `0x18008248c`: `Compress`
- `0x18008284a`: `Compress`
- `0x180082984`: `Compress`
- `0x180082ad5`: `Compress`
- `0x180082d3f`: `Compress`
- `0x180082044`: `Compressed size is larger than the allocated output sample size.`

## pseudocode

```c
__int64 __fastcall Avc444Compressor::Compress(
        Avc444Compressor *this,
        struct RdpSurface *a2,
        struct PixelMap *a3,
        struct IRdpBoundsAccumulator *a4,
        int a5,
        int a6,
        signed int a7,
        unsigned __int8 *a8,
        unsigned __int8 *a9,
        struct RdpRect *a10,
        unsigned int a11)
{
  struct ID3D11ShaderResourceView *v12; // rbx
  PipelineClock *Instance; // rax
  __int64 v17; // r8
  int v18; // r9d
  _DWORD *v19; // r12
  __int64 v20; // rdx
  __int64 v21; // rcx
  int SourceForCompress; // esi
  const char *v23; // rax
  char *v24; // rdx
  const char *v25; // rax
  int *v26; // rax
  unsigned int *v27; // rax
  PVOID *v28; // rdx
  unsigned int ActivityIdPrefix; // eax
  OutputAvc *v30; // rcx
  unsigned __int64 MillisecondCount64; // rax
  double v32; // xmm1_8
  int v33; // esi
  unsigned int v34; // eax
  double v35; // xmm2_8
  QueryCPUPerformance *v36; // rcx
  QueryCPUPerformance *v37; // rcx
  unsigned int v38; // eax
  unsigned __int8 *v39; // r14
  BOOL v40; // eax
  bool v41; // zf
  __int64 *v42; // rax
  __int64 v43; // r10
  unsigned int v44; // eax
  const char *v45; // rsi
  const char *v46; // rsi
  int v47; // r9d
  const char *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // r8
  __int64 v51; // r9
  unsigned int v52; // eax
  int v53; // r9d
  unsigned __int8 *v54; // r15
  __int64 v55; // rcx
  _DWORD *v56; // rbx
  Avc444Compressor *v57; // rcx
  int v58; // r9d
  __int64 v59; // rcx
  int v60; // r9d
  unsigned int v61; // ecx
  unsigned int v62; // eax
  unsigned int v63; // eax
  int v64; // eax
  unsigned __int8 *v65; // r15
  unsigned __int64 v66; // rax
  int v67; // r9d
  __int64 v68; // rbx
  unsigned __int64 v69; // r14
  int v70; // ebx
  unsigned int v71; // eax
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // rax
  __int64 v75; // rbx
  __int64 v76; // r14
  float v77; // xmm0_4
  float v78; // xmm1_4
  unsigned int v79; // ecx
  unsigned int v80; // eax
  OutputAvc *v81; // rcx
  struct RdpRect *v82; // rcx
  OutputAvc *v83; // rcx
  unsigned __int8 **v85; // [rsp+28h] [rbp-D8h]
  unsigned int *v86; // [rsp+30h] [rbp-D0h]
  unsigned __int8 *v87; // [rsp+38h] [rbp-C8h]
  int v88; // [rsp+40h] [rbp-C0h]
  unsigned int v89; // [rsp+60h] [rbp-A0h] BYREF
  PipelineClock *v90; // [rsp+68h] [rbp-98h] BYREF
  const char *v91; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v92; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 *v93; // [rsp+80h] [rbp-80h] BYREF
  int v94; // [rsp+88h] [rbp-78h] BYREF
  const char *v95; // [rsp+90h] [rbp-70h] BYREF
  const char *v96; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v97; // [rsp+A0h] [rbp-60h] BYREF
  const char *v98; // [rsp+A8h] [rbp-58h] BYREF
  const char *v99; // [rsp+B0h] [rbp-50h] BYREF
  int v100; // [rsp+B8h] [rbp-48h] BYREF
  struct ID3D11ShaderResourceView *v101; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v102[2]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v103[2]; // [rsp+D0h] [rbp-30h] BYREF
  struct PixelMap *v104; // [rsp+D8h] [rbp-28h] BYREF
  int v105; // [rsp+E0h] [rbp-20h] BYREF
  struct RdpRect *v106; // [rsp+E8h] [rbp-18h]
  unsigned __int8 *v107; // [rsp+F0h] [rbp-10h] BYREF
  int v108; // [rsp+F8h] [rbp-8h]

  v106 = a10;
  v12 = 0;
  v93 = a8;
  v100 = 0;
  v101 = 0;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v101);
  v104 = 0;
  Instance = PipelineClock::GetInstance();
  v19 = (_DWORD *)((char *)this - 48);
  *((_DWORD *)this + 8) = a11;
  v90 = Instance;
  if ( a2 )
  {
    SourceForCompress = AvcCompressor::GetSourceForCompress(
                          (Avc444Compressor *)((char *)this - 48),
                          a2,
                          &v101,
                          &v104,
                          &v100);
    if ( SourceForCompress < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_161;
      v23 = "GetSourceForCompress failed";
      v89 = 488;
      v24 = byte_18019F439;
LABEL_5:
      v94 = SourceForCompress;
LABEL_6:
      v91 = v23;
      v96 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avc444compressor.cpp";
      v25 = "Error HResult failed";
LABEL_7:
      v95 = v25;
      v87 = (unsigned __int8 *)&v89;
      v86 = (unsigned int *)&v96;
      v26 = &v94;
LABEL_8:
      v85 = (unsigned __int8 **)v26;
      v27 = (unsigned int *)&v95;
LABEL_9:
      v90 = (PipelineClock *)"Compress";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)"Compress",
        (_DWORD)v24,
        v17,
        v18,
        (__int64)v27,
        (__int64)v85,
        (__int64)v86,
        (__int64)v87,
        (__int64)&v90,
        (__int64)&v91);
      goto LABEL_161;
    }
    v28 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    {
      v12 = v101;
      a3 = v104;
      goto LABEL_21;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(v21);
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      &WPP_5d037097164339a27202bb0efcb23f22_Traceguids,
      ActivityIdPrefix);
    v12 = v101;
    a3 = v104;
  }
  else
  {
    if ( !a3 )
    {
      v20 = 2147500035LL;
      SourceForCompress = -2147467261;
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v89 = -2147467261;
        v91 = "pSrcImg is NULL";
        v90 = (PipelineClock *)"Compress";
        v96 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avc444compressor.cpp";
        v100 = 495;
        v95 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)"Compress",
          (unsigned int)byte_18019F38B,
          v17,
          v18,
          (__int64)&v95,
          (__int64)&v89,
          (__int64)&v96,
          (__int64)&v100,
          (__int64)&v90,
          (__int64)&v91);
      }
      goto LABEL_164;
    }
    v104 = a3;
  }
  v28 = (PVOID *)WPP_GLOBAL_Control;
LABEL_21:
  if ( !*((_QWORD *)this + 2) )
  {
    v20 = 2147500035LL;
    SourceForCompress = -2147467261;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_161;
    v94 = -2147467261;
    v91 = "m_pAvcCodec is NULL";
    v24 = (char *)word_18019F3E2;
    v89 = 500;
    v96 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avc444compressor.cpp";
    v25 = "Error condition failed";
    goto LABEL_7;
  }
  if ( *(_DWORD *)a9 < 4u )
  {
    v20 = 2147942522LL;
    SourceForCompress = -2147024774;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_161;
    v94 = -2147024774;
    v23 = "Compressed size is larger than the allocated output sample size.";
    v24 = (char *)&dword_18019F334;
    v89 = 505;
    goto LABEL_6;
  }
  v30 = (OutputAvc *)*((_QWORD *)this + 3);
  v91 = 0;
  if ( v30 && a3 )
  {
    OutputAvc::OutputRGB(v30, a3);
    v28 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 89) && *((_DWORD *)this + 93) != 2 )
  {
    MillisecondCount64 = PipelineClock::GetMillisecondCount64(v90);
    v28 = (PVOID *)WPP_GLOBAL_Control;
    v91 = (const char *)MillisecondCount64;
  }
  v32 = *((double *)this + 12);
  if ( *((_DWORD *)this + 27) )
  {
    v33 = (int)((double)a7 * *((double *)this + 9) / v32);
    *(_QWORD *)v102 = (unsigned int)v33;
    *(_QWORD *)v103 = (unsigned int)(int)((double)v33 * *((double *)this + 9) / v32);
    if ( v28 != &WPP_GLOBAL_Control && (*((_DWORD *)v28 + 7) & 0x100) != 0 && *((_BYTE *)v28 + 25) >= 5u )
    {
      v34 = RdpX_GetActivityIdPrefix((unsigned int)a7);
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_5d037097164339a27202bb0efcb23f22_Traceguids, v34, v33);
    }
  }
  else
  {
    v103[0] = 0;
    if ( v32 <= 0.0 )
    {
      *(_QWORD *)v102 = (unsigned int)a7;
    }
    else
    {
      v35 = *((double *)this + 9);
      v103[0] = (int)((double)a6 * v35 / 125.0);
      v102[0] = (int)((double)a7 * *((double *)this + 9) / v32);
      Helper::TracePipelineBitrate(a6, v32, v35);
    }
  }
  AvcEncoder::StartPerfCount(*((AvcEncoder **)this + 2));
  if ( !*((_QWORD *)this + 10) )
  {
    *((_QWORD *)this + 60) = QueryCPUPerformance::QueryCounter(v36);
    *((_QWORD *)this + 55) = QueryCPUPerformance::QueryCounter(v37) + 65000;
  }
  v38 = *(_DWORD *)a9 - 4;
  v105 = 0;
  v92 = v38;
  v97 = v38;
  SourceForCompress = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)v19 + 24LL))((char *)this - 48, &v105);
  if ( SourceForCompress < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_161;
    v23 = "Get420Quality is failed";
    v89 = 553;
    v24 = byte_18019F2DD;
    goto LABEL_5;
  }
  v107 = v93;
  v39 = v93 + 4;
  v40 = v105 != 100 || !(*(unsigned int (__fastcall **)(struct IRdpBoundsAccumulator *))(*(_QWORD *)a4 + 136LL))(a4);
  v19[177] = v40;
  if ( !(*((_QWORD *)this + 10) % (__int64)*((unsigned int *)this + 106)) )
    *((_QWORD *)this + 83) = 0;
  if ( *((_DWORD *)this + 165) )
  {
    v41 = *((_DWORD *)this + 89) == 0;
    v94 = 0;
    if ( v41 )
    {
      SourceForCompress = AvcCompressor::AlignSrcRgba((Avc444Compressor *)((char *)this - 48), v104, a4);
      if ( SourceForCompress < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          LODWORD(v93) = 656;
          v99 = "AlignSrcRgba failed";
          v98 = "Compress";
          v91 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avc444compressor.cpp";
          v89 = SourceForCompress;
          v90 = (PipelineClock *)"Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (unsigned int)"Compress",
            (unsigned int)word_18019F12A,
            v17,
            v53,
            (__int64)&v90,
            (__int64)&v89,
            (__int64)&v91,
            (__int64)&v93,
            (__int64)&v98,
            (__int64)&v99);
        }
        goto LABEL_161;
      }
    }
    else if ( v19[102] )
    {
      v42 = (__int64 *)*((_QWORD *)this + 1);
      v95 = 0;
      v96 = 0;
      v43 = *v42;
      if ( v12 )
      {
        SourceForCompress = (*(__int64 (__fastcall **)(__int64 *, struct ID3D11ShaderResourceView *, struct IRdpBoundsAccumulator *, const char **, const char **))v43)(
                              v42,
                              v12,
                              a4,
                              &v95,
                              &v96);
        if ( SourceForCompress < 0 )
        {
          if ( (unsigned int)dword_1801B76C8 <= 2 )
            goto LABEL_161;
          v89 = 589;
          v91 = "m_pColorConversion->Execute (HW Shader, Texture input) failed";
          v24 = &byte_18019F22F;
          LODWORD(v93) = SourceForCompress;
          *(_QWORD *)v103 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avc444compressor.cpp";
          *(_QWORD *)v102 = "Error HResult failed";
          v87 = (unsigned __int8 *)&v89;
          v86 = v103;
          v85 = &v93;
          v27 = v102;
          goto LABEL_9;
        }
        TCntPtr<IRdpSQMLogger>::SafeRelease(&v101, v20, v17);
        v101 = 0;
        TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v101);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v44 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_5d037097164339a27202bb0efcb23f22_Traceguids, v44);
        }
      }
      else
      {
        SourceForCompress = (*(__int64 (__fastcall **)(__int64 *, struct PixelMap *, struct IRdpBoundsAccumulator *, _QWORD, _QWORD, const char **, const char **, _QWORD, _DWORD))(v43 + 16))(
                              v42,
                              v104,
                              a4,
                              0,
                              0,
                              &v95,
                              &v96,
                              0,
                              *((unsigned __int8 *)this + 185));
        if ( SourceForCompress < 0 )
        {
          if ( (unsigned int)dword_1801B76C8 <= 2 )
            goto LABEL_161;
          LODWORD(v93) = 609;
          v91 = "m_pColorConversion->Execute (HW Shader, PixelMap input) failed";
          v24 = (char *)&word_18019F286;
          v89 = SourceForCompress;
          *(_QWORD *)v103 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avc444compressor.cpp";
          *(_QWORD *)v102 = "Error HResult failed";
          v87 = (unsigned __int8 *)&v93;
          v86 = v103;
          v85 = (unsigned __int8 **)&v89;
          v27 = v102;
          goto LABEL_9;
        }
      }
      v45 = v95;
      if ( v95 != *((const char **)this + 38) )
      {
        TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 304, v20, v17);
        *((_QWORD *)this + 38) = v45;
        TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 304);
      }
      v46 = v96;
      if ( v96 != *((const char **)this + 78) )
      {
        TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 624, v20, v17);
        *((_QWORD *)this + 78) = v46;
        TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 624);
      }
    }
    else
    {
      if ( !*((_QWORD *)this + 38) )
      {
        v20 = 2147500035LL;
        SourceForCompress = -2147467261;
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_161;
        v89 = -2147467261;
        v91 = "m_spYUVSample.GetPointer() is NULL";
        v24 = byte_18019F181;
        LODWORD(v93) = 617;
        v96 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avc444compressor.cpp";
        v95 = "Error condition failed";
        v87 = (unsigned __int8 *)&v93;
        v86 = (unsigned int *)&v96;
        v26 = (int *)&v89;
        goto LABEL_8;
      }
      v48 = (const char *)*((_QWORD *)this + 78);
      if ( !v48 )
      {
        v20 = 2147500035LL;
        SourceForCompress = -2147467261;
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_161;
        v89 = -2147467261;
        v91 = "m_spChromaSample.GetPointer() is NULL";
        v24 = (char *)&unk_18019F1D8;
        LODWORD(v93) = 618;
        v96 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avc444compressor.cpp";
        v95 = "Error condition failed";
        v87 = (unsigned __int8 *)&v93;
        v86 = (unsigned int *)&v96;
        v26 = (int *)&v89;
        goto LABEL_8;
      }
      v49 = *((_QWORD *)this + 2);
      v50 = *(_QWORD *)(v49 + 128);
      v51 = *(unsigned int *)(v49 + 144);
      v99 = (const char *)*((_QWORD *)this + 38);
      v88 = *((unsigned __int8 *)this + 185);
      v98 = v48;
      SourceForCompress = (*(__int64 (__fastcall **)(_QWORD, struct PixelMap *, struct IRdpBoundsAccumulator *, __int64, __int64, const char **, const char **, int *, int))(**((_QWORD **)this + 1) + 16LL))(
                            *((_QWORD *)this + 1),
                            v104,
                            a4,
                            v51,
                            v50,
                            &v99,
                            &v98,
                            &v94,
                            v88);
      if ( SourceForCompress < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_161;
        LODWORD(v93) = 638;
        v91 = "m_pColorConversion->Execute (SW, IMFSample) failed";
        v24 = byte_18019F0D3;
        v89 = SourceForCompress;
        v96 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avc444compressor.cpp";
        v95 = "Error HResult failed";
        v87 = (unsigned __int8 *)&v93;
        v86 = (unsigned int *)&v96;
        v26 = (int *)&v89;
        goto LABEL_8;
      }
      if ( v94 )
      {
        v92 = 0;
        *((_DWORD *)this + 165) = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v52 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_5d037097164339a27202bb0efcb23f22_Traceguids, v52);
        }
      }
    }
    AvcEncoder::GetCVTCount(*((AvcEncoder **)this + 2));
    SourceForCompress = Avc444Compressor::EncodeYUV420(
                          (Avc444Compressor *)((char *)this - 48),
                          a4,
                          &v92,
                          v94,
                          a5,
                          v103[0],
                          v102[0],
                          v39);
    if ( SourceForCompress < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        LODWORD(v93) = 670;
        v99 = "AVC EncodeYUV420 failed";
        v98 = "Compress";
        v91 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avc444compressor.cpp";
        v89 = SourceForCompress;
        v90 = (PipelineClock *)"Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)"Compress",
          (unsigned int)&dword_18019F07C,
          v17,
          v47,
          (__int64)&v90,
          (__int64)&v89,
          (__int64)&v91,
          (__int64)&v93,
          (__int64)&v98,
          (__int64)&v99);
      }
      goto LABEL_161;
    }
    if ( v92 )
    {
      v54 = &v39[v92];
      goto LABEL_95;
    }
    *((_DWORD *)this + 165) = 0;
  }
  else
  {
    v92 = 0;
  }
  v54 = v39;
LABEL_95:
  v55 = *((_QWORD *)this + 42);
  if ( v55 )
    (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v55 + 328LL))(
      v55,
      *((unsigned int *)this + 20),
      (char *)this + 192);
  if ( *((_DWORD *)this + 172) )
  {
    v56 = (_DWORD *)((char *)this + 648);
    *((_DWORD *)this + 162) = 0;
    AdvanceFeatureMap::Clean((Avc444Compressor *)((char *)this + 192));
  }
  else
  {
    v57 = (Avc444Compressor *)((char *)this - 48);
    if ( *((_DWORD *)this + 171) )
    {
      Avc444Compressor::UpdateFixedQuality(v57);
      AdvanceFeatureMap::Clean((Avc444Compressor *)((char *)this + 192));
      if ( v97 <= v92 )
      {
        v20 = 2147942522LL;
        SourceForCompress = -2147024774;
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          v89 = -2147024774;
          v99 = "Not enough bytes left in DisableDelayChroma scenario, encoding failed";
          v98 = "Compress";
          v91 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avc444compressor.cpp";
          LODWORD(v93) = 712;
          v90 = (PipelineClock *)"Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (unsigned int)"Compress",
            (unsigned int)&word_18019EFCE,
            v17,
            v58,
            (__int64)&v90,
            (__int64)&v89,
            (__int64)&v91,
            (__int64)&v93,
            (__int64)&v98,
            (__int64)&v99);
        }
        goto LABEL_161;
      }
      v56 = (_DWORD *)((char *)this + 648);
      v97 -= v92;
    }
    else
    {
      Avc444Compressor::UpdateFeatureMap(v57);
      AdvanceFeatureMap::ClearDirty((Avc444Compressor *)((char *)this + 192));
      v56 = (_DWORD *)((char *)this + 648);
      if ( v97 <= v92 )
        *v56 = 0;
      else
        v97 -= v92;
      if ( !(*((_QWORD *)this + 10) % (__int64)*((unsigned int *)this + 106)) && !*((_DWORD *)this + 173) )
      {
        v59 = *((_QWORD *)this + 2);
        v89 = 0;
        (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v59 + 48LL))(v59, &v89);
        if ( *((_DWORD *)this + 165) )
        {
          (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 2) + 48LL))(*((_QWORD *)this + 2), &v89);
          if ( v89 < 0x64 )
            *v56 = 0;
        }
      }
    }
  }
  AvcEncoder::StartPerfCount(*((AvcEncoder **)this + 2));
  if ( *v56 )
  {
    SourceForCompress = Avc444Compressor::EncodeChroma(
                          (Avc444Compressor *)((char *)this - 48),
                          v103[0],
                          v102[0],
                          &v97,
                          v54);
    if ( SourceForCompress < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        LODWORD(v93) = 753;
        v99 = "AVC EncodeChroma failed";
        v98 = "Compress";
        v91 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avc444compressor.cpp";
        v89 = SourceForCompress;
        v90 = (PipelineClock *)"Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)"Compress",
          (unsigned int)byte_18019F025,
          v17,
          v60,
          (__int64)&v90,
          (__int64)&v89,
          (__int64)&v91,
          (__int64)&v93,
          (__int64)&v98,
          (__int64)&v99);
      }
      goto LABEL_161;
    }
    v61 = v92;
    v20 = v97;
    v62 = v92 + 4;
    if ( !v97 )
    {
      *(_DWORD *)a9 = v62;
      *v56 = 0;
      goto LABEL_121;
    }
    v63 = v97 + v62;
  }
  else
  {
    v61 = v92;
    v20 = 0;
    v97 = 0;
    v63 = v92 + 4;
  }
  *(_DWORD *)a9 = v63;
LABEL_121:
  if ( !v61 && !(_DWORD)v20 )
  {
    SourceForCompress = 0;
    *(_DWORD *)a9 = 0;
    goto LABEL_161;
  }
  if ( *((_DWORD *)this + 171) )
  {
    v61 |= 0xC0000000;
    v92 = v61;
  }
  else
  {
    v64 = *((_DWORD *)this + 165);
    if ( !v64 )
    {
      v61 = 0x80000000;
      v92 = 0x80000000;
    }
    if ( !*v56 )
    {
      v61 |= 0x40000000u;
      v92 = v61;
      if ( !v64 )
        *(_DWORD *)a9 = 0;
    }
  }
  v65 = v107;
  *(_DWORD *)v107 = v61;
  if ( !*((_DWORD *)this + 89)
    || *((_DWORD *)this + 93) == 2
    || !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 96LL))(*((_QWORD *)this + 2)) )
  {
    goto LABEL_156;
  }
  v66 = PipelineClock::GetMillisecondCount64(v90);
  v68 = *((_QWORD *)this + 79);
  v69 = v66 - (_QWORD)v91;
  if ( !v68 )
  {
    if ( v69 > *((unsigned int *)this + 36) )
    {
      *((_QWORD *)this + 80) += v69;
      *((_QWORD *)this + 79) = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v70 = *((_DWORD *)this + 44);
        v71 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
        WPP_SF_Did(*((_QWORD *)WPP_GLOBAL_Control + 2), v72, v73, v71, v69, v70);
      }
    }
    goto LABEL_156;
  }
  *((_QWORD *)this + 80) += v69;
  v74 = *((unsigned int *)this + 44);
  v75 = v68 + 1;
  v76 = *((_QWORD *)this + 80);
  *((_QWORD *)this + 79) = v75;
  if ( v75 != v74 )
  {
LABEL_156:
    v81 = (OutputAvc *)*((_QWORD *)this + 3);
    if ( v81 )
    {
      if ( *((_QWORD *)this + 10) == 1 )
      {
        HIDWORD(v107) = *((_DWORD *)this + 13);
        v108 = *((_DWORD *)this + 14);
        LODWORD(v107) = 1;
        OutputAvc::OutputRdpAvcStreams(v81, (unsigned __int8 *)&v107, 12);
      }
      OutputAvc::OutputRdpAvcStreams(*((OutputAvc **)this + 3), a9, 4);
      OutputAvc::OutputRdpAvcStreams(*((OutputAvc **)this + 3), v65, *(_DWORD *)a9);
    }
    v82 = v106;
    *(_QWORD *)v106 = 0;
    *((_DWORD *)v82 + 2) = *((_DWORD *)this + 9);
    *((_DWORD *)v82 + 3) = *((_DWORD *)this + 10);
    goto LABEL_161;
  }
  if ( v76 < 0 )
    v77 = (float)(v76 & 1 | (unsigned int)((unsigned __int64)v76 >> 1))
        + (float)(v76 & 1 | (unsigned int)((unsigned __int64)v76 >> 1));
  else
    v77 = (float)(int)v76;
  if ( v75 < 0 )
    v78 = (float)(v75 & 1 | (unsigned int)((unsigned __int64)v75 >> 1))
        + (float)(v75 & 1 | (unsigned int)((unsigned __int64)v75 >> 1));
  else
    v78 = (float)(int)v75;
  v79 = (int)(float)(v77 / v78);
  if ( v79 <= *((_DWORD *)this + 36) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v80 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
      WPP_SF_Dqq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        &WPP_5d037097164339a27202bb0efcb23f22_Traceguids,
        v80,
        v76,
        v75);
    }
    *((_QWORD *)this + 80) = 0;
    *((_QWORD *)this + 79) = 0;
    goto LABEL_156;
  }
  SourceForCompress = -2147024638;
  if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v107 = (unsigned __int8 *)*((_QWORD *)this + 79);
    v99 = (const char *)v79;
    v91 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avc444compressor.cpp";
    v90 = (PipelineClock *)"HW encode falling back to SW encode. (Non-fatal)";
    v98 = "Compress";
    LODWORD(v93) = 828;
    v89 = -2147024638;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (unsigned int)"Compress",
      (unsigned int)&byte_18019EF37,
      v17,
      v67,
      (__int64)&v90,
      (__int64)&v89,
      (__int64)&v91,
      (__int64)&v93,
      (__int64)&v98,
      (__int64)&v99,
      (__int64)&v107);
  }
  *((_QWORD *)this + 80) = 0;
  *((_QWORD *)this + 79) = 0;
LABEL_161:
  if ( v100 == 1 )
    ReleaseSRWLockExclusive(*((PSRWLOCK *)this + 59));
  if ( SourceForCompress )
  {
LABEL_164:
    v83 = (OutputAvc *)*((_QWORD *)this + 3);
    if ( v83 )
      OutputAvc::`scalar deleting destructor'(v83, v20);
    *((_QWORD *)this + 3) = 0;
  }
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v101, v20, v17);
  return (unsigned int)SourceForCompress;
}

```

## disassembly

```asm
0x180081d80  push    rbp
0x180081d82  push    rbx
0x180081d83  push    rsi
0x180081d84  push    rdi
0x180081d85  push    r12
0x180081d87  push    r13
0x180081d89  push    r14
0x180081d8b  push    r15
0x180081d8d  lea     rbp, [rsp-18h]
0x180081d92  sub     rsp, 118h
0x180081d99  mov     rax, cs:__security_cookie
0x180081da0  xor     rax, rsp
0x180081da3  mov     [rbp+50h+var_50], rax
0x180081da7  mov     rax, [rbp+50h+arg_48]
0x180081dae  mov     rdi, rcx
0x180081db1  mov     r13, [rbp+50h+arg_40]
0x180081db8  lea     rcx, [rbp+50h+var_90]
0x180081dbc  mov     [rbp+50h+var_68], rax
0x180081dc0  xor     ebx, ebx
0x180081dc2  mov     rax, [rbp+50h+arg_38]
0x180081dc9  mov     r15, r9
0x180081dcc  mov     [rbp+50h+var_D0], rax
0x180081dd0  mov     rsi, r8
0x180081dd3  mov     r14, rdx
0x180081dd6  mov     [rbp+50h+var_98], 0
0x180081ddd  mov     [rbp+50h+var_90], rbx
0x180081de1  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180081de6  mov     [rbp+50h+var_78], rbx
0x180081dea  call    ?GetInstance@PipelineClock@@SAAEAV1@XZ; PipelineClock::GetInstance(void)
0x180081def  mov     ecx, [rbp+50h+arg_50]
0x180081df5  lea     r12, [rdi-30h]
0x180081df9  mov     [r12+50h], ecx
0x180081dfe  mov     [rsp+150h+var_E8], rax
0x180081e03  test    r14, r14
0x180081e06  jz      loc_180081F25
0x180081e0c  lea     rax, [rbp+50h+var_98]
0x180081e10  mov     rdx, r14; struct RdpSurface *
0x180081e13  lea     r9, [rbp+50h+var_78]; struct PixelMap **
0x180081e17  mov     [rsp+150h+var_130], rax; int *
0x180081e1c  lea     r8, [rbp+50h+var_90]; struct ID3D11ShaderResourceView **
0x180081e20  mov     rcx, r12; this
0x180081e23  call    ?GetSourceForCompress@AvcCompressor@@IEAAJPEAVRdpSurface@@PEAPEAUID3D11ShaderResourceView@@PEAPEAVPixelMap@@PEAH@Z; AvcCompressor::GetSourceForCompress(RdpSurface *,ID3D11ShaderResourceView * *,PixelMap * *,int *)
0x180081e28  mov     esi, eax
0x180081e2a  test    eax, eax
0x180081e2c  jns     loc_180081EC4
0x180081e32  mov     ecx, cs:dword_1801B76C8
0x180081e38  cmp     ecx, 2
0x180081e3b  jbe     loc_180082EA5
0x180081e41  lea     rax, aGetsourceforco; "GetSourceForCompress failed"
0x180081e48  mov     [rsp+150h+var_F0], 1E8h
0x180081e50  lea     rdx, byte_18019F439
0x180081e57  mov     [rbp+50h+var_C8], esi
0x180081e5a  mov     [rsp+150h+var_E0], rax
0x180081e5f  lea     rax, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x180081e66  mov     [rbp+50h+var_B8], rax
0x180081e6a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180081e71  mov     [rbp+50h+var_C0], rax
0x180081e75  lea     rax, [rsp+150h+var_E0]
0x180081e7a  mov     [rsp+150h+var_108], rax
0x180081e7f  lea     rax, [rsp+150h+var_E8]
0x180081e84  mov     [rsp+150h+var_110], rax
0x180081e89  lea     rax, [rsp+150h+var_F0]
0x180081e8e  mov     [rsp+150h+var_118], rax
0x180081e93  lea     rax, [rbp+50h+var_B8]
0x180081e97  mov     qword ptr [rsp+150h+var_120], rax
0x180081e9c  lea     rax, [rbp+50h+var_C8]
0x180081ea0  mov     qword ptr [rsp+150h+var_128], rax
0x180081ea5  lea     rax, [rbp+50h+var_C0]
0x180081ea9  lea     rcx, aCompress; "Compress"
0x180081eb0  mov     [rsp+150h+var_E8], rcx
0x180081eb5  mov     [rsp+150h+var_130], rax
0x180081eba  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180081ebf  jmp     loc_180082EA5
0x180081ec4  mov     rdx, cs:WPP_GLOBAL_Control
0x180081ecb  lea     rax, WPP_GLOBAL_Control
0x180081ed2  cmp     rdx, rax
0x180081ed5  jz      short loc_180081F18
0x180081ed7  test    dword ptr [rdx+1Ch], 100h
0x180081ede  jz      short loc_180081F18
0x180081ee0  cmp     byte ptr [rdx+19h], 5
0x180081ee4  jb      short loc_180081F18
0x180081ee6  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180081eec  mov     rcx, cs:WPP_GLOBAL_Control
0x180081ef3  lea     r8, WPP_5d037097164339a27202bb0efcb23f22_Traceguids
0x180081efa  mov     edx, 23h ; '#'
0x180081eff  mov     r9d, eax
0x180081f02  mov     rcx, [rcx+10h]
0x180081f06  call    WPP_SF_d
0x180081f0b  mov     rbx, [rbp+50h+var_90]
0x180081f0f  mov     rsi, [rbp+50h+var_78]
0x180081f13  jmp     loc_180081FCB
0x180081f18  mov     rbx, [rbp+50h+var_90]
0x180081f1c  mov     rsi, [rbp+50h+var_78]
0x180081f20  jmp     loc_180081FD2
0x180081f25  test    rsi, rsi
0x180081f28  jnz     loc_180081FC7
0x180081f2e  mov     eax, cs:dword_1801B76C8
0x180081f34  mov     edx, 80004003h
0x180081f39  mov     esi, edx
0x180081f3b  cmp     eax, 2
0x180081f3e  jbe     loc_180082EBC
0x180081f44  lea     rax, aPsrcimgIsNull; "pSrcImg is NULL"
0x180081f4b  mov     [rsp+150h+var_F0], edx
0x180081f4f  mov     [rsp+150h+var_E0], rax
0x180081f54  lea     rcx, aCompress; "Compress"
0x180081f5b  lea     rax, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x180081f62  mov     [rsp+150h+var_E8], rcx
0x180081f67  mov     [rbp+50h+var_B8], rax
0x180081f6b  lea     rdx, byte_18019F38B
0x180081f72  lea     rax, aErrorCondition; "Error condition failed"
0x180081f79  mov     [rbp+50h+var_98], 1EFh
0x180081f80  mov     [rbp+50h+var_C0], rax
0x180081f84  lea     rax, [rsp+150h+var_E0]
0x180081f89  mov     [rsp+150h+var_108], rax
0x180081f8e  lea     rax, [rsp+150h+var_E8]
0x180081f93  mov     [rsp+150h+var_110], rax
0x180081f98  lea     rax, [rbp+50h+var_98]
0x180081f9c  mov     [rsp+150h+var_118], rax
0x180081fa1  lea     rax, [rbp+50h+var_B8]
0x180081fa5  mov     qword ptr [rsp+150h+var_120], rax
0x180081faa  lea     rax, [rsp+150h+var_F0]
0x180081faf  mov     qword ptr [rsp+150h+var_128], rax
0x180081fb4  lea     rax, [rbp+50h+var_C0]
0x180081fb8  mov     [rsp+150h+var_130], rax
0x180081fbd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180081fc2  jmp     loc_180082EBC
0x180081fc7  mov     [rbp+50h+var_78], rsi
0x180081fcb  mov     rdx, cs:WPP_GLOBAL_Control
0x180081fd2  cmp     qword ptr [rdi+10h], 0
0x180081fd7  jnz     short loc_180082024
0x180081fd9  mov     eax, cs:dword_1801B76C8
0x180081fdf  mov     edx, 80004003h
0x180081fe4  mov     esi, edx
0x180081fe6  cmp     eax, 2
0x180081fe9  jbe     loc_180082EA5
0x180081fef  lea     rax, aMPavccodecIsNu; "m_pAvcCodec is NULL"
0x180081ff6  mov     [rbp+50h+var_C8], edx
0x180081ff9  mov     [rsp+150h+var_E0], rax
0x180081ffe  lea     rdx, word_18019F3E2
0x180082005  lea     rax, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18008200c  mov     [rsp+150h+var_F0], 1F4h
0x180082014  mov     [rbp+50h+var_B8], rax
0x180082018  lea     rax, aErrorCondition; "Error condition failed"
0x18008201f  jmp     loc_180081E71
0x180082024  cmp     dword ptr [r13+0], 4
0x180082029  jnb     short loc_18008205F
0x18008202b  mov     eax, cs:dword_1801B76C8
0x180082031  mov     edx, 8007007Ah
0x180082036  mov     esi, edx
0x180082038  cmp     eax, 2
0x18008203b  jbe     loc_180082EA5
0x180082041  mov     [rbp+50h+var_C8], edx
0x180082044  lea     rax, aCompressedSize; "Compressed size is larger than the allo"...
0x18008204b  lea     rdx, dword_18019F334
0x180082052  mov     [rsp+150h+var_F0], 1F9h
0x18008205a  jmp     loc_180081E5A
0x18008205f  mov     rcx, [rdi+18h]; this
0x180082063  mov     [rsp+150h+var_E0], 0
0x18008206c  test    rcx, rcx
0x18008206f  jz      short loc_180082085
0x180082071  test    rsi, rsi
0x180082074  jz      short loc_180082085
0x180082076  mov     rdx, rsi; struct PixelMap *
0x180082079  call    ?OutputRGB@OutputAvc@@QEAAXPEAVPixelMap@@@Z; OutputAvc::OutputRGB(PixelMap *)
0x18008207e  mov     rdx, cs:WPP_GLOBAL_Control
0x180082085  cmp     dword ptr [rdi+164h], 0
0x18008208c  jz      short loc_1800820AD
0x18008208e  cmp     dword ptr [rdi+174h], 2
0x180082095  jz      short loc_1800820AD
0x180082097  mov     rcx, [rsp+150h+var_E8]; this
0x18008209c  call    ?GetMillisecondCount64@PipelineClock@@QEAA_KXZ; PipelineClock::GetMillisecondCount64(void)
0x1800820a1  mov     rdx, cs:WPP_GLOBAL_Control
0x1800820a8  mov     [rsp+150h+var_E0], rax
0x1800820ad  cmp     dword ptr [rdi+6Ch], 0
0x1800820b1  movsd   xmm1, qword ptr [rdi+60h]; double
0x1800820b6  jz      loc_18008214A
0x1800820bc  mov     ecx, [rbp+50h+arg_30]
0x1800820c2  xorps   xmm0, xmm0
0x1800820c5  cvtsi2sd xmm0, rcx
0x1800820ca  mulsd   xmm0, qword ptr [rdi+48h]
0x1800820cf  divsd   xmm0, xmm1
0x1800820d3  cvttsd2si rsi, xmm0
0x1800820d8  xorps   xmm0, xmm0
0x1800820db  mov     eax, esi
0x1800820dd  mov     qword ptr [rbp+50h+var_88], rsi
0x1800820e1  cvtsi2sd xmm0, rax
0x1800820e6  mulsd   xmm0, qword ptr [rdi+48h]
0x1800820eb  divsd   xmm0, xmm1
0x1800820ef  cvttsd2si r14, xmm0
0x1800820f4  mov     qword ptr [rbp+50h+var_80], r14
0x1800820f8  lea     rax, WPP_GLOBAL_Control
0x1800820ff  cmp     rdx, rax
0x180082102  jz      loc_1800821B3
0x180082108  test    dword ptr [rdx+1Ch], 100h
0x18008210f  jz      loc_1800821B3
0x180082115  cmp     byte ptr [rdx+19h], 5
0x180082119  jb      loc_1800821B3
0x18008211f  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180082125  mov     rcx, cs:WPP_GLOBAL_Control
0x18008212c  lea     r8, WPP_5d037097164339a27202bb0efcb23f22_Traceguids
0x180082133  mov     edx, 24h ; '$'
0x180082138  mov     dword ptr [rsp+150h+var_130], esi
0x18008213c  mov     r9d, eax
0x18008213f  mov     rcx, [rcx+10h]
0x180082143  call    WPP_SF_Dd
0x180082148  jmp     short loc_1800821B3
0x18008214a  comisd  xmm1, cs:__real@0000000000000000
0x180082152  mov     [rbp+50h+var_80], 0
0x180082159  jbe     short loc_1800821A9
0x18008215b  mov     ecx, [rbp+50h+arg_28]; unsigned int
0x180082161  xorps   xmm0, xmm0
0x180082164  movsd   xmm2, qword ptr [rdi+48h]; double
0x180082169  cvtsi2sd xmm0, rcx
0x18008216e  mulsd   xmm0, qword ptr [rdi+48h]
0x180082173  divsd   xmm0, cs:__real@405f400000000000
0x18008217b  cvttsd2si rax, xmm0
0x180082180  xorps   xmm0, xmm0
0x180082183  mov     [rbp+50h+var_80], eax
0x180082186  mov     eax, [rbp+50h+arg_30]
0x18008218c  cvtsi2sd xmm0, rax
0x180082191  mulsd   xmm0, qword ptr [rdi+48h]
0x180082196  divsd   xmm0, xmm1
0x18008219a  cvttsd2si rax, xmm0
0x18008219f  mov     [rbp+50h+var_88], eax
0x1800821a2  call    ?TracePipelineBitrate@Helper@@SAXKNN@Z; Helper::TracePipelineBitrate(ulong,double,double)
0x1800821a7  jmp     short loc_1800821B3
0x1800821a9  mov     eax, [rbp+50h+arg_30]
0x1800821af  mov     qword ptr [rbp+50h+var_88], rax
0x1800821b3  mov     rcx, [rdi+10h]; this
0x1800821b7  call    ?StartPerfCount@AvcEncoder@@QEAAXXZ; AvcEncoder::StartPerfCount(void)
0x1800821bc  cmp     qword ptr [rdi+50h], 0
0x1800821c1  jnz     short loc_1800821E1
0x1800821c3  call    ?QueryCounter@QueryCPUPerformance@@QEAA_JXZ; QueryCPUPerformance::QueryCounter(void)
0x1800821c8  mov     [rdi+1E0h], rax
0x1800821cf  call    ?QueryCounter@QueryCPUPerformance@@QEAA_JXZ; QueryCPUPerformance::QueryCounter(void)
0x1800821d4  add     rax, 0FDE8h
0x1800821da  mov     [rdi+1B8h], rax
0x1800821e1  mov     eax, [r13+0]
0x1800821e5  lea     rdx, [rbp+50h+var_70]
0x1800821e9  add     eax, 0FFFFFFFCh
0x1800821ec  mov     [rbp+50h+var_70], 0
0x1800821f3  mov     [rsp+150h+var_D8], eax
0x1800821f7  mov     rcx, r12
0x1800821fa  mov     [rbp+50h+var_B0], eax
0x1800821fd  mov     rax, [r12]
0x180082201  mov     rax, [rax+18h]
0x180082205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008220a  mov     esi, eax
0x18008220c  test    eax, eax
0x18008220e  jns     short loc_18008223A
0x180082210  mov     eax, cs:dword_1801B76C8
0x180082216  cmp     eax, 2
0x180082219  jbe     loc_180082EA5
0x18008221f  lea     rax, aGet420qualityI; "Get420Quality is failed"
0x180082226  mov     [rsp+150h+var_F0], 229h
0x18008222e  lea     rdx, byte_18019F2DD
0x180082235  jmp     loc_180081E57
0x18008223a  cmp     [rbp+50h+var_70], 64h ; 'd'
0x18008223e  mov     rax, [rbp+50h+var_D0]
0x180082242  mov     [rbp+50h+var_60], rax
0x180082246  lea     r14, [rax+4]
0x18008224a  jnz     short loc_180082266
0x18008224c  mov     rax, [r15]
0x18008224f  mov     rcx, r15
0x180082252  mov     rax, [rax+88h]
0x180082259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008225e  test    eax, eax
0x180082260  jz      short loc_180082266
0x180082262  xor     eax, eax
0x180082264  jmp     short loc_18008226B
0x180082266  mov     eax, 1
0x18008226b  mov     [r12+2C4h], eax
0x180082273  mov     rax, [rdi+50h]
0x180082277  mov     ecx, [rdi+1A8h]
0x18008227d  cqo
0x18008227f  idiv    rcx
0x180082282  test    rdx, rdx
0x180082285  jnz     short loc_18008228E
0x180082287  mov     [rdi+298h], rdx
0x18008228e  cmp     dword ptr [rdi+294h], 0
0x180082295  jz      loc_1800828CB
0x18008229b  cmp     dword ptr [rdi+164h], 0
0x1800822a2  mov     [rbp+50h+var_C8], 0
0x1800822a9  jz      loc_180082810
0x1800822af  cmp     dword ptr [r12+198h], 0
0x1800822b8  jz      loc_1800825BB
0x1800822be  mov     rax, [rdi+8]
0x1800822c2  mov     r8, r15
0x1800822c5  mov     [rbp+50h+var_C0], 0
0x1800822cd  mov     [rbp+50h+var_B8], 0
0x1800822d5  mov     r10, [rax]
0x1800822d8  test    rbx, rbx
0x1800822db  jz      loc_1800824F3
0x1800822e1  lea     rcx, [rbp+50h+var_B8]
0x1800822e5  mov     rdx, rbx
0x1800822e8  mov     [rsp+150h+var_130], rcx
0x1800822ed  lea     r9, [rbp+50h+var_C0]
0x1800822f1  mov     rcx, rax
0x1800822f4  mov     rax, [r10]
0x1800822f7  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
