# CMFByteStreamMediaSource::OnByteStreamReadIndex(IMFAsyncResult *)

- ea: `0x1800846ec`
- end: `0x1800852fe`
- name: `?OnByteStreamReadIndex@CMFByteStreamMediaSource@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `3090`
- prototype: `void __fastcall(CMFByteStreamMediaSource *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180144660`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x18005ca98`
- `0x18005cf64`
- `0x18005d7f0`
- `0x18005d990`
- `0x18005de70`
- `0x1800649c4`
- `0x18006c93c`
- `0x180073b14`
- `0x1800846ec`
- `0x1800a617c`
- `0x1800a72d0`
- `0x1800d6114`
- `0x180141818`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800852ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800852ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008474b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008474b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008476f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084808`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800848c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084972`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084a1b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084abc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084b5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084c07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084cc7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084dae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084e0e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084ef7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084faa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085065`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008510d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800851bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008476f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084808`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800848c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084972`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084a1b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084abc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084b5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084c07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084cc7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084dae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084e0e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084ef7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084faa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085065`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008510d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800851bf`

## string_xrefs

- `0x180084706`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x180084bb3`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x180084c5e`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x180084d1e`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x180084e65`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x180084eb5`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x180084f4e`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x180085001`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x1800850bc`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x180085164`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`
- `0x180085216`: `CMFByteStreamMediaSource::OnByteStreamReadIndex`

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
        v6 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v10 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v14 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v17 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v20 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v23 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v26 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v30 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v33 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v40 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v47 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v44 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v38 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v51 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v54 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v57 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x1800846ec  mov     [rsp-38h+arg_8], rbx
0x1800846f1  push    rbp
0x1800846f2  push    rsi
0x1800846f3  push    rdi
0x1800846f4  push    r12
0x1800846f6  push    r13
0x1800846f8  push    r14
0x1800846fa  push    r15
0x1800846fc  mov     rbp, rsp
0x1800846ff  sub     rsp, 50h
0x180084703  mov     r15, rdx
0x180084706  lea     rsi, aCmfbytestreamm_60; "CMFByteStreamMediaSource::OnByteStreamR"...
0x18008470d  mov     rdi, rcx
0x180084710  mov     rdx, rsi; char *
0x180084713  mov     r8d, 0C4Dh; int
0x180084719  lea     rcx, [rbp+arg_0]; this
0x18008471d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180084722  xor     r13d, r13d
0x180084725  lea     r12, [rdi+2C8h]
0x18008472c  mov     rcx, r12; lpCriticalSection
0x18008472f  mov     [rbp+var_18], r13
0x180084733  mov     [rbp+var_20], r13d
0x180084737  mov     [rbp+arg_10], r13d
0x18008473b  mov     [rbp+var_10], r13
0x18008473f  mov     [rbp+var_8], r13
0x180084743  mov     [rbp+arg_18], r13d
0x180084747  mov     [rbp+arg_0], r13d
0x18008474b  call    cs:__imp_EnterCriticalSection
0x180084751  mov     rcx, rdi; this
0x180084754  call    ?CheckState@CMFByteStreamMediaSource@@AEAAJXZ; CMFByteStreamMediaSource::CheckState(void)
0x180084759  mov     ebx, eax
0x18008475b  test    eax, eax
0x18008475d  jns     loc_1800847EE
0x180084763  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008476a  test    rcx, rcx
0x18008476d  jnz     short loc_1800847B0
0x18008476f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084775  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008477c  mov     rcx, rax
0x18008477f  test    rax, rax
0x180084782  jz      short loc_1800847A2
0x180084784  mov     rax, [rax]
0x180084787  mov     edx, 7F0h
0x18008478c  mov     rax, [rax+8]
0x180084790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084795  test    eax, eax
0x180084797  jz      short loc_1800847A2
0x180084799  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800847a0  jmp     short loc_1800847B0
0x1800847a2  lea     rcx, qword_1801B07E0; this
0x1800847a9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800847b0  cmp     [rcx+8], r13b
0x1800847b4  jz      short loc_1800847D7
0x1800847b6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800847bb  cmp     [rax+7CCh], ebx
0x1800847c1  jz      short loc_1800847D7
0x1800847c3  mov     r9d, ebx; int
0x1800847c6  mov     r8d, 0C59h; int
0x1800847cc  mov     rdx, rsi; char *
0x1800847cf  mov     rcx, rax; this
0x1800847d2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800847d7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800847de  jb      loc_180085257
0x1800847e4  mov     edx, 124h
0x1800847e9  jmp     loc_180085239
0x1800847ee  test    r15, r15
0x1800847f1  jnz     loc_1800848A5
0x1800847f7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800847fe  mov     ebx, 80004003h
0x180084803  test    rcx, rcx
0x180084806  jnz     short loc_180084849
0x180084808  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008480e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180084815  mov     rcx, rax
0x180084818  test    rax, rax
0x18008481b  jz      short loc_18008483B
0x18008481d  mov     rax, [rax]
0x180084820  mov     edx, 7F0h
0x180084825  mov     rax, [rax+8]
0x180084829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008482e  test    eax, eax
0x180084830  jz      short loc_18008483B
0x180084832  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084839  jmp     short loc_180084849
0x18008483b  lea     rcx, qword_1801B07E0; this
0x180084842  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084849  cmp     [rcx+8], r13b
0x18008484d  jz      short loc_180084870
0x18008484f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084854  cmp     [rax+7CCh], ebx
0x18008485a  jz      short loc_180084870
0x18008485c  mov     r9d, ebx; int
0x18008485f  mov     r8d, 0C5Bh; int
0x180084865  mov     rdx, rsi; char *
0x180084868  mov     rcx, rax; this
0x18008486b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180084870  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180084877  jb      loc_180085262
0x18008487d  mov     edx, 125h
0x180084882  mov     rcx, cs:WPP_GLOBAL_Control
0x180084889  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x180084890  mov     r9, rdi
0x180084893  mov     dword ptr [rsp+50h+var_30], ebx
0x180084897  mov     rcx, [rcx+10h]
0x18008489b  call    WPP_SF_qD
0x1800848a0  jmp     loc_180085262
0x1800848a5  cmp     [rdi+448h], r13
0x1800848ac  jnz     loc_180084942
0x1800848b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800848b9  mov     ebx, 0C00D36B2h
0x1800848be  test    rcx, rcx
0x1800848c1  jnz     short loc_180084904
0x1800848c3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800848c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800848d0  mov     rcx, rax
0x1800848d3  test    rax, rax
0x1800848d6  jz      short loc_1800848F6
0x1800848d8  mov     rax, [rax]
0x1800848db  mov     edx, 7F0h
0x1800848e0  mov     rax, [rax+8]
0x1800848e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800848e9  test    eax, eax
0x1800848eb  jz      short loc_1800848F6
0x1800848ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800848f4  jmp     short loc_180084904
0x1800848f6  lea     rcx, qword_1801B07E0; this
0x1800848fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084904  cmp     [rcx+8], r13b
0x180084908  jz      short loc_18008492B
0x18008490a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008490f  cmp     [rax+7CCh], ebx
0x180084915  jz      short loc_18008492B
0x180084917  mov     r9d, ebx; int
0x18008491a  mov     r8d, 0C60h; int
0x180084920  mov     rdx, rsi; char *
0x180084923  mov     rcx, rax; this
0x180084926  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008492b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180084932  jb      loc_180085262
0x180084938  mov     edx, 126h
0x18008493d  jmp     loc_180084882
0x180084942  lea     r14, [rdi+460h]
0x180084949  mov     rdx, r15; struct IMFAsyncResult *
0x18008494c  mov     rcx, r14; this
0x18008494f  lea     r9, [rbp+var_20]; unsigned int *
0x180084953  lea     r8, [rbp+var_18]; struct IMFMediaBuffer **
0x180084957  call    ?EndReadData@CMFByteStreamSourceReader@@QEAAJPEAUIMFAsyncResult@@PEAPEAUIMFMediaBuffer@@PEAK@Z; CMFByteStreamSourceReader::EndReadData(IMFAsyncResult *,IMFMediaBuffer * *,ulong *)
0x18008495c  mov     ebx, eax
0x18008495e  test    eax, eax
0x180084960  jns     loc_1800849F1
0x180084966  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008496d  test    rcx, rcx
0x180084970  jnz     short loc_1800849B3
0x180084972  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084978  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008497f  mov     rcx, rax
0x180084982  test    rax, rax
0x180084985  jz      short loc_1800849A5
0x180084987  mov     rax, [rax]
0x18008498a  mov     edx, 7F0h
0x18008498f  mov     rax, [rax+8]
0x180084993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084998  test    eax, eax
0x18008499a  jz      short loc_1800849A5
0x18008499c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800849a3  jmp     short loc_1800849B3
0x1800849a5  lea     rcx, qword_1801B07E0; this
0x1800849ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800849b3  cmp     [rcx+8], r13b
0x1800849b7  jz      short loc_1800849DA
0x1800849b9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800849be  cmp     [rax+7CCh], ebx
0x1800849c4  jz      short loc_1800849DA
0x1800849c6  mov     r9d, ebx; int
0x1800849c9  mov     r8d, 0C63h; int
0x1800849cf  mov     rdx, rsi; char *
0x1800849d2  mov     rcx, rax; this
0x1800849d5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800849da  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800849e1  jb      loc_180085257
0x1800849e7  mov     edx, 127h
0x1800849ec  jmp     loc_180085239
0x1800849f1  mov     rcx, [rbp+var_18]
0x1800849f5  lea     rdx, [rbp+arg_10]
0x1800849f9  mov     rax, [rcx]
0x1800849fc  mov     rax, [rax+28h]
0x180084a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084a05  mov     ebx, eax
0x180084a07  test    eax, eax
0x180084a09  jns     loc_180084A9A
0x180084a0f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084a16  test    rcx, rcx
0x180084a19  jnz     short loc_180084A5C
0x180084a1b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084a21  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180084a28  mov     rcx, rax
0x180084a2b  test    rax, rax
0x180084a2e  jz      short loc_180084A4E
0x180084a30  mov     rax, [rax]
0x180084a33  mov     edx, 7F0h
0x180084a38  mov     rax, [rax+8]
0x180084a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084a41  test    eax, eax
0x180084a43  jz      short loc_180084A4E
0x180084a45  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084a4c  jmp     short loc_180084A5C
0x180084a4e  lea     rcx, qword_1801B07E0; this
0x180084a55  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084a5c  cmp     [rcx+8], r13b
0x180084a60  jz      short loc_180084A83
0x180084a62  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084a67  cmp     [rax+7CCh], ebx
0x180084a6d  jz      short loc_180084A83
0x180084a6f  mov     r9d, ebx; int
0x180084a72  mov     r8d, 0C68h; int
0x180084a78  mov     rdx, rsi; char *
0x180084a7b  mov     rcx, rax; this
0x180084a7e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180084a83  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180084a8a  jb      loc_180085257
0x180084a90  mov     edx, 128h
0x180084a95  jmp     loc_180085239
0x180084a9a  lea     rdx, [rbp+var_10]; unsigned __int64 *
0x180084a9e  mov     rcx, r14; this
0x180084aa1  call    ?GetCurrentPosition@CMFByteStreamSourceReader@@QEAAJPEA_K@Z; CMFByteStreamSourceReader::GetCurrentPosition(unsigned __int64 *)
0x180084aa6  mov     ebx, eax
0x180084aa8  test    eax, eax
0x180084aaa  jns     loc_180084B3B
0x180084ab0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084ab7  test    rcx, rcx
0x180084aba  jnz     short loc_180084AFD
0x180084abc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084ac2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180084ac9  mov     rcx, rax
0x180084acc  test    rax, rax
0x180084acf  jz      short loc_180084AEF
0x180084ad1  mov     rax, [rax]
0x180084ad4  mov     edx, 7F0h
0x180084ad9  mov     rax, [rax+8]
0x180084add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084ae2  test    eax, eax
0x180084ae4  jz      short loc_180084AEF
0x180084ae6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084aed  jmp     short loc_180084AFD
0x180084aef  lea     rcx, qword_1801B07E0; this
0x180084af6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084afd  cmp     [rcx+8], r13b
0x180084b01  jz      short loc_180084B24
0x180084b03  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084b08  cmp     [rax+7CCh], ebx
0x180084b0e  jz      short loc_180084B24
0x180084b10  mov     r9d, ebx; int
0x180084b13  mov     r8d, 0C69h; int
0x180084b19  mov     rdx, rsi; char *
0x180084b1c  mov     rcx, rax; this
0x180084b1f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180084b24  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180084b2b  jb      loc_180085257
0x180084b31  mov     edx, 129h
0x180084b36  jmp     loc_180085239
0x180084b3b  mov     eax, [rbp+arg_10]
0x180084b3e  mov     rsi, [rbp+var_10]
0x180084b42  cmp     rsi, rax
0x180084b45  jnb     loc_180084BDF
0x180084b4b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084b52  mov     ebx, 8000FFFFh
0x180084b57  test    rcx, rcx
0x180084b5a  jnz     short loc_180084B9D
0x180084b5c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084b62  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180084b69  mov     rcx, rax
0x180084b6c  test    rax, rax
0x180084b6f  jz      short loc_180084B8F
0x180084b71  mov     rax, [rax]
0x180084b74  mov     edx, 7F0h
0x180084b79  mov     rax, [rax+8]
0x180084b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084b82  test    eax, eax
0x180084b84  jz      short loc_180084B8F
0x180084b86  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084b8d  jmp     short loc_180084B9D
0x180084b8f  lea     rcx, qword_1801B07E0; this
0x180084b96  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084b9d  cmp     [rcx+8], r13b
0x180084ba1  jz      short loc_180084BC8
0x180084ba3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084ba8  cmp     [rax+7CCh], ebx
0x180084bae  jz      short loc_180084BC8
0x180084bb0  mov     r9d, ebx; int
0x180084bb3  lea     rdx, aCmfbytestreamm_60; "CMFByteStreamMediaSource::OnByteStreamR"...
0x180084bba  mov     r8d, 0C6Eh; int
0x180084bc0  mov     rcx, rax; this
0x180084bc3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180084bc8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180084bcf  jb      loc_180085262
0x180084bd5  mov     edx, 12Ah
0x180084bda  jmp     loc_180084882
0x180084bdf  mov     r8, [rbp+var_18]; struct IMFMediaBuffer *
0x180084be3  mov     rdx, r15; struct IMFAsyncResult *
0x180084be6  mov     rcx, rdi; this
  ... truncated ...
```
