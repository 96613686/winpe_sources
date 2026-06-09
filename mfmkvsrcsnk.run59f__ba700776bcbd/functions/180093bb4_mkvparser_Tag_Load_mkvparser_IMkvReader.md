# mkvparser::Tag::Load(mkvparser::IMkvReader *)

- ea: `0x180093bb4`
- end: `0x180094f56`
- name: `?Load@Tag@mkvparser@@QEAAJPEAUIMkvReader@2@@Z`
- size: `5026`
- prototype: `int(mkvparser::Tag *__hidden this, struct mkvparser::IMkvReader *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x180095a94`

## callees

- `0x180001ff0`
- `0x180002430`
- `0x180003760`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x180087dac`
- `0x180093bb4`
- `0x18009f9d4`
- `0x1800adea8`
- `0x1800ae378`
- `0x1800af4ec`
- `0x1800af7b0`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093c3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093cff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093efc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093f95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094032`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800940fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009414d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094280`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009436b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800944ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009456a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800945e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094664`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009492c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800949c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094a5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094af5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094b8f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094c29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094cbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094d76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094e9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093c3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093cff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093efc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093f95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094032`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800940fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009414d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094280`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009436b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800944ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009456a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800945e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094664`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009492c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800949c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094a5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094af5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094b8f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094c29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094cbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094d76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094e9e`

## pseudocode

```c
__int64 __fastcall mkvparser::Tag::Load(mkvparser::Tag *this, struct mkvparser::IMkvReader *a2)
{
  unsigned int v2; // r13d
  struct mkvparser::IMkvReader *v6; // rsi
  __int64 v7; // rdx
  int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  struct mkvparser::IMkvReader *v15; // rsi
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  struct mkvparser::IMkvReader *v22; // r12
  struct mkvparser::IMkvReader *v23; // r15
  unsigned int v24; // ebx
  struct mkvparser::IMkvReader *v25; // r14
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  struct mkvparser::IMkvReader *v29; // r14
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  unsigned __int64 v33; // rbx
  struct mkvparser::IMkvReader *v34; // r15
  mkvparser::Tag::Targets *v35; // rcx
  mkvparser::Tag::Targets *v36; // rax
  __int64 v37; // r8
  __int64 v38; // r9
  mkvparser *v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  struct CallStackContext *v60; // rax
  unsigned __int64 v61; // rax
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // r9
  _BYTE *v65; // rcx
  __int64 *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  __int64 i; // rax
  unsigned __int64 v70; // rax
  _BYTE *v71; // rax
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // r9
  __int64 *v75; // rcx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  __int64 j; // rcx
  _QWORD *v79; // r14
  __int64 v80; // rdx
  __int64 v81; // r8
  __int64 v82; // r9
  signed __int64 v83; // r13
  char *v84; // r15
  __int64 v85; // rdx
  __int64 v86; // r8
  __int64 v87; // r9
  __int64 v88; // r15
  __int64 v89; // r13
  __int64 v90; // rdx
  __int64 v91; // r8
  __int64 v92; // r9
  __int64 *v93; // rcx
  CallStackTracing *v94; // rax
  __int64 v95; // rdx
  __int64 v96; // r8
  __int64 v97; // r9
  __int64 *v98; // rcx
  CallStackTracing *v99; // rax
  __int64 v100; // rdx
  __int64 v101; // r8
  __int64 v102; // r9
  __int64 *v103; // rcx
  CallStackTracing *v104; // rax
  __int64 v105; // rdx
  __int64 v106; // r8
  __int64 v107; // r9
  __int64 *v108; // rcx
  CallStackTracing *v109; // rax
  __int64 v110; // rdx
  __int64 v111; // r8
  __int64 v112; // r9
  void *v113; // rax
  __int64 v114; // r8
  __int64 v115; // r9
  _QWORD *v116; // rbx
  _QWORD *v117; // rax
  __int64 v118; // r8
  __int64 v119; // r9
  unsigned int v120; // r8d
  struct CallStackContext *v121; // rax
  struct CallStackContext *v122; // rax
  struct CallStackContext *v123; // rax
  struct CallStackContext *v124; // rax
  __int64 v125; // rdx
  __int64 v126; // r8
  __int64 v127; // r9
  __int64 *v128; // rcx
  CallStackTracing *v129; // rax
  struct CallStackContext *v130; // rax
  __int64 *v131; // rcx
  CallStackTracing *v132; // rax
  struct CallStackContext *v133; // rax
  __int64 *v134; // rcx
  CallStackTracing *v135; // rax
  struct CallStackContext *v136; // rax
  __int64 *v137; // rcx
  CallStackTracing *v138; // rax
  struct CallStackContext *v139; // rax
  __int64 *v140; // rcx
  CallStackTracing *v141; // rax
  struct CallStackContext *v142; // rax
  __int64 *v143; // rcx
  CallStackTracing *v144; // rax
  struct CallStackContext *v145; // rax
  __int64 *v146; // rcx
  CallStackTracing *v147; // rax
  struct CallStackContext *v148; // rax
  __int64 *v149; // rcx
  CallStackTracing *v150; // rax
  struct CallStackContext *v151; // rax
  unsigned int v152; // ebx
  __int64 v153; // rdx
  __int64 v154; // rcx
  unsigned __int64 v155; // rax
  __int64 v156; // r8
  __int64 v157; // r9
  __int64 v158; // rcx
  __int64 *v159; // rcx
  CallStackTracing *v160; // rax
  struct CallStackContext *v161; // rax
  __int64 v162; // r15
  char **v163; // [rsp+20h] [rbp-48h]
  __int64 v164; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int64 v165; // [rsp+38h] [rbp-30h] BYREF
  signed __int64 v166; // [rsp+40h] [rbp-28h]
  void *Block; // [rsp+48h] [rbp-20h]
  struct mkvparser::IMkvReader *v168; // [rsp+50h] [rbp-18h]
  unsigned int v169; // [rsp+B0h] [rbp+48h] BYREF
  mkvparser *v170; // [rsp+B8h] [rbp+50h]
  __int64 v171; // [rsp+C0h] [rbp+58h] BYREF
  unsigned __int64 v172; // [rsp+C8h] [rbp+60h]

  v170 = a2;
  v2 = 0;
  if ( *((_QWORD *)this + 4) )
    return 0;
  v168 = *(struct mkvparser::IMkvReader **)this;
  v6 = v168;
  v164 = 0;
  v165 = 0;
  LODWORD(v171) = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v169, "mkvparser::Tag::Load", 4230);
  v8 = mkvparser::ReadID(
         (__int64 (__fastcall ***)(mkvparser *, struct mkvparser::IMkvReader *, __int64, unsigned __int8 *))a2,
         v168,
         &v164,
         &v171);
  if ( v8 < 0 )
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v9, v10);
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
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "mkvparser::Tag::Load", 4230, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_304;
    v14 = 366;
    goto LABEL_272;
  }
  if ( v164 != 29555 )
  {
LABEL_303:
    v8 = 0;
    goto LABEL_304;
  }
  v15 = (struct mkvparser::IMkvReader *)((char *)v6 + (int)v171);
  v8 = mkvparser::ReadUInt(
         (__int64 (__fastcall ***)(mkvparser *, struct mkvparser::IMkvReader *, __int64, unsigned __int8 *))a2,
         v15,
         (__int64 *)&v165,
         &v171);
  if ( v8 < 0 )
  {
    v19 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17, v18);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v21 + 499) != v8 )
        CallStackContext::TraceFailure(v21, "mkvparser::Tag::Load", 4237, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_304;
    v14 = 367;
    goto LABEL_272;
  }
  v22 = (struct mkvparser::IMkvReader *)((char *)v15 + (int)v171);
  v23 = (struct mkvparser::IMkvReader *)((char *)v22 + v165);
  v166 = (signed __int64)v22 + v165;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v169);
  v24 = 0;
  v25 = v22;
  LODWORD(v172) = 0;
  Block = 0;
  while ( 1 )
  {
    if ( (__int64)v25 >= (__int64)v23 )
      goto LABEL_77;
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v169, "mkvparser::Tag::Load", 4256);
    v8 = mkvparser::ReadID(
           (__int64 (__fastcall ***)(mkvparser *, struct mkvparser::IMkvReader *, __int64, unsigned __int8 *))v170,
           v25,
           &v164,
           &v171);
    if ( v8 < 0 )
    {
      v57 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
        CallStackTracing::s_wpInstance = v58;
        if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
        {
          v57 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v57 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v57 + 8) )
      {
        v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
        if ( *((_DWORD *)v59 + 499) != v8 )
          CallStackContext::TraceFailure(v59, "mkvparser::Tag::Load", 4256, v8);
      }
      if ( !g_wppLevels )
        goto LABEL_304;
      v14 = 368;
LABEL_272:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, this, v8);
      goto LABEL_304;
    }
    v29 = (struct mkvparser::IMkvReader *)((char *)v25 + (int)v171);
    if ( (__int64)v29 > (__int64)v23 )
      goto LABEL_76;
    v8 = mkvparser::ReadUInt(
           (__int64 (__fastcall ***)(mkvparser *, struct mkvparser::IMkvReader *, __int64, unsigned __int8 *))v170,
           v29,
           (__int64 *)&v165,
           &v171);
    if ( v8 < 0 )
    {
      v49 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
        CallStackTracing::s_wpInstance = v50;
        if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
        {
          v49 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v49 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v49 + 8) )
      {
        v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
        if ( *((_DWORD *)v51 + 499) != v8 )
          CallStackContext::TraceFailure(v51, "mkvparser::Tag::Load", 4265, v8);
      }
      if ( !g_wppLevels )
        goto LABEL_304;
      v14 = 369;
      goto LABEL_272;
    }
    v25 = (struct mkvparser::IMkvReader *)((char *)v29 + (int)v171);
    if ( (__int64)v25 > (__int64)v23 )
      goto LABEL_76;
    v33 = v165;
    v34 = (struct mkvparser::IMkvReader *)((char *)v25 + v165);
    if ( (__int64)((__int64)v25 + v165) > v166 )
      break;
    if ( v164 == 25536 )
    {
      v35 = (mkvparser::Tag::Targets *)*((_QWORD *)this + 2);
      if ( v35 )
        mkvparser::Tag::Targets::`scalar deleting destructor'(v35, v30);
      v36 = (mkvparser::Tag::Targets *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v36 )
      {
        v46 = (__int64 *)CallStackTracing::s_wpInstance;
        *((_QWORD *)this + 2) = 0;
        if ( !v46 )
        {
          v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0, v37, v38);
          CallStackTracing::s_wpInstance = v47;
          if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
          {
            v46 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v46 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        v8 = -2147024882;
        if ( *((_BYTE *)v46 + 8) )
        {
          v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
          if ( *((_DWORD *)v48 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v48, "mkvparser::Tag::Load", 4282, -2147024882);
        }
        if ( !g_wppLevels )
          goto LABEL_304;
        v14 = 370;
        goto LABEL_272;
      }
      *((_QWORD *)v36 + 1) = 0;
      *((_QWORD *)v36 + 2) = 0;
      *((_QWORD *)v36 + 3) = 0;
      *((_QWORD *)v36 + 4) = 0;
      *((_QWORD *)v36 + 5) = 0;
      v39 = v170;
      *(_QWORD *)v36 = 50;
      *((_QWORD *)this + 2) = v36;
      v8 = mkvparser::Tag::Targets::Parse(v36, v39, (__int64)v25, v33);
      if ( v8 < 0 )
      {
        v43 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40, v41, v42);
          CallStackTracing::s_wpInstance = v44;
          if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
          {
            v43 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v43 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v43 + 8) )
        {
          v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
          if ( *((_DWORD *)v45 + 499) != v8 )
            CallStackContext::TraceFailure(v45, "mkvparser::Tag::Load", 4284, v8);
        }
        if ( !g_wppLevels )
          goto LABEL_304;
        v14 = 371;
        goto LABEL_272;
      }
    }
    if ( v164 != 26568 || v2 == -1 )
    {
      v24 = v172;
      v25 = v34;
    }
    else
    {
      v24 = v172;
      ++v2;
      if ( (__int64)v34 > (__int64)Block && (_DWORD)v172 != -1 )
      {
        v24 = v172 + 1;
        Block = v34;
        LODWORD(v172) = v172 + 1;
      }
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v169);
    v23 = (struct mkvparser::IMkvReader *)v166;
  }
  v23 = (struct mkvparser::IMkvReader *)v166;
LABEL_76:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v169);
  v24 = v172;
LABEL_77:
  if ( !v2 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v169, "mkvparser::Tag::Load", 4307);
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
    v8 = -1072875842;
    if ( *((_BYTE *)v55 + 8) )
    {
      v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
      if ( *((_DWORD *)v60 + 499) != -1072875842 )
        CallStackContext::TraceFailure(v60, "mkvparser::Tag::Load", 4307, -1072875842);
    }
    if ( !g_wppLevels )
      goto LABEL_304;
    v14 = 372;
    goto LABEL_272;
  }
  v61 = 8LL * v2;
  if ( !is_mul_ok(v2, 8u) )
    v61 = -1;
  *((_QWORD *)this + 4) = operator new[](v61, (const struct std::nothrow_t *)&std::nothrow);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v169, "mkvparser::Tag::Load", 4311);
  v65 = (_BYTE *)*((_QWORD *)this + 4);
  if ( !v65 )
  {
    v66 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62, v63, v64);
      CallStackTracing::s_wpInstance = v67;
      if ( v67 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
      {
        v66 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v66 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    v8 = -2147024882;
    if ( *((_BYTE *)v66 + 8) )
    {
      v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
      if ( *((_DWORD *)v68 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v68, "mkvparser::Tag::Load", 4311, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_304;
    v14 = 373;
    goto LABEL_272;
  }
  for ( i = 8LL * v2; i; --i )
    *v65++ = 0;
  *((_DWORD *)this + 10) = v2;
  v70 = 8LL * v24;
  if ( !is_mul_ok(v24, 8u) )
    v70 = -1;
  v71 = operator new[](v70, (const struct std::nothrow_t *)&std::nothrow);
  *((_QWORD *)this + 6) = v71;
  if ( !v71 )
  {
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
    v8 = -2147024882;
    if ( *((_BYTE *)v75 + 8) )
    {
      v77 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v75);
      if ( *((_DWORD *)v77 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v77, "mkvparser::Tag::Load", 4316, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_304;
    v14 = 374;
    goto LABEL_272;
  }
  for ( j = 8LL * v24; j; --j )
    *v71++ = 0;
  v79 = 0;
  v172 = *((_QWORD *)this + 4);
  *((_DWORD *)this + 14) = v24;
  v169 = 0;
  while ( 2 )
  {
    if ( (__int64)v22 < (__int64)v23 )
    {
      if ( v79 && (__int64)v22 >= v79[9] + v79[10] )
      {
        v79 = (_QWORD *)*v79;
        continue;
      }
      v8 = mkvparser::ReadID(
             (__int64 (__fastcall ***)(mkvparser *, struct mkvparser::IMkvReader *, __int64, unsigned __int8 *))v170,
             v22,
             &v164,
             &v171);
      if ( v8 < 0 )
      {
        v149 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v150 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v80, v81, v82);
          CallStackTracing::s_wpInstance = v150;
          if ( v150 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v150 + 8LL))(v150, 2032) )
          {
            v149 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v149 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v149 + 8) )
        {
          v151 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v149);
          if ( *((_DWORD *)v151 + 499) != v8 )
            CallStackContext::TraceFailure(v151, "mkvparser::Tag::Load", 4334, v8);
        }
        if ( !g_wppLevels )
          goto LABEL_304;
        v14 = 375;
        goto LABEL_272;
      }
      v83 = v166;
      v84 = (char *)v22 + (int)v171;
      if ( (__int64)v84 > v166 )
      {
        v146 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v147 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v80, v81, v82);
          CallStackTracing::s_wpInstance = v147;
          if ( v147 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v147 + 8LL))(v147, 2032) )
          {
            v146 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v146 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        v8 = -1072875842;
        if ( *((_BYTE *)v146 + 8) )
        {
          v148 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v146);
          if ( *((_DWORD *)v148 + 499) != -1072875842 )
            CallStackContext::TraceFailure(v148, "mkvparser::Tag::Load", 4338, -1072875842);
        }
        if ( !g_wppLevels )
          goto LABEL_304;
        v14 = 376;
        goto LABEL_272;
      }
      v8 = mkvparser::ReadUInt(
             (__int64 (__fastcall ***)(mkvparser *, struct mkvparser::IMkvReader *, __int64, unsigned __int8 *))v170,
             (struct mkvparser::IMkvReader *)((char *)v22 + (int)v171),
             (__int64 *)&v165,
             &v171);
      if ( v8 < 0 )
      {
        v143 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v144 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v85, v86, v87);
          CallStackTracing::s_wpInstance = v144;
          if ( v144 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v144 + 8LL))(v144, 2032) )
          {
            v143 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v143 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v143 + 8) )
        {
          v145 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v143);
          if ( *((_DWORD *)v145 + 499) != v8 )
            CallStackContext::TraceFailure(v145, "mkvparser::Tag::Load", 4343, v8);
        }
        if ( !g_wppLevels )
          goto LABEL_304;
        v14 = 377;
        goto LABEL_272;
      }
      v22 = (struct mkvparser::IMkvReader *)&v84[(int)v171];
      if ( (__int64)v22 > v83 )
      {
        v140 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v141 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v85, v86, v87);
          CallStackTracing::s_wpInstance = v141;
          if ( v141 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v141 + 8LL))(v141, 2032) )
          {
            v140 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v140 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        v8 = -1072875842;
        if ( *((_BYTE *)v140 + 8) )
        {
          v142 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v140);
          if ( *((_DWORD *)v142 + 499) != -1072875842 )
            CallStackContext::TraceFailure(v142, "mkvparser::Tag::Load", 4347, -1072875842);
        }
        if ( !g_wppLevels )
          goto LABEL_304;
        v14 = 378;
        goto LABEL_272;
      }
      v88 = v165;
      v89 = v164;
      if ( !v79 )
        goto LABEL_168;
      switch ( v164 )
      {
        case 17827LL:
          v8 = mkvparser::UnserializeString(v170, v22, v165, (__int64)(v79 + 1), v163);
          if ( v8 < 0 )
          {
            v93 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v94 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v90, v91, v92);
              CallStackTracing::s_wpInstance = v94;
              if ( v94
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v94 + 8LL))(v94, 2032) )
              {
                v93 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v93 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            if ( *((_BYTE *)v93 + 8) )
            {
              v121 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v93);
              if ( *((_DWORD *)v121 + 499) != v8 )
                CallStackContext::TraceFailure(v121, "mkvparser::Tag::Load", 4357, v8);
            }
            if ( !g_wppLevels )
              goto LABEL_304;
            v14 = 379;
            goto LABEL_272;
          }
          goto LABEL_176;
        case 17530LL:
          v8 = mkvparser::UnserializeString(v170, v22, v165, (__int64)(v79 + 2), v163);
          if ( v8 < 0 )
          {
            v98 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v99 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v95, v96, v97);
              CallStackTracing::s_wpInstance = v99;
              if ( v99
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v99 + 8LL))(v99, 2032) )
              {
                v98 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v98 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            if ( *((_BYTE *)v98 + 8) )
            {
              v122 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v98);
              if ( *((_DWORD *)v122 + 499) != v8 )
                CallStackContext::TraceFailure(v122, "mkvparser::Tag::Load", 4361, v8);
            }
            if ( !g_wppLevels )
              goto LABEL_304;
            v14 = 380;
            goto LABEL_272;
          }
          goto LABEL_176;
        case 17540LL:
          v8 = mkvparser::UnserializeUInt(v170, v22, v165, (__int64)(v79 + 3), (__int64 *)v163);
          if ( v8 < 0 )
          {
            v103 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v104 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v100, v101, v102);
              CallStackTracing::s_wpInstance = v104;
              if ( v104
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v104 + 8LL))(v104, 2032) )
              {
                v103 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v103 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            if ( *((_BYTE *)v103 + 8) )
            {
              v123 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v103);
              if ( *((_DWORD *)v123 + 499) != v8 )
                CallStackContext::TraceFailure(v123, "mkvparser::Tag::Load", 4365, v8);
            }
            if ( !g_wppLevels )
              goto LABEL_304;
            v14 = 381;
            goto LABEL_272;
          }
          goto LABEL_176;
        case 17543LL:
          v8 = mkvparser::UnserializeString(v170, v22, v165, (__int64)(v79 + 4), v163);
          if ( v8 < 0 )
          {
            v108 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v109 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v105, v106, v107);
              CallStackTracing::s_wpInstance = v109;
              if ( v109
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v109 + 8LL))(v109, 2032) )
              {
                v108 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v108 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            if ( *((_BYTE *)v108 + 8) )
            {
              v124 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v108);
              if ( *((_DWORD *)v124 + 499) != v8 )
                CallStackContext::TraceFailure(v124, "mkvparser::Tag::Load", 4369, v8);
            }
            if ( !g_wppLevels )
              goto LABEL_304;
            v14 = 382;
            goto LABEL_272;
          }
          goto LABEL_176;
        case 17541LL:
          operator delete((void *)v79[5]);
          v79[5] = 0;
          v79[6] = 0;
          if ( v88 > 0x7FFFFFFF )
          {
            v134 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v135 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v110, v111, v112);
              CallStackTracing::s_wpInstance = v135;
              if ( v135
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v135 + 8LL))(v135, 2032) )
              {
                v134 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v134 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            v8 = -1072875842;
            if ( *((_BYTE *)v134 + 8) )
            {
              v136 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v134);
              if ( *((_DWORD *)v136 + 499) != -1072875842 )
                CallStackContext::TraceFailure(v136, "mkvparser::Tag::Load", 4379, -1072875842);
            }
            if ( !g_wppLevels )
              goto LABEL_304;
            v14 = 383;
            goto LABEL_272;
          }
          if ( v88 )
          {
            v113 = operator new[](v88, (const struct std::nothrow_t *)&std::nothrow);
            Block = v113;
            if ( !v113 )
            {
              v131 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v132 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0, v114, v115);
                CallStackTracing::s_wpInstance = v132;
                if ( v132
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v132 + 8LL))(v132, 2032) )
                {
                  v131 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v131 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                }
              }
              v8 = -2147024882;
              if ( *((_BYTE *)v131 + 8) )
              {
                v133 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v131);
                if ( *((_DWORD *)v133 + 499) != -2147024882 )
                  CallStackContext::TraceFailure(v133, "mkvparser::Tag::Load", 4388, -2147024882);
              }
              if ( !g_wppLevels )
                goto LABEL_304;
              v14 = 384;
              goto LABEL_272;
            }
            v8 = (**(__int64 (__fastcall ***)(mkvparser *, struct mkvparser::IMkvReader *, _QWORD, void *))v170)(
                   v170,
                   v22,
                   (unsigned int)v88,
                   v113);
            if ( v8 < 0 )
            {
              operator delete(Block);
              v128 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v129 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v125, v126, v127);
                CallStackTracing::s_wpInstance = v129;
                if ( v129
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v129 + 8LL))(v129, 2032) )
                {
                  v128 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v128 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                }
              }
              if ( *((_BYTE *)v128 + 8) )
              {
                v130 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v128);
                if ( *((_DWORD *)v130 + 499) != v8 )
                  CallStackContext::TraceFailure(v130, "mkvparser::Tag::Load", 4394, v8);
              }
              if ( !g_wppLevels )
                goto LABEL_304;
              v14 = 385;
              goto LABEL_272;
            }
            v79[5] = Block;
            v79[6] = v88;
            goto LABEL_168;
          }
LABEL_176:
          v22 = (struct mkvparser::IMkvReader *)((char *)v22 + v88);
          break;
        default:
LABEL_168:
          if ( v89 != 26568 )
            goto LABEL_176;
          v116 = (_QWORD *)v172;
          if ( v172 >= *((_QWORD *)this + 4) + 8 * (unsigned __int64)*((unsigned int *)this + 10) )
            goto LABEL_176;
          v117 = operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
          if ( !v117 )
          {
            v137 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v138 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0, v118, v119);
              CallStackTracing::s_wpInstance = v138;
              if ( v138
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v138 + 8LL))(v138, 2032) )
              {
                v137 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v137 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            v8 = -2147024882;
            if ( *((_BYTE *)v137 + 8) )
            {
              v139 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v137);
              if ( *((_DWORD *)v139 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v139, "mkvparser::Tag::Load", 4405, -2147024882);
            }
            if ( !g_wppLevels )
              goto LABEL_304;
            v14 = 386;
            goto LABEL_272;
          }
          v117[1] = 0;
          v117[2] = 0;
          v117[3] = 0;
          v117[4] = 0;
          v117[5] = 0;
          v117[7] = 0;
          v117[8] = 0;
          *v116 = v117;
          v172 = (unsigned __int64)(v116 + 1);
          v117[9] = v22;
          v117[10] = v88;
          *v117 = v79;
          if ( v79 )
          {
            ++*((_DWORD *)v79 + 17);
          }
          else
          {
            v120 = v169;
            if ( v169 != -1 )
            {
              *(_QWORD *)(*((_QWORD *)this + 6) + 8LL * v169) = v117;
              v169 = v120 + 1;
            }
          }
          v79 = v117;
          break;
      }
      v23 = (struct mkvparser::IMkvReader *)v166;
      continue;
    }
    break;
  }
  v152 = 0;
  while ( 2 )
  {
    if ( v152 >= *((_DWORD *)this + 10) )
    {
      v162 = v23 - v168;
      *(_QWORD *)this = v168;
      *((_QWORD *)this + 1) = v162;
      goto LABEL_303;
    }
    v153 = *((_QWORD *)this + 4);
    v154 = **(_QWORD **)(v153 + 8LL * v152);
    if ( !v154 )
    {
LABEL_291:
      ++v152;
      continue;
    }
    break;
  }
  if ( *(_QWORD *)(v154 + 56) )
    goto LABEL_290;
  v155 = 8LL * *(int *)(v154 + 68);
  if ( !is_mul_ok(*(int *)(v154 + 68), 8u) )
    v155 = -1;
  *(_QWORD *)(**(_QWORD **)(*((_QWORD *)this + 4) + 8LL * v152) + 56LL) = operator new[](
                                                                            v155,
                                                                            (const struct std::nothrow_t *)&std::nothrow);
  v153 = *((_QWORD *)this + 4);
  if ( *(_QWORD *)(**(_QWORD **)(v153 + 8LL * v152) + 56LL) )
  {
LABEL_290:
    *(_QWORD *)(*(_QWORD *)(**(_QWORD **)(v153 + 8LL * v152) + 56LL)
              + 8LL * *(int *)(**(_QWORD **)(v153 + 8LL * v152) + 64LL)) = *(_QWORD *)(v153 + 8LL * v152);
    v158 = *(_QWORD *)(*((_QWORD *)this + 4) + 8LL * v152);
    ++*(_DWORD *)(*(_QWORD *)v158 + 64LL);
    goto LABEL_291;
  }
  v159 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v160 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v153, v156, v157);
    CallStackTracing::s_wpInstance = v160;
    if ( v160 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v160 + 8LL))(v160, 2032) )
    {
      v159 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v159 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  v8 = -2147024882;
  if ( *((_BYTE *)v159 + 8) )
  {
    v161 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v159);
    if ( *((_DWORD *)v161 + 499) != -2147024882 )
      CallStackContext::TraceFailure(v161, "mkvparser::Tag::Load", 4440, -2147024882);
  }
  if ( g_wppLevels )
  {
    v14 = 387;
    goto LABEL_272;
  }
LABEL_304:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v169);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180093bb4  mov     [rsp-40h+arg_8], rdx
0x180093bb9  push    rbp
0x180093bba  push    rbx
0x180093bbb  push    rsi
0x180093bbc  push    rdi
0x180093bbd  push    r12
0x180093bbf  push    r13
0x180093bc1  push    r14
0x180093bc3  push    r15
0x180093bc5  mov     rbp, rsp
0x180093bc8  sub     rsp, 68h
0x180093bcc  xor     r13d, r13d
0x180093bcf  mov     r14, rdx
0x180093bd2  mov     rdi, rcx
0x180093bd5  cmp     [rcx+20h], r13
0x180093bd9  jz      short loc_180093BE2
0x180093bdb  xor     eax, eax
0x180093bdd  jmp     loc_180094F44
0x180093be2  mov     rsi, [rcx]
0x180093be5  lea     r15, aMkvparserTagLo; "mkvparser::Tag::Load"
0x180093bec  mov     r12d, 1086h
0x180093bf2  mov     [rbp+var_18], rsi
0x180093bf6  mov     r8d, r12d; int
0x180093bf9  mov     [rbp+var_38], r13
0x180093bfd  mov     rdx, r15; char *
0x180093c00  mov     [rbp+var_30], r13
0x180093c04  lea     rcx, [rbp+arg_0]; this
0x180093c08  mov     dword ptr [rbp+arg_10], r13d
0x180093c0c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180093c11  lea     r9, [rbp+arg_10]; __int64 *
0x180093c15  mov     rdx, rsi; struct mkvparser::IMkvReader *
0x180093c18  lea     r8, [rbp+var_38]; __int64
0x180093c1c  mov     rcx, r14; this
0x180093c1f  call    ?ReadID@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadID(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x180093c24  mov     ebx, eax
0x180093c26  test    eax, eax
0x180093c28  jns     loc_180093CC1
0x180093c2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180093c35  test    rcx, rcx
0x180093c38  jnz     short loc_180093C81
0x180093c3a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180093c41  nop     dword ptr [rax+rax+00h]
0x180093c46  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180093c4d  mov     rcx, rax
0x180093c50  test    rax, rax
0x180093c53  jz      short loc_180093C73
0x180093c55  mov     rax, [rax]
0x180093c58  mov     edx, 7F0h
0x180093c5d  mov     rax, [rax+8]
0x180093c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c66  test    eax, eax
0x180093c68  jz      short loc_180093C73
0x180093c6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180093c71  jmp     short loc_180093C81
0x180093c73  lea     rcx, qword_1800DBF70; this
0x180093c7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180093c81  cmp     [rcx+8], r13b
0x180093c85  jz      short loc_180093CA5
0x180093c87  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180093c8c  cmp     [rax+7CCh], ebx
0x180093c92  jz      short loc_180093CA5
0x180093c94  mov     r9d, ebx; int
0x180093c97  mov     r8d, r12d; int
0x180093c9a  mov     rdx, r15; char *
0x180093c9d  mov     rcx, rax; this
0x180093ca0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180093ca5  mov     esi, 1
0x180093caa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180093cb1  jb      loc_180094F39
0x180093cb7  mov     edx, 16Eh
0x180093cbc  jmp     loc_180094D47
0x180093cc1  cmp     [rbp+var_38], 7373h
0x180093cc9  jnz     loc_180094F36
0x180093ccf  movsxd  rax, dword ptr [rbp+arg_10]
0x180093cd3  lea     r9, [rbp+arg_10]; __int64 *
0x180093cd7  add     rsi, rax
0x180093cda  lea     r8, [rbp+var_30]; __int64
0x180093cde  mov     rdx, rsi; struct mkvparser::IMkvReader *
0x180093ce1  mov     rcx, r14; this
0x180093ce4  call    ?ReadUInt@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadUInt(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x180093ce9  mov     ebx, eax
0x180093ceb  test    eax, eax
0x180093ced  jns     loc_180093D89
0x180093cf3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180093cfa  test    rcx, rcx
0x180093cfd  jnz     short loc_180093D46
0x180093cff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180093d06  nop     dword ptr [rax+rax+00h]
0x180093d0b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180093d12  mov     rcx, rax
0x180093d15  test    rax, rax
0x180093d18  jz      short loc_180093D38
0x180093d1a  mov     rax, [rax]
0x180093d1d  mov     edx, 7F0h
0x180093d22  mov     rax, [rax+8]
0x180093d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093d2b  test    eax, eax
0x180093d2d  jz      short loc_180093D38
0x180093d2f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180093d36  jmp     short loc_180093D46
0x180093d38  lea     rcx, qword_1800DBF70; this
0x180093d3f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180093d46  cmp     [rcx+8], r13b
0x180093d4a  jz      short loc_180093D6D
0x180093d4c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180093d51  cmp     [rax+7CCh], ebx
0x180093d57  jz      short loc_180093D6D
0x180093d59  mov     r9d, ebx; int
0x180093d5c  mov     r8d, 108Dh; int
0x180093d62  mov     rdx, r15; char *
0x180093d65  mov     rcx, rax; this
0x180093d68  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180093d6d  mov     esi, 1
0x180093d72  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180093d79  jb      loc_180094F39
0x180093d7f  mov     edx, 16Fh
0x180093d84  jmp     loc_180094D47
0x180093d89  movsxd  r12, dword ptr [rbp+arg_10]
0x180093d8d  lea     rcx, [rbp+arg_0]; this
0x180093d91  mov     r15, [rbp+var_30]
0x180093d95  add     r12, rsi
0x180093d98  add     r15, r12
0x180093d9b  mov     [rbp+var_28], r15
0x180093d9f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180093da4  xor     ebx, ebx
0x180093da6  mov     r14, r12
0x180093da9  mov     dword ptr [rbp+arg_18], ebx
0x180093dac  mov     [rbp+Block], rbx
0x180093db0  lea     esi, [rbx+1]
0x180093db3  cmp     r14, r15
0x180093db6  jge     loc_1800940CB
0x180093dbc  mov     r8d, 10A0h; int
0x180093dc2  lea     rdx, aMkvparserTagLo; "mkvparser::Tag::Load"
0x180093dc9  lea     rcx, [rbp+arg_0]; this
0x180093dcd  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180093dd2  mov     rcx, [rbp+arg_8]; this
0x180093dd6  lea     r9, [rbp+arg_10]; __int64 *
0x180093dda  lea     r8, [rbp+var_38]; __int64
0x180093dde  mov     rdx, r14; struct mkvparser::IMkvReader *
0x180093de1  call    ?ReadID@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadID(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x180093de6  mov     ebx, eax
0x180093de8  test    eax, eax
0x180093dea  js      loc_180094141
0x180093df0  movsxd  rax, dword ptr [rbp+arg_10]
0x180093df4  add     r14, rax
0x180093df7  cmp     r14, r15
0x180093dfa  jg      loc_1800940BF
0x180093e00  mov     rcx, [rbp+arg_8]; this
0x180093e04  lea     r9, [rbp+arg_10]; __int64 *
0x180093e08  lea     r8, [rbp+var_30]; __int64
0x180093e0c  mov     rdx, r14; struct mkvparser::IMkvReader *
0x180093e0f  call    ?ReadUInt@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadUInt(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x180093e14  mov     ebx, eax
0x180093e16  test    eax, eax
0x180093e18  js      loc_180094026
0x180093e1e  movsxd  rax, dword ptr [rbp+arg_10]
0x180093e22  add     r14, rax
0x180093e25  cmp     r14, r15
0x180093e28  jg      loc_1800940BF
0x180093e2e  mov     rbx, [rbp+var_30]
0x180093e32  lea     r15, [r14+rbx]
0x180093e36  cmp     r15, [rbp+var_28]
0x180093e3a  jg      loc_1800940BB
0x180093e40  cmp     [rbp+var_38], 63C0h
0x180093e48  jnz     short loc_180093EAB
0x180093e4a  mov     rcx, [rdi+10h]; this
0x180093e4e  test    rcx, rcx
0x180093e51  jz      short loc_180093E58
0x180093e53  call    ??_GTargets@Tag@mkvparser@@QEAAPEAXI@Z; mkvparser::Tag::Targets::`scalar deleting destructor'(uint)
0x180093e58  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180093e5f  mov     ecx, 30h ; '0'; unsigned __int64
0x180093e64  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180093e69  xor     edx, edx
0x180093e6b  test    rax, rax
0x180093e6e  jz      loc_180093F85
0x180093e74  mov     [rax+8], rdx
0x180093e78  mov     r9, rbx; __int64
0x180093e7b  mov     [rax+10h], rdx
0x180093e7f  mov     r8, r14; __int64
0x180093e82  mov     [rax+18h], rdx
0x180093e86  mov     rcx, rax; this
0x180093e89  mov     [rax+20h], rdx
0x180093e8d  mov     [rax+28h], rdx
0x180093e91  mov     rdx, [rbp+arg_8]; struct mkvparser::IMkvReader *
0x180093e95  mov     qword ptr [rax], 32h ; '2'
0x180093e9c  mov     [rdi+10h], rax
0x180093ea0  call    ?Parse@Targets@Tag@mkvparser@@QEAAJPEAUIMkvReader@3@_J1@Z; mkvparser::Tag::Targets::Parse(mkvparser::IMkvReader *,__int64,__int64)
0x180093ea5  mov     ebx, eax
0x180093ea7  test    eax, eax
0x180093ea9  js      short loc_180093EF0
0x180093eab  cmp     [rbp+var_38], 67C8h
0x180093eb3  jnz     short loc_180093ED8
0x180093eb5  or      eax, 0FFFFFFFFh
0x180093eb8  cmp     r13d, eax
0x180093ebb  jnb     short loc_180093ED8
0x180093ebd  mov     ebx, dword ptr [rbp+arg_18]
0x180093ec0  add     r13d, esi
0x180093ec3  cmp     r15, [rbp+Block]
0x180093ec7  jle     short loc_180093EDE
0x180093ec9  cmp     ebx, eax
0x180093ecb  jnb     short loc_180093EDE
0x180093ecd  add     ebx, esi
0x180093ecf  mov     [rbp+Block], r15
0x180093ed3  mov     dword ptr [rbp+arg_18], ebx
0x180093ed6  jmp     short loc_180093EDE
0x180093ed8  mov     ebx, dword ptr [rbp+arg_18]
0x180093edb  mov     r14, r15
0x180093ede  lea     rcx, [rbp+arg_0]; this
0x180093ee2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180093ee7  mov     r15, [rbp+var_28]
0x180093eeb  jmp     loc_180093DB3
0x180093ef0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180093ef7  test    rcx, rcx
0x180093efa  jnz     short loc_180093F43
0x180093efc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180093f03  nop     dword ptr [rax+rax+00h]
0x180093f08  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180093f0f  mov     rcx, rax
0x180093f12  test    rax, rax
0x180093f15  jz      short loc_180093F35
0x180093f17  mov     rax, [rax]
0x180093f1a  mov     edx, 7F0h
0x180093f1f  mov     rax, [rax+8]
0x180093f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093f28  test    eax, eax
0x180093f2a  jz      short loc_180093F35
0x180093f2c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180093f33  jmp     short loc_180093F43
0x180093f35  lea     rcx, qword_1800DBF70; this
0x180093f3c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180093f43  cmp     byte ptr [rcx+8], 0
0x180093f47  jz      short loc_180093F6E
0x180093f49  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180093f4e  cmp     [rax+7CCh], ebx
0x180093f54  jz      short loc_180093F6E
0x180093f56  mov     r9d, ebx; int
0x180093f59  lea     rdx, aMkvparserTagLo; "mkvparser::Tag::Load"
0x180093f60  mov     r8d, 10BCh; int
0x180093f66  mov     rcx, rax; this
0x180093f69  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180093f6e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180093f75  jb      loc_180094F39
0x180093f7b  mov     edx, 173h
0x180093f80  jmp     loc_180094D47
0x180093f85  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180093f8c  mov     [rdi+10h], rdx
0x180093f90  test    rcx, rcx
0x180093f93  jnz     short loc_180093FE0
0x180093f95  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180093f9c  nop     dword ptr [rax+rax+00h]
0x180093fa1  xor     edx, edx
0x180093fa3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180093faa  mov     rcx, rax
0x180093fad  test    rax, rax
0x180093fb0  jz      short loc_180093FD2
0x180093fb2  mov     rax, [rax]
0x180093fb5  mov     edx, 7F0h
0x180093fba  mov     rax, [rax+8]
0x180093fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093fc3  xor     edx, edx
0x180093fc5  test    eax, eax
0x180093fc7  jz      short loc_180093FD2
0x180093fc9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180093fd0  jmp     short loc_180093FE0
0x180093fd2  lea     rcx, qword_1800DBF70; this
0x180093fd9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180093fe0  mov     ebx, 8007000Eh
0x180093fe5  cmp     [rcx+8], dl
0x180093fe8  jz      short loc_18009400F
0x180093fea  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180093fef  cmp     [rax+7CCh], ebx
0x180093ff5  jz      short loc_18009400F
0x180093ff7  mov     r9d, ebx; int
0x180093ffa  lea     rdx, aMkvparserTagLo; "mkvparser::Tag::Load"
0x180094001  mov     r8d, 10BAh; int
0x180094007  mov     rcx, rax; this
0x18009400a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009400f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180094016  jb      loc_180094F39
0x18009401c  mov     edx, 172h
0x180094021  jmp     loc_180094D47
0x180094026  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009402d  test    rcx, rcx
0x180094030  jnz     short loc_180094079
0x180094032  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180094039  nop     dword ptr [rax+rax+00h]
0x18009403e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180094045  mov     rcx, rax
0x180094048  test    rax, rax
0x18009404b  jz      short loc_18009406B
0x18009404d  mov     rax, [rax]
0x180094050  mov     edx, 7F0h
0x180094055  mov     rax, [rax+8]
0x180094059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009405e  test    eax, eax
0x180094060  jz      short loc_18009406B
0x180094062  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180094069  jmp     short loc_180094079
0x18009406b  lea     rcx, qword_1800DBF70; this
0x180094072  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
