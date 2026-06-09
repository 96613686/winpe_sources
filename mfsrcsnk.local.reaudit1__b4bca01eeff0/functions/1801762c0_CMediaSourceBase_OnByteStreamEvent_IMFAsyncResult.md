# CMediaSourceBase::OnByteStreamEvent(IMFAsyncResult *)

- ea: `0x1801762c0`
- end: `0x180176e3e`
- name: `?OnByteStreamEvent@CMediaSourceBase@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `2942`
- prototype: `void __fastcall(CMediaSourceBase *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1801762a0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x18003e398`
- `0x180079680`
- `0x1800a6aa4`
- `0x1800de42c`
- `0x18016d298`
- `0x180175e10`
- `0x1801762c0`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180176e19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180176e19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18017631d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18017631d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18017633e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801763f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801764a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180176541`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801765fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801766ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18017675f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180176811`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801768c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180176999`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180176a9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180176b84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180176c38`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180176cee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18017633e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801763f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801764a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180176541`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801765fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801766ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18017675f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180176811`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801768c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180176999`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180176a9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180176b84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180176c38`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180176cee`
- `MFPlat!MFCreateMediaEvent` at `0x180176a7c`
- `MFPlat!MFCreateMediaEvent` at `0x180176a7c`
- `MFPlat!DestroyPropVariant` at `0x180176e09`
- `MFPlat!DestroyPropVariant` at `0x180176e09`

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
                    if ( (unsigned __int8)byte_1801BA10B >= 8u )
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
                                v47 = &qword_1801B97E0;
                                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                                v51 = &qword_1801B97E0;
                                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                                v55 = &qword_1801B97E0;
                                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                            v59 = &qword_1801B97E0;
                            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                        v42 = &qword_1801B97E0;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                        v38 = &qword_1801B97E0;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                      v34 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                    v30 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                  v26 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v22 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v18 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v15 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v11 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v5 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x1801762c0  push    rbp
0x1801762c2  push    rbx
0x1801762c3  push    rsi
0x1801762c4  push    rdi
0x1801762c5  push    r12
0x1801762c7  push    r14
0x1801762c9  push    r15
0x1801762cb  mov     rbp, rsp
0x1801762ce  sub     rsp, 70h
0x1801762d2  mov     rsi, rdx
0x1801762d5  lea     r12, aCmediasourceba_3; "CMediaSourceBase::OnByteStreamEvent"
0x1801762dc  mov     rbx, rcx
0x1801762df  mov     rdx, r12; char *
0x1801762e2  mov     r8d, 7ACh; int
0x1801762e8  lea     rcx, [rbp+arg_0]; this
0x1801762ec  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801762f1  xor     r15d, r15d
0x1801762f4  lea     rcx, [rbx+28h]; lpCriticalSection
0x1801762f8  xorps   xmm0, xmm0
0x1801762fb  mov     [rbp+arg_10], r15d
0x1801762ff  xor     eax, eax
0x180176301  mov     [rbp+var_28], r15
0x180176305  movups  xmmword ptr [rbp+var_18], xmm0
0x180176309  mov     qword ptr [rbp+var_18+10h], rax
0x18017630d  mov     [rbp+var_38], r15
0x180176311  mov     [rbp+var_20], r15
0x180176315  mov     [rbp+var_40], r15
0x180176319  mov     [rbp+var_30], r15
0x18017631d  call    cs:__imp_EnterCriticalSection
0x180176324  nop     dword ptr [rax+rax+00h]
0x180176329  test    rsi, rsi
0x18017632c  jnz     loc_1801763C8
0x180176332  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180176339  test    rcx, rcx
0x18017633c  jnz     short loc_180176385
0x18017633e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180176345  nop     dword ptr [rax+rax+00h]
0x18017634a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180176351  mov     rcx, rax
0x180176354  test    rax, rax
0x180176357  jz      short loc_180176377
0x180176359  mov     rax, [rax]
0x18017635c  mov     edx, 7F0h
0x180176361  mov     rax, [rax+8]
0x180176365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017636a  test    eax, eax
0x18017636c  jz      short loc_180176377
0x18017636e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180176375  jmp     short loc_180176385
0x180176377  lea     rcx, qword_1801B97E0; this
0x18017637e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180176385  mov     edi, 80070057h
0x18017638a  cmp     [rcx+8], r15b
0x18017638e  jz      short loc_1801763B1
0x180176390  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180176395  cmp     [rax+7CCh], edi
0x18017639b  jz      short loc_1801763B1
0x18017639d  mov     r9d, edi; int
0x1801763a0  mov     r8d, 7B9h; int
0x1801763a6  mov     rdx, r12; char *
0x1801763a9  mov     rcx, rax; this
0x1801763ac  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801763b1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801763b8  jb      loc_180176D88
0x1801763be  mov     edx, 0B4h
0x1801763c3  jmp     loc_180176D6A
0x1801763c8  mov     rax, [rsi]
0x1801763cb  lea     rdx, [rbp+var_20]
0x1801763cf  mov     rcx, rsi
0x1801763d2  mov     rax, [rax+18h]
0x1801763d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801763db  mov     edi, eax
0x1801763dd  test    eax, eax
0x1801763df  jns     loc_180176476
0x1801763e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801763ec  test    rcx, rcx
0x1801763ef  jnz     short loc_180176438
0x1801763f1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801763f8  nop     dword ptr [rax+rax+00h]
0x1801763fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180176404  mov     rcx, rax
0x180176407  test    rax, rax
0x18017640a  jz      short loc_18017642A
0x18017640c  mov     rax, [rax]
0x18017640f  mov     edx, 7F0h
0x180176414  mov     rax, [rax+8]
0x180176418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017641d  test    eax, eax
0x18017641f  jz      short loc_18017642A
0x180176421  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180176428  jmp     short loc_180176438
0x18017642a  lea     rcx, qword_1801B97E0; this
0x180176431  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180176438  cmp     [rcx+8], r15b
0x18017643c  jz      short loc_18017645F
0x18017643e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180176443  cmp     [rax+7CCh], edi
0x180176449  jz      short loc_18017645F
0x18017644b  mov     r9d, edi; int
0x18017644e  mov     r8d, 7BCh; int
0x180176454  mov     rdx, r12; char *
0x180176457  mov     rcx, rax; this
0x18017645a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18017645f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180176466  jb      loc_180176D88
0x18017646c  mov     edx, 0B5h
0x180176471  jmp     loc_180176D6A
0x180176476  mov     rcx, [rbp+var_20]
0x18017647a  lea     r8, [rbp+var_38]
0x18017647e  lea     rdx, IID_IMFByteStream
0x180176485  mov     rax, [rcx]
0x180176488  mov     rax, [rax]
0x18017648b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180176490  mov     edi, eax
0x180176492  test    eax, eax
0x180176494  jns     loc_18017652B
0x18017649a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801764a1  test    rcx, rcx
0x1801764a4  jnz     short loc_1801764ED
0x1801764a6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801764ad  nop     dword ptr [rax+rax+00h]
0x1801764b2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801764b9  mov     rcx, rax
0x1801764bc  test    rax, rax
0x1801764bf  jz      short loc_1801764DF
0x1801764c1  mov     rax, [rax]
0x1801764c4  mov     edx, 7F0h
0x1801764c9  mov     rax, [rax+8]
0x1801764cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801764d2  test    eax, eax
0x1801764d4  jz      short loc_1801764DF
0x1801764d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801764dd  jmp     short loc_1801764ED
0x1801764df  lea     rcx, qword_1801B97E0; this
0x1801764e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801764ed  cmp     [rcx+8], r15b
0x1801764f1  jz      short loc_180176514
0x1801764f3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801764f8  cmp     [rax+7CCh], edi
0x1801764fe  jz      short loc_180176514
0x180176500  mov     r9d, edi; int
0x180176503  mov     r8d, 7BFh; int
0x180176509  mov     rdx, r12; char *
0x18017650c  mov     rcx, rax; this
0x18017650f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180176514  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18017651b  jb      loc_180176D88
0x180176521  mov     edx, 0B6h
0x180176526  jmp     loc_180176D6A
0x18017652b  cmp     [rbp+var_38], r15
0x18017652f  jnz     loc_1801765CB
0x180176535  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18017653c  test    rcx, rcx
0x18017653f  jnz     short loc_180176588
0x180176541  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180176548  nop     dword ptr [rax+rax+00h]
0x18017654d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180176554  mov     rcx, rax
0x180176557  test    rax, rax
0x18017655a  jz      short loc_18017657A
0x18017655c  mov     rax, [rax]
0x18017655f  mov     edx, 7F0h
0x180176564  mov     rax, [rax+8]
0x180176568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017656d  test    eax, eax
0x18017656f  jz      short loc_18017657A
0x180176571  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180176578  jmp     short loc_180176588
0x18017657a  lea     rcx, qword_1801B97E0; this
0x180176581  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180176588  mov     edi, 8000FFFFh
0x18017658d  cmp     [rcx+8], r15b
0x180176591  jz      short loc_1801765B4
0x180176593  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180176598  cmp     [rax+7CCh], edi
0x18017659e  jz      short loc_1801765B4
0x1801765a0  mov     r9d, edi; int
0x1801765a3  mov     r8d, 7C0h; int
0x1801765a9  mov     rdx, r12; char *
0x1801765ac  mov     rcx, rax; this
0x1801765af  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801765b4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801765bb  jb      loc_180176D88
0x1801765c1  mov     edx, 0B7h
0x1801765c6  jmp     loc_180176D6A
0x1801765cb  mov     rcx, [rbp+var_38]
0x1801765cf  lea     r8, [rbp+var_28]
0x1801765d3  lea     rdx, IID_IMFMediaEventGenerator
0x1801765da  mov     rax, [rcx]
0x1801765dd  mov     rax, [rax]
0x1801765e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801765e5  mov     edi, eax
0x1801765e7  test    eax, eax
0x1801765e9  jns     loc_180176680
0x1801765ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801765f6  test    rcx, rcx
0x1801765f9  jnz     short loc_180176642
0x1801765fb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180176602  nop     dword ptr [rax+rax+00h]
0x180176607  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18017660e  mov     rcx, rax
0x180176611  test    rax, rax
0x180176614  jz      short loc_180176634
0x180176616  mov     rax, [rax]
0x180176619  mov     edx, 7F0h
0x18017661e  mov     rax, [rax+8]
0x180176622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180176627  test    eax, eax
0x180176629  jz      short loc_180176634
0x18017662b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180176632  jmp     short loc_180176642
0x180176634  lea     rcx, qword_1801B97E0; this
0x18017663b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180176642  cmp     [rcx+8], r15b
0x180176646  jz      short loc_180176669
0x180176648  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18017664d  cmp     [rax+7CCh], edi
0x180176653  jz      short loc_180176669
0x180176655  mov     r9d, edi; int
0x180176658  mov     r8d, 7C3h; int
0x18017665e  mov     rdx, r12; char *
0x180176661  mov     rcx, rax; this
0x180176664  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180176669  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180176670  jb      loc_180176D88
0x180176676  mov     edx, 0B8h
0x18017667b  jmp     loc_180176D6A
0x180176680  mov     rcx, [rbp+var_28]
0x180176684  lea     r8, [rbp+var_40]
0x180176688  mov     rdx, rsi
0x18017668b  mov     rax, [rcx]
0x18017668e  mov     rax, [rax+28h]
0x180176692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180176697  mov     edi, eax
0x180176699  test    eax, eax
0x18017669b  jns     loc_180176732
0x1801766a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801766a8  test    rcx, rcx
0x1801766ab  jnz     short loc_1801766F4
0x1801766ad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801766b4  nop     dword ptr [rax+rax+00h]
0x1801766b9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801766c0  mov     rcx, rax
0x1801766c3  test    rax, rax
0x1801766c6  jz      short loc_1801766E6
0x1801766c8  mov     rax, [rax]
0x1801766cb  mov     edx, 7F0h
0x1801766d0  mov     rax, [rax+8]
0x1801766d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801766d9  test    eax, eax
0x1801766db  jz      short loc_1801766E6
0x1801766dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801766e4  jmp     short loc_1801766F4
0x1801766e6  lea     rcx, qword_1801B97E0; this
0x1801766ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801766f4  cmp     [rcx+8], r15b
0x1801766f8  jz      short loc_18017671B
0x1801766fa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801766ff  cmp     [rax+7CCh], edi
0x180176705  jz      short loc_18017671B
0x180176707  mov     r9d, edi; int
0x18017670a  mov     r8d, 7C6h; int
0x180176710  mov     rdx, r12; char *
0x180176713  mov     rcx, rax; this
0x180176716  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18017671b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180176722  jb      loc_180176D88
0x180176728  mov     edx, 0B9h
0x18017672d  jmp     loc_180176D6A
0x180176732  mov     rcx, [rbp+var_40]
0x180176736  lea     rdx, [rbp+arg_10]
0x18017673a  mov     rax, [rcx]
0x18017673d  mov     rax, [rax+108h]
0x180176744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180176749  mov     edi, eax
0x18017674b  test    eax, eax
0x18017674d  jns     loc_1801767E4
0x180176753  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18017675a  test    rcx, rcx
0x18017675d  jnz     short loc_1801767A6
0x18017675f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180176766  nop     dword ptr [rax+rax+00h]
0x18017676b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180176772  mov     rcx, rax
0x180176775  test    rax, rax
0x180176778  jz      short loc_180176798
0x18017677a  mov     rax, [rax]
0x18017677d  mov     edx, 7F0h
0x180176782  mov     rax, [rax+8]
0x180176786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017678b  test    eax, eax
0x18017678d  jz      short loc_180176798
0x18017678f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180176796  jmp     short loc_1801767A6
0x180176798  lea     rcx, qword_1801B97E0; this
0x18017679f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801767a6  cmp     [rcx+8], r15b
0x1801767aa  jz      short loc_1801767CD
0x1801767ac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801767b1  cmp     [rax+7CCh], edi
  ... truncated ...
```
