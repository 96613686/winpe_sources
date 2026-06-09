# MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample(IMFSample * *,bool)

- ea: `0x1800376e0`
- end: `0x1800383bc`
- name: `?TransformSample@MkvMfStreamVideoAV1@MkvMfSourceLib@@UEAAJPEAPEAUIMFSample@@_N@Z`
- size: `3292`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStreamVideoAV1 *__hidden this, struct IMFSample **, bool)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1800036c5`
- `0x180005ab8`
- `0x1800097f0`
- `0x1800098b8`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180026ac0`
- `0x1800376e0`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003773f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800377f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003789e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800379cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037ac3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037bb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037cad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037da4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037ec3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037fb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800380a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038194`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038287`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003773f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800377f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003789e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800379cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037ac3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037bb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037cad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037da4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037ec3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037fb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800380a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038194`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038287`
- `MFPlat!MFCreateMemoryBuffer` at `0x180037c91`
- `MFPlat!MFCreateMemoryBuffer` at `0x180037c91`

## pseudocode

```c
__int64 __fastcall MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample(
        MkvMfSourceLib::MkvMfStreamVideoAV1 *this,
        struct IMFSample **a2,
        bool a3)
{
  HRESULT v6; // edi
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  struct IMFSample *v17; // rbx
  HRESULT (__stdcall *ConvertToContiguousBuffer)(IMFSample *, IMFMediaBuffer **); // rdi
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  DWORD v28; // r15d
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  IMFMediaBuffer *ppBuffer; // [rsp+30h] [rbp-50h] BYREF
  __int64 v52; // [rsp+38h] [rbp-48h] BYREF
  void *v53; // [rsp+40h] [rbp-40h] BYREF
  void *Src; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v55[5]; // [rsp+50h] [rbp-30h] BYREF
  char v56; // [rsp+78h] [rbp-8h]
  char v57; // [rsp+C8h] [rbp+48h] BYREF
  size_t Size; // [rsp+D8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v57,
    "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample",
    934);
  if ( a2 )
  {
    if ( *a2 )
    {
      v6 = MkvMfSourceLib::MkvMfStream::TransformSample(this, a2, a3);
      if ( v6 >= 0 )
      {
        if ( a3 && *((_QWORD *)this + 57) && *((_QWORD *)this + 58) )
        {
          v17 = *a2;
          v55[0] = v17;
          Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(v55);
          v52 = 0;
          Src = 0;
          LODWORD(Size) = 0;
          ppBuffer = 0;
          v53 = 0;
          v55[1] = &Src;
          v55[2] = &v52;
          v55[3] = &v53;
          v55[4] = &ppBuffer;
          v56 = 1;
          ConvertToContiguousBuffer = v17->lpVtbl->ConvertToContiguousBuffer;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
          v6 = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *))ConvertToContiguousBuffer)(v17, &v52);
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(__int64, void **, _QWORD, size_t *))(*(_QWORD *)v52 + 24LL))(
                   v52,
                   &Src,
                   0,
                   &Size);
            if ( v6 >= 0 )
            {
              if ( (unsigned __int64)(unsigned int)(-1 - Size) >= *((_QWORD *)this + 58) )
              {
                v28 = Size + *((_DWORD *)this + 116);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
                v6 = MFCreateMemoryBuffer(v28, &ppBuffer);
                if ( v6 >= 0 )
                {
                  v6 = ((__int64 (__fastcall *)(IMFMediaBuffer *, void **, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
                         ppBuffer,
                         &v53,
                         0,
                         0);
                  if ( v6 >= 0 )
                  {
                    memcpy_0(v53, *((const void **)this + 57), *((_QWORD *)this + 58));
                    memcpy_0((char *)v53 + *((_QWORD *)this + 58), Src, (unsigned int)Size);
                    v6 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
                           ppBuffer,
                           v28);
                    if ( v6 >= 0 )
                    {
                      v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v52 + 32LL))(v52);
                      if ( v6 >= 0 )
                      {
                        Src = 0;
                        v6 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                        if ( v6 >= 0 )
                        {
                          v53 = 0;
                          v6 = ((__int64 (__fastcall *)(struct IMFSample *))v17->lpVtbl->RemoveAllBuffers)(v17);
                          if ( v6 >= 0 )
                          {
                            v6 = ((__int64 (__fastcall *)(struct IMFSample *, IMFMediaBuffer *))v17->lpVtbl->AddBuffer)(
                                   v17,
                                   ppBuffer);
                            if ( v6 >= 0 )
                            {
                              if ( Src )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 32LL))(v52);
                              if ( v53 )
                                ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                            }
                            else
                            {
                              v47 = (__int64 *)CallStackTracing::s_wpInstance;
                              if ( !CallStackTracing::s_wpInstance )
                              {
                                v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                                CallStackTracing::s_wpInstance = v48;
                                if ( v48
                                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(
                                       v48,
                                       2032) )
                                {
                                  v47 = (__int64 *)CallStackTracing::s_wpInstance;
                                }
                                else
                                {
                                  v47 = &qword_1800D6F70;
                                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                                }
                              }
                              if ( *((_BYTE *)v47 + 8) )
                              {
                                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
                                if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
                                  CallStackContext::TraceFailure(
                                    ThreadRelativeContext,
                                    "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample",
                                    992,
                                    v6);
                              }
                              if ( g_wppLevels )
                                WPP_SF_qD(
                                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                                  146,
                                  &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                                  this,
                                  v6);
                              if ( Src )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 32LL))(v52);
                              if ( v53 )
                                ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                            }
                          }
                          else
                          {
                            v44 = (__int64 *)CallStackTracing::s_wpInstance;
                            if ( !CallStackTracing::s_wpInstance )
                            {
                              v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                              CallStackTracing::s_wpInstance = v45;
                              if ( v45
                                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(
                                     v45,
                                     2032) )
                              {
                                v44 = (__int64 *)CallStackTracing::s_wpInstance;
                              }
                              else
                              {
                                v44 = &qword_1800D6F70;
                                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                              }
                            }
                            if ( *((_BYTE *)v44 + 8) )
                            {
                              v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
                              if ( *((_DWORD *)v46 + 499) != v6 )
                                CallStackContext::TraceFailure(
                                  v46,
                                  "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample",
                                  991,
                                  v6);
                            }
                            if ( g_wppLevels )
                              WPP_SF_qD(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                145,
                                &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                                this,
                                v6);
                            if ( Src )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 32LL))(v52);
                            if ( v53 )
                              ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                          }
                        }
                        else
                        {
                          v41 = (__int64 *)CallStackTracing::s_wpInstance;
                          if ( !CallStackTracing::s_wpInstance )
                          {
                            v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                            CallStackTracing::s_wpInstance = v42;
                            if ( v42
                              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(
                                   v42,
                                   2032) )
                            {
                              v41 = (__int64 *)CallStackTracing::s_wpInstance;
                            }
                            else
                            {
                              v41 = &qword_1800D6F70;
                              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                            }
                          }
                          if ( *((_BYTE *)v41 + 8) )
                          {
                            v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
                            if ( *((_DWORD *)v43 + 499) != v6 )
                              CallStackContext::TraceFailure(
                                v43,
                                "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample",
                                987,
                                v6);
                          }
                          if ( g_wppLevels )
                            WPP_SF_qD(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              144,
                              &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                              this,
                              v6);
                          if ( Src )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 32LL))(v52);
                          if ( v53 )
                            ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                        }
                      }
                      else
                      {
                        v38 = (__int64 *)CallStackTracing::s_wpInstance;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                          CallStackTracing::s_wpInstance = v39;
                          if ( v39
                            && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(
                                 v39,
                                 2032) )
                          {
                            v38 = (__int64 *)CallStackTracing::s_wpInstance;
                          }
                          else
                          {
                            v38 = &qword_1800D6F70;
                            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                          }
                        }
                        if ( *((_BYTE *)v38 + 8) )
                        {
                          v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
                          if ( *((_DWORD *)v40 + 499) != v6 )
                            CallStackContext::TraceFailure(
                              v40,
                              "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample",
                              985,
                              v6);
                        }
                        if ( g_wppLevels )
                          WPP_SF_qD(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            143,
                            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                            this,
                            v6);
                        if ( Src )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 32LL))(v52);
                        if ( v53 )
                          ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                      }
                    }
                    else
                    {
                      v35 = (__int64 *)CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                        CallStackTracing::s_wpInstance = v36;
                        if ( v36
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(
                               v36,
                               2032) )
                        {
                          v35 = (__int64 *)CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v35 = &qword_1800D6F70;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                        }
                      }
                      if ( *((_BYTE *)v35 + 8) )
                      {
                        v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
                        if ( *((_DWORD *)v37 + 499) != v6 )
                          CallStackContext::TraceFailure(
                            v37,
                            "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample",
                            982,
                            v6);
                      }
                      if ( g_wppLevels )
                        WPP_SF_qD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          142,
                          &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                          this,
                          v6);
                      if ( Src )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 32LL))(v52);
                      if ( v53 )
                        ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                    }
                  }
                  else
                  {
                    v32 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                      CallStackTracing::s_wpInstance = v33;
                      if ( v33
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(
                             v33,
                             2032) )
                      {
                        v32 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v32 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                      }
                    }
                    if ( *((_BYTE *)v32 + 8) )
                    {
                      v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
                      if ( *((_DWORD *)v34 + 499) != v6 )
                        CallStackContext::TraceFailure(
                          v34,
                          "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample",
                          977,
                          v6);
                    }
                    if ( g_wppLevels )
                      WPP_SF_qD(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        141,
                        &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                        this,
                        v6);
                    if ( Src )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 32LL))(v52);
                    if ( v53 )
                      ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                  }
                }
                else
                {
                  v29 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                    CallStackTracing::s_wpInstance = v30;
                    if ( v30
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
                    {
                      v29 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v29 = &qword_1800D6F70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                    }
                  }
                  if ( *((_BYTE *)v29 + 8) )
                  {
                    v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
                    if ( *((_DWORD *)v31 + 499) != v6 )
                      CallStackContext::TraceFailure(
                        v31,
                        "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample",
                        976,
                        v6);
                  }
                  if ( g_wppLevels )
                    WPP_SF_qD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      140,
                      &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                      this,
                      v6);
                  if ( Src )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 32LL))(v52);
                  if ( v53 )
                    ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                }
              }
              else
              {
                v6 = -1072875842;
                v25 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v26;
                  if ( v26
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
                  {
                    v25 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v25 = &qword_1800D6F70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                  }
                }
                if ( *((_BYTE *)v25 + 8) )
                {
                  v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
                  if ( *((_DWORD *)v27 + 499) != -1072875842 )
                    CallStackContext::TraceFailure(
                      v27,
                      "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample",
                      971,
                      -1072875842);
                }
                if ( g_wppLevels )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    139,
                    &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                    this,
                    -1072875842);
                if ( Src )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 32LL))(v52);
                if ( v53 )
                  ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
              }
            }
            else
            {
              v22 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                CallStackTracing::s_wpInstance = v23;
                if ( v23
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
                {
                  v22 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v22 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                }
              }
              if ( *((_BYTE *)v22 + 8) )
              {
                v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
                if ( *((_DWORD *)v24 + 499) != v6 )
                  CallStackContext::TraceFailure(v24, "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample", 965, v6);
              }
              if ( g_wppLevels )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  138,
                  &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                  this,
                  v6);
              if ( Src )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 32LL))(v52);
              if ( v53 )
                ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
            }
          }
          else
          {
            v19 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v20;
              if ( v20
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
              {
                v19 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v19 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v19 + 8) )
            {
              v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
              if ( *((_DWORD *)v21 + 499) != v6 )
                CallStackContext::TraceFailure(v21, "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample", 964, v6);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                137,
                &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                this,
                v6);
            if ( Src )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 32LL))(v52);
            if ( v53 )
              ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v55);
        }
      }
      else
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v15;
          if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
          {
            v14 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v14 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v14 + 8) )
        {
          v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
          if ( *((_DWORD *)v16 + 499) != v6 )
            CallStackContext::TraceFailure(v16, "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample", 937, v6);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            136,
            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
            this,
            v6);
      }
    }
    else
    {
      v6 = -2147467261;
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v13 + 499) != -2147467261 )
          CallStackContext::TraceFailure(v13, "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample", 935, -2147467261);
      }
      if ( g_wppLevels )
      {
        v10 = 135;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v6 = -2147467261;
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v9 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v9, "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample", 934, -2147467261);
    }
    if ( g_wppLevels )
    {
      v10 = 134;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
        this,
        -2147467261);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v57);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800376e0  mov     [rsp-38h+arg_0], rbx
0x1800376e5  push    rbp
0x1800376e6  push    rsi
0x1800376e7  push    rdi
0x1800376e8  push    r12
0x1800376ea  push    r13
0x1800376ec  push    r14
0x1800376ee  push    r15
0x1800376f0  mov     rbp, rsp
0x1800376f3  sub     rsp, 80h
0x1800376fa  mov     sil, r8b
0x1800376fd  mov     rbx, rdx
0x180037700  mov     r14, rcx
0x180037703  mov     r15d, 3A6h
0x180037709  mov     r8d, r15d; int
0x18003770c  lea     r13, aMkvmfsourcelib_55; "MkvMfSourceLib::MkvMfStreamVideoAV1::Tr"...
0x180037713  mov     rdx, r13; char *
0x180037716  lea     rcx, [rbp+arg_8]; this
0x18003771a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003771f  nop
0x180037720  xor     r12d, r12d
0x180037723  test    rbx, rbx
0x180037726  jnz     loc_1800377DC
0x18003772c  mov     ebx, 80004003h
0x180037731  mov     edi, ebx
0x180037733  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003773a  test    rcx, rcx
0x18003773d  jnz     short loc_180037780
0x18003773f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037745  mov     rcx, rax
0x180037748  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003774f  test    rax, rax
0x180037752  jz      short loc_180037772
0x180037754  mov     rax, [rax]
0x180037757  mov     edx, 7F0h
0x18003775c  mov     rax, [rax+8]
0x180037760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037765  test    eax, eax
0x180037767  jz      short loc_180037772
0x180037769  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037770  jmp     short loc_180037780
0x180037772  lea     rcx, qword_1800D6F70; this
0x180037779  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037780  cmp     [rcx+8], r12b
0x180037784  jz      short loc_1800377A4
0x180037786  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003778b  cmp     [rax+7CCh], ebx
0x180037791  jz      short loc_1800377A4
0x180037793  mov     r9d, ebx; int
0x180037796  mov     r8d, r15d; int
0x180037799  mov     rdx, r13; char *
0x18003779c  mov     rcx, rax; this
0x18003779f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800377a4  mov     sil, 1
0x1800377a7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800377ae  jb      loc_180038396
0x1800377b4  mov     edx, 86h
0x1800377b9  mov     [rsp+80h+var_60], ebx
0x1800377bd  mov     r9, r14
0x1800377c0  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x1800377c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800377ce  mov     rcx, [rcx+10h]
0x1800377d2  call    WPP_SF_qD
0x1800377d7  jmp     loc_180038396
0x1800377dc  cmp     [rbx], r12
0x1800377df  jnz     loc_18003787A
0x1800377e5  mov     ebx, 80004003h
0x1800377ea  mov     edi, ebx
0x1800377ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800377f3  test    rcx, rcx
0x1800377f6  jnz     short loc_180037839
0x1800377f8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800377fe  mov     rcx, rax
0x180037801  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037808  test    rax, rax
0x18003780b  jz      short loc_18003782B
0x18003780d  mov     rax, [rax]
0x180037810  mov     edx, 7F0h
0x180037815  mov     rax, [rax+8]
0x180037819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003781e  test    eax, eax
0x180037820  jz      short loc_18003782B
0x180037822  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037829  jmp     short loc_180037839
0x18003782b  lea     rcx, qword_1800D6F70; this
0x180037832  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037839  cmp     [rcx+8], r12b
0x18003783d  jz      short loc_180037860
0x18003783f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037844  cmp     [rax+7CCh], ebx
0x18003784a  jz      short loc_180037860
0x18003784c  mov     r9d, ebx; int
0x18003784f  mov     r8d, 3A7h; int
0x180037855  mov     rdx, r13; char *
0x180037858  mov     rcx, rax; this
0x18003785b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037860  mov     sil, 1
0x180037863  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18003786a  jb      loc_180038396
0x180037870  mov     edx, 87h
0x180037875  jmp     loc_1800377B9
0x18003787a  mov     r8b, sil; bool
0x18003787d  mov     rdx, rbx; struct IMFSample **
0x180037880  mov     rcx, r14; this
0x180037883  call    ?TransformSample@MkvMfStream@MkvMfSourceLib@@UEAAJPEAPEAUIMFSample@@_N@Z; MkvMfSourceLib::MkvMfStream::TransformSample(IMFSample * *,bool)
0x180037888  mov     edi, eax
0x18003788a  test    eax, eax
0x18003788c  jns     loc_180037924
0x180037892  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037899  test    rcx, rcx
0x18003789c  jnz     short loc_1800378DF
0x18003789e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800378a4  mov     rcx, rax
0x1800378a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800378ae  test    rax, rax
0x1800378b1  jz      short loc_1800378D1
0x1800378b3  mov     rax, [rax]
0x1800378b6  mov     edx, 7F0h
0x1800378bb  mov     rax, [rax+8]
0x1800378bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800378c4  test    eax, eax
0x1800378c6  jz      short loc_1800378D1
0x1800378c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800378cf  jmp     short loc_1800378DF
0x1800378d1  lea     rcx, qword_1800D6F70; this
0x1800378d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800378df  cmp     [rcx+8], r12b
0x1800378e3  jz      short loc_180037906
0x1800378e5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800378ea  cmp     [rax+7CCh], edi
0x1800378f0  jz      short loc_180037906
0x1800378f2  mov     r9d, edi; int
0x1800378f5  mov     r8d, 3A9h; int
0x1800378fb  mov     rdx, r13; char *
0x1800378fe  mov     rcx, rax; this
0x180037901  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037906  mov     sil, 1
0x180037909  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180037910  jb      loc_180038396
0x180037916  mov     edx, 88h
0x18003791b  mov     [rsp+80h+var_60], edi
0x18003791f  jmp     loc_1800377BD
0x180037924  test    sil, sil
0x180037927  jz      loc_180038396
0x18003792d  cmp     [r14+1C8h], r12
0x180037934  jz      loc_180038396
0x18003793a  cmp     [r14+1D0h], r12
0x180037941  jbe     loc_180038396
0x180037947  mov     rbx, [rbx]
0x18003794a  mov     [rbp+var_30], rbx
0x18003794e  lea     rcx, [rbp+var_30]
0x180037952  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x180037957  nop
0x180037958  mov     [rbp+var_48], r12
0x18003795c  mov     [rbp+Src], r12
0x180037960  mov     dword ptr [rbp+Size], r12d
0x180037964  mov     [rbp+ppBuffer], r12
0x180037968  mov     [rbp+var_40], r12
0x18003796c  lea     rax, [rbp+Src]
0x180037970  mov     [rbp+var_28], rax
0x180037974  lea     rax, [rbp+var_48]
0x180037978  mov     [rbp+var_20], rax
0x18003797c  lea     rax, [rbp+var_40]
0x180037980  mov     [rbp+var_18], rax
0x180037984  lea     rax, [rbp+ppBuffer]
0x180037988  mov     [rbp+var_10], rax
0x18003798c  mov     sil, 1
0x18003798f  mov     [rbp+var_8], sil
0x180037993  mov     rax, [rbx]
0x180037996  mov     rdi, [rax+148h]
0x18003799d  lea     rcx, [rbp+var_48]
0x1800379a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800379a6  lea     rdx, [rbp+var_48]
0x1800379aa  mov     rcx, rbx
0x1800379ad  mov     rax, rdi
0x1800379b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800379b5  mov     edi, eax
0x1800379b7  test    eax, eax
0x1800379b9  jns     loc_180037A92
0x1800379bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800379c6  test    rcx, rcx
0x1800379c9  jnz     short loc_180037A0C
0x1800379cb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800379d1  mov     rcx, rax
0x1800379d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800379db  test    rax, rax
0x1800379de  jz      short loc_1800379FE
0x1800379e0  mov     rax, [rax]
0x1800379e3  mov     edx, 7F0h
0x1800379e8  mov     rax, [rax+8]
0x1800379ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800379f1  test    eax, eax
0x1800379f3  jz      short loc_1800379FE
0x1800379f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800379fc  jmp     short loc_180037A0C
0x1800379fe  lea     rcx, qword_1800D6F70; this
0x180037a05  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037a0c  cmp     [rcx+8], r12b
0x180037a10  jz      short loc_180037A33
0x180037a12  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037a17  cmp     [rax+7CCh], edi
0x180037a1d  jz      short loc_180037A33
0x180037a1f  mov     r9d, edi; int
0x180037a22  mov     r8d, 3C4h; int
0x180037a28  mov     rdx, r13; char *
0x180037a2b  mov     rcx, rax; this
0x180037a2e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037a33  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180037a3a  jb      short loc_180037A60
0x180037a3c  mov     edx, 89h
0x180037a41  mov     [rsp+80h+var_60], edi
0x180037a45  mov     r9, r14
0x180037a48  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x180037a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037a56  mov     rcx, [rcx+10h]
0x180037a5a  call    WPP_SF_qD
0x180037a5f  nop
0x180037a60  cmp     [rbp+Src], r12
0x180037a64  jz      short loc_180037A76
0x180037a66  mov     rcx, [rbp+var_48]
0x180037a6a  mov     rax, [rcx]
0x180037a6d  mov     rax, [rax+20h]
0x180037a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a76  cmp     [rbp+var_40], r12
0x180037a7a  jz      short loc_180037A8D
0x180037a7c  mov     rcx, [rbp+ppBuffer]
0x180037a80  mov     rax, [rcx]
0x180037a83  mov     rax, [rax+20h]
0x180037a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a8c  nop
0x180037a8d  jmp     loc_180038378
0x180037a92  mov     rcx, [rbp+var_48]
0x180037a96  mov     rax, [rcx]
0x180037a99  lea     r9, [rbp+Size]
0x180037a9d  xor     r8d, r8d
0x180037aa0  lea     rdx, [rbp+Src]
0x180037aa4  mov     rax, [rax+18h]
0x180037aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037aad  mov     edi, eax
0x180037aaf  test    eax, eax
0x180037ab1  jns     loc_180037B8A
0x180037ab7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037abe  test    rcx, rcx
0x180037ac1  jnz     short loc_180037B04
0x180037ac3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037ac9  mov     rcx, rax
0x180037acc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037ad3  test    rax, rax
0x180037ad6  jz      short loc_180037AF6
0x180037ad8  mov     rax, [rax]
0x180037adb  mov     edx, 7F0h
0x180037ae0  mov     rax, [rax+8]
0x180037ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037ae9  test    eax, eax
0x180037aeb  jz      short loc_180037AF6
0x180037aed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037af4  jmp     short loc_180037B04
0x180037af6  lea     rcx, qword_1800D6F70; this
0x180037afd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037b04  cmp     [rcx+8], r12b
0x180037b08  jz      short loc_180037B2B
0x180037b0a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037b0f  cmp     [rax+7CCh], edi
0x180037b15  jz      short loc_180037B2B
0x180037b17  mov     r9d, edi; int
0x180037b1a  mov     r8d, 3C5h; int
0x180037b20  mov     rdx, r13; char *
0x180037b23  mov     rcx, rax; this
0x180037b26  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037b2b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180037b32  jb      short loc_180037B58
0x180037b34  mov     edx, 8Ah
0x180037b39  mov     [rsp+80h+var_60], edi
0x180037b3d  mov     r9, r14
0x180037b40  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x180037b47  mov     rcx, cs:WPP_GLOBAL_Control
0x180037b4e  mov     rcx, [rcx+10h]
0x180037b52  call    WPP_SF_qD
0x180037b57  nop
0x180037b58  cmp     [rbp+Src], r12
0x180037b5c  jz      short loc_180037B6E
0x180037b5e  mov     rcx, [rbp+var_48]
0x180037b62  mov     rax, [rcx]
0x180037b65  mov     rax, [rax+20h]
0x180037b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b6e  cmp     [rbp+var_40], r12
0x180037b72  jz      short loc_180037B85
0x180037b74  mov     rcx, [rbp+ppBuffer]
0x180037b78  mov     rax, [rcx]
0x180037b7b  mov     rax, [rax+20h]
0x180037b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b84  nop
0x180037b85  jmp     loc_180038378
0x180037b8a  or      eax, 0FFFFFFFFh
0x180037b8d  mov     ecx, dword ptr [rbp+Size]
0x180037b90  sub     eax, ecx
0x180037b92  cmp     rax, [r14+1D0h]
0x180037b99  jnb     loc_180037C77
0x180037b9f  mov     edi, 0C00D36BEh
0x180037ba4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
