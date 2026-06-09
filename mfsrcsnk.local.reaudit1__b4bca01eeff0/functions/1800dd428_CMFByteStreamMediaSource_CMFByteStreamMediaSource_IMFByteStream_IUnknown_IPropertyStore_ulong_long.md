# CMFByteStreamMediaSource::CMFByteStreamMediaSource(IMFByteStream *,IUnknown *,IPropertyStore *,ulong,long *)

- ea: `0x1800dd428`
- end: `0x1800ddeab`
- name: `??0CMFByteStreamMediaSource@@AEAA@PEAUIMFByteStream@@PEAUIUnknown@@PEAUIPropertyStore@@KPEAJ@Z`
- size: `2691`
- prototype: `CMFByteStreamMediaSource *__usercall@<rax>(CMFByteStreamMediaSource *__hidden this@<rcx>, struct IMFByteStream *@<rdx>, struct IUnknown *@<r8>, struct IPropertyStore *@<r9>, unsigned int, int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a8c70`

## callees

- `0x180005cf4`
- `0x18000c120`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x18004a8a8`
- `0x18004f030`
- `0x180053fb8`
- `0x18006dec0`
- `0x180079680`
- `0x1800dd428`
- `0x1800e1e84`
- `0x180110a94`
- `0x180111960`
- `0x180148e8c`
- `0x180148ea4`
- `0x180148ebc`
- `0x180148ed4`
- `0x18014b4dc`
- `0x18014f87c`
- `0x18014fc50`
- `0x18016df2c`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800dd5bd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800dd5bd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd781`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd849`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd92b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ddb88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dddd2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd781`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd849`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd92b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ddb88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dddd2`
- `MFPlat!MFGetConfigurationDWORD` at `0x1800ddcfd`
- `MFPlat!MFGetConfigurationDWORD` at `0x1800ddcfd`

## pseudocode

```c
CMFByteStreamMediaSource *__fastcall CMFByteStreamMediaSource::CMFByteStreamMediaSource(
        CMFByteStreamMediaSource *this,
        struct IMFByteStream *a2,
        struct IUnknown *a3,
        struct IPropertyStore *a4,
        unsigned int a5,
        int *a6)
{
  struct _RTL_CRITICAL_SECTION *v6; // r15
  __int64 *v11; // r15
  __int64 v12; // rdx
  int v13; // ebx
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rdx
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  const struct _tagpropertykey *v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rdx
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  _QWORD *v34; // rax
  __int64 v35; // rdx
  _QWORD *v36; // rsi
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rcx
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  unsigned int v44; // [rsp+20h] [rbp-40h]
  _BYTE v45[4]; // [rsp+30h] [rbp-30h] BYREF
  int v46; // [rsp+34h] [rbp-2Ch] BYREF
  __int64 v47; // [rsp+38h] [rbp-28h] BYREF
  __int64 v48; // [rsp+40h] [rbp-20h] BYREF
  __int64 v49; // [rsp+48h] [rbp-18h] BYREF
  unsigned int v50[4]; // [rsp+50h] [rbp-10h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 712);
  COpQueue::COpQueue(
    (CMFByteStreamMediaSource *)((char *)this + 88),
    (CMFByteStreamMediaSource *)((char *)this + 712),
    a6,
    (unsigned int)a4,
    v44);
  *((_DWORD *)this + 168) = a5;
  *((_DWORD *)this + 169) = 17;
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
  {
    HIBYTE(v50[0]) = a5;
    LOBYTE(v50[0]) = HIBYTE(a5);
    BYTE1(v50[0]) = BYTE2(a5);
    BYTE2(v50[0]) = BYTE1(a5);
    McTemplateU0s4pu_EventWriteTransfer(a5, (unsigned int)Object_Create, (unsigned int)v50, (_DWORD)this + 672, 17);
  }
  _InterlockedIncrement(&dword_1801B979C);
  *((_DWORD *)this + 146) = 1;
  *((_QWORD *)this + 72) = &CAudioBurstBufferSource::`vftable';
  CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>((char *)this + 592);
  *(_QWORD *)this = &CMFByteStreamMediaSource::`vftable'{for `IMFMediaSourceEx'};
  *((_QWORD *)this + 1) = &CMFByteStreamMediaSource::`vftable'{for `IMFGetService'};
  *((_QWORD *)this + 2) = &CMFByteStreamMediaSource::`vftable'{for `IMFRateSupport'};
  *((_QWORD *)this + 3) = &CMFByteStreamMediaSource::`vftable'{for `IMFRateControl'};
  *((_QWORD *)this + 4) = &CMFByteStreamMediaSource::`vftable'{for `IPropertyStore'};
  *((_QWORD *)this + 5) = &CMFByteStreamMediaSource::`vftable'{for `IMFObjectInformation'};
  *((_QWORD *)this + 6) = &CMFByteStreamMediaSource::`vftable'{for `IMFPMPClient'};
  *((_QWORD *)this + 7) = &CMFByteStreamMediaSource::`vftable'{for `IMFPMPClientApp'};
  *((_QWORD *)this + 8) = &CMFByteStreamMediaSource::`vftable'{for `IMFTrustedInput'};
  *((_QWORD *)this + 9) = &CMFByteStreamMediaSource::`vftable'{for `IMFSampleProtection'};
  *((_QWORD *)this + 10) = &CMFByteStreamMediaSource::`vftable'{for `IByteStreamMediaSource'};
  *((_QWORD *)this + 11) = &CMFByteStreamMediaSource::`vftable'{for `COpQueue'};
  *((_QWORD *)this + 72) = &CMFByteStreamMediaSource::`vftable'{for `CAudioBurstBufferSource'};
  *((_QWORD *)this + 74) = &CMFByteStreamMediaSource::`vftable'{for `CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>'};
  *((_QWORD *)this + 83) = &CMFByteStreamMediaSource::`vftable'{for `IMFTelemetryComponent'};
  CMFByteStreamMediaSource::OnByteStreamEventAsyncCallback::OnByteStreamEventAsyncCallback((CMFByteStreamMediaSource *)((char *)this + 680));
  CMFByteStreamMediaSource::OnByteStreamReadHeaderAsyncCallback::OnByteStreamReadHeaderAsyncCallback((CMFByteStreamMediaSource *)((char *)this + 688));
  CMFByteStreamMediaSource::OnByteStreamReadIndexAsyncCallback::OnByteStreamReadIndexAsyncCallback((CMFByteStreamMediaSource *)((char *)this + 696));
  CMFByteStreamMediaSource::OnByteStreamReadDataAsyncCallback::OnByteStreamReadDataAsyncCallback((CMFByteStreamMediaSource *)((char *)this + 704));
  InitializeCriticalSection(v6);
  *((_QWORD *)this + 94) = 0;
  *((_DWORD *)this + 190) = 0;
  CMFMediaEventGenerator::CMFMediaEventGenerator((CMFByteStreamMediaSource *)((char *)this + 768), a6);
  *((_QWORD *)this + 111) = 0;
  *((_QWORD *)this + 112) = a3;
  if ( a3 )
    ((void (__fastcall *)(struct IUnknown *))a3->lpVtbl->AddRef)(a3);
  *((_QWORD *)this + 113) = 0;
  v11 = (__int64 *)((char *)this + 944);
  *((_QWORD *)this + 114) = 0;
  *((_QWORD *)this + 115) = 0;
  *((_QWORD *)this + 116) = 0;
  *((_QWORD *)this + 117) = 0;
  *((_QWORD *)this + 118) = 0;
  *((_QWORD *)this + 119) = 0;
  *((_QWORD *)this + 120) = 0;
  *((_QWORD *)this + 121) = 0;
  *((_QWORD *)this + 122) = 0;
  *((_QWORD *)this + 123) = 0;
  *((_QWORD *)this + 124) = 0;
  *((_QWORD *)this + 125) = 0;
  *((_QWORD *)this + 126) = 0;
  *((_QWORD *)this + 127) = 0;
  *(_QWORD *)((char *)this + 1028) = 0;
  *((_DWORD *)this + 256) = 0;
  *((_QWORD *)this + 130) = -1;
  *((_QWORD *)this + 131) = 0;
  *((_QWORD *)this + 132) = 1065353216;
  *((_QWORD *)this + 133) = 0;
  *((_QWORD *)this + 134) = 0;
  *((_QWORD *)this + 135) = 4;
  *((_QWORD *)this + 136) = 0;
  *((_QWORD *)this + 137) = 0;
  *((_QWORD *)this + 138) = 0;
  *((_QWORD *)this + 139) = 0;
  CMFByteStreamSourceReader::CMFByteStreamSourceReader((CMFByteStreamMediaSource *)((char *)this + 1120), this, a2, a6);
  *((_QWORD *)this + 155) = 0;
  v49 = 0;
  *((_QWORD *)this + 156) = 0;
  *((_QWORD *)this + 157) = 0;
  *((_QWORD *)this + 158) = 0;
  *((_DWORD *)this + 318) = 0;
  *((_DWORD *)this + 319) = 1;
  *((_QWORD *)this + 160) = 1;
  *((_DWORD *)this + 322) = 0;
  *((_QWORD *)this + 162) = 30000000;
  *((_DWORD *)this + 326) = 0;
  *(_QWORD *)((char *)this + 1308) = 1;
  *((_DWORD *)this + 329) = 0;
  *((_QWORD *)this + 165) = 0;
  v48 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v45,
    "CMFByteStreamMediaSource::CMFByteStreamMediaSource",
    379);
  v13 = *a6;
  if ( *a6 < 0 )
  {
    v14 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v14 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v13 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFByteStreamMediaSource::CMFByteStreamMediaSource",
          379,
          v13);
    }
    if ( g_wppLevels )
    {
      v17 = 22;
LABEL_86:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, this, v13);
      goto LABEL_87;
    }
    goto LABEL_87;
  }
  if ( MFGetService(
         *((IUnknown **)this + 112),
         &MF_MEDIASOURCE_SERVICE,
         &IID_IMFSourceHeaderParserPlugin,
         (LPVOID *)this + 113) < 0 )
  {
    v19 = (wchar_t *)CallStackTracing::s_wpInstance;
    v13 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v21 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v21, "CMFByteStreamMediaSource::CMFByteStreamMediaSource", 388, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_87;
    v22 = 23;
    goto LABEL_27;
  }
  MFGetService(
    *((IUnknown **)this + 112),
    &MF_MEDIASOURCE_SERVICE,
    &IID_IMFSourceHeaderParserPlugin2,
    (LPVOID *)this + 114);
  if ( MFGetService(
         *((IUnknown **)this + 112),
         &MF_MEDIASOURCE_SERVICE,
         &IID_IMFSourceDataParserPlugin,
         (LPVOID *)this + 115) < 0 )
  {
    v24 = (wchar_t *)CallStackTracing::s_wpInstance;
    v13 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
      CallStackTracing::s_wpInstance = v25;
      if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
      {
        v24 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v24 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v24 + 8) )
    {
      v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
      if ( *((_DWORD *)v26 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v26, "CMFByteStreamMediaSource::CMFByteStreamMediaSource", 398, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_87;
    v22 = 24;
LABEL_27:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v22,
      &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
      this,
      -2147024809);
    goto LABEL_87;
  }
  MFGetService(
    *((IUnknown **)this + 112),
    &MF_MEDIASOURCE_SERVICE,
    &IID_IMFSourceIndexParserPlugin,
    (LPVOID *)this + 116);
  MFGetService(*((IUnknown **)this + 112), &MF_RATE_CONTROL_SERVICE, &IID_IMFRateSupport, (LPVOID *)this + 121);
  MFGetService(
    *((IUnknown **)this + 112),
    &MF_MEDIASOURCE_SERVICE,
    &IID_IMFSourceProtectedContentPlugin,
    (LPVOID *)this + 117);
  MFGetService(
    *((IUnknown **)this + 112),
    &MF_MEDIASOURCE_SERVICE,
    &IID_IMFSourceExtendedAttributesPlugin,
    (LPVOID *)this + 118);
  MFGetService(*((IUnknown **)this + 112), &MF_MEDIASOURCE_SERVICE, &IID_IMFSourcePropertyPlugin, (LPVOID *)this + 119);
  (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 112))(
    *((_QWORD *)this + 112),
    &IID_IMFSampleProtection,
    (char *)this + 976);
  (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 112))(
    *((_QWORD *)this + 112),
    &GUID_97ec2ea4_0e42_4937_97ac_9d6d328824e1,
    (char *)this + 1000);
  v13 = ((__int64 (__fastcall *)(struct IMFByteStream *, GUID *, char *))a2->lpVtbl->QueryInterface)(
          a2,
          &IID_IMFTrustedInput,
          (char *)this + 984);
  if ( v13 < 0 )
  {
    ComSmartPtr<CBaseStreamSink>::operator=((char *)this + 984);
    v13 = 0;
  }
  MFGetService(
    (IUnknown *)a2,
    &MF_BYTESTREAM_DOWNLOADRATE_SERVICE,
    &IID_IMFByteStreamDownloadRateControl,
    (LPVOID *)this + 124);
  ComSmartPtr<CMPEGFrame>::operator=((char *)this + 1248, a4);
  v50[0] = 0;
  if ( *((_QWORD *)this + 156)
    && *v11
    && (int)CPropertyStorePtr::GetInt32((CMFByteStreamMediaSource *)((char *)this + 1248), v27, v50) >= 0 )
  {
    v28 = *v11;
    v47 = 0;
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 24LL))(v28, &v47) >= 0 )
      (*(void (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v47 + 168LL))(
        v47,
        MF_MEDIASOURCE_PLUGIN_TEST_FLAGS,
        v50[0]);
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v47);
  }
  if ( a4
    && (v29 = *((_QWORD *)this + 119)) != 0
    && (v13 = (*(__int64 (__fastcall **)(__int64, struct IPropertyStore *))(*(_QWORD *)v29 + 24LL))(v29, a4), v13 < 0) )
  {
    v31 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
      CallStackTracing::s_wpInstance = v32;
      if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
      {
        v31 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v31 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v31 + 8) )
    {
      v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
      if ( *((_DWORD *)v33 + 499) != v13 )
        CallStackContext::TraceFailure(v33, "CMFByteStreamMediaSource::CMFByteStreamMediaSource", 450, v13);
    }
    if ( g_wppLevels )
    {
      v17 = 25;
      goto LABEL_86;
    }
  }
  else
  {
    v34 = operator new(0xD8u);
    v36 = v34;
    if ( v34 )
    {
      *v34 = &CMFMediaStreamArray::`vftable';
      v34[2] = 0;
      *((_WORD *)v34 + 16) = 0;
      *((_BYTE *)v34 + 34) = 0;
      memset_0(v34 + 5, 0, 0xA0u);
      v36[25] = 0;
      v36[1] = &CTPtrArray<CMP3Stream,20>::`vftable';
      *((_DWORD *)v36 + 5) |= 1u;
      *((_DWORD *)v36 + 52) = 0;
      v36[3] = 0;
      *((_QWORD *)this + 139) = v36;
      if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          27,
          &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
          this,
          (*((_DWORD *)this + 290) >> 12) & 1);
      if ( (*((_DWORD *)this + 290) & 0x1000) != 0
        || !((__int64 (__fastcall *)(struct IMFByteStream *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
              a2,
              &GUID_6d66d782_1d4f_4db7_8c63_cb8c77f1ef5e,
              &v49) )
      {
        *((_DWORD *)this + 321) = 1;
      }
      v46 = 0;
      MFGetConfigurationDWORD(0, L"Network\\DisableSampleBasedBuffering", &v46);
      if ( v46 )
        *((_DWORD *)this + 319) = 0;
      if ( ((__int64 (__fastcall *)(struct IMFByteStream *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
             a2,
             &IID_IMFAttributes,
             &v48) >= 0 )
      {
        v50[0] = 0;
        if ( (*(int (__fastcall **)(__int64, __int64 *, unsigned int *))(*(_QWORD *)v48 + 56LL))(
               v48,
               MF_BYTESTREAM_OPTICAL_MEDIA,
               v50) >= 0
          && v50[0] == 1 )
        {
          *((_DWORD *)this + 319) = 0;
        }
      }
      v39 = *((_QWORD *)this + 124);
      if ( v39 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 32LL))(v39, *((unsigned int *)this + 319));
      if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
        WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 17), v37, v38, this, (char *)this + 768, this);
    }
    else
    {
      v40 = (wchar_t *)CallStackTracing::s_wpInstance;
      v13 = -2147024882;
      *((_QWORD *)this + 139) = 0;
      if ( !v40 )
      {
        v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
        CallStackTracing::s_wpInstance = v41;
        if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
        {
          v40 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v40 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v40 + 8) )
      {
        v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
        if ( *((_DWORD *)v42 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v42, "CMFByteStreamMediaSource::CMFByteStreamMediaSource", 457, -2147024882);
      }
      if ( g_wppLevels )
      {
        v17 = 26;
        goto LABEL_86;
      }
    }
  }
LABEL_87:
  *a6 = v13;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v45);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v48);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v49);
  return this;
}

```

## disassembly

```asm
0x1800dd428  mov     [rsp-38h+arg_10], rbx
0x1800dd42d  push    rbp
0x1800dd42e  push    rsi
0x1800dd42f  push    rdi
0x1800dd430  push    r12
0x1800dd432  push    r13
0x1800dd434  push    r14
0x1800dd436  push    r15
0x1800dd438  mov     rbp, rsp
0x1800dd43b  sub     rsp, 60h
0x1800dd43f  mov     r13, [rbp+arg_28]
0x1800dd443  lea     r15, [rcx+2C8h]
0x1800dd44a  mov     rsi, r8
0x1800dd44d  mov     r14, rdx
0x1800dd450  mov     rdi, rcx
0x1800dd453  mov     r8, r13; int *
0x1800dd456  mov     rdx, r15; struct CMFCSLock *
0x1800dd459  add     rcx, 58h ; 'X'; this
0x1800dd45d  mov     r12, r9
0x1800dd460  call    ??0COpQueue@@QEAA@PEAVCMFCSLock@@PEAJKK@Z; COpQueue::COpQueue(CMFCSLock *,long *,ulong,ulong)
0x1800dd465  mov     ecx, [rbp+arg_20]
0x1800dd468  lea     r9, [rdi+2A0h]
0x1800dd46f  mov     [r9], ecx
0x1800dd472  mov     dword ptr [r9+4], 11h
0x1800dd47a  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x1800dd481  jz      short loc_1800DD4B3
0x1800dd483  mov     eax, ecx
0x1800dd485  mov     byte ptr [rbp+var_10+3], cl
0x1800dd488  shr     eax, 18h
0x1800dd48b  lea     r8, [rbp+var_10]
0x1800dd48f  mov     byte ptr [rbp+var_10], al
0x1800dd492  lea     rdx, Object_Create
0x1800dd499  mov     eax, ecx
0x1800dd49b  mov     byte ptr [rsp+60h+var_40], 11h
0x1800dd4a0  shr     eax, 10h
0x1800dd4a3  mov     byte ptr [rbp+var_10+1], al
0x1800dd4a6  mov     eax, ecx
0x1800dd4a8  shr     eax, 8
0x1800dd4ab  mov     byte ptr [rbp+var_10+2], al
0x1800dd4ae  call    McTemplateU0s4pu_EventWriteTransfer
0x1800dd4b3  lock inc cs:dword_1801B979C
0x1800dd4ba  lea     rax, ??_7CAudioBurstBufferSource@@6B@; const CAudioBurstBufferSource::`vftable'
0x1800dd4c1  mov     dword ptr [rdi+248h], 1
0x1800dd4cb  lea     rbx, [rdi+250h]
0x1800dd4d2  mov     [rdi+240h], rax
0x1800dd4d9  mov     rcx, rbx
0x1800dd4dc  call    ??0?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@QEAA@I@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>(uint)
0x1800dd4e1  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFMediaSourceEx@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFMediaSourceEx'}
0x1800dd4e8  mov     [rdi], rax
0x1800dd4eb  lea     rcx, [rdi+2A8h]; this
0x1800dd4f2  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFGetService@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFGetService'}
0x1800dd4f9  mov     [rdi+8], rax
0x1800dd4fd  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFRateSupport@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFRateSupport'}
0x1800dd504  mov     [rdi+10h], rax
0x1800dd508  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFRateControl@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFRateControl'}
0x1800dd50f  mov     [rdi+18h], rax
0x1800dd513  lea     rax, ??_7CMFByteStreamMediaSource@@6BIPropertyStore@@@; const CMFByteStreamMediaSource::`vftable'{for `IPropertyStore'}
0x1800dd51a  mov     [rdi+20h], rax
0x1800dd51e  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFObjectInformation@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFObjectInformation'}
0x1800dd525  mov     [rdi+28h], rax
0x1800dd529  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFPMPClient@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFPMPClient'}
0x1800dd530  mov     [rdi+30h], rax
0x1800dd534  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFPMPClientApp@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFPMPClientApp'}
0x1800dd53b  mov     [rdi+38h], rax
0x1800dd53f  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFTrustedInput@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFTrustedInput'}
0x1800dd546  mov     [rdi+40h], rax
0x1800dd54a  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFSampleProtection@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFSampleProtection'}
0x1800dd551  mov     [rdi+48h], rax
0x1800dd555  lea     rax, ??_7CMFByteStreamMediaSource@@6BIByteStreamMediaSource@@@; const CMFByteStreamMediaSource::`vftable'{for `IByteStreamMediaSource'}
0x1800dd55c  mov     [rdi+50h], rax
0x1800dd560  lea     rax, ??_7CMFByteStreamMediaSource@@6BCOpQueue@@@; const CMFByteStreamMediaSource::`vftable'{for `COpQueue'}
0x1800dd567  mov     [rdi+58h], rax
0x1800dd56b  lea     rax, ??_7CMFByteStreamMediaSource@@6BCAudioBurstBufferSource@@@; const CMFByteStreamMediaSource::`vftable'{for `CAudioBurstBufferSource'}
0x1800dd572  mov     [rdi+240h], rax
0x1800dd579  lea     rax, ??_7CMFByteStreamMediaSource@@6B?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@@; const CMFByteStreamMediaSource::`vftable'{for `CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>'}
0x1800dd580  mov     [rbx], rax
0x1800dd583  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFTelemetryComponent@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFTelemetryComponent'}
0x1800dd58a  mov     [rdi+298h], rax
0x1800dd591  call    ??0OnByteStreamEventAsyncCallback@CMFByteStreamMediaSource@@QEAA@XZ; CMFByteStreamMediaSource::OnByteStreamEventAsyncCallback::OnByteStreamEventAsyncCallback(void)
0x1800dd596  lea     rcx, [rdi+2B0h]; this
0x1800dd59d  call    ??0OnByteStreamReadHeaderAsyncCallback@CMFByteStreamMediaSource@@QEAA@XZ; CMFByteStreamMediaSource::OnByteStreamReadHeaderAsyncCallback::OnByteStreamReadHeaderAsyncCallback(void)
0x1800dd5a2  lea     rcx, [rdi+2B8h]; this
0x1800dd5a9  call    ??0OnByteStreamReadIndexAsyncCallback@CMFByteStreamMediaSource@@QEAA@XZ; CMFByteStreamMediaSource::OnByteStreamReadIndexAsyncCallback::OnByteStreamReadIndexAsyncCallback(void)
0x1800dd5ae  lea     rcx, [rdi+2C0h]; this
0x1800dd5b5  call    ??0OnByteStreamReadDataAsyncCallback@CMFByteStreamMediaSource@@QEAA@XZ; CMFByteStreamMediaSource::OnByteStreamReadDataAsyncCallback::OnByteStreamReadDataAsyncCallback(void)
0x1800dd5ba  mov     rcx, r15; lpCriticalSection
0x1800dd5bd  call    cs:__imp_InitializeCriticalSection
0x1800dd5c4  nop     dword ptr [rax+rax+00h]
0x1800dd5c9  xor     ebx, ebx
0x1800dd5cb  lea     rcx, [rdi+300h]; this
0x1800dd5d2  mov     [rdi+2F0h], rbx
0x1800dd5d9  mov     rdx, r13; int *
0x1800dd5dc  mov     [rdi+2F8h], ebx
0x1800dd5e2  call    ??0CMFMediaEventGenerator@@QEAA@PEAJ@Z; CMFMediaEventGenerator::CMFMediaEventGenerator(long *)
0x1800dd5e7  mov     [rdi+378h], rbx
0x1800dd5ee  mov     [rdi+380h], rsi
0x1800dd5f5  test    rsi, rsi
0x1800dd5f8  jz      short loc_1800DD609
0x1800dd5fa  mov     rax, [rsi]
0x1800dd5fd  mov     rcx, rsi
0x1800dd600  mov     rax, [rax+8]
0x1800dd604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd609  mov     [rdi+388h], rbx
0x1800dd610  lea     r15, [rdi+3B0h]
0x1800dd617  mov     [rdi+390h], rbx
0x1800dd61e  lea     rcx, [rdi+460h]; this
0x1800dd625  mov     [rdi+398h], rbx
0x1800dd62c  mov     r9, r13; int *
0x1800dd62f  mov     [rdi+3A0h], rbx
0x1800dd636  mov     r8, r14; struct IMFByteStream *
0x1800dd639  mov     [rdi+3A8h], rbx
0x1800dd640  mov     rdx, rdi; struct CMFByteStreamMediaSource *
0x1800dd643  mov     [r15], rbx
0x1800dd646  mov     [rdi+3B8h], rbx
0x1800dd64d  mov     [rdi+3C0h], rbx
0x1800dd654  mov     [rdi+3C8h], rbx
0x1800dd65b  mov     [rdi+3D0h], rbx
0x1800dd662  mov     [rdi+3D8h], rbx
0x1800dd669  mov     [rdi+3E0h], rbx
0x1800dd670  mov     [rdi+3E8h], rbx
0x1800dd677  mov     [rdi+3F0h], rbx
0x1800dd67e  mov     [rdi+3F8h], rbx
0x1800dd685  mov     [rdi+404h], rbx
0x1800dd68c  mov     [rdi+400h], ebx
0x1800dd692  mov     qword ptr [rdi+410h], 0FFFFFFFFFFFFFFFFh
0x1800dd69d  mov     [rdi+418h], rbx
0x1800dd6a4  mov     qword ptr [rdi+420h], 3F800000h
0x1800dd6af  mov     [rdi+428h], rbx
0x1800dd6b6  mov     [rdi+430h], rbx
0x1800dd6bd  mov     qword ptr [rdi+438h], 4
0x1800dd6c8  mov     [rdi+440h], rbx
0x1800dd6cf  mov     [rdi+448h], rbx
0x1800dd6d6  mov     [rdi+450h], rbx
0x1800dd6dd  mov     [rdi+458h], rbx
0x1800dd6e4  call    ??0CMFByteStreamSourceReader@@QEAA@PEAVCMFByteStreamMediaSource@@PEAUIMFByteStream@@PEAJ@Z; CMFByteStreamSourceReader::CMFByteStreamSourceReader(CMFByteStreamMediaSource *,IMFByteStream *,long *)
0x1800dd6e9  mov     eax, 1
0x1800dd6ee  mov     [rdi+4D8h], rbx
0x1800dd6f5  lea     rsi, [rdi+4E0h]
0x1800dd6fc  mov     [rbp+var_18], rbx
0x1800dd700  mov     [rsi], rbx
0x1800dd703  lea     rdx, aCmfbytestreamm_21; "CMFByteStreamMediaSource::CMFByteStream"...
0x1800dd70a  mov     [rdi+4E8h], rbx
0x1800dd711  lea     rcx, [rbp+var_30]; this
0x1800dd715  mov     [rdi+4F0h], rbx
0x1800dd71c  mov     r8d, 17Bh; int
0x1800dd722  mov     [rdi+4F8h], ebx
0x1800dd728  mov     [rdi+4FCh], eax
0x1800dd72e  mov     [rdi+500h], rax
0x1800dd735  mov     [rdi+508h], ebx
0x1800dd73b  mov     qword ptr [rdi+510h], 1C9C380h
0x1800dd746  mov     [rdi+518h], ebx
0x1800dd74c  mov     [rdi+51Ch], rax
0x1800dd753  mov     [rdi+524h], ebx
0x1800dd759  mov     [rdi+528h], rbx
0x1800dd760  mov     [rbp+var_20], rbx
0x1800dd764  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800dd769  mov     ebx, [r13+0]
0x1800dd76d  test    ebx, ebx
0x1800dd76f  jns     loc_1800DD80A
0x1800dd775  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dd77c  test    rcx, rcx
0x1800dd77f  jnz     short loc_1800DD7C8
0x1800dd781  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dd788  nop     dword ptr [rax+rax+00h]
0x1800dd78d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dd794  mov     rcx, rax
0x1800dd797  test    rax, rax
0x1800dd79a  jz      short loc_1800DD7BA
0x1800dd79c  mov     rax, [rax]
0x1800dd79f  mov     edx, 7F0h
0x1800dd7a4  mov     rax, [rax+8]
0x1800dd7a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd7ad  test    eax, eax
0x1800dd7af  jz      short loc_1800DD7BA
0x1800dd7b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dd7b8  jmp     short loc_1800DD7C8
0x1800dd7ba  lea     rcx, qword_1801B97E0; this
0x1800dd7c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dd7c8  cmp     byte ptr [rcx+8], 0
0x1800dd7cc  jz      short loc_1800DD7F3
0x1800dd7ce  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dd7d3  cmp     [rax+7CCh], ebx
0x1800dd7d9  jz      short loc_1800DD7F3
0x1800dd7db  mov     r9d, ebx; int
0x1800dd7de  lea     rdx, aCmfbytestreamm_21; "CMFByteStreamMediaSource::CMFByteStream"...
0x1800dd7e5  mov     r8d, 17Bh; int
0x1800dd7eb  mov     rcx, rax; this
0x1800dd7ee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800dd7f3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800dd7fa  jb      loc_1800DDE70
0x1800dd800  mov     edx, 16h
0x1800dd805  jmp     loc_1800DDE52
0x1800dd80a  mov     rcx, [rdi+380h]; punkObject
0x1800dd811  lea     rbx, MF_MEDIASOURCE_SERVICE
0x1800dd818  mov     rdx, rbx; guidService
0x1800dd81b  lea     r9, [rdi+388h]; ppvObject
0x1800dd822  lea     r8, IID_IMFSourceHeaderParserPlugin; riid
0x1800dd829  call    MFGetService
0x1800dd82e  test    eax, eax
0x1800dd830  jns     loc_1800DD8D6
0x1800dd836  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dd83d  mov     esi, 80070057h
0x1800dd842  mov     ebx, esi
0x1800dd844  test    rcx, rcx
0x1800dd847  jnz     short loc_1800DD890
0x1800dd849  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dd850  nop     dword ptr [rax+rax+00h]
0x1800dd855  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dd85c  mov     rcx, rax
0x1800dd85f  test    rax, rax
0x1800dd862  jz      short loc_1800DD882
0x1800dd864  mov     rax, [rax]
0x1800dd867  mov     edx, 7F0h
0x1800dd86c  mov     rax, [rax+8]
0x1800dd870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd875  test    eax, eax
0x1800dd877  jz      short loc_1800DD882
0x1800dd879  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dd880  jmp     short loc_1800DD890
0x1800dd882  lea     rcx, qword_1801B97E0; this
0x1800dd889  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dd890  cmp     byte ptr [rcx+8], 0
0x1800dd894  jz      short loc_1800DD8BB
0x1800dd896  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dd89b  cmp     [rax+7CCh], esi
0x1800dd8a1  jz      short loc_1800DD8BB
0x1800dd8a3  mov     r9d, esi; int
0x1800dd8a6  lea     rdx, aCmfbytestreamm_21; "CMFByteStreamMediaSource::CMFByteStream"...
0x1800dd8ad  mov     r8d, 184h; int
0x1800dd8b3  mov     rcx, rax; this
0x1800dd8b6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800dd8bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800dd8c2  jb      loc_1800DDE70
0x1800dd8c8  mov     edx, 17h
0x1800dd8cd  mov     dword ptr [rsp+60h+var_40], esi
0x1800dd8d1  jmp     loc_1800DDE56
0x1800dd8d6  mov     rcx, [rdi+380h]; punkObject
0x1800dd8dd  lea     r9, [rdi+390h]; ppvObject
0x1800dd8e4  lea     r8, IID_IMFSourceHeaderParserPlugin2; riid
0x1800dd8eb  mov     rdx, rbx; guidService
0x1800dd8ee  call    MFGetService
0x1800dd8f3  mov     rcx, [rdi+380h]; punkObject
0x1800dd8fa  lea     r9, [rdi+398h]; ppvObject
0x1800dd901  lea     r8, IID_IMFSourceDataParserPlugin; riid
0x1800dd908  mov     rdx, rbx; guidService
0x1800dd90b  call    MFGetService
0x1800dd910  test    eax, eax
0x1800dd912  jns     loc_1800DD9B4
0x1800dd918  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dd91f  mov     esi, 80070057h
0x1800dd924  mov     ebx, esi
0x1800dd926  test    rcx, rcx
0x1800dd929  jnz     short loc_1800DD972
0x1800dd92b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dd932  nop     dword ptr [rax+rax+00h]
0x1800dd937  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dd93e  mov     rcx, rax
0x1800dd941  test    rax, rax
0x1800dd944  jz      short loc_1800DD964
0x1800dd946  mov     rax, [rax]
0x1800dd949  mov     edx, 7F0h
0x1800dd94e  mov     rax, [rax+8]
0x1800dd952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd957  test    eax, eax
0x1800dd959  jz      short loc_1800DD964
0x1800dd95b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dd962  jmp     short loc_1800DD972
0x1800dd964  lea     rcx, qword_1801B97E0; this
0x1800dd96b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dd972  cmp     byte ptr [rcx+8], 0
0x1800dd976  jz      short loc_1800DD99D
0x1800dd978  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dd97d  cmp     [rax+7CCh], esi
0x1800dd983  jz      short loc_1800DD99D
0x1800dd985  mov     r9d, esi; int
0x1800dd988  lea     rdx, aCmfbytestreamm_21; "CMFByteStreamMediaSource::CMFByteStream"...
0x1800dd98f  mov     r8d, 18Eh; int
0x1800dd995  mov     rcx, rax; this
0x1800dd998  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800dd99d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800dd9a4  jb      loc_1800DDE70
0x1800dd9aa  mov     edx, 18h
0x1800dd9af  jmp     loc_1800DD8CD
0x1800dd9b4  mov     rcx, [rdi+380h]; punkObject
0x1800dd9bb  lea     r9, [rdi+3A0h]; ppvObject
0x1800dd9c2  lea     r8, IID_IMFSourceIndexParserPlugin; riid
0x1800dd9c9  mov     rdx, rbx; guidService
0x1800dd9cc  call    MFGetService
0x1800dd9d1  mov     rcx, [rdi+380h]; punkObject
0x1800dd9d8  lea     r9, [rdi+3C8h]; ppvObject
0x1800dd9df  lea     r8, IID_IMFRateSupport; riid
0x1800dd9e6  lea     rdx, MF_RATE_CONTROL_SERVICE; guidService
0x1800dd9ed  call    MFGetService
0x1800dd9f2  mov     rcx, [rdi+380h]; punkObject
0x1800dd9f9  lea     r9, [rdi+3A8h]; ppvObject
0x1800dda00  lea     r8, IID_IMFSourceProtectedContentPlugin; riid
0x1800dda07  mov     rdx, rbx; guidService
0x1800dda0a  call    MFGetService
0x1800dda0f  mov     rcx, [rdi+380h]; punkObject
0x1800dda16  lea     r8, IID_IMFSourceExtendedAttributesPlugin; riid
  ... truncated ...
```
