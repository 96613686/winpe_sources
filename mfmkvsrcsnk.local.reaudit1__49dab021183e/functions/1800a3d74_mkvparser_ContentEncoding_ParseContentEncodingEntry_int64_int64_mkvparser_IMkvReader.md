# mkvparser::ContentEncoding::ParseContentEncodingEntry(__int64,__int64,mkvparser::IMkvReader *)

- ea: `0x1800a3d74`
- end: `0x1800a4ad6`
- name: `?ParseContentEncodingEntry@ContentEncoding@mkvparser@@QEAAJ_J0PEAUIMkvReader@2@@Z`
- size: `3426`
- prototype: `__int64 __fastcall(mkvparser::ContentEncoding *__hidden this, __int64, __int64, struct mkvparser::IMkvReader *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800a4adc`

## callees

- `0x180001ff0`
- `0x180002430`
- `0x180003760`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x180087c70`
- `0x180087ccc`
- `0x1800a3480`
- `0x1800a3d74`
- `0x1800a5fec`
- `0x1800a649c`
- `0x1800af7b0`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3e51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3f29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3fee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a40c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a41ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4332`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a44dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a45c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a465b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a46f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a478d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a482f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a48e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a497d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4a30`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3e51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3f29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3fee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a40c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a41ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4332`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a44dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a45c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a465b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a46f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a478d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a482f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a48e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a497d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4a30`

## pseudocode

```c
__int64 __fastcall mkvparser::ContentEncoding::ParseContentEncodingEntry(
        mkvparser::ContentEncoding *this,
        struct mkvparser::IMkvReader *a2,
        __int64 a3,
        struct mkvparser::IMkvReader *a4)
{
  __int64 *v4; // r14
  int v5; // r12d
  int v6; // r15d
  struct mkvparser::IMkvReader *v7; // r13
  struct mkvparser::IMkvReader *v8; // rsi
  __int64 *v10; // rbx
  __int64 v11; // rdx
  int v12; // ebx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v18; // rdx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  unsigned __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  unsigned __int64 v39; // rax
  void *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  struct mkvparser::IMkvReader *v50; // rsi
  __int64 v51; // r13
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // r9
  __int64 v58; // rax
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // r9
  mkvparser::ContentEncoding::ContentCompression *v64; // rax
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 v67; // r9
  mkvparser::ContentEncoding::ContentCompression *v68; // r14
  mkvparser *v69; // r9
  unsigned int v70; // edx
  mkvparser::ContentEncoding::ContentEncryption *v71; // rax
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // r9
  mkvparser::ContentEncoding::ContentEncryption *v75; // rbx
  mkvparser *v76; // r9
  unsigned int v77; // edx
  int v78; // r14d
  __int64 *v79; // rcx
  CallStackTracing *v80; // rax
  struct CallStackContext *v81; // rax
  struct CallStackContext *v82; // rax
  __int64 *v83; // rcx
  CallStackTracing *v84; // rax
  struct CallStackContext *v85; // rax
  __int64 *v86; // rcx
  CallStackTracing *v87; // rax
  struct CallStackContext *v88; // rax
  __int64 v89; // rdx
  __int64 v90; // r8
  __int64 v91; // r9
  __int64 *v92; // rcx
  CallStackTracing *v93; // rax
  struct CallStackContext *v94; // rax
  __int64 *v95; // rcx
  CallStackTracing *v96; // rax
  struct CallStackContext *v97; // rax
  __int64 v98; // rdx
  __int64 v99; // r8
  __int64 v100; // r9
  __int64 *v101; // rcx
  CallStackTracing *v102; // rax
  struct CallStackContext *v103; // rax
  __int64 *v104; // rcx
  CallStackTracing *v105; // rax
  struct CallStackContext *v106; // rax
  __int64 *v107; // rcx
  CallStackTracing *v108; // rax
  struct CallStackContext *v109; // rax
  __int64 v110; // rdx
  __int64 v111; // r8
  __int64 v112; // r9
  __int64 *v113; // rcx
  CallStackTracing *v114; // rax
  struct CallStackContext *v115; // rax
  __int64 *v116; // [rsp+20h] [rbp-30h]
  __int64 *v117; // [rsp+28h] [rbp-28h]
  __int64 v118; // [rsp+30h] [rbp-20h] BYREF
  __int64 v119; // [rsp+38h] [rbp-18h] BYREF
  __int64 *v120; // [rsp+40h] [rbp-10h]
  __int64 v121; // [rsp+98h] [rbp+48h] BYREF
  struct mkvparser::IMkvReader *v122; // [rsp+A0h] [rbp+50h] BYREF
  mkvparser *v123; // [rsp+A8h] [rbp+58h]

  v123 = a4;
  v4 = (__int64 *)((char *)a2 + a3);
  v122 = a2;
  v5 = 0;
  v120 = (__int64 *)((char *)a2 + a3);
  v6 = 0;
  v118 = 0;
  v7 = a4;
  v119 = 0;
  v8 = a2;
  v10 = (__int64 *)a2;
  while ( (__int64)v10 < (__int64)v4 )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v121,
      "mkvparser::ContentEncoding::ParseContentEncodingEntry",
      5032);
    v12 = mkvparser::ParseElementHeader(v7, (struct mkvparser::IMkvReader *)&v122, v4, (__int64)&v118, &v119, v117);
    if ( v12 < 0 )
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v13, v14);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v12 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "mkvparser::ContentEncoding::ParseContentEncodingEntry",
            5032,
            v12);
      }
      if ( !g_wppLevels )
        goto LABEL_22;
      v18 = 423;
      goto LABEL_21;
    }
    if ( v118 == 20532 )
    {
      if ( v5 == 0x7FFFFFFF )
        goto LABEL_10;
      ++v5;
    }
    if ( v118 == 20533 && v6 != 0x7FFFFFFF )
      ++v6;
LABEL_10:
    v10 = (__int64 *)((char *)v122 + v119);
    v122 = (struct mkvparser::IMkvReader *)((char *)v122 + v119);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v121);
  }
  if ( v10 != v4 )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v121,
      "mkvparser::ContentEncoding::ParseContentEncodingEntry",
      5045);
    v23 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
      CallStackTracing::s_wpInstance = v24;
      if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v23 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    v12 = -1072875842;
    if ( *((_BYTE *)v23 + 8) )
    {
      v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
      if ( *((_DWORD *)v25 + 499) != -1072875842 )
        CallStackContext::TraceFailure(v25, "mkvparser::ContentEncoding::ParseContentEncodingEntry", 5045, -1072875842);
    }
    if ( !g_wppLevels )
      goto LABEL_22;
    v18 = 424;
    goto LABEL_21;
  }
  if ( v5 > 0 )
  {
    v32 = 8LL * v5;
    if ( !is_mul_ok(v5, 8u) )
      v32 = -1;
    *(_QWORD *)this = operator new[](v32, (const struct std::nothrow_t *)&std::nothrow);
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v121,
      "mkvparser::ContentEncoding::ParseContentEncodingEntry",
      5055);
    if ( !*(_QWORD *)this )
    {
      v36 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34, v35);
        CallStackTracing::s_wpInstance = v37;
        if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
        {
          v36 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v36 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      v12 = -2147024882;
      if ( *((_BYTE *)v36 + 8) )
      {
        v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
        if ( *((_DWORD *)v38 + 499) != -2147024882 )
          CallStackContext::TraceFailure(
            v38,
            "mkvparser::ContentEncoding::ParseContentEncodingEntry",
            5055,
            -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_22;
      v18 = 426;
LABEL_21:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, this, v12);
      goto LABEL_22;
    }
    *((_QWORD *)this + 1) = *(_QWORD *)this;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v121);
    if ( v6 > 0 )
      goto LABEL_60;
  }
  else
  {
    if ( v6 <= 0 )
    {
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)&v121,
        "mkvparser::ContentEncoding::ParseContentEncodingEntry",
        5050);
      v29 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
        CallStackTracing::s_wpInstance = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      v12 = -2147467259;
      if ( *((_BYTE *)v29 + 8) )
      {
        v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
        if ( *((_DWORD *)v31 + 499) != -2147467259 )
          CallStackContext::TraceFailure(
            v31,
            "mkvparser::ContentEncoding::ParseContentEncodingEntry",
            5050,
            -2147467259);
      }
      if ( !g_wppLevels )
        goto LABEL_22;
      v18 = 425;
      goto LABEL_21;
    }
LABEL_60:
    v39 = 8LL * v6;
    if ( !is_mul_ok(v6, 8u) )
      v39 = -1;
    v40 = operator new[](v39, (const struct std::nothrow_t *)&std::nothrow);
    *((_QWORD *)this + 2) = v40;
    if ( !v40 )
    {
      operator delete(*(void **)this);
      *(_QWORD *)this = 0;
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)&v121,
        "mkvparser::ContentEncoding::ParseContentEncodingEntry",
        5064);
      v44 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42, v43);
        CallStackTracing::s_wpInstance = v45;
        if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
        {
          v44 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v44 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      v12 = -2147024882;
      if ( *((_BYTE *)v44 + 8) )
      {
        v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
        if ( *((_DWORD *)v46 + 499) != -2147024882 )
          CallStackContext::TraceFailure(
            v46,
            "mkvparser::ContentEncoding::ParseContentEncodingEntry",
            5064,
            -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_22;
      v18 = 427;
      goto LABEL_21;
    }
    *((_QWORD *)this + 3) = v40;
  }
  v122 = v8;
  while ( 2 )
  {
    if ( (__int64)v8 < (__int64)v4 )
    {
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)&v121,
        "mkvparser::ContentEncoding::ParseContentEncodingEntry",
        5071);
      v12 = mkvparser::ParseElementHeader(v7, (struct mkvparser::IMkvReader *)&v122, v4, (__int64)&v118, &v119, v117);
      if ( v12 < 0 )
      {
        v107 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v108 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47, v48, v49);
          CallStackTracing::s_wpInstance = v108;
          if ( v108 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v108 + 8LL))(v108, 2032) )
          {
            v107 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v107 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v107 + 8) )
        {
          v109 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v107);
          if ( *((_DWORD *)v109 + 499) != v12 )
            CallStackContext::TraceFailure(v109, "mkvparser::ContentEncoding::ParseContentEncodingEntry", 5071, v12);
        }
        if ( g_wppLevels )
        {
          v18 = 428;
          goto LABEL_21;
        }
        goto LABEL_22;
      }
      v50 = v122;
      v51 = v119;
      v121 = 0;
      switch ( v118 )
      {
        case 20529LL:
          v12 = mkvparser::UnserializeUInt(v123, v122, v119, (__int64)&v121, v116);
          if ( v12 < 0 )
          {
            v79 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v80 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53, v54);
              CallStackTracing::s_wpInstance = v80;
              if ( v80
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v80 + 8LL))(v80, 2032) )
              {
                v79 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v79 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            if ( *((_BYTE *)v79 + 8) )
            {
              v81 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v79);
              if ( *((_DWORD *)v81 + 499) != v12 )
                CallStackContext::TraceFailure(v81, "mkvparser::ContentEncoding::ParseContentEncodingEntry", 5076, v12);
            }
            if ( g_wppLevels )
            {
              v18 = 429;
              goto LABEL_21;
            }
            goto LABEL_22;
          }
          *((_QWORD *)this + 4) = v121;
          break;
        case 20530LL:
          v12 = mkvparser::UnserializeUInt(v123, v122, v119, (__int64)&v121, v116);
          if ( v12 < 0 )
          {
            v83 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v84 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56, v57);
              CallStackTracing::s_wpInstance = v84;
              if ( v84
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v84 + 8LL))(v84, 2032) )
              {
                v83 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v83 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            if ( *((_BYTE *)v83 + 8) )
            {
              v85 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v83);
              if ( *((_DWORD *)v85 + 499) != v12 )
                CallStackContext::TraceFailure(v85, "mkvparser::ContentEncoding::ParseContentEncodingEntry", 5080, v12);
            }
            if ( g_wppLevels )
            {
              v18 = 430;
              goto LABEL_21;
            }
            goto LABEL_22;
          }
          v58 = v121;
          *((_QWORD *)this + 5) = v121;
          if ( !v58 )
          {
            v59 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56, v57);
              CallStackTracing::s_wpInstance = v60;
              if ( v60
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
              {
                v59 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v59 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            v12 = -1072875842;
            if ( *((_BYTE *)v59 + 8) )
            {
              v82 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
              if ( *((_DWORD *)v82 + 499) != -1072875842 )
                CallStackContext::TraceFailure(
                  v82,
                  "mkvparser::ContentEncoding::ParseContentEncodingEntry",
                  5085,
                  -1072875842);
            }
            if ( g_wppLevels )
            {
              v18 = 431;
              goto LABEL_21;
            }
            goto LABEL_22;
          }
          break;
        case 20531LL:
          v12 = mkvparser::UnserializeUInt(v123, v122, v119, (__int64)&v121, v116);
          if ( v12 < 0 )
          {
            v86 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v87 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v61, v62, v63);
              CallStackTracing::s_wpInstance = v87;
              if ( v87
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v87 + 8LL))(v87, 2032) )
              {
                v86 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v86 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            if ( *((_BYTE *)v86 + 8) )
            {
              v88 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v86);
              if ( *((_DWORD *)v88 + 499) != v12 )
                CallStackContext::TraceFailure(v88, "mkvparser::ContentEncoding::ParseContentEncodingEntry", 5088, v12);
            }
            if ( g_wppLevels )
            {
              v18 = 432;
              goto LABEL_21;
            }
            goto LABEL_22;
          }
          *((_QWORD *)this + 6) = v121;
          break;
        case 20532LL:
          if ( v5 > 0 )
          {
            v64 = (mkvparser::ContentEncoding::ContentCompression *)operator new(
                                                                      0x18u,
                                                                      (const struct std::nothrow_t *)&std::nothrow);
            v68 = v64;
            if ( !v64 )
            {
              v95 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v96 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v65, v66, v67);
                CallStackTracing::s_wpInstance = v96;
                if ( v96
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v96 + 8LL))(v96, 2032) )
                {
                  v95 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v95 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                }
              }
              v12 = -2147024882;
              if ( *((_BYTE *)v95 + 8) )
              {
                v97 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v95);
                if ( *((_DWORD *)v97 + 499) != -2147024882 )
                  CallStackContext::TraceFailure(
                    v97,
                    "mkvparser::ContentEncoding::ParseContentEncodingEntry",
                    5093,
                    -2147024882);
              }
              if ( g_wppLevels )
              {
                v18 = 433;
                goto LABEL_21;
              }
              goto LABEL_22;
            }
            v69 = v123;
            *(_QWORD *)v64 = 0;
            *((_QWORD *)v64 + 1) = 0;
            *((_QWORD *)v64 + 2) = 0;
            v12 = mkvparser::ContentEncoding::ParseCompressionEntry(this, v50, v51, v69, v64);
            if ( v12 < 0 )
            {
              mkvparser::ContentEncoding::ContentCompression::`scalar deleting destructor'(v68, v70);
              v92 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v93 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v89, v90, v91);
                CallStackTracing::s_wpInstance = v93;
                if ( v93
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v93 + 8LL))(v93, 2032) )
                {
                  v92 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v92 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                }
              }
              if ( *((_BYTE *)v92 + 8) )
              {
                v94 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v92);
                if ( *((_DWORD *)v94 + 499) != v12 )
                  CallStackContext::TraceFailure(
                    v94,
                    "mkvparser::ContentEncoding::ParseContentEncodingEntry",
                    5098,
                    v12);
              }
              if ( g_wppLevels )
              {
                v18 = 434;
                goto LABEL_21;
              }
              goto LABEL_22;
            }
            **((_QWORD **)this + 1) = v68;
            *((_QWORD *)this + 1) += 8LL;
            --v5;
            goto LABEL_100;
          }
          break;
        default:
          if ( v118 == 20533 && v6 > 0 )
          {
            v71 = (mkvparser::ContentEncoding::ContentEncryption *)operator new(
                                                                     0x50u,
                                                                     (const struct std::nothrow_t *)&std::nothrow);
            v75 = v71;
            if ( !v71 )
            {
              v104 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v105 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v72, v73, v74);
                CallStackTracing::s_wpInstance = v105;
                if ( v105
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v105 + 8LL))(v105, 2032) )
                {
                  v104 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v104 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                }
              }
              v12 = -2147024882;
              if ( *((_BYTE *)v104 + 8) )
              {
                v106 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v104);
                if ( *((_DWORD *)v106 + 499) != -2147024882 )
                  CallStackContext::TraceFailure(
                    v106,
                    "mkvparser::ContentEncoding::ParseContentEncodingEntry",
                    5104,
                    -2147024882);
              }
              if ( g_wppLevels )
              {
                v18 = 435;
                goto LABEL_21;
              }
              goto LABEL_22;
            }
            v76 = v123;
            *(_QWORD *)v71 = 0;
            *((_QWORD *)v71 + 1) = 0;
            *((_QWORD *)v71 + 2) = 0;
            *((_QWORD *)v71 + 3) = 0;
            *((_QWORD *)v71 + 4) = 0;
            *((_QWORD *)v71 + 5) = 0;
            *((_QWORD *)v71 + 6) = 0;
            *((_QWORD *)v71 + 7) = 0;
            *((_QWORD *)v71 + 8) = 0;
            *((_QWORD *)v71 + 9) = 1;
            v78 = mkvparser::ContentEncoding::ParseEncryptionEntry(this, (__int64)v50, v51, v76, v71);
            if ( v78 < 0 )
            {
              mkvparser::ContentEncoding::ContentEncryption::`scalar deleting destructor'(v75, v77);
              v101 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v102 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v98, v99, v100);
                CallStackTracing::s_wpInstance = v102;
                if ( v102
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v102 + 8LL))(v102, 2032) )
                {
                  v101 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v101 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                }
              }
              if ( *((_BYTE *)v101 + 8) )
              {
                v103 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v101);
                if ( *((_DWORD *)v103 + 499) != v78 )
                  CallStackContext::TraceFailure(
                    v103,
                    "mkvparser::ContentEncoding::ParseContentEncodingEntry",
                    5109,
                    v78);
              }
              if ( g_wppLevels )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  436,
                  WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids,
                  this,
                  v78);
              v12 = v78;
              goto LABEL_22;
            }
            **((_QWORD **)this + 3) = v75;
            *((_QWORD *)this + 3) += 8LL;
            --v6;
LABEL_100:
            v4 = v120;
          }
          break;
      }
      v8 = (struct mkvparser::IMkvReader *)((char *)v50 + v51);
      v122 = v8;
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v121);
      v7 = v123;
      continue;
    }
    break;
  }
  if ( v8 == (struct mkvparser::IMkvReader *)v4 )
    return 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v121,
    "mkvparser::ContentEncoding::ParseContentEncodingEntry",
    5120);
  v113 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v114 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v110, v111, v112);
    CallStackTracing::s_wpInstance = v114;
    if ( v114 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v114 + 8LL))(v114, 2032) )
    {
      v113 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v113 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  v12 = -1072875842;
  if ( *((_BYTE *)v113 + 8) )
  {
    v115 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v113);
    if ( *((_DWORD *)v115 + 499) != -1072875842 )
      CallStackContext::TraceFailure(v115, "mkvparser::ContentEncoding::ParseContentEncodingEntry", 5120, -1072875842);
  }
  if ( g_wppLevels )
  {
    v18 = 437;
    goto LABEL_21;
  }
LABEL_22:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v121);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800a3d74  mov     [rsp-38h+arg_0], rbx
0x1800a3d79  mov     [rsp-38h+arg_18], r9
0x1800a3d7e  push    rbp
0x1800a3d7f  push    rsi
0x1800a3d80  push    rdi
0x1800a3d81  push    r12
0x1800a3d83  push    r13
0x1800a3d85  push    r14
0x1800a3d87  push    r15
0x1800a3d89  mov     rbp, rsp
0x1800a3d8c  sub     rsp, 50h
0x1800a3d90  lea     r14, [rdx+r8]
0x1800a3d94  mov     [rbp+arg_10], rdx
0x1800a3d98  xor     r12d, r12d
0x1800a3d9b  mov     [rbp+var_10], r14
0x1800a3d9f  xor     r15d, r15d
0x1800a3da2  mov     [rbp+var_20], 0
0x1800a3daa  mov     r13, r9
0x1800a3dad  mov     [rbp+var_18], 0
0x1800a3db5  mov     rsi, rdx
0x1800a3db8  mov     rdi, rcx
0x1800a3dbb  mov     rbx, rdx
0x1800a3dbe  cmp     rbx, r14
0x1800a3dc1  jge     loc_1800A3EFF
0x1800a3dc7  mov     r8d, 13A8h; int
0x1800a3dcd  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x1800a3dd4  lea     rcx, [rbp+arg_8]; this
0x1800a3dd8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a3ddd  lea     rax, [rbp+var_18]
0x1800a3de1  mov     r8, r14; __int64 *
0x1800a3de4  lea     r9, [rbp+var_20]; __int64
0x1800a3de8  mov     [rsp+50h+var_30], rax; __int64 *
0x1800a3ded  lea     rdx, [rbp+arg_10]; struct mkvparser::IMkvReader *
0x1800a3df1  mov     rcx, r13; this
0x1800a3df4  call    ?ParseElementHeader@mkvparser@@YAJPEAUIMkvReader@1@AEA_J_J11@Z; mkvparser::ParseElementHeader(mkvparser::IMkvReader *,__int64 &,__int64,__int64 &,__int64 &)
0x1800a3df9  mov     ebx, eax
0x1800a3dfb  test    eax, eax
0x1800a3dfd  js      short loc_1800A3E45
0x1800a3dff  cmp     [rbp+var_20], 5034h
0x1800a3e07  jnz     short loc_1800A3E15
0x1800a3e09  cmp     r12d, 7FFFFFFFh
0x1800a3e10  jge     short loc_1800A3E2B
0x1800a3e12  inc     r12d
0x1800a3e15  cmp     [rbp+var_20], 5035h
0x1800a3e1d  jnz     short loc_1800A3E2B
0x1800a3e1f  cmp     r15d, 7FFFFFFFh
0x1800a3e26  jge     short loc_1800A3E2B
0x1800a3e28  inc     r15d
0x1800a3e2b  mov     rbx, [rbp+arg_10]
0x1800a3e2f  lea     rcx, [rbp+arg_8]; this
0x1800a3e33  add     rbx, [rbp+var_18]
0x1800a3e37  mov     [rbp+arg_10], rbx
0x1800a3e3b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a3e40  jmp     loc_1800A3DBE
0x1800a3e45  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3e4c  test    rcx, rcx
0x1800a3e4f  jnz     short loc_1800A3E98
0x1800a3e51  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a3e58  nop     dword ptr [rax+rax+00h]
0x1800a3e5d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3e64  mov     rcx, rax
0x1800a3e67  test    rax, rax
0x1800a3e6a  jz      short loc_1800A3E8A
0x1800a3e6c  mov     rax, [rax]
0x1800a3e6f  mov     edx, 7F0h
0x1800a3e74  mov     rax, [rax+8]
0x1800a3e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3e7d  test    eax, eax
0x1800a3e7f  jz      short loc_1800A3E8A
0x1800a3e81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3e88  jmp     short loc_1800A3E98
0x1800a3e8a  lea     rcx, qword_1800DBF70; this
0x1800a3e91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3e98  cmp     byte ptr [rcx+8], 0
0x1800a3e9c  jz      short loc_1800A3EC3
0x1800a3e9e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a3ea3  cmp     [rax+7CCh], ebx
0x1800a3ea9  jz      short loc_1800A3EC3
0x1800a3eab  mov     r9d, ebx; int
0x1800a3eae  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x1800a3eb5  mov     r8d, 13A8h; int
0x1800a3ebb  mov     rcx, rax; this
0x1800a3ebe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a3ec3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a3eca  jb      short loc_1800A3EEF
0x1800a3ecc  mov     edx, 1A7h
0x1800a3ed1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a3ed8  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x1800a3edf  mov     r9, rdi
0x1800a3ee2  mov     dword ptr [rsp+50h+var_30], ebx
0x1800a3ee6  mov     rcx, [rcx+10h]
0x1800a3eea  call    WPP_SF_qD
0x1800a3eef  lea     rcx, [rbp+arg_8]; this
0x1800a3ef3  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a3ef8  mov     eax, ebx
0x1800a3efa  jmp     loc_1800A4ABD
0x1800a3eff  jz      loc_1800A3FB4
0x1800a3f05  mov     esi, 13B5h
0x1800a3f0a  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x1800a3f11  mov     r8d, esi; int
0x1800a3f14  lea     rcx, [rbp+arg_8]; this
0x1800a3f18  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a3f1d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3f24  test    rcx, rcx
0x1800a3f27  jnz     short loc_1800A3F70
0x1800a3f29  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a3f30  nop     dword ptr [rax+rax+00h]
0x1800a3f35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3f3c  mov     rcx, rax
0x1800a3f3f  test    rax, rax
0x1800a3f42  jz      short loc_1800A3F62
0x1800a3f44  mov     rax, [rax]
0x1800a3f47  mov     edx, 7F0h
0x1800a3f4c  mov     rax, [rax+8]
0x1800a3f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3f55  test    eax, eax
0x1800a3f57  jz      short loc_1800A3F62
0x1800a3f59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3f60  jmp     short loc_1800A3F70
0x1800a3f62  lea     rcx, qword_1800DBF70; this
0x1800a3f69  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3f70  cmp     byte ptr [rcx+8], 0
0x1800a3f74  mov     ebx, 0C00D36BEh
0x1800a3f79  jz      short loc_1800A3F9D
0x1800a3f7b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a3f80  cmp     [rax+7CCh], ebx
0x1800a3f86  jz      short loc_1800A3F9D
0x1800a3f88  mov     r9d, ebx; int
0x1800a3f8b  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x1800a3f92  mov     r8d, esi; int
0x1800a3f95  mov     rcx, rax; this
0x1800a3f98  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a3f9d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a3fa4  jb      loc_1800A3EEF
0x1800a3faa  mov     edx, 1A8h
0x1800a3faf  jmp     loc_1800A3ED1
0x1800a3fb4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a3fb8  test    r12d, r12d
0x1800a3fbb  jg      loc_1800A4079
0x1800a3fc1  test    r15d, r15d
0x1800a3fc4  jg      loc_1800A416C
0x1800a3fca  mov     esi, 13BAh
0x1800a3fcf  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x1800a3fd6  mov     r8d, esi; int
0x1800a3fd9  lea     rcx, [rbp+arg_8]; this
0x1800a3fdd  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a3fe2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3fe9  test    rcx, rcx
0x1800a3fec  jnz     short loc_1800A4035
0x1800a3fee  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a3ff5  nop     dword ptr [rax+rax+00h]
0x1800a3ffa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4001  mov     rcx, rax
0x1800a4004  test    rax, rax
0x1800a4007  jz      short loc_1800A4027
0x1800a4009  mov     rax, [rax]
0x1800a400c  mov     edx, 7F0h
0x1800a4011  mov     rax, [rax+8]
0x1800a4015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a401a  test    eax, eax
0x1800a401c  jz      short loc_1800A4027
0x1800a401e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4025  jmp     short loc_1800A4035
0x1800a4027  lea     rcx, qword_1800DBF70; this
0x1800a402e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4035  cmp     byte ptr [rcx+8], 0
0x1800a4039  mov     ebx, 80004005h
0x1800a403e  jz      short loc_1800A4062
0x1800a4040  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a4045  cmp     [rax+7CCh], ebx
0x1800a404b  jz      short loc_1800A4062
0x1800a404d  mov     r9d, ebx; int
0x1800a4050  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x1800a4057  mov     r8d, esi; int
0x1800a405a  mov     rcx, rax; this
0x1800a405d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a4062  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a4069  jb      loc_1800A3EEF
0x1800a406f  mov     edx, 1A9h
0x1800a4074  jmp     loc_1800A3ED1
0x1800a4079  movsxd  rcx, r12d
0x1800a407c  mov     eax, 8
0x1800a4081  mul     rcx
0x1800a4084  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a408b  cmovb   rax, rbx
0x1800a408f  mov     rcx, rax; unsigned __int64
0x1800a4092  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800a4097  mov     r8d, 13BFh; int
0x1800a409d  mov     [rdi], rax
0x1800a40a0  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x1800a40a7  lea     rcx, [rbp+arg_8]; this
0x1800a40ab  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a40b0  mov     rax, [rdi]
0x1800a40b3  test    rax, rax
0x1800a40b6  jnz     loc_1800A4156
0x1800a40bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a40c3  test    rcx, rcx
0x1800a40c6  jnz     short loc_1800A410F
0x1800a40c8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a40cf  nop     dword ptr [rax+rax+00h]
0x1800a40d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a40db  mov     rcx, rax
0x1800a40de  test    rax, rax
0x1800a40e1  jz      short loc_1800A4101
0x1800a40e3  mov     rax, [rax]
0x1800a40e6  mov     edx, 7F0h
0x1800a40eb  mov     rax, [rax+8]
0x1800a40ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a40f4  test    eax, eax
0x1800a40f6  jz      short loc_1800A4101
0x1800a40f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a40ff  jmp     short loc_1800A410F
0x1800a4101  lea     rcx, qword_1800DBF70; this
0x1800a4108  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a410f  cmp     byte ptr [rcx+8], 0
0x1800a4113  mov     ebx, 8007000Eh
0x1800a4118  jz      short loc_1800A413F
0x1800a411a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a411f  cmp     [rax+7CCh], ebx
0x1800a4125  jz      short loc_1800A413F
0x1800a4127  mov     r9d, ebx; int
0x1800a412a  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x1800a4131  mov     r8d, 13BFh; int
0x1800a4137  mov     rcx, rax; this
0x1800a413a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a413f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a4146  jb      loc_1800A3EEF
0x1800a414c  mov     edx, 1AAh
0x1800a4151  jmp     loc_1800A3ED1
0x1800a4156  lea     rcx, [rbp+arg_8]; this
0x1800a415a  mov     [rdi+8], rax
0x1800a415e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a4163  test    r15d, r15d
0x1800a4166  jle     loc_1800A4259
0x1800a416c  movsxd  rcx, r15d
0x1800a416f  mov     eax, 8
0x1800a4174  mul     rcx
0x1800a4177  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a417e  cmovb   rax, rbx
0x1800a4182  mov     rcx, rax; unsigned __int64
0x1800a4185  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800a418a  mov     [rdi+10h], rax
0x1800a418e  test    rax, rax
0x1800a4191  jnz     loc_1800A4255
0x1800a4197  mov     rcx, [rdi]; Block
0x1800a419a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a419f  mov     esi, 13C8h
0x1800a41a4  mov     qword ptr [rdi], 0
0x1800a41ab  mov     r8d, esi; int
0x1800a41ae  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x1800a41b5  lea     rcx, [rbp+arg_8]; this
0x1800a41b9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a41be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a41c5  test    rcx, rcx
0x1800a41c8  jnz     short loc_1800A4211
0x1800a41ca  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a41d1  nop     dword ptr [rax+rax+00h]
0x1800a41d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a41dd  mov     rcx, rax
0x1800a41e0  test    rax, rax
0x1800a41e3  jz      short loc_1800A4203
0x1800a41e5  mov     rax, [rax]
0x1800a41e8  mov     edx, 7F0h
0x1800a41ed  mov     rax, [rax+8]
0x1800a41f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a41f6  test    eax, eax
0x1800a41f8  jz      short loc_1800A4203
0x1800a41fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4201  jmp     short loc_1800A4211
0x1800a4203  lea     rcx, qword_1800DBF70; this
0x1800a420a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4211  cmp     byte ptr [rcx+8], 0
0x1800a4215  mov     ebx, 8007000Eh
0x1800a421a  jz      short loc_1800A423E
0x1800a421c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a4221  cmp     [rax+7CCh], ebx
0x1800a4227  jz      short loc_1800A423E
0x1800a4229  mov     r9d, ebx; int
0x1800a422c  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x1800a4233  mov     r8d, esi; int
0x1800a4236  mov     rcx, rax; this
0x1800a4239  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a423e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a4245  jb      loc_1800A3EEF
0x1800a424b  mov     edx, 1ABh
0x1800a4250  jmp     loc_1800A3ED1
0x1800a4255  mov     [rdi+18h], rax
0x1800a4259  mov     [rbp+arg_10], rsi
0x1800a425d  cmp     rsi, r14
0x1800a4260  jge     loc_1800A4A06
0x1800a4266  mov     r8d, 13CFh; int
0x1800a426c  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x1800a4273  lea     rcx, [rbp+arg_8]; this
0x1800a4277  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a427c  lea     rax, [rbp+var_18]
0x1800a4280  mov     r8, r14; __int64 *
0x1800a4283  lea     r9, [rbp+var_20]; __int64
0x1800a4287  mov     [rsp+50h+var_30], rax; __int64 *
0x1800a428c  lea     rdx, [rbp+arg_10]; struct mkvparser::IMkvReader *
0x1800a4290  mov     rcx, r13; this
  ... truncated ...
```
