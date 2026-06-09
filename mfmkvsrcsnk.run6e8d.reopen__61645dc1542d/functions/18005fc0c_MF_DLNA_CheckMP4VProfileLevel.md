# MF::DLNA::CheckMP4VProfileLevel

- ea: `0x18005fc0c`
- end: `0x1800605cd`
- name: `MF::DLNA::CheckMP4VProfileLevel`
- size: `2497`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180063c90`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18005fc0c`
- `0x1800619d0`
- `0x180061c04`
- `0x180061d6c`
- `0x18006408c`
- `0x1800640f8`
- `0x180064144`
- `0x180071330`
- `0x18007e5e8`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800605a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800605a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005fcd9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005fd82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005fe27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005fef6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ffb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060055`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800600f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006019c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006023d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800602dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800603b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060440`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060510`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005fcd9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005fd82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005fe27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005fef6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ffb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060055`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800600f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006019c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006023d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800602dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800603b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060440`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060510`

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
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  unsigned int v27; // eax
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  unsigned int v33; // esi
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // r9
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  __int64 *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  __int64 *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  __int64 *v70; // rcx
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
              v37 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35, v36);
                CallStackTracing::s_wpInstance = v38;
                if ( v38
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
                {
                  v37 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v37 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v43 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40, v41, v42);
                CallStackTracing::s_wpInstance = v44;
                if ( v44
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
                {
                  v43 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v43 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v46 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
                CallStackTracing::s_wpInstance = v47;
                if ( v47
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
                {
                  v46 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v46 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v67 = (__int64 *)CallStackTracing::s_wpInstance;
              MP4VProfileAndLevel = -2147418113;
              if ( !CallStackTracing::s_wpInstance )
              {
                v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
                CallStackTracing::s_wpInstance = v68;
                if ( v68
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
                {
                  v67 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v67 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v52 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49, v50, v51);
                CallStackTracing::s_wpInstance = v53;
                if ( v53
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
                {
                  v52 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v52 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v58 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56, v57);
                CallStackTracing::s_wpInstance = v59;
                if ( v59
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
                {
                  v58 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v58 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v61 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
                CallStackTracing::s_wpInstance = v62;
                if ( v62
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
                {
                  v61 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v61 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            if ( (unsigned __int8)byte_1800D78D3 >= 0x10u )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 129, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids);
            v70 = (__int64 *)CallStackTracing::s_wpInstance;
            MP4VProfileAndLevel = -1072863756;
            if ( !CallStackTracing::s_wpInstance )
            {
              v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
              CallStackTracing::s_wpInstance = v71;
              if ( v71
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
              {
                v70 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v70 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            if ( (unsigned __int8)byte_1800D78D3 >= 0x10u )
              WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 17), 127);
            v64 = (__int64 *)CallStackTracing::s_wpInstance;
            MP4VProfileAndLevel = -1072863756;
            if ( !CallStackTracing::s_wpInstance )
            {
              v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
              CallStackTracing::s_wpInstance = v65;
              if ( v65
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
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
          if ( (unsigned __int8)byte_1800D78D3 >= 0x10u )
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 17),
              118,
              &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids,
              v27,
              v75);
          v28 = (__int64 *)CallStackTracing::s_wpInstance;
          MP4VProfileAndLevel = -1072863756;
          if ( !CallStackTracing::s_wpInstance )
          {
            v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
            CallStackTracing::s_wpInstance = v29;
            if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
            {
              v28 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v28 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
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
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v16, v17);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8, v9);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18005fc0c  mov     [rsp-28h+arg_8], rbx
0x18005fc11  push    rbp
0x18005fc12  push    rsi
0x18005fc13  push    rdi
0x18005fc14  push    r14
0x18005fc16  push    r15
0x18005fc18  mov     rbp, rsp
0x18005fc1b  sub     rsp, 70h
0x18005fc1f  mov     rdi, rdx
0x18005fc22  lea     r15, aMfDlnaCheckmp4; "MF::DLNA::CheckMP4VProfileLevel"
0x18005fc29  mov     rbx, rcx
0x18005fc2c  mov     rdx, r15; char *
0x18005fc2f  mov     r8d, 1F07h; int
0x18005fc35  lea     rcx, [rbp+arg_0]; this
0x18005fc39  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005fc3e  mov     rax, [rbx]
0x18005fc41  lea     r9, [rbp+arg_10]
0x18005fc45  xor     r14d, r14d
0x18005fc48  lea     r8, [rbp+pv]
0x18005fc4c  xorps   xmm0, xmm0
0x18005fc4f  mov     [rbp+var_28], r14d
0x18005fc53  lea     rdx, MF_MT_USER_DATA
0x18005fc5a  mov     [rbp+var_24], r14w
0x18005fc5f  mov     rax, [rax+80h]
0x18005fc66  mov     rcx, rbx
0x18005fc69  mov     [rbp+var_22], r14b
0x18005fc6d  movups  [rbp+var_20], xmm0
0x18005fc71  mov     [rbp+var_C], r14d
0x18005fc75  mov     [rbp+var_8], r14
0x18005fc79  mov     [rbp+pv], r14
0x18005fc7d  mov     [rbp+arg_10], r14d
0x18005fc81  mov     [rbp+var_3C], r14d
0x18005fc85  mov     [rbp+var_38], r14d
0x18005fc89  mov     [rbp+arg_0], r14d
0x18005fc8d  mov     [rbp+arg_18], r14d
0x18005fc91  mov     [rbp+var_40], r14d
0x18005fc95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fc9a  test    eax, eax
0x18005fc9c  jns     loc_18005FD5C
0x18005fca2  mov     rax, [rbx]
0x18005fca5  lea     r9, [rbp+arg_10]
0x18005fca9  lea     r8, [rbp+pv]
0x18005fcad  mov     rcx, rbx
0x18005fcb0  lea     rdx, MF_MT_MPEG_SEQUENCE_HEADER
0x18005fcb7  mov     rax, [rax+80h]
0x18005fcbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fcc3  mov     ebx, eax
0x18005fcc5  test    eax, eax
0x18005fcc7  jns     loc_18005FD5C
0x18005fccd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fcd4  test    rcx, rcx
0x18005fcd7  jnz     short loc_18005FD1A
0x18005fcd9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005fcdf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fce6  mov     rcx, rax
0x18005fce9  test    rax, rax
0x18005fcec  jz      short loc_18005FD0C
0x18005fcee  mov     rax, [rax]
0x18005fcf1  mov     edx, 7F0h
0x18005fcf6  mov     rax, [rax+8]
0x18005fcfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fcff  test    eax, eax
0x18005fd01  jz      short loc_18005FD0C
0x18005fd03  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fd0a  jmp     short loc_18005FD1A
0x18005fd0c  lea     rcx, qword_1800D6F70; this
0x18005fd13  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fd1a  cmp     [rcx+8], r14b
0x18005fd1e  jz      short loc_18005FD41
0x18005fd20  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005fd25  cmp     [rax+7CCh], ebx
0x18005fd2b  jz      short loc_18005FD41
0x18005fd2d  mov     r9d, ebx; int
0x18005fd30  mov     r8d, 1F18h; int
0x18005fd36  mov     rdx, r15; char *
0x18005fd39  mov     rcx, rax; this
0x18005fd3c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005fd41  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005fd48  jb      loc_1800605A4
0x18005fd4e  mov     edx, 73h ; 's'
0x18005fd53  mov     [rsp+70h+var_50], ebx
0x18005fd57  jmp     loc_18006058A
0x18005fd5c  mov     r8, [rbp+pv]; unsigned __int8 *
0x18005fd60  lea     rcx, [rbp+var_28]; this
0x18005fd64  mov     edx, [rbp+arg_10]; unsigned int
0x18005fd67  call    ?ParseData@CMP4VSequenceHeader@@QEAAJKPEBE@Z; CMP4VSequenceHeader::ParseData(ulong,uchar const *)
0x18005fd6c  mov     ebx, eax
0x18005fd6e  test    eax, eax
0x18005fd70  jns     loc_18005FE01
0x18005fd76  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fd7d  test    rcx, rcx
0x18005fd80  jnz     short loc_18005FDC3
0x18005fd82  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005fd88  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fd8f  mov     rcx, rax
0x18005fd92  test    rax, rax
0x18005fd95  jz      short loc_18005FDB5
0x18005fd97  mov     rax, [rax]
0x18005fd9a  mov     edx, 7F0h
0x18005fd9f  mov     rax, [rax+8]
0x18005fda3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fda8  test    eax, eax
0x18005fdaa  jz      short loc_18005FDB5
0x18005fdac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fdb3  jmp     short loc_18005FDC3
0x18005fdb5  lea     rcx, qword_1800D6F70; this
0x18005fdbc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fdc3  cmp     [rcx+8], r14b
0x18005fdc7  jz      short loc_18005FDEA
0x18005fdc9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005fdce  cmp     [rax+7CCh], ebx
0x18005fdd4  jz      short loc_18005FDEA
0x18005fdd6  mov     r9d, ebx; int
0x18005fdd9  mov     r8d, 1F1Bh; int
0x18005fddf  mov     rdx, r15; char *
0x18005fde2  mov     rcx, rax; this
0x18005fde5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005fdea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005fdf1  jb      loc_1800605A4
0x18005fdf7  mov     edx, 74h ; 't'
0x18005fdfc  jmp     loc_18005FD53
0x18005fe01  mov     cl, byte ptr [rbp+var_24]
0x18005fe04  lea     r8, [rbp+var_38]
0x18005fe08  lea     rdx, [rbp+var_3C]
0x18005fe0c  call    MF__DLNA__GetMP4VProfileAndLevel
0x18005fe11  mov     ebx, eax
0x18005fe13  test    eax, eax
0x18005fe15  jns     loc_18005FEA6
0x18005fe1b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fe22  test    rcx, rcx
0x18005fe25  jnz     short loc_18005FE68
0x18005fe27  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005fe2d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fe34  mov     rcx, rax
0x18005fe37  test    rax, rax
0x18005fe3a  jz      short loc_18005FE5A
0x18005fe3c  mov     rax, [rax]
0x18005fe3f  mov     edx, 7F0h
0x18005fe44  mov     rax, [rax+8]
0x18005fe48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe4d  test    eax, eax
0x18005fe4f  jz      short loc_18005FE5A
0x18005fe51  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fe58  jmp     short loc_18005FE68
0x18005fe5a  lea     rcx, qword_1800D6F70; this
0x18005fe61  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fe68  cmp     [rcx+8], r14b
0x18005fe6c  jz      short loc_18005FE8F
0x18005fe6e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005fe73  cmp     [rax+7CCh], ebx
0x18005fe79  jz      short loc_18005FE8F
0x18005fe7b  mov     r9d, ebx; int
0x18005fe7e  mov     r8d, 1F1Dh; int
0x18005fe84  mov     rdx, r15; char *
0x18005fe87  mov     rcx, rax; this
0x18005fe8a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005fe8f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005fe96  jb      loc_1800605A4
0x18005fe9c  mov     edx, 75h ; 'u'
0x18005fea1  jmp     loc_18005FD53
0x18005fea6  mov     eax, [rdi+4]
0x18005fea9  mov     ecx, [rbp+var_3C]
0x18005feac  cmp     eax, ecx
0x18005feae  jz      loc_18005FF75
0x18005feb4  cmp     cs:byte_1800D78D3, 10h
0x18005febb  jb      short loc_18005FEE3
0x18005febd  mov     [rsp+70h+var_50], ecx
0x18005fec1  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x18005fec8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fecf  mov     edx, 76h ; 'v'
0x18005fed4  mov     r9d, eax
0x18005fed7  mov     rcx, [rcx+88h]
0x18005fede  call    WPP_SF_dd
0x18005fee3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005feea  mov     edi, 0C00D65F4h
0x18005feef  mov     ebx, edi
0x18005fef1  test    rcx, rcx
0x18005fef4  jnz     short loc_18005FF37
0x18005fef6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005fefc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ff03  mov     rcx, rax
0x18005ff06  test    rax, rax
0x18005ff09  jz      short loc_18005FF29
0x18005ff0b  mov     rax, [rax]
0x18005ff0e  mov     edx, 7F0h
0x18005ff13  mov     rax, [rax+8]
0x18005ff17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ff1c  test    eax, eax
0x18005ff1e  jz      short loc_18005FF29
0x18005ff20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ff27  jmp     short loc_18005FF37
0x18005ff29  lea     rcx, qword_1800D6F70; this
0x18005ff30  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ff37  cmp     [rcx+8], r14b
0x18005ff3b  jz      short loc_18005FF5E
0x18005ff3d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005ff42  cmp     [rax+7CCh], edi
0x18005ff48  jz      short loc_18005FF5E
0x18005ff4a  mov     r9d, edi; int
0x18005ff4d  mov     r8d, 1F24h; int
0x18005ff53  mov     rdx, r15; char *
0x18005ff56  mov     rcx, rax; this
0x18005ff59  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005ff5e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005ff65  jb      loc_1800605A4
0x18005ff6b  mov     edx, 77h ; 'w'
0x18005ff70  jmp     loc_180060586
0x18005ff75  mov     ecx, [rdi+8]
0x18005ff78  mov     esi, [rbp+var_38]
0x18005ff7b  cmp     esi, ecx
0x18005ff7d  jz      loc_1800604BF
0x18005ff83  cmp     esi, [rdi+0Ch]
0x18005ff86  jz      loc_1800604BF
0x18005ff8c  cmp     eax, 1
0x18005ff8f  jnz     loc_180060174
0x18005ff95  lea     rdx, [rbp+arg_18]
0x18005ff99  call    MF__DLNA__GetMPEG4_P2_SP_Level_OrdinalValue
0x18005ff9e  mov     ebx, eax
0x18005ffa0  test    eax, eax
0x18005ffa2  jns     loc_180060033
0x18005ffa8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ffaf  test    rcx, rcx
0x18005ffb2  jnz     short loc_18005FFF5
0x18005ffb4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005ffba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ffc1  mov     rcx, rax
0x18005ffc4  test    rax, rax
0x18005ffc7  jz      short loc_18005FFE7
0x18005ffc9  mov     rax, [rax]
0x18005ffcc  mov     edx, 7F0h
0x18005ffd1  mov     rax, [rax+8]
0x18005ffd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ffda  test    eax, eax
0x18005ffdc  jz      short loc_18005FFE7
0x18005ffde  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ffe5  jmp     short loc_18005FFF5
0x18005ffe7  lea     rcx, qword_1800D6F70; this
0x18005ffee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fff5  cmp     [rcx+8], r14b
0x18005fff9  jz      short loc_18006001C
0x18005fffb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180060000  cmp     [rax+7CCh], ebx
0x180060006  jz      short loc_18006001C
0x180060008  mov     r9d, ebx; int
0x18006000b  mov     r8d, 1F2Ch; int
0x180060011  mov     rdx, r15; char *
0x180060014  mov     rcx, rax; this
0x180060017  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006001c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060023  jb      loc_1800605A4
0x180060029  mov     edx, 78h ; 'x'
0x18006002e  jmp     loc_18005FD53
0x180060033  mov     ecx, [rdi+0Ch]
0x180060036  lea     rdx, [rbp+var_40]
0x18006003a  call    MF__DLNA__GetMPEG4_P2_SP_Level_OrdinalValue
0x18006003f  mov     ebx, eax
0x180060041  test    eax, eax
0x180060043  jns     loc_1800600D4
0x180060049  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060050  test    rcx, rcx
0x180060053  jnz     short loc_180060096
0x180060055  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006005b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180060062  mov     rcx, rax
0x180060065  test    rax, rax
0x180060068  jz      short loc_180060088
0x18006006a  mov     rax, [rax]
0x18006006d  mov     edx, 7F0h
0x180060072  mov     rax, [rax+8]
0x180060076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006007b  test    eax, eax
0x18006007d  jz      short loc_180060088
0x18006007f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060086  jmp     short loc_180060096
0x180060088  lea     rcx, qword_1800D6F70; this
0x18006008f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180060096  cmp     [rcx+8], r14b
0x18006009a  jz      short loc_1800600BD
0x18006009c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800600a1  cmp     [rax+7CCh], ebx
0x1800600a7  jz      short loc_1800600BD
0x1800600a9  mov     r9d, ebx; int
0x1800600ac  mov     r8d, 1F2Dh; int
0x1800600b2  mov     rdx, r15; char *
0x1800600b5  mov     rcx, rax; this
0x1800600b8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800600bd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800600c4  jb      loc_1800605A4
0x1800600ca  mov     edx, 79h ; 'y'
0x1800600cf  jmp     loc_18005FD53
0x1800600d4  lea     rdx, [rbp+arg_0]
0x1800600d8  mov     ecx, esi
0x1800600da  call    MF__DLNA__GetMPEG4_P2_SP_Level_OrdinalValue
0x1800600df  mov     ebx, eax
0x1800600e1  test    eax, eax
0x1800600e3  jns     loc_18006035C
0x1800600e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800600f0  test    rcx, rcx
0x1800600f3  jnz     short loc_180060136
0x1800600f5  call    cs:__imp_MFGetCallStackTracingWeakReference
  ... truncated ...
```
