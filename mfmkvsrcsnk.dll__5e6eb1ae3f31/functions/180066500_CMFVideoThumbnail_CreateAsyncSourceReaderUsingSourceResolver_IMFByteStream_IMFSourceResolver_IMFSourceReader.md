# CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver(IMFByteStream *,IMFSourceResolver *,IMFSourceReader * *)

- ea: `0x180066500`
- end: `0x180066d93`
- name: `?CreateAsyncSourceReaderUsingSourceResolver@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAUIMFSourceResolver@@PEAPEAUIMFSourceReader@@@Z`
- size: `2195`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFByteStream *, struct IMFSourceResolver *, struct IMFSourceReader **)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18006764c`
- `0x1800678b0`

## callees

- `0x1800023e0`
- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180065ec8`
- `0x180066500`
- `0x180066d9c`
- `0x1800671c8`
- `0x180067afc`
- `0x180069a78`
- `0x180071330`
- `0x180071524`
- `0x1800af010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18006666a`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18006666a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180066686`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006674a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800667fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800668b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006699d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180066a57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180066b0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180066bfe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180066ca7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180066686`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006674a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800667fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800668b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006699d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180066a57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180066b0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180066bfe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180066ca7`

## string_xrefs

- `0x180066535`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x18006664a`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x180066aae`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x180066b62`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x180066c55`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x180066cfe`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`

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
  HRESULT AsyncSourceReader; // ebx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
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
  LARGE_INTEGER v37; // rbx
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  const unsigned __int16 *v44; // rdi
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 v48; // r14
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 v58; // rdx
  _BOOL8 v59; // r8
  __int64 v60; // r9
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // r9
  __int64 *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  _BYTE v71[8]; // [rsp+40h] [rbp-C0h] BYREF
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  struct IMFMediaSource *v73; // [rsp+50h] [rbp-B0h] BYREF
  struct CMFVideoThumbnail::CMFSourceResolverOp *v74; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v75; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v76; // [rsp+70h] [rbp-90h]
  PROPVARIANT pvar; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v78[12]; // [rsp+90h] [rbp-70h]
  _BYTE v79[16]; // [rsp+F0h] [rbp-10h] BYREF

  v78[1] = L"dummy.asf";
  ppv = 0;
  v78[0] = 0;
  v78[2] = L"dummy.mp3";
  v74 = 0;
  v78[3] = L"dummy.mp4";
  v73 = 0;
  v78[4] = L"dummy.avi";
  v78[5] = L"dummy.m2ts";
  v78[6] = L"dummy.wav";
  v78[7] = L"dummy.adts";
  v78[8] = L"dummy.ac3";
  v78[9] = L"dummy.mkv";
  v78[10] = L"dummy.flac";
  v76 = 0;
  v75 = 0;
  memset(&pvar, 0, sizeof(pvar));
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v71,
    "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
    416);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v10 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                       *((_QWORD *)this + 50),
                       v79);
    *((_DWORD *)ThreadRelativeContext + 504) = v9;
    *((_OWORD *)ThreadRelativeContext + 125) = v10;
  }
  *a4 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  AsyncSourceReader = PSCreateMemoryPropertyStore(&IID_IPropertyStore, &ppv);
  if ( AsyncSourceReader >= 0 )
  {
    LOWORD(v75) = 11;
    WORD4(v75) = -1;
    AsyncSourceReader = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(*(_QWORD *)ppv + 48LL))(
                          ppv,
                          &MFPKEY_MediaSource_DisableReadAhead,
                          &v75);
    if ( AsyncSourceReader >= 0 )
    {
      AsyncSourceReader = (*(__int64 (__fastcall **)(void *, __int64 *, __int128 *))(*(_QWORD *)ppv + 48LL))(
                            ppv,
                            qword_1800C0F28,
                            &v75);
      if ( AsyncSourceReader >= 0 )
      {
        if ( *((_DWORD *)this + 7) == 5
          && (AsyncSourceReader = (*(__int64 (__fastcall **)(void *, __int64 *, __int128 *))(*(_QWORD *)ppv + 48LL))(
                                    ppv,
                                    qword_1800C0F40,
                                    &v75),
              AsyncSourceReader < 0) )
        {
          v34 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
            CallStackTracing::s_wpInstance = v35;
            if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
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
            if ( *((_DWORD *)v36 + 499) != AsyncSourceReader )
              CallStackContext::TraceFailure(
                v36,
                "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                434,
                AsyncSourceReader);
          }
          if ( g_wppLevels )
          {
            v18 = 31;
            goto LABEL_108;
          }
        }
        else
        {
          v37 = *(LARGE_INTEGER *)((char *)this + 400);
          CMFPropVariant::Clear(&pvar);
          pvar.hVal = v37;
          pvar.vt = 13;
          if ( v37.QuadPart )
            (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v37.QuadPart + 8LL))(v37);
          AsyncSourceReader = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                ppv,
                                MFPKEY_TELEMETRY_SESSION,
                                &pvar);
          if ( AsyncSourceReader >= 0 )
          {
            v44 = 0;
            if ( *((_DWORD *)this + 7) < 0xBu )
              v44 = (const unsigned __int16 *)v78[*((int *)this + 7)];
            v48 = CMFVideoThumbnail::ElapsedTime(this);
            if ( v48 < *((_QWORD *)this + 45) )
            {
              Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v74);
              AsyncSourceReader = CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance(
                                    *((struct IMFTelemetrySession **)this + 50),
                                    &v74);
              if ( AsyncSourceReader >= 0 )
              {
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
                AsyncSourceReader = CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource(
                                      v74,
                                      a3,
                                      a2,
                                      v44,
                                      (struct IPropertyStore *)ppv,
                                      (*((_DWORD *)this + 90) - (int)v48) / 10000,
                                      &v73);
                if ( AsyncSourceReader >= 0 )
                {
                  AsyncSourceReader = CMFVideoThumbnail::CreateAsyncSourceReader(this, v73, v59, a4);
                  if ( AsyncSourceReader < 0 )
                  {
                    v67 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v64, v65, v66);
                      CallStackTracing::s_wpInstance = v68;
                      if ( v68
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(
                             v68,
                             2032) )
                      {
                        v67 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v67 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                      }
                    }
                    if ( *((_BYTE *)v67 + 8) )
                    {
                      v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v67);
                      if ( *((_DWORD *)v69 + 499) != AsyncSourceReader )
                        CallStackContext::TraceFailure(
                          v69,
                          "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                          457,
                          AsyncSourceReader);
                    }
                    if ( g_wppLevels )
                    {
                      v18 = 36;
                      goto LABEL_108;
                    }
                  }
                }
                else
                {
                  v61 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58, v59, v60);
                    CallStackTracing::s_wpInstance = v62;
                    if ( v62
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
                    {
                      v61 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v61 = &qword_1800D6F70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                    }
                  }
                  if ( *((_BYTE *)v61 + 8) )
                  {
                    v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
                    if ( *((_DWORD *)v63 + 499) != AsyncSourceReader )
                      CallStackContext::TraceFailure(
                        v63,
                        "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                        455,
                        AsyncSourceReader);
                  }
                  if ( g_wppLevels )
                  {
                    v18 = 35;
                    goto LABEL_108;
                  }
                }
              }
              else
              {
                v55 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53, v54);
                  CallStackTracing::s_wpInstance = v56;
                  if ( v56
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
                  {
                    v55 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v55 = &qword_1800D6F70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                  }
                }
                if ( *((_BYTE *)v55 + 8) )
                {
                  v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
                  if ( *((_DWORD *)v57 + 499) != AsyncSourceReader )
                    CallStackContext::TraceFailure(
                      v57,
                      "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                      453,
                      AsyncSourceReader);
                }
                if ( g_wppLevels )
                {
                  v18 = 34;
                  goto LABEL_108;
                }
              }
            }
            else
            {
              v49 = (__int64 *)CallStackTracing::s_wpInstance;
              AsyncSourceReader = -2147418113;
              if ( !CallStackTracing::s_wpInstance )
              {
                v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v46, v47);
                CallStackTracing::s_wpInstance = v50;
                if ( v50
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
                {
                  v49 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v49 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                }
              }
              if ( *((_BYTE *)v49 + 8) )
              {
                v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
                if ( *((_DWORD *)v51 + 499) != -2147418113 )
                  CallStackContext::TraceFailure(
                    v51,
                    "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                    450,
                    -2147418113);
              }
              if ( g_wppLevels )
              {
                v18 = 33;
                goto LABEL_108;
              }
            }
          }
          else
          {
            v41 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39, v40);
              CallStackTracing::s_wpInstance = v42;
              if ( v42
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
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
              if ( *((_DWORD *)v43 + 499) != AsyncSourceReader )
                CallStackContext::TraceFailure(
                  v43,
                  "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
                  439,
                  AsyncSourceReader);
            }
            if ( g_wppLevels )
            {
              v18 = 32;
              goto LABEL_108;
            }
          }
        }
      }
      else
      {
        v28 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26, v27);
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
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
          if ( *((_DWORD *)v30 + 499) != AsyncSourceReader )
            CallStackContext::TraceFailure(
              v30,
              "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
              429,
              AsyncSourceReader);
        }
        if ( g_wppLevels )
        {
          v18 = 30;
          goto LABEL_108;
        }
      }
    }
    else
    {
      v22 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
        CallStackTracing::s_wpInstance = v23;
        if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
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
        if ( *((_DWORD *)v24 + 499) != AsyncSourceReader )
          CallStackContext::TraceFailure(
            v24,
            "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
            426,
            AsyncSourceReader);
      }
      if ( g_wppLevels )
      {
        v18 = 29;
        goto LABEL_108;
      }
    }
  }
  else
  {
    v15 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v13, v14);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)v17 + 499) != AsyncSourceReader )
        CallStackContext::TraceFailure(
          v17,
          "CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver",
          420,
          AsyncSourceReader);
    }
    if ( g_wppLevels )
    {
      v18 = 28;
LABEL_108:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
        this,
        AsyncSourceReader);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v71);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
  CMFPropVariant::Clear(&pvar);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v74);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)AsyncSourceReader;
}

```

## disassembly

```asm
0x180066500  push    rbp
0x180066502  push    rbx
0x180066503  push    rsi
0x180066504  push    rdi
0x180066505  push    r12
0x180066507  push    r13
0x180066509  push    r14
0x18006650b  push    r15
0x18006650d  lea     rbp, [rsp-18h]
0x180066512  sub     rsp, 118h
0x180066519  mov     rax, cs:__security_cookie
0x180066520  xor     rax, rsp
0x180066523  mov     [rbp+50h+var_50], rax
0x180066527  xor     r14d, r14d
0x18006652a  lea     rax, aDummyAsf; "dummy.asf"
0x180066531  mov     [rbp+50h+var_B8], rax
0x180066535  lea     rdi, aCmfvideothumbn_1; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x18006653c  xorps   xmm0, xmm0
0x18006653f  mov     [rsp+150h+ppv], r14
0x180066544  lea     rax, aDummyMp3; "dummy.mp3"
0x18006654b  mov     [rbp+50h+var_C0], r14
0x18006654f  mov     [rbp+50h+var_B0], rax
0x180066553  mov     r13, r8
0x180066556  lea     rax, aDummyMp4; "dummy.mp4"
0x18006655d  mov     [rsp+150h+var_F8], r14
0x180066562  mov     [rbp+50h+var_A8], rax
0x180066566  mov     r12, rdx
0x180066569  lea     rax, aDummyAvi; "dummy.avi"
0x180066570  mov     [rsp+150h+var_100], r14
0x180066575  mov     [rbp+50h+var_A0], rax
0x180066579  mov     rsi, rcx
0x18006657c  lea     rax, aDummyM2ts; "dummy.m2ts"
0x180066583  mov     r8d, 1A0h; int
0x180066589  mov     [rbp+50h+var_98], rax
0x18006658d  lea     rcx, [rsp+150h+var_110]; this
0x180066592  lea     rax, aDummyWav; "dummy.wav"
0x180066599  mov     rdx, rdi; char *
0x18006659c  mov     [rbp+50h+var_90], rax
0x1800665a0  mov     r15, r9
0x1800665a3  lea     rax, aDummyAdts; "dummy.adts"
0x1800665aa  mov     [rbp+50h+var_88], rax
0x1800665ae  lea     rax, aDummyAc3; "dummy.ac3"
0x1800665b5  mov     [rbp+50h+var_80], rax
0x1800665b9  lea     rax, aDummyMkv; "dummy.mkv"
0x1800665c0  mov     [rbp+50h+var_78], rax
0x1800665c4  lea     rax, aDummyFlac; "dummy.flac"
0x1800665cb  mov     [rbp+50h+var_70], rax
0x1800665cf  xor     eax, eax
0x1800665d1  mov     [rsp+150h+var_E0], rax
0x1800665d6  mov     qword ptr [rbp+50h+pvar+10h], rax
0x1800665da  movups  [rsp+150h+var_F0], xmm0
0x1800665df  movups  xmmword ptr [rsp+150h+pvar], xmm0
0x1800665e4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800665e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800665f0  cmp     [rcx+8], r14b
0x1800665f4  jz      short loc_180066651
0x1800665f6  cmp     [rsi+190h], r14
0x1800665fd  jz      short loc_180066651
0x1800665ff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180066604  mov     rcx, [rsi+190h]
0x18006660b  mov     rdi, rax
0x18006660e  mov     rdx, [rcx]
0x180066611  mov     rax, [rdx+128h]
0x180066618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006661d  mov     rcx, [rsi+190h]
0x180066624  mov     ebx, eax
0x180066626  mov     rdx, [rcx]
0x180066629  mov     rax, [rdx+118h]
0x180066630  lea     rdx, [rbp+50h+var_60]
0x180066634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066639  movups  xmm0, xmmword ptr [rax]
0x18006663c  mov     [rdi+7E0h], ebx
0x180066642  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18006664a  lea     rdi, aCmfvideothumbn_1; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x180066651  lea     rcx, [rsp+150h+ppv]
0x180066656  mov     [r15], r14
0x180066659  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006665e  lea     rdx, [rsp+150h+ppv]; ppv
0x180066663  lea     rcx, IID_IPropertyStore; riid
0x18006666a  call    cs:__imp_PSCreateMemoryPropertyStore
0x180066670  mov     ebx, eax
0x180066672  test    eax, eax
0x180066674  jns     loc_180066705
0x18006667a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180066681  test    rcx, rcx
0x180066684  jnz     short loc_1800666C7
0x180066686  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006668c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180066693  mov     rcx, rax
0x180066696  test    rax, rax
0x180066699  jz      short loc_1800666B9
0x18006669b  mov     rax, [rax]
0x18006669e  mov     edx, 7F0h
0x1800666a3  mov     rax, [rax+8]
0x1800666a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800666ac  test    eax, eax
0x1800666ae  jz      short loc_1800666B9
0x1800666b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800666b7  jmp     short loc_1800666C7
0x1800666b9  lea     rcx, qword_1800D6F70; this
0x1800666c0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800666c7  cmp     [rcx+8], r14b
0x1800666cb  jz      short loc_1800666EE
0x1800666cd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800666d2  cmp     [rax+7CCh], ebx
0x1800666d8  jz      short loc_1800666EE
0x1800666da  mov     r9d, ebx; int
0x1800666dd  mov     r8d, 1A4h; int
0x1800666e3  mov     rdx, rdi; char *
0x1800666e6  mov     rcx, rax; this
0x1800666e9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800666ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800666f5  jb      loc_180066D3F
0x1800666fb  mov     edx, 1Ch
0x180066700  jmp     loc_180066D21
0x180066705  mov     rcx, [rsp+150h+ppv]
0x18006670a  lea     r8, [rsp+150h+var_F0]
0x18006670f  mov     eax, 0Bh
0x180066714  lea     rdx, MFPKEY_MediaSource_DisableReadAhead
0x18006671b  mov     word ptr [rsp+150h+var_F0], ax
0x180066720  or      eax, 0FFFFFFFFh
0x180066723  mov     word ptr [rsp+150h+var_F0+8], ax
0x180066728  mov     rax, [rcx]
0x18006672b  mov     rax, [rax+30h]
0x18006672f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066734  mov     ebx, eax
0x180066736  test    eax, eax
0x180066738  jns     loc_1800667C9
0x18006673e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180066745  test    rcx, rcx
0x180066748  jnz     short loc_18006678B
0x18006674a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180066750  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180066757  mov     rcx, rax
0x18006675a  test    rax, rax
0x18006675d  jz      short loc_18006677D
0x18006675f  mov     rax, [rax]
0x180066762  mov     edx, 7F0h
0x180066767  mov     rax, [rax+8]
0x18006676b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066770  test    eax, eax
0x180066772  jz      short loc_18006677D
0x180066774  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006677b  jmp     short loc_18006678B
0x18006677d  lea     rcx, qword_1800D6F70; this
0x180066784  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006678b  cmp     [rcx+8], r14b
0x18006678f  jz      short loc_1800667B2
0x180066791  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180066796  cmp     [rax+7CCh], ebx
0x18006679c  jz      short loc_1800667B2
0x18006679e  mov     r9d, ebx; int
0x1800667a1  mov     r8d, 1AAh; int
0x1800667a7  mov     rdx, rdi; char *
0x1800667aa  mov     rcx, rax; this
0x1800667ad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800667b2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800667b9  jb      loc_180066D3F
0x1800667bf  mov     edx, 1Dh
0x1800667c4  jmp     loc_180066D21
0x1800667c9  mov     rcx, [rsp+150h+ppv]
0x1800667ce  lea     r8, [rsp+150h+var_F0]
0x1800667d3  lea     rdx, qword_1800C0F28
0x1800667da  mov     rax, [rcx]
0x1800667dd  mov     rax, [rax+30h]
0x1800667e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800667e6  mov     ebx, eax
0x1800667e8  test    eax, eax
0x1800667ea  jns     loc_18006687B
0x1800667f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800667f7  test    rcx, rcx
0x1800667fa  jnz     short loc_18006683D
0x1800667fc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180066802  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180066809  mov     rcx, rax
0x18006680c  test    rax, rax
0x18006680f  jz      short loc_18006682F
0x180066811  mov     rax, [rax]
0x180066814  mov     edx, 7F0h
0x180066819  mov     rax, [rax+8]
0x18006681d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066822  test    eax, eax
0x180066824  jz      short loc_18006682F
0x180066826  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006682d  jmp     short loc_18006683D
0x18006682f  lea     rcx, qword_1800D6F70; this
0x180066836  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006683d  cmp     [rcx+8], r14b
0x180066841  jz      short loc_180066864
0x180066843  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180066848  cmp     [rax+7CCh], ebx
0x18006684e  jz      short loc_180066864
0x180066850  mov     r9d, ebx; int
0x180066853  mov     r8d, 1ADh; int
0x180066859  mov     rdx, rdi; char *
0x18006685c  mov     rcx, rax; this
0x18006685f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180066864  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006686b  jb      loc_180066D3F
0x180066871  mov     edx, 1Eh
0x180066876  jmp     loc_180066D21
0x18006687b  cmp     dword ptr [rsi+1Ch], 5
0x18006687f  jnz     loc_180066937
0x180066885  mov     rcx, [rsp+150h+ppv]
0x18006688a  lea     r8, [rsp+150h+var_F0]
0x18006688f  lea     rdx, qword_1800C0F40
0x180066896  mov     rax, [rcx]
0x180066899  mov     rax, [rax+30h]
0x18006689d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800668a2  mov     ebx, eax
0x1800668a4  test    eax, eax
0x1800668a6  jns     loc_180066937
0x1800668ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800668b3  test    rcx, rcx
0x1800668b6  jnz     short loc_1800668F9
0x1800668b8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800668be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800668c5  mov     rcx, rax
0x1800668c8  test    rax, rax
0x1800668cb  jz      short loc_1800668EB
0x1800668cd  mov     rax, [rax]
0x1800668d0  mov     edx, 7F0h
0x1800668d5  mov     rax, [rax+8]
0x1800668d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800668de  test    eax, eax
0x1800668e0  jz      short loc_1800668EB
0x1800668e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800668e9  jmp     short loc_1800668F9
0x1800668eb  lea     rcx, qword_1800D6F70; this
0x1800668f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800668f9  cmp     [rcx+8], r14b
0x1800668fd  jz      short loc_180066920
0x1800668ff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180066904  cmp     [rax+7CCh], ebx
0x18006690a  jz      short loc_180066920
0x18006690c  mov     r9d, ebx; int
0x18006690f  mov     r8d, 1B2h; int
0x180066915  mov     rdx, rdi; char *
0x180066918  mov     rcx, rax; this
0x18006691b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180066920  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066927  jb      loc_180066D3F
0x18006692d  mov     edx, 1Fh
0x180066932  jmp     loc_180066D21
0x180066937  mov     rbx, [rsi+190h]
0x18006693e  lea     rcx, [rsp+150h+pvar]; pvar
0x180066943  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180066948  mov     qword ptr [rbp+50h+pvar+8], rbx
0x18006694c  mov     eax, 0Dh
0x180066951  mov     word ptr [rsp+150h+pvar], ax
0x180066956  test    rbx, rbx
0x180066959  jz      short loc_18006696A
0x18006695b  mov     rax, [rbx]
0x18006695e  mov     rcx, rbx
0x180066961  mov     rax, [rax+8]
0x180066965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006696a  mov     rcx, [rsp+150h+ppv]
0x18006696f  lea     r8, [rsp+150h+pvar]
0x180066974  lea     rdx, MFPKEY_TELEMETRY_SESSION
0x18006697b  mov     rax, [rcx]
0x18006697e  mov     rax, [rax+30h]
0x180066982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066987  mov     ebx, eax
0x180066989  test    eax, eax
0x18006698b  jns     loc_180066A1C
0x180066991  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180066998  test    rcx, rcx
0x18006699b  jnz     short loc_1800669DE
0x18006699d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800669a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800669aa  mov     rcx, rax
0x1800669ad  test    rax, rax
0x1800669b0  jz      short loc_1800669D0
0x1800669b2  mov     rax, [rax]
0x1800669b5  mov     edx, 7F0h
0x1800669ba  mov     rax, [rax+8]
0x1800669be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800669c3  test    eax, eax
0x1800669c5  jz      short loc_1800669D0
0x1800669c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800669ce  jmp     short loc_1800669DE
0x1800669d0  lea     rcx, qword_1800D6F70; this
0x1800669d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800669de  cmp     [rcx+8], r14b
0x1800669e2  jz      short loc_180066A05
0x1800669e4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800669e9  cmp     [rax+7CCh], ebx
0x1800669ef  jz      short loc_180066A05
0x1800669f1  mov     r9d, ebx; int
0x1800669f4  mov     r8d, 1B7h; int
0x1800669fa  mov     rdx, rdi; char *
0x1800669fd  mov     rcx, rax; this
0x180066a00  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180066a05  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066a0c  jb      loc_180066D3F
0x180066a12  mov     edx, 20h ; ' '
0x180066a17  jmp     loc_180066D21
0x180066a1c  cmp     dword ptr [rsi+1Ch], 0Bh
0x180066a20  mov     rdi, r14
0x180066a23  jnb     short loc_180066A2E
  ... truncated ...
```
