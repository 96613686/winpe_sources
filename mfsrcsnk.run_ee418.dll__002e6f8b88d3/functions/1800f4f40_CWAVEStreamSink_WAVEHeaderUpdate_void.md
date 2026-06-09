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
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rdx
  __int64 v7; // rax
  unsigned __int64 v8; // r12
  wchar_t *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  unsigned __int64 v25; // rcx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  CRIFFMetadata *v35; // rcx
  CRIFFMetadata *v36; // rcx
  unsigned int v37; // r14d
  unsigned __int64 v38; // rcx
  unsigned __int8 *v39; // rax
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  unsigned __int8 *v43; // r15
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  wchar_t *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rcx
  unsigned int v54; // eax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // r9
  wchar_t *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  unsigned int v61; // edx
  unsigned int v62; // eax
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // r9
  wchar_t *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  unsigned int v69; // eax
  unsigned int v70; // edx
  __int64 v71; // rdx
  __int64 v72; // r8
  __int64 v73; // r9
  wchar_t *v74; // rcx
  CallStackTracing *v75; // rax
  struct CallStackContext *v76; // rax
  __int64 v77; // rdx
  __int64 v78; // r8
  __int64 v79; // r9
  wchar_t *v80; // rcx
  CallStackTracing *v81; // rax
  struct CallStackContext *v82; // rax
  __int64 v83; // rdx
  __int64 v84; // r8
  __int64 v85; // r9
  wchar_t *v86; // rcx
  CallStackTracing *v87; // rax
  struct CallStackContext *v88; // rax
  __int64 v89; // rdx
  __int64 v90; // r8
  __int64 v91; // r9
  wchar_t *v92; // rcx
  CallStackTracing *v93; // rax
  struct CallStackContext *v94; // rax
  __int64 v95; // rdx
  __int64 v96; // r8
  __int64 v97; // r9
  wchar_t *v98; // rcx
  CallStackTracing *v99; // rax
  struct CallStackContext *v100; // rax
  __int64 v101; // rdx
  __int64 v102; // r8
  __int64 v103; // r9
  wchar_t *v104; // rcx
  CallStackTracing *v105; // rax
  struct CallStackContext *v106; // rax
  __int64 v107; // rdx
  unsigned __int64 v109[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v110; // [rsp+90h] [rbp+48h] BYREF
  int v111; // [rsp+98h] [rbp+50h] BYREF
  unsigned __int64 v112; // [rsp+A0h] [rbp+58h] BYREF
  unsigned __int64 v113; // [rsp+A8h] [rbp+60h] BYREF

  v1 = *((_QWORD *)this + 84);
  Size = v1 != 0 ? 0 : 0x80004003;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v110, "CWAVEStreamSink::WAVEHeaderUpdate", 482);
  v6 = *((_QWORD *)this + 57);
  v7 = *((unsigned int *)this + 172);
  v111 = 0;
  v110 = 0;
  v8 = (v6 & 1) - v7 + v6 - 4;
  v109[0] = v8;
  if ( v1 )
  {
    Size = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 48) + 24LL))(*((_QWORD *)this + 48), &v111);
    if ( Size >= 0 )
    {
      Size = CWAVEStreamSink::WAVEHeaderGetSize(this, &v110);
      if ( Size >= 0 )
      {
        v25 = *((_QWORD *)this + 57);
        if ( v25 >= v110 )
        {
          if ( (v25 & 1) != 0 )
          {
            v110 = 0;
            Size = CWAVEStreamSink::WriteAsync(this, (const unsigned __int8 *)&v110, 1u);
            if ( Size < 0 )
            {
              v32 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
                CallStackTracing::s_wpInstance = v33;
                if ( v33
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
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
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != Size )
                  CallStackContext::TraceFailure(ThreadRelativeContext, "CWAVEStreamSink::WAVEHeaderUpdate", 507, Size);
              }
              if ( g_wppLevels )
              {
                v12 = 64;
                goto LABEL_12;
              }
              goto LABEL_192;
            }
            if ( (unsigned __int8)byte_1801B110A >= 0x20u )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 65, &WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids);
          }
          v35 = (CRIFFMetadata *)*((_QWORD *)this + 49);
          if ( v35 )
          {
            if ( (unsigned int)CRIFFMetadata::IsCommitReady(v35) == 1 )
            {
              v36 = (CRIFFMetadata *)*((_QWORD *)this + 49);
              v110 = 0;
              if ( (int)CRIFFMetadata::WriteMetadata(v36, 0, 0, &v110) >= 0 )
              {
                v37 = v110;
                if ( v110 )
                {
                  v38 = v110;
                  v110 = 0;
                  v39 = (unsigned __int8 *)operator new[](v38);
                  v43 = v39;
                  if ( !v39 )
                  {
                    v44 = (wchar_t *)CallStackTracing::s_wpInstance;
                    Size = -2147024882;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40, v41, v42);
                      CallStackTracing::s_wpInstance = v45;
                      if ( v45
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(
                             v45,
                             2032) )
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
                      if ( *((_DWORD *)v46 + 499) != -2147024882 )
                        CallStackContext::TraceFailure(v46, "CWAVEStreamSink::WAVEHeaderUpdate", 523, -2147024882);
                    }
                    if ( g_wppLevels )
                    {
                      v12 = 66;
                      goto LABEL_12;
                    }
                    goto LABEL_192;
                  }
                  Size = CRIFFMetadata::WriteMetadata(*((CRIFFMetadata **)this + 49), v39, v37, &v110);
                  if ( Size >= 0 )
                  {
                    Size = CWAVEStreamSink::WriteAsync(this, v43, v37);
                    if ( (unsigned __int8)byte_1801B110A >= 0x20u )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 12),
                        67,
                        &WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids,
                        v37);
                  }
                  operator delete(v43);
                  if ( Size < 0 )
                  {
                    v50 = (wchar_t *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47, v48, v49);
                      CallStackTracing::s_wpInstance = v51;
                      if ( v51
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(
                             v51,
                             2032) )
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
                        CallStackContext::TraceFailure(v52, "CWAVEStreamSink::WAVEHeaderUpdate", 535, Size);
                    }
                    if ( g_wppLevels )
                    {
                      v12 = 68;
                      goto LABEL_12;
                    }
                    goto LABEL_192;
                  }
                }
              }
            }
          }
          if ( (v111 & 4) != 0 )
          {
            v53 = *((_QWORD *)this + 57);
            v112 = 0;
            v54 = -1;
            v113 = (v53 & 1) + v53 - 8;
            if ( v113 <= 0xFFFFFFFF )
              v54 = (v53 & 1) + v53 - 8;
            v110 = v54;
            Size = CWAVEStreamSink::SeekAndWrite(this, 4u, &v110, 4u);
            if ( Size < 0 )
            {
              v58 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56, v57);
                CallStackTracing::s_wpInstance = v59;
                if ( v59
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
                {
                  v58 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v58 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v58 + 8) )
              {
                v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
                if ( *((_DWORD *)v60 + 499) != Size )
                  CallStackContext::TraceFailure(v60, "CWAVEStreamSink::WAVEHeaderUpdate", 547, Size);
              }
              if ( g_wppLevels )
              {
                v12 = 69;
                goto LABEL_12;
              }
              goto LABEL_192;
            }
            v61 = *((_DWORD *)this + 172);
            v62 = -1;
            if ( v8 <= 0xFFFFFFFF )
              v62 = v8;
            v110 = v62;
            Size = CWAVEStreamSink::SeekAndWrite(this, v61, &v110, 4u);
            if ( Size < 0 )
            {
              v66 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v63, v64, v65);
                CallStackTracing::s_wpInstance = v67;
                if ( v67
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
                {
                  v66 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v66 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v66 + 8) )
              {
                v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
                if ( *((_DWORD *)v68 + 499) != Size )
                  CallStackContext::TraceFailure(v68, "CWAVEStreamSink::WAVEHeaderUpdate", 551, Size);
              }
              if ( g_wppLevels )
              {
                v12 = 70;
                goto LABEL_12;
              }
              goto LABEL_192;
            }
            if ( *((_DWORD *)this + 171) )
            {
              v69 = -1;
              v112 = *((_QWORD *)this + 58) * *(unsigned int *)(*((_QWORD *)this + 84) + 4LL) / 10000000LL;
              if ( v112 <= 0xFFFFFFFF )
                v69 = v112;
              v70 = *((_DWORD *)this + 173);
              v110 = v69;
              Size = CWAVEStreamSink::SeekAndWrite(this, v70, &v110, 4u);
              if ( Size < 0 )
              {
                v74 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v75 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v71, v72, v73);
                  CallStackTracing::s_wpInstance = v75;
                  if ( v75
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v75 + 8LL))(v75, 2032) )
                  {
                    v74 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v74 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v74 + 8) )
                {
                  v76 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v74);
                  if ( *((_DWORD *)v76 + 499) != Size )
                    CallStackContext::TraceFailure(v76, "CWAVEStreamSink::WAVEHeaderUpdate", 560, Size);
                }
                if ( g_wppLevels )
                {
                  v12 = 71;
                  goto LABEL_12;
                }
                goto LABEL_192;
              }
            }
            if ( *((_QWORD *)this + 57) + (*((_QWORD *)this + 57) & 1uLL) <= 0xFFFFFFFF )
              goto LABEL_192;
            v110 = 875972178;
            Size = CWAVEStreamSink::SeekAndWrite(this, 0, &v110, 4u);
            if ( Size < 0 )
            {
              v80 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v81 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v77, v78, v79);
                CallStackTracing::s_wpInstance = v81;
                if ( v81
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v81 + 8LL))(v81, 2032) )
                {
                  v80 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v80 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v80 + 8) )
              {
                v82 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v80);
                if ( *((_DWORD *)v82 + 499) != Size )
                  CallStackContext::TraceFailure(v82, "CWAVEStreamSink::WAVEHeaderUpdate", 570, Size);
              }
              if ( g_wppLevels )
              {
                v12 = 72;
                goto LABEL_12;
              }
              goto LABEL_192;
            }
            v110 = 875983716;
            Size = CWAVEStreamSink::SeekAndWrite(this, 0xCu, &v110, 4u);
            if ( Size < 0 )
            {
              v86 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v87 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v83, v84, v85);
                CallStackTracing::s_wpInstance = v87;
                if ( v87
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v87 + 8LL))(v87, 2032) )
                {
                  v86 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v86 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v86 + 8) )
              {
                v88 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v86);
                if ( *((_DWORD *)v88 + 499) != Size )
                  CallStackContext::TraceFailure(v88, "CWAVEStreamSink::WAVEHeaderUpdate", 574, Size);
              }
              if ( g_wppLevels )
              {
                v12 = 73;
                goto LABEL_12;
              }
              goto LABEL_192;
            }
            Size = CWAVEStreamSink::SeekAndWrite(this, 0x14u, &v113, 8u);
            if ( Size < 0 )
            {
              v92 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v93 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v89, v90, v91);
                CallStackTracing::s_wpInstance = v93;
                if ( v93
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v93 + 8LL))(v93, 2032) )
                {
                  v92 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v92 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v92 + 8) )
              {
                v94 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v92);
                if ( *((_DWORD *)v94 + 499) != Size )
                  CallStackContext::TraceFailure(v94, "CWAVEStreamSink::WAVEHeaderUpdate", 577, Size);
              }
              if ( g_wppLevels )
              {
                v12 = 74;
                goto LABEL_12;
              }
              goto LABEL_192;
            }
            Size = CWAVEStreamSink::SeekAndWrite(this, 0x1Cu, v109, 8u);
            if ( Size < 0 )
            {
              v98 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v99 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v95, v96, v97);
                CallStackTracing::s_wpInstance = v99;
                if ( v99
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v99 + 8LL))(v99, 2032) )
                {
                  v98 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v98 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v98 + 8) )
              {
                v100 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v98);
                if ( *((_DWORD *)v100 + 499) != Size )
                  CallStackContext::TraceFailure(v100, "CWAVEStreamSink::WAVEHeaderUpdate", 579, Size);
              }
              if ( g_wppLevels )
              {
                v12 = 75;
                goto LABEL_12;
              }
              goto LABEL_192;
            }
            if ( *((_DWORD *)this + 171) )
            {
              Size = CWAVEStreamSink::SeekAndWrite(this, 0x24u, &v112, 8u);
              if ( Size < 0 )
              {
                v104 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v105 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v101, v102, v103);
                  CallStackTracing::s_wpInstance = v105;
                  if ( v105
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v105 + 8LL))(v105, 2032) )
                  {
                    v104 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v104 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v104 + 8) )
                {
                  v106 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v104);
                  if ( *((_DWORD *)v106 + 499) != Size )
                    CallStackContext::TraceFailure(v106, "CWAVEStreamSink::WAVEHeaderUpdate", 584, Size);
                }
                if ( g_wppLevels )
                {
                  v12 = 76;
                  goto LABEL_12;
                }
                goto LABEL_192;
              }
            }
            if ( (unsigned __int8)byte_1801B110A < 8u )
              goto LABEL_192;
            v107 = 77;
          }
          else
          {
            if ( (unsigned __int8)byte_1801B110A < 8u )
              goto LABEL_192;
            v107 = 78;
          }
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), v107, &WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids);
          goto LABEL_192;
        }
        v26 = (wchar_t *)CallStackTracing::s_wpInstance;
        Size = -2147418113;
        if ( !CallStackTracing::s_wpInstance )
        {
          v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
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
            CallStackContext::TraceFailure(v28, "CWAVEStreamSink::WAVEHeaderUpdate", 500, -2147418113);
        }
        if ( g_wppLevels )
        {
          v12 = 63;
          goto LABEL_12;
        }
      }
      else
      {
        v22 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
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
          if ( *((_DWORD *)v24 + 499) != Size )
            CallStackContext::TraceFailure(v24, "CWAVEStreamSink::WAVEHeaderUpdate", 495, Size);
        }
        if ( g_wppLevels )
        {
          v12 = 62;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v16 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
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
          CallStackContext::TraceFailure(v18, "CWAVEStreamSink::WAVEHeaderUpdate", 493, Size);
      }
      if ( g_wppLevels )
      {
        v12 = 61;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v9 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v4, v5);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)v11 + 499) != Size )
        CallStackContext::TraceFailure(v11, "CWAVEStreamSink::WAVEHeaderUpdate", 491, Size);
    }
    if ( g_wppLevels )
    {
      v12 = 60;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids, this, Size);
    }
  }
LABEL_192:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v110);
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
