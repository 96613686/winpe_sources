# CAVIMediaSourcePlugin::GetOffsetForStartPosition(_GUID const *,tagPROPVARIANT const *,ulong,unsigned __int64 *,__int64 *)

- ea: `0x18008bef0`
- end: `0x18008ca97`
- name: `?GetOffsetForStartPosition@CAVIMediaSourcePlugin@@UEAAJPEBU_GUID@@PEBUtagPROPVARIANT@@KPEA_KPEA_J@Z`
- size: `2983`
- prototype: `int(CAVIMediaSourcePlugin *__hidden this, const struct _GUID *, const struct tagPROPVARIANT *, unsigned int, unsigned __int64 *, __int64 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005cf4`
- `0x180008890`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x1800476a0`
- `0x18005e2e4`
- `0x180079680`
- `0x18007a0e4`
- `0x180085174`
- `0x18008bef0`
- `0x180121750`
- `0x180147250`
- `0x1801487d8`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008bf75`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c01a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c0bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c164`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c225`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c3aa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c476`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c57e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c666`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c7b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c8df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c9c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008bf75`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c01a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c0bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c164`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c225`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c3aa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c476`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c57e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c666`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c7b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c8df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008c9c1`

## string_xrefs

- `0x18008bf17`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`
- `0x18008c1c1`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`
- `0x18008c282`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`
- `0x18008c6c3`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`
- `0x18008c736`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`
- `0x18008c77f`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`
- `0x18008c814`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`
- `0x18008c864`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`
- `0x18008c93c`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`
- `0x18008ca1e`: `CAVIMediaSourcePlugin::GetOffsetForStartPosition`

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
        v13 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v18 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v21 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v24 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v28 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          if ( (unsigned __int8)byte_1801BA109 >= 4u )
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
              v67 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        else if ( (unsigned __int8)byte_1801BA109 >= 8u )
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
            v57 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v43 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v47 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      if ( (unsigned __int8)byte_1801BA109 >= 0x20u )
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
              v63 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v54 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v70 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x18008bef0  mov     [rsp-38h+arg_10], rbx
0x18008bef5  mov     [rsp-38h+arg_8], rdx
0x18008befa  mov     [rsp-38h+arg_0], rcx
0x18008beff  push    rbp
0x18008bf00  push    rsi
0x18008bf01  push    rdi
0x18008bf02  push    r12
0x18008bf04  push    r13
0x18008bf06  push    r14
0x18008bf08  push    r15
0x18008bf0a  mov     rbp, rsp
0x18008bf0d  sub     rsp, 80h
0x18008bf14  mov     rdi, r8
0x18008bf17  lea     r13, aCavimediasourc_2; "CAVIMediaSourcePlugin::GetOffsetForStar"...
0x18008bf1e  mov     rbx, rdx
0x18008bf21  mov     rsi, rcx
0x18008bf24  mov     rdx, r13; char *
0x18008bf27  lea     rcx, [rbp+var_3C]; this
0x18008bf2b  mov     r8d, 46Dh; int
0x18008bf31  mov     r14d, r9d
0x18008bf34  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18008bf39  mov     rax, [rsi+38h]
0x18008bf3d  xor     r12d, r12d
0x18008bf40  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18008bf44  mov     [rbp+var_20], r12
0x18008bf48  mov     [rbp+var_18], r12
0x18008bf4c  mov     [rbp+var_38], r12d
0x18008bf50  mov     eax, [rax+0A0h]
0x18008bf56  mov     [rbp+var_C], eax
0x18008bf59  test    rbx, rbx
0x18008bf5c  jnz     loc_18008BFFE
0x18008bf62  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008bf69  mov     edi, 80004003h
0x18008bf6e  mov     ebx, edi
0x18008bf70  test    rcx, rcx
0x18008bf73  jnz     short loc_18008BFBC
0x18008bf75  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008bf7c  nop     dword ptr [rax+rax+00h]
0x18008bf81  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008bf88  mov     rcx, rax
0x18008bf8b  test    rax, rax
0x18008bf8e  jz      short loc_18008BFAE
0x18008bf90  mov     rax, [rax]
0x18008bf93  mov     edx, 7F0h
0x18008bf98  mov     rax, [rax+8]
0x18008bf9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bfa1  test    eax, eax
0x18008bfa3  jz      short loc_18008BFAE
0x18008bfa5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008bfac  jmp     short loc_18008BFBC
0x18008bfae  lea     rcx, qword_1801B97E0; this
0x18008bfb5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008bfbc  cmp     [rcx+8], r12b
0x18008bfc0  jz      short loc_18008BFE3
0x18008bfc2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008bfc7  cmp     [rax+7CCh], edi
0x18008bfcd  jz      short loc_18008BFE3
0x18008bfcf  mov     r9d, edi; int
0x18008bfd2  mov     r8d, 476h; int
0x18008bfd8  mov     rdx, r13; char *
0x18008bfdb  mov     rcx, rax; this
0x18008bfde  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008bfe3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008bfea  jb      loc_18008CA5F
0x18008bff0  mov     edx, 76h ; 'v'
0x18008bff5  mov     dword ptr [rsp+80h+var_60], edi
0x18008bff9  jmp     loc_18008CA45
0x18008bffe  test    rdi, rdi
0x18008c001  jnz     loc_18008C09F
0x18008c007  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008c00e  mov     edi, 80004003h
0x18008c013  mov     ebx, edi
0x18008c015  test    rcx, rcx
0x18008c018  jnz     short loc_18008C061
0x18008c01a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008c021  nop     dword ptr [rax+rax+00h]
0x18008c026  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008c02d  mov     rcx, rax
0x18008c030  test    rax, rax
0x18008c033  jz      short loc_18008C053
0x18008c035  mov     rax, [rax]
0x18008c038  mov     edx, 7F0h
0x18008c03d  mov     rax, [rax+8]
0x18008c041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c046  test    eax, eax
0x18008c048  jz      short loc_18008C053
0x18008c04a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008c051  jmp     short loc_18008C061
0x18008c053  lea     rcx, qword_1801B97E0; this
0x18008c05a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008c061  cmp     [rcx+8], r12b
0x18008c065  jz      short loc_18008C088
0x18008c067  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008c06c  cmp     [rax+7CCh], edi
0x18008c072  jz      short loc_18008C088
0x18008c074  mov     r9d, edi; int
0x18008c077  mov     r8d, 477h; int
0x18008c07d  mov     rdx, r13; char *
0x18008c080  mov     rcx, rax; this
0x18008c083  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008c088  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008c08f  jb      loc_18008CA5F
0x18008c095  mov     edx, 77h ; 'w'
0x18008c09a  jmp     loc_18008BFF5
0x18008c09f  mov     r15, [rbp+arg_20]
0x18008c0a3  test    r15, r15
0x18008c0a6  jnz     loc_18008C144
0x18008c0ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008c0b3  mov     edi, 80004003h
0x18008c0b8  mov     ebx, edi
0x18008c0ba  test    rcx, rcx
0x18008c0bd  jnz     short loc_18008C106
0x18008c0bf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008c0c6  nop     dword ptr [rax+rax+00h]
0x18008c0cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008c0d2  mov     rcx, rax
0x18008c0d5  test    rax, rax
0x18008c0d8  jz      short loc_18008C0F8
0x18008c0da  mov     rax, [rax]
0x18008c0dd  mov     edx, 7F0h
0x18008c0e2  mov     rax, [rax+8]
0x18008c0e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c0eb  test    eax, eax
0x18008c0ed  jz      short loc_18008C0F8
0x18008c0ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008c0f6  jmp     short loc_18008C106
0x18008c0f8  lea     rcx, qword_1801B97E0; this
0x18008c0ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008c106  cmp     [rcx+8], r12b
0x18008c10a  jz      short loc_18008C12D
0x18008c10c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008c111  cmp     [rax+7CCh], edi
0x18008c117  jz      short loc_18008C12D
0x18008c119  mov     r9d, edi; int
0x18008c11c  mov     r8d, 478h; int
0x18008c122  mov     rdx, r13; char *
0x18008c125  mov     rcx, rax; this
0x18008c128  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008c12d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008c134  jb      loc_18008CA5F
0x18008c13a  mov     edx, 78h ; 'x'
0x18008c13f  jmp     loc_18008BFF5
0x18008c144  mov     r13, [rbp+arg_28]
0x18008c148  test    r13, r13
0x18008c14b  jnz     loc_18008C1ED
0x18008c151  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008c158  mov     edi, 80004003h
0x18008c15d  mov     ebx, edi
0x18008c15f  test    rcx, rcx
0x18008c162  jnz     short loc_18008C1AB
0x18008c164  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008c16b  nop     dword ptr [rax+rax+00h]
0x18008c170  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008c177  mov     rcx, rax
0x18008c17a  test    rax, rax
0x18008c17d  jz      short loc_18008C19D
0x18008c17f  mov     rax, [rax]
0x18008c182  mov     edx, 7F0h
0x18008c187  mov     rax, [rax+8]
0x18008c18b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c190  test    eax, eax
0x18008c192  jz      short loc_18008C19D
0x18008c194  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008c19b  jmp     short loc_18008C1AB
0x18008c19d  lea     rcx, qword_1801B97E0; this
0x18008c1a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008c1ab  cmp     [rcx+8], r12b
0x18008c1af  jz      short loc_18008C1D6
0x18008c1b1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008c1b6  cmp     [rax+7CCh], edi
0x18008c1bc  jz      short loc_18008C1D6
0x18008c1be  mov     r9d, edi; int
0x18008c1c1  lea     rdx, aCavimediasourc_2; "CAVIMediaSourcePlugin::GetOffsetForStar"...
0x18008c1c8  mov     r8d, 479h; int
0x18008c1ce  mov     rcx, rax; this
0x18008c1d1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008c1d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008c1dd  jb      loc_18008CA5F
0x18008c1e3  mov     edx, 79h ; 'y'
0x18008c1e8  jmp     loc_18008BFF5
0x18008c1ed  cmp     [rsi+48h], r12
0x18008c1f1  jz      loc_18008C9B0
0x18008c1f7  cmp     [rdi], r12w
0x18008c1fb  jz      loc_18008C9B0
0x18008c201  mov     r8, rdi; struct tagPROPVARIANT *
0x18008c204  mov     rdx, rbx; struct _GUID *
0x18008c207  mov     rcx, rsi; this
0x18008c20a  call    ?CheckForValidStartPosition@CAVIMediaSourcePlugin@@AEAAJPEBU_GUID@@PEBUtagPROPVARIANT@@@Z; CAVIMediaSourcePlugin::CheckForValidStartPosition(_GUID const *,tagPROPVARIANT const *)
0x18008c20f  mov     ebx, eax
0x18008c211  test    eax, eax
0x18008c213  jns     loc_18008C2AE
0x18008c219  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008c220  test    rcx, rcx
0x18008c223  jnz     short loc_18008C26C
0x18008c225  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008c22c  nop     dword ptr [rax+rax+00h]
0x18008c231  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008c238  mov     rcx, rax
0x18008c23b  test    rax, rax
0x18008c23e  jz      short loc_18008C25E
0x18008c240  mov     rax, [rax]
0x18008c243  mov     edx, 7F0h
0x18008c248  mov     rax, [rax+8]
0x18008c24c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c251  test    eax, eax
0x18008c253  jz      short loc_18008C25E
0x18008c255  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008c25c  jmp     short loc_18008C26C
0x18008c25e  lea     rcx, qword_1801B97E0; this
0x18008c265  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008c26c  cmp     [rcx+8], r12b
0x18008c270  jz      short loc_18008C297
0x18008c272  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008c277  cmp     [rax+7CCh], ebx
0x18008c27d  jz      short loc_18008C297
0x18008c27f  mov     r9d, ebx; int
0x18008c282  lea     rdx, aCavimediasourc_2; "CAVIMediaSourcePlugin::GetOffsetForStar"...
0x18008c289  mov     r8d, 47Fh; int
0x18008c28f  mov     rcx, rax; this
0x18008c292  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008c297  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008c29e  jb      loc_18008CA5F
0x18008c2a4  mov     edx, 7Bh ; '{'
0x18008c2a9  jmp     loc_18008CA41
0x18008c2ae  mov     eax, [rsi+258h]
0x18008c2b4  not     r14d
0x18008c2b7  and     eax, 1
0x18008c2ba  dec     rax
0x18008c2bd  mov     [r15], rax
0x18008c2c0  and     r14d, 1
0x18008c2c4  mov     [r13+0], rax
0x18008c2c8  mov     r8, [rbp+arg_0]
0x18008c2cc  mov     rax, [r8+38h]
0x18008c2d0  mov     ecx, [rax+70h]
0x18008c2d3  mov     [rax+0A0h], r14d
0x18008c2da  mov     r14d, r12d
0x18008c2dd  mov     [rbp+var_10], ecx
0x18008c2e0  mov     [rbp+var_40], r14d
0x18008c2e4  cmp     r14d, ecx
0x18008c2e7  jnb     loc_18008C890
0x18008c2ed  mov     rax, [r8+38h]
0x18008c2f1  mov     [rbp+var_30], r12
0x18008c2f5  mov     edx, r14d
0x18008c2f8  mov     rcx, [rax+68h]
0x18008c2fc  mov     r12, [rcx+rdx*8]
0x18008c300  mov     rcx, r12
0x18008c303  mov     rax, [r12]
0x18008c307  mov     rax, [rax+8]
0x18008c30b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c310  test    eax, eax
0x18008c312  jz      short loc_18008C372
0x18008c314  mov     rcx, r12; this
0x18008c317  call    ?GetNumberOfStreams@CAVIIAVSStreamParser@@QEAAKXZ; CAVIIAVSStreamParser::GetNumberOfStreams(void)
0x18008c31c  mov     [rbp+var_28], eax
0x18008c31f  xor     r14d, r14d
0x18008c322  cmp     r14d, eax
0x18008c325  jnb     loc_18008C3EE
0x18008c32b  mov     rax, [rbp+arg_0]
0x18008c32f  lea     r9, [rbp+var_30]
0x18008c333  lea     r8, [rbp+var_38]
0x18008c337  mov     edx, r14d
0x18008c33a  mov     rcx, [rax+30h]
0x18008c33e  mov     rax, [rcx]
0x18008c341  mov     rax, [rax+110h]
0x18008c348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c34d  mov     ebx, eax
0x18008c34f  test    eax, eax
0x18008c351  js      loc_18008C65A
0x18008c357  cmp     [rbp+var_38], 0
0x18008c35b  jnz     loc_18008C3FC
0x18008c361  lea     rcx, [rbp+var_30]
0x18008c365  call    ?Release@?$ComSmartPtr@UIUnknown@@@@QEAAXXZ; ComSmartPtr<IUnknown>::Release(void)
0x18008c36a  mov     eax, [rbp+var_28]
0x18008c36d  inc     r14d
0x18008c370  jmp     short loc_18008C322
0x18008c372  mov     rax, [rbp+arg_0]
0x18008c376  lea     r9, [rbp+var_30]
0x18008c37a  lea     r8, [rbp+var_38]
0x18008c37e  mov     edx, r14d
0x18008c381  mov     rcx, [rax+30h]
0x18008c385  mov     rax, [rcx]
0x18008c388  mov     rax, [rax+110h]
0x18008c38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c394  mov     ebx, eax
0x18008c396  test    eax, eax
0x18008c398  jns     short loc_18008C3F2
0x18008c39a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008c3a1  test    rcx, rcx
0x18008c3a4  jnz     loc_18008C84E
0x18008c3aa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008c3b1  nop     dword ptr [rax+rax+00h]
0x18008c3b6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008c3bd  mov     rcx, rax
0x18008c3c0  test    rax, rax
0x18008c3c3  jz      loc_18008C840
0x18008c3c9  mov     rax, [rax]
0x18008c3cc  mov     edx, 7F0h
0x18008c3d1  mov     rax, [rax+8]
0x18008c3d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c3da  test    eax, eax
  ... truncated ...
```
