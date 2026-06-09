# CMFByteStreamMediaSource::OnByteStreamReadHeader(IMFAsyncResult *)

- ea: `0x1800db2f8`
- end: `0x1800dbc52`
- name: `?OnByteStreamReadHeader@CMFByteStreamMediaSource@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `2394`
- prototype: `void __fastcall(CMFByteStreamMediaSource *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18014c5e0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x1800378e4`
- `0x180037dec`
- `0x180060378`
- `0x18006085c`
- `0x18006e194`
- `0x180079680`
- `0x1800ab218`
- `0x1800ac3e4`
- `0x1800db2f8`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dbc1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dbc1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800db357`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800db357`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800db385`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800db442`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800db4f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800db5aa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800db655`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800db6ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800db7ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800db8be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800db981`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dba29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dbacd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dbb82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800db385`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800db442`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800db4f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800db5aa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800db655`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800db6ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800db7ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800db8be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800db981`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dba29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dbacd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dbb82`

## string_xrefs

- `0x1800db312`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800db554`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800db607`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800db6b2`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800db75c`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800db849`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800db91b`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800db9de`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800dba86`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800dbb2a`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800dbbdf`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`

## pseudocode

```c
void __fastcall CMFByteStreamMediaSource::OnByteStreamReadHeader(
        CMFByteStreamMediaSource *this,
        struct IMFAsyncResult *a2)
{
  __int64 v4; // rdx
  wchar_t *v5; // rcx
  int CurrentPosition; // ebx
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
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  unsigned int v28; // ecx
  unsigned __int64 v29; // r14
  __int64 v30; // rdx
  __int64 v31; // rdx
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  CMFByteStreamSourceReader *v39; // rcx
  __int64 v40; // rdx
  wchar_t *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 v51; // rdx
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  unsigned int v55; // [rsp+40h] [rbp-20h] BYREF
  struct IMFMediaBuffer *v56; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 v57; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int64 v58; // [rsp+58h] [rbp-8h] BYREF
  int v59; // [rsp+A0h] [rbp+40h] BYREF
  int v60; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int v61; // [rsp+B8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v59,
    "CMFByteStreamMediaSource::OnByteStreamReadHeader",
    3037);
  v56 = 0;
  v61 = 0;
  v57 = 0;
  v58 = 0;
  v60 = 0;
  v59 = 0;
  v55 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
  if ( *((_DWORD *)this + 277) != 1 )
  {
    v5 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentPosition = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v5 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875854 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFByteStreamMediaSource::OnByteStreamReadHeader",
          3052,
          -1072875854);
    }
    if ( !g_wppLevels )
      goto LABEL_143;
    v9 = 279;
    goto LABEL_12;
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
        CallStackContext::TraceFailure(v12, "CMFByteStreamMediaSource::OnByteStreamReadHeader", 3055, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_143;
    v9 = 280;
    goto LABEL_12;
  }
  CurrentPosition = CMFByteStreamSourceReader::EndReadData(
                      (CMFByteStreamMediaSource *)((char *)this + 1120),
                      a2,
                      &v56,
                      &v55);
  if ( CurrentPosition < 0 )
  {
    v14 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
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
      if ( *((_DWORD *)v16 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(v16, "CMFByteStreamMediaSource::OnByteStreamReadHeader", 3057, CurrentPosition);
    }
    if ( !g_wppLevels )
      goto LABEL_143;
    v9 = 281;
    goto LABEL_12;
  }
  CurrentPosition = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, unsigned int *))v56->lpVtbl->GetCurrentLength)(
                      v56,
                      &v61);
  if ( CurrentPosition < 0 )
  {
    v18 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
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
    if ( *((_BYTE *)v18 + 8) )
    {
      v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)v20 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(v20, "CMFByteStreamMediaSource::OnByteStreamReadHeader", 3060, CurrentPosition);
    }
    if ( !g_wppLevels )
      goto LABEL_143;
    v9 = 282;
    goto LABEL_12;
  }
  CurrentPosition = CMFByteStreamSourceReader::GetCurrentPosition(
                      (CMFByteStreamMediaSource *)((char *)this + 1120),
                      &v57);
  if ( CurrentPosition < 0 )
  {
    v22 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
      CallStackTracing::s_wpInstance = v23;
      if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
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
      if ( *((_DWORD *)v24 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(v24, "CMFByteStreamMediaSource::OnByteStreamReadHeader", 3061, CurrentPosition);
    }
    if ( !g_wppLevels )
      goto LABEL_143;
    v9 = 283;
    goto LABEL_12;
  }
  if ( v57 < v61 )
  {
    v25 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentPosition = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
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
      if ( *((_DWORD *)v27 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v27, "CMFByteStreamMediaSource::OnByteStreamReadHeader", 3066, -2147418113);
    }
    if ( !g_wppLevels )
      goto LABEL_143;
    v9 = 284;
    goto LABEL_12;
  }
  v28 = *((_DWORD *)this + 290);
  v29 = v57 - v61;
  v30 = (v28 >> 8) & 1;
  if ( (v28 & 4) != 0 )
    v30 = (unsigned int)v30 | 2;
  if ( (v28 & 0x200) != 0 )
    v30 = (unsigned int)v30 | 4;
  if ( (v28 & 0x800) != 0 )
    LODWORD(v30) = v30 | 0x80;
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 113) + 48LL))(*((_QWORD *)this + 113), v30);
  CurrentPosition = CMFByteStreamMediaSource::SetSaltValueOnSourcePlugin(this, a2, v56);
  if ( CurrentPosition < 0 )
  {
    v32 = (wchar_t *)CallStackTracing::s_wpInstance;
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
      if ( *((_DWORD *)v34 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(v34, "CMFByteStreamMediaSource::OnByteStreamReadHeader", 3101, CurrentPosition);
    }
    if ( !g_wppLevels )
      goto LABEL_143;
    v9 = 285;
    goto LABEL_12;
  }
  CurrentPosition = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IMFMediaBuffer *, unsigned __int64, unsigned __int64 *, int *))(**((_QWORD **)this + 113) + 24LL))(
                      *((_QWORD *)this + 113),
                      *((_QWORD *)this + 146),
                      v56,
                      v29,
                      &v58,
                      &v60);
  if ( CurrentPosition < 0 )
  {
    v36 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
      CallStackTracing::s_wpInstance = v37;
      if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
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
      if ( *((_DWORD *)v38 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(v38, "CMFByteStreamMediaSource::OnByteStreamReadHeader", 3107, CurrentPosition);
    }
    if ( !g_wppLevels )
      goto LABEL_143;
    v9 = 286;
    goto LABEL_12;
  }
  if ( !v60 )
    goto LABEL_143;
  v39 = (CMFByteStreamMediaSource *)((char *)this + 1120);
  if ( v58 == -1 )
  {
    CurrentPosition = CMFByteStreamSourceReader::IsEndOfFile(v39, &v59);
    if ( CurrentPosition >= 0 )
    {
      if ( !v59 )
        goto LABEL_131;
      v48 = (wchar_t *)CallStackTracing::s_wpInstance;
      CurrentPosition = -1072875792;
      if ( !CallStackTracing::s_wpInstance )
      {
        v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
        CallStackTracing::s_wpInstance = v49;
        if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
        {
          v48 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v48 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v48 + 8) )
      {
        v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
        if ( *((_DWORD *)v50 + 499) != -1072875792 )
          CallStackContext::TraceFailure(v50, "CMFByteStreamMediaSource::OnByteStreamReadHeader", 3130, -1072875792);
      }
      if ( !g_wppLevels )
        goto LABEL_143;
      v9 = 289;
    }
    else
    {
      v45 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
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
        if ( *((_DWORD *)v47 + 499) != CurrentPosition )
          CallStackContext::TraceFailure(v47, "CMFByteStreamMediaSource::OnByteStreamReadHeader", 3126, CurrentPosition);
      }
      if ( !g_wppLevels )
        goto LABEL_143;
      v9 = 288;
    }
LABEL_12:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
      this,
      CurrentPosition);
LABEL_143:
    CMFByteStreamMediaSource::CompleteAsyncOperation(this, CurrentPosition);
    goto LABEL_144;
  }
  CurrentPosition = CMFByteStreamSourceReader::SetCurrentPosition(v39, v58, 0);
  if ( CurrentPosition < 0 )
  {
    v41 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
      CallStackTracing::s_wpInstance = v42;
      if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
      {
        v41 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v41 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v41 + 8) )
    {
      v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
      if ( *((_DWORD *)v43 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(v43, "CMFByteStreamMediaSource::OnByteStreamReadHeader", 3118, CurrentPosition);
    }
    if ( !g_wppLevels )
      goto LABEL_143;
    v9 = 287;
    goto LABEL_12;
  }
LABEL_131:
  CurrentPosition = CMFByteStreamSourceReader::BeginReadData(
                      (CMFByteStreamMediaSource *)((char *)this + 1120),
                      (struct IMFAsyncCallback *)this + 86,
                      *((_DWORD *)this + 276));
  if ( CurrentPosition < 0 )
  {
    v52 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51);
      CallStackTracing::s_wpInstance = v53;
      if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
      {
        v52 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v52 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v52 + 8) )
    {
      v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
      if ( *((_DWORD *)v54 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(v54, "CMFByteStreamMediaSource::OnByteStreamReadHeader", 3134, CurrentPosition);
    }
    if ( !g_wppLevels )
      goto LABEL_143;
    v9 = 290;
    goto LABEL_12;
  }
  if ( !v60 )
    goto LABEL_143;
LABEL_144:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v56);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v59);
}

```

## disassembly

```asm
0x1800db2f8  mov     [rsp-38h+arg_8], rbx
0x1800db2fd  push    rbp
0x1800db2fe  push    rsi
0x1800db2ff  push    rdi
0x1800db300  push    r12
0x1800db302  push    r13
0x1800db304  push    r14
0x1800db306  push    r15
0x1800db308  mov     rbp, rsp
0x1800db30b  sub     rsp, 60h
0x1800db30f  mov     r15, rdx
0x1800db312  lea     rsi, aCmfbytestreamm_18; "CMFByteStreamMediaSource::OnByteStreamR"...
0x1800db319  mov     rdi, rcx
0x1800db31c  mov     rdx, rsi; char *
0x1800db31f  mov     r8d, 0BDDh; int
0x1800db325  lea     rcx, [rbp+arg_0]; this
0x1800db329  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800db32e  xor     r13d, r13d
0x1800db331  lea     r12, [rdi+2C8h]
0x1800db338  mov     rcx, r12; lpCriticalSection
0x1800db33b  mov     [rbp+var_18], r13
0x1800db33f  mov     [rbp+arg_18], r13d
0x1800db343  mov     [rbp+var_10], r13
0x1800db347  mov     [rbp+var_8], r13
0x1800db34b  mov     [rbp+arg_10], r13d
0x1800db34f  mov     [rbp+arg_0], r13d
0x1800db353  mov     [rbp+var_20], r13d
0x1800db357  call    cs:__imp_EnterCriticalSection
0x1800db35e  nop     dword ptr [rax+rax+00h]
0x1800db363  lea     r14d, [r13+1]
0x1800db367  cmp     [rdi+454h], r14d
0x1800db36e  jz      loc_1800DB428
0x1800db374  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db37b  mov     ebx, 0C00D36B2h
0x1800db380  test    rcx, rcx
0x1800db383  jnz     short loc_1800DB3CC
0x1800db385  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800db38c  nop     dword ptr [rax+rax+00h]
0x1800db391  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db398  mov     rcx, rax
0x1800db39b  test    rax, rax
0x1800db39e  jz      short loc_1800DB3BE
0x1800db3a0  mov     rax, [rax]
0x1800db3a3  mov     edx, 7F0h
0x1800db3a8  mov     rax, [rax+8]
0x1800db3ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db3b1  test    eax, eax
0x1800db3b3  jz      short loc_1800DB3BE
0x1800db3b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db3bc  jmp     short loc_1800DB3CC
0x1800db3be  lea     rcx, qword_1801B97E0; this
0x1800db3c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db3cc  cmp     [rcx+8], r13b
0x1800db3d0  jz      short loc_1800DB3F3
0x1800db3d2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800db3d7  cmp     [rax+7CCh], ebx
0x1800db3dd  jz      short loc_1800DB3F3
0x1800db3df  mov     r9d, ebx; int
0x1800db3e2  mov     r8d, 0BECh; int
0x1800db3e8  mov     rdx, rsi; char *
0x1800db3eb  mov     rcx, rax; this
0x1800db3ee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800db3f3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800db3fa  jb      loc_1800DBC0E
0x1800db400  mov     edx, 117h
0x1800db405  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db40c  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x1800db413  mov     r9, rdi
0x1800db416  mov     dword ptr [rsp+60h+var_40], ebx
0x1800db41a  mov     rcx, [rcx+10h]
0x1800db41e  call    WPP_SF_qD
0x1800db423  jmp     loc_1800DBC0E
0x1800db428  test    r15, r15
0x1800db42b  jnz     loc_1800DB4C7
0x1800db431  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db438  mov     ebx, 80004003h
0x1800db43d  test    rcx, rcx
0x1800db440  jnz     short loc_1800DB489
0x1800db442  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800db449  nop     dword ptr [rax+rax+00h]
0x1800db44e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db455  mov     rcx, rax
0x1800db458  test    rax, rax
0x1800db45b  jz      short loc_1800DB47B
0x1800db45d  mov     rax, [rax]
0x1800db460  mov     edx, 7F0h
0x1800db465  mov     rax, [rax+8]
0x1800db469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db46e  test    eax, eax
0x1800db470  jz      short loc_1800DB47B
0x1800db472  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db479  jmp     short loc_1800DB489
0x1800db47b  lea     rcx, qword_1801B97E0; this
0x1800db482  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db489  cmp     [rcx+8], r13b
0x1800db48d  jz      short loc_1800DB4B0
0x1800db48f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800db494  cmp     [rax+7CCh], ebx
0x1800db49a  jz      short loc_1800DB4B0
0x1800db49c  mov     r9d, ebx; int
0x1800db49f  mov     r8d, 0BEFh; int
0x1800db4a5  mov     rdx, rsi; char *
0x1800db4a8  mov     rcx, rax; this
0x1800db4ab  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800db4b0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800db4b7  jb      loc_1800DBC0E
0x1800db4bd  mov     edx, 118h
0x1800db4c2  jmp     loc_1800DB405
0x1800db4c7  lea     rsi, [rdi+460h]
0x1800db4ce  mov     rdx, r15; struct IMFAsyncResult *
0x1800db4d1  mov     rcx, rsi; this
0x1800db4d4  lea     r9, [rbp+var_20]; unsigned int *
0x1800db4d8  lea     r8, [rbp+var_18]; struct IMFMediaBuffer **
0x1800db4dc  call    ?EndReadData@CMFByteStreamSourceReader@@QEAAJPEAUIMFAsyncResult@@PEAPEAUIMFMediaBuffer@@PEAK@Z; CMFByteStreamSourceReader::EndReadData(IMFAsyncResult *,IMFMediaBuffer * *,ulong *)
0x1800db4e1  mov     ebx, eax
0x1800db4e3  test    eax, eax
0x1800db4e5  jns     loc_1800DB580
0x1800db4eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db4f2  test    rcx, rcx
0x1800db4f5  jnz     short loc_1800DB53E
0x1800db4f7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800db4fe  nop     dword ptr [rax+rax+00h]
0x1800db503  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db50a  mov     rcx, rax
0x1800db50d  test    rax, rax
0x1800db510  jz      short loc_1800DB530
0x1800db512  mov     rax, [rax]
0x1800db515  mov     edx, 7F0h
0x1800db51a  mov     rax, [rax+8]
0x1800db51e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db523  test    eax, eax
0x1800db525  jz      short loc_1800DB530
0x1800db527  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db52e  jmp     short loc_1800DB53E
0x1800db530  lea     rcx, qword_1801B97E0; this
0x1800db537  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db53e  cmp     [rcx+8], r13b
0x1800db542  jz      short loc_1800DB569
0x1800db544  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800db549  cmp     [rax+7CCh], ebx
0x1800db54f  jz      short loc_1800DB569
0x1800db551  mov     r9d, ebx; int
0x1800db554  lea     rdx, aCmfbytestreamm_18; "CMFByteStreamMediaSource::OnByteStreamR"...
0x1800db55b  mov     r8d, 0BF1h; int
0x1800db561  mov     rcx, rax; this
0x1800db564  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800db569  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800db570  jb      loc_1800DBC0E
0x1800db576  mov     edx, 119h
0x1800db57b  jmp     loc_1800DB405
0x1800db580  mov     rcx, [rbp+var_18]
0x1800db584  lea     rdx, [rbp+arg_18]
0x1800db588  mov     rax, [rcx]
0x1800db58b  mov     rax, [rax+28h]
0x1800db58f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db594  mov     ebx, eax
0x1800db596  test    eax, eax
0x1800db598  jns     loc_1800DB633
0x1800db59e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db5a5  test    rcx, rcx
0x1800db5a8  jnz     short loc_1800DB5F1
0x1800db5aa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800db5b1  nop     dword ptr [rax+rax+00h]
0x1800db5b6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db5bd  mov     rcx, rax
0x1800db5c0  test    rax, rax
0x1800db5c3  jz      short loc_1800DB5E3
0x1800db5c5  mov     rax, [rax]
0x1800db5c8  mov     edx, 7F0h
0x1800db5cd  mov     rax, [rax+8]
0x1800db5d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db5d6  test    eax, eax
0x1800db5d8  jz      short loc_1800DB5E3
0x1800db5da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db5e1  jmp     short loc_1800DB5F1
0x1800db5e3  lea     rcx, qword_1801B97E0; this
0x1800db5ea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db5f1  cmp     [rcx+8], r13b
0x1800db5f5  jz      short loc_1800DB61C
0x1800db5f7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800db5fc  cmp     [rax+7CCh], ebx
0x1800db602  jz      short loc_1800DB61C
0x1800db604  mov     r9d, ebx; int
0x1800db607  lea     rdx, aCmfbytestreamm_18; "CMFByteStreamMediaSource::OnByteStreamR"...
0x1800db60e  mov     r8d, 0BF4h; int
0x1800db614  mov     rcx, rax; this
0x1800db617  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800db61c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800db623  jb      loc_1800DBC0E
0x1800db629  mov     edx, 11Ah
0x1800db62e  jmp     loc_1800DB405
0x1800db633  lea     rdx, [rbp+var_10]; unsigned __int64 *
0x1800db637  mov     rcx, rsi; this
0x1800db63a  call    ?GetCurrentPosition@CMFByteStreamSourceReader@@QEAAJPEA_K@Z; CMFByteStreamSourceReader::GetCurrentPosition(unsigned __int64 *)
0x1800db63f  mov     ebx, eax
0x1800db641  test    eax, eax
0x1800db643  jns     loc_1800DB6DE
0x1800db649  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db650  test    rcx, rcx
0x1800db653  jnz     short loc_1800DB69C
0x1800db655  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800db65c  nop     dword ptr [rax+rax+00h]
0x1800db661  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db668  mov     rcx, rax
0x1800db66b  test    rax, rax
0x1800db66e  jz      short loc_1800DB68E
0x1800db670  mov     rax, [rax]
0x1800db673  mov     edx, 7F0h
0x1800db678  mov     rax, [rax+8]
0x1800db67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db681  test    eax, eax
0x1800db683  jz      short loc_1800DB68E
0x1800db685  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db68c  jmp     short loc_1800DB69C
0x1800db68e  lea     rcx, qword_1801B97E0; this
0x1800db695  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db69c  cmp     [rcx+8], r13b
0x1800db6a0  jz      short loc_1800DB6C7
0x1800db6a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800db6a7  cmp     [rax+7CCh], ebx
0x1800db6ad  jz      short loc_1800DB6C7
0x1800db6af  mov     r9d, ebx; int
0x1800db6b2  lea     rdx, aCmfbytestreamm_18; "CMFByteStreamMediaSource::OnByteStreamR"...
0x1800db6b9  mov     r8d, 0BF5h; int
0x1800db6bf  mov     rcx, rax; this
0x1800db6c2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800db6c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800db6ce  jb      loc_1800DBC0E
0x1800db6d4  mov     edx, 11Bh
0x1800db6d9  jmp     loc_1800DB405
0x1800db6de  mov     eax, [rbp+arg_18]
0x1800db6e1  mov     r14, [rbp+var_10]
0x1800db6e5  cmp     r14, rax
0x1800db6e8  jnb     loc_1800DB788
0x1800db6ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db6f5  mov     ebx, 8000FFFFh
0x1800db6fa  test    rcx, rcx
0x1800db6fd  jnz     short loc_1800DB746
0x1800db6ff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800db706  nop     dword ptr [rax+rax+00h]
0x1800db70b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db712  mov     rcx, rax
0x1800db715  test    rax, rax
0x1800db718  jz      short loc_1800DB738
0x1800db71a  mov     rax, [rax]
0x1800db71d  mov     edx, 7F0h
0x1800db722  mov     rax, [rax+8]
0x1800db726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db72b  test    eax, eax
0x1800db72d  jz      short loc_1800DB738
0x1800db72f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db736  jmp     short loc_1800DB746
0x1800db738  lea     rcx, qword_1801B97E0; this
0x1800db73f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db746  cmp     [rcx+8], r13b
0x1800db74a  jz      short loc_1800DB771
0x1800db74c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800db751  cmp     [rax+7CCh], ebx
0x1800db757  jz      short loc_1800DB771
0x1800db759  mov     r9d, ebx; int
0x1800db75c  lea     rdx, aCmfbytestreamm_18; "CMFByteStreamMediaSource::OnByteStreamR"...
0x1800db763  mov     r8d, 0BFAh; int
0x1800db769  mov     rcx, rax; this
0x1800db76c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800db771  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800db778  jb      loc_1800DBC0E
0x1800db77e  mov     edx, 11Ch
0x1800db783  jmp     loc_1800DB405
0x1800db788  mov     ecx, [rdi+488h]
0x1800db78e  sub     r14, rax
0x1800db791  mov     edx, ecx
0x1800db793  shr     edx, 8
0x1800db796  and     edx, 1
0x1800db799  test    cl, 4
0x1800db79c  jz      short loc_1800DB7A1
0x1800db79e  or      edx, 2
0x1800db7a1  bt      ecx, 9
0x1800db7a5  jnb     short loc_1800DB7AA
0x1800db7a7  or      edx, 4
0x1800db7aa  bt      ecx, 0Bh
0x1800db7ae  jnb     short loc_1800DB7B4
0x1800db7b0  bts     edx, 7
0x1800db7b4  mov     rcx, [rdi+388h]
0x1800db7bb  mov     rax, [rcx]
0x1800db7be  mov     rax, [rax+30h]
0x1800db7c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db7c7  mov     r8, [rbp+var_18]; struct IMFMediaBuffer *
0x1800db7cb  mov     rdx, r15; struct IMFAsyncResult *
0x1800db7ce  mov     rcx, rdi; this
0x1800db7d1  call    ?SetSaltValueOnSourcePlugin@CMFByteStreamMediaSource@@AEAAJPEAUIMFAsyncResult@@PEAUIMFMediaBuffer@@@Z; CMFByteStreamMediaSource::SetSaltValueOnSourcePlugin(IMFAsyncResult *,IMFMediaBuffer *)
0x1800db7d6  mov     ebx, eax
0x1800db7d8  test    eax, eax
0x1800db7da  jns     loc_1800DB875
0x1800db7e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db7e7  test    rcx, rcx
0x1800db7ea  jnz     short loc_1800DB833
0x1800db7ec  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800db7f3  nop     dword ptr [rax+rax+00h]
0x1800db7f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db7ff  mov     rcx, rax
  ... truncated ...
```
