# CMFByteStreamMediaSource::OnByteStreamReadDataInternal(IMFMediaBuffer *,ulong)

- ea: `0x18005e320`
- end: `0x18005fb57`
- name: `?OnByteStreamReadDataInternal@CMFByteStreamMediaSource@@AEAAJPEAUIMFMediaBuffer@@K@Z`
- size: `6199`
- prototype: `__int64 __fastcall(CMFByteStreamMediaSource *__hidden this, struct IMFMediaBuffer *, unsigned int)`
- caller_count: `2`
- callee_count: `35`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005d368`
- `0x1800d15b4`

## callees

- `0x18000a6dc`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180047a00`
- `0x18005c3ac`
- `0x18005c800`
- `0x18005ca98`
- `0x18005e320`
- `0x18006c228`
- `0x18006c560`
- `0x18006c71c`
- `0x18006c93c`
- `0x180071a44`
- `0x180073b14`
- `0x18007b1dc`
- `0x1800a72d0`
- `0x1800c2bd4`
- `0x1800c71e0`
- `0x1800d2de8`
- `0x1800e3934`
- `0x180105d4c`
- `0x180109590`
- `0x1801095a8`
- `0x1801099f0`
- `0x18011b1e4`
- `0x180137db4`
- `0x1801477b4`
- `0x180147a70`
- `0x18014a214`
- `0x18014a614`
- `0x180163dcc`
- `0x180173010`

## import_xrefs

- `MFPlat!MFCreateMediaEvent` at `0x18005e9f4`
- `MFPlat!MFCreateMediaEvent` at `0x18005e9f4`

## string_xrefs

- `0x18005e353`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005e3e2`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005e471`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005e4ef`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005e565`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005e5df`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005e66c`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005e6d6`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005e754`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005e816`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005eb48`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005ebe0`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005ec36`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005ec94`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005eceb`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005ed45`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005ed9f`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005edf9`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005ee53`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005eead`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005ef07`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005ef61`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005efb4`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005f048`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005f1bb`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005f215`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005f5c4`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005f621`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005f67e`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005f6db`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005f73c`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005f7a4`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005f815`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005f8b5`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005f90f`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005f969`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005f9bc`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005fa39`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18005faae`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`

## pseudocode

```c
__int64 __fastcall CMFByteStreamMediaSource::OnByteStreamReadDataInternal(
        CMFByteStreamMediaSource *this,
        struct IMFMediaBuffer *a2,
        unsigned int a3)
{
  unsigned int *v6; // rsi
  void *v7; // r13
  void *v8; // r12
  HRESULT CurrentPosition; // ebx
  CallStackTracing *v10; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  struct IMFMediaBuffer *v13; // rdx
  CallStackTracing *v14; // rcx
  struct CallStackContext *v15; // rax
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  CallStackTracing *v18; // rcx
  struct CallStackContext *v19; // rax
  CallStackTracing *v20; // rcx
  struct CallStackContext *v21; // rax
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  __int64 v24; // r14
  CallStackTracing *v25; // rcx
  struct CallStackContext *v26; // rax
  int *v27; // rcx
  struct _MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE *v28; // r8
  CallStackTracing *v29; // rcx
  struct CallStackContext *v30; // rax
  char *v31; // rbx
  unsigned int v32; // r14d
  CallStackTracing *v33; // rcx
  struct CallStackContext *v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rdx
  unsigned int v37; // r9d
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  __int64 v40; // rdx
  CallStackTracing *v41; // rcx
  struct CallStackContext *v42; // rax
  CallStackTracing *v43; // rcx
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  CallStackTracing *v46; // rcx
  struct CallStackContext *v47; // rax
  CallStackTracing *v48; // rcx
  struct CallStackContext *v49; // rax
  CallStackTracing *v50; // rcx
  struct CallStackContext *v51; // rax
  CallStackTracing *v52; // rcx
  struct CallStackContext *v53; // rax
  CallStackTracing *v54; // rcx
  struct CallStackContext *v55; // rax
  CallStackTracing *v56; // rcx
  struct CallStackContext *v57; // rax
  CallStackTracing *v58; // rcx
  struct CallStackContext *v59; // rax
  __int64 v60; // rdx
  CallStackTracing *v61; // rcx
  struct CallStackContext *v62; // rax
  CallStackTracing *v63; // rcx
  struct CallStackContext *v64; // rax
  CallStackTracing *v65; // rcx
  struct CallStackContext *v66; // rax
  CallStackTracing *v67; // rcx
  struct CallStackContext *v68; // rax
  __int64 v69; // rdx
  int v70; // ecx
  struct IMFSample *v71; // rax
  struct IMFMediaType *v72; // rdx
  CallStackTracing *v73; // rcx
  struct CallStackContext *v74; // rax
  __int64 v75; // rdx
  CallStackTracing *v76; // rcx
  struct CallStackContext *v77; // rax
  __int64 v78; // rdx
  __int64 v79; // r8
  int v80; // ecx
  unsigned int v81; // edx
  __int64 v82; // rcx
  struct IMFPresentationDescriptor *v83; // rdx
  unsigned int v84; // r15d
  CallStackTracing *v85; // rcx
  struct CallStackContext *v86; // rax
  CallStackTracing *v87; // rcx
  struct CallStackContext *v88; // rax
  CallStackTracing *v89; // rcx
  struct CallStackContext *v90; // rax
  CallStackTracing *v91; // rcx
  struct CallStackContext *v92; // rax
  __int64 v93; // rdx
  CallStackTracing *v94; // rcx
  struct CallStackContext *v95; // rax
  CallStackTracing *v96; // rcx
  struct CallStackContext *v97; // rax
  CallStackTracing *v98; // rcx
  struct CallStackContext *v99; // rax
  CallStackTracing *v100; // rcx
  struct CallStackContext *v101; // rax
  CallStackTracing *v102; // rcx
  struct CallStackContext *v103; // rax
  CallStackTracing *v104; // rcx
  struct CallStackContext *v105; // rax
  __int64 v106; // rdx
  CallStackTracing *v107; // rcx
  struct CallStackContext *v108; // rax
  CallStackTracing *v109; // rcx
  struct CallStackContext *v110; // rax
  CallStackTracing *v111; // rcx
  struct CallStackContext *v112; // rax
  IMFMediaEvent *ppEvent; // [rsp+50h] [rbp-89h] BYREF
  __int64 v115; // [rsp+58h] [rbp-81h] BYREF
  __int64 v116; // [rsp+60h] [rbp-79h] BYREF
  _BYTE v117[4]; // [rsp+68h] [rbp-71h] BYREF
  int v118; // [rsp+6Ch] [rbp-6Dh] BYREF
  size_t Size; // [rsp+70h] [rbp-69h] BYREF
  unsigned int v120; // [rsp+78h] [rbp-61h] BYREF
  int v121; // [rsp+7Ch] [rbp-5Dh] BYREF
  struct IMFSample *v122; // [rsp+80h] [rbp-59h] BYREF
  int v123; // [rsp+88h] [rbp-51h] BYREF
  struct CMFMediaStream *v124; // [rsp+90h] [rbp-49h] BYREF
  unsigned int v125; // [rsp+98h] [rbp-41h] BYREF
  __int64 v126; // [rsp+A0h] [rbp-39h] BYREF
  struct IMFMediaType *v127; // [rsp+A8h] [rbp-31h] BYREF
  int v128; // [rsp+B0h] [rbp-29h] BYREF
  int v129; // [rsp+B4h] [rbp-25h] BYREF
  unsigned __int64 v130; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v131; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v132; // [rsp+C8h] [rbp-11h] BYREF
  char *v133; // [rsp+D0h] [rbp-9h]
  char v134; // [rsp+D8h] [rbp-1h] BYREF
  char v135; // [rsp+D9h] [rbp+0h]
  char v136; // [rsp+DAh] [rbp+1h]
  char v137; // [rsp+DBh] [rbp+2h]
  __int128 v138; // [rsp+E0h] [rbp+7h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v117,
    "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
    3346);
  v125 = 0;
  v6 = 0;
  ppEvent = 0;
  v7 = 0;
  v130 = 0;
  v8 = 0;
  v129 = 0;
  v122 = 0;
  v127 = 0;
  v123 = 0;
  v120 = 0;
  v124 = 0;
  v128 = 0;
  v131 = 0;
  CurrentPosition = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, unsigned int *))a2->lpVtbl->GetCurrentLength)(
                      a2,
                      &v125);
  if ( CurrentPosition < 0 )
  {
    v10 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v10 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != CurrentPosition )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
          3371,
          CurrentPosition);
    }
    if ( !g_wppLevels )
      goto LABEL_379;
    v12 = 315;
    goto LABEL_9;
  }
  CurrentPosition = CMFByteStreamSourceReader::GetCurrentPosition(
                      (CMFByteStreamMediaSource *)((char *)this + 1120),
                      (unsigned __int64 *)&ppEvent);
  if ( CurrentPosition < 0 )
  {
    v14 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v14 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext(v14);
      if ( *((_DWORD *)v15 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(
          v15,
          "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
          3372,
          CurrentPosition);
    }
    if ( !g_wppLevels )
      goto LABEL_379;
    v12 = 316;
    goto LABEL_9;
  }
  if ( *((_QWORD *)this + 137) )
  {
    CurrentPosition = CMFByteStreamSourceReader::ConfigureDataBuffering(
                        (CMFByteStreamMediaSource *)((char *)this + 1120),
                        0);
    if ( CurrentPosition >= 0 )
    {
      CurrentPosition = CMFByteStreamSourceReader::SetCurrentPosition(
                          (CMFByteStreamMediaSource *)((char *)this + 1120),
                          *(_QWORD *)(*((_QWORD *)this + 137) + 8LL),
                          0);
      if ( CurrentPosition >= 0 )
      {
        CurrentPosition = CMFByteStreamSourceReader::BeginReadData(
                            (CMFByteStreamMediaSource *)((char *)this + 1120),
                            (struct IMFAsyncCallback *)this + 87,
                            *((_DWORD *)this + 276));
        if ( CurrentPosition >= 0 )
          goto LABEL_379;
        v20 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v20 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v20 + 8) )
        {
          v21 = CallStackTracing::GetThreadRelativeContext(v20);
          if ( *((_DWORD *)v21 + 499) != CurrentPosition )
            CallStackContext::TraceFailure(
              v21,
              "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
              3386,
              CurrentPosition);
        }
        if ( !g_wppLevels )
          goto LABEL_379;
        v12 = 319;
      }
      else
      {
        v18 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v18 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v18 + 8) )
        {
          v19 = CallStackTracing::GetThreadRelativeContext(v18);
          if ( *((_DWORD *)v19 + 499) != CurrentPosition )
            CallStackContext::TraceFailure(
              v19,
              "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
              3385,
              CurrentPosition);
        }
        if ( !g_wppLevels )
          goto LABEL_379;
        v12 = 318;
      }
    }
    else
    {
      v16 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v16 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext(v16);
        if ( *((_DWORD *)v17 + 499) != CurrentPosition )
          CallStackContext::TraceFailure(
            v17,
            "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
            3383,
            CurrentPosition);
      }
      if ( !g_wppLevels )
        goto LABEL_379;
      v12 = 317;
    }
    goto LABEL_9;
  }
  if ( (unsigned int)CMFByteStreamMediaSource::ShouldDropData(this, v13, a3, (unsigned __int64)ppEvent) )
  {
    if ( *((_DWORD *)this + 277) == 2 )
      goto LABEL_379;
    CurrentPosition = CMFByteStreamMediaSource::ServiceOutstandingSampleRequests(this);
    if ( CurrentPosition >= 0 )
      goto LABEL_379;
    v22 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v22 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v22 + 8) )
    {
      v23 = CallStackTracing::GetThreadRelativeContext(v22);
      if ( *((_DWORD *)v23 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(
          v23,
          "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
          3398,
          CurrentPosition);
    }
    if ( !g_wppLevels )
      goto LABEL_379;
    v12 = 320;
    goto LABEL_9;
  }
  v24 = v125;
  if ( (unsigned __int64)ppEvent < v125 )
  {
    v25 = CallStackTracing::s_wpInstance;
    CurrentPosition = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v25 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v25 + 8) )
    {
      v26 = CallStackTracing::GetThreadRelativeContext(v25);
      if ( *((_DWORD *)v26 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v26, "CMFByteStreamMediaSource::OnByteStreamReadDataInternal", 3406, -2147418113);
    }
    if ( !g_wppLevels )
      goto LABEL_379;
    v12 = 321;
    goto LABEL_9;
  }
  v27 = (int *)*((_QWORD *)this + 139);
  v28 = (struct _MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE *)*((_QWORD *)this + 155);
  v121 = v27[52];
  CurrentPosition = CMFMediaStreamArray::GetStreamBufferState((CMFMediaStreamArray *)v27, v121, v28);
  if ( CurrentPosition < 0 )
  {
    v29 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v29 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v29 + 8) )
    {
      v30 = CallStackTracing::GetThreadRelativeContext(v29);
      if ( *((_DWORD *)v30 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(
          v30,
          "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
          3419,
          CurrentPosition);
    }
    if ( !g_wppLevels )
      goto LABEL_379;
    v12 = 322;
    goto LABEL_9;
  }
  v31 = (char *)ppEvent - v24;
  v32 = 0;
  v133 = v31;
  v118 = 0;
  CMFByteStreamMediaSource::IsEndOfDataSegment(this, &v118);
  if ( v118 )
    v130 = -2;
  CurrentPosition = (*(__int64 (__fastcall **)(_QWORD, struct IMFMediaBuffer *, char *, _QWORD, _QWORD, unsigned __int64 *))(**((_QWORD **)this + 115) + 56LL))(
                      *((_QWORD *)this + 115),
                      a2,
                      v31,
                      (unsigned int)v121,
                      *((_QWORD *)this + 155),
                      &v130);
  if ( CurrentPosition < 0 )
  {
    v33 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v33 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v33 + 8) )
    {
      v34 = CallStackTracing::GetThreadRelativeContext(v33);
      if ( *((_DWORD *)v34 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(
          v34,
          "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
          3435,
          CurrentPosition);
    }
    if ( !g_wppLevels )
      goto LABEL_379;
    v12 = 323;
LABEL_9:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
      this,
      CurrentPosition);
    goto LABEL_379;
  }
  if ( *((_QWORD *)this + 117) )
  {
    while ( 1 )
    {
      v35 = *((_QWORD *)this + 117);
      v118 = 0;
      v115 = 0;
      CurrentPosition = (*(__int64 (__fastcall **)(__int64, unsigned int *, __int64 *))(*(_QWORD *)v35 + 32LL))(
                          v35,
                          &v120,
                          &v115);
      if ( CurrentPosition < 0 )
      {
        v76 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v76 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v76 + 8) )
        {
          v77 = CallStackTracing::GetThreadRelativeContext(v76);
          if ( *((_DWORD *)v77 + 499) != CurrentPosition )
            CallStackContext::TraceFailure(
              v77,
              "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
              3446,
              CurrentPosition);
        }
        if ( g_wppLevels )
        {
          v69 = 324;
LABEL_237:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v69,
            &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
            this,
            CurrentPosition);
        }
LABEL_238:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v115);
        v7 = 0;
        v8 = 0;
        goto LABEL_379;
      }
      if ( !v115 )
        break;
      CurrentPosition = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v115 + 24LL))(v115, &v118);
      if ( CurrentPosition < 0 )
      {
        v67 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v67 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v67 + 8) )
        {
          v68 = CallStackTracing::GetThreadRelativeContext(v67);
          if ( *((_DWORD *)v68 + 499) != CurrentPosition )
            CallStackContext::TraceFailure(
              v68,
              "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
              3453,
              CurrentPosition);
        }
        if ( g_wppLevels )
        {
          v69 = 325;
          goto LABEL_237;
        }
        goto LABEL_238;
      }
      v7 = 0;
      if ( v118 )
      {
        while ( 1 )
        {
          v138 = 0;
          Size = 0;
          ppEvent = 0;
          v116 = 0;
          CurrentPosition = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v115 + 32LL))(
                              v115,
                              v32,
                              &v116);
          if ( CurrentPosition < 0 )
          {
            v65 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v65 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v65 + 8) )
            {
              v66 = CallStackTracing::GetThreadRelativeContext(v65);
              if ( *((_DWORD *)v66 + 499) != CurrentPosition )
                CallStackContext::TraceFailure(
                  v66,
                  "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
                  3462,
                  CurrentPosition);
            }
            if ( g_wppLevels )
            {
              v60 = 326;
              goto LABEL_204;
            }
            goto LABEL_205;
          }
          CurrentPosition = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v116 + 24LL))(v116, &v138);
          if ( CurrentPosition < 0 )
          {
            v63 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v63 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v63 + 8) )
            {
              v64 = CallStackTracing::GetThreadRelativeContext(v63);
              if ( *((_DWORD *)v64 + 499) != CurrentPosition )
                CallStackContext::TraceFailure(
                  v64,
                  "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
                  3463,
                  CurrentPosition);
            }
            if ( g_wppLevels )
            {
              v60 = 327;
              goto LABEL_204;
            }
            goto LABEL_205;
          }
          CurrentPosition = (*(__int64 (__fastcall **)(__int64, size_t *))(*(_QWORD *)v116 + 32LL))(v116, &Size);
          if ( CurrentPosition < 0 )
            break;
          CurrentPosition = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v116 + 48LL))(
                              v116,
                              (char *)&Size + 4);
          if ( CurrentPosition < 0 )
          {
            v58 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v58 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v58 + 8) )
            {
              v59 = CallStackTracing::GetThreadRelativeContext(v58);
              if ( *((_DWORD *)v59 + 499) != CurrentPosition )
                CallStackContext::TraceFailure(
                  v59,
                  "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
                  3466,
                  CurrentPosition);
            }
            if ( g_wppLevels )
            {
              v60 = 329;
LABEL_204:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v60,
                &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
                this,
                CurrentPosition);
              goto LABEL_205;
            }
            goto LABEL_205;
          }
          v36 = (unsigned int)Size;
          v8 = 0;
          if ( (_DWORD)Size )
          {
            v8 = operator new((unsigned int)Size);
            if ( !v8 )
            {
              v38 = CallStackTracing::s_wpInstance;
              CurrentPosition = -2147024882;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v38 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v38 + 8) )
              {
                v39 = CallStackTracing::GetThreadRelativeContext(v38);
                if ( *((_DWORD *)v39 + 499) != -2147024882 )
                  CallStackContext::TraceFailure(
                    v39,
                    "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
                    3471,
                    -2147024882);
              }
              if ( !g_wppLevels )
                goto LABEL_118;
              v40 = 330;
LABEL_117:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v40,
                &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
                this,
                -2147024882);
              goto LABEL_118;
            }
            v36 = (unsigned int)Size;
          }
          v37 = HIDWORD(Size);
          if ( HIDWORD(Size) )
          {
            v7 = operator new(HIDWORD(Size));
            if ( !v7 )
            {
              v41 = CallStackTracing::s_wpInstance;
              CurrentPosition = -2147024882;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v41 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v41 + 8) )
              {
                v42 = CallStackTracing::GetThreadRelativeContext(v41);
                if ( *((_DWORD *)v42 + 499) != -2147024882 )
                  CallStackContext::TraceFailure(
                    v42,
                    "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
                    3477,
                    -2147024882);
              }
              if ( !g_wppLevels )
                goto LABEL_118;
              v40 = 331;
              goto LABEL_117;
            }
            v37 = HIDWORD(Size);
            v36 = (unsigned int)Size;
          }
          if ( (_DWORD)v36 )
          {
            CurrentPosition = (*(__int64 (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v116 + 40LL))(
                                v116,
                                v36,
                                v8);
            if ( CurrentPosition < 0 )
            {
              v43 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v43 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v43 + 8) )
              {
                v44 = CallStackTracing::GetThreadRelativeContext(v43);
                if ( *((_DWORD *)v44 + 499) != CurrentPosition )
                  CallStackContext::TraceFailure(
                    v44,
                    "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
                    3482,
                    CurrentPosition);
              }
              if ( g_wppLevels )
              {
                v45 = 332;
                goto LABEL_133;
              }
              goto LABEL_118;
            }
            v37 = HIDWORD(Size);
          }
          if ( v37 )
          {
            CurrentPosition = (*(__int64 (__fastcall **)(__int64, _QWORD, void *))(*(_QWORD *)v116 + 56LL))(
                                v116,
                                v37,
                                v7);
            if ( CurrentPosition < 0 )
            {
              v46 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v46 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v46 + 8) )
              {
                v47 = CallStackTracing::GetThreadRelativeContext(v46);
                if ( *((_DWORD *)v47 + 499) != CurrentPosition )
                  CallStackContext::TraceFailure(
                    v47,
                    "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
                    3487,
                    CurrentPosition);
              }
              if ( g_wppLevels )
              {
                v45 = 333;
                goto LABEL_133;
              }
LABEL_118:
              ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v116);
              ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppEvent);
              ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v115);
              goto LABEL_379;
            }
          }
          CurrentPosition = MFCreateMediaEvent(0x384u, &GUID_00000000_0000_0000_0000_000000000000, 0, 0, &ppEvent);
          if ( CurrentPosition < 0 )
          {
            v56 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v56 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v56 + 8) )
            {
              v57 = CallStackTracing::GetThreadRelativeContext(v56);
              if ( *((_DWORD *)v57 + 499) != CurrentPosition )
                CallStackContext::TraceFailure(
                  v57,
                  "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
                  3490,
                  CurrentPosition);
            }
            if ( !g_wppLevels )
              goto LABEL_118;
            v45 = 334;
LABEL_133:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v45,
              &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
              this,
              CurrentPosition);
            goto LABEL_118;
          }
          CurrentPosition = ((__int64 (__fastcall *)(IMFMediaEvent *, void *, __int128 *, __int64))ppEvent->lpVtbl->SetBlob)(
                              ppEvent,
                              &MF_EVENT_STREAM_METADATA_SYSTEMID,
                              &v138,
                              16);
          if ( CurrentPosition < 0 )
          {
            v54 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v54 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v54 + 8) )
            {
              v55 = CallStackTracing::GetThreadRelativeContext(v54);
              if ( *((_DWORD *)v55 + 499) != CurrentPosition )
                CallStackContext::TraceFailure(
                  v55,
                  "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
                  3492,
                  CurrentPosition);
            }
            if ( !g_wppLevels )
              goto LABEL_118;
            v45 = 335;
            goto LABEL_133;
          }
          if ( (_DWORD)Size )
          {
            CurrentPosition = ((__int64 (__fastcall *)(IMFMediaEvent *, void *, void *))ppEvent->lpVtbl->SetBlob)(
                                ppEvent,
                                &MF_EVENT_STREAM_METADATA_CONTENT_KEYIDS,
                                v8);
            if ( CurrentPosition < 0 )
            {
              v48 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v48 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v48 + 8) )
              {
                v49 = CallStackTracing::GetThreadRelativeContext(v48);
                if ( *((_DWORD *)v49 + 499) != CurrentPosition )
                  CallStackContext::TraceFailure(
                    v49,
                    "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
                    3496,
                    CurrentPosition);
              }
              if ( !g_wppLevels )
                goto LABEL_118;
              v45 = 336;
              goto LABEL_133;
            }
          }
          if ( HIDWORD(Size) )
          {
            CurrentPosition = ((__int64 (__fastcall *)(IMFMediaEvent *, void *, void *))ppEvent->lpVtbl->SetBlob)(
                                ppEvent,
                                &MF_EVENT_STREAM_METADATA_KEYDATA,
                                v7);
            if ( CurrentPosition < 0 )
            {
              v50 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v50 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v50 + 8) )
              {
                v51 = CallStackTracing::GetThreadRelativeContext(v50);
                if ( *((_DWORD *)v51 + 499) != CurrentPosition )
                  CallStackContext::TraceFailure(
                    v51,
                    "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
                    3501,
                    CurrentPosition);
              }
              if ( !g_wppLevels )
                goto LABEL_118;
              v45 = 337;
              goto LABEL_133;
            }
          }
          operator delete(v8);
          v8 = 0;
          operator delete(v7);
          v7 = 0;
          CurrentPosition = CMFMediaEventGenerator::QueueEvent(
                              (CMFByteStreamMediaSource *)((char *)this + 768),
                              ppEvent);
          if ( CurrentPosition < 0 )
          {
            v52 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v52 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v52 + 8) )
            {
              v53 = CallStackTracing::GetThreadRelativeContext(v52);
              if ( *((_DWORD *)v53 + 499) != CurrentPosition )
                CallStackContext::TraceFailure(
                  v53,
                  "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
                  3507,
                  CurrentPosition);
            }
            if ( !g_wppLevels )
              goto LABEL_118;
            v45 = 338;
            goto LABEL_133;
          }
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v116);
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppEvent);
          if ( ++v32 >= v118 )
            goto LABEL_107;
        }
        v61 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v61 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v61 + 8) )
        {
          v62 = CallStackTracing::GetThreadRelativeContext(v61);
          if ( *((_DWORD *)v62 + 499) != CurrentPosition )
            CallStackContext::TraceFailure(
              v62,
              "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
              3465,
              CurrentPosition);
        }
        if ( g_wppLevels )
        {
          v60 = 328;
          goto LABEL_204;
        }
LABEL_205:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v116);
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppEvent);
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v115);
        v8 = 0;
        goto LABEL_379;
      }
LABEL_107:
      v32 = 0;
      if ( v115 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v115 + 16LL))(v115);
        v115 = 0;
      }
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v115);
    }
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v115);
    v7 = 0;
  }
  v8 = 0;
  v134 = Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 8;
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 8) != 0 )
  {
    v70 = *((_DWORD *)this + 168);
    v134 = HIBYTE(v70);
    v135 = BYTE2(v70);
    v136 = BYTE1(v70);
    v137 = v70;
    McTemplateU0s4pupqii_EventWriteTransfer(
      v70,
      (unsigned int)&Process_Input,
      (unsigned int)&v134,
      (_DWORD)this + 672,
      9,
      (char)a2,
      v125,
      0);
  }
  while ( 1 )
  {
    ComSmartPtr<CMPEGFrame>::operator=(&v122, 0);
    ComSmartPtr<CMPEGFrame>::operator=(&v127, 0);
    CurrentPosition = (*(__int64 (__fastcall **)(_QWORD, int *, unsigned int *, struct IMFSample **, struct IMFMediaType **))(**((_QWORD **)this + 115) + 64LL))(
                        *((_QWORD *)this + 115),
                        &v123,
                        &v120,
                        &v122,
                        &v127);
    if ( CurrentPosition < 0 )
    {
      v111 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v111 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v111 + 8) )
      {
        v112 = CallStackTracing::GetThreadRelativeContext(v111);
        if ( *((_DWORD *)v112 + 499) != CurrentPosition )
          CallStackContext::TraceFailure(
            v112,
            "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
            3536,
            CurrentPosition);
      }
      if ( g_wppLevels )
      {
        v75 = 339;
LABEL_376:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v75,
          &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
          this,
          CurrentPosition);
      }
      goto LABEL_377;
    }
    v71 = v122;
    if ( !v122 )
      break;
    ((void (__fastcall *)(struct IMFSample *, int *))v122->lpVtbl->GetTotalLength)(v122, &v128);
    ((void (__fastcall *)(struct IMFSample *, __int64 *))v122->lpVtbl->GetSampleTime)(v122, &v131);
    LOBYTE(v126) = Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 8;
    if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 8) != 0 )
    {
      v80 = *((_DWORD *)this + 168);
      v134 = HIBYTE(v80);
      v135 = BYTE2(v80);
      v136 = BYTE1(v80);
      v137 = v80;
      McTemplateU0s4pupqii_EventWriteTransfer(
        v80,
        (unsigned int)&Process_Output,
        (unsigned int)&v134,
        (_DWORD)this + 672,
        9,
        (char)v122,
        v128,
        v131);
    }
    if ( (unsigned __int8)byte_1801B110B >= 8u )
    {
      WPP_SF_qqDI(*((_QWORD *)WPP_GLOBAL_Control + 17), v78, v79, this, v122, v120, v131);
      if ( (unsigned __int8)byte_1801B110B >= 8u )
        MFTRACE_SAMPLE_IMPL(1u, v81, v122);
    }
    v71 = v122;
    v72 = v127;
LABEL_245:
    if ( v6 )
    {
      if ( v120 == v6[108] )
        goto LABEL_250;
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v6 + 16LL))(v6);
      v124 = 0;
    }
    CurrentPosition = CMFMediaStreamArray::GetStreamById(*((CMFMediaStreamArray **)this + 139), v120, &v124);
    if ( CurrentPosition < 0 )
    {
      v109 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v109 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v109 + 8) )
      {
        v110 = CallStackTracing::GetThreadRelativeContext(v109);
        if ( *((_DWORD *)v110 + 499) != CurrentPosition )
          CallStackContext::TraceFailure(
            v110,
            "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
            3586,
            CurrentPosition);
      }
      if ( g_wppLevels )
      {
        v93 = 343;
LABEL_367:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v93,
          &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
          this,
          CurrentPosition);
      }
LABEL_368:
      v6 = (unsigned int *)v124;
      goto LABEL_377;
    }
    v71 = v122;
    v72 = v127;
    v6 = (unsigned int *)v124;
LABEL_250:
    if ( v72 )
    {
      CurrentPosition = CMFMediaStream::QueueFormatChange((CMFMediaStream *)v6, v72);
      if ( CurrentPosition < 0 )
      {
        v100 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v100 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v100 + 8) )
        {
          v101 = CallStackTracing::GetThreadRelativeContext(v100);
          if ( *((_DWORD *)v101 + 499) != CurrentPosition )
            CallStackContext::TraceFailure(
              v101,
              "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
              3594,
              CurrentPosition);
        }
        if ( g_wppLevels )
        {
          v75 = 344;
          goto LABEL_376;
        }
        goto LABEL_377;
      }
      v71 = v122;
    }
    if ( v71 )
    {
      CurrentPosition = CMFMediaStream::NewSample((CMFMediaStream *)v6, v71);
      if ( CurrentPosition < 0 )
      {
        v102 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v102 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v102 + 8) )
        {
          v103 = CallStackTracing::GetThreadRelativeContext(v102);
          if ( *((_DWORD *)v103 + 499) != CurrentPosition )
            CallStackContext::TraceFailure(
              v103,
              "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
              3599,
              CurrentPosition);
        }
        if ( g_wppLevels )
        {
          v75 = 345;
          goto LABEL_376;
        }
        goto LABEL_377;
      }
    }
    if ( (v123 & 8) != 0 )
    {
      v82 = *((_QWORD *)this + 113);
      v132 = 0;
      v126 = 0;
      if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v82 + 40LL))(v82, &v126) >= 0
        && (*(int (__fastcall **)(__int64, const IID *, __int64 *))(*(_QWORD *)v126 + 64LL))(
             v126,
             &MF_PD_DURATION,
             &v132) >= 0
        && *((_QWORD *)this + 133) != v132 )
      {
        CurrentPosition = (*(__int64 (__fastcall **)(_QWORD, const IID *))(**((_QWORD **)this + 111) + 176LL))(
                            *((_QWORD *)this + 111),
                            &MF_PD_DURATION);
        if ( CurrentPosition < 0 )
        {
          v107 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v107 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v107 + 8) )
          {
            v108 = CallStackTracing::GetThreadRelativeContext(v107);
            if ( *((_DWORD *)v108 + 499) != CurrentPosition )
              CallStackContext::TraceFailure(
                v108,
                "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
                3614,
                CurrentPosition);
          }
          if ( g_wppLevels )
          {
            v106 = 346;
LABEL_358:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v106,
              &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
              this,
              CurrentPosition);
          }
LABEL_359:
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v126);
          goto LABEL_377;
        }
        v83 = (struct IMFPresentationDescriptor *)*((_QWORD *)this + 111);
        *((_QWORD *)this + 133) = v132;
        *((_DWORD *)this + 314) = 1;
        CurrentPosition = CMFByteStreamMediaSource::QueueMetadataEvent(this, v83);
        if ( CurrentPosition < 0 )
        {
          v104 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v104 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v104 + 8) )
          {
            v105 = CallStackTracing::GetThreadRelativeContext(v104);
            if ( *((_DWORD *)v105 + 499) != CurrentPosition )
              CallStackContext::TraceFailure(
                v105,
                "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
                3617,
                CurrentPosition);
          }
          if ( g_wppLevels )
          {
            v106 = 347;
            goto LABEL_358;
          }
          goto LABEL_359;
        }
      }
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v126);
    }
  }
  v72 = v127;
  if ( v127 )
    goto LABEL_245;
  if ( (unsigned __int8)byte_1801B110B >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 340, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, this);
  if ( (v123 & 1) == 0 )
    goto LABEL_382;
  CurrentPosition = CMFMediaStreamArray::NotifyEOS(*((CMFMediaStreamArray **)this + 139));
  if ( CurrentPosition < 0 )
  {
    v73 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v73 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v73 + 8) )
    {
      v74 = CallStackTracing::GetThreadRelativeContext(v73);
      if ( *((_DWORD *)v74 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(
          v74,
          "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
          3548,
          CurrentPosition);
    }
    if ( g_wppLevels )
    {
      v75 = 341;
      goto LABEL_376;
    }
    goto LABEL_377;
  }
  if ( (v123 & 1) == 0 )
  {
LABEL_382:
    v84 = v121;
    if ( v121 )
    {
      while ( 1 )
      {
        if ( v6 )
        {
          (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v6 + 16LL))(v6);
          v124 = 0;
        }
        CurrentPosition = CMFMediaStreamArray::GetStreamByIndex(*((CMFMediaStreamArray **)this + 139), v32, &v124);
        if ( CurrentPosition < 0 )
          break;
        v6 = (unsigned int *)v124;
        if ( !(*(unsigned int (__fastcall **)(char *))(*((_QWORD *)v124 + 5) + 24LL))((char *)v124 + 40) )
        {
          CurrentPosition = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(**((_QWORD **)this + 115) + 72LL))(
                              *((_QWORD *)this + 115),
                              v6[108],
                              &v129);
          if ( CurrentPosition < 0 )
          {
            v89 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v89 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v89 + 8) )
            {
              v90 = CallStackTracing::GetThreadRelativeContext(v89);
              if ( *((_DWORD *)v90 + 499) != CurrentPosition )
                CallStackContext::TraceFailure(
                  v90,
                  "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
                  3638,
                  CurrentPosition);
            }
            if ( g_wppLevels )
            {
              v75 = 349;
              goto LABEL_376;
            }
            goto LABEL_377;
          }
          if ( v129 )
          {
            CurrentPosition = CMFMediaStream::NotifyEOS((CMFMediaStream *)v6);
            if ( CurrentPosition < 0 )
            {
              v87 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v87 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v87 + 8) )
              {
                v88 = CallStackTracing::GetThreadRelativeContext(v87);
                if ( *((_DWORD *)v88 + 499) != CurrentPosition )
                  CallStackContext::TraceFailure(
                    v88,
                    "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
                    3642,
                    CurrentPosition);
              }
              if ( g_wppLevels )
              {
                v75 = 350;
                goto LABEL_376;
              }
              goto LABEL_377;
            }
          }
        }
        if ( ++v32 >= v84 )
          goto LABEL_272;
      }
      v91 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v91 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v91 + 8) )
      {
        v92 = CallStackTracing::GetThreadRelativeContext(v91);
        if ( *((_DWORD *)v92 + 499) != CurrentPosition )
          CallStackContext::TraceFailure(
            v92,
            "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
            3630,
            CurrentPosition);
      }
      if ( g_wppLevels )
      {
        v93 = 348;
        goto LABEL_367;
      }
      goto LABEL_368;
    }
  }
LABEL_272:
  if ( v130 == -1 )
    goto LABEL_311;
  v121 = 0;
  CurrentPosition = CMFByteStreamSourceReader::SetCurrentPosition(
                      (CMFByteStreamMediaSource *)((char *)this + 1120),
                      v130,
                      &v121);
  if ( v121 == 1 )
  {
    CurrentPosition = CMFMediaStreamArray::NotifyEOS(*((CMFMediaStreamArray **)this + 139));
    if ( CurrentPosition < 0 )
    {
      v85 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v85 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v85 + 8) )
      {
        v86 = CallStackTracing::GetThreadRelativeContext(v85);
        if ( *((_DWORD *)v86 + 499) != CurrentPosition )
          CallStackContext::TraceFailure(
            v86,
            "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
            3659,
            CurrentPosition);
      }
      if ( g_wppLevels )
      {
        v75 = 351;
        goto LABEL_376;
      }
      goto LABEL_377;
    }
  }
  if ( CurrentPosition >= 0 )
  {
LABEL_311:
    CurrentPosition = CMFByteStreamMediaSource::ServiceOutstandingSampleRequests(this);
    if ( CurrentPosition >= 0 )
    {
      if ( *((_DWORD *)this + 319)
        && (CurrentPosition = CMFByteStreamMediaSource::CheckBufferingState(this), CurrentPosition < 0) )
      {
        v98 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v98 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v98 + 8) )
        {
          v99 = CallStackTracing::GetThreadRelativeContext(v98);
          if ( *((_DWORD *)v99 + 499) != CurrentPosition )
            CallStackContext::TraceFailure(
              v99,
              "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
              3674,
              CurrentPosition);
        }
        if ( g_wppLevels )
        {
          v75 = 354;
          goto LABEL_376;
        }
      }
      else if ( (unsigned __int8)byte_1801B110B >= 0x10u )
      {
        WPP_SF_qII(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          355,
          &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
          this,
          v133,
          v130);
      }
    }
    else
    {
      v96 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v96 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v96 + 8) )
      {
        v97 = CallStackTracing::GetThreadRelativeContext(v96);
        if ( *((_DWORD *)v97 + 499) != CurrentPosition )
          CallStackContext::TraceFailure(
            v97,
            "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
            3670,
            CurrentPosition);
      }
      if ( g_wppLevels )
      {
        v75 = 353;
        goto LABEL_376;
      }
    }
  }
  else
  {
    v94 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v94 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v94 + 8) )
    {
      v95 = CallStackTracing::GetThreadRelativeContext(v94);
      if ( *((_DWORD *)v95 + 499) != CurrentPosition )
        CallStackContext::TraceFailure(
          v95,
          "CMFByteStreamMediaSource::OnByteStreamReadDataInternal",
          3661,
          CurrentPosition);
    }
    if ( g_wppLevels )
    {
      v75 = 352;
      goto LABEL_376;
    }
  }
LABEL_377:
  if ( v6 )
    (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v6 + 16LL))(v6);
LABEL_379:
  operator delete(v8);
  operator delete(v7);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v127);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v122);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v117);
  return (unsigned int)CurrentPosition;
}

```

## disassembly

```asm
0x18005e320  mov     [rsp-8+arg_10], rbx
0x18005e325  push    rbp
0x18005e326  push    rsi
0x18005e327  push    rdi
0x18005e328  push    r12
0x18005e32a  push    r13
0x18005e32c  push    r14
0x18005e32e  push    r15
0x18005e330  lea     rbp, [rsp-27h]
0x18005e335  sub     rsp, 100h
0x18005e33c  mov     rax, cs:__security_cookie
0x18005e343  xor     rax, rsp
0x18005e346  mov     [rbp+57h+var_40], rax
0x18005e34a  mov     r14d, r8d
0x18005e34d  mov     r15, rdx
0x18005e350  mov     rdi, rcx
0x18005e353  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x18005e35a  mov     r8d, 0D12h; int
0x18005e360  lea     rcx, [rbp+57h+var_C8]; this
0x18005e364  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005e369  xor     eax, eax
0x18005e36b  lea     rdx, [rbp+57h+var_98]
0x18005e36f  mov     [rbp+57h+var_98], eax
0x18005e372  mov     esi, eax
0x18005e374  mov     [rsp+130h+var_E0], rax
0x18005e379  mov     r13d, eax
0x18005e37c  mov     [rbp+57h+var_78], rax
0x18005e380  mov     r12d, eax
0x18005e383  mov     [rbp+57h+var_7C], eax
0x18005e386  mov     rcx, r15
0x18005e389  mov     [rbp+57h+var_B0], rax
0x18005e38d  mov     [rbp+57h+var_88], rax
0x18005e391  mov     [rbp+57h+var_A8], eax
0x18005e394  mov     [rbp+57h+var_B8], eax
0x18005e397  mov     [rbp+57h+var_A0], rax
0x18005e39b  mov     [rbp+57h+var_80], eax
0x18005e39e  mov     [rbp+57h+var_70], rax
0x18005e3a2  mov     rax, [r15]
0x18005e3a5  mov     rax, [rax+28h]
0x18005e3a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e3ae  mov     ebx, eax
0x18005e3b0  test    eax, eax
0x18005e3b2  jns     short loc_18005E42C
0x18005e3b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e3bb  test    rcx, rcx
0x18005e3be  jnz     short loc_18005E3CC
0x18005e3c0  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005e3c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005e3cc  cmp     [rcx+8], sil
0x18005e3d0  jz      short loc_18005E3F7
0x18005e3d2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e3d7  cmp     [rax+7CCh], ebx
0x18005e3dd  jz      short loc_18005E3F7
0x18005e3df  mov     r9d, ebx; int
0x18005e3e2  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x18005e3e9  mov     r8d, 0D2Bh; int
0x18005e3ef  mov     rcx, rax; this
0x18005e3f2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e3f7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e3fe  jb      loc_18005FB03
0x18005e404  mov     edx, 13Bh
0x18005e409  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e410  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x18005e417  mov     r9, rdi
0x18005e41a  mov     dword ptr [rsp+130h+ppEvent], ebx
0x18005e41e  mov     rcx, [rcx+10h]
0x18005e422  call    WPP_SF_qD
0x18005e427  jmp     loc_18005FB03
0x18005e42c  lea     rcx, [rdi+460h]; this
0x18005e433  lea     rdx, [rsp+130h+var_E0]; unsigned __int64 *
0x18005e438  call    ?GetCurrentPosition@CMFByteStreamSourceReader@@QEAAJPEA_K@Z; CMFByteStreamSourceReader::GetCurrentPosition(unsigned __int64 *)
0x18005e43d  mov     ebx, eax
0x18005e43f  test    eax, eax
0x18005e441  jns     short loc_18005E49D
0x18005e443  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e44a  test    rcx, rcx
0x18005e44d  jnz     short loc_18005E45B
0x18005e44f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005e454  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005e45b  cmp     [rcx+8], sil
0x18005e45f  jz      short loc_18005E486
0x18005e461  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e466  cmp     [rax+7CCh], ebx
0x18005e46c  jz      short loc_18005E486
0x18005e46e  mov     r9d, ebx; int
0x18005e471  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x18005e478  mov     r8d, 0D2Ch; int
0x18005e47e  mov     rcx, rax; this
0x18005e481  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e486  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e48d  jb      loc_18005FB03
0x18005e493  mov     edx, 13Ch
0x18005e498  jmp     loc_18005E409
0x18005e49d  cmp     [rdi+448h], rsi
0x18005e4a4  jz      loc_18005E60B
0x18005e4aa  lea     r14, [rdi+460h]
0x18005e4b1  xor     edx, edx; int
0x18005e4b3  mov     rcx, r14; this
0x18005e4b6  call    ?ConfigureDataBuffering@CMFByteStreamSourceReader@@QEAAJH@Z; CMFByteStreamSourceReader::ConfigureDataBuffering(int)
0x18005e4bb  mov     ebx, eax
0x18005e4bd  test    eax, eax
0x18005e4bf  jns     short loc_18005E51B
0x18005e4c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e4c8  test    rcx, rcx
0x18005e4cb  jnz     short loc_18005E4D9
0x18005e4cd  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005e4d2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005e4d9  cmp     [rcx+8], sil
0x18005e4dd  jz      short loc_18005E504
0x18005e4df  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e4e4  cmp     [rax+7CCh], ebx
0x18005e4ea  jz      short loc_18005E504
0x18005e4ec  mov     r9d, ebx; int
0x18005e4ef  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x18005e4f6  mov     r8d, 0D37h; int
0x18005e4fc  mov     rcx, rax; this
0x18005e4ff  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e504  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e50b  jb      loc_18005FB03
0x18005e511  mov     edx, 13Dh
0x18005e516  jmp     loc_18005E409
0x18005e51b  mov     rdx, [rdi+448h]
0x18005e522  xor     r8d, r8d; int *
0x18005e525  mov     rcx, r14; this
0x18005e528  mov     rdx, [rdx+8]; unsigned __int64
0x18005e52c  call    ?SetCurrentPosition@CMFByteStreamSourceReader@@QEAAJ_KPEAH@Z; CMFByteStreamSourceReader::SetCurrentPosition(unsigned __int64,int *)
0x18005e531  mov     ebx, eax
0x18005e533  test    eax, eax
0x18005e535  jns     short loc_18005E591
0x18005e537  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e53e  test    rcx, rcx
0x18005e541  jnz     short loc_18005E54F
0x18005e543  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005e548  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005e54f  cmp     [rcx+8], sil
0x18005e553  jz      short loc_18005E57A
0x18005e555  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e55a  cmp     [rax+7CCh], ebx
0x18005e560  jz      short loc_18005E57A
0x18005e562  mov     r9d, ebx; int
0x18005e565  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x18005e56c  mov     r8d, 0D39h; int
0x18005e572  mov     rcx, rax; this
0x18005e575  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e57a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e581  jb      loc_18005FB03
0x18005e587  mov     edx, 13Eh
0x18005e58c  jmp     loc_18005E409
0x18005e591  mov     r8d, [rdi+450h]; unsigned int
0x18005e598  lea     rdx, [rdi+2B8h]; struct IMFAsyncCallback *
0x18005e59f  mov     rcx, r14; this
0x18005e5a2  call    ?BeginReadData@CMFByteStreamSourceReader@@QEAAJPEAUIMFAsyncCallback@@K@Z; CMFByteStreamSourceReader::BeginReadData(IMFAsyncCallback *,ulong)
0x18005e5a7  mov     ebx, eax
0x18005e5a9  test    eax, eax
0x18005e5ab  jns     loc_18005FB03
0x18005e5b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e5b8  test    rcx, rcx
0x18005e5bb  jnz     short loc_18005E5C9
0x18005e5bd  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005e5c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005e5c9  cmp     [rcx+8], sil
0x18005e5cd  jz      short loc_18005E5F4
0x18005e5cf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e5d4  cmp     [rax+7CCh], ebx
0x18005e5da  jz      short loc_18005E5F4
0x18005e5dc  mov     r9d, ebx; int
0x18005e5df  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x18005e5e6  mov     r8d, 0D3Ah; int
0x18005e5ec  mov     rcx, rax; this
0x18005e5ef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e5f4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e5fb  jb      loc_18005FB03
0x18005e601  mov     edx, 13Fh
0x18005e606  jmp     loc_18005E409
0x18005e60b  mov     r9, [rsp+130h+var_E0]; unsigned __int64
0x18005e610  mov     r8d, r14d; unsigned int
0x18005e613  mov     rcx, rdi; this
0x18005e616  call    ?ShouldDropData@CMFByteStreamMediaSource@@AEAAHPEAUIMFMediaBuffer@@K_K@Z; CMFByteStreamMediaSource::ShouldDropData(IMFMediaBuffer *,ulong,unsigned __int64)
0x18005e61b  test    eax, eax
0x18005e61d  jz      short loc_18005E698
0x18005e61f  cmp     dword ptr [rdi+454h], 2
0x18005e626  jz      loc_18005FB03
0x18005e62c  mov     rcx, rdi; this
0x18005e62f  call    ?ServiceOutstandingSampleRequests@CMFByteStreamMediaSource@@AEAAJXZ; CMFByteStreamMediaSource::ServiceOutstandingSampleRequests(void)
0x18005e634  mov     ebx, eax
0x18005e636  test    eax, eax
0x18005e638  jns     loc_18005FB03
0x18005e63e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e645  test    rcx, rcx
0x18005e648  jnz     short loc_18005E656
0x18005e64a  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005e64f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005e656  cmp     [rcx+8], sil
0x18005e65a  jz      short loc_18005E681
0x18005e65c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e661  cmp     [rax+7CCh], ebx
0x18005e667  jz      short loc_18005E681
0x18005e669  mov     r9d, ebx; int
0x18005e66c  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x18005e673  mov     r8d, 0D46h; int
0x18005e679  mov     rcx, rax; this
0x18005e67c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e681  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e688  jb      loc_18005FB03
0x18005e68e  mov     edx, 140h
0x18005e693  jmp     loc_18005E409
0x18005e698  mov     r14d, [rbp+57h+var_98]
0x18005e69c  cmp     [rsp+130h+var_E0], r14
0x18005e6a1  jnb     short loc_18005E702
0x18005e6a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e6aa  mov     ebx, 8000FFFFh
0x18005e6af  test    rcx, rcx
0x18005e6b2  jnz     short loc_18005E6C0
0x18005e6b4  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005e6b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005e6c0  cmp     [rcx+8], sil
0x18005e6c4  jz      short loc_18005E6EB
0x18005e6c6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e6cb  cmp     [rax+7CCh], ebx
0x18005e6d1  jz      short loc_18005E6EB
0x18005e6d3  mov     r9d, ebx; int
0x18005e6d6  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x18005e6dd  mov     r8d, 0D4Eh; int
0x18005e6e3  mov     rcx, rax; this
0x18005e6e6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e6eb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e6f2  jb      loc_18005FB03
0x18005e6f8  mov     edx, 141h
0x18005e6fd  jmp     loc_18005E409
0x18005e702  mov     rcx, [rdi+458h]; this
0x18005e709  mov     r8, [rdi+4D8h]; struct _MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE *
0x18005e710  mov     eax, [rcx+0D0h]
0x18005e716  mov     edx, eax; unsigned int
0x18005e718  mov     [rbp+57h+var_B4], eax
0x18005e71b  call    ?GetStreamBufferState@CMFMediaStreamArray@@QEAAJIPEAU_MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE@@@Z; CMFMediaStreamArray::GetStreamBufferState(uint,_MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE *)
0x18005e720  mov     ebx, eax
0x18005e722  test    eax, eax
0x18005e724  jns     short loc_18005E780
0x18005e726  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e72d  test    rcx, rcx
0x18005e730  jnz     short loc_18005E73E
0x18005e732  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005e737  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005e73e  cmp     [rcx+8], sil
0x18005e742  jz      short loc_18005E769
0x18005e744  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e749  cmp     [rax+7CCh], ebx
0x18005e74f  jz      short loc_18005E769
0x18005e751  mov     r9d, ebx; int
0x18005e754  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x18005e75b  mov     r8d, 0D5Bh; int
0x18005e761  mov     rcx, rax; this
0x18005e764  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e769  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e770  jb      loc_18005FB03
0x18005e776  mov     edx, 142h
0x18005e77b  jmp     loc_18005E409
0x18005e780  mov     rbx, [rsp+130h+var_E0]
0x18005e785  lea     rdx, [rbp+57h+var_C4]; int *
0x18005e789  sub     rbx, r14
0x18005e78c  mov     rcx, rdi; this
0x18005e78f  xor     r14d, r14d
0x18005e792  mov     [rbp+57h+var_60], rbx
0x18005e796  mov     [rbp+57h+var_C4], r14d
0x18005e79a  call    ?IsEndOfDataSegment@CMFByteStreamMediaSource@@AEAAJPEAH@Z; CMFByteStreamMediaSource::IsEndOfDataSegment(int *)
0x18005e79f  cmp     [rbp+57h+var_C4], r14d
0x18005e7a3  jz      short loc_18005E7AD
0x18005e7a5  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFEh
0x18005e7ad  mov     rcx, [rdi+398h]
0x18005e7b4  mov     r8, rbx
0x18005e7b7  mov     r9d, [rbp+57h+var_B4]
0x18005e7bb  mov     rdx, r15
0x18005e7be  mov     rax, [rcx]
0x18005e7c1  mov     r10, [rax+38h]
0x18005e7c5  lea     rax, [rbp+57h+var_78]
0x18005e7c9  mov     [rsp+130h+var_108], rax
0x18005e7ce  mov     rax, [rdi+4D8h]
0x18005e7d5  mov     [rsp+130h+ppEvent], rax
0x18005e7da  mov     rax, r10
0x18005e7dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e7e2  mov     ebx, eax
0x18005e7e4  test    eax, eax
0x18005e7e6  jns     short loc_18005E842
0x18005e7e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e7ef  test    rcx, rcx
0x18005e7f2  jnz     short loc_18005E800
0x18005e7f4  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005e7f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005e800  cmp     [rcx+8], r14b
0x18005e804  jz      short loc_18005E82B
0x18005e806  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e80b  cmp     [rax+7CCh], ebx
0x18005e811  jz      short loc_18005E82B
0x18005e813  mov     r9d, ebx; int
0x18005e816  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x18005e81d  mov     r8d, 0D6Bh; int
0x18005e823  mov     rcx, rax; this
0x18005e826  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e82b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e832  jb      loc_18005FB03
  ... truncated ...
```
