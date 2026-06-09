# CAVIStreamSink::VerifyVideoMediaType(IMFMediaType *)

- ea: `0x1800b0874`
- end: `0x1800b1405`
- name: `?VerifyVideoMediaType@CAVIStreamSink@@AEAAJPEAUIMFMediaType@@@Z`
- size: `2961`
- prototype: `__int64 __fastcall(CAVIStreamSink *__hidden this, struct IMFMediaType *)`
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180128770`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180056e38`
- `0x18006cdb8`
- `0x180073b14`
- `0x180073e00`
- `0x1800b0874`
- `0x1801099f0`
- `0x180115a1c`
- `0x18011e37c`
- `0x180124268`
- `0x1801281dc`
- `0x180128208`
- `0x1801282b0`
- `0x18012d38c`
- `0x180163798`
- `0x1801723d4`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b08fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b09eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0ab1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0b87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0c65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0d51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0e09`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0ecb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0fbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1076`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1138`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1238`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b132a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b08fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b09eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0ab1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0b87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0c65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0d51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0e09`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0ecb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0fbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1076`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1138`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1238`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b132a`

## string_xrefs

- `0x1800b08a1`: `CAVIStreamSink::VerifyVideoMediaType`
- `0x1800b0cbc`: `CAVIStreamSink::VerifyVideoMediaType`
- `0x1800b0da8`: `CAVIStreamSink::VerifyVideoMediaType`
- `0x1800b0e60`: `CAVIStreamSink::VerifyVideoMediaType`
- `0x1800b0f22`: `CAVIStreamSink::VerifyVideoMediaType`
- `0x1800b1015`: `CAVIStreamSink::VerifyVideoMediaType`
- `0x1800b10cd`: `CAVIStreamSink::VerifyVideoMediaType`
- `0x1800b118f`: `CAVIStreamSink::VerifyVideoMediaType`
- `0x1800b128f`: `CAVIStreamSink::VerifyVideoMediaType`
- `0x1800b1381`: `CAVIStreamSink::VerifyVideoMediaType`

## pseudocode

```c
__int64 __fastcall CAVIStreamSink::VerifyVideoMediaType(CAVIStreamSink *this, struct IMFMediaType *a2)
{
  struct _GUID *v4; // rdx
  int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  wchar_t *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  unsigned int v31; // eax
  unsigned int v32; // r14d
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rcx
  unsigned int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  wchar_t *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // r9
  wchar_t *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // r9
  wchar_t *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  struct _GUID *v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r9
  wchar_t *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  __int64 v72; // rcx
  __int64 v73; // r8
  __int64 v74; // r9
  wchar_t *v75; // rcx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  __int64 v78; // r8
  __int64 v79; // r9
  wchar_t *v80; // rcx
  CallStackTracing *v81; // rax
  struct CallStackContext *v82; // rax
  __int64 v83; // rcx
  __int64 v84; // rdx
  __int64 v85; // r8
  __int64 v86; // r9
  wchar_t *v87; // rcx
  CallStackTracing *v88; // rax
  struct CallStackContext *v89; // rax
  int v91; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v92; // [rsp+44h] [rbp-25h] BYREF
  _BYTE v93[4]; // [rsp+48h] [rbp-21h] BYREF
  int v94; // [rsp+4Ch] [rbp-1Dh] BYREF
  _DWORD v95[4]; // [rsp+50h] [rbp-19h] BYREF
  __int128 v96; // [rsp+60h] [rbp-9h] BYREF
  __int128 Buf1; // [rsp+70h] [rbp+7h] BYREF

  Buf1 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v93, "CAVIStreamSink::VerifyVideoMediaType", 473);
  v5 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, __int128 *))a2->lpVtbl->GetGUID)(
         a2,
         &MF_MT_SUBTYPE,
         &Buf1);
  if ( v5 < 0 )
  {
    v8 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIStreamSink::VerifyVideoMediaType", 475, v5);
    }
    if ( !g_wppLevels )
      goto LABEL_171;
    v11 = 93;
    goto LABEL_12;
  }
  v96 = Buf1;
  if ( !(unsigned int)MFMEDIATYPEUtils::IsKnownUncompressedVideoType((MFMEDIATYPEUtils *)&v96, v4) )
  {
    if ( memcmp_0(&Buf1, &MFVideoFormat_MJPG, 0x10u) )
    {
      v5 = MF::OriginateError<14>();
      if ( v5 < 0 )
      {
        v15 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
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
          if ( *((_DWORD *)v17 + 499) != v5 )
            CallStackContext::TraceFailure(v17, "CAVIStreamSink::VerifyVideoMediaType", 480, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_171;
        v11 = 94;
        goto LABEL_12;
      }
    }
  }
  v18 = *((_QWORD *)this + 5);
  if ( v18 )
  {
    v96 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int128 *))(*(_QWORD *)v18 + 80LL))(
           v18,
           &MF_MT_SUBTYPE,
           &v96);
    if ( v5 < 0 )
    {
      v22 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
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
        if ( *((_DWORD *)v24 + 499) != v5 )
          CallStackContext::TraceFailure(v24, "CAVIStreamSink::VerifyVideoMediaType", 486, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_171;
      v11 = 95;
      goto LABEL_12;
    }
    if ( memcmp_0(&v96, &Buf1, 0x10u) )
    {
      if ( byte_1801B110A )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 96, &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids);
      v5 = MF::OriginateError<14>();
      if ( v5 < 0 )
      {
        v28 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26, v27);
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v28 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v28 + 8) )
        {
          v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
          if ( *((_DWORD *)v30 + 499) != v5 )
            CallStackContext::TraceFailure(v30, "CAVIStreamSink::VerifyVideoMediaType", 490, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_171;
        v11 = 97;
        goto LABEL_12;
      }
    }
  }
  v31 = MFGetAttributeUINT32(a2, &MF_MT_INTERLACE_MODE, 0);
  v32 = v31;
  if ( (v31 & 0xFFFFFFFD) != 0 )
  {
    if ( byte_1801B110A )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 98, &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids, v31);
    v5 = MF::OriginateError<21>();
    if ( v5 < 0 )
    {
      v36 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34, v35);
        CallStackTracing::s_wpInstance = v37;
        if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
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
        if ( *((_DWORD *)v38 + 499) != v5 )
          CallStackContext::TraceFailure(v38, "CAVIStreamSink::VerifyVideoMediaType", 500, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_171;
      v11 = 99;
      goto LABEL_12;
    }
  }
  v39 = *((_QWORD *)this + 5);
  if ( v39 )
  {
    v40 = MFGetAttributeUINT32(v39, &MF_MT_INTERLACE_MODE, 0);
    if ( v32 != v40 )
    {
      if ( byte_1801B110A )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 100, &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids, v40, v32);
      v5 = MF::OriginateError<21>();
      if ( v5 < 0 )
      {
        v44 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42, v43);
          CallStackTracing::s_wpInstance = v45;
          if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
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
          if ( *((_DWORD *)v46 + 499) != v5 )
            CallStackContext::TraceFailure(v46, "CAVIStreamSink::VerifyVideoMediaType", 510, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_171;
        v11 = 101;
        goto LABEL_12;
      }
    }
  }
  v94 = 0;
  v91 = 0;
  v5 = MFGetAttribute2UINT32asUINT64(a2, &MF_MT_FRAME_SIZE, &v91, &v94);
  if ( v5 < 0 )
  {
    v50 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47, v48, v49);
      CallStackTracing::s_wpInstance = v51;
      if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
      {
        v50 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v50 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v50 + 8) )
    {
      v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
      if ( *((_DWORD *)v52 + 499) != v5 )
        CallStackContext::TraceFailure(v52, "CAVIStreamSink::VerifyVideoMediaType", 517, v5);
    }
    if ( !g_wppLevels )
      goto LABEL_171;
    v11 = 102;
    goto LABEL_12;
  }
  v53 = *((_QWORD *)this + 5);
  if ( v53 )
  {
    v95[0] = 0;
    v92 = 0;
    v5 = MFGetAttribute2UINT32asUINT64(v53, &MF_MT_FRAME_SIZE, &v92, v95);
    if ( v5 < 0 )
    {
      v57 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54, v55, v56);
        CallStackTracing::s_wpInstance = v58;
        if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
        {
          v57 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v57 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v57 + 8) )
      {
        v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
        if ( *((_DWORD *)v59 + 499) != v5 )
          CallStackContext::TraceFailure(v59, "CAVIStreamSink::VerifyVideoMediaType", 523, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_171;
      v11 = 103;
      goto LABEL_12;
    }
    if ( v91 != v92 || v94 != v95[0] )
    {
      if ( byte_1801B110A )
        WPP_SF_dddd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          104,
          &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
          v92,
          v95[0],
          v91,
          v94);
      v5 = MF::OriginateError<17>(3222091453LL, L"MF_MT_FRAME_SIZE");
      if ( v5 < 0 )
      {
        v63 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v60, v61, v62);
          CallStackTracing::s_wpInstance = v64;
          if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
          {
            v63 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v63 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v63 + 8) )
        {
          v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
          if ( *((_DWORD *)v65 + 499) != v5 )
            CallStackContext::TraceFailure(v65, "CAVIStreamSink::VerifyVideoMediaType", 528, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_171;
        v11 = 105;
        goto LABEL_12;
      }
    }
  }
  v94 = 0;
  v91 = 0;
  v5 = MFGetAttribute2UINT32asUINT64(a2, &MF_MT_FRAME_RATE, &v94, &v91);
  if ( v5 < 0 )
  {
    v69 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v67, v68);
      CallStackTracing::s_wpInstance = v70;
      if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
      {
        v69 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v69 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v69 + 8) )
    {
      v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
      if ( *((_DWORD *)v71 + 499) != v5 )
        CallStackContext::TraceFailure(v71, "CAVIStreamSink::VerifyVideoMediaType", 534, v5);
    }
    if ( !g_wppLevels )
      goto LABEL_171;
    v11 = 106;
    goto LABEL_12;
  }
  v72 = *((_QWORD *)this + 5);
  if ( v72 )
  {
    v92 = 0;
    v95[0] = 0;
    v5 = MFGetAttribute2UINT32asUINT64(v72, &MF_MT_FRAME_RATE, &v92, v95);
    if ( v5 < 0 )
    {
      v75 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v73, v74);
        CallStackTracing::s_wpInstance = v76;
        if ( v76 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(v76, 2032) )
        {
          v75 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v75 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v75 + 8) )
      {
        v77 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v75);
        if ( *((_DWORD *)v77 + 499) != v5 )
          CallStackContext::TraceFailure(v77, "CAVIStreamSink::VerifyVideoMediaType", 540, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_171;
      v11 = 107;
      goto LABEL_12;
    }
    if ( v91 * v92 != v94 * v95[0] )
    {
      if ( byte_1801B110A )
        WPP_SF_dddd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          108,
          &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
          v92,
          v95[0],
          v94,
          v91);
      v5 = MF::OriginateError<17>(3222091453LL, L"MF_MT_FRAME_RATE");
      if ( v5 < 0 )
      {
        v80 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v81 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v78, v79);
          CallStackTracing::s_wpInstance = v81;
          if ( v81 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v81 + 8LL))(v81, 2032) )
          {
            v80 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v80 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v80 + 8) )
        {
          v82 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v80);
          if ( *((_DWORD *)v82 + 499) != v5 )
            CallStackContext::TraceFailure(v82, "CAVIStreamSink::VerifyVideoMediaType", 545, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_171;
        v11 = 109;
        goto LABEL_12;
      }
    }
  }
  v96 = Buf1;
  if ( !(unsigned int)MFMEDIATYPEUtils::IsKnownUncompressedVideoType((MFMEDIATYPEUtils *)&v96, v66) )
    goto LABEL_174;
  v92 = 0;
  v91 = 0;
  if ( (int)MFGetAttribute2UINT32asUINT64(a2, &MF_MT_PIXEL_ASPECT_RATIO, &v92, &v91) < 0 )
    goto LABEL_174;
  if ( v91 == v92 )
    goto LABEL_174;
  v5 = MF::OriginateError<25>(v83, L"MF_MT_PIXEL_ASPECT_RATIO");
  if ( v5 >= 0 )
    goto LABEL_174;
  v87 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v88 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v84, v85, v86);
    CallStackTracing::s_wpInstance = v88;
    if ( v88 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v88 + 8LL))(v88, 2032) )
    {
      v87 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v87 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v87 + 8) )
  {
    v89 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v87);
    if ( *((_DWORD *)v89 + 499) != v5 )
      CallStackContext::TraceFailure(v89, "CAVIStreamSink::VerifyVideoMediaType", 558, v5);
  }
  if ( g_wppLevels )
  {
    v11 = 110;
LABEL_12:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids, this, v5);
  }
LABEL_171:
  if ( byte_1801B110A )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 111, &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids);
  v5 = -1072875843;
LABEL_174:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v93);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800b0874  mov     [rsp-8+arg_10], rbx
0x1800b0879  push    rbp
0x1800b087a  push    rsi
0x1800b087b  push    rdi
0x1800b087c  push    r12
0x1800b087e  push    r13
0x1800b0880  push    r14
0x1800b0882  push    r15
0x1800b0884  lea     rbp, [rsp-27h]
0x1800b0889  sub     rsp, 90h
0x1800b0890  mov     rax, cs:__security_cookie
0x1800b0897  xor     rax, rsp
0x1800b089a  mov     [rbp+57h+var_40], rax
0x1800b089e  mov     r15, rdx
0x1800b08a1  lea     r14, aCavistreamsink_6; "CAVIStreamSink::VerifyVideoMediaType"
0x1800b08a8  mov     rsi, rcx
0x1800b08ab  xorps   xmm0, xmm0
0x1800b08ae  mov     rdx, r14; char *
0x1800b08b1  lea     rcx, [rbp+57h+var_78]; this
0x1800b08b5  mov     r8d, 1D9h; int
0x1800b08bb  movups  [rbp+57h+Buf1], xmm0
0x1800b08bf  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b08c4  mov     rax, [r15]
0x1800b08c7  lea     r8, [rbp+57h+Buf1]
0x1800b08cb  lea     rdx, MF_MT_SUBTYPE
0x1800b08d2  mov     rcx, r15
0x1800b08d5  mov     rax, [rax+50h]
0x1800b08d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b08de  xor     r12d, r12d
0x1800b08e1  lea     r13, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x1800b08e8  mov     ebx, eax
0x1800b08ea  test    eax, eax
0x1800b08ec  jns     loc_1800B099A
0x1800b08f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b08f9  test    rcx, rcx
0x1800b08fc  jnz     short loc_1800B093F
0x1800b08fe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b0904  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b090b  mov     rcx, rax
0x1800b090e  test    rax, rax
0x1800b0911  jz      short loc_1800B0931
0x1800b0913  mov     rax, [rax]
0x1800b0916  mov     edx, 7F0h
0x1800b091b  mov     rax, [rax+8]
0x1800b091f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0924  test    eax, eax
0x1800b0926  jz      short loc_1800B0931
0x1800b0928  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b092f  jmp     short loc_1800B093F
0x1800b0931  lea     rcx, qword_1801B07E0; this
0x1800b0938  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b093f  cmp     [rcx+8], r12b
0x1800b0943  jz      short loc_1800B0966
0x1800b0945  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b094a  cmp     [rax+7CCh], ebx
0x1800b0950  jz      short loc_1800B0966
0x1800b0952  mov     r9d, ebx; int
0x1800b0955  mov     r8d, 1DBh; int
0x1800b095b  mov     rdx, r14; char *
0x1800b095e  mov     rcx, rax; this
0x1800b0961  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b0966  mov     dil, 1
0x1800b0969  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800b0970  jb      loc_1800B13AD
0x1800b0976  mov     edx, 5Dh ; ']'
0x1800b097b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0982  mov     r9, rsi
0x1800b0985  mov     r8, r13
0x1800b0988  mov     [rsp+0C0h+var_A0], ebx
0x1800b098c  mov     rcx, [rcx+10h]
0x1800b0990  call    WPP_SF_qD
0x1800b0995  jmp     loc_1800B13AD
0x1800b099a  movaps  xmm0, [rbp+57h+Buf1]
0x1800b099e  lea     rcx, [rbp+57h+var_60]; this
0x1800b09a2  movdqa  [rbp+57h+var_60], xmm0
0x1800b09a7  call    ?IsKnownUncompressedVideoType@MFMEDIATYPEUtils@@YAHU_GUID@@@Z; MFMEDIATYPEUtils::IsKnownUncompressedVideoType(_GUID)
0x1800b09ac  test    eax, eax
0x1800b09ae  jnz     loc_1800B0A6D
0x1800b09b4  lea     r8d, [rax+10h]; Size
0x1800b09b8  lea     rdx, MFVideoFormat_MJPG; Buf2
0x1800b09bf  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800b09c3  call    memcmp_0
0x1800b09c8  test    eax, eax
0x1800b09ca  jz      loc_1800B0A6D
0x1800b09d0  call    ??$OriginateError@$0O@@MF@@YAJJAEAY0O@$$CBG@Z; MF::OriginateError<14>(long,ushort const (&)[14])
0x1800b09d5  mov     ebx, eax
0x1800b09d7  test    eax, eax
0x1800b09d9  jns     loc_1800B0A6D
0x1800b09df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b09e6  test    rcx, rcx
0x1800b09e9  jnz     short loc_1800B0A2C
0x1800b09eb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b09f1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b09f8  mov     rcx, rax
0x1800b09fb  test    rax, rax
0x1800b09fe  jz      short loc_1800B0A1E
0x1800b0a00  mov     rax, [rax]
0x1800b0a03  mov     edx, 7F0h
0x1800b0a08  mov     rax, [rax+8]
0x1800b0a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0a11  test    eax, eax
0x1800b0a13  jz      short loc_1800B0A1E
0x1800b0a15  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0a1c  jmp     short loc_1800B0A2C
0x1800b0a1e  lea     rcx, qword_1801B07E0; this
0x1800b0a25  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0a2c  cmp     [rcx+8], r12b
0x1800b0a30  jz      short loc_1800B0A53
0x1800b0a32  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b0a37  cmp     [rax+7CCh], ebx
0x1800b0a3d  jz      short loc_1800B0A53
0x1800b0a3f  mov     r9d, ebx; int
0x1800b0a42  mov     r8d, 1E0h; int
0x1800b0a48  mov     rdx, r14; char *
0x1800b0a4b  mov     rcx, rax; this
0x1800b0a4e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b0a53  mov     dil, 1
0x1800b0a56  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800b0a5d  jb      loc_1800B13AD
0x1800b0a63  mov     edx, 5Eh ; '^'
0x1800b0a68  jmp     loc_1800B097B
0x1800b0a6d  mov     rcx, [rsi+28h]
0x1800b0a71  mov     dil, 1
0x1800b0a74  test    rcx, rcx
0x1800b0a77  jz      loc_1800B0C06
0x1800b0a7d  xorps   xmm0, xmm0
0x1800b0a80  lea     r8, [rbp+57h+var_60]
0x1800b0a84  movups  [rbp+57h+var_60], xmm0
0x1800b0a88  mov     rax, [rcx]
0x1800b0a8b  lea     rdx, MF_MT_SUBTYPE
0x1800b0a92  mov     rax, [rax+50h]
0x1800b0a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0a9b  mov     ebx, eax
0x1800b0a9d  test    eax, eax
0x1800b0a9f  jns     loc_1800B0B30
0x1800b0aa5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0aac  test    rcx, rcx
0x1800b0aaf  jnz     short loc_1800B0AF2
0x1800b0ab1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b0ab7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0abe  mov     rcx, rax
0x1800b0ac1  test    rax, rax
0x1800b0ac4  jz      short loc_1800B0AE4
0x1800b0ac6  mov     rax, [rax]
0x1800b0ac9  mov     edx, 7F0h
0x1800b0ace  mov     rax, [rax+8]
0x1800b0ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0ad7  test    eax, eax
0x1800b0ad9  jz      short loc_1800B0AE4
0x1800b0adb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0ae2  jmp     short loc_1800B0AF2
0x1800b0ae4  lea     rcx, qword_1801B07E0; this
0x1800b0aeb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0af2  cmp     [rcx+8], r12b
0x1800b0af6  jz      short loc_1800B0B19
0x1800b0af8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b0afd  cmp     [rax+7CCh], ebx
0x1800b0b03  jz      short loc_1800B0B19
0x1800b0b05  mov     r9d, ebx; int
0x1800b0b08  mov     r8d, 1E6h; int
0x1800b0b0e  mov     rdx, r14; char *
0x1800b0b11  mov     rcx, rax; this
0x1800b0b14  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b0b19  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800b0b20  jb      loc_1800B13AD
0x1800b0b26  mov     edx, 5Fh ; '_'
0x1800b0b2b  jmp     loc_1800B097B
0x1800b0b30  mov     r8d, 10h; Size
0x1800b0b36  lea     rdx, [rbp+57h+Buf1]; Buf2
0x1800b0b3a  lea     rcx, [rbp+57h+var_60]; Buf1
0x1800b0b3e  call    memcmp_0
0x1800b0b43  test    eax, eax
0x1800b0b45  jz      loc_1800B0C06
0x1800b0b4b  cmp     cs:byte_1801B110A, dil
0x1800b0b52  jb      short loc_1800B0B6C
0x1800b0b54  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0b5b  mov     edx, 60h ; '`'
0x1800b0b60  mov     r8, r13
0x1800b0b63  mov     rcx, [rcx+60h]
0x1800b0b67  call    WPP_SF_
0x1800b0b6c  call    ??$OriginateError@$0O@@MF@@YAJJAEAY0O@$$CBG@Z; MF::OriginateError<14>(long,ushort const (&)[14])
0x1800b0b71  mov     ebx, eax
0x1800b0b73  test    eax, eax
0x1800b0b75  jns     loc_1800B0C06
0x1800b0b7b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0b82  test    rcx, rcx
0x1800b0b85  jnz     short loc_1800B0BC8
0x1800b0b87  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b0b8d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0b94  mov     rcx, rax
0x1800b0b97  test    rax, rax
0x1800b0b9a  jz      short loc_1800B0BBA
0x1800b0b9c  mov     rax, [rax]
0x1800b0b9f  mov     edx, 7F0h
0x1800b0ba4  mov     rax, [rax+8]
0x1800b0ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0bad  test    eax, eax
0x1800b0baf  jz      short loc_1800B0BBA
0x1800b0bb1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0bb8  jmp     short loc_1800B0BC8
0x1800b0bba  lea     rcx, qword_1801B07E0; this
0x1800b0bc1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0bc8  cmp     [rcx+8], r12b
0x1800b0bcc  jz      short loc_1800B0BEF
0x1800b0bce  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b0bd3  cmp     [rax+7CCh], ebx
0x1800b0bd9  jz      short loc_1800B0BEF
0x1800b0bdb  mov     r9d, ebx; int
0x1800b0bde  mov     r8d, 1EAh; int
0x1800b0be4  mov     rdx, r14; char *
0x1800b0be7  mov     rcx, rax; this
0x1800b0bea  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b0bef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800b0bf6  jb      loc_1800B13AD
0x1800b0bfc  mov     edx, 61h ; 'a'
0x1800b0c01  jmp     loc_1800B097B
0x1800b0c06  xor     r8d, r8d
0x1800b0c09  lea     rdx, MF_MT_INTERLACE_MODE
0x1800b0c10  mov     rcx, r15
0x1800b0c13  call    MFGetAttributeUINT32
0x1800b0c18  mov     r14d, eax
0x1800b0c1b  test    eax, 0FFFFFFFDh
0x1800b0c20  jz      loc_1800B0CE8
0x1800b0c26  cmp     cs:byte_1801B110A, dil
0x1800b0c2d  jb      short loc_1800B0C4A
0x1800b0c2f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0c36  mov     edx, 62h ; 'b'
0x1800b0c3b  mov     r9d, eax
0x1800b0c3e  mov     r8, r13
0x1800b0c41  mov     rcx, [rcx+60h]
0x1800b0c45  call    WPP_SF_d
0x1800b0c4a  call    ??$OriginateError@$0BF@@MF@@YAJJAEAY0BF@$$CBG@Z; MF::OriginateError<21>(long,ushort const (&)[21])
0x1800b0c4f  mov     ebx, eax
0x1800b0c51  test    eax, eax
0x1800b0c53  jns     loc_1800B0CE8
0x1800b0c59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0c60  test    rcx, rcx
0x1800b0c63  jnz     short loc_1800B0CA6
0x1800b0c65  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b0c6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0c72  mov     rcx, rax
0x1800b0c75  test    rax, rax
0x1800b0c78  jz      short loc_1800B0C98
0x1800b0c7a  mov     rax, [rax]
0x1800b0c7d  mov     edx, 7F0h
0x1800b0c82  mov     rax, [rax+8]
0x1800b0c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0c8b  test    eax, eax
0x1800b0c8d  jz      short loc_1800B0C98
0x1800b0c8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0c96  jmp     short loc_1800B0CA6
0x1800b0c98  lea     rcx, qword_1801B07E0; this
0x1800b0c9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0ca6  cmp     [rcx+8], r12b
0x1800b0caa  jz      short loc_1800B0CD1
0x1800b0cac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b0cb1  cmp     [rax+7CCh], ebx
0x1800b0cb7  jz      short loc_1800B0CD1
0x1800b0cb9  mov     r9d, ebx; int
0x1800b0cbc  lea     rdx, aCavistreamsink_6; "CAVIStreamSink::VerifyVideoMediaType"
0x1800b0cc3  mov     r8d, 1F4h; int
0x1800b0cc9  mov     rcx, rax; this
0x1800b0ccc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b0cd1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800b0cd8  jb      loc_1800B13AD
0x1800b0cde  mov     edx, 63h ; 'c'
0x1800b0ce3  jmp     loc_1800B097B
0x1800b0ce8  mov     rcx, [rsi+28h]
0x1800b0cec  test    rcx, rcx
0x1800b0cef  jz      loc_1800B0DD4
0x1800b0cf5  xor     r8d, r8d
0x1800b0cf8  lea     rdx, MF_MT_INTERLACE_MODE
0x1800b0cff  call    MFGetAttributeUINT32
0x1800b0d04  cmp     r14d, eax
0x1800b0d07  jz      loc_1800B0DD4
0x1800b0d0d  cmp     cs:byte_1801B110A, dil
0x1800b0d14  jb      short loc_1800B0D36
0x1800b0d16  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0d1d  mov     edx, 64h ; 'd'
0x1800b0d22  mov     r9d, eax
0x1800b0d25  mov     [rsp+0C0h+var_A0], r14d
0x1800b0d2a  mov     r8, r13
0x1800b0d2d  mov     rcx, [rcx+60h]
0x1800b0d31  call    WPP_SF_dd
0x1800b0d36  call    ??$OriginateError@$0BF@@MF@@YAJJAEAY0BF@$$CBG@Z; MF::OriginateError<21>(long,ushort const (&)[21])
0x1800b0d3b  mov     ebx, eax
0x1800b0d3d  test    eax, eax
0x1800b0d3f  jns     loc_1800B0DD4
0x1800b0d45  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0d4c  test    rcx, rcx
0x1800b0d4f  jnz     short loc_1800B0D92
0x1800b0d51  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b0d57  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0d5e  mov     rcx, rax
0x1800b0d61  test    rax, rax
0x1800b0d64  jz      short loc_1800B0D84
0x1800b0d66  mov     rax, [rax]
0x1800b0d69  mov     edx, 7F0h
0x1800b0d6e  mov     rax, [rax+8]
0x1800b0d72  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
