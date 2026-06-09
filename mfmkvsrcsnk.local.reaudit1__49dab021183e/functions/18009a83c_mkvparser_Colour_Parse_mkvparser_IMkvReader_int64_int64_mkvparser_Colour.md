# mkvparser::Colour::Parse(mkvparser::IMkvReader *,__int64,__int64,mkvparser::Colour * *)

- ea: `0x18009a83c`
- end: `0x18009b892`
- name: `?Parse@Colour@mkvparser@@SAJPEAUIMkvReader@2@_J1PEAPEAU12@@Z`
- size: `4182`
- prototype: `__int64 __fastcall(struct mkvparser::IMkvReader *this, __int64, __int64, struct mkvparser::Colour **)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1800a0d58`

## callees

- `0x180002430`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x180087c34`
- `0x180095ed0`
- `0x18009a83c`
- `0x18009d46c`
- `0x1800a5fec`
- `0x1800af7b0`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009a88f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009a92c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009a9e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ab48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009abc8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ac48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009acc8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ad48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009adc8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ae48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009aec8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009af48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009afc8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009b048`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009b0c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009b148`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009b5e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009b680`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009b728`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009b7d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009a88f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009a92c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009a9e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ab48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009abc8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ac48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009acc8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ad48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009adc8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ae48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009aec8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009af48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009afc8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009b048`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009b0c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009b148`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009b5e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009b680`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009b728`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009b7d6`

## pseudocode

```c
__int64 __fastcall mkvparser::Colour::Parse(
        struct mkvparser::IMkvReader *this,
        struct mkvparser::IMkvReader *a2,
        __int64 a3,
        struct mkvparser::Colour **a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  int v13; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  void *v26; // rdi
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 *v29; // r12
  struct mkvparser::IMkvReader *v30; // rsi
  __int64 *v31; // r14
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // r9
  __int64 *v60; // rcx
  CallStackTracing *v61; // rax
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // r9
  __int64 *v65; // rcx
  CallStackTracing *v66; // rax
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 *v70; // rcx
  CallStackTracing *v71; // rax
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // r9
  __int64 *v75; // rcx
  CallStackTracing *v76; // rax
  __int64 v77; // rdx
  __int64 v78; // r8
  __int64 v79; // r9
  __int64 *v80; // rcx
  CallStackTracing *v81; // rax
  __int64 v82; // rdx
  __int64 v83; // r8
  __int64 v84; // r9
  __int64 *v85; // rcx
  CallStackTracing *v86; // rax
  __int64 v87; // rdx
  __int64 v88; // r8
  __int64 v89; // r9
  __int64 *v90; // rcx
  CallStackTracing *v91; // rax
  __int64 v92; // rdx
  __int64 v93; // r8
  __int64 v94; // r9
  __int64 *v95; // rcx
  CallStackTracing *v96; // rax
  struct CallStackContext *v97; // rax
  struct CallStackContext *v98; // rax
  struct CallStackContext *v99; // rax
  struct CallStackContext *v100; // rax
  struct CallStackContext *v101; // rax
  struct CallStackContext *v102; // rax
  struct CallStackContext *v103; // rax
  struct CallStackContext *v104; // rax
  struct CallStackContext *v105; // rax
  struct CallStackContext *v106; // rax
  struct CallStackContext *v107; // rax
  struct CallStackContext *v108; // rax
  struct CallStackContext *v109; // rax
  __int64 v110; // rdx
  __int64 v111; // r8
  __int64 v112; // r9
  __int64 *v113; // rcx
  CallStackTracing *v114; // rax
  struct CallStackContext *v115; // rax
  __int64 v116; // rdx
  __int64 v117; // r8
  __int64 v118; // r9
  __int64 *v119; // rcx
  CallStackTracing *v120; // rax
  struct CallStackContext *v121; // rax
  __int64 v122; // rdx
  __int64 v123; // r8
  __int64 v124; // r9
  __int64 *v125; // rcx
  CallStackTracing *v126; // rax
  struct CallStackContext *v127; // rax
  __int64 *v129; // rcx
  CallStackTracing *v130; // rax
  struct CallStackContext *v131; // rax
  __int64 *v132; // [rsp+20h] [rbp-28h]
  __int64 *v133; // [rsp+28h] [rbp-20h]
  __int64 *v134; // [rsp+30h] [rbp-18h] BYREF
  __int64 v135; // [rsp+38h] [rbp-10h] BYREF
  struct mkvparser::IMkvReader *v136; // [rsp+90h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v136, "mkvparser::Colour::Parse", 5969);
  if ( !this )
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    v13 = -2147024809;
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "mkvparser::Colour::Parse", 5969, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_240;
    v15 = 507;
    goto LABEL_239;
  }
  if ( *a4 )
  {
    v16 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    v13 = -2147024809;
    if ( *((_BYTE *)v16 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)v18 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v18, "mkvparser::Colour::Parse", 5972, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_240;
    v15 = 508;
    goto LABEL_239;
  }
  v136 = a2;
  v134 = 0;
  v13 = LongLongAdd((__int64)a2, a3, (__int64 *)&v134);
  if ( v13 < 0 )
  {
    v22 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
      CallStackTracing::s_wpInstance = v23;
      if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v22 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v22 + 8) )
    {
      v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
      if ( *((_DWORD *)v24 + 499) != v13 )
        CallStackContext::TraceFailure(v24, "mkvparser::Colour::Parse", 5978, v13);
    }
    if ( !g_wppLevels )
      goto LABEL_240;
    v15 = 509;
    goto LABEL_239;
  }
  v26 = operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v26 )
  {
    v129 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v130 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v27, v28);
      CallStackTracing::s_wpInstance = v130;
      if ( v130 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v130 + 8LL))(v130, 2032) )
      {
        v129 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v129 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    v13 = -2147024882;
    if ( *((_BYTE *)v129 + 8) )
    {
      v131 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v129);
      if ( *((_DWORD *)v131 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v131, "mkvparser::Colour::Parse", 5981, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_240;
    v15 = 510;
LABEL_239:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, 0, v13);
    goto LABEL_240;
  }
  v29 = v134;
  *(_QWORD *)v26 = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)v26 + 1) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)v26 + 2) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)v26 + 3) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)v26 + 4) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)v26 + 5) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)v26 + 6) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)v26 + 7) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)v26 + 8) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)v26 + 9) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)v26 + 10) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)v26 + 11) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)v26 + 12) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)v26 + 13) = 0;
  while ( (__int64)a2 < (__int64)v29 )
  {
    v135 = 0;
    v134 = 0;
    v13 = mkvparser::ParseElementHeader(
            this,
            (struct mkvparser::IMkvReader *)&v136,
            v29,
            (__int64)&v135,
            (__int64 *)&v134,
            v133);
    if ( v13 < 0 )
    {
      mkvparser::Colour::`scalar deleting destructor'((mkvparser::Colour *)v26, v25);
      v119 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v120 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v116, v117, v118);
        CallStackTracing::s_wpInstance = v120;
        if ( v120 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v120 + 8LL))(v120, 2032) )
        {
          v119 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v119 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v119 + 8) )
      {
        v121 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v119);
        if ( *((_DWORD *)v121 + 499) != v13 )
          CallStackContext::TraceFailure(v121, "mkvparser::Colour::Parse", 5991, v13);
      }
      if ( g_wppLevels )
      {
        v15 = 511;
        goto LABEL_239;
      }
      goto LABEL_240;
    }
    v30 = v136;
    v31 = v134;
    switch ( v135 )
    {
      case 21937LL:
        v13 = mkvparser::UnserializeUInt(this, v136, (__int64)v134, (__int64)v26, v132);
        if ( v13 < 0 )
        {
          mkvparser::Colour::`scalar deleting destructor'((mkvparser::Colour *)v26, v25);
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
            CallStackTracing::s_wpInstance = v36;
            if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
            {
              v35 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v35 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v35 + 8) )
          {
            v97 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
            if ( *((_DWORD *)v97 + 499) != v13 )
              CallStackContext::TraceFailure(v97, "mkvparser::Colour::Parse", 5999, v13);
          }
          if ( g_wppLevels )
          {
            v15 = 512;
            goto LABEL_239;
          }
          goto LABEL_240;
        }
        break;
      case 21938LL:
        v13 = mkvparser::UnserializeUInt(this, v136, (__int64)v134, (__int64)v26 + 8, v132);
        if ( v13 < 0 )
        {
          mkvparser::Colour::`scalar deleting destructor'((mkvparser::Colour *)v26, v25);
          v40 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38, v39);
            CallStackTracing::s_wpInstance = v41;
            if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
            {
              v40 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v40 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v40 + 8) )
          {
            v98 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
            if ( *((_DWORD *)v98 + 499) != v13 )
              CallStackContext::TraceFailure(v98, "mkvparser::Colour::Parse", 6006, v13);
          }
          if ( g_wppLevels )
          {
            v15 = 513;
            goto LABEL_239;
          }
          goto LABEL_240;
        }
        break;
      case 21939LL:
        v13 = mkvparser::UnserializeUInt(this, v136, (__int64)v134, (__int64)v26 + 16, v132);
        if ( v13 < 0 )
        {
          mkvparser::Colour::`scalar deleting destructor'((mkvparser::Colour *)v26, v25);
          v45 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42, v43, v44);
            CallStackTracing::s_wpInstance = v46;
            if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
            {
              v45 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v45 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v45 + 8) )
          {
            v99 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
            if ( *((_DWORD *)v99 + 499) != v13 )
              CallStackContext::TraceFailure(v99, "mkvparser::Colour::Parse", 6013, v13);
          }
          if ( g_wppLevels )
          {
            v15 = 514;
            goto LABEL_239;
          }
          goto LABEL_240;
        }
        break;
      case 21940LL:
        v13 = mkvparser::UnserializeUInt(this, v136, (__int64)v134, (__int64)v26 + 24, v132);
        if ( v13 < 0 )
        {
          mkvparser::Colour::`scalar deleting destructor'((mkvparser::Colour *)v26, v25);
          v50 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47, v48, v49);
            CallStackTracing::s_wpInstance = v51;
            if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
            {
              v50 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v50 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v50 + 8) )
          {
            v100 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
            if ( *((_DWORD *)v100 + 499) != v13 )
              CallStackContext::TraceFailure(v100, "mkvparser::Colour::Parse", 6020, v13);
          }
          if ( g_wppLevels )
          {
            v15 = 515;
            goto LABEL_239;
          }
          goto LABEL_240;
        }
        break;
      case 21941LL:
        v13 = mkvparser::UnserializeUInt(this, v136, (__int64)v134, (__int64)v26 + 32, v132);
        if ( v13 < 0 )
        {
          mkvparser::Colour::`scalar deleting destructor'((mkvparser::Colour *)v26, v25);
          v55 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53, v54);
            CallStackTracing::s_wpInstance = v56;
            if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
            {
              v55 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v55 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v55 + 8) )
          {
            v101 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
            if ( *((_DWORD *)v101 + 499) != v13 )
              CallStackContext::TraceFailure(v101, "mkvparser::Colour::Parse", 6027, v13);
          }
          if ( g_wppLevels )
          {
            v15 = 516;
            goto LABEL_239;
          }
          goto LABEL_240;
        }
        break;
      case 21942LL:
        v13 = mkvparser::UnserializeUInt(this, v136, (__int64)v134, (__int64)v26 + 40, v132);
        if ( v13 < 0 )
        {
          mkvparser::Colour::`scalar deleting destructor'((mkvparser::Colour *)v26, v25);
          v60 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v57, v58, v59);
            CallStackTracing::s_wpInstance = v61;
            if ( v61 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
            {
              v60 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v60 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v60 + 8) )
          {
            v102 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
            if ( *((_DWORD *)v102 + 499) != v13 )
              CallStackContext::TraceFailure(v102, "mkvparser::Colour::Parse", 6034, v13);
          }
          if ( g_wppLevels )
          {
            v15 = 517;
            goto LABEL_239;
          }
          goto LABEL_240;
        }
        break;
      case 21943LL:
        v13 = mkvparser::UnserializeUInt(this, v136, (__int64)v134, (__int64)v26 + 48, v132);
        if ( v13 < 0 )
        {
          mkvparser::Colour::`scalar deleting destructor'((mkvparser::Colour *)v26, v25);
          v65 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62, v63, v64);
            CallStackTracing::s_wpInstance = v66;
            if ( v66 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v66 + 8LL))(v66, 2032) )
            {
              v65 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v65 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v65 + 8) )
          {
            v103 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v65);
            if ( *((_DWORD *)v103 + 499) != v13 )
              CallStackContext::TraceFailure(v103, "mkvparser::Colour::Parse", 6041, v13);
          }
          if ( g_wppLevels )
          {
            v15 = 518;
            goto LABEL_239;
          }
          goto LABEL_240;
        }
        break;
      case 21944LL:
        v13 = mkvparser::UnserializeUInt(this, v136, (__int64)v134, (__int64)v26 + 56, v132);
        if ( v13 < 0 )
        {
          mkvparser::Colour::`scalar deleting destructor'((mkvparser::Colour *)v26, v25);
          v70 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v67, v68, v69);
            CallStackTracing::s_wpInstance = v71;
            if ( v71 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
            {
              v70 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v70 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v70 + 8) )
          {
            v104 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v70);
            if ( *((_DWORD *)v104 + 499) != v13 )
              CallStackContext::TraceFailure(v104, "mkvparser::Colour::Parse", 6048, v13);
          }
          if ( g_wppLevels )
          {
            v15 = 519;
            goto LABEL_239;
          }
          goto LABEL_240;
        }
        break;
      case 21945LL:
        v13 = mkvparser::UnserializeUInt(this, v136, (__int64)v134, (__int64)v26 + 64, v132);
        if ( v13 < 0 )
        {
          mkvparser::Colour::`scalar deleting destructor'((mkvparser::Colour *)v26, v25);
          v75 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v72, v73, v74);
            CallStackTracing::s_wpInstance = v76;
            if ( v76 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(v76, 2032) )
            {
              v75 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v75 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v75 + 8) )
          {
            v105 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v75);
            if ( *((_DWORD *)v105 + 499) != v13 )
              CallStackContext::TraceFailure(v105, "mkvparser::Colour::Parse", 6055, v13);
          }
          if ( g_wppLevels )
          {
            v15 = 520;
            goto LABEL_239;
          }
          goto LABEL_240;
        }
        break;
      case 21946LL:
        v13 = mkvparser::UnserializeUInt(this, v136, (__int64)v134, (__int64)v26 + 72, v132);
        if ( v13 < 0 )
        {
          mkvparser::Colour::`scalar deleting destructor'((mkvparser::Colour *)v26, v25);
          v80 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v81 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v77, v78, v79);
            CallStackTracing::s_wpInstance = v81;
            if ( v81 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v81 + 8LL))(v81, 2032) )
            {
              v80 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v80 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v80 + 8) )
          {
            v106 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v80);
            if ( *((_DWORD *)v106 + 499) != v13 )
              CallStackContext::TraceFailure(v106, "mkvparser::Colour::Parse", 6062, v13);
          }
          if ( g_wppLevels )
          {
            v15 = 521;
            goto LABEL_239;
          }
          goto LABEL_240;
        }
        break;
      case 21947LL:
        v13 = mkvparser::UnserializeUInt(this, v136, (__int64)v134, (__int64)v26 + 80, v132);
        if ( v13 < 0 )
        {
          mkvparser::Colour::`scalar deleting destructor'((mkvparser::Colour *)v26, v25);
          v85 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v86 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v82, v83, v84);
            CallStackTracing::s_wpInstance = v86;
            if ( v86 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v86 + 8LL))(v86, 2032) )
            {
              v85 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v85 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v85 + 8) )
          {
            v107 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v85);
            if ( *((_DWORD *)v107 + 499) != v13 )
              CallStackContext::TraceFailure(v107, "mkvparser::Colour::Parse", 6069, v13);
          }
          if ( g_wppLevels )
          {
            v15 = 522;
            goto LABEL_239;
          }
          goto LABEL_240;
        }
        break;
      case 21948LL:
        v13 = mkvparser::UnserializeUInt(this, v136, (__int64)v134, (__int64)v26 + 88, v132);
        if ( v13 < 0 )
        {
          mkvparser::Colour::`scalar deleting destructor'((mkvparser::Colour *)v26, v25);
          v90 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v91 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v87, v88, v89);
            CallStackTracing::s_wpInstance = v91;
            if ( v91 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v91 + 8LL))(v91, 2032) )
            {
              v90 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v90 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v90 + 8) )
          {
            v108 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v90);
            if ( *((_DWORD *)v108 + 499) != v13 )
              CallStackContext::TraceFailure(v108, "mkvparser::Colour::Parse", 6076, v13);
          }
          if ( g_wppLevels )
          {
            v15 = 523;
            goto LABEL_239;
          }
          goto LABEL_240;
        }
        break;
      case 21949LL:
        v13 = mkvparser::UnserializeUInt(this, v136, (__int64)v134, (__int64)v26 + 96, v132);
        if ( v13 < 0 )
        {
          mkvparser::Colour::`scalar deleting destructor'((mkvparser::Colour *)v26, v25);
          v95 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v96 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v92, v93, v94);
            CallStackTracing::s_wpInstance = v96;
            if ( v96 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v96 + 8LL))(v96, 2032) )
            {
              v95 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v95 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v95 + 8) )
          {
            v109 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v95);
            if ( *((_DWORD *)v109 + 499) != v13 )
              CallStackContext::TraceFailure(v109, "mkvparser::Colour::Parse", 6083, v13);
          }
          if ( g_wppLevels )
          {
            v15 = 524;
            goto LABEL_239;
          }
          goto LABEL_240;
        }
        break;
      case 21968LL:
        v13 = mkvparser::MasteringMetadata::Parse(
                this,
                (__int64)v136,
                (__int64)v134,
                (struct mkvparser::MasteringMetadata **)v26 + 13);
        if ( v13 < 0 )
        {
          mkvparser::Colour::`scalar deleting destructor'((mkvparser::Colour *)v26, v25);
          v113 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v114 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v110, v111, v112);
            CallStackTracing::s_wpInstance = v114;
            if ( v114
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v114 + 8LL))(v114, 2032) )
            {
              v113 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v113 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v113 + 8) )
          {
            v115 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v113);
            if ( *((_DWORD *)v115 + 499) != v13 )
              CallStackContext::TraceFailure(v115, "mkvparser::Colour::Parse", 6090, v13);
          }
          if ( g_wppLevels )
          {
            v15 = 525;
            goto LABEL_239;
          }
          goto LABEL_240;
        }
        break;
    }
    a2 = (struct mkvparser::IMkvReader *)((char *)v30 + (_QWORD)v31);
    v136 = a2;
  }
  if ( a2 == (struct mkvparser::IMkvReader *)v29 )
  {
    *a4 = (struct mkvparser::Colour *)v26;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v136);
    return 0;
  }
  mkvparser::Colour::`scalar deleting destructor'((mkvparser::Colour *)v26, v25);
  v125 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v126 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v122, v123, v124);
    CallStackTracing::s_wpInstance = v126;
    if ( v126 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v126 + 8LL))(v126, 2032) )
    {
      v125 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v125 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  v13 = -1072875842;
  if ( *((_BYTE *)v125 + 8) )
  {
    v127 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v125);
    if ( *((_DWORD *)v127 + 499) != -1072875842 )
      CallStackContext::TraceFailure(v127, "mkvparser::Colour::Parse", 6100, -1072875842);
  }
  if ( g_wppLevels )
  {
    v15 = 526;
    goto LABEL_239;
  }
LABEL_240:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v136);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18009a83c  push    rbp
0x18009a83e  push    rbx
0x18009a83f  push    rsi
0x18009a840  push    rdi
0x18009a841  push    r12
0x18009a843  push    r13
0x18009a845  push    r14
0x18009a847  push    r15
0x18009a849  mov     rbp, rsp
0x18009a84c  sub     rsp, 48h
0x18009a850  mov     rbx, r8
0x18009a853  lea     r12, aMkvparserColou; "mkvparser::Colour::Parse"
0x18009a85a  mov     rsi, rdx
0x18009a85d  mov     r15, rcx
0x18009a860  mov     edi, 1751h
0x18009a865  lea     rcx, [rbp+arg_0]; this
0x18009a869  mov     r8d, edi; int
0x18009a86c  mov     rdx, r12; char *
0x18009a86f  mov     r13, r9
0x18009a872  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009a877  xor     r14d, r14d
0x18009a87a  test    r15, r15
0x18009a87d  jnz     loc_18009A916
0x18009a883  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009a88a  test    rcx, rcx
0x18009a88d  jnz     short loc_18009A8D6
0x18009a88f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009a896  nop     dword ptr [rax+rax+00h]
0x18009a89b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009a8a2  mov     rcx, rax
0x18009a8a5  test    rax, rax
0x18009a8a8  jz      short loc_18009A8C8
0x18009a8aa  mov     rax, [rax]
0x18009a8ad  mov     edx, 7F0h
0x18009a8b2  mov     rax, [rax+8]
0x18009a8b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a8bb  test    eax, eax
0x18009a8bd  jz      short loc_18009A8C8
0x18009a8bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009a8c6  jmp     short loc_18009A8D6
0x18009a8c8  lea     rcx, qword_1800DBF70; this
0x18009a8cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009a8d6  mov     ebx, 80070057h
0x18009a8db  cmp     [rcx+8], r14b
0x18009a8df  jz      short loc_18009A8FF
0x18009a8e1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009a8e6  cmp     [rax+7CCh], ebx
0x18009a8ec  jz      short loc_18009A8FF
0x18009a8ee  mov     r9d, ebx; int
0x18009a8f1  mov     r8d, edi; int
0x18009a8f4  mov     rdx, r12; char *
0x18009a8f7  mov     rcx, rax; this
0x18009a8fa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009a8ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009a906  jb      loc_18009B875
0x18009a90c  mov     edx, 1FBh
0x18009a911  jmp     loc_18009B857
0x18009a916  cmp     [r13+0], r14
0x18009a91a  jz      loc_18009A9B6
0x18009a920  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009a927  test    rcx, rcx
0x18009a92a  jnz     short loc_18009A973
0x18009a92c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009a933  nop     dword ptr [rax+rax+00h]
0x18009a938  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009a93f  mov     rcx, rax
0x18009a942  test    rax, rax
0x18009a945  jz      short loc_18009A965
0x18009a947  mov     rax, [rax]
0x18009a94a  mov     edx, 7F0h
0x18009a94f  mov     rax, [rax+8]
0x18009a953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a958  test    eax, eax
0x18009a95a  jz      short loc_18009A965
0x18009a95c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009a963  jmp     short loc_18009A973
0x18009a965  lea     rcx, qword_1800DBF70; this
0x18009a96c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009a973  mov     ebx, 80070057h
0x18009a978  cmp     [rcx+8], r14b
0x18009a97c  jz      short loc_18009A99F
0x18009a97e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009a983  cmp     [rax+7CCh], ebx
0x18009a989  jz      short loc_18009A99F
0x18009a98b  mov     r9d, ebx; int
0x18009a98e  mov     r8d, 1754h; int
0x18009a994  mov     rdx, r12; char *
0x18009a997  mov     rcx, rax; this
0x18009a99a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009a99f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009a9a6  jb      loc_18009B875
0x18009a9ac  mov     edx, 1FCh
0x18009a9b1  jmp     loc_18009B857
0x18009a9b6  lea     r8, [rbp+var_18]; __int64 *
0x18009a9ba  mov     [rbp+arg_0], rsi
0x18009a9be  mov     rdx, rbx; __int64
0x18009a9c1  mov     [rbp+var_18], r14
0x18009a9c5  mov     rcx, rsi; __int64
0x18009a9c8  call    ?LongLongAdd@@YAJ_J0PEA_J@Z; LongLongAdd(__int64,__int64,__int64 *)
0x18009a9cd  mov     ebx, eax
0x18009a9cf  test    eax, eax
0x18009a9d1  jns     loc_18009AA68
0x18009a9d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009a9de  test    rcx, rcx
0x18009a9e1  jnz     short loc_18009AA2A
0x18009a9e3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009a9ea  nop     dword ptr [rax+rax+00h]
0x18009a9ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009a9f6  mov     rcx, rax
0x18009a9f9  test    rax, rax
0x18009a9fc  jz      short loc_18009AA1C
0x18009a9fe  mov     rax, [rax]
0x18009aa01  mov     edx, 7F0h
0x18009aa06  mov     rax, [rax+8]
0x18009aa0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aa0f  test    eax, eax
0x18009aa11  jz      short loc_18009AA1C
0x18009aa13  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009aa1a  jmp     short loc_18009AA2A
0x18009aa1c  lea     rcx, qword_1800DBF70; this
0x18009aa23  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009aa2a  cmp     [rcx+8], r14b
0x18009aa2e  jz      short loc_18009AA51
0x18009aa30  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009aa35  cmp     [rax+7CCh], ebx
0x18009aa3b  jz      short loc_18009AA51
0x18009aa3d  mov     r9d, ebx; int
0x18009aa40  mov     r8d, 175Ah; int
0x18009aa46  mov     rdx, r12; char *
0x18009aa49  mov     rcx, rax; this
0x18009aa4c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009aa51  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009aa58  jb      loc_18009B875
0x18009aa5e  mov     edx, 1FDh
0x18009aa63  jmp     loc_18009B857
0x18009aa68  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009aa6f  mov     ecx, 70h ; 'p'; unsigned __int64
0x18009aa74  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18009aa79  mov     rdi, rax
0x18009aa7c  test    rax, rax
0x18009aa7f  jz      loc_18009B7CA
0x18009aa85  mov     r12, [rbp+var_18]
0x18009aa89  mov     rax, 7FFFFFFFFFFFFFFFh
0x18009aa93  mov     [rdi], rax
0x18009aa96  mov     [rdi+8], rax
0x18009aa9a  mov     [rdi+10h], rax
0x18009aa9e  mov     [rdi+18h], rax
0x18009aaa2  mov     [rdi+20h], rax
0x18009aaa6  mov     [rdi+28h], rax
0x18009aaaa  mov     [rdi+30h], rax
0x18009aaae  mov     [rdi+38h], rax
0x18009aab2  mov     [rdi+40h], rax
0x18009aab6  mov     [rdi+48h], rax
0x18009aaba  mov     [rdi+50h], rax
0x18009aabe  mov     [rdi+58h], rax
0x18009aac2  mov     [rdi+60h], rax
0x18009aac6  mov     [rdi+68h], r14
0x18009aaca  cmp     rsi, r12
0x18009aacd  jge     loc_18009B709
0x18009aad3  lea     rax, [rbp+var_18]
0x18009aad7  mov     [rbp+var_10], r14
0x18009aadb  lea     r9, [rbp+var_10]; __int64
0x18009aadf  mov     [rsp+48h+var_28], rax; __int64 *
0x18009aae4  mov     r8, r12; __int64 *
0x18009aae7  mov     [rbp+var_18], r14
0x18009aaeb  lea     rdx, [rbp+arg_0]; struct mkvparser::IMkvReader *
0x18009aaef  mov     rcx, r15; this
0x18009aaf2  call    ?ParseElementHeader@mkvparser@@YAJPEAUIMkvReader@1@AEA_J_J11@Z; mkvparser::ParseElementHeader(mkvparser::IMkvReader *,__int64 &,__int64,__int64 &,__int64 &)
0x18009aaf7  mov     ebx, eax
0x18009aaf9  test    eax, eax
0x18009aafb  js      loc_18009B66C
0x18009ab01  mov     rax, [rbp+var_10]
0x18009ab05  mov     rsi, [rbp+arg_0]
0x18009ab09  mov     r14, [rbp+var_18]
0x18009ab0d  cmp     rax, 55B1h
0x18009ab13  jnz     short loc_18009AB8C
0x18009ab15  mov     r9, rdi; __int64
0x18009ab18  mov     r8, r14; __int64
0x18009ab1b  mov     rdx, rsi; struct mkvparser::IMkvReader *
0x18009ab1e  mov     rcx, r15; this
0x18009ab21  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x18009ab26  mov     ebx, eax
0x18009ab28  test    eax, eax
0x18009ab2a  jns     loc_18009B1B0
0x18009ab30  mov     rcx, rdi; this
0x18009ab33  call    ??_GColour@mkvparser@@QEAAPEAXI@Z; mkvparser::Colour::`scalar deleting destructor'(uint)
0x18009ab38  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ab3f  test    rcx, rcx
0x18009ab42  jnz     loc_18009B1CD
0x18009ab48  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009ab4f  nop     dword ptr [rax+rax+00h]
0x18009ab54  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ab5b  mov     rcx, rax
0x18009ab5e  test    rax, rax
0x18009ab61  jz      loc_18009B1BF
0x18009ab67  mov     rax, [rax]
0x18009ab6a  mov     edx, 7F0h
0x18009ab6f  mov     rax, [rax+8]
0x18009ab73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ab78  test    eax, eax
0x18009ab7a  jz      loc_18009B1BF
0x18009ab80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ab87  jmp     loc_18009B1CD
0x18009ab8c  cmp     rax, 55B2h
0x18009ab92  jnz     short loc_18009AC0C
0x18009ab94  lea     r9, [rdi+8]; __int64
0x18009ab98  mov     r8, r14; __int64
0x18009ab9b  mov     rdx, rsi; struct mkvparser::IMkvReader *
0x18009ab9e  mov     rcx, r15; this
0x18009aba1  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x18009aba6  mov     ebx, eax
0x18009aba8  test    eax, eax
0x18009abaa  jns     loc_18009B1B0
0x18009abb0  mov     rcx, rdi; this
0x18009abb3  call    ??_GColour@mkvparser@@QEAAPEAXI@Z; mkvparser::Colour::`scalar deleting destructor'(uint)
0x18009abb8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009abbf  test    rcx, rcx
0x18009abc2  jnz     loc_18009B21D
0x18009abc8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009abcf  nop     dword ptr [rax+rax+00h]
0x18009abd4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009abdb  mov     rcx, rax
0x18009abde  test    rax, rax
0x18009abe1  jz      loc_18009B20F
0x18009abe7  mov     rax, [rax]
0x18009abea  mov     edx, 7F0h
0x18009abef  mov     rax, [rax+8]
0x18009abf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009abf8  test    eax, eax
0x18009abfa  jz      loc_18009B20F
0x18009ac00  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ac07  jmp     loc_18009B21D
0x18009ac0c  cmp     rax, 55B3h
0x18009ac12  jnz     short loc_18009AC8C
0x18009ac14  lea     r9, [rdi+10h]; __int64
0x18009ac18  mov     r8, r14; __int64
0x18009ac1b  mov     rdx, rsi; struct mkvparser::IMkvReader *
0x18009ac1e  mov     rcx, r15; this
0x18009ac21  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x18009ac26  mov     ebx, eax
0x18009ac28  test    eax, eax
0x18009ac2a  jns     loc_18009B1B0
0x18009ac30  mov     rcx, rdi; this
0x18009ac33  call    ??_GColour@mkvparser@@QEAAPEAXI@Z; mkvparser::Colour::`scalar deleting destructor'(uint)
0x18009ac38  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ac3f  test    rcx, rcx
0x18009ac42  jnz     loc_18009B26D
0x18009ac48  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009ac4f  nop     dword ptr [rax+rax+00h]
0x18009ac54  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ac5b  mov     rcx, rax
0x18009ac5e  test    rax, rax
0x18009ac61  jz      loc_18009B25F
0x18009ac67  mov     rax, [rax]
0x18009ac6a  mov     edx, 7F0h
0x18009ac6f  mov     rax, [rax+8]
0x18009ac73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ac78  test    eax, eax
0x18009ac7a  jz      loc_18009B25F
0x18009ac80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ac87  jmp     loc_18009B26D
0x18009ac8c  cmp     rax, 55B4h
0x18009ac92  jnz     short loc_18009AD0C
0x18009ac94  lea     r9, [rdi+18h]; __int64
0x18009ac98  mov     r8, r14; __int64
0x18009ac9b  mov     rdx, rsi; struct mkvparser::IMkvReader *
0x18009ac9e  mov     rcx, r15; this
0x18009aca1  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x18009aca6  mov     ebx, eax
0x18009aca8  test    eax, eax
0x18009acaa  jns     loc_18009B1B0
0x18009acb0  mov     rcx, rdi; this
0x18009acb3  call    ??_GColour@mkvparser@@QEAAPEAXI@Z; mkvparser::Colour::`scalar deleting destructor'(uint)
0x18009acb8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009acbf  test    rcx, rcx
0x18009acc2  jnz     loc_18009B2BD
0x18009acc8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009accf  nop     dword ptr [rax+rax+00h]
0x18009acd4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009acdb  mov     rcx, rax
0x18009acde  test    rax, rax
0x18009ace1  jz      loc_18009B2AF
0x18009ace7  mov     rax, [rax]
0x18009acea  mov     edx, 7F0h
0x18009acef  mov     rax, [rax+8]
0x18009acf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009acf8  test    eax, eax
0x18009acfa  jz      loc_18009B2AF
0x18009ad00  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ad07  jmp     loc_18009B2BD
0x18009ad0c  cmp     rax, 55B5h
0x18009ad12  jnz     short loc_18009AD8C
0x18009ad14  lea     r9, [rdi+20h]; __int64
0x18009ad18  mov     r8, r14; __int64
0x18009ad1b  mov     rdx, rsi; struct mkvparser::IMkvReader *
0x18009ad1e  mov     rcx, r15; this
0x18009ad21  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x18009ad26  mov     ebx, eax
0x18009ad28  test    eax, eax
0x18009ad2a  jns     loc_18009B1B0
  ... truncated ...
```
