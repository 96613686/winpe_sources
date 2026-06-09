# MkvMfSourceLib::MkvMfStreamVideoAV1::TransformSample(IMFSample * *,bool)

- ea: `0x180038fb0`
- end: `0x180039ce1`
- name: `?TransformSample@MkvMfStreamVideoAV1@MkvMfSourceLib@@UEAAJPEAPEAUIMFSample@@_N@Z`
- size: `3377`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStreamVideoAV1 *this, struct IMFSample **, char)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180003705`
- `0x180005c68`
- `0x180009b04`
- `0x180009bec`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180027af0`
- `0x180038fb0`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003900f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800390ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003917a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800392ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800393ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003949e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800395a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800396a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800397c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800398bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800399b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039aac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039ba5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003900f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800390ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003917a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800392ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800393ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003949e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800395a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800396a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800397c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800398bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800399b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039aac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039ba5`
- `MFPlat!MFCreateMemoryBuffer` at `0x180039585`
- `MFPlat!MFCreateMemoryBuffer` at `0x180039585`

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
                                  v80 = &qword_1800DBF70;
                                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                                v74 = &qword_1800DBF70;
                                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                              v68 = &qword_1800DBF70;
                              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                            v62 = &qword_1800DBF70;
                            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                          v56 = &qword_1800DBF70;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                        v50 = &qword_1800DBF70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                      v44 = &qword_1800DBF70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                    v37 = &qword_1800DBF70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                  v34 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                v28 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v20 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v14 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v10 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180038fb0  mov     [rsp-38h+arg_0], rbx
0x180038fb5  push    rbp
0x180038fb6  push    rsi
0x180038fb7  push    rdi
0x180038fb8  push    r12
0x180038fba  push    r13
0x180038fbc  push    r14
0x180038fbe  push    r15
0x180038fc0  mov     rbp, rsp
0x180038fc3  sub     rsp, 80h
0x180038fca  mov     sil, r8b
0x180038fcd  mov     rbx, rdx
0x180038fd0  mov     r14, rcx
0x180038fd3  mov     r15d, 3A6h
0x180038fd9  mov     r8d, r15d; int
0x180038fdc  lea     r13, aMkvmfsourcelib_55; "MkvMfSourceLib::MkvMfStreamVideoAV1::Tr"...
0x180038fe3  mov     rdx, r13; char *
0x180038fe6  lea     rcx, [rbp+arg_8]; this
0x180038fea  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180038fef  nop
0x180038ff0  xor     r12d, r12d
0x180038ff3  test    rbx, rbx
0x180038ff6  jnz     loc_1800390B2
0x180038ffc  mov     ebx, 80004003h
0x180039001  mov     edi, ebx
0x180039003  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003900a  test    rcx, rcx
0x18003900d  jnz     short loc_180039056
0x18003900f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039016  nop     dword ptr [rax+rax+00h]
0x18003901b  mov     rcx, rax
0x18003901e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039025  test    rax, rax
0x180039028  jz      short loc_180039048
0x18003902a  mov     rax, [rax]
0x18003902d  mov     edx, 7F0h
0x180039032  mov     rax, [rax+8]
0x180039036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003903b  test    eax, eax
0x18003903d  jz      short loc_180039048
0x18003903f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039046  jmp     short loc_180039056
0x180039048  lea     rcx, qword_1800DBF70; this
0x18003904f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039056  cmp     [rcx+8], r12b
0x18003905a  jz      short loc_18003907A
0x18003905c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039061  cmp     [rax+7CCh], ebx
0x180039067  jz      short loc_18003907A
0x180039069  mov     r9d, ebx; int
0x18003906c  mov     r8d, r15d; int
0x18003906f  mov     rdx, r13; char *
0x180039072  mov     rcx, rax; this
0x180039075  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003907a  mov     sil, 1
0x18003907d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180039084  jb      loc_180039CBA
0x18003908a  mov     edx, 86h
0x18003908f  mov     [rsp+80h+var_60], ebx
0x180039093  mov     r9, r14
0x180039096  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x18003909d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800390a4  mov     rcx, [rcx+10h]
0x1800390a8  call    WPP_SF_qD
0x1800390ad  jmp     loc_180039CBA
0x1800390b2  cmp     [rbx], r12
0x1800390b5  jnz     loc_180039156
0x1800390bb  mov     ebx, 80004003h
0x1800390c0  mov     edi, ebx
0x1800390c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800390c9  test    rcx, rcx
0x1800390cc  jnz     short loc_180039115
0x1800390ce  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800390d5  nop     dword ptr [rax+rax+00h]
0x1800390da  mov     rcx, rax
0x1800390dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800390e4  test    rax, rax
0x1800390e7  jz      short loc_180039107
0x1800390e9  mov     rax, [rax]
0x1800390ec  mov     edx, 7F0h
0x1800390f1  mov     rax, [rax+8]
0x1800390f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390fa  test    eax, eax
0x1800390fc  jz      short loc_180039107
0x1800390fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039105  jmp     short loc_180039115
0x180039107  lea     rcx, qword_1800DBF70; this
0x18003910e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039115  cmp     [rcx+8], r12b
0x180039119  jz      short loc_18003913C
0x18003911b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039120  cmp     [rax+7CCh], ebx
0x180039126  jz      short loc_18003913C
0x180039128  mov     r9d, ebx; int
0x18003912b  mov     r8d, 3A7h; int
0x180039131  mov     rdx, r13; char *
0x180039134  mov     rcx, rax; this
0x180039137  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003913c  mov     sil, 1
0x18003913f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180039146  jb      loc_180039CBA
0x18003914c  mov     edx, 87h
0x180039151  jmp     loc_18003908F
0x180039156  mov     r8b, sil; bool
0x180039159  mov     rdx, rbx; struct IMFSample **
0x18003915c  mov     rcx, r14; this
0x18003915f  call    ?TransformSample@MkvMfStream@MkvMfSourceLib@@UEAAJPEAPEAUIMFSample@@_N@Z; MkvMfSourceLib::MkvMfStream::TransformSample(IMFSample * *,bool)
0x180039164  mov     edi, eax
0x180039166  test    eax, eax
0x180039168  jns     loc_180039206
0x18003916e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039175  test    rcx, rcx
0x180039178  jnz     short loc_1800391C1
0x18003917a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039181  nop     dword ptr [rax+rax+00h]
0x180039186  mov     rcx, rax
0x180039189  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039190  test    rax, rax
0x180039193  jz      short loc_1800391B3
0x180039195  mov     rax, [rax]
0x180039198  mov     edx, 7F0h
0x18003919d  mov     rax, [rax+8]
0x1800391a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391a6  test    eax, eax
0x1800391a8  jz      short loc_1800391B3
0x1800391aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800391b1  jmp     short loc_1800391C1
0x1800391b3  lea     rcx, qword_1800DBF70; this
0x1800391ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800391c1  cmp     [rcx+8], r12b
0x1800391c5  jz      short loc_1800391E8
0x1800391c7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800391cc  cmp     [rax+7CCh], edi
0x1800391d2  jz      short loc_1800391E8
0x1800391d4  mov     r9d, edi; int
0x1800391d7  mov     r8d, 3A9h; int
0x1800391dd  mov     rdx, r13; char *
0x1800391e0  mov     rcx, rax; this
0x1800391e3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800391e8  mov     sil, 1
0x1800391eb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800391f2  jb      loc_180039CBA
0x1800391f8  mov     edx, 88h
0x1800391fd  mov     [rsp+80h+var_60], edi
0x180039201  jmp     loc_180039093
0x180039206  test    sil, sil
0x180039209  jz      loc_180039CBA
0x18003920f  cmp     [r14+1C8h], r12
0x180039216  jz      loc_180039CBA
0x18003921c  cmp     [r14+1D0h], r12
0x180039223  jbe     loc_180039CBA
0x180039229  mov     rbx, [rbx]
0x18003922c  mov     [rbp+var_30], rbx
0x180039230  lea     rcx, [rbp+var_30]
0x180039234  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x180039239  nop
0x18003923a  mov     [rbp+var_48], r12
0x18003923e  mov     [rbp+Src], r12
0x180039242  mov     dword ptr [rbp+Size], r12d
0x180039246  mov     [rbp+ppBuffer], r12
0x18003924a  mov     [rbp+var_40], r12
0x18003924e  lea     rax, [rbp+Src]
0x180039252  mov     [rbp+var_28], rax
0x180039256  lea     rax, [rbp+var_48]
0x18003925a  mov     [rbp+var_20], rax
0x18003925e  lea     rax, [rbp+var_40]
0x180039262  mov     [rbp+var_18], rax
0x180039266  lea     rax, [rbp+ppBuffer]
0x18003926a  mov     [rbp+var_10], rax
0x18003926e  mov     sil, 1
0x180039271  mov     [rbp+var_8], sil
0x180039275  mov     rax, [rbx]
0x180039278  mov     rdi, [rax+148h]
0x18003927f  lea     rcx, [rbp+var_48]
0x180039283  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039288  lea     rdx, [rbp+var_48]
0x18003928c  mov     rcx, rbx
0x18003928f  mov     rax, rdi
0x180039292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039297  mov     edi, eax
0x180039299  test    eax, eax
0x18003929b  jns     loc_18003937A
0x1800392a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800392a8  test    rcx, rcx
0x1800392ab  jnz     short loc_1800392F4
0x1800392ad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800392b4  nop     dword ptr [rax+rax+00h]
0x1800392b9  mov     rcx, rax
0x1800392bc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800392c3  test    rax, rax
0x1800392c6  jz      short loc_1800392E6
0x1800392c8  mov     rax, [rax]
0x1800392cb  mov     edx, 7F0h
0x1800392d0  mov     rax, [rax+8]
0x1800392d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392d9  test    eax, eax
0x1800392db  jz      short loc_1800392E6
0x1800392dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800392e4  jmp     short loc_1800392F4
0x1800392e6  lea     rcx, qword_1800DBF70; this
0x1800392ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800392f4  cmp     [rcx+8], r12b
0x1800392f8  jz      short loc_18003931B
0x1800392fa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800392ff  cmp     [rax+7CCh], edi
0x180039305  jz      short loc_18003931B
0x180039307  mov     r9d, edi; int
0x18003930a  mov     r8d, 3C4h; int
0x180039310  mov     rdx, r13; char *
0x180039313  mov     rcx, rax; this
0x180039316  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003931b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180039322  jb      short loc_180039348
0x180039324  mov     edx, 89h
0x180039329  mov     [rsp+80h+var_60], edi
0x18003932d  mov     r9, r14
0x180039330  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x180039337  mov     rcx, cs:WPP_GLOBAL_Control
0x18003933e  mov     rcx, [rcx+10h]
0x180039342  call    WPP_SF_qD
0x180039347  nop
0x180039348  cmp     [rbp+Src], r12
0x18003934c  jz      short loc_18003935E
0x18003934e  mov     rcx, [rbp+var_48]
0x180039352  mov     rax, [rcx]
0x180039355  mov     rax, [rax+20h]
0x180039359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003935e  cmp     [rbp+var_40], r12
0x180039362  jz      short loc_180039375
0x180039364  mov     rcx, [rbp+ppBuffer]
0x180039368  mov     rax, [rcx]
0x18003936b  mov     rax, [rax+20h]
0x18003936f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039374  nop
0x180039375  jmp     loc_180039C9C
0x18003937a  mov     rcx, [rbp+var_48]
0x18003937e  mov     rax, [rcx]
0x180039381  lea     r9, [rbp+Size]
0x180039385  xor     r8d, r8d
0x180039388  lea     rdx, [rbp+Src]
0x18003938c  mov     rax, [rax+18h]
0x180039390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039395  mov     edi, eax
0x180039397  test    eax, eax
0x180039399  jns     loc_180039478
0x18003939f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800393a6  test    rcx, rcx
0x1800393a9  jnz     short loc_1800393F2
0x1800393ab  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800393b2  nop     dword ptr [rax+rax+00h]
0x1800393b7  mov     rcx, rax
0x1800393ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800393c1  test    rax, rax
0x1800393c4  jz      short loc_1800393E4
0x1800393c6  mov     rax, [rax]
0x1800393c9  mov     edx, 7F0h
0x1800393ce  mov     rax, [rax+8]
0x1800393d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393d7  test    eax, eax
0x1800393d9  jz      short loc_1800393E4
0x1800393db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800393e2  jmp     short loc_1800393F2
0x1800393e4  lea     rcx, qword_1800DBF70; this
0x1800393eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800393f2  cmp     [rcx+8], r12b
0x1800393f6  jz      short loc_180039419
0x1800393f8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800393fd  cmp     [rax+7CCh], edi
0x180039403  jz      short loc_180039419
0x180039405  mov     r9d, edi; int
0x180039408  mov     r8d, 3C5h; int
0x18003940e  mov     rdx, r13; char *
0x180039411  mov     rcx, rax; this
0x180039414  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180039419  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180039420  jb      short loc_180039446
0x180039422  mov     edx, 8Ah
0x180039427  mov     [rsp+80h+var_60], edi
0x18003942b  mov     r9, r14
0x18003942e  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x180039435  mov     rcx, cs:WPP_GLOBAL_Control
0x18003943c  mov     rcx, [rcx+10h]
0x180039440  call    WPP_SF_qD
0x180039445  nop
0x180039446  cmp     [rbp+Src], r12
0x18003944a  jz      short loc_18003945C
0x18003944c  mov     rcx, [rbp+var_48]
0x180039450  mov     rax, [rcx]
0x180039453  mov     rax, [rax+20h]
0x180039457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003945c  cmp     [rbp+var_40], r12
0x180039460  jz      short loc_180039473
0x180039462  mov     rcx, [rbp+ppBuffer]
0x180039466  mov     rax, [rcx]
0x180039469  mov     rax, [rax+20h]
0x18003946d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039472  nop
0x180039473  jmp     loc_180039C9C
0x180039478  or      eax, 0FFFFFFFFh
0x18003947b  mov     ecx, dword ptr [rbp+Size]
  ... truncated ...
```
