# MF::DLNA::CheckAACAudioObjectType

- ea: `0x18005d764`
- end: `0x18005e531`
- name: `MF::DLNA::CheckAACAudioObjectType`
- size: `3533`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180063280`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18005d764`
- `0x180061778`
- `0x18006408c`
- `0x1800640b4`
- `0x180064144`
- `0x180071330`
- `0x18007b488`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e50f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e50f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d7fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d8c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d994`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005da99`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005db2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005dc64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ddbb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ded3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005dfa4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e073`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e142`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e210`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e2e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e3b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e473`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d7fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d8c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d994`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005da99`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005db2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005dc64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ddbb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ded3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005dfa4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e073`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e142`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e210`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e2e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e3b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e473`

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
        v11 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
    if ( byte_1800D78D3 )
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
        v16 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
    if ( byte_1800D78D3 )
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
        v24 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      if ( byte_1800D78D3 )
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
          v39 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                  if ( byte_1800D78D3 )
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
                      v72 = &qword_1800D6F70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                  if ( byte_1800D78D3 )
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
                      v69 = &qword_1800D6F70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                if ( byte_1800D78D3 )
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
                    v66 = &qword_1800D6F70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              if ( byte_1800D78D3 )
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
                  v63 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            if ( byte_1800D78D3 )
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
                v60 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          if ( byte_1800D78D3 )
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
              v57 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        if ( byte_1800D78D3 )
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
            v54 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
    if ( byte_1800D78D3 )
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
        v48 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          if ( (unsigned __int8)byte_1800D78D3 >= 0x10u )
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
              v35 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      if ( (unsigned __int8)byte_1800D78D3 >= 0x10u )
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
          v75 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v33 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18005d764  mov     [rsp-40h+arg_8], rdx
0x18005d769  push    rbp
0x18005d76a  push    rbx
0x18005d76b  push    rsi
0x18005d76c  push    rdi
0x18005d76d  push    r12
0x18005d76f  push    r13
0x18005d771  push    r14
0x18005d773  push    r15
0x18005d775  mov     rbp, rsp
0x18005d778  sub     rsp, 78h
0x18005d77c  mov     rdi, rdx
0x18005d77f  lea     r14, aMfDlnaCheckaac; "MF::DLNA::CheckAACAudioObjectType"
0x18005d786  mov     rbx, rcx
0x18005d789  mov     rdx, r14; char *
0x18005d78c  mov     r8d, 1BF8h; int
0x18005d792  lea     rcx, [rbp+arg_0]; this
0x18005d796  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005d79b  mov     eax, [rdi]
0x18005d79d  lea     r9, [rbp+arg_10]
0x18005d7a1  xor     r13d, r13d
0x18005d7a4  mov     [rbp+var_48], eax
0x18005d7a7  mov     rax, [rbx]
0x18005d7aa  lea     r8, [rbp+pv]
0x18005d7ae  lea     rdx, MF_MT_USER_DATA
0x18005d7b5  mov     [rbp+var_38], r13
0x18005d7b9  mov     rcx, rbx
0x18005d7bc  mov     [rbp+var_30], r13
0x18005d7c0  mov     [rbp+var_28], r13
0x18005d7c4  mov     rax, [rax+80h]
0x18005d7cb  mov     [rbp+var_20], r13
0x18005d7cf  mov     [rbp+var_18], r13d
0x18005d7d3  mov     [rbp+arg_0], r13d
0x18005d7d7  mov     [rbp+pv], r13
0x18005d7db  mov     [rbp+arg_10], r13d
0x18005d7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d7e4  mov     esi, eax
0x18005d7e6  test    eax, eax
0x18005d7e8  jns     loc_18005D880
0x18005d7ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d7f5  test    rcx, rcx
0x18005d7f8  jnz     short loc_18005D83B
0x18005d7fa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005d800  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d807  mov     rcx, rax
0x18005d80a  test    rax, rax
0x18005d80d  jz      short loc_18005D82D
0x18005d80f  mov     rax, [rax]
0x18005d812  mov     edx, 7F0h
0x18005d817  mov     rax, [rax+8]
0x18005d81b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d820  test    eax, eax
0x18005d822  jz      short loc_18005D82D
0x18005d824  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d82b  jmp     short loc_18005D83B
0x18005d82d  lea     rcx, qword_1800D6F70; this
0x18005d834  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d83b  cmp     [rcx+8], r13b
0x18005d83f  jz      short loc_18005D862
0x18005d841  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005d846  cmp     [rax+7CCh], esi
0x18005d84c  jz      short loc_18005D862
0x18005d84e  mov     r9d, esi; int
0x18005d851  mov     r8d, 1C12h; int
0x18005d857  mov     rdx, r14; char *
0x18005d85a  mov     rcx, rax; this
0x18005d85d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005d862  mov     edi, 1
0x18005d867  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18005d86e  jb      loc_18005E50B
0x18005d874  lea     edx, [rdi+25h]
0x18005d877  mov     [rsp+78h+var_58], esi
0x18005d87b  jmp     loc_18005E4F1
0x18005d880  mov     r8d, [rbp+arg_10]
0x18005d884  cmp     r8d, 0Ch
0x18005d888  jnb     loc_18005D947
0x18005d88e  mov     edi, 1
0x18005d893  cmp     cs:byte_1800D78D3, dil
0x18005d89a  jb      short loc_18005D8B5
0x18005d89c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d8a3  lea     edx, [rdi+26h]
0x18005d8a6  mov     r9d, r8d
0x18005d8a9  mov     rcx, [rcx+88h]
0x18005d8b0  call    WPP_SF_D
0x18005d8b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d8bc  mov     ebx, 0C00D36B4h
0x18005d8c1  mov     esi, ebx
0x18005d8c3  test    rcx, rcx
0x18005d8c6  jnz     short loc_18005D909
0x18005d8c8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005d8ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d8d5  mov     rcx, rax
0x18005d8d8  test    rax, rax
0x18005d8db  jz      short loc_18005D8FB
0x18005d8dd  mov     rax, [rax]
0x18005d8e0  mov     edx, 7F0h
0x18005d8e5  mov     rax, [rax+8]
0x18005d8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d8ee  test    eax, eax
0x18005d8f0  jz      short loc_18005D8FB
0x18005d8f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d8f9  jmp     short loc_18005D909
0x18005d8fb  lea     rcx, qword_1800D6F70; this
0x18005d902  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d909  cmp     [rcx+8], r13b
0x18005d90d  jz      short loc_18005D930
0x18005d90f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005d914  cmp     [rax+7CCh], ebx
0x18005d91a  jz      short loc_18005D930
0x18005d91c  mov     r9d, ebx; int
0x18005d91f  mov     r8d, 1C17h; int
0x18005d925  mov     rdx, r14; char *
0x18005d928  mov     rcx, rax; this
0x18005d92b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005d930  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18005d937  jb      loc_18005E50B
0x18005d93d  mov     edx, 28h ; '('
0x18005d942  jmp     loc_18005E4ED
0x18005d947  mov     rdx, [rbp+pv]
0x18005d94b  movzx   r9d, word ptr [rdx]
0x18005d94f  movzx   ecx, word ptr [rdx+2]
0x18005d953  cmp     r13w, r9w
0x18005d957  jz      loc_18005DA13
0x18005d95d  mov     edi, 1
0x18005d962  cmp     cs:byte_1800D78D3, dil
0x18005d969  jb      short loc_18005D981
0x18005d96b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d972  lea     edx, [rdi+28h]
0x18005d975  mov     rcx, [rcx+88h]
0x18005d97c  call    WPP_SF_D
0x18005d981  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d988  mov     ebx, 0C00D36B4h
0x18005d98d  mov     esi, ebx
0x18005d98f  test    rcx, rcx
0x18005d992  jnz     short loc_18005D9D5
0x18005d994  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005d99a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d9a1  mov     rcx, rax
0x18005d9a4  test    rax, rax
0x18005d9a7  jz      short loc_18005D9C7
0x18005d9a9  mov     rax, [rax]
0x18005d9ac  mov     edx, 7F0h
0x18005d9b1  mov     rax, [rax+8]
0x18005d9b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d9ba  test    eax, eax
0x18005d9bc  jz      short loc_18005D9C7
0x18005d9be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d9c5  jmp     short loc_18005D9D5
0x18005d9c7  lea     rcx, qword_1800D6F70; this
0x18005d9ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d9d5  cmp     [rcx+8], r13b
0x18005d9d9  jz      short loc_18005D9FC
0x18005d9db  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005d9e0  cmp     [rax+7CCh], ebx
0x18005d9e6  jz      short loc_18005D9FC
0x18005d9e8  mov     r9d, ebx; int
0x18005d9eb  mov     r8d, 1C21h; int
0x18005d9f1  mov     rdx, r14; char *
0x18005d9f4  mov     rcx, rax; this
0x18005d9f7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005d9fc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18005da03  jb      loc_18005E50B
0x18005da09  mov     edx, 2Ah ; '*'
0x18005da0e  jmp     loc_18005E4ED
0x18005da13  movzx   r15d, word ptr [rdx+4]
0x18005da18  lea     r12d, [r8-0Ch]
0x18005da1c  mov     edi, 1
0x18005da21  movzx   eax, cx
0x18005da24  sub     ax, di
0x18005da27  mov     edx, 0FCh
0x18005da2c  mov     r14d, r13d
0x18005da2f  mov     ebx, r13d
0x18005da32  lea     r10d, [rdi+2Fh]
0x18005da36  cmp     ax, dx
0x18005da39  jbe     short loc_18005DA47
0x18005da3b  lea     eax, [rdx+4]
0x18005da3e  cmp     cx, ax
0x18005da41  jb      loc_18005DC23
0x18005da47  movzx   eax, cx
0x18005da4a  mov     r8w, 3
0x18005da4f  sub     ax, di
0x18005da52  cmp     ax, r8w
0x18005da56  jbe     short loc_18005DA76
0x18005da58  lea     eax, [rcx-5]
0x18005da5b  cmp     ax, r8w
0x18005da5f  jbe     short loc_18005DA76
0x18005da61  lea     eax, [rcx-0Eh]
0x18005da64  cmp     ax, 7
0x18005da68  jbe     short loc_18005DA76
0x18005da6a  lea     eax, [rcx-28h]
0x18005da6d  cmp     ax, r8w
0x18005da71  ja      short loc_18005DAD7
0x18005da73  mov     r13d, edi
0x18005da76  lea     rdx, [rbp+arg_0]
0x18005da7a  call    MF__DLNA__GetAACLevel
0x18005da7f  mov     esi, eax
0x18005da81  test    eax, eax
0x18005da83  jns     loc_18005DC00
0x18005da89  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005da90  test    rcx, rcx
0x18005da93  jnz     loc_18005DBBE
0x18005da99  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005da9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005daa6  mov     rcx, rax
0x18005daa9  test    rax, rax
0x18005daac  jz      loc_18005DBB0
0x18005dab2  mov     rax, [rax]
0x18005dab5  mov     edx, 7F0h
0x18005daba  mov     rax, [rax+8]
0x18005dabe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dac3  test    eax, eax
0x18005dac5  jz      loc_18005DBB0
0x18005dacb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005dad2  jmp     loc_18005DBBE
0x18005dad7  lea     eax, [rcx-2Ch]
0x18005dada  cmp     ax, r8w
0x18005dade  ja      short loc_18005DAE5
0x18005dae0  mov     r14d, edi
0x18005dae3  jmp     short loc_18005DA76
0x18005dae5  movzx   eax, cx
0x18005dae8  sub     ax, r10w
0x18005daec  cmp     ax, r8w
0x18005daf0  ja      short loc_18005DAF6
0x18005daf2  mov     ebx, edi
0x18005daf4  jmp     short loc_18005DA76
0x18005daf6  cmp     cs:byte_1800D78D3, 10h
0x18005dafd  jb      short loc_18005DB1A
0x18005daff  mov     r9d, ecx
0x18005db02  mov     edx, 2Bh ; '+'
0x18005db07  mov     rcx, cs:WPP_GLOBAL_Control
0x18005db0e  mov     rcx, [rcx+88h]
0x18005db15  call    WPP_SF_D
0x18005db1a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005db21  mov     ebx, 0C00D65F4h
0x18005db26  mov     esi, ebx
0x18005db28  test    rcx, rcx
0x18005db2b  jnz     short loc_18005DB6E
0x18005db2d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005db33  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005db3a  mov     rcx, rax
0x18005db3d  test    rax, rax
0x18005db40  jz      short loc_18005DB60
0x18005db42  mov     rax, [rax]
0x18005db45  mov     edx, 7F0h
0x18005db4a  mov     rax, [rax+8]
0x18005db4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005db53  test    eax, eax
0x18005db55  jz      short loc_18005DB60
0x18005db57  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005db5e  jmp     short loc_18005DB6E
0x18005db60  lea     rcx, qword_1800D6F70; this
0x18005db67  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005db6e  cmp     [rcx+8], r13b
0x18005db72  jz      short loc_18005DB99
0x18005db74  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005db79  cmp     [rax+7CCh], ebx
0x18005db7f  jz      short loc_18005DB99
0x18005db81  mov     r9d, ebx; int
0x18005db84  lea     rdx, aMfDlnaCheckaac; "MF::DLNA::CheckAACAudioObjectType"
0x18005db8b  mov     r8d, 1C57h; int
0x18005db91  mov     rcx, rax; this
0x18005db94  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005db99  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18005dba0  jb      loc_18005E50B
0x18005dba6  mov     edx, 2Ch ; ','
0x18005dbab  jmp     loc_18005E4ED
0x18005dbb0  lea     rcx, qword_1800D6F70; this
0x18005dbb7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005dbbe  cmp     byte ptr [rcx+8], 0
0x18005dbc2  jz      short loc_18005DBE9
0x18005dbc4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005dbc9  cmp     [rax+7CCh], esi
0x18005dbcf  jz      short loc_18005DBE9
0x18005dbd1  mov     r9d, esi; int
0x18005dbd4  lea     rdx, aMfDlnaCheckaac; "MF::DLNA::CheckAACAudioObjectType"
0x18005dbdb  mov     r8d, 1C5Ah; int
0x18005dbe1  mov     rcx, rax; this
0x18005dbe4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005dbe9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18005dbf0  jb      loc_18005E50B
0x18005dbf6  mov     edx, 2Dh ; '-'
0x18005dbfb  jmp     loc_18005D877
0x18005dc00  mov     rcx, [rbp+arg_8]
0x18005dc04  mov     eax, [rbp+arg_0]
0x18005dc07  mov     r9d, [rcx+4]
0x18005dc0b  cmp     eax, r9d
0x18005dc0e  jb      loc_18005E434
0x18005dc14  cmp     eax, [rcx+8]
0x18005dc17  ja      loc_18005E434
0x18005dc1d  mov     r10d, 30h ; '0'
0x18005dc23  xor     eax, eax
0x18005dc25  cmp     ax, r15w
0x18005dc29  jz      loc_18005DCE7
0x18005dc2f  cmp     cs:byte_1800D78D3, dil
0x18005dc36  jb      short loc_18005DC51
0x18005dc38  mov     rcx, cs:WPP_GLOBAL_Control
0x18005dc3f  mov     r9d, r15d
0x18005dc42  mov     edx, r10d
0x18005dc45  mov     rcx, [rcx+88h]
0x18005dc4c  call    WPP_SF_D
  ... truncated ...
```
