# CMFByteStreamMediaSource::CreateStreamsForPresentation(void)

- ea: `0x1800cbd54`
- end: `0x1800cc8e8`
- name: `?CreateStreamsForPresentation@CMFByteStreamMediaSource@@AEAAJXZ`
- size: `2964`
- prototype: `__int64 __fastcall(CMFByteStreamMediaSource *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800d6114`

## callees

- `0x18000726c`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x18006c228`
- `0x180073b14`
- `0x180091984`
- `0x1800c2bd4`
- `0x1800c6d18`
- `0x1800cbd54`
- `0x1800ef10c`
- `0x180109590`
- `0x1801095a8`
- `0x18010a450`
- `0x1801416e0`
- `0x180149720`
- `0x1801497a0`
- `0x18014abac`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cbe2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc03d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc126`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc1d8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc267`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc2f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc385`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc414`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc541`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc671`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc756`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc82c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cbe2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc03d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc126`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc1d8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc267`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc2f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc385`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc414`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc541`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc671`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc756`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cc82c`

## string_xrefs

- `0x1800cbd6b`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800cbe85`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800cc0ee`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800cc17d`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800cc22f`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800cc2be`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800cc34d`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800cc3dc`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800cc46b`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800cc598`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800cc6c9`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800cc7ad`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800cc884`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`

## pseudocode

```c
__int64 __fastcall CMFByteStreamMediaSource::CreateStreamsForPresentation(CMFByteStreamMediaSource *this)
{
  struct CMFMediaStream *v2; // rdi
  _QWORD *v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  _QWORD *v7; // r13
  __int64 v8; // rdx
  int StreamById; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v15; // eax
  unsigned int v16; // r14d
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  struct IUnknown *v30; // r9
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct IUnknown *v36; // r9
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  wchar_t *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  wchar_t *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  wchar_t *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  unsigned int v64; // r14d
  unsigned int v65; // ecx
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r9
  wchar_t *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  CMFMediaStreamArray *v72; // rcx
  void *v73; // rcx
  __int64 v74; // rcx
  void *v75; // rax
  __int64 v76; // rdx
  __int64 v77; // r8
  __int64 v78; // r9
  wchar_t *v79; // rcx
  CallStackTracing *v80; // rax
  struct CallStackContext *v81; // rax
  __int64 v82; // rdx
  __int64 v83; // r8
  __int64 v84; // r9
  wchar_t *v85; // rcx
  CallStackTracing *v86; // rax
  struct CallStackContext *v87; // rax
  wchar_t *v88; // rcx
  CallStackTracing *v89; // rax
  struct CallStackContext *v90; // rax
  struct CMFMediaStream *v92; // [rsp+30h] [rbp-18h] BYREF
  struct IMFStreamDescriptor *v93[2]; // [rsp+38h] [rbp-10h] BYREF
  unsigned int v94; // [rsp+90h] [rbp+48h] BYREF
  unsigned int v95; // [rsp+98h] [rbp+50h] BYREF
  unsigned int v96; // [rsp+A0h] [rbp+58h] BYREF
  int v97; // [rsp+A8h] [rbp+60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v94,
    "CMFByteStreamMediaSource::CreateStreamsForPresentation",
    3868);
  v2 = 0;
  v92 = 0;
  v95 = 0;
  v97 = 0;
  v96 = 0;
  v3 = operator new(0xD8u);
  v7 = v3;
  if ( v3 )
  {
    *v3 = &CMFMediaStreamArray::`vftable';
    v3[2] = 0;
    *((_WORD *)v3 + 16) = 0;
    *((_BYTE *)v3 + 34) = 0;
    memset_0(v3 + 5, 0, 0xA0u);
    v7[25] = 0;
    v7[1] = &CTPtrArray<CMP3Stream,20>::`vftable';
    *((_DWORD *)v7 + 5) |= 1u;
    *((_DWORD *)v7 + 52) = 0;
    v7[3] = 0;
    StreamById = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 111) + 264LL))(
                   *((_QWORD *)this + 111),
                   &v95);
    if ( StreamById < 0 )
    {
      v12 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v10, v11);
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != StreamById )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CMFByteStreamMediaSource::CreateStreamsForPresentation",
            3885,
            StreamById);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          375,
          &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
          this,
          StreamById);
LABEL_161:
      CMFMediaStreamArray::`scalar deleting destructor'((CMFMediaStreamArray *)v7, 1u);
      goto LABEL_172;
    }
    v15 = v95;
    v16 = 0;
    v94 = v95;
    while ( v16 < v15 )
    {
      if ( v2 )
      {
        (*(void (__fastcall **)(struct CMFMediaStream *))(*(_QWORD *)v2 + 16LL))(v2);
        v2 = 0;
        v92 = 0;
      }
      v17 = *((_QWORD *)this + 111);
      v93[0] = 0;
      StreamById = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, struct IMFStreamDescriptor **))(*(_QWORD *)v17 + 272LL))(
                     v17,
                     v16,
                     &v97,
                     v93);
      if ( StreamById < 0 )
      {
        v61 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
          CallStackTracing::s_wpInstance = v62;
          if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
          {
            v61 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v61 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v61 + 8) )
        {
          v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
          if ( *((_DWORD *)v63 + 499) != StreamById )
            CallStackContext::TraceFailure(
              v63,
              "CMFByteStreamMediaSource::CreateStreamsForPresentation",
              3894,
              StreamById);
        }
        if ( g_wppLevels )
        {
          v44 = 376;
LABEL_110:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v44,
            &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
            this,
            StreamById);
        }
LABEL_111:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v93);
        goto LABEL_158;
      }
      StreamById = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, unsigned int *))v93[0]->lpVtbl->GetStreamIdentifier)(
                     v93[0],
                     &v96);
      if ( StreamById < 0 )
      {
        v58 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
          CallStackTracing::s_wpInstance = v59;
          if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
          {
            v58 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v58 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v58 + 8) )
        {
          v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
          if ( *((_DWORD *)v60 + 499) != StreamById )
            CallStackContext::TraceFailure(
              v60,
              "CMFByteStreamMediaSource::CreateStreamsForPresentation",
              3896,
              StreamById);
        }
        if ( g_wppLevels )
        {
          v44 = 377;
          goto LABEL_110;
        }
        goto LABEL_111;
      }
      if ( v97 )
      {
        if ( (unsigned __int8)byte_1801B110B >= 8u )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 17),
            379,
            &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
            this,
            v96);
        StreamById = CMFMediaStreamArray::GetStreamById(*((CMFMediaStreamArray **)this + 139), v96, &v92);
        if ( StreamById == -1072875819 )
        {
          StreamById = CMFMediaStream::CreateInstance(
                         (struct IByteStreamMediaSource *)(((unsigned __int64)this + 80) & -(__int64)(this != 0)),
                         v93[0],
                         &v92);
          if ( StreamById < 0 )
          {
            v45 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
              CallStackTracing::s_wpInstance = v46;
              if ( v46
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
              {
                v45 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v45 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v45 + 8) )
            {
              v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
              if ( *((_DWORD *)v47 + 499) != StreamById )
                CallStackContext::TraceFailure(
                  v47,
                  "CMFByteStreamMediaSource::CreateStreamsForPresentation",
                  3912,
                  StreamById);
            }
            if ( g_wppLevels )
            {
              v48 = 380;
              goto LABEL_57;
            }
            goto LABEL_58;
          }
          v2 = v92;
          if ( v92 )
            v30 = (struct IUnknown *)((char *)v92 + 8);
          else
            v30 = 0;
          StreamById = CMFByteStreamMediaSource::QueueEventWithIUnknown(this, 0xCDu, v28, v30);
          if ( StreamById < 0 )
          {
            v34 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
              CallStackTracing::s_wpInstance = v35;
              if ( v35
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
              {
                v34 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v34 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v34 + 8) )
            {
              v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
              if ( *((_DWORD *)v43 + 499) != StreamById )
                CallStackContext::TraceFailure(
                  v43,
                  "CMFByteStreamMediaSource::CreateStreamsForPresentation",
                  3914,
                  StreamById);
            }
            if ( g_wppLevels )
            {
              v44 = 381;
              goto LABEL_110;
            }
            goto LABEL_111;
          }
        }
        else
        {
          if ( StreamById < 0 )
          {
            v55 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25, v26);
              CallStackTracing::s_wpInstance = v56;
              if ( v56
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
              {
                v55 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v55 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v55 + 8) )
            {
              v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
              if ( *((_DWORD *)v57 + 499) != StreamById )
                CallStackContext::TraceFailure(
                  v57,
                  "CMFByteStreamMediaSource::CreateStreamsForPresentation",
                  3918,
                  StreamById);
            }
            if ( g_wppLevels )
            {
              v48 = 382;
LABEL_57:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v48,
                &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
                this,
                StreamById);
            }
LABEL_58:
            ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v93);
LABEL_59:
            v2 = v92;
            goto LABEL_158;
          }
          v2 = v92;
          if ( v92 )
            v36 = (struct IUnknown *)((char *)v92 + 8);
          else
            v36 = 0;
          StreamById = CMFByteStreamMediaSource::QueueEventWithIUnknown(this, 0xCEu, v25, v36);
          if ( StreamById < 0 )
          {
            v52 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38, v39);
              CallStackTracing::s_wpInstance = v53;
              if ( v53
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
              {
                v52 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v52 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v52 + 8) )
            {
              v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
              if ( *((_DWORD *)v54 + 499) != StreamById )
                CallStackContext::TraceFailure(
                  v54,
                  "CMFByteStreamMediaSource::CreateStreamsForPresentation",
                  3925,
                  StreamById);
            }
            if ( g_wppLevels )
            {
              v44 = 383;
              goto LABEL_110;
            }
            goto LABEL_111;
          }
        }
        StreamById = CMFMediaStreamArray::AddStream((CMFMediaStreamArray *)v7, v2);
        if ( StreamById < 0 )
        {
          v49 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40, v41, v42);
            CallStackTracing::s_wpInstance = v50;
            if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
            {
              v49 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v49 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v49 + 8) )
          {
            v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
            if ( *((_DWORD *)v51 + 499) != StreamById )
              CallStackContext::TraceFailure(
                v51,
                "CMFByteStreamMediaSource::CreateStreamsForPresentation",
                3929,
                StreamById);
          }
          if ( g_wppLevels )
          {
            v44 = 384;
            goto LABEL_110;
          }
          goto LABEL_111;
        }
      }
      else if ( (unsigned __int8)byte_1801B110B >= 8u )
      {
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          378,
          &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
          this,
          v96);
      }
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v93);
      v15 = v95;
      ++v16;
    }
    v64 = 0;
    v65 = *(_DWORD *)(*((_QWORD *)this + 139) + 208LL);
    v95 = v65;
    while ( v64 < v65 )
    {
      if ( v2 )
      {
        (*(void (__fastcall **)(struct CMFMediaStream *))(*(_QWORD *)v2 + 16LL))(v2);
        v92 = 0;
      }
      StreamById = CMFMediaStreamArray::GetStreamByIndex(*((CMFMediaStreamArray **)this + 139), v64, &v92);
      if ( StreamById < 0 )
      {
        v69 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v67, v68);
          CallStackTracing::s_wpInstance = v70;
          if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
          {
            v69 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v69 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v69 + 8) )
        {
          v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
          if ( *((_DWORD *)v71 + 499) != StreamById )
            CallStackContext::TraceFailure(
              v71,
              "CMFByteStreamMediaSource::CreateStreamsForPresentation",
              3940,
              StreamById);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            385,
            &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
            this,
            StreamById);
        goto LABEL_59;
      }
      v2 = v92;
      if ( !(unsigned int)CMFMediaStreamArray::ContainsStream((CMFMediaStreamArray *)v7, *((_DWORD *)v92 + 108)) )
      {
        CMFMediaStream::ForceEOS(v2);
        CMFMediaStream::Shutdown(v2);
      }
      v65 = v95;
      ++v64;
    }
    if ( v2 )
    {
      (*(void (__fastcall **)(struct CMFMediaStream *))(*(_QWORD *)v2 + 16LL))(v2);
      v2 = 0;
    }
    v72 = (CMFMediaStreamArray *)*((_QWORD *)this + 139);
    if ( v72 )
      CMFMediaStreamArray::`scalar deleting destructor'(v72, 1u);
    v73 = (void *)*((_QWORD *)this + 155);
    *((_QWORD *)this + 139) = v7;
    v7 = 0;
    operator delete(v73);
    v74 = *((_QWORD *)this + 139);
    *((_QWORD *)this + 155) = 0;
    v95 = *(_DWORD *)(v74 + 208);
    v75 = operator new(saturated_mul(v95, 8u));
    *((_QWORD *)this + 155) = v75;
    if ( v75 )
    {
      memset_0(v75, 0, 8LL * v95);
      if ( v94 == 1 )
        (*(void (__fastcall **)(char *))(*((_QWORD *)this + 72) + 8LL))((char *)this + 576);
      StreamById = CMFMediaStreamArray::NotifyRate(
                     *((CMFMediaStreamArray **)this + 139),
                     *((float *)this + 264),
                     *((_DWORD *)this + 265));
      if ( StreamById < 0 )
      {
        v85 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v86 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v82, v83, v84);
          CallStackTracing::s_wpInstance = v86;
          if ( v86 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v86 + 8LL))(v86, 2032) )
          {
            v85 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v85 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v85 + 8) )
        {
          v87 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v85);
          if ( *((_DWORD *)v87 + 499) != StreamById )
            CallStackContext::TraceFailure(
              v87,
              "CMFByteStreamMediaSource::CreateStreamsForPresentation",
              3981,
              StreamById);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            387,
            &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
            this,
            StreamById);
      }
    }
    else
    {
      v79 = (wchar_t *)CallStackTracing::s_wpInstance;
      StreamById = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v80 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v76, v77, v78);
        CallStackTracing::s_wpInstance = v80;
        if ( v80 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v80 + 8LL))(v80, 2032) )
        {
          v79 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v79 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v79 + 8) )
      {
        v81 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v79);
        if ( *((_DWORD *)v81 + 499) != -2147024882 )
          CallStackContext::TraceFailure(
            v81,
            "CMFByteStreamMediaSource::CreateStreamsForPresentation",
            3966,
            -2147024882);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          386,
          &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
          this,
          -2147024882);
    }
LABEL_158:
    if ( v2 )
      (*(void (__fastcall **)(struct CMFMediaStream *))(*(_QWORD *)v2 + 16LL))(v2);
    if ( v7 )
      goto LABEL_161;
  }
  else
  {
    v88 = (wchar_t *)CallStackTracing::s_wpInstance;
    StreamById = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v89 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
      CallStackTracing::s_wpInstance = v89;
      if ( v89 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v89 + 8LL))(v89, 2032) )
      {
        v88 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v88 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v88 + 8) )
    {
      v90 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v88);
      if ( *((_DWORD *)v90 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v90, "CMFByteStreamMediaSource::CreateStreamsForPresentation", 3883, -2147024882);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        374,
        &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
        this,
        -2147024882);
  }
LABEL_172:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v94);
  return (unsigned int)StreamById;
}

```

## disassembly

```asm
0x1800cbd54  push    rbp
0x1800cbd56  push    rbx
0x1800cbd57  push    rsi
0x1800cbd58  push    rdi
0x1800cbd59  push    r12
0x1800cbd5b  push    r13
0x1800cbd5d  push    r14
0x1800cbd5f  push    r15
0x1800cbd61  mov     rbp, rsp
0x1800cbd64  sub     rsp, 48h
0x1800cbd68  mov     rsi, rcx
0x1800cbd6b  lea     rdx, aCmfbytestreamm_86; "CMFByteStreamMediaSource::CreateStreams"...
0x1800cbd72  lea     rcx, [rbp+arg_0]; this
0x1800cbd76  mov     r8d, 0F1Ch; int
0x1800cbd7c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800cbd81  xor     r12d, r12d
0x1800cbd84  mov     ecx, 0D8h; Size
0x1800cbd89  mov     edi, r12d
0x1800cbd8c  mov     [rbp+var_18], r12
0x1800cbd90  mov     [rbp+arg_8], r12d
0x1800cbd94  mov     [rbp+arg_18], r12d
0x1800cbd98  mov     [rbp+arg_10], r12d
0x1800cbd9c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800cbda1  mov     r13, rax
0x1800cbda4  test    rax, rax
0x1800cbda7  jz      loc_1800CC817
0x1800cbdad  lea     rax, ??_7CMFMediaStreamArray@@6B@; const CMFMediaStreamArray::`vftable'
0x1800cbdb4  xor     edx, edx; Val
0x1800cbdb6  mov     [r13+0], rax
0x1800cbdba  lea     rcx, [r13+28h]; void *
0x1800cbdbe  xor     eax, eax
0x1800cbdc0  mov     [r13+10h], r12
0x1800cbdc4  mov     [r13+20h], ax
0x1800cbdc9  mov     r8d, 0A0h; Size
0x1800cbdcf  mov     [r13+22h], al
0x1800cbdd3  call    memset_0
0x1800cbdd8  mov     [r13+0C8h], r12
0x1800cbddf  lea     rax, ??_7?$CTPtrArray@VCMP3Stream@@$0BE@@@6B@; const CTPtrArray<CMP3Stream,20>::`vftable'
0x1800cbde6  mov     [r13+8], rax
0x1800cbdea  lea     r15d, [r12+1]
0x1800cbdef  or      [r13+14h], r15d
0x1800cbdf3  lea     rdx, [rbp+arg_8]
0x1800cbdf7  mov     [r13+0D0h], r12d
0x1800cbdfe  mov     [r13+18h], r12
0x1800cbe02  mov     rcx, [rsi+378h]
0x1800cbe09  mov     rax, [rcx]
0x1800cbe0c  mov     rax, [rax+108h]
0x1800cbe13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbe18  mov     ebx, eax
0x1800cbe1a  test    eax, eax
0x1800cbe1c  jns     loc_1800CBECF
0x1800cbe22  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cbe29  test    rcx, rcx
0x1800cbe2c  jnz     short loc_1800CBE6F
0x1800cbe2e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cbe34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cbe3b  mov     rcx, rax
0x1800cbe3e  test    rax, rax
0x1800cbe41  jz      short loc_1800CBE61
0x1800cbe43  mov     rax, [rax]
0x1800cbe46  mov     edx, 7F0h
0x1800cbe4b  mov     rax, [rax+8]
0x1800cbe4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbe54  test    eax, eax
0x1800cbe56  jz      short loc_1800CBE61
0x1800cbe58  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cbe5f  jmp     short loc_1800CBE6F
0x1800cbe61  lea     rcx, qword_1801B07E0; this
0x1800cbe68  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cbe6f  cmp     [rcx+8], r12b
0x1800cbe73  jz      short loc_1800CBE9A
0x1800cbe75  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cbe7a  cmp     [rax+7CCh], ebx
0x1800cbe80  jz      short loc_1800CBE9A
0x1800cbe82  mov     r9d, ebx; int
0x1800cbe85  lea     rdx, aCmfbytestreamm_86; "CMFByteStreamMediaSource::CreateStreams"...
0x1800cbe8c  mov     r8d, 0F2Dh; int
0x1800cbe92  mov     rcx, rax; this
0x1800cbe95  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cbe9a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800cbea1  jb      loc_1800CC807
0x1800cbea7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbeae  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x1800cbeb5  mov     edx, 177h
0x1800cbeba  mov     [rsp+48h+var_28], ebx
0x1800cbebe  mov     r9, rsi
0x1800cbec1  mov     rcx, [rcx+10h]
0x1800cbec5  call    WPP_SF_qD
0x1800cbeca  jmp     loc_1800CC807
0x1800cbecf  mov     eax, [rbp+arg_8]
0x1800cbed2  mov     r14d, r12d
0x1800cbed5  mov     [rbp+arg_0], eax
0x1800cbed8  lea     r12, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x1800cbedf  cmp     r14d, eax
0x1800cbee2  jnb     loc_1800CC4B6
0x1800cbee8  test    rdi, rdi
0x1800cbeeb  jz      short loc_1800CBF02
0x1800cbeed  mov     rax, [rdi]
0x1800cbef0  mov     rcx, rdi
0x1800cbef3  mov     rax, [rax+10h]
0x1800cbef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbefc  xor     edi, edi
0x1800cbefe  mov     [rbp+var_18], rdi
0x1800cbf02  mov     rcx, [rsi+378h]
0x1800cbf09  lea     r9, [rbp+var_10]
0x1800cbf0d  mov     [rbp+var_10], 0
0x1800cbf15  lea     r8, [rbp+arg_18]
0x1800cbf19  mov     edx, r14d
0x1800cbf1c  mov     rax, [rcx]
0x1800cbf1f  mov     rax, [rax+110h]
0x1800cbf26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbf2b  mov     ebx, eax
0x1800cbf2d  test    eax, eax
0x1800cbf2f  js      loc_1800CC408
0x1800cbf35  mov     rcx, [rbp+var_10]
0x1800cbf39  lea     rdx, [rbp+arg_10]
0x1800cbf3d  mov     rax, [rcx]
0x1800cbf40  mov     rax, [rax+108h]
0x1800cbf47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbf4c  mov     ebx, eax
0x1800cbf4e  test    eax, eax
0x1800cbf50  js      loc_1800CC379
0x1800cbf56  cmp     [rbp+arg_18], 0
0x1800cbf5a  jnz     short loc_1800CBF93
0x1800cbf5c  cmp     cs:byte_1801B110B, 8
0x1800cbf63  jb      loc_1800CC0B6
0x1800cbf69  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbf70  mov     edx, 17Ah
0x1800cbf75  mov     eax, [rbp+arg_10]
0x1800cbf78  mov     r9, rsi
0x1800cbf7b  mov     r8, r12
0x1800cbf7e  mov     [rsp+48h+var_28], eax
0x1800cbf82  mov     rcx, [rcx+88h]
0x1800cbf89  call    WPP_SF_qD
0x1800cbf8e  jmp     loc_1800CC0B6
0x1800cbf93  cmp     cs:byte_1801B110B, 8
0x1800cbf9a  jb      short loc_1800CBFC1
0x1800cbf9c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbfa3  mov     edx, 17Bh
0x1800cbfa8  mov     eax, [rbp+arg_10]
0x1800cbfab  mov     r9, rsi
0x1800cbfae  mov     r8, r12
0x1800cbfb1  mov     [rsp+48h+var_28], eax
0x1800cbfb5  mov     rcx, [rcx+88h]
0x1800cbfbc  call    WPP_SF_qD
0x1800cbfc1  mov     edx, [rbp+arg_10]; unsigned int
0x1800cbfc4  lea     r8, [rbp+var_18]; struct CMFMediaStream **
0x1800cbfc8  mov     rcx, [rsi+458h]; this
0x1800cbfcf  call    ?GetStreamById@CMFMediaStreamArray@@QEAAJKPEAPEAVCMFMediaStream@@@Z; CMFMediaStreamArray::GetStreamById(ulong,CMFMediaStream * *)
0x1800cbfd4  mov     ebx, eax
0x1800cbfd6  cmp     eax, 0C00D36D5h
0x1800cbfdb  jnz     loc_1800CC070
0x1800cbfe1  lea     rdx, [rsi+50h]
0x1800cbfe5  mov     rax, rsi
0x1800cbfe8  neg     rax
0x1800cbfeb  lea     r8, [rbp+var_18]; struct CMFMediaStream **
0x1800cbfef  sbb     rcx, rcx
0x1800cbff2  and     rcx, rdx; struct IByteStreamMediaSource *
0x1800cbff5  mov     rdx, [rbp+var_10]; struct IMFStreamDescriptor *
0x1800cbff9  call    ?CreateInstance@CMFMediaStream@@SAJPEAVIByteStreamMediaSource@@PEAUIMFStreamDescriptor@@PEAPEAV1@@Z; CMFMediaStream::CreateInstance(IByteStreamMediaSource *,IMFStreamDescriptor *,CMFMediaStream * *)
0x1800cbffe  mov     ebx, eax
0x1800cc000  test    eax, eax
0x1800cc002  js      loc_1800CC11A
0x1800cc008  mov     rdi, [rbp+var_18]
0x1800cc00c  test    rdi, rdi
0x1800cc00f  jz      short loc_1800CC017
0x1800cc011  lea     r9, [rdi+8]
0x1800cc015  jmp     short loc_1800CC01A
0x1800cc017  xor     r9d, r9d; struct IUnknown *
0x1800cc01a  mov     edx, 0CDh; unsigned int
0x1800cc01f  mov     rcx, rsi; this
0x1800cc022  call    ?QueueEventWithIUnknown@CMFByteStreamMediaSource@@AEAAJKJPEAUIUnknown@@@Z; CMFByteStreamMediaSource::QueueEventWithIUnknown(ulong,long,IUnknown *)
0x1800cc027  mov     ebx, eax
0x1800cc029  test    eax, eax
0x1800cc02b  jns     short loc_1800CC0A1
0x1800cc02d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc034  test    rcx, rcx
0x1800cc037  jnz     loc_1800CC0D8
0x1800cc03d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cc043  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc04a  mov     rcx, rax
0x1800cc04d  test    rax, rax
0x1800cc050  jz      short loc_1800CC0CA
0x1800cc052  mov     rax, [rax]
0x1800cc055  mov     edx, 7F0h
0x1800cc05a  mov     rax, [rax+8]
0x1800cc05e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc063  test    eax, eax
0x1800cc065  jz      short loc_1800CC0CA
0x1800cc067  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc06e  jmp     short loc_1800CC0D8
0x1800cc070  test    ebx, ebx
0x1800cc072  js      loc_1800CC2EA
0x1800cc078  mov     rdi, [rbp+var_18]
0x1800cc07c  test    rdi, rdi
0x1800cc07f  jz      short loc_1800CC087
0x1800cc081  lea     r9, [rdi+8]
0x1800cc085  jmp     short loc_1800CC08A
0x1800cc087  xor     r9d, r9d; struct IUnknown *
0x1800cc08a  mov     edx, 0CEh; unsigned int
0x1800cc08f  mov     rcx, rsi; this
0x1800cc092  call    ?QueueEventWithIUnknown@CMFByteStreamMediaSource@@AEAAJKJPEAUIUnknown@@@Z; CMFByteStreamMediaSource::QueueEventWithIUnknown(ulong,long,IUnknown *)
0x1800cc097  mov     ebx, eax
0x1800cc099  test    eax, eax
0x1800cc09b  js      loc_1800CC25B
0x1800cc0a1  mov     rdx, rdi; struct CMFMediaStream *
0x1800cc0a4  mov     rcx, r13; this
0x1800cc0a7  call    ?AddStream@CMFMediaStreamArray@@QEAAJPEAVCMFMediaStream@@@Z; CMFMediaStreamArray::AddStream(CMFMediaStream *)
0x1800cc0ac  mov     ebx, eax
0x1800cc0ae  test    eax, eax
0x1800cc0b0  js      loc_1800CC1CC
0x1800cc0b6  lea     rcx, [rbp+var_10]; void *
0x1800cc0ba  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800cc0bf  mov     eax, [rbp+arg_8]
0x1800cc0c2  add     r14d, r15d
0x1800cc0c5  jmp     loc_1800CBEDF
0x1800cc0ca  lea     rcx, qword_1801B07E0; this
0x1800cc0d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc0d8  cmp     byte ptr [rcx+8], 0
0x1800cc0dc  jz      short loc_1800CC103
0x1800cc0de  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cc0e3  cmp     [rax+7CCh], ebx
0x1800cc0e9  jz      short loc_1800CC103
0x1800cc0eb  mov     r9d, ebx; int
0x1800cc0ee  lea     rdx, aCmfbytestreamm_86; "CMFByteStreamMediaSource::CreateStreams"...
0x1800cc0f5  mov     r8d, 0F4Ah; int
0x1800cc0fb  mov     rcx, rax; this
0x1800cc0fe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cc103  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800cc10a  jb      loc_1800CC4A8
0x1800cc110  mov     edx, 17Dh
0x1800cc115  jmp     loc_1800CC48E
0x1800cc11a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc121  test    rcx, rcx
0x1800cc124  jnz     short loc_1800CC167
0x1800cc126  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cc12c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc133  mov     rcx, rax
0x1800cc136  test    rax, rax
0x1800cc139  jz      short loc_1800CC159
0x1800cc13b  mov     rax, [rax]
0x1800cc13e  mov     edx, 7F0h
0x1800cc143  mov     rax, [rax+8]
0x1800cc147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc14c  test    eax, eax
0x1800cc14e  jz      short loc_1800CC159
0x1800cc150  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc157  jmp     short loc_1800CC167
0x1800cc159  lea     rcx, qword_1801B07E0; this
0x1800cc160  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc167  cmp     byte ptr [rcx+8], 0
0x1800cc16b  jz      short loc_1800CC192
0x1800cc16d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cc172  cmp     [rax+7CCh], ebx
0x1800cc178  jz      short loc_1800CC192
0x1800cc17a  mov     r9d, ebx; int
0x1800cc17d  lea     rdx, aCmfbytestreamm_86; "CMFByteStreamMediaSource::CreateStreams"...
0x1800cc184  mov     r8d, 0F48h; int
0x1800cc18a  mov     rcx, rax; this
0x1800cc18d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cc192  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800cc199  jb      short loc_1800CC1BA
0x1800cc19b  mov     edx, 17Ch
0x1800cc1a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc1a7  mov     r9, rsi
0x1800cc1aa  mov     r8, r12
0x1800cc1ad  mov     [rsp+48h+var_28], ebx
0x1800cc1b1  mov     rcx, [rcx+10h]
0x1800cc1b5  call    WPP_SF_qD
0x1800cc1ba  lea     rcx, [rbp+var_10]; void *
0x1800cc1be  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800cc1c3  mov     rdi, [rbp+var_18]
0x1800cc1c7  jmp     loc_1800CC7EA
0x1800cc1cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc1d3  test    rcx, rcx
0x1800cc1d6  jnz     short loc_1800CC219
0x1800cc1d8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cc1de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc1e5  mov     rcx, rax
0x1800cc1e8  test    rax, rax
0x1800cc1eb  jz      short loc_1800CC20B
0x1800cc1ed  mov     rax, [rax]
0x1800cc1f0  mov     edx, 7F0h
0x1800cc1f5  mov     rax, [rax+8]
0x1800cc1f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc1fe  test    eax, eax
0x1800cc200  jz      short loc_1800CC20B
0x1800cc202  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc209  jmp     short loc_1800CC219
0x1800cc20b  lea     rcx, qword_1801B07E0; this
0x1800cc212  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cc219  cmp     byte ptr [rcx+8], 0
0x1800cc21d  jz      short loc_1800CC244
0x1800cc21f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cc224  cmp     [rax+7CCh], ebx
0x1800cc22a  jz      short loc_1800CC244
0x1800cc22c  mov     r9d, ebx; int
0x1800cc22f  lea     rdx, aCmfbytestreamm_86; "CMFByteStreamMediaSource::CreateStreams"...
0x1800cc236  mov     r8d, 0F59h; int
0x1800cc23c  mov     rcx, rax; this
  ... truncated ...
```
