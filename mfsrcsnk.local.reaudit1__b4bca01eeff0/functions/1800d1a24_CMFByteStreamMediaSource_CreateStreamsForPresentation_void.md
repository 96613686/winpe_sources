# CMFByteStreamMediaSource::CreateStreamsForPresentation(void)

- ea: `0x1800d1a24`
- end: `0x1800d2601`
- name: `?CreateStreamsForPresentation@CMFByteStreamMediaSource@@AEAAJXZ`
- size: `3037`
- prototype: `__int64 __fastcall(CMFByteStreamMediaSource *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800dc320`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x18003cc48`
- `0x18006d4d8`
- `0x180079680`
- `0x180096ba4`
- `0x1800c8a94`
- `0x1800cc738`
- `0x1800d1a24`
- `0x1800f5f88`
- `0x180110a7c`
- `0x180110a94`
- `0x180111960`
- `0x180149480`
- `0x180151940`
- `0x1801519c0`
- `0x180152ec0`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d1afe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d1d13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d1e02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d1eba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d1f4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d1fe4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d2079`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d210e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d2241`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d2377`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d2462`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d253e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d1afe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d1d13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d1e02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d1eba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d1f4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d1fe4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d2079`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d210e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d2241`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d2377`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d2462`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d253e`

## string_xrefs

- `0x1800d1a3b`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800d1b5b`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800d1dca`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800d1e5f`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800d1f17`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800d1fac`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800d2041`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800d20d6`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800d216b`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800d229e`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800d23d5`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800d24bf`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`
- `0x1800d259c`: `CMFByteStreamMediaSource::CreateStreamsForPresentation`

## pseudocode

```c
__int64 __fastcall CMFByteStreamMediaSource::CreateStreamsForPresentation(CMFByteStreamMediaSource *this)
{
  struct CMFMediaStream *v2; // rdi
  _QWORD *v3; // rax
  __int64 v4; // rdx
  _QWORD *v5; // r13
  __int64 v6; // rdx
  int StreamById; // ebx
  wchar_t *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v11; // eax
  unsigned int v12; // r14d
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  int v17; // r8d
  __int64 v18; // rdx
  int v19; // r8d
  struct IUnknown *v20; // r9
  __int64 v21; // rdx
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct IUnknown *v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rdx
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  unsigned int v48; // r14d
  unsigned int v49; // ecx
  __int64 v50; // rdx
  wchar_t *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  CMFMediaStreamArray *v54; // rcx
  void *v55; // rcx
  __int64 v56; // rcx
  void *v57; // rax
  __int64 v58; // rdx
  wchar_t *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  wchar_t *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  wchar_t *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  struct CMFMediaStream *v70; // [rsp+30h] [rbp-18h] BYREF
  struct IMFStreamDescriptor *v71[2]; // [rsp+38h] [rbp-10h] BYREF
  unsigned int v72; // [rsp+90h] [rbp+48h] BYREF
  unsigned int v73; // [rsp+98h] [rbp+50h] BYREF
  unsigned int v74; // [rsp+A0h] [rbp+58h] BYREF
  int v75; // [rsp+A8h] [rbp+60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v72,
    "CMFByteStreamMediaSource::CreateStreamsForPresentation",
    3868);
  v2 = 0;
  v70 = 0;
  v73 = 0;
  v75 = 0;
  v74 = 0;
  v3 = operator new(0xD8u);
  v5 = v3;
  if ( v3 )
  {
    *v3 = &CMFMediaStreamArray::`vftable';
    v3[2] = 0;
    *((_WORD *)v3 + 16) = 0;
    *((_BYTE *)v3 + 34) = 0;
    memset_0(v3 + 5, 0, 0xA0u);
    v5[25] = 0;
    v5[1] = &CTPtrArray<CMP3Stream,20>::`vftable';
    *((_DWORD *)v5 + 5) |= 1u;
    *((_DWORD *)v5 + 52) = 0;
    v5[3] = 0;
    StreamById = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 111) + 264LL))(
                   *((_QWORD *)this + 111),
                   &v73);
    if ( StreamById < 0 )
    {
      v8 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
        CallStackTracing::s_wpInstance = v9;
        if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
        {
          v8 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
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
      CMFMediaStreamArray::`scalar deleting destructor'((CMFMediaStreamArray *)v5, 1u);
      goto LABEL_172;
    }
    v11 = v73;
    v12 = 0;
    v72 = v73;
    while ( v12 < v11 )
    {
      if ( v2 )
      {
        (*(void (__fastcall **)(struct CMFMediaStream *))(*(_QWORD *)v2 + 16LL))(v2);
        v2 = 0;
        v70 = 0;
      }
      v13 = *((_QWORD *)this + 111);
      v71[0] = 0;
      StreamById = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, struct IMFStreamDescriptor **))(*(_QWORD *)v13 + 272LL))(
                     v13,
                     v12,
                     &v75,
                     v71);
      if ( StreamById < 0 )
      {
        v45 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
          CallStackTracing::s_wpInstance = v46;
          if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
          {
            v45 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v45 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v45 + 8) )
        {
          v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
          if ( *((_DWORD *)v47 + 499) != StreamById )
            CallStackContext::TraceFailure(
              v47,
              "CMFByteStreamMediaSource::CreateStreamsForPresentation",
              3894,
              StreamById);
        }
        if ( g_wppLevels )
        {
          v28 = 376;
LABEL_110:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v28,
            &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
            this,
            StreamById);
        }
LABEL_111:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v71);
        goto LABEL_158;
      }
      StreamById = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, unsigned int *))v71[0]->lpVtbl->GetStreamIdentifier)(
                     v71[0],
                     &v74);
      if ( StreamById < 0 )
      {
        v42 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
          CallStackTracing::s_wpInstance = v43;
          if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
          {
            v42 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v42 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v42 + 8) )
        {
          v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
          if ( *((_DWORD *)v44 + 499) != StreamById )
            CallStackContext::TraceFailure(
              v44,
              "CMFByteStreamMediaSource::CreateStreamsForPresentation",
              3896,
              StreamById);
        }
        if ( g_wppLevels )
        {
          v28 = 377;
          goto LABEL_110;
        }
        goto LABEL_111;
      }
      if ( v75 )
      {
        if ( (unsigned __int8)byte_1801BA10B >= 8u )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 17),
            379,
            &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
            this,
            v74);
        StreamById = CMFMediaStreamArray::GetStreamById(*((CMFMediaStreamArray **)this + 139), v74, &v70);
        if ( StreamById == -1072875819 )
        {
          StreamById = CMFMediaStream::CreateInstance(
                         (struct IByteStreamMediaSource *)(((unsigned __int64)this + 80) & -(__int64)(this != 0)),
                         v71[0],
                         &v70);
          if ( StreamById < 0 )
          {
            v29 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
              CallStackTracing::s_wpInstance = v30;
              if ( v30
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
              {
                v29 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v29 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v29 + 8) )
            {
              v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
              if ( *((_DWORD *)v31 + 499) != StreamById )
                CallStackContext::TraceFailure(
                  v31,
                  "CMFByteStreamMediaSource::CreateStreamsForPresentation",
                  3912,
                  StreamById);
            }
            if ( g_wppLevels )
            {
              v32 = 380;
              goto LABEL_57;
            }
            goto LABEL_58;
          }
          v2 = v70;
          if ( v70 )
            v20 = (struct IUnknown *)((char *)v70 + 8);
          else
            v20 = 0;
          StreamById = CMFByteStreamMediaSource::QueueEventWithIUnknown(this, 0xCDu, v19, v20);
          if ( StreamById < 0 )
          {
            v22 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
              CallStackTracing::s_wpInstance = v23;
              if ( v23
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
              {
                v22 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v22 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v22 + 8) )
            {
              v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
              if ( *((_DWORD *)v27 + 499) != StreamById )
                CallStackContext::TraceFailure(
                  v27,
                  "CMFByteStreamMediaSource::CreateStreamsForPresentation",
                  3914,
                  StreamById);
            }
            if ( g_wppLevels )
            {
              v28 = 381;
              goto LABEL_110;
            }
            goto LABEL_111;
          }
        }
        else
        {
          if ( StreamById < 0 )
          {
            v39 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
              CallStackTracing::s_wpInstance = v40;
              if ( v40
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
              {
                v39 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v39 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v39 + 8) )
            {
              v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
              if ( *((_DWORD *)v41 + 499) != StreamById )
                CallStackContext::TraceFailure(
                  v41,
                  "CMFByteStreamMediaSource::CreateStreamsForPresentation",
                  3918,
                  StreamById);
            }
            if ( g_wppLevels )
            {
              v32 = 382;
LABEL_57:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v32,
                &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
                this,
                StreamById);
            }
LABEL_58:
            ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v71);
LABEL_59:
            v2 = v70;
            goto LABEL_158;
          }
          v2 = v70;
          if ( v70 )
            v24 = (struct IUnknown *)((char *)v70 + 8);
          else
            v24 = 0;
          StreamById = CMFByteStreamMediaSource::QueueEventWithIUnknown(this, 0xCEu, v17, v24);
          if ( StreamById < 0 )
          {
            v36 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
              CallStackTracing::s_wpInstance = v37;
              if ( v37
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
              {
                v36 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v36 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v36 + 8) )
            {
              v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
              if ( *((_DWORD *)v38 + 499) != StreamById )
                CallStackContext::TraceFailure(
                  v38,
                  "CMFByteStreamMediaSource::CreateStreamsForPresentation",
                  3925,
                  StreamById);
            }
            if ( g_wppLevels )
            {
              v28 = 383;
              goto LABEL_110;
            }
            goto LABEL_111;
          }
        }
        StreamById = CMFMediaStreamArray::AddStream((CMFMediaStreamArray *)v5, v2);
        if ( StreamById < 0 )
        {
          v33 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
            CallStackTracing::s_wpInstance = v34;
            if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
            {
              v33 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v33 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v33 + 8) )
          {
            v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
            if ( *((_DWORD *)v35 + 499) != StreamById )
              CallStackContext::TraceFailure(
                v35,
                "CMFByteStreamMediaSource::CreateStreamsForPresentation",
                3929,
                StreamById);
          }
          if ( g_wppLevels )
          {
            v28 = 384;
            goto LABEL_110;
          }
          goto LABEL_111;
        }
      }
      else if ( (unsigned __int8)byte_1801BA10B >= 8u )
      {
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          378,
          &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
          this,
          v74);
      }
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v71);
      v11 = v73;
      ++v12;
    }
    v48 = 0;
    v49 = *(_DWORD *)(*((_QWORD *)this + 139) + 208LL);
    v73 = v49;
    while ( v48 < v49 )
    {
      if ( v2 )
      {
        (*(void (__fastcall **)(struct CMFMediaStream *))(*(_QWORD *)v2 + 16LL))(v2);
        v70 = 0;
      }
      StreamById = CMFMediaStreamArray::GetStreamByIndex(*((CMFMediaStreamArray **)this + 139), v48, &v70);
      if ( StreamById < 0 )
      {
        v51 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50);
          CallStackTracing::s_wpInstance = v52;
          if ( v52 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
          {
            v51 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v51 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v51 + 8) )
        {
          v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
          if ( *((_DWORD *)v53 + 499) != StreamById )
            CallStackContext::TraceFailure(
              v53,
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
      v2 = v70;
      if ( !(unsigned int)CMFMediaStreamArray::ContainsStream((CMFMediaStreamArray *)v5, *((_DWORD *)v70 + 108)) )
      {
        CMFMediaStream::ForceEOS(v2);
        CMFMediaStream::Shutdown(v2);
      }
      v49 = v73;
      ++v48;
    }
    if ( v2 )
    {
      (*(void (__fastcall **)(struct CMFMediaStream *))(*(_QWORD *)v2 + 16LL))(v2);
      v2 = 0;
    }
    v54 = (CMFMediaStreamArray *)*((_QWORD *)this + 139);
    if ( v54 )
      CMFMediaStreamArray::`scalar deleting destructor'(v54, 1u);
    v55 = (void *)*((_QWORD *)this + 155);
    *((_QWORD *)this + 139) = v5;
    v5 = 0;
    operator delete(v55);
    v56 = *((_QWORD *)this + 139);
    *((_QWORD *)this + 155) = 0;
    v73 = *(_DWORD *)(v56 + 208);
    v57 = operator new(saturated_mul(v73, 8u));
    *((_QWORD *)this + 155) = v57;
    if ( v57 )
    {
      memset_0(v57, 0, 8LL * v73);
      if ( v72 == 1 )
        (*(void (__fastcall **)(char *))(*((_QWORD *)this + 72) + 8LL))((char *)this + 576);
      StreamById = CMFMediaStreamArray::NotifyRate(
                     *((CMFMediaStreamArray **)this + 139),
                     *((float *)this + 264),
                     *((_DWORD *)this + 265));
      if ( StreamById < 0 )
      {
        v63 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62);
          CallStackTracing::s_wpInstance = v64;
          if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
          {
            v63 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v63 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v63 + 8) )
        {
          v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
          if ( *((_DWORD *)v65 + 499) != StreamById )
            CallStackContext::TraceFailure(
              v65,
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
      v59 = (wchar_t *)CallStackTracing::s_wpInstance;
      StreamById = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58);
        CallStackTracing::s_wpInstance = v60;
        if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
        {
          v59 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v59 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v59 + 8) )
      {
        v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
        if ( *((_DWORD *)v61 + 499) != -2147024882 )
          CallStackContext::TraceFailure(
            v61,
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
    if ( v5 )
      goto LABEL_161;
  }
  else
  {
    v66 = (wchar_t *)CallStackTracing::s_wpInstance;
    StreamById = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v67;
      if ( v67 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
      {
        v66 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v66 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v66 + 8) )
    {
      v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
      if ( *((_DWORD *)v68 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v68, "CMFByteStreamMediaSource::CreateStreamsForPresentation", 3883, -2147024882);
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
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v72);
  return (unsigned int)StreamById;
}

```

## disassembly

```asm
0x1800d1a24  push    rbp
0x1800d1a26  push    rbx
0x1800d1a27  push    rsi
0x1800d1a28  push    rdi
0x1800d1a29  push    r12
0x1800d1a2b  push    r13
0x1800d1a2d  push    r14
0x1800d1a2f  push    r15
0x1800d1a31  mov     rbp, rsp
0x1800d1a34  sub     rsp, 48h
0x1800d1a38  mov     rsi, rcx
0x1800d1a3b  lea     rdx, aCmfbytestreamm_86; "CMFByteStreamMediaSource::CreateStreams"...
0x1800d1a42  lea     rcx, [rbp+arg_0]; this
0x1800d1a46  mov     r8d, 0F1Ch; int
0x1800d1a4c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800d1a51  xor     r12d, r12d
0x1800d1a54  mov     ecx, 0D8h; Size
0x1800d1a59  mov     edi, r12d
0x1800d1a5c  mov     [rbp+var_18], r12
0x1800d1a60  mov     [rbp+arg_8], r12d
0x1800d1a64  mov     [rbp+arg_18], r12d
0x1800d1a68  mov     [rbp+arg_10], r12d
0x1800d1a6c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d1a71  mov     r13, rax
0x1800d1a74  test    rax, rax
0x1800d1a77  jz      loc_1800D2529
0x1800d1a7d  lea     rax, ??_7CMFMediaStreamArray@@6B@; const CMFMediaStreamArray::`vftable'
0x1800d1a84  xor     edx, edx; Val
0x1800d1a86  mov     [r13+0], rax
0x1800d1a8a  lea     rcx, [r13+28h]; void *
0x1800d1a8e  xor     eax, eax
0x1800d1a90  mov     [r13+10h], r12
0x1800d1a94  mov     [r13+20h], ax
0x1800d1a99  mov     r8d, 0A0h; Size
0x1800d1a9f  mov     [r13+22h], al
0x1800d1aa3  call    memset_0
0x1800d1aa8  mov     [r13+0C8h], r12
0x1800d1aaf  lea     rax, ??_7?$CTPtrArray@VCMP3Stream@@$0BE@@@6B@; const CTPtrArray<CMP3Stream,20>::`vftable'
0x1800d1ab6  mov     [r13+8], rax
0x1800d1aba  lea     r15d, [r12+1]
0x1800d1abf  or      [r13+14h], r15d
0x1800d1ac3  lea     rdx, [rbp+arg_8]
0x1800d1ac7  mov     [r13+0D0h], r12d
0x1800d1ace  mov     [r13+18h], r12
0x1800d1ad2  mov     rcx, [rsi+378h]
0x1800d1ad9  mov     rax, [rcx]
0x1800d1adc  mov     rax, [rax+108h]
0x1800d1ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1ae8  mov     ebx, eax
0x1800d1aea  test    eax, eax
0x1800d1aec  jns     loc_1800D1BA5
0x1800d1af2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d1af9  test    rcx, rcx
0x1800d1afc  jnz     short loc_1800D1B45
0x1800d1afe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d1b05  nop     dword ptr [rax+rax+00h]
0x1800d1b0a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d1b11  mov     rcx, rax
0x1800d1b14  test    rax, rax
0x1800d1b17  jz      short loc_1800D1B37
0x1800d1b19  mov     rax, [rax]
0x1800d1b1c  mov     edx, 7F0h
0x1800d1b21  mov     rax, [rax+8]
0x1800d1b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1b2a  test    eax, eax
0x1800d1b2c  jz      short loc_1800D1B37
0x1800d1b2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d1b35  jmp     short loc_1800D1B45
0x1800d1b37  lea     rcx, qword_1801B97E0; this
0x1800d1b3e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d1b45  cmp     [rcx+8], r12b
0x1800d1b49  jz      short loc_1800D1B70
0x1800d1b4b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d1b50  cmp     [rax+7CCh], ebx
0x1800d1b56  jz      short loc_1800D1B70
0x1800d1b58  mov     r9d, ebx; int
0x1800d1b5b  lea     rdx, aCmfbytestreamm_86; "CMFByteStreamMediaSource::CreateStreams"...
0x1800d1b62  mov     r8d, 0F2Dh; int
0x1800d1b68  mov     rcx, rax; this
0x1800d1b6b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d1b70  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800d1b77  jb      loc_1800D2519
0x1800d1b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d1b84  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x1800d1b8b  mov     edx, 177h
0x1800d1b90  mov     [rsp+48h+var_28], ebx
0x1800d1b94  mov     r9, rsi
0x1800d1b97  mov     rcx, [rcx+10h]
0x1800d1b9b  call    WPP_SF_qD
0x1800d1ba0  jmp     loc_1800D2519
0x1800d1ba5  mov     eax, [rbp+arg_8]
0x1800d1ba8  mov     r14d, r12d
0x1800d1bab  mov     [rbp+arg_0], eax
0x1800d1bae  lea     r12, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x1800d1bb5  cmp     r14d, eax
0x1800d1bb8  jnb     loc_1800D21B6
0x1800d1bbe  test    rdi, rdi
0x1800d1bc1  jz      short loc_1800D1BD8
0x1800d1bc3  mov     rax, [rdi]
0x1800d1bc6  mov     rcx, rdi
0x1800d1bc9  mov     rax, [rax+10h]
0x1800d1bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1bd2  xor     edi, edi
0x1800d1bd4  mov     [rbp+var_18], rdi
0x1800d1bd8  mov     rcx, [rsi+378h]
0x1800d1bdf  lea     r9, [rbp+var_10]
0x1800d1be3  mov     [rbp+var_10], 0
0x1800d1beb  lea     r8, [rbp+arg_18]
0x1800d1bef  mov     edx, r14d
0x1800d1bf2  mov     rax, [rcx]
0x1800d1bf5  mov     rax, [rax+110h]
0x1800d1bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1c01  mov     ebx, eax
0x1800d1c03  test    eax, eax
0x1800d1c05  js      loc_1800D2102
0x1800d1c0b  mov     rcx, [rbp+var_10]
0x1800d1c0f  lea     rdx, [rbp+arg_10]
0x1800d1c13  mov     rax, [rcx]
0x1800d1c16  mov     rax, [rax+108h]
0x1800d1c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1c22  mov     ebx, eax
0x1800d1c24  test    eax, eax
0x1800d1c26  js      loc_1800D206D
0x1800d1c2c  cmp     [rbp+arg_18], 0
0x1800d1c30  jnz     short loc_1800D1C69
0x1800d1c32  cmp     cs:byte_1801BA10B, 8
0x1800d1c39  jb      loc_1800D1D92
0x1800d1c3f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d1c46  mov     edx, 17Ah
0x1800d1c4b  mov     eax, [rbp+arg_10]
0x1800d1c4e  mov     r9, rsi
0x1800d1c51  mov     r8, r12
0x1800d1c54  mov     [rsp+48h+var_28], eax
0x1800d1c58  mov     rcx, [rcx+88h]
0x1800d1c5f  call    WPP_SF_qD
0x1800d1c64  jmp     loc_1800D1D92
0x1800d1c69  cmp     cs:byte_1801BA10B, 8
0x1800d1c70  jb      short loc_1800D1C97
0x1800d1c72  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d1c79  mov     edx, 17Bh
0x1800d1c7e  mov     eax, [rbp+arg_10]
0x1800d1c81  mov     r9, rsi
0x1800d1c84  mov     r8, r12
0x1800d1c87  mov     [rsp+48h+var_28], eax
0x1800d1c8b  mov     rcx, [rcx+88h]
0x1800d1c92  call    WPP_SF_qD
0x1800d1c97  mov     edx, [rbp+arg_10]; unsigned int
0x1800d1c9a  lea     r8, [rbp+var_18]; struct CMFMediaStream **
0x1800d1c9e  mov     rcx, [rsi+458h]; this
0x1800d1ca5  call    ?GetStreamById@CMFMediaStreamArray@@QEAAJKPEAPEAVCMFMediaStream@@@Z; CMFMediaStreamArray::GetStreamById(ulong,CMFMediaStream * *)
0x1800d1caa  mov     ebx, eax
0x1800d1cac  cmp     eax, 0C00D36D5h
0x1800d1cb1  jnz     loc_1800D1D4C
0x1800d1cb7  lea     rdx, [rsi+50h]
0x1800d1cbb  mov     rax, rsi
0x1800d1cbe  neg     rax
0x1800d1cc1  lea     r8, [rbp+var_18]; struct CMFMediaStream **
0x1800d1cc5  sbb     rcx, rcx
0x1800d1cc8  and     rcx, rdx; struct IByteStreamMediaSource *
0x1800d1ccb  mov     rdx, [rbp+var_10]; struct IMFStreamDescriptor *
0x1800d1ccf  call    ?CreateInstance@CMFMediaStream@@SAJPEAVIByteStreamMediaSource@@PEAUIMFStreamDescriptor@@PEAPEAV1@@Z; CMFMediaStream::CreateInstance(IByteStreamMediaSource *,IMFStreamDescriptor *,CMFMediaStream * *)
0x1800d1cd4  mov     ebx, eax
0x1800d1cd6  test    eax, eax
0x1800d1cd8  js      loc_1800D1DF6
0x1800d1cde  mov     rdi, [rbp+var_18]
0x1800d1ce2  test    rdi, rdi
0x1800d1ce5  jz      short loc_1800D1CED
0x1800d1ce7  lea     r9, [rdi+8]
0x1800d1ceb  jmp     short loc_1800D1CF0
0x1800d1ced  xor     r9d, r9d; struct IUnknown *
0x1800d1cf0  mov     edx, 0CDh; unsigned int
0x1800d1cf5  mov     rcx, rsi; this
0x1800d1cf8  call    ?QueueEventWithIUnknown@CMFByteStreamMediaSource@@AEAAJKJPEAUIUnknown@@@Z; CMFByteStreamMediaSource::QueueEventWithIUnknown(ulong,long,IUnknown *)
0x1800d1cfd  mov     ebx, eax
0x1800d1cff  test    eax, eax
0x1800d1d01  jns     short loc_1800D1D7D
0x1800d1d03  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d1d0a  test    rcx, rcx
0x1800d1d0d  jnz     loc_1800D1DB4
0x1800d1d13  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d1d1a  nop     dword ptr [rax+rax+00h]
0x1800d1d1f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d1d26  mov     rcx, rax
0x1800d1d29  test    rax, rax
0x1800d1d2c  jz      short loc_1800D1DA6
0x1800d1d2e  mov     rax, [rax]
0x1800d1d31  mov     edx, 7F0h
0x1800d1d36  mov     rax, [rax+8]
0x1800d1d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1d3f  test    eax, eax
0x1800d1d41  jz      short loc_1800D1DA6
0x1800d1d43  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d1d4a  jmp     short loc_1800D1DB4
0x1800d1d4c  test    ebx, ebx
0x1800d1d4e  js      loc_1800D1FD8
0x1800d1d54  mov     rdi, [rbp+var_18]
0x1800d1d58  test    rdi, rdi
0x1800d1d5b  jz      short loc_1800D1D63
0x1800d1d5d  lea     r9, [rdi+8]
0x1800d1d61  jmp     short loc_1800D1D66
0x1800d1d63  xor     r9d, r9d; struct IUnknown *
0x1800d1d66  mov     edx, 0CEh; unsigned int
0x1800d1d6b  mov     rcx, rsi; this
0x1800d1d6e  call    ?QueueEventWithIUnknown@CMFByteStreamMediaSource@@AEAAJKJPEAUIUnknown@@@Z; CMFByteStreamMediaSource::QueueEventWithIUnknown(ulong,long,IUnknown *)
0x1800d1d73  mov     ebx, eax
0x1800d1d75  test    eax, eax
0x1800d1d77  js      loc_1800D1F43
0x1800d1d7d  mov     rdx, rdi; struct CMFMediaStream *
0x1800d1d80  mov     rcx, r13; this
0x1800d1d83  call    ?AddStream@CMFMediaStreamArray@@QEAAJPEAVCMFMediaStream@@@Z; CMFMediaStreamArray::AddStream(CMFMediaStream *)
0x1800d1d88  mov     ebx, eax
0x1800d1d8a  test    eax, eax
0x1800d1d8c  js      loc_1800D1EAE
0x1800d1d92  lea     rcx, [rbp+var_10]; void *
0x1800d1d96  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800d1d9b  mov     eax, [rbp+arg_8]
0x1800d1d9e  add     r14d, r15d
0x1800d1da1  jmp     loc_1800D1BB5
0x1800d1da6  lea     rcx, qword_1801B97E0; this
0x1800d1dad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d1db4  cmp     byte ptr [rcx+8], 0
0x1800d1db8  jz      short loc_1800D1DDF
0x1800d1dba  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d1dbf  cmp     [rax+7CCh], ebx
0x1800d1dc5  jz      short loc_1800D1DDF
0x1800d1dc7  mov     r9d, ebx; int
0x1800d1dca  lea     rdx, aCmfbytestreamm_86; "CMFByteStreamMediaSource::CreateStreams"...
0x1800d1dd1  mov     r8d, 0F4Ah; int
0x1800d1dd7  mov     rcx, rax; this
0x1800d1dda  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d1ddf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800d1de6  jb      loc_1800D21A8
0x1800d1dec  mov     edx, 17Dh
0x1800d1df1  jmp     loc_1800D218E
0x1800d1df6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d1dfd  test    rcx, rcx
0x1800d1e00  jnz     short loc_1800D1E49
0x1800d1e02  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d1e09  nop     dword ptr [rax+rax+00h]
0x1800d1e0e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d1e15  mov     rcx, rax
0x1800d1e18  test    rax, rax
0x1800d1e1b  jz      short loc_1800D1E3B
0x1800d1e1d  mov     rax, [rax]
0x1800d1e20  mov     edx, 7F0h
0x1800d1e25  mov     rax, [rax+8]
0x1800d1e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1e2e  test    eax, eax
0x1800d1e30  jz      short loc_1800D1E3B
0x1800d1e32  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d1e39  jmp     short loc_1800D1E49
0x1800d1e3b  lea     rcx, qword_1801B97E0; this
0x1800d1e42  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d1e49  cmp     byte ptr [rcx+8], 0
0x1800d1e4d  jz      short loc_1800D1E74
0x1800d1e4f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d1e54  cmp     [rax+7CCh], ebx
0x1800d1e5a  jz      short loc_1800D1E74
0x1800d1e5c  mov     r9d, ebx; int
0x1800d1e5f  lea     rdx, aCmfbytestreamm_86; "CMFByteStreamMediaSource::CreateStreams"...
0x1800d1e66  mov     r8d, 0F48h; int
0x1800d1e6c  mov     rcx, rax; this
0x1800d1e6f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d1e74  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800d1e7b  jb      short loc_1800D1E9C
0x1800d1e7d  mov     edx, 17Ch
0x1800d1e82  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d1e89  mov     r9, rsi
0x1800d1e8c  mov     r8, r12
0x1800d1e8f  mov     [rsp+48h+var_28], ebx
0x1800d1e93  mov     rcx, [rcx+10h]
0x1800d1e97  call    WPP_SF_qD
0x1800d1e9c  lea     rcx, [rbp+var_10]; void *
0x1800d1ea0  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800d1ea5  mov     rdi, [rbp+var_18]
0x1800d1ea9  jmp     loc_1800D24FC
0x1800d1eae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d1eb5  test    rcx, rcx
0x1800d1eb8  jnz     short loc_1800D1F01
0x1800d1eba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d1ec1  nop     dword ptr [rax+rax+00h]
0x1800d1ec6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d1ecd  mov     rcx, rax
0x1800d1ed0  test    rax, rax
0x1800d1ed3  jz      short loc_1800D1EF3
0x1800d1ed5  mov     rax, [rax]
0x1800d1ed8  mov     edx, 7F0h
0x1800d1edd  mov     rax, [rax+8]
0x1800d1ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1ee6  test    eax, eax
0x1800d1ee8  jz      short loc_1800D1EF3
0x1800d1eea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d1ef1  jmp     short loc_1800D1F01
0x1800d1ef3  lea     rcx, qword_1801B97E0; this
0x1800d1efa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d1f01  cmp     byte ptr [rcx+8], 0
0x1800d1f05  jz      short loc_1800D1F2C
0x1800d1f07  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d1f0c  cmp     [rax+7CCh], ebx
0x1800d1f12  jz      short loc_1800D1F2C
  ... truncated ...
```
