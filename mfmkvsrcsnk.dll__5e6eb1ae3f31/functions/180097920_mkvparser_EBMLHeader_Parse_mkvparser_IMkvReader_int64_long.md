# mkvparser::EBMLHeader::Parse(mkvparser::IMkvReader *,__int64 &,long &)

- ea: `0x180097920`
- end: `0x180098c59`
- name: `?Parse@EBMLHeader@mkvparser@@QEAAJPEAUIMkvReader@2@AEA_JAEAJ@Z`
- size: `4921`
- prototype: `__int64 __fastcall(mkvparser::EBMLHeader *__hidden this, struct mkvparser::IMkvReader *, struct mkvparser::IMkvReader *, __int64 *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1800192b8`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x18008db7c`
- `0x180097920`
- `0x1800a1710`
- `0x1800a9220`
- `0x1800a96cc`
- `0x1800aa7cc`
- `0x1800aaa7c`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097970`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097a2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097b10`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097bc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097c8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097d41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097e71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097eee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097f6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097fe8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098063`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800980dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800981b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009829d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098381`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098465`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098544`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009862d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800986bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098750`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800987df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098873`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098908`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800989a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098a78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098b0c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098ba0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097970`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097a2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097b10`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097bc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097c8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097d41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097e71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097eee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097f6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097fe8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098063`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800980dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800981b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009829d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098381`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098465`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098544`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009862d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800986bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098750`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800987df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098873`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098908`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800989a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098a78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098b0c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098ba0`

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
        v11 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v20 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v27 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                    v101 = &qword_1800D6F70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                    v98 = &qword_1800D6F70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                        v69 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                        v55 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                        v73 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                        v57 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                        v77 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                        v59 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                        v81 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                        v61 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                        v85 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                        v64 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                        v89 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                        v66 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                        v95 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                        v92 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                      v114 = &qword_1800D6F70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                      v111 = &qword_1800D6F70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                    v107 = &qword_1800D6F70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                  v104 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v45 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v41 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v117 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v34 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180097920  push    rbp
0x180097922  push    rbx
0x180097923  push    rsi
0x180097924  push    rdi
0x180097925  push    r12
0x180097927  push    r13
0x180097929  push    r14
0x18009792b  push    r15
0x18009792d  mov     rbp, rsp
0x180097930  sub     rsp, 68h
0x180097934  mov     r14, r8
0x180097937  lea     r13, aMkvparserEbmlh; "mkvparser::EBMLHeader::Parse"
0x18009793e  mov     r15, rdx
0x180097941  mov     rsi, rcx
0x180097944  mov     rdx, r13; char *
0x180097947  lea     rcx, [rbp+arg_8]; this
0x18009794b  mov     r8d, 2E8h; int
0x180097951  mov     r12, r9
0x180097954  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180097959  xor     edi, edi
0x18009795b  test    r15, r15
0x18009795e  jnz     loc_1800979F7
0x180097964  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009796b  test    rcx, rcx
0x18009796e  jnz     short loc_1800979B1
0x180097970  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180097976  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009797d  mov     rcx, rax
0x180097980  test    rax, rax
0x180097983  jz      short loc_1800979A3
0x180097985  mov     rax, [rax]
0x180097988  mov     edx, 7F0h
0x18009798d  mov     rax, [rax+8]
0x180097991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097996  test    eax, eax
0x180097998  jz      short loc_1800979A3
0x18009799a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800979a1  jmp     short loc_1800979B1
0x1800979a3  lea     rcx, qword_1800D6F70; this
0x1800979aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800979b1  mov     ebx, 80070057h
0x1800979b6  cmp     [rcx+8], dil
0x1800979ba  jz      short loc_1800979DD
0x1800979bc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800979c1  cmp     [rax+7CCh], ebx
0x1800979c7  jz      short loc_1800979DD
0x1800979c9  mov     r9d, ebx; int
0x1800979cc  mov     r8d, 2E8h; int
0x1800979d2  mov     rdx, r13; char *
0x1800979d5  mov     rcx, rax; this
0x1800979d8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800979dd  mov     edi, 1
0x1800979e2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800979e9  jb      loc_180098C3D
0x1800979ef  lea     edx, [rdi+34h]
0x1800979f2  jmp     loc_180098C1F
0x1800979f7  mov     rax, [r15]
0x1800979fa  lea     r8, [rbp+var_28]
0x1800979fe  lea     rdx, [rbp+var_20]
0x180097a02  mov     [rbp+var_20], rdi
0x180097a06  mov     rcx, r15
0x180097a09  mov     [rbp+var_28], rdi
0x180097a0d  mov     rax, [rax+8]
0x180097a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097a16  mov     ebx, eax
0x180097a18  test    eax, eax
0x180097a1a  jns     loc_180097AAE
0x180097a20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180097a27  test    rcx, rcx
0x180097a2a  jnz     short loc_180097A6D
0x180097a2c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180097a32  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180097a39  mov     rcx, rax
0x180097a3c  test    rax, rax
0x180097a3f  jz      short loc_180097A5F
0x180097a41  mov     rax, [rax]
0x180097a44  mov     edx, 7F0h
0x180097a49  mov     rax, [rax+8]
0x180097a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097a52  test    eax, eax
0x180097a54  jz      short loc_180097A5F
0x180097a56  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180097a5d  jmp     short loc_180097A6D
0x180097a5f  lea     rcx, qword_1800D6F70; this
0x180097a66  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180097a6d  cmp     [rcx+8], dil
0x180097a71  jz      short loc_180097A94
0x180097a73  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180097a78  cmp     [rax+7CCh], ebx
0x180097a7e  jz      short loc_180097A94
0x180097a80  mov     r9d, ebx; int
0x180097a83  mov     r8d, 2EBh; int
0x180097a89  mov     rdx, r13; char *
0x180097a8c  mov     rcx, rax; this
0x180097a8f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180097a94  mov     edi, 1
0x180097a99  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180097aa0  jb      loc_180098C3D
0x180097aa6  lea     edx, [rdi+35h]
0x180097aa9  jmp     loc_180098C1F
0x180097aae  mov     r13, [rbp+var_28]
0x180097ab2  mov     eax, 400h
0x180097ab7  mov     [r14], rdi
0x180097aba  cmp     r13, rax
0x180097abd  mov     edi, 1
0x180097ac2  mov     [rbp+var_38], 0
0x180097ac6  cmovge  r13, rax
0x180097aca  mov     [r12], edi
0x180097ace  cmp     [r14], r13
0x180097ad1  jge     loc_180097B93
0x180097ad7  mov     rax, [r15]
0x180097ada  lea     r9, [rbp+var_38]
0x180097ade  mov     rdx, [r14]
0x180097ae1  mov     r8d, edi
0x180097ae4  mov     rcx, r15
0x180097ae7  mov     rax, [rax]
0x180097aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097aef  mov     ebx, eax
0x180097af1  test    eax, eax
0x180097af3  js      short loc_180097B04
0x180097af5  cmp     [rbp+var_38], 1Ah
0x180097af9  jz      loc_180097B93
0x180097aff  add     [r14], rdi
0x180097b02  jmp     short loc_180097ACE
0x180097b04  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180097b0b  test    rcx, rcx
0x180097b0e  jnz     short loc_180097B51
0x180097b10  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180097b16  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180097b1d  mov     rcx, rax
0x180097b20  test    rax, rax
0x180097b23  jz      short loc_180097B43
0x180097b25  mov     rax, [rax]
0x180097b28  mov     edx, 7F0h
0x180097b2d  mov     rax, [rax+8]
0x180097b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097b36  test    eax, eax
0x180097b38  jz      short loc_180097B43
0x180097b3a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180097b41  jmp     short loc_180097B51
0x180097b43  lea     rcx, qword_1800D6F70; this
0x180097b4a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180097b51  cmp     byte ptr [rcx+8], 0
0x180097b55  jz      short loc_180097B7C
0x180097b57  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180097b5c  cmp     [rax+7CCh], ebx
0x180097b62  jz      short loc_180097B7C
0x180097b64  mov     r9d, ebx; int
0x180097b67  lea     rdx, aMkvparserEbmlh; "mkvparser::EBMLHeader::Parse"
0x180097b6e  mov     r8d, 2F6h; int
0x180097b74  mov     rcx, rax; this
0x180097b77  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180097b7c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180097b83  jb      loc_180098C3D
0x180097b89  mov     edx, 37h ; '7'
0x180097b8e  jmp     loc_180098C1F
0x180097b93  mov     rdx, [r14]; struct mkvparser::IMkvReader *
0x180097b96  lea     r8, [rbp+var_30]; __int64
0x180097b9a  xor     r13d, r13d
0x180097b9d  mov     r9, r12; __int64 *
0x180097ba0  mov     rcx, r15; this
0x180097ba3  mov     [rbp+var_30], r13
0x180097ba7  call    ?ReadID@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadID(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x180097bac  mov     ebx, eax
0x180097bae  test    eax, eax
0x180097bb0  jns     loc_180097C45
0x180097bb6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180097bbd  test    rcx, rcx
0x180097bc0  jnz     short loc_180097C03
0x180097bc2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180097bc8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180097bcf  mov     rcx, rax
0x180097bd2  test    rax, rax
0x180097bd5  jz      short loc_180097BF5
0x180097bd7  mov     rax, [rax]
0x180097bda  mov     edx, 7F0h
0x180097bdf  mov     rax, [rax+8]
0x180097be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097be8  test    eax, eax
0x180097bea  jz      short loc_180097BF5
0x180097bec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180097bf3  jmp     short loc_180097C03
0x180097bf5  lea     rcx, qword_1800D6F70; this
0x180097bfc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180097c03  cmp     [rcx+8], r13b
0x180097c07  jz      short loc_180097C2E
0x180097c09  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180097c0e  cmp     [rax+7CCh], ebx
0x180097c14  jz      short loc_180097C2E
0x180097c16  mov     r9d, ebx; int
0x180097c19  lea     rdx, aMkvparserEbmlh; "mkvparser::EBMLHeader::Parse"
0x180097c20  mov     r8d, 2FFh; int
0x180097c26  mov     rcx, rax; this
0x180097c29  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180097c2e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180097c35  jb      loc_180098C3D
0x180097c3b  mov     edx, 38h ; '8'
0x180097c40  jmp     loc_180098C1F
0x180097c45  cmp     dword ptr [r12], 4
0x180097c4a  jnz     loc_180098B94
0x180097c50  cmp     [rbp+var_30], 1A45DFA3h
0x180097c58  jnz     loc_180098B94
0x180097c5e  add     qword ptr [r14], 4
0x180097c62  lea     r8, [rbp+arg_8]; __int64
0x180097c66  mov     rdx, [r14]; struct mkvparser::IMkvReader *
0x180097c69  mov     r9, r12; __int64 *
0x180097c6c  mov     rcx, r15; this
0x180097c6f  mov     [rbp+arg_8], r13
0x180097c73  call    ?ReadUInt@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadUInt(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x180097c78  mov     ebx, eax
0x180097c7a  test    eax, eax
0x180097c7c  jns     loc_180097D11
0x180097c82  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180097c89  test    rcx, rcx
0x180097c8c  jnz     short loc_180097CCF
0x180097c8e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180097c94  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180097c9b  mov     rcx, rax
0x180097c9e  test    rax, rax
0x180097ca1  jz      short loc_180097CC1
0x180097ca3  mov     rax, [rax]
0x180097ca6  mov     edx, 7F0h
0x180097cab  mov     rax, [rax+8]
0x180097caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097cb4  test    eax, eax
0x180097cb6  jz      short loc_180097CC1
0x180097cb8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180097cbf  jmp     short loc_180097CCF
0x180097cc1  lea     rcx, qword_1800D6F70; this
0x180097cc8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180097ccf  cmp     [rcx+8], r13b
0x180097cd3  jz      short loc_180097CFA
0x180097cd5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180097cda  cmp     [rax+7CCh], ebx
0x180097ce0  jz      short loc_180097CFA
0x180097ce2  mov     r9d, ebx; int
0x180097ce5  lea     rdx, aMkvparserEbmlh; "mkvparser::EBMLHeader::Parse"
0x180097cec  mov     r8d, 30Bh; int
0x180097cf2  mov     rcx, rax; this
0x180097cf5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180097cfa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180097d01  jb      loc_180098C3D
0x180097d07  mov     edx, 3Ah ; ':'
0x180097d0c  jmp     loc_180098C1F
0x180097d11  movsxd  rax, dword ptr [r12]
0x180097d15  add     [r14], rax
0x180097d18  mov     rax, [rbp+var_20]
0x180097d1c  mov     rcx, [rbp+arg_8]
0x180097d20  test    rax, rax
0x180097d23  js      loc_180097DC9
0x180097d29  sub     rax, [r14]
0x180097d2c  cmp     rax, rcx
0x180097d2f  jge     loc_180097DC9
0x180097d35  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180097d3c  test    rcx, rcx
0x180097d3f  jnz     short loc_180097D82
0x180097d41  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180097d47  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180097d4e  mov     rcx, rax
0x180097d51  test    rax, rax
0x180097d54  jz      short loc_180097D74
0x180097d56  mov     rax, [rax]
0x180097d59  mov     edx, 7F0h
0x180097d5e  mov     rax, [rax+8]
0x180097d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097d67  test    eax, eax
0x180097d69  jz      short loc_180097D74
0x180097d6b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180097d72  jmp     short loc_180097D82
0x180097d74  lea     rcx, qword_1800D6F70; this
0x180097d7b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180097d82  mov     ebx, 0C00D36BEh
0x180097d87  cmp     [rcx+8], r13b
0x180097d8b  jz      short loc_180097DB2
0x180097d8d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180097d92  cmp     [rax+7CCh], ebx
0x180097d98  jz      short loc_180097DB2
0x180097d9a  mov     r9d, ebx; int
0x180097d9d  lea     rdx, aMkvparserEbmlh; "mkvparser::EBMLHeader::Parse"
0x180097da4  mov     r8d, 313h; int
0x180097daa  mov     rcx, rax; this
0x180097dad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180097db2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180097db9  jb      loc_180098C3D
0x180097dbf  mov     edx, 3Bh ; ';'
0x180097dc4  jmp     loc_180098C1F
0x180097dc9  mov     rax, [rbp+var_28]
0x180097dcd  mov     [r12], ecx
0x180097dd1  mov     rdx, [r14]
0x180097dd4  sub     rax, rdx
0x180097dd7  cmp     rax, rcx
0x180097dda  jge     short loc_180097DE6
0x180097ddc  mov     ebx, 0C00D6590h
0x180097de1  jmp     loc_180098C3D
0x180097de6  lea     rbx, [rdx+rcx]
0x180097dea  mov     rcx, rsi; this
0x180097ded  mov     [rbp+var_18], rbx
0x180097df1  call    ?Init@EBMLHeader@mkvparser@@QEAAXXZ; mkvparser::EBMLHeader::Init(void)
0x180097df6  cmp     [r14], rbx
0x180097df9  jge     loc_1800988F6
  ... truncated ...
```
