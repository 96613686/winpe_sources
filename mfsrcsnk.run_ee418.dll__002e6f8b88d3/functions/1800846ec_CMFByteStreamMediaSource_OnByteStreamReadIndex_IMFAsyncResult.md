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
  __int64 v6; // r8
  __int64 v7; // r9
  wchar_t *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // r8
  __int64 v25; // r9
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // r8
  __int64 v30; // r9
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  unsigned __int64 v37; // rsi
  __int64 v38; // r8
  __int64 v39; // r9
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // r8
  __int64 v44; // r9
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  CMFByteStreamSourceReader *v48; // rcx
  int v49; // esi
  __int64 v50; // r8
  __int64 v51; // r8
  __int64 v52; // r9
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  __int64 v55; // r9
  wchar_t *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  struct CallStackContext *v59; // rax
  wchar_t *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  __int64 v63; // r8
  __int64 v64; // r9
  wchar_t *v65; // rcx
  CallStackTracing *v66; // rax
  struct CallStackContext *v67; // rax
  struct CMediaSourceOpStart **v68; // rdx
  __int64 v69; // r8
  __int64 v70; // r9
  wchar_t *v71; // rcx
  CallStackTracing *v72; // rax
  struct CallStackContext *v73; // rax
  __int64 v74; // r8
  __int64 v75; // r9
  wchar_t *v76; // rcx
  CallStackTracing *v77; // rax
  struct CallStackContext *v78; // rax
  __int64 v79; // r8
  __int64 v80; // r9
  wchar_t *v81; // rcx
  CallStackTracing *v82; // rax
  struct CallStackContext *v83; // rax
  CPendingLoadIndex *v84; // rcx
  CPendingLoadIndex *v85; // rcx
  unsigned int v86; // [rsp+30h] [rbp-20h] BYREF
  struct IMFMediaBuffer *v87; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int64 v88; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v89; // [rsp+48h] [rbp-8h] BYREF
  int v90; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v91; // [rsp+A0h] [rbp+50h] BYREF
  int v92; // [rsp+A8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v90,
    "CMFByteStreamMediaSource::OnByteStreamReadIndex",
    3149);
  v87 = 0;
  v86 = 0;
  v91 = 0;
  v88 = 0;
  v89 = 0;
  v92 = 0;
  v90 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
  CurrentPosition = CMFByteStreamMediaSource::CheckState(this);
  if ( CurrentPosition < 0 )
  {
    v8 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != CurrentPosition )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFByteStreamMediaSource::OnByteStreamReadIndex",
          3161,
          CurrentPosition);
    }
    if ( g_wppLevels )
    {
      v11 = 292;
LABEL_182:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
        this,
        CurrentPosition);
      goto LABEL_183;
    }
    goto LABEL_183;
  }
  if ( !a2 )
  {
    v12 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentPosition = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
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
      if ( *((_DWORD *)v14 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v14, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3163, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_184;
    v15 = 293;
LABEL_23:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
      this,
      CurrentPosition);
LABEL_184:
    v84 = (CPendingLoadIndex *)*((_QWORD *)this + 137);
    if ( v84 )
      CPendingLoadIndex::`scalar deleting destructor'(v84, v4);
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
    v16 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentPosition = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
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
      if ( *((_DWORD *)v18 + 499) != -1072875854 )
        CallStackContext::TraceFailure(v18, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3168, -1072875854);
    }
    if ( !g_wppLevels )
      goto LABEL_184;
    v15 = 294;
    goto LABEL_23;
  }
  CurrentPosition = CMFByteStreamSourceReader::EndReadData(
                      (CMFByteStreamMediaSource *)((char *)this + 1120),
                      a2,
                      &v87,
                      &v86);
  if ( CurrentPosition < 0 )
  {
    v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v19, v20);
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
      if ( *((_DWORD *)v23 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(v23, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3171, CurrentPosition);
    }
    if ( g_wppLevels )
    {
      v11 = 295;
      goto LABEL_182;
    }
LABEL_183:
    if ( (unsigned int)(CurrentPosition + 1072873852) <= 1 )
      goto LABEL_190;
    goto LABEL_184;
  }
  CurrentPosition = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, unsigned int *))v87->lpVtbl->GetCurrentLength)(
                      v87,
                      &v91);
  if ( CurrentPosition < 0 )
  {
    v26 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v24, v25);
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
      if ( *((_DWORD *)v28 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(v28, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3176, CurrentPosition);
    }
    if ( g_wppLevels )
    {
      v11 = 296;
      goto LABEL_182;
    }
    goto LABEL_183;
  }
  CurrentPosition = CMFByteStreamSourceReader::GetCurrentPosition(
                      (CMFByteStreamMediaSource *)((char *)this + 1120),
                      &v88);
  if ( CurrentPosition < 0 )
  {
    v31 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v29, v30);
      CallStackTracing::s_wpInstance = v32;
      if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
      {
        v31 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v31 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v31 + 8) )
    {
      v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
      if ( *((_DWORD *)v33 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(v33, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3177, CurrentPosition);
    }
    if ( g_wppLevels )
    {
      v11 = 297;
      goto LABEL_182;
    }
    goto LABEL_183;
  }
  if ( v88 < v91 )
  {
    v34 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentPosition = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v29, v30);
      CallStackTracing::s_wpInstance = v35;
      if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
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
      if ( *((_DWORD *)v36 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v36, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3182, -2147418113);
    }
    if ( !g_wppLevels )
      goto LABEL_184;
    v15 = 298;
    goto LABEL_23;
  }
  v37 = v88 - v91;
  CurrentPosition = CMFByteStreamMediaSource::SetSaltValueOnSourcePlugin(this, a2, v87);
  if ( CurrentPosition < 0 )
  {
    v40 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v38, v39);
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
        CallStackContext::TraceFailure(v42, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3191, CurrentPosition);
    }
    if ( g_wppLevels )
    {
      v11 = 299;
      goto LABEL_182;
    }
    goto LABEL_183;
  }
  CurrentPosition = (*(__int64 (__fastcall **)(_QWORD, struct IMFMediaBuffer *, unsigned __int64, unsigned __int64 *, int *))(**((_QWORD **)this + 116) + 40LL))(
                      *((_QWORD *)this + 116),
                      v87,
                      v37,
                      &v89,
                      &v92);
  if ( CurrentPosition < 0 )
  {
    v45 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v43, v44);
      CallStackTracing::s_wpInstance = v46;
      if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
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
      if ( *((_DWORD *)v47 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(v47, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3196, CurrentPosition);
    }
    if ( g_wppLevels )
    {
      v11 = 300;
      goto LABEL_182;
    }
    goto LABEL_183;
  }
  if ( v92 )
  {
    v48 = (CMFByteStreamMediaSource *)((char *)this + 1120);
    if ( v89 == -1 )
    {
      v49 = 0;
      CurrentPosition = CMFByteStreamSourceReader::IsEndOfFile(v48, &v90);
      if ( CurrentPosition < 0 )
      {
        v56 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v50, v55);
          CallStackTracing::s_wpInstance = v57;
          if ( v57 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
          {
            v56 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v56 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v56 + 8) )
        {
          v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
          if ( *((_DWORD *)v58 + 499) != CurrentPosition )
            CallStackContext::TraceFailure(
              v58,
              "CMFByteStreamMediaSource::OnByteStreamReadIndex",
              3213,
              CurrentPosition);
        }
        if ( g_wppLevels )
        {
          v11 = 301;
          goto LABEL_182;
        }
        goto LABEL_183;
      }
    }
    else
    {
      v49 = CMFByteStreamSourceReader::SetCurrentPosition(v48, v89, &v90);
    }
    if ( !v90 )
    {
      if ( v49 >= 0 )
      {
        CurrentPosition = CMFByteStreamSourceReader::BeginReadData(
                            (CMFByteStreamMediaSource *)((char *)this + 1120),
                            (struct IMFAsyncCallback *)this + 87,
                            *((_DWORD *)this + 276));
        if ( CurrentPosition >= 0 )
          goto LABEL_190;
        v65 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v63, v64);
          CallStackTracing::s_wpInstance = v66;
          if ( v66 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v66 + 8LL))(v66, 2032) )
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
          if ( *((_DWORD *)v67 + 499) != CurrentPosition )
            CallStackContext::TraceFailure(
              v67,
              "CMFByteStreamMediaSource::OnByteStreamReadIndex",
              3235,
              CurrentPosition);
        }
        if ( !g_wppLevels )
          goto LABEL_183;
        v11 = 304;
        goto LABEL_182;
      }
      v60 = (wchar_t *)CallStackTracing::s_wpInstance;
      CurrentPosition = v49;
      if ( !CallStackTracing::s_wpInstance )
      {
        v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v50, (unsigned int)v90);
        CallStackTracing::s_wpInstance = v61;
        if ( v61 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
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
        if ( *((_DWORD *)v62 + 499) != v49 )
          CallStackContext::TraceFailure(v62, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3234, v49);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 303, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, this, v49);
      goto LABEL_183;
    }
    CurrentPosition = CMFByteStreamMediaSource::FinishPendingStart(
                        this,
                        1,
                        **((struct CMediaSourceOpStart ***)this + 137),
                        v90);
    if ( CurrentPosition < 0 )
    {
      v53 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v51, v52);
        CallStackTracing::s_wpInstance = v54;
        if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
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
        v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
        if ( *((_DWORD *)v59 + 499) != CurrentPosition )
          CallStackContext::TraceFailure(v59, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3226, CurrentPosition);
      }
      if ( g_wppLevels )
      {
        v11 = 302;
        goto LABEL_182;
      }
      goto LABEL_183;
    }
  }
  else
  {
    v68 = (struct CMediaSourceOpStart **)*((_QWORD *)this + 137);
    v90 = 0;
    v88 = 0;
    CurrentPosition = CMFByteStreamMediaSource::DetermineOffsetForStartPosition(this, *v68, &v88, &v90);
    if ( CurrentPosition < 0 )
    {
      v71 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v69, v70);
        CallStackTracing::s_wpInstance = v72;
        if ( v72 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v72 + 8LL))(v72, 2032) )
        {
          v71 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v71 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v71 + 8) )
      {
        v73 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v71);
        if ( *((_DWORD *)v73 + 499) != CurrentPosition )
          CallStackContext::TraceFailure(v73, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3243, CurrentPosition);
      }
      if ( g_wppLevels )
      {
        v11 = 305;
        goto LABEL_182;
      }
      goto LABEL_183;
    }
    CurrentPosition = CMFByteStreamSourceReader::SetCurrentPosition(
                        (CMFByteStreamMediaSource *)((char *)this + 1120),
                        v88,
                        0);
    if ( CurrentPosition < 0 )
    {
      v76 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v77 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v74, v75);
        CallStackTracing::s_wpInstance = v77;
        if ( v77 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v77 + 8LL))(v77, 2032) )
        {
          v76 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v76 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v76 + 8) )
      {
        v78 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v76);
        if ( *((_DWORD *)v78 + 499) != CurrentPosition )
          CallStackContext::TraceFailure(v78, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3247, CurrentPosition);
      }
      if ( g_wppLevels )
      {
        v11 = 306;
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
      v81 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v82 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v79, v80);
        CallStackTracing::s_wpInstance = v82;
        if ( v82 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v82 + 8LL))(v82, 2032) )
        {
          v81 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v81 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v81 + 8) )
      {
        v83 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v81);
        if ( *((_DWORD *)v83 + 499) != CurrentPosition )
          CallStackContext::TraceFailure(v83, "CMFByteStreamMediaSource::OnByteStreamReadIndex", 3249, CurrentPosition);
      }
      if ( g_wppLevels )
      {
        v11 = 307;
        goto LABEL_182;
      }
      goto LABEL_183;
    }
  }
  v85 = (CPendingLoadIndex *)*((_QWORD *)this + 137);
  if ( v85 )
    CPendingLoadIndex::`scalar deleting destructor'(v85, v4);
  *((_QWORD *)this + 137) = 0;
  CMFByteStreamMediaSource::CompleteAsyncOperation(this, CurrentPosition);
LABEL_190:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v87);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v90);
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
