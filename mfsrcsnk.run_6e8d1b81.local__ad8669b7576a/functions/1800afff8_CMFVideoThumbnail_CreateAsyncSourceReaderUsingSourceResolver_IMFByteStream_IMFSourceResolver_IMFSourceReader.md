# CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver(IMFByteStream *,IMFSourceResolver *,IMFSourceReader * *)

- ea: `0x1800afff8`
- end: `0x1800b086c`
- name: `?CreateAsyncSourceReaderUsingSourceResolver@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAUIMFSourceResolver@@PEAPEAUIMFSourceReader@@@Z`
- size: `2164`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFByteStream *, struct IMFSourceResolver *, struct IMFSourceReader **)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800bf59c`
- `0x1800ee114`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180025548`
- `0x18006c7f4`
- `0x1800734a8`
- `0x180073b14`
- `0x18009a9a4`
- `0x1800afff8`
- `0x1800bc000`
- `0x1800fe368`
- `0x1801099f0`
- `0x18015a810`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b017e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0242`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b02f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b03b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0473`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b052d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b05e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b06d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0780`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b017e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0242`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b02f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b03b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0473`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b052d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b05e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b06d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0780`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800b0162`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800b0162`

## string_xrefs

- `0x1800b002d`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x1800b0142`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x1800b0584`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x1800b0638`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x1800b072b`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x1800b07d7`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`

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
  __int128 v58; // [rsp+78h] [rbp-88h] BYREF
  __int64 v59; // [rsp+88h] [rbp-78h]
  _QWORD v60[12]; // [rsp+90h] [rbp-70h]
  _BYTE v61[16]; // [rsp+F0h] [rbp-10h] BYREF

  v60[1] = L"dummy.asf";
  ppv = 0;
  v60[0] = 0;
  v60[2] = L"dummy.mp3";
  v55 = 0;
  v60[3] = L"dummy.mp4";
  v54 = 0;
  v60[4] = L"dummy.avi";
  v60[5] = L"dummy.m2ts";
  v60[6] = L"dummy.wav";
  v60[7] = L"dummy.adts";
  v60[8] = L"dummy.ac3";
  v60[9] = L"dummy.mkv";
  v60[10] = L"dummy.flac";
  v57 = 0;
  v59 = 0;
  v56 = 0;
  v58 = 0;
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
                       v61);
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
                            qword_180197A58,
                            &v56);
      if ( AsyncSourceReader >= 0 )
      {
        if ( *((_DWORD *)this + 7) == 5
          && (AsyncSourceReader = (*(__int64 (__fastcall **)(void *, __int64 *, __int128 *))(*(_QWORD *)ppv + 48LL))(
                                    ppv,
                                    qword_180197A40,
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
              v26 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          CMFPropVariant::operator=(&v58, *((_QWORD *)this + 50));
          AsyncSourceReader = (*(__int64 (__fastcall **)(void *, __int64 *, __int128 *))(*(_QWORD *)ppv + 48LL))(
                                ppv,
                                MFPKEY_TELEMETRY_SESSION,
                                &v58);
          if ( AsyncSourceReader >= 0 )
          {
            v33 = 0;
            if ( *((_DWORD *)this + 7) < 0xBu )
              v33 = (const unsigned __int16 *)v60[*((int *)this + 7)];
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
                        v48 = &qword_1801B07E0;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                      v44 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                    v40 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                  v36 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                v30 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v22 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v18 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v13 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
  CMFPropVariant::Clear((CMFPropVariant *)&v58);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)AsyncSourceReader;
}

```

## disassembly

```asm
0x1800afff8  push    rbp
0x1800afffa  push    rbx
0x1800afffb  push    rsi
0x1800afffc  push    rdi
0x1800afffd  push    r12
0x1800affff  push    r13
0x1800b0001  push    r14
0x1800b0003  push    r15
0x1800b0005  lea     rbp, [rsp-18h]
0x1800b000a  sub     rsp, 118h
0x1800b0011  mov     rax, cs:__security_cookie
0x1800b0018  xor     rax, rsp
0x1800b001b  mov     [rbp+50h+var_50], rax
0x1800b001f  xor     r14d, r14d
0x1800b0022  lea     rax, aDummyAsf; "dummy.asf"
0x1800b0029  mov     [rbp+50h+var_B8], rax
0x1800b002d  lea     rdi, aCmfvideothumbn_1; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800b0034  xorps   xmm0, xmm0
0x1800b0037  mov     [rsp+150h+ppv], r14
0x1800b003c  lea     rax, aDummyMp3; "dummy.mp3"
0x1800b0043  mov     [rbp+50h+var_C0], r14
0x1800b0047  mov     [rbp+50h+var_B0], rax
0x1800b004b  mov     r13, r8
0x1800b004e  lea     rax, aDummyMp4; "dummy.mp4"
0x1800b0055  mov     [rsp+150h+var_F8], r14
0x1800b005a  mov     [rbp+50h+var_A8], rax
0x1800b005e  mov     r12, rdx
0x1800b0061  lea     rax, aDummyAvi; "dummy.avi"
0x1800b0068  mov     [rsp+150h+var_100], r14
0x1800b006d  mov     [rbp+50h+var_A0], rax
0x1800b0071  mov     rsi, rcx
0x1800b0074  lea     rax, aDummyM2ts; "dummy.m2ts"
0x1800b007b  mov     r8d, 1A0h; int
0x1800b0081  mov     [rbp+50h+var_98], rax
0x1800b0085  lea     rcx, [rsp+150h+var_110]; this
0x1800b008a  lea     rax, aDummyWav; "dummy.wav"
0x1800b0091  mov     rdx, rdi; char *
0x1800b0094  mov     [rbp+50h+var_90], rax
0x1800b0098  mov     r15, r9
0x1800b009b  lea     rax, aDummyAdts; "dummy.adts"
0x1800b00a2  mov     [rbp+50h+var_88], rax
0x1800b00a6  lea     rax, aDummyAc3; "dummy.ac3"
0x1800b00ad  mov     [rbp+50h+var_80], rax
0x1800b00b1  lea     rax, aDummyMkv; "dummy.mkv"
0x1800b00b8  mov     [rbp+50h+var_78], rax
0x1800b00bc  lea     rax, aDummyFlac; "dummy.flac"
0x1800b00c3  mov     [rbp+50h+var_70], rax
0x1800b00c7  xor     eax, eax
0x1800b00c9  mov     [rsp+150h+var_E0], rax
0x1800b00ce  mov     [rbp+50h+var_C8], rax
0x1800b00d2  movups  [rsp+150h+var_F0], xmm0
0x1800b00d7  movups  [rsp+150h+var_D8], xmm0
0x1800b00dc  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b00e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b00e8  cmp     [rcx+8], r14b
0x1800b00ec  jz      short loc_1800B0149
0x1800b00ee  cmp     [rsi+190h], r14
0x1800b00f5  jz      short loc_1800B0149
0x1800b00f7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b00fc  mov     rcx, [rsi+190h]
0x1800b0103  mov     rdi, rax
0x1800b0106  mov     rdx, [rcx]
0x1800b0109  mov     rax, [rdx+128h]
0x1800b0110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0115  mov     rcx, [rsi+190h]
0x1800b011c  mov     ebx, eax
0x1800b011e  mov     rdx, [rcx]
0x1800b0121  mov     rax, [rdx+118h]
0x1800b0128  lea     rdx, [rbp+50h+var_60]
0x1800b012c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0131  movups  xmm0, xmmword ptr [rax]
0x1800b0134  mov     [rdi+7E0h], ebx
0x1800b013a  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800b0142  lea     rdi, aCmfvideothumbn_1; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800b0149  lea     rcx, [rsp+150h+ppv]
0x1800b014e  mov     [r15], r14
0x1800b0151  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b0156  lea     rdx, [rsp+150h+ppv]; ppv
0x1800b015b  lea     rcx, IID_IPropertyStore; riid
0x1800b0162  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800b0168  mov     ebx, eax
0x1800b016a  test    eax, eax
0x1800b016c  jns     loc_1800B01FD
0x1800b0172  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0179  test    rcx, rcx
0x1800b017c  jnz     short loc_1800B01BF
0x1800b017e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b0184  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b018b  mov     rcx, rax
0x1800b018e  test    rax, rax
0x1800b0191  jz      short loc_1800B01B1
0x1800b0193  mov     rax, [rax]
0x1800b0196  mov     edx, 7F0h
0x1800b019b  mov     rax, [rax+8]
0x1800b019f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b01a4  test    eax, eax
0x1800b01a6  jz      short loc_1800B01B1
0x1800b01a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b01af  jmp     short loc_1800B01BF
0x1800b01b1  lea     rcx, qword_1801B07E0; this
0x1800b01b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b01bf  cmp     [rcx+8], r14b
0x1800b01c3  jz      short loc_1800B01E6
0x1800b01c5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b01ca  cmp     [rax+7CCh], ebx
0x1800b01d0  jz      short loc_1800B01E6
0x1800b01d2  mov     r9d, ebx; int
0x1800b01d5  mov     r8d, 1A4h; int
0x1800b01db  mov     rdx, rdi; char *
0x1800b01de  mov     rcx, rax; this
0x1800b01e1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b01e6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b01ed  jb      loc_1800B0818
0x1800b01f3  mov     edx, 1Ch
0x1800b01f8  jmp     loc_1800B07FA
0x1800b01fd  mov     rcx, [rsp+150h+ppv]
0x1800b0202  lea     r8, [rsp+150h+var_F0]
0x1800b0207  mov     eax, 0Bh
0x1800b020c  lea     rdx, MFPKEY_MediaSource_DisableReadAhead
0x1800b0213  mov     word ptr [rsp+150h+var_F0], ax
0x1800b0218  or      eax, 0FFFFFFFFh
0x1800b021b  mov     word ptr [rsp+150h+var_F0+8], ax
0x1800b0220  mov     rax, [rcx]
0x1800b0223  mov     rax, [rax+30h]
0x1800b0227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b022c  mov     ebx, eax
0x1800b022e  test    eax, eax
0x1800b0230  jns     loc_1800B02C1
0x1800b0236  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b023d  test    rcx, rcx
0x1800b0240  jnz     short loc_1800B0283
0x1800b0242  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b0248  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b024f  mov     rcx, rax
0x1800b0252  test    rax, rax
0x1800b0255  jz      short loc_1800B0275
0x1800b0257  mov     rax, [rax]
0x1800b025a  mov     edx, 7F0h
0x1800b025f  mov     rax, [rax+8]
0x1800b0263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0268  test    eax, eax
0x1800b026a  jz      short loc_1800B0275
0x1800b026c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0273  jmp     short loc_1800B0283
0x1800b0275  lea     rcx, qword_1801B07E0; this
0x1800b027c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0283  cmp     [rcx+8], r14b
0x1800b0287  jz      short loc_1800B02AA
0x1800b0289  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b028e  cmp     [rax+7CCh], ebx
0x1800b0294  jz      short loc_1800B02AA
0x1800b0296  mov     r9d, ebx; int
0x1800b0299  mov     r8d, 1AAh; int
0x1800b029f  mov     rdx, rdi; char *
0x1800b02a2  mov     rcx, rax; this
0x1800b02a5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b02aa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b02b1  jb      loc_1800B0818
0x1800b02b7  mov     edx, 1Dh
0x1800b02bc  jmp     loc_1800B07FA
0x1800b02c1  mov     rcx, [rsp+150h+ppv]
0x1800b02c6  lea     r8, [rsp+150h+var_F0]
0x1800b02cb  lea     rdx, qword_180197A58
0x1800b02d2  mov     rax, [rcx]
0x1800b02d5  mov     rax, [rax+30h]
0x1800b02d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b02de  mov     ebx, eax
0x1800b02e0  test    eax, eax
0x1800b02e2  jns     loc_1800B0373
0x1800b02e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b02ef  test    rcx, rcx
0x1800b02f2  jnz     short loc_1800B0335
0x1800b02f4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b02fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0301  mov     rcx, rax
0x1800b0304  test    rax, rax
0x1800b0307  jz      short loc_1800B0327
0x1800b0309  mov     rax, [rax]
0x1800b030c  mov     edx, 7F0h
0x1800b0311  mov     rax, [rax+8]
0x1800b0315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b031a  test    eax, eax
0x1800b031c  jz      short loc_1800B0327
0x1800b031e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0325  jmp     short loc_1800B0335
0x1800b0327  lea     rcx, qword_1801B07E0; this
0x1800b032e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0335  cmp     [rcx+8], r14b
0x1800b0339  jz      short loc_1800B035C
0x1800b033b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b0340  cmp     [rax+7CCh], ebx
0x1800b0346  jz      short loc_1800B035C
0x1800b0348  mov     r9d, ebx; int
0x1800b034b  mov     r8d, 1ADh; int
0x1800b0351  mov     rdx, rdi; char *
0x1800b0354  mov     rcx, rax; this
0x1800b0357  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b035c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b0363  jb      loc_1800B0818
0x1800b0369  mov     edx, 1Eh
0x1800b036e  jmp     loc_1800B07FA
0x1800b0373  cmp     dword ptr [rsi+1Ch], 5
0x1800b0377  jnz     loc_1800B042F
0x1800b037d  mov     rcx, [rsp+150h+ppv]
0x1800b0382  lea     r8, [rsp+150h+var_F0]
0x1800b0387  lea     rdx, qword_180197A40
0x1800b038e  mov     rax, [rcx]
0x1800b0391  mov     rax, [rax+30h]
0x1800b0395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b039a  mov     ebx, eax
0x1800b039c  test    eax, eax
0x1800b039e  jns     loc_1800B042F
0x1800b03a4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b03ab  test    rcx, rcx
0x1800b03ae  jnz     short loc_1800B03F1
0x1800b03b0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b03b6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b03bd  mov     rcx, rax
0x1800b03c0  test    rax, rax
0x1800b03c3  jz      short loc_1800B03E3
0x1800b03c5  mov     rax, [rax]
0x1800b03c8  mov     edx, 7F0h
0x1800b03cd  mov     rax, [rax+8]
0x1800b03d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b03d6  test    eax, eax
0x1800b03d8  jz      short loc_1800B03E3
0x1800b03da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b03e1  jmp     short loc_1800B03F1
0x1800b03e3  lea     rcx, qword_1801B07E0; this
0x1800b03ea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b03f1  cmp     [rcx+8], r14b
0x1800b03f5  jz      short loc_1800B0418
0x1800b03f7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b03fc  cmp     [rax+7CCh], ebx
0x1800b0402  jz      short loc_1800B0418
0x1800b0404  mov     r9d, ebx; int
0x1800b0407  mov     r8d, 1B2h; int
0x1800b040d  mov     rdx, rdi; char *
0x1800b0410  mov     rcx, rax; this
0x1800b0413  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b0418  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b041f  jb      loc_1800B0818
0x1800b0425  mov     edx, 1Fh
0x1800b042a  jmp     loc_1800B07FA
0x1800b042f  mov     rdx, [rsi+190h]
0x1800b0436  lea     rcx, [rsp+150h+var_D8]
0x1800b043b  call    ??4CMFPropVariant@@QEAAAEAV0@PEAUIUnknown@@@Z; CMFPropVariant::operator=(IUnknown *)
0x1800b0440  mov     rcx, [rsp+150h+ppv]
0x1800b0445  lea     r8, [rsp+150h+var_D8]
0x1800b044a  lea     rdx, MFPKEY_TELEMETRY_SESSION
0x1800b0451  mov     rax, [rcx]
0x1800b0454  mov     rax, [rax+30h]
0x1800b0458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b045d  mov     ebx, eax
0x1800b045f  test    eax, eax
0x1800b0461  jns     loc_1800B04F2
0x1800b0467  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b046e  test    rcx, rcx
0x1800b0471  jnz     short loc_1800B04B4
0x1800b0473  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b0479  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0480  mov     rcx, rax
0x1800b0483  test    rax, rax
0x1800b0486  jz      short loc_1800B04A6
0x1800b0488  mov     rax, [rax]
0x1800b048b  mov     edx, 7F0h
0x1800b0490  mov     rax, [rax+8]
0x1800b0494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0499  test    eax, eax
0x1800b049b  jz      short loc_1800B04A6
0x1800b049d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b04a4  jmp     short loc_1800B04B4
0x1800b04a6  lea     rcx, qword_1801B07E0; this
0x1800b04ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b04b4  cmp     [rcx+8], r14b
0x1800b04b8  jz      short loc_1800B04DB
0x1800b04ba  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b04bf  cmp     [rax+7CCh], ebx
0x1800b04c5  jz      short loc_1800B04DB
0x1800b04c7  mov     r9d, ebx; int
0x1800b04ca  mov     r8d, 1B7h; int
0x1800b04d0  mov     rdx, rdi; char *
0x1800b04d3  mov     rcx, rax; this
0x1800b04d6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b04db  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b04e2  jb      loc_1800B0818
0x1800b04e8  mov     edx, 20h ; ' '
0x1800b04ed  jmp     loc_1800B07FA
0x1800b04f2  cmp     dword ptr [rsi+1Ch], 0Bh
0x1800b04f6  mov     rdi, r14
0x1800b04f9  jnb     short loc_1800B0504
0x1800b04fb  movsxd  rax, dword ptr [rsi+1Ch]
0x1800b04ff  mov     rdi, [rbp+rax*8+50h+var_C0]
0x1800b0504  mov     rcx, rsi; this
0x1800b0507  call    ?ElapsedTime@CMFVideoThumbnail@@AEAA_JXZ; CMFVideoThumbnail::ElapsedTime(void)
0x1800b050c  mov     r14, rax
0x1800b050f  cmp     rax, [rsi+168h]
0x1800b0516  jl      loc_1800B05B0
0x1800b051c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0523  mov     ebx, 8000FFFFh
  ... truncated ...
```
