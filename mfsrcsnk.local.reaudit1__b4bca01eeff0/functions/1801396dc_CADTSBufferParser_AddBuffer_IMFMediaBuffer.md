# CADTSBufferParser::AddBuffer(IMFMediaBuffer *)

- ea: `0x1801396dc`
- end: `0x18013a13e`
- name: `?AddBuffer@CADTSBufferParser@@QEAAJPEAUIMFMediaBuffer@@@Z`
- size: `2658`
- prototype: `__int64 __fastcall(IMFMediaBuffer **this, struct IMFMediaBuffer *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18008a820`
- `0x180100800`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180079680`
- `0x180079f34`
- `0x18008dd90`
- `0x1800f6ed0`
- `0x180110ed0`
- `0x18011190c`
- `0x1801396dc`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013975c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139815`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801398b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139966`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139a1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139aca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139b8c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139c2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139cd1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139d74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139e28`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139ede`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139f96`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013a049`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013975c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139815`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801398b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139966`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139a1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139aca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139b8c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139c2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139cd1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139d74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139e28`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139ede`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180139f96`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013a049`
- `MFPlat!MFCreateMemoryBuffer` at `0x180139944`
- `MFPlat!MFCreateMemoryBuffer` at `0x180139944`

## pseudocode

```c
__int64 __fastcall CADTSBufferParser::AddBuffer(IMFMediaBuffer **this, struct IMFMediaBuffer *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  wchar_t *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  IMFMediaBuffer *v22; // rcx
  __int64 v23; // rdx
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  unsigned int v31; // eax
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  wchar_t *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 v42; // rdx
  wchar_t *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rdx
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
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
  _BYTE v63[4]; // [rsp+30h] [rbp-30h] BYREF
  DWORD cbMaxLength; // [rsp+34h] [rbp-2Ch] BYREF
  unsigned int v65; // [rsp+38h] [rbp-28h] BYREF
  __int64 v66; // [rsp+40h] [rbp-20h] BYREF
  void *Source; // [rsp+48h] [rbp-18h] BYREF
  unsigned int SourceSize; // [rsp+50h] [rbp-10h] BYREF
  int SourceSize_4; // [rsp+54h] [rbp-Ch] BYREF

  v66 = 0;
  Source = 0;
  SourceSize = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v63, "CADTSBufferParser::AddBuffer", 256);
  v5 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, unsigned int *))a2->lpVtbl->GetCurrentLength)(a2, &SourceSize);
  if ( v5 < 0 )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CADTSBufferParser::AddBuffer", 256, v5);
    }
    if ( g_wppLevels )
    {
      v9 = 25;
LABEL_159:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_82f9222a817a345a00b3f046417f5137_Traceguids, this, v5);
      goto LABEL_160;
    }
    goto LABEL_160;
  }
  if ( *this )
    goto LABEL_47;
  cbMaxLength = 0;
  v5 = ULongLongToULong(2LL * SourceSize, &cbMaxLength);
  if ( v5 >= 0 )
  {
    if ( cbMaxLength > 0x200000 )
    {
      v14 = (wchar_t *)CallStackTracing::s_wpInstance;
      v5 = -1072875842;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
        if ( *((_DWORD *)v16 + 499) != -1072875842 )
          CallStackContext::TraceFailure(v16, "CADTSBufferParser::AddBuffer", 265, -1072875842);
      }
      if ( !g_wppLevels )
        goto LABEL_160;
      v17 = 27;
      goto LABEL_35;
    }
    v5 = MFCreateMemoryBuffer(cbMaxLength, this);
    if ( v5 < 0 )
    {
      v19 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v21 + 499) != v5 )
          CallStackContext::TraceFailure(v21, "CADTSBufferParser::AddBuffer", 268, v5);
      }
      if ( g_wppLevels )
      {
        v9 = 28;
        goto LABEL_159;
      }
      goto LABEL_160;
    }
LABEL_47:
    v22 = *this;
    v65 = 0;
    SourceSize_4 = 0;
    v5 = ((__int64 (__fastcall *)(IMFMediaBuffer *, unsigned int *))v22->lpVtbl->GetCurrentLength)(v22, &v65);
    if ( v5 < 0 )
    {
      v24 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != v5 )
          CallStackContext::TraceFailure(v26, "CADTSBufferParser::AddBuffer", 273, v5);
      }
      if ( g_wppLevels )
      {
        v9 = 29;
        goto LABEL_159;
      }
      goto LABEL_160;
    }
    v5 = ((__int64 (__fastcall *)(IMFMediaBuffer *, int *))(*this)->lpVtbl->GetMaxLength)(*this, &SourceSize_4);
    if ( v5 < 0 )
    {
      v28 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
        CallStackTracing::s_wpInstance = v29;
        if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
        {
          v28 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v28 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v28 + 8) )
      {
        v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
        if ( *((_DWORD *)v30 + 499) != v5 )
          CallStackContext::TraceFailure(v30, "CADTSBufferParser::AddBuffer", 274, v5);
      }
      if ( g_wppLevels )
      {
        v9 = 30;
        goto LABEL_159;
      }
      goto LABEL_160;
    }
    if ( SourceSize > SourceSize_4 - v65 )
    {
      if ( SourceSize <= *((_DWORD *)this + 2) + SourceSize_4 - v65 )
      {
        v5 = CADTSBufferParser::CompactBuffer((CADTSBufferParser *)this);
        if ( v5 < 0 )
        {
          v43 = (wchar_t *)CallStackTracing::s_wpInstance;
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
            if ( *((_DWORD *)v45 + 499) != v5 )
              CallStackContext::TraceFailure(v45, "CADTSBufferParser::AddBuffer", 293, v5);
          }
          if ( g_wppLevels )
          {
            v9 = 34;
            goto LABEL_159;
          }
          goto LABEL_160;
        }
      }
      else
      {
        v31 = SourceSize_4 + SourceSize;
        if ( SourceSize_4 + SourceSize < SourceSize )
        {
          v32 = (wchar_t *)CallStackTracing::s_wpInstance;
          v5 = -2147024362;
          if ( !CallStackTracing::s_wpInstance )
          {
            v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, SourceSize);
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
            if ( *((_DWORD *)v34 + 499) != -2147024362 )
              CallStackContext::TraceFailure(v34, "CADTSBufferParser::AddBuffer", 282, -2147024362);
          }
          if ( g_wppLevels )
          {
            v9 = 31;
            goto LABEL_159;
          }
          goto LABEL_160;
        }
        if ( v31 > 0x200000 )
        {
          v35 = (wchar_t *)CallStackTracing::s_wpInstance;
          v5 = -1072875842;
          if ( !CallStackTracing::s_wpInstance )
          {
            v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, SourceSize);
            CallStackTracing::s_wpInstance = v36;
            if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
            {
              v35 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v35 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v35 + 8) )
          {
            v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
            if ( *((_DWORD *)v37 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v37, "CADTSBufferParser::AddBuffer", 286, -1072875842);
          }
          if ( !g_wppLevels )
            goto LABEL_160;
          v17 = 32;
LABEL_35:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v17,
            &WPP_82f9222a817a345a00b3f046417f5137_Traceguids,
            this,
            -1072875842);
          goto LABEL_160;
        }
        v5 = CADTSBufferParser::ExpandBuffer((CADTSBufferParser *)this, v31);
        if ( v5 < 0 )
        {
          v39 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38);
            CallStackTracing::s_wpInstance = v40;
            if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
            {
              v39 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v39 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v39 + 8) )
          {
            v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
            if ( *((_DWORD *)v41 + 499) != v5 )
              CallStackContext::TraceFailure(v41, "CADTSBufferParser::AddBuffer", 289, v5);
          }
          if ( g_wppLevels )
          {
            v9 = 33;
            goto LABEL_159;
          }
          goto LABEL_160;
        }
      }
    }
    v5 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, void **, _QWORD, _QWORD))a2->lpVtbl->Lock)(a2, &Source, 0, 0);
    if ( v5 >= 0 )
    {
      v5 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, int *, unsigned int *))(*this)->lpVtbl->Lock)(
             *this,
             &v66,
             &SourceSize_4,
             &v65);
      if ( v5 >= 0 )
      {
        if ( memcpy_s((void *const)(v66 + v65), SourceSize_4 - v65, Source, SourceSize) )
        {
          v55 = (wchar_t *)CallStackTracing::s_wpInstance;
          v5 = -1072875855;
          if ( !CallStackTracing::s_wpInstance )
          {
            v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54);
            CallStackTracing::s_wpInstance = v56;
            if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
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
            if ( *((_DWORD *)v57 + 499) != -1072875855 )
              CallStackContext::TraceFailure(v57, "CADTSBufferParser::AddBuffer", 302, -1072875855);
          }
          if ( g_wppLevels )
          {
            v9 = 37;
            goto LABEL_159;
          }
        }
        else
        {
          v5 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))(*this)->lpVtbl->SetCurrentLength)(
                 *this,
                 SourceSize + v65);
          if ( v5 < 0 )
          {
            v59 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58);
              CallStackTracing::s_wpInstance = v60;
              if ( v60
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
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
              if ( *((_DWORD *)v61 + 499) != v5 )
                CallStackContext::TraceFailure(v61, "CADTSBufferParser::AddBuffer", 305, v5);
            }
            if ( g_wppLevels )
            {
              v9 = 38;
              goto LABEL_159;
            }
          }
        }
      }
      else
      {
        v51 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50);
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
          if ( *((_DWORD *)v53 + 499) != v5 )
            CallStackContext::TraceFailure(v53, "CADTSBufferParser::AddBuffer", 298, v5);
        }
        if ( g_wppLevels )
        {
          v9 = 36;
          goto LABEL_159;
        }
      }
    }
    else
    {
      v47 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
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
        if ( *((_DWORD *)v49 + 499) != v5 )
          CallStackContext::TraceFailure(v49, "CADTSBufferParser::AddBuffer", 297, v5);
      }
      if ( g_wppLevels )
      {
        v9 = 35;
        goto LABEL_159;
      }
    }
    goto LABEL_160;
  }
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
    if ( *((_DWORD *)v13 + 499) != v5 )
      CallStackContext::TraceFailure(v13, "CADTSBufferParser::AddBuffer", 261, v5);
  }
  if ( g_wppLevels )
  {
    v9 = 26;
    goto LABEL_159;
  }
LABEL_160:
  if ( v66 )
    ((void (__fastcall *)(IMFMediaBuffer *))(*this)->lpVtbl->Unlock)(*this);
  if ( Source )
    ((void (__fastcall *)(struct IMFMediaBuffer *))a2->lpVtbl->Unlock)(a2);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v63);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1801396dc  mov     [rsp-28h+arg_10], rbx
0x1801396e1  mov     [rsp-28h+arg_18], rsi
0x1801396e6  push    rbp
0x1801396e7  push    rdi
0x1801396e8  push    r12
0x1801396ea  push    r14
0x1801396ec  push    r15
0x1801396ee  mov     rbp, rsp
0x1801396f1  sub     rsp, 60h
0x1801396f5  mov     rax, cs:__security_cookie
0x1801396fc  xor     rax, rsp
0x1801396ff  mov     [rbp+var_8], rax
0x180139703  xor     r15d, r15d
0x180139706  lea     r12, aCadtsbufferpar_6; "CADTSBufferParser::AddBuffer"
0x18013970d  mov     r14, rdx
0x180139710  mov     [rbp+var_20], r15
0x180139714  mov     rdi, rcx
0x180139717  mov     [rbp+Source], r15
0x18013971b  mov     esi, 100h
0x180139720  mov     dword ptr [rbp+SourceSize], r15d
0x180139724  mov     r8d, esi; int
0x180139727  lea     rcx, [rbp+var_30]; this
0x18013972b  mov     rdx, r12; char *
0x18013972e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180139733  mov     rax, [r14]
0x180139736  lea     rdx, [rbp+SourceSize]
0x18013973a  mov     rcx, r14
0x18013973d  mov     rax, [rax+28h]
0x180139741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139746  mov     ebx, eax
0x180139748  test    eax, eax
0x18013974a  jns     loc_1801397DE
0x180139750  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180139757  test    rcx, rcx
0x18013975a  jnz     short loc_1801397A3
0x18013975c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180139763  nop     dword ptr [rax+rax+00h]
0x180139768  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013976f  mov     rcx, rax
0x180139772  test    rax, rax
0x180139775  jz      short loc_180139795
0x180139777  mov     rax, [rax]
0x18013977a  mov     edx, 7F0h
0x18013977f  mov     rax, [rax+8]
0x180139783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139788  test    eax, eax
0x18013978a  jz      short loc_180139795
0x18013978c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180139793  jmp     short loc_1801397A3
0x180139795  lea     rcx, qword_1801B97E0; this
0x18013979c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801397a3  cmp     [rcx+8], r15b
0x1801397a7  jz      short loc_1801397C7
0x1801397a9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801397ae  cmp     [rax+7CCh], ebx
0x1801397b4  jz      short loc_1801397C7
0x1801397b6  mov     r9d, ebx; int
0x1801397b9  mov     r8d, esi; int
0x1801397bc  mov     rdx, r12; char *
0x1801397bf  mov     rcx, rax; this
0x1801397c2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801397c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801397ce  jb      loc_18013A0E3
0x1801397d4  mov     edx, 19h
0x1801397d9  jmp     loc_18013A0C5
0x1801397de  mov     esi, 200000h
0x1801397e3  cmp     [rdi], r15
0x1801397e6  jnz     loc_1801399EB
0x1801397ec  mov     ecx, dword ptr [rbp+SourceSize]
0x1801397ef  lea     rdx, [rbp+cbMaxLength]; unsigned int *
0x1801397f3  add     rcx, rcx; unsigned __int64
0x1801397f6  mov     [rbp+cbMaxLength], r15d
0x1801397fa  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1801397ff  mov     ebx, eax
0x180139801  test    eax, eax
0x180139803  jns     loc_18013989A
0x180139809  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180139810  test    rcx, rcx
0x180139813  jnz     short loc_18013985C
0x180139815  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013981c  nop     dword ptr [rax+rax+00h]
0x180139821  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180139828  mov     rcx, rax
0x18013982b  test    rax, rax
0x18013982e  jz      short loc_18013984E
0x180139830  mov     rax, [rax]
0x180139833  mov     edx, 7F0h
0x180139838  mov     rax, [rax+8]
0x18013983c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139841  test    eax, eax
0x180139843  jz      short loc_18013984E
0x180139845  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013984c  jmp     short loc_18013985C
0x18013984e  lea     rcx, qword_1801B97E0; this
0x180139855  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013985c  cmp     [rcx+8], r15b
0x180139860  jz      short loc_180139883
0x180139862  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180139867  cmp     [rax+7CCh], ebx
0x18013986d  jz      short loc_180139883
0x18013986f  mov     r9d, ebx; int
0x180139872  mov     r8d, 105h; int
0x180139878  mov     rdx, r12; char *
0x18013987b  mov     rcx, rax; this
0x18013987e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180139883  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013988a  jb      loc_18013A0E3
0x180139890  mov     edx, 1Ah
0x180139895  jmp     loc_18013A0C5
0x18013989a  mov     ecx, [rbp+cbMaxLength]; cbMaxLength
0x18013989d  cmp     ecx, esi
0x18013989f  jbe     loc_180139941
0x1801398a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801398ac  mov     esi, 0C00D36BEh
0x1801398b1  mov     ebx, esi
0x1801398b3  test    rcx, rcx
0x1801398b6  jnz     short loc_1801398FF
0x1801398b8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801398bf  nop     dword ptr [rax+rax+00h]
0x1801398c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801398cb  mov     rcx, rax
0x1801398ce  test    rax, rax
0x1801398d1  jz      short loc_1801398F1
0x1801398d3  mov     rax, [rax]
0x1801398d6  mov     edx, 7F0h
0x1801398db  mov     rax, [rax+8]
0x1801398df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801398e4  test    eax, eax
0x1801398e6  jz      short loc_1801398F1
0x1801398e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801398ef  jmp     short loc_1801398FF
0x1801398f1  lea     rcx, qword_1801B97E0; this
0x1801398f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801398ff  cmp     [rcx+8], r15b
0x180139903  jz      short loc_180139926
0x180139905  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013990a  cmp     [rax+7CCh], esi
0x180139910  jz      short loc_180139926
0x180139912  mov     r9d, esi; int
0x180139915  mov     r8d, 109h; int
0x18013991b  mov     rdx, r12; char *
0x18013991e  mov     rcx, rax; this
0x180139921  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180139926  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013992d  jb      loc_18013A0E3
0x180139933  mov     edx, 1Bh
0x180139938  mov     [rsp+60h+var_40], esi
0x18013993c  jmp     loc_18013A0C9
0x180139941  mov     rdx, rdi; ppBuffer
0x180139944  call    cs:__imp_MFCreateMemoryBuffer
0x18013994b  nop     dword ptr [rax+rax+00h]
0x180139950  mov     ebx, eax
0x180139952  test    eax, eax
0x180139954  jns     loc_1801399EB
0x18013995a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180139961  test    rcx, rcx
0x180139964  jnz     short loc_1801399AD
0x180139966  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013996d  nop     dword ptr [rax+rax+00h]
0x180139972  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180139979  mov     rcx, rax
0x18013997c  test    rax, rax
0x18013997f  jz      short loc_18013999F
0x180139981  mov     rax, [rax]
0x180139984  mov     edx, 7F0h
0x180139989  mov     rax, [rax+8]
0x18013998d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139992  test    eax, eax
0x180139994  jz      short loc_18013999F
0x180139996  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013999d  jmp     short loc_1801399AD
0x18013999f  lea     rcx, qword_1801B97E0; this
0x1801399a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801399ad  cmp     [rcx+8], r15b
0x1801399b1  jz      short loc_1801399D4
0x1801399b3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801399b8  cmp     [rax+7CCh], ebx
0x1801399be  jz      short loc_1801399D4
0x1801399c0  mov     r9d, ebx; int
0x1801399c3  mov     r8d, 10Ch; int
0x1801399c9  mov     rdx, r12; char *
0x1801399cc  mov     rcx, rax; this
0x1801399cf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801399d4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801399db  jb      loc_18013A0E3
0x1801399e1  mov     edx, 1Ch
0x1801399e6  jmp     loc_18013A0C5
0x1801399eb  mov     rcx, [rdi]
0x1801399ee  lea     rdx, [rbp+var_28]
0x1801399f2  mov     [rbp+var_28], r15d
0x1801399f6  mov     dword ptr [rbp+SourceSize+4], r15d
0x1801399fa  mov     rax, [rcx]
0x1801399fd  mov     rax, [rax+28h]
0x180139a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139a06  mov     ebx, eax
0x180139a08  test    eax, eax
0x180139a0a  jns     loc_180139AA1
0x180139a10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180139a17  test    rcx, rcx
0x180139a1a  jnz     short loc_180139A63
0x180139a1c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180139a23  nop     dword ptr [rax+rax+00h]
0x180139a28  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180139a2f  mov     rcx, rax
0x180139a32  test    rax, rax
0x180139a35  jz      short loc_180139A55
0x180139a37  mov     rax, [rax]
0x180139a3a  mov     edx, 7F0h
0x180139a3f  mov     rax, [rax+8]
0x180139a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139a48  test    eax, eax
0x180139a4a  jz      short loc_180139A55
0x180139a4c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180139a53  jmp     short loc_180139A63
0x180139a55  lea     rcx, qword_1801B97E0; this
0x180139a5c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180139a63  cmp     [rcx+8], r15b
0x180139a67  jz      short loc_180139A8A
0x180139a69  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180139a6e  cmp     [rax+7CCh], ebx
0x180139a74  jz      short loc_180139A8A
0x180139a76  mov     r9d, ebx; int
0x180139a79  mov     r8d, 111h; int
0x180139a7f  mov     rdx, r12; char *
0x180139a82  mov     rcx, rax; this
0x180139a85  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180139a8a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180139a91  jb      loc_18013A0E3
0x180139a97  mov     edx, 1Dh
0x180139a9c  jmp     loc_18013A0C5
0x180139aa1  mov     rcx, [rdi]
0x180139aa4  lea     rdx, [rbp+SourceSize+4]
0x180139aa8  mov     rax, [rcx]
0x180139aab  mov     rax, [rax+38h]
0x180139aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139ab4  mov     ebx, eax
0x180139ab6  test    eax, eax
0x180139ab8  jns     loc_180139B4F
0x180139abe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180139ac5  test    rcx, rcx
0x180139ac8  jnz     short loc_180139B11
0x180139aca  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180139ad1  nop     dword ptr [rax+rax+00h]
0x180139ad6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180139add  mov     rcx, rax
0x180139ae0  test    rax, rax
0x180139ae3  jz      short loc_180139B03
0x180139ae5  mov     rax, [rax]
0x180139ae8  mov     edx, 7F0h
0x180139aed  mov     rax, [rax+8]
0x180139af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139af6  test    eax, eax
0x180139af8  jz      short loc_180139B03
0x180139afa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180139b01  jmp     short loc_180139B11
0x180139b03  lea     rcx, qword_1801B97E0; this
0x180139b0a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180139b11  cmp     [rcx+8], r15b
0x180139b15  jz      short loc_180139B38
0x180139b17  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180139b1c  cmp     [rax+7CCh], ebx
0x180139b22  jz      short loc_180139B38
0x180139b24  mov     r9d, ebx; int
0x180139b27  mov     r8d, 112h; int
0x180139b2d  mov     rdx, r12; char *
0x180139b30  mov     rcx, rax; this
0x180139b33  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180139b38  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180139b3f  jb      loc_18013A0E3
0x180139b45  mov     edx, 1Eh
0x180139b4a  jmp     loc_18013A0C5
0x180139b4f  mov     r8d, dword ptr [rbp+SourceSize+4]
0x180139b53  mov     ecx, r8d
0x180139b56  sub     ecx, [rbp+var_28]
0x180139b59  mov     edx, dword ptr [rbp+SourceSize]
0x180139b5c  cmp     edx, ecx
0x180139b5e  jbe     loc_180139DF9
0x180139b64  add     ecx, [rdi+8]
0x180139b67  cmp     edx, ecx
0x180139b69  jbe     loc_180139D56
0x180139b6f  lea     eax, [r8+rdx]
0x180139b73  cmp     eax, edx
0x180139b75  jnb     loc_180139C11
0x180139b7b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180139b82  mov     ebx, 80070216h
0x180139b87  test    rcx, rcx
0x180139b8a  jnz     short loc_180139BD3
0x180139b8c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180139b93  nop     dword ptr [rax+rax+00h]
0x180139b98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180139b9f  mov     rcx, rax
0x180139ba2  test    rax, rax
0x180139ba5  jz      short loc_180139BC5
0x180139ba7  mov     rax, [rax]
0x180139baa  mov     edx, 7F0h
0x180139baf  mov     rax, [rax+8]
0x180139bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139bb8  test    eax, eax
0x180139bba  jz      short loc_180139BC5
0x180139bbc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
