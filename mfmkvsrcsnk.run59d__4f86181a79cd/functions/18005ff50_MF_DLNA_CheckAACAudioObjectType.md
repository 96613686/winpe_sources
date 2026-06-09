# MF::DLNA::CheckAACAudioObjectType

- ea: `0x18005ff50`
- end: `0x180060d81`
- name: `MF::DLNA::CheckAACAudioObjectType`
- size: `3633`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180065ce0`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x18005ff50`
- `0x180064138`
- `0x180066af0`
- `0x180066b20`
- `0x180066bc0`
- `0x1800744d8`
- `0x18007ec30`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060d58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060d58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ffe6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800600ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006018c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060297`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060334`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060471`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800605ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800606ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800607c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060898`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006096d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060a41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060b17`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060bee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060cb6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ffe6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800600ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006018c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060297`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060334`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060471`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800605ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800606ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800607c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060898`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006096d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060a41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060b17`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060bee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060cb6`

## pseudocode

```c
__int64 __fastcall MF::DLNA::CheckAACAudioObjectType(__int64 *a1, _DWORD *a2)
{
  int v4; // r13d
  __int64 v5; // rax
  __int64 (__fastcall *v6)(__int64 *, const GUID *, LPVOID *, unsigned int *); // rax
  __int64 v7; // rdx
  int AACLevel; // esi
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 *v16; // rcx
  int v17; // ebx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  LPVOID v21; // rdx
  __int64 v22; // r9
  __int64 v23; // rcx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  unsigned int v27; // r15d
  unsigned int v28; // r12d
  __int64 v29; // rdx
  int v30; // r14d
  int v31; // ebx
  __int64 v32; // r9
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  int v42; // r15d
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // rdx
  int v46; // ecx
  BOOL v47; // eax
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  __int64 *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  __int64 *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  __int64 *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  __int64 *v72; // rcx
  CallStackTracing *v73; // rax
  struct CallStackContext *v74; // rax
  __int64 *v75; // rcx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  int v79; // [rsp+30h] [rbp-48h]
  LPVOID pv; // [rsp+38h] [rbp-40h] BYREF
  _QWORD v81[3]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v82; // [rsp+58h] [rbp-20h]
  unsigned int v83; // [rsp+60h] [rbp-18h]
  unsigned int v84; // [rsp+C0h] [rbp+48h] BYREF
  _DWORD *v85; // [rsp+C8h] [rbp+50h]
  unsigned int v86; // [rsp+D0h] [rbp+58h] BYREF
  int v87; // [rsp+D8h] [rbp+60h]

  v85 = a2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v84, "MF::DLNA::CheckAACAudioObjectType", 7160);
  v4 = 0;
  v79 = *a2;
  v5 = *a1;
  memset(v81, 0, sizeof(v81));
  v6 = *(__int64 (__fastcall **)(__int64 *, const GUID *, LPVOID *, unsigned int *))(v5 + 128);
  v82 = 0;
  v83 = 0;
  v84 = 0;
  pv = 0;
  v86 = 0;
  AACLevel = v6(a1, &MF_MT_USER_DATA, &pv, &v86);
  if ( AACLevel < 0 )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != AACLevel )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MF::DLNA::CheckAACAudioObjectType", 7186, AACLevel);
    }
    if ( g_wppLevels )
    {
      v14 = 38;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, 0, AACLevel);
      goto LABEL_228;
    }
    goto LABEL_228;
  }
  v15 = v86;
  if ( v86 < 0xC )
  {
    if ( byte_1800DC8D3 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 17), 39, v86, v86);
    v16 = (__int64 *)CallStackTracing::s_wpInstance;
    v17 = -1072875852;
    AACLevel = -1072875852;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v15, v10);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)v19 + 499) != -1072875852 )
        CallStackContext::TraceFailure(v19, "MF::DLNA::CheckAACAudioObjectType", 7191, -1072875852);
    }
    if ( !g_wppLevels )
      goto LABEL_228;
    v20 = 40;
    goto LABEL_227;
  }
  v21 = pv;
  v22 = *(unsigned __int16 *)pv;
  v23 = *((unsigned __int16 *)pv + 1);
  if ( (_WORD)v22 )
  {
    if ( byte_1800DC8D3 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 17), 41, v86, v22);
    v24 = (__int64 *)CallStackTracing::s_wpInstance;
    v17 = -1072875852;
    AACLevel = -1072875852;
    if ( !CallStackTracing::s_wpInstance )
    {
      v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v15, v22);
      CallStackTracing::s_wpInstance = v25;
      if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
      {
        v24 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v24 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v24 + 8) )
    {
      v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
      if ( *((_DWORD *)v26 + 499) != -1072875852 )
        CallStackContext::TraceFailure(v26, "MF::DLNA::CheckAACAudioObjectType", 7201, -1072875852);
    }
    if ( !g_wppLevels )
      goto LABEL_228;
    v20 = 42;
    goto LABEL_227;
  }
  v27 = *((unsigned __int16 *)pv + 2);
  v28 = v86 - 12;
  v29 = 252;
  v30 = 0;
  v31 = 0;
  if ( (unsigned __int16)(v23 - 1) > 0xFCu && (unsigned __int16)v23 < 0x100u )
  {
LABEL_75:
    if ( (_WORD)v27 )
    {
      if ( byte_1800DC8D3 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 17), 48, v15, v27);
      v39 = (__int64 *)CallStackTracing::s_wpInstance;
      v17 = -1072875852;
      AACLevel = -1072875852;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v15, v22);
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
        v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
        if ( *((_DWORD *)v41 + 499) != -1072875852 )
          CallStackContext::TraceFailure(v41, "MF::DLNA::CheckAACAudioObjectType", 7273, -1072875852);
      }
      if ( !g_wppLevels )
        goto LABEL_228;
      v20 = 49;
      goto LABEL_227;
    }
    v42 = 0;
    v84 = 0;
    v87 = 0;
    if ( !v28
      || (int)CAACAudioSpecificConfig::ParseData((CAACAudioSpecificConfig *)v81, v28, (const unsigned __int8 *)pv + 12) < 0 )
    {
      v47 = v30;
      v46 = v31;
      goto LABEL_117;
    }
    v43 = (unsigned int)v30 | HIDWORD(v82);
    v44 = HIDWORD(v81[0]);
    v45 = v31 | v83;
    switch ( HIDWORD(v81[0]) )
    {
      case 2:
        v42 = 1;
        goto LABEL_92;
      case 4:
        v84 = 1;
        goto LABEL_92;
      case 0x16:
        v87 = 1;
        goto LABEL_92;
    }
    if ( (_DWORD)v43 || (_DWORD)v45 )
    {
LABEL_92:
      v46 = v31;
      v47 = v30;
      v30 |= HIDWORD(v82);
      v31 |= v83;
      if ( !v4 && !v47 && !v46 )
      {
        if ( (_DWORD)v45 )
          v46 = 1;
        else
          v47 = v43 != 0;
      }
LABEL_117:
      v51 = v79 & 0x1000000;
      v52 = v79 & 0x2000000;
      v53 = v79 & 0x4000000;
      if ( (*v85 & 0x20000000) == 0 || v47 )
      {
        if ( (*v85 & 0x40000000) == 0 || v46 )
        {
          if ( !v42 || (_DWORD)v51 )
          {
            if ( !v30 || (_DWORD)v52 )
            {
              if ( !v31 || (_DWORD)v53 )
              {
                if ( !v84 || (v79 & 0x8000000) != 0 )
                {
                  if ( !v87 || (v79 & 0x10000000) != 0 )
                    goto LABEL_228;
                  if ( byte_1800DC8D3 )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 64, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
                  v72 = (__int64 *)CallStackTracing::s_wpInstance;
                  v17 = -1072863756;
                  AACLevel = -1072863756;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                    CallStackTracing::s_wpInstance = v73;
                    if ( v73
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v73 + 8LL))(v73, 2032) )
                    {
                      v72 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v72 = &qword_1800DBF70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                    }
                  }
                  if ( *((_BYTE *)v72 + 8) )
                  {
                    v74 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v72);
                    if ( *((_DWORD *)v74 + 499) != -1072863756 )
                      CallStackContext::TraceFailure(v74, "MF::DLNA::CheckAACAudioObjectType", 7364, -1072863756);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_228;
                  v20 = 65;
                }
                else
                {
                  if ( byte_1800DC8D3 )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 62, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
                  v69 = (__int64 *)CallStackTracing::s_wpInstance;
                  v17 = -1072863756;
                  AACLevel = -1072863756;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                    CallStackTracing::s_wpInstance = v70;
                    if ( v70
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
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
                    if ( *((_DWORD *)v71 + 499) != -1072863756 )
                      CallStackContext::TraceFailure(v71, "MF::DLNA::CheckAACAudioObjectType", 7358, -1072863756);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_228;
                  v20 = 63;
                }
              }
              else
              {
                if ( byte_1800DC8D3 )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 60, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
                v66 = (__int64 *)CallStackTracing::s_wpInstance;
                v17 = -1072863756;
                AACLevel = -1072863756;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                  CallStackTracing::s_wpInstance = v67;
                  if ( v67
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
                  {
                    v66 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v66 = &qword_1800DBF70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                  }
                }
                if ( *((_BYTE *)v66 + 8) )
                {
                  v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
                  if ( *((_DWORD *)v68 + 499) != -1072863756 )
                    CallStackContext::TraceFailure(v68, "MF::DLNA::CheckAACAudioObjectType", 7352, -1072863756);
                }
                if ( !g_wppLevels )
                  goto LABEL_228;
                v20 = 61;
              }
            }
            else
            {
              if ( byte_1800DC8D3 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 58, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
              v63 = (__int64 *)CallStackTracing::s_wpInstance;
              v17 = -1072863756;
              AACLevel = -1072863756;
              if ( !CallStackTracing::s_wpInstance )
              {
                v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                CallStackTracing::s_wpInstance = v64;
                if ( v64
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
                {
                  v63 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v63 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                }
              }
              if ( *((_BYTE *)v63 + 8) )
              {
                v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
                if ( *((_DWORD *)v65 + 499) != -1072863756 )
                  CallStackContext::TraceFailure(v65, "MF::DLNA::CheckAACAudioObjectType", 7346, -1072863756);
              }
              if ( !g_wppLevels )
                goto LABEL_228;
              v20 = 59;
            }
          }
          else
          {
            if ( byte_1800DC8D3 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 56, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
            v60 = (__int64 *)CallStackTracing::s_wpInstance;
            v17 = -1072863756;
            AACLevel = -1072863756;
            if ( !CallStackTracing::s_wpInstance )
            {
              v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
              CallStackTracing::s_wpInstance = v61;
              if ( v61
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
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
              v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
              if ( *((_DWORD *)v62 + 499) != -1072863756 )
                CallStackContext::TraceFailure(v62, "MF::DLNA::CheckAACAudioObjectType", 7340, -1072863756);
            }
            if ( !g_wppLevels )
              goto LABEL_228;
            v20 = 57;
          }
        }
        else
        {
          if ( byte_1800DC8D3 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 54, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
          v57 = (__int64 *)CallStackTracing::s_wpInstance;
          v17 = -1072863756;
          AACLevel = -1072863756;
          if ( !CallStackTracing::s_wpInstance )
          {
            v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
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
            if ( *((_DWORD *)v59 + 499) != -1072863756 )
              CallStackContext::TraceFailure(v59, "MF::DLNA::CheckAACAudioObjectType", 7334, -1072863756);
          }
          if ( !g_wppLevels )
            goto LABEL_228;
          v20 = 55;
        }
      }
      else
      {
        if ( byte_1800DC8D3 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 52, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
        v54 = (__int64 *)CallStackTracing::s_wpInstance;
        v17 = -1072863756;
        AACLevel = -1072863756;
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
        if ( *((_BYTE *)v54 + 8) )
        {
          v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
          if ( *((_DWORD *)v56 + 499) != -1072863756 )
            CallStackContext::TraceFailure(v56, "MF::DLNA::CheckAACAudioObjectType", 7328, -1072863756);
        }
        if ( !g_wppLevels )
          goto LABEL_228;
        v20 = 53;
      }
      goto LABEL_227;
    }
    if ( byte_1800DC8D3 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 17), 50, v43, HIDWORD(v81[0]));
    v48 = (__int64 *)CallStackTracing::s_wpInstance;
    v17 = -1072863756;
    AACLevel = -1072863756;
    if ( !CallStackTracing::s_wpInstance )
    {
      v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v43, v44);
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
      if ( *((_DWORD *)v50 + 499) != -1072863756 )
        CallStackContext::TraceFailure(v50, "MF::DLNA::CheckAACAudioObjectType", 7304, -1072863756);
    }
    if ( !g_wppLevels )
      goto LABEL_228;
    v20 = 51;
LABEL_227:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, 0, v17);
    goto LABEL_228;
  }
  LOWORD(v15) = 3;
  if ( (unsigned __int16)(v23 - 1) > 3u && (unsigned __int16)(v23 - 5) > 3u && (unsigned __int16)(v23 - 14) > 7u )
  {
    if ( (unsigned __int16)(v23 - 40) > 3u )
    {
      if ( (unsigned __int16)(v23 - 44) > 3u )
      {
        if ( (unsigned __int16)(v23 - 48) > 3u )
        {
          if ( (unsigned __int8)byte_1800DC8D3 >= 0x10u )
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 17), 43, v15, *((unsigned __int16 *)pv + 1));
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
          v17 = -1072863756;
          AACLevel = -1072863756;
          if ( !CallStackTracing::s_wpInstance )
          {
            v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v15, v22);
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
            v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
            if ( *((_DWORD *)v37 + 499) != -1072863756 )
              CallStackContext::TraceFailure(v37, "MF::DLNA::CheckAACAudioObjectType", 7255, -1072863756);
          }
          if ( !g_wppLevels )
            goto LABEL_228;
          v20 = 44;
          goto LABEL_227;
        }
        v31 = 1;
      }
      else
      {
        v30 = 1;
      }
    }
    else
    {
      v4 = 1;
    }
  }
  AACLevel = MF::DLNA::GetAACLevel(v23, &v84);
  if ( AACLevel >= 0 )
  {
    v22 = (unsigned int)v85[1];
    if ( v84 < (unsigned int)v22 || v84 > v85[2] )
    {
      if ( (unsigned __int8)byte_1800DC8D3 >= 0x10u )
        WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 17), 46);
      v75 = (__int64 *)CallStackTracing::s_wpInstance;
      v17 = -1072863756;
      AACLevel = -1072863756;
      if ( !CallStackTracing::s_wpInstance )
      {
        v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v15, v22);
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
        v77 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v75);
        if ( *((_DWORD *)v77 + 499) != -1072863756 )
          CallStackContext::TraceFailure(v77, "MF::DLNA::CheckAACAudioObjectType", 7266, -1072863756);
      }
      if ( !g_wppLevels )
        goto LABEL_228;
      v20 = 47;
      goto LABEL_227;
    }
    goto LABEL_75;
  }
  v33 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v15, v32);
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
  if ( *((_BYTE *)v33 + 8) )
  {
    v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
    if ( *((_DWORD *)v38 + 499) != AACLevel )
      CallStackContext::TraceFailure(v38, "MF::DLNA::CheckAACAudioObjectType", 7258, AACLevel);
  }
  if ( g_wppLevels )
  {
    v14 = 45;
    goto LABEL_12;
  }
LABEL_228:
  CoTaskMemFree(pv);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v84);
  return (unsigned int)AACLevel;
}

```

## disassembly

```asm
0x18005ff50  mov     [rsp-40h+arg_8], rdx
0x18005ff55  push    rbp
0x18005ff56  push    rbx
0x18005ff57  push    rsi
0x18005ff58  push    rdi
0x18005ff59  push    r12
0x18005ff5b  push    r13
0x18005ff5d  push    r14
0x18005ff5f  push    r15
0x18005ff61  mov     rbp, rsp
0x18005ff64  sub     rsp, 78h
0x18005ff68  mov     rdi, rdx
0x18005ff6b  lea     r14, aMfDlnaCheckaac; "MF::DLNA::CheckAACAudioObjectType"
0x18005ff72  mov     rbx, rcx
0x18005ff75  mov     rdx, r14; char *
0x18005ff78  mov     r8d, 1BF8h; int
0x18005ff7e  lea     rcx, [rbp+arg_0]; this
0x18005ff82  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005ff87  mov     eax, [rdi]
0x18005ff89  lea     r9, [rbp+arg_10]
0x18005ff8d  xor     r13d, r13d
0x18005ff90  mov     [rbp+var_48], eax
0x18005ff93  mov     rax, [rbx]
0x18005ff96  lea     r8, [rbp+pv]
0x18005ff9a  lea     rdx, MF_MT_USER_DATA
0x18005ffa1  mov     [rbp+var_38], r13
0x18005ffa5  mov     rcx, rbx
0x18005ffa8  mov     [rbp+var_30], r13
0x18005ffac  mov     [rbp+var_28], r13
0x18005ffb0  mov     rax, [rax+80h]
0x18005ffb7  mov     [rbp+var_20], r13
0x18005ffbb  mov     [rbp+var_18], r13d
0x18005ffbf  mov     [rbp+arg_0], r13d
0x18005ffc3  mov     [rbp+pv], r13
0x18005ffc7  mov     [rbp+arg_10], r13d
0x18005ffcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ffd0  mov     esi, eax
0x18005ffd2  test    eax, eax
0x18005ffd4  jns     loc_180060072
0x18005ffda  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ffe1  test    rcx, rcx
0x18005ffe4  jnz     short loc_18006002D
0x18005ffe6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005ffed  nop     dword ptr [rax+rax+00h]
0x18005fff2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fff9  mov     rcx, rax
0x18005fffc  test    rax, rax
0x18005ffff  jz      short loc_18006001F
0x180060001  mov     rax, [rax]
0x180060004  mov     edx, 7F0h
0x180060009  mov     rax, [rax+8]
0x18006000d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060012  test    eax, eax
0x180060014  jz      short loc_18006001F
0x180060016  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006001d  jmp     short loc_18006002D
0x18006001f  lea     rcx, qword_1800DBF70; this
0x180060026  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006002d  cmp     [rcx+8], r13b
0x180060031  jz      short loc_180060054
0x180060033  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180060038  cmp     [rax+7CCh], esi
0x18006003e  jz      short loc_180060054
0x180060040  mov     r9d, esi; int
0x180060043  mov     r8d, 1C12h; int
0x180060049  mov     rdx, r14; char *
0x18006004c  mov     rcx, rax; this
0x18006004f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060054  mov     edi, 1
0x180060059  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180060060  jb      loc_180060D54
0x180060066  lea     edx, [rdi+25h]
0x180060069  mov     [rsp+78h+var_58], esi
0x18006006d  jmp     loc_180060D3A
0x180060072  mov     r8d, [rbp+arg_10]
0x180060076  cmp     r8d, 0Ch
0x18006007a  jnb     loc_18006013F
0x180060080  mov     edi, 1
0x180060085  cmp     cs:byte_1800DC8D3, dil
0x18006008c  jb      short loc_1800600A7
0x18006008e  mov     rcx, cs:WPP_GLOBAL_Control
0x180060095  lea     edx, [rdi+26h]
0x180060098  mov     r9d, r8d
0x18006009b  mov     rcx, [rcx+88h]
0x1800600a2  call    WPP_SF_D
0x1800600a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800600ae  mov     ebx, 0C00D36B4h
0x1800600b3  mov     esi, ebx
0x1800600b5  test    rcx, rcx
0x1800600b8  jnz     short loc_180060101
0x1800600ba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800600c1  nop     dword ptr [rax+rax+00h]
0x1800600c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800600cd  mov     rcx, rax
0x1800600d0  test    rax, rax
0x1800600d3  jz      short loc_1800600F3
0x1800600d5  mov     rax, [rax]
0x1800600d8  mov     edx, 7F0h
0x1800600dd  mov     rax, [rax+8]
0x1800600e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800600e6  test    eax, eax
0x1800600e8  jz      short loc_1800600F3
0x1800600ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800600f1  jmp     short loc_180060101
0x1800600f3  lea     rcx, qword_1800DBF70; this
0x1800600fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180060101  cmp     [rcx+8], r13b
0x180060105  jz      short loc_180060128
0x180060107  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006010c  cmp     [rax+7CCh], ebx
0x180060112  jz      short loc_180060128
0x180060114  mov     r9d, ebx; int
0x180060117  mov     r8d, 1C17h; int
0x18006011d  mov     rdx, r14; char *
0x180060120  mov     rcx, rax; this
0x180060123  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060128  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18006012f  jb      loc_180060D54
0x180060135  mov     edx, 28h ; '('
0x18006013a  jmp     loc_180060D36
0x18006013f  mov     rdx, [rbp+pv]
0x180060143  movzx   r9d, word ptr [rdx]
0x180060147  movzx   ecx, word ptr [rdx+2]
0x18006014b  cmp     r13w, r9w
0x18006014f  jz      loc_180060211
0x180060155  mov     edi, 1
0x18006015a  cmp     cs:byte_1800DC8D3, dil
0x180060161  jb      short loc_180060179
0x180060163  mov     rcx, cs:WPP_GLOBAL_Control
0x18006016a  lea     edx, [rdi+28h]
0x18006016d  mov     rcx, [rcx+88h]
0x180060174  call    WPP_SF_D
0x180060179  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060180  mov     ebx, 0C00D36B4h
0x180060185  mov     esi, ebx
0x180060187  test    rcx, rcx
0x18006018a  jnz     short loc_1800601D3
0x18006018c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180060193  nop     dword ptr [rax+rax+00h]
0x180060198  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006019f  mov     rcx, rax
0x1800601a2  test    rax, rax
0x1800601a5  jz      short loc_1800601C5
0x1800601a7  mov     rax, [rax]
0x1800601aa  mov     edx, 7F0h
0x1800601af  mov     rax, [rax+8]
0x1800601b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800601b8  test    eax, eax
0x1800601ba  jz      short loc_1800601C5
0x1800601bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800601c3  jmp     short loc_1800601D3
0x1800601c5  lea     rcx, qword_1800DBF70; this
0x1800601cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800601d3  cmp     [rcx+8], r13b
0x1800601d7  jz      short loc_1800601FA
0x1800601d9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800601de  cmp     [rax+7CCh], ebx
0x1800601e4  jz      short loc_1800601FA
0x1800601e6  mov     r9d, ebx; int
0x1800601e9  mov     r8d, 1C21h; int
0x1800601ef  mov     rdx, r14; char *
0x1800601f2  mov     rcx, rax; this
0x1800601f5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800601fa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180060201  jb      loc_180060D54
0x180060207  mov     edx, 2Ah ; '*'
0x18006020c  jmp     loc_180060D36
0x180060211  movzx   r15d, word ptr [rdx+4]
0x180060216  lea     r12d, [r8-0Ch]
0x18006021a  mov     edi, 1
0x18006021f  movzx   eax, cx
0x180060222  sub     ax, di
0x180060225  mov     edx, 0FCh
0x18006022a  mov     r14d, r13d
0x18006022d  mov     ebx, r13d
0x180060230  lea     r10d, [rdi+2Fh]
0x180060234  cmp     ax, dx
0x180060237  jbe     short loc_180060245
0x180060239  lea     eax, [rdx+4]
0x18006023c  cmp     cx, ax
0x18006023f  jb      loc_180060430
0x180060245  movzx   eax, cx
0x180060248  mov     r8w, 3
0x18006024d  sub     ax, di
0x180060250  cmp     ax, r8w
0x180060254  jbe     short loc_180060274
0x180060256  lea     eax, [rcx-5]
0x180060259  cmp     ax, r8w
0x18006025d  jbe     short loc_180060274
0x18006025f  lea     eax, [rcx-0Eh]
0x180060262  cmp     ax, 7
0x180060266  jbe     short loc_180060274
0x180060268  lea     eax, [rcx-28h]
0x18006026b  cmp     ax, r8w
0x18006026f  ja      short loc_1800602DB
0x180060271  mov     r13d, edi
0x180060274  lea     rdx, [rbp+arg_0]
0x180060278  call    MF__DLNA__GetAACLevel
0x18006027d  mov     esi, eax
0x18006027f  test    eax, eax
0x180060281  jns     loc_18006040D
0x180060287  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006028e  test    rcx, rcx
0x180060291  jnz     loc_1800603CB
0x180060297  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006029e  nop     dword ptr [rax+rax+00h]
0x1800602a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800602aa  mov     rcx, rax
0x1800602ad  test    rax, rax
0x1800602b0  jz      loc_1800603BD
0x1800602b6  mov     rax, [rax]
0x1800602b9  mov     edx, 7F0h
0x1800602be  mov     rax, [rax+8]
0x1800602c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800602c7  test    eax, eax
0x1800602c9  jz      loc_1800603BD
0x1800602cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800602d6  jmp     loc_1800603CB
0x1800602db  lea     eax, [rcx-2Ch]
0x1800602de  cmp     ax, r8w
0x1800602e2  ja      short loc_1800602E9
0x1800602e4  mov     r14d, edi
0x1800602e7  jmp     short loc_180060274
0x1800602e9  movzx   eax, cx
0x1800602ec  sub     ax, r10w
0x1800602f0  cmp     ax, r8w
0x1800602f4  ja      short loc_1800602FD
0x1800602f6  mov     ebx, edi
0x1800602f8  jmp     loc_180060274
0x1800602fd  cmp     cs:byte_1800DC8D3, 10h
0x180060304  jb      short loc_180060321
0x180060306  mov     r9d, ecx
0x180060309  mov     edx, 2Bh ; '+'
0x18006030e  mov     rcx, cs:WPP_GLOBAL_Control
0x180060315  mov     rcx, [rcx+88h]
0x18006031c  call    WPP_SF_D
0x180060321  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060328  mov     ebx, 0C00D65F4h
0x18006032d  mov     esi, ebx
0x18006032f  test    rcx, rcx
0x180060332  jnz     short loc_18006037B
0x180060334  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006033b  nop     dword ptr [rax+rax+00h]
0x180060340  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180060347  mov     rcx, rax
0x18006034a  test    rax, rax
0x18006034d  jz      short loc_18006036D
0x18006034f  mov     rax, [rax]
0x180060352  mov     edx, 7F0h
0x180060357  mov     rax, [rax+8]
0x18006035b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060360  test    eax, eax
0x180060362  jz      short loc_18006036D
0x180060364  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006036b  jmp     short loc_18006037B
0x18006036d  lea     rcx, qword_1800DBF70; this
0x180060374  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006037b  cmp     [rcx+8], r13b
0x18006037f  jz      short loc_1800603A6
0x180060381  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180060386  cmp     [rax+7CCh], ebx
0x18006038c  jz      short loc_1800603A6
0x18006038e  mov     r9d, ebx; int
0x180060391  lea     rdx, aMfDlnaCheckaac; "MF::DLNA::CheckAACAudioObjectType"
0x180060398  mov     r8d, 1C57h; int
0x18006039e  mov     rcx, rax; this
0x1800603a1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800603a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800603ad  jb      loc_180060D54
0x1800603b3  mov     edx, 2Ch ; ','
0x1800603b8  jmp     loc_180060D36
0x1800603bd  lea     rcx, qword_1800DBF70; this
0x1800603c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800603cb  cmp     byte ptr [rcx+8], 0
0x1800603cf  jz      short loc_1800603F6
0x1800603d1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800603d6  cmp     [rax+7CCh], esi
0x1800603dc  jz      short loc_1800603F6
0x1800603de  mov     r9d, esi; int
0x1800603e1  lea     rdx, aMfDlnaCheckaac; "MF::DLNA::CheckAACAudioObjectType"
0x1800603e8  mov     r8d, 1C5Ah; int
0x1800603ee  mov     rcx, rax; this
0x1800603f1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800603f6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800603fd  jb      loc_180060D54
0x180060403  mov     edx, 2Dh ; '-'
0x180060408  jmp     loc_180060069
0x18006040d  mov     rcx, [rbp+arg_8]
0x180060411  mov     eax, [rbp+arg_0]
0x180060414  mov     r9d, [rcx+4]
0x180060418  cmp     eax, r9d
0x18006041b  jb      loc_180060C77
0x180060421  cmp     eax, [rcx+8]
0x180060424  ja      loc_180060C77
0x18006042a  mov     r10d, 30h ; '0'
0x180060430  xor     eax, eax
0x180060432  cmp     ax, r15w
0x180060436  jz      loc_1800604FA
0x18006043c  cmp     cs:byte_1800DC8D3, dil
0x180060443  jb      short loc_18006045E
  ... truncated ...
```
