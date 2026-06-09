# CAVIStreamSink::CreateInstance(CAVIMediaSink *,ulong,IMFMediaType *,CAVIStreamSink * *)

- ea: `0x1800b5f84`
- end: `0x1800b68a4`
- name: `?CreateInstance@CAVIStreamSink@@SAJPEAVCAVIMediaSink@@KPEAUIMFMediaType@@PEAPEAV1@@Z`
- size: `2336`
- prototype: `__int64 __fastcall(struct CAVIMediaSink *, unsigned int, struct IMFMediaType *, struct CAVIStreamSink **)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800e7160`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x1800734a8`
- `0x180073b14`
- `0x1800b5f84`
- `0x1801095a8`
- `0x1801099f0`
- `0x180124268`
- `0x1801282dc`
- `0x18012df98`
- `0x18012ec80`
- `0x180163048`
- `0x1801723d4`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5ffd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b60bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b618a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b624d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6318`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b63e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6494`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6540`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b65f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b66a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6748`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b67dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5ffd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b60bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b618a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b624d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6318`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b63e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6494`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6540`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b65f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b66a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6748`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b67dc`

## string_xrefs

- `0x1800b5fd5`: `CAVIStreamSink::CreateInstance`
- `0x1800b6054`: `CAVIStreamSink::CreateInstance`
- `0x1800b6116`: `CAVIStreamSink::CreateInstance`
- `0x1800b61e1`: `CAVIStreamSink::CreateInstance`
- `0x1800b62a4`: `CAVIStreamSink::CreateInstance`
- `0x1800b636f`: `CAVIStreamSink::CreateInstance`
- `0x1800b6442`: `CAVIStreamSink::CreateInstance`
- `0x1800b64eb`: `CAVIStreamSink::CreateInstance`
- `0x1800b6597`: `CAVIStreamSink::CreateInstance`
- `0x1800b6648`: `CAVIStreamSink::CreateInstance`
- `0x1800b66fe`: `CAVIStreamSink::CreateInstance`
- `0x1800b679f`: `CAVIStreamSink::CreateInstance`
- `0x1800b6833`: `CAVIStreamSink::CreateInstance`

## pseudocode

```c
__int64 __fastcall CAVIStreamSink::CreateInstance(
        struct CAVIMediaSink *a1,
        unsigned int a2,
        struct IMFMediaType *a3,
        struct CAVIStreamSink **a4)
{
  int ChunkID; // ebx
  __int64 v9; // rdx
  wchar_t *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  CAVIStreamSink *v30; // rax
  __int64 v31; // rdx
  CAVIStreamSink *v32; // rax
  CAVIStreamSink *v33; // rsi
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  char *v37; // r12
  __int64 v38; // rdx
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 v42; // rdx
  char *v43; // r9
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 v51; // rdx
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  wchar_t *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  wchar_t *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  _BYTE v62[4]; // [rsp+30h] [rbp-30h] BYREF
  int v63; // [rsp+34h] [rbp-2Ch] BYREF
  CAVIStreamSink *v64; // [rsp+38h] [rbp-28h] BYREF
  struct IMFMediaType *v65; // [rsp+40h] [rbp-20h] BYREF
  __int128 Buf1; // [rsp+48h] [rbp-18h] BYREF

  v65 = a3;
  if ( !a1 || !a3 || (ChunkID = 0, !a4) )
    ChunkID = -2147467261;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v62, "CAVIStreamSink::CreateInstance", 31);
  v64 = 0;
  if ( ChunkID < 0 )
  {
    v10 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != ChunkID )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIStreamSink::CreateInstance", 33, ChunkID);
    }
    if ( g_wppLevels )
    {
      v13 = 11;
LABEL_143:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids, 0, ChunkID);
      goto LABEL_144;
    }
    goto LABEL_144;
  }
  if ( a2 )
  {
    if ( a2 != 1 )
    {
      v58 = (wchar_t *)CallStackTracing::s_wpInstance;
      ChunkID = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
        CallStackTracing::s_wpInstance = v59;
        if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
        {
          v58 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v58 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v58 + 8) )
      {
        v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
        if ( *((_DWORD *)v60 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v60, "CAVIStreamSink::CreateInstance", 55, -2147024809);
      }
      if ( g_wppLevels )
      {
        v13 = 16;
        goto LABEL_143;
      }
      goto LABEL_144;
    }
    Buf1 = 0;
    v63 = ((__int64 (__fastcall *)(struct IMFMediaType *, __int128 *))a3->lpVtbl->GetMajorType)(a3, &Buf1);
    ChunkID = v63;
    if ( v63 < 0 )
    {
      v23 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)v25 + 499) != ChunkID )
          CallStackContext::TraceFailure(v25, "CAVIStreamSink::CreateInstance", 47, ChunkID);
      }
      if ( g_wppLevels )
      {
        v13 = 14;
        goto LABEL_143;
      }
      goto LABEL_144;
    }
    if ( memcmp_0(&Buf1, &MFMediaType_Audio, 0x10u) )
    {
      v63 = MF::OriginateError<17>(3222091444LL, L"MF_MT_MAJOR_TYPE");
      ChunkID = v63;
      if ( v63 < 0 )
      {
        v27 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
          CallStackTracing::s_wpInstance = v28;
          if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
          {
            v27 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v27 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v27 + 8) )
        {
          v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
          if ( *((_DWORD *)v29 + 499) != ChunkID )
            CallStackContext::TraceFailure(v29, "CAVIStreamSink::CreateInstance", 50, ChunkID);
        }
        if ( g_wppLevels )
        {
          v13 = 15;
          goto LABEL_143;
        }
        goto LABEL_144;
      }
    }
    goto LABEL_64;
  }
  Buf1 = 0;
  v63 = ((__int64 (__fastcall *)(struct IMFMediaType *, __int128 *))a3->lpVtbl->GetMajorType)(a3, &Buf1);
  ChunkID = v63;
  if ( v63 >= 0 )
  {
    if ( memcmp_0(&Buf1, &MFMediaType_Video, 0x10u) )
    {
      v63 = MF::OriginateError<17>(3222091444LL, L"MF_MT_MAJOR_TYPE");
      ChunkID = v63;
      if ( v63 < 0 )
      {
        v19 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
          CallStackTracing::s_wpInstance = v20;
          if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
          {
            v19 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v19 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v19 + 8) )
        {
          v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
          if ( *((_DWORD *)v21 + 499) != ChunkID )
            CallStackContext::TraceFailure(v21, "CAVIStreamSink::CreateInstance", 41, ChunkID);
        }
        if ( g_wppLevels )
        {
          v13 = 13;
          goto LABEL_143;
        }
        goto LABEL_144;
      }
    }
LABEL_64:
    v30 = (CAVIStreamSink *)operator new(0x268u);
    if ( v30 && (v32 = CAVIStreamSink::CAVIStreamSink(v30, a1, a2, &v63), v64 = v32, (v33 = v32) != 0) )
    {
      ChunkID = v63;
      if ( v63 >= 0 )
      {
        v37 = (char *)v32 + 32;
        ChunkID = CMFMediaTypeHandlerBase::Initialize((CAVIStreamSink *)((char *)v32 + 32), v31, &v65);
        if ( ChunkID >= 0 )
        {
          ChunkID = (*(__int64 (__fastcall **)(char *, struct IMFMediaType *))(*(_QWORD *)v37 + 48LL))(v37, a3);
          if ( ChunkID >= 0 )
          {
            ChunkID = AVIHelpers::GetChunkID(
                        (AVIHelpers *)a2,
                        (unsigned int)a3,
                        (struct IMFMediaType *)((char *)v33 + 508),
                        v43);
            if ( ChunkID >= 0 )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)v33 + 384);
              ChunkID = CAVIStreamIndex::CreateInstance(
                          a2,
                          (const char *const)v33 + 508,
                          (struct CAVIStreamIndex **)v33 + 48);
              if ( ChunkID >= 0 )
              {
                v64 = 0;
                *a4 = v33;
              }
              else
              {
                v52 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51);
                  CallStackTracing::s_wpInstance = v53;
                  if ( v53
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
                  {
                    v52 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v52 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v52 + 8) )
                {
                  v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
                  if ( *((_DWORD *)v54 + 499) != ChunkID )
                    CallStackContext::TraceFailure(v54, "CAVIStreamSink::CreateInstance", 64, ChunkID);
                }
                if ( g_wppLevels )
                {
                  v13 = 22;
                  goto LABEL_143;
                }
              }
            }
            else
            {
              v48 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47);
                CallStackTracing::s_wpInstance = v49;
                if ( v49
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
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
                if ( *((_DWORD *)v50 + 499) != ChunkID )
                  CallStackContext::TraceFailure(v50, "CAVIStreamSink::CreateInstance", 63, ChunkID);
              }
              if ( g_wppLevels )
              {
                v13 = 21;
                goto LABEL_143;
              }
            }
          }
          else
          {
            v44 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42);
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
              if ( *((_DWORD *)v46 + 499) != ChunkID )
                CallStackContext::TraceFailure(v46, "CAVIStreamSink::CreateInstance", 62, ChunkID);
            }
            if ( g_wppLevels )
            {
              v13 = 20;
              goto LABEL_143;
            }
          }
        }
        else
        {
          v39 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38);
            CallStackTracing::s_wpInstance = v40;
            if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
            {
              v39 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v39 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v39 + 8) )
          {
            v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
            if ( *((_DWORD *)v41 + 499) != ChunkID )
              CallStackContext::TraceFailure(v41, "CAVIStreamSink::CreateInstance", 61, ChunkID);
          }
          if ( g_wppLevels )
          {
            v13 = 19;
            goto LABEL_143;
          }
        }
      }
      else
      {
        v34 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( ChunkID < 0 && *((_DWORD *)v36 + 499) != ChunkID )
            CallStackContext::TraceFailure(v36, "CAVIStreamSink::CreateInstance", 60, ChunkID);
        }
        if ( g_wppLevels )
        {
          v13 = 18;
          goto LABEL_143;
        }
      }
    }
    else
    {
      v55 = (wchar_t *)CallStackTracing::s_wpInstance;
      ChunkID = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
        CallStackTracing::s_wpInstance = v56;
        if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
        {
          v55 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v55 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v55 + 8) )
      {
        v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
        if ( *((_DWORD *)v57 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v57, "CAVIStreamSink::CreateInstance", 59, -2147024882);
      }
      if ( g_wppLevels )
      {
        v13 = 17;
        goto LABEL_143;
      }
    }
    goto LABEL_144;
  }
  v15 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
    CallStackTracing::s_wpInstance = v16;
    if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
    {
      v15 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v15 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v15 + 8) )
  {
    v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
    if ( *((_DWORD *)v17 + 499) != ChunkID )
      CallStackContext::TraceFailure(v17, "CAVIStreamSink::CreateInstance", 38, ChunkID);
  }
  if ( g_wppLevels )
  {
    v13 = 12;
    goto LABEL_143;
  }
LABEL_144:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v64);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v62);
  return (unsigned int)ChunkID;
}

```

## disassembly

```asm
0x1800b5f84  push    rbp
0x1800b5f86  push    rbx
0x1800b5f87  push    rsi
0x1800b5f88  push    r12
0x1800b5f8a  push    r13
0x1800b5f8c  push    r14
0x1800b5f8e  push    r15
0x1800b5f90  mov     rbp, rsp
0x1800b5f93  sub     rsp, 60h
0x1800b5f97  mov     rax, cs:__security_cookie
0x1800b5f9e  xor     rax, rsp
0x1800b5fa1  mov     [rbp+var_8], rax
0x1800b5fa5  xor     r12d, r12d
0x1800b5fa8  mov     [rbp+var_20], r8
0x1800b5fac  mov     r13, r9
0x1800b5faf  mov     r14, r8
0x1800b5fb2  mov     r15d, edx
0x1800b5fb5  mov     rsi, rcx
0x1800b5fb8  test    rcx, rcx
0x1800b5fbb  jz      short loc_1800B5FCA
0x1800b5fbd  test    r8, r8
0x1800b5fc0  jz      short loc_1800B5FCA
0x1800b5fc2  mov     ebx, r12d
0x1800b5fc5  test    r9, r9
0x1800b5fc8  jnz     short loc_1800B5FCF
0x1800b5fca  mov     ebx, 80004003h
0x1800b5fcf  mov     r8d, 1Fh; int
0x1800b5fd5  lea     rdx, aCavistreamsink_7; "CAVIStreamSink::CreateInstance"
0x1800b5fdc  lea     rcx, [rbp+var_30]; this
0x1800b5fe0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b5fe5  mov     [rbp+var_28], r12
0x1800b5fe9  test    ebx, ebx
0x1800b5feb  jns     loc_1800B6080
0x1800b5ff1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5ff8  test    rcx, rcx
0x1800b5ffb  jnz     short loc_1800B603E
0x1800b5ffd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b6003  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b600a  mov     rcx, rax
0x1800b600d  test    rax, rax
0x1800b6010  jz      short loc_1800B6030
0x1800b6012  mov     rax, [rax]
0x1800b6015  mov     edx, 7F0h
0x1800b601a  mov     rax, [rax+8]
0x1800b601e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6023  test    eax, eax
0x1800b6025  jz      short loc_1800B6030
0x1800b6027  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b602e  jmp     short loc_1800B603E
0x1800b6030  lea     rcx, qword_1801B07E0; this
0x1800b6037  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b603e  cmp     [rcx+8], r12b
0x1800b6042  jz      short loc_1800B6069
0x1800b6044  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b6049  cmp     [rax+7CCh], ebx
0x1800b604f  jz      short loc_1800B6069
0x1800b6051  mov     r9d, ebx; int
0x1800b6054  lea     rdx, aCavistreamsink_7; "CAVIStreamSink::CreateInstance"
0x1800b605b  mov     r8d, 21h ; '!'; int
0x1800b6061  mov     rcx, rax; this
0x1800b6064  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b6069  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b6070  jb      loc_1800B6874
0x1800b6076  mov     edx, 0Bh
0x1800b607b  jmp     loc_1800B6856
0x1800b6080  test    r15d, r15d
0x1800b6083  jnz     loc_1800B620D
0x1800b6089  xorps   xmm0, xmm0
0x1800b608c  lea     rdx, [rbp+Buf1]
0x1800b6090  movups  [rbp+Buf1], xmm0
0x1800b6094  mov     rax, [r14]
0x1800b6097  mov     rcx, r14
0x1800b609a  mov     rax, [rax+108h]
0x1800b60a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b60a6  mov     [rbp+var_2C], eax
0x1800b60a9  mov     ebx, eax
0x1800b60ab  test    eax, eax
0x1800b60ad  jns     loc_1800B6142
0x1800b60b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b60ba  test    rcx, rcx
0x1800b60bd  jnz     short loc_1800B6100
0x1800b60bf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b60c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b60cc  mov     rcx, rax
0x1800b60cf  test    rax, rax
0x1800b60d2  jz      short loc_1800B60F2
0x1800b60d4  mov     rax, [rax]
0x1800b60d7  mov     edx, 7F0h
0x1800b60dc  mov     rax, [rax+8]
0x1800b60e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b60e5  test    eax, eax
0x1800b60e7  jz      short loc_1800B60F2
0x1800b60e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b60f0  jmp     short loc_1800B6100
0x1800b60f2  lea     rcx, qword_1801B07E0; this
0x1800b60f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6100  cmp     [rcx+8], r12b
0x1800b6104  jz      short loc_1800B612B
0x1800b6106  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b610b  cmp     [rax+7CCh], ebx
0x1800b6111  jz      short loc_1800B612B
0x1800b6113  mov     r9d, ebx; int
0x1800b6116  lea     rdx, aCavistreamsink_7; "CAVIStreamSink::CreateInstance"
0x1800b611d  mov     r8d, 26h ; '&'; int
0x1800b6123  mov     rcx, rax; this
0x1800b6126  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b612b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b6132  jb      loc_1800B6874
0x1800b6138  mov     edx, 0Ch
0x1800b613d  jmp     loc_1800B6856
0x1800b6142  mov     r8d, 10h; Size
0x1800b6148  lea     rdx, MFMediaType_Video; Buf2
0x1800b614f  lea     rcx, [rbp+Buf1]; Buf1
0x1800b6153  call    memcmp_0
0x1800b6158  test    eax, eax
0x1800b615a  jz      loc_1800B639B
0x1800b6160  lea     rdx, aMfMtMajorType; "MF_MT_MAJOR_TYPE"
0x1800b6167  mov     ecx, 0C00D36B4h
0x1800b616c  call    ??$OriginateError@$0BB@@MF@@YAJJAEAY0BB@$$CBG@Z; MF::OriginateError<17>(long,ushort const (&)[17])
0x1800b6171  mov     [rbp+var_2C], eax
0x1800b6174  mov     ebx, eax
0x1800b6176  test    eax, eax
0x1800b6178  jns     loc_1800B639B
0x1800b617e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6185  test    rcx, rcx
0x1800b6188  jnz     short loc_1800B61CB
0x1800b618a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b6190  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6197  mov     rcx, rax
0x1800b619a  test    rax, rax
0x1800b619d  jz      short loc_1800B61BD
0x1800b619f  mov     rax, [rax]
0x1800b61a2  mov     edx, 7F0h
0x1800b61a7  mov     rax, [rax+8]
0x1800b61ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b61b0  test    eax, eax
0x1800b61b2  jz      short loc_1800B61BD
0x1800b61b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b61bb  jmp     short loc_1800B61CB
0x1800b61bd  lea     rcx, qword_1801B07E0; this
0x1800b61c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b61cb  cmp     [rcx+8], r12b
0x1800b61cf  jz      short loc_1800B61F6
0x1800b61d1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b61d6  cmp     [rax+7CCh], ebx
0x1800b61dc  jz      short loc_1800B61F6
0x1800b61de  mov     r9d, ebx; int
0x1800b61e1  lea     rdx, aCavistreamsink_7; "CAVIStreamSink::CreateInstance"
0x1800b61e8  mov     r8d, 29h ; ')'; int
0x1800b61ee  mov     rcx, rax; this
0x1800b61f1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b61f6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b61fd  jb      loc_1800B6874
0x1800b6203  mov     edx, 0Dh
0x1800b6208  jmp     loc_1800B6856
0x1800b620d  cmp     r15d, 1
0x1800b6211  jnz     loc_1800B67CB
0x1800b6217  xorps   xmm0, xmm0
0x1800b621a  lea     rdx, [rbp+Buf1]
0x1800b621e  movups  [rbp+Buf1], xmm0
0x1800b6222  mov     rax, [r14]
0x1800b6225  mov     rcx, r14
0x1800b6228  mov     rax, [rax+108h]
0x1800b622f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6234  mov     [rbp+var_2C], eax
0x1800b6237  mov     ebx, eax
0x1800b6239  test    eax, eax
0x1800b623b  jns     loc_1800B62D0
0x1800b6241  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6248  test    rcx, rcx
0x1800b624b  jnz     short loc_1800B628E
0x1800b624d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b6253  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b625a  mov     rcx, rax
0x1800b625d  test    rax, rax
0x1800b6260  jz      short loc_1800B6280
0x1800b6262  mov     rax, [rax]
0x1800b6265  mov     edx, 7F0h
0x1800b626a  mov     rax, [rax+8]
0x1800b626e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6273  test    eax, eax
0x1800b6275  jz      short loc_1800B6280
0x1800b6277  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b627e  jmp     short loc_1800B628E
0x1800b6280  lea     rcx, qword_1801B07E0; this
0x1800b6287  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b628e  cmp     [rcx+8], r12b
0x1800b6292  jz      short loc_1800B62B9
0x1800b6294  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b6299  cmp     [rax+7CCh], ebx
0x1800b629f  jz      short loc_1800B62B9
0x1800b62a1  mov     r9d, ebx; int
0x1800b62a4  lea     rdx, aCavistreamsink_7; "CAVIStreamSink::CreateInstance"
0x1800b62ab  mov     r8d, 2Fh ; '/'; int
0x1800b62b1  mov     rcx, rax; this
0x1800b62b4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b62b9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b62c0  jb      loc_1800B6874
0x1800b62c6  mov     edx, 0Eh
0x1800b62cb  jmp     loc_1800B6856
0x1800b62d0  mov     r8d, 10h; Size
0x1800b62d6  lea     rdx, MFMediaType_Audio; Buf2
0x1800b62dd  lea     rcx, [rbp+Buf1]; Buf1
0x1800b62e1  call    memcmp_0
0x1800b62e6  test    eax, eax
0x1800b62e8  jz      loc_1800B639B
0x1800b62ee  lea     rdx, aMfMtMajorType; "MF_MT_MAJOR_TYPE"
0x1800b62f5  mov     ecx, 0C00D36B4h
0x1800b62fa  call    ??$OriginateError@$0BB@@MF@@YAJJAEAY0BB@$$CBG@Z; MF::OriginateError<17>(long,ushort const (&)[17])
0x1800b62ff  mov     [rbp+var_2C], eax
0x1800b6302  mov     ebx, eax
0x1800b6304  test    eax, eax
0x1800b6306  jns     loc_1800B639B
0x1800b630c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6313  test    rcx, rcx
0x1800b6316  jnz     short loc_1800B6359
0x1800b6318  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b631e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6325  mov     rcx, rax
0x1800b6328  test    rax, rax
0x1800b632b  jz      short loc_1800B634B
0x1800b632d  mov     rax, [rax]
0x1800b6330  mov     edx, 7F0h
0x1800b6335  mov     rax, [rax+8]
0x1800b6339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b633e  test    eax, eax
0x1800b6340  jz      short loc_1800B634B
0x1800b6342  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6349  jmp     short loc_1800B6359
0x1800b634b  lea     rcx, qword_1801B07E0; this
0x1800b6352  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6359  cmp     [rcx+8], r12b
0x1800b635d  jz      short loc_1800B6384
0x1800b635f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b6364  cmp     [rax+7CCh], ebx
0x1800b636a  jz      short loc_1800B6384
0x1800b636c  mov     r9d, ebx; int
0x1800b636f  lea     rdx, aCavistreamsink_7; "CAVIStreamSink::CreateInstance"
0x1800b6376  mov     r8d, 32h ; '2'; int
0x1800b637c  mov     rcx, rax; this
0x1800b637f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b6384  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b638b  jb      loc_1800B6874
0x1800b6391  mov     edx, 0Fh
0x1800b6396  jmp     loc_1800B6856
0x1800b639b  mov     ecx, 268h; Size
0x1800b63a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b63a5  test    rax, rax
0x1800b63a8  jz      loc_1800B6737
0x1800b63ae  lea     r9, [rbp+var_2C]; int *
0x1800b63b2  mov     r8d, r15d; unsigned int
0x1800b63b5  mov     rdx, rsi; struct CAVIMediaSink *
0x1800b63b8  mov     rcx, rax; this
0x1800b63bb  call    ??0CAVIStreamSink@@IEAA@PEAVCAVIMediaSink@@KPEAJ@Z; CAVIStreamSink::CAVIStreamSink(CAVIMediaSink *,ulong,long *)
0x1800b63c0  mov     [rbp+var_28], rax
0x1800b63c4  mov     rsi, rax
0x1800b63c7  test    rax, rax
0x1800b63ca  jz      loc_1800B6737
0x1800b63d0  mov     ebx, [rbp+var_2C]
0x1800b63d3  test    ebx, ebx
0x1800b63d5  jns     loc_1800B646E
0x1800b63db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b63e2  test    rcx, rcx
0x1800b63e5  jnz     short loc_1800B6428
0x1800b63e7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b63ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b63f4  mov     rcx, rax
0x1800b63f7  test    rax, rax
0x1800b63fa  jz      short loc_1800B641A
0x1800b63fc  mov     rax, [rax]
0x1800b63ff  mov     edx, 7F0h
0x1800b6404  mov     rax, [rax+8]
0x1800b6408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b640d  test    eax, eax
0x1800b640f  jz      short loc_1800B641A
0x1800b6411  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6418  jmp     short loc_1800B6428
0x1800b641a  lea     rcx, qword_1801B07E0; this
0x1800b6421  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6428  cmp     [rcx+8], r12b
0x1800b642c  jz      short loc_1800B6457
0x1800b642e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b6433  test    ebx, ebx
0x1800b6435  jns     short loc_1800B6457
0x1800b6437  cmp     [rax+7CCh], ebx
0x1800b643d  jz      short loc_1800B6457
0x1800b643f  mov     r9d, ebx; int
0x1800b6442  lea     rdx, aCavistreamsink_7; "CAVIStreamSink::CreateInstance"
0x1800b6449  mov     r8d, 3Ch ; '<'; int
0x1800b644f  mov     rcx, rax; this
0x1800b6452  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b6457  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b645e  jb      loc_1800B6874
0x1800b6464  mov     edx, 12h
0x1800b6469  jmp     loc_1800B6856
0x1800b646e  lea     r12, [rax+20h]
0x1800b6472  mov     rcx, r12; this
0x1800b6475  lea     r8, [rbp+var_20]; struct IMFMediaType **
0x1800b6479  call    ?Initialize@CMFMediaTypeHandlerBase@@QEAAJKPEAPEAUIMFMediaType@@@Z; CMFMediaTypeHandlerBase::Initialize(ulong,IMFMediaType * *)
0x1800b647e  mov     ebx, eax
  ... truncated ...
```
