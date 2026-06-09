# CMFByteStreamMediaSource::CMFByteStreamMediaSource(IMFByteStream *,IUnknown *,IPropertyStore *,ulong,long *)

- ea: `0x1800d7170`
- end: `0x1800d7bc8`
- name: `??0CMFByteStreamMediaSource@@AEAA@PEAUIMFByteStream@@PEAUIUnknown@@PEAUIPropertyStore@@KPEAJ@Z`
- size: `2648`
- prototype: `CMFByteStreamMediaSource *__usercall@<rax>(CMFByteStreamMediaSource *__hidden this@<rcx>, struct IMFByteStream *@<rdx>, struct IUnknown *@<r8>, struct IPropertyStore *@<r9>, unsigned int, int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a3d18`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x18003ccec`
- `0x180047a00`
- `0x18004c264`
- `0x18004f1d4`
- `0x18006c6b0`
- `0x180073b14`
- `0x1800d7170`
- `0x1800db9e8`
- `0x1801095a8`
- `0x18010a450`
- `0x180141120`
- `0x180141134`
- `0x180141148`
- `0x18014115c`
- `0x1801435ec`
- `0x180147738`
- `0x180147ae0`
- `0x180164f7c`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800d7305`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800d7305`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d74c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d7585`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d7661`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d78b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d7af6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d74c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d7585`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d7661`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d78b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d7af6`
- `MFPlat!MFGetConfigurationDWORD` at `0x1800d7a27`
- `MFPlat!MFGetConfigurationDWORD` at `0x1800d7a27`

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
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // ebx
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  const struct _tagpropertykey *v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  _QWORD *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  _QWORD *v46; // rsi
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // rcx
  wchar_t *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  unsigned int v54; // [rsp+20h] [rbp-40h]
  _BYTE v55[4]; // [rsp+30h] [rbp-30h] BYREF
  int v56; // [rsp+34h] [rbp-2Ch] BYREF
  __int64 v57; // [rsp+38h] [rbp-28h] BYREF
  __int64 v58; // [rsp+40h] [rbp-20h] BYREF
  __int64 v59; // [rsp+48h] [rbp-18h] BYREF
  unsigned int v60[4]; // [rsp+50h] [rbp-10h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 712);
  COpQueue::COpQueue(
    (CMFByteStreamMediaSource *)((char *)this + 88),
    (CMFByteStreamMediaSource *)((char *)this + 712),
    a6,
    (unsigned int)a4,
    v54);
  *((_DWORD *)this + 168) = a5;
  *((_DWORD *)this + 169) = 17;
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
  {
    HIBYTE(v60[0]) = a5;
    LOBYTE(v60[0]) = HIBYTE(a5);
    BYTE1(v60[0]) = BYTE2(a5);
    BYTE2(v60[0]) = BYTE1(a5);
    McTemplateU0s4pu_EventWriteTransfer(a5, (unsigned int)&Object_Create, (unsigned int)v60, (_DWORD)this + 672, 17);
  }
  _InterlockedIncrement(dword_1801B079C);
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
  v59 = 0;
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
  v58 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v55,
    "CMFByteStreamMediaSource::CMFByteStreamMediaSource",
    379);
  v15 = *a6;
  if ( *a6 < 0 )
  {
    v16 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v15 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFByteStreamMediaSource::CMFByteStreamMediaSource",
          379,
          v15);
    }
    if ( g_wppLevels )
    {
      v19 = 22;
LABEL_86:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, this, v15);
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
    v23 = (wchar_t *)CallStackTracing::s_wpInstance;
    v15 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
      CallStackTracing::s_wpInstance = v24;
      if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
      {
        v23 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v23 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v23 + 8) )
    {
      v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
      if ( *((_DWORD *)v25 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v25, "CMFByteStreamMediaSource::CMFByteStreamMediaSource", 388, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_87;
    v26 = 23;
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
    v30 = (wchar_t *)CallStackTracing::s_wpInstance;
    v15 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
      CallStackTracing::s_wpInstance = v31;
      if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
      {
        v30 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v30 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v30 + 8) )
    {
      v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
      if ( *((_DWORD *)v32 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v32, "CMFByteStreamMediaSource::CMFByteStreamMediaSource", 398, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_87;
    v26 = 24;
LABEL_27:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v26,
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
  v15 = ((__int64 (__fastcall *)(struct IMFByteStream *, GUID *, char *))a2->lpVtbl->QueryInterface)(
          a2,
          &IID_IMFTrustedInput,
          (char *)this + 984);
  if ( v15 < 0 )
  {
    ComSmartPtr<CBaseStreamSink>::operator=((char *)this + 984);
    v15 = 0;
  }
  MFGetService(
    (IUnknown *)a2,
    &MF_BYTESTREAM_DOWNLOADRATE_SERVICE,
    &IID_IMFByteStreamDownloadRateControl,
    (LPVOID *)this + 124);
  ComSmartPtr<CMPEGFrame>::operator=((char *)this + 1248, a4);
  v60[0] = 0;
  if ( *((_QWORD *)this + 156)
    && *v11
    && (int)CPropertyStorePtr::GetInt32((CMFByteStreamMediaSource *)((char *)this + 1248), v33, v60) >= 0 )
  {
    v34 = *v11;
    v57 = 0;
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 24LL))(v34, &v57) >= 0 )
      (*(void (__fastcall **)(__int64, void *, _QWORD))(*(_QWORD *)v57 + 168LL))(
        v57,
        &MF_MEDIASOURCE_PLUGIN_TEST_FLAGS,
        v60[0]);
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v57);
  }
  if ( a4
    && (v35 = *((_QWORD *)this + 119)) != 0
    && (v15 = (*(__int64 (__fastcall **)(__int64, struct IPropertyStore *))(*(_QWORD *)v35 + 24LL))(v35, a4), v15 < 0) )
  {
    v39 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37, v38);
      CallStackTracing::s_wpInstance = v40;
      if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
      {
        v39 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v39 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v39 + 8) )
    {
      v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
      if ( *((_DWORD *)v41 + 499) != v15 )
        CallStackContext::TraceFailure(v41, "CMFByteStreamMediaSource::CMFByteStreamMediaSource", 450, v15);
    }
    if ( g_wppLevels )
    {
      v19 = 25;
      goto LABEL_86;
    }
  }
  else
  {
    v42 = operator new(0xD8u);
    v46 = v42;
    if ( v42 )
    {
      *v42 = &CMFMediaStreamArray::`vftable';
      v42[2] = 0;
      *((_WORD *)v42 + 16) = 0;
      *((_BYTE *)v42 + 34) = 0;
      memset_0(v42 + 5, 0, 0xA0u);
      v46[25] = 0;
      v46[1] = &CTPtrArray<CMP3Stream,20>::`vftable';
      *((_DWORD *)v46 + 5) |= 1u;
      *((_DWORD *)v46 + 52) = 0;
      v46[3] = 0;
      *((_QWORD *)this + 139) = v46;
      if ( (unsigned __int8)byte_1801B110B >= 0x10u )
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
              &v59) )
      {
        *((_DWORD *)this + 321) = 1;
      }
      v56 = 0;
      MFGetConfigurationDWORD(0, L"Network\\DisableSampleBasedBuffering", &v56);
      if ( v56 )
        *((_DWORD *)this + 319) = 0;
      if ( ((__int64 (__fastcall *)(struct IMFByteStream *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
             a2,
             &IID_IMFAttributes,
             &v58) >= 0 )
      {
        v60[0] = 0;
        if ( (*(int (__fastcall **)(__int64, void *, unsigned int *))(*(_QWORD *)v58 + 56LL))(
               v58,
               &MF_BYTESTREAM_OPTICAL_MEDIA,
               v60) >= 0
          && v60[0] == 1 )
        {
          *((_DWORD *)this + 319) = 0;
        }
      }
      v49 = *((_QWORD *)this + 124);
      if ( v49 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v49 + 32LL))(v49, *((unsigned int *)this + 319));
      if ( (unsigned __int8)byte_1801B110B >= 0x10u )
        WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 17), v47, v48, this, (char *)this + 768, this);
    }
    else
    {
      v50 = (wchar_t *)CallStackTracing::s_wpInstance;
      v15 = -2147024882;
      *((_QWORD *)this + 139) = 0;
      if ( !v50 )
      {
        v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v44, v45);
        CallStackTracing::s_wpInstance = v51;
        if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
        {
          v50 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v50 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v50 + 8) )
      {
        v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
        if ( *((_DWORD *)v52 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v52, "CMFByteStreamMediaSource::CMFByteStreamMediaSource", 457, -2147024882);
      }
      if ( g_wppLevels )
      {
        v19 = 26;
        goto LABEL_86;
      }
    }
  }
LABEL_87:
  *a6 = v15;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v55);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v58);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v59);
  return this;
}

```

## disassembly

```asm
0x1800d7170  mov     [rsp-38h+arg_10], rbx
0x1800d7175  push    rbp
0x1800d7176  push    rsi
0x1800d7177  push    rdi
0x1800d7178  push    r12
0x1800d717a  push    r13
0x1800d717c  push    r14
0x1800d717e  push    r15
0x1800d7180  mov     rbp, rsp
0x1800d7183  sub     rsp, 60h
0x1800d7187  mov     r13, [rbp+arg_28]
0x1800d718b  lea     r15, [rcx+2C8h]
0x1800d7192  mov     rsi, r8
0x1800d7195  mov     r14, rdx
0x1800d7198  mov     rdi, rcx
0x1800d719b  mov     r8, r13; int *
0x1800d719e  mov     rdx, r15; struct CMFCSLock *
0x1800d71a1  add     rcx, 58h ; 'X'; this
0x1800d71a5  mov     r12, r9
0x1800d71a8  call    ??0COpQueue@@QEAA@PEAVCMFCSLock@@PEAJKK@Z; COpQueue::COpQueue(CMFCSLock *,long *,ulong,ulong)
0x1800d71ad  mov     ecx, [rbp+arg_20]
0x1800d71b0  lea     r9, [rdi+2A0h]
0x1800d71b7  mov     [r9], ecx
0x1800d71ba  mov     dword ptr [r9+4], 11h
0x1800d71c2  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x1800d71c9  jz      short loc_1800D71FB
0x1800d71cb  mov     eax, ecx
0x1800d71cd  mov     byte ptr [rbp+var_10+3], cl
0x1800d71d0  shr     eax, 18h
0x1800d71d3  lea     r8, [rbp+var_10]
0x1800d71d7  mov     byte ptr [rbp+var_10], al
0x1800d71da  lea     rdx, Object_Create
0x1800d71e1  mov     eax, ecx
0x1800d71e3  mov     byte ptr [rsp+60h+var_40], 11h
0x1800d71e8  shr     eax, 10h
0x1800d71eb  mov     byte ptr [rbp+var_10+1], al
0x1800d71ee  mov     eax, ecx
0x1800d71f0  shr     eax, 8
0x1800d71f3  mov     byte ptr [rbp+var_10+2], al
0x1800d71f6  call    McTemplateU0s4pu_EventWriteTransfer
0x1800d71fb  lock inc cs:dword_1801B079C
0x1800d7202  lea     rax, ??_7CAudioBurstBufferSource@@6B@; const CAudioBurstBufferSource::`vftable'
0x1800d7209  mov     dword ptr [rdi+248h], 1
0x1800d7213  lea     rbx, [rdi+250h]
0x1800d721a  mov     [rdi+240h], rax
0x1800d7221  mov     rcx, rbx
0x1800d7224  call    ??0?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@QEAA@I@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>(uint)
0x1800d7229  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFMediaSourceEx@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFMediaSourceEx'}
0x1800d7230  mov     [rdi], rax
0x1800d7233  lea     rcx, [rdi+2A8h]; this
0x1800d723a  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFGetService@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFGetService'}
0x1800d7241  mov     [rdi+8], rax
0x1800d7245  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFRateSupport@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFRateSupport'}
0x1800d724c  mov     [rdi+10h], rax
0x1800d7250  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFRateControl@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFRateControl'}
0x1800d7257  mov     [rdi+18h], rax
0x1800d725b  lea     rax, ??_7CMFByteStreamMediaSource@@6BIPropertyStore@@@; const CMFByteStreamMediaSource::`vftable'{for `IPropertyStore'}
0x1800d7262  mov     [rdi+20h], rax
0x1800d7266  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFObjectInformation@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFObjectInformation'}
0x1800d726d  mov     [rdi+28h], rax
0x1800d7271  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFPMPClient@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFPMPClient'}
0x1800d7278  mov     [rdi+30h], rax
0x1800d727c  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFPMPClientApp@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFPMPClientApp'}
0x1800d7283  mov     [rdi+38h], rax
0x1800d7287  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFTrustedInput@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFTrustedInput'}
0x1800d728e  mov     [rdi+40h], rax
0x1800d7292  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFSampleProtection@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFSampleProtection'}
0x1800d7299  mov     [rdi+48h], rax
0x1800d729d  lea     rax, ??_7CMFByteStreamMediaSource@@6BIByteStreamMediaSource@@@; const CMFByteStreamMediaSource::`vftable'{for `IByteStreamMediaSource'}
0x1800d72a4  mov     [rdi+50h], rax
0x1800d72a8  lea     rax, ??_7CMFByteStreamMediaSource@@6BCOpQueue@@@; const CMFByteStreamMediaSource::`vftable'{for `COpQueue'}
0x1800d72af  mov     [rdi+58h], rax
0x1800d72b3  lea     rax, ??_7CMFByteStreamMediaSource@@6BCAudioBurstBufferSource@@@; const CMFByteStreamMediaSource::`vftable'{for `CAudioBurstBufferSource'}
0x1800d72ba  mov     [rdi+240h], rax
0x1800d72c1  lea     rax, ??_7CMFByteStreamMediaSource@@6B?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@@; const CMFByteStreamMediaSource::`vftable'{for `CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>'}
0x1800d72c8  mov     [rbx], rax
0x1800d72cb  lea     rax, ??_7CMFByteStreamMediaSource@@6BIMFTelemetryComponent@@@; const CMFByteStreamMediaSource::`vftable'{for `IMFTelemetryComponent'}
0x1800d72d2  mov     [rdi+298h], rax
0x1800d72d9  call    ??0OnByteStreamEventAsyncCallback@CMFByteStreamMediaSource@@QEAA@XZ; CMFByteStreamMediaSource::OnByteStreamEventAsyncCallback::OnByteStreamEventAsyncCallback(void)
0x1800d72de  lea     rcx, [rdi+2B0h]; this
0x1800d72e5  call    ??0OnByteStreamReadHeaderAsyncCallback@CMFByteStreamMediaSource@@QEAA@XZ; CMFByteStreamMediaSource::OnByteStreamReadHeaderAsyncCallback::OnByteStreamReadHeaderAsyncCallback(void)
0x1800d72ea  lea     rcx, [rdi+2B8h]; this
0x1800d72f1  call    ??0OnByteStreamReadIndexAsyncCallback@CMFByteStreamMediaSource@@QEAA@XZ; CMFByteStreamMediaSource::OnByteStreamReadIndexAsyncCallback::OnByteStreamReadIndexAsyncCallback(void)
0x1800d72f6  lea     rcx, [rdi+2C0h]; this
0x1800d72fd  call    ??0OnByteStreamReadDataAsyncCallback@CMFByteStreamMediaSource@@QEAA@XZ; CMFByteStreamMediaSource::OnByteStreamReadDataAsyncCallback::OnByteStreamReadDataAsyncCallback(void)
0x1800d7302  mov     rcx, r15; lpCriticalSection
0x1800d7305  call    cs:__imp_InitializeCriticalSection
0x1800d730b  xor     ebx, ebx
0x1800d730d  lea     rcx, [rdi+300h]; this
0x1800d7314  mov     [rdi+2F0h], rbx
0x1800d731b  mov     rdx, r13; int *
0x1800d731e  mov     [rdi+2F8h], ebx
0x1800d7324  call    ??0CMFMediaEventGenerator@@QEAA@PEAJ@Z; CMFMediaEventGenerator::CMFMediaEventGenerator(long *)
0x1800d7329  mov     [rdi+378h], rbx
0x1800d7330  mov     [rdi+380h], rsi
0x1800d7337  test    rsi, rsi
0x1800d733a  jz      short loc_1800D734B
0x1800d733c  mov     rax, [rsi]
0x1800d733f  mov     rcx, rsi
0x1800d7342  mov     rax, [rax+8]
0x1800d7346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d734b  mov     [rdi+388h], rbx
0x1800d7352  lea     r15, [rdi+3B0h]
0x1800d7359  mov     [rdi+390h], rbx
0x1800d7360  lea     rcx, [rdi+460h]; this
0x1800d7367  mov     [rdi+398h], rbx
0x1800d736e  mov     r9, r13; int *
0x1800d7371  mov     [rdi+3A0h], rbx
0x1800d7378  mov     r8, r14; struct IMFByteStream *
0x1800d737b  mov     [rdi+3A8h], rbx
0x1800d7382  mov     rdx, rdi; struct CMFByteStreamMediaSource *
0x1800d7385  mov     [r15], rbx
0x1800d7388  mov     [rdi+3B8h], rbx
0x1800d738f  mov     [rdi+3C0h], rbx
0x1800d7396  mov     [rdi+3C8h], rbx
0x1800d739d  mov     [rdi+3D0h], rbx
0x1800d73a4  mov     [rdi+3D8h], rbx
0x1800d73ab  mov     [rdi+3E0h], rbx
0x1800d73b2  mov     [rdi+3E8h], rbx
0x1800d73b9  mov     [rdi+3F0h], rbx
0x1800d73c0  mov     [rdi+3F8h], rbx
0x1800d73c7  mov     [rdi+404h], rbx
0x1800d73ce  mov     [rdi+400h], ebx
0x1800d73d4  mov     qword ptr [rdi+410h], 0FFFFFFFFFFFFFFFFh
0x1800d73df  mov     [rdi+418h], rbx
0x1800d73e6  mov     qword ptr [rdi+420h], 3F800000h
0x1800d73f1  mov     [rdi+428h], rbx
0x1800d73f8  mov     [rdi+430h], rbx
0x1800d73ff  mov     qword ptr [rdi+438h], 4
0x1800d740a  mov     [rdi+440h], rbx
0x1800d7411  mov     [rdi+448h], rbx
0x1800d7418  mov     [rdi+450h], rbx
0x1800d741f  mov     [rdi+458h], rbx
0x1800d7426  call    ??0CMFByteStreamSourceReader@@QEAA@PEAVCMFByteStreamMediaSource@@PEAUIMFByteStream@@PEAJ@Z; CMFByteStreamSourceReader::CMFByteStreamSourceReader(CMFByteStreamMediaSource *,IMFByteStream *,long *)
0x1800d742b  mov     eax, 1
0x1800d7430  mov     [rdi+4D8h], rbx
0x1800d7437  lea     rsi, [rdi+4E0h]
0x1800d743e  mov     [rbp+var_18], rbx
0x1800d7442  mov     [rsi], rbx
0x1800d7445  lea     rdx, aCmfbytestreamm_21; "CMFByteStreamMediaSource::CMFByteStream"...
0x1800d744c  mov     [rdi+4E8h], rbx
0x1800d7453  lea     rcx, [rbp+var_30]; this
0x1800d7457  mov     [rdi+4F0h], rbx
0x1800d745e  mov     r8d, 17Bh; int
0x1800d7464  mov     [rdi+4F8h], ebx
0x1800d746a  mov     [rdi+4FCh], eax
0x1800d7470  mov     [rdi+500h], rax
0x1800d7477  mov     [rdi+508h], ebx
0x1800d747d  mov     qword ptr [rdi+510h], 1C9C380h
0x1800d7488  mov     [rdi+518h], ebx
0x1800d748e  mov     [rdi+51Ch], rax
0x1800d7495  mov     [rdi+524h], ebx
0x1800d749b  mov     [rdi+528h], rbx
0x1800d74a2  mov     [rbp+var_20], rbx
0x1800d74a6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800d74ab  mov     ebx, [r13+0]
0x1800d74af  test    ebx, ebx
0x1800d74b1  jns     loc_1800D7546
0x1800d74b7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d74be  test    rcx, rcx
0x1800d74c1  jnz     short loc_1800D7504
0x1800d74c3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d74c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d74d0  mov     rcx, rax
0x1800d74d3  test    rax, rax
0x1800d74d6  jz      short loc_1800D74F6
0x1800d74d8  mov     rax, [rax]
0x1800d74db  mov     edx, 7F0h
0x1800d74e0  mov     rax, [rax+8]
0x1800d74e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d74e9  test    eax, eax
0x1800d74eb  jz      short loc_1800D74F6
0x1800d74ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d74f4  jmp     short loc_1800D7504
0x1800d74f6  lea     rcx, qword_1801B07E0; this
0x1800d74fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d7504  cmp     byte ptr [rcx+8], 0
0x1800d7508  jz      short loc_1800D752F
0x1800d750a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d750f  cmp     [rax+7CCh], ebx
0x1800d7515  jz      short loc_1800D752F
0x1800d7517  mov     r9d, ebx; int
0x1800d751a  lea     rdx, aCmfbytestreamm_21; "CMFByteStreamMediaSource::CMFByteStream"...
0x1800d7521  mov     r8d, 17Bh; int
0x1800d7527  mov     rcx, rax; this
0x1800d752a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d752f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d7536  jb      loc_1800D7B8E
0x1800d753c  mov     edx, 16h
0x1800d7541  jmp     loc_1800D7B70
0x1800d7546  mov     rcx, [rdi+380h]; punkObject
0x1800d754d  lea     rbx, MF_MEDIASOURCE_SERVICE
0x1800d7554  mov     rdx, rbx; guidService
0x1800d7557  lea     r9, [rdi+388h]; ppvObject
0x1800d755e  lea     r8, IID_IMFSourceHeaderParserPlugin; riid
0x1800d7565  call    MFGetService
0x1800d756a  test    eax, eax
0x1800d756c  jns     loc_1800D760C
0x1800d7572  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d7579  mov     esi, 80070057h
0x1800d757e  mov     ebx, esi
0x1800d7580  test    rcx, rcx
0x1800d7583  jnz     short loc_1800D75C6
0x1800d7585  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d758b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d7592  mov     rcx, rax
0x1800d7595  test    rax, rax
0x1800d7598  jz      short loc_1800D75B8
0x1800d759a  mov     rax, [rax]
0x1800d759d  mov     edx, 7F0h
0x1800d75a2  mov     rax, [rax+8]
0x1800d75a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d75ab  test    eax, eax
0x1800d75ad  jz      short loc_1800D75B8
0x1800d75af  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d75b6  jmp     short loc_1800D75C6
0x1800d75b8  lea     rcx, qword_1801B07E0; this
0x1800d75bf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d75c6  cmp     byte ptr [rcx+8], 0
0x1800d75ca  jz      short loc_1800D75F1
0x1800d75cc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d75d1  cmp     [rax+7CCh], esi
0x1800d75d7  jz      short loc_1800D75F1
0x1800d75d9  mov     r9d, esi; int
0x1800d75dc  lea     rdx, aCmfbytestreamm_21; "CMFByteStreamMediaSource::CMFByteStream"...
0x1800d75e3  mov     r8d, 184h; int
0x1800d75e9  mov     rcx, rax; this
0x1800d75ec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d75f1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d75f8  jb      loc_1800D7B8E
0x1800d75fe  mov     edx, 17h
0x1800d7603  mov     dword ptr [rsp+60h+var_40], esi
0x1800d7607  jmp     loc_1800D7B74
0x1800d760c  mov     rcx, [rdi+380h]; punkObject
0x1800d7613  lea     r9, [rdi+390h]; ppvObject
0x1800d761a  lea     r8, IID_IMFSourceHeaderParserPlugin2; riid
0x1800d7621  mov     rdx, rbx; guidService
0x1800d7624  call    MFGetService
0x1800d7629  mov     rcx, [rdi+380h]; punkObject
0x1800d7630  lea     r9, [rdi+398h]; ppvObject
0x1800d7637  lea     r8, IID_IMFSourceDataParserPlugin; riid
0x1800d763e  mov     rdx, rbx; guidService
0x1800d7641  call    MFGetService
0x1800d7646  test    eax, eax
0x1800d7648  jns     loc_1800D76E4
0x1800d764e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d7655  mov     esi, 80070057h
0x1800d765a  mov     ebx, esi
0x1800d765c  test    rcx, rcx
0x1800d765f  jnz     short loc_1800D76A2
0x1800d7661  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d7667  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d766e  mov     rcx, rax
0x1800d7671  test    rax, rax
0x1800d7674  jz      short loc_1800D7694
0x1800d7676  mov     rax, [rax]
0x1800d7679  mov     edx, 7F0h
0x1800d767e  mov     rax, [rax+8]
0x1800d7682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7687  test    eax, eax
0x1800d7689  jz      short loc_1800D7694
0x1800d768b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d7692  jmp     short loc_1800D76A2
0x1800d7694  lea     rcx, qword_1801B07E0; this
0x1800d769b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d76a2  cmp     byte ptr [rcx+8], 0
0x1800d76a6  jz      short loc_1800D76CD
0x1800d76a8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d76ad  cmp     [rax+7CCh], esi
0x1800d76b3  jz      short loc_1800D76CD
0x1800d76b5  mov     r9d, esi; int
0x1800d76b8  lea     rdx, aCmfbytestreamm_21; "CMFByteStreamMediaSource::CMFByteStream"...
0x1800d76bf  mov     r8d, 18Eh; int
0x1800d76c5  mov     rcx, rax; this
0x1800d76c8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d76cd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d76d4  jb      loc_1800D7B8E
0x1800d76da  mov     edx, 18h
0x1800d76df  jmp     loc_1800D7603
0x1800d76e4  mov     rcx, [rdi+380h]; punkObject
0x1800d76eb  lea     r9, [rdi+3A0h]; ppvObject
0x1800d76f2  lea     r8, IID_IMFSourceIndexParserPlugin; riid
0x1800d76f9  mov     rdx, rbx; guidService
0x1800d76fc  call    MFGetService
0x1800d7701  mov     rcx, [rdi+380h]; punkObject
0x1800d7708  lea     r9, [rdi+3C8h]; ppvObject
0x1800d770f  lea     r8, IID_IMFRateSupport; riid
0x1800d7716  lea     rdx, MF_RATE_CONTROL_SERVICE; guidService
0x1800d771d  call    MFGetService
0x1800d7722  mov     rcx, [rdi+380h]; punkObject
0x1800d7729  lea     r9, [rdi+3A8h]; ppvObject
0x1800d7730  lea     r8, IID_IMFSourceProtectedContentPlugin; riid
0x1800d7737  mov     rdx, rbx; guidService
0x1800d773a  call    MFGetService
0x1800d773f  mov     rcx, [rdi+380h]; punkObject
0x1800d7746  lea     r8, IID_IMFSourceExtendedAttributesPlugin; riid
0x1800d774d  mov     r9, r15; ppvObject
0x1800d7750  mov     rdx, rbx; guidService
0x1800d7753  call    MFGetService
0x1800d7758  mov     rcx, [rdi+380h]; punkObject
  ... truncated ...
```
