# mkvparser::ContentEncoding::ParseContentEncodingEntry(__int64,__int64,mkvparser::IMkvReader *)

- ea: `0x18009f58c`
- end: `0x1800a028f`
- name: `?ParseContentEncodingEntry@ContentEncoding@mkvparser@@QEAAJ_J0PEAUIMkvReader@2@@Z`
- size: `3331`
- prototype: `__int64 __fastcall(mkvparser::ContentEncoding *__hidden this, __int64, __int64, struct mkvparser::IMkvReader *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800a0298`

## callees

- `0x180001fd0`
- `0x180002410`
- `0x180003720`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x18008415c`
- `0x1800841b8`
- `0x18009ecd4`
- `0x18009f58c`
- `0x1800a1710`
- `0x1800a1b98`
- `0x1800aaa7c`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f669`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f73b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f7fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f8ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f9ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009fb28`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009fccc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009fdb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009fe3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009fed6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ff65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a0001`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a00af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a0143`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a01f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f669`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f73b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f7fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f8ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f9ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009fb28`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009fccc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009fdb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009fe3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009fed6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ff65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a0001`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a00af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a0143`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a01f0`

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
          v15 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v23 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v36 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v29 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v44 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v107 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                v79 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                v83 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                v59 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                v86 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                  v95 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                  v92 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                  v104 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                  v101 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v113 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18009f58c  mov     [rsp-38h+arg_0], rbx
0x18009f591  mov     [rsp-38h+arg_18], r9
0x18009f596  push    rbp
0x18009f597  push    rsi
0x18009f598  push    rdi
0x18009f599  push    r12
0x18009f59b  push    r13
0x18009f59d  push    r14
0x18009f59f  push    r15
0x18009f5a1  mov     rbp, rsp
0x18009f5a4  sub     rsp, 50h
0x18009f5a8  lea     r14, [rdx+r8]
0x18009f5ac  mov     [rbp+arg_10], rdx
0x18009f5b0  xor     r12d, r12d
0x18009f5b3  mov     [rbp+var_10], r14
0x18009f5b7  xor     r15d, r15d
0x18009f5ba  mov     [rbp+var_20], 0
0x18009f5c2  mov     r13, r9
0x18009f5c5  mov     [rbp+var_18], 0
0x18009f5cd  mov     rsi, rdx
0x18009f5d0  mov     rdi, rcx
0x18009f5d3  mov     rbx, rdx
0x18009f5d6  cmp     rbx, r14
0x18009f5d9  jge     loc_18009F711
0x18009f5df  mov     r8d, 13A8h; int
0x18009f5e5  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x18009f5ec  lea     rcx, [rbp+arg_8]; this
0x18009f5f0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009f5f5  lea     rax, [rbp+var_18]
0x18009f5f9  mov     r8, r14; __int64 *
0x18009f5fc  lea     r9, [rbp+var_20]; __int64
0x18009f600  mov     [rsp+50h+var_30], rax; __int64 *
0x18009f605  lea     rdx, [rbp+arg_10]; struct mkvparser::IMkvReader *
0x18009f609  mov     rcx, r13; this
0x18009f60c  call    ?ParseElementHeader@mkvparser@@YAJPEAUIMkvReader@1@AEA_J_J11@Z; mkvparser::ParseElementHeader(mkvparser::IMkvReader *,__int64 &,__int64,__int64 &,__int64 &)
0x18009f611  mov     ebx, eax
0x18009f613  test    eax, eax
0x18009f615  js      short loc_18009F65D
0x18009f617  cmp     [rbp+var_20], 5034h
0x18009f61f  jnz     short loc_18009F62D
0x18009f621  cmp     r12d, 7FFFFFFFh
0x18009f628  jge     short loc_18009F643
0x18009f62a  inc     r12d
0x18009f62d  cmp     [rbp+var_20], 5035h
0x18009f635  jnz     short loc_18009F643
0x18009f637  cmp     r15d, 7FFFFFFFh
0x18009f63e  jge     short loc_18009F643
0x18009f640  inc     r15d
0x18009f643  mov     rbx, [rbp+arg_10]
0x18009f647  lea     rcx, [rbp+arg_8]; this
0x18009f64b  add     rbx, [rbp+var_18]
0x18009f64f  mov     [rbp+arg_10], rbx
0x18009f653  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009f658  jmp     loc_18009F5D6
0x18009f65d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f664  test    rcx, rcx
0x18009f667  jnz     short loc_18009F6AA
0x18009f669  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009f66f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f676  mov     rcx, rax
0x18009f679  test    rax, rax
0x18009f67c  jz      short loc_18009F69C
0x18009f67e  mov     rax, [rax]
0x18009f681  mov     edx, 7F0h
0x18009f686  mov     rax, [rax+8]
0x18009f68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f68f  test    eax, eax
0x18009f691  jz      short loc_18009F69C
0x18009f693  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f69a  jmp     short loc_18009F6AA
0x18009f69c  lea     rcx, qword_1800D6F70; this
0x18009f6a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f6aa  cmp     byte ptr [rcx+8], 0
0x18009f6ae  jz      short loc_18009F6D5
0x18009f6b0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009f6b5  cmp     [rax+7CCh], ebx
0x18009f6bb  jz      short loc_18009F6D5
0x18009f6bd  mov     r9d, ebx; int
0x18009f6c0  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x18009f6c7  mov     r8d, 13A8h; int
0x18009f6cd  mov     rcx, rax; this
0x18009f6d0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009f6d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009f6dc  jb      short loc_18009F701
0x18009f6de  mov     edx, 1A7h
0x18009f6e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f6ea  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x18009f6f1  mov     r9, rdi
0x18009f6f4  mov     dword ptr [rsp+50h+var_30], ebx
0x18009f6f8  mov     rcx, [rcx+10h]
0x18009f6fc  call    WPP_SF_qD
0x18009f701  lea     rcx, [rbp+arg_8]; this
0x18009f705  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009f70a  mov     eax, ebx
0x18009f70c  jmp     loc_1800A0277
0x18009f711  jz      loc_18009F7C0
0x18009f717  mov     esi, 13B5h
0x18009f71c  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x18009f723  mov     r8d, esi; int
0x18009f726  lea     rcx, [rbp+arg_8]; this
0x18009f72a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009f72f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f736  test    rcx, rcx
0x18009f739  jnz     short loc_18009F77C
0x18009f73b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009f741  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f748  mov     rcx, rax
0x18009f74b  test    rax, rax
0x18009f74e  jz      short loc_18009F76E
0x18009f750  mov     rax, [rax]
0x18009f753  mov     edx, 7F0h
0x18009f758  mov     rax, [rax+8]
0x18009f75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f761  test    eax, eax
0x18009f763  jz      short loc_18009F76E
0x18009f765  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f76c  jmp     short loc_18009F77C
0x18009f76e  lea     rcx, qword_1800D6F70; this
0x18009f775  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f77c  cmp     byte ptr [rcx+8], 0
0x18009f780  mov     ebx, 0C00D36BEh
0x18009f785  jz      short loc_18009F7A9
0x18009f787  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009f78c  cmp     [rax+7CCh], ebx
0x18009f792  jz      short loc_18009F7A9
0x18009f794  mov     r9d, ebx; int
0x18009f797  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x18009f79e  mov     r8d, esi; int
0x18009f7a1  mov     rcx, rax; this
0x18009f7a4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009f7a9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009f7b0  jb      loc_18009F701
0x18009f7b6  mov     edx, 1A8h
0x18009f7bb  jmp     loc_18009F6E3
0x18009f7c0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18009f7c4  test    r12d, r12d
0x18009f7c7  jg      loc_18009F87F
0x18009f7cd  test    r15d, r15d
0x18009f7d0  jg      loc_18009F96C
0x18009f7d6  mov     esi, 13BAh
0x18009f7db  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x18009f7e2  mov     r8d, esi; int
0x18009f7e5  lea     rcx, [rbp+arg_8]; this
0x18009f7e9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009f7ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f7f5  test    rcx, rcx
0x18009f7f8  jnz     short loc_18009F83B
0x18009f7fa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009f800  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f807  mov     rcx, rax
0x18009f80a  test    rax, rax
0x18009f80d  jz      short loc_18009F82D
0x18009f80f  mov     rax, [rax]
0x18009f812  mov     edx, 7F0h
0x18009f817  mov     rax, [rax+8]
0x18009f81b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f820  test    eax, eax
0x18009f822  jz      short loc_18009F82D
0x18009f824  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f82b  jmp     short loc_18009F83B
0x18009f82d  lea     rcx, qword_1800D6F70; this
0x18009f834  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f83b  cmp     byte ptr [rcx+8], 0
0x18009f83f  mov     ebx, 80004005h
0x18009f844  jz      short loc_18009F868
0x18009f846  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009f84b  cmp     [rax+7CCh], ebx
0x18009f851  jz      short loc_18009F868
0x18009f853  mov     r9d, ebx; int
0x18009f856  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x18009f85d  mov     r8d, esi; int
0x18009f860  mov     rcx, rax; this
0x18009f863  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009f868  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009f86f  jb      loc_18009F701
0x18009f875  mov     edx, 1A9h
0x18009f87a  jmp     loc_18009F6E3
0x18009f87f  movsxd  rcx, r12d
0x18009f882  mov     eax, 8
0x18009f887  mul     rcx
0x18009f88a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009f891  cmovb   rax, rbx
0x18009f895  mov     rcx, rax; unsigned __int64
0x18009f898  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18009f89d  mov     r8d, 13BFh; int
0x18009f8a3  mov     [rdi], rax
0x18009f8a6  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x18009f8ad  lea     rcx, [rbp+arg_8]; this
0x18009f8b1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009f8b6  mov     rax, [rdi]
0x18009f8b9  test    rax, rax
0x18009f8bc  jnz     loc_18009F956
0x18009f8c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f8c9  test    rcx, rcx
0x18009f8cc  jnz     short loc_18009F90F
0x18009f8ce  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009f8d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f8db  mov     rcx, rax
0x18009f8de  test    rax, rax
0x18009f8e1  jz      short loc_18009F901
0x18009f8e3  mov     rax, [rax]
0x18009f8e6  mov     edx, 7F0h
0x18009f8eb  mov     rax, [rax+8]
0x18009f8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f8f4  test    eax, eax
0x18009f8f6  jz      short loc_18009F901
0x18009f8f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f8ff  jmp     short loc_18009F90F
0x18009f901  lea     rcx, qword_1800D6F70; this
0x18009f908  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f90f  cmp     byte ptr [rcx+8], 0
0x18009f913  mov     ebx, 8007000Eh
0x18009f918  jz      short loc_18009F93F
0x18009f91a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009f91f  cmp     [rax+7CCh], ebx
0x18009f925  jz      short loc_18009F93F
0x18009f927  mov     r9d, ebx; int
0x18009f92a  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x18009f931  mov     r8d, 13BFh; int
0x18009f937  mov     rcx, rax; this
0x18009f93a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009f93f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009f946  jb      loc_18009F701
0x18009f94c  mov     edx, 1AAh
0x18009f951  jmp     loc_18009F6E3
0x18009f956  lea     rcx, [rbp+arg_8]; this
0x18009f95a  mov     [rdi+8], rax
0x18009f95e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009f963  test    r15d, r15d
0x18009f966  jle     loc_18009FA53
0x18009f96c  movsxd  rcx, r15d
0x18009f96f  mov     eax, 8
0x18009f974  mul     rcx
0x18009f977  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009f97e  cmovb   rax, rbx
0x18009f982  mov     rcx, rax; unsigned __int64
0x18009f985  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18009f98a  mov     [rdi+10h], rax
0x18009f98e  test    rax, rax
0x18009f991  jnz     loc_18009FA4F
0x18009f997  mov     rcx, [rdi]; Block
0x18009f99a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009f99f  mov     esi, 13C8h
0x18009f9a4  mov     qword ptr [rdi], 0
0x18009f9ab  mov     r8d, esi; int
0x18009f9ae  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x18009f9b5  lea     rcx, [rbp+arg_8]; this
0x18009f9b9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009f9be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f9c5  test    rcx, rcx
0x18009f9c8  jnz     short loc_18009FA0B
0x18009f9ca  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009f9d0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f9d7  mov     rcx, rax
0x18009f9da  test    rax, rax
0x18009f9dd  jz      short loc_18009F9FD
0x18009f9df  mov     rax, [rax]
0x18009f9e2  mov     edx, 7F0h
0x18009f9e7  mov     rax, [rax+8]
0x18009f9eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f9f0  test    eax, eax
0x18009f9f2  jz      short loc_18009F9FD
0x18009f9f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f9fb  jmp     short loc_18009FA0B
0x18009f9fd  lea     rcx, qword_1800D6F70; this
0x18009fa04  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009fa0b  cmp     byte ptr [rcx+8], 0
0x18009fa0f  mov     ebx, 8007000Eh
0x18009fa14  jz      short loc_18009FA38
0x18009fa16  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009fa1b  cmp     [rax+7CCh], ebx
0x18009fa21  jz      short loc_18009FA38
0x18009fa23  mov     r9d, ebx; int
0x18009fa26  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x18009fa2d  mov     r8d, esi; int
0x18009fa30  mov     rcx, rax; this
0x18009fa33  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009fa38  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009fa3f  jb      loc_18009F701
0x18009fa45  mov     edx, 1ABh
0x18009fa4a  jmp     loc_18009F6E3
0x18009fa4f  mov     [rdi+18h], rax
0x18009fa53  mov     [rbp+arg_10], rsi
0x18009fa57  cmp     rsi, r14
0x18009fa5a  jge     loc_1800A01C6
0x18009fa60  mov     r8d, 13CFh; int
0x18009fa66  lea     rdx, aMkvparserConte_2; "mkvparser::ContentEncoding::ParseConten"...
0x18009fa6d  lea     rcx, [rbp+arg_8]; this
0x18009fa71  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009fa76  lea     rax, [rbp+var_18]
0x18009fa7a  mov     r8, r14; __int64 *
0x18009fa7d  lea     r9, [rbp+var_20]; __int64
0x18009fa81  mov     [rsp+50h+var_30], rax; __int64 *
0x18009fa86  lea     rdx, [rbp+arg_10]; struct mkvparser::IMkvReader *
0x18009fa8a  mov     rcx, r13; this
0x18009fa8d  call    ?ParseElementHeader@mkvparser@@YAJPEAUIMkvReader@1@AEA_J_J11@Z; mkvparser::ParseElementHeader(mkvparser::IMkvReader *,__int64 &,__int64,__int64 &,__int64 &)
0x18009fa92  mov     ebx, eax
0x18009fa94  test    eax, eax
0x18009fa96  js      loc_1800A0137
0x18009fa9c  mov     rax, [rbp+var_20]
  ... truncated ...
```
