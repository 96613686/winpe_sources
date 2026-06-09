# CMediaSourceBase::OnByteStreamEvent(IMFAsyncResult *)

- ea: `0x18016d180`
- end: `0x18016dc91`
- name: `?OnByteStreamEvent@CMediaSourceBase@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `2833`
- prototype: `void __fastcall(CMediaSourceBase *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18016d160`

## callees

- `0x18000a6dc`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180073b14`
- `0x1800a152c`
- `0x1800d8114`
- `0x180164394`
- `0x18016ccf0`
- `0x18016d180`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18016dc73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18016dc73`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18016d1dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18016d1dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d1f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d2a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d354`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d3e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d49d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d549`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d5f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d6a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d751`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d81d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d916`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d9f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016daa4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016db54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d1f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d2a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d354`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d3e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d49d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d549`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d5f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d6a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d751`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d81d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d916`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016d9f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016daa4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016db54`
- `MFPlat!MFCreateMediaEvent` at `0x18016d8fa`
- `MFPlat!MFCreateMediaEvent` at `0x18016d8fa`
- `MFPlat!DestroyPropVariant` at `0x18016dc69`
- `MFPlat!DestroyPropVariant` at `0x18016dc69`

## pseudocode

```c
void __fastcall CMediaSourceBase::OnByteStreamEvent(CMediaSourceBase *this, struct IMFAsyncResult *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  wchar_t *v7; // rcx
  CallStackTracing *v8; // rax
  HRESULT v9; // edi
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  wchar_t *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // r9
  wchar_t *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  unsigned int v63; // esi
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // r9
  wchar_t *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
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
  __int64 v82; // rdx
  __int64 v83; // r8
  __int64 v84; // r9
  wchar_t *v85; // rcx
  CallStackTracing *v86; // rax
  struct CallStackContext *v87; // rax
  struct IMFMediaEvent *v88; // [rsp+30h] [rbp-40h] BYREF
  struct IMFByteStream *v89; // [rsp+38h] [rbp-38h] BYREF
  IMFMediaEvent *ppEvent; // [rsp+40h] [rbp-30h] BYREF
  __int64 v91; // [rsp+48h] [rbp-28h] BYREF
  __int64 v92; // [rsp+50h] [rbp-20h] BYREF
  struct tagPROPVARIANT v93; // [rsp+58h] [rbp-18h] BYREF
  int v94; // [rsp+B0h] [rbp+40h] BYREF
  int v95; // [rsp+B8h] [rbp+48h] BYREF
  unsigned int v96; // [rsp+C0h] [rbp+50h] BYREF
  int v97; // [rsp+C8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v94, "CMediaSourceBase::OnByteStreamEvent", 1964);
  v96 = 0;
  v91 = 0;
  memset(&v93, 0, sizeof(v93));
  v89 = 0;
  v92 = 0;
  v88 = 0;
  ppEvent = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( a2 )
  {
    v9 = ((__int64 (__fastcall *)(struct IMFAsyncResult *, __int64 *))a2->lpVtbl->GetState)(a2, &v92);
    if ( v9 >= 0 )
    {
      v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IMFByteStream **))v92)(v92, &IID_IMFByteStream, &v89);
      if ( v9 >= 0 )
      {
        if ( v89 )
        {
          v9 = ((__int64 (__fastcall *)(struct IMFByteStream *, GUID *, __int64 *))v89->lpVtbl->QueryInterface)(
                 v89,
                 &IID_IMFMediaEventGenerator,
                 &v91);
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, struct IMFAsyncResult *, struct IMFMediaEvent **))(*(_QWORD *)v91 + 40LL))(
                   v91,
                   a2,
                   &v88);
            if ( v9 >= 0 )
            {
              v9 = ((__int64 (__fastcall *)(struct IMFMediaEvent *, unsigned int *))v88->lpVtbl->GetType)(v88, &v96);
              if ( v9 >= 0 )
              {
                v9 = ((__int64 (__fastcall *)(struct IMFMediaEvent *, struct tagPROPVARIANT *))v88->lpVtbl->GetValue)(
                       v88,
                       &v93);
                if ( v9 >= 0 )
                {
                  v95 = 0;
                  v9 = ((__int64 (__fastcall *)(struct IMFMediaEvent *, int *))v88->lpVtbl->GetStatus)(v88, &v95);
                  if ( v9 >= 0 )
                  {
                    if ( (unsigned __int8)byte_1801B110B >= 8u )
                      MFTRACE_MEDIA_EVENT_IMPL(0x30003u, v51, v88);
                    if ( *((_DWORD *)this + 49) )
                      goto LABEL_163;
                    v9 = CMediaSourceBase::InternalQueueEvent(this, v96, v95, &v93);
                    if ( v9 >= 0 )
                    {
                      if ( v95 >= 0 && v96 == 700 )
                      {
                        v63 = *((_DWORD *)this + 176);
                        v94 = 0;
                        v97 = 0;
                        CMediaSourceBase::HandleByteStreamCharacteristicsChanged(this, v89, &v94, &v97);
                        if ( v94 )
                        {
                          v9 = MFCreateMediaEvent(0xDBu, &GUID_00000000_0000_0000_0000_000000000000, 0, 0, &ppEvent);
                          if ( v9 < 0 )
                          {
                            v67 = (wchar_t *)CallStackTracing::s_wpInstance;
                            if ( !CallStackTracing::s_wpInstance )
                            {
                              v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v64, v65, v66);
                              CallStackTracing::s_wpInstance = v68;
                              if ( v68
                                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(
                                     v68,
                                     2032) )
                              {
                                v67 = (wchar_t *)CallStackTracing::s_wpInstance;
                              }
                              else
                              {
                                v67 = &qword_1801B07E0;
                                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                              }
                            }
                            if ( *((_BYTE *)v67 + 8) )
                            {
                              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v67);
                              if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
                                CallStackContext::TraceFailure(
                                  ThreadRelativeContext,
                                  "CMediaSourceBase::OnByteStreamEvent",
                                  2036,
                                  v9);
                            }
                            if ( g_wppLevels )
                            {
                              v11 = 190;
                              goto LABEL_162;
                            }
                            goto LABEL_163;
                          }
                          ((void (__fastcall *)(IMFMediaEvent *, const GUID *, _QWORD))ppEvent->lpVtbl->SetUINT32)(
                            ppEvent,
                            &MF_EVENT_SOURCE_CHARACTERISTICS,
                            *((unsigned int *)this + 176));
                          ((void (__fastcall *)(IMFMediaEvent *, const GUID *, _QWORD))ppEvent->lpVtbl->SetUINT32)(
                            ppEvent,
                            &MF_EVENT_SOURCE_CHARACTERISTICS_OLD,
                            v63);
                          v9 = CMFMediaEventGenerator::QueueEvent((CMediaSourceBase *)((char *)this + 32), ppEvent);
                          if ( v9 < 0 )
                          {
                            v73 = (wchar_t *)CallStackTracing::s_wpInstance;
                            if ( !CallStackTracing::s_wpInstance )
                            {
                              v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v70, v71, v72);
                              CallStackTracing::s_wpInstance = v74;
                              if ( v74
                                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(
                                     v74,
                                     2032) )
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
                              if ( *((_DWORD *)v75 + 499) != v9 )
                                CallStackContext::TraceFailure(v75, "CMediaSourceBase::OnByteStreamEvent", 2043, v9);
                            }
                            if ( g_wppLevels )
                            {
                              v11 = 191;
                              goto LABEL_162;
                            }
                            goto LABEL_163;
                          }
                        }
                        if ( v97 )
                        {
                          v9 = CMediaSourceBase::InternalQueueMetadataEvent(
                                 this,
                                 *((struct IMFPresentationDescriptor **)this + 30));
                          if ( v9 < 0 )
                          {
                            v79 = (wchar_t *)CallStackTracing::s_wpInstance;
                            if ( !CallStackTracing::s_wpInstance )
                            {
                              v80 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v76, v77, v78);
                              CallStackTracing::s_wpInstance = v80;
                              if ( v80
                                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v80 + 8LL))(
                                     v80,
                                     2032) )
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
                              if ( *((_DWORD *)v81 + 499) != v9 )
                                CallStackContext::TraceFailure(v81, "CMediaSourceBase::OnByteStreamEvent", 2048, v9);
                            }
                            if ( g_wppLevels )
                            {
                              v11 = 192;
                              goto LABEL_162;
                            }
                            goto LABEL_163;
                          }
                        }
                      }
                      v9 = (*(__int64 (__fastcall **)(__int64, char *, struct IMFByteStream *))(*(_QWORD *)v91 + 32LL))(
                             v91,
                             (char *)this + 184,
                             v89);
                      if ( v9 < 0 )
                      {
                        v85 = (wchar_t *)CallStackTracing::s_wpInstance;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          v86 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v82, v83, v84);
                          CallStackTracing::s_wpInstance = v86;
                          if ( v86
                            && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v86 + 8LL))(
                                 v86,
                                 2032) )
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
                          if ( *((_DWORD *)v87 + 499) != v9 )
                            CallStackContext::TraceFailure(v87, "CMediaSourceBase::OnByteStreamEvent", 2054, v9);
                        }
                        if ( g_wppLevels )
                        {
                          v11 = 193;
                          goto LABEL_162;
                        }
                      }
                      goto LABEL_163;
                    }
                    v60 = (wchar_t *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v57, v58, v59);
                      CallStackTracing::s_wpInstance = v61;
                      if ( v61
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(
                             v61,
                             2032) )
                      {
                        v60 = (wchar_t *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v60 = &qword_1801B07E0;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                      }
                    }
                    if ( *((_BYTE *)v60 + 8) )
                    {
                      v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
                      if ( *((_DWORD *)v62 + 499) != v9 )
                        CallStackContext::TraceFailure(v62, "CMediaSourceBase::OnByteStreamEvent", 2013, v9);
                    }
                    if ( g_wppLevels )
                    {
                      v11 = 189;
                      goto LABEL_162;
                    }
                  }
                  else
                  {
                    v54 = (wchar_t *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                      CallStackTracing::s_wpInstance = v55;
                      if ( v55
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(
                             v55,
                             2032) )
                      {
                        v54 = (wchar_t *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v54 = &qword_1801B07E0;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                      }
                    }
                    if ( *((_BYTE *)v54 + 8) )
                    {
                      v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
                      if ( *((_DWORD *)v56 + 499) != v9 )
                        CallStackContext::TraceFailure(v56, "CMediaSourceBase::OnByteStreamEvent", 2000, v9);
                    }
                    if ( g_wppLevels )
                    {
                      v11 = 188;
                      goto LABEL_162;
                    }
                  }
                }
                else
                {
                  v48 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v46, v47);
                    CallStackTracing::s_wpInstance = v49;
                    if ( v49
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
                    {
                      v48 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v48 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                    }
                  }
                  if ( *((_BYTE *)v48 + 8) )
                  {
                    v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
                    if ( *((_DWORD *)v50 + 499) != v9 )
                      CallStackContext::TraceFailure(v50, "CMediaSourceBase::OnByteStreamEvent", 1996, v9);
                  }
                  if ( g_wppLevels )
                  {
                    v11 = 187;
                    goto LABEL_162;
                  }
                }
              }
              else
              {
                v42 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40, v41);
                  CallStackTracing::s_wpInstance = v43;
                  if ( v43
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
                  {
                    v42 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v42 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v42 + 8) )
                {
                  v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
                  if ( *((_DWORD *)v44 + 499) != v9 )
                    CallStackContext::TraceFailure(v44, "CMediaSourceBase::OnByteStreamEvent", 1993, v9);
                }
                if ( g_wppLevels )
                {
                  v11 = 186;
                  goto LABEL_162;
                }
              }
            }
            else
            {
              v36 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34, v35);
                CallStackTracing::s_wpInstance = v37;
                if ( v37
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
                {
                  v36 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v36 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v36 + 8) )
              {
                v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
                if ( *((_DWORD *)v38 + 499) != v9 )
                  CallStackContext::TraceFailure(v38, "CMediaSourceBase::OnByteStreamEvent", 1990, v9);
              }
              if ( g_wppLevels )
              {
                v11 = 185;
                goto LABEL_162;
              }
            }
          }
          else
          {
            v30 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
              CallStackTracing::s_wpInstance = v31;
              if ( v31
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
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
              if ( *((_DWORD *)v32 + 499) != v9 )
                CallStackContext::TraceFailure(v32, "CMediaSourceBase::OnByteStreamEvent", 1987, v9);
            }
            if ( g_wppLevels )
            {
              v11 = 184;
              goto LABEL_162;
            }
          }
        }
        else
        {
          v24 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
            CallStackTracing::s_wpInstance = v25;
            if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
            {
              v24 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v24 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          v9 = -2147418113;
          if ( *((_BYTE *)v24 + 8) )
          {
            v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
            if ( *((_DWORD *)v26 + 499) != -2147418113 )
              CallStackContext::TraceFailure(v26, "CMediaSourceBase::OnByteStreamEvent", 1984, -2147418113);
          }
          if ( g_wppLevels )
          {
            v11 = 183;
            goto LABEL_162;
          }
        }
      }
      else
      {
        v21 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
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
          if ( *((_DWORD *)v23 + 499) != v9 )
            CallStackContext::TraceFailure(v23, "CMediaSourceBase::OnByteStreamEvent", 1983, v9);
        }
        if ( g_wppLevels )
        {
          v11 = 182;
          goto LABEL_162;
        }
      }
    }
    else
    {
      v15 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != v9 )
          CallStackContext::TraceFailure(v17, "CMediaSourceBase::OnByteStreamEvent", 1980, v9);
      }
      if ( g_wppLevels )
      {
        v11 = 181;
        goto LABEL_162;
      }
    }
  }
  else
  {
    v7 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    v9 = -2147024809;
    if ( *((_BYTE *)v7 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v10 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v10, "CMediaSourceBase::OnByteStreamEvent", 1977, -2147024809);
    }
    if ( g_wppLevels )
    {
      v11 = 180;
LABEL_162:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v9);
    }
  }
LABEL_163:
  if ( ppEvent )
  {
    ((void (__fastcall *)(IMFMediaEvent *))ppEvent->lpVtbl->Release)(ppEvent);
    ppEvent = 0;
  }
  if ( v88 )
  {
    ((void (__fastcall *)(struct IMFMediaEvent *))v88->lpVtbl->Release)(v88);
    v88 = 0;
  }
  if ( v91 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
    v91 = 0;
  }
  if ( v89 )
  {
    ((void (__fastcall *)(struct IMFByteStream *))v89->lpVtbl->Release)(v89);
    v89 = 0;
  }
  if ( v92 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
    v92 = 0;
  }
  DestroyPropVariant(&v93);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v94);
}

```

## disassembly

```asm
0x18016d180  push    rbp
0x18016d182  push    rbx
0x18016d183  push    rsi
0x18016d184  push    rdi
0x18016d185  push    r12
0x18016d187  push    r14
0x18016d189  push    r15
0x18016d18b  mov     rbp, rsp
0x18016d18e  sub     rsp, 70h
0x18016d192  mov     rsi, rdx
0x18016d195  lea     r12, aCmediasourceba_3; "CMediaSourceBase::OnByteStreamEvent"
0x18016d19c  mov     rbx, rcx
0x18016d19f  mov     rdx, r12; char *
0x18016d1a2  mov     r8d, 7ACh; int
0x18016d1a8  lea     rcx, [rbp+arg_0]; this
0x18016d1ac  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18016d1b1  xor     r15d, r15d
0x18016d1b4  lea     rcx, [rbx+28h]; lpCriticalSection
0x18016d1b8  xorps   xmm0, xmm0
0x18016d1bb  mov     [rbp+arg_10], r15d
0x18016d1bf  xor     eax, eax
0x18016d1c1  mov     [rbp+var_28], r15
0x18016d1c5  movups  xmmword ptr [rbp+var_18], xmm0
0x18016d1c9  mov     qword ptr [rbp+var_18+10h], rax
0x18016d1cd  mov     [rbp+var_38], r15
0x18016d1d1  mov     [rbp+var_20], r15
0x18016d1d5  mov     [rbp+var_40], r15
0x18016d1d9  mov     [rbp+var_30], r15
0x18016d1dd  call    cs:__imp_EnterCriticalSection
0x18016d1e3  test    rsi, rsi
0x18016d1e6  jnz     loc_18016D27C
0x18016d1ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d1f3  test    rcx, rcx
0x18016d1f6  jnz     short loc_18016D239
0x18016d1f8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18016d1fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d205  mov     rcx, rax
0x18016d208  test    rax, rax
0x18016d20b  jz      short loc_18016D22B
0x18016d20d  mov     rax, [rax]
0x18016d210  mov     edx, 7F0h
0x18016d215  mov     rax, [rax+8]
0x18016d219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d21e  test    eax, eax
0x18016d220  jz      short loc_18016D22B
0x18016d222  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d229  jmp     short loc_18016D239
0x18016d22b  lea     rcx, qword_1801B07E0; this
0x18016d232  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d239  mov     edi, 80070057h
0x18016d23e  cmp     [rcx+8], r15b
0x18016d242  jz      short loc_18016D265
0x18016d244  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016d249  cmp     [rax+7CCh], edi
0x18016d24f  jz      short loc_18016D265
0x18016d251  mov     r9d, edi; int
0x18016d254  mov     r8d, 7B9h; int
0x18016d25a  mov     rdx, r12; char *
0x18016d25d  mov     rcx, rax; this
0x18016d260  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18016d265  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18016d26c  jb      loc_18016DBE8
0x18016d272  mov     edx, 0B4h
0x18016d277  jmp     loc_18016DBCA
0x18016d27c  mov     rax, [rsi]
0x18016d27f  lea     rdx, [rbp+var_20]
0x18016d283  mov     rcx, rsi
0x18016d286  mov     rax, [rax+18h]
0x18016d28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d28f  mov     edi, eax
0x18016d291  test    eax, eax
0x18016d293  jns     loc_18016D324
0x18016d299  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d2a0  test    rcx, rcx
0x18016d2a3  jnz     short loc_18016D2E6
0x18016d2a5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18016d2ab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d2b2  mov     rcx, rax
0x18016d2b5  test    rax, rax
0x18016d2b8  jz      short loc_18016D2D8
0x18016d2ba  mov     rax, [rax]
0x18016d2bd  mov     edx, 7F0h
0x18016d2c2  mov     rax, [rax+8]
0x18016d2c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d2cb  test    eax, eax
0x18016d2cd  jz      short loc_18016D2D8
0x18016d2cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d2d6  jmp     short loc_18016D2E6
0x18016d2d8  lea     rcx, qword_1801B07E0; this
0x18016d2df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d2e6  cmp     [rcx+8], r15b
0x18016d2ea  jz      short loc_18016D30D
0x18016d2ec  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016d2f1  cmp     [rax+7CCh], edi
0x18016d2f7  jz      short loc_18016D30D
0x18016d2f9  mov     r9d, edi; int
0x18016d2fc  mov     r8d, 7BCh; int
0x18016d302  mov     rdx, r12; char *
0x18016d305  mov     rcx, rax; this
0x18016d308  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18016d30d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18016d314  jb      loc_18016DBE8
0x18016d31a  mov     edx, 0B5h
0x18016d31f  jmp     loc_18016DBCA
0x18016d324  mov     rcx, [rbp+var_20]
0x18016d328  lea     r8, [rbp+var_38]
0x18016d32c  lea     rdx, IID_IMFByteStream
0x18016d333  mov     rax, [rcx]
0x18016d336  mov     rax, [rax]
0x18016d339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d33e  mov     edi, eax
0x18016d340  test    eax, eax
0x18016d342  jns     loc_18016D3D3
0x18016d348  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d34f  test    rcx, rcx
0x18016d352  jnz     short loc_18016D395
0x18016d354  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18016d35a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d361  mov     rcx, rax
0x18016d364  test    rax, rax
0x18016d367  jz      short loc_18016D387
0x18016d369  mov     rax, [rax]
0x18016d36c  mov     edx, 7F0h
0x18016d371  mov     rax, [rax+8]
0x18016d375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d37a  test    eax, eax
0x18016d37c  jz      short loc_18016D387
0x18016d37e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d385  jmp     short loc_18016D395
0x18016d387  lea     rcx, qword_1801B07E0; this
0x18016d38e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d395  cmp     [rcx+8], r15b
0x18016d399  jz      short loc_18016D3BC
0x18016d39b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016d3a0  cmp     [rax+7CCh], edi
0x18016d3a6  jz      short loc_18016D3BC
0x18016d3a8  mov     r9d, edi; int
0x18016d3ab  mov     r8d, 7BFh; int
0x18016d3b1  mov     rdx, r12; char *
0x18016d3b4  mov     rcx, rax; this
0x18016d3b7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18016d3bc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18016d3c3  jb      loc_18016DBE8
0x18016d3c9  mov     edx, 0B6h
0x18016d3ce  jmp     loc_18016DBCA
0x18016d3d3  cmp     [rbp+var_38], r15
0x18016d3d7  jnz     loc_18016D46D
0x18016d3dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d3e4  test    rcx, rcx
0x18016d3e7  jnz     short loc_18016D42A
0x18016d3e9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18016d3ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d3f6  mov     rcx, rax
0x18016d3f9  test    rax, rax
0x18016d3fc  jz      short loc_18016D41C
0x18016d3fe  mov     rax, [rax]
0x18016d401  mov     edx, 7F0h
0x18016d406  mov     rax, [rax+8]
0x18016d40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d40f  test    eax, eax
0x18016d411  jz      short loc_18016D41C
0x18016d413  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d41a  jmp     short loc_18016D42A
0x18016d41c  lea     rcx, qword_1801B07E0; this
0x18016d423  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d42a  mov     edi, 8000FFFFh
0x18016d42f  cmp     [rcx+8], r15b
0x18016d433  jz      short loc_18016D456
0x18016d435  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016d43a  cmp     [rax+7CCh], edi
0x18016d440  jz      short loc_18016D456
0x18016d442  mov     r9d, edi; int
0x18016d445  mov     r8d, 7C0h; int
0x18016d44b  mov     rdx, r12; char *
0x18016d44e  mov     rcx, rax; this
0x18016d451  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18016d456  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18016d45d  jb      loc_18016DBE8
0x18016d463  mov     edx, 0B7h
0x18016d468  jmp     loc_18016DBCA
0x18016d46d  mov     rcx, [rbp+var_38]
0x18016d471  lea     r8, [rbp+var_28]
0x18016d475  lea     rdx, IID_IMFMediaEventGenerator
0x18016d47c  mov     rax, [rcx]
0x18016d47f  mov     rax, [rax]
0x18016d482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d487  mov     edi, eax
0x18016d489  test    eax, eax
0x18016d48b  jns     loc_18016D51C
0x18016d491  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d498  test    rcx, rcx
0x18016d49b  jnz     short loc_18016D4DE
0x18016d49d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18016d4a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d4aa  mov     rcx, rax
0x18016d4ad  test    rax, rax
0x18016d4b0  jz      short loc_18016D4D0
0x18016d4b2  mov     rax, [rax]
0x18016d4b5  mov     edx, 7F0h
0x18016d4ba  mov     rax, [rax+8]
0x18016d4be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d4c3  test    eax, eax
0x18016d4c5  jz      short loc_18016D4D0
0x18016d4c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d4ce  jmp     short loc_18016D4DE
0x18016d4d0  lea     rcx, qword_1801B07E0; this
0x18016d4d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d4de  cmp     [rcx+8], r15b
0x18016d4e2  jz      short loc_18016D505
0x18016d4e4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016d4e9  cmp     [rax+7CCh], edi
0x18016d4ef  jz      short loc_18016D505
0x18016d4f1  mov     r9d, edi; int
0x18016d4f4  mov     r8d, 7C3h; int
0x18016d4fa  mov     rdx, r12; char *
0x18016d4fd  mov     rcx, rax; this
0x18016d500  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18016d505  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18016d50c  jb      loc_18016DBE8
0x18016d512  mov     edx, 0B8h
0x18016d517  jmp     loc_18016DBCA
0x18016d51c  mov     rcx, [rbp+var_28]
0x18016d520  lea     r8, [rbp+var_40]
0x18016d524  mov     rdx, rsi
0x18016d527  mov     rax, [rcx]
0x18016d52a  mov     rax, [rax+28h]
0x18016d52e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d533  mov     edi, eax
0x18016d535  test    eax, eax
0x18016d537  jns     loc_18016D5C8
0x18016d53d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d544  test    rcx, rcx
0x18016d547  jnz     short loc_18016D58A
0x18016d549  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18016d54f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d556  mov     rcx, rax
0x18016d559  test    rax, rax
0x18016d55c  jz      short loc_18016D57C
0x18016d55e  mov     rax, [rax]
0x18016d561  mov     edx, 7F0h
0x18016d566  mov     rax, [rax+8]
0x18016d56a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d56f  test    eax, eax
0x18016d571  jz      short loc_18016D57C
0x18016d573  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d57a  jmp     short loc_18016D58A
0x18016d57c  lea     rcx, qword_1801B07E0; this
0x18016d583  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d58a  cmp     [rcx+8], r15b
0x18016d58e  jz      short loc_18016D5B1
0x18016d590  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016d595  cmp     [rax+7CCh], edi
0x18016d59b  jz      short loc_18016D5B1
0x18016d59d  mov     r9d, edi; int
0x18016d5a0  mov     r8d, 7C6h; int
0x18016d5a6  mov     rdx, r12; char *
0x18016d5a9  mov     rcx, rax; this
0x18016d5ac  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18016d5b1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18016d5b8  jb      loc_18016DBE8
0x18016d5be  mov     edx, 0B9h
0x18016d5c3  jmp     loc_18016DBCA
0x18016d5c8  mov     rcx, [rbp+var_40]
0x18016d5cc  lea     rdx, [rbp+arg_10]
0x18016d5d0  mov     rax, [rcx]
0x18016d5d3  mov     rax, [rax+108h]
0x18016d5da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d5df  mov     edi, eax
0x18016d5e1  test    eax, eax
0x18016d5e3  jns     loc_18016D674
0x18016d5e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d5f0  test    rcx, rcx
0x18016d5f3  jnz     short loc_18016D636
0x18016d5f5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18016d5fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d602  mov     rcx, rax
0x18016d605  test    rax, rax
0x18016d608  jz      short loc_18016D628
0x18016d60a  mov     rax, [rax]
0x18016d60d  mov     edx, 7F0h
0x18016d612  mov     rax, [rax+8]
0x18016d616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d61b  test    eax, eax
0x18016d61d  jz      short loc_18016D628
0x18016d61f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d626  jmp     short loc_18016D636
0x18016d628  lea     rcx, qword_1801B07E0; this
0x18016d62f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016d636  cmp     [rcx+8], r15b
0x18016d63a  jz      short loc_18016D65D
0x18016d63c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016d641  cmp     [rax+7CCh], edi
0x18016d647  jz      short loc_18016D65D
0x18016d649  mov     r9d, edi; int
0x18016d64c  mov     r8d, 7C9h; int
0x18016d652  mov     rdx, r12; char *
0x18016d655  mov     rcx, rax; this
0x18016d658  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18016d65d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18016d664  jb      loc_18016DBE8
  ... truncated ...
```
