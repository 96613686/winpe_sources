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
  __int64 v11; // rax
  CAVIMediaSourcePlugin *v12; // rsi
  wchar_t *v13; // rcx
  int CurrentIndexEntry; // ebx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rax
  CAVIMediaSourcePlugin *v33; // r8
  __int64 v34; // rax
  unsigned int v35; // ecx
  unsigned int v36; // r14d
  __int64 v37; // rax
  CAVIIAVSStreamParser *v38; // r12
  unsigned int NumberOfStreams; // eax
  unsigned int i; // r14d
  __int64 v41; // rdx
  __int64 v42; // rdx
  wchar_t *v43; // rcx
  CallStackTracing *v44; // rax
  __int64 v45; // rax
  __int64 v46; // rdx
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  CAVIMediaSourcePlugin *v49; // rbx
  LARGE_INTEGER hVal; // rdx
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rdx
  wchar_t *v54; // rcx
  CallStackTracing *v55; // rax
  __int64 v56; // rdx
  wchar_t *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  __int64 v60; // rdx
  struct CallStackContext *v61; // rax
  struct CallStackContext *v62; // rax
  wchar_t *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  struct CallStackContext *v66; // rax
  wchar_t *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  wchar_t *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  unsigned int v74; // [rsp+40h] [rbp-40h]
  _BYTE v75[4]; // [rsp+44h] [rbp-3Ch] BYREF
  int v76; // [rsp+48h] [rbp-38h] BYREF
  __int64 v77; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v78; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v79; // [rsp+60h] [rbp-20h] BYREF
  __int64 v80; // [rsp+68h] [rbp-18h] BYREF
  unsigned int v81; // [rsp+70h] [rbp-10h]
  int v82; // [rsp+74h] [rbp-Ch]

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v75,
    "CAVIMediaSourcePlugin::GetOffsetForStartPosition",
    1133);
  v11 = *((_QWORD *)this + 7);
  v12 = (CAVIMediaSourcePlugin *)((char *)this - 24);
  v79 = 0;
  v80 = 0;
  v76 = 0;
  v82 = *(_DWORD *)(v11 + 160);
  if ( !a2 )
  {
    v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentIndexEntry = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CAVIMediaSourcePlugin::GetOffsetForStartPosition",
          1142,
          -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_178;
    v17 = 118;
    goto LABEL_12;
  }
  if ( !a3 )
  {
    v18 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentIndexEntry = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
      if ( *((_DWORD *)v20 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v20, "CAVIMediaSourcePlugin::GetOffsetForStartPosition", 1143, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_178;
    v17 = 119;
    goto LABEL_12;
  }
  if ( !a5 )
  {
    v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentIndexEntry = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
      if ( *((_DWORD *)v23 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v23, "CAVIMediaSourcePlugin::GetOffsetForStartPosition", 1144, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_178;
    v17 = 120;
    goto LABEL_12;
  }
  if ( !a6 )
  {
    v24 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentIndexEntry = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
      if ( *((_DWORD *)v26 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v26, "CAVIMediaSourcePlugin::GetOffsetForStartPosition", 1145, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_178;
    v17 = 121;
LABEL_12:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
      v12,
      -2147467261);
    goto LABEL_178;
  }
  if ( *((_QWORD *)v12 + 9) && a3->vt )
  {
    CurrentIndexEntry = CAVIMediaSourcePlugin::CheckForValidStartPosition(v12, a2, a3);
    if ( CurrentIndexEntry < 0 )
    {
      v28 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
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
        if ( *((_DWORD *)v30 + 499) != CurrentIndexEntry )
          CallStackContext::TraceFailure(
            v30,
            "CAVIMediaSourcePlugin::GetOffsetForStartPosition",
            1151,
            CurrentIndexEntry);
      }
      if ( g_wppLevels )
      {
        v31 = 123;
        goto LABEL_177;
      }
      goto LABEL_178;
    }
    v32 = (*((_DWORD *)v12 + 150) & 1) - 1LL;
    *a5 = v32;
    *a6 = v32;
    v33 = this;
    v34 = *((_QWORD *)this + 7);
    v35 = *(_DWORD *)(v34 + 112);
    *(_DWORD *)(v34 + 160) = (a4 & 1) == 0;
    v36 = 0;
    v81 = v35;
    while ( 1 )
    {
      v74 = v36;
      if ( v36 >= v35 )
      {
        if ( *a5 == -1 )
        {
          if ( (unsigned __int8)byte_1801B1109 >= 4u )
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qI)(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              130,
              &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
              v12,
              (LARGE_INTEGER)a3->hVal.QuadPart);
          v67 = (wchar_t *)CallStackTracing::s_wpInstance;
          CurrentIndexEntry = -1072875803;
          if ( !CallStackTracing::s_wpInstance )
          {
            v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
            CallStackTracing::s_wpInstance = v68;
            if ( v68 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
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
            if ( *((_DWORD *)v69 + 499) != -1072875803 )
              CallStackContext::TraceFailure(v69, "CAVIMediaSourcePlugin::GetOffsetForStartPosition", 1298, -1072875803);
          }
          if ( g_wppLevels )
          {
            v31 = 131;
            goto LABEL_177;
          }
        }
        else if ( (unsigned __int8)byte_1801B1109 >= 8u )
        {
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qIII)(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            132,
            &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
            v12,
            (LARGE_INTEGER)a3->hVal.QuadPart,
            *a5,
            *a6);
        }
        goto LABEL_178;
      }
      v37 = *((_QWORD *)v33 + 7);
      v77 = 0;
      v38 = *(CAVIIAVSStreamParser **)(*(_QWORD *)(v37 + 104) + 8LL * v36);
      if ( (*(unsigned int (__fastcall **)(CAVIIAVSStreamParser *))(*(_QWORD *)v38 + 8LL))(v38) )
      {
        NumberOfStreams = CAVIIAVSStreamParser::GetNumberOfStreams(v38);
        v78 = NumberOfStreams;
        for ( i = 0; ; ++i )
        {
          if ( i >= NumberOfStreams )
          {
            v36 = v74;
            goto LABEL_73;
          }
          CurrentIndexEntry = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, __int64 *))(**((_QWORD **)this + 6)
                                                                                          + 272LL))(
                                *((_QWORD *)this + 6),
                                i,
                                &v76,
                                &v77);
          if ( CurrentIndexEntry < 0 )
            break;
          if ( v76 )
            goto LABEL_74;
          ComSmartPtr<IUnknown>::Release(&v77);
          NumberOfStreams = v78;
        }
        v57 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41);
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
          if ( *((_DWORD *)v59 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(
              v59,
              "CAVIMediaSourcePlugin::GetOffsetForStartPosition",
              1186,
              CurrentIndexEntry);
        }
        if ( g_wppLevels )
        {
          v60 = 124;
          goto LABEL_122;
        }
        goto LABEL_123;
      }
      CurrentIndexEntry = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, __int64 *))(**((_QWORD **)this + 6) + 272LL))(
                            *((_QWORD *)this + 6),
                            v36,
                            &v76,
                            &v77);
      if ( CurrentIndexEntry < 0 )
      {
        v43 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42);
          CallStackTracing::s_wpInstance = v44;
          if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
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
          v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
          if ( *((_DWORD *)v66 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(
              v66,
              "CAVIMediaSourcePlugin::GetOffsetForStartPosition",
              1196,
              CurrentIndexEntry);
        }
        if ( g_wppLevels )
        {
          v60 = 125;
LABEL_122:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v60,
            &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
            v12,
            CurrentIndexEntry);
        }
        goto LABEL_123;
      }
LABEL_73:
      if ( !v76 )
        goto LABEL_111;
LABEL_74:
      if ( *((_DWORD *)v38 + 20) )
      {
        v36 = v74;
        goto LABEL_111;
      }
      v45 = MF_TIME_FORMAT_BYTESTREAM_OFFSET - *(_QWORD *)&a2->Data1;
      if ( MF_TIME_FORMAT_BYTESTREAM_OFFSET == *(_QWORD *)&a2->Data1 )
        v45 = 0xCA572657DBDF638CuLL - *(_QWORD *)a2->Data4;
      if ( !v45 )
      {
        CurrentIndexEntry = (*(__int64 (__fastcall **)(CAVIIAVSStreamParser *, LARGE_INTEGER, unsigned __int64 *, __int64 *))(*(_QWORD *)v38 + 32LL))(
                              v38,
                              a3->hVal,
                              &v79,
                              &v80);
        if ( CurrentIndexEntry == 1 )
        {
          CurrentIndexEntry = 0;
LABEL_80:
          v36 = v74;
          goto LABEL_111;
        }
        if ( CurrentIndexEntry < 0 )
        {
          v47 = (wchar_t *)CallStackTracing::s_wpInstance;
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
              v47 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v47 + 8) )
          {
            v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
            if ( *((_DWORD *)v61 + 499) != CurrentIndexEntry )
              CallStackContext::TraceFailure(
                v61,
                "CAVIMediaSourcePlugin::GetOffsetForStartPosition",
                1225,
                CurrentIndexEntry);
          }
          if ( g_wppLevels )
          {
            v60 = 126;
            goto LABEL_122;
          }
          goto LABEL_123;
        }
        goto LABEL_100;
      }
      if ( *((_DWORD *)v12 + 170) )
        goto LABEL_91;
      if ( !a3->hVal.QuadPart )
        break;
      v49 = this;
      *((_DWORD *)this + 164) = 1;
      if ( (unsigned __int8)byte_1801B1109 >= 0x20u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 127, &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids, v12);
LABEL_92:
      hVal = a3->hVal;
      v51 = *((_QWORD *)v49 + 71);
      if ( v51 != hVal.QuadPart || v51 == -1 )
      {
        CurrentIndexEntry = (*(__int64 (__fastcall **)(CAVIIAVSStreamParser *, LARGE_INTEGER, unsigned __int64 *, __int64 *))(*(_QWORD *)v38 + 24LL))(
                              v38,
                              hVal,
                              &v79,
                              &v80);
        if ( CurrentIndexEntry < 0 )
        {
          v63 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56);
            CallStackTracing::s_wpInstance = v64;
            if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
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
            if ( *((_DWORD *)v65 + 499) != CurrentIndexEntry )
              CallStackContext::TraceFailure(
                v65,
                "CAVIMediaSourcePlugin::GetOffsetForStartPosition",
                1259,
                CurrentIndexEntry);
          }
          if ( g_wppLevels )
          {
            v60 = 129;
            goto LABEL_122;
          }
LABEL_123:
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v77);
          goto LABEL_178;
        }
      }
      else
      {
        v52 = *(_QWORD *)v38;
        v78 = 0;
        v80 = (*(__int64 (__fastcall **)(CAVIIAVSStreamParser *))(v52 + 96))(v38);
        CurrentIndexEntry = CAVIStreamParser::GetCurrentIndexEntry(v38, &v79, &v78);
        if ( CurrentIndexEntry < 0 )
        {
          v54 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v53);
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
            v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
            if ( *((_DWORD *)v62 + 499) != CurrentIndexEntry )
              CallStackContext::TraceFailure(
                v62,
                "CAVIMediaSourcePlugin::GetOffsetForStartPosition",
                1253,
                CurrentIndexEntry);
          }
          if ( g_wppLevels )
          {
            v60 = 128;
            goto LABEL_122;
          }
          goto LABEL_123;
        }
      }
LABEL_100:
      if ( (*((_DWORD *)this + 144) & 1) == 0 )
      {
        if ( v79 < *a5 )
          *a5 = v79;
        if ( *a6 == -1 || v80 < *a6 )
          *a6 = v80;
        goto LABEL_80;
      }
      if ( v79 > *a5 )
        *a5 = v79;
      v36 = v74;
      if ( v80 > *a6 )
        *a6 = v80;
LABEL_111:
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v77);
      v35 = v81;
      ++v36;
      v33 = this;
    }
    *((_DWORD *)this + 164) = 2;
    CAVIMediaSourcePlugin::FlushFirstFrameInfo(v12);
LABEL_91:
    v49 = this;
    goto LABEL_92;
  }
  v70 = (wchar_t *)CallStackTracing::s_wpInstance;
  CurrentIndexEntry = -1072875854;
  if ( !CallStackTracing::s_wpInstance )
  {
    v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
    if ( *((_DWORD *)v72 + 499) != -1072875854 )
      CallStackContext::TraceFailure(v72, "CAVIMediaSourcePlugin::GetOffsetForStartPosition", 1149, -1072875854);
  }
  if ( g_wppLevels )
  {
    v31 = 122;
LABEL_177:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v31,
      &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
      v12,
      CurrentIndexEntry);
  }
LABEL_178:
  *(_DWORD *)(*((_QWORD *)this + 7) + 160LL) = v82;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v75);
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
