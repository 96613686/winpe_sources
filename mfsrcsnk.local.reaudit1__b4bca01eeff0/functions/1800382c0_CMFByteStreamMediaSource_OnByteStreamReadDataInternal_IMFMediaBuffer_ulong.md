# CMFByteStreamMediaSource::OnByteStreamReadDataInternal(IMFMediaBuffer *,ulong)

- ea: `0x1800382c0`
- end: `0x180039afe`
- name: `?OnByteStreamReadDataInternal@CMFByteStreamMediaSource@@AEAAJPEAUIMFMediaBuffer@@K@Z`
- size: `6206`
- prototype: `__int64 __fastcall(CMFByteStreamMediaSource *__hidden this, struct IMFMediaBuffer *, unsigned int)`
- caller_count: `2`
- callee_count: `35`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180037280`
- `0x1800d7560`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x1800382c0`
- `0x18003e398`
- `0x18004a8a8`
- `0x18005fc5c`
- `0x1800600d4`
- `0x180060378`
- `0x18006d4d8`
- `0x18006d830`
- `0x18006df50`
- `0x18006e194`
- `0x180077708`
- `0x180079680`
- `0x180080f54`
- `0x1800ac3e4`
- `0x1800c8a94`
- `0x1800ccc3c`
- `0x1800d8e60`
- `0x1800ea1bc`
- `0x18010d088`
- `0x180110a7c`
- `0x180110a94`
- `0x180110ed0`
- `0x180121750`
- `0x18013f664`
- `0x18014f8fc`
- `0x18014fbd8`
- `0x1801524b4`
- `0x1801528e4`
- `0x18016ccc0`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFCreateMediaEvent` at `0x180038994`
- `MFPlat!MFCreateMediaEvent` at `0x180038994`

## string_xrefs

- `0x1800382f3`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180038382`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180038411`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18003848f`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180038505`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18003857f`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18003860c`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180038676`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x1800386f4`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x1800387b6`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180038aee`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180038b86`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180038bdc`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180038c3a`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180038c91`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180038ceb`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180038d45`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180038d9f`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180038df9`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180038e53`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180038ead`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180038f07`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180038f5a`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180038fee`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180039161`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x1800391bb`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18003956a`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x1800395c7`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180039624`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180039681`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x1800396e2`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18003974a`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x1800397bb`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18003985b`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x1800398b5`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x18003990f`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180039962`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x1800399df`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`
- `0x180039a54`: `CMFByteStreamMediaSource::OnByteStreamReadDataInternal`

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
          CurrentPosition = ((__int64 (__fastcall *)(IMFMediaEvent *, __int64 *, __int128 *, __int64))ppEvent->lpVtbl->SetBlob)(
                              ppEvent,
                              MF_EVENT_STREAM_METADATA_SYSTEMID,
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
            CurrentPosition = ((__int64 (__fastcall *)(IMFMediaEvent *, __int64 *, void *))ppEvent->lpVtbl->SetBlob)(
                                ppEvent,
                                MF_EVENT_STREAM_METADATA_CONTENT_KEYIDS,
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
            CurrentPosition = ((__int64 (__fastcall *)(IMFMediaEvent *, __int64 *, void *))ppEvent->lpVtbl->SetBlob)(
                                ppEvent,
                                MF_EVENT_STREAM_METADATA_KEYDATA,
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
      (unsigned int)Process_Input,
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
        (unsigned int)Process_Output,
        (unsigned int)&v134,
        (_DWORD)this + 672,
        9,
        (char)v122,
        v128,
        v131);
    }
    if ( (unsigned __int8)byte_1801BA10B >= 8u )
    {
      WPP_SF_qqDI(*((_QWORD *)WPP_GLOBAL_Control + 17), v78, v79, this, v122, v120, v131);
      if ( (unsigned __int8)byte_1801BA10B >= 8u )
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
  if ( (unsigned __int8)byte_1801BA10B >= 8u )
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
      else if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
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
0x1800382c0  mov     [rsp-8+arg_10], rbx
0x1800382c5  push    rbp
0x1800382c6  push    rsi
0x1800382c7  push    rdi
0x1800382c8  push    r12
0x1800382ca  push    r13
0x1800382cc  push    r14
0x1800382ce  push    r15
0x1800382d0  lea     rbp, [rsp-27h]
0x1800382d5  sub     rsp, 100h
0x1800382dc  mov     rax, cs:__security_cookie
0x1800382e3  xor     rax, rsp
0x1800382e6  mov     [rbp+57h+var_40], rax
0x1800382ea  mov     r14d, r8d
0x1800382ed  mov     r15, rdx
0x1800382f0  mov     rdi, rcx
0x1800382f3  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x1800382fa  mov     r8d, 0D12h; int
0x180038300  lea     rcx, [rbp+57h+var_C8]; this
0x180038304  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180038309  xor     eax, eax
0x18003830b  lea     rdx, [rbp+57h+var_98]
0x18003830f  mov     [rbp+57h+var_98], eax
0x180038312  mov     esi, eax
0x180038314  mov     [rsp+130h+var_E0], rax
0x180038319  mov     r13d, eax
0x18003831c  mov     [rbp+57h+var_78], rax
0x180038320  mov     r12d, eax
0x180038323  mov     [rbp+57h+var_7C], eax
0x180038326  mov     rcx, r15
0x180038329  mov     [rbp+57h+var_B0], rax
0x18003832d  mov     [rbp+57h+var_88], rax
0x180038331  mov     [rbp+57h+var_A8], eax
0x180038334  mov     [rbp+57h+var_B8], eax
0x180038337  mov     [rbp+57h+var_A0], rax
0x18003833b  mov     [rbp+57h+var_80], eax
0x18003833e  mov     [rbp+57h+var_70], rax
0x180038342  mov     rax, [r15]
0x180038345  mov     rax, [rax+28h]
0x180038349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003834e  mov     ebx, eax
0x180038350  test    eax, eax
0x180038352  jns     short loc_1800383CC
0x180038354  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003835b  test    rcx, rcx
0x18003835e  jnz     short loc_18003836C
0x180038360  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180038365  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003836c  cmp     [rcx+8], sil
0x180038370  jz      short loc_180038397
0x180038372  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038377  cmp     [rax+7CCh], ebx
0x18003837d  jz      short loc_180038397
0x18003837f  mov     r9d, ebx; int
0x180038382  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x180038389  mov     r8d, 0D2Bh; int
0x18003838f  mov     rcx, rax; this
0x180038392  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038397  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003839e  jb      loc_180039AA9
0x1800383a4  mov     edx, 13Bh
0x1800383a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383b0  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x1800383b7  mov     r9, rdi
0x1800383ba  mov     dword ptr [rsp+130h+ppEvent], ebx
0x1800383be  mov     rcx, [rcx+10h]
0x1800383c2  call    WPP_SF_qD
0x1800383c7  jmp     loc_180039AA9
0x1800383cc  lea     rcx, [rdi+460h]; this
0x1800383d3  lea     rdx, [rsp+130h+var_E0]; unsigned __int64 *
0x1800383d8  call    ?GetCurrentPosition@CMFByteStreamSourceReader@@QEAAJPEA_K@Z; CMFByteStreamSourceReader::GetCurrentPosition(unsigned __int64 *)
0x1800383dd  mov     ebx, eax
0x1800383df  test    eax, eax
0x1800383e1  jns     short loc_18003843D
0x1800383e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800383ea  test    rcx, rcx
0x1800383ed  jnz     short loc_1800383FB
0x1800383ef  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800383f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800383fb  cmp     [rcx+8], sil
0x1800383ff  jz      short loc_180038426
0x180038401  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038406  cmp     [rax+7CCh], ebx
0x18003840c  jz      short loc_180038426
0x18003840e  mov     r9d, ebx; int
0x180038411  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x180038418  mov     r8d, 0D2Ch; int
0x18003841e  mov     rcx, rax; this
0x180038421  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038426  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003842d  jb      loc_180039AA9
0x180038433  mov     edx, 13Ch
0x180038438  jmp     loc_1800383A9
0x18003843d  cmp     [rdi+448h], rsi
0x180038444  jz      loc_1800385AB
0x18003844a  lea     r14, [rdi+460h]
0x180038451  xor     edx, edx; int
0x180038453  mov     rcx, r14; this
0x180038456  call    ?ConfigureDataBuffering@CMFByteStreamSourceReader@@QEAAJH@Z; CMFByteStreamSourceReader::ConfigureDataBuffering(int)
0x18003845b  mov     ebx, eax
0x18003845d  test    eax, eax
0x18003845f  jns     short loc_1800384BB
0x180038461  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038468  test    rcx, rcx
0x18003846b  jnz     short loc_180038479
0x18003846d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180038472  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180038479  cmp     [rcx+8], sil
0x18003847d  jz      short loc_1800384A4
0x18003847f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038484  cmp     [rax+7CCh], ebx
0x18003848a  jz      short loc_1800384A4
0x18003848c  mov     r9d, ebx; int
0x18003848f  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x180038496  mov     r8d, 0D37h; int
0x18003849c  mov     rcx, rax; this
0x18003849f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800384a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800384ab  jb      loc_180039AA9
0x1800384b1  mov     edx, 13Dh
0x1800384b6  jmp     loc_1800383A9
0x1800384bb  mov     rdx, [rdi+448h]
0x1800384c2  xor     r8d, r8d; int *
0x1800384c5  mov     rcx, r14; this
0x1800384c8  mov     rdx, [rdx+8]; unsigned __int64
0x1800384cc  call    ?SetCurrentPosition@CMFByteStreamSourceReader@@QEAAJ_KPEAH@Z; CMFByteStreamSourceReader::SetCurrentPosition(unsigned __int64,int *)
0x1800384d1  mov     ebx, eax
0x1800384d3  test    eax, eax
0x1800384d5  jns     short loc_180038531
0x1800384d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800384de  test    rcx, rcx
0x1800384e1  jnz     short loc_1800384EF
0x1800384e3  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800384e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800384ef  cmp     [rcx+8], sil
0x1800384f3  jz      short loc_18003851A
0x1800384f5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800384fa  cmp     [rax+7CCh], ebx
0x180038500  jz      short loc_18003851A
0x180038502  mov     r9d, ebx; int
0x180038505  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x18003850c  mov     r8d, 0D39h; int
0x180038512  mov     rcx, rax; this
0x180038515  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003851a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038521  jb      loc_180039AA9
0x180038527  mov     edx, 13Eh
0x18003852c  jmp     loc_1800383A9
0x180038531  mov     r8d, [rdi+450h]; unsigned int
0x180038538  lea     rdx, [rdi+2B8h]; struct IMFAsyncCallback *
0x18003853f  mov     rcx, r14; this
0x180038542  call    ?BeginReadData@CMFByteStreamSourceReader@@QEAAJPEAUIMFAsyncCallback@@K@Z; CMFByteStreamSourceReader::BeginReadData(IMFAsyncCallback *,ulong)
0x180038547  mov     ebx, eax
0x180038549  test    eax, eax
0x18003854b  jns     loc_180039AA9
0x180038551  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038558  test    rcx, rcx
0x18003855b  jnz     short loc_180038569
0x18003855d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180038562  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180038569  cmp     [rcx+8], sil
0x18003856d  jz      short loc_180038594
0x18003856f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038574  cmp     [rax+7CCh], ebx
0x18003857a  jz      short loc_180038594
0x18003857c  mov     r9d, ebx; int
0x18003857f  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x180038586  mov     r8d, 0D3Ah; int
0x18003858c  mov     rcx, rax; this
0x18003858f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038594  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003859b  jb      loc_180039AA9
0x1800385a1  mov     edx, 13Fh
0x1800385a6  jmp     loc_1800383A9
0x1800385ab  mov     r9, [rsp+130h+var_E0]; unsigned __int64
0x1800385b0  mov     r8d, r14d; unsigned int
0x1800385b3  mov     rcx, rdi; this
0x1800385b6  call    ?ShouldDropData@CMFByteStreamMediaSource@@AEAAHPEAUIMFMediaBuffer@@K_K@Z; CMFByteStreamMediaSource::ShouldDropData(IMFMediaBuffer *,ulong,unsigned __int64)
0x1800385bb  test    eax, eax
0x1800385bd  jz      short loc_180038638
0x1800385bf  cmp     dword ptr [rdi+454h], 2
0x1800385c6  jz      loc_180039AA9
0x1800385cc  mov     rcx, rdi; this
0x1800385cf  call    ?ServiceOutstandingSampleRequests@CMFByteStreamMediaSource@@AEAAJXZ; CMFByteStreamMediaSource::ServiceOutstandingSampleRequests(void)
0x1800385d4  mov     ebx, eax
0x1800385d6  test    eax, eax
0x1800385d8  jns     loc_180039AA9
0x1800385de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800385e5  test    rcx, rcx
0x1800385e8  jnz     short loc_1800385F6
0x1800385ea  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800385ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800385f6  cmp     [rcx+8], sil
0x1800385fa  jz      short loc_180038621
0x1800385fc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038601  cmp     [rax+7CCh], ebx
0x180038607  jz      short loc_180038621
0x180038609  mov     r9d, ebx; int
0x18003860c  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x180038613  mov     r8d, 0D46h; int
0x180038619  mov     rcx, rax; this
0x18003861c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038621  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038628  jb      loc_180039AA9
0x18003862e  mov     edx, 140h
0x180038633  jmp     loc_1800383A9
0x180038638  mov     r14d, [rbp+57h+var_98]
0x18003863c  cmp     [rsp+130h+var_E0], r14
0x180038641  jnb     short loc_1800386A2
0x180038643  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003864a  mov     ebx, 8000FFFFh
0x18003864f  test    rcx, rcx
0x180038652  jnz     short loc_180038660
0x180038654  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180038659  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180038660  cmp     [rcx+8], sil
0x180038664  jz      short loc_18003868B
0x180038666  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003866b  cmp     [rax+7CCh], ebx
0x180038671  jz      short loc_18003868B
0x180038673  mov     r9d, ebx; int
0x180038676  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x18003867d  mov     r8d, 0D4Eh; int
0x180038683  mov     rcx, rax; this
0x180038686  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003868b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038692  jb      loc_180039AA9
0x180038698  mov     edx, 141h
0x18003869d  jmp     loc_1800383A9
0x1800386a2  mov     rcx, [rdi+458h]; this
0x1800386a9  mov     r8, [rdi+4D8h]; struct _MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE *
0x1800386b0  mov     eax, [rcx+0D0h]
0x1800386b6  mov     edx, eax; unsigned int
0x1800386b8  mov     [rbp+57h+var_B4], eax
0x1800386bb  call    ?GetStreamBufferState@CMFMediaStreamArray@@QEAAJIPEAU_MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE@@@Z; CMFMediaStreamArray::GetStreamBufferState(uint,_MF_MEDIASOURCE_PLUGIN_STREAM_BUFFER_STATE *)
0x1800386c0  mov     ebx, eax
0x1800386c2  test    eax, eax
0x1800386c4  jns     short loc_180038720
0x1800386c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800386cd  test    rcx, rcx
0x1800386d0  jnz     short loc_1800386DE
0x1800386d2  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800386d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800386de  cmp     [rcx+8], sil
0x1800386e2  jz      short loc_180038709
0x1800386e4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800386e9  cmp     [rax+7CCh], ebx
0x1800386ef  jz      short loc_180038709
0x1800386f1  mov     r9d, ebx; int
0x1800386f4  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x1800386fb  mov     r8d, 0D5Bh; int
0x180038701  mov     rcx, rax; this
0x180038704  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038709  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038710  jb      loc_180039AA9
0x180038716  mov     edx, 142h
0x18003871b  jmp     loc_1800383A9
0x180038720  mov     rbx, [rsp+130h+var_E0]
0x180038725  lea     rdx, [rbp+57h+var_C4]; int *
0x180038729  sub     rbx, r14
0x18003872c  mov     rcx, rdi; this
0x18003872f  xor     r14d, r14d
0x180038732  mov     [rbp+57h+var_60], rbx
0x180038736  mov     [rbp+57h+var_C4], r14d
0x18003873a  call    ?IsEndOfDataSegment@CMFByteStreamMediaSource@@AEAAJPEAH@Z; CMFByteStreamMediaSource::IsEndOfDataSegment(int *)
0x18003873f  cmp     [rbp+57h+var_C4], r14d
0x180038743  jz      short loc_18003874D
0x180038745  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFEh
0x18003874d  mov     rcx, [rdi+398h]
0x180038754  mov     r8, rbx
0x180038757  mov     r9d, [rbp+57h+var_B4]
0x18003875b  mov     rdx, r15
0x18003875e  mov     rax, [rcx]
0x180038761  mov     r10, [rax+38h]
0x180038765  lea     rax, [rbp+57h+var_78]
0x180038769  mov     [rsp+130h+var_108], rax
0x18003876e  mov     rax, [rdi+4D8h]
0x180038775  mov     [rsp+130h+ppEvent], rax
0x18003877a  mov     rax, r10
0x18003877d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038782  mov     ebx, eax
0x180038784  test    eax, eax
0x180038786  jns     short loc_1800387E2
0x180038788  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003878f  test    rcx, rcx
0x180038792  jnz     short loc_1800387A0
0x180038794  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180038799  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800387a0  cmp     [rcx+8], r14b
0x1800387a4  jz      short loc_1800387CB
0x1800387a6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800387ab  cmp     [rax+7CCh], ebx
0x1800387b1  jz      short loc_1800387CB
0x1800387b3  mov     r9d, ebx; int
0x1800387b6  lea     rdx, aCmfbytestreamm_64; "CMFByteStreamMediaSource::OnByteStreamR"...
0x1800387bd  mov     r8d, 0D6Bh; int
0x1800387c3  mov     rcx, rax; this
0x1800387c6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800387cb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800387d2  jb      loc_180039AA9
  ... truncated ...
```
