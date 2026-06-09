# CAVIIAVSStreamParser::AddSample(IMFSample *)

- ea: `0x18013cf30`
- end: `0x18013da18`
- name: `?AddSample@CAVIIAVSStreamParser@@UEAAJPEAUIMFSample@@@Z`
- size: `2792`
- prototype: `__int64 __fastcall(struct DVINFO **this, struct IMFSample *)`
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
  __int64 v6; // r8
  __int64 v7; // r9
  wchar_t *v8; // rcx
  int AudioSampleFromMuxedSample; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  struct IMFSampleVtbl *lpVtbl; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  wchar_t *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  struct IMFSample *v39; // rdx
  CVPtrList *v40; // rdi
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
  struct IMFMediaBuffer *v48; // r8
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r9
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  struct IMFSample *v55; // rdx
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r9
  wchar_t *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // r9
  wchar_t *v65; // rcx
  CallStackTracing *v66; // rax
  struct CallStackContext *v67; // rax
  struct IMFSample *v68; // rdx
  CVPtrList *v69; // rdi
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // r9
  wchar_t *v73; // rcx
  CallStackTracing *v74; // rax
  struct CallStackContext *v75; // rax
  __int64 v76; // rdx
  __int64 v77; // r8
  __int64 v78; // r9
  wchar_t *v79; // rcx
  CallStackTracing *v80; // rax
  struct CallStackContext *v81; // rax
  void *v82; // rdx
  __int64 v83; // rdx
  __int64 v84; // r8
  __int64 v85; // r9
  wchar_t *v86; // rcx
  CallStackTracing *v87; // rax
  struct CallStackContext *v88; // rax
  __int64 v89; // rdx
  __int64 v90; // r8
  __int64 v91; // r9
  wchar_t *v92; // rcx
  CallStackTracing *v93; // rax
  struct CallStackContext *v94; // rax
  __int64 v96; // [rsp+30h] [rbp-20h] BYREF
  struct IMFSample *v97; // [rsp+38h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-10h] BYREF
  struct tWAVEFORMATEX *v99; // [rsp+48h] [rbp-8h] BYREF
  struct IMFMediaBuffer *v100; // [rsp+90h] [rbp+40h] BYREF
  int v101; // [rsp+A0h] [rbp+50h] BYREF
  struct IMFMediaBuffer *v102; // [rsp+A8h] [rbp+58h] BYREF

  v101 = 0;
  v97 = 0;
  pv = 0;
  v99 = 0;
  v4 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v100, "CAVIIAVSStreamParser::AddSample", 162);
  if ( !this[198] )
  {
    v8 = (wchar_t *)CallStackTracing::s_wpInstance;
    AudioSampleFromMuxedSample = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v6, v7);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v8 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875854 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIIAVSStreamParser::AddSample", 162, -1072875854);
    }
    if ( g_wppLevels )
    {
      v12 = 24;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
        this,
        AudioSampleFromMuxedSample);
      goto LABEL_170;
    }
    goto LABEL_170;
  }
  AudioSampleFromMuxedSample = ((__int64 (__fastcall *)(struct IMFSample *, int *))a2->lpVtbl->GetBufferCount)(
                                 a2,
                                 &v101);
  if ( AudioSampleFromMuxedSample >= 0 )
  {
    if ( !v101 || !this[201] && !this[202] )
      goto LABEL_155;
    lpVtbl = a2->lpVtbl;
    v96 = 0;
    v100 = 0;
    v102 = 0;
    AudioSampleFromMuxedSample = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *))lpVtbl->ConvertToContiguousBuffer)(
                                   a2,
                                   &v96);
    if ( AudioSampleFromMuxedSample < 0 )
    {
      v23 = (wchar_t *)CallStackTracing::s_wpInstance;
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
        if ( *((_DWORD *)v25 + 499) != AudioSampleFromMuxedSample )
          CallStackContext::TraceFailure(v25, "CAVIIAVSStreamParser::AddSample", 172, AudioSampleFromMuxedSample);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          &WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
          this,
          AudioSampleFromMuxedSample);
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v102);
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v100);
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v96);
      goto LABEL_170;
    }
    AudioSampleFromMuxedSample = parseIAVSStream(this[198], v96, &v100, &v102, (struct tWAVEFORMATEX **)&pv, &v99);
    if ( AudioSampleFromMuxedSample < 0 )
    {
      v29 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
        CallStackTracing::s_wpInstance = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
        if ( *((_DWORD *)v31 + 499) != AudioSampleFromMuxedSample )
          CallStackContext::TraceFailure(v31, "CAVIIAVSStreamParser::AddSample", 185, AudioSampleFromMuxedSample);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          &WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
          this,
          AudioSampleFromMuxedSample);
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v102);
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v100);
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v96);
      v4 = pv;
      goto LABEL_166;
    }
    v4 = pv;
    if ( pv )
    {
      AudioSampleFromMuxedSample = CAVIIAVSStreamParser::CreateAudioFormatChange(
                                     (CAVIIAVSStreamParser *)this,
                                     (struct tWAVEFORMATEX *)pv,
                                     &v97);
      if ( AudioSampleFromMuxedSample < 0 )
      {
        v35 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
          CallStackTracing::s_wpInstance = v36;
          if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
          {
            v35 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v35 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v35 + 8) )
        {
          v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
          if ( *((_DWORD *)v37 + 499) != AudioSampleFromMuxedSample )
            CallStackContext::TraceFailure(v37, "CAVIIAVSStreamParser::AddSample", 191, AudioSampleFromMuxedSample);
        }
        if ( !g_wppLevels )
          goto LABEL_64;
        v38 = 28;
        goto LABEL_63;
      }
      v39 = v97;
      v40 = (CVPtrList *)(this + 86);
      v97 = 0;
      if ( !CVPtrList::AddTail((CVPtrList *)(this + 86), v39) )
      {
        v44 = (wchar_t *)CallStackTracing::s_wpInstance;
        AudioSampleFromMuxedSample = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42, v43);
          CallStackTracing::s_wpInstance = v45;
          if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
          {
            v44 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v44 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v44 + 8) )
        {
          v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
          if ( *((_DWORD *)v46 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v46, "CAVIIAVSStreamParser::AddSample", 192, -2147024882);
        }
        if ( !g_wppLevels )
          goto LABEL_64;
        v47 = 29;
        goto LABEL_76;
      }
    }
    else
    {
      v40 = (CVPtrList *)(this + 86);
    }
    if ( this[201] )
    {
      v48 = v100;
      if ( !v100 )
      {
LABEL_103:
        if ( v99 )
        {
          AudioSampleFromMuxedSample = CAVIIAVSStreamParser::CreateAudioFormatChange(
                                         (CAVIIAVSStreamParser *)this,
                                         v99,
                                         &v97);
          if ( AudioSampleFromMuxedSample < 0 )
          {
            v65 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62, v63, v64);
              CallStackTracing::s_wpInstance = v66;
              if ( v66
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v66 + 8LL))(v66, 2032) )
              {
                v65 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v65 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v65 + 8) )
            {
              v67 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v65);
              if ( *((_DWORD *)v67 + 499) != AudioSampleFromMuxedSample )
                CallStackContext::TraceFailure(v67, "CAVIIAVSStreamParser::AddSample", 205, AudioSampleFromMuxedSample);
            }
            if ( !g_wppLevels )
              goto LABEL_64;
            v38 = 32;
LABEL_63:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v38,
              &WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
              this,
              AudioSampleFromMuxedSample);
LABEL_64:
            ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v102);
            ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v100);
            ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v96);
LABEL_166:
            if ( v4 )
              CoTaskMemFree(v4);
            if ( v99 )
              CoTaskMemFree(v99);
            goto LABEL_170;
          }
          v68 = v97;
          v69 = (CVPtrList *)(this + 142);
          v97 = 0;
          if ( !CVPtrList::AddTail((CVPtrList *)(this + 142), v68) )
          {
            v73 = (wchar_t *)CallStackTracing::s_wpInstance;
            AudioSampleFromMuxedSample = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v70, v71, v72);
              CallStackTracing::s_wpInstance = v74;
              if ( v74
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(v74, 2032) )
              {
                v73 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v73 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v73 + 8) )
            {
              v75 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v73);
              if ( *((_DWORD *)v75 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v75, "CAVIIAVSStreamParser::AddSample", 206, -2147024882);
            }
            if ( !g_wppLevels )
              goto LABEL_64;
            v47 = 33;
LABEL_76:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v47,
              &WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
              this,
              -2147024882);
            goto LABEL_64;
          }
          v48 = v100;
        }
        else
        {
          v69 = (CVPtrList *)(this + 142);
        }
        if ( this[202] && v102 )
        {
          pv = 0;
          AudioSampleFromMuxedSample = CAVIIAVSStreamParser::CreateAudioSampleFromMuxedSample(
                                         (CAVIIAVSStreamParser *)this,
                                         a2,
                                         v48,
                                         (struct IMFSample **)&pv);
          if ( AudioSampleFromMuxedSample < 0 )
          {
            v79 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v80 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v76, v77, v78);
              CallStackTracing::s_wpInstance = v80;
              if ( v80
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v80 + 8LL))(v80, 2032) )
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
              if ( *((_DWORD *)v81 + 499) != AudioSampleFromMuxedSample )
                CallStackContext::TraceFailure(v81, "CAVIIAVSStreamParser::AddSample", 213, AudioSampleFromMuxedSample);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                34,
                &WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
                this,
                AudioSampleFromMuxedSample);
LABEL_141:
            ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&pv);
            goto LABEL_64;
          }
          v82 = pv;
          pv = 0;
          if ( !CVPtrList::AddTail(v69, v82) )
          {
            v86 = (wchar_t *)CallStackTracing::s_wpInstance;
            AudioSampleFromMuxedSample = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              v87 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v83, v84, v85);
              CallStackTracing::s_wpInstance = v87;
              if ( v87
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v87 + 8LL))(v87, 2032) )
              {
                v86 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v86 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v86 + 8) )
            {
              v88 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v86);
              if ( *((_DWORD *)v88 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v88, "CAVIIAVSStreamParser::AddSample", 214, -2147024882);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                35,
                &WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
                this,
                -2147024882);
            goto LABEL_141;
          }
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&pv);
        }
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v102);
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v100);
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v96);
LABEL_155:
        AudioSampleFromMuxedSample = CAVIStreamParser::AddSample((CAVIStreamParser *)this, a2);
        if ( AudioSampleFromMuxedSample < 0 )
        {
          v92 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v93 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v89, v90, v91);
            CallStackTracing::s_wpInstance = v93;
            if ( v93 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v93 + 8LL))(v93, 2032) )
            {
              v92 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v92 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v92 + 8) )
          {
            v94 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v92);
            if ( *((_DWORD *)v94 + 499) != AudioSampleFromMuxedSample )
              CallStackContext::TraceFailure(v94, "CAVIIAVSStreamParser::AddSample", 220, AudioSampleFromMuxedSample);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              36,
              &WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids,
              this,
              AudioSampleFromMuxedSample);
        }
        goto LABEL_166;
      }
      AudioSampleFromMuxedSample = CAVIIAVSStreamParser::CreateAudioSampleFromMuxedSample(
                                     (CAVIIAVSStreamParser *)this,
                                     a2,
                                     v100,
                                     &v97);
      if ( AudioSampleFromMuxedSample < 0 )
      {
        v52 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49, v50, v51);
          CallStackTracing::s_wpInstance = v53;
          if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
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
          if ( *((_DWORD *)v54 + 499) != AudioSampleFromMuxedSample )
            CallStackContext::TraceFailure(v54, "CAVIIAVSStreamParser::AddSample", 197, AudioSampleFromMuxedSample);
        }
        if ( !g_wppLevels )
          goto LABEL_64;
        v38 = 30;
        goto LABEL_63;
      }
      v55 = v97;
      v97 = 0;
      if ( !CVPtrList::AddTail(v40, v55) )
      {
        v59 = (wchar_t *)CallStackTracing::s_wpInstance;
        AudioSampleFromMuxedSample = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56, v57, v58);
          CallStackTracing::s_wpInstance = v60;
          if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
          {
            v59 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v59 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v59 + 8) )
        {
          v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
          if ( *((_DWORD *)v61 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v61, "CAVIIAVSStreamParser::AddSample", 198, -2147024882);
        }
        if ( !g_wppLevels )
          goto LABEL_64;
        v47 = 31;
        goto LABEL_76;
      }
    }
    v48 = v100;
    goto LABEL_103;
  }
  v16 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
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
    v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
    if ( *((_DWORD *)v18 + 499) != AudioSampleFromMuxedSample )
      CallStackContext::TraceFailure(v18, "CAVIIAVSStreamParser::AddSample", 164, AudioSampleFromMuxedSample);
  }
  if ( g_wppLevels )
  {
    v12 = 25;
    goto LABEL_12;
  }
LABEL_170:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v100);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v97);
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
