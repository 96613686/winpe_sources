# CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver(IMFByteStream *,IMFSourceResolver *,IMFSourceReader * *)

- ea: `0x1800b554c`
- end: `0x1800b5dfd`
- name: `?CreateAsyncSourceReaderUsingSourceResolver@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAUIMFSourceResolver@@PEAPEAUIMFSourceReader@@@Z`
- size: `2225`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFByteStream *, struct IMFSourceResolver *, struct IMFSourceReader **)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800c5298`
- `0x1800f4ef0`

## callees

- `0x180005cf4`
- `0x180010fc4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x18006e048`
- `0x1800790a8`
- `0x180079680`
- `0x1800a0034`
- `0x1800b554c`
- `0x1800c1b20`
- `0x180105348`
- `0x180110ed0`
- `0x1801632cc`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b56d8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b57a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b585a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b591c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b59e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5aa5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5b5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5c58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5d0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b56d8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b57a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b585a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b591c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b59e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5aa5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5b5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5c58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5d0a`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800b56b6`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800b56b6`

## string_xrefs

- `0x1800b5581`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x1800b5696`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x1800b5b02`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x1800b5bbc`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x1800b5cb5`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x1800b5d67`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`

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
  wchar_t *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  const unsigned __int16 *v33; // rdi
  __int64 v34; // rdx
  __int64 v35; // r14
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  _BYTE v52[8]; // [rsp+40h] [rbp-C0h] BYREF
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  struct IMFMediaSource *v54; // [rsp+50h] [rbp-B0h] BYREF
  struct CMFVideoThumbnail::CMFSourceResolverOp *v55; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v56; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v57; // [rsp+70h] [rbp-90h]
  PROPVARIANT pvar; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v59[12]; // [rsp+90h] [rbp-70h]
  _BYTE v60[16]; // [rsp+F0h] [rbp-10h] BYREF

  v59[1] = L"dummy.asf";
  ppv = 0;
  v59[0] = 0;
  v59[2] = L"dummy.mp3";
  v55 = 0;
  v59[3] = L"dummy.mp4";
  v54 = 0;
  v59[4] = L"dummy.avi";
  v59[5] = L"dummy.m2ts";
  v59[6] = L"dummy.wav";
  v59[7] = L"dummy.adts";
  v59[8] = L"dummy.ac3";
  v59[9] = L"dummy.mkv";
  v59[10] = L"dummy.flac";
  v57 = 0;
  v56 = 0;
  memset(&pvar, 0, sizeof(pvar));
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v52,
    "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
    416);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v10 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                       *((_QWORD *)this + 50),
                       v60);
    *((_DWORD *)ThreadRelativeContext + 504) = v9;
    *((_OWORD *)ThreadRelativeContext + 125) = v10;
  }
  *a4 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  AsyncSourceReader = PSCreateMemoryPropertyStore(&IID_IPropertyStore, &ppv);
  if ( AsyncSourceReader >= 0 )
  {
    LOWORD(v56) = 11;
    WORD4(v56) = -1;
    AsyncSourceReader = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(*(_QWORD *)ppv + 48LL))(
                          ppv,
                          &MFPKEY_MediaSource_DisableReadAhead,
                          &v56);
    if ( AsyncSourceReader >= 0 )
    {
      AsyncSourceReader = (*(__int64 (__fastcall **)(void *, __int64 *, __int128 *))(*(_QWORD *)ppv + 48LL))(
                            ppv,
                            qword_1801A0A60,
                            &v56);
      if ( AsyncSourceReader >= 0 )
      {
        if ( *((_DWORD *)this + 7) == 5
          && (AsyncSourceReader = (*(__int64 (__fastcall **)(void *, __int64 *, __int128 *))(*(_QWORD *)ppv + 48LL))(
                                    ppv,
                                    qword_1801A0A48,
                                    &v56),
              AsyncSourceReader < 0) )
        {
          v26 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
            CallStackTracing::s_wpInstance = v27;
            if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
            {
              v26 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v26 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          if ( g_wppLevels )
          {
            v16 = 31;
            goto LABEL_106;
          }
        }
        else
        {
          CMFPropVariant::operator=(&pvar, *((_QWORD *)this + 50));
          AsyncSourceReader = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                ppv,
                                MFPKEY_TELEMETRY_SESSION,
                                &pvar);
          if ( AsyncSourceReader >= 0 )
          {
            v33 = 0;
            if ( *((_DWORD *)this + 7) < 0xBu )
              v33 = (const unsigned __int16 *)v59[*((int *)this + 7)];
            v35 = CMFVideoThumbnail::ElapsedTime(this);
            if ( v35 < *((_QWORD *)this + 45) )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
              AsyncSourceReader = CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance(
                                    *((struct IMFTelemetrySession **)this + 50),
                                    &v55);
              if ( AsyncSourceReader >= 0 )
              {
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54);
                AsyncSourceReader = CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource(
                                      v55,
                                      a3,
                                      a2,
                                      v33,
                                      (struct IPropertyStore *)ppv,
                                      (*((_DWORD *)this + 90) - (int)v35) / 10000,
                                      &v54);
                if ( AsyncSourceReader >= 0 )
                {
                  AsyncSourceReader = CMFVideoThumbnail::CreateAsyncSourceReader(this, v54, 0, a4);
                  if ( AsyncSourceReader < 0 )
                  {
                    v48 = (wchar_t *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47);
                      CallStackTracing::s_wpInstance = v49;
                      if ( v49
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(
                             v49,
                             2032) )
                      {
                        v48 = (wchar_t *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v48 = &qword_1801B97E0;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                      }
                    }
                    if ( *((_BYTE *)v48 + 8) )
                    {
                      v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
                      if ( *((_DWORD *)v50 + 499) != AsyncSourceReader )
                        CallStackContext::TraceFailure(
                          v50,
                          "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                          457,
                          AsyncSourceReader);
                    }
                    if ( g_wppLevels )
                    {
                      v16 = 36;
                      goto LABEL_106;
                    }
                  }
                }
                else
                {
                  v44 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43);
                    CallStackTracing::s_wpInstance = v45;
                    if ( v45
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
                    {
                      v44 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v44 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                    }
                  }
                  if ( *((_BYTE *)v44 + 8) )
                  {
                    v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
                    if ( *((_DWORD *)v46 + 499) != AsyncSourceReader )
                      CallStackContext::TraceFailure(
                        v46,
                        "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                        455,
                        AsyncSourceReader);
                  }
                  if ( g_wppLevels )
                  {
                    v16 = 35;
                    goto LABEL_106;
                  }
                }
              }
              else
              {
                v40 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
                  CallStackTracing::s_wpInstance = v41;
                  if ( v41
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
                  {
                    v40 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v40 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                  }
                }
                if ( *((_BYTE *)v40 + 8) )
                {
                  v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
                  if ( *((_DWORD *)v42 + 499) != AsyncSourceReader )
                    CallStackContext::TraceFailure(
                      v42,
                      "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                      453,
                      AsyncSourceReader);
                }
                if ( g_wppLevels )
                {
                  v16 = 34;
                  goto LABEL_106;
                }
              }
            }
            else
            {
              v36 = (wchar_t *)CallStackTracing::s_wpInstance;
              AsyncSourceReader = -2147418113;
              if ( !CallStackTracing::s_wpInstance )
              {
                v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34);
                CallStackTracing::s_wpInstance = v37;
                if ( v37
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
                {
                  v36 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v36 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v36 + 8) )
              {
                v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
                if ( *((_DWORD *)v38 + 499) != -2147418113 )
                  CallStackContext::TraceFailure(
                    v38,
                    "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                    450,
                    -2147418113);
              }
              if ( g_wppLevels )
              {
                v16 = 33;
                goto LABEL_106;
              }
            }
          }
          else
          {
            v30 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
              CallStackTracing::s_wpInstance = v31;
              if ( v31
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
              {
                v30 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v30 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v30 + 8) )
            {
              v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
              if ( *((_DWORD *)v32 + 499) != AsyncSourceReader )
                CallStackContext::TraceFailure(
                  v32,
                  "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                  439,
                  AsyncSourceReader);
            }
            if ( g_wppLevels )
            {
              v16 = 32;
              goto LABEL_106;
            }
          }
        }
      }
      else
      {
        v22 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
          CallStackTracing::s_wpInstance = v23;
          if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
          {
            v22 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v22 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        if ( g_wppLevels )
        {
          v16 = 30;
          goto LABEL_106;
        }
      }
    }
    else
    {
      v18 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
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
        if ( *((_DWORD *)v20 + 499) != AsyncSourceReader )
          CallStackContext::TraceFailure(
            v20,
            "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
            426,
            AsyncSourceReader);
      }
      if ( g_wppLevels )
      {
        v16 = 29;
        goto LABEL_106;
      }
    }
  }
  else
  {
    v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
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
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v15 + 499) != AsyncSourceReader )
        CallStackContext::TraceFailure(
          v15,
          "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
          420,
          AsyncSourceReader);
    }
    if ( g_wppLevels )
    {
      v16 = 28;
LABEL_106:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
        this,
        AsyncSourceReader);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v52);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54);
  CMFPropVariant::Clear(&pvar);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)AsyncSourceReader;
}

```

## disassembly

```asm
0x1800b554c  push    rbp
0x1800b554e  push    rbx
0x1800b554f  push    rsi
0x1800b5550  push    rdi
0x1800b5551  push    r12
0x1800b5553  push    r13
0x1800b5555  push    r14
0x1800b5557  push    r15
0x1800b5559  lea     rbp, [rsp-18h]
0x1800b555e  sub     rsp, 118h
0x1800b5565  mov     rax, cs:__security_cookie
0x1800b556c  xor     rax, rsp
0x1800b556f  mov     [rbp+50h+var_50], rax
0x1800b5573  xor     r14d, r14d
0x1800b5576  lea     rax, aDummyAsf; "dummy.asf"
0x1800b557d  mov     [rbp+50h+var_B8], rax
0x1800b5581  lea     rdi, aCmfvideothumbn_1; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800b5588  xorps   xmm0, xmm0
0x1800b558b  mov     [rsp+150h+ppv], r14
0x1800b5590  lea     rax, aDummyMp3; "dummy.mp3"
0x1800b5597  mov     [rbp+50h+var_C0], r14
0x1800b559b  mov     [rbp+50h+var_B0], rax
0x1800b559f  mov     r13, r8
0x1800b55a2  lea     rax, aDummyMp4; "dummy.mp4"
0x1800b55a9  mov     [rsp+150h+var_F8], r14
0x1800b55ae  mov     [rbp+50h+var_A8], rax
0x1800b55b2  mov     r12, rdx
0x1800b55b5  lea     rax, aDummyAvi; "dummy.avi"
0x1800b55bc  mov     [rsp+150h+var_100], r14
0x1800b55c1  mov     [rbp+50h+var_A0], rax
0x1800b55c5  mov     rsi, rcx
0x1800b55c8  lea     rax, aDummyM2ts; "dummy.m2ts"
0x1800b55cf  mov     r8d, 1A0h; int
0x1800b55d5  mov     [rbp+50h+var_98], rax
0x1800b55d9  lea     rcx, [rsp+150h+var_110]; this
0x1800b55de  lea     rax, aDummyWav; "dummy.wav"
0x1800b55e5  mov     rdx, rdi; char *
0x1800b55e8  mov     [rbp+50h+var_90], rax
0x1800b55ec  mov     r15, r9
0x1800b55ef  lea     rax, aDummyAdts; "dummy.adts"
0x1800b55f6  mov     [rbp+50h+var_88], rax
0x1800b55fa  lea     rax, aDummyAc3; "dummy.ac3"
0x1800b5601  mov     [rbp+50h+var_80], rax
0x1800b5605  lea     rax, aDummyMkv; "dummy.mkv"
0x1800b560c  mov     [rbp+50h+var_78], rax
0x1800b5610  lea     rax, aDummyFlac; "dummy.flac"
0x1800b5617  mov     [rbp+50h+var_70], rax
0x1800b561b  xor     eax, eax
0x1800b561d  mov     [rsp+150h+var_E0], rax
0x1800b5622  mov     qword ptr [rbp+50h+pvar+10h], rax
0x1800b5626  movups  [rsp+150h+var_F0], xmm0
0x1800b562b  movups  xmmword ptr [rsp+150h+pvar], xmm0
0x1800b5630  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b5635  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b563c  cmp     [rcx+8], r14b
0x1800b5640  jz      short loc_1800B569D
0x1800b5642  cmp     [rsi+190h], r14
0x1800b5649  jz      short loc_1800B569D
0x1800b564b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b5650  mov     rcx, [rsi+190h]
0x1800b5657  mov     rdi, rax
0x1800b565a  mov     rdx, [rcx]
0x1800b565d  mov     rax, [rdx+128h]
0x1800b5664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5669  mov     rcx, [rsi+190h]
0x1800b5670  mov     ebx, eax
0x1800b5672  mov     rdx, [rcx]
0x1800b5675  mov     rax, [rdx+118h]
0x1800b567c  lea     rdx, [rbp+50h+var_60]
0x1800b5680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5685  movups  xmm0, xmmword ptr [rax]
0x1800b5688  mov     [rdi+7E0h], ebx
0x1800b568e  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800b5696  lea     rdi, aCmfvideothumbn_1; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800b569d  lea     rcx, [rsp+150h+ppv]
0x1800b56a2  mov     [r15], r14
0x1800b56a5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b56aa  lea     rdx, [rsp+150h+ppv]; ppv
0x1800b56af  lea     rcx, IID_IPropertyStore; riid
0x1800b56b6  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800b56bd  nop     dword ptr [rax+rax+00h]
0x1800b56c2  mov     ebx, eax
0x1800b56c4  test    eax, eax
0x1800b56c6  jns     loc_1800B575D
0x1800b56cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b56d3  test    rcx, rcx
0x1800b56d6  jnz     short loc_1800B571F
0x1800b56d8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b56df  nop     dword ptr [rax+rax+00h]
0x1800b56e4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b56eb  mov     rcx, rax
0x1800b56ee  test    rax, rax
0x1800b56f1  jz      short loc_1800B5711
0x1800b56f3  mov     rax, [rax]
0x1800b56f6  mov     edx, 7F0h
0x1800b56fb  mov     rax, [rax+8]
0x1800b56ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5704  test    eax, eax
0x1800b5706  jz      short loc_1800B5711
0x1800b5708  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b570f  jmp     short loc_1800B571F
0x1800b5711  lea     rcx, qword_1801B97E0; this
0x1800b5718  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b571f  cmp     [rcx+8], r14b
0x1800b5723  jz      short loc_1800B5746
0x1800b5725  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b572a  cmp     [rax+7CCh], ebx
0x1800b5730  jz      short loc_1800B5746
0x1800b5732  mov     r9d, ebx; int
0x1800b5735  mov     r8d, 1A4h; int
0x1800b573b  mov     rdx, rdi; char *
0x1800b573e  mov     rcx, rax; this
0x1800b5741  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b5746  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b574d  jb      loc_1800B5DA8
0x1800b5753  mov     edx, 1Ch
0x1800b5758  jmp     loc_1800B5D8A
0x1800b575d  mov     rcx, [rsp+150h+ppv]
0x1800b5762  lea     r8, [rsp+150h+var_F0]
0x1800b5767  mov     eax, 0Bh
0x1800b576c  lea     rdx, MFPKEY_MediaSource_DisableReadAhead
0x1800b5773  mov     word ptr [rsp+150h+var_F0], ax
0x1800b5778  or      eax, 0FFFFFFFFh
0x1800b577b  mov     word ptr [rsp+150h+var_F0+8], ax
0x1800b5780  mov     rax, [rcx]
0x1800b5783  mov     rax, [rax+30h]
0x1800b5787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b578c  mov     ebx, eax
0x1800b578e  test    eax, eax
0x1800b5790  jns     loc_1800B5827
0x1800b5796  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b579d  test    rcx, rcx
0x1800b57a0  jnz     short loc_1800B57E9
0x1800b57a2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b57a9  nop     dword ptr [rax+rax+00h]
0x1800b57ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b57b5  mov     rcx, rax
0x1800b57b8  test    rax, rax
0x1800b57bb  jz      short loc_1800B57DB
0x1800b57bd  mov     rax, [rax]
0x1800b57c0  mov     edx, 7F0h
0x1800b57c5  mov     rax, [rax+8]
0x1800b57c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b57ce  test    eax, eax
0x1800b57d0  jz      short loc_1800B57DB
0x1800b57d2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b57d9  jmp     short loc_1800B57E9
0x1800b57db  lea     rcx, qword_1801B97E0; this
0x1800b57e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b57e9  cmp     [rcx+8], r14b
0x1800b57ed  jz      short loc_1800B5810
0x1800b57ef  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b57f4  cmp     [rax+7CCh], ebx
0x1800b57fa  jz      short loc_1800B5810
0x1800b57fc  mov     r9d, ebx; int
0x1800b57ff  mov     r8d, 1AAh; int
0x1800b5805  mov     rdx, rdi; char *
0x1800b5808  mov     rcx, rax; this
0x1800b580b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b5810  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b5817  jb      loc_1800B5DA8
0x1800b581d  mov     edx, 1Dh
0x1800b5822  jmp     loc_1800B5D8A
0x1800b5827  mov     rcx, [rsp+150h+ppv]
0x1800b582c  lea     r8, [rsp+150h+var_F0]
0x1800b5831  lea     rdx, qword_1801A0A60
0x1800b5838  mov     rax, [rcx]
0x1800b583b  mov     rax, [rax+30h]
0x1800b583f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5844  mov     ebx, eax
0x1800b5846  test    eax, eax
0x1800b5848  jns     loc_1800B58DF
0x1800b584e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5855  test    rcx, rcx
0x1800b5858  jnz     short loc_1800B58A1
0x1800b585a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b5861  nop     dword ptr [rax+rax+00h]
0x1800b5866  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b586d  mov     rcx, rax
0x1800b5870  test    rax, rax
0x1800b5873  jz      short loc_1800B5893
0x1800b5875  mov     rax, [rax]
0x1800b5878  mov     edx, 7F0h
0x1800b587d  mov     rax, [rax+8]
0x1800b5881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5886  test    eax, eax
0x1800b5888  jz      short loc_1800B5893
0x1800b588a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5891  jmp     short loc_1800B58A1
0x1800b5893  lea     rcx, qword_1801B97E0; this
0x1800b589a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b58a1  cmp     [rcx+8], r14b
0x1800b58a5  jz      short loc_1800B58C8
0x1800b58a7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b58ac  cmp     [rax+7CCh], ebx
0x1800b58b2  jz      short loc_1800B58C8
0x1800b58b4  mov     r9d, ebx; int
0x1800b58b7  mov     r8d, 1ADh; int
0x1800b58bd  mov     rdx, rdi; char *
0x1800b58c0  mov     rcx, rax; this
0x1800b58c3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b58c8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b58cf  jb      loc_1800B5DA8
0x1800b58d5  mov     edx, 1Eh
0x1800b58da  jmp     loc_1800B5D8A
0x1800b58df  cmp     dword ptr [rsi+1Ch], 5
0x1800b58e3  jnz     loc_1800B59A1
0x1800b58e9  mov     rcx, [rsp+150h+ppv]
0x1800b58ee  lea     r8, [rsp+150h+var_F0]
0x1800b58f3  lea     rdx, qword_1801A0A48
0x1800b58fa  mov     rax, [rcx]
0x1800b58fd  mov     rax, [rax+30h]
0x1800b5901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5906  mov     ebx, eax
0x1800b5908  test    eax, eax
0x1800b590a  jns     loc_1800B59A1
0x1800b5910  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5917  test    rcx, rcx
0x1800b591a  jnz     short loc_1800B5963
0x1800b591c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b5923  nop     dword ptr [rax+rax+00h]
0x1800b5928  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b592f  mov     rcx, rax
0x1800b5932  test    rax, rax
0x1800b5935  jz      short loc_1800B5955
0x1800b5937  mov     rax, [rax]
0x1800b593a  mov     edx, 7F0h
0x1800b593f  mov     rax, [rax+8]
0x1800b5943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5948  test    eax, eax
0x1800b594a  jz      short loc_1800B5955
0x1800b594c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5953  jmp     short loc_1800B5963
0x1800b5955  lea     rcx, qword_1801B97E0; this
0x1800b595c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5963  cmp     [rcx+8], r14b
0x1800b5967  jz      short loc_1800B598A
0x1800b5969  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b596e  cmp     [rax+7CCh], ebx
0x1800b5974  jz      short loc_1800B598A
0x1800b5976  mov     r9d, ebx; int
0x1800b5979  mov     r8d, 1B2h; int
0x1800b597f  mov     rdx, rdi; char *
0x1800b5982  mov     rcx, rax; this
0x1800b5985  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b598a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b5991  jb      loc_1800B5DA8
0x1800b5997  mov     edx, 1Fh
0x1800b599c  jmp     loc_1800B5D8A
0x1800b59a1  mov     rdx, [rsi+190h]
0x1800b59a8  lea     rcx, [rsp+150h+pvar]
0x1800b59ad  call    ??4CMFPropVariant@@QEAAAEAV0@PEAUIUnknown@@@Z; CMFPropVariant::operator=(IUnknown *)
0x1800b59b2  mov     rcx, [rsp+150h+ppv]
0x1800b59b7  lea     r8, [rsp+150h+pvar]
0x1800b59bc  lea     rdx, MFPKEY_TELEMETRY_SESSION
0x1800b59c3  mov     rax, [rcx]
0x1800b59c6  mov     rax, [rax+30h]
0x1800b59ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b59cf  mov     ebx, eax
0x1800b59d1  test    eax, eax
0x1800b59d3  jns     loc_1800B5A6A
0x1800b59d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b59e0  test    rcx, rcx
0x1800b59e3  jnz     short loc_1800B5A2C
0x1800b59e5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b59ec  nop     dword ptr [rax+rax+00h]
0x1800b59f1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b59f8  mov     rcx, rax
0x1800b59fb  test    rax, rax
0x1800b59fe  jz      short loc_1800B5A1E
0x1800b5a00  mov     rax, [rax]
0x1800b5a03  mov     edx, 7F0h
0x1800b5a08  mov     rax, [rax+8]
0x1800b5a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5a11  test    eax, eax
0x1800b5a13  jz      short loc_1800B5A1E
0x1800b5a15  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5a1c  jmp     short loc_1800B5A2C
0x1800b5a1e  lea     rcx, qword_1801B97E0; this
0x1800b5a25  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5a2c  cmp     [rcx+8], r14b
0x1800b5a30  jz      short loc_1800B5A53
0x1800b5a32  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b5a37  cmp     [rax+7CCh], ebx
0x1800b5a3d  jz      short loc_1800B5A53
0x1800b5a3f  mov     r9d, ebx; int
0x1800b5a42  mov     r8d, 1B7h; int
0x1800b5a48  mov     rdx, rdi; char *
0x1800b5a4b  mov     rcx, rax; this
0x1800b5a4e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b5a53  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b5a5a  jb      loc_1800B5DA8
0x1800b5a60  mov     edx, 20h ; ' '
0x1800b5a65  jmp     loc_1800B5D8A
0x1800b5a6a  cmp     dword ptr [rsi+1Ch], 0Bh
0x1800b5a6e  mov     rdi, r14
0x1800b5a71  jnb     short loc_1800B5A7C
0x1800b5a73  movsxd  rax, dword ptr [rsi+1Ch]
0x1800b5a77  mov     rdi, [rbp+rax*8+50h+var_C0]
0x1800b5a7c  mov     rcx, rsi; this
  ... truncated ...
```
