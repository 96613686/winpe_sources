# CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver(IMFByteStream *,IMFSourceResolver *,IMFSourceReader * *)

- ea: `0x18004ab18`
- end: `0x18004b3ab`
- name: `?CreateAsyncSourceReaderUsingSourceResolver@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAUIMFSourceResolver@@PEAPEAUIMFSourceReader@@@Z`
- size: `2195`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFByteStream *, struct IMFSourceResolver *, struct IMFSourceReader **)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18004bc64`
- `0x18004bec8`

## callees

- `0x180001e80`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180034a04`
- `0x180039e60`
- `0x180048710`
- `0x18004a4d8`
- `0x18004ab18`
- `0x18004b3b4`
- `0x18004b7e0`
- `0x18004c114`
- `0x180056010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18004ac82`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18004ac82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ac9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ad62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ae14`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004aed0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004afb5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b06f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b123`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b216`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b2bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ac9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ad62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ae14`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004aed0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004afb5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b06f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b123`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b216`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b2bf`

## string_xrefs

- `0x18004ab4d`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x18004ac62`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x18004b0c6`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x18004b17a`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x18004b26d`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x18004b316`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver(
        CMFVideoThumbnail *this,
        struct IMFByteStream *a2,
        struct IMFSourceResolver *a3,
        struct IMFSourceReader **a4)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v9; // ebx
  __int128 v10; // xmm0
  __int64 v11; // rdx
  int AsyncSourceReader; // ebx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  LARGE_INTEGER v29; // rbx
  __int64 v30; // rdx
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  const unsigned __int16 *v34; // rdi
  __int64 v35; // rdx
  __int64 v36; // r14
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 v40; // rdx
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rdx
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  _BYTE v54[8]; // [rsp+40h] [rbp-C0h] BYREF
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  struct IMFMediaSource *v56; // [rsp+50h] [rbp-B0h] BYREF
  struct CMFVideoThumbnail::CMFSourceResolverOp *v57; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v58; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v59; // [rsp+70h] [rbp-90h]
  PROPVARIANT pvar; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v61[12]; // [rsp+90h] [rbp-70h]
  _BYTE v62[16]; // [rsp+F0h] [rbp-10h] BYREF

  v61[1] = L"dummy.asf";
  ppv = 0;
  v61[0] = 0;
  v61[2] = L"dummy.mp3";
  v57 = 0;
  v61[3] = L"dummy.mp4";
  v56 = 0;
  v61[4] = L"dummy.avi";
  v61[5] = L"dummy.m2ts";
  v61[6] = L"dummy.wav";
  v61[7] = L"dummy.adts";
  v61[8] = L"dummy.ac3";
  v61[9] = L"dummy.mkv";
  v61[10] = L"dummy.flac";
  v59 = 0;
  v58 = 0;
  memset(&pvar, 0, sizeof(pvar));
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v54,
    "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
    416);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v10 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                       *((_QWORD *)this + 50),
                       v62);
    *((_DWORD *)ThreadRelativeContext + 504) = v9;
    *((_OWORD *)ThreadRelativeContext + 125) = v10;
  }
  *a4 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  AsyncSourceReader = PSCreateMemoryPropertyStore(&IID_IPropertyStore, &ppv);
  if ( AsyncSourceReader >= 0 )
  {
    LOWORD(v58) = 11;
    WORD4(v58) = -1;
    AsyncSourceReader = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(*(_QWORD *)ppv + 48LL))(
                          ppv,
                          &MFPKEY_MediaSource_DisableReadAhead,
                          &v58);
    if ( AsyncSourceReader >= 0 )
    {
      AsyncSourceReader = (*(__int64 (__fastcall **)(void *, __int64 *, __int128 *))(*(_QWORD *)ppv + 48LL))(
                            ppv,
                            qword_180066A00,
                            &v58);
      if ( AsyncSourceReader >= 0 )
      {
        if ( *((_DWORD *)this + 7) == 5
          && (AsyncSourceReader = (*(__int64 (__fastcall **)(void *, __int64 *, __int128 *))(*(_QWORD *)ppv + 48LL))(
                                    ppv,
                                    qword_1800669E8,
                                    &v58),
              AsyncSourceReader < 0) )
        {
          v26 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
            CallStackTracing::s_wpInstance = v27;
            if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
            {
              v26 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v26 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v26 + 8) )
          {
            v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
            if ( *((_DWORD *)v28 + 499) != AsyncSourceReader )
              CallStackContext::TraceFailure(
                v28,
                "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                434,
                AsyncSourceReader);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v16 = 31;
            goto LABEL_108;
          }
        }
        else
        {
          v29 = *(LARGE_INTEGER *)((char *)this + 400);
          CMFPropVariant::Clear(&pvar);
          pvar.hVal = v29;
          pvar.vt = 13;
          if ( v29.QuadPart )
            (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v29.QuadPart + 8LL))(v29);
          AsyncSourceReader = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                ppv,
                                MFPKEY_TELEMETRY_SESSION,
                                &pvar);
          if ( AsyncSourceReader >= 0 )
          {
            v34 = 0;
            if ( *((_DWORD *)this + 7) < 0xBu )
              v34 = (const unsigned __int16 *)v61[*((int *)this + 7)];
            v36 = CMFVideoThumbnail::ElapsedTime(this);
            if ( v36 < *((_QWORD *)this + 45) )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
              AsyncSourceReader = CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance(
                                    *((struct IMFTelemetrySession **)this + 50),
                                    &v57);
              if ( AsyncSourceReader >= 0 )
              {
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
                AsyncSourceReader = CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource(
                                      v57,
                                      a3,
                                      a2,
                                      v34,
                                      (struct IPropertyStore *)ppv,
                                      (*((_DWORD *)this + 90) - (int)v36) / 10000,
                                      &v56);
                if ( AsyncSourceReader >= 0 )
                {
                  AsyncSourceReader = CMFVideoThumbnail::CreateAsyncSourceReader(this, v56, v45, a4);
                  if ( AsyncSourceReader < 0 )
                  {
                    v50 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49);
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
                        v50 = &qword_18006EB20;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                      }
                    }
                    if ( *((_BYTE *)v50 + 8) )
                    {
                      v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
                      if ( *((_DWORD *)v52 + 499) != AsyncSourceReader )
                        CallStackContext::TraceFailure(
                          v52,
                          "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                          457,
                          AsyncSourceReader);
                    }
                    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                    {
                      v16 = 36;
                      goto LABEL_108;
                    }
                  }
                }
                else
                {
                  v46 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
                    CallStackTracing::s_wpInstance = v47;
                    if ( v47
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
                    {
                      v46 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v46 = &qword_18006EB20;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                    }
                  }
                  if ( *((_BYTE *)v46 + 8) )
                  {
                    v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
                    if ( *((_DWORD *)v48 + 499) != AsyncSourceReader )
                      CallStackContext::TraceFailure(
                        v48,
                        "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                        455,
                        AsyncSourceReader);
                  }
                  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  {
                    v16 = 35;
                    goto LABEL_108;
                  }
                }
              }
              else
              {
                v41 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
                  CallStackTracing::s_wpInstance = v42;
                  if ( v42
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
                  {
                    v41 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v41 = &qword_18006EB20;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                  }
                }
                if ( *((_BYTE *)v41 + 8) )
                {
                  v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
                  if ( *((_DWORD *)v43 + 499) != AsyncSourceReader )
                    CallStackContext::TraceFailure(
                      v43,
                      "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                      453,
                      AsyncSourceReader);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v16 = 34;
                  goto LABEL_108;
                }
              }
            }
            else
            {
              v37 = (__int64 *)CallStackTracing::s_wpInstance;
              AsyncSourceReader = -2147418113;
              if ( !CallStackTracing::s_wpInstance )
              {
                v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
                CallStackTracing::s_wpInstance = v38;
                if ( v38
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
                {
                  v37 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v37 = &qword_18006EB20;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                }
              }
              if ( *((_BYTE *)v37 + 8) )
              {
                v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
                if ( *((_DWORD *)v39 + 499) != -2147418113 )
                  CallStackContext::TraceFailure(
                    v39,
                    "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                    450,
                    -2147418113);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v16 = 33;
                goto LABEL_108;
              }
            }
          }
          else
          {
            v31 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
              CallStackTracing::s_wpInstance = v32;
              if ( v32
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
              {
                v31 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v31 = &qword_18006EB20;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            if ( *((_BYTE *)v31 + 8) )
            {
              v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
              if ( *((_DWORD *)v33 + 499) != AsyncSourceReader )
                CallStackContext::TraceFailure(
                  v33,
                  "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                  439,
                  AsyncSourceReader);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v16 = 32;
              goto LABEL_108;
            }
          }
        }
      }
      else
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
          CallStackTracing::s_wpInstance = v23;
          if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
          {
            v22 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v22 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v22 + 8) )
        {
          v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
          if ( *((_DWORD *)v24 + 499) != AsyncSourceReader )
            CallStackContext::TraceFailure(
              v24,
              "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
              429,
              AsyncSourceReader);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v16 = 30;
          goto LABEL_108;
        }
      }
    }
    else
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)v20 + 499) != AsyncSourceReader )
          CallStackContext::TraceFailure(
            v20,
            "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
            426,
            AsyncSourceReader);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v16 = 29;
        goto LABEL_108;
      }
    }
  }
  else
  {
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v15 + 499) != AsyncSourceReader )
        CallStackContext::TraceFailure(
          v15,
          "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
          420,
          AsyncSourceReader);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v16 = 28;
LABEL_108:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
        this,
        AsyncSourceReader);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v54);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
  CMFPropVariant::Clear(&pvar);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)AsyncSourceReader;
}

```

## disassembly

```asm
0x18004ab18  push    rbp
0x18004ab1a  push    rbx
0x18004ab1b  push    rsi
0x18004ab1c  push    rdi
0x18004ab1d  push    r12
0x18004ab1f  push    r13
0x18004ab21  push    r14
0x18004ab23  push    r15
0x18004ab25  lea     rbp, [rsp-18h]
0x18004ab2a  sub     rsp, 118h
0x18004ab31  mov     rax, cs:__security_cookie
0x18004ab38  xor     rax, rsp
0x18004ab3b  mov     [rbp+50h+var_50], rax
0x18004ab3f  xor     r14d, r14d
0x18004ab42  lea     rax, aDummyAsf; "dummy.asf"
0x18004ab49  mov     [rbp+50h+var_B8], rax
0x18004ab4d  lea     rdi, aCmfvideothumbn_1; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x18004ab54  xorps   xmm0, xmm0
0x18004ab57  mov     [rsp+150h+ppv], r14
0x18004ab5c  lea     rax, aDummyMp3; "dummy.mp3"
0x18004ab63  mov     [rbp+50h+var_C0], r14
0x18004ab67  mov     [rbp+50h+var_B0], rax
0x18004ab6b  mov     r13, r8
0x18004ab6e  lea     rax, aDummyMp4; "dummy.mp4"
0x18004ab75  mov     [rsp+150h+var_F8], r14
0x18004ab7a  mov     [rbp+50h+var_A8], rax
0x18004ab7e  mov     r12, rdx
0x18004ab81  lea     rax, aDummyAvi; "dummy.avi"
0x18004ab88  mov     [rsp+150h+var_100], r14
0x18004ab8d  mov     [rbp+50h+var_A0], rax
0x18004ab91  mov     rsi, rcx
0x18004ab94  lea     rax, aDummyM2ts; "dummy.m2ts"
0x18004ab9b  mov     r8d, 1A0h; int
0x18004aba1  mov     [rbp+50h+var_98], rax
0x18004aba5  lea     rcx, [rsp+150h+var_110]; this
0x18004abaa  lea     rax, aDummyWav; "dummy.wav"
0x18004abb1  mov     rdx, rdi; char *
0x18004abb4  mov     [rbp+50h+var_90], rax
0x18004abb8  mov     r15, r9
0x18004abbb  lea     rax, aDummyAdts; "dummy.adts"
0x18004abc2  mov     [rbp+50h+var_88], rax
0x18004abc6  lea     rax, aDummyAc3; "dummy.ac3"
0x18004abcd  mov     [rbp+50h+var_80], rax
0x18004abd1  lea     rax, aDummyMkv; "dummy.mkv"
0x18004abd8  mov     [rbp+50h+var_78], rax
0x18004abdc  lea     rax, aDummyFlac; "dummy.flac"
0x18004abe3  mov     [rbp+50h+var_70], rax
0x18004abe7  xor     eax, eax
0x18004abe9  mov     [rsp+150h+var_E0], rax
0x18004abee  mov     qword ptr [rbp+50h+pvar+10h], rax
0x18004abf2  movups  [rsp+150h+var_F0], xmm0
0x18004abf7  movups  xmmword ptr [rsp+150h+pvar], xmm0
0x18004abfc  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004ac01  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004ac08  cmp     [rcx+8], r14b
0x18004ac0c  jz      short loc_18004AC69
0x18004ac0e  cmp     [rsi+190h], r14
0x18004ac15  jz      short loc_18004AC69
0x18004ac17  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004ac1c  mov     rcx, [rsi+190h]
0x18004ac23  mov     rdi, rax
0x18004ac26  mov     rdx, [rcx]
0x18004ac29  mov     rax, [rdx+128h]
0x18004ac30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac35  mov     rcx, [rsi+190h]
0x18004ac3c  mov     ebx, eax
0x18004ac3e  mov     rdx, [rcx]
0x18004ac41  mov     rax, [rdx+118h]
0x18004ac48  lea     rdx, [rbp+50h+var_60]
0x18004ac4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac51  movups  xmm0, xmmword ptr [rax]
0x18004ac54  mov     [rdi+7E0h], ebx
0x18004ac5a  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18004ac62  lea     rdi, aCmfvideothumbn_1; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x18004ac69  lea     rcx, [rsp+150h+ppv]
0x18004ac6e  mov     [r15], r14
0x18004ac71  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ac76  lea     rdx, [rsp+150h+ppv]; ppv
0x18004ac7b  lea     rcx, IID_IPropertyStore; riid
0x18004ac82  call    cs:__imp_PSCreateMemoryPropertyStore
0x18004ac88  mov     ebx, eax
0x18004ac8a  test    eax, eax
0x18004ac8c  jns     loc_18004AD1D
0x18004ac92  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ac99  test    rcx, rcx
0x18004ac9c  jnz     short loc_18004ACDF
0x18004ac9e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004aca4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004acab  mov     rcx, rax
0x18004acae  test    rax, rax
0x18004acb1  jz      short loc_18004ACD1
0x18004acb3  mov     rax, [rax]
0x18004acb6  mov     edx, 7F0h
0x18004acbb  mov     rax, [rax+8]
0x18004acbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004acc4  test    eax, eax
0x18004acc6  jz      short loc_18004ACD1
0x18004acc8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004accf  jmp     short loc_18004ACDF
0x18004acd1  lea     rcx, qword_18006EB20; this
0x18004acd8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004acdf  cmp     [rcx+8], r14b
0x18004ace3  jz      short loc_18004AD06
0x18004ace5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004acea  cmp     [rax+7CCh], ebx
0x18004acf0  jz      short loc_18004AD06
0x18004acf2  mov     r9d, ebx; int
0x18004acf5  mov     r8d, 1A4h; int
0x18004acfb  mov     rdx, rdi; char *
0x18004acfe  mov     rcx, rax; this
0x18004ad01  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004ad06  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004ad0b  cmp     al, 1
0x18004ad0d  jb      loc_18004B357
0x18004ad13  mov     edx, 1Ch
0x18004ad18  jmp     loc_18004B339
0x18004ad1d  mov     rcx, [rsp+150h+ppv]
0x18004ad22  lea     r8, [rsp+150h+var_F0]
0x18004ad27  mov     eax, 0Bh
0x18004ad2c  lea     rdx, MFPKEY_MediaSource_DisableReadAhead
0x18004ad33  mov     word ptr [rsp+150h+var_F0], ax
0x18004ad38  or      eax, 0FFFFFFFFh
0x18004ad3b  mov     word ptr [rsp+150h+var_F0+8], ax
0x18004ad40  mov     rax, [rcx]
0x18004ad43  mov     rax, [rax+30h]
0x18004ad47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad4c  mov     ebx, eax
0x18004ad4e  test    eax, eax
0x18004ad50  jns     loc_18004ADE1
0x18004ad56  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ad5d  test    rcx, rcx
0x18004ad60  jnz     short loc_18004ADA3
0x18004ad62  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004ad68  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ad6f  mov     rcx, rax
0x18004ad72  test    rax, rax
0x18004ad75  jz      short loc_18004AD95
0x18004ad77  mov     rax, [rax]
0x18004ad7a  mov     edx, 7F0h
0x18004ad7f  mov     rax, [rax+8]
0x18004ad83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad88  test    eax, eax
0x18004ad8a  jz      short loc_18004AD95
0x18004ad8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ad93  jmp     short loc_18004ADA3
0x18004ad95  lea     rcx, qword_18006EB20; this
0x18004ad9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ada3  cmp     [rcx+8], r14b
0x18004ada7  jz      short loc_18004ADCA
0x18004ada9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004adae  cmp     [rax+7CCh], ebx
0x18004adb4  jz      short loc_18004ADCA
0x18004adb6  mov     r9d, ebx; int
0x18004adb9  mov     r8d, 1AAh; int
0x18004adbf  mov     rdx, rdi; char *
0x18004adc2  mov     rcx, rax; this
0x18004adc5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004adca  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004adcf  cmp     al, 1
0x18004add1  jb      loc_18004B357
0x18004add7  mov     edx, 1Dh
0x18004addc  jmp     loc_18004B339
0x18004ade1  mov     rcx, [rsp+150h+ppv]
0x18004ade6  lea     r8, [rsp+150h+var_F0]
0x18004adeb  lea     rdx, qword_180066A00
0x18004adf2  mov     rax, [rcx]
0x18004adf5  mov     rax, [rax+30h]
0x18004adf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004adfe  mov     ebx, eax
0x18004ae00  test    eax, eax
0x18004ae02  jns     loc_18004AE93
0x18004ae08  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ae0f  test    rcx, rcx
0x18004ae12  jnz     short loc_18004AE55
0x18004ae14  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004ae1a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ae21  mov     rcx, rax
0x18004ae24  test    rax, rax
0x18004ae27  jz      short loc_18004AE47
0x18004ae29  mov     rax, [rax]
0x18004ae2c  mov     edx, 7F0h
0x18004ae31  mov     rax, [rax+8]
0x18004ae35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae3a  test    eax, eax
0x18004ae3c  jz      short loc_18004AE47
0x18004ae3e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ae45  jmp     short loc_18004AE55
0x18004ae47  lea     rcx, qword_18006EB20; this
0x18004ae4e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ae55  cmp     [rcx+8], r14b
0x18004ae59  jz      short loc_18004AE7C
0x18004ae5b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004ae60  cmp     [rax+7CCh], ebx
0x18004ae66  jz      short loc_18004AE7C
0x18004ae68  mov     r9d, ebx; int
0x18004ae6b  mov     r8d, 1ADh; int
0x18004ae71  mov     rdx, rdi; char *
0x18004ae74  mov     rcx, rax; this
0x18004ae77  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004ae7c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004ae81  cmp     al, 1
0x18004ae83  jb      loc_18004B357
0x18004ae89  mov     edx, 1Eh
0x18004ae8e  jmp     loc_18004B339
0x18004ae93  cmp     dword ptr [rsi+1Ch], 5
0x18004ae97  jnz     loc_18004AF4F
0x18004ae9d  mov     rcx, [rsp+150h+ppv]
0x18004aea2  lea     r8, [rsp+150h+var_F0]
0x18004aea7  lea     rdx, qword_1800669E8
0x18004aeae  mov     rax, [rcx]
0x18004aeb1  mov     rax, [rax+30h]
0x18004aeb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aeba  mov     ebx, eax
0x18004aebc  test    eax, eax
0x18004aebe  jns     loc_18004AF4F
0x18004aec4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004aecb  test    rcx, rcx
0x18004aece  jnz     short loc_18004AF11
0x18004aed0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004aed6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004aedd  mov     rcx, rax
0x18004aee0  test    rax, rax
0x18004aee3  jz      short loc_18004AF03
0x18004aee5  mov     rax, [rax]
0x18004aee8  mov     edx, 7F0h
0x18004aeed  mov     rax, [rax+8]
0x18004aef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aef6  test    eax, eax
0x18004aef8  jz      short loc_18004AF03
0x18004aefa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004af01  jmp     short loc_18004AF11
0x18004af03  lea     rcx, qword_18006EB20; this
0x18004af0a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004af11  cmp     [rcx+8], r14b
0x18004af15  jz      short loc_18004AF38
0x18004af17  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004af1c  cmp     [rax+7CCh], ebx
0x18004af22  jz      short loc_18004AF38
0x18004af24  mov     r9d, ebx; int
0x18004af27  mov     r8d, 1B2h; int
0x18004af2d  mov     rdx, rdi; char *
0x18004af30  mov     rcx, rax; this
0x18004af33  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004af38  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004af3d  cmp     al, 1
0x18004af3f  jb      loc_18004B357
0x18004af45  mov     edx, 1Fh
0x18004af4a  jmp     loc_18004B339
0x18004af4f  mov     rbx, [rsi+190h]
0x18004af56  lea     rcx, [rsp+150h+pvar]; pvar
0x18004af5b  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18004af60  mov     qword ptr [rbp+50h+pvar+8], rbx
0x18004af64  mov     eax, 0Dh
0x18004af69  mov     word ptr [rsp+150h+pvar], ax
0x18004af6e  test    rbx, rbx
0x18004af71  jz      short loc_18004AF82
0x18004af73  mov     rax, [rbx]
0x18004af76  mov     rcx, rbx
0x18004af79  mov     rax, [rax+8]
0x18004af7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af82  mov     rcx, [rsp+150h+ppv]
0x18004af87  lea     r8, [rsp+150h+pvar]
0x18004af8c  lea     rdx, MFPKEY_TELEMETRY_SESSION
0x18004af93  mov     rax, [rcx]
0x18004af96  mov     rax, [rax+30h]
0x18004af9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af9f  mov     ebx, eax
0x18004afa1  test    eax, eax
0x18004afa3  jns     loc_18004B034
0x18004afa9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004afb0  test    rcx, rcx
0x18004afb3  jnz     short loc_18004AFF6
0x18004afb5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004afbb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004afc2  mov     rcx, rax
0x18004afc5  test    rax, rax
0x18004afc8  jz      short loc_18004AFE8
0x18004afca  mov     rax, [rax]
0x18004afcd  mov     edx, 7F0h
0x18004afd2  mov     rax, [rax+8]
0x18004afd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004afdb  test    eax, eax
0x18004afdd  jz      short loc_18004AFE8
0x18004afdf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004afe6  jmp     short loc_18004AFF6
0x18004afe8  lea     rcx, qword_18006EB20; this
0x18004afef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004aff6  cmp     [rcx+8], r14b
0x18004affa  jz      short loc_18004B01D
0x18004affc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b001  cmp     [rax+7CCh], ebx
0x18004b007  jz      short loc_18004B01D
0x18004b009  mov     r9d, ebx; int
0x18004b00c  mov     r8d, 1B7h; int
0x18004b012  mov     rdx, rdi; char *
0x18004b015  mov     rcx, rax; this
0x18004b018  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b01d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004b022  cmp     al, 1
0x18004b024  jb      loc_18004B357
  ... truncated ...
```
