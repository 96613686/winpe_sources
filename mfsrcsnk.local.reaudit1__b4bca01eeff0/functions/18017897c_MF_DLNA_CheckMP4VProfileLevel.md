# MF::DLNA::CheckMP4VProfileLevel

- ea: `0x18017897c`
- end: `0x180179392`
- name: `MF::DLNA::CheckMP4VProfileLevel`
- size: `2582`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18017a770`
- `0x18017aa50`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x18006e524`
- `0x180079680`
- `0x180091c5c`
- `0x1800cab9c`
- `0x1800df4c8`
- `0x180105a6c`
- `0x18011cbac`
- `0x18017897c`
- `0x18017abfc`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180178a49`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180178af8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180178ba3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180178c78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180178d3c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180178de3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180178e89`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180178f36`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180178fdd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180179083`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18017915c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801791f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801792c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180178a49`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180178af8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180178ba3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180178c78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180178d3c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180178de3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180178e89`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180178f36`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180178fdd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180179083`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18017915c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801791f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801792c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180179366`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180179366`

## pseudocode

```c
__int64 __fastcall MF::DLNA::CheckMP4VProfileLevel(__int64 *a1, _DWORD *a2)
{
  __int64 v4; // rax
  int (__fastcall *v5)(__int64 *, const GUID *, LPVOID *, unsigned int *); // rax
  __int64 v6; // rdx
  int MP4VProfileAndLevel; // ebx
  wchar_t *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rcx
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  unsigned int v21; // eax
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  unsigned int v27; // esi
  __int64 v28; // rdx
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v32; // rdx
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
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
  unsigned int v60; // [rsp+30h] [rbp-40h] BYREF
  int v61; // [rsp+34h] [rbp-3Ch] BYREF
  unsigned int v62; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-30h] BYREF
  int v64; // [rsp+48h] [rbp-28h] BYREF
  __int16 v65; // [rsp+4Ch] [rbp-24h]
  char v66; // [rsp+4Eh] [rbp-22h]
  __int128 v67; // [rsp+50h] [rbp-20h]
  int v68; // [rsp+64h] [rbp-Ch]
  __int64 v69; // [rsp+68h] [rbp-8h]
  unsigned int v70; // [rsp+A0h] [rbp+30h] BYREF
  unsigned int v71; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v72; // [rsp+B8h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v70, "MF::DLNA::CheckMP4VProfileLevel", 7943);
  v4 = *a1;
  v64 = 0;
  v65 = 0;
  v5 = *(int (__fastcall **)(__int64 *, const GUID *, LPVOID *, unsigned int *))(v4 + 128);
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  pv = 0;
  v71 = 0;
  v61 = 0;
  v62 = 0;
  v70 = 0;
  v72 = 0;
  v60 = 0;
  if ( v5(a1, &MF_MT_USER_DATA, &pv, &v71) >= 0
    || (MP4VProfileAndLevel = (*(__int64 (__fastcall **)(__int64 *, const GUID *, LPVOID *, unsigned int *))(*a1 + 128))(
                                a1,
                                &MF_MT_MPEG_SEQUENCE_HEADER,
                                &pv,
                                &v71),
        MP4VProfileAndLevel >= 0) )
  {
    MP4VProfileAndLevel = CMP4VSequenceHeader::ParseData((CMP4VSequenceHeader *)&v64, v71, (const unsigned __int8 *)pv);
    if ( MP4VProfileAndLevel >= 0 )
    {
      LOBYTE(v13) = v65;
      MP4VProfileAndLevel = MF::DLNA::GetMP4VProfileAndLevel(v13, &v61, &v62);
      if ( MP4VProfileAndLevel >= 0 )
      {
        v21 = a2[1];
        if ( v21 == v61 )
        {
          v26 = (unsigned int)a2[2];
          v27 = v62;
          if ( v62 == (_DWORD)v26 || v62 == a2[3] )
            goto LABEL_155;
          if ( v21 == 1 )
          {
            MP4VProfileAndLevel = MF::DLNA::GetMPEG4_P2_SP_Level_OrdinalValue(v26, &v72);
            if ( MP4VProfileAndLevel < 0 )
            {
              v29 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
                CallStackTracing::s_wpInstance = v30;
                if ( v30
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
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
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != MP4VProfileAndLevel )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "MF::DLNA::CheckMP4VProfileLevel",
                    7980,
                    MP4VProfileAndLevel);
              }
              if ( g_wppLevels )
              {
                v11 = 120;
                goto LABEL_13;
              }
              goto LABEL_158;
            }
            MP4VProfileAndLevel = MF::DLNA::GetMPEG4_P2_SP_Level_OrdinalValue((unsigned int)a2[3], &v60);
            if ( MP4VProfileAndLevel < 0 )
            {
              v33 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
                CallStackTracing::s_wpInstance = v34;
                if ( v34
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
                {
                  v33 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v33 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v33 + 8) )
              {
                v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
                if ( *((_DWORD *)v35 + 499) != MP4VProfileAndLevel )
                  CallStackContext::TraceFailure(v35, "MF::DLNA::CheckMP4VProfileLevel", 7981, MP4VProfileAndLevel);
              }
              if ( g_wppLevels )
              {
                v11 = 121;
                goto LABEL_13;
              }
              goto LABEL_158;
            }
            MP4VProfileAndLevel = MF::DLNA::GetMPEG4_P2_SP_Level_OrdinalValue(v27, &v70);
            if ( MP4VProfileAndLevel < 0 )
            {
              v36 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
                CallStackTracing::s_wpInstance = v37;
                if ( v37
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
                {
                  v36 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v36 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v36 + 8) )
              {
                v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
                if ( *((_DWORD *)v38 + 499) != MP4VProfileAndLevel )
                  CallStackContext::TraceFailure(v38, "MF::DLNA::CheckMP4VProfileLevel", 7982, MP4VProfileAndLevel);
              }
              if ( g_wppLevels )
              {
                v11 = 122;
                goto LABEL_13;
              }
              goto LABEL_158;
            }
          }
          else
          {
            if ( v21 != 18 )
            {
              v53 = (wchar_t *)CallStackTracing::s_wpInstance;
              MP4VProfileAndLevel = -2147418113;
              if ( !CallStackTracing::s_wpInstance )
              {
                v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
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
                if ( *((_DWORD *)v55 + 499) != -2147418113 )
                  CallStackContext::TraceFailure(v55, "MF::DLNA::CheckMP4VProfileLevel", 7993, -2147418113);
              }
              if ( g_wppLevels )
              {
                v11 = 126;
                goto LABEL_13;
              }
              goto LABEL_158;
            }
            MP4VProfileAndLevel = MF::DLNA::GetMPEG4_P2_ASP_Level_OrdinalValue(v26, &v72);
            if ( MP4VProfileAndLevel < 0 )
            {
              v40 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
                CallStackTracing::s_wpInstance = v41;
                if ( v41
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
                {
                  v40 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v40 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v40 + 8) )
              {
                v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
                if ( *((_DWORD *)v42 + 499) != MP4VProfileAndLevel )
                  CallStackContext::TraceFailure(v42, "MF::DLNA::CheckMP4VProfileLevel", 7986, MP4VProfileAndLevel);
              }
              if ( g_wppLevels )
              {
                v11 = 123;
                goto LABEL_13;
              }
              goto LABEL_158;
            }
            MP4VProfileAndLevel = MF::DLNA::GetMPEG4_P2_ASP_Level_OrdinalValue((unsigned int)a2[3], &v60);
            if ( MP4VProfileAndLevel < 0 )
            {
              v44 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43);
                CallStackTracing::s_wpInstance = v45;
                if ( v45
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
                {
                  v44 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v44 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v44 + 8) )
              {
                v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
                if ( *((_DWORD *)v46 + 499) != MP4VProfileAndLevel )
                  CallStackContext::TraceFailure(v46, "MF::DLNA::CheckMP4VProfileLevel", 7987, MP4VProfileAndLevel);
              }
              if ( g_wppLevels )
              {
                v11 = 124;
                goto LABEL_13;
              }
              goto LABEL_158;
            }
            MP4VProfileAndLevel = MF::DLNA::GetMPEG4_P2_ASP_Level_OrdinalValue(v27, &v70);
            if ( MP4VProfileAndLevel < 0 )
            {
              v47 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
                CallStackTracing::s_wpInstance = v48;
                if ( v48
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
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
                if ( *((_DWORD *)v49 + 499) != MP4VProfileAndLevel )
                  CallStackContext::TraceFailure(v49, "MF::DLNA::CheckMP4VProfileLevel", 7988, MP4VProfileAndLevel);
              }
              if ( g_wppLevels )
              {
                v11 = 125;
                goto LABEL_13;
              }
              goto LABEL_158;
            }
          }
          if ( v70 >= v72 && v70 <= v60 )
          {
LABEL_155:
            if ( (*a2 & 0x1000000) == 0 || v68 )
              goto LABEL_158;
            if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 129, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
            v56 = (wchar_t *)CallStackTracing::s_wpInstance;
            MP4VProfileAndLevel = -1072863756;
            if ( !CallStackTracing::s_wpInstance )
            {
              v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
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
                CallStackContext::TraceFailure(v58, "MF::DLNA::CheckMP4VProfileLevel", 8013, -1072863756);
            }
            if ( !g_wppLevels )
              goto LABEL_158;
            v25 = 130;
          }
          else
          {
            if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
              WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 17), 127);
            v50 = (wchar_t *)CallStackTracing::s_wpInstance;
            MP4VProfileAndLevel = -1072863756;
            if ( !CallStackTracing::s_wpInstance )
            {
              v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
              CallStackTracing::s_wpInstance = v51;
              if ( v51
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
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
                CallStackContext::TraceFailure(v52, "MF::DLNA::CheckMP4VProfileLevel", 8002, -1072863756);
            }
            if ( !g_wppLevels )
              goto LABEL_158;
            v25 = 128;
          }
        }
        else
        {
          if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 17),
              118,
              &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
              v21,
              v61);
          v22 = (wchar_t *)CallStackTracing::s_wpInstance;
          MP4VProfileAndLevel = -1072863756;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
            CallStackTracing::s_wpInstance = v23;
            if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
            {
              v22 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v22 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v22 + 8) )
          {
            v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
            if ( *((_DWORD *)v24 + 499) != -1072863756 )
              CallStackContext::TraceFailure(v24, "MF::DLNA::CheckMP4VProfileLevel", 7972, -1072863756);
          }
          if ( !g_wppLevels )
            goto LABEL_158;
          v25 = 119;
        }
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v25,
          &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
          0,
          -1072863756);
        goto LABEL_158;
      }
      v18 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)v20 + 499) != MP4VProfileAndLevel )
          CallStackContext::TraceFailure(v20, "MF::DLNA::CheckMP4VProfileLevel", 7965, MP4VProfileAndLevel);
      }
      if ( g_wppLevels )
      {
        v11 = 117;
        goto LABEL_13;
      }
    }
    else
    {
      v14 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v16 + 499) != MP4VProfileAndLevel )
          CallStackContext::TraceFailure(v16, "MF::DLNA::CheckMP4VProfileLevel", 7963, MP4VProfileAndLevel);
      }
      if ( g_wppLevels )
      {
        v11 = 116;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v8 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v10 + 499) != MP4VProfileAndLevel )
        CallStackContext::TraceFailure(v10, "MF::DLNA::CheckMP4VProfileLevel", 7960, MP4VProfileAndLevel);
    }
    if ( g_wppLevels )
    {
      v11 = 115;
LABEL_13:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
        0,
        MP4VProfileAndLevel);
    }
  }
LABEL_158:
  CoTaskMemFree(pv);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v70);
  return (unsigned int)MP4VProfileAndLevel;
}

```

## disassembly

```asm
0x18017897c  mov     [rsp-28h+arg_8], rbx
0x180178981  push    rbp
0x180178982  push    rsi
0x180178983  push    rdi
0x180178984  push    r14
0x180178986  push    r15
0x180178988  mov     rbp, rsp
0x18017898b  sub     rsp, 70h
0x18017898f  mov     rdi, rdx
0x180178992  lea     r15, aMfDlnaCheckmp4; "MF::DLNA::CheckMP4VProfileLevel"
0x180178999  mov     rbx, rcx
0x18017899c  mov     rdx, r15; char *
0x18017899f  mov     r8d, 1F07h; int
0x1801789a5  lea     rcx, [rbp+arg_0]; this
0x1801789a9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801789ae  mov     rax, [rbx]
0x1801789b1  lea     r9, [rbp+arg_10]
0x1801789b5  xor     r14d, r14d
0x1801789b8  lea     r8, [rbp+pv]
0x1801789bc  xorps   xmm0, xmm0
0x1801789bf  mov     [rbp+var_28], r14d
0x1801789c3  lea     rdx, MF_MT_USER_DATA
0x1801789ca  mov     [rbp+var_24], r14w
0x1801789cf  mov     rax, [rax+80h]
0x1801789d6  mov     rcx, rbx
0x1801789d9  mov     [rbp+var_22], r14b
0x1801789dd  movups  [rbp+var_20], xmm0
0x1801789e1  mov     [rbp+var_C], r14d
0x1801789e5  mov     [rbp+var_8], r14
0x1801789e9  mov     [rbp+pv], r14
0x1801789ed  mov     [rbp+arg_10], r14d
0x1801789f1  mov     [rbp+var_3C], r14d
0x1801789f5  mov     [rbp+var_38], r14d
0x1801789f9  mov     [rbp+arg_0], r14d
0x1801789fd  mov     [rbp+arg_18], r14d
0x180178a01  mov     [rbp+var_40], r14d
0x180178a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180178a0a  test    eax, eax
0x180178a0c  jns     loc_180178AD2
0x180178a12  mov     rax, [rbx]
0x180178a15  lea     r9, [rbp+arg_10]
0x180178a19  lea     r8, [rbp+pv]
0x180178a1d  mov     rcx, rbx
0x180178a20  lea     rdx, MF_MT_MPEG_SEQUENCE_HEADER
0x180178a27  mov     rax, [rax+80h]
0x180178a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180178a33  mov     ebx, eax
0x180178a35  test    eax, eax
0x180178a37  jns     loc_180178AD2
0x180178a3d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180178a44  test    rcx, rcx
0x180178a47  jnz     short loc_180178A90
0x180178a49  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180178a50  nop     dword ptr [rax+rax+00h]
0x180178a55  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180178a5c  mov     rcx, rax
0x180178a5f  test    rax, rax
0x180178a62  jz      short loc_180178A82
0x180178a64  mov     rax, [rax]
0x180178a67  mov     edx, 7F0h
0x180178a6c  mov     rax, [rax+8]
0x180178a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180178a75  test    eax, eax
0x180178a77  jz      short loc_180178A82
0x180178a79  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180178a80  jmp     short loc_180178A90
0x180178a82  lea     rcx, qword_1801B97E0; this
0x180178a89  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180178a90  cmp     [rcx+8], r14b
0x180178a94  jz      short loc_180178AB7
0x180178a96  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180178a9b  cmp     [rax+7CCh], ebx
0x180178aa1  jz      short loc_180178AB7
0x180178aa3  mov     r9d, ebx; int
0x180178aa6  mov     r8d, 1F18h; int
0x180178aac  mov     rdx, r15; char *
0x180178aaf  mov     rcx, rax; this
0x180178ab2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180178ab7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180178abe  jb      loc_180179362
0x180178ac4  mov     edx, 73h ; 's'
0x180178ac9  mov     [rsp+70h+var_50], ebx
0x180178acd  jmp     loc_180179348
0x180178ad2  mov     r8, [rbp+pv]; unsigned __int8 *
0x180178ad6  lea     rcx, [rbp+var_28]; this
0x180178ada  mov     edx, [rbp+arg_10]; unsigned int
0x180178add  call    ?ParseData@CMP4VSequenceHeader@@QEAAJKPEBE@Z; CMP4VSequenceHeader::ParseData(ulong,uchar const *)
0x180178ae2  mov     ebx, eax
0x180178ae4  test    eax, eax
0x180178ae6  jns     loc_180178B7D
0x180178aec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180178af3  test    rcx, rcx
0x180178af6  jnz     short loc_180178B3F
0x180178af8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180178aff  nop     dword ptr [rax+rax+00h]
0x180178b04  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180178b0b  mov     rcx, rax
0x180178b0e  test    rax, rax
0x180178b11  jz      short loc_180178B31
0x180178b13  mov     rax, [rax]
0x180178b16  mov     edx, 7F0h
0x180178b1b  mov     rax, [rax+8]
0x180178b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180178b24  test    eax, eax
0x180178b26  jz      short loc_180178B31
0x180178b28  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180178b2f  jmp     short loc_180178B3F
0x180178b31  lea     rcx, qword_1801B97E0; this
0x180178b38  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180178b3f  cmp     [rcx+8], r14b
0x180178b43  jz      short loc_180178B66
0x180178b45  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180178b4a  cmp     [rax+7CCh], ebx
0x180178b50  jz      short loc_180178B66
0x180178b52  mov     r9d, ebx; int
0x180178b55  mov     r8d, 1F1Bh; int
0x180178b5b  mov     rdx, r15; char *
0x180178b5e  mov     rcx, rax; this
0x180178b61  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180178b66  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180178b6d  jb      loc_180179362
0x180178b73  mov     edx, 74h ; 't'
0x180178b78  jmp     loc_180178AC9
0x180178b7d  mov     cl, byte ptr [rbp+var_24]
0x180178b80  lea     r8, [rbp+var_38]
0x180178b84  lea     rdx, [rbp+var_3C]
0x180178b88  call    MF__DLNA__GetMP4VProfileAndLevel
0x180178b8d  mov     ebx, eax
0x180178b8f  test    eax, eax
0x180178b91  jns     loc_180178C28
0x180178b97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180178b9e  test    rcx, rcx
0x180178ba1  jnz     short loc_180178BEA
0x180178ba3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180178baa  nop     dword ptr [rax+rax+00h]
0x180178baf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180178bb6  mov     rcx, rax
0x180178bb9  test    rax, rax
0x180178bbc  jz      short loc_180178BDC
0x180178bbe  mov     rax, [rax]
0x180178bc1  mov     edx, 7F0h
0x180178bc6  mov     rax, [rax+8]
0x180178bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180178bcf  test    eax, eax
0x180178bd1  jz      short loc_180178BDC
0x180178bd3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180178bda  jmp     short loc_180178BEA
0x180178bdc  lea     rcx, qword_1801B97E0; this
0x180178be3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180178bea  cmp     [rcx+8], r14b
0x180178bee  jz      short loc_180178C11
0x180178bf0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180178bf5  cmp     [rax+7CCh], ebx
0x180178bfb  jz      short loc_180178C11
0x180178bfd  mov     r9d, ebx; int
0x180178c00  mov     r8d, 1F1Dh; int
0x180178c06  mov     rdx, r15; char *
0x180178c09  mov     rcx, rax; this
0x180178c0c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180178c11  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180178c18  jb      loc_180179362
0x180178c1e  mov     edx, 75h ; 'u'
0x180178c23  jmp     loc_180178AC9
0x180178c28  mov     eax, [rdi+4]
0x180178c2b  mov     ecx, [rbp+var_3C]
0x180178c2e  cmp     eax, ecx
0x180178c30  jz      loc_180178CFD
0x180178c36  cmp     cs:byte_1801BA10B, 10h
0x180178c3d  jb      short loc_180178C65
0x180178c3f  mov     [rsp+70h+var_50], ecx
0x180178c43  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x180178c4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180178c51  mov     edx, 76h ; 'v'
0x180178c56  mov     r9d, eax
0x180178c59  mov     rcx, [rcx+88h]
0x180178c60  call    WPP_SF_dd
0x180178c65  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180178c6c  mov     edi, 0C00D65F4h
0x180178c71  mov     ebx, edi
0x180178c73  test    rcx, rcx
0x180178c76  jnz     short loc_180178CBF
0x180178c78  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180178c7f  nop     dword ptr [rax+rax+00h]
0x180178c84  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180178c8b  mov     rcx, rax
0x180178c8e  test    rax, rax
0x180178c91  jz      short loc_180178CB1
0x180178c93  mov     rax, [rax]
0x180178c96  mov     edx, 7F0h
0x180178c9b  mov     rax, [rax+8]
0x180178c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180178ca4  test    eax, eax
0x180178ca6  jz      short loc_180178CB1
0x180178ca8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180178caf  jmp     short loc_180178CBF
0x180178cb1  lea     rcx, qword_1801B97E0; this
0x180178cb8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180178cbf  cmp     [rcx+8], r14b
0x180178cc3  jz      short loc_180178CE6
0x180178cc5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180178cca  cmp     [rax+7CCh], edi
0x180178cd0  jz      short loc_180178CE6
0x180178cd2  mov     r9d, edi; int
0x180178cd5  mov     r8d, 1F24h; int
0x180178cdb  mov     rdx, r15; char *
0x180178cde  mov     rcx, rax; this
0x180178ce1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180178ce6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180178ced  jb      loc_180179362
0x180178cf3  mov     edx, 77h ; 'w'
0x180178cf8  jmp     loc_180179344
0x180178cfd  mov     ecx, [rdi+8]
0x180178d00  mov     esi, [rbp+var_38]
0x180178d03  cmp     esi, ecx
0x180178d05  jz      loc_180179277
0x180178d0b  cmp     esi, [rdi+0Ch]
0x180178d0e  jz      loc_180179277
0x180178d14  cmp     eax, 1
0x180178d17  jnz     loc_180178F0E
0x180178d1d  lea     rdx, [rbp+arg_18]
0x180178d21  call    MF__DLNA__GetMPEG4_P2_SP_Level_OrdinalValue
0x180178d26  mov     ebx, eax
0x180178d28  test    eax, eax
0x180178d2a  jns     loc_180178DC1
0x180178d30  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180178d37  test    rcx, rcx
0x180178d3a  jnz     short loc_180178D83
0x180178d3c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180178d43  nop     dword ptr [rax+rax+00h]
0x180178d48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180178d4f  mov     rcx, rax
0x180178d52  test    rax, rax
0x180178d55  jz      short loc_180178D75
0x180178d57  mov     rax, [rax]
0x180178d5a  mov     edx, 7F0h
0x180178d5f  mov     rax, [rax+8]
0x180178d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180178d68  test    eax, eax
0x180178d6a  jz      short loc_180178D75
0x180178d6c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180178d73  jmp     short loc_180178D83
0x180178d75  lea     rcx, qword_1801B97E0; this
0x180178d7c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180178d83  cmp     [rcx+8], r14b
0x180178d87  jz      short loc_180178DAA
0x180178d89  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180178d8e  cmp     [rax+7CCh], ebx
0x180178d94  jz      short loc_180178DAA
0x180178d96  mov     r9d, ebx; int
0x180178d99  mov     r8d, 1F2Ch; int
0x180178d9f  mov     rdx, r15; char *
0x180178da2  mov     rcx, rax; this
0x180178da5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180178daa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180178db1  jb      loc_180179362
0x180178db7  mov     edx, 78h ; 'x'
0x180178dbc  jmp     loc_180178AC9
0x180178dc1  mov     ecx, [rdi+0Ch]
0x180178dc4  lea     rdx, [rbp+var_40]
0x180178dc8  call    MF__DLNA__GetMPEG4_P2_SP_Level_OrdinalValue
0x180178dcd  mov     ebx, eax
0x180178dcf  test    eax, eax
0x180178dd1  jns     loc_180178E68
0x180178dd7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180178dde  test    rcx, rcx
0x180178de1  jnz     short loc_180178E2A
0x180178de3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180178dea  nop     dword ptr [rax+rax+00h]
0x180178def  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180178df6  mov     rcx, rax
0x180178df9  test    rax, rax
0x180178dfc  jz      short loc_180178E1C
0x180178dfe  mov     rax, [rax]
0x180178e01  mov     edx, 7F0h
0x180178e06  mov     rax, [rax+8]
0x180178e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180178e0f  test    eax, eax
0x180178e11  jz      short loc_180178E1C
0x180178e13  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180178e1a  jmp     short loc_180178E2A
0x180178e1c  lea     rcx, qword_1801B97E0; this
0x180178e23  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180178e2a  cmp     [rcx+8], r14b
0x180178e2e  jz      short loc_180178E51
0x180178e30  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180178e35  cmp     [rax+7CCh], ebx
0x180178e3b  jz      short loc_180178E51
0x180178e3d  mov     r9d, ebx; int
0x180178e40  mov     r8d, 1F2Dh; int
0x180178e46  mov     rdx, r15; char *
0x180178e49  mov     rcx, rax; this
0x180178e4c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180178e51  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180178e58  jb      loc_180179362
0x180178e5e  mov     edx, 79h ; 'y'
0x180178e63  jmp     loc_180178AC9
0x180178e68  lea     rdx, [rbp+arg_0]
0x180178e6c  mov     ecx, esi
0x180178e6e  call    MF__DLNA__GetMPEG4_P2_SP_Level_OrdinalValue
0x180178e73  mov     ebx, eax
  ... truncated ...
```
