# PipeETWEvents::Enable(ulong,ulong)

- ea: `0x1800c7560`
- end: `0x1800c8641`
- name: `?Enable@PipeETWEvents@@UEAAJKK@Z`
- size: `4321`
- prototype: `__int64 __fastcall(PipeETWEvents *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800c8650`

## callees

- `0x180016ad0`
- `0x180019a80`
- `0x180019ab0`
- `0x18001e740`
- `0x180046a84`
- `0x18004bc24`
- `0x1800506ac`
- `0x1800711c8`
- `0x180078820`
- `0x1800c7560`
- `0x1800d8450`

## string_xrefs

- `0x1800c7aea`: `RDV::RDP::Encoder::ProtocolBytes`
- `0x1800c7b4f`: `Failed to initialize RDV::RDP::Encoder::ProtocolBytes perf counter`
- `0x1800c7e41`: `RDV::RDP::GraphicsPipelineMicroStats::GfxMDOutMoves`
- `0x1800c7e92`: `RDPAPI_GetGenericCounter GfxMDOutMoves failed`
- `0x1800c7ead`: `RDV::RDP::GraphicsPipelineMicroStats::GfxInterFrameCacheInARects`
- `0x1800c7efe`: `RDPAPI_GetGenericCounter GfxInterFrameCacheInARects failed`
- `0x1800c7f19`: `RDV::RDP::GraphicsPipelineMicroStats::GfxInterFrameCacheHitRects`
- `0x1800c7f6a`: `RDPAPI_GetGenericCounter GfxInterFrameCacheHitRects failed`
- `0x1800c7f85`: `RDV::RDP::GraphicsPipelineMicroStats::GfxInterFrameCacheOutARects`
- `0x1800c7fd6`: `RDPAPI_GetGenericCounter GfxInterFrameCacheOutARects failed`
- `0x1800c7ff1`: `RDV::RDP::GraphicsPipelineMicroStats::GfxIntraFrameCacheHitRects`
- `0x1800c8042`: `RDPAPI_GetGenericCounter GfxIntraFrameCacheHitRects failed`
- `0x1800c805d`: `RDV::RDP::GraphicsPipelineMicroStats::GfxCacheInsertRects`
- `0x1800c80ae`: `RDPAPI_GetGenericCounter GfxCacheInsertRects failed`
- `0x1800c80c9`: `RDV::RDP::GraphicsPipelineMicroStats::GfxCacheInsertImports`
- `0x1800c811a`: `RDPAPI_GetGenericCounter GfxCacheInsertImports failed`
- `0x1800c8135`: `RDV::RDP::GraphicsPipelineMicroStats::GfxCacheEvictRects`
- `0x1800c8186`: `RDPAPI_GetGenericCounter GfxCacheEvictRects failed`

## pseudocode

```c
__int64 __fastcall PipeETWEvents::Enable(PipeETWEvents *this, int a2, int a3)
{
  int v5; // r8d
  int LongCounter; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v8; // edx
  const char *v9; // rcx
  PipeETWEvents *v10; // rcx
  PipeETWEvents *v11; // rcx
  PipeETWEvents *v12; // rcx
  PipeETWEvents *v13; // rcx
  PipeETWEvents *v14; // rcx
  char *v16; // [rsp+80h] [rbp+8h] BYREF
  int v17; // [rsp+90h] [rbp+18h]

  v17 = a3;
  v16 = (char *)this + 88;
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
  v5 = v17;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  LongCounter = RDPAPI_GetLongCounter(
                  (unsigned int)L"RDV::RDP::Encoder::FrameEncodingStart",
                  a2,
                  v5,
                  -1,
                  1,
                  1,
                  0,
                  (__int64)this + 112);
  if ( LongCounter < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 13;
      v9 = "Failed to initialize RDV::RDP::Encoder::FrameEncodingStart counter";
LABEL_62:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        (unsigned int)WPP_6f5e31529dd9301685fed12fae0064c9_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v9,
        LongCounter);
      goto LABEL_201;
    }
    goto LABEL_201;
  }
  LongCounter = RDPAPI_GetLongCounter(
                  (unsigned int)L"RDV::RDP::Encoder::FrameEncodingEnd",
                  a2,
                  v17,
                  -1,
                  1,
                  1,
                  0,
                  (__int64)this + 120);
  if ( LongCounter >= 0 )
  {
    LongCounter = RDPAPI_GetLongCounter(
                    (unsigned int)L"RDV::RDP::Encoder::ProtocolBytes",
                    a2,
                    0,
                    -1,
                    1,
                    1,
                    0,
                    (__int64)this + 128);
    if ( LongCounter < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 15;
        v9 = "Failed to initialize RDV::RDP::Encoder::ProtocolBytes perf counter";
        goto LABEL_62;
      }
      goto LABEL_201;
    }
    LongCounter = RDPAPI_GetGenericCounter(
                    (unsigned int)L"RDV::RDP::GraphicsPipeline::ProgressiveEncodingStatus",
                    a2,
                    0,
                    -1,
                    4,
                    (__int64)this + 136);
    if ( LongCounter < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 16;
        v9 = "Failed to initialize RDV::RDP::GraphicsPipeline::ProgressiveEncodingStatus perf counter";
        goto LABEL_62;
      }
      goto LABEL_201;
    }
    LongCounter = RDPAPI_GetGenericCounter(
                    (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxUTInVideoARects",
                    a2,
                    0,
                    -1,
                    4,
                    (__int64)this + 160);
    if ( LongCounter < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 17;
        v9 = "RDPAPI_GetGenericCounter GfxUTInVideoARects failed";
        goto LABEL_62;
      }
      goto LABEL_201;
    }
    LongCounter = RDPAPI_GetGenericCounter(
                    (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxUTOutEncARects",
                    a2,
                    0,
                    -1,
                    4,
                    (__int64)this + 168);
    if ( LongCounter < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 18;
        v9 = "RDPAPI_GetGenericCounter GfxUTOutEncARects failed";
        goto LABEL_62;
      }
      goto LABEL_201;
    }
    LongCounter = RDPAPI_GetGenericCounter(
                    (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxDRInARects",
                    a2,
                    0,
                    -1,
                    4,
                    (__int64)this + 176);
    if ( LongCounter < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_201;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 19;
      goto LABEL_93;
    }
    LongCounter = RDPAPI_GetGenericCounter(
                    (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxDROutARects",
                    a2,
                    0,
                    -1,
                    4,
                    (__int64)this + 184);
    if ( LongCounter >= 0 )
    {
      LongCounter = RDPAPI_GetGenericCounter(
                      (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxMDInARects",
                      a2,
                      0,
                      -1,
                      4,
                      (__int64)this + 192);
      if ( LongCounter < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_201;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 21;
LABEL_93:
        v9 = "RDPAPI_GetGenericCounter GfxMDInARects failed";
        goto LABEL_62;
      }
      LongCounter = RDPAPI_GetGenericCounter(
                      (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxMDOutARects",
                      a2,
                      0,
                      -1,
                      4,
                      (__int64)this + 200);
      if ( LongCounter >= 0 )
      {
        LongCounter = RDPAPI_GetGenericCounter(
                        (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxMDOutMoves",
                        a2,
                        0,
                        -1,
                        4,
                        (__int64)this + 208);
        if ( LongCounter >= 0 )
        {
          LongCounter = RDPAPI_GetGenericCounter(
                          (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxInterFrameCacheInARects",
                          a2,
                          0,
                          -1,
                          4,
                          (__int64)this + 216);
          if ( LongCounter >= 0 )
          {
            LongCounter = RDPAPI_GetGenericCounter(
                            (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxInterFrameCacheHitRects",
                            a2,
                            0,
                            -1,
                            4,
                            (__int64)this + 224);
            if ( LongCounter >= 0 )
            {
              LongCounter = RDPAPI_GetGenericCounter(
                              (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxInterFrameCacheOutARects",
                              a2,
                              0,
                              -1,
                              4,
                              (__int64)this + 232);
              if ( LongCounter >= 0 )
              {
                LongCounter = RDPAPI_GetGenericCounter(
                                (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxIntraFrameCacheHitRects",
                                a2,
                                0,
                                -1,
                                4,
                                (__int64)this + 240);
                if ( LongCounter >= 0 )
                {
                  LongCounter = RDPAPI_GetGenericCounter(
                                  (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxCacheInsertRects",
                                  a2,
                                  0,
                                  -1,
                                  4,
                                  (__int64)this + 248);
                  if ( LongCounter >= 0 )
                  {
                    LongCounter = RDPAPI_GetGenericCounter(
                                    (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxCacheInsertImports",
                                    a2,
                                    0,
                                    -1,
                                    4,
                                    (__int64)this + 256);
                    if ( LongCounter >= 0 )
                    {
                      LongCounter = RDPAPI_GetGenericCounter(
                                      (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxCacheEvictRects",
                                      a2,
                                      0,
                                      -1,
                                      4,
                                      (__int64)this + 264);
                      if ( LongCounter >= 0 )
                      {
                        LongCounter = RDPAPI_GetGenericCounter(
                                        (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxClassifierInARects",
                                        a2,
                                        0,
                                        -1,
                                        4,
                                        (__int64)this + 272);
                        if ( LongCounter >= 0 )
                        {
                          LongCounter = RDPAPI_GetGenericCounter(
                                          (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxClassifierOutTextRects",
                                          a2,
                                          0,
                                          -1,
                                          4,
                                          (__int64)this + 280);
                          if ( LongCounter >= 0 )
                          {
                            LongCounter = RDPAPI_GetGenericCounter(
                                            (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxClassifierOutImageRects",
                                            a2,
                                            0,
                                            -1,
                                            4,
                                            (__int64)this + 288);
                            if ( LongCounter >= 0 )
                            {
                              LongCounter = RDPAPI_GetGenericCounter(
                                              (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxClassifierOutSolidRects",
                                              a2,
                                              0,
                                              -1,
                                              4,
                                              (__int64)this + 296);
                              if ( LongCounter >= 0 )
                              {
                                LongCounter = RDPAPI_GetGenericCounter(
                                                (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxClearCodec",
                                                a2,
                                                0,
                                                -1,
                                                4,
                                                (__int64)this + 304);
                                if ( LongCounter >= 0 )
                                {
                                  LongCounter = RDPAPI_GetGenericCounter(
                                                  (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxCodecStats",
                                                  a2,
                                                  0,
                                                  -1,
                                                  4,
                                                  (__int64)this + 312);
                                  if ( LongCounter >= 0 )
                                  {
                                    LongCounter = RDPAPI_GetGenericCounter(
                                                    (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxDeltaReducedRects",
                                                    a2,
                                                    0,
                                                    -1,
                                                    4,
                                                    (__int64)this + 320);
                                    if ( LongCounter >= 0 )
                                    {
                                      LongCounter = RDPAPI_GetGenericCounter(
                                                      (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxDirtyRects",
                                                      a2,
                                                      0,
                                                      -1,
                                                      4,
                                                      (__int64)this + 328);
                                      if ( LongCounter >= 0 )
                                      {
                                        LongCounter = RDPAPI_GetGenericCounter(
                                                        (unsigned int)L"RDV::RDP::GraphicsPipelineMicroStats::GfxPrimitiveRects",
                                                        a2,
                                                        0,
                                                        -1,
                                                        4,
                                                        (__int64)this + 336);
                                        if ( LongCounter >= 0 )
                                        {
                                          LongCounter = RDPAPI_GetGenericCounter(
                                                          (unsigned int)L"RDV::CLOUDDV::QOE::QOEServerFrameDetails",
                                                          a2,
                                                          0,
                                                          -1,
                                                          4,
                                                          (__int64)this + 416);
                                          if ( LongCounter >= 0 )
                                          {
                                            *((_DWORD *)this + 106) = 0;
                                            PipeETWEvents::Allocate_Accumulator(v10, (void **)this + 44, 0x2000u);
                                            PipeETWEvents::Allocate_Accumulator(v11, (void **)this + 45, 0x2000u);
                                            PipeETWEvents::Allocate_Accumulator(v12, (void **)this + 46, 0x2000u);
                                            PipeETWEvents::Allocate_Accumulator(v13, (void **)this + 47, 0x6000u);
                                            PipeETWEvents::Allocate_Accumulator(v14, (void **)this + 48, 0x6000u);
                                            goto LABEL_201;
                                          }
                                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                          {
                                            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                                            v8 = 40;
                                            v9 = "RDPAPI_GetGenericCounter QOEServerFrameDetails failed";
                                            goto LABEL_62;
                                          }
                                        }
                                        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                        {
                                          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                                          v8 = 39;
                                          v9 = "RDPAPI_GetGenericCounter m_spPerfCounterGfxPrimitiveRects failed";
                                          goto LABEL_62;
                                        }
                                      }
                                      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                      {
                                        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                                        v8 = 38;
                                        v9 = "RDPAPI_GetGenericCounter m_spPerfCounterGfxDirtyRects failed";
                                        goto LABEL_62;
                                      }
                                    }
                                    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                    {
                                      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                                      v8 = 37;
                                      v9 = "RDPAPI_GetGenericCounter GfxDeltaReducedRects failed";
                                      goto LABEL_62;
                                    }
                                  }
                                  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                  {
                                    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                                    v8 = 36;
                                    v9 = "RDPAPI_GetGenericCounter GfxCodecStats failed";
                                    goto LABEL_62;
                                  }
                                }
                                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                {
                                  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                                  v8 = 35;
                                  v9 = "RDPAPI_GetGenericCounter GfxClearCodec failed";
                                  goto LABEL_62;
                                }
                              }
                              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                              {
                                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                                v8 = 34;
                                v9 = "RDPAPI_GetGenericCounter GfxClassifierOutSolidRects failed";
                                goto LABEL_62;
                              }
                            }
                            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                            {
                              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                              v8 = 33;
                              v9 = "RDPAPI_GetGenericCounter GfxClassifierOutImageRects failed";
                              goto LABEL_62;
                            }
                          }
                          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                            v8 = 32;
                            v9 = "RDPAPI_GetGenericCounter GfxClassifierOutTextRects failed";
                            goto LABEL_62;
                          }
                        }
                        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                        {
                          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                          v8 = 31;
                          v9 = "RDPAPI_GetGenericCounter GfxClassifierInARects failed";
                          goto LABEL_62;
                        }
                      }
                      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                        v8 = 30;
                        v9 = "RDPAPI_GetGenericCounter GfxCacheEvictRects failed";
                        goto LABEL_62;
                      }
                    }
                    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                      v8 = 29;
                      v9 = "RDPAPI_GetGenericCounter GfxCacheInsertImports failed";
                      goto LABEL_62;
                    }
                  }
                  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                    v8 = 28;
                    v9 = "RDPAPI_GetGenericCounter GfxCacheInsertRects failed";
                    goto LABEL_62;
                  }
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                  v8 = 27;
                  v9 = "RDPAPI_GetGenericCounter GfxIntraFrameCacheHitRects failed";
                  goto LABEL_62;
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v8 = 26;
                v9 = "RDPAPI_GetGenericCounter GfxInterFrameCacheOutARects failed";
                goto LABEL_62;
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v8 = 25;
              v9 = "RDPAPI_GetGenericCounter GfxInterFrameCacheHitRects failed";
              goto LABEL_62;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v8 = 24;
            v9 = "RDPAPI_GetGenericCounter GfxInterFrameCacheInARects failed";
            goto LABEL_62;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v8 = 23;
          v9 = "RDPAPI_GetGenericCounter GfxMDOutMoves failed";
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
      v8 = 22;
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
      v8 = 20;
    }
    v9 = "RDPAPI_GetGenericCounter GfxMDOutARects failed";
    goto LABEL_62;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 14;
    v9 = "Failed to initialize RDV::RDP::Encoder::FrameEncodingEn counter";
    goto LABEL_62;
  }
LABEL_201:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v16);
  return (unsigned int)LongCounter;
}

```

## disassembly

```asm
0x1800c7560  mov     rax, rsp
0x1800c7563  mov     [rax+10h], rbx
0x1800c7567  mov     [rax+18h], r8d
0x1800c756b  push    rbp
0x1800c756c  push    rsi
0x1800c756d  push    rdi
0x1800c756e  push    r12
0x1800c7570  push    r13
0x1800c7572  push    r14
0x1800c7574  push    r15
0x1800c7576  sub     rsp, 40h
0x1800c757a  mov     rdi, rcx
0x1800c757d  mov     esi, edx
0x1800c757f  add     rcx, 58h ; 'X'; this
0x1800c7583  mov     [rax+8], rcx
0x1800c7587  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800c758c  lea     rbx, [rdi+70h]
0x1800c7590  xor     r12d, r12d
0x1800c7593  cmp     [rbx], r12
0x1800c7596  jz      short loc_1800C75AB
0x1800c7598  mov     rcx, rbx; void *
0x1800c759b  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c75a0  mov     rcx, rbx
0x1800c75a3  mov     [rbx], r12
0x1800c75a6  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c75ab  lea     r14, [rdi+78h]
0x1800c75af  cmp     [r14], r12
0x1800c75b2  jz      short loc_1800C75C7
0x1800c75b4  mov     rcx, r14; void *
0x1800c75b7  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c75bc  mov     rcx, r14
0x1800c75bf  mov     [r14], r12
0x1800c75c2  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c75c7  lea     r15, [rdi+80h]
0x1800c75ce  cmp     [r15], r12
0x1800c75d1  jz      short loc_1800C75E6
0x1800c75d3  mov     rcx, r15; void *
0x1800c75d6  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c75db  mov     rcx, r15
0x1800c75de  mov     [r15], r12
0x1800c75e1  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c75e6  lea     rbp, [rdi+0A0h]
0x1800c75ed  mov     [rdi+90h], r12d
0x1800c75f4  mov     [rdi+94h], esi
0x1800c75fa  mov     [rdi+98h], r12d
0x1800c7601  cmp     [rbp+0], r12
0x1800c7605  jz      short loc_1800C761B
0x1800c7607  mov     rcx, rbp; void *
0x1800c760a  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c760f  mov     rcx, rbp
0x1800c7612  mov     [rbp+0], r12
0x1800c7616  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c761b  lea     r13, [rdi+0A8h]
0x1800c7622  cmp     [r13+0], r12
0x1800c7626  jz      short loc_1800C763C
0x1800c7628  mov     rcx, r13; void *
0x1800c762b  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c7630  mov     rcx, r13
0x1800c7633  mov     [r13+0], r12
0x1800c7637  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c763c  lea     r12, [rdi+0B0h]
0x1800c7643  cmp     qword ptr [r12], 0
0x1800c7648  jz      short loc_1800C7662
0x1800c764a  mov     rcx, r12; void *
0x1800c764d  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c7652  mov     rcx, r12
0x1800c7655  mov     qword ptr [r12], 0
0x1800c765d  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c7662  lea     r12, [rdi+0B8h]
0x1800c7669  cmp     qword ptr [r12], 0
0x1800c766e  jz      short loc_1800C7688
0x1800c7670  mov     rcx, r12; void *
0x1800c7673  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c7678  mov     rcx, r12
0x1800c767b  mov     qword ptr [r12], 0
0x1800c7683  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c7688  lea     r12, [rdi+0C0h]
0x1800c768f  cmp     qword ptr [r12], 0
0x1800c7694  jz      short loc_1800C76AE
0x1800c7696  mov     rcx, r12; void *
0x1800c7699  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c769e  mov     rcx, r12
0x1800c76a1  mov     qword ptr [r12], 0
0x1800c76a9  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c76ae  lea     r12, [rdi+0C8h]
0x1800c76b5  cmp     qword ptr [r12], 0
0x1800c76ba  jz      short loc_1800C76D4
0x1800c76bc  mov     rcx, r12; void *
0x1800c76bf  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c76c4  mov     rcx, r12
0x1800c76c7  mov     qword ptr [r12], 0
0x1800c76cf  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c76d4  lea     r12, [rdi+0D0h]
0x1800c76db  cmp     qword ptr [r12], 0
0x1800c76e0  jz      short loc_1800C76FA
0x1800c76e2  mov     rcx, r12; void *
0x1800c76e5  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c76ea  mov     rcx, r12
0x1800c76ed  mov     qword ptr [r12], 0
0x1800c76f5  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c76fa  lea     r12, [rdi+0D8h]
0x1800c7701  cmp     qword ptr [r12], 0
0x1800c7706  jz      short loc_1800C7720
0x1800c7708  mov     rcx, r12; void *
0x1800c770b  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c7710  mov     rcx, r12
0x1800c7713  mov     qword ptr [r12], 0
0x1800c771b  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c7720  lea     r12, [rdi+0E0h]
0x1800c7727  cmp     qword ptr [r12], 0
0x1800c772c  jz      short loc_1800C7746
0x1800c772e  mov     rcx, r12; void *
0x1800c7731  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c7736  mov     rcx, r12
0x1800c7739  mov     qword ptr [r12], 0
0x1800c7741  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c7746  lea     r12, [rdi+0E8h]
0x1800c774d  cmp     qword ptr [r12], 0
0x1800c7752  jz      short loc_1800C776C
0x1800c7754  mov     rcx, r12; void *
0x1800c7757  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c775c  mov     rcx, r12
0x1800c775f  mov     qword ptr [r12], 0
0x1800c7767  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c776c  lea     r12, [rdi+0F0h]
0x1800c7773  cmp     qword ptr [r12], 0
0x1800c7778  jz      short loc_1800C7792
0x1800c777a  mov     rcx, r12; void *
0x1800c777d  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c7782  mov     rcx, r12
0x1800c7785  mov     qword ptr [r12], 0
0x1800c778d  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c7792  lea     r12, [rdi+0F8h]
0x1800c7799  cmp     qword ptr [r12], 0
0x1800c779e  jz      short loc_1800C77B8
0x1800c77a0  mov     rcx, r12; void *
0x1800c77a3  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c77a8  mov     rcx, r12
0x1800c77ab  mov     qword ptr [r12], 0
0x1800c77b3  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c77b8  lea     r12, [rdi+100h]
0x1800c77bf  cmp     qword ptr [r12], 0
0x1800c77c4  jz      short loc_1800C77DE
0x1800c77c6  mov     rcx, r12; void *
0x1800c77c9  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c77ce  mov     rcx, r12
0x1800c77d1  mov     qword ptr [r12], 0
0x1800c77d9  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c77de  lea     r12, [rdi+108h]
0x1800c77e5  cmp     qword ptr [r12], 0
0x1800c77ea  jz      short loc_1800C7804
0x1800c77ec  mov     rcx, r12; void *
0x1800c77ef  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c77f4  mov     rcx, r12
0x1800c77f7  mov     qword ptr [r12], 0
0x1800c77ff  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c7804  lea     r12, [rdi+110h]
0x1800c780b  cmp     qword ptr [r12], 0
0x1800c7810  jz      short loc_1800C782A
0x1800c7812  mov     rcx, r12; void *
0x1800c7815  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c781a  mov     rcx, r12
0x1800c781d  mov     qword ptr [r12], 0
0x1800c7825  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c782a  lea     r12, [rdi+118h]
0x1800c7831  cmp     qword ptr [r12], 0
0x1800c7836  jz      short loc_1800C7850
0x1800c7838  mov     rcx, r12; void *
0x1800c783b  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c7840  mov     rcx, r12
0x1800c7843  mov     qword ptr [r12], 0
0x1800c784b  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c7850  lea     r12, [rdi+120h]
0x1800c7857  cmp     qword ptr [r12], 0
0x1800c785c  jz      short loc_1800C7876
0x1800c785e  mov     rcx, r12; void *
0x1800c7861  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c7866  mov     rcx, r12
0x1800c7869  mov     qword ptr [r12], 0
0x1800c7871  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c7876  lea     r12, [rdi+128h]
0x1800c787d  cmp     qword ptr [r12], 0
0x1800c7882  jz      short loc_1800C789C
0x1800c7884  mov     rcx, r12; void *
0x1800c7887  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c788c  mov     rcx, r12
0x1800c788f  mov     qword ptr [r12], 0
0x1800c7897  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c789c  lea     r12, [rdi+130h]
0x1800c78a3  cmp     qword ptr [r12], 0
0x1800c78a8  jz      short loc_1800C78C2
0x1800c78aa  mov     rcx, r12; void *
0x1800c78ad  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c78b2  mov     rcx, r12
0x1800c78b5  mov     qword ptr [r12], 0
0x1800c78bd  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c78c2  lea     r12, [rdi+88h]
0x1800c78c9  cmp     qword ptr [r12], 0
0x1800c78ce  jz      short loc_1800C78E8
0x1800c78d0  mov     rcx, r12; void *
0x1800c78d3  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c78d8  mov     rcx, r12
0x1800c78db  mov     qword ptr [r12], 0
0x1800c78e3  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c78e8  lea     rax, [rdi+138h]
0x1800c78ef  cmp     qword ptr [rax], 0
0x1800c78f3  jz      short loc_1800C7913
0x1800c78f5  mov     rcx, rax; void *
0x1800c78f8  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c78fd  lea     rax, [rdi+138h]
0x1800c7904  mov     rcx, rax
0x1800c7907  mov     qword ptr [rax], 0
0x1800c790e  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c7913  lea     rax, [rdi+1A0h]
0x1800c791a  cmp     qword ptr [rax], 0
0x1800c791e  jz      short loc_1800C793E
0x1800c7920  mov     rcx, rax; void *
0x1800c7923  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c7928  lea     rax, [rdi+1A0h]
0x1800c792f  mov     rcx, rax
0x1800c7932  mov     qword ptr [rax], 0
0x1800c7939  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c793e  lea     rax, [rdi+140h]
0x1800c7945  cmp     qword ptr [rax], 0
0x1800c7949  jz      short loc_1800C7969
0x1800c794b  mov     rcx, rax; void *
0x1800c794e  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c7953  lea     rax, [rdi+140h]
0x1800c795a  mov     rcx, rax
0x1800c795d  mov     qword ptr [rax], 0
0x1800c7964  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c7969  lea     rax, [rdi+148h]
0x1800c7970  cmp     qword ptr [rax], 0
0x1800c7974  jz      short loc_1800C7994
0x1800c7976  mov     rcx, rax; void *
0x1800c7979  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c797e  lea     rax, [rdi+148h]
0x1800c7985  mov     rcx, rax
0x1800c7988  mov     qword ptr [rax], 0
0x1800c798f  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c7994  lea     rax, [rdi+150h]
0x1800c799b  cmp     qword ptr [rax], 0
0x1800c799f  jz      short loc_1800C79BF
0x1800c79a1  mov     rcx, rax; void *
0x1800c79a4  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800c79a9  lea     rax, [rdi+150h]
0x1800c79b0  mov     rcx, rax
0x1800c79b3  mov     qword ptr [rax], 0
0x1800c79ba  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800c79bf  mov     rcx, [rdi+40h]; Block
0x1800c79c3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c79c8  mov     r8d, [rsp+78h+arg_10]
0x1800c79d0  lea     rcx, aRdvRdpEncoderF_0; "RDV::RDP::Encoder::FrameEncodingStart"
0x1800c79d7  xor     eax, eax
0x1800c79d9  mov     [rsp+78h+var_40], rbx
0x1800c79de  mov     [rsp+78h+var_48], eax
0x1800c79e2  or      r9d, 0FFFFFFFFh
0x1800c79e6  mov     [rdi+40h], rax
0x1800c79ea  mov     edx, esi
0x1800c79ec  mov     [rdi+48h], rax
0x1800c79f0  mov     eax, 1
0x1800c79f5  mov     dword ptr [rsp+78h+var_50], eax
0x1800c79f9  mov     dword ptr [rsp+78h+var_58], eax
0x1800c79fd  call    RDPAPI_GetLongCounter
0x1800c7a02  mov     ebx, eax
0x1800c7a04  test    eax, eax
0x1800c7a06  jns     short loc_1800C7A6C
0x1800c7a08  mov     rax, cs:WPP_GLOBAL_Control
0x1800c7a0f  lea     rcx, WPP_GLOBAL_Control
0x1800c7a16  cmp     rax, rcx
0x1800c7a19  jz      loc_1800C861A
0x1800c7a1f  test    byte ptr [rax+1Ch], 8
0x1800c7a23  jz      loc_1800C861A
0x1800c7a29  cmp     byte ptr [rax+19h], 2
0x1800c7a2d  jb      loc_1800C861A
0x1800c7a33  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c7a38  mov     edx, 0Dh
0x1800c7a3d  lea     rcx, aFailedToInitia_37; "Failed to initialize RDV::RDP::Encoder:"...
0x1800c7a44  mov     dword ptr [rsp+78h+var_50], ebx
0x1800c7a48  lea     r8, WPP_6f5e31529dd9301685fed12fae0064c9_Traceguids
0x1800c7a4f  mov     [rsp+78h+var_58], rcx
0x1800c7a54  mov     r9d, eax
0x1800c7a57  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7a5e  mov     rcx, [rcx+10h]
0x1800c7a62  call    WPP_SF_DsD
0x1800c7a67  jmp     loc_1800C861A
0x1800c7a6c  mov     r8d, [rsp+78h+arg_10]
0x1800c7a74  lea     rcx, aRdvRdpEncoderF_1; "RDV::RDP::Encoder::FrameEncodingEnd"
0x1800c7a7b  mov     [rsp+78h+var_40], r14
0x1800c7a80  or      r9d, 0FFFFFFFFh
0x1800c7a84  xor     r14d, r14d
0x1800c7a87  mov     edx, esi
0x1800c7a89  mov     [rsp+78h+var_48], r14d
0x1800c7a8e  lea     eax, [r14+1]
0x1800c7a92  mov     dword ptr [rsp+78h+var_50], eax
0x1800c7a96  mov     dword ptr [rsp+78h+var_58], eax
0x1800c7a9a  call    RDPAPI_GetLongCounter
0x1800c7a9f  mov     ebx, eax
0x1800c7aa1  test    eax, eax
0x1800c7aa3  jns     short loc_1800C7AE5
  ... truncated ...
```
