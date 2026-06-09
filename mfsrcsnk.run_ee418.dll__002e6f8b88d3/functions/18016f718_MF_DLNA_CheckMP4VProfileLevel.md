# MF::DLNA::CheckMP4VProfileLevel

- ea: `0x18016f718`
- end: `0x1801700d9`
- name: `MF::DLNA::CheckMP4VProfileLevel`
- size: `2497`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180171460`
- `0x180171740`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x18006cdb8`
- `0x180073b14`
- `0x18008cc4c`
- `0x1800c4c20`
- `0x1800d913c`
- `0x1800feab4`
- `0x180115a1c`
- `0x18016f718`
- `0x1801718ec`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016f7e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016f88e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016f933`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016fa02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016fac0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016fb61`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016fc01`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016fca8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016fd49`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016fde9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016febc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016ff4c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18017001c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016f7e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016f88e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016f933`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016fa02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016fac0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016fb61`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016fc01`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016fca8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016fd49`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016fde9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016febc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016ff4c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18017001c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801700b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801700b4`

## pseudocode

```c
__int64 __fastcall MF::DLNA::CheckMP4VProfileLevel(__int64 *a1, _DWORD *a2)
{
  __int64 v4; // rax
  int (__fastcall *v5)(__int64 *, const GUID *, LPVOID *, unsigned int *); // rax
  __int64 v6; // rdx
  int MP4VProfileAndLevel; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  wchar_t *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  unsigned int v27; // eax
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  unsigned int v33; // esi
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  wchar_t *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  wchar_t *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r9
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // r9
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
  unsigned int v74; // [rsp+30h] [rbp-40h] BYREF
  int v75; // [rsp+34h] [rbp-3Ch] BYREF
  unsigned int v76; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-30h] BYREF
  int v78; // [rsp+48h] [rbp-28h] BYREF
  __int16 v79; // [rsp+4Ch] [rbp-24h]
  char v80; // [rsp+4Eh] [rbp-22h]
  __int128 v81; // [rsp+50h] [rbp-20h]
  int v82; // [rsp+64h] [rbp-Ch]
  __int64 v83; // [rsp+68h] [rbp-8h]
  unsigned int v84; // [rsp+A0h] [rbp+30h] BYREF
  unsigned int v85; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v86; // [rsp+B8h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v84, "MF::DLNA::CheckMP4VProfileLevel", 7943);
  v4 = *a1;
  v78 = 0;
  v79 = 0;
  v5 = *(int (__fastcall **)(__int64 *, const GUID *, LPVOID *, unsigned int *))(v4 + 128);
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  pv = 0;
  v85 = 0;
  v75 = 0;
  v76 = 0;
  v84 = 0;
  v86 = 0;
  v74 = 0;
  if ( v5(a1, &MF_MT_USER_DATA, &pv, &v85) >= 0
    || (MP4VProfileAndLevel = (*(__int64 (__fastcall **)(__int64 *, const GUID *, LPVOID *, unsigned int *))(*a1 + 128))(
                                a1,
                                &MF_MT_MPEG_SEQUENCE_HEADER,
                                &pv,
                                &v85),
        MP4VProfileAndLevel >= 0) )
  {
    MP4VProfileAndLevel = CMP4VSequenceHeader::ParseData((CMP4VSequenceHeader *)&v78, v85, (const unsigned __int8 *)pv);
    if ( MP4VProfileAndLevel >= 0 )
    {
      LOBYTE(v15) = v79;
      MP4VProfileAndLevel = MF::DLNA::GetMP4VProfileAndLevel(v15, &v75, &v76);
      if ( MP4VProfileAndLevel >= 0 )
      {
        v27 = a2[1];
        if ( v27 == v75 )
        {
          v32 = (unsigned int)a2[2];
          v33 = v76;
          if ( v76 == (_DWORD)v32 || v76 == a2[3] )
            goto LABEL_155;
          if ( v27 == 1 )
          {
            MP4VProfileAndLevel = MF::DLNA::GetMPEG4_P2_SP_Level_OrdinalValue(v32, &v86);
            if ( MP4VProfileAndLevel < 0 )
            {
              v37 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35, v36);
                CallStackTracing::s_wpInstance = v38;
                if ( v38
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
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
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != MP4VProfileAndLevel )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "MF::DLNA::CheckMP4VProfileLevel",
                    7980,
                    MP4VProfileAndLevel);
              }
              if ( g_wppLevels )
              {
                v13 = 120;
                goto LABEL_13;
              }
              goto LABEL_158;
            }
            MP4VProfileAndLevel = MF::DLNA::GetMPEG4_P2_SP_Level_OrdinalValue((unsigned int)a2[3], &v74);
            if ( MP4VProfileAndLevel < 0 )
            {
              v43 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40, v41, v42);
                CallStackTracing::s_wpInstance = v44;
                if ( v44
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
                {
                  v43 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v43 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v43 + 8) )
              {
                v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
                if ( *((_DWORD *)v45 + 499) != MP4VProfileAndLevel )
                  CallStackContext::TraceFailure(v45, "MF::DLNA::CheckMP4VProfileLevel", 7981, MP4VProfileAndLevel);
              }
              if ( g_wppLevels )
              {
                v13 = 121;
                goto LABEL_13;
              }
              goto LABEL_158;
            }
            MP4VProfileAndLevel = MF::DLNA::GetMPEG4_P2_SP_Level_OrdinalValue(v33, &v84);
            if ( MP4VProfileAndLevel < 0 )
            {
              v46 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
                CallStackTracing::s_wpInstance = v47;
                if ( v47
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
                {
                  v46 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v46 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v46 + 8) )
              {
                v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
                if ( *((_DWORD *)v48 + 499) != MP4VProfileAndLevel )
                  CallStackContext::TraceFailure(v48, "MF::DLNA::CheckMP4VProfileLevel", 7982, MP4VProfileAndLevel);
              }
              if ( g_wppLevels )
              {
                v13 = 122;
                goto LABEL_13;
              }
              goto LABEL_158;
            }
          }
          else
          {
            if ( v27 != 18 )
            {
              v67 = (wchar_t *)CallStackTracing::s_wpInstance;
              MP4VProfileAndLevel = -2147418113;
              if ( !CallStackTracing::s_wpInstance )
              {
                v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
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
                if ( *((_DWORD *)v69 + 499) != -2147418113 )
                  CallStackContext::TraceFailure(v69, "MF::DLNA::CheckMP4VProfileLevel", 7993, -2147418113);
              }
              if ( g_wppLevels )
              {
                v13 = 126;
                goto LABEL_13;
              }
              goto LABEL_158;
            }
            MP4VProfileAndLevel = MF::DLNA::GetMPEG4_P2_ASP_Level_OrdinalValue(v32, &v86);
            if ( MP4VProfileAndLevel < 0 )
            {
              v52 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49, v50, v51);
                CallStackTracing::s_wpInstance = v53;
                if ( v53
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
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
                if ( *((_DWORD *)v54 + 499) != MP4VProfileAndLevel )
                  CallStackContext::TraceFailure(v54, "MF::DLNA::CheckMP4VProfileLevel", 7986, MP4VProfileAndLevel);
              }
              if ( g_wppLevels )
              {
                v13 = 123;
                goto LABEL_13;
              }
              goto LABEL_158;
            }
            MP4VProfileAndLevel = MF::DLNA::GetMPEG4_P2_ASP_Level_OrdinalValue((unsigned int)a2[3], &v74);
            if ( MP4VProfileAndLevel < 0 )
            {
              v58 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56, v57);
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
                if ( *((_DWORD *)v60 + 499) != MP4VProfileAndLevel )
                  CallStackContext::TraceFailure(v60, "MF::DLNA::CheckMP4VProfileLevel", 7987, MP4VProfileAndLevel);
              }
              if ( g_wppLevels )
              {
                v13 = 124;
                goto LABEL_13;
              }
              goto LABEL_158;
            }
            MP4VProfileAndLevel = MF::DLNA::GetMPEG4_P2_ASP_Level_OrdinalValue(v33, &v84);
            if ( MP4VProfileAndLevel < 0 )
            {
              v61 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
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
                if ( *((_DWORD *)v63 + 499) != MP4VProfileAndLevel )
                  CallStackContext::TraceFailure(v63, "MF::DLNA::CheckMP4VProfileLevel", 7988, MP4VProfileAndLevel);
              }
              if ( g_wppLevels )
              {
                v13 = 125;
                goto LABEL_13;
              }
              goto LABEL_158;
            }
          }
          if ( v84 >= v86 && v84 <= v74 )
          {
LABEL_155:
            if ( (*a2 & 0x1000000) == 0 || v82 )
              goto LABEL_158;
            if ( (unsigned __int8)byte_1801B110B >= 0x10u )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 129, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
            v70 = (wchar_t *)CallStackTracing::s_wpInstance;
            MP4VProfileAndLevel = -1072863756;
            if ( !CallStackTracing::s_wpInstance )
            {
              v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
              CallStackTracing::s_wpInstance = v71;
              if ( v71
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
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
                CallStackContext::TraceFailure(v72, "MF::DLNA::CheckMP4VProfileLevel", 8013, -1072863756);
            }
            if ( !g_wppLevels )
              goto LABEL_158;
            v31 = 130;
          }
          else
          {
            if ( (unsigned __int8)byte_1801B110B >= 0x10u )
              WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 17), 127);
            v64 = (wchar_t *)CallStackTracing::s_wpInstance;
            MP4VProfileAndLevel = -1072863756;
            if ( !CallStackTracing::s_wpInstance )
            {
              v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
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
                CallStackContext::TraceFailure(v66, "MF::DLNA::CheckMP4VProfileLevel", 8002, -1072863756);
            }
            if ( !g_wppLevels )
              goto LABEL_158;
            v31 = 128;
          }
        }
        else
        {
          if ( (unsigned __int8)byte_1801B110B >= 0x10u )
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 17),
              118,
              &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
              v27,
              v75);
          v28 = (wchar_t *)CallStackTracing::s_wpInstance;
          MP4VProfileAndLevel = -1072863756;
          if ( !CallStackTracing::s_wpInstance )
          {
            v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
            CallStackTracing::s_wpInstance = v29;
            if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
            {
              v28 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v28 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v28 + 8) )
          {
            v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
            if ( *((_DWORD *)v30 + 499) != -1072863756 )
              CallStackContext::TraceFailure(v30, "MF::DLNA::CheckMP4VProfileLevel", 7972, -1072863756);
          }
          if ( !g_wppLevels )
            goto LABEL_158;
          v31 = 119;
        }
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v31,
          &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
          0,
          -1072863756);
        goto LABEL_158;
      }
      v24 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
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
        if ( *((_DWORD *)v26 + 499) != MP4VProfileAndLevel )
          CallStackContext::TraceFailure(v26, "MF::DLNA::CheckMP4VProfileLevel", 7965, MP4VProfileAndLevel);
      }
      if ( g_wppLevels )
      {
        v13 = 117;
        goto LABEL_13;
      }
    }
    else
    {
      v18 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v16, v17);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)v20 + 499) != MP4VProfileAndLevel )
          CallStackContext::TraceFailure(v20, "MF::DLNA::CheckMP4VProfileLevel", 7963, MP4VProfileAndLevel);
      }
      if ( g_wppLevels )
      {
        v13 = 116;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v10 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8, v9);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != MP4VProfileAndLevel )
        CallStackContext::TraceFailure(v12, "MF::DLNA::CheckMP4VProfileLevel", 7960, MP4VProfileAndLevel);
    }
    if ( g_wppLevels )
    {
      v13 = 115;
LABEL_13:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
        0,
        MP4VProfileAndLevel);
    }
  }
LABEL_158:
  CoTaskMemFree(pv);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v84);
  return (unsigned int)MP4VProfileAndLevel;
}

```

## disassembly

```asm
0x18016f718  mov     [rsp-28h+arg_8], rbx
0x18016f71d  push    rbp
0x18016f71e  push    rsi
0x18016f71f  push    rdi
0x18016f720  push    r14
0x18016f722  push    r15
0x18016f724  mov     rbp, rsp
0x18016f727  sub     rsp, 70h
0x18016f72b  mov     rdi, rdx
0x18016f72e  lea     r15, aMfDlnaCheckmp4; "MF::DLNA::CheckMP4VProfileLevel"
0x18016f735  mov     rbx, rcx
0x18016f738  mov     rdx, r15; char *
0x18016f73b  mov     r8d, 1F07h; int
0x18016f741  lea     rcx, [rbp+arg_0]; this
0x18016f745  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18016f74a  mov     rax, [rbx]
0x18016f74d  lea     r9, [rbp+arg_10]
0x18016f751  xor     r14d, r14d
0x18016f754  lea     r8, [rbp+pv]
0x18016f758  xorps   xmm0, xmm0
0x18016f75b  mov     [rbp+var_28], r14d
0x18016f75f  lea     rdx, MF_MT_USER_DATA
0x18016f766  mov     [rbp+var_24], r14w
0x18016f76b  mov     rax, [rax+80h]
0x18016f772  mov     rcx, rbx
0x18016f775  mov     [rbp+var_22], r14b
0x18016f779  movups  [rbp+var_20], xmm0
0x18016f77d  mov     [rbp+var_C], r14d
0x18016f781  mov     [rbp+var_8], r14
0x18016f785  mov     [rbp+pv], r14
0x18016f789  mov     [rbp+arg_10], r14d
0x18016f78d  mov     [rbp+var_3C], r14d
0x18016f791  mov     [rbp+var_38], r14d
0x18016f795  mov     [rbp+arg_0], r14d
0x18016f799  mov     [rbp+arg_18], r14d
0x18016f79d  mov     [rbp+var_40], r14d
0x18016f7a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016f7a6  test    eax, eax
0x18016f7a8  jns     loc_18016F868
0x18016f7ae  mov     rax, [rbx]
0x18016f7b1  lea     r9, [rbp+arg_10]
0x18016f7b5  lea     r8, [rbp+pv]
0x18016f7b9  mov     rcx, rbx
0x18016f7bc  lea     rdx, MF_MT_MPEG_SEQUENCE_HEADER
0x18016f7c3  mov     rax, [rax+80h]
0x18016f7ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016f7cf  mov     ebx, eax
0x18016f7d1  test    eax, eax
0x18016f7d3  jns     loc_18016F868
0x18016f7d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016f7e0  test    rcx, rcx
0x18016f7e3  jnz     short loc_18016F826
0x18016f7e5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18016f7eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18016f7f2  mov     rcx, rax
0x18016f7f5  test    rax, rax
0x18016f7f8  jz      short loc_18016F818
0x18016f7fa  mov     rax, [rax]
0x18016f7fd  mov     edx, 7F0h
0x18016f802  mov     rax, [rax+8]
0x18016f806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016f80b  test    eax, eax
0x18016f80d  jz      short loc_18016F818
0x18016f80f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016f816  jmp     short loc_18016F826
0x18016f818  lea     rcx, qword_1801B07E0; this
0x18016f81f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016f826  cmp     [rcx+8], r14b
0x18016f82a  jz      short loc_18016F84D
0x18016f82c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016f831  cmp     [rax+7CCh], ebx
0x18016f837  jz      short loc_18016F84D
0x18016f839  mov     r9d, ebx; int
0x18016f83c  mov     r8d, 1F18h; int
0x18016f842  mov     rdx, r15; char *
0x18016f845  mov     rcx, rax; this
0x18016f848  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18016f84d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18016f854  jb      loc_1801700B0
0x18016f85a  mov     edx, 73h ; 's'
0x18016f85f  mov     [rsp+70h+var_50], ebx
0x18016f863  jmp     loc_180170096
0x18016f868  mov     r8, [rbp+pv]; unsigned __int8 *
0x18016f86c  lea     rcx, [rbp+var_28]; this
0x18016f870  mov     edx, [rbp+arg_10]; unsigned int
0x18016f873  call    ?ParseData@CMP4VSequenceHeader@@QEAAJKPEBE@Z; CMP4VSequenceHeader::ParseData(ulong,uchar const *)
0x18016f878  mov     ebx, eax
0x18016f87a  test    eax, eax
0x18016f87c  jns     loc_18016F90D
0x18016f882  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016f889  test    rcx, rcx
0x18016f88c  jnz     short loc_18016F8CF
0x18016f88e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18016f894  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18016f89b  mov     rcx, rax
0x18016f89e  test    rax, rax
0x18016f8a1  jz      short loc_18016F8C1
0x18016f8a3  mov     rax, [rax]
0x18016f8a6  mov     edx, 7F0h
0x18016f8ab  mov     rax, [rax+8]
0x18016f8af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016f8b4  test    eax, eax
0x18016f8b6  jz      short loc_18016F8C1
0x18016f8b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016f8bf  jmp     short loc_18016F8CF
0x18016f8c1  lea     rcx, qword_1801B07E0; this
0x18016f8c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016f8cf  cmp     [rcx+8], r14b
0x18016f8d3  jz      short loc_18016F8F6
0x18016f8d5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016f8da  cmp     [rax+7CCh], ebx
0x18016f8e0  jz      short loc_18016F8F6
0x18016f8e2  mov     r9d, ebx; int
0x18016f8e5  mov     r8d, 1F1Bh; int
0x18016f8eb  mov     rdx, r15; char *
0x18016f8ee  mov     rcx, rax; this
0x18016f8f1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18016f8f6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18016f8fd  jb      loc_1801700B0
0x18016f903  mov     edx, 74h ; 't'
0x18016f908  jmp     loc_18016F85F
0x18016f90d  mov     cl, byte ptr [rbp+var_24]
0x18016f910  lea     r8, [rbp+var_38]
0x18016f914  lea     rdx, [rbp+var_3C]
0x18016f918  call    MF__DLNA__GetMP4VProfileAndLevel
0x18016f91d  mov     ebx, eax
0x18016f91f  test    eax, eax
0x18016f921  jns     loc_18016F9B2
0x18016f927  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016f92e  test    rcx, rcx
0x18016f931  jnz     short loc_18016F974
0x18016f933  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18016f939  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18016f940  mov     rcx, rax
0x18016f943  test    rax, rax
0x18016f946  jz      short loc_18016F966
0x18016f948  mov     rax, [rax]
0x18016f94b  mov     edx, 7F0h
0x18016f950  mov     rax, [rax+8]
0x18016f954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016f959  test    eax, eax
0x18016f95b  jz      short loc_18016F966
0x18016f95d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016f964  jmp     short loc_18016F974
0x18016f966  lea     rcx, qword_1801B07E0; this
0x18016f96d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016f974  cmp     [rcx+8], r14b
0x18016f978  jz      short loc_18016F99B
0x18016f97a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016f97f  cmp     [rax+7CCh], ebx
0x18016f985  jz      short loc_18016F99B
0x18016f987  mov     r9d, ebx; int
0x18016f98a  mov     r8d, 1F1Dh; int
0x18016f990  mov     rdx, r15; char *
0x18016f993  mov     rcx, rax; this
0x18016f996  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18016f99b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18016f9a2  jb      loc_1801700B0
0x18016f9a8  mov     edx, 75h ; 'u'
0x18016f9ad  jmp     loc_18016F85F
0x18016f9b2  mov     eax, [rdi+4]
0x18016f9b5  mov     ecx, [rbp+var_3C]
0x18016f9b8  cmp     eax, ecx
0x18016f9ba  jz      loc_18016FA81
0x18016f9c0  cmp     cs:byte_1801B110B, 10h
0x18016f9c7  jb      short loc_18016F9EF
0x18016f9c9  mov     [rsp+70h+var_50], ecx
0x18016f9cd  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x18016f9d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18016f9db  mov     edx, 76h ; 'v'
0x18016f9e0  mov     r9d, eax
0x18016f9e3  mov     rcx, [rcx+88h]
0x18016f9ea  call    WPP_SF_dd
0x18016f9ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016f9f6  mov     edi, 0C00D65F4h
0x18016f9fb  mov     ebx, edi
0x18016f9fd  test    rcx, rcx
0x18016fa00  jnz     short loc_18016FA43
0x18016fa02  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18016fa08  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18016fa0f  mov     rcx, rax
0x18016fa12  test    rax, rax
0x18016fa15  jz      short loc_18016FA35
0x18016fa17  mov     rax, [rax]
0x18016fa1a  mov     edx, 7F0h
0x18016fa1f  mov     rax, [rax+8]
0x18016fa23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016fa28  test    eax, eax
0x18016fa2a  jz      short loc_18016FA35
0x18016fa2c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016fa33  jmp     short loc_18016FA43
0x18016fa35  lea     rcx, qword_1801B07E0; this
0x18016fa3c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016fa43  cmp     [rcx+8], r14b
0x18016fa47  jz      short loc_18016FA6A
0x18016fa49  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016fa4e  cmp     [rax+7CCh], edi
0x18016fa54  jz      short loc_18016FA6A
0x18016fa56  mov     r9d, edi; int
0x18016fa59  mov     r8d, 1F24h; int
0x18016fa5f  mov     rdx, r15; char *
0x18016fa62  mov     rcx, rax; this
0x18016fa65  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18016fa6a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18016fa71  jb      loc_1801700B0
0x18016fa77  mov     edx, 77h ; 'w'
0x18016fa7c  jmp     loc_180170092
0x18016fa81  mov     ecx, [rdi+8]
0x18016fa84  mov     esi, [rbp+var_38]
0x18016fa87  cmp     esi, ecx
0x18016fa89  jz      loc_18016FFCB
0x18016fa8f  cmp     esi, [rdi+0Ch]
0x18016fa92  jz      loc_18016FFCB
0x18016fa98  cmp     eax, 1
0x18016fa9b  jnz     loc_18016FC80
0x18016faa1  lea     rdx, [rbp+arg_18]
0x18016faa5  call    MF__DLNA__GetMPEG4_P2_SP_Level_OrdinalValue
0x18016faaa  mov     ebx, eax
0x18016faac  test    eax, eax
0x18016faae  jns     loc_18016FB3F
0x18016fab4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016fabb  test    rcx, rcx
0x18016fabe  jnz     short loc_18016FB01
0x18016fac0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18016fac6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18016facd  mov     rcx, rax
0x18016fad0  test    rax, rax
0x18016fad3  jz      short loc_18016FAF3
0x18016fad5  mov     rax, [rax]
0x18016fad8  mov     edx, 7F0h
0x18016fadd  mov     rax, [rax+8]
0x18016fae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016fae6  test    eax, eax
0x18016fae8  jz      short loc_18016FAF3
0x18016faea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016faf1  jmp     short loc_18016FB01
0x18016faf3  lea     rcx, qword_1801B07E0; this
0x18016fafa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016fb01  cmp     [rcx+8], r14b
0x18016fb05  jz      short loc_18016FB28
0x18016fb07  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016fb0c  cmp     [rax+7CCh], ebx
0x18016fb12  jz      short loc_18016FB28
0x18016fb14  mov     r9d, ebx; int
0x18016fb17  mov     r8d, 1F2Ch; int
0x18016fb1d  mov     rdx, r15; char *
0x18016fb20  mov     rcx, rax; this
0x18016fb23  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18016fb28  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18016fb2f  jb      loc_1801700B0
0x18016fb35  mov     edx, 78h ; 'x'
0x18016fb3a  jmp     loc_18016F85F
0x18016fb3f  mov     ecx, [rdi+0Ch]
0x18016fb42  lea     rdx, [rbp+var_40]
0x18016fb46  call    MF__DLNA__GetMPEG4_P2_SP_Level_OrdinalValue
0x18016fb4b  mov     ebx, eax
0x18016fb4d  test    eax, eax
0x18016fb4f  jns     loc_18016FBE0
0x18016fb55  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016fb5c  test    rcx, rcx
0x18016fb5f  jnz     short loc_18016FBA2
0x18016fb61  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18016fb67  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18016fb6e  mov     rcx, rax
0x18016fb71  test    rax, rax
0x18016fb74  jz      short loc_18016FB94
0x18016fb76  mov     rax, [rax]
0x18016fb79  mov     edx, 7F0h
0x18016fb7e  mov     rax, [rax+8]
0x18016fb82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016fb87  test    eax, eax
0x18016fb89  jz      short loc_18016FB94
0x18016fb8b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016fb92  jmp     short loc_18016FBA2
0x18016fb94  lea     rcx, qword_1801B07E0; this
0x18016fb9b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016fba2  cmp     [rcx+8], r14b
0x18016fba6  jz      short loc_18016FBC9
0x18016fba8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016fbad  cmp     [rax+7CCh], ebx
0x18016fbb3  jz      short loc_18016FBC9
0x18016fbb5  mov     r9d, ebx; int
0x18016fbb8  mov     r8d, 1F2Dh; int
0x18016fbbe  mov     rdx, r15; char *
0x18016fbc1  mov     rcx, rax; this
0x18016fbc4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18016fbc9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18016fbd0  jb      loc_1801700B0
0x18016fbd6  mov     edx, 79h ; 'y'
0x18016fbdb  jmp     loc_18016F85F
0x18016fbe0  lea     rdx, [rbp+arg_0]
0x18016fbe4  mov     ecx, esi
0x18016fbe6  call    MF__DLNA__GetMPEG4_P2_SP_Level_OrdinalValue
0x18016fbeb  mov     ebx, eax
0x18016fbed  test    eax, eax
0x18016fbef  jns     loc_18016FE68
0x18016fbf5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016fbfc  test    rcx, rcx
0x18016fbff  jnz     short loc_18016FC42
0x18016fc01  call    cs:__imp_MFGetCallStackTracingWeakReference
  ... truncated ...
```
