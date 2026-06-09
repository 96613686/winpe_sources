# CAVIIAVSStreamParser::AddSample(IMFSample *)

- ea: `0x18013cf30`
- end: `0x18013da18`
- name: `?AddSample@CAVIIAVSStreamParser@@UEAAJPEAUIMFSample@@@Z`
- size: `2792`
- prototype: `__int64 __fastcall(CAVIIAVSStreamParser *__hidden this, struct IMFSample *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800086c8`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x1800e50b0`
- `0x180138b20`
- `0x18013cf30`
- `0x18013da20`
- `0x18013de00`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013cf9c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d062`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d139`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d22d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d317`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d3fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d4c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d572`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d627`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d6d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d7a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d873`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d93b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013cf9c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d062`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d139`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d22d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d317`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d3fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d4c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d572`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d627`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d6d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d7a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d873`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013d93b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013d9d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013d9e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013d9d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013d9e6`

## pseudocode

```c
__int64 __fastcall CAVIIAVSStreamParser::AddSample(struct DVINFO **this, struct IMFSample *a2)
{
  void *v4; // r15
  __int64 v5; // rdx
  wchar_t *v6; // rcx
  int AudioSampleFromMuxedSample; // ebx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  struct IMFSampleVtbl *lpVtbl; // rax
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  struct IMFSample *v29; // rdx
  CVPtrList *v30; // rdi
  __int64 v31; // rdx
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  struct IMFMediaBuffer *v36; // r8
  __int64 v37; // rdx
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  struct IMFSample *v41; // rdx
  __int64 v42; // rdx
  wchar_t *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rdx
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  struct IMFSample *v50; // rdx
  CVPtrList *v51; // rdi
  __int64 v52; // rdx
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  __int64 v56; // rdx
  wchar_t *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  void *v60; // rdx
  __int64 v61; // rdx
  wchar_t *v62; // rcx
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  __int64 v65; // rdx
  wchar_t *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  __int64 v70; // [rsp+30h] [rbp-20h] BYREF
  struct IMFSample *v71; // [rsp+38h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-10h] BYREF
  struct tWAVEFORMATEX *v73; // [rsp+48h] [rbp-8h] BYREF
  struct IMFMediaBuffer *v74; // [rsp+90h] [rbp+40h] BYREF
  int v75; // [rsp+A0h] [rbp+50h] BYREF
  struct IMFMediaBuffer *v76; // [rsp+A8h] [rbp+58h] BYREF

  v75 = 0;
  v71 = 0;
  pv = 0;
  v73 = 0;
  v4 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v74, "CAVIIAVSStreamParser::AddSample", 162);
  if ( !this[198] )
  {
    v6 = (wchar_t *)CallStackTracing::s_wpInstance;
    AudioSampleFromMuxedSample = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v6 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875854 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIIAVSStreamParser::AddSample", 162, -1072875854);
    }
    if ( g_wppLevels )
    {
      v10 = 24;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
        this,
        AudioSampleFromMuxedSample);
      goto LABEL_170;
    }
    goto LABEL_170;
  }
  AudioSampleFromMuxedSample = ((__int64 (__fastcall *)(struct IMFSample *, int *))a2->lpVtbl->GetBufferCount)(a2, &v75);
  if ( AudioSampleFromMuxedSample >= 0 )
  {
    if ( !v75 || !this[201] && !this[202] )
      goto LABEL_155;
    lpVtbl = a2->lpVtbl;
    v70 = 0;
    v74 = 0;
    v76 = 0;
    AudioSampleFromMuxedSample = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *))lpVtbl->ConvertToContiguousBuffer)(
                                   a2,
                                   &v70);
    if ( AudioSampleFromMuxedSample < 0 )
    {
      v17 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != AudioSampleFromMuxedSample )
          CallStackContext::TraceFailure(v19, "CAVIIAVSStreamParser::AddSample", 172, AudioSampleFromMuxedSample);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
          this,
          AudioSampleFromMuxedSample);
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v76);
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v74);
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v70);
      goto LABEL_170;
    }
    AudioSampleFromMuxedSample = parseIAVSStream(this[198], v70, &v74, &v76, (struct tWAVEFORMATEX **)&pv, &v73);
    if ( AudioSampleFromMuxedSample < 0 )
    {
      v21 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
        if ( *((_DWORD *)v23 + 499) != AudioSampleFromMuxedSample )
          CallStackContext::TraceFailure(v23, "CAVIIAVSStreamParser::AddSample", 185, AudioSampleFromMuxedSample);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
          this,
          AudioSampleFromMuxedSample);
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v76);
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v74);
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v70);
      v4 = pv;
      goto LABEL_166;
    }
    v4 = pv;
    if ( pv )
    {
      AudioSampleFromMuxedSample = CAVIIAVSStreamParser::CreateAudioFormatChange(
                                     (CAVIIAVSStreamParser *)this,
                                     (struct tWAVEFORMATEX *)pv,
                                     &v71);
      if ( AudioSampleFromMuxedSample < 0 )
      {
        v25 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( *((_DWORD *)v27 + 499) != AudioSampleFromMuxedSample )
            CallStackContext::TraceFailure(v27, "CAVIIAVSStreamParser::AddSample", 191, AudioSampleFromMuxedSample);
        }
        if ( !g_wppLevels )
          goto LABEL_64;
        v28 = 28;
        goto LABEL_63;
      }
      v29 = v71;
      v30 = (CVPtrList *)(this + 86);
      v71 = 0;
      if ( !CVPtrList::AddTail((CVPtrList *)(this + 86), v29) )
      {
        v32 = (wchar_t *)CallStackTracing::s_wpInstance;
        AudioSampleFromMuxedSample = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
          CallStackTracing::s_wpInstance = v33;
          if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
          {
            v32 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v32 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v32 + 8) )
        {
          v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
          if ( *((_DWORD *)v34 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v34, "CAVIIAVSStreamParser::AddSample", 192, -2147024882);
        }
        if ( !g_wppLevels )
          goto LABEL_64;
        v35 = 29;
        goto LABEL_76;
      }
    }
    else
    {
      v30 = (CVPtrList *)(this + 86);
    }
    if ( this[201] )
    {
      v36 = v74;
      if ( !v74 )
      {
LABEL_103:
        if ( v73 )
        {
          AudioSampleFromMuxedSample = CAVIIAVSStreamParser::CreateAudioFormatChange(
                                         (CAVIIAVSStreamParser *)this,
                                         v73,
                                         &v71);
          if ( AudioSampleFromMuxedSample < 0 )
          {
            v47 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
              CallStackTracing::s_wpInstance = v48;
              if ( v48
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
              {
                v47 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v47 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v47 + 8) )
            {
              v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
              if ( *((_DWORD *)v49 + 499) != AudioSampleFromMuxedSample )
                CallStackContext::TraceFailure(v49, "CAVIIAVSStreamParser::AddSample", 205, AudioSampleFromMuxedSample);
            }
            if ( !g_wppLevels )
              goto LABEL_64;
            v28 = 32;
LABEL_63:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v28,
              WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
              this,
              AudioSampleFromMuxedSample);
LABEL_64:
            ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v76);
            ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v74);
            ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v70);
LABEL_166:
            if ( v4 )
              CoTaskMemFree(v4);
            if ( v73 )
              CoTaskMemFree(v73);
            goto LABEL_170;
          }
          v50 = v71;
          v51 = (CVPtrList *)(this + 142);
          v71 = 0;
          if ( !CVPtrList::AddTail((CVPtrList *)(this + 142), v50) )
          {
            v53 = (wchar_t *)CallStackTracing::s_wpInstance;
            AudioSampleFromMuxedSample = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52);
              CallStackTracing::s_wpInstance = v54;
              if ( v54
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
              {
                v53 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v53 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v53 + 8) )
            {
              v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
              if ( *((_DWORD *)v55 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v55, "CAVIIAVSStreamParser::AddSample", 206, -2147024882);
            }
            if ( !g_wppLevels )
              goto LABEL_64;
            v35 = 33;
LABEL_76:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v35,
              WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
              this,
              -2147024882);
            goto LABEL_64;
          }
          v36 = v74;
        }
        else
        {
          v51 = (CVPtrList *)(this + 142);
        }
        if ( this[202] && v76 )
        {
          pv = 0;
          AudioSampleFromMuxedSample = CAVIIAVSStreamParser::CreateAudioSampleFromMuxedSample(
                                         (CAVIIAVSStreamParser *)this,
                                         a2,
                                         v36,
                                         (struct IMFSample **)&pv);
          if ( AudioSampleFromMuxedSample < 0 )
          {
            v57 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56);
              CallStackTracing::s_wpInstance = v58;
              if ( v58
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
              {
                v57 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v57 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v57 + 8) )
            {
              v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
              if ( *((_DWORD *)v59 + 499) != AudioSampleFromMuxedSample )
                CallStackContext::TraceFailure(v59, "CAVIIAVSStreamParser::AddSample", 213, AudioSampleFromMuxedSample);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                34,
                WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
                this,
                AudioSampleFromMuxedSample);
LABEL_141:
            ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&pv);
            goto LABEL_64;
          }
          v60 = pv;
          pv = 0;
          if ( !CVPtrList::AddTail(v51, v60) )
          {
            v62 = (wchar_t *)CallStackTracing::s_wpInstance;
            AudioSampleFromMuxedSample = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v61);
              CallStackTracing::s_wpInstance = v63;
              if ( v63
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
              {
                v62 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v62 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v62 + 8) )
            {
              v64 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v62);
              if ( *((_DWORD *)v64 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v64, "CAVIIAVSStreamParser::AddSample", 214, -2147024882);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                35,
                WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
                this,
                -2147024882);
            goto LABEL_141;
          }
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&pv);
        }
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v76);
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v74);
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v70);
LABEL_155:
        AudioSampleFromMuxedSample = CAVIStreamParser::AddSample((CAVIStreamParser *)this, a2);
        if ( AudioSampleFromMuxedSample < 0 )
        {
          v66 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v65);
            CallStackTracing::s_wpInstance = v67;
            if ( v67 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
            {
              v66 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v66 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v66 + 8) )
          {
            v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
            if ( *((_DWORD *)v68 + 499) != AudioSampleFromMuxedSample )
              CallStackContext::TraceFailure(v68, "CAVIIAVSStreamParser::AddSample", 220, AudioSampleFromMuxedSample);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              36,
              WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
              this,
              AudioSampleFromMuxedSample);
        }
        goto LABEL_166;
      }
      AudioSampleFromMuxedSample = CAVIIAVSStreamParser::CreateAudioSampleFromMuxedSample(
                                     (CAVIIAVSStreamParser *)this,
                                     a2,
                                     v74,
                                     &v71);
      if ( AudioSampleFromMuxedSample < 0 )
      {
        v38 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
          CallStackTracing::s_wpInstance = v39;
          if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
          {
            v38 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v38 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v38 + 8) )
        {
          v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
          if ( *((_DWORD *)v40 + 499) != AudioSampleFromMuxedSample )
            CallStackContext::TraceFailure(v40, "CAVIIAVSStreamParser::AddSample", 197, AudioSampleFromMuxedSample);
        }
        if ( !g_wppLevels )
          goto LABEL_64;
        v28 = 30;
        goto LABEL_63;
      }
      v41 = v71;
      v71 = 0;
      if ( !CVPtrList::AddTail(v30, v41) )
      {
        v43 = (wchar_t *)CallStackTracing::s_wpInstance;
        AudioSampleFromMuxedSample = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42);
          CallStackTracing::s_wpInstance = v44;
          if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
          {
            v43 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v43 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v43 + 8) )
        {
          v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
          if ( *((_DWORD *)v45 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v45, "CAVIIAVSStreamParser::AddSample", 198, -2147024882);
        }
        if ( !g_wppLevels )
          goto LABEL_64;
        v35 = 31;
        goto LABEL_76;
      }
    }
    v36 = v74;
    goto LABEL_103;
  }
  v12 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
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
    v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
    if ( *((_DWORD *)v14 + 499) != AudioSampleFromMuxedSample )
      CallStackContext::TraceFailure(v14, "CAVIIAVSStreamParser::AddSample", 164, AudioSampleFromMuxedSample);
  }
  if ( g_wppLevels )
  {
    v10 = 25;
    goto LABEL_12;
  }
LABEL_170:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v74);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v71);
  return (unsigned int)AudioSampleFromMuxedSample;
}

```

## disassembly

```asm
0x18013cf30  mov     [rsp-38h+arg_8], rbx
0x18013cf35  push    rbp
0x18013cf36  push    rsi
0x18013cf37  push    rdi
0x18013cf38  push    r12
0x18013cf3a  push    r13
0x18013cf3c  push    r14
0x18013cf3e  push    r15
0x18013cf40  mov     rbp, rsp
0x18013cf43  sub     rsp, 50h
0x18013cf47  xor     r12d, r12d
0x18013cf4a  lea     r13, aCaviiavsstream_0; "CAVIIAVSStreamParser::AddSample"
0x18013cf51  mov     r14, rdx
0x18013cf54  mov     [rbp+arg_10], r12d
0x18013cf58  mov     rsi, rcx
0x18013cf5b  mov     [rbp+var_18], r12
0x18013cf5f  mov     edi, 0A2h
0x18013cf64  mov     [rbp+pv], r12
0x18013cf68  mov     r8d, edi; int
0x18013cf6b  mov     [rbp+var_8], r12
0x18013cf6f  mov     rdx, r13; char *
0x18013cf72  lea     rcx, [rbp+arg_0]; this
0x18013cf76  mov     r15d, r12d
0x18013cf79  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18013cf7e  cmp     [rsi+630h], r12
0x18013cf85  jnz     loc_18013D036
0x18013cf8b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013cf92  mov     ebx, 0C00D36B2h
0x18013cf97  test    rcx, rcx
0x18013cf9a  jnz     short loc_18013CFDD
0x18013cf9c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013cfa2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013cfa9  mov     rcx, rax
0x18013cfac  test    rax, rax
0x18013cfaf  jz      short loc_18013CFCF
0x18013cfb1  mov     rax, [rax]
0x18013cfb4  mov     edx, 7F0h
0x18013cfb9  mov     rax, [rax+8]
0x18013cfbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013cfc2  test    eax, eax
0x18013cfc4  jz      short loc_18013CFCF
0x18013cfc6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013cfcd  jmp     short loc_18013CFDD
0x18013cfcf  lea     rcx, qword_1801B07E0; this
0x18013cfd6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013cfdd  cmp     [rcx+8], r12b
0x18013cfe1  jz      short loc_18013D001
0x18013cfe3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013cfe8  cmp     [rax+7CCh], ebx
0x18013cfee  jz      short loc_18013D001
0x18013cff0  mov     r9d, ebx; int
0x18013cff3  mov     r8d, edi; int
0x18013cff6  mov     rdx, r13; char *
0x18013cff9  mov     rcx, rax; this
0x18013cffc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013d001  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013d008  jb      loc_18013D9EC
0x18013d00e  mov     edx, 18h
0x18013d013  mov     rcx, cs:WPP_GLOBAL_Control
0x18013d01a  lea     r8, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids
0x18013d021  mov     r9, rsi
0x18013d024  mov     dword ptr [rsp+50h+var_30], ebx
0x18013d028  mov     rcx, [rcx+10h]
0x18013d02c  call    WPP_SF_qD
0x18013d031  jmp     loc_18013D9EC
0x18013d036  mov     rax, [r14]
0x18013d039  lea     rdx, [rbp+arg_10]
0x18013d03d  mov     rcx, r14
0x18013d040  mov     rax, [rax+138h]
0x18013d047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d04c  mov     ebx, eax
0x18013d04e  test    eax, eax
0x18013d050  jns     loc_18013D0E1
0x18013d056  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013d05d  test    rcx, rcx
0x18013d060  jnz     short loc_18013D0A3
0x18013d062  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013d068  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013d06f  mov     rcx, rax
0x18013d072  test    rax, rax
0x18013d075  jz      short loc_18013D095
0x18013d077  mov     rax, [rax]
0x18013d07a  mov     edx, 7F0h
0x18013d07f  mov     rax, [rax+8]
0x18013d083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d088  test    eax, eax
0x18013d08a  jz      short loc_18013D095
0x18013d08c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013d093  jmp     short loc_18013D0A3
0x18013d095  lea     rcx, qword_1801B07E0; this
0x18013d09c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013d0a3  cmp     [rcx+8], r12b
0x18013d0a7  jz      short loc_18013D0CA
0x18013d0a9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013d0ae  cmp     [rax+7CCh], ebx
0x18013d0b4  jz      short loc_18013D0CA
0x18013d0b6  mov     r9d, ebx; int
0x18013d0b9  mov     r8d, 0A4h; int
0x18013d0bf  mov     rdx, r13; char *
0x18013d0c2  mov     rcx, rax; this
0x18013d0c5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013d0ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013d0d1  jb      loc_18013D9EC
0x18013d0d7  mov     edx, 19h
0x18013d0dc  jmp     loc_18013D013
0x18013d0e1  cmp     [rbp+arg_10], r12d
0x18013d0e5  jbe     loc_18013D91A
0x18013d0eb  cmp     [rsi+648h], r12
0x18013d0f2  jnz     short loc_18013D101
0x18013d0f4  cmp     [rsi+650h], r12
0x18013d0fb  jz      loc_18013D91A
0x18013d101  mov     rax, [r14]
0x18013d104  lea     rdx, [rbp+var_20]
0x18013d108  mov     rcx, r14
0x18013d10b  mov     [rbp+var_20], r12
0x18013d10f  mov     [rbp+arg_0], r12
0x18013d113  mov     [rbp+arg_18], r12
0x18013d117  mov     rax, [rax+148h]
0x18013d11e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d123  mov     ebx, eax
0x18013d125  test    eax, eax
0x18013d127  jns     loc_18013D1ED
0x18013d12d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013d134  test    rcx, rcx
0x18013d137  jnz     short loc_18013D17A
0x18013d139  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013d13f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013d146  mov     rcx, rax
0x18013d149  test    rax, rax
0x18013d14c  jz      short loc_18013D16C
0x18013d14e  mov     rax, [rax]
0x18013d151  mov     edx, 7F0h
0x18013d156  mov     rax, [rax+8]
0x18013d15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d15f  test    eax, eax
0x18013d161  jz      short loc_18013D16C
0x18013d163  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013d16a  jmp     short loc_18013D17A
0x18013d16c  lea     rcx, qword_1801B07E0; this
0x18013d173  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013d17a  cmp     [rcx+8], r12b
0x18013d17e  jz      short loc_18013D1A1
0x18013d180  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013d185  cmp     [rax+7CCh], ebx
0x18013d18b  jz      short loc_18013D1A1
0x18013d18d  mov     r9d, ebx; int
0x18013d190  mov     r8d, 0ACh; int
0x18013d196  mov     rdx, r13; char *
0x18013d199  mov     rcx, rax; this
0x18013d19c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013d1a1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013d1a8  jb      short loc_18013D1CD
0x18013d1aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18013d1b1  lea     r8, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids
0x18013d1b8  mov     edx, 1Ah
0x18013d1bd  mov     dword ptr [rsp+50h+var_30], ebx
0x18013d1c1  mov     r9, rsi
0x18013d1c4  mov     rcx, [rcx+10h]
0x18013d1c8  call    WPP_SF_qD
0x18013d1cd  lea     rcx, [rbp+arg_18]; void *
0x18013d1d1  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18013d1d6  lea     rcx, [rbp+arg_0]; void *
0x18013d1da  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18013d1df  lea     rcx, [rbp+var_20]; void *
0x18013d1e3  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18013d1e8  jmp     loc_18013D9EC
0x18013d1ed  mov     rdx, [rbp+var_20]
0x18013d1f1  lea     rax, [rbp+var_8]
0x18013d1f5  mov     rcx, [rsi+630h]; struct DVINFO *
0x18013d1fc  lea     r9, [rbp+arg_18]
0x18013d200  mov     [rsp+50h+var_28], rax; struct tWAVEFORMATEX **
0x18013d205  lea     r8, [rbp+arg_0]
0x18013d209  lea     rax, [rbp+pv]
0x18013d20d  mov     [rsp+50h+var_30], rax; struct tWAVEFORMATEX **
0x18013d212  call    parseIAVSStream
0x18013d217  mov     ebx, eax
0x18013d219  test    eax, eax
0x18013d21b  jns     loc_18013D2E5
0x18013d221  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013d228  test    rcx, rcx
0x18013d22b  jnz     short loc_18013D26E
0x18013d22d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013d233  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013d23a  mov     rcx, rax
0x18013d23d  test    rax, rax
0x18013d240  jz      short loc_18013D260
0x18013d242  mov     rax, [rax]
0x18013d245  mov     edx, 7F0h
0x18013d24a  mov     rax, [rax+8]
0x18013d24e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d253  test    eax, eax
0x18013d255  jz      short loc_18013D260
0x18013d257  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013d25e  jmp     short loc_18013D26E
0x18013d260  lea     rcx, qword_1801B07E0; this
0x18013d267  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013d26e  cmp     [rcx+8], r12b
0x18013d272  jz      short loc_18013D295
0x18013d274  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013d279  cmp     [rax+7CCh], ebx
0x18013d27f  jz      short loc_18013D295
0x18013d281  mov     r9d, ebx; int
0x18013d284  mov     r8d, 0B9h; int
0x18013d28a  mov     rdx, r13; char *
0x18013d28d  mov     rcx, rax; this
0x18013d290  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013d295  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013d29c  jb      short loc_18013D2C1
0x18013d29e  mov     rcx, cs:WPP_GLOBAL_Control
0x18013d2a5  lea     r8, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids
0x18013d2ac  mov     edx, 1Bh
0x18013d2b1  mov     dword ptr [rsp+50h+var_30], ebx
0x18013d2b5  mov     r9, rsi
0x18013d2b8  mov     rcx, [rcx+10h]
0x18013d2bc  call    WPP_SF_qD
0x18013d2c1  lea     rcx, [rbp+arg_18]; void *
0x18013d2c5  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18013d2ca  lea     rcx, [rbp+arg_0]; void *
0x18013d2ce  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18013d2d3  lea     rcx, [rbp+var_20]; void *
0x18013d2d7  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18013d2dc  mov     r15, [rbp+pv]
0x18013d2e0  jmp     loc_18013D9CF
0x18013d2e5  mov     r15, [rbp+pv]
0x18013d2e9  test    r15, r15
0x18013d2ec  jz      loc_18013D481
0x18013d2f2  lea     r8, [rbp+var_18]; struct IMFSample **
0x18013d2f6  mov     rdx, r15; struct tWAVEFORMATEX *
0x18013d2f9  mov     rcx, rsi; this
0x18013d2fc  call    ?CreateAudioFormatChange@CAVIIAVSStreamParser@@AEAAJPEAUtWAVEFORMATEX@@PEAPEAUIMFSample@@@Z; CAVIIAVSStreamParser::CreateAudioFormatChange(tWAVEFORMATEX *,IMFSample * *)
0x18013d301  mov     ebx, eax
0x18013d303  test    eax, eax
0x18013d305  jns     loc_18013D3CB
0x18013d30b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013d312  test    rcx, rcx
0x18013d315  jnz     short loc_18013D358
0x18013d317  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013d31d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013d324  mov     rcx, rax
0x18013d327  test    rax, rax
0x18013d32a  jz      short loc_18013D34A
0x18013d32c  mov     rax, [rax]
0x18013d32f  mov     edx, 7F0h
0x18013d334  mov     rax, [rax+8]
0x18013d338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d33d  test    eax, eax
0x18013d33f  jz      short loc_18013D34A
0x18013d341  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013d348  jmp     short loc_18013D358
0x18013d34a  lea     rcx, qword_1801B07E0; this
0x18013d351  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013d358  cmp     [rcx+8], r12b
0x18013d35c  jz      short loc_18013D37F
0x18013d35e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013d363  cmp     [rax+7CCh], ebx
0x18013d369  jz      short loc_18013D37F
0x18013d36b  mov     r9d, ebx; int
0x18013d36e  mov     r8d, 0BFh; int
0x18013d374  mov     rdx, r13; char *
0x18013d377  mov     rcx, rax; this
0x18013d37a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013d37f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013d386  jb      short loc_18013D3AB
0x18013d388  mov     edx, 1Ch
0x18013d38d  mov     dword ptr [rsp+50h+var_30], ebx
0x18013d391  mov     rcx, cs:WPP_GLOBAL_Control
0x18013d398  lea     r8, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids
0x18013d39f  mov     r9, rsi
0x18013d3a2  mov     rcx, [rcx+10h]
0x18013d3a6  call    WPP_SF_qD
0x18013d3ab  lea     rcx, [rbp+arg_18]; void *
0x18013d3af  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18013d3b4  lea     rcx, [rbp+arg_0]; void *
0x18013d3b8  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18013d3bd  lea     rcx, [rbp+var_20]; void *
0x18013d3c1  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18013d3c6  jmp     loc_18013D9CF
0x18013d3cb  mov     rdx, [rbp+var_18]; void *
0x18013d3cf  lea     rdi, [rsi+2B0h]
0x18013d3d6  mov     rcx, rdi; this
0x18013d3d9  mov     [rbp+var_18], r12
0x18013d3dd  call    ?AddTail@CVPtrList@@QEAAPEAXPEAX@Z; CVPtrList::AddTail(void *)
0x18013d3e2  test    rax, rax
0x18013d3e5  jnz     loc_18013D488
0x18013d3eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013d3f2  mov     edi, 8007000Eh
0x18013d3f7  mov     ebx, edi
0x18013d3f9  test    rcx, rcx
0x18013d3fc  jnz     short loc_18013D43F
0x18013d3fe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013d404  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013d40b  mov     rcx, rax
0x18013d40e  test    rax, rax
0x18013d411  jz      short loc_18013D431
0x18013d413  mov     rax, [rax]
0x18013d416  mov     edx, 7F0h
0x18013d41b  mov     rax, [rax+8]
0x18013d41f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d424  test    eax, eax
0x18013d426  jz      short loc_18013D431
  ... truncated ...
```
