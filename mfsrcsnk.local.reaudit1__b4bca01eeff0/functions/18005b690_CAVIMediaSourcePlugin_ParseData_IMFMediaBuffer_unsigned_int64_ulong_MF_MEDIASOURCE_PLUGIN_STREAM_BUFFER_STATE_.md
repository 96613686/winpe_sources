# CAVIMediaSourcePlugin::ParseData(IMFMediaBuffer *,unsigned __int64,ulong,_MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE *,unsigned __int64 *)

- ea: `0x18005b690`
- end: `0x18005c8e3`
- name: `?ParseData@CAVIMediaSourcePlugin@@UEAAJPEAUIMFMediaBuffer@@_KKPEAU_MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE@@PEA_K@Z`
- size: `4691`
- prototype: `int(CAVIMediaSourcePlugin *__hidden this, struct IMFMediaBuffer *, unsigned __int64, unsigned int, struct _MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180005cf4`
- `0x180008890`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x1800476a0`
- `0x18005b030`
- `0x18005b690`
- `0x18005c8ec`
- `0x18005e2e4`
- `0x180077708`
- `0x180079680`
- `0x18007a0e4`
- `0x180121750`
- `0x18013fe10`
- `0x180140e04`
- `0x180148844`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b724`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b7d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b888`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ba3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005bc1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005bfce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c05f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c0f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c189`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c26e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c322`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c3b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c44c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c4e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c5c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c672`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c707`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b724`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b7d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b888`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ba3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005bc1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005bfce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c05f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c0f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c189`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c26e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c322`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c3b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c44c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c4e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c5c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c672`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005c707`
- `MFPlat!MFCreateSample` at `0x18005bdc8`
- `MFPlat!MFCreateSample` at `0x18005bdc8`

## string_xrefs

- `0x18005b6af`: `CAVIMediaSourcePlugin::ParseData`
- `0x18005b8e5`: `CAVIMediaSourcePlugin::ParseData`
- `0x18005ba9c`: `CAVIMediaSourcePlugin::ParseData`
- `0x18005c0bc`: `CAVIMediaSourcePlugin::ParseData`
- `0x18005c151`: `CAVIMediaSourcePlugin::ParseData`
- `0x18005c1e6`: `CAVIMediaSourcePlugin::ParseData`
- `0x18005c236`: `CAVIMediaSourcePlugin::ParseData`
- `0x18005c2cb`: `CAVIMediaSourcePlugin::ParseData`
- `0x18005c37f`: `CAVIMediaSourcePlugin::ParseData`
- `0x18005c414`: `CAVIMediaSourcePlugin::ParseData`
- `0x18005c4a9`: `CAVIMediaSourcePlugin::ParseData`
- `0x18005c53e`: `CAVIMediaSourcePlugin::ParseData`
- `0x18005c58e`: `CAVIMediaSourcePlugin::ParseData`
- `0x18005c623`: `CAVIMediaSourcePlugin::ParseData`
- `0x18005c6cf`: `CAVIMediaSourcePlugin::ParseData`
- `0x18005c764`: `CAVIMediaSourcePlugin::ParseData`

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
        v12 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v17 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v21 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      if ( (unsigned __int8)byte_1801BA109 >= 0x20u )
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
            v31 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      if ( (unsigned __int8)byte_1801BA109 >= 0x20u )
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
            v77 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v45 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v84 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        if ( (unsigned __int8)byte_1801BA109 >= 0x20u )
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
            v81 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v111 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v101 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                  v98 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                    v95 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                      v88 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                    v92 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                  if ( (unsigned __int8)byte_1801BA109 >= 8u )
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
                  if ( (unsigned __int8)byte_1801BA109 >= 8u )
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
                      v73 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                      v105 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v108 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  if ( byte_1801BA109 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 166, &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids, v11);
  v114 = a6;
LABEL_276:
  if ( (unsigned __int8)byte_1801BA109 >= 8u )
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
0x18005b690  mov     [rsp-8+arg_0], rcx
0x18005b695  push    rbp
0x18005b696  push    rbx
0x18005b697  push    rsi
0x18005b698  push    rdi
0x18005b699  push    r12
0x18005b69b  push    r13
0x18005b69d  push    r14
0x18005b69f  push    r15
0x18005b6a1  lea     rbp, [rsp-0Fh]
0x18005b6a6  sub     rsp, 88h
0x18005b6ad  xor     esi, esi
0x18005b6af  lea     r15, aCavimediasourc_1; "CAVIMediaSourcePlugin::ParseData"
0x18005b6b6  mov     rdi, r8
0x18005b6b9  mov     [rbp+47h+var_70], esi
0x18005b6bc  mov     rbx, rdx
0x18005b6bf  mov     [rbp+47h+var_68], rsi
0x18005b6c3  mov     r13, rcx
0x18005b6c6  mov     [rbp+47h+ppIMFSample], rsi
0x18005b6ca  mov     rdx, r15; char *
0x18005b6cd  mov     [rbp+47h+var_50], rsi
0x18005b6d1  mov     r8d, 5D9h; int
0x18005b6d7  mov     [rbp+47h+var_58], esi
0x18005b6da  lea     rcx, [rbp+47h+var_80]; this
0x18005b6de  mov     [rbp+47h+var_5C], esi
0x18005b6e1  mov     r12d, r9d
0x18005b6e4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005b6e9  lea     r14, [r13-10h]
0x18005b6ed  cmp     [r14+48h], rsi
0x18005b6f1  jz      loc_18005C824
0x18005b6f7  mov     rax, [r13+40h]
0x18005b6fb  cmp     dword ptr [rax+0B4h], 3
0x18005b702  jnz     loc_18005C824
0x18005b708  test    rbx, rbx
0x18005b70b  jnz     loc_18005B7B2
0x18005b711  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b718  mov     edi, 80004003h
0x18005b71d  mov     ebx, edi
0x18005b71f  test    rcx, rcx
0x18005b722  jnz     short loc_18005B76B
0x18005b724  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005b72b  nop     dword ptr [rax+rax+00h]
0x18005b730  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b737  mov     rcx, rax
0x18005b73a  test    rax, rax
0x18005b73d  jz      short loc_18005B75D
0x18005b73f  mov     rax, [rax]
0x18005b742  mov     edx, 7F0h
0x18005b747  mov     rax, [rax+8]
0x18005b74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b750  test    eax, eax
0x18005b752  jz      short loc_18005B75D
0x18005b754  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b75b  jmp     short loc_18005B76B
0x18005b75d  lea     rcx, qword_1801B97E0; this
0x18005b764  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b76b  cmp     [rcx+8], sil
0x18005b76f  jz      short loc_18005B792
0x18005b771  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005b776  cmp     [rax+7CCh], edi
0x18005b77c  jz      short loc_18005B792
0x18005b77e  mov     r9d, edi; int
0x18005b781  mov     r8d, 5E0h; int
0x18005b787  mov     rdx, r15; char *
0x18005b78a  mov     rcx, rax; this
0x18005b78d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005b792  mov     esi, 1
0x18005b797  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18005b79e  jb      loc_18005C899
0x18005b7a4  mov     edx, 9Bh
0x18005b7a9  mov     dword ptr [rsp+0C0h+var_A0], edi
0x18005b7ad  jmp     loc_18005C87F
0x18005b7b2  mov     rsi, [rbp+47h+arg_28]
0x18005b7b6  test    rsi, rsi
0x18005b7b9  jnz     loc_18005B85C
0x18005b7bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b7c6  mov     edi, 80004003h
0x18005b7cb  mov     ebx, edi
0x18005b7cd  test    rcx, rcx
0x18005b7d0  jnz     short loc_18005B819
0x18005b7d2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005b7d9  nop     dword ptr [rax+rax+00h]
0x18005b7de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b7e5  mov     rcx, rax
0x18005b7e8  test    rax, rax
0x18005b7eb  jz      short loc_18005B80B
0x18005b7ed  mov     rax, [rax]
0x18005b7f0  mov     edx, 7F0h
0x18005b7f5  mov     rax, [rax+8]
0x18005b7f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b7fe  test    eax, eax
0x18005b800  jz      short loc_18005B80B
0x18005b802  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b809  jmp     short loc_18005B819
0x18005b80b  lea     rcx, qword_1801B97E0; this
0x18005b812  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b819  cmp     byte ptr [rcx+8], 0
0x18005b81d  jz      short loc_18005B840
0x18005b81f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005b824  cmp     [rax+7CCh], edi
0x18005b82a  jz      short loc_18005B840
0x18005b82c  mov     r9d, edi; int
0x18005b82f  mov     r8d, 5E1h; int
0x18005b835  mov     rdx, r15; char *
0x18005b838  mov     rcx, rax; this
0x18005b83b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005b840  mov     esi, 1
0x18005b845  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18005b84c  jb      loc_18005C899
0x18005b852  mov     edx, 9Ch
0x18005b857  jmp     loc_18005B7A9
0x18005b85c  lea     rcx, [r13+48h]; this
0x18005b860  mov     r8, rbx; struct IMFMediaBuffer *
0x18005b863  mov     rdx, rdi; unsigned __int64
0x18005b866  call    ?AddBuffer@CSourcePluginBufferReader@@QEAAJ_KPEAUIMFMediaBuffer@@@Z; CSourcePluginBufferReader::AddBuffer(unsigned __int64,IMFMediaBuffer *)
0x18005b86b  lea     r15, WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids
0x18005b872  mov     ebx, eax
0x18005b874  test    eax, eax
0x18005b876  jns     loc_18005B930
0x18005b87c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b883  test    rcx, rcx
0x18005b886  jnz     short loc_18005B8CF
0x18005b888  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005b88f  nop     dword ptr [rax+rax+00h]
0x18005b894  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b89b  mov     rcx, rax
0x18005b89e  test    rax, rax
0x18005b8a1  jz      short loc_18005B8C1
0x18005b8a3  mov     rax, [rax]
0x18005b8a6  mov     edx, 7F0h
0x18005b8ab  mov     rax, [rax+8]
0x18005b8af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b8b4  test    eax, eax
0x18005b8b6  jz      short loc_18005B8C1
0x18005b8b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b8bf  jmp     short loc_18005B8CF
0x18005b8c1  lea     rcx, qword_1801B97E0; this
0x18005b8c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b8cf  cmp     byte ptr [rcx+8], 0
0x18005b8d3  jz      short loc_18005B8FA
0x18005b8d5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005b8da  cmp     [rax+7CCh], ebx
0x18005b8e0  jz      short loc_18005B8FA
0x18005b8e2  mov     r9d, ebx; int
0x18005b8e5  lea     rdx, aCavimediasourc_1; "CAVIMediaSourcePlugin::ParseData"
0x18005b8ec  mov     r8d, 5E3h; int
0x18005b8f2  mov     rcx, rax; this
0x18005b8f5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005b8fa  mov     esi, 1
0x18005b8ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18005b906  jb      loc_18005C7A5
0x18005b90c  mov     edx, 9Dh
0x18005b911  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b918  mov     r9, r14
0x18005b91b  mov     r8, r15
0x18005b91e  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18005b922  mov     rcx, [rcx+10h]
0x18005b926  call    WPP_SF_qD
0x18005b92b  jmp     loc_18005C7A5
0x18005b930  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18005b937  mov     esi, 1
0x18005b93c  mov     rax, [r14+50h]
0x18005b940  mov     r9d, [rax+70h]
0x18005b944  mov     eax, [r13+24Ch]
0x18005b94b  mov     [rbp+47h+var_7C], r9d
0x18005b94f  cmp     eax, 0FFFFFFFFh
0x18005b952  jz      short loc_18005B9AB
0x18005b954  mov     edx, eax
0x18005b956  mov     rax, [r13+40h]
0x18005b95a  mov     rcx, [rax+68h]
0x18005b95e  mov     rcx, [rcx+rdx*8]
0x18005b962  mov     rax, [rcx]
0x18005b965  mov     rax, [rax+58h]
0x18005b969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b96e  mov     ebx, eax
0x18005b970  cmp     eax, esi
0x18005b972  jnz     loc_18005BA1F
0x18005b978  cmp     cs:byte_1801BA109, 20h ; ' '
0x18005b97f  jb      short loc_18005B9A7
0x18005b981  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b988  mov     edx, 9Eh
0x18005b98d  mov     eax, [r14+25Ch]
0x18005b994  mov     r9, r14
0x18005b997  mov     r8, r15
0x18005b99a  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18005b99e  mov     rcx, [rcx+38h]
0x18005b9a2  call    WPP_SF_qD
0x18005b9a7  mov     r9d, [rbp+47h+var_7C]
0x18005b9ab  or      r8d, 0FFFFFFFFh
0x18005b9af  cmp     dword ptr [r13+258h], 0
0x18005b9b7  mov     [rbp+47h+var_6C], r8d
0x18005b9bb  jnz     loc_18005BB0B
0x18005b9c1  mov     rdi, [rbp+47h+arg_20]
0x18005b9c5  xor     ebx, ebx
0x18005b9c7  cmp     ebx, r12d
0x18005b9ca  jnb     loc_18005BB0B
0x18005b9d0  cmp     r12d, r9d
0x18005b9d3  jnz     loc_18005BB0B
0x18005b9d9  cmp     cs:byte_1801BA109, 20h ; ' '
0x18005b9e0  jb      short loc_18005BA10
0x18005b9e2  mov     eax, [rdi+rbx*8+4]
0x18005b9e6  mov     edx, 0A0h
0x18005b9eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b9f2  mov     r9, r14
0x18005b9f5  mov     dword ptr [rsp+0C0h+var_98], eax
0x18005b9f9  mov     r8, r15
0x18005b9fc  mov     eax, [rdi+rbx*8]
0x18005b9ff  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18005ba03  mov     rcx, [rcx+38h]
0x18005ba07  call    WPP_SF_qDD
0x18005ba0c  mov     r9d, [rbp+47h+var_7C]
0x18005ba10  cmp     dword ptr [rdi+rbx*8+4], 0
0x18005ba15  jz      loc_18005BAC8
0x18005ba1b  add     ebx, esi
0x18005ba1d  jmp     short loc_18005B9C7
0x18005ba1f  test    ebx, ebx
0x18005ba21  js      short loc_18005BA33
0x18005ba23  mov     dword ptr [r13+24Ch], 0FFFFFFFFh
0x18005ba2e  jmp     loc_18005B9A7
0x18005ba33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ba3a  test    rcx, rcx
0x18005ba3d  jnz     short loc_18005BA86
0x18005ba3f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005ba46  nop     dword ptr [rax+rax+00h]
0x18005ba4b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ba52  mov     rcx, rax
0x18005ba55  test    rax, rax
0x18005ba58  jz      short loc_18005BA78
0x18005ba5a  mov     rax, [rax]
0x18005ba5d  mov     edx, 7F0h
0x18005ba62  mov     rax, [rax+8]
0x18005ba66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ba6b  test    eax, eax
0x18005ba6d  jz      short loc_18005BA78
0x18005ba6f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ba76  jmp     short loc_18005BA86
0x18005ba78  lea     rcx, qword_1801B97E0; this
0x18005ba7f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ba86  cmp     byte ptr [rcx+8], 0
0x18005ba8a  jz      short loc_18005BAB1
0x18005ba8c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005ba91  cmp     [rax+7CCh], ebx
0x18005ba97  jz      short loc_18005BAB1
0x18005ba99  mov     r9d, ebx; int
0x18005ba9c  lea     rdx, aCavimediasourc_1; "CAVIMediaSourcePlugin::ParseData"
0x18005baa3  mov     r8d, 5FDh; int
0x18005baa9  mov     rcx, rax; this
0x18005baac  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005bab1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18005bab8  jb      loc_18005C7A5
0x18005babe  mov     edx, 9Fh
0x18005bac3  jmp     loc_18005B911
0x18005bac8  xor     edx, edx
0x18005baca  cmp     edx, r12d
0x18005bacd  jnb     short loc_18005BB0B
0x18005bacf  lea     r8, ds:0[rdx*8]
0x18005bad7  cmp     edx, r9d
0x18005bada  jnb     short loc_18005BAF2
0x18005badc  mov     rax, [r13+40h]
0x18005bae0  mov     rcx, [rax+68h]
0x18005bae4  mov     rax, [rcx+r8]
0x18005bae8  xor     ecx, ecx
0x18005baea  cmp     [rax+50h], ecx
0x18005baed  setnz   cl
0x18005baf0  jmp     short loc_18005BAF4
0x18005baf2  xor     ecx, ecx
0x18005baf4  cmp     dword ptr [r8+rdi+4], 0
0x18005bafa  jz      short loc_18005BB00
0x18005bafc  test    ecx, ecx
0x18005bafe  jz      short loc_18005BB04
0x18005bb00  add     edx, esi
0x18005bb02  jmp     short loc_18005BACA
0x18005bb04  mov     eax, [r8+rdi]
0x18005bb08  mov     [rbp+47h+var_6C], eax
0x18005bb0b  mov     rax, [r13+40h]
0x18005bb0f  or      edx, 0FFFFFFFFh
0x18005bb12  xor     edi, edi
0x18005bb14  mov     [rbp+47h+var_60], 0FFFFFFFFh
0x18005bb1b  mov     [rbp+47h+var_90], edx
0x18005bb1e  mov     ecx, [rax+0A0h]
0x18005bb24  neg     ecx
0x18005bb26  sbb     rax, rax
0x18005bb29  mov     [rbp+47h+var_88], rax
0x18005bb2d  cmp     edi, r9d
0x18005bb30  jnb     loc_18005BD33
0x18005bb36  mov     rcx, [rbp+47h+var_68]
0x18005bb3a  test    rcx, rcx
0x18005bb3d  jz      short loc_18005BB53
0x18005bb3f  mov     rax, [rcx]
0x18005bb42  mov     rax, [rax+10h]
0x18005bb46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb4b  mov     [rbp+47h+var_68], 0
0x18005bb53  mov     rcx, [rbp+47h+ppIMFSample]
0x18005bb57  test    rcx, rcx
0x18005bb5a  jz      short loc_18005BB70
0x18005bb5c  mov     rax, [rcx]
0x18005bb5f  mov     rax, [rax+10h]
0x18005bb63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb68  mov     [rbp+47h+ppIMFSample], 0
0x18005bb70  mov     rax, [r13+40h]
  ... truncated ...
```
