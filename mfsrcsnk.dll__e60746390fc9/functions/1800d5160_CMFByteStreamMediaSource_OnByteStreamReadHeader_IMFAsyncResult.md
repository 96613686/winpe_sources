# CMFByteStreamMediaSource::OnByteStreamReadHeader(IMFAsyncResult *)

- ea: `0x1800d5160`
- end: `0x1800d5a65`
- name: `?OnByteStreamReadHeader@CMFByteStreamMediaSource@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `2309`
- prototype: `void __fastcall(CMFByteStreamMediaSource *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180144640`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x18005ca98`
- `0x18005cf64`
- `0x18005d990`
- `0x18005de70`
- `0x18006c93c`
- `0x180073b14`
- `0x1800a617c`
- `0x1800a72d0`
- `0x1800d5160`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d5a35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d5a35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d51bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d51bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d51e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d529e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d534d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d53fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d549f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d5543`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d562a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d56f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d57b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d5855`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d58f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d59a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d51e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d529e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d534d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d53fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d549f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d5543`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d562a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d56f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d57b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d5855`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d58f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d59a2`

## string_xrefs

- `0x1800d517a`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800d53a4`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800d5451`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800d54f6`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800d559a`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800d5681`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800d574d`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800d580a`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800d58ac`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800d594a`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`
- `0x1800d59f9`: `CMFByteStreamMediaSource::OnByteStreamReadHeader`

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
        v5 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v10 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v14 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v18 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v22 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v25 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v32 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v36 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v48 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v45 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v41 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v52 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x1800d5160  mov     [rsp-38h+arg_8], rbx
0x1800d5165  push    rbp
0x1800d5166  push    rsi
0x1800d5167  push    rdi
0x1800d5168  push    r12
0x1800d516a  push    r13
0x1800d516c  push    r14
0x1800d516e  push    r15
0x1800d5170  mov     rbp, rsp
0x1800d5173  sub     rsp, 60h
0x1800d5177  mov     r15, rdx
0x1800d517a  lea     rsi, aCmfbytestreamm_18; "CMFByteStreamMediaSource::OnByteStreamR"...
0x1800d5181  mov     rdi, rcx
0x1800d5184  mov     rdx, rsi; char *
0x1800d5187  mov     r8d, 0BDDh; int
0x1800d518d  lea     rcx, [rbp+arg_0]; this
0x1800d5191  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800d5196  xor     r13d, r13d
0x1800d5199  lea     r12, [rdi+2C8h]
0x1800d51a0  mov     rcx, r12; lpCriticalSection
0x1800d51a3  mov     [rbp+var_18], r13
0x1800d51a7  mov     [rbp+arg_18], r13d
0x1800d51ab  mov     [rbp+var_10], r13
0x1800d51af  mov     [rbp+var_8], r13
0x1800d51b3  mov     [rbp+arg_10], r13d
0x1800d51b7  mov     [rbp+arg_0], r13d
0x1800d51bb  mov     [rbp+var_20], r13d
0x1800d51bf  call    cs:__imp_EnterCriticalSection
0x1800d51c5  lea     r14d, [r13+1]
0x1800d51c9  cmp     [rdi+454h], r14d
0x1800d51d0  jz      loc_1800D5284
0x1800d51d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d51dd  mov     ebx, 0C00D36B2h
0x1800d51e2  test    rcx, rcx
0x1800d51e5  jnz     short loc_1800D5228
0x1800d51e7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d51ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d51f4  mov     rcx, rax
0x1800d51f7  test    rax, rax
0x1800d51fa  jz      short loc_1800D521A
0x1800d51fc  mov     rax, [rax]
0x1800d51ff  mov     edx, 7F0h
0x1800d5204  mov     rax, [rax+8]
0x1800d5208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d520d  test    eax, eax
0x1800d520f  jz      short loc_1800D521A
0x1800d5211  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d5218  jmp     short loc_1800D5228
0x1800d521a  lea     rcx, qword_1801B07E0; this
0x1800d5221  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d5228  cmp     [rcx+8], r13b
0x1800d522c  jz      short loc_1800D524F
0x1800d522e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d5233  cmp     [rax+7CCh], ebx
0x1800d5239  jz      short loc_1800D524F
0x1800d523b  mov     r9d, ebx; int
0x1800d523e  mov     r8d, 0BECh; int
0x1800d5244  mov     rdx, rsi; char *
0x1800d5247  mov     rcx, rax; this
0x1800d524a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d524f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800d5256  jb      loc_1800D5A28
0x1800d525c  mov     edx, 117h
0x1800d5261  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d5268  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x1800d526f  mov     r9, rdi
0x1800d5272  mov     dword ptr [rsp+60h+var_40], ebx
0x1800d5276  mov     rcx, [rcx+10h]
0x1800d527a  call    WPP_SF_qD
0x1800d527f  jmp     loc_1800D5A28
0x1800d5284  test    r15, r15
0x1800d5287  jnz     loc_1800D531D
0x1800d528d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d5294  mov     ebx, 80004003h
0x1800d5299  test    rcx, rcx
0x1800d529c  jnz     short loc_1800D52DF
0x1800d529e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d52a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d52ab  mov     rcx, rax
0x1800d52ae  test    rax, rax
0x1800d52b1  jz      short loc_1800D52D1
0x1800d52b3  mov     rax, [rax]
0x1800d52b6  mov     edx, 7F0h
0x1800d52bb  mov     rax, [rax+8]
0x1800d52bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d52c4  test    eax, eax
0x1800d52c6  jz      short loc_1800D52D1
0x1800d52c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d52cf  jmp     short loc_1800D52DF
0x1800d52d1  lea     rcx, qword_1801B07E0; this
0x1800d52d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d52df  cmp     [rcx+8], r13b
0x1800d52e3  jz      short loc_1800D5306
0x1800d52e5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d52ea  cmp     [rax+7CCh], ebx
0x1800d52f0  jz      short loc_1800D5306
0x1800d52f2  mov     r9d, ebx; int
0x1800d52f5  mov     r8d, 0BEFh; int
0x1800d52fb  mov     rdx, rsi; char *
0x1800d52fe  mov     rcx, rax; this
0x1800d5301  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d5306  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800d530d  jb      loc_1800D5A28
0x1800d5313  mov     edx, 118h
0x1800d5318  jmp     loc_1800D5261
0x1800d531d  lea     rsi, [rdi+460h]
0x1800d5324  mov     rdx, r15; struct IMFAsyncResult *
0x1800d5327  mov     rcx, rsi; this
0x1800d532a  lea     r9, [rbp+var_20]; unsigned int *
0x1800d532e  lea     r8, [rbp+var_18]; struct IMFMediaBuffer **
0x1800d5332  call    ?EndReadData@CMFByteStreamSourceReader@@QEAAJPEAUIMFAsyncResult@@PEAPEAUIMFMediaBuffer@@PEAK@Z; CMFByteStreamSourceReader::EndReadData(IMFAsyncResult *,IMFMediaBuffer * *,ulong *)
0x1800d5337  mov     ebx, eax
0x1800d5339  test    eax, eax
0x1800d533b  jns     loc_1800D53D0
0x1800d5341  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d5348  test    rcx, rcx
0x1800d534b  jnz     short loc_1800D538E
0x1800d534d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d5353  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d535a  mov     rcx, rax
0x1800d535d  test    rax, rax
0x1800d5360  jz      short loc_1800D5380
0x1800d5362  mov     rax, [rax]
0x1800d5365  mov     edx, 7F0h
0x1800d536a  mov     rax, [rax+8]
0x1800d536e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5373  test    eax, eax
0x1800d5375  jz      short loc_1800D5380
0x1800d5377  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d537e  jmp     short loc_1800D538E
0x1800d5380  lea     rcx, qword_1801B07E0; this
0x1800d5387  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d538e  cmp     [rcx+8], r13b
0x1800d5392  jz      short loc_1800D53B9
0x1800d5394  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d5399  cmp     [rax+7CCh], ebx
0x1800d539f  jz      short loc_1800D53B9
0x1800d53a1  mov     r9d, ebx; int
0x1800d53a4  lea     rdx, aCmfbytestreamm_18; "CMFByteStreamMediaSource::OnByteStreamR"...
0x1800d53ab  mov     r8d, 0BF1h; int
0x1800d53b1  mov     rcx, rax; this
0x1800d53b4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d53b9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800d53c0  jb      loc_1800D5A28
0x1800d53c6  mov     edx, 119h
0x1800d53cb  jmp     loc_1800D5261
0x1800d53d0  mov     rcx, [rbp+var_18]
0x1800d53d4  lea     rdx, [rbp+arg_18]
0x1800d53d8  mov     rax, [rcx]
0x1800d53db  mov     rax, [rax+28h]
0x1800d53df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d53e4  mov     ebx, eax
0x1800d53e6  test    eax, eax
0x1800d53e8  jns     loc_1800D547D
0x1800d53ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d53f5  test    rcx, rcx
0x1800d53f8  jnz     short loc_1800D543B
0x1800d53fa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d5400  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d5407  mov     rcx, rax
0x1800d540a  test    rax, rax
0x1800d540d  jz      short loc_1800D542D
0x1800d540f  mov     rax, [rax]
0x1800d5412  mov     edx, 7F0h
0x1800d5417  mov     rax, [rax+8]
0x1800d541b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5420  test    eax, eax
0x1800d5422  jz      short loc_1800D542D
0x1800d5424  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d542b  jmp     short loc_1800D543B
0x1800d542d  lea     rcx, qword_1801B07E0; this
0x1800d5434  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d543b  cmp     [rcx+8], r13b
0x1800d543f  jz      short loc_1800D5466
0x1800d5441  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d5446  cmp     [rax+7CCh], ebx
0x1800d544c  jz      short loc_1800D5466
0x1800d544e  mov     r9d, ebx; int
0x1800d5451  lea     rdx, aCmfbytestreamm_18; "CMFByteStreamMediaSource::OnByteStreamR"...
0x1800d5458  mov     r8d, 0BF4h; int
0x1800d545e  mov     rcx, rax; this
0x1800d5461  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d5466  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800d546d  jb      loc_1800D5A28
0x1800d5473  mov     edx, 11Ah
0x1800d5478  jmp     loc_1800D5261
0x1800d547d  lea     rdx, [rbp+var_10]; unsigned __int64 *
0x1800d5481  mov     rcx, rsi; this
0x1800d5484  call    ?GetCurrentPosition@CMFByteStreamSourceReader@@QEAAJPEA_K@Z; CMFByteStreamSourceReader::GetCurrentPosition(unsigned __int64 *)
0x1800d5489  mov     ebx, eax
0x1800d548b  test    eax, eax
0x1800d548d  jns     loc_1800D5522
0x1800d5493  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d549a  test    rcx, rcx
0x1800d549d  jnz     short loc_1800D54E0
0x1800d549f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d54a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d54ac  mov     rcx, rax
0x1800d54af  test    rax, rax
0x1800d54b2  jz      short loc_1800D54D2
0x1800d54b4  mov     rax, [rax]
0x1800d54b7  mov     edx, 7F0h
0x1800d54bc  mov     rax, [rax+8]
0x1800d54c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d54c5  test    eax, eax
0x1800d54c7  jz      short loc_1800D54D2
0x1800d54c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d54d0  jmp     short loc_1800D54E0
0x1800d54d2  lea     rcx, qword_1801B07E0; this
0x1800d54d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d54e0  cmp     [rcx+8], r13b
0x1800d54e4  jz      short loc_1800D550B
0x1800d54e6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d54eb  cmp     [rax+7CCh], ebx
0x1800d54f1  jz      short loc_1800D550B
0x1800d54f3  mov     r9d, ebx; int
0x1800d54f6  lea     rdx, aCmfbytestreamm_18; "CMFByteStreamMediaSource::OnByteStreamR"...
0x1800d54fd  mov     r8d, 0BF5h; int
0x1800d5503  mov     rcx, rax; this
0x1800d5506  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d550b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800d5512  jb      loc_1800D5A28
0x1800d5518  mov     edx, 11Bh
0x1800d551d  jmp     loc_1800D5261
0x1800d5522  mov     eax, [rbp+arg_18]
0x1800d5525  mov     r14, [rbp+var_10]
0x1800d5529  cmp     r14, rax
0x1800d552c  jnb     loc_1800D55C6
0x1800d5532  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d5539  mov     ebx, 8000FFFFh
0x1800d553e  test    rcx, rcx
0x1800d5541  jnz     short loc_1800D5584
0x1800d5543  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d5549  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d5550  mov     rcx, rax
0x1800d5553  test    rax, rax
0x1800d5556  jz      short loc_1800D5576
0x1800d5558  mov     rax, [rax]
0x1800d555b  mov     edx, 7F0h
0x1800d5560  mov     rax, [rax+8]
0x1800d5564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5569  test    eax, eax
0x1800d556b  jz      short loc_1800D5576
0x1800d556d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d5574  jmp     short loc_1800D5584
0x1800d5576  lea     rcx, qword_1801B07E0; this
0x1800d557d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d5584  cmp     [rcx+8], r13b
0x1800d5588  jz      short loc_1800D55AF
0x1800d558a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d558f  cmp     [rax+7CCh], ebx
0x1800d5595  jz      short loc_1800D55AF
0x1800d5597  mov     r9d, ebx; int
0x1800d559a  lea     rdx, aCmfbytestreamm_18; "CMFByteStreamMediaSource::OnByteStreamR"...
0x1800d55a1  mov     r8d, 0BFAh; int
0x1800d55a7  mov     rcx, rax; this
0x1800d55aa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d55af  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d55b6  jb      loc_1800D5A28
0x1800d55bc  mov     edx, 11Ch
0x1800d55c1  jmp     loc_1800D5261
0x1800d55c6  mov     ecx, [rdi+488h]
0x1800d55cc  sub     r14, rax
0x1800d55cf  mov     edx, ecx
0x1800d55d1  shr     edx, 8
0x1800d55d4  and     edx, 1
0x1800d55d7  test    cl, 4
0x1800d55da  jz      short loc_1800D55DF
0x1800d55dc  or      edx, 2
0x1800d55df  bt      ecx, 9
0x1800d55e3  jnb     short loc_1800D55E8
0x1800d55e5  or      edx, 4
0x1800d55e8  bt      ecx, 0Bh
0x1800d55ec  jnb     short loc_1800D55F2
0x1800d55ee  bts     edx, 7
0x1800d55f2  mov     rcx, [rdi+388h]
0x1800d55f9  mov     rax, [rcx]
0x1800d55fc  mov     rax, [rax+30h]
0x1800d5600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5605  mov     r8, [rbp+var_18]; struct IMFMediaBuffer *
0x1800d5609  mov     rdx, r15; struct IMFAsyncResult *
0x1800d560c  mov     rcx, rdi; this
0x1800d560f  call    ?SetSaltValueOnSourcePlugin@CMFByteStreamMediaSource@@AEAAJPEAUIMFAsyncResult@@PEAUIMFMediaBuffer@@@Z; CMFByteStreamMediaSource::SetSaltValueOnSourcePlugin(IMFAsyncResult *,IMFMediaBuffer *)
0x1800d5614  mov     ebx, eax
0x1800d5616  test    eax, eax
0x1800d5618  jns     loc_1800D56AD
0x1800d561e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d5625  test    rcx, rcx
0x1800d5628  jnz     short loc_1800D566B
0x1800d562a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d5630  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d5637  mov     rcx, rax
0x1800d563a  test    rax, rax
0x1800d563d  jz      short loc_1800D565D
0x1800d563f  mov     rax, [rax]
0x1800d5642  mov     edx, 7F0h
0x1800d5647  mov     rax, [rax+8]
0x1800d564b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5650  test    eax, eax
0x1800d5652  jz      short loc_1800D565D
  ... truncated ...
```
