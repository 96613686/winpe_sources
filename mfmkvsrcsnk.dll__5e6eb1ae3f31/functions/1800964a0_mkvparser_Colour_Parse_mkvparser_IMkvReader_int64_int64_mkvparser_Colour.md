# mkvparser::Colour::Parse(mkvparser::IMkvReader *,__int64,__int64,mkvparser::Colour * *)

- ea: `0x1800964a0`
- end: `0x180097479`
- name: `?Parse@Colour@mkvparser@@SAJPEAUIMkvReader@2@_J1PEAPEAU12@@Z`
- size: `4057`
- prototype: `__int64 __fastcall(struct mkvparser::IMkvReader *this, __int64, __int64, struct mkvparser::Colour **)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18009c6dc`

## callees

- `0x180002410`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x180084120`
- `0x180091d70`
- `0x1800964a0`
- `0x180098f7c`
- `0x1800a1710`
- `0x1800aaa7c`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800964f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009658a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009663b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009679a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096814`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009688e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096908`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096982`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800969fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096a76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096af0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096b6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096be4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096c5e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096cd8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096d4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800971e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009727a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009731c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800973c4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800964f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009658a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009663b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009679a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096814`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009688e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096908`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096982`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800969fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096a76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096af0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096b6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096be4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096c5e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096cd8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096d4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800971e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009727a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009731c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800973c4`

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
        v11 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v16 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v22 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v129 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v119 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v35 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v40 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v45 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v50 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v55 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v60 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v65 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v70 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v75 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v80 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v85 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v90 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v95 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v113 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v125 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x1800964a0  push    rbp
0x1800964a2  push    rbx
0x1800964a3  push    rsi
0x1800964a4  push    rdi
0x1800964a5  push    r12
0x1800964a7  push    r13
0x1800964a9  push    r14
0x1800964ab  push    r15
0x1800964ad  mov     rbp, rsp
0x1800964b0  sub     rsp, 48h
0x1800964b4  mov     rbx, r8
0x1800964b7  lea     r12, aMkvparserColou; "mkvparser::Colour::Parse"
0x1800964be  mov     rsi, rdx
0x1800964c1  mov     r15, rcx
0x1800964c4  mov     edi, 1751h
0x1800964c9  lea     rcx, [rbp+arg_0]; this
0x1800964cd  mov     r8d, edi; int
0x1800964d0  mov     rdx, r12; char *
0x1800964d3  mov     r13, r9
0x1800964d6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800964db  xor     r14d, r14d
0x1800964de  test    r15, r15
0x1800964e1  jnz     loc_180096574
0x1800964e7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800964ee  test    rcx, rcx
0x1800964f1  jnz     short loc_180096534
0x1800964f3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800964f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180096500  mov     rcx, rax
0x180096503  test    rax, rax
0x180096506  jz      short loc_180096526
0x180096508  mov     rax, [rax]
0x18009650b  mov     edx, 7F0h
0x180096510  mov     rax, [rax+8]
0x180096514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096519  test    eax, eax
0x18009651b  jz      short loc_180096526
0x18009651d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180096524  jmp     short loc_180096534
0x180096526  lea     rcx, qword_1800D6F70; this
0x18009652d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180096534  mov     ebx, 80070057h
0x180096539  cmp     [rcx+8], r14b
0x18009653d  jz      short loc_18009655D
0x18009653f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180096544  cmp     [rax+7CCh], ebx
0x18009654a  jz      short loc_18009655D
0x18009654c  mov     r9d, ebx; int
0x18009654f  mov     r8d, edi; int
0x180096552  mov     rdx, r12; char *
0x180096555  mov     rcx, rax; this
0x180096558  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009655d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180096564  jb      loc_18009745D
0x18009656a  mov     edx, 1FBh
0x18009656f  jmp     loc_18009743F
0x180096574  cmp     [r13+0], r14
0x180096578  jz      loc_18009660E
0x18009657e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180096585  test    rcx, rcx
0x180096588  jnz     short loc_1800965CB
0x18009658a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180096590  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180096597  mov     rcx, rax
0x18009659a  test    rax, rax
0x18009659d  jz      short loc_1800965BD
0x18009659f  mov     rax, [rax]
0x1800965a2  mov     edx, 7F0h
0x1800965a7  mov     rax, [rax+8]
0x1800965ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800965b0  test    eax, eax
0x1800965b2  jz      short loc_1800965BD
0x1800965b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800965bb  jmp     short loc_1800965CB
0x1800965bd  lea     rcx, qword_1800D6F70; this
0x1800965c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800965cb  mov     ebx, 80070057h
0x1800965d0  cmp     [rcx+8], r14b
0x1800965d4  jz      short loc_1800965F7
0x1800965d6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800965db  cmp     [rax+7CCh], ebx
0x1800965e1  jz      short loc_1800965F7
0x1800965e3  mov     r9d, ebx; int
0x1800965e6  mov     r8d, 1754h; int
0x1800965ec  mov     rdx, r12; char *
0x1800965ef  mov     rcx, rax; this
0x1800965f2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800965f7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800965fe  jb      loc_18009745D
0x180096604  mov     edx, 1FCh
0x180096609  jmp     loc_18009743F
0x18009660e  lea     r8, [rbp+var_18]; __int64 *
0x180096612  mov     [rbp+arg_0], rsi
0x180096616  mov     rdx, rbx; __int64
0x180096619  mov     [rbp+var_18], r14
0x18009661d  mov     rcx, rsi; __int64
0x180096620  call    ?LongLongAdd@@YAJ_J0PEA_J@Z; LongLongAdd(__int64,__int64,__int64 *)
0x180096625  mov     ebx, eax
0x180096627  test    eax, eax
0x180096629  jns     loc_1800966BA
0x18009662f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180096636  test    rcx, rcx
0x180096639  jnz     short loc_18009667C
0x18009663b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180096641  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180096648  mov     rcx, rax
0x18009664b  test    rax, rax
0x18009664e  jz      short loc_18009666E
0x180096650  mov     rax, [rax]
0x180096653  mov     edx, 7F0h
0x180096658  mov     rax, [rax+8]
0x18009665c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096661  test    eax, eax
0x180096663  jz      short loc_18009666E
0x180096665  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009666c  jmp     short loc_18009667C
0x18009666e  lea     rcx, qword_1800D6F70; this
0x180096675  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009667c  cmp     [rcx+8], r14b
0x180096680  jz      short loc_1800966A3
0x180096682  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180096687  cmp     [rax+7CCh], ebx
0x18009668d  jz      short loc_1800966A3
0x18009668f  mov     r9d, ebx; int
0x180096692  mov     r8d, 175Ah; int
0x180096698  mov     rdx, r12; char *
0x18009669b  mov     rcx, rax; this
0x18009669e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800966a3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800966aa  jb      loc_18009745D
0x1800966b0  mov     edx, 1FDh
0x1800966b5  jmp     loc_18009743F
0x1800966ba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800966c1  mov     ecx, 70h ; 'p'; unsigned __int64
0x1800966c6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800966cb  mov     rdi, rax
0x1800966ce  test    rax, rax
0x1800966d1  jz      loc_1800973B8
0x1800966d7  mov     r12, [rbp+var_18]
0x1800966db  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800966e5  mov     [rdi], rax
0x1800966e8  mov     [rdi+8], rax
0x1800966ec  mov     [rdi+10h], rax
0x1800966f0  mov     [rdi+18h], rax
0x1800966f4  mov     [rdi+20h], rax
0x1800966f8  mov     [rdi+28h], rax
0x1800966fc  mov     [rdi+30h], rax
0x180096700  mov     [rdi+38h], rax
0x180096704  mov     [rdi+40h], rax
0x180096708  mov     [rdi+48h], rax
0x18009670c  mov     [rdi+50h], rax
0x180096710  mov     [rdi+58h], rax
0x180096714  mov     [rdi+60h], rax
0x180096718  mov     [rdi+68h], r14
0x18009671c  cmp     rsi, r12
0x18009671f  jge     loc_1800972FD
0x180096725  lea     rax, [rbp+var_18]
0x180096729  mov     [rbp+var_10], r14
0x18009672d  lea     r9, [rbp+var_10]; __int64
0x180096731  mov     [rsp+48h+var_28], rax; __int64 *
0x180096736  mov     r8, r12; __int64 *
0x180096739  mov     [rbp+var_18], r14
0x18009673d  lea     rdx, [rbp+arg_0]; struct mkvparser::IMkvReader *
0x180096741  mov     rcx, r15; this
0x180096744  call    ?ParseElementHeader@mkvparser@@YAJPEAUIMkvReader@1@AEA_J_J11@Z; mkvparser::ParseElementHeader(mkvparser::IMkvReader *,__int64 &,__int64,__int64 &,__int64 &)
0x180096749  mov     ebx, eax
0x18009674b  test    eax, eax
0x18009674d  js      loc_180097266
0x180096753  mov     rax, [rbp+var_10]
0x180096757  mov     rsi, [rbp+arg_0]
0x18009675b  mov     r14, [rbp+var_18]
0x18009675f  cmp     rax, 55B1h
0x180096765  jnz     short loc_1800967D8
0x180096767  mov     r9, rdi; __int64
0x18009676a  mov     r8, r14; __int64
0x18009676d  mov     rdx, rsi; struct mkvparser::IMkvReader *
0x180096770  mov     rcx, r15; this
0x180096773  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x180096778  mov     ebx, eax
0x18009677a  test    eax, eax
0x18009677c  jns     loc_180096DB0
0x180096782  mov     rcx, rdi; this
0x180096785  call    ??_GColour@mkvparser@@QEAAPEAXI@Z; mkvparser::Colour::`scalar deleting destructor'(uint)
0x18009678a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180096791  test    rcx, rcx
0x180096794  jnz     loc_180096DCD
0x18009679a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800967a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800967a7  mov     rcx, rax
0x1800967aa  test    rax, rax
0x1800967ad  jz      loc_180096DBF
0x1800967b3  mov     rax, [rax]
0x1800967b6  mov     edx, 7F0h
0x1800967bb  mov     rax, [rax+8]
0x1800967bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800967c4  test    eax, eax
0x1800967c6  jz      loc_180096DBF
0x1800967cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800967d3  jmp     loc_180096DCD
0x1800967d8  cmp     rax, 55B2h
0x1800967de  jnz     short loc_180096852
0x1800967e0  lea     r9, [rdi+8]; __int64
0x1800967e4  mov     r8, r14; __int64
0x1800967e7  mov     rdx, rsi; struct mkvparser::IMkvReader *
0x1800967ea  mov     rcx, r15; this
0x1800967ed  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x1800967f2  mov     ebx, eax
0x1800967f4  test    eax, eax
0x1800967f6  jns     loc_180096DB0
0x1800967fc  mov     rcx, rdi; this
0x1800967ff  call    ??_GColour@mkvparser@@QEAAPEAXI@Z; mkvparser::Colour::`scalar deleting destructor'(uint)
0x180096804  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009680b  test    rcx, rcx
0x18009680e  jnz     loc_180096E1D
0x180096814  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009681a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180096821  mov     rcx, rax
0x180096824  test    rax, rax
0x180096827  jz      loc_180096E0F
0x18009682d  mov     rax, [rax]
0x180096830  mov     edx, 7F0h
0x180096835  mov     rax, [rax+8]
0x180096839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009683e  test    eax, eax
0x180096840  jz      loc_180096E0F
0x180096846  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009684d  jmp     loc_180096E1D
0x180096852  cmp     rax, 55B3h
0x180096858  jnz     short loc_1800968CC
0x18009685a  lea     r9, [rdi+10h]; __int64
0x18009685e  mov     r8, r14; __int64
0x180096861  mov     rdx, rsi; struct mkvparser::IMkvReader *
0x180096864  mov     rcx, r15; this
0x180096867  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x18009686c  mov     ebx, eax
0x18009686e  test    eax, eax
0x180096870  jns     loc_180096DB0
0x180096876  mov     rcx, rdi; this
0x180096879  call    ??_GColour@mkvparser@@QEAAPEAXI@Z; mkvparser::Colour::`scalar deleting destructor'(uint)
0x18009687e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180096885  test    rcx, rcx
0x180096888  jnz     loc_180096E6D
0x18009688e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180096894  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009689b  mov     rcx, rax
0x18009689e  test    rax, rax
0x1800968a1  jz      loc_180096E5F
0x1800968a7  mov     rax, [rax]
0x1800968aa  mov     edx, 7F0h
0x1800968af  mov     rax, [rax+8]
0x1800968b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800968b8  test    eax, eax
0x1800968ba  jz      loc_180096E5F
0x1800968c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800968c7  jmp     loc_180096E6D
0x1800968cc  cmp     rax, 55B4h
0x1800968d2  jnz     short loc_180096946
0x1800968d4  lea     r9, [rdi+18h]; __int64
0x1800968d8  mov     r8, r14; __int64
0x1800968db  mov     rdx, rsi; struct mkvparser::IMkvReader *
0x1800968de  mov     rcx, r15; this
0x1800968e1  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x1800968e6  mov     ebx, eax
0x1800968e8  test    eax, eax
0x1800968ea  jns     loc_180096DB0
0x1800968f0  mov     rcx, rdi; this
0x1800968f3  call    ??_GColour@mkvparser@@QEAAPEAXI@Z; mkvparser::Colour::`scalar deleting destructor'(uint)
0x1800968f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800968ff  test    rcx, rcx
0x180096902  jnz     loc_180096EBD
0x180096908  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009690e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180096915  mov     rcx, rax
0x180096918  test    rax, rax
0x18009691b  jz      loc_180096EAF
0x180096921  mov     rax, [rax]
0x180096924  mov     edx, 7F0h
0x180096929  mov     rax, [rax+8]
0x18009692d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096932  test    eax, eax
0x180096934  jz      loc_180096EAF
0x18009693a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180096941  jmp     loc_180096EBD
0x180096946  cmp     rax, 55B5h
0x18009694c  jnz     short loc_1800969C0
0x18009694e  lea     r9, [rdi+20h]; __int64
0x180096952  mov     r8, r14; __int64
0x180096955  mov     rdx, rsi; struct mkvparser::IMkvReader *
0x180096958  mov     rcx, r15; this
0x18009695b  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x180096960  mov     ebx, eax
0x180096962  test    eax, eax
0x180096964  jns     loc_180096DB0
0x18009696a  mov     rcx, rdi; this
0x18009696d  call    ??_GColour@mkvparser@@QEAAPEAXI@Z; mkvparser::Colour::`scalar deleting destructor'(uint)
0x180096972  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180096979  test    rcx, rcx
0x18009697c  jnz     loc_180096F0D
0x180096982  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180096988  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
