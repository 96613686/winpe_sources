# CAVIIAVSStreamParser::AddSample(IMFSample *)

- ea: `0x180144a80`
- end: `0x1801455c3`
- name: `?AddSample@CAVIIAVSStreamParser@@UEAAJPEAUIMFSample@@@Z`
- size: `2883`
- prototype: `__int64 __fastcall(CAVIIAVSStreamParser *__hidden this, struct IMFSample *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x18003b238`
- `0x180079680`
- `0x1800eb9d4`
- `0x180140420`
- `0x180144a80`
- `0x1801455cc`
- `0x1801459e0`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144aec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144bb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144c95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144d8f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144e7f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144f6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014503b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801450ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801451a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014525f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145331`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145405`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801454d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144aec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144bb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144c95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144d8f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144e7f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144f6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014503b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801450ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801451a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014525f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145331`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145405`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801454d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180145575`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014558a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180145575`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014558a`

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
        v6 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v17 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v21 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v25 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v32 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v47 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v53 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v57 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v62 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v66 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v38 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v43 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v12 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x180144a80  mov     [rsp-38h+arg_8], rbx
0x180144a85  push    rbp
0x180144a86  push    rsi
0x180144a87  push    rdi
0x180144a88  push    r12
0x180144a8a  push    r13
0x180144a8c  push    r14
0x180144a8e  push    r15
0x180144a90  mov     rbp, rsp
0x180144a93  sub     rsp, 50h
0x180144a97  xor     r12d, r12d
0x180144a9a  lea     r13, aCaviiavsstream_0; "CAVIIAVSStreamParser::AddSample"
0x180144aa1  mov     r14, rdx
0x180144aa4  mov     [rbp+arg_10], r12d
0x180144aa8  mov     rsi, rcx
0x180144aab  mov     [rbp+var_18], r12
0x180144aaf  mov     edi, 0A2h
0x180144ab4  mov     [rbp+pv], r12
0x180144ab8  mov     r8d, edi; int
0x180144abb  mov     [rbp+var_8], r12
0x180144abf  mov     rdx, r13; char *
0x180144ac2  lea     rcx, [rbp+arg_0]; this
0x180144ac6  mov     r15d, r12d
0x180144ac9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180144ace  cmp     [rsi+630h], r12
0x180144ad5  jnz     loc_180144B8C
0x180144adb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180144ae2  mov     ebx, 0C00D36B2h
0x180144ae7  test    rcx, rcx
0x180144aea  jnz     short loc_180144B33
0x180144aec  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180144af3  nop     dword ptr [rax+rax+00h]
0x180144af8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180144aff  mov     rcx, rax
0x180144b02  test    rax, rax
0x180144b05  jz      short loc_180144B25
0x180144b07  mov     rax, [rax]
0x180144b0a  mov     edx, 7F0h
0x180144b0f  mov     rax, [rax+8]
0x180144b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144b18  test    eax, eax
0x180144b1a  jz      short loc_180144B25
0x180144b1c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180144b23  jmp     short loc_180144B33
0x180144b25  lea     rcx, qword_1801B97E0; this
0x180144b2c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180144b33  cmp     [rcx+8], r12b
0x180144b37  jz      short loc_180144B57
0x180144b39  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180144b3e  cmp     [rax+7CCh], ebx
0x180144b44  jz      short loc_180144B57
0x180144b46  mov     r9d, ebx; int
0x180144b49  mov     r8d, edi; int
0x180144b4c  mov     rdx, r13; char *
0x180144b4f  mov     rcx, rax; this
0x180144b52  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180144b57  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180144b5e  jb      loc_180145596
0x180144b64  mov     edx, 18h
0x180144b69  mov     rcx, cs:WPP_GLOBAL_Control
0x180144b70  lea     r8, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids
0x180144b77  mov     r9, rsi
0x180144b7a  mov     dword ptr [rsp+50h+var_30], ebx
0x180144b7e  mov     rcx, [rcx+10h]
0x180144b82  call    WPP_SF_qD
0x180144b87  jmp     loc_180145596
0x180144b8c  mov     rax, [r14]
0x180144b8f  lea     rdx, [rbp+arg_10]
0x180144b93  mov     rcx, r14
0x180144b96  mov     rax, [rax+138h]
0x180144b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144ba2  mov     ebx, eax
0x180144ba4  test    eax, eax
0x180144ba6  jns     loc_180144C3D
0x180144bac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180144bb3  test    rcx, rcx
0x180144bb6  jnz     short loc_180144BFF
0x180144bb8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180144bbf  nop     dword ptr [rax+rax+00h]
0x180144bc4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180144bcb  mov     rcx, rax
0x180144bce  test    rax, rax
0x180144bd1  jz      short loc_180144BF1
0x180144bd3  mov     rax, [rax]
0x180144bd6  mov     edx, 7F0h
0x180144bdb  mov     rax, [rax+8]
0x180144bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144be4  test    eax, eax
0x180144be6  jz      short loc_180144BF1
0x180144be8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180144bef  jmp     short loc_180144BFF
0x180144bf1  lea     rcx, qword_1801B97E0; this
0x180144bf8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180144bff  cmp     [rcx+8], r12b
0x180144c03  jz      short loc_180144C26
0x180144c05  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180144c0a  cmp     [rax+7CCh], ebx
0x180144c10  jz      short loc_180144C26
0x180144c12  mov     r9d, ebx; int
0x180144c15  mov     r8d, 0A4h; int
0x180144c1b  mov     rdx, r13; char *
0x180144c1e  mov     rcx, rax; this
0x180144c21  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180144c26  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180144c2d  jb      loc_180145596
0x180144c33  mov     edx, 19h
0x180144c38  jmp     loc_180144B69
0x180144c3d  cmp     [rbp+arg_10], r12d
0x180144c41  jbe     loc_1801454B2
0x180144c47  cmp     [rsi+648h], r12
0x180144c4e  jnz     short loc_180144C5D
0x180144c50  cmp     [rsi+650h], r12
0x180144c57  jz      loc_1801454B2
0x180144c5d  mov     rax, [r14]
0x180144c60  lea     rdx, [rbp+var_20]
0x180144c64  mov     rcx, r14
0x180144c67  mov     [rbp+var_20], r12
0x180144c6b  mov     [rbp+arg_0], r12
0x180144c6f  mov     [rbp+arg_18], r12
0x180144c73  mov     rax, [rax+148h]
0x180144c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144c7f  mov     ebx, eax
0x180144c81  test    eax, eax
0x180144c83  jns     loc_180144D4F
0x180144c89  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180144c90  test    rcx, rcx
0x180144c93  jnz     short loc_180144CDC
0x180144c95  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180144c9c  nop     dword ptr [rax+rax+00h]
0x180144ca1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180144ca8  mov     rcx, rax
0x180144cab  test    rax, rax
0x180144cae  jz      short loc_180144CCE
0x180144cb0  mov     rax, [rax]
0x180144cb3  mov     edx, 7F0h
0x180144cb8  mov     rax, [rax+8]
0x180144cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144cc1  test    eax, eax
0x180144cc3  jz      short loc_180144CCE
0x180144cc5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180144ccc  jmp     short loc_180144CDC
0x180144cce  lea     rcx, qword_1801B97E0; this
0x180144cd5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180144cdc  cmp     [rcx+8], r12b
0x180144ce0  jz      short loc_180144D03
0x180144ce2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180144ce7  cmp     [rax+7CCh], ebx
0x180144ced  jz      short loc_180144D03
0x180144cef  mov     r9d, ebx; int
0x180144cf2  mov     r8d, 0ACh; int
0x180144cf8  mov     rdx, r13; char *
0x180144cfb  mov     rcx, rax; this
0x180144cfe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180144d03  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180144d0a  jb      short loc_180144D2F
0x180144d0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180144d13  lea     r8, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids
0x180144d1a  mov     edx, 1Ah
0x180144d1f  mov     dword ptr [rsp+50h+var_30], ebx
0x180144d23  mov     r9, rsi
0x180144d26  mov     rcx, [rcx+10h]
0x180144d2a  call    WPP_SF_qD
0x180144d2f  lea     rcx, [rbp+arg_18]; void *
0x180144d33  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180144d38  lea     rcx, [rbp+arg_0]; void *
0x180144d3c  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180144d41  lea     rcx, [rbp+var_20]; void *
0x180144d45  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180144d4a  jmp     loc_180145596
0x180144d4f  mov     rdx, [rbp+var_20]
0x180144d53  lea     rax, [rbp+var_8]
0x180144d57  mov     rcx, [rsi+630h]; struct DVINFO *
0x180144d5e  lea     r9, [rbp+arg_18]
0x180144d62  mov     [rsp+50h+var_28], rax; struct tWAVEFORMATEX **
0x180144d67  lea     r8, [rbp+arg_0]
0x180144d6b  lea     rax, [rbp+pv]
0x180144d6f  mov     [rsp+50h+var_30], rax; struct tWAVEFORMATEX **
0x180144d74  call    parseIAVSStream
0x180144d79  mov     ebx, eax
0x180144d7b  test    eax, eax
0x180144d7d  jns     loc_180144E4D
0x180144d83  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180144d8a  test    rcx, rcx
0x180144d8d  jnz     short loc_180144DD6
0x180144d8f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180144d96  nop     dword ptr [rax+rax+00h]
0x180144d9b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180144da2  mov     rcx, rax
0x180144da5  test    rax, rax
0x180144da8  jz      short loc_180144DC8
0x180144daa  mov     rax, [rax]
0x180144dad  mov     edx, 7F0h
0x180144db2  mov     rax, [rax+8]
0x180144db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144dbb  test    eax, eax
0x180144dbd  jz      short loc_180144DC8
0x180144dbf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180144dc6  jmp     short loc_180144DD6
0x180144dc8  lea     rcx, qword_1801B97E0; this
0x180144dcf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180144dd6  cmp     [rcx+8], r12b
0x180144dda  jz      short loc_180144DFD
0x180144ddc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180144de1  cmp     [rax+7CCh], ebx
0x180144de7  jz      short loc_180144DFD
0x180144de9  mov     r9d, ebx; int
0x180144dec  mov     r8d, 0B9h; int
0x180144df2  mov     rdx, r13; char *
0x180144df5  mov     rcx, rax; this
0x180144df8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180144dfd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180144e04  jb      short loc_180144E29
0x180144e06  mov     rcx, cs:WPP_GLOBAL_Control
0x180144e0d  lea     r8, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids
0x180144e14  mov     edx, 1Bh
0x180144e19  mov     dword ptr [rsp+50h+var_30], ebx
0x180144e1d  mov     r9, rsi
0x180144e20  mov     rcx, [rcx+10h]
0x180144e24  call    WPP_SF_qD
0x180144e29  lea     rcx, [rbp+arg_18]; void *
0x180144e2d  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180144e32  lea     rcx, [rbp+arg_0]; void *
0x180144e36  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180144e3b  lea     rcx, [rbp+var_20]; void *
0x180144e3f  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180144e44  mov     r15, [rbp+pv]
0x180144e48  jmp     loc_18014556D
0x180144e4d  mov     r15, [rbp+pv]
0x180144e51  test    r15, r15
0x180144e54  jz      loc_180144FF5
0x180144e5a  lea     r8, [rbp+var_18]; struct IMFSample **
0x180144e5e  mov     rdx, r15; struct tWAVEFORMATEX *
0x180144e61  mov     rcx, rsi; this
0x180144e64  call    ?CreateAudioFormatChange@CAVIIAVSStreamParser@@AEAAJPEAUtWAVEFORMATEX@@PEAPEAUIMFSample@@@Z; CAVIIAVSStreamParser::CreateAudioFormatChange(tWAVEFORMATEX *,IMFSample * *)
0x180144e69  mov     ebx, eax
0x180144e6b  test    eax, eax
0x180144e6d  jns     loc_180144F39
0x180144e73  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180144e7a  test    rcx, rcx
0x180144e7d  jnz     short loc_180144EC6
0x180144e7f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180144e86  nop     dword ptr [rax+rax+00h]
0x180144e8b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180144e92  mov     rcx, rax
0x180144e95  test    rax, rax
0x180144e98  jz      short loc_180144EB8
0x180144e9a  mov     rax, [rax]
0x180144e9d  mov     edx, 7F0h
0x180144ea2  mov     rax, [rax+8]
0x180144ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144eab  test    eax, eax
0x180144ead  jz      short loc_180144EB8
0x180144eaf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180144eb6  jmp     short loc_180144EC6
0x180144eb8  lea     rcx, qword_1801B97E0; this
0x180144ebf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180144ec6  cmp     [rcx+8], r12b
0x180144eca  jz      short loc_180144EED
0x180144ecc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180144ed1  cmp     [rax+7CCh], ebx
0x180144ed7  jz      short loc_180144EED
0x180144ed9  mov     r9d, ebx; int
0x180144edc  mov     r8d, 0BFh; int
0x180144ee2  mov     rdx, r13; char *
0x180144ee5  mov     rcx, rax; this
0x180144ee8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180144eed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180144ef4  jb      short loc_180144F19
0x180144ef6  mov     edx, 1Ch
0x180144efb  mov     dword ptr [rsp+50h+var_30], ebx
0x180144eff  mov     rcx, cs:WPP_GLOBAL_Control
0x180144f06  lea     r8, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids
0x180144f0d  mov     r9, rsi
0x180144f10  mov     rcx, [rcx+10h]
0x180144f14  call    WPP_SF_qD
0x180144f19  lea     rcx, [rbp+arg_18]; void *
0x180144f1d  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180144f22  lea     rcx, [rbp+arg_0]; void *
0x180144f26  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180144f2b  lea     rcx, [rbp+var_20]; void *
0x180144f2f  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180144f34  jmp     loc_18014556D
0x180144f39  mov     rdx, [rbp+var_18]; void *
0x180144f3d  lea     rdi, [rsi+2B0h]
0x180144f44  mov     rcx, rdi; this
0x180144f47  mov     [rbp+var_18], r12
0x180144f4b  call    ?AddTail@CVPtrList@@QEAAPEAXPEAX@Z; CVPtrList::AddTail(void *)
0x180144f50  test    rax, rax
0x180144f53  jnz     loc_180144FFC
0x180144f59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180144f60  mov     edi, 8007000Eh
0x180144f65  mov     ebx, edi
0x180144f67  test    rcx, rcx
0x180144f6a  jnz     short loc_180144FB3
0x180144f6c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180144f73  nop     dword ptr [rax+rax+00h]
0x180144f78  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180144f7f  mov     rcx, rax
0x180144f82  test    rax, rax
0x180144f85  jz      short loc_180144FA5
  ... truncated ...
```
