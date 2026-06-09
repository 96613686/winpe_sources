# CADTSBufferParser::AddBuffer(IMFMediaBuffer *)

- ea: `0x180132088`
- end: `0x180132a8f`
- name: `?AddBuffer@CADTSBufferParser@@QEAAJPEAUIMFMediaBuffer@@@Z`
- size: `2567`
- prototype: `__int64 __fastcall(CADTSBufferParser *__hidden this, struct IMFMediaBuffer *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180085bb0`
- `0x1800f9a30`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180073b14`
- `0x18007450c`
- `0x180088fb0`
- `0x1800effc4`
- `0x1801099f0`
- `0x18010a3fc`
- `0x180132088`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180132108`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801321bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180132258`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801322fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801323aa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180132452`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013250e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801325a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180132647`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801326e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180132792`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180132842`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801328f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801329a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180132108`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801321bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180132258`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801322fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801323aa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180132452`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013250e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801325a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180132647`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801326e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180132792`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180132842`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801328f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801329a1`
- `MFPlat!MFCreateMemoryBuffer` at `0x1801322de`
- `MFPlat!MFCreateMemoryBuffer` at `0x1801322de`

## pseudocode

```c
__int64 __fastcall CADTSBufferParser::AddBuffer(IMFMediaBuffer **this, struct IMFMediaBuffer *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  wchar_t *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  IMFMediaBuffer *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  unsigned int v41; // eax
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  wchar_t *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // r9
  wchar_t *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // r9
  wchar_t *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r9
  wchar_t *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // r9
  wchar_t *v75; // rcx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  __int64 v78; // rdx
  __int64 v79; // r8
  __int64 v80; // r9
  wchar_t *v81; // rcx
  CallStackTracing *v82; // rax
  struct CallStackContext *v83; // rax
  _BYTE v85[4]; // [rsp+30h] [rbp-30h] BYREF
  DWORD cbMaxLength; // [rsp+34h] [rbp-2Ch] BYREF
  unsigned int v87; // [rsp+38h] [rbp-28h] BYREF
  __int64 v88; // [rsp+40h] [rbp-20h] BYREF
  void *Source; // [rsp+48h] [rbp-18h] BYREF
  unsigned int SourceSize; // [rsp+50h] [rbp-10h] BYREF
  unsigned int SourceSize_4; // [rsp+54h] [rbp-Ch] BYREF

  v88 = 0;
  Source = 0;
  SourceSize = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v85, "CADTSBufferParser::AddBuffer", 256);
  v5 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, unsigned int *))a2->lpVtbl->GetCurrentLength)(a2, &SourceSize);
  if ( v5 < 0 )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CADTSBufferParser::AddBuffer", 256, v5);
    }
    if ( g_wppLevels )
    {
      v11 = 25;
LABEL_159:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_82f9222a817a345a00b3f046417f5137_Traceguids, this, v5);
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
      v18 = (wchar_t *)CallStackTracing::s_wpInstance;
      v5 = -1072875842;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
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
        if ( *((_DWORD *)v20 + 499) != -1072875842 )
          CallStackContext::TraceFailure(v20, "CADTSBufferParser::AddBuffer", 265, -1072875842);
      }
      if ( !g_wppLevels )
        goto LABEL_160;
      v21 = 27;
      goto LABEL_35;
    }
    v5 = MFCreateMemoryBuffer(cbMaxLength, this);
    if ( v5 < 0 )
    {
      v25 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
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
        if ( *((_DWORD *)v27 + 499) != v5 )
          CallStackContext::TraceFailure(v27, "CADTSBufferParser::AddBuffer", 268, v5);
      }
      if ( g_wppLevels )
      {
        v11 = 28;
        goto LABEL_159;
      }
      goto LABEL_160;
    }
LABEL_47:
    v28 = *this;
    v87 = 0;
    SourceSize_4 = 0;
    v5 = ((__int64 (__fastcall *)(IMFMediaBuffer *, unsigned int *))v28->lpVtbl->GetCurrentLength)(v28, &v87);
    if ( v5 < 0 )
    {
      v32 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
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
        if ( *((_DWORD *)v34 + 499) != v5 )
          CallStackContext::TraceFailure(v34, "CADTSBufferParser::AddBuffer", 273, v5);
      }
      if ( g_wppLevels )
      {
        v11 = 29;
        goto LABEL_159;
      }
      goto LABEL_160;
    }
    v5 = ((__int64 (__fastcall *)(IMFMediaBuffer *, unsigned int *))(*this)->lpVtbl->GetMaxLength)(*this, &SourceSize_4);
    if ( v5 < 0 )
    {
      v38 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36, v37);
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
        v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
        if ( *((_DWORD *)v40 + 499) != v5 )
          CallStackContext::TraceFailure(v40, "CADTSBufferParser::AddBuffer", 274, v5);
      }
      if ( g_wppLevels )
      {
        v11 = 30;
        goto LABEL_159;
      }
      goto LABEL_160;
    }
    if ( SourceSize > SourceSize_4 - v87 )
    {
      if ( SourceSize <= *((_DWORD *)this + 2) + SourceSize_4 - v87 )
      {
        v5 = CADTSBufferParser::CompactBuffer((CADTSBufferParser *)this);
        if ( v5 < 0 )
        {
          v57 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54, v55, v56);
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
            if ( *((_DWORD *)v59 + 499) != v5 )
              CallStackContext::TraceFailure(v59, "CADTSBufferParser::AddBuffer", 293, v5);
          }
          if ( g_wppLevels )
          {
            v11 = 34;
            goto LABEL_159;
          }
          goto LABEL_160;
        }
      }
      else
      {
        v41 = SourceSize_4 + SourceSize;
        if ( SourceSize_4 + SourceSize < SourceSize )
        {
          v42 = (wchar_t *)CallStackTracing::s_wpInstance;
          v5 = -2147024362;
          if ( !CallStackTracing::s_wpInstance )
          {
            v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, SourceSize, SourceSize_4, v37);
            CallStackTracing::s_wpInstance = v43;
            if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
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
            if ( *((_DWORD *)v44 + 499) != -2147024362 )
              CallStackContext::TraceFailure(v44, "CADTSBufferParser::AddBuffer", 282, -2147024362);
          }
          if ( g_wppLevels )
          {
            v11 = 31;
            goto LABEL_159;
          }
          goto LABEL_160;
        }
        if ( v41 > 0x200000 )
        {
          v45 = (wchar_t *)CallStackTracing::s_wpInstance;
          v5 = -1072875842;
          if ( !CallStackTracing::s_wpInstance )
          {
            v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, SourceSize, SourceSize_4, v37);
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
            if ( *((_DWORD *)v47 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v47, "CADTSBufferParser::AddBuffer", 286, -1072875842);
          }
          if ( !g_wppLevels )
            goto LABEL_160;
          v21 = 32;
LABEL_35:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v21,
            &WPP_82f9222a817a345a00b3f046417f5137_Traceguids,
            this,
            -1072875842);
          goto LABEL_160;
        }
        v5 = CADTSBufferParser::ExpandBuffer((CADTSBufferParser *)this, v41);
        if ( v5 < 0 )
        {
          v51 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48, v49, v50);
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
            if ( *((_DWORD *)v53 + 499) != v5 )
              CallStackContext::TraceFailure(v53, "CADTSBufferParser::AddBuffer", 289, v5);
          }
          if ( g_wppLevels )
          {
            v11 = 33;
            goto LABEL_159;
          }
          goto LABEL_160;
        }
      }
    }
    v5 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, void **, _QWORD, _QWORD))a2->lpVtbl->Lock)(a2, &Source, 0, 0);
    if ( v5 >= 0 )
    {
      v5 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, unsigned int *, unsigned int *))(*this)->lpVtbl->Lock)(
             *this,
             &v88,
             &SourceSize_4,
             &v87);
      if ( v5 >= 0 )
      {
        if ( memcpy_s((void *const)(v88 + v87), SourceSize_4 - v87, Source, SourceSize) )
        {
          v75 = (wchar_t *)CallStackTracing::s_wpInstance;
          v5 = -1072875855;
          if ( !CallStackTracing::s_wpInstance )
          {
            v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v72, v73, v74);
            CallStackTracing::s_wpInstance = v76;
            if ( v76 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(v76, 2032) )
            {
              v75 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v75 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v75 + 8) )
          {
            v77 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v75);
            if ( *((_DWORD *)v77 + 499) != -1072875855 )
              CallStackContext::TraceFailure(v77, "CADTSBufferParser::AddBuffer", 302, -1072875855);
          }
          if ( g_wppLevels )
          {
            v11 = 37;
            goto LABEL_159;
          }
        }
        else
        {
          v5 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))(*this)->lpVtbl->SetCurrentLength)(
                 *this,
                 SourceSize + v87);
          if ( v5 < 0 )
          {
            v81 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v82 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v78, v79, v80);
              CallStackTracing::s_wpInstance = v82;
              if ( v82
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v82 + 8LL))(v82, 2032) )
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
              if ( *((_DWORD *)v83 + 499) != v5 )
                CallStackContext::TraceFailure(v83, "CADTSBufferParser::AddBuffer", 305, v5);
            }
            if ( g_wppLevels )
            {
              v11 = 38;
              goto LABEL_159;
            }
          }
        }
      }
      else
      {
        v69 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v67, v68);
          CallStackTracing::s_wpInstance = v70;
          if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
          {
            v69 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v69 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v69 + 8) )
        {
          v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
          if ( *((_DWORD *)v71 + 499) != v5 )
            CallStackContext::TraceFailure(v71, "CADTSBufferParser::AddBuffer", 298, v5);
        }
        if ( g_wppLevels )
        {
          v11 = 36;
          goto LABEL_159;
        }
      }
    }
    else
    {
      v63 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v60, v61, v62);
        CallStackTracing::s_wpInstance = v64;
        if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
        {
          v63 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v63 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v63 + 8) )
      {
        v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
        if ( *((_DWORD *)v65 + 499) != v5 )
          CallStackContext::TraceFailure(v65, "CADTSBufferParser::AddBuffer", 297, v5);
      }
      if ( g_wppLevels )
      {
        v11 = 35;
        goto LABEL_159;
      }
    }
    goto LABEL_160;
  }
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
    if ( *((_DWORD *)v17 + 499) != v5 )
      CallStackContext::TraceFailure(v17, "CADTSBufferParser::AddBuffer", 261, v5);
  }
  if ( g_wppLevels )
  {
    v11 = 26;
    goto LABEL_159;
  }
LABEL_160:
  if ( v88 )
    ((void (__fastcall *)(IMFMediaBuffer *))(*this)->lpVtbl->Unlock)(*this);
  if ( Source )
    ((void (__fastcall *)(struct IMFMediaBuffer *))a2->lpVtbl->Unlock)(a2);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v85);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180132088  mov     [rsp-28h+arg_10], rbx
0x18013208d  mov     [rsp-28h+arg_18], rsi
0x180132092  push    rbp
0x180132093  push    rdi
0x180132094  push    r12
0x180132096  push    r14
0x180132098  push    r15
0x18013209a  mov     rbp, rsp
0x18013209d  sub     rsp, 60h
0x1801320a1  mov     rax, cs:__security_cookie
0x1801320a8  xor     rax, rsp
0x1801320ab  mov     [rbp+var_8], rax
0x1801320af  xor     r15d, r15d
0x1801320b2  lea     r12, aCadtsbufferpar_6; "CADTSBufferParser::AddBuffer"
0x1801320b9  mov     r14, rdx
0x1801320bc  mov     [rbp+var_20], r15
0x1801320c0  mov     rdi, rcx
0x1801320c3  mov     [rbp+Source], r15
0x1801320c7  mov     esi, 100h
0x1801320cc  mov     dword ptr [rbp+SourceSize], r15d
0x1801320d0  mov     r8d, esi; int
0x1801320d3  lea     rcx, [rbp+var_30]; this
0x1801320d7  mov     rdx, r12; char *
0x1801320da  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801320df  mov     rax, [r14]
0x1801320e2  lea     rdx, [rbp+SourceSize]
0x1801320e6  mov     rcx, r14
0x1801320e9  mov     rax, [rax+28h]
0x1801320ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801320f2  mov     ebx, eax
0x1801320f4  test    eax, eax
0x1801320f6  jns     loc_180132184
0x1801320fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180132103  test    rcx, rcx
0x180132106  jnz     short loc_180132149
0x180132108  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013210e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180132115  mov     rcx, rax
0x180132118  test    rax, rax
0x18013211b  jz      short loc_18013213B
0x18013211d  mov     rax, [rax]
0x180132120  mov     edx, 7F0h
0x180132125  mov     rax, [rax+8]
0x180132129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013212e  test    eax, eax
0x180132130  jz      short loc_18013213B
0x180132132  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180132139  jmp     short loc_180132149
0x18013213b  lea     rcx, qword_1801B07E0; this
0x180132142  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180132149  cmp     [rcx+8], r15b
0x18013214d  jz      short loc_18013216D
0x18013214f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180132154  cmp     [rax+7CCh], ebx
0x18013215a  jz      short loc_18013216D
0x18013215c  mov     r9d, ebx; int
0x18013215f  mov     r8d, esi; int
0x180132162  mov     rdx, r12; char *
0x180132165  mov     rcx, rax; this
0x180132168  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013216d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180132174  jb      loc_180132A35
0x18013217a  mov     edx, 19h
0x18013217f  jmp     loc_180132A17
0x180132184  mov     esi, 200000h
0x180132189  cmp     [rdi], r15
0x18013218c  jnz     loc_180132379
0x180132192  mov     ecx, dword ptr [rbp+SourceSize]
0x180132195  lea     rdx, [rbp+cbMaxLength]; unsigned int *
0x180132199  add     rcx, rcx; unsigned __int64
0x18013219c  mov     [rbp+cbMaxLength], r15d
0x1801321a0  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1801321a5  mov     ebx, eax
0x1801321a7  test    eax, eax
0x1801321a9  jns     loc_18013223A
0x1801321af  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801321b6  test    rcx, rcx
0x1801321b9  jnz     short loc_1801321FC
0x1801321bb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801321c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801321c8  mov     rcx, rax
0x1801321cb  test    rax, rax
0x1801321ce  jz      short loc_1801321EE
0x1801321d0  mov     rax, [rax]
0x1801321d3  mov     edx, 7F0h
0x1801321d8  mov     rax, [rax+8]
0x1801321dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801321e1  test    eax, eax
0x1801321e3  jz      short loc_1801321EE
0x1801321e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801321ec  jmp     short loc_1801321FC
0x1801321ee  lea     rcx, qword_1801B07E0; this
0x1801321f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801321fc  cmp     [rcx+8], r15b
0x180132200  jz      short loc_180132223
0x180132202  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180132207  cmp     [rax+7CCh], ebx
0x18013220d  jz      short loc_180132223
0x18013220f  mov     r9d, ebx; int
0x180132212  mov     r8d, 105h; int
0x180132218  mov     rdx, r12; char *
0x18013221b  mov     rcx, rax; this
0x18013221e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180132223  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013222a  jb      loc_180132A35
0x180132230  mov     edx, 1Ah
0x180132235  jmp     loc_180132A17
0x18013223a  mov     ecx, [rbp+cbMaxLength]; cbMaxLength
0x18013223d  cmp     ecx, esi
0x18013223f  jbe     loc_1801322DB
0x180132245  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013224c  mov     esi, 0C00D36BEh
0x180132251  mov     ebx, esi
0x180132253  test    rcx, rcx
0x180132256  jnz     short loc_180132299
0x180132258  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013225e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180132265  mov     rcx, rax
0x180132268  test    rax, rax
0x18013226b  jz      short loc_18013228B
0x18013226d  mov     rax, [rax]
0x180132270  mov     edx, 7F0h
0x180132275  mov     rax, [rax+8]
0x180132279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013227e  test    eax, eax
0x180132280  jz      short loc_18013228B
0x180132282  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180132289  jmp     short loc_180132299
0x18013228b  lea     rcx, qword_1801B07E0; this
0x180132292  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180132299  cmp     [rcx+8], r15b
0x18013229d  jz      short loc_1801322C0
0x18013229f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801322a4  cmp     [rax+7CCh], esi
0x1801322aa  jz      short loc_1801322C0
0x1801322ac  mov     r9d, esi; int
0x1801322af  mov     r8d, 109h; int
0x1801322b5  mov     rdx, r12; char *
0x1801322b8  mov     rcx, rax; this
0x1801322bb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801322c0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801322c7  jb      loc_180132A35
0x1801322cd  mov     edx, 1Bh
0x1801322d2  mov     [rsp+60h+var_40], esi
0x1801322d6  jmp     loc_180132A1B
0x1801322db  mov     rdx, rdi; ppBuffer
0x1801322de  call    cs:__imp_MFCreateMemoryBuffer
0x1801322e4  mov     ebx, eax
0x1801322e6  test    eax, eax
0x1801322e8  jns     loc_180132379
0x1801322ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801322f5  test    rcx, rcx
0x1801322f8  jnz     short loc_18013233B
0x1801322fa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180132300  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180132307  mov     rcx, rax
0x18013230a  test    rax, rax
0x18013230d  jz      short loc_18013232D
0x18013230f  mov     rax, [rax]
0x180132312  mov     edx, 7F0h
0x180132317  mov     rax, [rax+8]
0x18013231b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132320  test    eax, eax
0x180132322  jz      short loc_18013232D
0x180132324  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013232b  jmp     short loc_18013233B
0x18013232d  lea     rcx, qword_1801B07E0; this
0x180132334  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013233b  cmp     [rcx+8], r15b
0x18013233f  jz      short loc_180132362
0x180132341  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180132346  cmp     [rax+7CCh], ebx
0x18013234c  jz      short loc_180132362
0x18013234e  mov     r9d, ebx; int
0x180132351  mov     r8d, 10Ch; int
0x180132357  mov     rdx, r12; char *
0x18013235a  mov     rcx, rax; this
0x18013235d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180132362  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180132369  jb      loc_180132A35
0x18013236f  mov     edx, 1Ch
0x180132374  jmp     loc_180132A17
0x180132379  mov     rcx, [rdi]
0x18013237c  lea     rdx, [rbp+var_28]
0x180132380  mov     [rbp+var_28], r15d
0x180132384  mov     dword ptr [rbp+SourceSize+4], r15d
0x180132388  mov     rax, [rcx]
0x18013238b  mov     rax, [rax+28h]
0x18013238f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132394  mov     ebx, eax
0x180132396  test    eax, eax
0x180132398  jns     loc_180132429
0x18013239e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801323a5  test    rcx, rcx
0x1801323a8  jnz     short loc_1801323EB
0x1801323aa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801323b0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801323b7  mov     rcx, rax
0x1801323ba  test    rax, rax
0x1801323bd  jz      short loc_1801323DD
0x1801323bf  mov     rax, [rax]
0x1801323c2  mov     edx, 7F0h
0x1801323c7  mov     rax, [rax+8]
0x1801323cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801323d0  test    eax, eax
0x1801323d2  jz      short loc_1801323DD
0x1801323d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801323db  jmp     short loc_1801323EB
0x1801323dd  lea     rcx, qword_1801B07E0; this
0x1801323e4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801323eb  cmp     [rcx+8], r15b
0x1801323ef  jz      short loc_180132412
0x1801323f1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801323f6  cmp     [rax+7CCh], ebx
0x1801323fc  jz      short loc_180132412
0x1801323fe  mov     r9d, ebx; int
0x180132401  mov     r8d, 111h; int
0x180132407  mov     rdx, r12; char *
0x18013240a  mov     rcx, rax; this
0x18013240d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180132412  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180132419  jb      loc_180132A35
0x18013241f  mov     edx, 1Dh
0x180132424  jmp     loc_180132A17
0x180132429  mov     rcx, [rdi]
0x18013242c  lea     rdx, [rbp+SourceSize+4]
0x180132430  mov     rax, [rcx]
0x180132433  mov     rax, [rax+38h]
0x180132437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013243c  mov     ebx, eax
0x18013243e  test    eax, eax
0x180132440  jns     loc_1801324D1
0x180132446  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013244d  test    rcx, rcx
0x180132450  jnz     short loc_180132493
0x180132452  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180132458  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013245f  mov     rcx, rax
0x180132462  test    rax, rax
0x180132465  jz      short loc_180132485
0x180132467  mov     rax, [rax]
0x18013246a  mov     edx, 7F0h
0x18013246f  mov     rax, [rax+8]
0x180132473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132478  test    eax, eax
0x18013247a  jz      short loc_180132485
0x18013247c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180132483  jmp     short loc_180132493
0x180132485  lea     rcx, qword_1801B07E0; this
0x18013248c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180132493  cmp     [rcx+8], r15b
0x180132497  jz      short loc_1801324BA
0x180132499  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013249e  cmp     [rax+7CCh], ebx
0x1801324a4  jz      short loc_1801324BA
0x1801324a6  mov     r9d, ebx; int
0x1801324a9  mov     r8d, 112h; int
0x1801324af  mov     rdx, r12; char *
0x1801324b2  mov     rcx, rax; this
0x1801324b5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801324ba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801324c1  jb      loc_180132A35
0x1801324c7  mov     edx, 1Eh
0x1801324cc  jmp     loc_180132A17
0x1801324d1  mov     r8d, dword ptr [rbp+SourceSize+4]
0x1801324d5  mov     ecx, r8d
0x1801324d8  sub     ecx, [rbp+var_28]
0x1801324db  mov     edx, dword ptr [rbp+SourceSize]
0x1801324de  cmp     edx, ecx
0x1801324e0  jbe     loc_180132763
0x1801324e6  add     ecx, [rdi+8]
0x1801324e9  cmp     edx, ecx
0x1801324eb  jbe     loc_1801326C6
0x1801324f1  lea     eax, [r8+rdx]
0x1801324f5  cmp     eax, edx
0x1801324f7  jnb     loc_18013258D
0x1801324fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180132504  mov     ebx, 80070216h
0x180132509  test    rcx, rcx
0x18013250c  jnz     short loc_18013254F
0x18013250e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180132514  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013251b  mov     rcx, rax
0x18013251e  test    rax, rax
0x180132521  jz      short loc_180132541
0x180132523  mov     rax, [rax]
0x180132526  mov     edx, 7F0h
0x18013252b  mov     rax, [rax+8]
0x18013252f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132534  test    eax, eax
0x180132536  jz      short loc_180132541
0x180132538  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013253f  jmp     short loc_18013254F
0x180132541  lea     rcx, qword_1801B07E0; this
0x180132548  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013254f  cmp     [rcx+8], r15b
0x180132553  jz      short loc_180132576
0x180132555  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013255a  cmp     [rax+7CCh], ebx
0x180132560  jz      short loc_180132576
  ... truncated ...
```
