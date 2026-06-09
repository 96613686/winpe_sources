# CWAVMediaSourcePlugin::BuildPresentationDescriptor(void)

- ea: `0x180062b28`
- end: `0x180063433`
- name: `?BuildPresentationDescriptor@CWAVMediaSourcePlugin@@AEAAJXZ`
- size: `2315`
- prototype: `__int64 __fastcall(CWAVMediaSourcePlugin *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180104f00`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x18004a8a8`
- `0x180062b28`
- `0x18006343c`
- `0x18006bb54`
- `0x180077708`
- `0x180079680`
- `0x180079f34`
- `0x180110ed0`
- `0x18017b734`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062bbb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062c5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062d15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062dd2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062f3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062fed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006309c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063181`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063274`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006332f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062bbb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062c5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062d15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062dd2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062f3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062fed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006309c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063181`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063274`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006332f`
- `MFPlat!MFCreatePresentationDescriptor` at `0x180062fcb`
- `MFPlat!MFCreatePresentationDescriptor` at `0x180062fcb`
- `MFPlat!MFCreateStreamDescriptor` at `0x180062cf3`
- `MFPlat!MFCreateStreamDescriptor` at `0x180062cf3`

## string_xrefs

- `0x180062b53`: `CWAVMediaSourcePlugin::BuildPresentationDescriptor`

## pseudocode

```c
__int64 __fastcall CWAVMediaSourcePlugin::BuildPresentationDescriptor(CWAVMediaSourcePlugin *this)
{
  __int64 v2; // rdx
  __int64 **v3; // r15
  __int64 v4; // rcx
  CAudioStreamParser *v5; // rcx
  wchar_t *v6; // rcx
  HRESULT Format; // ebx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rcx
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 *v37; // rdi
  __int64 v38; // rbx
  __int64 v39; // rax
  __int64 v40; // rdx
  wchar_t *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  _BYTE v53[8]; // [rsp+30h] [rbp-40h] BYREF
  IMFStreamDescriptor *ppDescriptor; // [rsp+38h] [rbp-38h] BYREF
  unsigned int v55; // [rsp+40h] [rbp-30h] BYREF
  IMFMediaType *apMediaTypes; // [rsp+48h] [rbp-28h] BYREF
  __int128 Buf1; // [rsp+50h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v53,
    "CWAVMediaSourcePlugin::BuildPresentationDescriptor",
    362);
  v3 = (__int64 **)((char *)this + 48);
  v4 = *((_QWORD *)this + 6);
  ppDescriptor = 0;
  apMediaTypes = 0;
  v55 = 0;
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *v3 = 0;
  }
  v5 = *(CAudioStreamParser **)(*((_QWORD *)this + 7) + 472LL);
  if ( !v5 )
  {
    v6 = (wchar_t *)CallStackTracing::s_wpInstance;
    Format = -1072875842;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875842 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWAVMediaSourcePlugin::BuildPresentationDescriptor",
          373,
          -1072875842);
    }
    if ( !g_wppLevels )
      goto LABEL_126;
    v10 = 42;
    goto LABEL_125;
  }
  Format = CAudioStreamParser::GetFormat(v5, &apMediaTypes);
  if ( Format < 0 )
  {
    v12 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v14 + 499) != Format )
        CallStackContext::TraceFailure(v14, "CWAVMediaSourcePlugin::BuildPresentationDescriptor", 378, Format);
    }
    if ( !g_wppLevels )
      goto LABEL_126;
    v10 = 43;
    goto LABEL_125;
  }
  Format = MFCreateStreamDescriptor(1u, 1u, &apMediaTypes, &ppDescriptor);
  if ( Format < 0 )
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
      if ( *((_DWORD *)v18 + 499) != Format )
        CallStackContext::TraceFailure(v18, "CWAVMediaSourcePlugin::BuildPresentationDescriptor", 383, Format);
    }
    if ( !g_wppLevels )
      goto LABEL_126;
    v10 = 44;
    goto LABEL_125;
  }
  Buf1 = 0;
  Format = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int128 *))apMediaTypes->lpVtbl->GetGUID)(
             apMediaTypes,
             &MF_MT_SUBTYPE,
             &Buf1);
  if ( Format < 0 )
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
      if ( *((_DWORD *)v22 + 499) != Format )
        CallStackContext::TraceFailure(v22, "CWAVMediaSourcePlugin::BuildPresentationDescriptor", 387, Format);
    }
    if ( !g_wppLevels )
      goto LABEL_126;
    v10 = 45;
    goto LABEL_125;
  }
  if ( !memcmp_0(&Buf1, &MFAudioFormat_PCM, 0x10u) || !memcmp_0(&Buf1, &MFAudioFormat_Float, 0x10u) )
  {
    Format = ((__int64 (__fastcall *)(IMFStreamDescriptor *, __int64 *, _QWORD))ppDescriptor->lpVtbl->SetUINT32)(
               ppDescriptor,
               MF_SD_AUDIO_ENCODER_DELAY,
               0);
    if ( Format < 0 )
    {
      v23 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v23 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v24 = CallStackTracing::GetThreadRelativeContext(v23);
        if ( *((_DWORD *)v24 + 499) != Format )
          CallStackContext::TraceFailure(v24, "CWAVMediaSourcePlugin::BuildPresentationDescriptor", 390, Format);
      }
      if ( !g_wppLevels )
        goto LABEL_126;
      v10 = 46;
      goto LABEL_125;
    }
    Format = ((__int64 (__fastcall *)(IMFStreamDescriptor *, __int64 *, _QWORD))ppDescriptor->lpVtbl->SetUINT32)(
               ppDescriptor,
               MF_SD_AUDIO_ENCODER_PADDING,
               0);
    if ( Format < 0 )
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
        if ( *((_DWORD *)v28 + 499) != Format )
          CallStackContext::TraceFailure(v28, "CWAVMediaSourcePlugin::BuildPresentationDescriptor", 391, Format);
      }
      if ( !g_wppLevels )
        goto LABEL_126;
      v10 = 47;
      goto LABEL_125;
    }
  }
  Format = MFCreatePresentationDescriptor(1u, &ppDescriptor, (IMFPresentationDescriptor **)this + 6);
  if ( Format < 0 )
  {
    v30 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
      CallStackTracing::s_wpInstance = v31;
      if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
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
      if ( *((_DWORD *)v32 + 499) != Format )
        CallStackContext::TraceFailure(v32, "CWAVMediaSourcePlugin::BuildPresentationDescriptor", 396, Format);
    }
    if ( !g_wppLevels )
      goto LABEL_126;
    v10 = 48;
    goto LABEL_125;
  }
  Format = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(**v3 + 280))(*v3, 0);
  if ( Format < 0 )
  {
    v34 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
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
      if ( *((_DWORD *)v36 + 499) != Format )
        CallStackContext::TraceFailure(v36, "CWAVMediaSourcePlugin::BuildPresentationDescriptor", 398, Format);
    }
    if ( !g_wppLevels )
      goto LABEL_126;
    v10 = 49;
    goto LABEL_125;
  }
  v37 = *v3;
  v38 = **v3;
  v39 = llMulDiv(
          *(_QWORD *)(*((_QWORD *)this + 7) + 488LL),
          10000000,
          *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 472LL) + 448LL) + 8LL) + 8LL),
          *((_QWORD *)this + 7));
  Format = (*(__int64 (__fastcall **)(__int64 *, const IID *, __int64))(v38 + 176))(v37, &MF_PD_DURATION, v39);
  if ( Format < 0 )
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
      if ( *((_DWORD *)v43 + 499) != Format )
        CallStackContext::TraceFailure(v43, "CWAVMediaSourcePlugin::BuildPresentationDescriptor", 399, Format);
    }
    if ( !g_wppLevels )
      goto LABEL_126;
    v10 = 50;
    goto LABEL_125;
  }
  if ( ((int (__fastcall *)(IMFMediaType *, const GUID *, unsigned int *))apMediaTypes->lpVtbl->GetUINT32)(
         apMediaTypes,
         &MF_MT_AUDIO_AVG_BYTES_PER_SECOND,
         &v55) >= 0
    && (int)ULongLongToULong(8LL * v55, &v55) >= 0 )
  {
    Format = (*(__int64 (__fastcall **)(__int64 *, const IID *, _QWORD))(**v3 + 168))(
               *v3,
               &MF_PD_AUDIO_ENCODING_BITRATE,
               v55);
    if ( Format < 0 )
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
        if ( *((_DWORD *)v47 + 499) != Format )
          CallStackContext::TraceFailure(v47, "CWAVMediaSourcePlugin::BuildPresentationDescriptor", 412, Format);
      }
      if ( !g_wppLevels )
        goto LABEL_126;
      v10 = 51;
      goto LABEL_125;
    }
  }
  Format = (*(__int64 (__fastcall **)(__int64 *, const IID *, const wchar_t *))(**v3 + 200))(
             *v3,
             &MF_PD_MIME_TYPE,
             L"audio/wav");
  if ( Format >= 0 )
    goto LABEL_127;
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
    if ( *((_DWORD *)v51 + 499) != Format )
      CallStackContext::TraceFailure(v51, "CWAVMediaSourcePlugin::BuildPresentationDescriptor", 416, Format);
  }
  if ( g_wppLevels )
  {
    v10 = 52;
LABEL_125:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_b9c73e557172350cc31d2d464215ca3e_Traceguids, this, Format);
  }
LABEL_126:
  ComSmartPtr<CMPEGFrame>::operator=((char *)this + 48, 0);
LABEL_127:
  if ( ppDescriptor )
  {
    ((void (__fastcall *)(IMFStreamDescriptor *))ppDescriptor->lpVtbl->Release)(ppDescriptor);
    ppDescriptor = 0;
  }
  if ( apMediaTypes )
    ((void (__fastcall *)(IMFMediaType *))apMediaTypes->lpVtbl->Release)(apMediaTypes);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v53);
  return (unsigned int)Format;
}

```

## disassembly

```asm
0x180062b28  mov     [rsp-28h+arg_8], rbx
0x180062b2d  mov     [rsp-28h+arg_10], rdi
0x180062b32  push    rbp
0x180062b33  push    r12
0x180062b35  push    r13
0x180062b37  push    r14
0x180062b39  push    r15
0x180062b3b  mov     rbp, rsp
0x180062b3e  sub     rsp, 70h
0x180062b42  mov     rax, cs:__security_cookie
0x180062b49  xor     rax, rsp
0x180062b4c  mov     [rbp+var_10], rax
0x180062b50  mov     r14, rcx
0x180062b53  lea     r13, aCwavmediasourc_4; "CWAVMediaSourcePlugin::BuildPresentatio"...
0x180062b5a  mov     rdx, r13; char *
0x180062b5d  lea     rcx, [rbp+var_40]; this
0x180062b61  mov     r8d, 16Ah; int
0x180062b67  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180062b6c  xor     r12d, r12d
0x180062b6f  lea     r15, [r14+30h]
0x180062b73  mov     rcx, [r15]
0x180062b76  mov     [rbp+ppDescriptor], r12
0x180062b7a  mov     [rbp+apMediaTypes], r12
0x180062b7e  mov     [rbp+var_30], r12d
0x180062b82  test    rcx, rcx
0x180062b85  jz      short loc_180062B96
0x180062b87  mov     rax, [rcx]
0x180062b8a  mov     rax, [rax+10h]
0x180062b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062b93  mov     [r15], r12
0x180062b96  mov     rax, [r14+38h]
0x180062b9a  mov     rcx, [rax+1D8h]; this
0x180062ba1  test    rcx, rcx
0x180062ba4  jnz     loc_180062C40
0x180062baa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062bb1  mov     ebx, 0C00D36BEh
0x180062bb6  test    rcx, rcx
0x180062bb9  jnz     short loc_180062C02
0x180062bbb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180062bc2  nop     dword ptr [rax+rax+00h]
0x180062bc7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180062bce  mov     rcx, rax
0x180062bd1  test    rax, rax
0x180062bd4  jz      short loc_180062BF4
0x180062bd6  mov     rax, [rax]
0x180062bd9  mov     edx, 7F0h
0x180062bde  mov     rax, [rax+8]
0x180062be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062be7  test    eax, eax
0x180062be9  jz      short loc_180062BF4
0x180062beb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062bf2  jmp     short loc_180062C02
0x180062bf4  lea     rcx, qword_1801B97E0; this
0x180062bfb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180062c02  cmp     [rcx+8], r12b
0x180062c06  jz      short loc_180062C29
0x180062c08  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180062c0d  cmp     [rax+7CCh], ebx
0x180062c13  jz      short loc_180062C29
0x180062c15  mov     r9d, ebx; int
0x180062c18  mov     r8d, 175h; int
0x180062c1e  mov     rdx, r13; char *
0x180062c21  mov     rcx, rax; this
0x180062c24  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180062c29  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062c30  jb      loc_1800633C9
0x180062c36  mov     edx, 2Ah ; '*'
0x180062c3b  jmp     loc_1800633AB
0x180062c40  lea     rdx, [rbp+apMediaTypes]; struct IMFMediaType **
0x180062c44  call    ?GetFormat@CAudioStreamParser@@QEBAJPEAPEAUIMFMediaType@@@Z; CAudioStreamParser::GetFormat(IMFMediaType * *)
0x180062c49  mov     ebx, eax
0x180062c4b  test    eax, eax
0x180062c4d  jns     loc_180062CE4
0x180062c53  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062c5a  test    rcx, rcx
0x180062c5d  jnz     short loc_180062CA6
0x180062c5f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180062c66  nop     dword ptr [rax+rax+00h]
0x180062c6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180062c72  mov     rcx, rax
0x180062c75  test    rax, rax
0x180062c78  jz      short loc_180062C98
0x180062c7a  mov     rax, [rax]
0x180062c7d  mov     edx, 7F0h
0x180062c82  mov     rax, [rax+8]
0x180062c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062c8b  test    eax, eax
0x180062c8d  jz      short loc_180062C98
0x180062c8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062c96  jmp     short loc_180062CA6
0x180062c98  lea     rcx, qword_1801B97E0; this
0x180062c9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180062ca6  cmp     [rcx+8], r12b
0x180062caa  jz      short loc_180062CCD
0x180062cac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180062cb1  cmp     [rax+7CCh], ebx
0x180062cb7  jz      short loc_180062CCD
0x180062cb9  mov     r9d, ebx; int
0x180062cbc  mov     r8d, 17Ah; int
0x180062cc2  mov     rdx, r13; char *
0x180062cc5  mov     rcx, rax; this
0x180062cc8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180062ccd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062cd4  jb      loc_1800633C9
0x180062cda  mov     edx, 2Bh ; '+'
0x180062cdf  jmp     loc_1800633AB
0x180062ce4  mov     edx, 1; cMediaTypes
0x180062ce9  lea     r9, [rbp+ppDescriptor]; ppDescriptor
0x180062ced  mov     ecx, edx; dwStreamIdentifier
0x180062cef  lea     r8, [rbp+apMediaTypes]; apMediaTypes
0x180062cf3  call    cs:__imp_MFCreateStreamDescriptor
0x180062cfa  nop     dword ptr [rax+rax+00h]
0x180062cff  mov     ebx, eax
0x180062d01  test    eax, eax
0x180062d03  jns     loc_180062D9A
0x180062d09  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062d10  test    rcx, rcx
0x180062d13  jnz     short loc_180062D5C
0x180062d15  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180062d1c  nop     dword ptr [rax+rax+00h]
0x180062d21  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180062d28  mov     rcx, rax
0x180062d2b  test    rax, rax
0x180062d2e  jz      short loc_180062D4E
0x180062d30  mov     rax, [rax]
0x180062d33  mov     edx, 7F0h
0x180062d38  mov     rax, [rax+8]
0x180062d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d41  test    eax, eax
0x180062d43  jz      short loc_180062D4E
0x180062d45  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062d4c  jmp     short loc_180062D5C
0x180062d4e  lea     rcx, qword_1801B97E0; this
0x180062d55  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180062d5c  cmp     [rcx+8], r12b
0x180062d60  jz      short loc_180062D83
0x180062d62  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180062d67  cmp     [rax+7CCh], ebx
0x180062d6d  jz      short loc_180062D83
0x180062d6f  mov     r9d, ebx; int
0x180062d72  mov     r8d, 17Fh; int
0x180062d78  mov     rdx, r13; char *
0x180062d7b  mov     rcx, rax; this
0x180062d7e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180062d83  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062d8a  jb      loc_1800633C9
0x180062d90  mov     edx, 2Ch ; ','
0x180062d95  jmp     loc_1800633AB
0x180062d9a  mov     rcx, [rbp+apMediaTypes]
0x180062d9e  lea     r8, [rbp+Buf1]
0x180062da2  xorps   xmm0, xmm0
0x180062da5  lea     rdx, MF_MT_SUBTYPE
0x180062dac  movups  [rbp+Buf1], xmm0
0x180062db0  mov     rax, [rcx]
0x180062db3  mov     rax, [rax+50h]
0x180062db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062dbc  mov     ebx, eax
0x180062dbe  test    eax, eax
0x180062dc0  jns     loc_180062E57
0x180062dc6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062dcd  test    rcx, rcx
0x180062dd0  jnz     short loc_180062E19
0x180062dd2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180062dd9  nop     dword ptr [rax+rax+00h]
0x180062dde  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180062de5  mov     rcx, rax
0x180062de8  test    rax, rax
0x180062deb  jz      short loc_180062E0B
0x180062ded  mov     rax, [rax]
0x180062df0  mov     edx, 7F0h
0x180062df5  mov     rax, [rax+8]
0x180062df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062dfe  test    eax, eax
0x180062e00  jz      short loc_180062E0B
0x180062e02  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062e09  jmp     short loc_180062E19
0x180062e0b  lea     rcx, qword_1801B97E0; this
0x180062e12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180062e19  cmp     [rcx+8], r12b
0x180062e1d  jz      short loc_180062E40
0x180062e1f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180062e24  cmp     [rax+7CCh], ebx
0x180062e2a  jz      short loc_180062E40
0x180062e2c  mov     r9d, ebx; int
0x180062e2f  mov     r8d, 183h; int
0x180062e35  mov     rdx, r13; char *
0x180062e38  mov     rcx, rax; this
0x180062e3b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180062e40  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062e47  jb      loc_1800633C9
0x180062e4d  mov     edx, 2Dh ; '-'
0x180062e52  jmp     loc_1800633AB
0x180062e57  mov     ebx, 10h
0x180062e5c  lea     rdx, MFAudioFormat_PCM; Buf2
0x180062e63  mov     r8d, ebx; Size
0x180062e66  lea     rcx, [rbp+Buf1]; Buf1
0x180062e6a  call    memcmp_0
0x180062e6f  test    eax, eax
0x180062e71  jz      short loc_180062E8E
0x180062e73  mov     r8d, ebx; Size
0x180062e76  lea     rdx, MFAudioFormat_Float; Buf2
0x180062e7d  lea     rcx, [rbp+Buf1]; Buf1
0x180062e81  call    memcmp_0
0x180062e86  test    eax, eax
0x180062e88  jnz     loc_180062FBF
0x180062e8e  mov     rcx, [rbp+ppDescriptor]
0x180062e92  lea     rdx, MF_SD_AUDIO_ENCODER_DELAY
0x180062e99  xor     r8d, r8d
0x180062e9c  mov     rax, [rcx]
0x180062e9f  mov     rax, [rax+0A8h]
0x180062ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062eab  mov     ebx, eax
0x180062ead  test    eax, eax
0x180062eaf  jns     short loc_180062F07
0x180062eb1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062eb8  test    rcx, rcx
0x180062ebb  jnz     short loc_180062EC9
0x180062ebd  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180062ec2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180062ec9  cmp     [rcx+8], r12b
0x180062ecd  jz      short loc_180062EF0
0x180062ecf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180062ed4  cmp     [rax+7CCh], ebx
0x180062eda  jz      short loc_180062EF0
0x180062edc  mov     r9d, ebx; int
0x180062edf  mov     r8d, 186h; int
0x180062ee5  mov     rdx, r13; char *
0x180062ee8  mov     rcx, rax; this
0x180062eeb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180062ef0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062ef7  jb      loc_1800633C9
0x180062efd  mov     edx, 2Eh ; '.'
0x180062f02  jmp     loc_1800633AB
0x180062f07  mov     rcx, [rbp+ppDescriptor]
0x180062f0b  lea     rdx, MF_SD_AUDIO_ENCODER_PADDING
0x180062f12  xor     r8d, r8d
0x180062f15  mov     rax, [rcx]
0x180062f18  mov     rax, [rax+0A8h]
0x180062f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062f24  mov     ebx, eax
0x180062f26  test    eax, eax
0x180062f28  jns     loc_180062FBF
0x180062f2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062f35  test    rcx, rcx
0x180062f38  jnz     short loc_180062F81
0x180062f3a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180062f41  nop     dword ptr [rax+rax+00h]
0x180062f46  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180062f4d  mov     rcx, rax
0x180062f50  test    rax, rax
0x180062f53  jz      short loc_180062F73
0x180062f55  mov     rax, [rax]
0x180062f58  mov     edx, 7F0h
0x180062f5d  mov     rax, [rax+8]
0x180062f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062f66  test    eax, eax
0x180062f68  jz      short loc_180062F73
0x180062f6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062f71  jmp     short loc_180062F81
0x180062f73  lea     rcx, qword_1801B97E0; this
0x180062f7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180062f81  cmp     [rcx+8], r12b
0x180062f85  jz      short loc_180062FA8
0x180062f87  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180062f8c  cmp     [rax+7CCh], ebx
0x180062f92  jz      short loc_180062FA8
0x180062f94  mov     r9d, ebx; int
0x180062f97  mov     r8d, 187h; int
0x180062f9d  mov     rdx, r13; char *
0x180062fa0  mov     rcx, rax; this
0x180062fa3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180062fa8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062faf  jb      loc_1800633C9
0x180062fb5  mov     edx, 2Fh ; '/'
0x180062fba  jmp     loc_1800633AB
0x180062fbf  mov     r8, r15; ppPresentationDescriptor
0x180062fc2  lea     rdx, [rbp+ppDescriptor]; apStreamDescriptors
0x180062fc6  mov     ecx, 1; cStreamDescriptors
0x180062fcb  call    cs:__imp_MFCreatePresentationDescriptor
0x180062fd2  nop     dword ptr [rax+rax+00h]
0x180062fd7  mov     ebx, eax
0x180062fd9  test    eax, eax
0x180062fdb  jns     loc_180063072
0x180062fe1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062fe8  test    rcx, rcx
0x180062feb  jnz     short loc_180063034
0x180062fed  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180062ff4  nop     dword ptr [rax+rax+00h]
0x180062ff9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180063000  mov     rcx, rax
0x180063003  test    rax, rax
0x180063006  jz      short loc_180063026
0x180063008  mov     rax, [rax]
0x18006300b  mov     edx, 7F0h
0x180063010  mov     rax, [rax+8]
0x180063014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063019  test    eax, eax
0x18006301b  jz      short loc_180063026
0x18006301d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180063024  jmp     short loc_180063034
  ... truncated ...
```
