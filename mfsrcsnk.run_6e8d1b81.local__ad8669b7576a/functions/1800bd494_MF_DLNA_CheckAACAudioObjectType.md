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
  wchar_t *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  wchar_t *v13; // rcx
  int v14; // ebx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  LPVOID v18; // rdx
  __int64 v19; // r9
  __int64 v20; // rcx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  unsigned int v24; // r15d
  unsigned int v25; // r12d
  __int64 v26; // rdx
  int v27; // r14d
  int v28; // ebx
  __int64 v29; // r8
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // r9
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  int v40; // r15d
  int v41; // r8d
  __int64 v42; // rdx
  int v43; // ecx
  BOOL v44; // eax
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  wchar_t *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  wchar_t *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  wchar_t *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  wchar_t *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  wchar_t *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  wchar_t *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  int v74; // [rsp+30h] [rbp-48h]
  LPVOID pv; // [rsp+38h] [rbp-40h] BYREF
  _QWORD v76[3]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v77; // [rsp+58h] [rbp-20h]
  unsigned int v78; // [rsp+60h] [rbp-18h]
  unsigned int v79; // [rsp+C0h] [rbp+48h] BYREF
  _DWORD *v80; // [rsp+C8h] [rbp+50h]
  unsigned int v81; // [rsp+D0h] [rbp+58h] BYREF
  int v82; // [rsp+D8h] [rbp+60h]

  v80 = a2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v79, "MF::DLNA::CheckAACAudioObjectType", 7160);
  v4 = 0;
  v74 = *a2;
  v5 = *a1;
  memset(v76, 0, sizeof(v76));
  v6 = *(__int64 (__fastcall **)(__int64 *, const GUID *, LPVOID *, unsigned int *))(v5 + 128);
  v77 = 0;
  v78 = 0;
  v79 = 0;
  pv = 0;
  v81 = 0;
  AACLevel = v6(a1, &MF_MT_USER_DATA, &pv, &v81);
  if ( AACLevel < 0 )
  {
    v9 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != AACLevel )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MF::DLNA::CheckAACAudioObjectType", 7186, AACLevel);
    }
    if ( g_wppLevels )
    {
      v12 = 38;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, 0, AACLevel);
      goto LABEL_228;
    }
    goto LABEL_228;
  }
  if ( v81 < 0xC )
  {
    if ( byte_1801B110B )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 17), 39, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, v81);
    v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    v14 = -1072875852;
    AACLevel = -1072875852;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v13 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v16 + 499) != -1072875852 )
        CallStackContext::TraceFailure(v16, "MF::DLNA::CheckAACAudioObjectType", 7191, -1072875852);
    }
    if ( !g_wppLevels )
      goto LABEL_228;
    v17 = 40;
    goto LABEL_227;
  }
  v18 = pv;
  v19 = *(unsigned __int16 *)pv;
  v20 = *((unsigned __int16 *)pv + 1);
  if ( (_WORD)v19 )
  {
    if ( byte_1801B110B )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 17), 41, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, v19);
    v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    v14 = -1072875852;
    AACLevel = -1072875852;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
      CallStackTracing::s_wpInstance = v22;
      if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
      {
        v21 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v21 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v21 + 8) )
    {
      v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
      if ( *((_DWORD *)v23 + 499) != -1072875852 )
        CallStackContext::TraceFailure(v23, "MF::DLNA::CheckAACAudioObjectType", 7201, -1072875852);
    }
    if ( !g_wppLevels )
      goto LABEL_228;
    v17 = 42;
    goto LABEL_227;
  }
  v24 = *((unsigned __int16 *)pv + 2);
  v25 = v81 - 12;
  v26 = 252;
  v27 = 0;
  v28 = 0;
  if ( (unsigned __int16)(v20 - 1) > 0xFCu && (unsigned __int16)v20 < 0x100u )
  {
LABEL_75:
    if ( (_WORD)v24 )
    {
      if ( byte_1801B110B )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 17), 48, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, v24);
      v37 = (wchar_t *)CallStackTracing::s_wpInstance;
      v14 = -1072875852;
      AACLevel = -1072875852;
      if ( !CallStackTracing::s_wpInstance )
      {
        v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
        CallStackTracing::s_wpInstance = v38;
        if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
        {
          v37 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v37 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v37 + 8) )
      {
        v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
        if ( *((_DWORD *)v39 + 499) != -1072875852 )
          CallStackContext::TraceFailure(v39, "MF::DLNA::CheckAACAudioObjectType", 7273, -1072875852);
      }
      if ( !g_wppLevels )
        goto LABEL_228;
      v17 = 49;
      goto LABEL_227;
    }
    v40 = 0;
    v79 = 0;
    v82 = 0;
    if ( !v25
      || (int)CAACAudioSpecificConfig::ParseData((CAACAudioSpecificConfig *)v76, v25, (const unsigned __int8 *)pv + 12) < 0 )
    {
      v44 = v27;
      v43 = v28;
      goto LABEL_117;
    }
    v41 = v27 | HIDWORD(v77);
    v42 = v28 | v78;
    switch ( HIDWORD(v76[0]) )
    {
      case 2:
        v40 = 1;
        goto LABEL_92;
      case 4:
        v79 = 1;
        goto LABEL_92;
      case 0x16:
        v82 = 1;
        goto LABEL_92;
    }
    if ( v41 || (_DWORD)v42 )
    {
LABEL_92:
      v43 = v28;
      v44 = v27;
      v27 |= HIDWORD(v77);
      v28 |= v78;
      if ( !v4 && !v44 && !v43 )
      {
        if ( (_DWORD)v42 )
          v43 = 1;
        else
          v44 = v41 != 0;
      }
LABEL_117:
      v48 = v74 & 0x1000000;
      if ( (*v80 & 0x20000000) == 0 || v44 )
      {
        if ( (*v80 & 0x40000000) == 0 || v43 )
        {
          if ( !v40 || (_DWORD)v48 )
          {
            if ( !v27 || (v74 & 0x2000000) != 0 )
            {
              if ( !v28 || (v74 & 0x4000000) != 0 )
              {
                if ( !v79 || (v74 & 0x8000000) != 0 )
                {
                  if ( !v82 || (v74 & 0x10000000) != 0 )
                    goto LABEL_228;
                  if ( byte_1801B110B )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 64, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
                  v67 = (wchar_t *)CallStackTracing::s_wpInstance;
                  v14 = -1072863756;
                  AACLevel = -1072863756;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
                    CallStackTracing::s_wpInstance = v68;
                    if ( v68
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
                    {
                      v67 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v67 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                    }
                  }
                  if ( *((_BYTE *)v67 + 8) )
                  {
                    v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v67);
                    if ( *((_DWORD *)v69 + 499) != -1072863756 )
                      CallStackContext::TraceFailure(v69, "MF::DLNA::CheckAACAudioObjectType", 7364, -1072863756);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_228;
                  v17 = 65;
                }
                else
                {
                  if ( byte_1801B110B )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 62, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
                  v64 = (wchar_t *)CallStackTracing::s_wpInstance;
                  v14 = -1072863756;
                  AACLevel = -1072863756;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
                    CallStackTracing::s_wpInstance = v65;
                    if ( v65
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
                    {
                      v64 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v64 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                    }
                  }
                  if ( *((_BYTE *)v64 + 8) )
                  {
                    v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
                    if ( *((_DWORD *)v66 + 499) != -1072863756 )
                      CallStackContext::TraceFailure(v66, "MF::DLNA::CheckAACAudioObjectType", 7358, -1072863756);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_228;
                  v17 = 63;
                }
              }
              else
              {
                if ( byte_1801B110B )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 60, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
                v61 = (wchar_t *)CallStackTracing::s_wpInstance;
                v14 = -1072863756;
                AACLevel = -1072863756;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
                  CallStackTracing::s_wpInstance = v62;
                  if ( v62
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
                  {
                    v61 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v61 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v61 + 8) )
                {
                  v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
                  if ( *((_DWORD *)v63 + 499) != -1072863756 )
                    CallStackContext::TraceFailure(v63, "MF::DLNA::CheckAACAudioObjectType", 7352, -1072863756);
                }
                if ( !g_wppLevels )
                  goto LABEL_228;
                v17 = 61;
              }
            }
            else
            {
              if ( byte_1801B110B )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 58, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
              v58 = (wchar_t *)CallStackTracing::s_wpInstance;
              v14 = -1072863756;
              AACLevel = -1072863756;
              if ( !CallStackTracing::s_wpInstance )
              {
                v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
                CallStackTracing::s_wpInstance = v59;
                if ( v59
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
                {
                  v58 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v58 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v58 + 8) )
              {
                v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
                if ( *((_DWORD *)v60 + 499) != -1072863756 )
                  CallStackContext::TraceFailure(v60, "MF::DLNA::CheckAACAudioObjectType", 7346, -1072863756);
              }
              if ( !g_wppLevels )
                goto LABEL_228;
              v17 = 59;
            }
          }
          else
          {
            if ( byte_1801B110B )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 56, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
            v55 = (wchar_t *)CallStackTracing::s_wpInstance;
            v14 = -1072863756;
            AACLevel = -1072863756;
            if ( !CallStackTracing::s_wpInstance )
            {
              v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
              CallStackTracing::s_wpInstance = v56;
              if ( v56
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
              {
                v55 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v55 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v55 + 8) )
            {
              v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
              if ( *((_DWORD *)v57 + 499) != -1072863756 )
                CallStackContext::TraceFailure(v57, "MF::DLNA::CheckAACAudioObjectType", 7340, -1072863756);
            }
            if ( !g_wppLevels )
              goto LABEL_228;
            v17 = 57;
          }
        }
        else
        {
          if ( byte_1801B110B )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 54, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
          v52 = (wchar_t *)CallStackTracing::s_wpInstance;
          v14 = -1072863756;
          AACLevel = -1072863756;
          if ( !CallStackTracing::s_wpInstance )
          {
            v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
            CallStackTracing::s_wpInstance = v53;
            if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
            {
              v52 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v52 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v52 + 8) )
          {
            v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
            if ( *((_DWORD *)v54 + 499) != -1072863756 )
              CallStackContext::TraceFailure(v54, "MF::DLNA::CheckAACAudioObjectType", 7334, -1072863756);
          }
          if ( !g_wppLevels )
            goto LABEL_228;
          v17 = 55;
        }
      }
      else
      {
        if ( byte_1801B110B )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 52, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
        v49 = (wchar_t *)CallStackTracing::s_wpInstance;
        v14 = -1072863756;
        AACLevel = -1072863756;
        if ( !CallStackTracing::s_wpInstance )
        {
          v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
          CallStackTracing::s_wpInstance = v50;
          if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
          {
            v49 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v49 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v49 + 8) )
        {
          v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
          if ( *((_DWORD *)v51 + 499) != -1072863756 )
            CallStackContext::TraceFailure(v51, "MF::DLNA::CheckAACAudioObjectType", 7328, -1072863756);
        }
        if ( !g_wppLevels )
          goto LABEL_228;
        v17 = 53;
      }
      goto LABEL_227;
    }
    if ( byte_1801B110B )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        50,
        &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
        HIDWORD(v76[0]));
    v45 = (wchar_t *)CallStackTracing::s_wpInstance;
    v14 = -1072863756;
    AACLevel = -1072863756;
    if ( !CallStackTracing::s_wpInstance )
    {
      v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42);
      CallStackTracing::s_wpInstance = v46;
      if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
      {
        v45 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v45 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v45 + 8) )
    {
      v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
      if ( *((_DWORD *)v47 + 499) != -1072863756 )
        CallStackContext::TraceFailure(v47, "MF::DLNA::CheckAACAudioObjectType", 7304, -1072863756);
    }
    if ( !g_wppLevels )
      goto LABEL_228;
    v17 = 51;
LABEL_227:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, 0, v14);
    goto LABEL_228;
  }
  if ( (unsigned __int16)(v20 - 1) > 3u && (unsigned __int16)(v20 - 5) > 3u && (unsigned __int16)(v20 - 14) > 7u )
  {
    if ( (unsigned __int16)(v20 - 40) > 3u )
    {
      if ( (unsigned __int16)(v20 - 44) > 3u )
      {
        if ( (unsigned __int16)(v20 - 48) > 3u )
        {
          if ( (unsigned __int8)byte_1801B110B >= 0x10u )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 17),
              43,
              &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
              *((unsigned __int16 *)pv + 1));
          v32 = (wchar_t *)CallStackTracing::s_wpInstance;
          v14 = -1072863756;
          AACLevel = -1072863756;
          if ( !CallStackTracing::s_wpInstance )
          {
            v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
            CallStackTracing::s_wpInstance = v33;
            if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
            {
              v32 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v32 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v32 + 8) )
          {
            v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
            if ( *((_DWORD *)v34 + 499) != -1072863756 )
              CallStackContext::TraceFailure(v34, "MF::DLNA::CheckAACAudioObjectType", 7255, -1072863756);
          }
          if ( !g_wppLevels )
            goto LABEL_228;
          v17 = 44;
          goto LABEL_227;
        }
        v28 = 1;
      }
      else
      {
        v27 = 1;
      }
    }
    else
    {
      v4 = 1;
    }
  }
  AACLevel = MF::DLNA::GetAACLevel(v20, &v79);
  if ( AACLevel >= 0 )
  {
    v36 = (unsigned int)v80[1];
    if ( v79 < (unsigned int)v36 || v79 > v80[2] )
    {
      if ( (unsigned __int8)byte_1801B110B >= 0x10u )
        WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 17), 46, v29, v36, v80[2], v79);
      v70 = (wchar_t *)CallStackTracing::s_wpInstance;
      v14 = -1072863756;
      AACLevel = -1072863756;
      if ( !CallStackTracing::s_wpInstance )
      {
        v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
        CallStackTracing::s_wpInstance = v71;
        if ( v71 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
        {
          v70 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v70 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v70 + 8) )
      {
        v72 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v70);
        if ( *((_DWORD *)v72 + 499) != -1072863756 )
          CallStackContext::TraceFailure(v72, "MF::DLNA::CheckAACAudioObjectType", 7266, -1072863756);
      }
      if ( !g_wppLevels )
        goto LABEL_228;
      v17 = 47;
      goto LABEL_227;
    }
    goto LABEL_75;
  }
  v30 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
    CallStackTracing::s_wpInstance = v31;
    if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
    {
      v30 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v30 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v30 + 8) )
  {
    v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
    if ( *((_DWORD *)v35 + 499) != AACLevel )
      CallStackContext::TraceFailure(v35, "MF::DLNA::CheckAACAudioObjectType", 7258, AACLevel);
  }
  if ( g_wppLevels )
  {
    v12 = 45;
    goto LABEL_12;
  }
LABEL_228:
  CoTaskMemFree(pv);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v79);
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
