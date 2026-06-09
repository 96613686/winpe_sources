# PipeETWEvents::Enable(ulong,ulong)

- ea: `0x14008c0c0`
- end: `0x14008d04a`
- name: `?Enable@PipeETWEvents@@UEAAJKK@Z`
- size: `3978`
- prototype: `__int64 __fastcall(PipeETWEvents *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14008d050`

## callees

- `0x140003b08`
- `0x14000b7d8`
- `0x14000d078`
- `0x14000dcac`
- `0x14003e0b4`
- `0x14005b6d8`
- `0x14005bc74`
- `0x14008be64`
- `0x14008c0c0`
- `0x14009023c`
- `0x140090414`

## string_xrefs

- `0x14008c623`: `RDV::RDP::Encoder::ProtocolBytes`
- `0x14008c66a`: `Failed to initialize RDV::RDP::Encoder::ProtocolBytes perf counter`
- `0x14008c9c5`: `RDV::RDP::GraphicsPipelineMicroStats::GfxInterFrameCacheHitRects`
- `0x14008ca11`: `RDPAPI_GetGenericCounter GfxInterFrameCacheHitRects failed`
- `0x14008ca26`: `RDV::RDP::GraphicsPipelineMicroStats::GfxInterFrameCacheOutARects`
- `0x14008ca72`: `RDPAPI_GetGenericCounter GfxInterFrameCacheOutARects failed`
- `0x14008c903`: `RDV::RDP::GraphicsPipelineMicroStats::GfxMDOutMoves`
- `0x14008c94f`: `RDPAPI_GetGenericCounter GfxMDOutMoves failed`
- `0x14008c964`: `RDV::RDP::GraphicsPipelineMicroStats::GfxInterFrameCacheInARects`
- `0x14008c9b0`: `RDPAPI_GetGenericCounter GfxInterFrameCacheInARects failed`
- `0x14008cb49`: `RDV::RDP::GraphicsPipelineMicroStats::GfxCacheInsertImports`
- `0x14008cb95`: `RDPAPI_GetGenericCounter GfxCacheInsertImports failed`
- `0x14008cbaa`: `RDV::RDP::GraphicsPipelineMicroStats::GfxCacheEvictRects`
- `0x14008cbf6`: `RDPAPI_GetGenericCounter GfxCacheEvictRects failed`
- `0x14008ca87`: `RDV::RDP::GraphicsPipelineMicroStats::GfxIntraFrameCacheHitRects`
- `0x14008cad3`: `RDPAPI_GetGenericCounter GfxIntraFrameCacheHitRects failed`
- `0x14008cae8`: `RDV::RDP::GraphicsPipelineMicroStats::GfxCacheInsertRects`
- `0x14008cb34`: `RDPAPI_GetGenericCounter GfxCacheInsertRects failed`

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
  char *v69; // [rsp+28h] [rbp-50h]
  char *v70; // [rsp+80h] [rbp+8h] BYREF
  int v71; // [rsp+90h] [rbp+18h]

  v71 = a3;
  v70 = (char *)this + 88;
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
  v5 = v71;
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
      LODWORD(v69) = LongCounter;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        (unsigned int)WPP_6f5e31529dd9301685fed12fae0064c9_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v11,
        v69);
      goto LABEL_201;
    }
    goto LABEL_201;
  }
  LongCounter = RDPAPI_GetLongCounter((unsigned int)L"RDV::RDP::Encoder::FrameEncodingEnd", a2, v71, v8);
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
    v69 = (char *)this + 136;
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
    v69 = (char *)this + 160;
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
    v69 = (char *)this + 168;
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
    v69 = (char *)this + 176;
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
    v69 = (char *)this + 184;
    LongCounter = RDPAPI_GetGenericCounter(
                    (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxDROutARects",
                    a2,
                    v21,
                    v22);
    if ( LongCounter >= 0 )
    {
      v69 = (char *)this + 192;
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
      v69 = (char *)this + 200;
      LongCounter = RDPAPI_GetGenericCounter(
                      (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxMDOutARects",
                      a2,
                      v25,
                      v26);
      if ( LongCounter >= 0 )
      {
        v69 = (char *)this + 208;
        LongCounter = RDPAPI_GetGenericCounter(
                        (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxMDOutMoves",
                        a2,
                        v27,
                        v28);
        if ( LongCounter >= 0 )
        {
          v69 = (char *)this + 216;
          LongCounter = RDPAPI_GetGenericCounter(
                          (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxInterFrameCacheInARects",
                          a2,
                          v29,
                          v30);
          if ( LongCounter >= 0 )
          {
            v69 = (char *)this + 224;
            LongCounter = RDPAPI_GetGenericCounter(
                            (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxInterFrameCacheHitRects",
                            a2,
                            v31,
                            v32);
            if ( LongCounter >= 0 )
            {
              v69 = (char *)this + 232;
              LongCounter = RDPAPI_GetGenericCounter(
                              (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxInterFrameCacheOutARects",
                              a2,
                              v33,
                              v34);
              if ( LongCounter >= 0 )
              {
                v69 = (char *)this + 240;
                LongCounter = RDPAPI_GetGenericCounter(
                                (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxIntraFrameCacheHitRects",
                                a2,
                                v35,
                                v36);
                if ( LongCounter >= 0 )
                {
                  v69 = (char *)this + 248;
                  LongCounter = RDPAPI_GetGenericCounter(
                                  (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxCacheInsertRects",
                                  a2,
                                  v37,
                                  v38);
                  if ( LongCounter >= 0 )
                  {
                    v69 = (char *)this + 256;
                    LongCounter = RDPAPI_GetGenericCounter(
                                    (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxCacheInsertImports",
                                    a2,
                                    v39,
                                    v40);
                    if ( LongCounter >= 0 )
                    {
                      v69 = (char *)this + 264;
                      LongCounter = RDPAPI_GetGenericCounter(
                                      (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxCacheEvictRects",
                                      a2,
                                      v41,
                                      v42);
                      if ( LongCounter >= 0 )
                      {
                        v69 = (char *)this + 272;
                        LongCounter = RDPAPI_GetGenericCounter(
                                        (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxClassifierInARects",
                                        a2,
                                        v43,
                                        v44);
                        if ( LongCounter >= 0 )
                        {
                          v69 = (char *)this + 280;
                          LongCounter = RDPAPI_GetGenericCounter(
                                          (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxClassifierOutTextRects",
                                          a2,
                                          v45,
                                          v46);
                          if ( LongCounter >= 0 )
                          {
                            v69 = (char *)this + 288;
                            LongCounter = RDPAPI_GetGenericCounter(
                                            (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxClassifierOutImageRects",
                                            a2,
                                            v47,
                                            v48);
                            if ( LongCounter >= 0 )
                            {
                              v69 = (char *)this + 296;
                              LongCounter = RDPAPI_GetGenericCounter(
                                              (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxClassifierOutSolidRects",
                                              a2,
                                              v49,
                                              v50);
                              if ( LongCounter >= 0 )
                              {
                                v69 = (char *)this + 304;
                                LongCounter = RDPAPI_GetGenericCounter(
                                                (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxClearCodec",
                                                a2,
                                                v51,
                                                v52);
                                if ( LongCounter >= 0 )
                                {
                                  v69 = (char *)this + 312;
                                  LongCounter = RDPAPI_GetGenericCounter(
                                                  (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxCodecStats",
                                                  a2,
                                                  v53,
                                                  v54);
                                  if ( LongCounter >= 0 )
                                  {
                                    v69 = (char *)this + 320;
                                    LongCounter = RDPAPI_GetGenericCounter(
                                                    (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxDeltaReducedRects",
                                                    a2,
                                                    v55,
                                                    v56);
                                    if ( LongCounter >= 0 )
                                    {
                                      v69 = (char *)this + 328;
                                      LongCounter = RDPAPI_GetGenericCounter(
                                                      (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxDirtyRects",
                                                      a2,
                                                      v57,
                                                      v58);
                                      if ( LongCounter >= 0 )
                                      {
                                        v69 = (char *)this + 336;
                                        LongCounter = RDPAPI_GetGenericCounter(
                                                        (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxPrimitiveRects",
                                                        a2,
                                                        v59,
                                                        v60);
                                        if ( LongCounter >= 0 )
                                        {
                                          v69 = (char *)this + 416;
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
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v70);
  return (unsigned int)LongCounter;
}

```

## disassembly

```asm
0x14008c0c0  mov     rax, rsp
0x14008c0c3  mov     [rax+10h], rbx
0x14008c0c7  mov     [rax+18h], r8d
0x14008c0cb  push    rbp
0x14008c0cc  push    rsi
0x14008c0cd  push    rdi
0x14008c0ce  push    r12
0x14008c0d0  push    r13
0x14008c0d2  push    r14
0x14008c0d4  push    r15
0x14008c0d6  sub     rsp, 40h
0x14008c0da  mov     rdi, rcx
0x14008c0dd  mov     esi, edx
0x14008c0df  add     rcx, 58h ; 'X'; this
0x14008c0e3  mov     [rax+8], rcx
0x14008c0e7  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x14008c0ec  lea     rbx, [rdi+70h]
0x14008c0f0  xor     r12d, r12d
0x14008c0f3  cmp     [rbx], r12
0x14008c0f6  jz      short loc_14008C10B
0x14008c0f8  mov     rcx, rbx
0x14008c0fb  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c100  mov     rcx, rbx
0x14008c103  mov     [rbx], r12
0x14008c106  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c10b  lea     r14, [rdi+78h]
0x14008c10f  cmp     [r14], r12
0x14008c112  jz      short loc_14008C127
0x14008c114  mov     rcx, r14
0x14008c117  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c11c  mov     rcx, r14
0x14008c11f  mov     [r14], r12
0x14008c122  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c127  lea     r15, [rdi+80h]
0x14008c12e  cmp     [r15], r12
0x14008c131  jz      short loc_14008C146
0x14008c133  mov     rcx, r15
0x14008c136  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c13b  mov     rcx, r15
0x14008c13e  mov     [r15], r12
0x14008c141  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c146  lea     rbp, [rdi+0A0h]
0x14008c14d  mov     [rdi+90h], r12d
0x14008c154  mov     [rdi+94h], esi
0x14008c15a  mov     [rdi+98h], r12d
0x14008c161  cmp     [rbp+0], r12
0x14008c165  jz      short loc_14008C17B
0x14008c167  mov     rcx, rbp
0x14008c16a  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c16f  mov     rcx, rbp
0x14008c172  mov     [rbp+0], r12
0x14008c176  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c17b  lea     r13, [rdi+0A8h]
0x14008c182  cmp     [r13+0], r12
0x14008c186  jz      short loc_14008C19C
0x14008c188  mov     rcx, r13
0x14008c18b  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c190  mov     rcx, r13
0x14008c193  mov     [r13+0], r12
0x14008c197  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c19c  lea     r12, [rdi+0B0h]
0x14008c1a3  cmp     qword ptr [r12], 0
0x14008c1a8  jz      short loc_14008C1C2
0x14008c1aa  mov     rcx, r12
0x14008c1ad  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c1b2  mov     rcx, r12
0x14008c1b5  mov     qword ptr [r12], 0
0x14008c1bd  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c1c2  lea     r12, [rdi+0B8h]
0x14008c1c9  cmp     qword ptr [r12], 0
0x14008c1ce  jz      short loc_14008C1E8
0x14008c1d0  mov     rcx, r12
0x14008c1d3  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c1d8  mov     rcx, r12
0x14008c1db  mov     qword ptr [r12], 0
0x14008c1e3  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c1e8  lea     r12, [rdi+0C0h]
0x14008c1ef  cmp     qword ptr [r12], 0
0x14008c1f4  jz      short loc_14008C20E
0x14008c1f6  mov     rcx, r12
0x14008c1f9  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c1fe  mov     rcx, r12
0x14008c201  mov     qword ptr [r12], 0
0x14008c209  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c20e  lea     r12, [rdi+0C8h]
0x14008c215  cmp     qword ptr [r12], 0
0x14008c21a  jz      short loc_14008C234
0x14008c21c  mov     rcx, r12
0x14008c21f  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c224  mov     rcx, r12
0x14008c227  mov     qword ptr [r12], 0
0x14008c22f  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c234  lea     r12, [rdi+0D0h]
0x14008c23b  cmp     qword ptr [r12], 0
0x14008c240  jz      short loc_14008C25A
0x14008c242  mov     rcx, r12
0x14008c245  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c24a  mov     rcx, r12
0x14008c24d  mov     qword ptr [r12], 0
0x14008c255  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c25a  lea     r12, [rdi+0D8h]
0x14008c261  cmp     qword ptr [r12], 0
0x14008c266  jz      short loc_14008C280
0x14008c268  mov     rcx, r12
0x14008c26b  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c270  mov     rcx, r12
0x14008c273  mov     qword ptr [r12], 0
0x14008c27b  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c280  lea     r12, [rdi+0E0h]
0x14008c287  cmp     qword ptr [r12], 0
0x14008c28c  jz      short loc_14008C2A6
0x14008c28e  mov     rcx, r12
0x14008c291  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c296  mov     rcx, r12
0x14008c299  mov     qword ptr [r12], 0
0x14008c2a1  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c2a6  lea     r12, [rdi+0E8h]
0x14008c2ad  cmp     qword ptr [r12], 0
0x14008c2b2  jz      short loc_14008C2CC
0x14008c2b4  mov     rcx, r12
0x14008c2b7  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c2bc  mov     rcx, r12
0x14008c2bf  mov     qword ptr [r12], 0
0x14008c2c7  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c2cc  lea     r12, [rdi+0F0h]
0x14008c2d3  cmp     qword ptr [r12], 0
0x14008c2d8  jz      short loc_14008C2F2
0x14008c2da  mov     rcx, r12
0x14008c2dd  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c2e2  mov     rcx, r12
0x14008c2e5  mov     qword ptr [r12], 0
0x14008c2ed  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c2f2  lea     r12, [rdi+0F8h]
0x14008c2f9  cmp     qword ptr [r12], 0
0x14008c2fe  jz      short loc_14008C318
0x14008c300  mov     rcx, r12
0x14008c303  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c308  mov     rcx, r12
0x14008c30b  mov     qword ptr [r12], 0
0x14008c313  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c318  lea     r12, [rdi+100h]
0x14008c31f  cmp     qword ptr [r12], 0
0x14008c324  jz      short loc_14008C33E
0x14008c326  mov     rcx, r12
0x14008c329  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c32e  mov     rcx, r12
0x14008c331  mov     qword ptr [r12], 0
0x14008c339  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c33e  lea     r12, [rdi+108h]
0x14008c345  cmp     qword ptr [r12], 0
0x14008c34a  jz      short loc_14008C364
0x14008c34c  mov     rcx, r12
0x14008c34f  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c354  mov     rcx, r12
0x14008c357  mov     qword ptr [r12], 0
0x14008c35f  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c364  lea     r12, [rdi+110h]
0x14008c36b  cmp     qword ptr [r12], 0
0x14008c370  jz      short loc_14008C38A
0x14008c372  mov     rcx, r12
0x14008c375  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c37a  mov     rcx, r12
0x14008c37d  mov     qword ptr [r12], 0
0x14008c385  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c38a  lea     r12, [rdi+118h]
0x14008c391  cmp     qword ptr [r12], 0
0x14008c396  jz      short loc_14008C3B0
0x14008c398  mov     rcx, r12
0x14008c39b  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c3a0  mov     rcx, r12
0x14008c3a3  mov     qword ptr [r12], 0
0x14008c3ab  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c3b0  lea     r12, [rdi+120h]
0x14008c3b7  cmp     qword ptr [r12], 0
0x14008c3bc  jz      short loc_14008C3D6
0x14008c3be  mov     rcx, r12
0x14008c3c1  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c3c6  mov     rcx, r12
0x14008c3c9  mov     qword ptr [r12], 0
0x14008c3d1  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c3d6  lea     r12, [rdi+128h]
0x14008c3dd  cmp     qword ptr [r12], 0
0x14008c3e2  jz      short loc_14008C3FC
0x14008c3e4  mov     rcx, r12
0x14008c3e7  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c3ec  mov     rcx, r12
0x14008c3ef  mov     qword ptr [r12], 0
0x14008c3f7  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c3fc  lea     r12, [rdi+130h]
0x14008c403  cmp     qword ptr [r12], 0
0x14008c408  jz      short loc_14008C422
0x14008c40a  mov     rcx, r12
0x14008c40d  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c412  mov     rcx, r12
0x14008c415  mov     qword ptr [r12], 0
0x14008c41d  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c422  lea     r12, [rdi+88h]
0x14008c429  cmp     qword ptr [r12], 0
0x14008c42e  jz      short loc_14008C448
0x14008c430  mov     rcx, r12
0x14008c433  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c438  mov     rcx, r12
0x14008c43b  mov     qword ptr [r12], 0
0x14008c443  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c448  lea     rax, [rdi+138h]
0x14008c44f  cmp     qword ptr [rax], 0
0x14008c453  jz      short loc_14008C473
0x14008c455  mov     rcx, rax
0x14008c458  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c45d  lea     rax, [rdi+138h]
0x14008c464  mov     rcx, rax
0x14008c467  mov     qword ptr [rax], 0
0x14008c46e  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c473  lea     rax, [rdi+1A0h]
0x14008c47a  cmp     qword ptr [rax], 0
0x14008c47e  jz      short loc_14008C49E
0x14008c480  mov     rcx, rax
0x14008c483  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c488  lea     rax, [rdi+1A0h]
0x14008c48f  mov     rcx, rax
0x14008c492  mov     qword ptr [rax], 0
0x14008c499  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c49e  lea     rax, [rdi+140h]
0x14008c4a5  cmp     qword ptr [rax], 0
0x14008c4a9  jz      short loc_14008C4C9
0x14008c4ab  mov     rcx, rax
0x14008c4ae  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c4b3  lea     rax, [rdi+140h]
0x14008c4ba  mov     rcx, rax
0x14008c4bd  mov     qword ptr [rax], 0
0x14008c4c4  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c4c9  lea     rax, [rdi+148h]
0x14008c4d0  cmp     qword ptr [rax], 0
0x14008c4d4  jz      short loc_14008C4F4
0x14008c4d6  mov     rcx, rax
0x14008c4d9  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c4de  lea     rax, [rdi+148h]
0x14008c4e5  mov     rcx, rax
0x14008c4e8  mov     qword ptr [rax], 0
0x14008c4ef  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c4f4  lea     rax, [rdi+150h]
0x14008c4fb  cmp     qword ptr [rax], 0
0x14008c4ff  jz      short loc_14008C51F
0x14008c501  mov     rcx, rax
0x14008c504  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14008c509  lea     rax, [rdi+150h]
0x14008c510  mov     rcx, rax
0x14008c513  mov     qword ptr [rax], 0
0x14008c51a  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14008c51f  mov     rcx, [rdi+40h]; Block
0x14008c523  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14008c528  mov     r8d, [rsp+78h+arg_10]
0x14008c530  lea     rcx, aRdvRdpEncoderF; "RDV::RDP::Encoder::FrameEncodingStart"
0x14008c537  xor     eax, eax
0x14008c539  mov     [rsp+78h+var_40], rbx
0x14008c53e  mov     [rdi+40h], rax
0x14008c542  mov     edx, esi
0x14008c544  mov     [rdi+48h], rax
0x14008c548  call    RDPAPI_GetLongCounter
0x14008c54d  mov     ebx, eax
0x14008c54f  test    eax, eax
0x14008c551  jns     short loc_14008C5B7
0x14008c553  mov     rax, cs:WPP_GLOBAL_Control
0x14008c55a  lea     rcx, WPP_GLOBAL_Control
0x14008c561  cmp     rax, rcx
0x14008c564  jz      loc_14008D023
0x14008c56a  test    byte ptr [rax+1Ch], 8
0x14008c56e  jz      loc_14008D023
0x14008c574  cmp     byte ptr [rax+19h], 2
0x14008c578  jb      loc_14008D023
0x14008c57e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14008c583  mov     edx, 0Dh
0x14008c588  lea     rcx, aFailedToInitia_19; "Failed to initialize RDV::RDP::Encoder:"...
0x14008c58f  mov     dword ptr [rsp+78h+var_50], ebx
0x14008c593  lea     r8, WPP_6f5e31529dd9301685fed12fae0064c9_Traceguids
0x14008c59a  mov     [rsp+78h+var_58], rcx
0x14008c59f  mov     r9d, eax
0x14008c5a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c5a9  mov     rcx, [rcx+10h]
0x14008c5ad  call    WPP_SF_DsD
0x14008c5b2  jmp     loc_14008D023
0x14008c5b7  mov     r8d, [rsp+78h+arg_10]
0x14008c5bf  lea     rcx, aRdvRdpEncoderF_0; "RDV::RDP::Encoder::FrameEncodingEnd"
0x14008c5c6  mov     edx, esi
0x14008c5c8  mov     [rsp+78h+var_40], r14
0x14008c5cd  call    RDPAPI_GetLongCounter
0x14008c5d2  mov     ebx, eax
0x14008c5d4  test    eax, eax
0x14008c5d6  jns     short loc_14008C619
0x14008c5d8  mov     rax, cs:WPP_GLOBAL_Control
0x14008c5df  lea     rcx, WPP_GLOBAL_Control
0x14008c5e6  cmp     rax, rcx
0x14008c5e9  jz      loc_14008D023
0x14008c5ef  test    byte ptr [rax+1Ch], 8
0x14008c5f3  jz      loc_14008D023
0x14008c5f9  cmp     byte ptr [rax+19h], 2
0x14008c5fd  jb      loc_14008D023
0x14008c603  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14008c608  mov     edx, 0Eh
0x14008c60d  lea     rcx, aFailedToInitia_21; "Failed to initialize RDV::RDP::Encoder:"...
  ... truncated ...
```
