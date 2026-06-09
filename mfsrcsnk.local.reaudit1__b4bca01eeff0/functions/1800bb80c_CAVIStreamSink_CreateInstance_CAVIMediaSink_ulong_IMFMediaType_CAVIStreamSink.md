# CAVIStreamSink::CreateInstance(CAVIMediaSink *,ulong,IMFMediaType *,CAVIStreamSink * *)

- ea: `0x1800bb80c`
- end: `0x1800bc175`
- name: `?CreateInstance@CAVIStreamSink@@SAJPEAVCAVIMediaSink@@KPEAUIMFMediaType@@PEAPEAV1@@Z`
- size: `2409`
- prototype: `__int64 __fastcall(struct CAVIMediaSink *, unsigned int, struct IMFMediaType *, struct CAVIStreamSink **)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800edbc8`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x1800790a8`
- `0x180079680`
- `0x1800bb80c`
- `0x180110a94`
- `0x180110ed0`
- `0x18012b14c`
- `0x18012f454`
- `0x180135408`
- `0x180136158`
- `0x18016beb8`
- `0x18017b734`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bb885`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bb94d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bba1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbae7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbbb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbc8d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbd40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbdf2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbea9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbf65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc00c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc0a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bb885`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bb94d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bba1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbae7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbbb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbc8d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbd40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbdf2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbea9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbf65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc00c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc0a6`

## string_xrefs

- `0x1800bb85d`: `CAVIStreamSink::CreateInstance`
- `0x1800bb8e2`: `CAVIStreamSink::CreateInstance`
- `0x1800bb9aa`: `CAVIStreamSink::CreateInstance`
- `0x1800bba7b`: `CAVIStreamSink::CreateInstance`
- `0x1800bbb44`: `CAVIStreamSink::CreateInstance`
- `0x1800bbc15`: `CAVIStreamSink::CreateInstance`
- `0x1800bbcee`: `CAVIStreamSink::CreateInstance`
- `0x1800bbd9d`: `CAVIStreamSink::CreateInstance`
- `0x1800bbe4f`: `CAVIStreamSink::CreateInstance`
- `0x1800bbf06`: `CAVIStreamSink::CreateInstance`
- `0x1800bbfc2`: `CAVIStreamSink::CreateInstance`
- `0x1800bc069`: `CAVIStreamSink::CreateInstance`
- `0x1800bc103`: `CAVIStreamSink::CreateInstance`

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
        v10 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v58 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v23 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v27 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v19 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                    v52 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                  v48 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v44 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v39 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v34 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v55 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v15 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x1800bb80c  push    rbp
0x1800bb80e  push    rbx
0x1800bb80f  push    rsi
0x1800bb810  push    r12
0x1800bb812  push    r13
0x1800bb814  push    r14
0x1800bb816  push    r15
0x1800bb818  mov     rbp, rsp
0x1800bb81b  sub     rsp, 60h
0x1800bb81f  mov     rax, cs:__security_cookie
0x1800bb826  xor     rax, rsp
0x1800bb829  mov     [rbp+var_8], rax
0x1800bb82d  xor     r12d, r12d
0x1800bb830  mov     [rbp+var_20], r8
0x1800bb834  mov     r13, r9
0x1800bb837  mov     r14, r8
0x1800bb83a  mov     r15d, edx
0x1800bb83d  mov     rsi, rcx
0x1800bb840  test    rcx, rcx
0x1800bb843  jz      short loc_1800BB852
0x1800bb845  test    r8, r8
0x1800bb848  jz      short loc_1800BB852
0x1800bb84a  mov     ebx, r12d
0x1800bb84d  test    r9, r9
0x1800bb850  jnz     short loc_1800BB857
0x1800bb852  mov     ebx, 80004003h
0x1800bb857  mov     r8d, 1Fh; int
0x1800bb85d  lea     rdx, aCavistreamsink_7; "CAVIStreamSink::CreateInstance"
0x1800bb864  lea     rcx, [rbp+var_30]; this
0x1800bb868  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800bb86d  mov     [rbp+var_28], r12
0x1800bb871  test    ebx, ebx
0x1800bb873  jns     loc_1800BB90E
0x1800bb879  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb880  test    rcx, rcx
0x1800bb883  jnz     short loc_1800BB8CC
0x1800bb885  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bb88c  nop     dword ptr [rax+rax+00h]
0x1800bb891  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb898  mov     rcx, rax
0x1800bb89b  test    rax, rax
0x1800bb89e  jz      short loc_1800BB8BE
0x1800bb8a0  mov     rax, [rax]
0x1800bb8a3  mov     edx, 7F0h
0x1800bb8a8  mov     rax, [rax+8]
0x1800bb8ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb8b1  test    eax, eax
0x1800bb8b3  jz      short loc_1800BB8BE
0x1800bb8b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb8bc  jmp     short loc_1800BB8CC
0x1800bb8be  lea     rcx, qword_1801B97E0; this
0x1800bb8c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb8cc  cmp     [rcx+8], r12b
0x1800bb8d0  jz      short loc_1800BB8F7
0x1800bb8d2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bb8d7  cmp     [rax+7CCh], ebx
0x1800bb8dd  jz      short loc_1800BB8F7
0x1800bb8df  mov     r9d, ebx; int
0x1800bb8e2  lea     rdx, aCavistreamsink_7; "CAVIStreamSink::CreateInstance"
0x1800bb8e9  mov     r8d, 21h ; '!'; int
0x1800bb8ef  mov     rcx, rax; this
0x1800bb8f2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bb8f7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bb8fe  jb      loc_1800BC144
0x1800bb904  mov     edx, 0Bh
0x1800bb909  jmp     loc_1800BC126
0x1800bb90e  test    r15d, r15d
0x1800bb911  jnz     loc_1800BBAA7
0x1800bb917  xorps   xmm0, xmm0
0x1800bb91a  lea     rdx, [rbp+Buf1]
0x1800bb91e  movups  [rbp+Buf1], xmm0
0x1800bb922  mov     rax, [r14]
0x1800bb925  mov     rcx, r14
0x1800bb928  mov     rax, [rax+108h]
0x1800bb92f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb934  mov     [rbp+var_2C], eax
0x1800bb937  mov     ebx, eax
0x1800bb939  test    eax, eax
0x1800bb93b  jns     loc_1800BB9D6
0x1800bb941  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb948  test    rcx, rcx
0x1800bb94b  jnz     short loc_1800BB994
0x1800bb94d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bb954  nop     dword ptr [rax+rax+00h]
0x1800bb959  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb960  mov     rcx, rax
0x1800bb963  test    rax, rax
0x1800bb966  jz      short loc_1800BB986
0x1800bb968  mov     rax, [rax]
0x1800bb96b  mov     edx, 7F0h
0x1800bb970  mov     rax, [rax+8]
0x1800bb974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb979  test    eax, eax
0x1800bb97b  jz      short loc_1800BB986
0x1800bb97d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb984  jmp     short loc_1800BB994
0x1800bb986  lea     rcx, qword_1801B97E0; this
0x1800bb98d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb994  cmp     [rcx+8], r12b
0x1800bb998  jz      short loc_1800BB9BF
0x1800bb99a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bb99f  cmp     [rax+7CCh], ebx
0x1800bb9a5  jz      short loc_1800BB9BF
0x1800bb9a7  mov     r9d, ebx; int
0x1800bb9aa  lea     rdx, aCavistreamsink_7; "CAVIStreamSink::CreateInstance"
0x1800bb9b1  mov     r8d, 26h ; '&'; int
0x1800bb9b7  mov     rcx, rax; this
0x1800bb9ba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bb9bf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bb9c6  jb      loc_1800BC144
0x1800bb9cc  mov     edx, 0Ch
0x1800bb9d1  jmp     loc_1800BC126
0x1800bb9d6  mov     r8d, 10h; Size
0x1800bb9dc  lea     rdx, MFMediaType_Video; Buf2
0x1800bb9e3  lea     rcx, [rbp+Buf1]; Buf1
0x1800bb9e7  call    memcmp_0
0x1800bb9ec  test    eax, eax
0x1800bb9ee  jz      loc_1800BBC41
0x1800bb9f4  lea     rdx, aMfMtMajorType; "MF_MT_MAJOR_TYPE"
0x1800bb9fb  mov     ecx, 0C00D36B4h
0x1800bba00  call    ??$OriginateError@$0BB@@MF@@YAJJAEAY0BB@$$CBG@Z; MF::OriginateError<17>(long,ushort const (&)[17])
0x1800bba05  mov     [rbp+var_2C], eax
0x1800bba08  mov     ebx, eax
0x1800bba0a  test    eax, eax
0x1800bba0c  jns     loc_1800BBC41
0x1800bba12  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bba19  test    rcx, rcx
0x1800bba1c  jnz     short loc_1800BBA65
0x1800bba1e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bba25  nop     dword ptr [rax+rax+00h]
0x1800bba2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bba31  mov     rcx, rax
0x1800bba34  test    rax, rax
0x1800bba37  jz      short loc_1800BBA57
0x1800bba39  mov     rax, [rax]
0x1800bba3c  mov     edx, 7F0h
0x1800bba41  mov     rax, [rax+8]
0x1800bba45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bba4a  test    eax, eax
0x1800bba4c  jz      short loc_1800BBA57
0x1800bba4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bba55  jmp     short loc_1800BBA65
0x1800bba57  lea     rcx, qword_1801B97E0; this
0x1800bba5e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bba65  cmp     [rcx+8], r12b
0x1800bba69  jz      short loc_1800BBA90
0x1800bba6b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bba70  cmp     [rax+7CCh], ebx
0x1800bba76  jz      short loc_1800BBA90
0x1800bba78  mov     r9d, ebx; int
0x1800bba7b  lea     rdx, aCavistreamsink_7; "CAVIStreamSink::CreateInstance"
0x1800bba82  mov     r8d, 29h ; ')'; int
0x1800bba88  mov     rcx, rax; this
0x1800bba8b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bba90  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bba97  jb      loc_1800BC144
0x1800bba9d  mov     edx, 0Dh
0x1800bbaa2  jmp     loc_1800BC126
0x1800bbaa7  cmp     r15d, 1
0x1800bbaab  jnz     loc_1800BC095
0x1800bbab1  xorps   xmm0, xmm0
0x1800bbab4  lea     rdx, [rbp+Buf1]
0x1800bbab8  movups  [rbp+Buf1], xmm0
0x1800bbabc  mov     rax, [r14]
0x1800bbabf  mov     rcx, r14
0x1800bbac2  mov     rax, [rax+108h]
0x1800bbac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbace  mov     [rbp+var_2C], eax
0x1800bbad1  mov     ebx, eax
0x1800bbad3  test    eax, eax
0x1800bbad5  jns     loc_1800BBB70
0x1800bbadb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbae2  test    rcx, rcx
0x1800bbae5  jnz     short loc_1800BBB2E
0x1800bbae7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bbaee  nop     dword ptr [rax+rax+00h]
0x1800bbaf3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbafa  mov     rcx, rax
0x1800bbafd  test    rax, rax
0x1800bbb00  jz      short loc_1800BBB20
0x1800bbb02  mov     rax, [rax]
0x1800bbb05  mov     edx, 7F0h
0x1800bbb0a  mov     rax, [rax+8]
0x1800bbb0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbb13  test    eax, eax
0x1800bbb15  jz      short loc_1800BBB20
0x1800bbb17  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbb1e  jmp     short loc_1800BBB2E
0x1800bbb20  lea     rcx, qword_1801B97E0; this
0x1800bbb27  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbb2e  cmp     [rcx+8], r12b
0x1800bbb32  jz      short loc_1800BBB59
0x1800bbb34  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bbb39  cmp     [rax+7CCh], ebx
0x1800bbb3f  jz      short loc_1800BBB59
0x1800bbb41  mov     r9d, ebx; int
0x1800bbb44  lea     rdx, aCavistreamsink_7; "CAVIStreamSink::CreateInstance"
0x1800bbb4b  mov     r8d, 2Fh ; '/'; int
0x1800bbb51  mov     rcx, rax; this
0x1800bbb54  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bbb59  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bbb60  jb      loc_1800BC144
0x1800bbb66  mov     edx, 0Eh
0x1800bbb6b  jmp     loc_1800BC126
0x1800bbb70  mov     r8d, 10h; Size
0x1800bbb76  lea     rdx, MFMediaType_Audio; Buf2
0x1800bbb7d  lea     rcx, [rbp+Buf1]; Buf1
0x1800bbb81  call    memcmp_0
0x1800bbb86  test    eax, eax
0x1800bbb88  jz      loc_1800BBC41
0x1800bbb8e  lea     rdx, aMfMtMajorType; "MF_MT_MAJOR_TYPE"
0x1800bbb95  mov     ecx, 0C00D36B4h
0x1800bbb9a  call    ??$OriginateError@$0BB@@MF@@YAJJAEAY0BB@$$CBG@Z; MF::OriginateError<17>(long,ushort const (&)[17])
0x1800bbb9f  mov     [rbp+var_2C], eax
0x1800bbba2  mov     ebx, eax
0x1800bbba4  test    eax, eax
0x1800bbba6  jns     loc_1800BBC41
0x1800bbbac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbbb3  test    rcx, rcx
0x1800bbbb6  jnz     short loc_1800BBBFF
0x1800bbbb8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bbbbf  nop     dword ptr [rax+rax+00h]
0x1800bbbc4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbbcb  mov     rcx, rax
0x1800bbbce  test    rax, rax
0x1800bbbd1  jz      short loc_1800BBBF1
0x1800bbbd3  mov     rax, [rax]
0x1800bbbd6  mov     edx, 7F0h
0x1800bbbdb  mov     rax, [rax+8]
0x1800bbbdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbbe4  test    eax, eax
0x1800bbbe6  jz      short loc_1800BBBF1
0x1800bbbe8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbbef  jmp     short loc_1800BBBFF
0x1800bbbf1  lea     rcx, qword_1801B97E0; this
0x1800bbbf8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbbff  cmp     [rcx+8], r12b
0x1800bbc03  jz      short loc_1800BBC2A
0x1800bbc05  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bbc0a  cmp     [rax+7CCh], ebx
0x1800bbc10  jz      short loc_1800BBC2A
0x1800bbc12  mov     r9d, ebx; int
0x1800bbc15  lea     rdx, aCavistreamsink_7; "CAVIStreamSink::CreateInstance"
0x1800bbc1c  mov     r8d, 32h ; '2'; int
0x1800bbc22  mov     rcx, rax; this
0x1800bbc25  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bbc2a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bbc31  jb      loc_1800BC144
0x1800bbc37  mov     edx, 0Fh
0x1800bbc3c  jmp     loc_1800BC126
0x1800bbc41  mov     ecx, 268h; Size
0x1800bbc46  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bbc4b  test    rax, rax
0x1800bbc4e  jz      loc_1800BBFFB
0x1800bbc54  lea     r9, [rbp+var_2C]; int *
0x1800bbc58  mov     r8d, r15d; unsigned int
0x1800bbc5b  mov     rdx, rsi; struct CAVIMediaSink *
0x1800bbc5e  mov     rcx, rax; this
0x1800bbc61  call    ??0CAVIStreamSink@@IEAA@PEAVCAVIMediaSink@@KPEAJ@Z; CAVIStreamSink::CAVIStreamSink(CAVIMediaSink *,ulong,long *)
0x1800bbc66  mov     [rbp+var_28], rax
0x1800bbc6a  mov     rsi, rax
0x1800bbc6d  test    rax, rax
0x1800bbc70  jz      loc_1800BBFFB
0x1800bbc76  mov     ebx, [rbp+var_2C]
0x1800bbc79  test    ebx, ebx
0x1800bbc7b  jns     loc_1800BBD1A
0x1800bbc81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbc88  test    rcx, rcx
0x1800bbc8b  jnz     short loc_1800BBCD4
0x1800bbc8d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bbc94  nop     dword ptr [rax+rax+00h]
0x1800bbc99  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbca0  mov     rcx, rax
0x1800bbca3  test    rax, rax
0x1800bbca6  jz      short loc_1800BBCC6
0x1800bbca8  mov     rax, [rax]
0x1800bbcab  mov     edx, 7F0h
0x1800bbcb0  mov     rax, [rax+8]
0x1800bbcb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbcb9  test    eax, eax
0x1800bbcbb  jz      short loc_1800BBCC6
0x1800bbcbd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbcc4  jmp     short loc_1800BBCD4
0x1800bbcc6  lea     rcx, qword_1801B97E0; this
0x1800bbccd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bbcd4  cmp     [rcx+8], r12b
0x1800bbcd8  jz      short loc_1800BBD03
0x1800bbcda  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bbcdf  test    ebx, ebx
0x1800bbce1  jns     short loc_1800BBD03
0x1800bbce3  cmp     [rax+7CCh], ebx
0x1800bbce9  jz      short loc_1800BBD03
0x1800bbceb  mov     r9d, ebx; int
0x1800bbcee  lea     rdx, aCavistreamsink_7; "CAVIStreamSink::CreateInstance"
0x1800bbcf5  mov     r8d, 3Ch ; '<'; int
0x1800bbcfb  mov     rcx, rax; this
0x1800bbcfe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bbd03  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bbd0a  jb      loc_1800BC144
0x1800bbd10  mov     edx, 12h
  ... truncated ...
```
