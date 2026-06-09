# PipeETWEvents::Enable(ulong,ulong)

- ea: `0x140089f50`
- end: `0x14008aeda`
- name: `?Enable@PipeETWEvents@@UEAAJKK@Z`
- size: `3978`
- prototype: `__int64 __fastcall(PipeETWEvents *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14008aee0`

## callees

- `0x140003b08`
- `0x14000b7d8`
- `0x14000d078`
- `0x14000dcac`
- `0x14003c0f0`
- `0x140059568`
- `0x140059b04`
- `0x140089cf4`
- `0x140089f50`
- `0x14008e0cc`
- `0x14008e2a4`

## string_xrefs

- `0x14008a4b3`: `RDV::RDP::Encoder::ProtocolBytes`
- `0x14008a4fa`: `Failed to initialize RDV::RDP::Encoder::ProtocolBytes perf counter`
- `0x14008a855`: `RDV::RDP::GraphicsPipelineMicroStats::GfxInterFrameCacheHitRects`
- `0x14008a8a1`: `RDPAPI_GetGenericCounter GfxInterFrameCacheHitRects failed`
- `0x14008a8b6`: `RDV::RDP::GraphicsPipelineMicroStats::GfxInterFrameCacheOutARects`
- `0x14008a902`: `RDPAPI_GetGenericCounter GfxInterFrameCacheOutARects failed`
- `0x14008a793`: `RDV::RDP::GraphicsPipelineMicroStats::GfxMDOutMoves`
- `0x14008a7df`: `RDPAPI_GetGenericCounter GfxMDOutMoves failed`
- `0x14008a7f4`: `RDV::RDP::GraphicsPipelineMicroStats::GfxInterFrameCacheInARects`
- `0x14008a840`: `RDPAPI_GetGenericCounter GfxInterFrameCacheInARects failed`
- `0x14008a9d9`: `RDV::RDP::GraphicsPipelineMicroStats::GfxCacheInsertImports`
- `0x14008aa25`: `RDPAPI_GetGenericCounter GfxCacheInsertImports failed`
- `0x14008aa3a`: `RDV::RDP::GraphicsPipelineMicroStats::GfxCacheEvictRects`
- `0x14008aa86`: `RDPAPI_GetGenericCounter GfxCacheEvictRects failed`
- `0x14008a917`: `RDV::RDP::GraphicsPipelineMicroStats::GfxIntraFrameCacheHitRects`
- `0x14008a963`: `RDPAPI_GetGenericCounter GfxIntraFrameCacheHitRects failed`
- `0x14008a978`: `RDV::RDP::GraphicsPipelineMicroStats::GfxCacheInsertRects`
- `0x14008a9c4`: `RDPAPI_GetGenericCounter GfxCacheInsertRects failed`

## pseudocode

```c
__int64 __fastcall PipeETWEvents::Enable(PipeETWEvents *this, int a2, int a3)
{
  int v5; // r8d
  int v6; // r9d
  int LongCounter; // ebx
  int v8; // r9d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v10; // edx
  const char *v11; // rcx
  int v12; // r9d
  int v13; // r8d
  int v14; // r9d
  int v15; // r8d
  int v16; // r9d
  int v17; // r8d
  int v18; // r9d
  int v19; // r8d
  int v20; // r9d
  int v21; // r8d
  int v22; // r9d
  int v23; // r8d
  int v24; // r9d
  int v25; // r8d
  int v26; // r9d
  int v27; // r8d
  int v28; // r9d
  int v29; // r8d
  int v30; // r9d
  int v31; // r8d
  int v32; // r9d
  int v33; // r8d
  int v34; // r9d
  int v35; // r8d
  int v36; // r9d
  int v37; // r8d
  int v38; // r9d
  int v39; // r8d
  int v40; // r9d
  int v41; // r8d
  int v42; // r9d
  int v43; // r8d
  int v44; // r9d
  int v45; // r8d
  int v46; // r9d
  int v47; // r8d
  int v48; // r9d
  int v49; // r8d
  int v50; // r9d
  int v51; // r8d
  int v52; // r9d
  int v53; // r8d
  int v54; // r9d
  int v55; // r8d
  int v56; // r9d
  int v57; // r8d
  int v58; // r9d
  int v59; // r8d
  int v60; // r9d
  int v61; // r8d
  int v62; // r9d
  PipeETWEvents *v63; // rcx
  PipeETWEvents *v64; // rcx
  PipeETWEvents *v65; // rcx
  PipeETWEvents *v66; // rcx
  PipeETWEvents *v67; // rcx
  char *v69; // [rsp+80h] [rbp+8h] BYREF
  int v70; // [rsp+90h] [rbp+18h]

  v70 = a3;
  v69 = (char *)this + 88;
  CTSCriticalSection::Lock((PipeETWEvents *)((char *)this + 88));
  if ( *((_QWORD *)this + 14) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 112);
    *((_QWORD *)this + 14) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 112);
  }
  if ( *((_QWORD *)this + 15) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 120);
    *((_QWORD *)this + 15) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 120);
  }
  if ( *((_QWORD *)this + 16) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 128);
    *((_QWORD *)this + 16) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 128);
  }
  *((_DWORD *)this + 36) = 0;
  *((_DWORD *)this + 37) = a2;
  *((_DWORD *)this + 38) = 0;
  if ( *((_QWORD *)this + 20) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 160);
    *((_QWORD *)this + 20) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 160);
  }
  if ( *((_QWORD *)this + 21) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 168);
    *((_QWORD *)this + 21) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 168);
  }
  if ( *((_QWORD *)this + 22) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 176);
    *((_QWORD *)this + 22) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 176);
  }
  if ( *((_QWORD *)this + 23) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 184);
    *((_QWORD *)this + 23) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 184);
  }
  if ( *((_QWORD *)this + 24) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 192);
    *((_QWORD *)this + 24) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 192);
  }
  if ( *((_QWORD *)this + 25) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 200);
    *((_QWORD *)this + 25) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 200);
  }
  if ( *((_QWORD *)this + 26) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 208);
    *((_QWORD *)this + 26) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 208);
  }
  if ( *((_QWORD *)this + 27) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 216);
    *((_QWORD *)this + 27) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 216);
  }
  if ( *((_QWORD *)this + 28) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 224);
    *((_QWORD *)this + 28) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 224);
  }
  if ( *((_QWORD *)this + 29) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 232);
    *((_QWORD *)this + 29) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 232);
  }
  if ( *((_QWORD *)this + 30) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 240);
    *((_QWORD *)this + 30) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 240);
  }
  if ( *((_QWORD *)this + 31) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 248);
    *((_QWORD *)this + 31) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 248);
  }
  if ( *((_QWORD *)this + 32) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 256);
    *((_QWORD *)this + 32) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 256);
  }
  if ( *((_QWORD *)this + 33) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 264);
    *((_QWORD *)this + 33) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 264);
  }
  if ( *((_QWORD *)this + 34) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 272);
    *((_QWORD *)this + 34) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 272);
  }
  if ( *((_QWORD *)this + 35) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 280);
    *((_QWORD *)this + 35) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 280);
  }
  if ( *((_QWORD *)this + 36) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 288);
    *((_QWORD *)this + 36) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 288);
  }
  if ( *((_QWORD *)this + 37) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 296);
    *((_QWORD *)this + 37) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 296);
  }
  if ( *((_QWORD *)this + 38) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 304);
    *((_QWORD *)this + 38) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 304);
  }
  if ( *((_QWORD *)this + 17) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 136);
    *((_QWORD *)this + 17) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 136);
  }
  if ( *((_QWORD *)this + 39) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 312);
    *((_QWORD *)this + 39) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 312);
  }
  if ( *((_QWORD *)this + 52) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 416);
    *((_QWORD *)this + 52) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 416);
  }
  if ( *((_QWORD *)this + 40) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 320);
    *((_QWORD *)this + 40) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 320);
  }
  if ( *((_QWORD *)this + 41) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 328);
    *((_QWORD *)this + 41) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 328);
  }
  if ( *((_QWORD *)this + 42) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 336);
    *((_QWORD *)this + 42) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 336);
  }
  operator delete(*((void **)this + 8));
  v5 = v70;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  LongCounter = RDPAPI_GetLongCounter((unsigned int)L"RDV::RDP::Encoder::FrameEncodingStart", a2, v5, v6);
  if ( LongCounter < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 13;
      v11 = "Failed to initialize RDV::RDP::Encoder::FrameEncodingStart counter";
LABEL_62:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        (unsigned int)WPP_6f5e31529dd9301685fed12fae0064c9_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v11,
        LongCounter);
      goto LABEL_201;
    }
    goto LABEL_201;
  }
  LongCounter = RDPAPI_GetLongCounter((unsigned int)L"RDV::RDP::Encoder::FrameEncodingEnd", a2, v70, v8);
  if ( LongCounter >= 0 )
  {
    LongCounter = RDPAPI_GetLongCounter((unsigned int)L"RDV::RDP::Encoder::ProtocolBytes", a2, 0, v12);
    if ( LongCounter < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 15;
        v11 = "Failed to initialize RDV::RDP::Encoder::ProtocolBytes perf counter";
        goto LABEL_62;
      }
      goto LABEL_201;
    }
    LongCounter = RDPAPI_GetGenericCounter(
                    (unsigned int)L"RDV::RDP::GraphicsPipeline::ProgressiveEncodingStatus",
                    a2,
                    v13,
                    v14);
    if ( LongCounter < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 16;
        v11 = "Failed to initialize RDV::RDP::GraphicsPipeline::ProgressiveEncodingStatus perf counter";
        goto LABEL_62;
      }
      goto LABEL_201;
    }
    LongCounter = RDPAPI_GetGenericCounter(
                    (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxUTInVideoARects",
                    a2,
                    v15,
                    v16);
    if ( LongCounter < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 17;
        v11 = "RDPAPI_GetGenericCounter GfxUTInVideoARects failed";
        goto LABEL_62;
      }
      goto LABEL_201;
    }
    LongCounter = RDPAPI_GetGenericCounter(
                    (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxUTOutEncARects",
                    a2,
                    v17,
                    v18);
    if ( LongCounter < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 18;
        v11 = "RDPAPI_GetGenericCounter GfxUTOutEncARects failed";
        goto LABEL_62;
      }
      goto LABEL_201;
    }
    LongCounter = RDPAPI_GetGenericCounter(
                    (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxDRInARects",
                    a2,
                    v19,
                    v20);
    if ( LongCounter < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_201;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 19;
      goto LABEL_93;
    }
    LongCounter = RDPAPI_GetGenericCounter(
                    (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxDROutARects",
                    a2,
                    v21,
                    v22);
    if ( LongCounter >= 0 )
    {
      LongCounter = RDPAPI_GetGenericCounter(
                      (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxMDInARects",
                      a2,
                      v23,
                      v24);
      if ( LongCounter < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_201;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 21;
LABEL_93:
        v11 = "RDPAPI_GetGenericCounter GfxMDInARects failed";
        goto LABEL_62;
      }
      LongCounter = RDPAPI_GetGenericCounter(
                      (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxMDOutARects",
                      a2,
                      v25,
                      v26);
      if ( LongCounter >= 0 )
      {
        LongCounter = RDPAPI_GetGenericCounter(
                        (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxMDOutMoves",
                        a2,
                        v27,
                        v28);
        if ( LongCounter >= 0 )
        {
          LongCounter = RDPAPI_GetGenericCounter(
                          (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxInterFrameCacheInARects",
                          a2,
                          v29,
                          v30);
          if ( LongCounter >= 0 )
          {
            LongCounter = RDPAPI_GetGenericCounter(
                            (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxInterFrameCacheHitRects",
                            a2,
                            v31,
                            v32);
            if ( LongCounter >= 0 )
            {
              LongCounter = RDPAPI_GetGenericCounter(
                              (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxInterFrameCacheOutARects",
                              a2,
                              v33,
                              v34);
              if ( LongCounter >= 0 )
              {
                LongCounter = RDPAPI_GetGenericCounter(
                                (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxIntraFrameCacheHitRects",
                                a2,
                                v35,
                                v36);
                if ( LongCounter >= 0 )
                {
                  LongCounter = RDPAPI_GetGenericCounter(
                                  (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxCacheInsertRects",
                                  a2,
                                  v37,
                                  v38);
                  if ( LongCounter >= 0 )
                  {
                    LongCounter = RDPAPI_GetGenericCounter(
                                    (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxCacheInsertImports",
                                    a2,
                                    v39,
                                    v40);
                    if ( LongCounter >= 0 )
                    {
                      LongCounter = RDPAPI_GetGenericCounter(
                                      (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxCacheEvictRects",
                                      a2,
                                      v41,
                                      v42);
                      if ( LongCounter >= 0 )
                      {
                        LongCounter = RDPAPI_GetGenericCounter(
                                        (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxClassifierInARects",
                                        a2,
                                        v43,
                                        v44);
                        if ( LongCounter >= 0 )
                        {
                          LongCounter = RDPAPI_GetGenericCounter(
                                          (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxClassifierOutTextRects",
                                          a2,
                                          v45,
                                          v46);
                          if ( LongCounter >= 0 )
                          {
                            LongCounter = RDPAPI_GetGenericCounter(
                                            (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxClassifierOutImageRects",
                                            a2,
                                            v47,
                                            v48);
                            if ( LongCounter >= 0 )
                            {
                              LongCounter = RDPAPI_GetGenericCounter(
                                              (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxClassifierOutSolidRects",
                                              a2,
                                              v49,
                                              v50);
                              if ( LongCounter >= 0 )
                              {
                                LongCounter = RDPAPI_GetGenericCounter(
                                                (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxClearCodec",
                                                a2,
                                                v51,
                                                v52);
                                if ( LongCounter >= 0 )
                                {
                                  LongCounter = RDPAPI_GetGenericCounter(
                                                  (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxCodecStats",
                                                  a2,
                                                  v53,
                                                  v54);
                                  if ( LongCounter >= 0 )
                                  {
                                    LongCounter = RDPAPI_GetGenericCounter(
                                                    (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxDeltaReducedRects",
                                                    a2,
                                                    v55,
                                                    v56);
                                    if ( LongCounter >= 0 )
                                    {
                                      LongCounter = RDPAPI_GetGenericCounter(
                                                      (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxDirtyRects",
                                                      a2,
                                                      v57,
                                                      v58);
                                      if ( LongCounter >= 0 )
                                      {
                                        LongCounter = RDPAPI_GetGenericCounter(
                                                        (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxPrimitiveRects",
                                                        a2,
                                                        v59,
                                                        v60);
                                        if ( LongCounter >= 0 )
                                        {
                                          LongCounter = RDPAPI_GetGenericCounter(
                                                          (unsigned int)L"RDV::CLOUDDV::QOE::QOEServerFrameDetails",
                                                          a2,
                                                          v61,
                                                          v62);
                                          if ( LongCounter >= 0 )
                                          {
                                            *((_DWORD *)this + 106) = 0;
                                            PipeETWEvents::Allocate_Accumulator(v63, (void **)this + 44, 0x2000u);
                                            PipeETWEvents::Allocate_Accumulator(v64, (void **)this + 45, 0x2000u);
                                            PipeETWEvents::Allocate_Accumulator(v65, (void **)this + 46, 0x2000u);
                                            PipeETWEvents::Allocate_Accumulator(v66, (void **)this + 47, 0x6000u);
                                            PipeETWEvents::Allocate_Accumulator(v67, (void **)this + 48, 0x6000u);
                                            goto LABEL_201;
                                          }
                                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                          {
                                            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                                            v10 = 40;
                                            v11 = "RDPAPI_GetGenericCounter QOEServerFrameDetails failed";
                                            goto LABEL_62;
                                          }
                                        }
                                        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                        {
                                          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                                          v10 = 39;
                                          v11 = "RDPAPI_GetGenericCounter m_spPerfCounterGfxPrimitiveRects failed";
                                          goto LABEL_62;
                                        }
                                      }
                                      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                      {
                                        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                                        v10 = 38;
                                        v11 = "RDPAPI_GetGenericCounter m_spPerfCounterGfxDirtyRects failed";
                                        goto LABEL_62;
                                      }
                                    }
                                    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                    {
                                      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                                      v10 = 37;
                                      v11 = "RDPAPI_GetGenericCounter GfxDeltaReducedRects failed";
                                      goto LABEL_62;
                                    }
                                  }
                                  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                  {
                                    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                                    v10 = 36;
                                    v11 = "RDPAPI_GetGenericCounter GfxCodecStats failed";
                                    goto LABEL_62;
                                  }
                                }
                                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                {
                                  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                                  v10 = 35;
                                  v11 = "RDPAPI_GetGenericCounter GfxClearCodec failed";
                                  goto LABEL_62;
                                }
                              }
                              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                              {
                                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                                v10 = 34;
                                v11 = "RDPAPI_GetGenericCounter GfxClassifierOutSolidRects failed";
                                goto LABEL_62;
                              }
                            }
                            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                            {
                              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                              v10 = 33;
                              v11 = "RDPAPI_GetGenericCounter GfxClassifierOutImageRects failed";
                              goto LABEL_62;
                            }
                          }
                          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                            v10 = 32;
                            v11 = "RDPAPI_GetGenericCounter GfxClassifierOutTextRects failed";
                            goto LABEL_62;
                          }
                        }
                        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                        {
                          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                          v10 = 31;
                          v11 = "RDPAPI_GetGenericCounter GfxClassifierInARects failed";
                          goto LABEL_62;
                        }
                      }
                      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                        v10 = 30;
                        v11 = "RDPAPI_GetGenericCounter GfxCacheEvictRects failed";
                        goto LABEL_62;
                      }
                    }
                    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                      v10 = 29;
                      v11 = "RDPAPI_GetGenericCounter GfxCacheInsertImports failed";
                      goto LABEL_62;
                    }
                  }
                  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                    v10 = 28;
                    v11 = "RDPAPI_GetGenericCounter GfxCacheInsertRects failed";
                    goto LABEL_62;
                  }
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                  v10 = 27;
                  v11 = "RDPAPI_GetGenericCounter GfxIntraFrameCacheHitRects failed";
                  goto LABEL_62;
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v10 = 26;
                v11 = "RDPAPI_GetGenericCounter GfxInterFrameCacheOutARects failed";
                goto LABEL_62;
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v10 = 25;
              v11 = "RDPAPI_GetGenericCounter GfxInterFrameCacheHitRects failed";
              goto LABEL_62;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v10 = 24;
            v11 = "RDPAPI_GetGenericCounter GfxInterFrameCacheInARects failed";
            goto LABEL_62;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v10 = 23;
          v11 = "RDPAPI_GetGenericCounter GfxMDOutMoves failed";
          goto LABEL_62;
        }
        goto LABEL_201;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_201;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 22;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_201;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 20;
    }
    v11 = "RDPAPI_GetGenericCounter GfxMDOutARects failed";
    goto LABEL_62;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 14;
    v11 = "Failed to initialize RDV::RDP::Encoder::FrameEncodingEn counter";
    goto LABEL_62;
  }
LABEL_201:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v69);
  return (unsigned int)LongCounter;
}

```

## disassembly

```asm
0x140089f50  mov     rax, rsp
0x140089f53  mov     [rax+10h], rbx
0x140089f57  mov     [rax+18h], r8d
0x140089f5b  push    rbp
0x140089f5c  push    rsi
0x140089f5d  push    rdi
0x140089f5e  push    r12
0x140089f60  push    r13
0x140089f62  push    r14
0x140089f64  push    r15
0x140089f66  sub     rsp, 40h
0x140089f6a  mov     rdi, rcx
0x140089f6d  mov     esi, edx
0x140089f6f  add     rcx, 58h ; 'X'; this
0x140089f73  mov     [rax+8], rcx
0x140089f77  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x140089f7c  lea     rbx, [rdi+70h]
0x140089f80  xor     r12d, r12d
0x140089f83  cmp     [rbx], r12
0x140089f86  jz      short loc_140089F9B
0x140089f88  mov     rcx, rbx
0x140089f8b  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140089f90  mov     rcx, rbx
0x140089f93  mov     [rbx], r12
0x140089f96  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x140089f9b  lea     r14, [rdi+78h]
0x140089f9f  cmp     [r14], r12
0x140089fa2  jz      short loc_140089FB7
0x140089fa4  mov     rcx, r14
0x140089fa7  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140089fac  mov     rcx, r14
0x140089faf  mov     [r14], r12
0x140089fb2  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x140089fb7  lea     r15, [rdi+80h]
0x140089fbe  cmp     [r15], r12
0x140089fc1  jz      short loc_140089FD6
0x140089fc3  mov     rcx, r15
0x140089fc6  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140089fcb  mov     rcx, r15
0x140089fce  mov     [r15], r12
0x140089fd1  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x140089fd6  lea     rbp, [rdi+0A0h]
0x140089fdd  mov     [rdi+90h], r12d
0x140089fe4  mov     [rdi+94h], esi
0x140089fea  mov     [rdi+98h], r12d
0x140089ff1  cmp     [rbp+0], r12
0x140089ff5  jz      short loc_14008A00B
0x140089ff7  mov     rcx, rbp
0x140089ffa  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140089fff  mov     rcx, rbp
0x14008a002  mov     [rbp+0], r12
0x14008a006  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a00b  lea     r13, [rdi+0A8h]
0x14008a012  cmp     [r13+0], r12
0x14008a016  jz      short loc_14008A02C
0x14008a018  mov     rcx, r13
0x14008a01b  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a020  mov     rcx, r13
0x14008a023  mov     [r13+0], r12
0x14008a027  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a02c  lea     r12, [rdi+0B0h]
0x14008a033  cmp     qword ptr [r12], 0
0x14008a038  jz      short loc_14008A052
0x14008a03a  mov     rcx, r12
0x14008a03d  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a042  mov     rcx, r12
0x14008a045  mov     qword ptr [r12], 0
0x14008a04d  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a052  lea     r12, [rdi+0B8h]
0x14008a059  cmp     qword ptr [r12], 0
0x14008a05e  jz      short loc_14008A078
0x14008a060  mov     rcx, r12
0x14008a063  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a068  mov     rcx, r12
0x14008a06b  mov     qword ptr [r12], 0
0x14008a073  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a078  lea     r12, [rdi+0C0h]
0x14008a07f  cmp     qword ptr [r12], 0
0x14008a084  jz      short loc_14008A09E
0x14008a086  mov     rcx, r12
0x14008a089  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a08e  mov     rcx, r12
0x14008a091  mov     qword ptr [r12], 0
0x14008a099  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a09e  lea     r12, [rdi+0C8h]
0x14008a0a5  cmp     qword ptr [r12], 0
0x14008a0aa  jz      short loc_14008A0C4
0x14008a0ac  mov     rcx, r12
0x14008a0af  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a0b4  mov     rcx, r12
0x14008a0b7  mov     qword ptr [r12], 0
0x14008a0bf  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a0c4  lea     r12, [rdi+0D0h]
0x14008a0cb  cmp     qword ptr [r12], 0
0x14008a0d0  jz      short loc_14008A0EA
0x14008a0d2  mov     rcx, r12
0x14008a0d5  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a0da  mov     rcx, r12
0x14008a0dd  mov     qword ptr [r12], 0
0x14008a0e5  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a0ea  lea     r12, [rdi+0D8h]
0x14008a0f1  cmp     qword ptr [r12], 0
0x14008a0f6  jz      short loc_14008A110
0x14008a0f8  mov     rcx, r12
0x14008a0fb  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a100  mov     rcx, r12
0x14008a103  mov     qword ptr [r12], 0
0x14008a10b  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a110  lea     r12, [rdi+0E0h]
0x14008a117  cmp     qword ptr [r12], 0
0x14008a11c  jz      short loc_14008A136
0x14008a11e  mov     rcx, r12
0x14008a121  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a126  mov     rcx, r12
0x14008a129  mov     qword ptr [r12], 0
0x14008a131  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a136  lea     r12, [rdi+0E8h]
0x14008a13d  cmp     qword ptr [r12], 0
0x14008a142  jz      short loc_14008A15C
0x14008a144  mov     rcx, r12
0x14008a147  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a14c  mov     rcx, r12
0x14008a14f  mov     qword ptr [r12], 0
0x14008a157  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a15c  lea     r12, [rdi+0F0h]
0x14008a163  cmp     qword ptr [r12], 0
0x14008a168  jz      short loc_14008A182
0x14008a16a  mov     rcx, r12
0x14008a16d  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a172  mov     rcx, r12
0x14008a175  mov     qword ptr [r12], 0
0x14008a17d  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a182  lea     r12, [rdi+0F8h]
0x14008a189  cmp     qword ptr [r12], 0
0x14008a18e  jz      short loc_14008A1A8
0x14008a190  mov     rcx, r12
0x14008a193  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a198  mov     rcx, r12
0x14008a19b  mov     qword ptr [r12], 0
0x14008a1a3  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a1a8  lea     r12, [rdi+100h]
0x14008a1af  cmp     qword ptr [r12], 0
0x14008a1b4  jz      short loc_14008A1CE
0x14008a1b6  mov     rcx, r12
0x14008a1b9  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a1be  mov     rcx, r12
0x14008a1c1  mov     qword ptr [r12], 0
0x14008a1c9  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a1ce  lea     r12, [rdi+108h]
0x14008a1d5  cmp     qword ptr [r12], 0
0x14008a1da  jz      short loc_14008A1F4
0x14008a1dc  mov     rcx, r12
0x14008a1df  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a1e4  mov     rcx, r12
0x14008a1e7  mov     qword ptr [r12], 0
0x14008a1ef  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a1f4  lea     r12, [rdi+110h]
0x14008a1fb  cmp     qword ptr [r12], 0
0x14008a200  jz      short loc_14008A21A
0x14008a202  mov     rcx, r12
0x14008a205  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a20a  mov     rcx, r12
0x14008a20d  mov     qword ptr [r12], 0
0x14008a215  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a21a  lea     r12, [rdi+118h]
0x14008a221  cmp     qword ptr [r12], 0
0x14008a226  jz      short loc_14008A240
0x14008a228  mov     rcx, r12
0x14008a22b  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a230  mov     rcx, r12
0x14008a233  mov     qword ptr [r12], 0
0x14008a23b  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a240  lea     r12, [rdi+120h]
0x14008a247  cmp     qword ptr [r12], 0
0x14008a24c  jz      short loc_14008A266
0x14008a24e  mov     rcx, r12
0x14008a251  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a256  mov     rcx, r12
0x14008a259  mov     qword ptr [r12], 0
0x14008a261  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a266  lea     r12, [rdi+128h]
0x14008a26d  cmp     qword ptr [r12], 0
0x14008a272  jz      short loc_14008A28C
0x14008a274  mov     rcx, r12
0x14008a277  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a27c  mov     rcx, r12
0x14008a27f  mov     qword ptr [r12], 0
0x14008a287  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a28c  lea     r12, [rdi+130h]
0x14008a293  cmp     qword ptr [r12], 0
0x14008a298  jz      short loc_14008A2B2
0x14008a29a  mov     rcx, r12
0x14008a29d  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a2a2  mov     rcx, r12
0x14008a2a5  mov     qword ptr [r12], 0
0x14008a2ad  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a2b2  lea     r12, [rdi+88h]
0x14008a2b9  cmp     qword ptr [r12], 0
0x14008a2be  jz      short loc_14008A2D8
0x14008a2c0  mov     rcx, r12
0x14008a2c3  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a2c8  mov     rcx, r12
0x14008a2cb  mov     qword ptr [r12], 0
0x14008a2d3  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a2d8  lea     rax, [rdi+138h]
0x14008a2df  cmp     qword ptr [rax], 0
0x14008a2e3  jz      short loc_14008A303
0x14008a2e5  mov     rcx, rax
0x14008a2e8  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a2ed  lea     rax, [rdi+138h]
0x14008a2f4  mov     rcx, rax
0x14008a2f7  mov     qword ptr [rax], 0
0x14008a2fe  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a303  lea     rax, [rdi+1A0h]
0x14008a30a  cmp     qword ptr [rax], 0
0x14008a30e  jz      short loc_14008A32E
0x14008a310  mov     rcx, rax
0x14008a313  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a318  lea     rax, [rdi+1A0h]
0x14008a31f  mov     rcx, rax
0x14008a322  mov     qword ptr [rax], 0
0x14008a329  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a32e  lea     rax, [rdi+140h]
0x14008a335  cmp     qword ptr [rax], 0
0x14008a339  jz      short loc_14008A359
0x14008a33b  mov     rcx, rax
0x14008a33e  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a343  lea     rax, [rdi+140h]
0x14008a34a  mov     rcx, rax
0x14008a34d  mov     qword ptr [rax], 0
0x14008a354  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a359  lea     rax, [rdi+148h]
0x14008a360  cmp     qword ptr [rax], 0
0x14008a364  jz      short loc_14008A384
0x14008a366  mov     rcx, rax
0x14008a369  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a36e  lea     rax, [rdi+148h]
0x14008a375  mov     rcx, rax
0x14008a378  mov     qword ptr [rax], 0
0x14008a37f  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a384  lea     rax, [rdi+150h]
0x14008a38b  cmp     qword ptr [rax], 0
0x14008a38f  jz      short loc_14008A3AF
0x14008a391  mov     rcx, rax
0x14008a394  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008a399  lea     rax, [rdi+150h]
0x14008a3a0  mov     rcx, rax
0x14008a3a3  mov     qword ptr [rax], 0
0x14008a3aa  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008a3af  mov     rcx, [rdi+40h]; Block
0x14008a3b3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14008a3b8  mov     r8d, [rsp+78h+arg_10]
0x14008a3c0  lea     rcx, aRdvRdpEncoderF; "RDV::RDP::Encoder::FrameEncodingStart"
0x14008a3c7  xor     eax, eax
0x14008a3c9  mov     [rsp+78h+var_40], rbx
0x14008a3ce  mov     [rdi+40h], rax
0x14008a3d2  mov     edx, esi
0x14008a3d4  mov     [rdi+48h], rax
0x14008a3d8  call    RDPAPI_GetLongCounter
0x14008a3dd  mov     ebx, eax
0x14008a3df  test    eax, eax
0x14008a3e1  jns     short loc_14008A447
0x14008a3e3  mov     rax, cs:WPP_GLOBAL_Control
0x14008a3ea  lea     rcx, WPP_GLOBAL_Control
0x14008a3f1  cmp     rax, rcx
0x14008a3f4  jz      loc_14008AEB3
0x14008a3fa  test    byte ptr [rax+1Ch], 8
0x14008a3fe  jz      loc_14008AEB3
0x14008a404  cmp     byte ptr [rax+19h], 2
0x14008a408  jb      loc_14008AEB3
0x14008a40e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14008a413  mov     edx, 0Dh
0x14008a418  lea     rcx, aFailedToInitia_19; "Failed to initialize RDV::RDP::Encoder:"...
0x14008a41f  mov     dword ptr [rsp+78h+var_50], ebx
0x14008a423  lea     r8, WPP_6f5e31529dd9301685fed12fae0064c9_Traceguids
0x14008a42a  mov     [rsp+78h+var_58], rcx
0x14008a42f  mov     r9d, eax
0x14008a432  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a439  mov     rcx, [rcx+10h]
0x14008a43d  call    WPP_SF_DsD
0x14008a442  jmp     loc_14008AEB3
0x14008a447  mov     r8d, [rsp+78h+arg_10]
0x14008a44f  lea     rcx, aRdvRdpEncoderF_0; "RDV::RDP::Encoder::FrameEncodingEnd"
0x14008a456  mov     edx, esi
0x14008a458  mov     [rsp+78h+var_40], r14
0x14008a45d  call    RDPAPI_GetLongCounter
0x14008a462  mov     ebx, eax
0x14008a464  test    eax, eax
0x14008a466  jns     short loc_14008A4A9
0x14008a468  mov     rax, cs:WPP_GLOBAL_Control
0x14008a46f  lea     rcx, WPP_GLOBAL_Control
0x14008a476  cmp     rax, rcx
0x14008a479  jz      loc_14008AEB3
0x14008a47f  test    byte ptr [rax+1Ch], 8
0x14008a483  jz      loc_14008AEB3
0x14008a489  cmp     byte ptr [rax+19h], 2
0x14008a48d  jb      loc_14008AEB3
0x14008a493  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14008a498  mov     edx, 0Eh
0x14008a49d  lea     rcx, aFailedToInitia_21; "Failed to initialize RDV::RDP::Encoder:"...
  ... truncated ...
```
