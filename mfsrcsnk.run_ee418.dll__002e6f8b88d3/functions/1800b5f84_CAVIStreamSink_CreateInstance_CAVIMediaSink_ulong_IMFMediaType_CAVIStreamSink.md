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
  __int64 v10; // r8
  __int64 v11; // r9
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  CAVIStreamSink *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  CAVIStreamSink *v44; // rax
  CAVIStreamSink *v45; // rsi
  wchar_t *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  char *v49; // r12
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // r8
  char *v58; // r9
  wchar_t *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // r9
  wchar_t *v65; // rcx
  CallStackTracing *v66; // rax
  struct CallStackContext *v67; // rax
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // r9
  wchar_t *v71; // rcx
  CallStackTracing *v72; // rax
  struct CallStackContext *v73; // rax
  wchar_t *v74; // rcx
  CallStackTracing *v75; // rax
  struct CallStackContext *v76; // rax
  wchar_t *v77; // rcx
  CallStackTracing *v78; // rax
  struct CallStackContext *v79; // rax
  _BYTE v81[4]; // [rsp+30h] [rbp-30h] BYREF
  int v82; // [rsp+34h] [rbp-2Ch] BYREF
  CAVIStreamSink *v83; // [rsp+38h] [rbp-28h] BYREF
  struct IMFMediaType *v84; // [rsp+40h] [rbp-20h] BYREF
  __int128 Buf1; // [rsp+48h] [rbp-18h] BYREF

  v84 = a3;
  if ( !a1 || !a3 || (ChunkID = 0, !a4) )
    ChunkID = -2147467261;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v81, "CAVIStreamSink::CreateInstance", 31);
  v83 = 0;
  if ( ChunkID < 0 )
  {
    v12 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10, v11);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != ChunkID )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIStreamSink::CreateInstance", 33, ChunkID);
    }
    if ( g_wppLevels )
    {
      v15 = 11;
LABEL_143:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids, 0, ChunkID);
      goto LABEL_144;
    }
    goto LABEL_144;
  }
  if ( a2 )
  {
    if ( a2 != 1 )
    {
      v77 = (wchar_t *)CallStackTracing::s_wpInstance;
      ChunkID = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10, v11);
        CallStackTracing::s_wpInstance = v78;
        if ( v78 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v78 + 8LL))(v78, 2032) )
        {
          v77 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v77 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v77 + 8) )
      {
        v79 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v77);
        if ( *((_DWORD *)v79 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v79, "CAVIStreamSink::CreateInstance", 55, -2147024809);
      }
      if ( g_wppLevels )
      {
        v15 = 16;
        goto LABEL_143;
      }
      goto LABEL_144;
    }
    Buf1 = 0;
    v82 = ((__int64 (__fastcall *)(struct IMFMediaType *, __int128 *))a3->lpVtbl->GetMajorType)(a3, &Buf1);
    ChunkID = v82;
    if ( v82 < 0 )
    {
      v31 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
        CallStackTracing::s_wpInstance = v32;
        if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
        {
          v31 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v31 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v31 + 8) )
      {
        v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
        if ( *((_DWORD *)v33 + 499) != ChunkID )
          CallStackContext::TraceFailure(v33, "CAVIStreamSink::CreateInstance", 47, ChunkID);
      }
      if ( g_wppLevels )
      {
        v15 = 14;
        goto LABEL_143;
      }
      goto LABEL_144;
    }
    if ( memcmp_0(&Buf1, &MFMediaType_Audio, 0x10u) )
    {
      v82 = MF::OriginateError<17>(3222091444LL, L"MF_MT_MAJOR_TYPE");
      ChunkID = v82;
      if ( v82 < 0 )
      {
        v37 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35, v36);
          CallStackTracing::s_wpInstance = v38;
          if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
          {
            v37 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v37 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v37 + 8) )
        {
          v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
          if ( *((_DWORD *)v39 + 499) != ChunkID )
            CallStackContext::TraceFailure(v39, "CAVIStreamSink::CreateInstance", 50, ChunkID);
        }
        if ( g_wppLevels )
        {
          v15 = 15;
          goto LABEL_143;
        }
        goto LABEL_144;
      }
    }
    goto LABEL_64;
  }
  Buf1 = 0;
  v82 = ((__int64 (__fastcall *)(struct IMFMediaType *, __int128 *))a3->lpVtbl->GetMajorType)(a3, &Buf1);
  ChunkID = v82;
  if ( v82 >= 0 )
  {
    if ( memcmp_0(&Buf1, &MFMediaType_Video, 0x10u) )
    {
      v82 = MF::OriginateError<17>(3222091444LL, L"MF_MT_MAJOR_TYPE");
      ChunkID = v82;
      if ( v82 < 0 )
      {
        v25 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( *((_DWORD *)v27 + 499) != ChunkID )
            CallStackContext::TraceFailure(v27, "CAVIStreamSink::CreateInstance", 41, ChunkID);
        }
        if ( g_wppLevels )
        {
          v15 = 13;
          goto LABEL_143;
        }
        goto LABEL_144;
      }
    }
LABEL_64:
    v40 = (CAVIStreamSink *)operator new(0x268u);
    if ( v40 && (v44 = CAVIStreamSink::CAVIStreamSink(v40, a1, a2, &v82), v83 = v44, (v45 = v44) != 0) )
    {
      ChunkID = v82;
      if ( v82 >= 0 )
      {
        v49 = (char *)v44 + 32;
        ChunkID = CMFMediaTypeHandlerBase::Initialize((CAVIStreamSink *)((char *)v44 + 32), v41, &v84);
        if ( ChunkID >= 0 )
        {
          ChunkID = (*(__int64 (__fastcall **)(char *, struct IMFMediaType *))(*(_QWORD *)v49 + 48LL))(v49, a3);
          if ( ChunkID >= 0 )
          {
            ChunkID = AVIHelpers::GetChunkID(
                        (AVIHelpers *)a2,
                        (unsigned int)a3,
                        (struct IMFMediaType *)((char *)v45 + 508),
                        v58);
            if ( ChunkID >= 0 )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)v45 + 48);
              ChunkID = CAVIStreamIndex::CreateInstance(
                          a2,
                          (const char *const)v45 + 508,
                          (struct CAVIStreamIndex **)v45 + 48);
              if ( ChunkID >= 0 )
              {
                v83 = 0;
                *a4 = v45;
              }
              else
              {
                v71 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v68, v69, v70);
                  CallStackTracing::s_wpInstance = v72;
                  if ( v72
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v72 + 8LL))(v72, 2032) )
                  {
                    v71 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v71 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v71 + 8) )
                {
                  v73 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v71);
                  if ( *((_DWORD *)v73 + 499) != ChunkID )
                    CallStackContext::TraceFailure(v73, "CAVIStreamSink::CreateInstance", 64, ChunkID);
                }
                if ( g_wppLevels )
                {
                  v15 = 22;
                  goto LABEL_143;
                }
              }
            }
            else
            {
              v65 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62, v63, v64);
                CallStackTracing::s_wpInstance = v66;
                if ( v66
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v66 + 8LL))(v66, 2032) )
                {
                  v65 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v65 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v65 + 8) )
              {
                v67 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v65);
                if ( *((_DWORD *)v67 + 499) != ChunkID )
                  CallStackContext::TraceFailure(v67, "CAVIStreamSink::CreateInstance", 63, ChunkID);
              }
              if ( g_wppLevels )
              {
                v15 = 21;
                goto LABEL_143;
              }
            }
          }
          else
          {
            v59 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56, v57, v58);
              CallStackTracing::s_wpInstance = v60;
              if ( v60
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
              {
                v59 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v59 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v59 + 8) )
            {
              v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
              if ( *((_DWORD *)v61 + 499) != ChunkID )
                CallStackContext::TraceFailure(v61, "CAVIStreamSink::CreateInstance", 62, ChunkID);
            }
            if ( g_wppLevels )
            {
              v15 = 20;
              goto LABEL_143;
            }
          }
        }
        else
        {
          v53 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50, v51, v52);
            CallStackTracing::s_wpInstance = v54;
            if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
            {
              v53 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v53 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v53 + 8) )
          {
            v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
            if ( *((_DWORD *)v55 + 499) != ChunkID )
              CallStackContext::TraceFailure(v55, "CAVIStreamSink::CreateInstance", 61, ChunkID);
          }
          if ( g_wppLevels )
          {
            v15 = 19;
            goto LABEL_143;
          }
        }
      }
      else
      {
        v46 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42, v43);
          CallStackTracing::s_wpInstance = v47;
          if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
          {
            v46 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v46 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v46 + 8) )
        {
          v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
          if ( ChunkID < 0 && *((_DWORD *)v48 + 499) != ChunkID )
            CallStackContext::TraceFailure(v48, "CAVIStreamSink::CreateInstance", 60, ChunkID);
        }
        if ( g_wppLevels )
        {
          v15 = 18;
          goto LABEL_143;
        }
      }
    }
    else
    {
      v74 = (wchar_t *)CallStackTracing::s_wpInstance;
      ChunkID = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v75 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42, v43);
        CallStackTracing::s_wpInstance = v75;
        if ( v75 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v75 + 8LL))(v75, 2032) )
        {
          v74 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v74 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v74 + 8) )
      {
        v76 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v74);
        if ( *((_DWORD *)v76 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v76, "CAVIStreamSink::CreateInstance", 59, -2147024882);
      }
      if ( g_wppLevels )
      {
        v15 = 17;
        goto LABEL_143;
      }
    }
    goto LABEL_144;
  }
  v19 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17, v18);
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
      CallStackContext::TraceFailure(v21, "CAVIStreamSink::CreateInstance", 38, ChunkID);
  }
  if ( g_wppLevels )
  {
    v15 = 12;
    goto LABEL_143;
  }
LABEL_144:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v83);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v81);
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
