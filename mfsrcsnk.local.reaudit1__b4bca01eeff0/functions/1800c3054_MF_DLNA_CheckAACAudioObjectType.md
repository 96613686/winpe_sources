# MF::DLNA::CheckAACAudioObjectType

- ea: `0x1800c3054`
- end: `0x1800c3ea8`
- name: `MF::DLNA::CheckAACAudioObjectType`
- size: `3668`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18017a1b0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180079680`
- `0x1800a0fb4`
- `0x1800c3054`
- `0x1800c7fdc`
- `0x18011cbac`
- `0x180124a8c`
- `0x18017abfc`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c30ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c31c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c329e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c33a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c344d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3591`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c36f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3813`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c38ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c39bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3a94`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3b68`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3c3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3d15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3ddd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c30ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c31c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c329e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c33a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c344d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3591`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c36f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3813`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c38ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c39bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3a94`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3b68`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3c3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3d15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3ddd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3e7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3e7f`

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
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  struct CallStackContext *v34; // rax
  wchar_t *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  int v38; // r15d
  int v39; // r8d
  __int64 v40; // rdx
  int v41; // ecx
  BOOL v42; // eax
  wchar_t *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rdx
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  wchar_t *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  wchar_t *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  wchar_t *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  wchar_t *v62; // rcx
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  wchar_t *v65; // rcx
  CallStackTracing *v66; // rax
  struct CallStackContext *v67; // rax
  wchar_t *v68; // rcx
  CallStackTracing *v69; // rax
  struct CallStackContext *v70; // rax
  int v72; // [rsp+30h] [rbp-48h]
  LPVOID pv; // [rsp+38h] [rbp-40h] BYREF
  _QWORD v74[3]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v75; // [rsp+58h] [rbp-20h]
  unsigned int v76; // [rsp+60h] [rbp-18h]
  unsigned int v77; // [rsp+C0h] [rbp+48h] BYREF
  _DWORD *v78; // [rsp+C8h] [rbp+50h]
  unsigned int v79; // [rsp+D0h] [rbp+58h] BYREF
  int v80; // [rsp+D8h] [rbp+60h]

  v78 = a2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v77, "MF::DLNA::CheckAACAudioObjectType", 7160);
  v4 = 0;
  v72 = *a2;
  v5 = *a1;
  memset(v74, 0, sizeof(v74));
  v6 = *(__int64 (__fastcall **)(__int64 *, const GUID *, LPVOID *, unsigned int *))(v5 + 128);
  v75 = 0;
  v76 = 0;
  v77 = 0;
  pv = 0;
  v79 = 0;
  AACLevel = v6(a1, &MF_MT_USER_DATA, &pv, &v79);
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
        v9 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  if ( v79 < 0xC )
  {
    if ( byte_1801BA10B )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 17), 39, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, v79);
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
        v13 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
    if ( byte_1801BA10B )
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
        v21 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  v25 = v79 - 12;
  v26 = 252;
  v27 = 0;
  v28 = 0;
  if ( (unsigned __int16)(v20 - 1) > 0xFCu && (unsigned __int16)v20 < 0x100u )
  {
LABEL_75:
    if ( (_WORD)v24 )
    {
      if ( byte_1801BA10B )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 17), 48, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, v24);
      v35 = (wchar_t *)CallStackTracing::s_wpInstance;
      v14 = -1072875852;
      AACLevel = -1072875852;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
        if ( *((_DWORD *)v37 + 499) != -1072875852 )
          CallStackContext::TraceFailure(v37, "MF::DLNA::CheckAACAudioObjectType", 7273, -1072875852);
      }
      if ( !g_wppLevels )
        goto LABEL_228;
      v17 = 49;
      goto LABEL_227;
    }
    v38 = 0;
    v77 = 0;
    v80 = 0;
    if ( !v25
      || (int)CAACAudioSpecificConfig::ParseData((CAACAudioSpecificConfig *)v74, v25, (const unsigned __int8 *)pv + 12) < 0 )
    {
      v42 = v27;
      v41 = v28;
      goto LABEL_117;
    }
    v39 = v27 | HIDWORD(v75);
    v40 = v28 | v76;
    switch ( HIDWORD(v74[0]) )
    {
      case 2:
        v38 = 1;
        goto LABEL_92;
      case 4:
        v77 = 1;
        goto LABEL_92;
      case 0x16:
        v80 = 1;
        goto LABEL_92;
    }
    if ( v39 || (_DWORD)v40 )
    {
LABEL_92:
      v41 = v28;
      v42 = v27;
      v27 |= HIDWORD(v75);
      v28 |= v76;
      if ( !v4 && !v42 && !v41 )
      {
        if ( (_DWORD)v40 )
          v41 = 1;
        else
          v42 = v39 != 0;
      }
LABEL_117:
      v46 = v72 & 0x1000000;
      if ( (*v78 & 0x20000000) == 0 || v42 )
      {
        if ( (*v78 & 0x40000000) == 0 || v41 )
        {
          if ( !v38 || (_DWORD)v46 )
          {
            if ( !v27 || (v72 & 0x2000000) != 0 )
            {
              if ( !v28 || (v72 & 0x4000000) != 0 )
              {
                if ( !v77 || (v72 & 0x8000000) != 0 )
                {
                  if ( !v80 || (v72 & 0x10000000) != 0 )
                    goto LABEL_228;
                  if ( byte_1801BA10B )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 64, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
                  v65 = (wchar_t *)CallStackTracing::s_wpInstance;
                  v14 = -1072863756;
                  AACLevel = -1072863756;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
                    CallStackTracing::s_wpInstance = v66;
                    if ( v66
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v66 + 8LL))(v66, 2032) )
                    {
                      v65 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v65 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                    }
                  }
                  if ( *((_BYTE *)v65 + 8) )
                  {
                    v67 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v65);
                    if ( *((_DWORD *)v67 + 499) != -1072863756 )
                      CallStackContext::TraceFailure(v67, "MF::DLNA::CheckAACAudioObjectType", 7364, -1072863756);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_228;
                  v17 = 65;
                }
                else
                {
                  if ( byte_1801BA10B )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 62, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
                  v62 = (wchar_t *)CallStackTracing::s_wpInstance;
                  v14 = -1072863756;
                  AACLevel = -1072863756;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
                    CallStackTracing::s_wpInstance = v63;
                    if ( v63
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
                    {
                      v62 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v62 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                    }
                  }
                  if ( *((_BYTE *)v62 + 8) )
                  {
                    v64 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v62);
                    if ( *((_DWORD *)v64 + 499) != -1072863756 )
                      CallStackContext::TraceFailure(v64, "MF::DLNA::CheckAACAudioObjectType", 7358, -1072863756);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_228;
                  v17 = 63;
                }
              }
              else
              {
                if ( byte_1801BA10B )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 60, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
                v59 = (wchar_t *)CallStackTracing::s_wpInstance;
                v14 = -1072863756;
                AACLevel = -1072863756;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
                  CallStackTracing::s_wpInstance = v60;
                  if ( v60
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
                  {
                    v59 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v59 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                  }
                }
                if ( *((_BYTE *)v59 + 8) )
                {
                  v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
                  if ( *((_DWORD *)v61 + 499) != -1072863756 )
                    CallStackContext::TraceFailure(v61, "MF::DLNA::CheckAACAudioObjectType", 7352, -1072863756);
                }
                if ( !g_wppLevels )
                  goto LABEL_228;
                v17 = 61;
              }
            }
            else
            {
              if ( byte_1801BA10B )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 58, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
              v56 = (wchar_t *)CallStackTracing::s_wpInstance;
              v14 = -1072863756;
              AACLevel = -1072863756;
              if ( !CallStackTracing::s_wpInstance )
              {
                v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
                CallStackTracing::s_wpInstance = v57;
                if ( v57
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
                {
                  v56 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v56 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v56 + 8) )
              {
                v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
                if ( *((_DWORD *)v58 + 499) != -1072863756 )
                  CallStackContext::TraceFailure(v58, "MF::DLNA::CheckAACAudioObjectType", 7346, -1072863756);
              }
              if ( !g_wppLevels )
                goto LABEL_228;
              v17 = 59;
            }
          }
          else
          {
            if ( byte_1801BA10B )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 56, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
            v53 = (wchar_t *)CallStackTracing::s_wpInstance;
            v14 = -1072863756;
            AACLevel = -1072863756;
            if ( !CallStackTracing::s_wpInstance )
            {
              v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
              CallStackTracing::s_wpInstance = v54;
              if ( v54
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
              {
                v53 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v53 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v53 + 8) )
            {
              v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
              if ( *((_DWORD *)v55 + 499) != -1072863756 )
                CallStackContext::TraceFailure(v55, "MF::DLNA::CheckAACAudioObjectType", 7340, -1072863756);
            }
            if ( !g_wppLevels )
              goto LABEL_228;
            v17 = 57;
          }
        }
        else
        {
          if ( byte_1801BA10B )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 54, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
          v50 = (wchar_t *)CallStackTracing::s_wpInstance;
          v14 = -1072863756;
          AACLevel = -1072863756;
          if ( !CallStackTracing::s_wpInstance )
          {
            v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
            CallStackTracing::s_wpInstance = v51;
            if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
            {
              v50 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v50 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v50 + 8) )
          {
            v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
            if ( *((_DWORD *)v52 + 499) != -1072863756 )
              CallStackContext::TraceFailure(v52, "MF::DLNA::CheckAACAudioObjectType", 7334, -1072863756);
          }
          if ( !g_wppLevels )
            goto LABEL_228;
          v17 = 55;
        }
      }
      else
      {
        if ( byte_1801BA10B )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 52, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
        v47 = (wchar_t *)CallStackTracing::s_wpInstance;
        v14 = -1072863756;
        AACLevel = -1072863756;
        if ( !CallStackTracing::s_wpInstance )
        {
          v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
          CallStackTracing::s_wpInstance = v48;
          if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
          {
            v47 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v47 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v47 + 8) )
        {
          v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
          if ( *((_DWORD *)v49 + 499) != -1072863756 )
            CallStackContext::TraceFailure(v49, "MF::DLNA::CheckAACAudioObjectType", 7328, -1072863756);
        }
        if ( !g_wppLevels )
          goto LABEL_228;
        v17 = 53;
      }
      goto LABEL_227;
    }
    if ( byte_1801BA10B )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        50,
        &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
        HIDWORD(v74[0]));
    v43 = (wchar_t *)CallStackTracing::s_wpInstance;
    v14 = -1072863756;
    AACLevel = -1072863756;
    if ( !CallStackTracing::s_wpInstance )
    {
      v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
      CallStackTracing::s_wpInstance = v44;
      if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
      {
        v43 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v43 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v43 + 8) )
    {
      v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
      if ( *((_DWORD *)v45 + 499) != -1072863756 )
        CallStackContext::TraceFailure(v45, "MF::DLNA::CheckAACAudioObjectType", 7304, -1072863756);
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
          if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 17),
              43,
              &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
              *((unsigned __int16 *)pv + 1));
          v31 = (wchar_t *)CallStackTracing::s_wpInstance;
          v14 = -1072863756;
          AACLevel = -1072863756;
          if ( !CallStackTracing::s_wpInstance )
          {
            v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
            CallStackTracing::s_wpInstance = v32;
            if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
            {
              v31 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v31 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v31 + 8) )
          {
            v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
            if ( *((_DWORD *)v33 + 499) != -1072863756 )
              CallStackContext::TraceFailure(v33, "MF::DLNA::CheckAACAudioObjectType", 7255, -1072863756);
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
  AACLevel = MF::DLNA::GetAACLevel(v20, &v77);
  if ( AACLevel >= 0 )
  {
    if ( v77 < v78[1] || v77 > v78[2] )
    {
      if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
        WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 17), 46);
      v68 = (wchar_t *)CallStackTracing::s_wpInstance;
      v14 = -1072863756;
      AACLevel = -1072863756;
      if ( !CallStackTracing::s_wpInstance )
      {
        v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
        CallStackTracing::s_wpInstance = v69;
        if ( v69 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v69 + 8LL))(v69, 2032) )
        {
          v68 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v68 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v68 + 8) )
      {
        v70 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v68);
        if ( *((_DWORD *)v70 + 499) != -1072863756 )
          CallStackContext::TraceFailure(v70, "MF::DLNA::CheckAACAudioObjectType", 7266, -1072863756);
      }
      if ( !g_wppLevels )
        goto LABEL_228;
      v17 = 47;
      goto LABEL_227;
    }
    goto LABEL_75;
  }
  v29 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
    CallStackTracing::s_wpInstance = v30;
    if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
    {
      v29 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v29 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v29 + 8) )
  {
    v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
    if ( *((_DWORD *)v34 + 499) != AACLevel )
      CallStackContext::TraceFailure(v34, "MF::DLNA::CheckAACAudioObjectType", 7258, AACLevel);
  }
  if ( g_wppLevels )
  {
    v12 = 45;
    goto LABEL_12;
  }
LABEL_228:
  CoTaskMemFree(pv);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v77);
  return (unsigned int)AACLevel;
}

```

## disassembly

```asm
0x1800c3054  mov     [rsp-40h+arg_8], rdx
0x1800c3059  push    rbp
0x1800c305a  push    rbx
0x1800c305b  push    rsi
0x1800c305c  push    rdi
0x1800c305d  push    r12
0x1800c305f  push    r13
0x1800c3061  push    r14
0x1800c3063  push    r15
0x1800c3065  mov     rbp, rsp
0x1800c3068  sub     rsp, 78h
0x1800c306c  mov     rdi, rdx
0x1800c306f  lea     r14, aMfDlnaCheckaac; "MF::DLNA::CheckAACAudioObjectType"
0x1800c3076  mov     rbx, rcx
0x1800c3079  mov     rdx, r14; char *
0x1800c307c  mov     r8d, 1BF8h; int
0x1800c3082  lea     rcx, [rbp+arg_0]; this
0x1800c3086  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800c308b  mov     eax, [rdi]
0x1800c308d  lea     r9, [rbp+arg_10]
0x1800c3091  xor     r13d, r13d
0x1800c3094  mov     [rbp+var_48], eax
0x1800c3097  mov     rax, [rbx]
0x1800c309a  lea     r8, [rbp+pv]
0x1800c309e  lea     rdx, MF_MT_USER_DATA
0x1800c30a5  mov     [rbp+var_38], r13
0x1800c30a9  mov     rcx, rbx
0x1800c30ac  mov     [rbp+var_30], r13
0x1800c30b0  mov     [rbp+var_28], r13
0x1800c30b4  mov     rax, [rax+80h]
0x1800c30bb  mov     [rbp+var_20], r13
0x1800c30bf  mov     [rbp+var_18], r13d
0x1800c30c3  mov     [rbp+arg_0], r13d
0x1800c30c7  mov     [rbp+pv], r13
0x1800c30cb  mov     [rbp+arg_10], r13d
0x1800c30cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c30d4  mov     esi, eax
0x1800c30d6  test    eax, eax
0x1800c30d8  jns     loc_1800C3176
0x1800c30de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c30e5  test    rcx, rcx
0x1800c30e8  jnz     short loc_1800C3131
0x1800c30ea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c30f1  nop     dword ptr [rax+rax+00h]
0x1800c30f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c30fd  mov     rcx, rax
0x1800c3100  test    rax, rax
0x1800c3103  jz      short loc_1800C3123
0x1800c3105  mov     rax, [rax]
0x1800c3108  mov     edx, 7F0h
0x1800c310d  mov     rax, [rax+8]
0x1800c3111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3116  test    eax, eax
0x1800c3118  jz      short loc_1800C3123
0x1800c311a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3121  jmp     short loc_1800C3131
0x1800c3123  lea     rcx, qword_1801B97E0; this
0x1800c312a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3131  cmp     [rcx+8], r13b
0x1800c3135  jz      short loc_1800C3158
0x1800c3137  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c313c  cmp     [rax+7CCh], esi
0x1800c3142  jz      short loc_1800C3158
0x1800c3144  mov     r9d, esi; int
0x1800c3147  mov     r8d, 1C12h; int
0x1800c314d  mov     rdx, r14; char *
0x1800c3150  mov     rcx, rax; this
0x1800c3153  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c3158  mov     edi, 1
0x1800c315d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800c3164  jb      loc_1800C3E7B
0x1800c316a  lea     edx, [rdi+25h]
0x1800c316d  mov     [rsp+78h+var_58], esi
0x1800c3171  jmp     loc_1800C3E61
0x1800c3176  mov     r8d, [rbp+arg_10]
0x1800c317a  cmp     r8d, 0Ch
0x1800c317e  jnb     loc_1800C324A
0x1800c3184  mov     edi, 1
0x1800c3189  cmp     cs:byte_1801BA10B, dil
0x1800c3190  jb      short loc_1800C31B2
0x1800c3192  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3199  lea     edx, [rdi+26h]
0x1800c319c  mov     r9d, r8d
0x1800c319f  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x1800c31a6  mov     rcx, [rcx+88h]
0x1800c31ad  call    WPP_SF_d
0x1800c31b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c31b9  mov     ebx, 0C00D36B4h
0x1800c31be  mov     esi, ebx
0x1800c31c0  test    rcx, rcx
0x1800c31c3  jnz     short loc_1800C320C
0x1800c31c5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c31cc  nop     dword ptr [rax+rax+00h]
0x1800c31d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c31d8  mov     rcx, rax
0x1800c31db  test    rax, rax
0x1800c31de  jz      short loc_1800C31FE
0x1800c31e0  mov     rax, [rax]
0x1800c31e3  mov     edx, 7F0h
0x1800c31e8  mov     rax, [rax+8]
0x1800c31ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c31f1  test    eax, eax
0x1800c31f3  jz      short loc_1800C31FE
0x1800c31f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c31fc  jmp     short loc_1800C320C
0x1800c31fe  lea     rcx, qword_1801B97E0; this
0x1800c3205  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c320c  cmp     [rcx+8], r13b
0x1800c3210  jz      short loc_1800C3233
0x1800c3212  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c3217  cmp     [rax+7CCh], ebx
0x1800c321d  jz      short loc_1800C3233
0x1800c321f  mov     r9d, ebx; int
0x1800c3222  mov     r8d, 1C17h; int
0x1800c3228  mov     rdx, r14; char *
0x1800c322b  mov     rcx, rax; this
0x1800c322e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c3233  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800c323a  jb      loc_1800C3E7B
0x1800c3240  mov     edx, 28h ; '('
0x1800c3245  jmp     loc_1800C3E5D
0x1800c324a  mov     rdx, [rbp+pv]
0x1800c324e  movzx   r9d, word ptr [rdx]
0x1800c3252  movzx   ecx, word ptr [rdx+2]
0x1800c3256  cmp     r13w, r9w
0x1800c325a  jz      loc_1800C3323
0x1800c3260  mov     edi, 1
0x1800c3265  cmp     cs:byte_1801BA10B, dil
0x1800c326c  jb      short loc_1800C328B
0x1800c326e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3275  lea     edx, [rdi+28h]
0x1800c3278  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x1800c327f  mov     rcx, [rcx+88h]
0x1800c3286  call    WPP_SF_d
0x1800c328b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3292  mov     ebx, 0C00D36B4h
0x1800c3297  mov     esi, ebx
0x1800c3299  test    rcx, rcx
0x1800c329c  jnz     short loc_1800C32E5
0x1800c329e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c32a5  nop     dword ptr [rax+rax+00h]
0x1800c32aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c32b1  mov     rcx, rax
0x1800c32b4  test    rax, rax
0x1800c32b7  jz      short loc_1800C32D7
0x1800c32b9  mov     rax, [rax]
0x1800c32bc  mov     edx, 7F0h
0x1800c32c1  mov     rax, [rax+8]
0x1800c32c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c32ca  test    eax, eax
0x1800c32cc  jz      short loc_1800C32D7
0x1800c32ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c32d5  jmp     short loc_1800C32E5
0x1800c32d7  lea     rcx, qword_1801B97E0; this
0x1800c32de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c32e5  cmp     [rcx+8], r13b
0x1800c32e9  jz      short loc_1800C330C
0x1800c32eb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c32f0  cmp     [rax+7CCh], ebx
0x1800c32f6  jz      short loc_1800C330C
0x1800c32f8  mov     r9d, ebx; int
0x1800c32fb  mov     r8d, 1C21h; int
0x1800c3301  mov     rdx, r14; char *
0x1800c3304  mov     rcx, rax; this
0x1800c3307  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c330c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800c3313  jb      loc_1800C3E7B
0x1800c3319  mov     edx, 2Ah ; '*'
0x1800c331e  jmp     loc_1800C3E5D
0x1800c3323  movzx   r15d, word ptr [rdx+4]
0x1800c3328  lea     r12d, [r8-0Ch]
0x1800c332c  mov     edi, 1
0x1800c3331  movzx   eax, cx
0x1800c3334  sub     ax, di
0x1800c3337  mov     edx, 0FCh
0x1800c333c  mov     r14d, r13d
0x1800c333f  mov     ebx, r13d
0x1800c3342  lea     r10d, [rdi+2Fh]
0x1800c3346  cmp     ax, dx
0x1800c3349  jbe     short loc_1800C3357
0x1800c334b  lea     eax, [rdx+4]
0x1800c334e  cmp     cx, ax
0x1800c3351  jb      loc_1800C3549
0x1800c3357  movzx   eax, cx
0x1800c335a  mov     r8w, 3
0x1800c335f  sub     ax, di
0x1800c3362  cmp     ax, r8w
0x1800c3366  jbe     short loc_1800C3386
0x1800c3368  lea     eax, [rcx-5]
0x1800c336b  cmp     ax, r8w
0x1800c336f  jbe     short loc_1800C3386
0x1800c3371  lea     eax, [rcx-0Eh]
0x1800c3374  cmp     ax, 7
0x1800c3378  jbe     short loc_1800C3386
0x1800c337a  lea     eax, [rcx-28h]
0x1800c337d  cmp     ax, r8w
0x1800c3381  ja      short loc_1800C33ED
0x1800c3383  mov     r13d, edi
0x1800c3386  lea     rdx, [rbp+arg_0]
0x1800c338a  call    MF__DLNA__GetAACLevel
0x1800c338f  mov     esi, eax
0x1800c3391  test    eax, eax
0x1800c3393  jns     loc_1800C3526
0x1800c3399  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c33a0  test    rcx, rcx
0x1800c33a3  jnz     loc_1800C34E4
0x1800c33a9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c33b0  nop     dword ptr [rax+rax+00h]
0x1800c33b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c33bc  mov     rcx, rax
0x1800c33bf  test    rax, rax
0x1800c33c2  jz      loc_1800C34D6
0x1800c33c8  mov     rax, [rax]
0x1800c33cb  mov     edx, 7F0h
0x1800c33d0  mov     rax, [rax+8]
0x1800c33d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c33d9  test    eax, eax
0x1800c33db  jz      loc_1800C34D6
0x1800c33e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c33e8  jmp     loc_1800C34E4
0x1800c33ed  lea     eax, [rcx-2Ch]
0x1800c33f0  cmp     ax, r8w
0x1800c33f4  ja      short loc_1800C33FB
0x1800c33f6  mov     r14d, edi
0x1800c33f9  jmp     short loc_1800C3386
0x1800c33fb  movzx   eax, cx
0x1800c33fe  sub     ax, r10w
0x1800c3402  cmp     ax, r8w
0x1800c3406  ja      short loc_1800C340F
0x1800c3408  mov     ebx, edi
0x1800c340a  jmp     loc_1800C3386
0x1800c340f  cmp     cs:byte_1801BA10B, 10h
0x1800c3416  jb      short loc_1800C343A
0x1800c3418  mov     r9d, ecx
0x1800c341b  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x1800c3422  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3429  mov     edx, 2Bh ; '+'
0x1800c342e  mov     rcx, [rcx+88h]
0x1800c3435  call    WPP_SF_d
0x1800c343a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3441  mov     ebx, 0C00D65F4h
0x1800c3446  mov     esi, ebx
0x1800c3448  test    rcx, rcx
0x1800c344b  jnz     short loc_1800C3494
0x1800c344d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c3454  nop     dword ptr [rax+rax+00h]
0x1800c3459  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3460  mov     rcx, rax
0x1800c3463  test    rax, rax
0x1800c3466  jz      short loc_1800C3486
0x1800c3468  mov     rax, [rax]
0x1800c346b  mov     edx, 7F0h
0x1800c3470  mov     rax, [rax+8]
0x1800c3474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3479  test    eax, eax
0x1800c347b  jz      short loc_1800C3486
0x1800c347d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3484  jmp     short loc_1800C3494
0x1800c3486  lea     rcx, qword_1801B97E0; this
0x1800c348d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3494  cmp     [rcx+8], r13b
0x1800c3498  jz      short loc_1800C34BF
0x1800c349a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c349f  cmp     [rax+7CCh], ebx
0x1800c34a5  jz      short loc_1800C34BF
0x1800c34a7  mov     r9d, ebx; int
0x1800c34aa  lea     rdx, aMfDlnaCheckaac; "MF::DLNA::CheckAACAudioObjectType"
0x1800c34b1  mov     r8d, 1C57h; int
0x1800c34b7  mov     rcx, rax; this
0x1800c34ba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c34bf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800c34c6  jb      loc_1800C3E7B
0x1800c34cc  mov     edx, 2Ch ; ','
0x1800c34d1  jmp     loc_1800C3E5D
0x1800c34d6  lea     rcx, qword_1801B97E0; this
0x1800c34dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c34e4  cmp     byte ptr [rcx+8], 0
0x1800c34e8  jz      short loc_1800C350F
0x1800c34ea  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c34ef  cmp     [rax+7CCh], esi
0x1800c34f5  jz      short loc_1800C350F
0x1800c34f7  mov     r9d, esi; int
0x1800c34fa  lea     rdx, aMfDlnaCheckaac; "MF::DLNA::CheckAACAudioObjectType"
0x1800c3501  mov     r8d, 1C5Ah; int
0x1800c3507  mov     rcx, rax; this
0x1800c350a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c350f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800c3516  jb      loc_1800C3E7B
0x1800c351c  mov     edx, 2Dh ; '-'
0x1800c3521  jmp     loc_1800C316D
0x1800c3526  mov     rcx, [rbp+arg_8]
0x1800c352a  mov     eax, [rbp+arg_0]
0x1800c352d  mov     r9d, [rcx+4]
0x1800c3531  cmp     eax, r9d
0x1800c3534  jb      loc_1800C3D9E
0x1800c353a  cmp     eax, [rcx+8]
0x1800c353d  ja      loc_1800C3D9E
0x1800c3543  mov     r10d, 30h ; '0'
0x1800c3549  xor     eax, eax
0x1800c354b  cmp     ax, r15w
  ... truncated ...
```
