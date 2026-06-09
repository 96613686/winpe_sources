# CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver(IMFByteStream *,IMFSourceResolver *,IMFSourceReader * *)

- ea: `0x180069134`
- end: `0x180069a04`
- name: `?CreateAsyncSourceReaderUsingSourceResolver@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAUIMFSourceResolver@@PEAPEAUIMFSourceReader@@@Z`
- size: `2256`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFByteStream *, struct IMFSourceResolver *, struct IMFSourceReader **)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18006a2ac`
- `0x18006a524`

## callees

- `0x180002400`
- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180068ac4`
- `0x180069134`
- `0x180069a0c`
- `0x180069df0`
- `0x18006a780`
- `0x18006c764`
- `0x1800744d8`
- `0x1800746f8`
- `0x1800b4010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18006929e`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18006929e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800692c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006938a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069442`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069504`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800695ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800696af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069769`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069862`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069911`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800692c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006938a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069442`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069504`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800695ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800696af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069769`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069862`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069911`

## string_xrefs

- `0x180069169`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x18006927e`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x18006970c`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x1800697c6`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x1800698bf`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`
- `0x18006996e`: `CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver`

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
      AsyncSourceReader = (*(__int64 (__fastcall **)(void *, void *, __int128 *))(*(_QWORD *)ppv + 48LL))(
                            ppv,
                            &unk_1800C5F20,
                            &v75);
      if ( AsyncSourceReader >= 0 )
      {
        if ( *((_DWORD *)this + 7) == 5
          && (AsyncSourceReader = (*(__int64 (__fastcall **)(void *, void *, __int128 *))(*(_QWORD *)ppv + 48LL))(
                                    ppv,
                                    &unk_1800C5F38,
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
              v34 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          AsyncSourceReader = (*(__int64 (__fastcall **)(void *, void *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                ppv,
                                &MFPKEY_TELEMETRY_SESSION,
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
                        v67 = &qword_1800DBF70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                      v61 = &qword_1800DBF70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                    v55 = &qword_1800DBF70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                  v49 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                v41 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v28 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v22 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v15 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180069134  push    rbp
0x180069136  push    rbx
0x180069137  push    rsi
0x180069138  push    rdi
0x180069139  push    r12
0x18006913b  push    r13
0x18006913d  push    r14
0x18006913f  push    r15
0x180069141  lea     rbp, [rsp-18h]
0x180069146  sub     rsp, 118h
0x18006914d  mov     rax, cs:__security_cookie
0x180069154  xor     rax, rsp
0x180069157  mov     [rbp+50h+var_50], rax
0x18006915b  xor     r14d, r14d
0x18006915e  lea     rax, aDummyAsf; "dummy.asf"
0x180069165  mov     [rbp+50h+var_B8], rax
0x180069169  lea     rdi, aCmfvideothumbn_1; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x180069170  xorps   xmm0, xmm0
0x180069173  mov     [rsp+150h+ppv], r14
0x180069178  lea     rax, aDummyMp3; "dummy.mp3"
0x18006917f  mov     [rbp+50h+var_C0], r14
0x180069183  mov     [rbp+50h+var_B0], rax
0x180069187  mov     r13, r8
0x18006918a  lea     rax, aDummyMp4; "dummy.mp4"
0x180069191  mov     [rsp+150h+var_F8], r14
0x180069196  mov     [rbp+50h+var_A8], rax
0x18006919a  mov     r12, rdx
0x18006919d  lea     rax, aDummyAvi; "dummy.avi"
0x1800691a4  mov     [rsp+150h+var_100], r14
0x1800691a9  mov     [rbp+50h+var_A0], rax
0x1800691ad  mov     rsi, rcx
0x1800691b0  lea     rax, aDummyM2ts; "dummy.m2ts"
0x1800691b7  mov     r8d, 1A0h; int
0x1800691bd  mov     [rbp+50h+var_98], rax
0x1800691c1  lea     rcx, [rsp+150h+var_110]; this
0x1800691c6  lea     rax, aDummyWav; "dummy.wav"
0x1800691cd  mov     rdx, rdi; char *
0x1800691d0  mov     [rbp+50h+var_90], rax
0x1800691d4  mov     r15, r9
0x1800691d7  lea     rax, aDummyAdts; "dummy.adts"
0x1800691de  mov     [rbp+50h+var_88], rax
0x1800691e2  lea     rax, aDummyAc3; "dummy.ac3"
0x1800691e9  mov     [rbp+50h+var_80], rax
0x1800691ed  lea     rax, aDummyMkv; "dummy.mkv"
0x1800691f4  mov     [rbp+50h+var_78], rax
0x1800691f8  lea     rax, aDummyFlac; "dummy.flac"
0x1800691ff  mov     [rbp+50h+var_70], rax
0x180069203  xor     eax, eax
0x180069205  mov     [rsp+150h+var_E0], rax
0x18006920a  mov     qword ptr [rbp+50h+pvar+10h], rax
0x18006920e  movups  [rsp+150h+var_F0], xmm0
0x180069213  movups  xmmword ptr [rsp+150h+pvar], xmm0
0x180069218  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006921d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180069224  cmp     [rcx+8], r14b
0x180069228  jz      short loc_180069285
0x18006922a  cmp     [rsi+190h], r14
0x180069231  jz      short loc_180069285
0x180069233  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069238  mov     rcx, [rsi+190h]
0x18006923f  mov     rdi, rax
0x180069242  mov     rdx, [rcx]
0x180069245  mov     rax, [rdx+128h]
0x18006924c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069251  mov     rcx, [rsi+190h]
0x180069258  mov     ebx, eax
0x18006925a  mov     rdx, [rcx]
0x18006925d  mov     rax, [rdx+118h]
0x180069264  lea     rdx, [rbp+50h+var_60]
0x180069268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006926d  movups  xmm0, xmmword ptr [rax]
0x180069270  mov     [rdi+7E0h], ebx
0x180069276  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18006927e  lea     rdi, aCmfvideothumbn_1; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x180069285  lea     rcx, [rsp+150h+ppv]
0x18006928a  mov     [r15], r14
0x18006928d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180069292  lea     rdx, [rsp+150h+ppv]; ppv
0x180069297  lea     rcx, IID_IPropertyStore; riid
0x18006929e  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800692a5  nop     dword ptr [rax+rax+00h]
0x1800692aa  mov     ebx, eax
0x1800692ac  test    eax, eax
0x1800692ae  jns     loc_180069345
0x1800692b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800692bb  test    rcx, rcx
0x1800692be  jnz     short loc_180069307
0x1800692c0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800692c7  nop     dword ptr [rax+rax+00h]
0x1800692cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800692d3  mov     rcx, rax
0x1800692d6  test    rax, rax
0x1800692d9  jz      short loc_1800692F9
0x1800692db  mov     rax, [rax]
0x1800692de  mov     edx, 7F0h
0x1800692e3  mov     rax, [rax+8]
0x1800692e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800692ec  test    eax, eax
0x1800692ee  jz      short loc_1800692F9
0x1800692f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800692f7  jmp     short loc_180069307
0x1800692f9  lea     rcx, qword_1800DBF70; this
0x180069300  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180069307  cmp     [rcx+8], r14b
0x18006930b  jz      short loc_18006932E
0x18006930d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069312  cmp     [rax+7CCh], ebx
0x180069318  jz      short loc_18006932E
0x18006931a  mov     r9d, ebx; int
0x18006931d  mov     r8d, 1A4h; int
0x180069323  mov     rdx, rdi; char *
0x180069326  mov     rcx, rax; this
0x180069329  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006932e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180069335  jb      loc_1800699AF
0x18006933b  mov     edx, 1Ch
0x180069340  jmp     loc_180069991
0x180069345  mov     rcx, [rsp+150h+ppv]
0x18006934a  lea     r8, [rsp+150h+var_F0]
0x18006934f  mov     eax, 0Bh
0x180069354  lea     rdx, MFPKEY_MediaSource_DisableReadAhead
0x18006935b  mov     word ptr [rsp+150h+var_F0], ax
0x180069360  or      eax, 0FFFFFFFFh
0x180069363  mov     word ptr [rsp+150h+var_F0+8], ax
0x180069368  mov     rax, [rcx]
0x18006936b  mov     rax, [rax+30h]
0x18006936f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069374  mov     ebx, eax
0x180069376  test    eax, eax
0x180069378  jns     loc_18006940F
0x18006937e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069385  test    rcx, rcx
0x180069388  jnz     short loc_1800693D1
0x18006938a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180069391  nop     dword ptr [rax+rax+00h]
0x180069396  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006939d  mov     rcx, rax
0x1800693a0  test    rax, rax
0x1800693a3  jz      short loc_1800693C3
0x1800693a5  mov     rax, [rax]
0x1800693a8  mov     edx, 7F0h
0x1800693ad  mov     rax, [rax+8]
0x1800693b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800693b6  test    eax, eax
0x1800693b8  jz      short loc_1800693C3
0x1800693ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800693c1  jmp     short loc_1800693D1
0x1800693c3  lea     rcx, qword_1800DBF70; this
0x1800693ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800693d1  cmp     [rcx+8], r14b
0x1800693d5  jz      short loc_1800693F8
0x1800693d7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800693dc  cmp     [rax+7CCh], ebx
0x1800693e2  jz      short loc_1800693F8
0x1800693e4  mov     r9d, ebx; int
0x1800693e7  mov     r8d, 1AAh; int
0x1800693ed  mov     rdx, rdi; char *
0x1800693f0  mov     rcx, rax; this
0x1800693f3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800693f8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800693ff  jb      loc_1800699AF
0x180069405  mov     edx, 1Dh
0x18006940a  jmp     loc_180069991
0x18006940f  mov     rcx, [rsp+150h+ppv]
0x180069414  lea     r8, [rsp+150h+var_F0]
0x180069419  lea     rdx, unk_1800C5F20
0x180069420  mov     rax, [rcx]
0x180069423  mov     rax, [rax+30h]
0x180069427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006942c  mov     ebx, eax
0x18006942e  test    eax, eax
0x180069430  jns     loc_1800694C7
0x180069436  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006943d  test    rcx, rcx
0x180069440  jnz     short loc_180069489
0x180069442  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180069449  nop     dword ptr [rax+rax+00h]
0x18006944e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180069455  mov     rcx, rax
0x180069458  test    rax, rax
0x18006945b  jz      short loc_18006947B
0x18006945d  mov     rax, [rax]
0x180069460  mov     edx, 7F0h
0x180069465  mov     rax, [rax+8]
0x180069469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006946e  test    eax, eax
0x180069470  jz      short loc_18006947B
0x180069472  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069479  jmp     short loc_180069489
0x18006947b  lea     rcx, qword_1800DBF70; this
0x180069482  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180069489  cmp     [rcx+8], r14b
0x18006948d  jz      short loc_1800694B0
0x18006948f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069494  cmp     [rax+7CCh], ebx
0x18006949a  jz      short loc_1800694B0
0x18006949c  mov     r9d, ebx; int
0x18006949f  mov     r8d, 1ADh; int
0x1800694a5  mov     rdx, rdi; char *
0x1800694a8  mov     rcx, rax; this
0x1800694ab  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800694b0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800694b7  jb      loc_1800699AF
0x1800694bd  mov     edx, 1Eh
0x1800694c2  jmp     loc_180069991
0x1800694c7  cmp     dword ptr [rsi+1Ch], 5
0x1800694cb  jnz     loc_180069589
0x1800694d1  mov     rcx, [rsp+150h+ppv]
0x1800694d6  lea     r8, [rsp+150h+var_F0]
0x1800694db  lea     rdx, unk_1800C5F38
0x1800694e2  mov     rax, [rcx]
0x1800694e5  mov     rax, [rax+30h]
0x1800694e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800694ee  mov     ebx, eax
0x1800694f0  test    eax, eax
0x1800694f2  jns     loc_180069589
0x1800694f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800694ff  test    rcx, rcx
0x180069502  jnz     short loc_18006954B
0x180069504  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006950b  nop     dword ptr [rax+rax+00h]
0x180069510  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180069517  mov     rcx, rax
0x18006951a  test    rax, rax
0x18006951d  jz      short loc_18006953D
0x18006951f  mov     rax, [rax]
0x180069522  mov     edx, 7F0h
0x180069527  mov     rax, [rax+8]
0x18006952b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069530  test    eax, eax
0x180069532  jz      short loc_18006953D
0x180069534  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006953b  jmp     short loc_18006954B
0x18006953d  lea     rcx, qword_1800DBF70; this
0x180069544  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006954b  cmp     [rcx+8], r14b
0x18006954f  jz      short loc_180069572
0x180069551  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069556  cmp     [rax+7CCh], ebx
0x18006955c  jz      short loc_180069572
0x18006955e  mov     r9d, ebx; int
0x180069561  mov     r8d, 1B2h; int
0x180069567  mov     rdx, rdi; char *
0x18006956a  mov     rcx, rax; this
0x18006956d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180069572  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180069579  jb      loc_1800699AF
0x18006957f  mov     edx, 1Fh
0x180069584  jmp     loc_180069991
0x180069589  mov     rbx, [rsi+190h]
0x180069590  lea     rcx, [rsp+150h+pvar]; pvar
0x180069595  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18006959a  mov     qword ptr [rbp+50h+pvar+8], rbx
0x18006959e  mov     eax, 0Dh
0x1800695a3  mov     word ptr [rsp+150h+pvar], ax
0x1800695a8  test    rbx, rbx
0x1800695ab  jz      short loc_1800695BC
0x1800695ad  mov     rax, [rbx]
0x1800695b0  mov     rcx, rbx
0x1800695b3  mov     rax, [rax+8]
0x1800695b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800695bc  mov     rcx, [rsp+150h+ppv]
0x1800695c1  lea     r8, [rsp+150h+pvar]
0x1800695c6  lea     rdx, MFPKEY_TELEMETRY_SESSION
0x1800695cd  mov     rax, [rcx]
0x1800695d0  mov     rax, [rax+30h]
0x1800695d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800695d9  mov     ebx, eax
0x1800695db  test    eax, eax
0x1800695dd  jns     loc_180069674
0x1800695e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800695ea  test    rcx, rcx
0x1800695ed  jnz     short loc_180069636
0x1800695ef  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800695f6  nop     dword ptr [rax+rax+00h]
0x1800695fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180069602  mov     rcx, rax
0x180069605  test    rax, rax
0x180069608  jz      short loc_180069628
0x18006960a  mov     rax, [rax]
0x18006960d  mov     edx, 7F0h
0x180069612  mov     rax, [rax+8]
0x180069616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006961b  test    eax, eax
0x18006961d  jz      short loc_180069628
0x18006961f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069626  jmp     short loc_180069636
0x180069628  lea     rcx, qword_1800DBF70; this
0x18006962f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180069636  cmp     [rcx+8], r14b
0x18006963a  jz      short loc_18006965D
0x18006963c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069641  cmp     [rax+7CCh], ebx
0x180069647  jz      short loc_18006965D
0x180069649  mov     r9d, ebx; int
0x18006964c  mov     r8d, 1B7h; int
0x180069652  mov     rdx, rdi; char *
0x180069655  mov     rcx, rax; this
0x180069658  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006965d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
  ... truncated ...
```
