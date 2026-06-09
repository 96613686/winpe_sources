# CAVIStreamSink::VerifyVideoMediaType(IMFMediaType *)

- ea: `0x1800b5e04`
- end: `0x1800b69e4`
- name: `?VerifyVideoMediaType@CAVIStreamSink@@AEAAJPEAUIMFMediaType@@@Z`
- size: `3040`
- prototype: `__int64 __fastcall(CAVIStreamSink *__hidden this, struct IMFMediaType *)`
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18012f910`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x18005a094`
- `0x18006e524`
- `0x180079680`
- `0x180079a9c`
- `0x1800b5e04`
- `0x180110ed0`
- `0x18011cbac`
- `0x180124a8c`
- `0x18012b14c`
- `0x18012f324`
- `0x18012f358`
- `0x18012f420`
- `0x180134798`
- `0x18016c688`
- `0x18017b734`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5e8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5f81`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b604d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6129`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b620d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b62ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b63bd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6485`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b657e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b663c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6704`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b680a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6902`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5e8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5f81`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b604d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6129`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b620d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b62ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b63bd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6485`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b657e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b663c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6704`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b680a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b6902`

## string_xrefs

- `0x1800b5e31`: `CAVIStreamSink::VerifyVideoMediaType`
- `0x1800b626a`: `CAVIStreamSink::VerifyVideoMediaType`
- `0x1800b635c`: `CAVIStreamSink::VerifyVideoMediaType`
- `0x1800b641a`: `CAVIStreamSink::VerifyVideoMediaType`
- `0x1800b64e2`: `CAVIStreamSink::VerifyVideoMediaType`
- `0x1800b65db`: `CAVIStreamSink::VerifyVideoMediaType`
- `0x1800b6699`: `CAVIStreamSink::VerifyVideoMediaType`
- `0x1800b6761`: `CAVIStreamSink::VerifyVideoMediaType`
- `0x1800b6867`: `CAVIStreamSink::VerifyVideoMediaType`
- `0x1800b695f`: `CAVIStreamSink::VerifyVideoMediaType`

## pseudocode

```c
__int64 __fastcall CAVIStreamSink::VerifyVideoMediaType(CAVIStreamSink *this, struct IMFMediaType *a2)
{
  struct _GUID *v4; // rdx
  int v5; // ebx
  wchar_t *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  unsigned int v23; // eax
  unsigned int v24; // r14d
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rcx
  unsigned int v30; // eax
  __int64 v31; // rdx
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rdx
  wchar_t *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  struct _GUID *v48; // rdx
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 v52; // rcx
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  wchar_t *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rdx
  wchar_t *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  int v65; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v66; // [rsp+44h] [rbp-25h] BYREF
  _BYTE v67[4]; // [rsp+48h] [rbp-21h] BYREF
  int v68; // [rsp+4Ch] [rbp-1Dh] BYREF
  _DWORD v69[4]; // [rsp+50h] [rbp-19h] BYREF
  __int128 v70; // [rsp+60h] [rbp-9h] BYREF
  __int128 Buf1; // [rsp+70h] [rbp+7h] BYREF

  Buf1 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v67, "CAVIStreamSink::VerifyVideoMediaType", 473);
  v5 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, __int128 *))a2->lpVtbl->GetGUID)(
         a2,
         &MF_MT_SUBTYPE,
         &Buf1);
  if ( v5 < 0 )
  {
    v6 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIStreamSink::VerifyVideoMediaType", 475, v5);
    }
    if ( !g_wppLevels )
      goto LABEL_171;
    v9 = 93;
    goto LABEL_12;
  }
  v70 = Buf1;
  if ( !(unsigned int)MFMEDIATYPEUtils::IsKnownUncompressedVideoType((MFMEDIATYPEUtils *)&v70, v4) )
  {
    if ( memcmp_0(&Buf1, &MFVideoFormat_MJPG, 0x10u) )
    {
      v5 = MF::OriginateError<14>();
      if ( v5 < 0 )
      {
        v11 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
          CallStackTracing::s_wpInstance = v12;
          if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
          {
            v11 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v11 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v11 + 8) )
        {
          v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
          if ( *((_DWORD *)v13 + 499) != v5 )
            CallStackContext::TraceFailure(v13, "CAVIStreamSink::VerifyVideoMediaType", 480, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_171;
        v9 = 94;
        goto LABEL_12;
      }
    }
  }
  v14 = *((_QWORD *)this + 5);
  if ( v14 )
  {
    v70 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int128 *))(*(_QWORD *)v14 + 80LL))(
           v14,
           &MF_MT_SUBTYPE,
           &v70);
    if ( v5 < 0 )
    {
      v16 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != v5 )
          CallStackContext::TraceFailure(v18, "CAVIStreamSink::VerifyVideoMediaType", 486, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_171;
      v9 = 95;
      goto LABEL_12;
    }
    if ( memcmp_0(&v70, &Buf1, 0x10u) )
    {
      if ( byte_1801BA10A )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 96, &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids);
      v5 = MF::OriginateError<14>();
      if ( v5 < 0 )
      {
        v20 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
          CallStackTracing::s_wpInstance = v21;
          if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
          {
            v20 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v20 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v20 + 8) )
        {
          v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
          if ( *((_DWORD *)v22 + 499) != v5 )
            CallStackContext::TraceFailure(v22, "CAVIStreamSink::VerifyVideoMediaType", 490, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_171;
        v9 = 97;
        goto LABEL_12;
      }
    }
  }
  v23 = MFGetAttributeUINT32(a2, &MF_MT_INTERLACE_MODE, 0);
  v24 = v23;
  if ( (v23 & 0xFFFFFFFD) != 0 )
  {
    if ( byte_1801BA10A )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 98, &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids, v23);
    v5 = MF::OriginateError<21>();
    if ( v5 < 0 )
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
        if ( *((_DWORD *)v28 + 499) != v5 )
          CallStackContext::TraceFailure(v28, "CAVIStreamSink::VerifyVideoMediaType", 500, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_171;
      v9 = 99;
      goto LABEL_12;
    }
  }
  v29 = *((_QWORD *)this + 5);
  if ( v29 )
  {
    v30 = MFGetAttributeUINT32(v29, &MF_MT_INTERLACE_MODE, 0);
    if ( v24 != v30 )
    {
      if ( byte_1801BA10A )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 100, &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids, v30, v24);
      v5 = MF::OriginateError<21>();
      if ( v5 < 0 )
      {
        v32 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
          CallStackTracing::s_wpInstance = v33;
          if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
          {
            v32 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v32 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v32 + 8) )
        {
          v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
          if ( *((_DWORD *)v34 + 499) != v5 )
            CallStackContext::TraceFailure(v34, "CAVIStreamSink::VerifyVideoMediaType", 510, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_171;
        v9 = 101;
        goto LABEL_12;
      }
    }
  }
  v68 = 0;
  v65 = 0;
  v5 = MFGetAttribute2UINT32asUINT64(a2, &MF_MT_FRAME_SIZE, &v65, &v68);
  if ( v5 < 0 )
  {
    v36 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
      CallStackTracing::s_wpInstance = v37;
      if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
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
      if ( *((_DWORD *)v38 + 499) != v5 )
        CallStackContext::TraceFailure(v38, "CAVIStreamSink::VerifyVideoMediaType", 517, v5);
    }
    if ( !g_wppLevels )
      goto LABEL_171;
    v9 = 102;
    goto LABEL_12;
  }
  v39 = *((_QWORD *)this + 5);
  if ( v39 )
  {
    v69[0] = 0;
    v66 = 0;
    v5 = MFGetAttribute2UINT32asUINT64(v39, &MF_MT_FRAME_SIZE, &v66, v69);
    if ( v5 < 0 )
    {
      v41 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
        CallStackTracing::s_wpInstance = v42;
        if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
        {
          v41 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v41 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v41 + 8) )
      {
        v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
        if ( *((_DWORD *)v43 + 499) != v5 )
          CallStackContext::TraceFailure(v43, "CAVIStreamSink::VerifyVideoMediaType", 523, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_171;
      v9 = 103;
      goto LABEL_12;
    }
    if ( v65 != v66 || v68 != v69[0] )
    {
      if ( byte_1801BA10A )
        WPP_SF_dddd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          104,
          &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
          v66,
          v69[0],
          v65,
          v68);
      v5 = MF::OriginateError<17>(3222091453LL, L"MF_MT_FRAME_SIZE");
      if ( v5 < 0 )
      {
        v45 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
          CallStackTracing::s_wpInstance = v46;
          if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
          {
            v45 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v45 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v45 + 8) )
        {
          v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
          if ( *((_DWORD *)v47 + 499) != v5 )
            CallStackContext::TraceFailure(v47, "CAVIStreamSink::VerifyVideoMediaType", 528, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_171;
        v9 = 105;
        goto LABEL_12;
      }
    }
  }
  v68 = 0;
  v65 = 0;
  v5 = MFGetAttribute2UINT32asUINT64(a2, &MF_MT_FRAME_RATE, &v68, &v65);
  if ( v5 < 0 )
  {
    v49 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
      CallStackTracing::s_wpInstance = v50;
      if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
      {
        v49 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v49 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v49 + 8) )
    {
      v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
      if ( *((_DWORD *)v51 + 499) != v5 )
        CallStackContext::TraceFailure(v51, "CAVIStreamSink::VerifyVideoMediaType", 534, v5);
    }
    if ( !g_wppLevels )
      goto LABEL_171;
    v9 = 106;
    goto LABEL_12;
  }
  v52 = *((_QWORD *)this + 5);
  if ( v52 )
  {
    v66 = 0;
    v69[0] = 0;
    v5 = MFGetAttribute2UINT32asUINT64(v52, &MF_MT_FRAME_RATE, &v66, v69);
    if ( v5 < 0 )
    {
      v53 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
        CallStackTracing::s_wpInstance = v54;
        if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
        {
          v53 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v53 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v53 + 8) )
      {
        v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
        if ( *((_DWORD *)v55 + 499) != v5 )
          CallStackContext::TraceFailure(v55, "CAVIStreamSink::VerifyVideoMediaType", 540, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_171;
      v9 = 107;
      goto LABEL_12;
    }
    if ( v65 * v66 != v68 * v69[0] )
    {
      if ( byte_1801BA10A )
        WPP_SF_dddd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          108,
          &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
          v66,
          v69[0],
          v68,
          v65);
      v5 = MF::OriginateError<17>(3222091453LL, L"MF_MT_FRAME_RATE");
      if ( v5 < 0 )
      {
        v56 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
          CallStackTracing::s_wpInstance = v57;
          if ( v57 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
          {
            v56 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v56 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v56 + 8) )
        {
          v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
          if ( *((_DWORD *)v58 + 499) != v5 )
            CallStackContext::TraceFailure(v58, "CAVIStreamSink::VerifyVideoMediaType", 545, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_171;
        v9 = 109;
        goto LABEL_12;
      }
    }
  }
  v70 = Buf1;
  if ( !(unsigned int)MFMEDIATYPEUtils::IsKnownUncompressedVideoType((MFMEDIATYPEUtils *)&v70, v48) )
    goto LABEL_174;
  v66 = 0;
  v65 = 0;
  if ( (int)MFGetAttribute2UINT32asUINT64(a2, &MF_MT_PIXEL_ASPECT_RATIO, &v66, &v65) < 0 )
    goto LABEL_174;
  if ( v65 == v66 )
    goto LABEL_174;
  v5 = MF::OriginateError<25>(v59, L"MF_MT_PIXEL_ASPECT_RATIO");
  if ( v5 >= 0 )
    goto LABEL_174;
  v61 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v60);
    CallStackTracing::s_wpInstance = v62;
    if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
    {
      v61 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v61 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v61 + 8) )
  {
    v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
    if ( *((_DWORD *)v63 + 499) != v5 )
      CallStackContext::TraceFailure(v63, "CAVIStreamSink::VerifyVideoMediaType", 558, v5);
  }
  if ( g_wppLevels )
  {
    v9 = 110;
LABEL_12:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids, this, v5);
  }
LABEL_171:
  if ( byte_1801BA10A )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 111, &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids);
  v5 = -1072875843;
LABEL_174:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v67);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800b5e04  mov     [rsp-8+arg_10], rbx
0x1800b5e09  push    rbp
0x1800b5e0a  push    rsi
0x1800b5e0b  push    rdi
0x1800b5e0c  push    r12
0x1800b5e0e  push    r13
0x1800b5e10  push    r14
0x1800b5e12  push    r15
0x1800b5e14  lea     rbp, [rsp-27h]
0x1800b5e19  sub     rsp, 90h
0x1800b5e20  mov     rax, cs:__security_cookie
0x1800b5e27  xor     rax, rsp
0x1800b5e2a  mov     [rbp+57h+var_40], rax
0x1800b5e2e  mov     r15, rdx
0x1800b5e31  lea     r14, aCavistreamsink_6; "CAVIStreamSink::VerifyVideoMediaType"
0x1800b5e38  mov     rsi, rcx
0x1800b5e3b  xorps   xmm0, xmm0
0x1800b5e3e  mov     rdx, r14; char *
0x1800b5e41  lea     rcx, [rbp+57h+var_78]; this
0x1800b5e45  mov     r8d, 1D9h; int
0x1800b5e4b  movups  [rbp+57h+Buf1], xmm0
0x1800b5e4f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b5e54  mov     rax, [r15]
0x1800b5e57  lea     r8, [rbp+57h+Buf1]
0x1800b5e5b  lea     rdx, MF_MT_SUBTYPE
0x1800b5e62  mov     rcx, r15
0x1800b5e65  mov     rax, [rax+50h]
0x1800b5e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5e6e  xor     r12d, r12d
0x1800b5e71  lea     r13, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x1800b5e78  mov     ebx, eax
0x1800b5e7a  test    eax, eax
0x1800b5e7c  jns     loc_1800B5F30
0x1800b5e82  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5e89  test    rcx, rcx
0x1800b5e8c  jnz     short loc_1800B5ED5
0x1800b5e8e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b5e95  nop     dword ptr [rax+rax+00h]
0x1800b5e9a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5ea1  mov     rcx, rax
0x1800b5ea4  test    rax, rax
0x1800b5ea7  jz      short loc_1800B5EC7
0x1800b5ea9  mov     rax, [rax]
0x1800b5eac  mov     edx, 7F0h
0x1800b5eb1  mov     rax, [rax+8]
0x1800b5eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5eba  test    eax, eax
0x1800b5ebc  jz      short loc_1800B5EC7
0x1800b5ebe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5ec5  jmp     short loc_1800B5ED5
0x1800b5ec7  lea     rcx, qword_1801B97E0; this
0x1800b5ece  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5ed5  cmp     [rcx+8], r12b
0x1800b5ed9  jz      short loc_1800B5EFC
0x1800b5edb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b5ee0  cmp     [rax+7CCh], ebx
0x1800b5ee6  jz      short loc_1800B5EFC
0x1800b5ee8  mov     r9d, ebx; int
0x1800b5eeb  mov     r8d, 1DBh; int
0x1800b5ef1  mov     rdx, r14; char *
0x1800b5ef4  mov     rcx, rax; this
0x1800b5ef7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b5efc  mov     dil, 1
0x1800b5eff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800b5f06  jb      loc_1800B698B
0x1800b5f0c  mov     edx, 5Dh ; ']'
0x1800b5f11  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5f18  mov     r9, rsi
0x1800b5f1b  mov     r8, r13
0x1800b5f1e  mov     [rsp+0C0h+var_A0], ebx
0x1800b5f22  mov     rcx, [rcx+10h]
0x1800b5f26  call    WPP_SF_qD
0x1800b5f2b  jmp     loc_1800B698B
0x1800b5f30  movaps  xmm0, [rbp+57h+Buf1]
0x1800b5f34  lea     rcx, [rbp+57h+var_60]; this
0x1800b5f38  movdqa  [rbp+57h+var_60], xmm0
0x1800b5f3d  call    ?IsKnownUncompressedVideoType@MFMEDIATYPEUtils@@YAHU_GUID@@@Z; MFMEDIATYPEUtils::IsKnownUncompressedVideoType(_GUID)
0x1800b5f42  test    eax, eax
0x1800b5f44  jnz     loc_1800B6009
0x1800b5f4a  lea     r8d, [rax+10h]; Size
0x1800b5f4e  lea     rdx, MFVideoFormat_MJPG; Buf2
0x1800b5f55  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800b5f59  call    memcmp_0
0x1800b5f5e  test    eax, eax
0x1800b5f60  jz      loc_1800B6009
0x1800b5f66  call    ??$OriginateError@$0O@@MF@@YAJJAEAY0O@$$CBG@Z; MF::OriginateError<14>(long,ushort const (&)[14])
0x1800b5f6b  mov     ebx, eax
0x1800b5f6d  test    eax, eax
0x1800b5f6f  jns     loc_1800B6009
0x1800b5f75  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5f7c  test    rcx, rcx
0x1800b5f7f  jnz     short loc_1800B5FC8
0x1800b5f81  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b5f88  nop     dword ptr [rax+rax+00h]
0x1800b5f8d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5f94  mov     rcx, rax
0x1800b5f97  test    rax, rax
0x1800b5f9a  jz      short loc_1800B5FBA
0x1800b5f9c  mov     rax, [rax]
0x1800b5f9f  mov     edx, 7F0h
0x1800b5fa4  mov     rax, [rax+8]
0x1800b5fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5fad  test    eax, eax
0x1800b5faf  jz      short loc_1800B5FBA
0x1800b5fb1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5fb8  jmp     short loc_1800B5FC8
0x1800b5fba  lea     rcx, qword_1801B97E0; this
0x1800b5fc1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5fc8  cmp     [rcx+8], r12b
0x1800b5fcc  jz      short loc_1800B5FEF
0x1800b5fce  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b5fd3  cmp     [rax+7CCh], ebx
0x1800b5fd9  jz      short loc_1800B5FEF
0x1800b5fdb  mov     r9d, ebx; int
0x1800b5fde  mov     r8d, 1E0h; int
0x1800b5fe4  mov     rdx, r14; char *
0x1800b5fe7  mov     rcx, rax; this
0x1800b5fea  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b5fef  mov     dil, 1
0x1800b5ff2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800b5ff9  jb      loc_1800B698B
0x1800b5fff  mov     edx, 5Eh ; '^'
0x1800b6004  jmp     loc_1800B5F11
0x1800b6009  mov     rcx, [rsi+28h]
0x1800b600d  mov     dil, 1
0x1800b6010  test    rcx, rcx
0x1800b6013  jz      loc_1800B61AE
0x1800b6019  xorps   xmm0, xmm0
0x1800b601c  lea     r8, [rbp+57h+var_60]
0x1800b6020  movups  [rbp+57h+var_60], xmm0
0x1800b6024  mov     rax, [rcx]
0x1800b6027  lea     rdx, MF_MT_SUBTYPE
0x1800b602e  mov     rax, [rax+50h]
0x1800b6032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6037  mov     ebx, eax
0x1800b6039  test    eax, eax
0x1800b603b  jns     loc_1800B60D2
0x1800b6041  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6048  test    rcx, rcx
0x1800b604b  jnz     short loc_1800B6094
0x1800b604d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b6054  nop     dword ptr [rax+rax+00h]
0x1800b6059  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6060  mov     rcx, rax
0x1800b6063  test    rax, rax
0x1800b6066  jz      short loc_1800B6086
0x1800b6068  mov     rax, [rax]
0x1800b606b  mov     edx, 7F0h
0x1800b6070  mov     rax, [rax+8]
0x1800b6074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6079  test    eax, eax
0x1800b607b  jz      short loc_1800B6086
0x1800b607d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6084  jmp     short loc_1800B6094
0x1800b6086  lea     rcx, qword_1801B97E0; this
0x1800b608d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6094  cmp     [rcx+8], r12b
0x1800b6098  jz      short loc_1800B60BB
0x1800b609a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b609f  cmp     [rax+7CCh], ebx
0x1800b60a5  jz      short loc_1800B60BB
0x1800b60a7  mov     r9d, ebx; int
0x1800b60aa  mov     r8d, 1E6h; int
0x1800b60b0  mov     rdx, r14; char *
0x1800b60b3  mov     rcx, rax; this
0x1800b60b6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b60bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800b60c2  jb      loc_1800B698B
0x1800b60c8  mov     edx, 5Fh ; '_'
0x1800b60cd  jmp     loc_1800B5F11
0x1800b60d2  mov     r8d, 10h; Size
0x1800b60d8  lea     rdx, [rbp+57h+Buf1]; Buf2
0x1800b60dc  lea     rcx, [rbp+57h+var_60]; Buf1
0x1800b60e0  call    memcmp_0
0x1800b60e5  test    eax, eax
0x1800b60e7  jz      loc_1800B61AE
0x1800b60ed  cmp     cs:byte_1801BA10A, dil
0x1800b60f4  jb      short loc_1800B610E
0x1800b60f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b60fd  mov     edx, 60h ; '`'
0x1800b6102  mov     r8, r13
0x1800b6105  mov     rcx, [rcx+60h]
0x1800b6109  call    WPP_SF_
0x1800b610e  call    ??$OriginateError@$0O@@MF@@YAJJAEAY0O@$$CBG@Z; MF::OriginateError<14>(long,ushort const (&)[14])
0x1800b6113  mov     ebx, eax
0x1800b6115  test    eax, eax
0x1800b6117  jns     loc_1800B61AE
0x1800b611d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6124  test    rcx, rcx
0x1800b6127  jnz     short loc_1800B6170
0x1800b6129  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b6130  nop     dword ptr [rax+rax+00h]
0x1800b6135  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b613c  mov     rcx, rax
0x1800b613f  test    rax, rax
0x1800b6142  jz      short loc_1800B6162
0x1800b6144  mov     rax, [rax]
0x1800b6147  mov     edx, 7F0h
0x1800b614c  mov     rax, [rax+8]
0x1800b6150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6155  test    eax, eax
0x1800b6157  jz      short loc_1800B6162
0x1800b6159  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6160  jmp     short loc_1800B6170
0x1800b6162  lea     rcx, qword_1801B97E0; this
0x1800b6169  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6170  cmp     [rcx+8], r12b
0x1800b6174  jz      short loc_1800B6197
0x1800b6176  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b617b  cmp     [rax+7CCh], ebx
0x1800b6181  jz      short loc_1800B6197
0x1800b6183  mov     r9d, ebx; int
0x1800b6186  mov     r8d, 1EAh; int
0x1800b618c  mov     rdx, r14; char *
0x1800b618f  mov     rcx, rax; this
0x1800b6192  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b6197  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800b619e  jb      loc_1800B698B
0x1800b61a4  mov     edx, 61h ; 'a'
0x1800b61a9  jmp     loc_1800B5F11
0x1800b61ae  xor     r8d, r8d
0x1800b61b1  lea     rdx, MF_MT_INTERLACE_MODE
0x1800b61b8  mov     rcx, r15
0x1800b61bb  call    MFGetAttributeUINT32
0x1800b61c0  mov     r14d, eax
0x1800b61c3  test    eax, 0FFFFFFFDh
0x1800b61c8  jz      loc_1800B6296
0x1800b61ce  cmp     cs:byte_1801BA10A, dil
0x1800b61d5  jb      short loc_1800B61F2
0x1800b61d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b61de  mov     edx, 62h ; 'b'
0x1800b61e3  mov     r9d, eax
0x1800b61e6  mov     r8, r13
0x1800b61e9  mov     rcx, [rcx+60h]
0x1800b61ed  call    WPP_SF_d
0x1800b61f2  call    ??$OriginateError@$0BF@@MF@@YAJJAEAY0BF@$$CBG@Z; MF::OriginateError<21>(long,ushort const (&)[21])
0x1800b61f7  mov     ebx, eax
0x1800b61f9  test    eax, eax
0x1800b61fb  jns     loc_1800B6296
0x1800b6201  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6208  test    rcx, rcx
0x1800b620b  jnz     short loc_1800B6254
0x1800b620d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b6214  nop     dword ptr [rax+rax+00h]
0x1800b6219  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6220  mov     rcx, rax
0x1800b6223  test    rax, rax
0x1800b6226  jz      short loc_1800B6246
0x1800b6228  mov     rax, [rax]
0x1800b622b  mov     edx, 7F0h
0x1800b6230  mov     rax, [rax+8]
0x1800b6234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6239  test    eax, eax
0x1800b623b  jz      short loc_1800B6246
0x1800b623d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6244  jmp     short loc_1800B6254
0x1800b6246  lea     rcx, qword_1801B97E0; this
0x1800b624d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6254  cmp     [rcx+8], r12b
0x1800b6258  jz      short loc_1800B627F
0x1800b625a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b625f  cmp     [rax+7CCh], ebx
0x1800b6265  jz      short loc_1800B627F
0x1800b6267  mov     r9d, ebx; int
0x1800b626a  lea     rdx, aCavistreamsink_6; "CAVIStreamSink::VerifyVideoMediaType"
0x1800b6271  mov     r8d, 1F4h; int
0x1800b6277  mov     rcx, rax; this
0x1800b627a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b627f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800b6286  jb      loc_1800B698B
0x1800b628c  mov     edx, 63h ; 'c'
0x1800b6291  jmp     loc_1800B5F11
0x1800b6296  mov     rcx, [rsi+28h]
0x1800b629a  test    rcx, rcx
0x1800b629d  jz      loc_1800B6388
0x1800b62a3  xor     r8d, r8d
0x1800b62a6  lea     rdx, MF_MT_INTERLACE_MODE
0x1800b62ad  call    MFGetAttributeUINT32
0x1800b62b2  cmp     r14d, eax
0x1800b62b5  jz      loc_1800B6388
0x1800b62bb  cmp     cs:byte_1801BA10A, dil
0x1800b62c2  jb      short loc_1800B62E4
0x1800b62c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b62cb  mov     edx, 64h ; 'd'
0x1800b62d0  mov     r9d, eax
0x1800b62d3  mov     [rsp+0C0h+var_A0], r14d
0x1800b62d8  mov     r8, r13
0x1800b62db  mov     rcx, [rcx+60h]
0x1800b62df  call    WPP_SF_dd
0x1800b62e4  call    ??$OriginateError@$0BF@@MF@@YAJJAEAY0BF@$$CBG@Z; MF::OriginateError<21>(long,ushort const (&)[21])
0x1800b62e9  mov     ebx, eax
0x1800b62eb  test    eax, eax
0x1800b62ed  jns     loc_1800B6388
0x1800b62f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b62fa  test    rcx, rcx
0x1800b62fd  jnz     short loc_1800B6346
0x1800b62ff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b6306  nop     dword ptr [rax+rax+00h]
0x1800b630b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b6312  mov     rcx, rax
  ... truncated ...
```
