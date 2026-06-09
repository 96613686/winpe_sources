# CWAVEStreamSink::WAVEHeaderUpdate(void)

- ea: `0x1800fbb08`
- end: `0x1800fc7cd`
- name: `?WAVEHeaderUpdate@CWAVEStreamSink@@QEAAJXZ`
- size: `3269`
- prototype: `__int64 __fastcall(CWAVEStreamSink *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180102930`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180079680`
- `0x1800e5f40`
- `0x1800fa974`
- `0x1800fbb08`
- `0x180110a88`
- `0x180110ad4`
- `0x18011cbac`
- `0x18012405c`
- `0x180124630`
- `0x180124a8c`
- `0x180136dd4`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fbb94`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fbc64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fbd0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fbdb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fbe72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fbf90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fc085`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fc17f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fc246`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fc347`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fc418`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fc4ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fc582`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fc635`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fc6f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fbb94`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fbc64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fbd0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fbdb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fbe72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fbf90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fc085`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fc17f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fc246`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fc347`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fc418`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fc4ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fc582`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fc635`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fc6f5`

## string_xrefs

- `0x1800fbb23`: `CWAVEStreamSink::WAVEHeaderUpdate`
- `0x1800fbfed`: `CWAVEStreamSink::WAVEHeaderUpdate`
- `0x1800fc0e2`: `CWAVEStreamSink::WAVEHeaderUpdate`
- `0x1800fc114`: `CWAVEStreamSink::WAVEHeaderUpdate`
- `0x1800fc5df`: `CWAVEStreamSink::WAVEHeaderUpdate`
- `0x1800fc692`: `CWAVEStreamSink::WAVEHeaderUpdate`
- `0x1800fc752`: `CWAVEStreamSink::WAVEHeaderUpdate`

## pseudocode

```c
__int64 __fastcall CWAVEStreamSink::WAVEHeaderUpdate(CWAVEStreamSink *this)
{
  __int64 v1; // rbx
  int Size; // edi
  __int64 v4; // rdx
  __int64 v5; // rax
  unsigned __int64 v6; // r12
  wchar_t *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  unsigned __int64 v19; // rcx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  CRIFFMetadata *v27; // rcx
  CRIFFMetadata *v28; // rcx
  unsigned int v29; // r14d
  unsigned __int64 v30; // rcx
  unsigned __int8 *v31; // rax
  __int64 v32; // rdx
  unsigned __int8 *v33; // r15
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rcx
  unsigned int v42; // eax
  __int64 v43; // rdx
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  unsigned int v47; // edx
  unsigned int v48; // eax
  __int64 v49; // rdx
  wchar_t *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  unsigned int v53; // eax
  unsigned int v54; // edx
  __int64 v55; // rdx
  wchar_t *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  __int64 v59; // rdx
  wchar_t *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  __int64 v63; // rdx
  wchar_t *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  __int64 v67; // rdx
  wchar_t *v68; // rcx
  CallStackTracing *v69; // rax
  struct CallStackContext *v70; // rax
  __int64 v71; // rdx
  wchar_t *v72; // rcx
  CallStackTracing *v73; // rax
  struct CallStackContext *v74; // rax
  __int64 v75; // rdx
  wchar_t *v76; // rcx
  CallStackTracing *v77; // rax
  struct CallStackContext *v78; // rax
  __int64 v79; // rdx
  unsigned __int64 v81[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v82; // [rsp+90h] [rbp+48h] BYREF
  int v83; // [rsp+98h] [rbp+50h] BYREF
  unsigned __int64 v84; // [rsp+A0h] [rbp+58h] BYREF
  unsigned __int64 v85; // [rsp+A8h] [rbp+60h] BYREF

  v1 = *((_QWORD *)this + 84);
  Size = v1 != 0 ? 0 : 0x80004003;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v82, "CWAVEStreamSink::WAVEHeaderUpdate", 482);
  v4 = *((_QWORD *)this + 57);
  v5 = *((unsigned int *)this + 172);
  v83 = 0;
  v82 = 0;
  v6 = (v4 & 1) - v5 + v4 - 4;
  v81[0] = v6;
  if ( v1 )
  {
    Size = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 48) + 24LL))(*((_QWORD *)this + 48), &v83);
    if ( Size >= 0 )
    {
      Size = CWAVEStreamSink::WAVEHeaderGetSize(this, &v82);
      if ( Size >= 0 )
      {
        v19 = *((_QWORD *)this + 57);
        if ( v19 >= v82 )
        {
          if ( (v19 & 1) != 0 )
          {
            v82 = 0;
            Size = CWAVEStreamSink::WriteAsync(this, (const unsigned __int8 *)&v82, 1u);
            if ( Size < 0 )
            {
              v24 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
                CallStackTracing::s_wpInstance = v25;
                if ( v25
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
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
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != Size )
                  CallStackContext::TraceFailure(ThreadRelativeContext, "CWAVEStreamSink::WAVEHeaderUpdate", 507, Size);
              }
              if ( g_wppLevels )
              {
                v10 = 64;
                goto LABEL_12;
              }
              goto LABEL_192;
            }
            if ( (unsigned __int8)byte_1801BA10A >= 0x20u )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 65, WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids);
          }
          v27 = (CRIFFMetadata *)*((_QWORD *)this + 49);
          if ( v27 )
          {
            if ( (unsigned int)CRIFFMetadata::IsCommitReady(v27) == 1 )
            {
              v28 = (CRIFFMetadata *)*((_QWORD *)this + 49);
              v82 = 0;
              if ( (int)CRIFFMetadata::WriteMetadata(v28, 0, 0, &v82) >= 0 )
              {
                v29 = v82;
                if ( v82 )
                {
                  v30 = v82;
                  v82 = 0;
                  v31 = (unsigned __int8 *)operator new[](v30);
                  v33 = v31;
                  if ( !v31 )
                  {
                    v34 = (wchar_t *)CallStackTracing::s_wpInstance;
                    Size = -2147024882;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
                      CallStackTracing::s_wpInstance = v35;
                      if ( v35
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(
                             v35,
                             2032) )
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
                      if ( *((_DWORD *)v36 + 499) != -2147024882 )
                        CallStackContext::TraceFailure(v36, "CWAVEStreamSink::WAVEHeaderUpdate", 523, -2147024882);
                    }
                    if ( g_wppLevels )
                    {
                      v10 = 66;
                      goto LABEL_12;
                    }
                    goto LABEL_192;
                  }
                  Size = CRIFFMetadata::WriteMetadata(*((CRIFFMetadata **)this + 49), v31, v29, &v82);
                  if ( Size >= 0 )
                  {
                    Size = CWAVEStreamSink::WriteAsync(this, v33, v29);
                    if ( (unsigned __int8)byte_1801BA10A >= 0x20u )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 12),
                        67,
                        WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids,
                        v29);
                  }
                  operator delete(v33);
                  if ( Size < 0 )
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
                      if ( *((_DWORD *)v40 + 499) != Size )
                        CallStackContext::TraceFailure(v40, "CWAVEStreamSink::WAVEHeaderUpdate", 535, Size);
                    }
                    if ( g_wppLevels )
                    {
                      v10 = 68;
                      goto LABEL_12;
                    }
                    goto LABEL_192;
                  }
                }
              }
            }
          }
          if ( (v83 & 4) != 0 )
          {
            v41 = *((_QWORD *)this + 57);
            v84 = 0;
            v42 = -1;
            v85 = (v41 & 1) + v41 - 8;
            if ( v85 <= 0xFFFFFFFF )
              v42 = (v41 & 1) + v41 - 8;
            v82 = v42;
            Size = CWAVEStreamSink::SeekAndWrite(this, 4u, &v82, 4u);
            if ( Size < 0 )
            {
              v44 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43);
                CallStackTracing::s_wpInstance = v45;
                if ( v45
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
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
                if ( *((_DWORD *)v46 + 499) != Size )
                  CallStackContext::TraceFailure(v46, "CWAVEStreamSink::WAVEHeaderUpdate", 547, Size);
              }
              if ( g_wppLevels )
              {
                v10 = 69;
                goto LABEL_12;
              }
              goto LABEL_192;
            }
            v47 = *((_DWORD *)this + 172);
            v48 = -1;
            if ( v6 <= 0xFFFFFFFF )
              v48 = v6;
            v82 = v48;
            Size = CWAVEStreamSink::SeekAndWrite(this, v47, &v82, 4u);
            if ( Size < 0 )
            {
              v50 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49);
                CallStackTracing::s_wpInstance = v51;
                if ( v51
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
                {
                  v50 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v50 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v50 + 8) )
              {
                v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
                if ( *((_DWORD *)v52 + 499) != Size )
                  CallStackContext::TraceFailure(v52, "CWAVEStreamSink::WAVEHeaderUpdate", 551, Size);
              }
              if ( g_wppLevels )
              {
                v10 = 70;
                goto LABEL_12;
              }
              goto LABEL_192;
            }
            if ( *((_DWORD *)this + 171) )
            {
              v53 = -1;
              v84 = *((_QWORD *)this + 58) * *(unsigned int *)(*((_QWORD *)this + 84) + 4LL) / 10000000LL;
              if ( v84 <= 0xFFFFFFFF )
                v53 = v84;
              v54 = *((_DWORD *)this + 173);
              v82 = v53;
              Size = CWAVEStreamSink::SeekAndWrite(this, v54, &v82, 4u);
              if ( Size < 0 )
              {
                v56 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55);
                  CallStackTracing::s_wpInstance = v57;
                  if ( v57
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
                  {
                    v56 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v56 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                  }
                }
                if ( *((_BYTE *)v56 + 8) )
                {
                  v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
                  if ( *((_DWORD *)v58 + 499) != Size )
                    CallStackContext::TraceFailure(v58, "CWAVEStreamSink::WAVEHeaderUpdate", 560, Size);
                }
                if ( g_wppLevels )
                {
                  v10 = 71;
                  goto LABEL_12;
                }
                goto LABEL_192;
              }
            }
            if ( *((_QWORD *)this + 57) + (*((_QWORD *)this + 57) & 1uLL) <= 0xFFFFFFFF )
              goto LABEL_192;
            v82 = 875972178;
            Size = CWAVEStreamSink::SeekAndWrite(this, 0, &v82, 4u);
            if ( Size < 0 )
            {
              v60 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v59);
                CallStackTracing::s_wpInstance = v61;
                if ( v61
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
                {
                  v60 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v60 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v60 + 8) )
              {
                v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
                if ( *((_DWORD *)v62 + 499) != Size )
                  CallStackContext::TraceFailure(v62, "CWAVEStreamSink::WAVEHeaderUpdate", 570, Size);
              }
              if ( g_wppLevels )
              {
                v10 = 72;
                goto LABEL_12;
              }
              goto LABEL_192;
            }
            v82 = 875983716;
            Size = CWAVEStreamSink::SeekAndWrite(this, 0xCu, &v82, 4u);
            if ( Size < 0 )
            {
              v64 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v63);
                CallStackTracing::s_wpInstance = v65;
                if ( v65
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
                {
                  v64 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v64 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v64 + 8) )
              {
                v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
                if ( *((_DWORD *)v66 + 499) != Size )
                  CallStackContext::TraceFailure(v66, "CWAVEStreamSink::WAVEHeaderUpdate", 574, Size);
              }
              if ( g_wppLevels )
              {
                v10 = 73;
                goto LABEL_12;
              }
              goto LABEL_192;
            }
            Size = CWAVEStreamSink::SeekAndWrite(this, 0x14u, &v85, 8u);
            if ( Size < 0 )
            {
              v68 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v67);
                CallStackTracing::s_wpInstance = v69;
                if ( v69
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v69 + 8LL))(v69, 2032) )
                {
                  v68 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v68 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v68 + 8) )
              {
                v70 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v68);
                if ( *((_DWORD *)v70 + 499) != Size )
                  CallStackContext::TraceFailure(v70, "CWAVEStreamSink::WAVEHeaderUpdate", 577, Size);
              }
              if ( g_wppLevels )
              {
                v10 = 74;
                goto LABEL_12;
              }
              goto LABEL_192;
            }
            Size = CWAVEStreamSink::SeekAndWrite(this, 0x1Cu, v81, 8u);
            if ( Size < 0 )
            {
              v72 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v71);
                CallStackTracing::s_wpInstance = v73;
                if ( v73
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v73 + 8LL))(v73, 2032) )
                {
                  v72 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v72 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v72 + 8) )
              {
                v74 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v72);
                if ( *((_DWORD *)v74 + 499) != Size )
                  CallStackContext::TraceFailure(v74, "CWAVEStreamSink::WAVEHeaderUpdate", 579, Size);
              }
              if ( g_wppLevels )
              {
                v10 = 75;
                goto LABEL_12;
              }
              goto LABEL_192;
            }
            if ( *((_DWORD *)this + 171) )
            {
              Size = CWAVEStreamSink::SeekAndWrite(this, 0x24u, &v84, 8u);
              if ( Size < 0 )
              {
                v76 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v77 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v75);
                  CallStackTracing::s_wpInstance = v77;
                  if ( v77
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v77 + 8LL))(v77, 2032) )
                  {
                    v76 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v76 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                  }
                }
                if ( *((_BYTE *)v76 + 8) )
                {
                  v78 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v76);
                  if ( *((_DWORD *)v78 + 499) != Size )
                    CallStackContext::TraceFailure(v78, "CWAVEStreamSink::WAVEHeaderUpdate", 584, Size);
                }
                if ( g_wppLevels )
                {
                  v10 = 76;
                  goto LABEL_12;
                }
                goto LABEL_192;
              }
            }
            if ( (unsigned __int8)byte_1801BA10A < 8u )
              goto LABEL_192;
            v79 = 77;
          }
          else
          {
            if ( (unsigned __int8)byte_1801BA10A < 8u )
              goto LABEL_192;
            v79 = 78;
          }
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), v79, WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids);
          goto LABEL_192;
        }
        v20 = (wchar_t *)CallStackTracing::s_wpInstance;
        Size = -2147418113;
        if ( !CallStackTracing::s_wpInstance )
        {
          v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
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
          if ( *((_DWORD *)v22 + 499) != -2147418113 )
            CallStackContext::TraceFailure(v22, "CWAVEStreamSink::WAVEHeaderUpdate", 500, -2147418113);
        }
        if ( g_wppLevels )
        {
          v10 = 63;
          goto LABEL_12;
        }
      }
      else
      {
        v16 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
          CallStackTracing::s_wpInstance = v17;
          if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
          {
            v16 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v16 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v16 + 8) )
        {
          v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
          if ( *((_DWORD *)v18 + 499) != Size )
            CallStackContext::TraceFailure(v18, "CWAVEStreamSink::WAVEHeaderUpdate", 495, Size);
        }
        if ( g_wppLevels )
        {
          v10 = 62;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v12 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( *((_DWORD *)v14 + 499) != Size )
          CallStackContext::TraceFailure(v14, "CWAVEStreamSink::WAVEHeaderUpdate", 493, Size);
      }
      if ( g_wppLevels )
      {
        v10 = 61;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v7 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v9 + 499) != Size )
        CallStackContext::TraceFailure(v9, "CWAVEStreamSink::WAVEHeaderUpdate", 491, Size);
    }
    if ( g_wppLevels )
    {
      v10 = 60;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids, this, Size);
    }
  }
LABEL_192:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v82);
  return (unsigned int)Size;
}

```

## disassembly

```asm
0x1800fbb08  push    rbp
0x1800fbb0a  push    rbx
0x1800fbb0b  push    rsi
0x1800fbb0c  push    rdi
0x1800fbb0d  push    r12
0x1800fbb0f  push    r13
0x1800fbb11  push    r14
0x1800fbb13  push    r15
0x1800fbb15  mov     rbp, rsp
0x1800fbb18  sub     rsp, 48h
0x1800fbb1c  mov     rbx, [rcx+2A0h]
0x1800fbb23  lea     r14, aCwavestreamsin_9; "CWAVEStreamSink::WAVEHeaderUpdate"
0x1800fbb2a  mov     rsi, rcx
0x1800fbb2d  mov     rax, rbx
0x1800fbb30  neg     rax
0x1800fbb33  lea     rcx, [rbp+arg_0]; this
0x1800fbb37  mov     r8d, 1E2h; int
0x1800fbb3d  mov     rdx, r14; char *
0x1800fbb40  sbb     edi, edi
0x1800fbb42  not     edi
0x1800fbb44  and     edi, 80004003h
0x1800fbb4a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800fbb4f  mov     rdx, [rsi+1C8h]
0x1800fbb56  xor     r13d, r13d
0x1800fbb59  mov     eax, [rsi+2B0h]
0x1800fbb5f  mov     rcx, rdx
0x1800fbb62  mov     [rbp+arg_8], r13d
0x1800fbb66  mov     [rbp+arg_0], r13d
0x1800fbb6a  lea     r15d, [r13+1]
0x1800fbb6e  and     rcx, r15
0x1800fbb71  lea     r12, [rdx-4]
0x1800fbb75  sub     rcx, rax
0x1800fbb78  add     r12, rcx
0x1800fbb7b  mov     [rbp+var_18], r12
0x1800fbb7f  test    rbx, rbx
0x1800fbb82  jnz     loc_1800FBC37
0x1800fbb88  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbb8f  test    rcx, rcx
0x1800fbb92  jnz     short loc_1800FBBDB
0x1800fbb94  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800fbb9b  nop     dword ptr [rax+rax+00h]
0x1800fbba0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbba7  mov     rcx, rax
0x1800fbbaa  test    rax, rax
0x1800fbbad  jz      short loc_1800FBBCD
0x1800fbbaf  mov     rax, [rax]
0x1800fbbb2  mov     edx, 7F0h
0x1800fbbb7  mov     rax, [rax+8]
0x1800fbbbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbbc0  test    eax, eax
0x1800fbbc2  jz      short loc_1800FBBCD
0x1800fbbc4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbbcb  jmp     short loc_1800FBBDB
0x1800fbbcd  lea     rcx, qword_1801B97E0; this
0x1800fbbd4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbbdb  cmp     [rcx+8], r13b
0x1800fbbdf  jz      short loc_1800FBC02
0x1800fbbe1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800fbbe6  cmp     [rax+7CCh], edi
0x1800fbbec  jz      short loc_1800FBC02
0x1800fbbee  mov     r9d, edi; int
0x1800fbbf1  mov     r8d, 1EBh; int
0x1800fbbf7  mov     rdx, r14; char *
0x1800fbbfa  mov     rcx, rax; this
0x1800fbbfd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800fbc02  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800fbc09  jb      loc_1800FC7B0
0x1800fbc0f  mov     edx, 3Ch ; '<'
0x1800fbc14  lea     r8, WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids
0x1800fbc1b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fbc22  mov     r9, rsi
0x1800fbc25  mov     [rsp+48h+var_28], edi
0x1800fbc29  mov     rcx, [rcx+10h]
0x1800fbc2d  call    WPP_SF_qD
0x1800fbc32  jmp     loc_1800FC7B0
0x1800fbc37  mov     rcx, [rsi+180h]
0x1800fbc3e  lea     rdx, [rbp+arg_8]
0x1800fbc42  mov     rax, [rcx]
0x1800fbc45  mov     rax, [rax+18h]
0x1800fbc49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbc4e  mov     edi, eax
0x1800fbc50  test    eax, eax
0x1800fbc52  jns     loc_1800FBCE9
0x1800fbc58  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbc5f  test    rcx, rcx
0x1800fbc62  jnz     short loc_1800FBCAB
0x1800fbc64  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800fbc6b  nop     dword ptr [rax+rax+00h]
0x1800fbc70  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbc77  mov     rcx, rax
0x1800fbc7a  test    rax, rax
0x1800fbc7d  jz      short loc_1800FBC9D
0x1800fbc7f  mov     rax, [rax]
0x1800fbc82  mov     edx, 7F0h
0x1800fbc87  mov     rax, [rax+8]
0x1800fbc8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbc90  test    eax, eax
0x1800fbc92  jz      short loc_1800FBC9D
0x1800fbc94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbc9b  jmp     short loc_1800FBCAB
0x1800fbc9d  lea     rcx, qword_1801B97E0; this
0x1800fbca4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbcab  cmp     [rcx+8], r13b
0x1800fbcaf  jz      short loc_1800FBCD2
0x1800fbcb1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800fbcb6  cmp     [rax+7CCh], edi
0x1800fbcbc  jz      short loc_1800FBCD2
0x1800fbcbe  mov     r9d, edi; int
0x1800fbcc1  mov     r8d, 1EDh; int
0x1800fbcc7  mov     rdx, r14; char *
0x1800fbcca  mov     rcx, rax; this
0x1800fbccd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800fbcd2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800fbcd9  jb      loc_1800FC7B0
0x1800fbcdf  mov     edx, 3Dh ; '='
0x1800fbce4  jmp     loc_1800FBC14
0x1800fbce9  lea     rdx, [rbp+arg_0]; unsigned int *
0x1800fbced  mov     rcx, rsi; this
0x1800fbcf0  call    ?WAVEHeaderGetSize@CWAVEStreamSink@@AEAAJPEAK@Z; CWAVEStreamSink::WAVEHeaderGetSize(ulong *)
0x1800fbcf5  mov     edi, eax
0x1800fbcf7  test    eax, eax
0x1800fbcf9  jns     loc_1800FBD90
0x1800fbcff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbd06  test    rcx, rcx
0x1800fbd09  jnz     short loc_1800FBD52
0x1800fbd0b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800fbd12  nop     dword ptr [rax+rax+00h]
0x1800fbd17  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbd1e  mov     rcx, rax
0x1800fbd21  test    rax, rax
0x1800fbd24  jz      short loc_1800FBD44
0x1800fbd26  mov     rax, [rax]
0x1800fbd29  mov     edx, 7F0h
0x1800fbd2e  mov     rax, [rax+8]
0x1800fbd32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbd37  test    eax, eax
0x1800fbd39  jz      short loc_1800FBD44
0x1800fbd3b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbd42  jmp     short loc_1800FBD52
0x1800fbd44  lea     rcx, qword_1801B97E0; this
0x1800fbd4b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbd52  cmp     [rcx+8], r13b
0x1800fbd56  jz      short loc_1800FBD79
0x1800fbd58  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800fbd5d  cmp     [rax+7CCh], edi
0x1800fbd63  jz      short loc_1800FBD79
0x1800fbd65  mov     r9d, edi; int
0x1800fbd68  mov     r8d, 1EFh; int
0x1800fbd6e  mov     rdx, r14; char *
0x1800fbd71  mov     rcx, rax; this
0x1800fbd74  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800fbd79  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800fbd80  jb      loc_1800FC7B0
0x1800fbd86  mov     edx, 3Eh ; '>'
0x1800fbd8b  jmp     loc_1800FBC14
0x1800fbd90  mov     rcx, [rsi+1C8h]
0x1800fbd97  mov     eax, [rbp+arg_0]
0x1800fbd9a  cmp     rcx, rax
0x1800fbd9d  jnb     loc_1800FBE39
0x1800fbda3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbdaa  mov     edi, 8000FFFFh
0x1800fbdaf  test    rcx, rcx
0x1800fbdb2  jnz     short loc_1800FBDFB
0x1800fbdb4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800fbdbb  nop     dword ptr [rax+rax+00h]
0x1800fbdc0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbdc7  mov     rcx, rax
0x1800fbdca  test    rax, rax
0x1800fbdcd  jz      short loc_1800FBDED
0x1800fbdcf  mov     rax, [rax]
0x1800fbdd2  mov     edx, 7F0h
0x1800fbdd7  mov     rax, [rax+8]
0x1800fbddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbde0  test    eax, eax
0x1800fbde2  jz      short loc_1800FBDED
0x1800fbde4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbdeb  jmp     short loc_1800FBDFB
0x1800fbded  lea     rcx, qword_1801B97E0; this
0x1800fbdf4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbdfb  cmp     [rcx+8], r13b
0x1800fbdff  jz      short loc_1800FBE22
0x1800fbe01  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800fbe06  cmp     [rax+7CCh], edi
0x1800fbe0c  jz      short loc_1800FBE22
0x1800fbe0e  mov     r9d, edi; int
0x1800fbe11  mov     r8d, 1F4h; int
0x1800fbe17  mov     rdx, r14; char *
0x1800fbe1a  mov     rcx, rax; this
0x1800fbe1d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800fbe22  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800fbe29  jb      loc_1800FC7B0
0x1800fbe2f  mov     edx, 3Fh ; '?'
0x1800fbe34  jmp     loc_1800FBC14
0x1800fbe39  lea     rbx, WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids
0x1800fbe40  test    r15b, cl
0x1800fbe43  jz      loc_1800FBF1B
0x1800fbe49  mov     r8d, r15d; unsigned int
0x1800fbe4c  mov     [rbp+arg_0], r13d
0x1800fbe50  lea     rdx, [rbp+arg_0]; unsigned __int8 *
0x1800fbe54  mov     rcx, rsi; this
0x1800fbe57  call    ?WriteAsync@CWAVEStreamSink@@AEAAJPEBEI@Z; CWAVEStreamSink::WriteAsync(uchar const *,uint)
0x1800fbe5c  mov     edi, eax
0x1800fbe5e  test    eax, eax
0x1800fbe60  jns     loc_1800FBEFA
0x1800fbe66  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbe6d  test    rcx, rcx
0x1800fbe70  jnz     short loc_1800FBEB9
0x1800fbe72  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800fbe79  nop     dword ptr [rax+rax+00h]
0x1800fbe7e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbe85  mov     rcx, rax
0x1800fbe88  test    rax, rax
0x1800fbe8b  jz      short loc_1800FBEAB
0x1800fbe8d  mov     rax, [rax]
0x1800fbe90  mov     edx, 7F0h
0x1800fbe95  mov     rax, [rax+8]
0x1800fbe99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbe9e  test    eax, eax
0x1800fbea0  jz      short loc_1800FBEAB
0x1800fbea2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbea9  jmp     short loc_1800FBEB9
0x1800fbeab  lea     rcx, qword_1801B97E0; this
0x1800fbeb2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbeb9  cmp     [rcx+8], r13b
0x1800fbebd  jz      short loc_1800FBEE0
0x1800fbebf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800fbec4  cmp     [rax+7CCh], edi
0x1800fbeca  jz      short loc_1800FBEE0
0x1800fbecc  mov     r9d, edi; int
0x1800fbecf  mov     r8d, 1FBh; int
0x1800fbed5  mov     rdx, r14; char *
0x1800fbed8  mov     rcx, rax; this
0x1800fbedb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800fbee0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800fbee7  jb      loc_1800FC7B0
0x1800fbeed  mov     edx, 40h ; '@'
0x1800fbef2  mov     r8, rbx
0x1800fbef5  jmp     loc_1800FBC1B
0x1800fbefa  cmp     cs:byte_1801BA10A, 20h ; ' '
0x1800fbf01  jb      short loc_1800FBF1B
0x1800fbf03  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fbf0a  mov     edx, 41h ; 'A'
0x1800fbf0f  mov     r8, rbx
0x1800fbf12  mov     rcx, [rcx+60h]
0x1800fbf16  call    WPP_SF_
0x1800fbf1b  mov     rcx, [rsi+188h]; this
0x1800fbf22  test    rcx, rcx
0x1800fbf25  jz      loc_1800FC11B
0x1800fbf2b  call    ?IsCommitReady@CRIFFMetadata@@QEAAHXZ; CRIFFMetadata::IsCommitReady(void)
0x1800fbf30  cmp     eax, r15d
0x1800fbf33  jnz     loc_1800FC11B
0x1800fbf39  mov     rcx, [rsi+188h]; this
0x1800fbf40  lea     r9, [rbp+arg_0]; unsigned int *
0x1800fbf44  xor     r8d, r8d; int
0x1800fbf47  mov     [rbp+arg_0], r13d
0x1800fbf4b  xor     edx, edx; unsigned __int8 *
0x1800fbf4d  call    ?WriteMetadata@CRIFFMetadata@@QEAAJPEAEHPEAK@Z; CRIFFMetadata::WriteMetadata(uchar *,int,ulong *)
0x1800fbf52  test    eax, eax
0x1800fbf54  js      loc_1800FC11B
0x1800fbf5a  mov     r14d, [rbp+arg_0]
0x1800fbf5e  test    r14d, r14d
0x1800fbf61  jz      loc_1800FC114
0x1800fbf67  mov     ecx, r14d; unsigned __int64
0x1800fbf6a  mov     [rbp+arg_0], r13d
0x1800fbf6e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800fbf73  mov     r15, rax
0x1800fbf76  test    rax, rax
0x1800fbf79  jnz     loc_1800FC019
0x1800fbf7f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbf86  mov     edi, 8007000Eh
0x1800fbf8b  test    rcx, rcx
0x1800fbf8e  jnz     short loc_1800FBFD7
0x1800fbf90  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800fbf97  nop     dword ptr [rax+rax+00h]
0x1800fbf9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbfa3  mov     rcx, rax
0x1800fbfa6  test    rax, rax
0x1800fbfa9  jz      short loc_1800FBFC9
0x1800fbfab  mov     rax, [rax]
0x1800fbfae  mov     edx, 7F0h
0x1800fbfb3  mov     rax, [rax+8]
0x1800fbfb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fbfbc  test    eax, eax
0x1800fbfbe  jz      short loc_1800FBFC9
0x1800fbfc0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbfc7  jmp     short loc_1800FBFD7
0x1800fbfc9  lea     rcx, qword_1801B97E0; this
0x1800fbfd0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fbfd7  cmp     [rcx+8], r13b
0x1800fbfdb  jz      short loc_1800FC002
0x1800fbfdd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800fbfe2  cmp     [rax+7CCh], edi
0x1800fbfe8  jz      short loc_1800FC002
0x1800fbfea  mov     r9d, edi; int
0x1800fbfed  lea     rdx, aCwavestreamsin_9; "CWAVEStreamSink::WAVEHeaderUpdate"
0x1800fbff4  mov     r8d, 20Bh; int
0x1800fbffa  mov     rcx, rax; this
0x1800fbffd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800fc002  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800fc009  jb      loc_1800FC7B0
  ... truncated ...
```
