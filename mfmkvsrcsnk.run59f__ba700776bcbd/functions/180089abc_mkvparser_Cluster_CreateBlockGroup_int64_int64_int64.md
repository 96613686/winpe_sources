# mkvparser::Cluster::CreateBlockGroup(__int64,__int64,__int64)

- ea: `0x180089abc`
- end: `0x18008a40a`
- name: `?CreateBlockGroup@Cluster@mkvparser@@AEAAJ_J00@Z`
- size: `2382`
- prototype: `int(mkvparser::Cluster *__hidden this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1800895cc`

## callees

- `0x180002430`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x180089abc`
- `0x1800992cc`
- `0x1800adea8`
- `0x1800ae378`
- `0x1800af0d4`
- `0x1800af7b0`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089bea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089ce0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089d7a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089e0f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089ea9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089f3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089fd8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a08b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a143`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a284`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a347`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089bea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089ce0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089d7a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089e0f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089ea9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089f3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089fd8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a08b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a143`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a284`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a347`

## string_xrefs

- `0x180089b15`: `mkvparser::Cluster::CreateBlockGroup`
- `0x180089ca8`: `mkvparser::Cluster::CreateBlockGroup`
- `0x180089d42`: `mkvparser::Cluster::CreateBlockGroup`
- `0x180089dd7`: `mkvparser::Cluster::CreateBlockGroup`
- `0x180089e71`: `mkvparser::Cluster::CreateBlockGroup`
- `0x180089f06`: `mkvparser::Cluster::CreateBlockGroup`
- `0x180089fa0`: `mkvparser::Cluster::CreateBlockGroup`
- `0x18008a035`: `mkvparser::Cluster::CreateBlockGroup`
- `0x18008a06c`: `mkvparser::Cluster::CreateBlockGroup`
- `0x18008a0ed`: `mkvparser::Cluster::CreateBlockGroup`
- `0x18008a124`: `mkvparser::Cluster::CreateBlockGroup`
- `0x18008a1a5`: `mkvparser::Cluster::CreateBlockGroup`
- `0x18008a252`: `mkvparser::Cluster::CreateBlockGroup`
- `0x18008a2e6`: `mkvparser::Cluster::CreateBlockGroup`
- `0x18008a3a4`: `mkvparser::Cluster::CreateBlockGroup`

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
                  v80 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                v73 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v60 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v54 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v48 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v45 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v42 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v33 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v25 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v32, &WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, this, v11);
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
        v39 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      v36 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180089abc  mov     [rsp-40h+arg_18], r9
0x180089ac1  push    rbp
0x180089ac2  push    rbx
0x180089ac3  push    rsi
0x180089ac4  push    rdi
0x180089ac5  push    r12
0x180089ac7  push    r13
0x180089ac9  push    r14
0x180089acb  push    r15
0x180089acd  mov     rbp, rsp
0x180089ad0  sub     rsp, 58h
0x180089ad4  mov     rax, [rcx]
0x180089ad7  lea     r12, [rdx+r8]
0x180089adb  xor     r14d, r14d
0x180089ade  mov     [rbp+var_20], 1
0x180089ae6  mov     rsi, rdx
0x180089ae9  mov     [rbp+var_18], r14
0x180089aed  mov     rdi, rcx
0x180089af0  mov     r13, [rax]
0x180089af3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180089af7  mov     [rbp+var_10], rax
0x180089afb  mov     r15, rax
0x180089afe  mov     [rbp+arg_10], rax
0x180089b02  cmp     rsi, r12
0x180089b05  jge     loc_18008A061
0x180089b0b  mov     r8d, 1F22h; int
0x180089b11  mov     [rbp+var_28], r14
0x180089b15  lea     rdx, aMkvparserClust_6; "mkvparser::Cluster::CreateBlockGroup"
0x180089b1c  mov     dword ptr [rbp+arg_8], r14d
0x180089b20  lea     rcx, [rbp+arg_0]; this
0x180089b24  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180089b29  lea     r9, [rbp+arg_8]; __int64 *
0x180089b2d  mov     rdx, rsi; struct mkvparser::IMkvReader *
0x180089b30  lea     r8, [rbp+var_28]; __int64
0x180089b34  mov     rcx, r13; this
0x180089b37  call    ?ReadID@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadID(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x180089b3c  mov     ebx, eax
0x180089b3e  test    eax, eax
0x180089b40  js      loc_180089FCC
0x180089b46  movsxd  rax, dword ptr [rbp+arg_8]
0x180089b4a  add     rsi, rax
0x180089b4d  cmp     rsi, r12
0x180089b50  jg      loc_180089F32
0x180089b56  lea     r9, [rbp+arg_8]; __int64 *
0x180089b5a  mov     [rbp+arg_0], r14
0x180089b5e  lea     r8, [rbp+arg_0]; __int64
0x180089b62  mov     rdx, rsi; struct mkvparser::IMkvReader *
0x180089b65  mov     rcx, r13; this
0x180089b68  call    ?ReadUInt@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadUInt(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x180089b6d  mov     ebx, eax
0x180089b6f  test    eax, eax
0x180089b71  js      loc_180089E9D
0x180089b77  movsxd  r14, dword ptr [rbp+arg_8]
0x180089b7b  mov     rax, [rbp+var_28]
0x180089b7f  add     r14, rsi
0x180089b82  mov     rsi, [rbp+arg_0]
0x180089b86  cmp     rax, 0A1h
0x180089b8c  jnz     short loc_180089BAC
0x180089b8e  mov     rbx, [rbp+arg_10]
0x180089b92  test    r15, r15
0x180089b95  mov     rax, r14
0x180089b98  cmovs   rbx, rsi
0x180089b9c  cmovns  rax, r15
0x180089ba0  mov     [rbp+arg_10], rbx
0x180089ba4  mov     r15, rax
0x180089ba7  jmp     loc_180089C70
0x180089bac  cmp     rax, 9Bh
0x180089bb2  jnz     short loc_180089C23
0x180089bb4  cmp     rsi, 8
0x180089bb8  jg      loc_180089CD4
0x180089bbe  lea     r9, [rbp+var_10]; __int64
0x180089bc2  mov     r8, rsi; __int64
0x180089bc5  mov     rdx, r14; struct mkvparser::IMkvReader *
0x180089bc8  mov     rcx, r13; this
0x180089bcb  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x180089bd0  mov     ebx, eax
0x180089bd2  test    eax, eax
0x180089bd4  jns     loc_180089C70
0x180089bda  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089be1  test    rcx, rcx
0x180089be4  jnz     loc_180089C92
0x180089bea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089bf1  nop     dword ptr [rax+rax+00h]
0x180089bf6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089bfd  mov     rcx, rax
0x180089c00  test    rax, rax
0x180089c03  jz      short loc_180089C84
0x180089c05  mov     rax, [rax]
0x180089c08  mov     edx, 7F0h
0x180089c0d  mov     rax, [rax+8]
0x180089c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089c16  test    eax, eax
0x180089c18  jz      short loc_180089C84
0x180089c1a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089c21  jmp     short loc_180089C92
0x180089c23  cmp     rax, 0FBh
0x180089c29  jnz     short loc_180089C70
0x180089c2b  lea     rax, [rsi-1]
0x180089c2f  cmp     rax, 7
0x180089c33  ja      loc_180089E03
0x180089c39  movsxd  r8, esi; __int64
0x180089c3c  lea     r9, [rbp+arg_0]; __int64
0x180089c40  mov     rdx, r14; struct mkvparser::IMkvReader *
0x180089c43  mov     [rbp+arg_0], 0
0x180089c4b  mov     rcx, r13; this
0x180089c4e  call    ?UnserializeInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x180089c53  mov     ebx, eax
0x180089c55  test    eax, eax
0x180089c57  js      loc_180089D6E
0x180089c5d  mov     rax, [rbp+arg_0]
0x180089c61  test    rax, rax
0x180089c64  jg      short loc_180089C6C
0x180089c66  mov     [rbp+var_20], rax
0x180089c6a  jmp     short loc_180089C70
0x180089c6c  mov     [rbp+var_18], rax
0x180089c70  lea     rcx, [rbp+arg_0]; this
0x180089c74  add     rsi, r14
0x180089c77  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180089c7c  xor     r14d, r14d
0x180089c7f  jmp     loc_180089B02
0x180089c84  lea     rcx, qword_1800DBF70; this
0x180089c8b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089c92  cmp     byte ptr [rcx+8], 0
0x180089c96  jz      short loc_180089CBD
0x180089c98  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089c9d  cmp     [rax+7CCh], ebx
0x180089ca3  jz      short loc_180089CBD
0x180089ca5  mov     r9d, ebx; int
0x180089ca8  lea     rdx, aMkvparserClust_6; "mkvparser::Cluster::CreateBlockGroup"
0x180089caf  mov     r8d, 1F3Dh; int
0x180089cb5  mov     rcx, rax; this
0x180089cb8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180089cbd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180089cc4  jb      loc_18008A3ED
0x180089cca  mov     edx, 2D3h
0x180089ccf  jmp     loc_18008A3C7
0x180089cd4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089cdb  test    rcx, rcx
0x180089cde  jnz     short loc_180089D27
0x180089ce0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089ce7  nop     dword ptr [rax+rax+00h]
0x180089cec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089cf3  mov     rcx, rax
0x180089cf6  test    rax, rax
0x180089cf9  jz      short loc_180089D19
0x180089cfb  mov     rax, [rax]
0x180089cfe  mov     edx, 7F0h
0x180089d03  mov     rax, [rax+8]
0x180089d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089d0c  test    eax, eax
0x180089d0e  jz      short loc_180089D19
0x180089d10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089d17  jmp     short loc_180089D27
0x180089d19  lea     rcx, qword_1800DBF70; this
0x180089d20  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089d27  cmp     byte ptr [rcx+8], 0
0x180089d2b  mov     ebx, 0C00D36BEh
0x180089d30  jz      short loc_180089D57
0x180089d32  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089d37  cmp     [rax+7CCh], ebx
0x180089d3d  jz      short loc_180089D57
0x180089d3f  mov     r9d, ebx; int
0x180089d42  lea     rdx, aMkvparserClust_6; "mkvparser::Cluster::CreateBlockGroup"
0x180089d49  mov     r8d, 1F3Ah; int
0x180089d4f  mov     rcx, rax; this
0x180089d52  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180089d57  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180089d5e  jb      loc_18008A3ED
0x180089d64  mov     edx, 2D2h
0x180089d69  jmp     loc_18008A3C7
0x180089d6e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089d75  test    rcx, rcx
0x180089d78  jnz     short loc_180089DC1
0x180089d7a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089d81  nop     dword ptr [rax+rax+00h]
0x180089d86  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089d8d  mov     rcx, rax
0x180089d90  test    rax, rax
0x180089d93  jz      short loc_180089DB3
0x180089d95  mov     rax, [rax]
0x180089d98  mov     edx, 7F0h
0x180089d9d  mov     rax, [rax+8]
0x180089da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089da6  test    eax, eax
0x180089da8  jz      short loc_180089DB3
0x180089daa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089db1  jmp     short loc_180089DC1
0x180089db3  lea     rcx, qword_1800DBF70; this
0x180089dba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089dc1  cmp     byte ptr [rcx+8], 0
0x180089dc5  jz      short loc_180089DEC
0x180089dc7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089dcc  cmp     [rax+7CCh], ebx
0x180089dd2  jz      short loc_180089DEC
0x180089dd4  mov     r9d, ebx; int
0x180089dd7  lea     rdx, aMkvparserClust_6; "mkvparser::Cluster::CreateBlockGroup"
0x180089dde  mov     r8d, 1F47h; int
0x180089de4  mov     rcx, rax; this
0x180089de7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180089dec  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180089df3  jb      loc_18008A3ED
0x180089df9  mov     edx, 2D5h
0x180089dfe  jmp     loc_18008A3C7
0x180089e03  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089e0a  test    rcx, rcx
0x180089e0d  jnz     short loc_180089E56
0x180089e0f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089e16  nop     dword ptr [rax+rax+00h]
0x180089e1b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089e22  mov     rcx, rax
0x180089e25  test    rax, rax
0x180089e28  jz      short loc_180089E48
0x180089e2a  mov     rax, [rax]
0x180089e2d  mov     edx, 7F0h
0x180089e32  mov     rax, [rax+8]
0x180089e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089e3b  test    eax, eax
0x180089e3d  jz      short loc_180089E48
0x180089e3f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089e46  jmp     short loc_180089E56
0x180089e48  lea     rcx, qword_1800DBF70; this
0x180089e4f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089e56  cmp     byte ptr [rcx+8], 0
0x180089e5a  mov     ebx, 0C00D36BEh
0x180089e5f  jz      short loc_180089E86
0x180089e61  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089e66  cmp     [rax+7CCh], ebx
0x180089e6c  jz      short loc_180089E86
0x180089e6e  mov     r9d, ebx; int
0x180089e71  lea     rdx, aMkvparserClust_6; "mkvparser::Cluster::CreateBlockGroup"
0x180089e78  mov     r8d, 1F41h; int
0x180089e7e  mov     rcx, rax; this
0x180089e81  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180089e86  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180089e8d  jb      loc_18008A3ED
0x180089e93  mov     edx, 2D4h
0x180089e98  jmp     loc_18008A3C7
0x180089e9d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089ea4  test    rcx, rcx
0x180089ea7  jnz     short loc_180089EF0
0x180089ea9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089eb0  nop     dword ptr [rax+rax+00h]
0x180089eb5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089ebc  mov     rcx, rax
0x180089ebf  test    rax, rax
0x180089ec2  jz      short loc_180089EE2
0x180089ec4  mov     rax, [rax]
0x180089ec7  mov     edx, 7F0h
0x180089ecc  mov     rax, [rax+8]
0x180089ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089ed5  test    eax, eax
0x180089ed7  jz      short loc_180089EE2
0x180089ed9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089ee0  jmp     short loc_180089EF0
0x180089ee2  lea     rcx, qword_1800DBF70; this
0x180089ee9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089ef0  cmp     [rcx+8], r14b
0x180089ef4  jz      short loc_180089F1B
0x180089ef6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089efb  cmp     [rax+7CCh], ebx
0x180089f01  jz      short loc_180089F1B
0x180089f03  mov     r9d, ebx; int
0x180089f06  lea     rdx, aMkvparserClust_6; "mkvparser::Cluster::CreateBlockGroup"
0x180089f0d  mov     r8d, 1F2Ch; int
0x180089f13  mov     rcx, rax; this
0x180089f16  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180089f1b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180089f22  jb      loc_18008A3ED
0x180089f28  mov     edx, 2D1h
0x180089f2d  jmp     loc_18008A3C7
0x180089f32  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089f39  test    rcx, rcx
0x180089f3c  jnz     short loc_180089F85
0x180089f3e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089f45  nop     dword ptr [rax+rax+00h]
0x180089f4a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089f51  mov     rcx, rax
0x180089f54  test    rax, rax
0x180089f57  jz      short loc_180089F77
0x180089f59  mov     rax, [rax]
0x180089f5c  mov     edx, 7F0h
0x180089f61  mov     rax, [rax+8]
0x180089f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089f6a  test    eax, eax
0x180089f6c  jz      short loc_180089F77
0x180089f6e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089f75  jmp     short loc_180089F85
0x180089f77  lea     rcx, qword_1800DBF70; this
0x180089f7e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089f85  mov     ebx, 0C00D36BEh
0x180089f8a  cmp     [rcx+8], r14b
0x180089f8e  jz      short loc_180089FB5
0x180089f90  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089f95  cmp     [rax+7CCh], ebx
0x180089f9b  jz      short loc_180089FB5
0x180089f9d  mov     r9d, ebx; int
0x180089fa0  lea     rdx, aMkvparserClust_6; "mkvparser::Cluster::CreateBlockGroup"
0x180089fa7  mov     r8d, 1F26h; int
0x180089fad  mov     rcx, rax; this
0x180089fb0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
  ... truncated ...
```
