# CWAVEStreamSink::WAVEHeaderUpdate(void)

- ea: `0x1800f4f40`
- end: `0x1800f5baa`
- name: `?WAVEHeaderUpdate@CWAVEStreamSink@@QEAAJXZ`
- size: `3178`
- prototype: `__int64 __fastcall(CWAVEStreamSink *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800fba30`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180073b14`
- `0x1800df864`
- `0x1800f3e5c`
- `0x1800f4f40`
- `0x18010959c`
- `0x1801095e8`
- `0x180115a1c`
- `0x18011d99c`
- `0x18011df44`
- `0x18011e37c`
- `0x18012f8a4`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f4fcc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5096`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5137`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f51da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5292`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f53aa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5499`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f558d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f564e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5749`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5814`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f58c4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5972`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5a1f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5ad9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f4fcc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5096`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5137`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f51da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5292`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f53aa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5499`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f558d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f564e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5749`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5814`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f58c4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5972`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5a1f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5ad9`

## string_xrefs

- `0x1800f4f5b`: `CWAVEStreamSink::WAVEHeaderUpdate`
- `0x1800f5401`: `CWAVEStreamSink::WAVEHeaderUpdate`
- `0x1800f54f0`: `CWAVEStreamSink::WAVEHeaderUpdate`
- `0x1800f5522`: `CWAVEStreamSink::WAVEHeaderUpdate`
- `0x1800f59c9`: `CWAVEStreamSink::WAVEHeaderUpdate`
- `0x1800f5a76`: `CWAVEStreamSink::WAVEHeaderUpdate`
- `0x1800f5b30`: `CWAVEStreamSink::WAVEHeaderUpdate`

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
                  v24 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            if ( (unsigned __int8)byte_1801B110A >= 0x20u )
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
                        v34 = &qword_1801B07E0;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                    if ( (unsigned __int8)byte_1801B110A >= 0x20u )
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
                        v38 = &qword_1801B07E0;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                  v44 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                  v50 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                    v56 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                  v60 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                  v64 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                  v68 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                  v72 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                    v76 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            if ( (unsigned __int8)byte_1801B110A < 8u )
              goto LABEL_192;
            v79 = 77;
          }
          else
          {
            if ( (unsigned __int8)byte_1801B110A < 8u )
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
            v20 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v16 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v12 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v7 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x1800f4f40  push    rbp
0x1800f4f42  push    rbx
0x1800f4f43  push    rsi
0x1800f4f44  push    rdi
0x1800f4f45  push    r12
0x1800f4f47  push    r13
0x1800f4f49  push    r14
0x1800f4f4b  push    r15
0x1800f4f4d  mov     rbp, rsp
0x1800f4f50  sub     rsp, 48h
0x1800f4f54  mov     rbx, [rcx+2A0h]
0x1800f4f5b  lea     r14, aCwavestreamsin_9; "CWAVEStreamSink::WAVEHeaderUpdate"
0x1800f4f62  mov     rsi, rcx
0x1800f4f65  mov     rax, rbx
0x1800f4f68  neg     rax
0x1800f4f6b  lea     rcx, [rbp+arg_0]; this
0x1800f4f6f  mov     r8d, 1E2h; int
0x1800f4f75  mov     rdx, r14; char *
0x1800f4f78  sbb     edi, edi
0x1800f4f7a  not     edi
0x1800f4f7c  and     edi, 80004003h
0x1800f4f82  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800f4f87  mov     rdx, [rsi+1C8h]
0x1800f4f8e  xor     r13d, r13d
0x1800f4f91  mov     eax, [rsi+2B0h]
0x1800f4f97  mov     rcx, rdx
0x1800f4f9a  mov     [rbp+arg_8], r13d
0x1800f4f9e  mov     [rbp+arg_0], r13d
0x1800f4fa2  lea     r15d, [r13+1]
0x1800f4fa6  and     rcx, r15
0x1800f4fa9  lea     r12, [rdx-4]
0x1800f4fad  sub     rcx, rax
0x1800f4fb0  add     r12, rcx
0x1800f4fb3  mov     [rbp+var_18], r12
0x1800f4fb7  test    rbx, rbx
0x1800f4fba  jnz     loc_1800F5069
0x1800f4fc0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f4fc7  test    rcx, rcx
0x1800f4fca  jnz     short loc_1800F500D
0x1800f4fcc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f4fd2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f4fd9  mov     rcx, rax
0x1800f4fdc  test    rax, rax
0x1800f4fdf  jz      short loc_1800F4FFF
0x1800f4fe1  mov     rax, [rax]
0x1800f4fe4  mov     edx, 7F0h
0x1800f4fe9  mov     rax, [rax+8]
0x1800f4fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4ff2  test    eax, eax
0x1800f4ff4  jz      short loc_1800F4FFF
0x1800f4ff6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f4ffd  jmp     short loc_1800F500D
0x1800f4fff  lea     rcx, qword_1801B07E0; this
0x1800f5006  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f500d  cmp     [rcx+8], r13b
0x1800f5011  jz      short loc_1800F5034
0x1800f5013  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f5018  cmp     [rax+7CCh], edi
0x1800f501e  jz      short loc_1800F5034
0x1800f5020  mov     r9d, edi; int
0x1800f5023  mov     r8d, 1EBh; int
0x1800f5029  mov     rdx, r14; char *
0x1800f502c  mov     rcx, rax; this
0x1800f502f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f5034  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800f503b  jb      loc_1800F5B8E
0x1800f5041  mov     edx, 3Ch ; '<'
0x1800f5046  lea     r8, WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids
0x1800f504d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f5054  mov     r9, rsi
0x1800f5057  mov     [rsp+48h+var_28], edi
0x1800f505b  mov     rcx, [rcx+10h]
0x1800f505f  call    WPP_SF_qD
0x1800f5064  jmp     loc_1800F5B8E
0x1800f5069  mov     rcx, [rsi+180h]
0x1800f5070  lea     rdx, [rbp+arg_8]
0x1800f5074  mov     rax, [rcx]
0x1800f5077  mov     rax, [rax+18h]
0x1800f507b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5080  mov     edi, eax
0x1800f5082  test    eax, eax
0x1800f5084  jns     loc_1800F5115
0x1800f508a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5091  test    rcx, rcx
0x1800f5094  jnz     short loc_1800F50D7
0x1800f5096  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f509c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f50a3  mov     rcx, rax
0x1800f50a6  test    rax, rax
0x1800f50a9  jz      short loc_1800F50C9
0x1800f50ab  mov     rax, [rax]
0x1800f50ae  mov     edx, 7F0h
0x1800f50b3  mov     rax, [rax+8]
0x1800f50b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f50bc  test    eax, eax
0x1800f50be  jz      short loc_1800F50C9
0x1800f50c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f50c7  jmp     short loc_1800F50D7
0x1800f50c9  lea     rcx, qword_1801B07E0; this
0x1800f50d0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f50d7  cmp     [rcx+8], r13b
0x1800f50db  jz      short loc_1800F50FE
0x1800f50dd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f50e2  cmp     [rax+7CCh], edi
0x1800f50e8  jz      short loc_1800F50FE
0x1800f50ea  mov     r9d, edi; int
0x1800f50ed  mov     r8d, 1EDh; int
0x1800f50f3  mov     rdx, r14; char *
0x1800f50f6  mov     rcx, rax; this
0x1800f50f9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f50fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800f5105  jb      loc_1800F5B8E
0x1800f510b  mov     edx, 3Dh ; '='
0x1800f5110  jmp     loc_1800F5046
0x1800f5115  lea     rdx, [rbp+arg_0]; unsigned int *
0x1800f5119  mov     rcx, rsi; this
0x1800f511c  call    ?WAVEHeaderGetSize@CWAVEStreamSink@@AEAAJPEAK@Z; CWAVEStreamSink::WAVEHeaderGetSize(ulong *)
0x1800f5121  mov     edi, eax
0x1800f5123  test    eax, eax
0x1800f5125  jns     loc_1800F51B6
0x1800f512b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5132  test    rcx, rcx
0x1800f5135  jnz     short loc_1800F5178
0x1800f5137  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f513d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5144  mov     rcx, rax
0x1800f5147  test    rax, rax
0x1800f514a  jz      short loc_1800F516A
0x1800f514c  mov     rax, [rax]
0x1800f514f  mov     edx, 7F0h
0x1800f5154  mov     rax, [rax+8]
0x1800f5158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f515d  test    eax, eax
0x1800f515f  jz      short loc_1800F516A
0x1800f5161  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5168  jmp     short loc_1800F5178
0x1800f516a  lea     rcx, qword_1801B07E0; this
0x1800f5171  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5178  cmp     [rcx+8], r13b
0x1800f517c  jz      short loc_1800F519F
0x1800f517e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f5183  cmp     [rax+7CCh], edi
0x1800f5189  jz      short loc_1800F519F
0x1800f518b  mov     r9d, edi; int
0x1800f518e  mov     r8d, 1EFh; int
0x1800f5194  mov     rdx, r14; char *
0x1800f5197  mov     rcx, rax; this
0x1800f519a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f519f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800f51a6  jb      loc_1800F5B8E
0x1800f51ac  mov     edx, 3Eh ; '>'
0x1800f51b1  jmp     loc_1800F5046
0x1800f51b6  mov     rcx, [rsi+1C8h]
0x1800f51bd  mov     eax, [rbp+arg_0]
0x1800f51c0  cmp     rcx, rax
0x1800f51c3  jnb     loc_1800F5259
0x1800f51c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f51d0  mov     edi, 8000FFFFh
0x1800f51d5  test    rcx, rcx
0x1800f51d8  jnz     short loc_1800F521B
0x1800f51da  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f51e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f51e7  mov     rcx, rax
0x1800f51ea  test    rax, rax
0x1800f51ed  jz      short loc_1800F520D
0x1800f51ef  mov     rax, [rax]
0x1800f51f2  mov     edx, 7F0h
0x1800f51f7  mov     rax, [rax+8]
0x1800f51fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5200  test    eax, eax
0x1800f5202  jz      short loc_1800F520D
0x1800f5204  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f520b  jmp     short loc_1800F521B
0x1800f520d  lea     rcx, qword_1801B07E0; this
0x1800f5214  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f521b  cmp     [rcx+8], r13b
0x1800f521f  jz      short loc_1800F5242
0x1800f5221  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f5226  cmp     [rax+7CCh], edi
0x1800f522c  jz      short loc_1800F5242
0x1800f522e  mov     r9d, edi; int
0x1800f5231  mov     r8d, 1F4h; int
0x1800f5237  mov     rdx, r14; char *
0x1800f523a  mov     rcx, rax; this
0x1800f523d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f5242  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800f5249  jb      loc_1800F5B8E
0x1800f524f  mov     edx, 3Fh ; '?'
0x1800f5254  jmp     loc_1800F5046
0x1800f5259  lea     rbx, WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids
0x1800f5260  test    r15b, cl
0x1800f5263  jz      loc_1800F5335
0x1800f5269  mov     r8d, r15d; unsigned int
0x1800f526c  mov     [rbp+arg_0], r13d
0x1800f5270  lea     rdx, [rbp+arg_0]; unsigned __int8 *
0x1800f5274  mov     rcx, rsi; this
0x1800f5277  call    ?WriteAsync@CWAVEStreamSink@@AEAAJPEBEI@Z; CWAVEStreamSink::WriteAsync(uchar const *,uint)
0x1800f527c  mov     edi, eax
0x1800f527e  test    eax, eax
0x1800f5280  jns     loc_1800F5314
0x1800f5286  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f528d  test    rcx, rcx
0x1800f5290  jnz     short loc_1800F52D3
0x1800f5292  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f5298  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f529f  mov     rcx, rax
0x1800f52a2  test    rax, rax
0x1800f52a5  jz      short loc_1800F52C5
0x1800f52a7  mov     rax, [rax]
0x1800f52aa  mov     edx, 7F0h
0x1800f52af  mov     rax, [rax+8]
0x1800f52b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f52b8  test    eax, eax
0x1800f52ba  jz      short loc_1800F52C5
0x1800f52bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f52c3  jmp     short loc_1800F52D3
0x1800f52c5  lea     rcx, qword_1801B07E0; this
0x1800f52cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f52d3  cmp     [rcx+8], r13b
0x1800f52d7  jz      short loc_1800F52FA
0x1800f52d9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f52de  cmp     [rax+7CCh], edi
0x1800f52e4  jz      short loc_1800F52FA
0x1800f52e6  mov     r9d, edi; int
0x1800f52e9  mov     r8d, 1FBh; int
0x1800f52ef  mov     rdx, r14; char *
0x1800f52f2  mov     rcx, rax; this
0x1800f52f5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f52fa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800f5301  jb      loc_1800F5B8E
0x1800f5307  mov     edx, 40h ; '@'
0x1800f530c  mov     r8, rbx
0x1800f530f  jmp     loc_1800F504D
0x1800f5314  cmp     cs:byte_1801B110A, 20h ; ' '
0x1800f531b  jb      short loc_1800F5335
0x1800f531d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f5324  mov     edx, 41h ; 'A'
0x1800f5329  mov     r8, rbx
0x1800f532c  mov     rcx, [rcx+60h]
0x1800f5330  call    WPP_SF_
0x1800f5335  mov     rcx, [rsi+188h]; this
0x1800f533c  test    rcx, rcx
0x1800f533f  jz      loc_1800F5529
0x1800f5345  call    ?IsCommitReady@CRIFFMetadata@@QEAAHXZ; CRIFFMetadata::IsCommitReady(void)
0x1800f534a  cmp     eax, r15d
0x1800f534d  jnz     loc_1800F5529
0x1800f5353  mov     rcx, [rsi+188h]; this
0x1800f535a  lea     r9, [rbp+arg_0]; unsigned int *
0x1800f535e  xor     r8d, r8d; int
0x1800f5361  mov     [rbp+arg_0], r13d
0x1800f5365  xor     edx, edx; unsigned __int8 *
0x1800f5367  call    ?WriteMetadata@CRIFFMetadata@@QEAAJPEAEHPEAK@Z; CRIFFMetadata::WriteMetadata(uchar *,int,ulong *)
0x1800f536c  test    eax, eax
0x1800f536e  js      loc_1800F5529
0x1800f5374  mov     r14d, [rbp+arg_0]
0x1800f5378  test    r14d, r14d
0x1800f537b  jz      loc_1800F5522
0x1800f5381  mov     ecx, r14d; unsigned __int64
0x1800f5384  mov     [rbp+arg_0], r13d
0x1800f5388  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800f538d  mov     r15, rax
0x1800f5390  test    rax, rax
0x1800f5393  jnz     loc_1800F542D
0x1800f5399  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f53a0  mov     edi, 8007000Eh
0x1800f53a5  test    rcx, rcx
0x1800f53a8  jnz     short loc_1800F53EB
0x1800f53aa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f53b0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f53b7  mov     rcx, rax
0x1800f53ba  test    rax, rax
0x1800f53bd  jz      short loc_1800F53DD
0x1800f53bf  mov     rax, [rax]
0x1800f53c2  mov     edx, 7F0h
0x1800f53c7  mov     rax, [rax+8]
0x1800f53cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f53d0  test    eax, eax
0x1800f53d2  jz      short loc_1800F53DD
0x1800f53d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f53db  jmp     short loc_1800F53EB
0x1800f53dd  lea     rcx, qword_1801B07E0; this
0x1800f53e4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f53eb  cmp     [rcx+8], r13b
0x1800f53ef  jz      short loc_1800F5416
0x1800f53f1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f53f6  cmp     [rax+7CCh], edi
0x1800f53fc  jz      short loc_1800F5416
0x1800f53fe  mov     r9d, edi; int
0x1800f5401  lea     rdx, aCwavestreamsin_9; "CWAVEStreamSink::WAVEHeaderUpdate"
0x1800f5408  mov     r8d, 20Bh; int
0x1800f540e  mov     rcx, rax; this
0x1800f5411  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f5416  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f541d  jb      loc_1800F5B8E
0x1800f5423  mov     edx, 42h ; 'B'
0x1800f5428  jmp     loc_1800F530C
0x1800f542d  mov     rcx, [rsi+188h]; this
0x1800f5434  lea     r9, [rbp+arg_0]; unsigned int *
0x1800f5438  mov     r8d, r14d; int
0x1800f543b  mov     rdx, r15; unsigned __int8 *
  ... truncated ...
```
