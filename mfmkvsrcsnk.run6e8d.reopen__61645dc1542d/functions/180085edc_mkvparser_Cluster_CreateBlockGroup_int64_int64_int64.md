# mkvparser::Cluster::CreateBlockGroup(__int64,__int64,__int64)

- ea: `0x180085edc`
- end: `0x1800867e7`
- name: `?CreateBlockGroup@Cluster@mkvparser@@AEAAJ_J00@Z`
- size: `2315`
- prototype: `__int64 __fastcall(mkvparser ***this, struct mkvparser::IMkvReader *, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180085a08`

## callees

- `0x180002410`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x180085edc`
- `0x180094fcc`
- `0x1800a9220`
- `0x1800a96cc`
- `0x1800aa3d4`
- `0x1800aaa7c`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008600a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800860fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008618e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008621d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800862b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086340`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800863d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086481`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086533`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008666e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008672b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008600a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800860fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008618e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008621d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800862b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086340`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800863d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086481`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086533`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008666e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008672b`

## string_xrefs

- `0x180085f35`: `mkvparser::Cluster::CreateBlockGroup`
- `0x1800860c2`: `mkvparser::Cluster::CreateBlockGroup`
- `0x180086156`: `mkvparser::Cluster::CreateBlockGroup`
- `0x1800861e5`: `mkvparser::Cluster::CreateBlockGroup`
- `0x180086279`: `mkvparser::Cluster::CreateBlockGroup`
- `0x180086308`: `mkvparser::Cluster::CreateBlockGroup`
- `0x18008639c`: `mkvparser::Cluster::CreateBlockGroup`
- `0x18008642b`: `mkvparser::Cluster::CreateBlockGroup`
- `0x180086462`: `mkvparser::Cluster::CreateBlockGroup`
- `0x1800864dd`: `mkvparser::Cluster::CreateBlockGroup`
- `0x180086514`: `mkvparser::Cluster::CreateBlockGroup`
- `0x18008658f`: `mkvparser::Cluster::CreateBlockGroup`
- `0x18008663c`: `mkvparser::Cluster::CreateBlockGroup`
- `0x1800866ca`: `mkvparser::Cluster::CreateBlockGroup`
- `0x180086782`: `mkvparser::Cluster::CreateBlockGroup`

## pseudocode

```c
__int64 __fastcall mkvparser::Cluster::CreateBlockGroup(
        mkvparser ***this,
        struct mkvparser::IMkvReader *a2,
        __int64 a3,
        __int64 a4)
{
  mkvparser **v4; // rax
  struct mkvparser::IMkvReader *v5; // r12
  struct mkvparser::IMkvReader *v6; // rsi
  mkvparser *v8; // r13
  __int64 v9; // r15
  __int64 v10; // rdx
  int v11; // ebx
  __int64 v12; // r8
  __int64 v13; // r9
  struct mkvparser::IMkvReader *v14; // rsi
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  struct mkvparser::IMkvReader *v18; // r14
  __int64 v19; // rsi
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // r9
  __int64 *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  __int64 v63; // rbx
  mkvparser **v64; // r14
  __int64 v65; // rsi
  _QWORD *v66; // rax
  _QWORD *v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rdx
  __int64 v70; // r8
  __int64 v71; // r9
  mkvparser::BlockGroup *v72; // rcx
  __int64 *v73; // rcx
  CallStackTracing *v74; // rax
  struct CallStackContext *v75; // rax
  __int64 v76; // rdx
  __int64 v77; // r8
  __int64 v78; // r9
  mkvparser *v79; // rcx
  __int64 *v80; // rcx
  CallStackTracing *v81; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int *v84; // [rsp+20h] [rbp-38h]
  int *v85; // [rsp+20h] [rbp-38h]
  __int64 v86; // [rsp+30h] [rbp-28h] BYREF
  __int64 v87; // [rsp+38h] [rbp-20h]
  __int64 v88; // [rsp+40h] [rbp-18h]
  __int64 v89; // [rsp+48h] [rbp-10h] BYREF
  __int64 v90; // [rsp+A0h] [rbp+48h] BYREF
  __int64 v91; // [rsp+A8h] [rbp+50h] BYREF
  __int64 v92; // [rsp+B0h] [rbp+58h]
  __int64 v93; // [rsp+B8h] [rbp+60h]

  v93 = a4;
  v4 = *this;
  v5 = (struct mkvparser::IMkvReader *)((char *)a2 + a3);
  v87 = 1;
  v6 = a2;
  v88 = 0;
  v8 = *v4;
  v89 = -1;
  v9 = -1;
  v92 = -1;
  while ( 1 )
  {
    if ( (__int64)v6 >= (__int64)v5 )
    {
      if ( v6 == v5 )
      {
        if ( v9 >= 0 )
        {
          v63 = *((int *)this + 15);
          v64 = this[6];
          v65 = v63;
          v66 = operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
          v67 = v66;
          if ( v66 )
          {
            v66[1] = this;
            *((_DWORD *)v66 + 4) = v63;
            *v66 = &mkvparser::BlockGroup::`vftable';
            v66[4] = v92;
            v66[5] = -1;
            *((_WORD *)v66 + 24) = -1;
            *((_DWORD *)v66 + 16) = -1;
            v66[9] = v93;
            v68 = v87;
            v67[3] = v9;
            *((_BYTE *)v67 + 50) = 0;
            v67[7] = 0;
            v67[10] = v68;
            v67[11] = v88;
            v67[12] = v89;
          }
          else
          {
            v67 = 0;
          }
          v64[v63] = (mkvparser *)v67;
          CallStackScopeTrace::CallStackScopeTrace(
            (CallStackScopeTrace *)&v90,
            "mkvparser::Cluster::CreateBlockGroup",
            8036);
          v72 = v64[v63];
          if ( v72 )
          {
            v11 = mkvparser::BlockGroup::Parse(v72);
            if ( v11 >= 0 )
            {
              ++*((_DWORD *)this + 15);
              v11 = 0;
            }
            else
            {
              v79 = v64[v65];
              if ( v79 )
                (**(void (__fastcall ***)(mkvparser *, __int64))v79)(v79, 1);
              v80 = (__int64 *)CallStackTracing::s_wpInstance;
              v64[v65] = 0;
              if ( !v80 )
              {
                v81 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v76, v77, v78);
                CallStackTracing::s_wpInstance = v81;
                if ( v81
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v81 + 8LL))(v81, 2032) )
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
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v80);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "mkvparser::Cluster::CreateBlockGroup",
                    8044,
                    v11);
              }
              if ( g_wppLevels )
              {
                v32 = 729;
                goto LABEL_140;
              }
            }
          }
          else
          {
            v73 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v69, v70, v71);
              CallStackTracing::s_wpInstance = v74;
              if ( v74
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(v74, 2032) )
              {
                v73 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v73 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            v11 = -2147024882;
            if ( *((_BYTE *)v73 + 8) )
            {
              v75 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v73);
              if ( *((_DWORD *)v75 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v75, "mkvparser::Cluster::CreateBlockGroup", 8036, -2147024882);
            }
            if ( g_wppLevels )
            {
              v32 = 728;
              goto LABEL_140;
            }
          }
        }
        else
        {
          CallStackScopeTrace::CallStackScopeTrace(
            (CallStackScopeTrace *)&v90,
            "mkvparser::Cluster::CreateBlockGroup",
            8025);
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
          v11 = -1072875842;
          if ( *((_BYTE *)v60 + 8) )
          {
            v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
            if ( *((_DWORD *)v62 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v62, "mkvparser::Cluster::CreateBlockGroup", 8025, -1072875842);
          }
          if ( g_wppLevels )
          {
            v32 = 727;
            goto LABEL_140;
          }
        }
      }
      else
      {
        CallStackScopeTrace::CallStackScopeTrace(
          (CallStackScopeTrace *)&v90,
          "mkvparser::Cluster::CreateBlockGroup",
          8020);
        v54 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
          CallStackTracing::s_wpInstance = v55;
          if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
          {
            v54 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v54 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        v11 = -1072875842;
        if ( *((_BYTE *)v54 + 8) )
        {
          v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
          if ( *((_DWORD *)v56 + 499) != -1072875842 )
            CallStackContext::TraceFailure(v56, "mkvparser::Cluster::CreateBlockGroup", 8020, -1072875842);
        }
        if ( g_wppLevels )
        {
          v32 = 726;
          goto LABEL_140;
        }
      }
      goto LABEL_142;
    }
    v86 = 0;
    LODWORD(v91) = 0;
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v90, "mkvparser::Cluster::CreateBlockGroup", 7970);
    v11 = mkvparser::ReadID(v8, v6, (__int64)&v86, &v91, v84);
    if ( v11 < 0 )
    {
      v48 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v12, v13);
        CallStackTracing::s_wpInstance = v49;
        if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
        {
          v48 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v48 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v48 + 8) )
      {
        v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
        if ( *((_DWORD *)v50 + 499) != v11 )
          CallStackContext::TraceFailure(v50, "mkvparser::Cluster::CreateBlockGroup", 7970, v11);
      }
      if ( g_wppLevels )
      {
        v32 = 719;
        goto LABEL_140;
      }
      goto LABEL_142;
    }
    v14 = (struct mkvparser::IMkvReader *)((char *)v6 + (int)v91);
    if ( (__int64)v14 > (__int64)v5 )
    {
      v45 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v12, v13);
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
      v11 = -1072875842;
      if ( *((_BYTE *)v45 + 8) )
      {
        v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
        if ( *((_DWORD *)v47 + 499) != -1072875842 )
          CallStackContext::TraceFailure(v47, "mkvparser::Cluster::CreateBlockGroup", 7974, -1072875842);
      }
      if ( g_wppLevels )
      {
        v32 = 720;
        goto LABEL_140;
      }
      goto LABEL_142;
    }
    v90 = 0;
    v11 = mkvparser::ReadUInt(v8, v14, (__int64)&v90, &v91, v85);
    if ( v11 < 0 )
    {
      v42 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16, v17);
        CallStackTracing::s_wpInstance = v43;
        if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
        {
          v42 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v42 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v42 + 8) )
      {
        v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
        if ( *((_DWORD *)v44 + 499) != v11 )
          CallStackContext::TraceFailure(v44, "mkvparser::Cluster::CreateBlockGroup", 7980, v11);
      }
      if ( g_wppLevels )
      {
        v32 = 721;
        goto LABEL_140;
      }
      goto LABEL_142;
    }
    v18 = (struct mkvparser::IMkvReader *)((char *)v14 + (int)v91);
    v19 = v90;
    if ( v86 == 161 )
    {
      v20 = v92;
      v21 = (__int64)v18;
      if ( v9 >= 0 )
        v21 = v9;
      else
        v20 = v90;
      v92 = v20;
      v9 = v21;
      goto LABEL_24;
    }
    if ( v86 == 155 )
    {
      if ( v90 > 8 )
      {
        v33 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16, v17);
          CallStackTracing::s_wpInstance = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
          {
            v33 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v33 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        v11 = -1072875842;
        if ( *((_BYTE *)v33 + 8) )
        {
          v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
          if ( *((_DWORD *)v35 + 499) != -1072875842 )
            CallStackContext::TraceFailure(v35, "mkvparser::Cluster::CreateBlockGroup", 7994, -1072875842);
        }
        if ( !g_wppLevels )
          goto LABEL_142;
        v32 = 722;
      }
      else
      {
        v11 = mkvparser::UnserializeUInt(v8, v18, v90, (__int64)&v89, (__int64 *)v84);
        if ( v11 >= 0 )
          goto LABEL_24;
        v25 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( *((_DWORD *)v31 + 499) != v11 )
            CallStackContext::TraceFailure(v31, "mkvparser::Cluster::CreateBlockGroup", 7997, v11);
        }
        if ( !g_wppLevels )
          goto LABEL_142;
        v32 = 723;
      }
LABEL_140:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v32, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, this, v11);
      goto LABEL_142;
    }
    if ( v86 == 251 )
      break;
LABEL_24:
    v6 = (struct mkvparser::IMkvReader *)((char *)v18 + v19);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v90);
  }
  if ( (unsigned __int64)(v90 - 1) > 7 )
  {
    v39 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16, v17);
      CallStackTracing::s_wpInstance = v40;
      if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
      {
        v39 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v39 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    v11 = -1072875842;
    if ( *((_BYTE *)v39 + 8) )
    {
      v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
      if ( *((_DWORD *)v41 + 499) != -1072875842 )
        CallStackContext::TraceFailure(v41, "mkvparser::Cluster::CreateBlockGroup", 8001, -1072875842);
    }
    if ( g_wppLevels )
    {
      v32 = 724;
      goto LABEL_140;
    }
    goto LABEL_142;
  }
  v27 = (int)v90;
  v90 = 0;
  v11 = mkvparser::UnserializeInt(v8, v18, v27, (__int64)&v90, (__int64 *)v84);
  if ( v11 >= 0 )
  {
    if ( v90 > 0 )
      v88 = v90;
    else
      v87 = v90;
    goto LABEL_24;
  }
  v36 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
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
  if ( *((_BYTE *)v36 + 8) )
  {
    v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
    if ( *((_DWORD *)v38 + 499) != v11 )
      CallStackContext::TraceFailure(v38, "mkvparser::Cluster::CreateBlockGroup", 8007, v11);
  }
  if ( g_wppLevels )
  {
    v32 = 725;
    goto LABEL_140;
  }
LABEL_142:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v90);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180085edc  mov     [rsp-40h+arg_18], r9
0x180085ee1  push    rbp
0x180085ee2  push    rbx
0x180085ee3  push    rsi
0x180085ee4  push    rdi
0x180085ee5  push    r12
0x180085ee7  push    r13
0x180085ee9  push    r14
0x180085eeb  push    r15
0x180085eed  mov     rbp, rsp
0x180085ef0  sub     rsp, 58h
0x180085ef4  mov     rax, [rcx]
0x180085ef7  lea     r12, [rdx+r8]
0x180085efb  xor     r14d, r14d
0x180085efe  mov     [rbp+var_20], 1
0x180085f06  mov     rsi, rdx
0x180085f09  mov     [rbp+var_18], r14
0x180085f0d  mov     rdi, rcx
0x180085f10  mov     r13, [rax]
0x180085f13  or      rax, 0FFFFFFFFFFFFFFFFh
0x180085f17  mov     [rbp+var_10], rax
0x180085f1b  mov     r15, rax
0x180085f1e  mov     [rbp+arg_10], rax
0x180085f22  cmp     rsi, r12
0x180085f25  jge     loc_180086457
0x180085f2b  mov     r8d, 1F22h; int
0x180085f31  mov     [rbp+var_28], r14
0x180085f35  lea     rdx, aMkvparserClust_6; "mkvparser::Cluster::CreateBlockGroup"
0x180085f3c  mov     dword ptr [rbp+arg_8], r14d
0x180085f40  lea     rcx, [rbp+arg_0]; this
0x180085f44  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180085f49  lea     r9, [rbp+arg_8]; __int64 *
0x180085f4d  mov     rdx, rsi; struct mkvparser::IMkvReader *
0x180085f50  lea     r8, [rbp+var_28]; __int64
0x180085f54  mov     rcx, r13; this
0x180085f57  call    ?ReadID@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadID(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x180085f5c  mov     ebx, eax
0x180085f5e  test    eax, eax
0x180085f60  js      loc_1800863C8
0x180085f66  movsxd  rax, dword ptr [rbp+arg_8]
0x180085f6a  add     rsi, rax
0x180085f6d  cmp     rsi, r12
0x180085f70  jg      loc_180086334
0x180085f76  lea     r9, [rbp+arg_8]; __int64 *
0x180085f7a  mov     [rbp+arg_0], r14
0x180085f7e  lea     r8, [rbp+arg_0]; __int64
0x180085f82  mov     rdx, rsi; struct mkvparser::IMkvReader *
0x180085f85  mov     rcx, r13; this
0x180085f88  call    ?ReadUInt@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadUInt(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x180085f8d  mov     ebx, eax
0x180085f8f  test    eax, eax
0x180085f91  js      loc_1800862A5
0x180085f97  movsxd  r14, dword ptr [rbp+arg_8]
0x180085f9b  mov     rax, [rbp+var_28]
0x180085f9f  add     r14, rsi
0x180085fa2  mov     rsi, [rbp+arg_0]
0x180085fa6  cmp     rax, 0A1h
0x180085fac  jnz     short loc_180085FCC
0x180085fae  mov     rbx, [rbp+arg_10]
0x180085fb2  test    r15, r15
0x180085fb5  mov     rax, r14
0x180085fb8  cmovs   rbx, rsi
0x180085fbc  cmovns  rax, r15
0x180085fc0  mov     [rbp+arg_10], rbx
0x180085fc4  mov     r15, rax
0x180085fc7  jmp     loc_18008608A
0x180085fcc  cmp     rax, 9Bh
0x180085fd2  jnz     short loc_18008603D
0x180085fd4  cmp     rsi, 8
0x180085fd8  jg      loc_1800860EE
0x180085fde  lea     r9, [rbp+var_10]; __int64
0x180085fe2  mov     r8, rsi; __int64
0x180085fe5  mov     rdx, r14; struct mkvparser::IMkvReader *
0x180085fe8  mov     rcx, r13; this
0x180085feb  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x180085ff0  mov     ebx, eax
0x180085ff2  test    eax, eax
0x180085ff4  jns     loc_18008608A
0x180085ffa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086001  test    rcx, rcx
0x180086004  jnz     loc_1800860AC
0x18008600a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180086010  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180086017  mov     rcx, rax
0x18008601a  test    rax, rax
0x18008601d  jz      short loc_18008609E
0x18008601f  mov     rax, [rax]
0x180086022  mov     edx, 7F0h
0x180086027  mov     rax, [rax+8]
0x18008602b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086030  test    eax, eax
0x180086032  jz      short loc_18008609E
0x180086034  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008603b  jmp     short loc_1800860AC
0x18008603d  cmp     rax, 0FBh
0x180086043  jnz     short loc_18008608A
0x180086045  lea     rax, [rsi-1]
0x180086049  cmp     rax, 7
0x18008604d  ja      loc_180086211
0x180086053  movsxd  r8, esi; __int64
0x180086056  lea     r9, [rbp+arg_0]; __int64
0x18008605a  mov     rdx, r14; struct mkvparser::IMkvReader *
0x18008605d  mov     [rbp+arg_0], 0
0x180086065  mov     rcx, r13; this
0x180086068  call    ?UnserializeInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x18008606d  mov     ebx, eax
0x18008606f  test    eax, eax
0x180086071  js      loc_180086182
0x180086077  mov     rax, [rbp+arg_0]
0x18008607b  test    rax, rax
0x18008607e  jg      short loc_180086086
0x180086080  mov     [rbp+var_20], rax
0x180086084  jmp     short loc_18008608A
0x180086086  mov     [rbp+var_18], rax
0x18008608a  lea     rcx, [rbp+arg_0]; this
0x18008608e  add     rsi, r14
0x180086091  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180086096  xor     r14d, r14d
0x180086099  jmp     loc_180085F22
0x18008609e  lea     rcx, qword_1800D6F70; this
0x1800860a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800860ac  cmp     byte ptr [rcx+8], 0
0x1800860b0  jz      short loc_1800860D7
0x1800860b2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800860b7  cmp     [rax+7CCh], ebx
0x1800860bd  jz      short loc_1800860D7
0x1800860bf  mov     r9d, ebx; int
0x1800860c2  lea     rdx, aMkvparserClust_6; "mkvparser::Cluster::CreateBlockGroup"
0x1800860c9  mov     r8d, 1F3Dh; int
0x1800860cf  mov     rcx, rax; this
0x1800860d2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800860d7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800860de  jb      loc_1800867CB
0x1800860e4  mov     edx, 2D3h
0x1800860e9  jmp     loc_1800867A5
0x1800860ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800860f5  test    rcx, rcx
0x1800860f8  jnz     short loc_18008613B
0x1800860fa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180086100  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180086107  mov     rcx, rax
0x18008610a  test    rax, rax
0x18008610d  jz      short loc_18008612D
0x18008610f  mov     rax, [rax]
0x180086112  mov     edx, 7F0h
0x180086117  mov     rax, [rax+8]
0x18008611b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086120  test    eax, eax
0x180086122  jz      short loc_18008612D
0x180086124  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008612b  jmp     short loc_18008613B
0x18008612d  lea     rcx, qword_1800D6F70; this
0x180086134  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008613b  cmp     byte ptr [rcx+8], 0
0x18008613f  mov     ebx, 0C00D36BEh
0x180086144  jz      short loc_18008616B
0x180086146  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008614b  cmp     [rax+7CCh], ebx
0x180086151  jz      short loc_18008616B
0x180086153  mov     r9d, ebx; int
0x180086156  lea     rdx, aMkvparserClust_6; "mkvparser::Cluster::CreateBlockGroup"
0x18008615d  mov     r8d, 1F3Ah; int
0x180086163  mov     rcx, rax; this
0x180086166  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008616b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180086172  jb      loc_1800867CB
0x180086178  mov     edx, 2D2h
0x18008617d  jmp     loc_1800867A5
0x180086182  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086189  test    rcx, rcx
0x18008618c  jnz     short loc_1800861CF
0x18008618e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180086194  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008619b  mov     rcx, rax
0x18008619e  test    rax, rax
0x1800861a1  jz      short loc_1800861C1
0x1800861a3  mov     rax, [rax]
0x1800861a6  mov     edx, 7F0h
0x1800861ab  mov     rax, [rax+8]
0x1800861af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800861b4  test    eax, eax
0x1800861b6  jz      short loc_1800861C1
0x1800861b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800861bf  jmp     short loc_1800861CF
0x1800861c1  lea     rcx, qword_1800D6F70; this
0x1800861c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800861cf  cmp     byte ptr [rcx+8], 0
0x1800861d3  jz      short loc_1800861FA
0x1800861d5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800861da  cmp     [rax+7CCh], ebx
0x1800861e0  jz      short loc_1800861FA
0x1800861e2  mov     r9d, ebx; int
0x1800861e5  lea     rdx, aMkvparserClust_6; "mkvparser::Cluster::CreateBlockGroup"
0x1800861ec  mov     r8d, 1F47h; int
0x1800861f2  mov     rcx, rax; this
0x1800861f5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800861fa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180086201  jb      loc_1800867CB
0x180086207  mov     edx, 2D5h
0x18008620c  jmp     loc_1800867A5
0x180086211  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086218  test    rcx, rcx
0x18008621b  jnz     short loc_18008625E
0x18008621d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180086223  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008622a  mov     rcx, rax
0x18008622d  test    rax, rax
0x180086230  jz      short loc_180086250
0x180086232  mov     rax, [rax]
0x180086235  mov     edx, 7F0h
0x18008623a  mov     rax, [rax+8]
0x18008623e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086243  test    eax, eax
0x180086245  jz      short loc_180086250
0x180086247  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008624e  jmp     short loc_18008625E
0x180086250  lea     rcx, qword_1800D6F70; this
0x180086257  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008625e  cmp     byte ptr [rcx+8], 0
0x180086262  mov     ebx, 0C00D36BEh
0x180086267  jz      short loc_18008628E
0x180086269  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008626e  cmp     [rax+7CCh], ebx
0x180086274  jz      short loc_18008628E
0x180086276  mov     r9d, ebx; int
0x180086279  lea     rdx, aMkvparserClust_6; "mkvparser::Cluster::CreateBlockGroup"
0x180086280  mov     r8d, 1F41h; int
0x180086286  mov     rcx, rax; this
0x180086289  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008628e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180086295  jb      loc_1800867CB
0x18008629b  mov     edx, 2D4h
0x1800862a0  jmp     loc_1800867A5
0x1800862a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800862ac  test    rcx, rcx
0x1800862af  jnz     short loc_1800862F2
0x1800862b1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800862b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800862be  mov     rcx, rax
0x1800862c1  test    rax, rax
0x1800862c4  jz      short loc_1800862E4
0x1800862c6  mov     rax, [rax]
0x1800862c9  mov     edx, 7F0h
0x1800862ce  mov     rax, [rax+8]
0x1800862d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800862d7  test    eax, eax
0x1800862d9  jz      short loc_1800862E4
0x1800862db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800862e2  jmp     short loc_1800862F2
0x1800862e4  lea     rcx, qword_1800D6F70; this
0x1800862eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800862f2  cmp     [rcx+8], r14b
0x1800862f6  jz      short loc_18008631D
0x1800862f8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800862fd  cmp     [rax+7CCh], ebx
0x180086303  jz      short loc_18008631D
0x180086305  mov     r9d, ebx; int
0x180086308  lea     rdx, aMkvparserClust_6; "mkvparser::Cluster::CreateBlockGroup"
0x18008630f  mov     r8d, 1F2Ch; int
0x180086315  mov     rcx, rax; this
0x180086318  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008631d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180086324  jb      loc_1800867CB
0x18008632a  mov     edx, 2D1h
0x18008632f  jmp     loc_1800867A5
0x180086334  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008633b  test    rcx, rcx
0x18008633e  jnz     short loc_180086381
0x180086340  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180086346  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008634d  mov     rcx, rax
0x180086350  test    rax, rax
0x180086353  jz      short loc_180086373
0x180086355  mov     rax, [rax]
0x180086358  mov     edx, 7F0h
0x18008635d  mov     rax, [rax+8]
0x180086361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086366  test    eax, eax
0x180086368  jz      short loc_180086373
0x18008636a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086371  jmp     short loc_180086381
0x180086373  lea     rcx, qword_1800D6F70; this
0x18008637a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180086381  mov     ebx, 0C00D36BEh
0x180086386  cmp     [rcx+8], r14b
0x18008638a  jz      short loc_1800863B1
0x18008638c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180086391  cmp     [rax+7CCh], ebx
0x180086397  jz      short loc_1800863B1
0x180086399  mov     r9d, ebx; int
0x18008639c  lea     rdx, aMkvparserClust_6; "mkvparser::Cluster::CreateBlockGroup"
0x1800863a3  mov     r8d, 1F26h; int
0x1800863a9  mov     rcx, rax; this
0x1800863ac  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800863b1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800863b8  jb      loc_1800867CB
0x1800863be  mov     edx, 2D0h
0x1800863c3  jmp     loc_1800867A5
0x1800863c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800863cf  test    rcx, rcx
  ... truncated ...
```
