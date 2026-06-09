# mkvparser::CuePoint::Load(mkvparser::IMkvReader *)

- ea: `0x180092f5c`
- end: `0x180093bab`
- name: `?Load@CuePoint@mkvparser@@QEAAJPEAUIMkvReader@2@@Z`
- size: `3151`
- prototype: `int(mkvparser::CuePoint *__hidden this, struct mkvparser::IMkvReader *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800950f0`

## callees

- `0x180003760`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x180092f5c`
- `0x1800a0088`
- `0x1800adea8`
- `0x1800ae378`
- `0x1800af7b0`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180092fdf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009307b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093135`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093286`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093344`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800933de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093478`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009350d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800935a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009365f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093740`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093874`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093909`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009399e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093a38`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093af1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180092fdf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009307b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093135`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093286`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093344`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800933de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093478`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009350d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800935a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009365f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093740`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093874`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093909`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009399e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093a38`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093af1`

## pseudocode

```c
__int64 __fastcall mkvparser::CuePoint::Load(
        mkvparser::CuePoint *this,
        __int64 (__fastcall ***a2)(mkvparser *, struct mkvparser::IMkvReader *, __int64, unsigned __int8 *))
{
  __int64 v2; // r15
  struct mkvparser::IMkvReader *v6; // r15
  __int64 v7; // rdx
  int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  struct mkvparser::IMkvReader *v18; // rsi
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  struct mkvparser::IMkvReader *v25; // r14
  struct mkvparser::IMkvReader *v26; // rsi
  struct mkvparser::IMkvReader *v27; // r13
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  struct mkvparser::IMkvReader *v31; // r13
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  struct mkvparser::IMkvReader *v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  __int64 v41; // rax
  struct CallStackContext *v42; // rax
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  unsigned __int64 v64; // rax
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 v67; // r9
  mkvparser::CuePoint::TrackPosition *v68; // r13
  __int64 *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // r9
  struct mkvparser::IMkvReader *v75; // r14
  struct mkvparser::IMkvReader *v76; // r14
  __int64 *v77; // rcx
  CallStackTracing *v78; // rax
  struct CallStackContext *v79; // rax
  __int64 *v80; // rcx
  CallStackTracing *v81; // rax
  struct CallStackContext *v82; // rax
  __int64 *v83; // rcx
  CallStackTracing *v84; // rax
  struct CallStackContext *v85; // rax
  __int64 *v86; // rcx
  CallStackTracing *v87; // rax
  struct CallStackContext *v88; // rax
  __int64 *v89; // rcx
  CallStackTracing *v90; // rax
  struct CallStackContext *v91; // rax
  __int64 *v92; // [rsp+20h] [rbp-20h]
  __int64 v93[2]; // [rsp+30h] [rbp-10h] BYREF
  char v94; // [rsp+80h] [rbp+40h] BYREF
  __int64 v95; // [rsp+90h] [rbp+50h] BYREF
  __int64 v96; // [rsp+98h] [rbp+58h] BYREF

  v2 = *((_QWORD *)this + 3);
  if ( v2 >= 0 )
    return 0;
  v96 = 0;
  LODWORD(v95) = 0;
  v93[0] = 0;
  v6 = (struct mkvparser::IMkvReader *)-v2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v94, "mkvparser::CuePoint::Load", 2783);
  v8 = mkvparser::ReadID(a2, v6, &v96, &v95);
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
        CallStackContext::TraceFailure(ThreadRelativeContext, "mkvparser::CuePoint::Load", 2783, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_195;
    v14 = 254;
    goto LABEL_182;
  }
  if ( v96 != 187 )
  {
    v15 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v9, v10);
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
    v8 = -1072875842;
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)v17 + 499) != -1072875842 )
        CallStackContext::TraceFailure(v17, "mkvparser::CuePoint::Load", 2787, -1072875842);
    }
    if ( !g_wppLevels )
      goto LABEL_195;
    v14 = 255;
    goto LABEL_182;
  }
  v18 = (struct mkvparser::IMkvReader *)((char *)v6 + (int)v95);
  v8 = mkvparser::ReadUInt(a2, v18, v93, &v95);
  if ( v8 >= 0 )
  {
    v25 = (struct mkvparser::IMkvReader *)((char *)v18 + (int)v95);
    v26 = (struct mkvparser::IMkvReader *)((char *)v25 + v93[0]);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v94);
    v27 = v25;
    while ( (__int64)v27 < (__int64)v26 )
    {
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v94, "mkvparser::CuePoint::Load", 2807);
      v8 = mkvparser::ReadID(a2, v27, &v96, &v95);
      if ( v8 < 0 )
      {
        v55 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
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
          v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
          if ( *((_DWORD *)v57 + 499) != v8 )
            CallStackContext::TraceFailure(v57, "mkvparser::CuePoint::Load", 2807, v8);
        }
        if ( g_wppLevels )
        {
          v14 = 257;
          goto LABEL_182;
        }
        goto LABEL_195;
      }
      v31 = (struct mkvparser::IMkvReader *)((char *)v27 + (int)v95);
      if ( (__int64)v31 > (__int64)v26 )
      {
        v52 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
          CallStackTracing::s_wpInstance = v53;
          if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
          {
            v52 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v52 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        v8 = -1072875842;
        if ( *((_BYTE *)v52 + 8) )
        {
          v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
          if ( *((_DWORD *)v54 + 499) != -1072875842 )
            CallStackContext::TraceFailure(v54, "mkvparser::CuePoint::Load", 2811, -1072875842);
        }
        if ( g_wppLevels )
        {
          v14 = 258;
          goto LABEL_182;
        }
        goto LABEL_195;
      }
      v8 = mkvparser::ReadUInt(a2, v31, v93, &v95);
      if ( v8 < 0 )
      {
        v49 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
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
            CallStackContext::TraceFailure(v51, "mkvparser::CuePoint::Load", 2816, v8);
        }
        if ( g_wppLevels )
        {
          v14 = 259;
          goto LABEL_182;
        }
        goto LABEL_195;
      }
      v35 = (struct mkvparser::IMkvReader *)((char *)v31 + (int)v95);
      if ( (__int64)v35 > (__int64)v26 )
      {
        v46 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v33, v34);
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
        v8 = -1072875842;
        if ( *((_BYTE *)v46 + 8) )
        {
          v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
          if ( *((_DWORD *)v48 + 499) != -1072875842 )
            CallStackContext::TraceFailure(v48, "mkvparser::CuePoint::Load", 2820, -1072875842);
        }
        if ( g_wppLevels )
        {
          v14 = 260;
          goto LABEL_182;
        }
        goto LABEL_195;
      }
      v27 = (struct mkvparser::IMkvReader *)((char *)v35 + v93[0]);
      if ( (__int64)v35 + v93[0] > (__int64)v26 )
      {
        v43 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v93[0], v34);
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
        v8 = -1072875842;
        if ( *((_BYTE *)v43 + 8) )
        {
          v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
          if ( *((_DWORD *)v45 + 499) != -1072875842 )
            CallStackContext::TraceFailure(v45, "mkvparser::CuePoint::Load", 2826, -1072875842);
        }
        if ( g_wppLevels )
        {
          v14 = 261;
          goto LABEL_182;
        }
        goto LABEL_195;
      }
      if ( v96 == 179 )
      {
        v8 = mkvparser::UnserializeUInt((mkvparser *)a2, v35, v93[0], (__int64)this + 24, v92);
        if ( v8 < 0 )
        {
          v39 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37, v38);
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
          if ( *((_BYTE *)v39 + 8) )
          {
            v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
            if ( *((_DWORD *)v42 + 499) != v8 )
              CallStackContext::TraceFailure(v42, "mkvparser::CuePoint::Load", 2831, v8);
          }
          if ( g_wppLevels )
          {
            v14 = 262;
            goto LABEL_182;
          }
          goto LABEL_195;
        }
      }
      else if ( v96 == 183 )
      {
        v41 = *((_QWORD *)this + 5);
        if ( v41 != -1 )
          *((_QWORD *)this + 5) = v41 + 1;
      }
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v94);
    }
    if ( *((_QWORD *)this + 5) )
    {
      v64 = 32LL * *((_QWORD *)this + 5);
      if ( !is_mul_ok(*((_QWORD *)this + 5), 0x20u) )
        v64 = -1;
      *((_QWORD *)this + 4) = operator new[](v64, (const struct std::nothrow_t *)&std::nothrow);
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v94, "mkvparser::CuePoint::Load", 2849);
      v68 = (mkvparser::CuePoint::TrackPosition *)*((_QWORD *)this + 4);
      if ( v68 )
      {
        while ( (__int64)v25 < (__int64)v26 )
        {
          v8 = mkvparser::ReadID(a2, v25, &v96, &v95);
          if ( v8 < 0 )
          {
            v86 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v87 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v72, v73, v74);
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
              if ( *((_DWORD *)v88 + 499) != v8 )
                CallStackContext::TraceFailure(v88, "mkvparser::CuePoint::Load", 2857, v8);
            }
            if ( g_wppLevels )
            {
              v14 = 265;
              goto LABEL_182;
            }
            goto LABEL_195;
          }
          v75 = (struct mkvparser::IMkvReader *)((char *)v25 + (int)v95);
          if ( (__int64)v75 > (__int64)v26 )
          {
            v83 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v84 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v72, v73, v74);
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
            v8 = -1072875842;
            if ( *((_BYTE *)v83 + 8) )
            {
              v85 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v83);
              if ( *((_DWORD *)v85 + 499) != -1072875842 )
                CallStackContext::TraceFailure(v85, "mkvparser::CuePoint::Load", 2860, -1072875842);
            }
            if ( g_wppLevels )
            {
              v14 = 266;
              goto LABEL_182;
            }
            goto LABEL_195;
          }
          v8 = mkvparser::ReadUInt(a2, v75, v93, &v95);
          if ( v8 < 0 )
          {
            v80 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v81 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v65, v66, v67);
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
              v82 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v80);
              if ( *((_DWORD *)v82 + 499) != v8 )
                CallStackContext::TraceFailure(v82, "mkvparser::CuePoint::Load", 2865, v8);
            }
            if ( g_wppLevels )
            {
              v14 = 267;
              goto LABEL_182;
            }
            goto LABEL_195;
          }
          v76 = (struct mkvparser::IMkvReader *)((char *)v75 + (int)v95);
          if ( v96 == 183 && (unsigned __int64)v68 < *((_QWORD *)this + 4) + 32LL * *((_QWORD *)this + 5) )
          {
            v8 = mkvparser::CuePoint::TrackPosition::Parse(v68, (struct mkvparser::IMkvReader *)a2, v76, v93[0]);
            if ( v8 < 0 )
            {
              v77 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v65, v66, v67);
                CallStackTracing::s_wpInstance = v78;
                if ( v78
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v78 + 8LL))(v78, 2032) )
                {
                  v77 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v77 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                }
              }
              if ( *((_BYTE *)v77 + 8) )
              {
                v79 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v77);
                if ( *((_DWORD *)v79 + 499) != v8 )
                  CallStackContext::TraceFailure(v79, "mkvparser::CuePoint::Load", 2873, v8);
              }
              if ( g_wppLevels )
              {
                v14 = 268;
                goto LABEL_182;
              }
              goto LABEL_195;
            }
            v68 = (mkvparser::CuePoint::TrackPosition *)((char *)v68 + 32);
          }
          v25 = (struct mkvparser::IMkvReader *)((char *)v76 + v93[0]);
        }
        if ( v25 == v26 )
        {
          *(_QWORD *)this = v6;
          *((_QWORD *)this + 1) = v26 - v6;
          v8 = 0;
        }
        else
        {
          v89 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v90 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v65, v66, v67);
            CallStackTracing::s_wpInstance = v90;
            if ( v90 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v90 + 8LL))(v90, 2032) )
            {
              v89 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v89 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          v8 = -1072875842;
          if ( *((_BYTE *)v89 + 8) )
          {
            v91 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v89);
            if ( *((_DWORD *)v91 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v91, "mkvparser::CuePoint::Load", 2881, -1072875842);
          }
          if ( g_wppLevels )
          {
            v14 = 269;
            goto LABEL_182;
          }
        }
      }
      else
      {
        v69 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v65, v66, v67);
          CallStackTracing::s_wpInstance = v70;
          if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
          {
            v69 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v69 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        v8 = -2147024882;
        if ( *((_BYTE *)v69 + 8) )
        {
          v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
          if ( *((_DWORD *)v71 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v71, "mkvparser::CuePoint::Load", 2849, -2147024882);
        }
        if ( g_wppLevels )
        {
          v14 = 264;
          goto LABEL_182;
        }
      }
    }
    else
    {
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v94, "mkvparser::CuePoint::Load", 2841);
      v61 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58, v59, v60);
        CallStackTracing::s_wpInstance = v62;
        if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
        {
          v61 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v61 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      v8 = -1072875842;
      if ( *((_BYTE *)v61 + 8) )
      {
        v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
        if ( *((_DWORD *)v63 + 499) != -1072875842 )
          CallStackContext::TraceFailure(v63, "mkvparser::CuePoint::Load", 2841, -1072875842);
      }
      if ( g_wppLevels )
      {
        v14 = 263;
        goto LABEL_182;
      }
    }
    goto LABEL_195;
  }
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
    if ( *((_DWORD *)v24 + 499) != v8 )
      CallStackContext::TraceFailure(v24, "mkvparser::CuePoint::Load", 2792, v8);
  }
  if ( g_wppLevels )
  {
    v14 = 256;
LABEL_182:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, this, v8);
  }
LABEL_195:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v94);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180092f5c  mov     [rsp-38h+arg_8], rbx
0x180092f61  push    rbp
0x180092f62  push    rsi
0x180092f63  push    rdi
0x180092f64  push    r12
0x180092f66  push    r13
0x180092f68  push    r14
0x180092f6a  push    r15
0x180092f6c  mov     rbp, rsp
0x180092f6f  sub     rsp, 40h
0x180092f73  mov     r15, [rcx+18h]
0x180092f77  xor     r14d, r14d
0x180092f7a  mov     r12, rdx
0x180092f7d  mov     rdi, rcx
0x180092f80  test    r15, r15
0x180092f83  js      short loc_180092F8C
0x180092f85  xor     eax, eax
0x180092f87  jmp     loc_180093B92
0x180092f8c  mov     esi, 0ADFh
0x180092f91  mov     [rbp+arg_18], r14
0x180092f95  lea     r13, aMkvparserCuepo; "mkvparser::CuePoint::Load"
0x180092f9c  mov     dword ptr [rbp+arg_10], r14d
0x180092fa0  mov     r8d, esi; int
0x180092fa3  mov     [rbp+var_10], r14
0x180092fa7  mov     rdx, r13; char *
0x180092faa  lea     rcx, [rbp+arg_0]; this
0x180092fae  neg     r15
0x180092fb1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180092fb6  lea     r9, [rbp+arg_10]; __int64 *
0x180092fba  mov     rdx, r15; struct mkvparser::IMkvReader *
0x180092fbd  lea     r8, [rbp+arg_18]; __int64
0x180092fc1  mov     rcx, r12; this
0x180092fc4  call    ?ReadID@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadID(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x180092fc9  mov     ebx, eax
0x180092fcb  test    eax, eax
0x180092fcd  jns     loc_180093061
0x180092fd3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180092fda  test    rcx, rcx
0x180092fdd  jnz     short loc_180093026
0x180092fdf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180092fe6  nop     dword ptr [rax+rax+00h]
0x180092feb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180092ff2  mov     rcx, rax
0x180092ff5  test    rax, rax
0x180092ff8  jz      short loc_180093018
0x180092ffa  mov     rax, [rax]
0x180092ffd  mov     edx, 7F0h
0x180093002  mov     rax, [rax+8]
0x180093006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009300b  test    eax, eax
0x18009300d  jz      short loc_180093018
0x18009300f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180093016  jmp     short loc_180093026
0x180093018  lea     rcx, qword_1800DBF70; this
0x18009301f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180093026  cmp     [rcx+8], r14b
0x18009302a  jz      short loc_18009304A
0x18009302c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180093031  cmp     [rax+7CCh], ebx
0x180093037  jz      short loc_18009304A
0x180093039  mov     r9d, ebx; int
0x18009303c  mov     r8d, esi; int
0x18009303f  mov     rdx, r13; char *
0x180093042  mov     rcx, rax; this
0x180093045  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009304a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180093051  jb      loc_180093B87
0x180093057  mov     edx, 0FEh
0x18009305c  jmp     loc_180093ABC
0x180093061  cmp     [rbp+arg_18], 0BBh
0x180093069  jz      loc_180093105
0x18009306f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180093076  test    rcx, rcx
0x180093079  jnz     short loc_1800930C2
0x18009307b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180093082  nop     dword ptr [rax+rax+00h]
0x180093087  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009308e  mov     rcx, rax
0x180093091  test    rax, rax
0x180093094  jz      short loc_1800930B4
0x180093096  mov     rax, [rax]
0x180093099  mov     edx, 7F0h
0x18009309e  mov     rax, [rax+8]
0x1800930a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800930a7  test    eax, eax
0x1800930a9  jz      short loc_1800930B4
0x1800930ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800930b2  jmp     short loc_1800930C2
0x1800930b4  lea     rcx, qword_1800DBF70; this
0x1800930bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800930c2  mov     ebx, 0C00D36BEh
0x1800930c7  cmp     [rcx+8], r14b
0x1800930cb  jz      short loc_1800930EE
0x1800930cd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800930d2  cmp     [rax+7CCh], ebx
0x1800930d8  jz      short loc_1800930EE
0x1800930da  mov     r9d, ebx; int
0x1800930dd  mov     r8d, 0AE3h; int
0x1800930e3  mov     rdx, r13; char *
0x1800930e6  mov     rcx, rax; this
0x1800930e9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800930ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800930f5  jb      loc_180093B87
0x1800930fb  mov     edx, 0FFh
0x180093100  jmp     loc_180093ABC
0x180093105  movsxd  rsi, dword ptr [rbp+arg_10]
0x180093109  lea     r9, [rbp+arg_10]; __int64 *
0x18009310d  add     rsi, r15
0x180093110  lea     r8, [rbp+var_10]; __int64
0x180093114  mov     rdx, rsi; struct mkvparser::IMkvReader *
0x180093117  mov     rcx, r12; this
0x18009311a  call    ?ReadUInt@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadUInt(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x18009311f  mov     ebx, eax
0x180093121  test    eax, eax
0x180093123  jns     loc_1800931BA
0x180093129  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180093130  test    rcx, rcx
0x180093133  jnz     short loc_18009317C
0x180093135  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009313c  nop     dword ptr [rax+rax+00h]
0x180093141  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180093148  mov     rcx, rax
0x18009314b  test    rax, rax
0x18009314e  jz      short loc_18009316E
0x180093150  mov     rax, [rax]
0x180093153  mov     edx, 7F0h
0x180093158  mov     rax, [rax+8]
0x18009315c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093161  test    eax, eax
0x180093163  jz      short loc_18009316E
0x180093165  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009316c  jmp     short loc_18009317C
0x18009316e  lea     rcx, qword_1800DBF70; this
0x180093175  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009317c  cmp     [rcx+8], r14b
0x180093180  jz      short loc_1800931A3
0x180093182  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180093187  cmp     [rax+7CCh], ebx
0x18009318d  jz      short loc_1800931A3
0x18009318f  mov     r9d, ebx; int
0x180093192  mov     r8d, 0AE8h; int
0x180093198  mov     rdx, r13; char *
0x18009319b  mov     rcx, rax; this
0x18009319e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800931a3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800931aa  jb      loc_180093B87
0x1800931b0  mov     edx, 100h
0x1800931b5  jmp     loc_180093ABC
0x1800931ba  movsxd  r14, dword ptr [rbp+arg_10]
0x1800931be  lea     rcx, [rbp+arg_0]; this
0x1800931c2  add     r14, rsi
0x1800931c5  mov     rsi, [rbp+var_10]
0x1800931c9  add     rsi, r14
0x1800931cc  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800931d1  mov     r13, r14
0x1800931d4  cmp     r13, rsi
0x1800931d7  jge     loc_180093630
0x1800931dd  mov     r8d, 0AF7h; int
0x1800931e3  lea     rdx, aMkvparserCuepo; "mkvparser::CuePoint::Load"
0x1800931ea  lea     rcx, [rbp+arg_0]; this
0x1800931ee  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800931f3  lea     r9, [rbp+arg_10]; __int64 *
0x1800931f7  mov     rdx, r13; struct mkvparser::IMkvReader *
0x1800931fa  lea     r8, [rbp+arg_18]; __int64
0x1800931fe  mov     rcx, r12; this
0x180093201  call    ?ReadID@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadID(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x180093206  mov     ebx, eax
0x180093208  test    eax, eax
0x18009320a  js      loc_18009359B
0x180093210  movsxd  rax, dword ptr [rbp+arg_10]
0x180093214  add     r13, rax
0x180093217  cmp     r13, rsi
0x18009321a  jg      loc_180093501
0x180093220  lea     r9, [rbp+arg_10]; __int64 *
0x180093224  mov     rdx, r13; struct mkvparser::IMkvReader *
0x180093227  lea     r8, [rbp+var_10]; __int64
0x18009322b  mov     rcx, r12; this
0x18009322e  call    ?ReadUInt@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadUInt(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x180093233  mov     ebx, eax
0x180093235  test    eax, eax
0x180093237  js      loc_18009346C
0x18009323d  movsxd  rdx, dword ptr [rbp+arg_10]
0x180093241  add     rdx, r13; struct mkvparser::IMkvReader *
0x180093244  cmp     rdx, rsi
0x180093247  jg      loc_1800933D2
0x18009324d  mov     r8, [rbp+var_10]; __int64
0x180093251  lea     r13, [rdx+r8]
0x180093255  cmp     r13, rsi
0x180093258  jg      loc_180093338
0x18009325e  cmp     [rbp+arg_18], 0B3h
0x180093266  jnz     short loc_1800932BF
0x180093268  lea     r9, [rdi+18h]; __int64
0x18009326c  mov     rcx, r12; this
0x18009326f  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x180093274  mov     ebx, eax
0x180093276  test    eax, eax
0x180093278  jns     short loc_1800932DA
0x18009327a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180093281  test    rcx, rcx
0x180093284  jnz     short loc_1800932F6
0x180093286  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009328d  nop     dword ptr [rax+rax+00h]
0x180093292  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180093299  mov     rcx, rax
0x18009329c  test    rax, rax
0x18009329f  jz      short loc_1800932E8
0x1800932a1  mov     rax, [rax]
0x1800932a4  mov     edx, 7F0h
0x1800932a9  mov     rax, [rax+8]
0x1800932ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800932b2  test    eax, eax
0x1800932b4  jz      short loc_1800932E8
0x1800932b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800932bd  jmp     short loc_1800932F6
0x1800932bf  cmp     [rbp+arg_18], 0B7h
0x1800932c7  jnz     short loc_1800932DA
0x1800932c9  mov     rax, [rdi+28h]
0x1800932cd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800932d1  jnb     short loc_1800932DA
0x1800932d3  inc     rax
0x1800932d6  mov     [rdi+28h], rax
0x1800932da  lea     rcx, [rbp+arg_0]; this
0x1800932de  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800932e3  jmp     loc_1800931D4
0x1800932e8  lea     rcx, qword_1800DBF70; this
0x1800932ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800932f6  cmp     byte ptr [rcx+8], 0
0x1800932fa  jz      short loc_180093321
0x1800932fc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180093301  cmp     [rax+7CCh], ebx
0x180093307  jz      short loc_180093321
0x180093309  mov     r9d, ebx; int
0x18009330c  lea     rdx, aMkvparserCuepo; "mkvparser::CuePoint::Load"
0x180093313  mov     r8d, 0B0Fh; int
0x180093319  mov     rcx, rax; this
0x18009331c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180093321  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180093328  jb      loc_180093B87
0x18009332e  mov     edx, 106h
0x180093333  jmp     loc_180093ABC
0x180093338  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009333f  test    rcx, rcx
0x180093342  jnz     short loc_18009338B
0x180093344  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009334b  nop     dword ptr [rax+rax+00h]
0x180093350  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180093357  mov     rcx, rax
0x18009335a  test    rax, rax
0x18009335d  jz      short loc_18009337D
0x18009335f  mov     rax, [rax]
0x180093362  mov     edx, 7F0h
0x180093367  mov     rax, [rax+8]
0x18009336b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093370  test    eax, eax
0x180093372  jz      short loc_18009337D
0x180093374  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009337b  jmp     short loc_18009338B
0x18009337d  lea     rcx, qword_1800DBF70; this
0x180093384  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009338b  cmp     byte ptr [rcx+8], 0
0x18009338f  mov     ebx, 0C00D36BEh
0x180093394  jz      short loc_1800933BB
0x180093396  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009339b  cmp     [rax+7CCh], ebx
0x1800933a1  jz      short loc_1800933BB
0x1800933a3  mov     r9d, ebx; int
0x1800933a6  lea     rdx, aMkvparserCuepo; "mkvparser::CuePoint::Load"
0x1800933ad  mov     r8d, 0B0Ah; int
0x1800933b3  mov     rcx, rax; this
0x1800933b6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800933bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800933c2  jb      loc_180093B87
0x1800933c8  mov     edx, 105h
0x1800933cd  jmp     loc_180093ABC
0x1800933d2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800933d9  test    rcx, rcx
0x1800933dc  jnz     short loc_180093425
0x1800933de  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800933e5  nop     dword ptr [rax+rax+00h]
0x1800933ea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800933f1  mov     rcx, rax
0x1800933f4  test    rax, rax
0x1800933f7  jz      short loc_180093417
0x1800933f9  mov     rax, [rax]
0x1800933fc  mov     edx, 7F0h
0x180093401  mov     rax, [rax+8]
0x180093405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009340a  test    eax, eax
0x18009340c  jz      short loc_180093417
0x18009340e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180093415  jmp     short loc_180093425
0x180093417  lea     rcx, qword_1800DBF70; this
0x18009341e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180093425  cmp     byte ptr [rcx+8], 0
0x180093429  mov     ebx, 0C00D36BEh
0x18009342e  jz      short loc_180093455
0x180093430  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180093435  cmp     [rax+7CCh], ebx
0x18009343b  jz      short loc_180093455
0x18009343d  mov     r9d, ebx; int
  ... truncated ...
```
