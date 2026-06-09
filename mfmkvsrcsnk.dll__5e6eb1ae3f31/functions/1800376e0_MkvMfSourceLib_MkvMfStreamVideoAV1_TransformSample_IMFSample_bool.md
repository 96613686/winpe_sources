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
// Hidden C++ exception states: #wind=6
__int64 __fastcall MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample(
        MkvMfSourceLib::MkvMfStreamVideoAV1 *this,
        struct IMFSample **a2,
        char a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // edi
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  struct IMFSample *v23; // rbx
  HRESULT (__stdcall *ConvertToContiguousBuffer)(IMFSample *, IMFMediaBuffer **); // rdi
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  DWORD v40; // r15d
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 *v62; // rcx
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 v67; // r9
  __int64 *v68; // rcx
  CallStackTracing *v69; // rax
  struct CallStackContext *v70; // rax
  __int64 v71; // rdx
  __int64 v72; // r8
  __int64 v73; // r9
  __int64 *v74; // rcx
  CallStackTracing *v75; // rax
  struct CallStackContext *v76; // rax
  __int64 v77; // rdx
  __int64 v78; // r8
  __int64 v79; // r9
  __int64 *v80; // rcx
  CallStackTracing *v81; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  IMFMediaBuffer *ppBuffer; // [rsp+30h] [rbp-50h] BYREF
  __int64 v85; // [rsp+38h] [rbp-48h] BYREF
  void *v86; // [rsp+40h] [rbp-40h] BYREF
  void *Src; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v88[5]; // [rsp+50h] [rbp-30h] BYREF
  char v89; // [rsp+78h] [rbp-8h]
  char v90; // [rsp+C8h] [rbp+48h] BYREF
  size_t Size; // [rsp+D8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v90,
    "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample",
    934);
  if ( a2 )
  {
    if ( *a2 )
    {
      v9 = MkvMfSourceLib::MkvMfStream::TransformSample(this, a2);
      if ( v9 >= 0 )
      {
        if ( a3 && *((_QWORD *)this + 57) && *((_QWORD *)this + 58) )
        {
          v23 = *a2;
          v88[0] = v23;
          Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(v88);
          v85 = 0;
          Src = 0;
          LODWORD(Size) = 0;
          ppBuffer = 0;
          v86 = 0;
          v88[1] = &Src;
          v88[2] = &v85;
          v88[3] = &v86;
          v88[4] = &ppBuffer;
          v89 = 1;
          ConvertToContiguousBuffer = v23->lpVtbl->ConvertToContiguousBuffer;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
          v9 = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *))ConvertToContiguousBuffer)(v23, &v85);
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, void **, _QWORD, size_t *))(*(_QWORD *)v85 + 24LL))(
                   v85,
                   &Src,
                   0,
                   &Size);
            if ( v9 >= 0 )
            {
              if ( (unsigned __int64)(unsigned int)(-1 - Size) >= *((_QWORD *)this + 58) )
              {
                v40 = Size + *((_DWORD *)this + 116);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
                v9 = MFCreateMemoryBuffer(v40, &ppBuffer);
                if ( v9 >= 0 )
                {
                  v9 = ((__int64 (__fastcall *)(IMFMediaBuffer *, void **, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
                         ppBuffer,
                         &v86,
                         0,
                         0);
                  if ( v9 >= 0 )
                  {
                    memcpy_0(v86, *((const void **)this + 57), *((_QWORD *)this + 58));
                    memcpy_0((char *)v86 + *((_QWORD *)this + 58), Src, (unsigned int)Size);
                    v9 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
                           ppBuffer,
                           v40);
                    if ( v9 >= 0 )
                    {
                      v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v85 + 32LL))(v85);
                      if ( v9 >= 0 )
                      {
                        Src = 0;
                        v9 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                        if ( v9 >= 0 )
                        {
                          v86 = 0;
                          v9 = ((__int64 (__fastcall *)(struct IMFSample *))v23->lpVtbl->RemoveAllBuffers)(v23);
                          if ( v9 >= 0 )
                          {
                            v9 = ((__int64 (__fastcall *)(struct IMFSample *, IMFMediaBuffer *))v23->lpVtbl->AddBuffer)(
                                   v23,
                                   ppBuffer);
                            if ( v9 >= 0 )
                            {
                              if ( Src )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 32LL))(v85);
                              if ( v86 )
                                ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                            }
                            else
                            {
                              v80 = (__int64 *)CallStackTracing::s_wpInstance;
                              if ( !CallStackTracing::s_wpInstance )
                              {
                                v81 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v77, v78, v79);
                                CallStackTracing::s_wpInstance = v81;
                                if ( v81
                                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v81 + 8LL))(
                                       v81,
                                       2032) )
                                {
                                  v80 = (__int64 *)CallStackTracing::s_wpInstance;
                                }
                                else
                                {
                                  v80 = &qword_1800D6F70;
                                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                                }
                              }
                              if ( *((_BYTE *)v80 + 8) )
                              {
                                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v80);
                                if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
                                  CallStackContext::TraceFailure(
                                    ThreadRelativeContext,
                                    "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample",
                                    992,
                                    v9);
                              }
                              if ( g_wppLevels )
                                WPP_SF_qD(
                                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                                  146,
                                  &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                                  this,
                                  v9);
                              if ( Src )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 32LL))(v85);
                              if ( v86 )
                                ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                            }
                          }
                          else
                          {
                            v74 = (__int64 *)CallStackTracing::s_wpInstance;
                            if ( !CallStackTracing::s_wpInstance )
                            {
                              v75 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v71, v72, v73);
                              CallStackTracing::s_wpInstance = v75;
                              if ( v75
                                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v75 + 8LL))(
                                     v75,
                                     2032) )
                              {
                                v74 = (__int64 *)CallStackTracing::s_wpInstance;
                              }
                              else
                              {
                                v74 = &qword_1800D6F70;
                                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                              }
                            }
                            if ( *((_BYTE *)v74 + 8) )
                            {
                              v76 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v74);
                              if ( *((_DWORD *)v76 + 499) != v9 )
                                CallStackContext::TraceFailure(
                                  v76,
                                  "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample",
                                  991,
                                  v9);
                            }
                            if ( g_wppLevels )
                              WPP_SF_qD(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                145,
                                &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                                this,
                                v9);
                            if ( Src )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 32LL))(v85);
                            if ( v86 )
                              ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                          }
                        }
                        else
                        {
                          v68 = (__int64 *)CallStackTracing::s_wpInstance;
                          if ( !CallStackTracing::s_wpInstance )
                          {
                            v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v65, v66, v67);
                            CallStackTracing::s_wpInstance = v69;
                            if ( v69
                              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v69 + 8LL))(
                                   v69,
                                   2032) )
                            {
                              v68 = (__int64 *)CallStackTracing::s_wpInstance;
                            }
                            else
                            {
                              v68 = &qword_1800D6F70;
                              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                            }
                          }
                          if ( *((_BYTE *)v68 + 8) )
                          {
                            v70 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v68);
                            if ( *((_DWORD *)v70 + 499) != v9 )
                              CallStackContext::TraceFailure(
                                v70,
                                "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample",
                                987,
                                v9);
                          }
                          if ( g_wppLevels )
                            WPP_SF_qD(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              144,
                              &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                              this,
                              v9);
                          if ( Src )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 32LL))(v85);
                          if ( v86 )
                            ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                        }
                      }
                      else
                      {
                        v62 = (__int64 *)CallStackTracing::s_wpInstance;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v59, v60, v61);
                          CallStackTracing::s_wpInstance = v63;
                          if ( v63
                            && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(
                                 v63,
                                 2032) )
                          {
                            v62 = (__int64 *)CallStackTracing::s_wpInstance;
                          }
                          else
                          {
                            v62 = &qword_1800D6F70;
                            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                          }
                        }
                        if ( *((_BYTE *)v62 + 8) )
                        {
                          v64 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v62);
                          if ( *((_DWORD *)v64 + 499) != v9 )
                            CallStackContext::TraceFailure(
                              v64,
                              "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample",
                              985,
                              v9);
                        }
                        if ( g_wppLevels )
                          WPP_SF_qD(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            143,
                            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                            this,
                            v9);
                        if ( Src )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 32LL))(v85);
                        if ( v86 )
                          ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                      }
                    }
                    else
                    {
                      v56 = (__int64 *)CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v53, v54, v55);
                        CallStackTracing::s_wpInstance = v57;
                        if ( v57
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(
                               v57,
                               2032) )
                        {
                          v56 = (__int64 *)CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v56 = &qword_1800D6F70;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                        }
                      }
                      if ( *((_BYTE *)v56 + 8) )
                      {
                        v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
                        if ( *((_DWORD *)v58 + 499) != v9 )
                          CallStackContext::TraceFailure(
                            v58,
                            "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample",
                            982,
                            v9);
                      }
                      if ( g_wppLevels )
                        WPP_SF_qD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          142,
                          &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                          this,
                          v9);
                      if ( Src )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 32LL))(v85);
                      if ( v86 )
                        ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                    }
                  }
                  else
                  {
                    v50 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47, v48, v49);
                      CallStackTracing::s_wpInstance = v51;
                      if ( v51
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(
                             v51,
                             2032) )
                      {
                        v50 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v50 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                      }
                    }
                    if ( *((_BYTE *)v50 + 8) )
                    {
                      v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
                      if ( *((_DWORD *)v52 + 499) != v9 )
                        CallStackContext::TraceFailure(
                          v52,
                          "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample",
                          977,
                          v9);
                    }
                    if ( g_wppLevels )
                      WPP_SF_qD(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        141,
                        &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                        this,
                        v9);
                    if ( Src )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 32LL))(v85);
                    if ( v86 )
                      ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                  }
                }
                else
                {
                  v44 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42, v43);
                    CallStackTracing::s_wpInstance = v45;
                    if ( v45
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
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
                    if ( *((_DWORD *)v46 + 499) != v9 )
                      CallStackContext::TraceFailure(
                        v46,
                        "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample",
                        976,
                        v9);
                  }
                  if ( g_wppLevels )
                    WPP_SF_qD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      140,
                      &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                      this,
                      v9);
                  if ( Src )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 32LL))(v85);
                  if ( v86 )
                    ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
                }
              }
              else
              {
                v9 = -1072875842;
                v37 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
                  CallStackTracing::s_wpInstance = v38;
                  if ( v38
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
                  {
                    v37 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v37 = &qword_1800D6F70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                  }
                }
                if ( *((_BYTE *)v37 + 8) )
                {
                  v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
                  if ( *((_DWORD *)v39 + 499) != -1072875842 )
                    CallStackContext::TraceFailure(
                      v39,
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
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 32LL))(v85);
                if ( v86 )
                  ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
              }
            }
            else
            {
              v34 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
                CallStackTracing::s_wpInstance = v35;
                if ( v35
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
                {
                  v34 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v34 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                }
              }
              if ( *((_BYTE *)v34 + 8) )
              {
                v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
                if ( *((_DWORD *)v36 + 499) != v9 )
                  CallStackContext::TraceFailure(v36, "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample", 965, v9);
              }
              if ( g_wppLevels )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  138,
                  &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                  this,
                  v9);
              if ( Src )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 32LL))(v85);
              if ( v86 )
                ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
            }
          }
          else
          {
            v28 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26, v27);
              CallStackTracing::s_wpInstance = v29;
              if ( v29
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
              {
                v28 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v28 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v28 + 8) )
            {
              v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
              if ( *((_DWORD *)v30 + 499) != v9 )
                CallStackContext::TraceFailure(v30, "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample", 964, v9);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                137,
                &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
                this,
                v9);
            if ( Src )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 32LL))(v85);
            if ( v86 )
              ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v88);
        }
      }
      else
      {
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18, v19);
          CallStackTracing::s_wpInstance = v21;
          if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
          {
            v20 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v20 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v20 + 8) )
        {
          v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
          if ( *((_DWORD *)v22 + 499) != v9 )
            CallStackContext::TraceFailure(v22, "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample", 937, v9);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            136,
            &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
            this,
            v9);
      }
    }
    else
    {
      v9 = -2147467261;
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7, v8);
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
        if ( *((_DWORD *)v16 + 499) != -2147467261 )
          CallStackContext::TraceFailure(v16, "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample", 935, -2147467261);
      }
      if ( g_wppLevels )
      {
        v13 = 135;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v9 = -2147467261;
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7, v8);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v12, "MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample", 934, -2147467261);
    }
    if ( g_wppLevels )
    {
      v13 = 134;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
        this,
        -2147467261);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v90);
  return (unsigned int)v9;
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
