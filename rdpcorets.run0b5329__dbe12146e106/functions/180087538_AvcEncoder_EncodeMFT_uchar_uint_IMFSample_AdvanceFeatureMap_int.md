# AvcEncoder::EncodeMFT(uchar *,uint *,IMFSample *,AdvanceFeatureMap *,int)

- ea: `0x180087538`
- end: `0x180088a89`
- name: `?EncodeMFT@AvcEncoder@@AEAAJPEAEPEAIPEAUIMFSample@@PEAVAdvanceFeatureMap@@H@Z`
- size: `5457`
- prototype: `__int64 __usercall@<rax>(AvcEncoder *__hidden this@<rcx>, unsigned __int8 *@<rdx>, unsigned int *@<r8>, struct IMFSample *@<r9>, struct AdvanceFeatureMap *, int)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180084c60`

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x1800071c0`
- `0x180009628`
- `0x18000ee00`
- `0x180017d8c`
- `0x180017e38`
- `0x180033940`
- `0x180033958`
- `0x180033da0`
- `0x180034970`
- `0x180059838`
- `0x1800598d0`
- `0x180087538`
- `0x18008b350`
- `0x18008c414`
- `0x1800d9a30`
- `0x1800db044`
- `0x1800e46bc`
- `0x18014c328`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180088020`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180088020`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800875bb`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800877e7`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800878b1`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800880c4`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180088560`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800875bb`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800877e7`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800878b1`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800880c4`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180088560`

## string_xrefs

- `0x180087c31`: `Compressed size is larger than the allocated output sample size.`
- `0x180088783`: `Compressed size is larger than the allocated output sample size.`
- `0x1800876ef`: `m_spMFApi->CreateSample failed `
- `0x18008794f`: `MFSampleExtension_VideoEncodeQPMap failed.`
- `0x1800879ee`: `UpdateRectList failed`
- `0x180087f06`: `UpdateRectList failed`
- `0x180087d13`: `WriteHeaderInfo failed`
- `0x180088866`: `WriteHeaderInfo failed`
- `0x180088388`: `AVC m_spEncoderMFT->ProcessMessage MFT_MESSAGE_COMMAND_FLUSH failed`
- `0x180088986`: `Received METransformDrainComplete or  MEEndOfPresentation from the MFT for EncodeMFT, it is illegal for the low latency encoder`

## pseudocode

```c
__int64 __fastcall AvcEncoder::EncodeMFT(
        AvcEncoder *this,
        unsigned __int8 *a2,
        unsigned int *a3,
        struct IMFSample *a4,
        struct AdvanceFeatureMap *a5,
        int a6)
{
  unsigned int v6; // r13d
  int Sample; // ebx
  unsigned int ActivityIdPrefix; // eax
  __int64 v13; // rcx
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // rcx
  char *v17; // rax
  char *v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  void *v25; // rax
  __int64 v26; // rcx
  int v27; // eax
  size_t v28; // r8
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  __int64 v35; // rdx
  int v36; // ecx
  __int64 v37; // r8
  int v38; // r9d
  __int16 *v39; // rdx
  const char **v40; // rax
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  __int64 v44; // rcx
  unsigned int v45; // ebx
  OutputAvc *v46; // rcx
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  int v50; // ecx
  int v51; // r8d
  int v52; // r9d
  int v53; // r14d
  __int64 v54; // rcx
  __int64 (__fastcall *v55)(__int64, __int64, const char **); // rax
  int v56; // ecx
  int v57; // r8d
  int v58; // r9d
  int v59; // r8d
  int v60; // r9d
  unsigned __int8 *v61; // r14
  __int64 v62; // rcx
  unsigned int v63; // eax
  char *v64; // rdx
  const char *v65; // rax
  const char *v66; // rcx
  __int64 v67; // rcx
  int v68; // eax
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // r8
  int v72; // r9d
  __int64 v73; // rcx
  __int64 v74; // rdx
  int v75; // ecx
  __int64 v76; // r8
  int v77; // r9d
  const char *v78; // rcx
  const char *v79; // rax
  int *v80; // rdx
  char *v81; // rbx
  int v82; // eax
  __int64 v83; // rax
  __int64 v84; // rdx
  int v85; // ecx
  __int64 v86; // r8
  int v87; // r9d
  __int64 v88; // rdx
  __int64 v89; // r8
  int v90; // ecx
  int v91; // r8d
  int v92; // r9d
  __int64 v93; // rcx
  unsigned int v94; // ebx
  unsigned __int8 *v95; // rsi
  OutputAvc *v96; // rcx
  struct AdvanceFeatureMap *v97; // r8
  int v98; // ecx
  int v99; // r9d
  __int64 v100; // rdx
  __int64 v101; // r8
  const char *v102; // rcx
  RateControlHW *v103; // rcx
  char *v104; // rax
  __int16 *v105; // rdx
  void **v107; // [rsp+30h] [rbp-D0h]
  void *p_Src; // [rsp+40h] [rbp-C0h]
  unsigned __int8 **v109; // [rsp+48h] [rbp-B8h]
  int v110; // [rsp+50h] [rbp-B0h] BYREF
  int Size; // [rsp+54h] [rbp-ACh] BYREF
  int Size_4; // [rsp+58h] [rbp-A8h] BYREF
  const char *v113; // [rsp+60h] [rbp-A0h] BYREF
  void *Src; // [rsp+68h] [rbp-98h] BYREF
  int v115; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 *v116; // [rsp+78h] [rbp-88h] BYREF
  const char *v117; // [rsp+80h] [rbp-80h] BYREF
  const char *v118; // [rsp+88h] [rbp-78h] BYREF
  const char *v119; // [rsp+90h] [rbp-70h] BYREF
  const char *v120; // [rsp+98h] [rbp-68h] BYREF
  struct AdvanceFeatureMap *v121; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v122; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v123; // [rsp+B8h] [rbp-48h]
  void **v124; // [rsp+C8h] [rbp-38h] BYREF
  int v125; // [rsp+D0h] [rbp-30h]
  unsigned __int8 *v126; // [rsp+D8h] [rbp-28h] BYREF
  int v127; // [rsp+E0h] [rbp-20h]
  const char **v128; // [rsp+E8h] [rbp-18h] BYREF
  int v129; // [rsp+F0h] [rbp-10h]

  v6 = 0;
  v116 = (unsigned __int8 *)a4;
  v126 = a2;
  v121 = a5;
  if ( a6 && !*a3 )
  {
    Sample = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(this);
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        &WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids,
        ActivityIdPrefix);
    }
    return (unsigned int)Sample;
  }
  v13 = *((_QWORD *)this + 8);
  if ( !*((_QWORD *)this + 13) )
  {
    v126 = 0;
    v127 = 0;
    v122 = 0;
    v123 = 0;
    Sample = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int8 **))(*(_QWORD *)v13 + 56LL))(v13, 0, &v126);
    if ( Sample < 0 )
    {
      LODWORD(v16) = dword_1801B76C8;
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        return (unsigned int)Sample;
      v17 = "Failed to get output stream info";
      v115 = 1656;
      v18 = byte_1801A054D;
LABEL_11:
      v116 = (unsigned __int8 *)v17;
      Src = "EncodeMFT";
      v117 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v113 = "Error HResult failed";
      Size = Sample;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v16,
        (_DWORD)v18,
        v14,
        v15,
        (__int64)&v113,
        (__int64)&Size,
        (__int64)&v117,
        (__int64)&v115,
        (__int64)&Src,
        (__int64)&v116);
      return (unsigned int)Sample;
    }
    if ( ((unsigned __int16)v126 & 0x300) == 0 )
    {
      if ( HIDWORD(v126) )
      {
        if ( !*((_QWORD *)this + 11) )
        {
          Sample = CMFApi::CreateSample(*((CMFApi **)this + 12), HIDWORD(v126), (struct IMFSample **)this + 11);
          if ( Sample < 0 )
          {
            if ( (unsigned int)dword_1801B76C8 <= 2 )
              return (unsigned int)Sample;
            v17 = "m_spMFApi->CreateSample failed ";
            v115 = 1671;
            v18 = byte_1801A04AB;
            goto LABEL_11;
          }
        }
      }
    }
    v19 = *((_QWORD *)this + 8);
    *((_QWORD *)&v122 + 1) = *((_QWORD *)this + 11);
    Sample = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IMFSample *, _QWORD))(*(_QWORD *)v19 + 192LL))(
               v19,
               0,
               a4,
               0);
    if ( Sample < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        return (unsigned int)Sample;
      v17 = "Failed to process the encoder input";
      v115 = 1678;
      v18 = (char *)&dword_1801A04FC;
      goto LABEL_11;
    }
    v20 = *((_QWORD *)this + 8);
    Size_4 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int128 *, int *))(*(_QWORD *)v20 + 200LL))(
            v20,
            0,
            1,
            &v122,
            &Size_4);
    Sample = 0;
    if ( v21 != -1072861838 )
      Sample = v21;
    if ( Sample < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        return (unsigned int)Sample;
      v17 = "Failed to process encoder output";
      v115 = 1686;
      v18 = (char *)word_1801A045A;
      goto LABEL_11;
    }
    if ( !*((_QWORD *)&v122 + 1) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = RdpX_GetActivityIdPrefix(v16);
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          (unsigned int)&WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids,
          v22,
          (__int64)"OutputDataBuf.pSample");
      }
      return (unsigned int)-2147467261;
    }
    if ( *((_DWORD *)this + 44) )
    {
      v23 = *((_QWORD *)this + 11);
      Size = 0;
      if ( (*(int (__fastcall **)(__int64, __int64 *, int *))(*(_QWORD *)v23 + 112LL))(
             v23,
             MFSampleExtension_VideoEncodeQPMap,
             &Size) >= 0 )
      {
        if ( Size )
        {
          if ( Size != *((_DWORD *)this + 36) )
          {
            operator delete(*((void **)this + 15));
            v24 = (unsigned int)Size;
            *((_DWORD *)this + 36) = 0;
            v25 = operator new[](v24);
            *((_QWORD *)this + 15) = v25;
            if ( !v25 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v27 = RdpX_GetActivityIdPrefix(v26);
                WPP_SF_Ds(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  42,
                  (unsigned int)&WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids,
                  v27,
                  (__int64)"BYTE");
              }
              return (unsigned int)-2147024882;
            }
            v28 = (unsigned int)Size;
            *((_DWORD *)this + 36) = Size;
            *((_QWORD *)this + 16) = v25;
            memset_0(v25, 2, v28);
          }
          Sample = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 11)
                                                                                        + 120LL))(
                     *((_QWORD *)this + 11),
                     MFSampleExtension_VideoEncodeQPMap,
                     *((_QWORD *)this + 16),
                     *((unsigned int *)this + 36),
                     0);
          if ( Sample < 0 )
          {
            if ( (unsigned int)dword_1801B76C8 > 2 )
            {
              v115 = 1713;
              v116 = "MFSampleExtension_VideoEncodeQPMap failed.";
              v110 = Sample;
              Src = "EncodeMFT";
              v117 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
              v119 = "Error HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v29,
                (unsigned int)byte_1801A0409,
                v30,
                v31,
                (__int64)&v119,
                (__int64)&v110,
                (__int64)&v117,
                (__int64)&v115,
                (__int64)&Src,
                (__int64)&v116);
            }
            return (unsigned int)Sample;
          }
        }
      }
    }
    Sample = AvcEncoder::UpdateRectList(this, a5);
    if ( Sample < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v110 = 1722;
        v116 = "UpdateRectList failed";
        v115 = Sample;
        Src = "EncodeMFT";
        v117 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
        v119 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v32,
          (unsigned int)qword_1801A03B8,
          v33,
          v34,
          (__int64)&v119,
          (__int64)&v115,
          (__int64)&v117,
          (__int64)&v110,
          (__int64)&Src,
          (__int64)&v116);
      }
      return (unsigned int)Sample;
    }
    v113 = 0;
    Sample = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const char **))(**((_QWORD **)&v122 + 1) + 320LL))(
               *((_QWORD *)&v122 + 1),
               0,
               &v113);
    if ( Sample < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
      {
LABEL_54:
        TCntPtr<IRdpSQMLogger>::SafeRelease(&v113, v35, v37);
        return (unsigned int)Sample;
      }
      v110 = 1726;
      v116 = "OutputDataBuf.pSample->GetBufferByIndex failed";
      v39 = &word_1801A0316;
      Src = "EncodeMFT";
      v117 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v119 = "Error HResult failed";
      v109 = &v116;
      p_Src = &Src;
      v107 = (void **)&v117;
      v40 = &v119;
LABEL_53:
      v115 = Sample;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v36,
        (_DWORD)v39,
        v37,
        v38,
        (__int64)v40,
        (__int64)&v115,
        (__int64)v107,
        (__int64)&v110,
        (__int64)p_Src,
        (__int64)v109);
      goto LABEL_54;
    }
    v129 = 0;
    v128 = &v113;
    Size = 0;
    Src = 0;
    Sample = RAIIBufferLock::Lock((RAIIBufferLock *)&v128, (unsigned __int8 **)&Src, 0, (unsigned int *)&Size);
    if ( Sample >= 0 )
    {
      v44 = (unsigned int)(10 * *((_DWORD *)this + 84) + 4);
      v45 = Size + v44;
      if ( *a3 >= Size + (int)v44 )
      {
        memcpy_0(&a2[v44], Src, (unsigned int)Size);
        v46 = (OutputAvc *)*((_QWORD *)this + 20);
        if ( v46 )
          OutputAvc::OutputAvcStreams(v46, (unsigned __int8 *)Src, Size);
        *((_DWORD *)this + 39) = Size;
        RAIIBufferLock::~RAIIBufferLock((RAIIBufferLock *)&v128);
        *a3 = v45;
        Sample = AvcEncoder::WriteHeaderInfo(this, a2, a5);
        if ( Sample >= 0 )
        {
          TCntPtr<IRdpSQMLogger>::SafeRelease(&v113, v35, v37);
          goto LABEL_157;
        }
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_54;
        v110 = 1764;
        v118 = "WriteHeaderInfo failed";
        v39 = (__int16 *)byte_1801A02C5;
        v116 = "EncodeMFT";
        Src = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
        v117 = "Error HResult failed";
        v109 = (unsigned __int8 **)&v118;
        p_Src = &v116;
        v107 = &Src;
        v40 = &v117;
        goto LABEL_53;
      }
      Sample = -2147024774;
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v110 = 1743;
        v118 = "Compressed size is larger than the allocated output sample size.";
        v115 = -2147024774;
        v116 = "EncodeMFT";
        v117 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
        v119 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          -2147024774,
          (unsigned int)&dword_1801A0274,
          v42,
          v43,
          (__int64)&v119,
          (__int64)&v115,
          (__int64)&v117,
          (__int64)&v110,
          (__int64)&v116,
          (__int64)&v118);
      }
    }
    else if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v110 = 1734;
      v116 = "raiiBufLock(spAvcBuffer).Lock() failed";
      v115 = Sample;
      v117 = "EncodeMFT";
      v119 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v118 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v41,
        (unsigned int)&byte_1801A0367,
        v42,
        v43,
        (__int64)&v118,
        (__int64)&v115,
        (__int64)&v119,
        (__int64)&v110,
        (__int64)&v117,
        (__int64)&v116);
    }
    RAIIBufferLock::~RAIIBufferLock((RAIIBufferLock *)&v128);
    goto LABEL_54;
  }
  v128 = 0;
  v129 = 0;
  Sample = (*(__int64 (__fastcall **)(__int64, _QWORD, const char ***))(*(_QWORD *)v13 + 56LL))(v13, 0, &v128);
  if ( Sample < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v110 = 1787;
      v118 = "m_spEncoderMFT->GetOutputStreamInfo failed";
      Size_4 = Sample;
      v116 = "EncodeMFT";
      Src = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v117 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v47,
        (unsigned int)word_1801A01D2,
        v48,
        v49,
        (__int64)&v117,
        (__int64)&Size_4,
        (__int64)&Src,
        (__int64)&v110,
        (__int64)&v116,
        (__int64)&v118);
    }
    return (unsigned int)Sample;
  }
  if ( ((unsigned __int16)v128 & 0x300) == 0 )
  {
    Sample = -2147024809;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v110 = 1790;
      v118 = "AVC hardware encoder requests the MFT allocator";
      Size_4 = -2147024809;
      v116 = "EncodeMFT";
      Src = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v117 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024809,
        (unsigned int)byte_1801A0223,
        v48,
        v49,
        (__int64)&v117,
        (__int64)&Size_4,
        (__int64)&Src,
        (__int64)&v110,
        (__int64)&v116,
        (__int64)&v118);
    }
    return (unsigned int)Sample;
  }
  Sample = AvcEncoder::UpdateRectList(this, a5);
  if ( Sample < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v110 = 1802;
      v118 = "UpdateRectList failed";
      Size_4 = Sample;
      v116 = "EncodeMFT";
      Src = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v117 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v50,
        (unsigned int)qword_1801A0138,
        v51,
        v52,
        (__int64)&v117,
        (__int64)&Size_4,
        (__int64)&Src,
        (__int64)&v110,
        (__int64)&v116,
        (__int64)&v118);
    }
    return (unsigned int)Sample;
  }
  v113 = 0;
  Size = 1;
  v123 = 0;
  v53 = 0;
  v115 = 0;
  *(_QWORD *)&v122 = 0;
  do
  {
    v54 = *((_QWORD *)this + 13);
    *((_QWORD *)&v122 + 1) = 0;
    ++v6;
    v55 = *(__int64 (__fastcall **)(__int64, __int64, const char **))(*(_QWORD *)v54 + 24LL);
    if ( !*((_DWORD *)this + 50) )
    {
      Sample = v55(v54, 0, &v113);
LABEL_84:
      if ( Sample < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_172;
        v104 = "m_spEventGenerator->GetEvent failed";
        LODWORD(v119) = 1847;
        v105 = &word_1801A008E;
      }
      else
      {
        Sample = (*(__int64 (__fastcall **)(const char *, int *))(*(_QWORD *)v113 + 264LL))(v113, &v115);
        if ( Sample < 0 )
        {
          if ( (unsigned int)dword_1801B76C8 <= 2 )
            goto LABEL_172;
          v104 = "spEvent->GetType failed";
          LODWORD(v119) = 1852;
          v105 = (__int16 *)&dword_18019FFEC;
        }
        else
        {
          switch ( v115 )
          {
            case 601:
              if ( !Size )
                break;
              v61 = v116;
              Sample = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int8 *, _QWORD))(**((_QWORD **)this + 8)
                                                                                            + 192LL))(
                         *((_QWORD *)this + 8),
                         0,
                         v116,
                         0);
              if ( Sample == -1072875851 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  v63 = RdpX_GetActivityIdPrefix(v62);
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    43,
                    &WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids,
                    v63);
                }
                Sample = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 184LL))(
                           *((_QWORD *)this + 8),
                           0,
                           0);
                if ( Sample < 0 )
                {
                  if ( (unsigned int)dword_1801B76C8 > 2 )
                  {
                    v65 = "AVC m_spEncoderMFT->ProcessMessage MFT_MESSAGE_COMMAND_FLUSH failed";
                    v110 = 1863;
                    v64 = byte_1801A003D;
LABEL_98:
                    v118 = v65;
                    v116 = "EncodeMFT";
                    Src = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
                    v117 = "Error HResult failed";
                    Size_4 = Sample;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                      v62,
                      (_DWORD)v64,
                      v59,
                      v60,
                      (__int64)&v117,
                      (__int64)&Size_4,
                      (__int64)&Src,
                      (__int64)&v110,
                      (__int64)&v116,
                      (__int64)&v118);
                  }
LABEL_99:
                  v66 = v113;
                  if ( !v113 )
                    return (unsigned int)Sample;
                  v113 = 0;
LABEL_174:
                  (*(void (__fastcall **)(const char *))(*(_QWORD *)v66 + 16LL))(v66);
                  return (unsigned int)Sample;
                }
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v122 + 1) + 16LL))(*((_QWORD *)&v122 + 1));
                Sample = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int8 *, _QWORD))(**((_QWORD **)this + 8)
                                                                                              + 192LL))(
                           *((_QWORD *)this + 8),
                           0,
                           v61,
                           0);
                if ( Sample < 0 )
                {
                  if ( (unsigned int)dword_1801B76C8 <= 2 )
                    goto LABEL_99;
                  v110 = 1867;
                  v64 = (char *)word_18019FF4A;
                  goto LABEL_97;
                }
              }
              else if ( Sample < 0 )
              {
                if ( (unsigned int)dword_1801B76C8 <= 2 )
                  goto LABEL_99;
                v110 = 1871;
                v64 = byte_18019FF9B;
LABEL_97:
                v65 = "AVC m_spEncoderMFT->ProcessInput failed";
                goto LABEL_98;
              }
              Size = 0;
              goto LABEL_109;
            case 602:
              v67 = *((_QWORD *)this + 8);
              v110 = 0;
              v68 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int128 *, int *))(*(_QWORD *)v67 + 200LL))(
                      v67,
                      0,
                      1,
                      &v122,
                      &v110);
              Sample = v68;
              if ( v68 < 0 )
              {
                if ( v68 != -1072861855 )
                {
                  if ( (unsigned int)dword_1801B76C8 > 2 )
                  {
                    Size_4 = 1946;
                    v118 = "m_spEncoderMFT->ProcessOutput() failed";
                    Size = v68;
                    v116 = "EncodeMFT";
                    Src = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
                    v117 = "Error HResult failed";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                      v70,
                      (unsigned int)word_18019FCC2,
                      v71,
                      v72,
                      (__int64)&v117,
                      (__int64)&Size,
                      (__int64)&Src,
                      (__int64)&Size_4,
                      (__int64)&v116,
                      (__int64)&v118);
                  }
                  goto LABEL_172;
                }
                v73 = *((_QWORD *)this + 8);
                Src = 0;
                Sample = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void **))(*(_QWORD *)v73 + 112LL))(
                           v73,
                           0,
                           0,
                           &Src);
                if ( Sample < 0 )
                {
                  if ( (unsigned int)dword_1801B76C8 <= 2 )
                    goto LABEL_125;
                  v79 = "m_spEncoderMFT->GetOutputAvailableType() failed";
                  Size_4 = 1939;
                  v80 = &dword_18019FD64;
                }
                else
                {
                  Sample = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *, _QWORD))(**((_QWORD **)this + 8) + 128LL))(
                             *((_QWORD *)this + 8),
                             0,
                             Src,
                             0);
                  if ( Sample >= 0 )
                  {
                    TCntPtr<IRdpSQMLogger>::SafeRelease(&Src, v74, v76);
LABEL_109:
                    v53 = 1;
                    goto LABEL_110;
                  }
                  if ( (unsigned int)dword_1801B76C8 <= 2 )
                    goto LABEL_125;
                  v79 = "m_spEncoderMFT->SetOutputType() failed";
                  Size_4 = 1942;
                  v80 = (int *)byte_18019FDB5;
                }
                v118 = v79;
                v116 = "EncodeMFT";
                v117 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
                v119 = "Error HResult failed";
                Size = Sample;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                  v75,
                  (_DWORD)v80,
                  v76,
                  v77,
                  (__int64)&v119,
                  (__int64)&Size,
                  (__int64)&v117,
                  (__int64)&Size_4,
                  (__int64)&v116,
                  (__int64)&v118);
LABEL_125:
                TCntPtr<IRdpSQMLogger>::SafeRelease(&Src, v74, v76);
LABEL_172:
                v66 = v113;
                if ( !v113 )
                  return (unsigned int)Sample;
                v113 = 0;
                goto LABEL_174;
              }
              v81 = (char *)*((_QWORD *)&v122 + 1);
              if ( !*((_QWORD *)&v122 + 1) )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v82 = RdpX_GetActivityIdPrefix(v70);
                  WPP_SF_Ds(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    44,
                    (unsigned int)&WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids,
                    v82,
                    (__int64)"OutputDataBuf.pSample");
                }
                Sample = -2147467261;
                goto LABEL_136;
              }
              Src = 0;
              v117 = 0;
              TCntPtr<IRdpSQMLogger>::SafeRelease(&v117, v69, v71);
              v83 = *(_QWORD *)v81;
              v117 = v81;
              Sample = (*(__int64 (__fastcall **)(char *, _QWORD, void **))(v83 + 320))(v81, 0, &Src);
              if ( Sample >= 0 )
              {
                v125 = 0;
                v124 = &Src;
                Size = 0;
                v116 = 0;
                Sample = RAIIBufferLock::Lock((RAIIBufferLock *)&v124, &v116, 0, (unsigned int *)&Size);
                if ( Sample >= 0 )
                {
                  v93 = (unsigned int)(10 * *((_DWORD *)this + 84) + 4);
                  v94 = v93 + Size;
                  if ( *a3 >= (int)v93 + Size )
                  {
                    v95 = v126;
                    memcpy_0(&v126[v93], v116, (unsigned int)Size);
                    v96 = (OutputAvc *)*((_QWORD *)this + 20);
                    if ( v96 )
                      OutputAvc::OutputAvcStreams(v96, v116, Size);
                    *((_DWORD *)this + 39) = Size;
                    RAIIBufferLock::~RAIIBufferLock((RAIIBufferLock *)&v124);
                    v97 = v121;
                    *a3 = v94;
                    Sample = AvcEncoder::WriteHeaderInfo(this, v95, v97);
                    if ( Sample >= 0 )
                    {
                      TCntPtr<IRdpSQMLogger>::SafeRelease(&v117, v84, v86);
                      TCntPtr<IRdpSQMLogger>::SafeRelease(&Src, v100, v101);
                      goto LABEL_155;
                    }
                    if ( (unsigned int)dword_1801B76C8 > 2 )
                    {
                      LODWORD(v119) = 1930;
                      v126 = "WriteHeaderInfo failed";
                      Size_4 = Sample;
                      v121 = (struct AdvanceFeatureMap *)"EncodeMFT";
                      v120 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
                      v118 = "Error HResult failed";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                        v98,
                        (unsigned int)&byte_18019FE57,
                        v86,
                        v99,
                        (__int64)&v118,
                        (__int64)&Size_4,
                        (__int64)&v120,
                        (__int64)&v119,
                        (__int64)&v121,
                        (__int64)&v126);
                    }
                    goto LABEL_141;
                  }
                  Sample = -2147024774;
                  if ( (unsigned int)dword_1801B76C8 > 2 )
                  {
                    LODWORD(v119) = 1909;
                    v126 = "Compressed size is larger than the allocated output sample size.";
                    Size_4 = -2147024774;
                    v121 = (struct AdvanceFeatureMap *)"EncodeMFT";
                    v120 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
                    v118 = "Error HResult failed";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                      -2147024774,
                      (unsigned int)&word_18019FE06,
                      v91,
                      v92,
                      (__int64)&v118,
                      (__int64)&Size_4,
                      (__int64)&v120,
                      (__int64)&v119,
                      (__int64)&v121,
                      (__int64)&v126);
                  }
                }
                else if ( (unsigned int)dword_1801B76C8 > 2 )
                {
                  Size_4 = 1900;
                  v120 = "raiiBufLock(spAvcBuffer).Lock() failed";
                  LODWORD(v119) = Sample;
                  v118 = "EncodeMFT";
                  v121 = (struct AdvanceFeatureMap *)"onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
                  v126 = "Error HResult failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    v90,
                    (unsigned int)byte_18019FEF9,
                    v91,
                    v92,
                    (__int64)&v126,
                    (__int64)&v119,
                    (__int64)&v121,
                    (__int64)&Size_4,
                    (__int64)&v118,
                    (__int64)&v120);
                }
                RAIIBufferLock::~RAIIBufferLock((RAIIBufferLock *)&v124);
              }
              else if ( (unsigned int)dword_1801B76C8 > 2 )
              {
                Size_4 = 1892;
                v118 = "pInternalOutSample->GetBufferByIndex failed";
                Size = Sample;
                v116 = "EncodeMFT";
                v119 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
                v120 = "Error HResult failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                  v85,
                  (unsigned int)qword_18019FEA8,
                  v86,
                  v87,
                  (__int64)&v120,
                  (__int64)&Size,
                  (__int64)&v119,
                  (__int64)&Size_4,
                  (__int64)&v116,
                  (__int64)&v118);
              }
LABEL_141:
              TCntPtr<IRdpSQMLogger>::SafeRelease(&v117, v84, v86);
              TCntPtr<IRdpSQMLogger>::SafeRelease(&Src, v88, v89);
LABEL_136:
              v66 = v113;
              if ( !v113 )
                return (unsigned int)Sample;
              v113 = 0;
              goto LABEL_174;
            case 603:
            case 211:
              v56 = -2147024809;
              Sample = -2147024809;
              if ( (unsigned int)dword_1801B76C8 <= 2 )
                goto LABEL_172;
              v104 = "Received METransformDrainComplete or  MEEndOfPresentation from the MFT for EncodeMFT, it is illegal"
                     " for the low latency encoder";
              LODWORD(v119) = 1953;
              v110 = -2147024809;
              v105 = (__int16 *)byte_18019FD13;
LABEL_171:
              v126 = (unsigned __int8 *)v104;
              v121 = (struct AdvanceFeatureMap *)"EncodeMFT";
              v120 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
              v118 = "Error HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v56,
                (_DWORD)v105,
                v57,
                v58,
                (__int64)&v118,
                (__int64)&v110,
                (__int64)&v120,
                (__int64)&v119,
                (__int64)&v121,
                (__int64)&v126);
              goto LABEL_172;
          }
          Sample = -2147467259;
          if ( (unsigned int)dword_1801B76C8 <= 2 )
            goto LABEL_172;
          v104 = "Received an Error from the MFT for EncodeMFT, but error is unknown";
          LODWORD(v119) = 1958;
          v105 = (__int16 *)qword_18019FC20;
        }
      }
      v110 = Sample;
      goto LABEL_171;
    }
    Sample = v55(v54, 1, &v113);
    if ( Sample != -1072873856 )
      goto LABEL_84;
    if ( (unsigned int)dword_1801B76C8 > 5 )
    {
      v110 = v6;
      v118 = "MF_E_NO_EVENTS_AVAILABLE received. ";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v56,
        (unsigned int)&dword_1801A0104,
        v57,
        v58,
        (__int64)&v118,
        (__int64)&v110);
    }
    Sleep(0xAu);
LABEL_110:
    v78 = v113;
    if ( v113 )
    {
      v113 = 0;
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v78 + 16LL))(v78);
    }
    v113 = 0;
    v115 = 0;
    v122 = 0;
    v123 = 0;
  }
  while ( v6 < 0xA );
  if ( v53 )
  {
    if ( (unsigned int)dword_1801B76C8 > 5 )
    {
      v118 = "Exiting because (count >= MAX_HARDWARE_ENCODER_COUNT)!";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v78,
        (unsigned int)&byte_1801A00DF,
        v59,
        v60,
        (__int64)&v118);
    }
  }
  else if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v110 = 1814;
    v118 = "EncodeMFT";
    Size_4 = Sample;
    v116 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
    Src = "MF_E_NO_EVENTS_AVAILABLE received - Exiting!";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)v78,
      (unsigned int)byte_1801A0189,
      v59,
      v60,
      (__int64)&Src,
      (__int64)&Size_4,
      (__int64)&v116,
      (__int64)&v110,
      (__int64)&v118);
  }
LABEL_155:
  v102 = v113;
  if ( v113 )
  {
    v113 = 0;
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v102 + 16LL))(v102);
  }
LABEL_157:
  v103 = (RateControlHW *)*((_QWORD *)this + 32);
  if ( v103 && !*((_DWORD *)this + 46) )
    RateControlHW::Update(v103, 8 * *a3);
  return (unsigned int)Sample;
}

```

## disassembly

```asm
0x180087538  push    rbp
0x18008753a  push    rbx
0x18008753b  push    rsi
0x18008753c  push    rdi
0x18008753d  push    r12
0x18008753f  push    r13
0x180087541  push    r14
0x180087543  push    r15
0x180087545  lea     rbp, [rsp-8]
0x18008754a  sub     rsp, 108h
0x180087551  mov     rax, cs:__security_cookie
0x180087558  xor     rax, rsp
0x18008755b  mov     [rbp+40h+var_48], rax
0x18008755f  mov     rsi, [rbp+40h+arg_20]
0x180087563  xor     r13d, r13d
0x180087566  mov     r15, r9
0x180087569  mov     [rsp+140h+var_C8], r9
0x18008756e  mov     r12, r8
0x180087571  mov     r14, rdx
0x180087574  mov     rdi, rcx
0x180087577  mov     [rbp+40h+var_68], rdx
0x18008757b  mov     [rbp+40h+var_A0], rsi
0x18008757f  cmp     [rbp+40h+arg_28], r13d
0x180087583  jz      short loc_1800875E4
0x180087585  cmp     [r8], r13d
0x180087588  jnz     short loc_1800875E4
0x18008758a  mov     ebx, r13d
0x18008758d  mov     rax, cs:WPP_GLOBAL_Control
0x180087594  lea     rsi, WPP_GLOBAL_Control
0x18008759b  cmp     rax, rsi
0x18008759e  jz      loc_180088A67
0x1800875a4  test    dword ptr [rax+1Ch], 100h
0x1800875ab  jz      loc_180088A67
0x1800875b1  cmp     byte ptr [rax+19h], 5
0x1800875b5  jb      loc_180088A67
0x1800875bb  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800875c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800875c8  lea     edx, [r13+28h]
0x1800875cc  mov     r9d, eax
0x1800875cf  lea     r8, WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids
0x1800875d6  mov     rcx, [rcx+10h]
0x1800875da  call    WPP_SF_d
0x1800875df  jmp     loc_180088A67
0x1800875e4  mov     rcx, [rcx+40h]
0x1800875e8  xor     eax, eax
0x1800875ea  xor     edx, edx
0x1800875ec  cmp     [rdi+68h], r13
0x1800875f0  jnz     loc_180087D99
0x1800875f6  xorps   xmm0, xmm0
0x1800875f9  mov     [rbp+40h+var_68], rax
0x1800875fd  mov     [rbp+40h+var_60], eax
0x180087600  lea     r8, [rbp+40h+var_68]
0x180087604  movups  [rbp+40h+var_98], xmm0
0x180087608  movups  [rbp+40h+var_88], xmm0
0x18008760c  mov     rax, [rcx]
0x18008760f  mov     rax, [rax+38h]
0x180087613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087618  mov     ebx, eax
0x18008761a  test    eax, eax
0x18008761c  jns     loc_1800876B8
0x180087622  mov     ecx, cs:dword_1801B76C8
0x180087628  cmp     ecx, 2
0x18008762b  jbe     loc_180088A67
0x180087631  lea     rax, aFailedToGetOut; "Failed to get output stream info"
0x180087638  mov     [rsp+140h+var_D0], 678h
0x180087640  lea     rdx, byte_1801A054D
0x180087647  mov     [rsp+140h+var_C8], rax
0x18008764c  lea     rax, aEncodemft; "EncodeMFT"
0x180087653  mov     [rsp+140h+Src], rax
0x180087658  lea     rax, aOnecoreuapTerm_2; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18008765f  mov     [rbp+40h+var_C0], rax
0x180087663  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008766a  mov     [rsp+140h+var_E0], rax
0x18008766f  lea     rax, [rsp+140h+var_C8]
0x180087674  mov     [rsp+140h+var_F8], rax
0x180087679  lea     rax, [rsp+140h+Src]
0x18008767e  mov     [rsp+140h+var_100], rax
0x180087683  lea     rax, [rsp+140h+var_D0]
0x180087688  mov     [rsp+140h+var_108], rax
0x18008768d  lea     rax, [rbp+40h+var_C0]
0x180087691  mov     [rsp+140h+var_110], rax
0x180087696  lea     rax, [rsp+140h+Size]
0x18008769b  mov     [rsp+140h+var_118], rax
0x1800876a0  lea     rax, [rsp+140h+var_E0]
0x1800876a5  mov     dword ptr [rsp+140h+Size], ebx
0x1800876a9  mov     [rsp+140h+var_120], rax
0x1800876ae  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800876b3  jmp     loc_180088A67
0x1800876b8  test    dword ptr [rbp+40h+var_68], 300h
0x1800876bf  jnz     short loc_18008770A
0x1800876c1  mov     edx, dword ptr [rbp+40h+var_68+4]; unsigned int
0x1800876c4  test    edx, edx
0x1800876c6  jz      short loc_18008770A
0x1800876c8  lea     r8, [rdi+58h]; struct IMFSample **
0x1800876cc  cmp     [r8], r13
0x1800876cf  jnz     short loc_18008770A
0x1800876d1  mov     rcx, [rdi+60h]; this
0x1800876d5  call    ?CreateSample@CMFApi@@QEAAJIPEAPEAUIMFSample@@@Z; CMFApi::CreateSample(uint,IMFSample * *)
0x1800876da  mov     ebx, eax
0x1800876dc  test    eax, eax
0x1800876de  jns     short loc_18008770A
0x1800876e0  mov     eax, cs:dword_1801B76C8
0x1800876e6  cmp     eax, 2
0x1800876e9  jbe     loc_180088A67
0x1800876ef  lea     rax, aMSpmfapiCreate; "m_spMFApi->CreateSample failed "
0x1800876f6  mov     [rsp+140h+var_D0], 687h
0x1800876fe  lea     rdx, byte_1801A04AB
0x180087705  jmp     loc_180087647
0x18008770a  mov     rax, [rdi+58h]
0x18008770e  xor     r9d, r9d
0x180087711  mov     rcx, [rdi+40h]
0x180087715  mov     r8, r15
0x180087718  mov     qword ptr [rbp+40h+var_98+8], rax
0x18008771c  xor     edx, edx
0x18008771e  mov     rax, [rcx]
0x180087721  mov     rax, [rax+0C0h]
0x180087728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008772d  mov     ebx, eax
0x18008772f  test    eax, eax
0x180087731  jns     short loc_18008775D
0x180087733  mov     eax, cs:dword_1801B76C8
0x180087739  cmp     eax, 2
0x18008773c  jbe     loc_180088A67
0x180087742  lea     rax, aFailedToProces_0; "Failed to process the encoder input"
0x180087749  mov     [rsp+140h+var_D0], 68Eh
0x180087751  lea     rdx, dword_1801A04FC
0x180087758  jmp     loc_180087647
0x18008775d  mov     rcx, [rdi+40h]
0x180087761  lea     rdx, [rsp+140h+Size+4]
0x180087766  mov     dword ptr [rsp+140h+Size+4], r13d
0x18008776b  lea     r9, [rbp+40h+var_98]
0x18008776f  mov     [rsp+140h+var_120], rdx
0x180087774  xor     edx, edx
0x180087776  mov     rax, [rcx]
0x180087779  lea     r8d, [rdx+1]
0x18008777d  mov     rax, [rax+0C8h]
0x180087784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087789  cmp     eax, 0C00D6D72h
0x18008778e  mov     ebx, r13d
0x180087791  cmovnz  ebx, eax
0x180087794  test    ebx, ebx
0x180087796  jns     short loc_1800877C2
0x180087798  mov     eax, cs:dword_1801B76C8
0x18008779e  cmp     eax, 2
0x1800877a1  jbe     loc_180088A67
0x1800877a7  lea     rax, aFailedToProces_1; "Failed to process encoder output"
0x1800877ae  mov     [rsp+140h+var_D0], 696h
0x1800877b6  lea     rdx, word_1801A045A
0x1800877bd  jmp     loc_180087647
0x1800877c2  cmp     qword ptr [rbp+40h+var_98+8], r13
0x1800877c6  jnz     short loc_180087822
0x1800877c8  mov     rax, cs:WPP_GLOBAL_Control
0x1800877cf  lea     rsi, WPP_GLOBAL_Control
0x1800877d6  cmp     rax, rsi
0x1800877d9  jz      short loc_180087818
0x1800877db  test    byte ptr [rax+1Ch], 8
0x1800877df  jz      short loc_180087818
0x1800877e1  cmp     byte ptr [rax+19h], 2
0x1800877e5  jb      short loc_180087818
0x1800877e7  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800877ed  lea     rcx, aOutputdatabufP_0; "OutputDataBuf.pSample"
0x1800877f4  mov     edx, 29h ; ')'
0x1800877f9  mov     [rsp+140h+var_120], rcx
0x1800877fe  lea     r8, WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids
0x180087805  mov     rcx, cs:WPP_GLOBAL_Control
0x18008780c  mov     r9d, eax
0x18008780f  mov     rcx, [rcx+10h]
0x180087813  call    WPP_SF_Ds
0x180087818  mov     ebx, 80004003h
0x18008781d  jmp     loc_180088A67
0x180087822  cmp     [rdi+0B0h], r13d
0x180087829  jz      loc_1800879CA
0x18008782f  mov     rcx, [rdi+58h]
0x180087833  lea     r8, [rsp+140h+Size]
0x180087838  mov     dword ptr [rsp+140h+Size], r13d
0x18008783d  lea     rdx, MFSampleExtension_VideoEncodeQPMap
0x180087844  mov     rax, [rcx]
0x180087847  mov     rax, [rax+70h]
0x18008784b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087850  test    eax, eax
0x180087852  js      loc_1800879CA
0x180087858  mov     eax, dword ptr [rsp+140h+Size]
0x18008785c  test    eax, eax
0x18008785e  jz      loc_1800879CA
0x180087864  cmp     eax, [rdi+90h]
0x18008786a  jz      loc_18008790C
0x180087870  mov     rcx, [rdi+78h]; Block
0x180087874  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180087879  mov     ecx, dword ptr [rsp+140h+Size]; unsigned __int64
0x18008787d  mov     [rdi+90h], r13d
0x180087884  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180087889  mov     [rdi+78h], rax
0x18008788d  test    rax, rax
0x180087890  jnz     short loc_1800878EC
0x180087892  mov     rax, cs:WPP_GLOBAL_Control
0x180087899  lea     rsi, WPP_GLOBAL_Control
0x1800878a0  cmp     rax, rsi
0x1800878a3  jz      short loc_1800878E2
0x1800878a5  test    byte ptr [rax+1Ch], 8
0x1800878a9  jz      short loc_1800878E2
0x1800878ab  cmp     byte ptr [rax+19h], 2
0x1800878af  jb      short loc_1800878E2
0x1800878b1  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800878b7  lea     rcx, aByte; "BYTE"
0x1800878be  mov     edx, 2Ah ; '*'
0x1800878c3  mov     [rsp+140h+var_120], rcx
0x1800878c8  lea     r8, WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids
0x1800878cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800878d6  mov     r9d, eax
0x1800878d9  mov     rcx, [rcx+10h]
0x1800878dd  call    WPP_SF_Ds
0x1800878e2  mov     ebx, 8007000Eh
0x1800878e7  jmp     loc_180088A67
0x1800878ec  mov     r8d, dword ptr [rsp+140h+Size]; Size
0x1800878f1  mov     edx, 2; Val
0x1800878f6  mov     rcx, rax; void *
0x1800878f9  mov     [rdi+90h], r8d
0x180087900  mov     [rdi+80h], rax
0x180087907  call    memset_0
0x18008790c  mov     rcx, [rdi+58h]
0x180087910  lea     rdx, MFSampleExtension_VideoEncodeQPMap
0x180087917  mov     r9d, [rdi+90h]
0x18008791e  mov     r8, [rdi+80h]
0x180087925  mov     [rsp+140h+var_120], r13
0x18008792a  mov     rax, [rcx]
0x18008792d  mov     rax, [rax+78h]
0x180087931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087936  mov     ebx, eax
0x180087938  test    eax, eax
0x18008793a  jns     loc_1800879CA
0x180087940  mov     eax, cs:dword_1801B76C8
0x180087946  cmp     eax, 2
0x180087949  jbe     loc_180088A67
0x18008794f  lea     rax, aMfsampleextens; "MFSampleExtension_VideoEncodeQPMap fail"...
0x180087956  mov     [rsp+140h+var_D0], 6B1h
0x18008795e  mov     [rsp+140h+var_C8], rax
0x180087963  lea     rdx, byte_1801A0409
0x18008796a  lea     rax, aEncodemft; "EncodeMFT"
0x180087971  mov     [rsp+140h+var_F0], ebx
0x180087975  mov     [rsp+140h+Src], rax
0x18008797a  lea     rax, aOnecoreuapTerm_2; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x180087981  mov     [rbp+40h+var_C0], rax
0x180087985  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008798c  mov     [rbp+40h+var_B0], rax
0x180087990  lea     rax, [rsp+140h+var_C8]
0x180087995  mov     [rsp+140h+var_F8], rax
0x18008799a  lea     rax, [rsp+140h+Src]
0x18008799f  mov     [rsp+140h+var_100], rax
0x1800879a4  lea     rax, [rsp+140h+var_D0]
0x1800879a9  mov     [rsp+140h+var_108], rax
0x1800879ae  lea     rax, [rbp+40h+var_C0]
0x1800879b2  mov     [rsp+140h+var_110], rax
0x1800879b7  lea     rax, [rsp+140h+var_F0]
0x1800879bc  mov     [rsp+140h+var_118], rax
0x1800879c1  lea     rax, [rbp+40h+var_B0]
0x1800879c5  jmp     loc_1800876A9
0x1800879ca  mov     rdx, rsi; struct AdvanceFeatureMap *
0x1800879cd  mov     rcx, rdi; this
0x1800879d0  call    ?UpdateRectList@AvcEncoder@@AEAAJPEAVAdvanceFeatureMap@@@Z; AvcEncoder::UpdateRectList(AdvanceFeatureMap *)
0x1800879d5  mov     ebx, eax
0x1800879d7  test    eax, eax
0x1800879d9  jns     loc_180087A69
0x1800879df  mov     eax, cs:dword_1801B76C8
0x1800879e5  cmp     eax, 2
0x1800879e8  jbe     loc_180088A67
0x1800879ee  lea     rax, aUpdaterectlist_0; "UpdateRectList failed"
0x1800879f5  mov     [rsp+140h+var_F0], 6BAh
0x1800879fd  mov     [rsp+140h+var_C8], rax
0x180087a02  lea     rdx, qword_1801A03B8
0x180087a09  lea     rax, aEncodemft; "EncodeMFT"
0x180087a10  mov     [rsp+140h+var_D0], ebx
0x180087a14  mov     [rsp+140h+Src], rax
0x180087a19  lea     rax, aOnecoreuapTerm_2; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x180087a20  mov     [rbp+40h+var_C0], rax
0x180087a24  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180087a2b  mov     [rbp+40h+var_B0], rax
0x180087a2f  lea     rax, [rsp+140h+var_C8]
0x180087a34  mov     [rsp+140h+var_F8], rax
0x180087a39  lea     rax, [rsp+140h+Src]
0x180087a3e  mov     [rsp+140h+var_100], rax
0x180087a43  lea     rax, [rsp+140h+var_F0]
0x180087a48  mov     [rsp+140h+var_108], rax
0x180087a4d  lea     rax, [rbp+40h+var_C0]
0x180087a51  mov     [rsp+140h+var_110], rax
0x180087a56  lea     rax, [rsp+140h+var_D0]
0x180087a5b  mov     [rsp+140h+var_118], rax
0x180087a60  lea     rax, [rbp+40h+var_B0]
0x180087a64  jmp     loc_1800876A9
0x180087a69  mov     rcx, qword ptr [rbp+40h+var_98+8]
0x180087a6d  lea     r8, [rsp+140h+var_E0]
0x180087a72  mov     [rsp+140h+var_E0], r13
0x180087a77  xor     edx, edx
0x180087a79  mov     rax, [rcx]
0x180087a7c  mov     rax, [rax+140h]
0x180087a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087a88  mov     ebx, eax
0x180087a8a  test    eax, eax
0x180087a8c  jns     loc_180087B30
0x180087a92  mov     eax, cs:dword_1801B76C8
0x180087a98  cmp     eax, 2
  ... truncated ...
```
