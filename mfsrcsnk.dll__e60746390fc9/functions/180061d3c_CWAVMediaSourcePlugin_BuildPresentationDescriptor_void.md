# CWAVMediaSourcePlugin::BuildPresentationDescriptor(void)

- ea: `0x180061d3c`
- end: `0x1800625fe`
- name: `?BuildPresentationDescriptor@CWAVMediaSourcePlugin@@AEAAJXZ`
- size: `2242`
- prototype: `__int64 __fastcall(CWAVMediaSourcePlugin *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800fdf40`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180047a00`
- `0x180061d3c`
- `0x180062604`
- `0x18006ac64`
- `0x180071a44`
- `0x180073b14`
- `0x18007450c`
- `0x1801099f0`
- `0x1801723d4`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061dcf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061e6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061f17`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061fce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062130`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800621d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062280`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006235f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006244c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062501`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061dcf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061e6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061f17`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061fce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062130`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800621d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062280`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006235f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006244c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062501`
- `MFPlat!MFCreatePresentationDescriptor` at `0x1800621bb`
- `MFPlat!MFCreatePresentationDescriptor` at `0x1800621bb`
- `MFPlat!MFCreateStreamDescriptor` at `0x180061efb`
- `MFPlat!MFCreateStreamDescriptor` at `0x180061efb`

## string_xrefs

- `0x180061d67`: `CWAVMediaSourcePlugin::BuildPresentationDescriptor`

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
        v6 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v12 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v16 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v20 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v26 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v30 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v34 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v41 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v45 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      v49 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x180061d3c  mov     [rsp-28h+arg_8], rbx
0x180061d41  mov     [rsp-28h+arg_10], rdi
0x180061d46  push    rbp
0x180061d47  push    r12
0x180061d49  push    r13
0x180061d4b  push    r14
0x180061d4d  push    r15
0x180061d4f  mov     rbp, rsp
0x180061d52  sub     rsp, 70h
0x180061d56  mov     rax, cs:__security_cookie
0x180061d5d  xor     rax, rsp
0x180061d60  mov     [rbp+var_10], rax
0x180061d64  mov     r14, rcx
0x180061d67  lea     r13, aCwavmediasourc_4; "CWAVMediaSourcePlugin::BuildPresentatio"...
0x180061d6e  mov     rdx, r13; char *
0x180061d71  lea     rcx, [rbp+var_40]; this
0x180061d75  mov     r8d, 16Ah; int
0x180061d7b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180061d80  xor     r12d, r12d
0x180061d83  lea     r15, [r14+30h]
0x180061d87  mov     rcx, [r15]
0x180061d8a  mov     [rbp+ppDescriptor], r12
0x180061d8e  mov     [rbp+apMediaTypes], r12
0x180061d92  mov     [rbp+var_30], r12d
0x180061d96  test    rcx, rcx
0x180061d99  jz      short loc_180061DAA
0x180061d9b  mov     rax, [rcx]
0x180061d9e  mov     rax, [rax+10h]
0x180061da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061da7  mov     [r15], r12
0x180061daa  mov     rax, [r14+38h]
0x180061dae  mov     rcx, [rax+1D8h]; this
0x180061db5  test    rcx, rcx
0x180061db8  jnz     loc_180061E4E
0x180061dbe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061dc5  mov     ebx, 0C00D36BEh
0x180061dca  test    rcx, rcx
0x180061dcd  jnz     short loc_180061E10
0x180061dcf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180061dd5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061ddc  mov     rcx, rax
0x180061ddf  test    rax, rax
0x180061de2  jz      short loc_180061E02
0x180061de4  mov     rax, [rax]
0x180061de7  mov     edx, 7F0h
0x180061dec  mov     rax, [rax+8]
0x180061df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061df5  test    eax, eax
0x180061df7  jz      short loc_180061E02
0x180061df9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061e00  jmp     short loc_180061E10
0x180061e02  lea     rcx, qword_1801B07E0; this
0x180061e09  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180061e10  cmp     [rcx+8], r12b
0x180061e14  jz      short loc_180061E37
0x180061e16  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061e1b  cmp     [rax+7CCh], ebx
0x180061e21  jz      short loc_180061E37
0x180061e23  mov     r9d, ebx; int
0x180061e26  mov     r8d, 175h; int
0x180061e2c  mov     rdx, r13; char *
0x180061e2f  mov     rcx, rax; this
0x180061e32  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180061e37  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061e3e  jb      loc_180062595
0x180061e44  mov     edx, 2Ah ; '*'
0x180061e49  jmp     loc_180062577
0x180061e4e  lea     rdx, [rbp+apMediaTypes]; struct IMFMediaType **
0x180061e52  call    ?GetFormat@CAudioStreamParser@@QEBAJPEAPEAUIMFMediaType@@@Z; CAudioStreamParser::GetFormat(IMFMediaType * *)
0x180061e57  mov     ebx, eax
0x180061e59  test    eax, eax
0x180061e5b  jns     loc_180061EEC
0x180061e61  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061e68  test    rcx, rcx
0x180061e6b  jnz     short loc_180061EAE
0x180061e6d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180061e73  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061e7a  mov     rcx, rax
0x180061e7d  test    rax, rax
0x180061e80  jz      short loc_180061EA0
0x180061e82  mov     rax, [rax]
0x180061e85  mov     edx, 7F0h
0x180061e8a  mov     rax, [rax+8]
0x180061e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061e93  test    eax, eax
0x180061e95  jz      short loc_180061EA0
0x180061e97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061e9e  jmp     short loc_180061EAE
0x180061ea0  lea     rcx, qword_1801B07E0; this
0x180061ea7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180061eae  cmp     [rcx+8], r12b
0x180061eb2  jz      short loc_180061ED5
0x180061eb4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061eb9  cmp     [rax+7CCh], ebx
0x180061ebf  jz      short loc_180061ED5
0x180061ec1  mov     r9d, ebx; int
0x180061ec4  mov     r8d, 17Ah; int
0x180061eca  mov     rdx, r13; char *
0x180061ecd  mov     rcx, rax; this
0x180061ed0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180061ed5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061edc  jb      loc_180062595
0x180061ee2  mov     edx, 2Bh ; '+'
0x180061ee7  jmp     loc_180062577
0x180061eec  mov     edx, 1; cMediaTypes
0x180061ef1  lea     r9, [rbp+ppDescriptor]; ppDescriptor
0x180061ef5  mov     ecx, edx; dwStreamIdentifier
0x180061ef7  lea     r8, [rbp+apMediaTypes]; apMediaTypes
0x180061efb  call    cs:__imp_MFCreateStreamDescriptor
0x180061f01  mov     ebx, eax
0x180061f03  test    eax, eax
0x180061f05  jns     loc_180061F96
0x180061f0b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061f12  test    rcx, rcx
0x180061f15  jnz     short loc_180061F58
0x180061f17  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180061f1d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061f24  mov     rcx, rax
0x180061f27  test    rax, rax
0x180061f2a  jz      short loc_180061F4A
0x180061f2c  mov     rax, [rax]
0x180061f2f  mov     edx, 7F0h
0x180061f34  mov     rax, [rax+8]
0x180061f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f3d  test    eax, eax
0x180061f3f  jz      short loc_180061F4A
0x180061f41  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061f48  jmp     short loc_180061F58
0x180061f4a  lea     rcx, qword_1801B07E0; this
0x180061f51  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180061f58  cmp     [rcx+8], r12b
0x180061f5c  jz      short loc_180061F7F
0x180061f5e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061f63  cmp     [rax+7CCh], ebx
0x180061f69  jz      short loc_180061F7F
0x180061f6b  mov     r9d, ebx; int
0x180061f6e  mov     r8d, 17Fh; int
0x180061f74  mov     rdx, r13; char *
0x180061f77  mov     rcx, rax; this
0x180061f7a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180061f7f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061f86  jb      loc_180062595
0x180061f8c  mov     edx, 2Ch ; ','
0x180061f91  jmp     loc_180062577
0x180061f96  mov     rcx, [rbp+apMediaTypes]
0x180061f9a  lea     r8, [rbp+Buf1]
0x180061f9e  xorps   xmm0, xmm0
0x180061fa1  lea     rdx, MF_MT_SUBTYPE
0x180061fa8  movups  [rbp+Buf1], xmm0
0x180061fac  mov     rax, [rcx]
0x180061faf  mov     rax, [rax+50h]
0x180061fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061fb8  mov     ebx, eax
0x180061fba  test    eax, eax
0x180061fbc  jns     loc_18006204D
0x180061fc2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061fc9  test    rcx, rcx
0x180061fcc  jnz     short loc_18006200F
0x180061fce  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180061fd4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061fdb  mov     rcx, rax
0x180061fde  test    rax, rax
0x180061fe1  jz      short loc_180062001
0x180061fe3  mov     rax, [rax]
0x180061fe6  mov     edx, 7F0h
0x180061feb  mov     rax, [rax+8]
0x180061fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061ff4  test    eax, eax
0x180061ff6  jz      short loc_180062001
0x180061ff8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061fff  jmp     short loc_18006200F
0x180062001  lea     rcx, qword_1801B07E0; this
0x180062008  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006200f  cmp     [rcx+8], r12b
0x180062013  jz      short loc_180062036
0x180062015  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006201a  cmp     [rax+7CCh], ebx
0x180062020  jz      short loc_180062036
0x180062022  mov     r9d, ebx; int
0x180062025  mov     r8d, 183h; int
0x18006202b  mov     rdx, r13; char *
0x18006202e  mov     rcx, rax; this
0x180062031  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180062036  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006203d  jb      loc_180062595
0x180062043  mov     edx, 2Dh ; '-'
0x180062048  jmp     loc_180062577
0x18006204d  mov     ebx, 10h
0x180062052  lea     rdx, MFAudioFormat_PCM; Buf2
0x180062059  mov     r8d, ebx; Size
0x18006205c  lea     rcx, [rbp+Buf1]; Buf1
0x180062060  call    memcmp_0
0x180062065  test    eax, eax
0x180062067  jz      short loc_180062084
0x180062069  mov     r8d, ebx; Size
0x18006206c  lea     rdx, MFAudioFormat_Float; Buf2
0x180062073  lea     rcx, [rbp+Buf1]; Buf1
0x180062077  call    memcmp_0
0x18006207c  test    eax, eax
0x18006207e  jnz     loc_1800621AF
0x180062084  mov     rcx, [rbp+ppDescriptor]
0x180062088  lea     rdx, MF_SD_AUDIO_ENCODER_DELAY
0x18006208f  xor     r8d, r8d
0x180062092  mov     rax, [rcx]
0x180062095  mov     rax, [rax+0A8h]
0x18006209c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800620a1  mov     ebx, eax
0x1800620a3  test    eax, eax
0x1800620a5  jns     short loc_1800620FD
0x1800620a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800620ae  test    rcx, rcx
0x1800620b1  jnz     short loc_1800620BF
0x1800620b3  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800620b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800620bf  cmp     [rcx+8], r12b
0x1800620c3  jz      short loc_1800620E6
0x1800620c5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800620ca  cmp     [rax+7CCh], ebx
0x1800620d0  jz      short loc_1800620E6
0x1800620d2  mov     r9d, ebx; int
0x1800620d5  mov     r8d, 186h; int
0x1800620db  mov     rdx, r13; char *
0x1800620de  mov     rcx, rax; this
0x1800620e1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800620e6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800620ed  jb      loc_180062595
0x1800620f3  mov     edx, 2Eh ; '.'
0x1800620f8  jmp     loc_180062577
0x1800620fd  mov     rcx, [rbp+ppDescriptor]
0x180062101  lea     rdx, MF_SD_AUDIO_ENCODER_PADDING
0x180062108  xor     r8d, r8d
0x18006210b  mov     rax, [rcx]
0x18006210e  mov     rax, [rax+0A8h]
0x180062115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006211a  mov     ebx, eax
0x18006211c  test    eax, eax
0x18006211e  jns     loc_1800621AF
0x180062124  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006212b  test    rcx, rcx
0x18006212e  jnz     short loc_180062171
0x180062130  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180062136  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006213d  mov     rcx, rax
0x180062140  test    rax, rax
0x180062143  jz      short loc_180062163
0x180062145  mov     rax, [rax]
0x180062148  mov     edx, 7F0h
0x18006214d  mov     rax, [rax+8]
0x180062151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062156  test    eax, eax
0x180062158  jz      short loc_180062163
0x18006215a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062161  jmp     short loc_180062171
0x180062163  lea     rcx, qword_1801B07E0; this
0x18006216a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180062171  cmp     [rcx+8], r12b
0x180062175  jz      short loc_180062198
0x180062177  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006217c  cmp     [rax+7CCh], ebx
0x180062182  jz      short loc_180062198
0x180062184  mov     r9d, ebx; int
0x180062187  mov     r8d, 187h; int
0x18006218d  mov     rdx, r13; char *
0x180062190  mov     rcx, rax; this
0x180062193  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180062198  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006219f  jb      loc_180062595
0x1800621a5  mov     edx, 2Fh ; '/'
0x1800621aa  jmp     loc_180062577
0x1800621af  mov     r8, r15; ppPresentationDescriptor
0x1800621b2  lea     rdx, [rbp+ppDescriptor]; apStreamDescriptors
0x1800621b6  mov     ecx, 1; cStreamDescriptors
0x1800621bb  call    cs:__imp_MFCreatePresentationDescriptor
0x1800621c1  mov     ebx, eax
0x1800621c3  test    eax, eax
0x1800621c5  jns     loc_180062256
0x1800621cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800621d2  test    rcx, rcx
0x1800621d5  jnz     short loc_180062218
0x1800621d7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800621dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800621e4  mov     rcx, rax
0x1800621e7  test    rax, rax
0x1800621ea  jz      short loc_18006220A
0x1800621ec  mov     rax, [rax]
0x1800621ef  mov     edx, 7F0h
0x1800621f4  mov     rax, [rax+8]
0x1800621f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800621fd  test    eax, eax
0x1800621ff  jz      short loc_18006220A
0x180062201  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062208  jmp     short loc_180062218
0x18006220a  lea     rcx, qword_1801B07E0; this
0x180062211  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180062218  cmp     [rcx+8], r12b
0x18006221c  jz      short loc_18006223F
0x18006221e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180062223  cmp     [rax+7CCh], ebx
0x180062229  jz      short loc_18006223F
0x18006222b  mov     r9d, ebx; int
  ... truncated ...
```
