# MF::DLNA::CheckMP4VProfileLevel

- ea: `0x18006250c`
- end: `0x180062f22`
- name: `MF::DLNA::CheckMP4VProfileLevel`
- size: `2582`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800666f0`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x18006250c`
- `0x180064394`
- `0x1800645d0`
- `0x180064740`
- `0x180066af0`
- `0x180066b6c`
- `0x180066bc0`
- `0x1800744d8`
- `0x180081f04`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062ef6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062ef6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800625d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062688`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062733`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062808`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800628cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062973`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062a19`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062ac6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062b6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062c13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062cec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062d82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062e58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800625d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062688`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062733`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062808`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800628cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062973`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062a19`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062ac6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062b6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062c13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062cec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062d82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062e58`

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
                  v37 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                  v43 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                  v46 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                  v67 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                  v52 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                  v58 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                  v61 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            if ( (unsigned __int8)byte_1800DC8D3 >= 0x10u )
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
                v70 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            if ( (unsigned __int8)byte_1800DC8D3 >= 0x10u )
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
                v64 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          if ( (unsigned __int8)byte_1800DC8D3 >= 0x10u )
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
              v28 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v24 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v18 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v10 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x18006250c  mov     [rsp-28h+arg_8], rbx
0x180062511  push    rbp
0x180062512  push    rsi
0x180062513  push    rdi
0x180062514  push    r14
0x180062516  push    r15
0x180062518  mov     rbp, rsp
0x18006251b  sub     rsp, 70h
0x18006251f  mov     rdi, rdx
0x180062522  lea     r15, aMfDlnaCheckmp4; "MF::DLNA::CheckMP4VProfileLevel"
0x180062529  mov     rbx, rcx
0x18006252c  mov     rdx, r15; char *
0x18006252f  mov     r8d, 1F07h; int
0x180062535  lea     rcx, [rbp+arg_0]; this
0x180062539  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006253e  mov     rax, [rbx]
0x180062541  lea     r9, [rbp+arg_10]
0x180062545  xor     r14d, r14d
0x180062548  lea     r8, [rbp+pv]
0x18006254c  xorps   xmm0, xmm0
0x18006254f  mov     [rbp+var_28], r14d
0x180062553  lea     rdx, MF_MT_USER_DATA
0x18006255a  mov     [rbp+var_24], r14w
0x18006255f  mov     rax, [rax+80h]
0x180062566  mov     rcx, rbx
0x180062569  mov     [rbp+var_22], r14b
0x18006256d  movups  [rbp+var_20], xmm0
0x180062571  mov     [rbp+var_C], r14d
0x180062575  mov     [rbp+var_8], r14
0x180062579  mov     [rbp+pv], r14
0x18006257d  mov     [rbp+arg_10], r14d
0x180062581  mov     [rbp+var_3C], r14d
0x180062585  mov     [rbp+var_38], r14d
0x180062589  mov     [rbp+arg_0], r14d
0x18006258d  mov     [rbp+arg_18], r14d
0x180062591  mov     [rbp+var_40], r14d
0x180062595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006259a  test    eax, eax
0x18006259c  jns     loc_180062662
0x1800625a2  mov     rax, [rbx]
0x1800625a5  lea     r9, [rbp+arg_10]
0x1800625a9  lea     r8, [rbp+pv]
0x1800625ad  mov     rcx, rbx
0x1800625b0  lea     rdx, MF_MT_MPEG_SEQUENCE_HEADER
0x1800625b7  mov     rax, [rax+80h]
0x1800625be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800625c3  mov     ebx, eax
0x1800625c5  test    eax, eax
0x1800625c7  jns     loc_180062662
0x1800625cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800625d4  test    rcx, rcx
0x1800625d7  jnz     short loc_180062620
0x1800625d9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800625e0  nop     dword ptr [rax+rax+00h]
0x1800625e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800625ec  mov     rcx, rax
0x1800625ef  test    rax, rax
0x1800625f2  jz      short loc_180062612
0x1800625f4  mov     rax, [rax]
0x1800625f7  mov     edx, 7F0h
0x1800625fc  mov     rax, [rax+8]
0x180062600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062605  test    eax, eax
0x180062607  jz      short loc_180062612
0x180062609  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062610  jmp     short loc_180062620
0x180062612  lea     rcx, qword_1800DBF70; this
0x180062619  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180062620  cmp     [rcx+8], r14b
0x180062624  jz      short loc_180062647
0x180062626  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006262b  cmp     [rax+7CCh], ebx
0x180062631  jz      short loc_180062647
0x180062633  mov     r9d, ebx; int
0x180062636  mov     r8d, 1F18h; int
0x18006263c  mov     rdx, r15; char *
0x18006263f  mov     rcx, rax; this
0x180062642  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180062647  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006264e  jb      loc_180062EF2
0x180062654  mov     edx, 73h ; 's'
0x180062659  mov     [rsp+70h+var_50], ebx
0x18006265d  jmp     loc_180062ED8
0x180062662  mov     r8, [rbp+pv]; unsigned __int8 *
0x180062666  lea     rcx, [rbp+var_28]; this
0x18006266a  mov     edx, [rbp+arg_10]; unsigned int
0x18006266d  call    ?ParseData@CMP4VSequenceHeader@@QEAAJKPEBE@Z; CMP4VSequenceHeader::ParseData(ulong,uchar const *)
0x180062672  mov     ebx, eax
0x180062674  test    eax, eax
0x180062676  jns     loc_18006270D
0x18006267c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062683  test    rcx, rcx
0x180062686  jnz     short loc_1800626CF
0x180062688  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006268f  nop     dword ptr [rax+rax+00h]
0x180062694  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006269b  mov     rcx, rax
0x18006269e  test    rax, rax
0x1800626a1  jz      short loc_1800626C1
0x1800626a3  mov     rax, [rax]
0x1800626a6  mov     edx, 7F0h
0x1800626ab  mov     rax, [rax+8]
0x1800626af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800626b4  test    eax, eax
0x1800626b6  jz      short loc_1800626C1
0x1800626b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800626bf  jmp     short loc_1800626CF
0x1800626c1  lea     rcx, qword_1800DBF70; this
0x1800626c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800626cf  cmp     [rcx+8], r14b
0x1800626d3  jz      short loc_1800626F6
0x1800626d5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800626da  cmp     [rax+7CCh], ebx
0x1800626e0  jz      short loc_1800626F6
0x1800626e2  mov     r9d, ebx; int
0x1800626e5  mov     r8d, 1F1Bh; int
0x1800626eb  mov     rdx, r15; char *
0x1800626ee  mov     rcx, rax; this
0x1800626f1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800626f6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800626fd  jb      loc_180062EF2
0x180062703  mov     edx, 74h ; 't'
0x180062708  jmp     loc_180062659
0x18006270d  mov     cl, byte ptr [rbp+var_24]
0x180062710  lea     r8, [rbp+var_38]
0x180062714  lea     rdx, [rbp+var_3C]
0x180062718  call    MF__DLNA__GetMP4VProfileAndLevel
0x18006271d  mov     ebx, eax
0x18006271f  test    eax, eax
0x180062721  jns     loc_1800627B8
0x180062727  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006272e  test    rcx, rcx
0x180062731  jnz     short loc_18006277A
0x180062733  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006273a  nop     dword ptr [rax+rax+00h]
0x18006273f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180062746  mov     rcx, rax
0x180062749  test    rax, rax
0x18006274c  jz      short loc_18006276C
0x18006274e  mov     rax, [rax]
0x180062751  mov     edx, 7F0h
0x180062756  mov     rax, [rax+8]
0x18006275a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006275f  test    eax, eax
0x180062761  jz      short loc_18006276C
0x180062763  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006276a  jmp     short loc_18006277A
0x18006276c  lea     rcx, qword_1800DBF70; this
0x180062773  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006277a  cmp     [rcx+8], r14b
0x18006277e  jz      short loc_1800627A1
0x180062780  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180062785  cmp     [rax+7CCh], ebx
0x18006278b  jz      short loc_1800627A1
0x18006278d  mov     r9d, ebx; int
0x180062790  mov     r8d, 1F1Dh; int
0x180062796  mov     rdx, r15; char *
0x180062799  mov     rcx, rax; this
0x18006279c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800627a1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800627a8  jb      loc_180062EF2
0x1800627ae  mov     edx, 75h ; 'u'
0x1800627b3  jmp     loc_180062659
0x1800627b8  mov     eax, [rdi+4]
0x1800627bb  mov     ecx, [rbp+var_3C]
0x1800627be  cmp     eax, ecx
0x1800627c0  jz      loc_18006288D
0x1800627c6  cmp     cs:byte_1800DC8D3, 10h
0x1800627cd  jb      short loc_1800627F5
0x1800627cf  mov     [rsp+70h+var_50], ecx
0x1800627d3  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x1800627da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800627e1  mov     edx, 76h ; 'v'
0x1800627e6  mov     r9d, eax
0x1800627e9  mov     rcx, [rcx+88h]
0x1800627f0  call    WPP_SF_dd
0x1800627f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800627fc  mov     edi, 0C00D65F4h
0x180062801  mov     ebx, edi
0x180062803  test    rcx, rcx
0x180062806  jnz     short loc_18006284F
0x180062808  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006280f  nop     dword ptr [rax+rax+00h]
0x180062814  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006281b  mov     rcx, rax
0x18006281e  test    rax, rax
0x180062821  jz      short loc_180062841
0x180062823  mov     rax, [rax]
0x180062826  mov     edx, 7F0h
0x18006282b  mov     rax, [rax+8]
0x18006282f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062834  test    eax, eax
0x180062836  jz      short loc_180062841
0x180062838  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006283f  jmp     short loc_18006284F
0x180062841  lea     rcx, qword_1800DBF70; this
0x180062848  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006284f  cmp     [rcx+8], r14b
0x180062853  jz      short loc_180062876
0x180062855  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006285a  cmp     [rax+7CCh], edi
0x180062860  jz      short loc_180062876
0x180062862  mov     r9d, edi; int
0x180062865  mov     r8d, 1F24h; int
0x18006286b  mov     rdx, r15; char *
0x18006286e  mov     rcx, rax; this
0x180062871  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180062876  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006287d  jb      loc_180062EF2
0x180062883  mov     edx, 77h ; 'w'
0x180062888  jmp     loc_180062ED4
0x18006288d  mov     ecx, [rdi+8]
0x180062890  mov     esi, [rbp+var_38]
0x180062893  cmp     esi, ecx
0x180062895  jz      loc_180062E07
0x18006289b  cmp     esi, [rdi+0Ch]
0x18006289e  jz      loc_180062E07
0x1800628a4  cmp     eax, 1
0x1800628a7  jnz     loc_180062A9E
0x1800628ad  lea     rdx, [rbp+arg_18]
0x1800628b1  call    MF__DLNA__GetMPEG4_P2_SP_Level_OrdinalValue
0x1800628b6  mov     ebx, eax
0x1800628b8  test    eax, eax
0x1800628ba  jns     loc_180062951
0x1800628c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800628c7  test    rcx, rcx
0x1800628ca  jnz     short loc_180062913
0x1800628cc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800628d3  nop     dword ptr [rax+rax+00h]
0x1800628d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800628df  mov     rcx, rax
0x1800628e2  test    rax, rax
0x1800628e5  jz      short loc_180062905
0x1800628e7  mov     rax, [rax]
0x1800628ea  mov     edx, 7F0h
0x1800628ef  mov     rax, [rax+8]
0x1800628f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800628f8  test    eax, eax
0x1800628fa  jz      short loc_180062905
0x1800628fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062903  jmp     short loc_180062913
0x180062905  lea     rcx, qword_1800DBF70; this
0x18006290c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180062913  cmp     [rcx+8], r14b
0x180062917  jz      short loc_18006293A
0x180062919  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006291e  cmp     [rax+7CCh], ebx
0x180062924  jz      short loc_18006293A
0x180062926  mov     r9d, ebx; int
0x180062929  mov     r8d, 1F2Ch; int
0x18006292f  mov     rdx, r15; char *
0x180062932  mov     rcx, rax; this
0x180062935  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006293a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062941  jb      loc_180062EF2
0x180062947  mov     edx, 78h ; 'x'
0x18006294c  jmp     loc_180062659
0x180062951  mov     ecx, [rdi+0Ch]
0x180062954  lea     rdx, [rbp+var_40]
0x180062958  call    MF__DLNA__GetMPEG4_P2_SP_Level_OrdinalValue
0x18006295d  mov     ebx, eax
0x18006295f  test    eax, eax
0x180062961  jns     loc_1800629F8
0x180062967  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006296e  test    rcx, rcx
0x180062971  jnz     short loc_1800629BA
0x180062973  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006297a  nop     dword ptr [rax+rax+00h]
0x18006297f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180062986  mov     rcx, rax
0x180062989  test    rax, rax
0x18006298c  jz      short loc_1800629AC
0x18006298e  mov     rax, [rax]
0x180062991  mov     edx, 7F0h
0x180062996  mov     rax, [rax+8]
0x18006299a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006299f  test    eax, eax
0x1800629a1  jz      short loc_1800629AC
0x1800629a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800629aa  jmp     short loc_1800629BA
0x1800629ac  lea     rcx, qword_1800DBF70; this
0x1800629b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800629ba  cmp     [rcx+8], r14b
0x1800629be  jz      short loc_1800629E1
0x1800629c0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800629c5  cmp     [rax+7CCh], ebx
0x1800629cb  jz      short loc_1800629E1
0x1800629cd  mov     r9d, ebx; int
0x1800629d0  mov     r8d, 1F2Dh; int
0x1800629d6  mov     rdx, r15; char *
0x1800629d9  mov     rcx, rax; this
0x1800629dc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800629e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800629e8  jb      loc_180062EF2
0x1800629ee  mov     edx, 79h ; 'y'
0x1800629f3  jmp     loc_180062659
0x1800629f8  lea     rdx, [rbp+arg_0]
0x1800629fc  mov     ecx, esi
0x1800629fe  call    MF__DLNA__GetMPEG4_P2_SP_Level_OrdinalValue
0x180062a03  mov     ebx, eax
  ... truncated ...
```
