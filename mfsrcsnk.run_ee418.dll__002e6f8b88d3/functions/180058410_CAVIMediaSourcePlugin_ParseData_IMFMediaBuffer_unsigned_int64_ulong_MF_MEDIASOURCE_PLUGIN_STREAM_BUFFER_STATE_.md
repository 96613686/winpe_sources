# CAVIMediaSourcePlugin::ParseData(IMFMediaBuffer *,unsigned __int64,ulong,_MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE *,unsigned __int64 *)

- ea: `0x180058410`
- end: `0x1800595f6`
- name: `?ParseData@CAVIMediaSourcePlugin@@UEAAJPEAUIMFMediaBuffer@@_KKPEAU_MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE@@PEA_K@Z`
- size: `4582`
- prototype: `int(CAVIMediaSourcePlugin *__hidden this, struct IMFMediaBuffer *, unsigned __int64, unsigned int, struct _MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180005eb8`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x18003fe50`
- `0x180057dd8`
- `0x180058410`
- `0x1800595fc`
- `0x18005af5c`
- `0x180071a44`
- `0x180073b14`
- `0x180074814`
- `0x18011b1e4`
- `0x180138540`
- `0x1801394b4`
- `0x180140b20`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800584a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005854c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800585fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800587ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058985`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058d2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058db5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058e44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058ed3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058fb2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059060`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800590ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005917e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005920d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800592ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059392`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059421`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800584a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005854c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800585fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800587ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058985`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058d2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058db5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058e44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058ed3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058fb2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059060`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800590ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005917e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005920d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800592ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059392`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059421`
- `MFPlat!MFCreateSample` at `0x180058b2a`
- `MFPlat!MFCreateSample` at `0x180058b2a`

## string_xrefs

- `0x18005842f`: `CAVIMediaSourcePlugin::ParseData`
- `0x180058653`: `CAVIMediaSourcePlugin::ParseData`
- `0x180058804`: `CAVIMediaSourcePlugin::ParseData`
- `0x180058e0c`: `CAVIMediaSourcePlugin::ParseData`
- `0x180058e9b`: `CAVIMediaSourcePlugin::ParseData`
- `0x180058f2a`: `CAVIMediaSourcePlugin::ParseData`
- `0x180058f7a`: `CAVIMediaSourcePlugin::ParseData`
- `0x180059009`: `CAVIMediaSourcePlugin::ParseData`
- `0x1800590b7`: `CAVIMediaSourcePlugin::ParseData`
- `0x180059146`: `CAVIMediaSourcePlugin::ParseData`
- `0x1800591d5`: `CAVIMediaSourcePlugin::ParseData`
- `0x180059264`: `CAVIMediaSourcePlugin::ParseData`
- `0x1800592b4`: `CAVIMediaSourcePlugin::ParseData`
- `0x180059343`: `CAVIMediaSourcePlugin::ParseData`
- `0x1800593e9`: `CAVIMediaSourcePlugin::ParseData`
- `0x180059478`: `CAVIMediaSourcePlugin::ParseData`

## pseudocode

```c
__int64 __fastcall CAVIMediaSourcePlugin::ParseData(
        CAVIMediaSourcePlugin *this,
        struct IMFMediaBuffer *a2,
        unsigned __int64 a3,
        unsigned int a4,
        struct _MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE *a5,
        unsigned __int64 *a6)
{
  CAVIMediaSourcePlugin *v8; // r13
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  char *v13; // r14
  wchar_t *v14; // rcx
  HRESULT CurrentIndexEntry; // ebx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  unsigned int v29; // r9d
  unsigned int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  bool v35; // zf
  __int64 i; // rbx
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 j; // rdx
  __int64 v41; // r8
  BOOL v42; // ecx
  __int64 v43; // rax
  unsigned int v44; // edx
  __int64 v45; // rdi
  CAVIIAVSStreamParser *v46; // rbx
  unsigned int NumberOfStreams; // r13d
  unsigned int k; // r12d
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  wchar_t *v55; // rcx
  CallStackTracing *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // r9
  CAVIStreamParser *v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // r9
  __int64 v64; // r13
  CAVIStreamParser *v65; // r12
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r9
  IMFSample *v69; // rcx
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // r9
  __int64 v73; // rdx
  __int64 v74; // r8
  __int64 v75; // r9
  __int64 v76; // rdx
  __int64 v77; // r8
  __int64 v78; // r9
  IMFSample *v79; // rdi
  HRESULT (__stdcall *SetSampleTime)(IMFSample *, LONGLONG); // rbx
  __int64 v81; // rax
  __int64 v82; // rdx
  __int64 v83; // r8
  __int64 v84; // r9
  __int64 v85; // rdx
  __int64 v86; // r8
  __int64 v87; // r9
  __int64 v88; // rax
  __int64 v89; // rdx
  __int64 v90; // r8
  __int64 v91; // r9
  __int64 v92; // rbx
  __int64 v93; // rax
  __int64 v94; // rcx
  __int64 v95; // rdx
  __int64 v96; // r8
  __int64 v97; // rax
  __int64 v98; // rcx
  int v99; // edi
  __int64 v100; // rdx
  __int64 v101; // r8
  __int64 v102; // r9
  wchar_t *v103; // rcx
  CallStackTracing *v104; // rax
  int v105; // eax
  __int64 v106; // rdx
  __int64 v107; // r8
  __int64 v108; // r9
  wchar_t *v109; // rcx
  CallStackTracing *v110; // rax
  struct CallStackContext *v111; // rax
  __int64 v112; // rdx
  wchar_t *v113; // rcx
  CallStackTracing *v114; // rax
  struct CallStackContext *v115; // rax
  wchar_t *v116; // rcx
  CallStackTracing *v117; // rax
  struct CallStackContext *v118; // rax
  struct CallStackContext *v119; // rax
  wchar_t *v120; // rcx
  CallStackTracing *v121; // rax
  struct CallStackContext *v122; // rax
  __int64 v123; // rdx
  wchar_t *v124; // rcx
  CallStackTracing *v125; // rax
  struct CallStackContext *v126; // rax
  wchar_t *v127; // rcx
  CallStackTracing *v128; // rax
  struct CallStackContext *v129; // rax
  wchar_t *v130; // rcx
  CallStackTracing *v131; // rax
  struct CallStackContext *v132; // rax
  wchar_t *v133; // rcx
  CallStackTracing *v134; // rax
  struct CallStackContext *v135; // rax
  struct CallStackContext *v136; // rax
  wchar_t *v137; // rcx
  CallStackTracing *v138; // rax
  struct CallStackContext *v139; // rax
  wchar_t *v140; // rcx
  CallStackTracing *v141; // rax
  struct CallStackContext *v142; // rax
  wchar_t *v143; // rcx
  CallStackTracing *v144; // rax
  struct CallStackContext *v145; // rax
  unsigned __int64 *v146; // rcx
  CallStackTracing *v147; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  int v150; // [rsp+30h] [rbp-49h]
  unsigned __int64 v151; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v152[4]; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v153; // [rsp+44h] [rbp-35h]
  IMFSample *ppIMFSample; // [rsp+48h] [rbp-31h] BYREF
  int v155; // [rsp+50h] [rbp-29h] BYREF
  int v156; // [rsp+54h] [rbp-25h]
  __int64 v157; // [rsp+58h] [rbp-21h] BYREF
  int v158; // [rsp+60h] [rbp-19h] BYREF
  int v159; // [rsp+64h] [rbp-15h] BYREF
  unsigned int v160; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int64 v161; // [rsp+70h] [rbp-9h] BYREF
  _QWORD v162[9]; // [rsp+78h] [rbp-1h] BYREF

  v155 = 0;
  v157 = 0;
  v8 = this;
  ppIMFSample = 0;
  v161 = 0;
  v160 = 0;
  v159 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v152, "CAVIMediaSourcePlugin::ParseData", 1497);
  v13 = (char *)v8 - 16;
  if ( !*((_QWORD *)v8 + 7) || *(_DWORD *)(*((_QWORD *)v8 + 8) + 180LL) != 3 )
  {
    v147 = CallStackTracing::s_wpInstance;
    CurrentIndexEntry = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v147 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v147 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v147);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875854 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIMediaSourcePlugin::ParseData", 1501, -1072875854);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        154,
        &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
        v13,
        -1072875854);
    goto LABEL_285;
  }
  if ( !a2 )
  {
    v14 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentIndexEntry = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v14 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)v17 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v17, "CAVIMediaSourcePlugin::ParseData", 1504, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_285;
    v18 = 155;
    goto LABEL_14;
  }
  if ( !a6 )
  {
    v19 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentIndexEntry = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v21 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v21, "CAVIMediaSourcePlugin::ParseData", 1505, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_285;
    v18 = 156;
LABEL_14:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v18,
      &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
      v13,
      -2147467261);
    goto LABEL_285;
  }
  CurrentIndexEntry = CSourcePluginBufferReader::AddBuffer((CAVIMediaSourcePlugin *)((char *)v8 + 72), a3, a2);
  if ( CurrentIndexEntry < 0 )
  {
    v25 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
      CallStackTracing::s_wpInstance = v26;
      if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
      {
        v25 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v25 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v25 + 8) )
    {
      v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
      if ( *((_DWORD *)v27 + 499) != CurrentIndexEntry )
        CallStackContext::TraceFailure(v27, "CAVIMediaSourcePlugin::ParseData", 1507, CurrentIndexEntry);
    }
    if ( !g_wppLevels )
      goto LABEL_270;
    v28 = 157;
    goto LABEL_37;
  }
  *a6 = -1;
  v29 = *(_DWORD *)(*((_QWORD *)v13 + 10) + 112LL);
  v30 = *((_DWORD *)v8 + 147);
  v153 = v29;
  if ( v30 != -1 )
  {
    v31 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 8) + 104LL) + 8LL * v30);
    CurrentIndexEntry = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 88LL))(v31);
    if ( CurrentIndexEntry == 1 )
    {
      if ( (unsigned __int8)byte_1801B1109 >= 0x20u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          158,
          &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
          (char *)v8 - 16,
          *((_DWORD *)v13 + 151));
    }
    else
    {
      if ( CurrentIndexEntry < 0 )
      {
        v37 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
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
          if ( *((_DWORD *)v39 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(v39, "CAVIMediaSourcePlugin::ParseData", 1533, CurrentIndexEntry);
        }
        if ( !g_wppLevels )
          goto LABEL_270;
        v28 = 159;
LABEL_37:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v28,
          &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
          v13,
          CurrentIndexEntry);
        goto LABEL_270;
      }
      *((_DWORD *)v8 + 147) = -1;
    }
    v29 = v153;
  }
  v35 = *((_DWORD *)v8 + 150) == 0;
  v156 = -1;
  if ( v35 )
  {
    for ( i = 0; (unsigned int)i < a4 && a4 == v29; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned __int8)byte_1801B1109 >= 0x20u )
      {
        WPP_SF_qDD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          160,
          &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
          (char *)v8 - 16,
          *((_DWORD *)a5 + 2 * i),
          *((_DWORD *)a5 + 2 * i + 1));
        v29 = v153;
      }
      if ( !*((_DWORD *)a5 + 2 * i + 1) )
      {
        for ( j = 0; (unsigned int)j < a4; j = (unsigned int)(j + 1) )
        {
          v41 = 8 * j;
          v42 = (unsigned int)j < v29
             && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 8) + 104LL) + 8 * j) + 80LL) != 0;
          if ( *(_DWORD *)((char *)a5 + v41 + 4) && !v42 )
          {
            v156 = *(_DWORD *)((char *)a5 + v41);
            goto LABEL_72;
          }
        }
        break;
      }
    }
  }
LABEL_72:
  while ( 2 )
  {
    v43 = *((_QWORD *)v8 + 8);
    v44 = -1;
    v45 = 0;
    v158 = -1;
    v150 = -1;
    v151 = -(__int64)(*(_DWORD *)(v43 + 160) != 0);
    while ( (unsigned int)v45 < v29 )
    {
      if ( v157 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v157 + 16LL))(v157);
        v157 = 0;
      }
      if ( ppIMFSample )
      {
        ((void (__fastcall *)(IMFSample *))ppIMFSample->lpVtbl->Release)(ppIMFSample);
        ppIMFSample = 0;
      }
      v46 = *(CAVIIAVSStreamParser **)(*(_QWORD *)(*((_QWORD *)v8 + 8) + 104LL) + 8 * v45);
      if ( (*(unsigned int (__fastcall **)(CAVIIAVSStreamParser *))(*(_QWORD *)v46 + 8LL))(v46) )
      {
        NumberOfStreams = CAVIIAVSStreamParser::GetNumberOfStreams(v46);
        for ( k = 0; ; ++k )
        {
          if ( k >= NumberOfStreams )
          {
            v8 = this;
            goto LABEL_90;
          }
          CurrentIndexEntry = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, __int64 *))(**((_QWORD **)this + 7)
                                                                                          + 272LL))(
                                *((_QWORD *)this + 7),
                                k,
                                &v155,
                                &v157);
          if ( CurrentIndexEntry < 0 )
            break;
          if ( v155 )
            goto LABEL_91;
          ComSmartPtr<IUnknown>::Release(&v157);
        }
        v109 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v110 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49, v50, v51);
          CallStackTracing::s_wpInstance = v110;
          if ( v110 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v110 + 8LL))(v110, 2032) )
          {
            v109 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v109 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v109 + 8) )
        {
          v111 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v109);
          if ( *((_DWORD *)v111 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(v111, "CAVIMediaSourcePlugin::ParseData", 1611, CurrentIndexEntry);
        }
        if ( g_wppLevels )
        {
          v112 = 161;
          goto LABEL_268;
        }
LABEL_269:
        v8 = this;
LABEL_270:
        if ( CurrentIndexEntry == -1072863856 )
        {
LABEL_271:
          v146 = a6;
          CurrentIndexEntry = 0;
          *a6 = *((_QWORD *)v8 + 69);
          goto LABEL_276;
        }
        goto LABEL_285;
      }
      CurrentIndexEntry = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, __int64 *))(**((_QWORD **)v8 + 7) + 272LL))(
                            *((_QWORD *)v8 + 7),
                            (unsigned int)v45,
                            &v155,
                            &v157);
      if ( CurrentIndexEntry < 0 )
      {
        v55 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53, v54);
          CallStackTracing::s_wpInstance = v56;
          if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
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
          v119 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
          if ( *((_DWORD *)v119 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(v119, "CAVIMediaSourcePlugin::ParseData", 1621, CurrentIndexEntry);
        }
        if ( !g_wppLevels )
          goto LABEL_270;
        v28 = 162;
        goto LABEL_37;
      }
LABEL_90:
      if ( !v155 )
        goto LABEL_97;
LABEL_91:
      CurrentIndexEntry = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v157 + 264LL))(v157, &v158);
      if ( CurrentIndexEntry < 0 )
      {
        v116 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v117 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v57, v58, v59);
          CallStackTracing::s_wpInstance = v117;
          if ( v117 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v117 + 8LL))(v117, 2032) )
          {
            v116 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v116 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v116 + 8) )
        {
          v118 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v116);
          if ( *((_DWORD *)v118 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(v118, "CAVIMediaSourcePlugin::ParseData", 1628, CurrentIndexEntry);
        }
        if ( !g_wppLevels )
          goto LABEL_269;
        v112 = 163;
        goto LABEL_268;
      }
      if ( v156 != -1 && v156 != v158 )
      {
        if ( (unsigned __int8)byte_1801B1109 >= 0x20u )
          WPP_SF_qDD(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            164,
            &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
            v13,
            v45,
            v158);
        v8 = this;
LABEL_97:
        v44 = v150;
        goto LABEL_98;
      }
      v8 = this;
      v60 = *(CAVIStreamParser **)(*(_QWORD *)(*((_QWORD *)this + 8) + 104LL) + 8 * v45);
      if ( *((_DWORD *)v60 + 20) )
        goto LABEL_97;
      CurrentIndexEntry = CAVIStreamParser::GetCurrentIndexEntry(v60, &v161, &v160);
      if ( CurrentIndexEntry < 0 )
      {
        v113 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v114 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v61, v62, v63);
          CallStackTracing::s_wpInstance = v114;
          if ( v114 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v114 + 8LL))(v114, 2032) )
          {
            v113 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v113 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v113 + 8) )
        {
          v115 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v113);
          if ( *((_DWORD *)v115 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(v115, "CAVIMediaSourcePlugin::ParseData", 1641, CurrentIndexEntry);
        }
        if ( !g_wppLevels )
          goto LABEL_270;
        v28 = 165;
        goto LABEL_37;
      }
      if ( *(_DWORD *)(*((_QWORD *)v13 + 10) + 160LL) )
      {
        if ( v151 <= v161 )
          goto LABEL_97;
      }
      else if ( v151 >= v161 )
      {
        goto LABEL_97;
      }
      v44 = v45;
      v151 = v161;
      v150 = v45;
LABEL_98:
      v29 = v153;
      v45 = (unsigned int)(v45 + 1);
    }
    if ( v44 != -1 )
    {
      v64 = v44;
      v65 = *(CAVIStreamParser **)(*(_QWORD *)(*((_QWORD *)this + 8) + 104LL) + 8LL * v44);
      CurrentIndexEntry = CAVIStreamParser::IsNextSamplesFormatDifferent(v65, &v159);
      if ( CurrentIndexEntry < 0 )
      {
        v143 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v144 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v67, v68);
          CallStackTracing::s_wpInstance = v144;
          if ( v144 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v144 + 8LL))(v144, 2032) )
          {
            v143 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v143 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v143 + 8) )
        {
          v145 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v143);
          if ( *((_DWORD *)v145 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(v145, "CAVIMediaSourcePlugin::ParseData", 1664, CurrentIndexEntry);
        }
        if ( !g_wppLevels )
          goto LABEL_269;
        v112 = 167;
      }
      else
      {
        v69 = ppIMFSample;
        if ( ppIMFSample )
        {
          ppIMFSample = 0;
          ((void (__fastcall *)(IMFSample *))v69->lpVtbl->Release)(v69);
        }
        if ( v159 )
        {
          v151 = 0;
          CurrentIndexEntry = CAVIStreamParser::UpdateCurrentFormat(v65);
          if ( CurrentIndexEntry < 0 )
          {
            v133 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v134 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v70, v71, v72);
              CallStackTracing::s_wpInstance = v134;
              if ( v134
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v134 + 8LL))(v134, 2032) )
              {
                v133 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v133 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v133 + 8) )
            {
              v135 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v133);
              if ( *((_DWORD *)v135 + 499) != CurrentIndexEntry )
                CallStackContext::TraceFailure(v135, "CAVIMediaSourcePlugin::ParseData", 1672, CurrentIndexEntry);
            }
            if ( !g_wppLevels )
              goto LABEL_190;
            v123 = 168;
          }
          else
          {
            CurrentIndexEntry = (*(__int64 (__fastcall **)(CAVIStreamParser *, unsigned __int64 *))(*(_QWORD *)v65 + 48LL))(
                                  v65,
                                  &v151);
            if ( CurrentIndexEntry < 0 )
            {
              v130 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v131 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v73, v74, v75);
                CallStackTracing::s_wpInstance = v131;
                if ( v131
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v131 + 8LL))(v131, 2032) )
                {
                  v130 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v130 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v130 + 8) )
              {
                v132 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v130);
                if ( *((_DWORD *)v132 + 499) != CurrentIndexEntry )
                  CallStackContext::TraceFailure(v132, "CAVIMediaSourcePlugin::ParseData", 1673, CurrentIndexEntry);
              }
              if ( !g_wppLevels )
                goto LABEL_190;
              v123 = 169;
            }
            else
            {
              CurrentIndexEntry = MFCreateSample(&ppIMFSample);
              if ( CurrentIndexEntry < 0 )
              {
                v127 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v128 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v76, v77, v78);
                  CallStackTracing::s_wpInstance = v128;
                  if ( v128
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v128 + 8LL))(v128, 2032) )
                  {
                    v127 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v127 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v127 + 8) )
                {
                  v129 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v127);
                  if ( *((_DWORD *)v129 + 499) != CurrentIndexEntry )
                    CallStackContext::TraceFailure(v129, "CAVIMediaSourcePlugin::ParseData", 1676, CurrentIndexEntry);
                }
                if ( !g_wppLevels )
                  goto LABEL_190;
                v123 = 170;
              }
              else
              {
                v79 = ppIMFSample;
                SetSampleTime = ppIMFSample->lpVtbl->SetSampleTime;
                v81 = (*(__int64 (__fastcall **)(CAVIStreamParser *))(*(_QWORD *)v65 + 96LL))(v65);
                CurrentIndexEntry = ((__int64 (__fastcall *)(IMFSample *, __int64))SetSampleTime)(v79, v81);
                if ( CurrentIndexEntry >= 0 )
                {
                  CurrentIndexEntry = ((__int64 (__fastcall *)(IMFSample *, void *, unsigned __int64))ppIMFSample->lpVtbl->SetUnknown)(
                                        ppIMFSample,
                                        &AVI_SAMPLE_ATTRIBUTE_FORMATCHANGE_MEDIATYPE,
                                        v151);
                  if ( CurrentIndexEntry >= 0 )
                  {
                    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v151);
                    goto LABEL_118;
                  }
                  v120 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v121 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v85, v86, v87);
                    CallStackTracing::s_wpInstance = v121;
                    if ( v121
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v121 + 8LL))(
                           v121,
                           2032) )
                    {
                      v120 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v120 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                    }
                  }
                  if ( *((_BYTE *)v120 + 8) )
                  {
                    v122 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v120);
                    if ( *((_DWORD *)v122 + 499) != CurrentIndexEntry )
                      CallStackContext::TraceFailure(v122, "CAVIMediaSourcePlugin::ParseData", 1678, CurrentIndexEntry);
                  }
                  if ( g_wppLevels )
                  {
                    v123 = 172;
                    goto LABEL_189;
                  }
LABEL_190:
                  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v151);
                  goto LABEL_269;
                }
                v124 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v125 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v82, v83, v84);
                  CallStackTracing::s_wpInstance = v125;
                  if ( v125
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v125 + 8LL))(v125, 2032) )
                  {
                    v124 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v124 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v124 + 8) )
                {
                  v126 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v124);
                  if ( *((_DWORD *)v126 + 499) != CurrentIndexEntry )
                    CallStackContext::TraceFailure(v126, "CAVIMediaSourcePlugin::ParseData", 1677, CurrentIndexEntry);
                }
                if ( !g_wppLevels )
                  goto LABEL_190;
                v123 = 171;
              }
            }
          }
LABEL_189:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v123,
            &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
            v13,
            CurrentIndexEntry);
          goto LABEL_190;
        }
        v88 = *(_QWORD *)v65;
        LODWORD(v151) = 0;
        CurrentIndexEntry = (*(__int64 (__fastcall **)(CAVIStreamParser *, IMFSample **, unsigned __int64 *))(v88 + 72))(
                              v65,
                              &ppIMFSample,
                              &v151);
        if ( CurrentIndexEntry >= 0 )
        {
LABEL_118:
          if ( ppIMFSample )
          {
            if ( *((_QWORD *)v13 + 84) )
            {
              v92 = 3 * v64;
              v8 = this;
              v93 = *((_QWORD *)this + 82);
              if ( *(_QWORD *)(v93 + 8 * v92) && !*(_DWORD *)(v93 + 8 * v92 + 16) )
              {
                v151 = 0;
                v162[0] = 0;
                ((void (__fastcall *)(IMFSample *, unsigned __int64 *))ppIMFSample->lpVtbl->GetSampleTime)(
                  ppIMFSample,
                  &v151);
                v94 = *(_QWORD *)(*((_QWORD *)this + 82) + 8 * v92);
                (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v94 + 280LL))(v94, v162);
                v97 = *((_QWORD *)this + 82);
                if ( v151 == v162[0] )
                {
                  v98 = *(_QWORD *)(v97 + 8 * v92);
                  if ( v98 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                    *(_QWORD *)(*((_QWORD *)this + 82) + 8 * v92) = 0;
                  }
                  v99 = v150;
                  if ( (unsigned __int8)byte_1801B1109 >= 8u )
                    WPP_SF_qD(
                      *((_QWORD *)WPP_GLOBAL_Control + 7),
                      174,
                      &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
                      v13,
                      v150);
                }
                else
                {
                  *(_QWORD *)(v97 + 8 * v92 + 8) = v151;
                  v99 = v150;
                  if ( (unsigned __int8)byte_1801B1109 >= 8u )
                    WPP_SF_qdI(
                      *((_QWORD *)WPP_GLOBAL_Control + 7),
                      v95,
                      v96,
                      v13,
                      v150,
                      *(_QWORD *)(*((_QWORD *)this + 82) + 8 * v92 + 8));
                  *(_DWORD *)(*((_QWORD *)this + 82) + 8 * v92 + 16) = 1;
                }
LABEL_132:
                CurrentIndexEntry = (*(__int64 (__fastcall **)(CAVIStreamParser *, IMFSample *))(*(_QWORD *)v65 + 16LL))(
                                      v65,
                                      ppIMFSample);
                if ( CurrentIndexEntry < 0 )
                {
                  v103 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v104 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v100, v101, v102);
                    CallStackTracing::s_wpInstance = v104;
                    if ( v104
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v104 + 8LL))(
                           v104,
                           2032) )
                    {
                      v103 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v103 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                    }
                  }
                  if ( *((_BYTE *)v103 + 8) )
                  {
                    v136 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v103);
                    if ( *((_DWORD *)v136 + 499) != CurrentIndexEntry )
                      CallStackContext::TraceFailure(v136, "CAVIMediaSourcePlugin::ParseData", 1723, CurrentIndexEntry);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_270;
                  v28 = 176;
                  goto LABEL_37;
                }
LABEL_138:
                v105 = (*(__int64 (__fastcall **)(CAVIStreamParser *))(*(_QWORD *)v65 + 88LL))(v65);
                CurrentIndexEntry = v105;
                if ( v105 == -1072863856 )
                {
                  v8 = this;
                  *((_DWORD *)this + 147) = v99;
                  goto LABEL_271;
                }
                if ( v105 == 1 )
                {
                  v156 = -1;
                }
                else if ( v105 < 0 )
                {
                  v137 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v138 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v106, v107, v108);
                    CallStackTracing::s_wpInstance = v138;
                    if ( v138
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v138 + 8LL))(
                           v138,
                           2032) )
                    {
                      v137 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v137 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                    }
                  }
                  if ( *((_BYTE *)v137 + 8) )
                  {
                    v139 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v137);
                    if ( *((_DWORD *)v139 + 499) != CurrentIndexEntry )
                      CallStackContext::TraceFailure(v139, "CAVIMediaSourcePlugin::ParseData", 1744, CurrentIndexEntry);
                  }
                  if ( g_wppLevels )
                    WPP_SF_qD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      177,
                      &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
                      v13,
                      CurrentIndexEntry);
                  goto LABEL_285;
                }
                v8 = this;
                v29 = v153;
                continue;
              }
            }
            else
            {
              v8 = this;
            }
            v99 = v150;
            goto LABEL_132;
          }
          v99 = v150;
          goto LABEL_138;
        }
        v140 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v141 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v89, v90, v91);
          CallStackTracing::s_wpInstance = v141;
          if ( v141 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v141 + 8LL))(v141, 2032) )
          {
            v140 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v140 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v140 + 8) )
        {
          v142 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v140);
          if ( *((_DWORD *)v142 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(v142, "CAVIMediaSourcePlugin::ParseData", 1683, CurrentIndexEntry);
        }
        if ( !g_wppLevels )
          goto LABEL_269;
        v112 = 173;
      }
LABEL_268:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v112,
        &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
        v13,
        CurrentIndexEntry);
      goto LABEL_269;
    }
    break;
  }
  CurrentIndexEntry = 1;
  if ( byte_1801B1109 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 166, &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids, v13);
  v146 = a6;
LABEL_276:
  if ( (unsigned __int8)byte_1801B1109 >= 8u )
    WPP_SF_qI(*((_QWORD *)WPP_GLOBAL_Control + 7), 178, &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids, v13, *v146);
LABEL_285:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v152);
  if ( ppIMFSample )
    ((void (__fastcall *)(IMFSample *))ppIMFSample->lpVtbl->Release)(ppIMFSample);
  if ( v157 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v157 + 16LL))(v157);
  return (unsigned int)CurrentIndexEntry;
}

```

## disassembly

```asm
0x180058410  mov     [rsp-8+arg_0], rcx
0x180058415  push    rbp
0x180058416  push    rbx
0x180058417  push    rsi
0x180058418  push    rdi
0x180058419  push    r12
0x18005841b  push    r13
0x18005841d  push    r14
0x18005841f  push    r15
0x180058421  lea     rbp, [rsp-0Fh]
0x180058426  sub     rsp, 88h
0x18005842d  xor     esi, esi
0x18005842f  lea     r15, aCavimediasourc_1; "CAVIMediaSourcePlugin::ParseData"
0x180058436  mov     rdi, r8
0x180058439  mov     [rbp+47h+var_70], esi
0x18005843c  mov     rbx, rdx
0x18005843f  mov     [rbp+47h+var_68], rsi
0x180058443  mov     r13, rcx
0x180058446  mov     [rbp+47h+ppIMFSample], rsi
0x18005844a  mov     rdx, r15; char *
0x18005844d  mov     [rbp+47h+var_50], rsi
0x180058451  mov     r8d, 5D9h; int
0x180058457  mov     [rbp+47h+var_58], esi
0x18005845a  lea     rcx, [rbp+47h+var_80]; this
0x18005845e  mov     [rbp+47h+var_5C], esi
0x180058461  mov     r12d, r9d
0x180058464  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180058469  lea     r14, [r13-10h]
0x18005846d  cmp     [r14+48h], rsi
0x180058471  jz      loc_180059538
0x180058477  mov     rax, [r13+40h]
0x18005847b  cmp     dword ptr [rax+0B4h], 3
0x180058482  jnz     loc_180059538
0x180058488  test    rbx, rbx
0x18005848b  jnz     loc_18005852C
0x180058491  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058498  mov     edi, 80004003h
0x18005849d  mov     ebx, edi
0x18005849f  test    rcx, rcx
0x1800584a2  jnz     short loc_1800584E5
0x1800584a4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800584aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800584b1  mov     rcx, rax
0x1800584b4  test    rax, rax
0x1800584b7  jz      short loc_1800584D7
0x1800584b9  mov     rax, [rax]
0x1800584bc  mov     edx, 7F0h
0x1800584c1  mov     rax, [rax+8]
0x1800584c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800584ca  test    eax, eax
0x1800584cc  jz      short loc_1800584D7
0x1800584ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800584d5  jmp     short loc_1800584E5
0x1800584d7  lea     rcx, qword_1801B07E0; this
0x1800584de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800584e5  cmp     [rcx+8], sil
0x1800584e9  jz      short loc_18005850C
0x1800584eb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800584f0  cmp     [rax+7CCh], edi
0x1800584f6  jz      short loc_18005850C
0x1800584f8  mov     r9d, edi; int
0x1800584fb  mov     r8d, 5E0h; int
0x180058501  mov     rdx, r15; char *
0x180058504  mov     rcx, rax; this
0x180058507  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005850c  mov     esi, 1
0x180058511  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180058518  jb      loc_1800595AD
0x18005851e  mov     edx, 9Bh
0x180058523  mov     dword ptr [rsp+0C0h+var_A0], edi
0x180058527  jmp     loc_180059593
0x18005852c  mov     rsi, [rbp+47h+arg_28]
0x180058530  test    rsi, rsi
0x180058533  jnz     loc_1800585D0
0x180058539  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058540  mov     edi, 80004003h
0x180058545  mov     ebx, edi
0x180058547  test    rcx, rcx
0x18005854a  jnz     short loc_18005858D
0x18005854c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180058552  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180058559  mov     rcx, rax
0x18005855c  test    rax, rax
0x18005855f  jz      short loc_18005857F
0x180058561  mov     rax, [rax]
0x180058564  mov     edx, 7F0h
0x180058569  mov     rax, [rax+8]
0x18005856d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058572  test    eax, eax
0x180058574  jz      short loc_18005857F
0x180058576  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005857d  jmp     short loc_18005858D
0x18005857f  lea     rcx, qword_1801B07E0; this
0x180058586  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005858d  cmp     byte ptr [rcx+8], 0
0x180058591  jz      short loc_1800585B4
0x180058593  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180058598  cmp     [rax+7CCh], edi
0x18005859e  jz      short loc_1800585B4
0x1800585a0  mov     r9d, edi; int
0x1800585a3  mov     r8d, 5E1h; int
0x1800585a9  mov     rdx, r15; char *
0x1800585ac  mov     rcx, rax; this
0x1800585af  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800585b4  mov     esi, 1
0x1800585b9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800585c0  jb      loc_1800595AD
0x1800585c6  mov     edx, 9Ch
0x1800585cb  jmp     loc_180058523
0x1800585d0  lea     rcx, [r13+48h]; this
0x1800585d4  mov     r8, rbx; struct IMFMediaBuffer *
0x1800585d7  mov     rdx, rdi; unsigned __int64
0x1800585da  call    ?AddBuffer@CSourcePluginBufferReader@@QEAAJ_KPEAUIMFMediaBuffer@@@Z; CSourcePluginBufferReader::AddBuffer(unsigned __int64,IMFMediaBuffer *)
0x1800585df  lea     r15, WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids
0x1800585e6  mov     ebx, eax
0x1800585e8  test    eax, eax
0x1800585ea  jns     loc_18005869E
0x1800585f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800585f7  test    rcx, rcx
0x1800585fa  jnz     short loc_18005863D
0x1800585fc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180058602  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180058609  mov     rcx, rax
0x18005860c  test    rax, rax
0x18005860f  jz      short loc_18005862F
0x180058611  mov     rax, [rax]
0x180058614  mov     edx, 7F0h
0x180058619  mov     rax, [rax+8]
0x18005861d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058622  test    eax, eax
0x180058624  jz      short loc_18005862F
0x180058626  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005862d  jmp     short loc_18005863D
0x18005862f  lea     rcx, qword_1801B07E0; this
0x180058636  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005863d  cmp     byte ptr [rcx+8], 0
0x180058641  jz      short loc_180058668
0x180058643  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180058648  cmp     [rax+7CCh], ebx
0x18005864e  jz      short loc_180058668
0x180058650  mov     r9d, ebx; int
0x180058653  lea     rdx, aCavimediasourc_1; "CAVIMediaSourcePlugin::ParseData"
0x18005865a  mov     r8d, 5E3h; int
0x180058660  mov     rcx, rax; this
0x180058663  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180058668  mov     esi, 1
0x18005866d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180058674  jb      loc_1800594B9
0x18005867a  mov     edx, 9Dh
0x18005867f  mov     rcx, cs:WPP_GLOBAL_Control
0x180058686  mov     r9, r14
0x180058689  mov     r8, r15
0x18005868c  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180058690  mov     rcx, [rcx+10h]
0x180058694  call    WPP_SF_qD
0x180058699  jmp     loc_1800594B9
0x18005869e  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1800586a5  mov     esi, 1
0x1800586aa  mov     rax, [r14+50h]
0x1800586ae  mov     r9d, [rax+70h]
0x1800586b2  mov     eax, [r13+24Ch]
0x1800586b9  mov     [rbp+47h+var_7C], r9d
0x1800586bd  cmp     eax, 0FFFFFFFFh
0x1800586c0  jz      short loc_180058719
0x1800586c2  mov     edx, eax
0x1800586c4  mov     rax, [r13+40h]
0x1800586c8  mov     rcx, [rax+68h]
0x1800586cc  mov     rcx, [rcx+rdx*8]
0x1800586d0  mov     rax, [rcx]
0x1800586d3  mov     rax, [rax+58h]
0x1800586d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800586dc  mov     ebx, eax
0x1800586de  cmp     eax, esi
0x1800586e0  jnz     loc_18005878D
0x1800586e6  cmp     cs:byte_1801B1109, 20h ; ' '
0x1800586ed  jb      short loc_180058715
0x1800586ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800586f6  mov     edx, 9Eh
0x1800586fb  mov     eax, [r14+25Ch]
0x180058702  mov     r9, r14
0x180058705  mov     r8, r15
0x180058708  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18005870c  mov     rcx, [rcx+38h]
0x180058710  call    WPP_SF_qD
0x180058715  mov     r9d, [rbp+47h+var_7C]
0x180058719  or      r8d, 0FFFFFFFFh
0x18005871d  cmp     dword ptr [r13+258h], 0
0x180058725  mov     [rbp+47h+var_6C], r8d
0x180058729  jnz     loc_180058873
0x18005872f  mov     rdi, [rbp+47h+arg_20]
0x180058733  xor     ebx, ebx
0x180058735  cmp     ebx, r12d
0x180058738  jnb     loc_180058873
0x18005873e  cmp     r12d, r9d
0x180058741  jnz     loc_180058873
0x180058747  cmp     cs:byte_1801B1109, 20h ; ' '
0x18005874e  jb      short loc_18005877E
0x180058750  mov     eax, [rdi+rbx*8+4]
0x180058754  mov     edx, 0A0h
0x180058759  mov     rcx, cs:WPP_GLOBAL_Control
0x180058760  mov     r9, r14
0x180058763  mov     dword ptr [rsp+0C0h+var_98], eax
0x180058767  mov     r8, r15
0x18005876a  mov     eax, [rdi+rbx*8]
0x18005876d  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180058771  mov     rcx, [rcx+38h]
0x180058775  call    WPP_SF_qDD
0x18005877a  mov     r9d, [rbp+47h+var_7C]
0x18005877e  cmp     dword ptr [rdi+rbx*8+4], 0
0x180058783  jz      loc_180058830
0x180058789  add     ebx, esi
0x18005878b  jmp     short loc_180058735
0x18005878d  test    ebx, ebx
0x18005878f  js      short loc_1800587A1
0x180058791  mov     dword ptr [r13+24Ch], 0FFFFFFFFh
0x18005879c  jmp     loc_180058715
0x1800587a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800587a8  test    rcx, rcx
0x1800587ab  jnz     short loc_1800587EE
0x1800587ad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800587b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800587ba  mov     rcx, rax
0x1800587bd  test    rax, rax
0x1800587c0  jz      short loc_1800587E0
0x1800587c2  mov     rax, [rax]
0x1800587c5  mov     edx, 7F0h
0x1800587ca  mov     rax, [rax+8]
0x1800587ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800587d3  test    eax, eax
0x1800587d5  jz      short loc_1800587E0
0x1800587d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800587de  jmp     short loc_1800587EE
0x1800587e0  lea     rcx, qword_1801B07E0; this
0x1800587e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800587ee  cmp     byte ptr [rcx+8], 0
0x1800587f2  jz      short loc_180058819
0x1800587f4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800587f9  cmp     [rax+7CCh], ebx
0x1800587ff  jz      short loc_180058819
0x180058801  mov     r9d, ebx; int
0x180058804  lea     rdx, aCavimediasourc_1; "CAVIMediaSourcePlugin::ParseData"
0x18005880b  mov     r8d, 5FDh; int
0x180058811  mov     rcx, rax; this
0x180058814  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180058819  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180058820  jb      loc_1800594B9
0x180058826  mov     edx, 9Fh
0x18005882b  jmp     loc_18005867F
0x180058830  xor     edx, edx
0x180058832  cmp     edx, r12d
0x180058835  jnb     short loc_180058873
0x180058837  lea     r8, ds:0[rdx*8]
0x18005883f  cmp     edx, r9d
0x180058842  jnb     short loc_18005885A
0x180058844  mov     rax, [r13+40h]
0x180058848  mov     rcx, [rax+68h]
0x18005884c  mov     rax, [rcx+r8]
0x180058850  xor     ecx, ecx
0x180058852  cmp     [rax+50h], ecx
0x180058855  setnz   cl
0x180058858  jmp     short loc_18005885C
0x18005885a  xor     ecx, ecx
0x18005885c  cmp     dword ptr [r8+rdi+4], 0
0x180058862  jz      short loc_180058868
0x180058864  test    ecx, ecx
0x180058866  jz      short loc_18005886C
0x180058868  add     edx, esi
0x18005886a  jmp     short loc_180058832
0x18005886c  mov     eax, [r8+rdi]
0x180058870  mov     [rbp+47h+var_6C], eax
0x180058873  mov     rax, [r13+40h]
0x180058877  or      edx, 0FFFFFFFFh
0x18005887a  xor     edi, edi
0x18005887c  mov     [rbp+47h+var_60], 0FFFFFFFFh
0x180058883  mov     [rbp+47h+var_90], edx
0x180058886  mov     ecx, [rax+0A0h]
0x18005888c  neg     ecx
0x18005888e  sbb     rax, rax
0x180058891  mov     [rbp+47h+var_88], rax
0x180058895  cmp     edi, r9d
0x180058898  jnb     loc_180058A95
0x18005889e  mov     rcx, [rbp+47h+var_68]
0x1800588a2  test    rcx, rcx
0x1800588a5  jz      short loc_1800588BB
0x1800588a7  mov     rax, [rcx]
0x1800588aa  mov     rax, [rax+10h]
0x1800588ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800588b3  mov     [rbp+47h+var_68], 0
0x1800588bb  mov     rcx, [rbp+47h+ppIMFSample]
0x1800588bf  test    rcx, rcx
0x1800588c2  jz      short loc_1800588D8
0x1800588c4  mov     rax, [rcx]
0x1800588c7  mov     rax, [rax+10h]
0x1800588cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800588d0  mov     [rbp+47h+ppIMFSample], 0
0x1800588d8  mov     rax, [r13+40h]
0x1800588dc  mov     rcx, [rax+68h]
0x1800588e0  mov     rbx, [rcx+rdi*8]
0x1800588e4  mov     rcx, rbx
0x1800588e7  mov     rax, [rbx]
  ... truncated ...
```
