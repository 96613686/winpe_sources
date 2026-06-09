# CMFByteStreamMediaSource::OnByteStreamReadIndex(IMFAsyncResult *)

- ea: `0x1800892a0`
- end: `0x180089f1f`
- name: `?OnByteStreamReadIndex@CMFByteStreamMediaSource@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `3199`
- prototype: `void __fastcall(CMFByteStreamMediaSource *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18014c600`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180037734`
- `0x1800378e4`
- `0x180037dec`
- `0x180060378`
- `0x18006085c`
- `0x180065a4c`
- `0x18006e194`
- `0x180079680`
- `0x1800892a0`
- `0x1800ab218`
- `0x1800ac3e4`
- `0x1800dc320`
- `0x1801495b8`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180089ee8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180089ee8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800892ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800892ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089329`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800893c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089489`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008953e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800895ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089694`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008973a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800897eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800898b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008999e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089a04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089af3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089bac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089c6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089d1b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089dd3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089329`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800893c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089489`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008953e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800895ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089694`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008973a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800897eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800898b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008999e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089a04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089af3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089bac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089c6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089d1b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089dd3`

## string_xrefs

- `0x1800892ba`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x180089797`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x180089848`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x18008990e`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x180089a61`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x180089ab1`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x180089b50`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x180089c09`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x180089cca`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x180089d78`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x180089e30`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`

## pseudocode

```c
void __fastcall CMFByteStreamMediaSource::OnByteStreamReadIndex(
        CMFByteStreamMediaSource *this,
        struct IMFAsyncResult *a2)
{
  __int64 v4; // rdx
  int CurrentPosition; // ebx
  wchar_t *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  wchar_t *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  unsigned __int64 v29; // rsi
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  CMFByteStreamSourceReader *v36; // rcx
  int v37; // esi
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  struct CallStackContext *v43; // rax
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  struct CMediaSourceOpStart **v50; // rdx
  wchar_t *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  wchar_t *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  wchar_t *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  CPendingLoadIndex *v60; // rcx
  CPendingLoadIndex *v61; // rcx
  unsigned int v62; // [rsp+30h] [rbp-20h] BYREF
  struct IMFMediaBuffer *v63; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int64 v64; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v65; // [rsp+48h] [rbp-8h] BYREF
  int v66; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v67; // [rsp+A0h] [rbp+50h] BYREF
  int v68; // [rsp+A8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v66,
    "CMFByteStreamMediaSource::OnByteStreamReadIndex",
    3149);
  v63 = 0;
  v62 = 0;
  v67 = 0;
  v64 = 0;
  v65 = 0;
  v68 = 0;
  v66 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
  CurrentPosition = CMFByteStreamMediaSource::CheckState(this);
  if ( CurrentPosition < 0 )
  {
    v6 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != CurrentPosition )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFByteStreamMediaSource::OnByteStreamReadIndex",
          3161,
          CurrentPosition);
    }
    if ( g_wppLevels )
    {
      v9 = 292;
LABEL_182:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
        this,
        CurrentPosition);
      goto LABEL_183;
    }
    goto LABEL_183;
  }
  if ( !a2 )
  {
    v10 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentPosition = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v12, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3163, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_184;
    v13 = 293;
LABEL_23:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
      this,
      CurrentPosition);
LABEL_184:
    v60 = (CPendingLoadIndex *)*((_QWORD *)this + 137);
    if ( v60 )
      CPendingLoadIndex::`scalar deleting destructor'(v60, v4);
    *((_QWORD *)this + 137) = 0;
    CMFByteStreamMediaSource::CompleteAsyncOperation(this, CurrentPosition);
    (*(void (__fastcall **)(CMFByteStreamMediaSource *, __int64, GUID *, _QWORD, _QWORD))(*(_QWORD *)this + 48LL))(
      this,
      1,
      &GUID_00000000_0000_0000_0000_000000000000,
      (unsigned int)CurrentPosition,
      0);
    goto LABEL_190;
  }
  if ( !*((_QWORD *)this + 137) )
  {
    v14 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentPosition = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
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
      v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)v16 + 499) != -1072875854 )
        CallStackContext::TraceFailure(v16, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3168, -1072875854);
    }
    if ( !g_wppLevels )
      goto LABEL_184;
    v13 = 294;
    goto LABEL_23;
  }
  CurrentPosition = CMFByteStreamSourceReader::EndReadData(
                      (CMFByteStreamMediaSource *)((char *)this + 1120),
                      a2,
                      &v63,
                      &v62);
  if ( CurrentPosition < 0 )
  {
    v17 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
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
      if ( *((_DWORD *)v19 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(v19, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3171, CurrentPosition);
    }
    if ( g_wppLevels )
    {
      v9 = 295;
      goto LABEL_182;
    }
LABEL_183:
    if ( (unsigned int)(CurrentPosition + 1072873852) <= 1 )
      goto LABEL_190;
    goto LABEL_184;
  }
  CurrentPosition = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, unsigned int *))v63->lpVtbl->GetCurrentLength)(
                      v63,
                      &v67);
  if ( CurrentPosition < 0 )
  {
    v20 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v21;
      if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
      {
        v20 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)v22 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(v22, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3176, CurrentPosition);
    }
    if ( g_wppLevels )
    {
      v9 = 296;
      goto LABEL_182;
    }
    goto LABEL_183;
  }
  CurrentPosition = CMFByteStreamSourceReader::GetCurrentPosition(
                      (CMFByteStreamMediaSource *)((char *)this + 1120),
                      &v64);
  if ( CurrentPosition < 0 )
  {
    v23 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v24;
      if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
      {
        v23 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v23 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v23 + 8) )
    {
      v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
      if ( *((_DWORD *)v25 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(v25, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3177, CurrentPosition);
    }
    if ( g_wppLevels )
    {
      v9 = 297;
      goto LABEL_182;
    }
    goto LABEL_183;
  }
  if ( v64 < v67 )
  {
    v26 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentPosition = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v27;
      if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
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
      if ( *((_DWORD *)v28 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v28, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3182, -2147418113);
    }
    if ( !g_wppLevels )
      goto LABEL_184;
    v13 = 298;
    goto LABEL_23;
  }
  v29 = v64 - v67;
  CurrentPosition = CMFByteStreamMediaSource::SetSaltValueOnSourcePlugin(this, a2, v63);
  if ( CurrentPosition < 0 )
  {
    v30 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v31;
      if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
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
      if ( *((_DWORD *)v32 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(v32, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3191, CurrentPosition);
    }
    if ( g_wppLevels )
    {
      v9 = 299;
      goto LABEL_182;
    }
    goto LABEL_183;
  }
  CurrentPosition = (*(__int64 (__fastcall **)(_QWORD, struct IMFMediaBuffer *, unsigned __int64, unsigned __int64 *, int *))(**((_QWORD **)this + 116) + 40LL))(
                      *((_QWORD *)this + 116),
                      v63,
                      v29,
                      &v65,
                      &v68);
  if ( CurrentPosition < 0 )
  {
    v33 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
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
      if ( *((_DWORD *)v35 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(v35, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3196, CurrentPosition);
    }
    if ( g_wppLevels )
    {
      v9 = 300;
      goto LABEL_182;
    }
    goto LABEL_183;
  }
  if ( v68 )
  {
    v36 = (CMFByteStreamMediaSource *)((char *)this + 1120);
    if ( v65 == -1 )
    {
      v37 = 0;
      CurrentPosition = CMFByteStreamSourceReader::IsEndOfFile(v36, &v66);
      if ( CurrentPosition < 0 )
      {
        v40 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
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
          if ( *((_DWORD *)v42 + 499) != CurrentPosition )
            CallStackContext::TraceFailure(
              v42,
              "CMFByteStreamMediaSource::OnByteStreamReadIndex",
              3213,
              CurrentPosition);
        }
        if ( g_wppLevels )
        {
          v9 = 301;
          goto LABEL_182;
        }
        goto LABEL_183;
      }
    }
    else
    {
      v37 = CMFByteStreamSourceReader::SetCurrentPosition(v36, v65, &v66);
    }
    if ( !v66 )
    {
      if ( v37 >= 0 )
      {
        CurrentPosition = CMFByteStreamSourceReader::BeginReadData(
                            (CMFByteStreamMediaSource *)((char *)this + 1120),
                            (struct IMFAsyncCallback *)this + 87,
                            *((_DWORD *)this + 276));
        if ( CurrentPosition >= 0 )
          goto LABEL_190;
        v47 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
          CallStackTracing::s_wpInstance = v48;
          if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
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
          if ( *((_DWORD *)v49 + 499) != CurrentPosition )
            CallStackContext::TraceFailure(
              v49,
              "CMFByteStreamMediaSource::OnByteStreamReadIndex",
              3235,
              CurrentPosition);
        }
        if ( !g_wppLevels )
          goto LABEL_183;
        v9 = 304;
        goto LABEL_182;
      }
      v44 = (wchar_t *)CallStackTracing::s_wpInstance;
      CurrentPosition = v37;
      if ( !CallStackTracing::s_wpInstance )
      {
        v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
        CallStackTracing::s_wpInstance = v45;
        if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
        {
          v44 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v44 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v44 + 8) )
      {
        v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
        if ( *((_DWORD *)v46 + 499) != v37 )
          CallStackContext::TraceFailure(v46, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3234, v37);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 303, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, this, v37);
      goto LABEL_183;
    }
    CurrentPosition = CMFByteStreamMediaSource::FinishPendingStart(
                        this,
                        1,
                        **((struct CMediaSourceOpStart ***)this + 137),
                        v66);
    if ( CurrentPosition < 0 )
    {
      v38 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
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
        v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
        if ( *((_DWORD *)v43 + 499) != CurrentPosition )
          CallStackContext::TraceFailure(v43, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3226, CurrentPosition);
      }
      if ( g_wppLevels )
      {
        v9 = 302;
        goto LABEL_182;
      }
      goto LABEL_183;
    }
  }
  else
  {
    v50 = (struct CMediaSourceOpStart **)*((_QWORD *)this + 137);
    v66 = 0;
    v64 = 0;
    CurrentPosition = CMFByteStreamMediaSource::DetermineOffsetForStartPosition(this, *v50, &v64, &v66);
    if ( CurrentPosition < 0 )
    {
      v51 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
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
        if ( *((_DWORD *)v53 + 499) != CurrentPosition )
          CallStackContext::TraceFailure(v53, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3243, CurrentPosition);
      }
      if ( g_wppLevels )
      {
        v9 = 305;
        goto LABEL_182;
      }
      goto LABEL_183;
    }
    CurrentPosition = CMFByteStreamSourceReader::SetCurrentPosition(
                        (CMFByteStreamMediaSource *)((char *)this + 1120),
                        v64,
                        0);
    if ( CurrentPosition < 0 )
    {
      v54 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
        CallStackTracing::s_wpInstance = v55;
        if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
        {
          v54 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v54 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v54 + 8) )
      {
        v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
        if ( *((_DWORD *)v56 + 499) != CurrentPosition )
          CallStackContext::TraceFailure(v56, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3247, CurrentPosition);
      }
      if ( g_wppLevels )
      {
        v9 = 306;
        goto LABEL_182;
      }
      goto LABEL_183;
    }
    CurrentPosition = CMFByteStreamMediaSource::FinishPendingStart(
                        this,
                        1,
                        **((struct CMediaSourceOpStart ***)this + 137),
                        0);
    if ( CurrentPosition < 0 )
    {
      v57 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
        CallStackTracing::s_wpInstance = v58;
        if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
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
        if ( *((_DWORD *)v59 + 499) != CurrentPosition )
          CallStackContext::TraceFailure(v59, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3249, CurrentPosition);
      }
      if ( g_wppLevels )
      {
        v9 = 307;
        goto LABEL_182;
      }
      goto LABEL_183;
    }
  }
  v61 = (CPendingLoadIndex *)*((_QWORD *)this + 137);
  if ( v61 )
    CPendingLoadIndex::`scalar deleting destructor'(v61, v4);
  *((_QWORD *)this + 137) = 0;
  CMFByteStreamMediaSource::CompleteAsyncOperation(this, CurrentPosition);
LABEL_190:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v63);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v66);
}

```

## disassembly

```asm
0x1800892a0  mov     [rsp-38h+arg_8], rbx
0x1800892a5  push    rbp
0x1800892a6  push    rsi
0x1800892a7  push    rdi
0x1800892a8  push    r12
0x1800892aa  push    r13
0x1800892ac  push    r14
0x1800892ae  push    r15
0x1800892b0  mov     rbp, rsp
0x1800892b3  sub     rsp, 50h
0x1800892b7  mov     r15, rdx
0x1800892ba  lea     rsi, aCmfbytestreamm_60; "CMFByteStreamMediaSource::OnByteStreamR"...
0x1800892c1  mov     rdi, rcx
0x1800892c4  mov     rdx, rsi; char *
0x1800892c7  mov     r8d, 0C4Dh; int
0x1800892cd  lea     rcx, [rbp+arg_0]; this
0x1800892d1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800892d6  xor     r13d, r13d
0x1800892d9  lea     r12, [rdi+2C8h]
0x1800892e0  mov     rcx, r12; lpCriticalSection
0x1800892e3  mov     [rbp+var_18], r13
0x1800892e7  mov     [rbp+var_20], r13d
0x1800892eb  mov     [rbp+arg_10], r13d
0x1800892ef  mov     [rbp+var_10], r13
0x1800892f3  mov     [rbp+var_8], r13
0x1800892f7  mov     [rbp+arg_18], r13d
0x1800892fb  mov     [rbp+arg_0], r13d
0x1800892ff  call    cs:__imp_EnterCriticalSection
0x180089306  nop     dword ptr [rax+rax+00h]
0x18008930b  mov     rcx, rdi; this
0x18008930e  call    ?CheckState@CMFByteStreamMediaSource@@AEAAJXZ; CMFByteStreamMediaSource::CheckState(void)
0x180089313  mov     ebx, eax
0x180089315  test    eax, eax
0x180089317  jns     loc_1800893AE
0x18008931d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089324  test    rcx, rcx
0x180089327  jnz     short loc_180089370
0x180089329  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089330  nop     dword ptr [rax+rax+00h]
0x180089335  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008933c  mov     rcx, rax
0x18008933f  test    rax, rax
0x180089342  jz      short loc_180089362
0x180089344  mov     rax, [rax]
0x180089347  mov     edx, 7F0h
0x18008934c  mov     rax, [rax+8]
0x180089350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089355  test    eax, eax
0x180089357  jz      short loc_180089362
0x180089359  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089360  jmp     short loc_180089370
0x180089362  lea     rcx, qword_1801B97E0; this
0x180089369  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089370  cmp     [rcx+8], r13b
0x180089374  jz      short loc_180089397
0x180089376  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008937b  cmp     [rax+7CCh], ebx
0x180089381  jz      short loc_180089397
0x180089383  mov     r9d, ebx; int
0x180089386  mov     r8d, 0C59h; int
0x18008938c  mov     rdx, rsi; char *
0x18008938f  mov     rcx, rax; this
0x180089392  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180089397  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008939e  jb      loc_180089E71
0x1800893a4  mov     edx, 124h
0x1800893a9  jmp     loc_180089E53
0x1800893ae  test    r15, r15
0x1800893b1  jnz     loc_18008946B
0x1800893b7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800893be  mov     ebx, 80004003h
0x1800893c3  test    rcx, rcx
0x1800893c6  jnz     short loc_18008940F
0x1800893c8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800893cf  nop     dword ptr [rax+rax+00h]
0x1800893d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800893db  mov     rcx, rax
0x1800893de  test    rax, rax
0x1800893e1  jz      short loc_180089401
0x1800893e3  mov     rax, [rax]
0x1800893e6  mov     edx, 7F0h
0x1800893eb  mov     rax, [rax+8]
0x1800893ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800893f4  test    eax, eax
0x1800893f6  jz      short loc_180089401
0x1800893f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800893ff  jmp     short loc_18008940F
0x180089401  lea     rcx, qword_1801B97E0; this
0x180089408  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008940f  cmp     [rcx+8], r13b
0x180089413  jz      short loc_180089436
0x180089415  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008941a  cmp     [rax+7CCh], ebx
0x180089420  jz      short loc_180089436
0x180089422  mov     r9d, ebx; int
0x180089425  mov     r8d, 0C5Bh; int
0x18008942b  mov     rdx, rsi; char *
0x18008942e  mov     rcx, rax; this
0x180089431  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180089436  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008943d  jb      loc_180089E7C
0x180089443  mov     edx, 125h
0x180089448  mov     rcx, cs:WPP_GLOBAL_Control
0x18008944f  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x180089456  mov     r9, rdi
0x180089459  mov     dword ptr [rsp+50h+var_30], ebx
0x18008945d  mov     rcx, [rcx+10h]
0x180089461  call    WPP_SF_qD
0x180089466  jmp     loc_180089E7C
0x18008946b  cmp     [rdi+448h], r13
0x180089472  jnz     loc_18008950E
0x180089478  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008947f  mov     ebx, 0C00D36B2h
0x180089484  test    rcx, rcx
0x180089487  jnz     short loc_1800894D0
0x180089489  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089490  nop     dword ptr [rax+rax+00h]
0x180089495  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008949c  mov     rcx, rax
0x18008949f  test    rax, rax
0x1800894a2  jz      short loc_1800894C2
0x1800894a4  mov     rax, [rax]
0x1800894a7  mov     edx, 7F0h
0x1800894ac  mov     rax, [rax+8]
0x1800894b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800894b5  test    eax, eax
0x1800894b7  jz      short loc_1800894C2
0x1800894b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800894c0  jmp     short loc_1800894D0
0x1800894c2  lea     rcx, qword_1801B97E0; this
0x1800894c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800894d0  cmp     [rcx+8], r13b
0x1800894d4  jz      short loc_1800894F7
0x1800894d6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800894db  cmp     [rax+7CCh], ebx
0x1800894e1  jz      short loc_1800894F7
0x1800894e3  mov     r9d, ebx; int
0x1800894e6  mov     r8d, 0C60h; int
0x1800894ec  mov     rdx, rsi; char *
0x1800894ef  mov     rcx, rax; this
0x1800894f2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800894f7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800894fe  jb      loc_180089E7C
0x180089504  mov     edx, 126h
0x180089509  jmp     loc_180089448
0x18008950e  lea     r14, [rdi+460h]
0x180089515  mov     rdx, r15; struct IMFAsyncResult *
0x180089518  mov     rcx, r14; this
0x18008951b  lea     r9, [rbp+var_20]; unsigned int *
0x18008951f  lea     r8, [rbp+var_18]; struct IMFMediaBuffer **
0x180089523  call    ?EndReadData@CMFByteStreamSourceReader@@QEAAJPEAUIMFAsyncResult@@PEAPEAUIMFMediaBuffer@@PEAK@Z; CMFByteStreamSourceReader::EndReadData(IMFAsyncResult *,IMFMediaBuffer * *,ulong *)
0x180089528  mov     ebx, eax
0x18008952a  test    eax, eax
0x18008952c  jns     loc_1800895C3
0x180089532  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089539  test    rcx, rcx
0x18008953c  jnz     short loc_180089585
0x18008953e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089545  nop     dword ptr [rax+rax+00h]
0x18008954a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089551  mov     rcx, rax
0x180089554  test    rax, rax
0x180089557  jz      short loc_180089577
0x180089559  mov     rax, [rax]
0x18008955c  mov     edx, 7F0h
0x180089561  mov     rax, [rax+8]
0x180089565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008956a  test    eax, eax
0x18008956c  jz      short loc_180089577
0x18008956e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089575  jmp     short loc_180089585
0x180089577  lea     rcx, qword_1801B97E0; this
0x18008957e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089585  cmp     [rcx+8], r13b
0x180089589  jz      short loc_1800895AC
0x18008958b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089590  cmp     [rax+7CCh], ebx
0x180089596  jz      short loc_1800895AC
0x180089598  mov     r9d, ebx; int
0x18008959b  mov     r8d, 0C63h; int
0x1800895a1  mov     rdx, rsi; char *
0x1800895a4  mov     rcx, rax; this
0x1800895a7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800895ac  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800895b3  jb      loc_180089E71
0x1800895b9  mov     edx, 127h
0x1800895be  jmp     loc_180089E53
0x1800895c3  mov     rcx, [rbp+var_18]
0x1800895c7  lea     rdx, [rbp+arg_10]
0x1800895cb  mov     rax, [rcx]
0x1800895ce  mov     rax, [rax+28h]
0x1800895d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800895d7  mov     ebx, eax
0x1800895d9  test    eax, eax
0x1800895db  jns     loc_180089672
0x1800895e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800895e8  test    rcx, rcx
0x1800895eb  jnz     short loc_180089634
0x1800895ed  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800895f4  nop     dword ptr [rax+rax+00h]
0x1800895f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089600  mov     rcx, rax
0x180089603  test    rax, rax
0x180089606  jz      short loc_180089626
0x180089608  mov     rax, [rax]
0x18008960b  mov     edx, 7F0h
0x180089610  mov     rax, [rax+8]
0x180089614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089619  test    eax, eax
0x18008961b  jz      short loc_180089626
0x18008961d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089624  jmp     short loc_180089634
0x180089626  lea     rcx, qword_1801B97E0; this
0x18008962d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089634  cmp     [rcx+8], r13b
0x180089638  jz      short loc_18008965B
0x18008963a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008963f  cmp     [rax+7CCh], ebx
0x180089645  jz      short loc_18008965B
0x180089647  mov     r9d, ebx; int
0x18008964a  mov     r8d, 0C68h; int
0x180089650  mov     rdx, rsi; char *
0x180089653  mov     rcx, rax; this
0x180089656  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008965b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180089662  jb      loc_180089E71
0x180089668  mov     edx, 128h
0x18008966d  jmp     loc_180089E53
0x180089672  lea     rdx, [rbp+var_10]; unsigned __int64 *
0x180089676  mov     rcx, r14; this
0x180089679  call    ?GetCurrentPosition@CMFByteStreamSourceReader@@QEAAJPEA_K@Z; CMFByteStreamSourceReader::GetCurrentPosition(unsigned __int64 *)
0x18008967e  mov     ebx, eax
0x180089680  test    eax, eax
0x180089682  jns     loc_180089719
0x180089688  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008968f  test    rcx, rcx
0x180089692  jnz     short loc_1800896DB
0x180089694  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008969b  nop     dword ptr [rax+rax+00h]
0x1800896a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800896a7  mov     rcx, rax
0x1800896aa  test    rax, rax
0x1800896ad  jz      short loc_1800896CD
0x1800896af  mov     rax, [rax]
0x1800896b2  mov     edx, 7F0h
0x1800896b7  mov     rax, [rax+8]
0x1800896bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800896c0  test    eax, eax
0x1800896c2  jz      short loc_1800896CD
0x1800896c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800896cb  jmp     short loc_1800896DB
0x1800896cd  lea     rcx, qword_1801B97E0; this
0x1800896d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800896db  cmp     [rcx+8], r13b
0x1800896df  jz      short loc_180089702
0x1800896e1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800896e6  cmp     [rax+7CCh], ebx
0x1800896ec  jz      short loc_180089702
0x1800896ee  mov     r9d, ebx; int
0x1800896f1  mov     r8d, 0C69h; int
0x1800896f7  mov     rdx, rsi; char *
0x1800896fa  mov     rcx, rax; this
0x1800896fd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180089702  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180089709  jb      loc_180089E71
0x18008970f  mov     edx, 129h
0x180089714  jmp     loc_180089E53
0x180089719  mov     eax, [rbp+arg_10]
0x18008971c  mov     rsi, [rbp+var_10]
0x180089720  cmp     rsi, rax
0x180089723  jnb     loc_1800897C3
0x180089729  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089730  mov     ebx, 8000FFFFh
0x180089735  test    rcx, rcx
0x180089738  jnz     short loc_180089781
0x18008973a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089741  nop     dword ptr [rax+rax+00h]
0x180089746  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008974d  mov     rcx, rax
0x180089750  test    rax, rax
0x180089753  jz      short loc_180089773
0x180089755  mov     rax, [rax]
0x180089758  mov     edx, 7F0h
0x18008975d  mov     rax, [rax+8]
0x180089761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089766  test    eax, eax
0x180089768  jz      short loc_180089773
0x18008976a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089771  jmp     short loc_180089781
0x180089773  lea     rcx, qword_1801B97E0; this
0x18008977a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089781  cmp     [rcx+8], r13b
0x180089785  jz      short loc_1800897AC
0x180089787  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008978c  cmp     [rax+7CCh], ebx
0x180089792  jz      short loc_1800897AC
0x180089794  mov     r9d, ebx; int
0x180089797  lea     rdx, aCmfbytestreamm_60; "CMFByteStreamMediaSource::OnByteStreamR"...
0x18008979e  mov     r8d, 0C6Eh; int
0x1800897a4  mov     rcx, rax; this
  ... truncated ...
```
