# CAVIMediaSourcePlugin::ParseData(IMFMediaBuffer *,unsigned __int64,ulong,_MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE *,unsigned __int64 *)

- ea: `0x180058410`
- end: `0x1800595f6`
- name: `?ParseData@CAVIMediaSourcePlugin@@UEAAJPEAUIMFMediaBuffer@@_KKPEAU_MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE@@PEA_K@Z`
- size: `4582`
- prototype: `__int64 __fastcall(CAVIMediaSourcePlugin *this, struct IMFMediaBuffer *, unsigned __int64, unsigned int, struct _MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE *, unsigned __int64 *)`
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
  char *v11; // r14
  wchar_t *v12; // rcx
  HRESULT CurrentIndexEntry; // ebx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  unsigned int v25; // r9d
  unsigned int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rdx
  bool v29; // zf
  __int64 i; // rbx
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 j; // rdx
  __int64 v35; // r8
  BOOL v36; // ecx
  __int64 v37; // rax
  unsigned int v38; // edx
  __int64 v39; // rdi
  CAVIIAVSStreamParser *v40; // rbx
  unsigned int NumberOfStreams; // r13d
  unsigned int k; // r12d
  __int64 v43; // rdx
  __int64 v44; // rdx
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  __int64 v47; // rdx
  CAVIStreamParser *v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // r13
  CAVIStreamParser *v51; // r12
  __int64 v52; // rdx
  IMFSample *v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // rdx
  __int64 v56; // rdx
  IMFSample *v57; // rdi
  HRESULT (__stdcall *SetSampleTime)(IMFSample *, LONGLONG); // rbx
  __int64 v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rdx
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rbx
  __int64 v65; // rax
  __int64 v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // rax
  __int64 v70; // rcx
  int v71; // edi
  __int64 v72; // rdx
  wchar_t *v73; // rcx
  CallStackTracing *v74; // rax
  int v75; // eax
  __int64 v76; // rdx
  wchar_t *v77; // rcx
  CallStackTracing *v78; // rax
  struct CallStackContext *v79; // rax
  __int64 v80; // rdx
  wchar_t *v81; // rcx
  CallStackTracing *v82; // rax
  struct CallStackContext *v83; // rax
  wchar_t *v84; // rcx
  CallStackTracing *v85; // rax
  struct CallStackContext *v86; // rax
  struct CallStackContext *v87; // rax
  wchar_t *v88; // rcx
  CallStackTracing *v89; // rax
  struct CallStackContext *v90; // rax
  __int64 v91; // rdx
  wchar_t *v92; // rcx
  CallStackTracing *v93; // rax
  struct CallStackContext *v94; // rax
  wchar_t *v95; // rcx
  CallStackTracing *v96; // rax
  struct CallStackContext *v97; // rax
  wchar_t *v98; // rcx
  CallStackTracing *v99; // rax
  struct CallStackContext *v100; // rax
  wchar_t *v101; // rcx
  CallStackTracing *v102; // rax
  struct CallStackContext *v103; // rax
  struct CallStackContext *v104; // rax
  wchar_t *v105; // rcx
  CallStackTracing *v106; // rax
  struct CallStackContext *v107; // rax
  wchar_t *v108; // rcx
  CallStackTracing *v109; // rax
  struct CallStackContext *v110; // rax
  wchar_t *v111; // rcx
  CallStackTracing *v112; // rax
  struct CallStackContext *v113; // rax
  unsigned __int64 *v114; // rcx
  CallStackTracing *v115; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  int v118; // [rsp+30h] [rbp-49h]
  unsigned __int64 v119; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v120[4]; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v121; // [rsp+44h] [rbp-35h]
  IMFSample *ppIMFSample; // [rsp+48h] [rbp-31h] BYREF
  int v123; // [rsp+50h] [rbp-29h] BYREF
  int v124; // [rsp+54h] [rbp-25h]
  __int64 v125; // [rsp+58h] [rbp-21h] BYREF
  int v126; // [rsp+60h] [rbp-19h] BYREF
  int v127; // [rsp+64h] [rbp-15h] BYREF
  unsigned int v128; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int64 v129; // [rsp+70h] [rbp-9h] BYREF
  _QWORD v130[9]; // [rsp+78h] [rbp-1h] BYREF

  v123 = 0;
  v125 = 0;
  v8 = this;
  ppIMFSample = 0;
  v129 = 0;
  v128 = 0;
  v127 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v120, "CAVIMediaSourcePlugin::ParseData", 1497);
  v11 = (char *)v8 - 16;
  if ( !*((_QWORD *)v8 + 7) || *(_DWORD *)(*((_QWORD *)v8 + 8) + 180LL) != 3 )
  {
    v115 = CallStackTracing::s_wpInstance;
    CurrentIndexEntry = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v115 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v115 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v115);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875854 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIMediaSourcePlugin::ParseData", 1501, -1072875854);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        154,
        &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
        v11,
        -1072875854);
    goto LABEL_285;
  }
  if ( !a2 )
  {
    v12 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentIndexEntry = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v12 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v15 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v15, "CAVIMediaSourcePlugin::ParseData", 1504, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_285;
    v16 = 155;
    goto LABEL_14;
  }
  if ( !a6 )
  {
    v17 = (wchar_t *)CallStackTracing::s_wpInstance;
    CurrentIndexEntry = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v17 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v17 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v17 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
      if ( *((_DWORD *)v19 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v19, "CAVIMediaSourcePlugin::ParseData", 1505, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_285;
    v16 = 156;
LABEL_14:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
      v11,
      -2147467261);
    goto LABEL_285;
  }
  CurrentIndexEntry = CSourcePluginBufferReader::AddBuffer((CAVIMediaSourcePlugin *)((char *)v8 + 72), a3, a2);
  if ( CurrentIndexEntry < 0 )
  {
    v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
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
      if ( *((_DWORD *)v23 + 499) != CurrentIndexEntry )
        CallStackContext::TraceFailure(v23, "CAVIMediaSourcePlugin::ParseData", 1507, CurrentIndexEntry);
    }
    if ( !g_wppLevels )
      goto LABEL_270;
    v24 = 157;
    goto LABEL_37;
  }
  *a6 = -1;
  v25 = *(_DWORD *)(*((_QWORD *)v11 + 10) + 112LL);
  v26 = *((_DWORD *)v8 + 147);
  v121 = v25;
  if ( v26 != -1 )
  {
    v27 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 8) + 104LL) + 8LL * v26);
    CurrentIndexEntry = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 88LL))(v27);
    if ( CurrentIndexEntry == 1 )
    {
      if ( (unsigned __int8)byte_1801B1109 >= 0x20u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          158,
          &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
          (char *)v8 - 16,
          *((_DWORD *)v11 + 151));
    }
    else
    {
      if ( CurrentIndexEntry < 0 )
      {
        v31 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
          CallStackTracing::s_wpInstance = v32;
          if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
          {
            v31 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v31 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v31 + 8) )
        {
          v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
          if ( *((_DWORD *)v33 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(v33, "CAVIMediaSourcePlugin::ParseData", 1533, CurrentIndexEntry);
        }
        if ( !g_wppLevels )
          goto LABEL_270;
        v24 = 159;
LABEL_37:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v24,
          &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
          v11,
          CurrentIndexEntry);
        goto LABEL_270;
      }
      *((_DWORD *)v8 + 147) = -1;
    }
    v25 = v121;
  }
  v29 = *((_DWORD *)v8 + 150) == 0;
  v124 = -1;
  if ( v29 )
  {
    for ( i = 0; (unsigned int)i < a4 && a4 == v25; i = (unsigned int)(i + 1) )
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
        v25 = v121;
      }
      if ( !*((_DWORD *)a5 + 2 * i + 1) )
      {
        for ( j = 0; (unsigned int)j < a4; j = (unsigned int)(j + 1) )
        {
          v35 = 8 * j;
          v36 = (unsigned int)j < v25
             && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 8) + 104LL) + 8 * j) + 80LL) != 0;
          if ( *(_DWORD *)((char *)a5 + v35 + 4) && !v36 )
          {
            v124 = *(_DWORD *)((char *)a5 + v35);
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
    v37 = *((_QWORD *)v8 + 8);
    v38 = -1;
    v39 = 0;
    v126 = -1;
    v118 = -1;
    v119 = -(__int64)(*(_DWORD *)(v37 + 160) != 0);
    while ( (unsigned int)v39 < v25 )
    {
      if ( v125 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v125 + 16LL))(v125);
        v125 = 0;
      }
      if ( ppIMFSample )
      {
        ((void (__fastcall *)(IMFSample *))ppIMFSample->lpVtbl->Release)(ppIMFSample);
        ppIMFSample = 0;
      }
      v40 = *(CAVIIAVSStreamParser **)(*(_QWORD *)(*((_QWORD *)v8 + 8) + 104LL) + 8 * v39);
      if ( (*(unsigned int (__fastcall **)(CAVIIAVSStreamParser *))(*(_QWORD *)v40 + 8LL))(v40) )
      {
        NumberOfStreams = CAVIIAVSStreamParser::GetNumberOfStreams(v40);
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
                                &v123,
                                &v125);
          if ( CurrentIndexEntry < 0 )
            break;
          if ( v123 )
            goto LABEL_91;
          ComSmartPtr<IUnknown>::Release(&v125);
        }
        v77 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43);
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
            CallStackContext::TraceFailure(v79, "CAVIMediaSourcePlugin::ParseData", 1611, CurrentIndexEntry);
        }
        if ( g_wppLevels )
        {
          v80 = 161;
          goto LABEL_268;
        }
LABEL_269:
        v8 = this;
LABEL_270:
        if ( CurrentIndexEntry == -1072863856 )
        {
LABEL_271:
          v114 = a6;
          CurrentIndexEntry = 0;
          *a6 = *((_QWORD *)v8 + 69);
          goto LABEL_276;
        }
        goto LABEL_285;
      }
      CurrentIndexEntry = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, __int64 *))(**((_QWORD **)v8 + 7) + 272LL))(
                            *((_QWORD *)v8 + 7),
                            (unsigned int)v39,
                            &v123,
                            &v125);
      if ( CurrentIndexEntry < 0 )
      {
        v45 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
          CallStackTracing::s_wpInstance = v46;
          if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
          {
            v45 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v45 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v45 + 8) )
        {
          v87 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
          if ( *((_DWORD *)v87 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(v87, "CAVIMediaSourcePlugin::ParseData", 1621, CurrentIndexEntry);
        }
        if ( !g_wppLevels )
          goto LABEL_270;
        v24 = 162;
        goto LABEL_37;
      }
LABEL_90:
      if ( !v123 )
        goto LABEL_97;
LABEL_91:
      CurrentIndexEntry = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v125 + 264LL))(v125, &v126);
      if ( CurrentIndexEntry < 0 )
      {
        v84 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v85 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47);
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
          if ( *((_DWORD *)v86 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(v86, "CAVIMediaSourcePlugin::ParseData", 1628, CurrentIndexEntry);
        }
        if ( !g_wppLevels )
          goto LABEL_269;
        v80 = 163;
        goto LABEL_268;
      }
      if ( v124 != -1 && v124 != v126 )
      {
        if ( (unsigned __int8)byte_1801B1109 >= 0x20u )
          WPP_SF_qDD(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            164,
            &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
            v11,
            v39,
            v126);
        v8 = this;
LABEL_97:
        v38 = v118;
        goto LABEL_98;
      }
      v8 = this;
      v48 = *(CAVIStreamParser **)(*(_QWORD *)(*((_QWORD *)this + 8) + 104LL) + 8 * v39);
      if ( *((_DWORD *)v48 + 20) )
        goto LABEL_97;
      CurrentIndexEntry = CAVIStreamParser::GetCurrentIndexEntry(v48, &v129, &v128);
      if ( CurrentIndexEntry < 0 )
      {
        v81 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v82 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49);
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
          if ( *((_DWORD *)v83 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(v83, "CAVIMediaSourcePlugin::ParseData", 1641, CurrentIndexEntry);
        }
        if ( !g_wppLevels )
          goto LABEL_270;
        v24 = 165;
        goto LABEL_37;
      }
      if ( *(_DWORD *)(*((_QWORD *)v11 + 10) + 160LL) )
      {
        if ( v119 <= v129 )
          goto LABEL_97;
      }
      else if ( v119 >= v129 )
      {
        goto LABEL_97;
      }
      v38 = v39;
      v119 = v129;
      v118 = v39;
LABEL_98:
      v25 = v121;
      v39 = (unsigned int)(v39 + 1);
    }
    if ( v38 != -1 )
    {
      v50 = v38;
      v51 = *(CAVIStreamParser **)(*(_QWORD *)(*((_QWORD *)this + 8) + 104LL) + 8LL * v38);
      CurrentIndexEntry = CAVIStreamParser::IsNextSamplesFormatDifferent(v51, &v127);
      if ( CurrentIndexEntry < 0 )
      {
        v111 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v112 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52);
          CallStackTracing::s_wpInstance = v112;
          if ( v112 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v112 + 8LL))(v112, 2032) )
          {
            v111 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v111 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v111 + 8) )
        {
          v113 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v111);
          if ( *((_DWORD *)v113 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(v113, "CAVIMediaSourcePlugin::ParseData", 1664, CurrentIndexEntry);
        }
        if ( !g_wppLevels )
          goto LABEL_269;
        v80 = 167;
      }
      else
      {
        v53 = ppIMFSample;
        if ( ppIMFSample )
        {
          ppIMFSample = 0;
          ((void (__fastcall *)(IMFSample *))v53->lpVtbl->Release)(v53);
        }
        if ( v127 )
        {
          v119 = 0;
          CurrentIndexEntry = CAVIStreamParser::UpdateCurrentFormat(v51);
          if ( CurrentIndexEntry < 0 )
          {
            v101 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v102 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54);
              CallStackTracing::s_wpInstance = v102;
              if ( v102
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v102 + 8LL))(v102, 2032) )
              {
                v101 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v101 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v101 + 8) )
            {
              v103 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v101);
              if ( *((_DWORD *)v103 + 499) != CurrentIndexEntry )
                CallStackContext::TraceFailure(v103, "CAVIMediaSourcePlugin::ParseData", 1672, CurrentIndexEntry);
            }
            if ( !g_wppLevels )
              goto LABEL_190;
            v91 = 168;
          }
          else
          {
            CurrentIndexEntry = (*(__int64 (__fastcall **)(CAVIStreamParser *, unsigned __int64 *))(*(_QWORD *)v51 + 48LL))(
                                  v51,
                                  &v119);
            if ( CurrentIndexEntry < 0 )
            {
              v98 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v99 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55);
                CallStackTracing::s_wpInstance = v99;
                if ( v99
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v99 + 8LL))(v99, 2032) )
                {
                  v98 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v98 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v98 + 8) )
              {
                v100 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v98);
                if ( *((_DWORD *)v100 + 499) != CurrentIndexEntry )
                  CallStackContext::TraceFailure(v100, "CAVIMediaSourcePlugin::ParseData", 1673, CurrentIndexEntry);
              }
              if ( !g_wppLevels )
                goto LABEL_190;
              v91 = 169;
            }
            else
            {
              CurrentIndexEntry = MFCreateSample(&ppIMFSample);
              if ( CurrentIndexEntry < 0 )
              {
                v95 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v96 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56);
                  CallStackTracing::s_wpInstance = v96;
                  if ( v96
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v96 + 8LL))(v96, 2032) )
                  {
                    v95 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v95 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v95 + 8) )
                {
                  v97 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v95);
                  if ( *((_DWORD *)v97 + 499) != CurrentIndexEntry )
                    CallStackContext::TraceFailure(v97, "CAVIMediaSourcePlugin::ParseData", 1676, CurrentIndexEntry);
                }
                if ( !g_wppLevels )
                  goto LABEL_190;
                v91 = 170;
              }
              else
              {
                v57 = ppIMFSample;
                SetSampleTime = ppIMFSample->lpVtbl->SetSampleTime;
                v59 = (*(__int64 (__fastcall **)(CAVIStreamParser *))(*(_QWORD *)v51 + 96LL))(v51);
                CurrentIndexEntry = ((__int64 (__fastcall *)(IMFSample *, __int64))SetSampleTime)(v57, v59);
                if ( CurrentIndexEntry >= 0 )
                {
                  CurrentIndexEntry = ((__int64 (__fastcall *)(IMFSample *, __int64 *, unsigned __int64))ppIMFSample->lpVtbl->SetUnknown)(
                                        ppIMFSample,
                                        AVI_SAMPLE_ATTRIBUTE_FORMATCHANGE_MEDIATYPE,
                                        v119);
                  if ( CurrentIndexEntry >= 0 )
                  {
                    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v119);
                    goto LABEL_118;
                  }
                  v88 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v89 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v61);
                    CallStackTracing::s_wpInstance = v89;
                    if ( v89
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v89 + 8LL))(v89, 2032) )
                    {
                      v88 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v88 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                    }
                  }
                  if ( *((_BYTE *)v88 + 8) )
                  {
                    v90 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v88);
                    if ( *((_DWORD *)v90 + 499) != CurrentIndexEntry )
                      CallStackContext::TraceFailure(v90, "CAVIMediaSourcePlugin::ParseData", 1678, CurrentIndexEntry);
                  }
                  if ( g_wppLevels )
                  {
                    v91 = 172;
                    goto LABEL_189;
                  }
LABEL_190:
                  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v119);
                  goto LABEL_269;
                }
                v92 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v93 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v60);
                  CallStackTracing::s_wpInstance = v93;
                  if ( v93
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v93 + 8LL))(v93, 2032) )
                  {
                    v92 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v92 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v92 + 8) )
                {
                  v94 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v92);
                  if ( *((_DWORD *)v94 + 499) != CurrentIndexEntry )
                    CallStackContext::TraceFailure(v94, "CAVIMediaSourcePlugin::ParseData", 1677, CurrentIndexEntry);
                }
                if ( !g_wppLevels )
                  goto LABEL_190;
                v91 = 171;
              }
            }
          }
LABEL_189:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v91,
            &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
            v11,
            CurrentIndexEntry);
          goto LABEL_190;
        }
        v62 = *(_QWORD *)v51;
        LODWORD(v119) = 0;
        CurrentIndexEntry = (*(__int64 (__fastcall **)(CAVIStreamParser *, IMFSample **, unsigned __int64 *))(v62 + 72))(
                              v51,
                              &ppIMFSample,
                              &v119);
        if ( CurrentIndexEntry >= 0 )
        {
LABEL_118:
          if ( ppIMFSample )
          {
            if ( *((_QWORD *)v11 + 84) )
            {
              v64 = 3 * v50;
              v8 = this;
              v65 = *((_QWORD *)this + 82);
              if ( *(_QWORD *)(v65 + 8 * v64) && !*(_DWORD *)(v65 + 8 * v64 + 16) )
              {
                v119 = 0;
                v130[0] = 0;
                ((void (__fastcall *)(IMFSample *, unsigned __int64 *))ppIMFSample->lpVtbl->GetSampleTime)(
                  ppIMFSample,
                  &v119);
                v66 = *(_QWORD *)(*((_QWORD *)this + 82) + 8 * v64);
                (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v66 + 280LL))(v66, v130);
                v69 = *((_QWORD *)this + 82);
                if ( v119 == v130[0] )
                {
                  v70 = *(_QWORD *)(v69 + 8 * v64);
                  if ( v70 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
                    *(_QWORD *)(*((_QWORD *)this + 82) + 8 * v64) = 0;
                  }
                  v71 = v118;
                  if ( (unsigned __int8)byte_1801B1109 >= 8u )
                    WPP_SF_qD(
                      *((_QWORD *)WPP_GLOBAL_Control + 7),
                      174,
                      &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
                      v11,
                      v118);
                }
                else
                {
                  *(_QWORD *)(v69 + 8 * v64 + 8) = v119;
                  v71 = v118;
                  if ( (unsigned __int8)byte_1801B1109 >= 8u )
                    WPP_SF_qdI(
                      *((_QWORD *)WPP_GLOBAL_Control + 7),
                      v67,
                      v68,
                      v11,
                      v118,
                      *(_QWORD *)(*((_QWORD *)this + 82) + 8 * v64 + 8));
                  *(_DWORD *)(*((_QWORD *)this + 82) + 8 * v64 + 16) = 1;
                }
LABEL_132:
                CurrentIndexEntry = (*(__int64 (__fastcall **)(CAVIStreamParser *, IMFSample *))(*(_QWORD *)v51 + 16LL))(
                                      v51,
                                      ppIMFSample);
                if ( CurrentIndexEntry < 0 )
                {
                  v73 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v72);
                    CallStackTracing::s_wpInstance = v74;
                    if ( v74
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(v74, 2032) )
                    {
                      v73 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v73 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                    }
                  }
                  if ( *((_BYTE *)v73 + 8) )
                  {
                    v104 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v73);
                    if ( *((_DWORD *)v104 + 499) != CurrentIndexEntry )
                      CallStackContext::TraceFailure(v104, "CAVIMediaSourcePlugin::ParseData", 1723, CurrentIndexEntry);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_270;
                  v24 = 176;
                  goto LABEL_37;
                }
LABEL_138:
                v75 = (*(__int64 (__fastcall **)(CAVIStreamParser *))(*(_QWORD *)v51 + 88LL))(v51);
                CurrentIndexEntry = v75;
                if ( v75 == -1072863856 )
                {
                  v8 = this;
                  *((_DWORD *)this + 147) = v71;
                  goto LABEL_271;
                }
                if ( v75 == 1 )
                {
                  v124 = -1;
                }
                else if ( v75 < 0 )
                {
                  v105 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v106 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v76);
                    CallStackTracing::s_wpInstance = v106;
                    if ( v106
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v106 + 8LL))(
                           v106,
                           2032) )
                    {
                      v105 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v105 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                    }
                  }
                  if ( *((_BYTE *)v105 + 8) )
                  {
                    v107 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v105);
                    if ( *((_DWORD *)v107 + 499) != CurrentIndexEntry )
                      CallStackContext::TraceFailure(v107, "CAVIMediaSourcePlugin::ParseData", 1744, CurrentIndexEntry);
                  }
                  if ( g_wppLevels )
                    WPP_SF_qD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      177,
                      &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
                      v11,
                      CurrentIndexEntry);
                  goto LABEL_285;
                }
                v8 = this;
                v25 = v121;
                continue;
              }
            }
            else
            {
              v8 = this;
            }
            v71 = v118;
            goto LABEL_132;
          }
          v71 = v118;
          goto LABEL_138;
        }
        v108 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v109 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v63);
          CallStackTracing::s_wpInstance = v109;
          if ( v109 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v109 + 8LL))(v109, 2032) )
          {
            v108 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v108 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v108 + 8) )
        {
          v110 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v108);
          if ( *((_DWORD *)v110 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(v110, "CAVIMediaSourcePlugin::ParseData", 1683, CurrentIndexEntry);
        }
        if ( !g_wppLevels )
          goto LABEL_269;
        v80 = 173;
      }
LABEL_268:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v80,
        &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
        v11,
        CurrentIndexEntry);
      goto LABEL_269;
    }
    break;
  }
  CurrentIndexEntry = 1;
  if ( byte_1801B1109 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 166, &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids, v11);
  v114 = a6;
LABEL_276:
  if ( (unsigned __int8)byte_1801B1109 >= 8u )
    WPP_SF_qI(*((_QWORD *)WPP_GLOBAL_Control + 7), 178, &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids, v11, *v114);
LABEL_285:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v120);
  if ( ppIMFSample )
    ((void (__fastcall *)(IMFSample *))ppIMFSample->lpVtbl->Release)(ppIMFSample);
  if ( v125 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v125 + 16LL))(v125);
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
