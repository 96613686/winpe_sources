# mkvparser::EBMLHeader::Parse(mkvparser::IMkvReader *,__int64 &,long &)

- ea: `0x18009bd54`
- end: `0x18009d134`
- name: `?Parse@EBMLHeader@mkvparser@@QEAAJPEAUIMkvReader@2@AEA_JAEAJ@Z`
- size: `5088`
- prototype: `__int64 __fastcall(mkvparser::EBMLHeader *__hidden this, struct mkvparser::IMkvReader *, struct mkvparser::IMkvReader *, __int64 *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180019e3c`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x180091ae0`
- `0x18009bd54`
- `0x1800a5fec`
- `0x1800adea8`
- `0x1800ae378`
- `0x1800af4ec`
- `0x1800af7b0`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009bda4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009be66`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009bf50`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c008`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c0da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c193`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c2c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c34c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c3cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c452`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c4d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c556`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c639`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c723`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c80d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c8f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c9dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cacb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cb60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cbfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cc8f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cd29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cdc4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ce68`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cf40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cfda`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009d074`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009bda4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009be66`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009bf50`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c008`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c0da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c193`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c2c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c34c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c3cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c452`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c4d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c556`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c639`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c723`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c80d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c8f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c9dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cacb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cb60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cbfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cc8f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cd29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cdc4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ce68`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cf40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cfda`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009d074`

## pseudocode

```c
__int64 __fastcall mkvparser::EBMLHeader::Parse(
        mkvparser::EBMLHeader *this,
        __int64 (__fastcall ***a2)(mkvparser *, struct mkvparser::IMkvReader *, __int64, unsigned __int8 *),
        struct mkvparser::IMkvReader **a3,
        __int64 *a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  int UInt; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 (__fastcall **v16)(mkvparser *, struct mkvparser::IMkvReader *, __int64, unsigned __int8 *); // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // r13
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  struct mkvparser::IMkvReader *v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  struct mkvparser::IMkvReader *v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  char *v44; // rcx
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rax
  struct mkvparser::IMkvReader *v49; // rdx
  __int64 *v50; // rbx
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  char *v54; // r12
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  char *v63; // r9
  __int64 *v64; // rcx
  CallStackTracing *v65; // rax
  __int64 *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  __int64 *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  struct CallStackContext *v72; // rax
  __int64 *v73; // rcx
  CallStackTracing *v74; // rax
  struct CallStackContext *v75; // rax
  struct CallStackContext *v76; // rax
  __int64 *v77; // rcx
  CallStackTracing *v78; // rax
  struct CallStackContext *v79; // rax
  struct CallStackContext *v80; // rax
  __int64 *v81; // rcx
  CallStackTracing *v82; // rax
  struct CallStackContext *v83; // rax
  struct CallStackContext *v84; // rax
  __int64 *v85; // rcx
  CallStackTracing *v86; // rax
  struct CallStackContext *v87; // rax
  struct CallStackContext *v88; // rax
  __int64 *v89; // rcx
  CallStackTracing *v90; // rax
  struct CallStackContext *v91; // rax
  __int64 *v92; // rcx
  CallStackTracing *v93; // rax
  struct CallStackContext *v94; // rax
  __int64 *v95; // rcx
  CallStackTracing *v96; // rax
  struct CallStackContext *v97; // rax
  __int64 *v98; // rcx
  CallStackTracing *v99; // rax
  struct CallStackContext *v100; // rax
  __int64 *v101; // rcx
  CallStackTracing *v102; // rax
  struct CallStackContext *v103; // rax
  __int64 *v104; // rcx
  CallStackTracing *v105; // rax
  struct CallStackContext *v106; // rax
  __int64 *v107; // rcx
  CallStackTracing *v108; // rax
  struct CallStackContext *v109; // rax
  __int64 *v111; // rcx
  CallStackTracing *v112; // rax
  struct CallStackContext *v113; // rax
  __int64 *v114; // rcx
  CallStackTracing *v115; // rax
  struct CallStackContext *v116; // rax
  __int64 *v117; // rcx
  CallStackTracing *v118; // rax
  struct CallStackContext *v119; // rax
  __int64 *v120; // [rsp+20h] [rbp-48h]
  __int64 *v121; // [rsp+28h] [rbp-40h]
  char v122[8]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v123; // [rsp+38h] [rbp-30h] BYREF
  __int64 v124; // [rsp+40h] [rbp-28h] BYREF
  __int64 v125; // [rsp+48h] [rbp-20h] BYREF
  __int64 *v126; // [rsp+50h] [rbp-18h]
  char *v127; // [rsp+B8h] [rbp+50h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v127, "mkvparser::EBMLHeader::Parse", 744);
  if ( !a2 )
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
    UInt = -2147024809;
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "mkvparser::EBMLHeader::Parse", 744, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_322;
    v15 = 53;
    goto LABEL_321;
  }
  v16 = *a2;
  v125 = 0;
  v124 = 0;
  UInt = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(mkvparser *, struct mkvparser::IMkvReader *, __int64, unsigned __int8 *), __int64 *, __int64 *))v16[1])(
           a2,
           &v125,
           &v124);
  if ( UInt < 0 )
  {
    v20 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18, v19);
      CallStackTracing::s_wpInstance = v21;
      if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
      {
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)v22 + 499) != UInt )
        CallStackContext::TraceFailure(v22, "mkvparser::EBMLHeader::Parse", 747, UInt);
    }
    if ( !g_wppLevels )
      goto LABEL_322;
    v15 = 54;
LABEL_321:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, this, UInt);
    goto LABEL_322;
  }
  v23 = v124;
  *a3 = 0;
  v122[0] = 0;
  if ( v23 >= 1024 )
    v23 = 1024;
  *(_DWORD *)a4 = 1;
  while ( (__int64)*a3 < v23 )
  {
    UInt = (**a2)((mkvparser *)a2, *a3, 1, (unsigned __int8 *)v122);
    if ( UInt < 0 )
    {
      v27 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25, v26);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v29 + 499) != UInt )
          CallStackContext::TraceFailure(v29, "mkvparser::EBMLHeader::Parse", 758, UInt);
      }
      if ( g_wppLevels )
      {
        v15 = 55;
        goto LABEL_321;
      }
      goto LABEL_322;
    }
    if ( v122[0] == 26 )
      break;
    *a3 = (struct mkvparser::IMkvReader *)((char *)*a3 + 1);
  }
  v30 = *a3;
  v123 = 0;
  UInt = mkvparser::ReadID(a2, v30, &v123, a4);
  if ( UInt >= 0 )
  {
    if ( *(_DWORD *)a4 == 4 && v123 == 440786851 )
    {
      *a3 = (struct mkvparser::IMkvReader *)((char *)*a3 + 4);
      v37 = *a3;
      v127 = 0;
      UInt = mkvparser::ReadUInt(a2, v37, (__int64 *)&v127, a4);
      if ( UInt >= 0 )
      {
        *a3 = (struct mkvparser::IMkvReader *)((char *)*a3 + *(int *)a4);
        v44 = v127;
        if ( v125 < 0 || v125 - (__int64)*a3 >= (__int64)v127 )
        {
          v48 = v124;
          *(_DWORD *)a4 = (_DWORD)v127;
          v49 = *a3;
          if ( v48 - (__int64)*a3 >= (__int64)v44 )
          {
            v50 = (__int64 *)&v44[(_QWORD)v49];
            v126 = (__int64 *)&v44[(_QWORD)v49];
            mkvparser::EBMLHeader::Init(this);
            while ( (__int64)*a3 < (__int64)v50 )
            {
              UInt = mkvparser::ParseElementHeader(
                       (mkvparser *)a2,
                       (struct mkvparser::IMkvReader *)a3,
                       v50,
                       (__int64)&v123,
                       (__int64 *)&v127,
                       v121);
              if ( UInt < 0 )
              {
                v101 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v102 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
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
                  if ( *((_DWORD *)v103 + 499) != UInt )
                    CallStackContext::TraceFailure(v103, "mkvparser::EBMLHeader::Parse", 803, UInt);
                }
                if ( g_wppLevels )
                {
                  v15 = 60;
                  goto LABEL_321;
                }
                goto LABEL_322;
              }
              v54 = v127;
              if ( !v127 )
              {
                v98 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v99 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
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
                UInt = -1072875842;
                if ( *((_BYTE *)v98 + 8) )
                {
                  v100 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v98);
                  if ( *((_DWORD *)v100 + 499) != -1072875842 )
                    CallStackContext::TraceFailure(v100, "mkvparser::EBMLHeader::Parse", 807, -1072875842);
                }
                if ( g_wppLevels )
                {
                  v15 = 61;
                  goto LABEL_321;
                }
                goto LABEL_322;
              }
              switch ( v123 )
              {
                case 17030LL:
                  UInt = mkvparser::UnserializeUInt((mkvparser *)a2, *a3, (__int64)v127, (__int64)this, v120);
                  if ( UInt < 0 )
                  {
                    v69 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                      CallStackTracing::s_wpInstance = v70;
                      if ( v70
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(
                             v70,
                             2032) )
                      {
                        v69 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v69 = &qword_1800DBF70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                      }
                    }
                    if ( *((_BYTE *)v69 + 8) )
                    {
                      v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
                      if ( *((_DWORD *)v71 + 499) != UInt )
                        CallStackContext::TraceFailure(v71, "mkvparser::EBMLHeader::Parse", 811, UInt);
                    }
                    if ( g_wppLevels )
                    {
                      v15 = 62;
                      goto LABEL_321;
                    }
                    goto LABEL_322;
                  }
                  if ( !*(_QWORD *)this )
                  {
                    v55 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                      CallStackTracing::s_wpInstance = v56;
                      if ( v56
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(
                             v56,
                             2032) )
                      {
                        v55 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v55 = &qword_1800DBF70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                      }
                    }
                    UInt = -1072875842;
                    if ( *((_BYTE *)v55 + 8) )
                    {
                      v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
                      if ( *((_DWORD *)v68 + 499) != -1072875842 )
                        CallStackContext::TraceFailure(v68, "mkvparser::EBMLHeader::Parse", 815, -1072875842);
                    }
                    if ( g_wppLevels )
                    {
                      v15 = 63;
                      goto LABEL_321;
                    }
                    goto LABEL_322;
                  }
                  break;
                case 17143LL:
                  UInt = mkvparser::UnserializeUInt((mkvparser *)a2, *a3, (__int64)v127, (__int64)this + 8, v120);
                  if ( UInt < 0 )
                  {
                    v73 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                      CallStackTracing::s_wpInstance = v74;
                      if ( v74
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(
                             v74,
                             2032) )
                      {
                        v73 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v73 = &qword_1800DBF70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                      }
                    }
                    if ( *((_BYTE *)v73 + 8) )
                    {
                      v75 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v73);
                      if ( *((_DWORD *)v75 + 499) != UInt )
                        CallStackContext::TraceFailure(v75, "mkvparser::EBMLHeader::Parse", 818, UInt);
                    }
                    if ( g_wppLevels )
                    {
                      v15 = 64;
                      goto LABEL_321;
                    }
                    goto LABEL_322;
                  }
                  if ( !*((_QWORD *)this + 1) )
                  {
                    v57 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                      CallStackTracing::s_wpInstance = v58;
                      if ( v58
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(
                             v58,
                             2032) )
                      {
                        v57 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v57 = &qword_1800DBF70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                      }
                    }
                    UInt = -1072875842;
                    if ( *((_BYTE *)v57 + 8) )
                    {
                      v72 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
                      if ( *((_DWORD *)v72 + 499) != -1072875842 )
                        CallStackContext::TraceFailure(v72, "mkvparser::EBMLHeader::Parse", 822, -1072875842);
                    }
                    if ( g_wppLevels )
                    {
                      v15 = 65;
                      goto LABEL_321;
                    }
                    goto LABEL_322;
                  }
                  break;
                case 17138LL:
                  UInt = mkvparser::UnserializeUInt((mkvparser *)a2, *a3, (__int64)v127, (__int64)this + 16, v120);
                  if ( UInt < 0 )
                  {
                    v77 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                      CallStackTracing::s_wpInstance = v78;
                      if ( v78
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v78 + 8LL))(
                             v78,
                             2032) )
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
                      if ( *((_DWORD *)v79 + 499) != UInt )
                        CallStackContext::TraceFailure(v79, "mkvparser::EBMLHeader::Parse", 825, UInt);
                    }
                    if ( g_wppLevels )
                    {
                      v15 = 66;
                      goto LABEL_321;
                    }
                    goto LABEL_322;
                  }
                  if ( !*((_QWORD *)this + 2) )
                  {
                    v59 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                      CallStackTracing::s_wpInstance = v60;
                      if ( v60
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(
                             v60,
                             2032) )
                      {
                        v59 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v59 = &qword_1800DBF70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                      }
                    }
                    UInt = -1072875842;
                    if ( *((_BYTE *)v59 + 8) )
                    {
                      v76 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
                      if ( *((_DWORD *)v76 + 499) != -1072875842 )
                        CallStackContext::TraceFailure(v76, "mkvparser::EBMLHeader::Parse", 829, -1072875842);
                    }
                    if ( g_wppLevels )
                    {
                      v15 = 67;
                      goto LABEL_321;
                    }
                    goto LABEL_322;
                  }
                  break;
                case 17139LL:
                  UInt = mkvparser::UnserializeUInt((mkvparser *)a2, *a3, (__int64)v127, (__int64)this + 24, v120);
                  if ( UInt < 0 )
                  {
                    v81 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v82 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                      CallStackTracing::s_wpInstance = v82;
                      if ( v82
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v82 + 8LL))(
                             v82,
                             2032) )
                      {
                        v81 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v81 = &qword_1800DBF70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                      }
                    }
                    if ( *((_BYTE *)v81 + 8) )
                    {
                      v83 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v81);
                      if ( *((_DWORD *)v83 + 499) != UInt )
                        CallStackContext::TraceFailure(v83, "mkvparser::EBMLHeader::Parse", 832, UInt);
                    }
                    if ( g_wppLevels )
                    {
                      v15 = 68;
                      goto LABEL_321;
                    }
                    goto LABEL_322;
                  }
                  if ( !*((_QWORD *)this + 3) )
                  {
                    v61 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                      CallStackTracing::s_wpInstance = v62;
                      if ( v62
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(
                             v62,
                             2032) )
                      {
                        v61 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v61 = &qword_1800DBF70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                      }
                    }
                    UInt = -1072875842;
                    if ( *((_BYTE *)v61 + 8) )
                    {
                      v80 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
                      if ( *((_DWORD *)v80 + 499) != -1072875842 )
                        CallStackContext::TraceFailure(v80, "mkvparser::EBMLHeader::Parse", 836, -1072875842);
                    }
                    if ( g_wppLevels )
                    {
                      v15 = 69;
                      goto LABEL_321;
                    }
                    goto LABEL_322;
                  }
                  break;
                case 17026LL:
                  v63 = (char *)this + 32;
                  if ( *((_QWORD *)this + 4) )
                  {
                    v85 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v86 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v63);
                      CallStackTracing::s_wpInstance = v86;
                      if ( v86
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v86 + 8LL))(
                             v86,
                             2032) )
                      {
                        v85 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v85 = &qword_1800DBF70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                      }
                    }
                    UInt = -1072875842;
                    if ( *((_BYTE *)v85 + 8) )
                    {
                      v87 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v85);
                      if ( *((_DWORD *)v87 + 499) != -1072875842 )
                        CallStackContext::TraceFailure(v87, "mkvparser::EBMLHeader::Parse", 841, -1072875842);
                    }
                    if ( g_wppLevels )
                    {
                      v15 = 70;
                      goto LABEL_321;
                    }
                    goto LABEL_322;
                  }
                  UInt = mkvparser::UnserializeString((mkvparser *)a2, *a3, (__int64)v127, (__int64)v63, (char **)v120);
                  if ( UInt < 0 )
                  {
                    v64 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                      CallStackTracing::s_wpInstance = v65;
                      if ( v65
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(
                             v65,
                             2032) )
                      {
                        v64 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v64 = &qword_1800DBF70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                      }
                    }
                    if ( *((_BYTE *)v64 + 8) )
                    {
                      v84 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
                      if ( *((_DWORD *)v84 + 499) != UInt )
                        CallStackContext::TraceFailure(v84, "mkvparser::EBMLHeader::Parse", 844, UInt);
                    }
                    if ( g_wppLevels )
                    {
                      v15 = 71;
                      goto LABEL_321;
                    }
                    goto LABEL_322;
                  }
                  break;
                case 17031LL:
                  UInt = mkvparser::UnserializeUInt((mkvparser *)a2, *a3, (__int64)v127, (__int64)this + 40, v120);
                  if ( UInt < 0 )
                  {
                    v89 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v90 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                      CallStackTracing::s_wpInstance = v90;
                      if ( v90
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v90 + 8LL))(
                             v90,
                             2032) )
                      {
                        v89 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v89 = &qword_1800DBF70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                      }
                    }
                    if ( *((_BYTE *)v89 + 8) )
                    {
                      v91 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v89);
                      if ( *((_DWORD *)v91 + 499) != UInt )
                        CallStackContext::TraceFailure(v91, "mkvparser::EBMLHeader::Parse", 846, UInt);
                    }
                    if ( g_wppLevels )
                    {
                      v15 = 72;
                      goto LABEL_321;
                    }
                    goto LABEL_322;
                  }
                  if ( !*((_QWORD *)this + 5) )
                  {
                    v66 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                      CallStackTracing::s_wpInstance = v67;
                      if ( v67
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(
                             v67,
                             2032) )
                      {
                        v66 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v66 = &qword_1800DBF70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                      }
                    }
                    UInt = -1072875842;
                    if ( *((_BYTE *)v66 + 8) )
                    {
                      v88 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
                      if ( *((_DWORD *)v88 + 499) != -1072875842 )
                        CallStackContext::TraceFailure(v88, "mkvparser::EBMLHeader::Parse", 850, -1072875842);
                    }
                    if ( g_wppLevels )
                    {
                      v15 = 73;
                      goto LABEL_321;
                    }
                    goto LABEL_322;
                  }
                  break;
                case 17029LL:
                  UInt = mkvparser::UnserializeUInt((mkvparser *)a2, *a3, (__int64)v127, (__int64)this + 48, v120);
                  if ( UInt < 0 )
                  {
                    v95 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v96 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                      CallStackTracing::s_wpInstance = v96;
                      if ( v96
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v96 + 8LL))(
                             v96,
                             2032) )
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
                      v97 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v95);
                      if ( *((_DWORD *)v97 + 499) != UInt )
                        CallStackContext::TraceFailure(v97, "mkvparser::EBMLHeader::Parse", 853, UInt);
                    }
                    if ( g_wppLevels )
                    {
                      v15 = 74;
                      goto LABEL_321;
                    }
                    goto LABEL_322;
                  }
                  if ( !*((_QWORD *)this + 6) )
                  {
                    v92 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v93 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                      CallStackTracing::s_wpInstance = v93;
                      if ( v93
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v93 + 8LL))(
                             v93,
                             2032) )
                      {
                        v92 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v92 = &qword_1800DBF70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                      }
                    }
                    UInt = -1072875842;
                    if ( *((_BYTE *)v92 + 8) )
                    {
                      v94 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v92);
                      if ( *((_DWORD *)v94 + 499) != -1072875842 )
                        CallStackContext::TraceFailure(v94, "mkvparser::EBMLHeader::Parse", 857, -1072875842);
                    }
                    if ( g_wppLevels )
                    {
                      v15 = 75;
                      goto LABEL_321;
                    }
                    goto LABEL_322;
                  }
                  break;
              }
              *a3 = (struct mkvparser::IMkvReader *)((char *)*a3 + (_QWORD)v54);
              v50 = v126;
            }
            if ( *a3 == (struct mkvparser::IMkvReader *)v50 )
            {
              if ( *((_QWORD *)this + 4) )
              {
                if ( *((__int64 *)this + 6) <= 0 || *((__int64 *)this + 5) <= 0 )
                {
                  v114 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v115 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                    CallStackTracing::s_wpInstance = v115;
                    if ( v115
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v115 + 8LL))(
                           v115,
                           2032) )
                    {
                      v114 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v114 = &qword_1800DBF70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                    }
                  }
                  UInt = -1072875842;
                  if ( *((_BYTE *)v114 + 8) )
                  {
                    v116 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v114);
                    if ( *((_DWORD *)v116 + 499) != -1072875842 )
                      CallStackContext::TraceFailure(v116, "mkvparser::EBMLHeader::Parse", 873, -1072875842);
                  }
                  if ( g_wppLevels )
                  {
                    v15 = 78;
                    goto LABEL_321;
                  }
                }
                else
                {
                  if ( (unsigned __int64)(*((_QWORD *)this + 2) - 1LL) <= 3
                    && (unsigned __int64)(*((_QWORD *)this + 3) - 1LL) <= 7 )
                  {
                    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v127);
                    return 0;
                  }
                  v111 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v112 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                    CallStackTracing::s_wpInstance = v112;
                    if ( v112
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v112 + 8LL))(
                           v112,
                           2032) )
                    {
                      v111 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v111 = &qword_1800DBF70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                    }
                  }
                  UInt = -1072875842;
                  if ( *((_BYTE *)v111 + 8) )
                  {
                    v113 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v111);
                    if ( *((_DWORD *)v113 + 499) != -1072875842 )
                      CallStackContext::TraceFailure(v113, "mkvparser::EBMLHeader::Parse", 879, -1072875842);
                  }
                  if ( g_wppLevels )
                  {
                    v15 = 79;
                    goto LABEL_321;
                  }
                }
              }
              else
              {
                v107 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v108 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                  CallStackTracing::s_wpInstance = v108;
                  if ( v108
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v108 + 8LL))(v108, 2032) )
                  {
                    v107 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v107 = &qword_1800DBF70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                  }
                }
                UInt = -1072875842;
                if ( *((_BYTE *)v107 + 8) )
                {
                  v109 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v107);
                  if ( *((_DWORD *)v109 + 499) != -1072875842 )
                    CallStackContext::TraceFailure(v109, "mkvparser::EBMLHeader::Parse", 870, -1072875842);
                }
                if ( g_wppLevels )
                {
                  v15 = 77;
                  goto LABEL_321;
                }
              }
            }
            else
            {
              v104 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v105 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
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
              UInt = -1072875842;
              if ( *((_BYTE *)v104 + 8) )
              {
                v106 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v104);
                if ( *((_DWORD *)v106 + 499) != -1072875842 )
                  CallStackContext::TraceFailure(v106, "mkvparser::EBMLHeader::Parse", 866, -1072875842);
              }
              if ( g_wppLevels )
              {
                v15 = 76;
                goto LABEL_321;
              }
            }
          }
          else
          {
            UInt = -1072863856;
          }
        }
        else
        {
          v45 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39, v40);
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
          UInt = -1072875842;
          if ( *((_BYTE *)v45 + 8) )
          {
            v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
            if ( *((_DWORD *)v47 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v47, "mkvparser::EBMLHeader::Parse", 787, -1072875842);
          }
          if ( g_wppLevels )
          {
            v15 = 59;
            goto LABEL_321;
          }
        }
      }
      else
      {
        v41 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39, v40);
          CallStackTracing::s_wpInstance = v42;
          if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
          {
            v41 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v41 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v41 + 8) )
        {
          v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
          if ( *((_DWORD *)v43 + 499) != UInt )
            CallStackContext::TraceFailure(v43, "mkvparser::EBMLHeader::Parse", 779, UInt);
        }
        if ( g_wppLevels )
        {
          v15 = 58;
          goto LABEL_321;
        }
      }
    }
    else
    {
      v117 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v118 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
        CallStackTracing::s_wpInstance = v118;
        if ( v118 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v118 + 8LL))(v118, 2032) )
        {
          v117 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v117 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      UInt = -1072875842;
      if ( *((_BYTE *)v117 + 8) )
      {
        v119 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v117);
        if ( *((_DWORD *)v119 + 499) != -1072875842 )
          CallStackContext::TraceFailure(v119, "mkvparser::EBMLHeader::Parse", 771, -1072875842);
      }
      if ( g_wppLevels )
      {
        v15 = 57;
        goto LABEL_321;
      }
    }
  }
  else
  {
    v34 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
      CallStackTracing::s_wpInstance = v35;
      if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
      {
        v34 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v34 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v34 + 8) )
    {
      v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
      if ( *((_DWORD *)v36 + 499) != UInt )
        CallStackContext::TraceFailure(v36, "mkvparser::EBMLHeader::Parse", 767, UInt);
    }
    if ( g_wppLevels )
    {
      v15 = 56;
      goto LABEL_321;
    }
  }
LABEL_322:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v127);
  return (unsigned int)UInt;
}

```

## disassembly

```asm
0x18009bd54  push    rbp
0x18009bd56  push    rbx
0x18009bd57  push    rsi
0x18009bd58  push    rdi
0x18009bd59  push    r12
0x18009bd5b  push    r13
0x18009bd5d  push    r14
0x18009bd5f  push    r15
0x18009bd61  mov     rbp, rsp
0x18009bd64  sub     rsp, 68h
0x18009bd68  mov     r14, r8
0x18009bd6b  lea     r13, aMkvparserEbmlh; "mkvparser::EBMLHeader::Parse"
0x18009bd72  mov     r15, rdx
0x18009bd75  mov     rsi, rcx
0x18009bd78  mov     rdx, r13; char *
0x18009bd7b  lea     rcx, [rbp+arg_8]; this
0x18009bd7f  mov     r8d, 2E8h; int
0x18009bd85  mov     r12, r9
0x18009bd88  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009bd8d  xor     edi, edi
0x18009bd8f  test    r15, r15
0x18009bd92  jnz     loc_18009BE31
0x18009bd98  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bd9f  test    rcx, rcx
0x18009bda2  jnz     short loc_18009BDEB
0x18009bda4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009bdab  nop     dword ptr [rax+rax+00h]
0x18009bdb0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bdb7  mov     rcx, rax
0x18009bdba  test    rax, rax
0x18009bdbd  jz      short loc_18009BDDD
0x18009bdbf  mov     rax, [rax]
0x18009bdc2  mov     edx, 7F0h
0x18009bdc7  mov     rax, [rax+8]
0x18009bdcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bdd0  test    eax, eax
0x18009bdd2  jz      short loc_18009BDDD
0x18009bdd4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bddb  jmp     short loc_18009BDEB
0x18009bddd  lea     rcx, qword_1800DBF70; this
0x18009bde4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bdeb  mov     ebx, 80070057h
0x18009bdf0  cmp     [rcx+8], dil
0x18009bdf4  jz      short loc_18009BE17
0x18009bdf6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009bdfb  cmp     [rax+7CCh], ebx
0x18009be01  jz      short loc_18009BE17
0x18009be03  mov     r9d, ebx; int
0x18009be06  mov     r8d, 2E8h; int
0x18009be0c  mov     rdx, r13; char *
0x18009be0f  mov     rcx, rax; this
0x18009be12  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009be17  mov     edi, 1
0x18009be1c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18009be23  jb      loc_18009D117
0x18009be29  lea     edx, [rdi+34h]
0x18009be2c  jmp     loc_18009D0F9
0x18009be31  mov     rax, [r15]
0x18009be34  lea     r8, [rbp+var_28]
0x18009be38  lea     rdx, [rbp+var_20]
0x18009be3c  mov     [rbp+var_20], rdi
0x18009be40  mov     rcx, r15
0x18009be43  mov     [rbp+var_28], rdi
0x18009be47  mov     rax, [rax+8]
0x18009be4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009be50  mov     ebx, eax
0x18009be52  test    eax, eax
0x18009be54  jns     loc_18009BEEE
0x18009be5a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009be61  test    rcx, rcx
0x18009be64  jnz     short loc_18009BEAD
0x18009be66  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009be6d  nop     dword ptr [rax+rax+00h]
0x18009be72  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009be79  mov     rcx, rax
0x18009be7c  test    rax, rax
0x18009be7f  jz      short loc_18009BE9F
0x18009be81  mov     rax, [rax]
0x18009be84  mov     edx, 7F0h
0x18009be89  mov     rax, [rax+8]
0x18009be8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009be92  test    eax, eax
0x18009be94  jz      short loc_18009BE9F
0x18009be96  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009be9d  jmp     short loc_18009BEAD
0x18009be9f  lea     rcx, qword_1800DBF70; this
0x18009bea6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bead  cmp     [rcx+8], dil
0x18009beb1  jz      short loc_18009BED4
0x18009beb3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009beb8  cmp     [rax+7CCh], ebx
0x18009bebe  jz      short loc_18009BED4
0x18009bec0  mov     r9d, ebx; int
0x18009bec3  mov     r8d, 2EBh; int
0x18009bec9  mov     rdx, r13; char *
0x18009becc  mov     rcx, rax; this
0x18009becf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009bed4  mov     edi, 1
0x18009bed9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18009bee0  jb      loc_18009D117
0x18009bee6  lea     edx, [rdi+35h]
0x18009bee9  jmp     loc_18009D0F9
0x18009beee  mov     r13, [rbp+var_28]
0x18009bef2  mov     eax, 400h
0x18009bef7  mov     [r14], rdi
0x18009befa  cmp     r13, rax
0x18009befd  mov     edi, 1
0x18009bf02  mov     [rbp+var_38], 0
0x18009bf06  cmovge  r13, rax
0x18009bf0a  mov     [r12], edi
0x18009bf0e  cmp     [r14], r13
0x18009bf11  jge     loc_18009BFD9
0x18009bf17  mov     rax, [r15]
0x18009bf1a  lea     r9, [rbp+var_38]
0x18009bf1e  mov     rdx, [r14]
0x18009bf21  mov     r8d, edi
0x18009bf24  mov     rcx, r15
0x18009bf27  mov     rax, [rax]
0x18009bf2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bf2f  mov     ebx, eax
0x18009bf31  test    eax, eax
0x18009bf33  js      short loc_18009BF44
0x18009bf35  cmp     [rbp+var_38], 1Ah
0x18009bf39  jz      loc_18009BFD9
0x18009bf3f  add     [r14], rdi
0x18009bf42  jmp     short loc_18009BF0E
0x18009bf44  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bf4b  test    rcx, rcx
0x18009bf4e  jnz     short loc_18009BF97
0x18009bf50  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009bf57  nop     dword ptr [rax+rax+00h]
0x18009bf5c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bf63  mov     rcx, rax
0x18009bf66  test    rax, rax
0x18009bf69  jz      short loc_18009BF89
0x18009bf6b  mov     rax, [rax]
0x18009bf6e  mov     edx, 7F0h
0x18009bf73  mov     rax, [rax+8]
0x18009bf77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bf7c  test    eax, eax
0x18009bf7e  jz      short loc_18009BF89
0x18009bf80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bf87  jmp     short loc_18009BF97
0x18009bf89  lea     rcx, qword_1800DBF70; this
0x18009bf90  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bf97  cmp     byte ptr [rcx+8], 0
0x18009bf9b  jz      short loc_18009BFC2
0x18009bf9d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009bfa2  cmp     [rax+7CCh], ebx
0x18009bfa8  jz      short loc_18009BFC2
0x18009bfaa  mov     r9d, ebx; int
0x18009bfad  lea     rdx, aMkvparserEbmlh; "mkvparser::EBMLHeader::Parse"
0x18009bfb4  mov     r8d, 2F6h; int
0x18009bfba  mov     rcx, rax; this
0x18009bfbd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009bfc2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18009bfc9  jb      loc_18009D117
0x18009bfcf  mov     edx, 37h ; '7'
0x18009bfd4  jmp     loc_18009D0F9
0x18009bfd9  mov     rdx, [r14]; struct mkvparser::IMkvReader *
0x18009bfdc  lea     r8, [rbp+var_30]; __int64
0x18009bfe0  xor     r13d, r13d
0x18009bfe3  mov     r9, r12; __int64 *
0x18009bfe6  mov     rcx, r15; this
0x18009bfe9  mov     [rbp+var_30], r13
0x18009bfed  call    ?ReadID@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadID(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x18009bff2  mov     ebx, eax
0x18009bff4  test    eax, eax
0x18009bff6  jns     loc_18009C091
0x18009bffc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c003  test    rcx, rcx
0x18009c006  jnz     short loc_18009C04F
0x18009c008  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009c00f  nop     dword ptr [rax+rax+00h]
0x18009c014  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c01b  mov     rcx, rax
0x18009c01e  test    rax, rax
0x18009c021  jz      short loc_18009C041
0x18009c023  mov     rax, [rax]
0x18009c026  mov     edx, 7F0h
0x18009c02b  mov     rax, [rax+8]
0x18009c02f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c034  test    eax, eax
0x18009c036  jz      short loc_18009C041
0x18009c038  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c03f  jmp     short loc_18009C04F
0x18009c041  lea     rcx, qword_1800DBF70; this
0x18009c048  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c04f  cmp     [rcx+8], r13b
0x18009c053  jz      short loc_18009C07A
0x18009c055  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009c05a  cmp     [rax+7CCh], ebx
0x18009c060  jz      short loc_18009C07A
0x18009c062  mov     r9d, ebx; int
0x18009c065  lea     rdx, aMkvparserEbmlh; "mkvparser::EBMLHeader::Parse"
0x18009c06c  mov     r8d, 2FFh; int
0x18009c072  mov     rcx, rax; this
0x18009c075  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009c07a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18009c081  jb      loc_18009D117
0x18009c087  mov     edx, 38h ; '8'
0x18009c08c  jmp     loc_18009D0F9
0x18009c091  cmp     dword ptr [r12], 4
0x18009c096  jnz     loc_18009D068
0x18009c09c  cmp     [rbp+var_30], 1A45DFA3h
0x18009c0a4  jnz     loc_18009D068
0x18009c0aa  add     qword ptr [r14], 4
0x18009c0ae  lea     r8, [rbp+arg_8]; __int64
0x18009c0b2  mov     rdx, [r14]; struct mkvparser::IMkvReader *
0x18009c0b5  mov     r9, r12; __int64 *
0x18009c0b8  mov     rcx, r15; this
0x18009c0bb  mov     [rbp+arg_8], r13
0x18009c0bf  call    ?ReadUInt@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadUInt(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x18009c0c4  mov     ebx, eax
0x18009c0c6  test    eax, eax
0x18009c0c8  jns     loc_18009C163
0x18009c0ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c0d5  test    rcx, rcx
0x18009c0d8  jnz     short loc_18009C121
0x18009c0da  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009c0e1  nop     dword ptr [rax+rax+00h]
0x18009c0e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c0ed  mov     rcx, rax
0x18009c0f0  test    rax, rax
0x18009c0f3  jz      short loc_18009C113
0x18009c0f5  mov     rax, [rax]
0x18009c0f8  mov     edx, 7F0h
0x18009c0fd  mov     rax, [rax+8]
0x18009c101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c106  test    eax, eax
0x18009c108  jz      short loc_18009C113
0x18009c10a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c111  jmp     short loc_18009C121
0x18009c113  lea     rcx, qword_1800DBF70; this
0x18009c11a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c121  cmp     [rcx+8], r13b
0x18009c125  jz      short loc_18009C14C
0x18009c127  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009c12c  cmp     [rax+7CCh], ebx
0x18009c132  jz      short loc_18009C14C
0x18009c134  mov     r9d, ebx; int
0x18009c137  lea     rdx, aMkvparserEbmlh; "mkvparser::EBMLHeader::Parse"
0x18009c13e  mov     r8d, 30Bh; int
0x18009c144  mov     rcx, rax; this
0x18009c147  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009c14c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18009c153  jb      loc_18009D117
0x18009c159  mov     edx, 3Ah ; ':'
0x18009c15e  jmp     loc_18009D0F9
0x18009c163  movsxd  rax, dword ptr [r12]
0x18009c167  add     [r14], rax
0x18009c16a  mov     rax, [rbp+var_20]
0x18009c16e  mov     rcx, [rbp+arg_8]
0x18009c172  test    rax, rax
0x18009c175  js      loc_18009C221
0x18009c17b  sub     rax, [r14]
0x18009c17e  cmp     rax, rcx
0x18009c181  jge     loc_18009C221
0x18009c187  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c18e  test    rcx, rcx
0x18009c191  jnz     short loc_18009C1DA
0x18009c193  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009c19a  nop     dword ptr [rax+rax+00h]
0x18009c19f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c1a6  mov     rcx, rax
0x18009c1a9  test    rax, rax
0x18009c1ac  jz      short loc_18009C1CC
0x18009c1ae  mov     rax, [rax]
0x18009c1b1  mov     edx, 7F0h
0x18009c1b6  mov     rax, [rax+8]
0x18009c1ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c1bf  test    eax, eax
0x18009c1c1  jz      short loc_18009C1CC
0x18009c1c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c1ca  jmp     short loc_18009C1DA
0x18009c1cc  lea     rcx, qword_1800DBF70; this
0x18009c1d3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c1da  mov     ebx, 0C00D36BEh
0x18009c1df  cmp     [rcx+8], r13b
0x18009c1e3  jz      short loc_18009C20A
0x18009c1e5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009c1ea  cmp     [rax+7CCh], ebx
0x18009c1f0  jz      short loc_18009C20A
0x18009c1f2  mov     r9d, ebx; int
0x18009c1f5  lea     rdx, aMkvparserEbmlh; "mkvparser::EBMLHeader::Parse"
0x18009c1fc  mov     r8d, 313h; int
0x18009c202  mov     rcx, rax; this
0x18009c205  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009c20a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18009c211  jb      loc_18009D117
0x18009c217  mov     edx, 3Bh ; ';'
0x18009c21c  jmp     loc_18009D0F9
0x18009c221  mov     rax, [rbp+var_28]
0x18009c225  mov     [r12], ecx
0x18009c229  mov     rdx, [r14]
0x18009c22c  sub     rax, rdx
0x18009c22f  cmp     rax, rcx
0x18009c232  jge     short loc_18009C23E
0x18009c234  mov     ebx, 0C00D6590h
0x18009c239  jmp     loc_18009D117
  ... truncated ...
```
