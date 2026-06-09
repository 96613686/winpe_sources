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
  wchar_t *v5; // rcx
  CallStackTracing *v6; // rax
  HRESULT v7; // edi
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rdx
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  unsigned int v45; // esi
  __int64 v46; // rdx
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v50; // rdx
  wchar_t *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  __int64 v54; // rdx
  wchar_t *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 v58; // rdx
  wchar_t *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  struct IMFMediaEvent *v62; // [rsp+30h] [rbp-40h] BYREF
  struct IMFByteStream *v63; // [rsp+38h] [rbp-38h] BYREF
  IMFMediaEvent *ppEvent; // [rsp+40h] [rbp-30h] BYREF
  __int64 v65; // [rsp+48h] [rbp-28h] BYREF
  __int64 v66; // [rsp+50h] [rbp-20h] BYREF
  struct tagPROPVARIANT v67; // [rsp+58h] [rbp-18h] BYREF
  int v68; // [rsp+B0h] [rbp+40h] BYREF
  int v69; // [rsp+B8h] [rbp+48h] BYREF
  unsigned int v70; // [rsp+C0h] [rbp+50h] BYREF
  int v71; // [rsp+C8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v68, "CMediaSourceBase::OnByteStreamEvent", 1964);
  v70 = 0;
  v65 = 0;
  memset(&v67, 0, sizeof(v67));
  v63 = 0;
  v66 = 0;
  v62 = 0;
  ppEvent = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( a2 )
  {
    v7 = ((__int64 (__fastcall *)(struct IMFAsyncResult *, __int64 *))a2->lpVtbl->GetState)(a2, &v66);
    if ( v7 >= 0 )
    {
      v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IMFByteStream **))v66)(v66, &IID_IMFByteStream, &v63);
      if ( v7 >= 0 )
      {
        if ( v63 )
        {
          v7 = ((__int64 (__fastcall *)(struct IMFByteStream *, GUID *, __int64 *))v63->lpVtbl->QueryInterface)(
                 v63,
                 &IID_IMFMediaEventGenerator,
                 &v65);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, struct IMFAsyncResult *, struct IMFMediaEvent **))(*(_QWORD *)v65 + 40LL))(
                   v65,
                   a2,
                   &v62);
            if ( v7 >= 0 )
            {
              v7 = ((__int64 (__fastcall *)(struct IMFMediaEvent *, unsigned int *))v62->lpVtbl->GetType)(v62, &v70);
              if ( v7 >= 0 )
              {
                v7 = ((__int64 (__fastcall *)(struct IMFMediaEvent *, struct tagPROPVARIANT *))v62->lpVtbl->GetValue)(
                       v62,
                       &v67);
                if ( v7 >= 0 )
                {
                  v69 = 0;
                  v7 = ((__int64 (__fastcall *)(struct IMFMediaEvent *, int *))v62->lpVtbl->GetStatus)(v62, &v69);
                  if ( v7 >= 0 )
                  {
                    if ( (unsigned __int8)byte_1801B110B >= 8u )
                      MFTRACE_MEDIA_EVENT_IMPL(0x30003u, v37, v62);
                    if ( *((_DWORD *)this + 49) )
                      goto LABEL_163;
                    v7 = CMediaSourceBase::InternalQueueEvent(this, v70, v69, &v67);
                    if ( v7 >= 0 )
                    {
                      if ( v69 >= 0 && v70 == 700 )
                      {
                        v45 = *((_DWORD *)this + 176);
                        v68 = 0;
                        v71 = 0;
                        CMediaSourceBase::HandleByteStreamCharacteristicsChanged(this, v63, &v68, &v71);
                        if ( v68 )
                        {
                          v7 = MFCreateMediaEvent(0xDBu, &GUID_00000000_0000_0000_0000_000000000000, 0, 0, &ppEvent);
                          if ( v7 < 0 )
                          {
                            v47 = (wchar_t *)CallStackTracing::s_wpInstance;
                            if ( !CallStackTracing::s_wpInstance )
                            {
                              v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
                              CallStackTracing::s_wpInstance = v48;
                              if ( v48
                                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(
                                     v48,
                                     2032) )
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
                              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
                              if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
                                CallStackContext::TraceFailure(
                                  ThreadRelativeContext,
                                  "CMediaSourceBase::OnByteStreamEvent",
                                  2036,
                                  v7);
                            }
                            if ( g_wppLevels )
                            {
                              v9 = 190;
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
                            v45);
                          v7 = CMFMediaEventGenerator::QueueEvent((CMediaSourceBase *)((char *)this + 32), ppEvent);
                          if ( v7 < 0 )
                          {
                            v51 = (wchar_t *)CallStackTracing::s_wpInstance;
                            if ( !CallStackTracing::s_wpInstance )
                            {
                              v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50);
                              CallStackTracing::s_wpInstance = v52;
                              if ( v52
                                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(
                                     v52,
                                     2032) )
                              {
                                v51 = (wchar_t *)CallStackTracing::s_wpInstance;
                              }
                              else
                              {
                                v51 = &qword_1801B07E0;
                                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                              }
                            }
                            if ( *((_BYTE *)v51 + 8) )
                            {
                              v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
                              if ( *((_DWORD *)v53 + 499) != v7 )
                                CallStackContext::TraceFailure(v53, "CMediaSourceBase::OnByteStreamEvent", 2043, v7);
                            }
                            if ( g_wppLevels )
                            {
                              v9 = 191;
                              goto LABEL_162;
                            }
                            goto LABEL_163;
                          }
                        }
                        if ( v71 )
                        {
                          v7 = CMediaSourceBase::InternalQueueMetadataEvent(
                                 this,
                                 *((struct IMFPresentationDescriptor **)this + 30));
                          if ( v7 < 0 )
                          {
                            v55 = (wchar_t *)CallStackTracing::s_wpInstance;
                            if ( !CallStackTracing::s_wpInstance )
                            {
                              v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54);
                              CallStackTracing::s_wpInstance = v56;
                              if ( v56
                                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(
                                     v56,
                                     2032) )
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
                              if ( *((_DWORD *)v57 + 499) != v7 )
                                CallStackContext::TraceFailure(v57, "CMediaSourceBase::OnByteStreamEvent", 2048, v7);
                            }
                            if ( g_wppLevels )
                            {
                              v9 = 192;
                              goto LABEL_162;
                            }
                            goto LABEL_163;
                          }
                        }
                      }
                      v7 = (*(__int64 (__fastcall **)(__int64, char *, struct IMFByteStream *))(*(_QWORD *)v65 + 32LL))(
                             v65,
                             (char *)this + 184,
                             v63);
                      if ( v7 < 0 )
                      {
                        v59 = (wchar_t *)CallStackTracing::s_wpInstance;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58);
                          CallStackTracing::s_wpInstance = v60;
                          if ( v60
                            && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(
                                 v60,
                                 2032) )
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
                          if ( *((_DWORD *)v61 + 499) != v7 )
                            CallStackContext::TraceFailure(v61, "CMediaSourceBase::OnByteStreamEvent", 2054, v7);
                        }
                        if ( g_wppLevels )
                        {
                          v9 = 193;
                          goto LABEL_162;
                        }
                      }
                      goto LABEL_163;
                    }
                    v42 = (wchar_t *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41);
                      CallStackTracing::s_wpInstance = v43;
                      if ( v43
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(
                             v43,
                             2032) )
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
                      if ( *((_DWORD *)v44 + 499) != v7 )
                        CallStackContext::TraceFailure(v44, "CMediaSourceBase::OnByteStreamEvent", 2013, v7);
                    }
                    if ( g_wppLevels )
                    {
                      v9 = 189;
                      goto LABEL_162;
                    }
                  }
                  else
                  {
                    v38 = (wchar_t *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
                      CallStackTracing::s_wpInstance = v39;
                      if ( v39
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(
                             v39,
                             2032) )
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
                      if ( *((_DWORD *)v40 + 499) != v7 )
                        CallStackContext::TraceFailure(v40, "CMediaSourceBase::OnByteStreamEvent", 2000, v7);
                    }
                    if ( g_wppLevels )
                    {
                      v9 = 188;
                      goto LABEL_162;
                    }
                  }
                }
                else
                {
                  v34 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
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
                    v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
                    if ( *((_DWORD *)v36 + 499) != v7 )
                      CallStackContext::TraceFailure(v36, "CMediaSourceBase::OnByteStreamEvent", 1996, v7);
                  }
                  if ( g_wppLevels )
                  {
                    v9 = 187;
                    goto LABEL_162;
                  }
                }
              }
              else
              {
                v30 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
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
                  if ( *((_DWORD *)v32 + 499) != v7 )
                    CallStackContext::TraceFailure(v32, "CMediaSourceBase::OnByteStreamEvent", 1993, v7);
                }
                if ( g_wppLevels )
                {
                  v9 = 186;
                  goto LABEL_162;
                }
              }
            }
            else
            {
              v26 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
                CallStackTracing::s_wpInstance = v27;
                if ( v27
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
                {
                  v26 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v26 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v26 + 8) )
              {
                v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
                if ( *((_DWORD *)v28 + 499) != v7 )
                  CallStackContext::TraceFailure(v28, "CMediaSourceBase::OnByteStreamEvent", 1990, v7);
              }
              if ( g_wppLevels )
              {
                v9 = 185;
                goto LABEL_162;
              }
            }
          }
          else
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
                v22 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v22 + 8) )
            {
              v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
              if ( *((_DWORD *)v24 + 499) != v7 )
                CallStackContext::TraceFailure(v24, "CMediaSourceBase::OnByteStreamEvent", 1987, v7);
            }
            if ( g_wppLevels )
            {
              v9 = 184;
              goto LABEL_162;
            }
          }
        }
        else
        {
          v18 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
            CallStackTracing::s_wpInstance = v19;
            if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
            {
              v18 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v18 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          v7 = -2147418113;
          if ( *((_BYTE *)v18 + 8) )
          {
            v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
            if ( *((_DWORD *)v20 + 499) != -2147418113 )
              CallStackContext::TraceFailure(v20, "CMediaSourceBase::OnByteStreamEvent", 1984, -2147418113);
          }
          if ( g_wppLevels )
          {
            v9 = 183;
            goto LABEL_162;
          }
        }
      }
      else
      {
        v15 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
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
          if ( *((_DWORD *)v17 + 499) != v7 )
            CallStackContext::TraceFailure(v17, "CMediaSourceBase::OnByteStreamEvent", 1983, v7);
        }
        if ( g_wppLevels )
        {
          v9 = 182;
          goto LABEL_162;
        }
      }
    }
    else
    {
      v11 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v13 + 499) != v7 )
          CallStackContext::TraceFailure(v13, "CMediaSourceBase::OnByteStreamEvent", 1980, v7);
      }
      if ( g_wppLevels )
      {
        v9 = 181;
        goto LABEL_162;
      }
    }
  }
  else
  {
    v5 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v5 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    v7 = -2147024809;
    if ( *((_BYTE *)v5 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v8 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v8, "CMediaSourceBase::OnByteStreamEvent", 1977, -2147024809);
    }
    if ( g_wppLevels )
    {
      v9 = 180;
LABEL_162:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v7);
    }
  }
LABEL_163:
  if ( ppEvent )
  {
    ((void (__fastcall *)(IMFMediaEvent *))ppEvent->lpVtbl->Release)(ppEvent);
    ppEvent = 0;
  }
  if ( v62 )
  {
    ((void (__fastcall *)(struct IMFMediaEvent *))v62->lpVtbl->Release)(v62);
    v62 = 0;
  }
  if ( v65 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    v65 = 0;
  }
  if ( v63 )
  {
    ((void (__fastcall *)(struct IMFByteStream *))v63->lpVtbl->Release)(v63);
    v63 = 0;
  }
  if ( v66 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    v66 = 0;
  }
  DestroyPropVariant(&v67);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v68);
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
