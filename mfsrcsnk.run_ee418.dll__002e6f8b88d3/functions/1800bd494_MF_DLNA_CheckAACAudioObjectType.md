# MF::DLNA::CheckAACAudioObjectType

- ea: `0x1800bd494`
- end: `0x1800be284`
- name: `MF::DLNA::CheckAACAudioObjectType`
- size: `3568`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180170ea0`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180073b14`
- `0x18009b8bc`
- `0x1800bd494`
- `0x1800c2164`
- `0x180115a1c`
- `0x18011e37c`
- `0x1801718ec`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd52a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd5ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd6d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd7d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd872`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd9b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bdb0e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bdc26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bdcf7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bddc6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bde95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bdf63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800be033`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800be104`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800be1c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd52a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd5ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd6d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd7d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd872`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd9b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bdb0e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bdc26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bdcf7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bddc6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bde95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bdf63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800be033`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800be104`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800be1c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800be262`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800be262`

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
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  wchar_t *v16; // rcx
  int v17; // ebx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  LPVOID v21; // rdx
  __int64 v22; // r9
  __int64 v23; // rcx
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  unsigned int v27; // r15d
  unsigned int v28; // r12d
  __int64 v29; // rdx
  int v30; // r14d
  int v31; // ebx
  __int64 v32; // r9
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  wchar_t *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  struct CallStackContext *v38; // rax
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  int v42; // r15d
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // rdx
  int v46; // ecx
  BOOL v47; // eax
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  wchar_t *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  wchar_t *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  wchar_t *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  wchar_t *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  wchar_t *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  wchar_t *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  wchar_t *v72; // rcx
  CallStackTracing *v73; // rax
  struct CallStackContext *v74; // rax
  wchar_t *v75; // rcx
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
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v9, v10);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
    if ( byte_1801B110B )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 17), 39, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, v86);
    v16 = (wchar_t *)CallStackTracing::s_wpInstance;
    v17 = -1072875852;
    AACLevel = -1072875852;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v15, v10);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v16 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
    if ( byte_1801B110B )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 17), 41, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, v22);
    v24 = (wchar_t *)CallStackTracing::s_wpInstance;
    v17 = -1072875852;
    AACLevel = -1072875852;
    if ( !CallStackTracing::s_wpInstance )
    {
      v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v15, v22);
      CallStackTracing::s_wpInstance = v25;
      if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
      {
        v24 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v24 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      if ( byte_1801B110B )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 17), 48, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, v27);
      v39 = (wchar_t *)CallStackTracing::s_wpInstance;
      v17 = -1072875852;
      AACLevel = -1072875852;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v15, v22);
        CallStackTracing::s_wpInstance = v40;
        if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
        {
          v39 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v39 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                  if ( byte_1801B110B )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 64, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
                  v72 = (wchar_t *)CallStackTracing::s_wpInstance;
                  v17 = -1072863756;
                  AACLevel = -1072863756;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                    CallStackTracing::s_wpInstance = v73;
                    if ( v73
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v73 + 8LL))(v73, 2032) )
                    {
                      v72 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v72 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                  if ( byte_1801B110B )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 62, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
                  v69 = (wchar_t *)CallStackTracing::s_wpInstance;
                  v17 = -1072863756;
                  AACLevel = -1072863756;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                    CallStackTracing::s_wpInstance = v70;
                    if ( v70
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
                    {
                      v69 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v69 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                if ( byte_1801B110B )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 60, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
                v66 = (wchar_t *)CallStackTracing::s_wpInstance;
                v17 = -1072863756;
                AACLevel = -1072863756;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                  CallStackTracing::s_wpInstance = v67;
                  if ( v67
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
                  {
                    v66 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v66 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              if ( byte_1801B110B )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 58, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
              v63 = (wchar_t *)CallStackTracing::s_wpInstance;
              v17 = -1072863756;
              AACLevel = -1072863756;
              if ( !CallStackTracing::s_wpInstance )
              {
                v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                CallStackTracing::s_wpInstance = v64;
                if ( v64
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
                {
                  v63 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v63 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            if ( byte_1801B110B )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 56, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
            v60 = (wchar_t *)CallStackTracing::s_wpInstance;
            v17 = -1072863756;
            AACLevel = -1072863756;
            if ( !CallStackTracing::s_wpInstance )
            {
              v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
              CallStackTracing::s_wpInstance = v61;
              if ( v61
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
              {
                v60 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v60 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          if ( byte_1801B110B )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 54, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
          v57 = (wchar_t *)CallStackTracing::s_wpInstance;
          v17 = -1072863756;
          AACLevel = -1072863756;
          if ( !CallStackTracing::s_wpInstance )
          {
            v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
            CallStackTracing::s_wpInstance = v58;
            if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
            {
              v57 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v57 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        if ( byte_1801B110B )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 52, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
        v54 = (wchar_t *)CallStackTracing::s_wpInstance;
        v17 = -1072863756;
        AACLevel = -1072863756;
        if ( !CallStackTracing::s_wpInstance )
        {
          v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
          CallStackTracing::s_wpInstance = v55;
          if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
          {
            v54 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v54 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
    if ( byte_1801B110B )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        50,
        &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
        HIDWORD(v81[0]));
    v48 = (wchar_t *)CallStackTracing::s_wpInstance;
    v17 = -1072863756;
    AACLevel = -1072863756;
    if ( !CallStackTracing::s_wpInstance )
    {
      v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v43, v44);
      CallStackTracing::s_wpInstance = v49;
      if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
      {
        v48 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v48 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          if ( (unsigned __int8)byte_1801B110B >= 0x10u )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 17),
              43,
              &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
              *((unsigned __int16 *)pv + 1));
          v35 = (wchar_t *)CallStackTracing::s_wpInstance;
          v17 = -1072863756;
          AACLevel = -1072863756;
          if ( !CallStackTracing::s_wpInstance )
          {
            v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v15, v22);
            CallStackTracing::s_wpInstance = v36;
            if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
            {
              v35 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v35 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      if ( (unsigned __int8)byte_1801B110B >= 0x10u )
        WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 17), 46);
      v75 = (wchar_t *)CallStackTracing::s_wpInstance;
      v17 = -1072863756;
      AACLevel = -1072863756;
      if ( !CallStackTracing::s_wpInstance )
      {
        v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v15, v22);
        CallStackTracing::s_wpInstance = v76;
        if ( v76 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(v76, 2032) )
        {
          v75 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v75 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
  v33 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v15, v32);
    CallStackTracing::s_wpInstance = v34;
    if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
    {
      v33 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v33 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x1800bd494  mov     [rsp-40h+arg_8], rdx
0x1800bd499  push    rbp
0x1800bd49a  push    rbx
0x1800bd49b  push    rsi
0x1800bd49c  push    rdi
0x1800bd49d  push    r12
0x1800bd49f  push    r13
0x1800bd4a1  push    r14
0x1800bd4a3  push    r15
0x1800bd4a5  mov     rbp, rsp
0x1800bd4a8  sub     rsp, 78h
0x1800bd4ac  mov     rdi, rdx
0x1800bd4af  lea     r14, aMfDlnaCheckaac; "MF::DLNA::CheckAACAudioObjectType"
0x1800bd4b6  mov     rbx, rcx
0x1800bd4b9  mov     rdx, r14; char *
0x1800bd4bc  mov     r8d, 1BF8h; int
0x1800bd4c2  lea     rcx, [rbp+arg_0]; this
0x1800bd4c6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800bd4cb  mov     eax, [rdi]
0x1800bd4cd  lea     r9, [rbp+arg_10]
0x1800bd4d1  xor     r13d, r13d
0x1800bd4d4  mov     [rbp+var_48], eax
0x1800bd4d7  mov     rax, [rbx]
0x1800bd4da  lea     r8, [rbp+pv]
0x1800bd4de  lea     rdx, MF_MT_USER_DATA
0x1800bd4e5  mov     [rbp+var_38], r13
0x1800bd4e9  mov     rcx, rbx
0x1800bd4ec  mov     [rbp+var_30], r13
0x1800bd4f0  mov     [rbp+var_28], r13
0x1800bd4f4  mov     rax, [rax+80h]
0x1800bd4fb  mov     [rbp+var_20], r13
0x1800bd4ff  mov     [rbp+var_18], r13d
0x1800bd503  mov     [rbp+arg_0], r13d
0x1800bd507  mov     [rbp+pv], r13
0x1800bd50b  mov     [rbp+arg_10], r13d
0x1800bd50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd514  mov     esi, eax
0x1800bd516  test    eax, eax
0x1800bd518  jns     loc_1800BD5B0
0x1800bd51e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd525  test    rcx, rcx
0x1800bd528  jnz     short loc_1800BD56B
0x1800bd52a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bd530  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd537  mov     rcx, rax
0x1800bd53a  test    rax, rax
0x1800bd53d  jz      short loc_1800BD55D
0x1800bd53f  mov     rax, [rax]
0x1800bd542  mov     edx, 7F0h
0x1800bd547  mov     rax, [rax+8]
0x1800bd54b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd550  test    eax, eax
0x1800bd552  jz      short loc_1800BD55D
0x1800bd554  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd55b  jmp     short loc_1800BD56B
0x1800bd55d  lea     rcx, qword_1801B07E0; this
0x1800bd564  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd56b  cmp     [rcx+8], r13b
0x1800bd56f  jz      short loc_1800BD592
0x1800bd571  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bd576  cmp     [rax+7CCh], esi
0x1800bd57c  jz      short loc_1800BD592
0x1800bd57e  mov     r9d, esi; int
0x1800bd581  mov     r8d, 1C12h; int
0x1800bd587  mov     rdx, r14; char *
0x1800bd58a  mov     rcx, rax; this
0x1800bd58d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bd592  mov     edi, 1
0x1800bd597  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800bd59e  jb      loc_1800BE25E
0x1800bd5a4  lea     edx, [rdi+25h]
0x1800bd5a7  mov     [rsp+78h+var_58], esi
0x1800bd5ab  jmp     loc_1800BE244
0x1800bd5b0  mov     r8d, [rbp+arg_10]
0x1800bd5b4  cmp     r8d, 0Ch
0x1800bd5b8  jnb     loc_1800BD67E
0x1800bd5be  mov     edi, 1
0x1800bd5c3  cmp     cs:byte_1801B110B, dil
0x1800bd5ca  jb      short loc_1800BD5EC
0x1800bd5cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd5d3  lea     edx, [rdi+26h]
0x1800bd5d6  mov     r9d, r8d
0x1800bd5d9  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x1800bd5e0  mov     rcx, [rcx+88h]
0x1800bd5e7  call    WPP_SF_d
0x1800bd5ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd5f3  mov     ebx, 0C00D36B4h
0x1800bd5f8  mov     esi, ebx
0x1800bd5fa  test    rcx, rcx
0x1800bd5fd  jnz     short loc_1800BD640
0x1800bd5ff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bd605  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd60c  mov     rcx, rax
0x1800bd60f  test    rax, rax
0x1800bd612  jz      short loc_1800BD632
0x1800bd614  mov     rax, [rax]
0x1800bd617  mov     edx, 7F0h
0x1800bd61c  mov     rax, [rax+8]
0x1800bd620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd625  test    eax, eax
0x1800bd627  jz      short loc_1800BD632
0x1800bd629  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd630  jmp     short loc_1800BD640
0x1800bd632  lea     rcx, qword_1801B07E0; this
0x1800bd639  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd640  cmp     [rcx+8], r13b
0x1800bd644  jz      short loc_1800BD667
0x1800bd646  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bd64b  cmp     [rax+7CCh], ebx
0x1800bd651  jz      short loc_1800BD667
0x1800bd653  mov     r9d, ebx; int
0x1800bd656  mov     r8d, 1C17h; int
0x1800bd65c  mov     rdx, r14; char *
0x1800bd65f  mov     rcx, rax; this
0x1800bd662  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bd667  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800bd66e  jb      loc_1800BE25E
0x1800bd674  mov     edx, 28h ; '('
0x1800bd679  jmp     loc_1800BE240
0x1800bd67e  mov     rdx, [rbp+pv]
0x1800bd682  movzx   r9d, word ptr [rdx]
0x1800bd686  movzx   ecx, word ptr [rdx+2]
0x1800bd68a  cmp     r13w, r9w
0x1800bd68e  jz      loc_1800BD751
0x1800bd694  mov     edi, 1
0x1800bd699  cmp     cs:byte_1801B110B, dil
0x1800bd6a0  jb      short loc_1800BD6BF
0x1800bd6a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd6a9  lea     edx, [rdi+28h]
0x1800bd6ac  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x1800bd6b3  mov     rcx, [rcx+88h]
0x1800bd6ba  call    WPP_SF_d
0x1800bd6bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd6c6  mov     ebx, 0C00D36B4h
0x1800bd6cb  mov     esi, ebx
0x1800bd6cd  test    rcx, rcx
0x1800bd6d0  jnz     short loc_1800BD713
0x1800bd6d2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bd6d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd6df  mov     rcx, rax
0x1800bd6e2  test    rax, rax
0x1800bd6e5  jz      short loc_1800BD705
0x1800bd6e7  mov     rax, [rax]
0x1800bd6ea  mov     edx, 7F0h
0x1800bd6ef  mov     rax, [rax+8]
0x1800bd6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd6f8  test    eax, eax
0x1800bd6fa  jz      short loc_1800BD705
0x1800bd6fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd703  jmp     short loc_1800BD713
0x1800bd705  lea     rcx, qword_1801B07E0; this
0x1800bd70c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd713  cmp     [rcx+8], r13b
0x1800bd717  jz      short loc_1800BD73A
0x1800bd719  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bd71e  cmp     [rax+7CCh], ebx
0x1800bd724  jz      short loc_1800BD73A
0x1800bd726  mov     r9d, ebx; int
0x1800bd729  mov     r8d, 1C21h; int
0x1800bd72f  mov     rdx, r14; char *
0x1800bd732  mov     rcx, rax; this
0x1800bd735  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bd73a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800bd741  jb      loc_1800BE25E
0x1800bd747  mov     edx, 2Ah ; '*'
0x1800bd74c  jmp     loc_1800BE240
0x1800bd751  movzx   r15d, word ptr [rdx+4]
0x1800bd756  lea     r12d, [r8-0Ch]
0x1800bd75a  mov     edi, 1
0x1800bd75f  movzx   eax, cx
0x1800bd762  sub     ax, di
0x1800bd765  mov     edx, 0FCh
0x1800bd76a  mov     r14d, r13d
0x1800bd76d  mov     ebx, r13d
0x1800bd770  lea     r10d, [rdi+2Fh]
0x1800bd774  cmp     ax, dx
0x1800bd777  jbe     short loc_1800BD785
0x1800bd779  lea     eax, [rdx+4]
0x1800bd77c  cmp     cx, ax
0x1800bd77f  jb      loc_1800BD968
0x1800bd785  movzx   eax, cx
0x1800bd788  mov     r8w, 3
0x1800bd78d  sub     ax, di
0x1800bd790  cmp     ax, r8w
0x1800bd794  jbe     short loc_1800BD7B4
0x1800bd796  lea     eax, [rcx-5]
0x1800bd799  cmp     ax, r8w
0x1800bd79d  jbe     short loc_1800BD7B4
0x1800bd79f  lea     eax, [rcx-0Eh]
0x1800bd7a2  cmp     ax, 7
0x1800bd7a6  jbe     short loc_1800BD7B4
0x1800bd7a8  lea     eax, [rcx-28h]
0x1800bd7ab  cmp     ax, r8w
0x1800bd7af  ja      short loc_1800BD815
0x1800bd7b1  mov     r13d, edi
0x1800bd7b4  lea     rdx, [rbp+arg_0]
0x1800bd7b8  call    MF__DLNA__GetAACLevel
0x1800bd7bd  mov     esi, eax
0x1800bd7bf  test    eax, eax
0x1800bd7c1  jns     loc_1800BD945
0x1800bd7c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd7ce  test    rcx, rcx
0x1800bd7d1  jnz     loc_1800BD903
0x1800bd7d7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bd7dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd7e4  mov     rcx, rax
0x1800bd7e7  test    rax, rax
0x1800bd7ea  jz      loc_1800BD8F5
0x1800bd7f0  mov     rax, [rax]
0x1800bd7f3  mov     edx, 7F0h
0x1800bd7f8  mov     rax, [rax+8]
0x1800bd7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd801  test    eax, eax
0x1800bd803  jz      loc_1800BD8F5
0x1800bd809  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd810  jmp     loc_1800BD903
0x1800bd815  lea     eax, [rcx-2Ch]
0x1800bd818  cmp     ax, r8w
0x1800bd81c  ja      short loc_1800BD823
0x1800bd81e  mov     r14d, edi
0x1800bd821  jmp     short loc_1800BD7B4
0x1800bd823  movzx   eax, cx
0x1800bd826  sub     ax, r10w
0x1800bd82a  cmp     ax, r8w
0x1800bd82e  ja      short loc_1800BD834
0x1800bd830  mov     ebx, edi
0x1800bd832  jmp     short loc_1800BD7B4
0x1800bd834  cmp     cs:byte_1801B110B, 10h
0x1800bd83b  jb      short loc_1800BD85F
0x1800bd83d  mov     r9d, ecx
0x1800bd840  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x1800bd847  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd84e  mov     edx, 2Bh ; '+'
0x1800bd853  mov     rcx, [rcx+88h]
0x1800bd85a  call    WPP_SF_d
0x1800bd85f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd866  mov     ebx, 0C00D65F4h
0x1800bd86b  mov     esi, ebx
0x1800bd86d  test    rcx, rcx
0x1800bd870  jnz     short loc_1800BD8B3
0x1800bd872  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bd878  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd87f  mov     rcx, rax
0x1800bd882  test    rax, rax
0x1800bd885  jz      short loc_1800BD8A5
0x1800bd887  mov     rax, [rax]
0x1800bd88a  mov     edx, 7F0h
0x1800bd88f  mov     rax, [rax+8]
0x1800bd893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd898  test    eax, eax
0x1800bd89a  jz      short loc_1800BD8A5
0x1800bd89c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd8a3  jmp     short loc_1800BD8B3
0x1800bd8a5  lea     rcx, qword_1801B07E0; this
0x1800bd8ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd8b3  cmp     [rcx+8], r13b
0x1800bd8b7  jz      short loc_1800BD8DE
0x1800bd8b9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bd8be  cmp     [rax+7CCh], ebx
0x1800bd8c4  jz      short loc_1800BD8DE
0x1800bd8c6  mov     r9d, ebx; int
0x1800bd8c9  lea     rdx, aMfDlnaCheckaac; "MF::DLNA::CheckAACAudioObjectType"
0x1800bd8d0  mov     r8d, 1C57h; int
0x1800bd8d6  mov     rcx, rax; this
0x1800bd8d9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bd8de  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800bd8e5  jb      loc_1800BE25E
0x1800bd8eb  mov     edx, 2Ch ; ','
0x1800bd8f0  jmp     loc_1800BE240
0x1800bd8f5  lea     rcx, qword_1801B07E0; this
0x1800bd8fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd903  cmp     byte ptr [rcx+8], 0
0x1800bd907  jz      short loc_1800BD92E
0x1800bd909  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bd90e  cmp     [rax+7CCh], esi
0x1800bd914  jz      short loc_1800BD92E
0x1800bd916  mov     r9d, esi; int
0x1800bd919  lea     rdx, aMfDlnaCheckaac; "MF::DLNA::CheckAACAudioObjectType"
0x1800bd920  mov     r8d, 1C5Ah; int
0x1800bd926  mov     rcx, rax; this
0x1800bd929  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bd92e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800bd935  jb      loc_1800BE25E
0x1800bd93b  mov     edx, 2Dh ; '-'
0x1800bd940  jmp     loc_1800BD5A7
0x1800bd945  mov     rcx, [rbp+arg_8]
0x1800bd949  mov     eax, [rbp+arg_0]
0x1800bd94c  mov     r9d, [rcx+4]
0x1800bd950  cmp     eax, r9d
0x1800bd953  jb      loc_1800BE187
0x1800bd959  cmp     eax, [rcx+8]
0x1800bd95c  ja      loc_1800BE187
0x1800bd962  mov     r10d, 30h ; '0'
0x1800bd968  xor     eax, eax
0x1800bd96a  cmp     ax, r15w
0x1800bd96e  jz      loc_1800BDA33
0x1800bd974  cmp     cs:byte_1801B110B, dil
0x1800bd97b  jb      short loc_1800BD99D
0x1800bd97d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd984  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
  ... truncated ...
```
