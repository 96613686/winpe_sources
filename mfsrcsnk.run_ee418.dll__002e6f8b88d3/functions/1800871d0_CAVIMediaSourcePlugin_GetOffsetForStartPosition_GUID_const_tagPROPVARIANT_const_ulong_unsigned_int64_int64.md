# CAVIMediaSourcePlugin::GetOffsetForStartPosition(_GUID const *,tagPROPVARIANT const *,ulong,unsigned __int64 *,__int64 *)

- ea: `0x1800871d0`
- end: `0x180087d2e`
- name: `?GetOffsetForStartPosition@CAVIMediaSourcePlugin@@UEAAJPEBU_GUID@@PEBUtagPROPVARIANT@@KPEA_KPEA_J@Z`
- size: `2910`
- prototype: `int(CAVIMediaSourcePlugin *__hidden this, const struct _GUID *, const struct tagPROPVARIANT *, unsigned int, unsigned __int64 *, __int64 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005eb8`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x18003fe50`
- `0x18005af5c`
- `0x180073b14`
- `0x180074814`
- `0x180080794`
- `0x1800871d0`
- `0x18011b1e4`
- `0x18013f5b8`
- `0x180140abc`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087255`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800872f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087393`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087432`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800874ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008766c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087732`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087834`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087916`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087a61`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087b83`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087c5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087255`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800872f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087393`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087432`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800874ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008766c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087732`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087834`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087916`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087a61`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087b83`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087c5f`

## string_xrefs

- `0x1800871f7`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`
- `0x180087489`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`
- `0x180087544`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`
- `0x18008796d`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`
- `0x1800879e0`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`
- `0x180087a29`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`
- `0x180087ab8`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`
- `0x180087b08`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`
- `0x180087bda`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`
- `0x180087cb6`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`

## pseudocode

```c
__int64 __fastcall CAVIMediaSourcePlugin::GetOffsetForStartPosition(
        CAVIMediaSourcePlugin *this,
        const struct _GUID *a2,
        const struct tagPROPVARIANT *a3,
        char a4,
        unsigned __int64 *a5,
        __int64 *a6)
{
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rax
  CAVIMediaSourcePlugin *v14; // rsi
  wchar_t *v15; // rcx
  int CurrentIndexEntry; // ebx
  CallStackTracing *v17; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rax
  CAVIMediaSourcePlugin *v37; // r8
  __int64 v38; // rax
  unsigned int v39; // ecx
  unsigned int v40; // r14d
  __int64 v41; // rax
  CAVIIAVSStreamParser *v42; // r12
  unsigned int NumberOfStreams; // eax
  unsigned int i; // r14d
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  wchar_t *v51; // rcx
  CallStackTracing *v52; // rax
  __int64 v53; // rax
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // r9
  wchar_t *v57; // rcx
  CallStackTracing *v58; // rax
  CAVIMediaSourcePlugin *v59; // rbx
  LARGE_INTEGER hVal; // rdx
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // r9
  wchar_t *v66; // rcx
  CallStackTracing *v67; // rax
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // r9
  wchar_t *v71; // rcx
  CallStackTracing *v72; // rax
  struct CallStackContext *v73; // rax
  __int64 v74; // rdx
  struct CallStackContext *v75; // rax
  struct CallStackContext *v76; // rax
  wchar_t *v77; // rcx
  CallStackTracing *v78; // rax
  struct CallStackContext *v79; // rax
  struct CallStackContext *v80; // rax
  wchar_t *v81; // rcx
  CallStackTracing *v82; // rax
  struct CallStackContext *v83; // rax
  wchar_t *v84; // rcx
  CallStackTracing *v85; // rax
  struct CallStackContext *v86; // rax
  unsigned int v88; // [rsp+40h] [rbp-40h]
  _BYTE v89[4]; // [rsp+44h] [rbp-3Ch] BYREF
  int v90; // [rsp+48h] [rbp-38h] BYREF
  __int64 v91; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v92; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v93; // [rsp+60h] [rbp-20h] BYREF
  __int64 v94; // [rsp+68h] [rbp-18h] BYREF
  unsigned int v95; // [rsp+70h] [rbp-10h]
  int v96; // [rsp+74h] [rbp-Ch]

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v89,
    "CAVIMediaSourcePlugin::GetOffsetForStartPosition",
    1133);
  v13 = *((_QWORD *)this + 7);
  v14 = (CAVIMediaSourcePlugin *)((char *)this - 24);
  v93 = 0;
  v94 = 0;
  v90 = 0;
  v96 = *(_DWORD *)(v13 + 160);
  if ( !a2 )
  {
    v15 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentIndexEntry = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v15 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CAVIMediaSourcePlugin::GetOffsetForStartPosition",
          1142,
          -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_178;
    v19 = 118;
    goto LABEL_12;
  }
  if ( !a3 )
  {
    v20 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentIndexEntry = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
      CallStackTracing::s_wpInstance = v21;
      if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
      {
        v20 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)v22 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v22, "CAVIMediaSourcePlugin::GetOffsetForStartPosition", 1143, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_178;
    v19 = 119;
    goto LABEL_12;
  }
  if ( !a5 )
  {
    v23 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentIndexEntry = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
      CallStackTracing::s_wpInstance = v24;
      if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
      {
        v23 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v23 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v23 + 8) )
    {
      v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
      if ( *((_DWORD *)v25 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v25, "CAVIMediaSourcePlugin::GetOffsetForStartPosition", 1144, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_178;
    v19 = 120;
    goto LABEL_12;
  }
  if ( !a6 )
  {
    v26 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentIndexEntry = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
      CallStackTracing::s_wpInstance = v27;
      if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
      {
        v26 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v26 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v26 + 8) )
    {
      v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
      if ( *((_DWORD *)v28 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v28, "CAVIMediaSourcePlugin::GetOffsetForStartPosition", 1145, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_178;
    v19 = 121;
LABEL_12:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
      v14,
      -2147467261);
    goto LABEL_178;
  }
  if ( *((_QWORD *)v14 + 9) && a3->vt )
  {
    CurrentIndexEntry = CAVIMediaSourcePlugin::CheckForValidStartPosition(v14, a2, a3);
    if ( CurrentIndexEntry < 0 )
    {
      v32 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
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
        if ( *((_DWORD *)v34 + 499) != CurrentIndexEntry )
          CallStackContext::TraceFailure(
            v34,
            "CAVIMediaSourcePlugin::GetOffsetForStartPosition",
            1151,
            CurrentIndexEntry);
      }
      if ( g_wppLevels )
      {
        v35 = 123;
        goto LABEL_177;
      }
      goto LABEL_178;
    }
    v36 = (*((_DWORD *)v14 + 150) & 1) - 1LL;
    *a5 = v36;
    *a6 = v36;
    v37 = this;
    v38 = *((_QWORD *)this + 7);
    v39 = *(_DWORD *)(v38 + 112);
    *(_DWORD *)(v38 + 160) = (a4 & 1) == 0;
    v40 = 0;
    v95 = v39;
    while ( 1 )
    {
      v88 = v40;
      if ( v40 >= v39 )
      {
        if ( *a5 == -1 )
        {
          if ( (unsigned __int8)byte_1801B1109 >= 4u )
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qI)(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              130,
              &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
              v14,
              (LARGE_INTEGER)a3->hVal.QuadPart);
          v81 = (wchar_t *)CallStackTracing::s_wpInstance;
          CurrentIndexEntry = -1072875803;
          if ( !CallStackTracing::s_wpInstance )
          {
            v82 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v37, v31);
            CallStackTracing::s_wpInstance = v82;
            if ( v82 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v82 + 8LL))(v82, 2032) )
            {
              v81 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v81 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v81 + 8) )
          {
            v83 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v81);
            if ( *((_DWORD *)v83 + 499) != -1072875803 )
              CallStackContext::TraceFailure(v83, "CAVIMediaSourcePlugin::GetOffsetForStartPosition", 1298, -1072875803);
          }
          if ( g_wppLevels )
          {
            v35 = 131;
            goto LABEL_177;
          }
        }
        else if ( (unsigned __int8)byte_1801B1109 >= 8u )
        {
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qIII)(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            132,
            &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
            v14,
            (LARGE_INTEGER)a3->hVal.QuadPart,
            *a5,
            *a6);
        }
        goto LABEL_178;
      }
      v41 = *((_QWORD *)v37 + 7);
      v91 = 0;
      v42 = *(CAVIIAVSStreamParser **)(*(_QWORD *)(v41 + 104) + 8LL * v40);
      if ( (*(unsigned int (__fastcall **)(CAVIIAVSStreamParser *))(*(_QWORD *)v42 + 8LL))(v42) )
      {
        NumberOfStreams = CAVIIAVSStreamParser::GetNumberOfStreams(v42);
        v92 = NumberOfStreams;
        for ( i = 0; ; ++i )
        {
          if ( i >= NumberOfStreams )
          {
            v40 = v88;
            goto LABEL_73;
          }
          CurrentIndexEntry = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, __int64 *))(**((_QWORD **)this + 6)
                                                                                          + 272LL))(
                                *((_QWORD *)this + 6),
                                i,
                                &v90,
                                &v91);
          if ( CurrentIndexEntry < 0 )
            break;
          if ( v90 )
            goto LABEL_74;
          ComSmartPtr<IUnknown>::Release(&v91);
          NumberOfStreams = v92;
        }
        v71 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v46, v47);
          CallStackTracing::s_wpInstance = v72;
          if ( v72 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v72 + 8LL))(v72, 2032) )
          {
            v71 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v71 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v71 + 8) )
        {
          v73 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v71);
          if ( *((_DWORD *)v73 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(
              v73,
              "CAVIMediaSourcePlugin::GetOffsetForStartPosition",
              1186,
              CurrentIndexEntry);
        }
        if ( g_wppLevels )
        {
          v74 = 124;
          goto LABEL_122;
        }
        goto LABEL_123;
      }
      CurrentIndexEntry = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, __int64 *))(**((_QWORD **)this + 6) + 272LL))(
                            *((_QWORD *)this + 6),
                            v40,
                            &v90,
                            &v91);
      if ( CurrentIndexEntry < 0 )
      {
        v51 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48, v49, v50);
          CallStackTracing::s_wpInstance = v52;
          if ( v52 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
          {
            v51 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v51 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v51 + 8) )
        {
          v80 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
          if ( *((_DWORD *)v80 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(
              v80,
              "CAVIMediaSourcePlugin::GetOffsetForStartPosition",
              1196,
              CurrentIndexEntry);
        }
        if ( g_wppLevels )
        {
          v74 = 125;
LABEL_122:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v74,
            &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
            v14,
            CurrentIndexEntry);
        }
        goto LABEL_123;
      }
LABEL_73:
      if ( !v90 )
        goto LABEL_111;
LABEL_74:
      if ( *((_DWORD *)v42 + 20) )
      {
        v40 = v88;
        goto LABEL_111;
      }
      v53 = MF_TIME_FORMAT_BYTESTREAM_OFFSET - *(_QWORD *)&a2->Data1;
      if ( MF_TIME_FORMAT_BYTESTREAM_OFFSET == *(_QWORD *)&a2->Data1 )
        v53 = 0xCA572657DBDF638CuLL - *(_QWORD *)a2->Data4;
      if ( !v53 )
      {
        CurrentIndexEntry = (*(__int64 (__fastcall **)(CAVIIAVSStreamParser *, LARGE_INTEGER, unsigned __int64 *, __int64 *))(*(_QWORD *)v42 + 32LL))(
                              v42,
                              a3->hVal,
                              &v93,
                              &v94);
        if ( CurrentIndexEntry == 1 )
        {
          CurrentIndexEntry = 0;
LABEL_80:
          v40 = v88;
          goto LABEL_111;
        }
        if ( CurrentIndexEntry < 0 )
        {
          v57 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54, v55, v56);
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
            v75 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
            if ( *((_DWORD *)v75 + 499) != CurrentIndexEntry )
              CallStackContext::TraceFailure(
                v75,
                "CAVIMediaSourcePlugin::GetOffsetForStartPosition",
                1225,
                CurrentIndexEntry);
          }
          if ( g_wppLevels )
          {
            v74 = 126;
            goto LABEL_122;
          }
          goto LABEL_123;
        }
        goto LABEL_100;
      }
      if ( *((_DWORD *)v14 + 170) )
        goto LABEL_91;
      if ( !a3->hVal.QuadPart )
        break;
      v59 = this;
      *((_DWORD *)this + 164) = 1;
      if ( (unsigned __int8)byte_1801B1109 >= 0x20u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 127, &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids, v14);
LABEL_92:
      hVal = a3->hVal;
      v61 = *((_QWORD *)v59 + 71);
      if ( v61 != hVal.QuadPart || v61 == -1 )
      {
        CurrentIndexEntry = (*(__int64 (__fastcall **)(CAVIIAVSStreamParser *, LARGE_INTEGER, unsigned __int64 *, __int64 *))(*(_QWORD *)v42 + 24LL))(
                              v42,
                              hVal,
                              &v93,
                              &v94);
        if ( CurrentIndexEntry < 0 )
        {
          v77 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v68, v69, v70);
            CallStackTracing::s_wpInstance = v78;
            if ( v78 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v78 + 8LL))(v78, 2032) )
            {
              v77 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v77 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v77 + 8) )
          {
            v79 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v77);
            if ( *((_DWORD *)v79 + 499) != CurrentIndexEntry )
              CallStackContext::TraceFailure(
                v79,
                "CAVIMediaSourcePlugin::GetOffsetForStartPosition",
                1259,
                CurrentIndexEntry);
          }
          if ( g_wppLevels )
          {
            v74 = 129;
            goto LABEL_122;
          }
LABEL_123:
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v91);
          goto LABEL_178;
        }
      }
      else
      {
        v62 = *(_QWORD *)v42;
        v92 = 0;
        v94 = (*(__int64 (__fastcall **)(CAVIIAVSStreamParser *))(v62 + 96))(v42);
        CurrentIndexEntry = CAVIStreamParser::GetCurrentIndexEntry(v42, &v93, &v92);
        if ( CurrentIndexEntry < 0 )
        {
          v66 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v63, v64, v65);
            CallStackTracing::s_wpInstance = v67;
            if ( v67 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
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
            v76 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
            if ( *((_DWORD *)v76 + 499) != CurrentIndexEntry )
              CallStackContext::TraceFailure(
                v76,
                "CAVIMediaSourcePlugin::GetOffsetForStartPosition",
                1253,
                CurrentIndexEntry);
          }
          if ( g_wppLevels )
          {
            v74 = 128;
            goto LABEL_122;
          }
          goto LABEL_123;
        }
      }
LABEL_100:
      if ( (*((_DWORD *)this + 144) & 1) == 0 )
      {
        if ( v93 < *a5 )
          *a5 = v93;
        if ( *a6 == -1 || v94 < *a6 )
          *a6 = v94;
        goto LABEL_80;
      }
      if ( v93 > *a5 )
        *a5 = v93;
      v40 = v88;
      if ( v94 > *a6 )
        *a6 = v94;
LABEL_111:
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v91);
      v39 = v95;
      ++v40;
      v37 = this;
    }
    *((_DWORD *)this + 164) = 2;
    CAVIMediaSourcePlugin::FlushFirstFrameInfo(v14);
LABEL_91:
    v59 = this;
    goto LABEL_92;
  }
  v84 = (wchar_t *)CallStackTracing::s_wpInstance;
  CurrentIndexEntry = -1072875854;
  if ( !CallStackTracing::s_wpInstance )
  {
    v85 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
    CallStackTracing::s_wpInstance = v85;
    if ( v85 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v85 + 8LL))(v85, 2032) )
    {
      v84 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v84 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v84 + 8) )
  {
    v86 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v84);
    if ( *((_DWORD *)v86 + 499) != -1072875854 )
      CallStackContext::TraceFailure(v86, "CAVIMediaSourcePlugin::GetOffsetForStartPosition", 1149, -1072875854);
  }
  if ( g_wppLevels )
  {
    v35 = 122;
LABEL_177:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v35,
      &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
      v14,
      CurrentIndexEntry);
  }
LABEL_178:
  *(_DWORD *)(*((_QWORD *)this + 7) + 160LL) = v96;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v89);
  return (unsigned int)CurrentIndexEntry;
}

```

## disassembly

```asm
0x1800871d0  mov     [rsp-38h+arg_10], rbx
0x1800871d5  mov     [rsp-38h+arg_8], rdx
0x1800871da  mov     [rsp-38h+arg_0], rcx
0x1800871df  push    rbp
0x1800871e0  push    rsi
0x1800871e1  push    rdi
0x1800871e2  push    r12
0x1800871e4  push    r13
0x1800871e6  push    r14
0x1800871e8  push    r15
0x1800871ea  mov     rbp, rsp
0x1800871ed  sub     rsp, 80h
0x1800871f4  mov     rdi, r8
0x1800871f7  lea     r13, aCavimediasourc_2; "CAVIMediaSourcePlugin::GetOffsetForStar"...
0x1800871fe  mov     rbx, rdx
0x180087201  mov     rsi, rcx
0x180087204  mov     rdx, r13; char *
0x180087207  lea     rcx, [rbp+var_3C]; this
0x18008720b  mov     r8d, 46Dh; int
0x180087211  mov     r14d, r9d
0x180087214  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180087219  mov     rax, [rsi+38h]
0x18008721d  xor     r12d, r12d
0x180087220  add     rsi, 0FFFFFFFFFFFFFFE8h
0x180087224  mov     [rbp+var_20], r12
0x180087228  mov     [rbp+var_18], r12
0x18008722c  mov     [rbp+var_38], r12d
0x180087230  mov     eax, [rax+0A0h]
0x180087236  mov     [rbp+var_C], eax
0x180087239  test    rbx, rbx
0x18008723c  jnz     loc_1800872D8
0x180087242  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180087249  mov     edi, 80004003h
0x18008724e  mov     ebx, edi
0x180087250  test    rcx, rcx
0x180087253  jnz     short loc_180087296
0x180087255  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008725b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180087262  mov     rcx, rax
0x180087265  test    rax, rax
0x180087268  jz      short loc_180087288
0x18008726a  mov     rax, [rax]
0x18008726d  mov     edx, 7F0h
0x180087272  mov     rax, [rax+8]
0x180087276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008727b  test    eax, eax
0x18008727d  jz      short loc_180087288
0x18008727f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180087286  jmp     short loc_180087296
0x180087288  lea     rcx, qword_1801B07E0; this
0x18008728f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180087296  cmp     [rcx+8], r12b
0x18008729a  jz      short loc_1800872BD
0x18008729c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800872a1  cmp     [rax+7CCh], edi
0x1800872a7  jz      short loc_1800872BD
0x1800872a9  mov     r9d, edi; int
0x1800872ac  mov     r8d, 476h; int
0x1800872b2  mov     rdx, r13; char *
0x1800872b5  mov     rcx, rax; this
0x1800872b8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800872bd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800872c4  jb      loc_180087CF7
0x1800872ca  mov     edx, 76h ; 'v'
0x1800872cf  mov     dword ptr [rsp+80h+var_60], edi
0x1800872d3  jmp     loc_180087CDD
0x1800872d8  test    rdi, rdi
0x1800872db  jnz     loc_180087373
0x1800872e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800872e8  mov     edi, 80004003h
0x1800872ed  mov     ebx, edi
0x1800872ef  test    rcx, rcx
0x1800872f2  jnz     short loc_180087335
0x1800872f4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800872fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180087301  mov     rcx, rax
0x180087304  test    rax, rax
0x180087307  jz      short loc_180087327
0x180087309  mov     rax, [rax]
0x18008730c  mov     edx, 7F0h
0x180087311  mov     rax, [rax+8]
0x180087315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008731a  test    eax, eax
0x18008731c  jz      short loc_180087327
0x18008731e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180087325  jmp     short loc_180087335
0x180087327  lea     rcx, qword_1801B07E0; this
0x18008732e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180087335  cmp     [rcx+8], r12b
0x180087339  jz      short loc_18008735C
0x18008733b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180087340  cmp     [rax+7CCh], edi
0x180087346  jz      short loc_18008735C
0x180087348  mov     r9d, edi; int
0x18008734b  mov     r8d, 477h; int
0x180087351  mov     rdx, r13; char *
0x180087354  mov     rcx, rax; this
0x180087357  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008735c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180087363  jb      loc_180087CF7
0x180087369  mov     edx, 77h ; 'w'
0x18008736e  jmp     loc_1800872CF
0x180087373  mov     r15, [rbp+arg_20]
0x180087377  test    r15, r15
0x18008737a  jnz     loc_180087412
0x180087380  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180087387  mov     edi, 80004003h
0x18008738c  mov     ebx, edi
0x18008738e  test    rcx, rcx
0x180087391  jnz     short loc_1800873D4
0x180087393  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180087399  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800873a0  mov     rcx, rax
0x1800873a3  test    rax, rax
0x1800873a6  jz      short loc_1800873C6
0x1800873a8  mov     rax, [rax]
0x1800873ab  mov     edx, 7F0h
0x1800873b0  mov     rax, [rax+8]
0x1800873b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800873b9  test    eax, eax
0x1800873bb  jz      short loc_1800873C6
0x1800873bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800873c4  jmp     short loc_1800873D4
0x1800873c6  lea     rcx, qword_1801B07E0; this
0x1800873cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800873d4  cmp     [rcx+8], r12b
0x1800873d8  jz      short loc_1800873FB
0x1800873da  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800873df  cmp     [rax+7CCh], edi
0x1800873e5  jz      short loc_1800873FB
0x1800873e7  mov     r9d, edi; int
0x1800873ea  mov     r8d, 478h; int
0x1800873f0  mov     rdx, r13; char *
0x1800873f3  mov     rcx, rax; this
0x1800873f6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800873fb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180087402  jb      loc_180087CF7
0x180087408  mov     edx, 78h ; 'x'
0x18008740d  jmp     loc_1800872CF
0x180087412  mov     r13, [rbp+arg_28]
0x180087416  test    r13, r13
0x180087419  jnz     loc_1800874B5
0x18008741f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180087426  mov     edi, 80004003h
0x18008742b  mov     ebx, edi
0x18008742d  test    rcx, rcx
0x180087430  jnz     short loc_180087473
0x180087432  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180087438  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008743f  mov     rcx, rax
0x180087442  test    rax, rax
0x180087445  jz      short loc_180087465
0x180087447  mov     rax, [rax]
0x18008744a  mov     edx, 7F0h
0x18008744f  mov     rax, [rax+8]
0x180087453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087458  test    eax, eax
0x18008745a  jz      short loc_180087465
0x18008745c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180087463  jmp     short loc_180087473
0x180087465  lea     rcx, qword_1801B07E0; this
0x18008746c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180087473  cmp     [rcx+8], r12b
0x180087477  jz      short loc_18008749E
0x180087479  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008747e  cmp     [rax+7CCh], edi
0x180087484  jz      short loc_18008749E
0x180087486  mov     r9d, edi; int
0x180087489  lea     rdx, aCavimediasourc_2; "CAVIMediaSourcePlugin::GetOffsetForStar"...
0x180087490  mov     r8d, 479h; int
0x180087496  mov     rcx, rax; this
0x180087499  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008749e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800874a5  jb      loc_180087CF7
0x1800874ab  mov     edx, 79h ; 'y'
0x1800874b0  jmp     loc_1800872CF
0x1800874b5  cmp     [rsi+48h], r12
0x1800874b9  jz      loc_180087C4E
0x1800874bf  cmp     [rdi], r12w
0x1800874c3  jz      loc_180087C4E
0x1800874c9  mov     r8, rdi; struct tagPROPVARIANT *
0x1800874cc  mov     rdx, rbx; struct _GUID *
0x1800874cf  mov     rcx, rsi; this
0x1800874d2  call    ?CheckForValidStartPosition@CAVIMediaSourcePlugin@@AEAAJPEBU_GUID@@PEBUtagPROPVARIANT@@@Z; CAVIMediaSourcePlugin::CheckForValidStartPosition(_GUID const *,tagPROPVARIANT const *)
0x1800874d7  mov     ebx, eax
0x1800874d9  test    eax, eax
0x1800874db  jns     loc_180087570
0x1800874e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800874e8  test    rcx, rcx
0x1800874eb  jnz     short loc_18008752E
0x1800874ed  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800874f3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800874fa  mov     rcx, rax
0x1800874fd  test    rax, rax
0x180087500  jz      short loc_180087520
0x180087502  mov     rax, [rax]
0x180087505  mov     edx, 7F0h
0x18008750a  mov     rax, [rax+8]
0x18008750e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087513  test    eax, eax
0x180087515  jz      short loc_180087520
0x180087517  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008751e  jmp     short loc_18008752E
0x180087520  lea     rcx, qword_1801B07E0; this
0x180087527  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008752e  cmp     [rcx+8], r12b
0x180087532  jz      short loc_180087559
0x180087534  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180087539  cmp     [rax+7CCh], ebx
0x18008753f  jz      short loc_180087559
0x180087541  mov     r9d, ebx; int
0x180087544  lea     rdx, aCavimediasourc_2; "CAVIMediaSourcePlugin::GetOffsetForStar"...
0x18008754b  mov     r8d, 47Fh; int
0x180087551  mov     rcx, rax; this
0x180087554  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180087559  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180087560  jb      loc_180087CF7
0x180087566  mov     edx, 7Bh ; '{'
0x18008756b  jmp     loc_180087CD9
0x180087570  mov     eax, [rsi+258h]
0x180087576  not     r14d
0x180087579  and     eax, 1
0x18008757c  dec     rax
0x18008757f  mov     [r15], rax
0x180087582  and     r14d, 1
0x180087586  mov     [r13+0], rax
0x18008758a  mov     r8, [rbp+arg_0]
0x18008758e  mov     rax, [r8+38h]
0x180087592  mov     ecx, [rax+70h]
0x180087595  mov     [rax+0A0h], r14d
0x18008759c  mov     r14d, r12d
0x18008759f  mov     [rbp+var_10], ecx
0x1800875a2  mov     [rbp+var_40], r14d
0x1800875a6  cmp     r14d, ecx
0x1800875a9  jnb     loc_180087B34
0x1800875af  mov     rax, [r8+38h]
0x1800875b3  mov     [rbp+var_30], r12
0x1800875b7  mov     edx, r14d
0x1800875ba  mov     rcx, [rax+68h]
0x1800875be  mov     r12, [rcx+rdx*8]
0x1800875c2  mov     rcx, r12
0x1800875c5  mov     rax, [r12]
0x1800875c9  mov     rax, [rax+8]
0x1800875cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800875d2  test    eax, eax
0x1800875d4  jz      short loc_180087634
0x1800875d6  mov     rcx, r12; this
0x1800875d9  call    ?GetNumberOfStreams@CAVIIAVSStreamParser@@QEAAKXZ; CAVIIAVSStreamParser::GetNumberOfStreams(void)
0x1800875de  mov     [rbp+var_28], eax
0x1800875e1  xor     r14d, r14d
0x1800875e4  cmp     r14d, eax
0x1800875e7  jnb     loc_1800876AA
0x1800875ed  mov     rax, [rbp+arg_0]
0x1800875f1  lea     r9, [rbp+var_30]
0x1800875f5  lea     r8, [rbp+var_38]
0x1800875f9  mov     edx, r14d
0x1800875fc  mov     rcx, [rax+30h]
0x180087600  mov     rax, [rcx]
0x180087603  mov     rax, [rax+110h]
0x18008760a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008760f  mov     ebx, eax
0x180087611  test    eax, eax
0x180087613  js      loc_18008790A
0x180087619  cmp     [rbp+var_38], 0
0x18008761d  jnz     loc_1800876B8
0x180087623  lea     rcx, [rbp+var_30]
0x180087627  call    ?Release@?$ComSmartPtr@UIUnknown@@@@QEAAXXZ; ComSmartPtr<IUnknown>::Release(void)
0x18008762c  mov     eax, [rbp+var_28]
0x18008762f  inc     r14d
0x180087632  jmp     short loc_1800875E4
0x180087634  mov     rax, [rbp+arg_0]
0x180087638  lea     r9, [rbp+var_30]
0x18008763c  lea     r8, [rbp+var_38]
0x180087640  mov     edx, r14d
0x180087643  mov     rcx, [rax+30h]
0x180087647  mov     rax, [rcx]
0x18008764a  mov     rax, [rax+110h]
0x180087651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087656  mov     ebx, eax
0x180087658  test    eax, eax
0x18008765a  jns     short loc_1800876AE
0x18008765c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180087663  test    rcx, rcx
0x180087666  jnz     loc_180087AF2
0x18008766c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180087672  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180087679  mov     rcx, rax
0x18008767c  test    rax, rax
0x18008767f  jz      loc_180087AE4
0x180087685  mov     rax, [rax]
0x180087688  mov     edx, 7F0h
0x18008768d  mov     rax, [rax+8]
0x180087691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087696  test    eax, eax
0x180087698  jz      loc_180087AE4
0x18008769e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800876a5  jmp     loc_180087AF2
0x1800876aa  mov     r14d, [rbp+var_40]
0x1800876ae  cmp     [rbp+var_38], 0
0x1800876b2  jz      loc_1800878EF
  ... truncated ...
```
