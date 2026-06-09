# CMP3MediaSourcePlugin::CreatePresentationDescriptor(void)

- ea: `0x180056ebc`
- end: `0x180057723`
- name: `?CreatePresentationDescriptor@CMP3MediaSourcePlugin@@AEAAJXZ`
- size: `2151`
- prototype: `__int64 __fastcall(CMP3MediaSourcePlugin *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180053d00`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x18004f0d0`
- `0x180056ebc`
- `0x18006ac64`
- `0x180071a44`
- `0x180073b14`
- `0x1801099f0`
- `0x18011b1e4`
- `0x18014786c`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180056f42`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057238`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800572df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005738a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800574b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005758d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005763e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180056f42`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057238`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800572df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005738a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800574b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005758d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005763e`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x18005721c`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x18005721c`
- `MFPlat!MFCreatePresentationDescriptor` at `0x18005736e`
- `MFPlat!MFCreatePresentationDescriptor` at `0x18005736e`
- `MFPlat!MFCreateStreamDescriptor` at `0x1800572c3`
- `MFPlat!MFCreateStreamDescriptor` at `0x1800572c3`
- `MFPlat!MFCreateMediaType` at `0x1800571ac`
- `MFPlat!MFCreateMediaType` at `0x1800571ac`

## string_xrefs

- `0x180056ee6`: `CMP3MediaSourcePlugin::CreatePresentationDescriptor`

## pseudocode

```c
__int64 __fastcall CMP3MediaSourcePlugin::CreatePresentationDescriptor(CMP3MediaSourcePlugin *this)
{
  __int64 v2; // rdx
  wchar_t *v3; // rcx
  HRESULT v4; // ebx
  CallStackTracing *v5; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v7; // rdx
  __int64 v8; // rax
  char *v9; // rcx
  __int64 v10; // r9
  DWORD nAvgBytesPerSec; // r8d
  __int64 v12; // rcx
  __int64 v13; // rax
  DWORD v14; // eax
  __int64 v15; // rdx
  unsigned int *v16; // rcx
  __int64 v17; // rax
  unsigned int v18; // r10d
  unsigned int v19; // edx
  _DWORD *v20; // rax
  WORD v21; // cx
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  _QWORD *v32; // r15
  __int64 v33; // rdx
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  CallStackTracing *v37; // rcx
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
  _BYTE v52[8]; // [rsp+40h] [rbp-29h] BYREF
  WAVEFORMATEX pWaveFormat; // [rsp+48h] [rbp-21h] BYREF
  IMFMediaType *ppMFType; // [rsp+60h] [rbp-9h] BYREF
  IMFStreamDescriptor *ppDescriptor; // [rsp+68h] [rbp-1h] BYREF

  ppDescriptor = 0;
  ppMFType = 0;
  memset(&pWaveFormat, 0, sizeof(pWaveFormat));
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v52,
    "CMP3MediaSourcePlugin::CreatePresentationDescriptor",
    2397);
  memset(&pWaveFormat, 0, sizeof(pWaveFormat));
  if ( !*((_QWORD *)this + 105) )
  {
    v3 = (wchar_t *)CallStackTracing::s_wpInstance;
    v4 = -1072875842;
    if ( !CallStackTracing::s_wpInstance )
    {
      v5 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2);
      CallStackTracing::s_wpInstance = v5;
      if ( v5 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v5 + 8LL))(v5, 2032) )
      {
        v3 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v3 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v3 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v3);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875842 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMP3MediaSourcePlugin::CreatePresentationDescriptor",
          2406,
          -1072875842);
    }
    if ( g_wppLevels )
    {
      v7 = 238;
LABEL_126:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_d883d89413f235918ed5b1c680996b82_Traceguids, this, v4);
      goto LABEL_127;
    }
    goto LABEL_127;
  }
  v8 = *((_QWORD *)this + 106);
  if ( *(_DWORD *)(v8 + 164) )
  {
    if ( (unsigned __int8)byte_1801B110B >= 4u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 239, &WPP_d883d89413f235918ed5b1c680996b82_Traceguids, this);
    v9 = (char *)this + 856;
  }
  else
  {
    if ( !*(_DWORD *)(v8 + 296) )
      goto LABEL_19;
    v9 = (char *)this + 864;
  }
  ComSmartPtr<CMPEGFrame>::operator=(v9, (char *)this + 848);
LABEL_19:
  v10 = *((unsigned int *)this + 343);
  if ( (_DWORD)v10 )
  {
    nAvgBytesPerSec = (*((_DWORD *)this + 346) / (unsigned int)v10) >> 3;
    pWaveFormat.nAvgBytesPerSec = nAvgBytesPerSec;
  }
  else
  {
    nAvgBytesPerSec = pWaveFormat.nAvgBytesPerSec;
  }
  v12 = *((_QWORD *)this + 107);
  if ( v12 )
  {
    if ( (*(_BYTE *)(v12 + 172) & 3) == 3 )
    {
      v13 = *(unsigned int *)(v12 + 152);
      if ( (_DWORD)v13 )
      {
        v14 = llMulDiv(
                *(unsigned int *)(v12 + 176),
                *(unsigned int *)(v12 + 148),
                v13 * *(unsigned int *)(v12 + 168),
                v10);
        pWaveFormat.nAvgBytesPerSec = v14;
        if ( (unsigned __int8)byte_1801B110B < 0x20u )
          goto LABEL_36;
        v15 = 240;
LABEL_33:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          v15,
          &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
          this,
          8 * v14);
        goto LABEL_36;
      }
    }
  }
  v16 = (unsigned int *)*((_QWORD *)this + 108);
  if ( v16 )
  {
    v17 = v16[78];
    if ( (_DWORD)v17 )
    {
      v18 = v16[77];
      if ( v18 )
      {
        v19 = v16[38];
        if ( v19 )
        {
          v14 = llMulDiv(v18, v16[37], v17 * v19, v10);
          pWaveFormat.nAvgBytesPerSec = v14;
          if ( (unsigned __int8)byte_1801B110B < 0x20u )
            goto LABEL_36;
          v15 = 241;
          goto LABEL_33;
        }
      }
    }
  }
  if ( (unsigned __int8)byte_1801B110B >= 0x20u )
    WPP_SF_qddd(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      242,
      &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
      this,
      *((_DWORD *)this + 346),
      v10,
      8 * nAvgBytesPerSec);
LABEL_36:
  v20 = (_DWORD *)*((_QWORD *)this + 105);
  v21 = 85;
  if ( v20[35] != 3 )
    v21 = 80;
  pWaveFormat.wFormatTag = v21;
  pWaveFormat.nBlockAlign = 1;
  if ( v20[23] == 3 )
    pWaveFormat.nChannels = 1;
  else
    pWaveFormat.nChannels = 2;
  pWaveFormat.nSamplesPerSec = v20[37];
  v4 = MFCreateMediaType(&ppMFType);
  if ( v4 >= 0 )
  {
    v4 = MFInitMediaTypeFromWaveFormatEx(ppMFType, &pWaveFormat, 0x12u);
    if ( v4 >= 0 )
    {
      v4 = MFCreateStreamDescriptor(0, 1u, &ppMFType, &ppDescriptor);
      if ( v4 >= 0 )
      {
        v32 = (_QWORD *)((char *)this + 184);
        v4 = MFCreatePresentationDescriptor(1u, &ppDescriptor, (IMFPresentationDescriptor **)this + 23);
        if ( v4 >= 0 )
        {
          v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v32 + 280LL))(*v32, 0);
          if ( v4 >= 0 )
          {
            v4 = (*(__int64 (__fastcall **)(_QWORD, const IID *, _QWORD))(*(_QWORD *)*v32 + 168LL))(
                   *v32,
                   &MF_PD_AUDIO_ENCODING_BITRATE,
                   8 * pWaveFormat.nAvgBytesPerSec);
            if ( v4 >= 0 )
            {
              if ( *((_QWORD *)this + 107)
                || *((_QWORD *)this + 108)
                || *((_DWORD *)this + 344) != *((_DWORD *)this + 345) )
              {
                v4 = (*(__int64 (__fastcall **)(_QWORD, const IID *, __int64))(*(_QWORD *)*v32 + 168LL))(
                       *v32,
                       &MF_PD_AUDIO_ISVARIABLEBITRATE,
                       1);
                if ( v4 < 0 )
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
                    if ( *((_DWORD *)v50 + 499) != v4 )
                      CallStackContext::TraceFailure(
                        v50,
                        "CMP3MediaSourcePlugin::CreatePresentationDescriptor",
                        2513,
                        v4);
                  }
                  if ( g_wppLevels )
                  {
                    v7 = 249;
                    goto LABEL_126;
                  }
                }
              }
              else
              {
                v4 = (*(__int64 (__fastcall **)(_QWORD, const IID *, _QWORD))(*(_QWORD *)*v32 + 168LL))(
                       *v32,
                       &MF_PD_AUDIO_ISVARIABLEBITRATE,
                       0);
                if ( v4 < 0 )
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
                    if ( *((_DWORD *)v46 + 499) != v4 )
                      CallStackContext::TraceFailure(
                        v46,
                        "CMP3MediaSourcePlugin::CreatePresentationDescriptor",
                        2518,
                        v4);
                  }
                  if ( g_wppLevels )
                  {
                    v7 = 250;
                    goto LABEL_126;
                  }
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
                if ( *((_DWORD *)v42 + 499) != v4 )
                  CallStackContext::TraceFailure(v42, "CMP3MediaSourcePlugin::CreatePresentationDescriptor", 2503, v4);
              }
              if ( g_wppLevels )
              {
                v7 = 248;
                goto LABEL_126;
              }
            }
          }
          else
          {
            v37 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v37 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v37 + 8) )
            {
              v38 = CallStackTracing::GetThreadRelativeContext(v37);
              if ( *((_DWORD *)v38 + 499) != v4 )
                CallStackContext::TraceFailure(v38, "CMP3MediaSourcePlugin::CreatePresentationDescriptor", 2496, v4);
            }
            if ( g_wppLevels )
            {
              v7 = 247;
              goto LABEL_126;
            }
          }
        }
        else
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
            if ( *((_DWORD *)v36 + 499) != v4 )
              CallStackContext::TraceFailure(v36, "CMP3MediaSourcePlugin::CreatePresentationDescriptor", 2494, v4);
          }
          if ( g_wppLevels )
          {
            v7 = 246;
            goto LABEL_126;
          }
        }
      }
      else
      {
        v29 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
          CallStackTracing::s_wpInstance = v30;
          if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
          {
            v29 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v29 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v29 + 8) )
        {
          v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
          if ( *((_DWORD *)v31 + 499) != v4 )
            CallStackContext::TraceFailure(v31, "CMP3MediaSourcePlugin::CreatePresentationDescriptor", 2491, v4);
        }
        if ( g_wppLevels )
        {
          v7 = 245;
          goto LABEL_126;
        }
      }
    }
    else
    {
      v25 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
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
        if ( *((_DWORD *)v27 + 499) != v4 )
          CallStackContext::TraceFailure(v27, "CMP3MediaSourcePlugin::CreatePresentationDescriptor", 2489, v4);
      }
      if ( g_wppLevels )
      {
        v7 = 244;
        goto LABEL_126;
      }
    }
  }
  else
  {
    v22 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v22 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v22 + 8) )
    {
      v23 = CallStackTracing::GetThreadRelativeContext(v22);
      if ( *((_DWORD *)v23 + 499) != v4 )
        CallStackContext::TraceFailure(v23, "CMP3MediaSourcePlugin::CreatePresentationDescriptor", 2488, v4);
    }
    if ( g_wppLevels )
    {
      v7 = 243;
      goto LABEL_126;
    }
  }
LABEL_127:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v52);
  if ( ppMFType )
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
  if ( ppDescriptor )
    ((void (__fastcall *)(IMFStreamDescriptor *))ppDescriptor->lpVtbl->Release)(ppDescriptor);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180056ebc  push    rbp
0x180056ebe  push    rbx
0x180056ebf  push    rsi
0x180056ec0  push    rdi
0x180056ec1  push    r12
0x180056ec3  push    r13
0x180056ec5  push    r14
0x180056ec7  push    r15
0x180056ec9  lea     rbp, [rsp-1Fh]
0x180056ece  sub     rsp, 88h
0x180056ed5  mov     rax, cs:__security_cookie
0x180056edc  xor     rax, rsp
0x180056edf  mov     [rbp+57h+var_50], rax
0x180056ee3  mov     rdi, rcx
0x180056ee6  lea     r13, aCmp3mediasourc_21; "CMP3MediaSourcePlugin::CreatePresentati"...
0x180056eed  xor     r12d, r12d
0x180056ef0  lea     rcx, [rbp+57h+var_80]; this
0x180056ef4  xorps   xmm0, xmm0
0x180056ef7  mov     [rbp+57h+ppDescriptor], r12
0x180056efb  xor     eax, eax
0x180056efd  mov     [rbp+57h+ppMFType], r12
0x180056f01  mov     rdx, r13; char *
0x180056f04  mov     [rbp+57h+pWaveFormat.cbSize], ax
0x180056f08  mov     r8d, 95Dh; int
0x180056f0e  movups  xmmword ptr [rbp+57h+pWaveFormat.wFormatTag], xmm0
0x180056f12  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180056f17  xor     eax, eax
0x180056f19  xorps   xmm0, xmm0
0x180056f1c  movups  xmmword ptr [rbp+57h+pWaveFormat.wFormatTag], xmm0
0x180056f20  mov     [rbp+57h+pWaveFormat.cbSize], ax
0x180056f24  cmp     [rdi+348h], r12
0x180056f2b  jnz     loc_180056FCD
0x180056f31  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180056f38  mov     ebx, 0C00D36BEh
0x180056f3d  test    rcx, rcx
0x180056f40  jnz     short loc_180056F83
0x180056f42  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180056f48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180056f4f  mov     rcx, rax
0x180056f52  test    rax, rax
0x180056f55  jz      short loc_180056F75
0x180056f57  mov     rax, [rax]
0x180056f5a  mov     edx, 7F0h
0x180056f5f  mov     rax, [rax+8]
0x180056f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056f68  test    eax, eax
0x180056f6a  jz      short loc_180056F75
0x180056f6c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180056f73  jmp     short loc_180056F83
0x180056f75  lea     rcx, qword_1801B07E0; this
0x180056f7c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180056f83  cmp     [rcx+8], r12b
0x180056f87  jz      short loc_180056FAA
0x180056f89  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180056f8e  cmp     [rax+7CCh], ebx
0x180056f94  jz      short loc_180056FAA
0x180056f96  mov     r9d, ebx; int
0x180056f99  mov     r8d, 966h; int
0x180056f9f  mov     rdx, r13; char *
0x180056fa2  mov     rcx, rax; this
0x180056fa5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180056faa  mov     esi, 1
0x180056faf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180056fb6  jb      loc_1800576CE
0x180056fbc  mov     edx, 0EEh
0x180056fc1  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x180056fc8  jmp     loc_1800576B7
0x180056fcd  lea     rbx, [rdi+350h]
0x180056fd4  mov     rax, [rbx]
0x180056fd7  lea     r14, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x180056fde  cmp     [rax+0A4h], r12d
0x180056fe5  jz      short loc_180057017
0x180056fe7  cmp     cs:byte_1801B110B, 4
0x180056fee  jb      short loc_18005700E
0x180056ff0  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ff7  mov     edx, 0EFh
0x180056ffc  mov     r9, rdi
0x180056fff  mov     r8, r14
0x180057002  mov     rcx, [rcx+88h]
0x180057009  call    WPP_SF_q
0x18005700e  lea     rcx, [rdi+358h]
0x180057015  jmp     short loc_180057027
0x180057017  cmp     [rax+128h], r12d
0x18005701e  jz      short loc_18005702F
0x180057020  lea     rcx, [rdi+360h]
0x180057027  mov     rdx, rbx
0x18005702a  call    ??4?$ComSmartPtr@VCMPEGFrame@@@@QEAAPEAVCMPEGFrame@@AEBV0@@Z; ComSmartPtr<CMPEGFrame>::operator=(ComSmartPtr<CMPEGFrame> const &)
0x18005702f  mov     r9d, [rdi+55Ch]; __int64
0x180057036  test    r9d, r9d
0x180057039  jz      short loc_180057053
0x18005703b  mov     eax, [rdi+568h]
0x180057041  xor     edx, edx
0x180057043  div     r9d
0x180057046  mov     r8d, eax
0x180057049  shr     r8d, 3
0x18005704d  mov     [rbp+57h+pWaveFormat.nAvgBytesPerSec], r8d
0x180057051  jmp     short loc_180057057
0x180057053  mov     r8d, [rbp+57h+pWaveFormat.nAvgBytesPerSec]
0x180057057  mov     rcx, [rdi+358h]
0x18005705e  test    rcx, rcx
0x180057061  jz      short loc_1800570AD
0x180057063  mov     eax, [rcx+0ACh]
0x180057069  and     eax, 3
0x18005706c  cmp     al, 3
0x18005706e  jnz     short loc_1800570AD
0x180057070  mov     eax, [rcx+98h]
0x180057076  test    eax, eax
0x180057078  jz      short loc_1800570AD
0x18005707a  mov     r8d, [rcx+0A8h]
0x180057081  mov     edx, [rcx+94h]; __int64
0x180057087  mov     ecx, [rcx+0B0h]; __int64
0x18005708d  imul    r8, rax; __int64
0x180057091  call    ?llMulDiv@@YA_J_J000@Z; llMulDiv(__int64,__int64,__int64,__int64)
0x180057096  mov     [rbp+57h+pWaveFormat.nAvgBytesPerSec], eax
0x180057099  cmp     cs:byte_1801B110B, 20h ; ' '
0x1800570a0  jb      loc_180057163
0x1800570a6  mov     edx, 0F0h
0x1800570ab  jmp     short loc_1800570FF
0x1800570ad  mov     rcx, [rdi+360h]
0x1800570b4  test    rcx, rcx
0x1800570b7  jz      short loc_180057121
0x1800570b9  mov     eax, [rcx+138h]
0x1800570bf  test    eax, eax
0x1800570c1  jz      short loc_180057121
0x1800570c3  mov     r10d, [rcx+134h]
0x1800570ca  test    r10d, r10d
0x1800570cd  jz      short loc_180057121
0x1800570cf  mov     edx, [rcx+98h]
0x1800570d5  test    edx, edx
0x1800570d7  jz      short loc_180057121
0x1800570d9  mov     r8d, edx
0x1800570dc  mov     edx, [rcx+94h]; __int64
0x1800570e2  imul    r8, rax; __int64
0x1800570e6  mov     ecx, r10d; __int64
0x1800570e9  call    ?llMulDiv@@YA_J_J000@Z; llMulDiv(__int64,__int64,__int64,__int64)
0x1800570ee  mov     [rbp+57h+pWaveFormat.nAvgBytesPerSec], eax
0x1800570f1  cmp     cs:byte_1801B110B, 20h ; ' '
0x1800570f8  jb      short loc_180057163
0x1800570fa  mov     edx, 0F1h
0x1800570ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180057106  mov     r9, rdi
0x180057109  shl     eax, 3
0x18005710c  mov     r8, r14
0x18005710f  mov     [rsp+0C0h+var_A0], eax
0x180057113  mov     rcx, [rcx+88h]
0x18005711a  call    WPP_SF_qD
0x18005711f  jmp     short loc_180057163
0x180057121  cmp     cs:byte_1801B110B, 20h ; ' '
0x180057128  jb      short loc_180057163
0x18005712a  mov     rcx, cs:WPP_GLOBAL_Control
0x180057131  lea     eax, ds:0[r8*8]
0x180057139  mov     [rsp+0C0h+var_90], eax
0x18005713d  mov     edx, 0F2h
0x180057142  mov     eax, [rdi+568h]
0x180057148  mov     r8, r14
0x18005714b  mov     [rsp+0C0h+var_98], r9d
0x180057150  mov     r9, rdi
0x180057153  mov     rcx, [rcx+88h]
0x18005715a  mov     [rsp+0C0h+var_A0], eax
0x18005715e  call    WPP_SF_qddd
0x180057163  mov     rax, [rdi+348h]
0x18005716a  mov     ecx, 55h ; 'U'
0x18005716f  cmp     dword ptr [rax+8Ch], 3
0x180057176  jz      short loc_18005717D
0x180057178  mov     ecx, 50h ; 'P'
0x18005717d  mov     esi, 1
0x180057182  mov     [rbp+57h+pWaveFormat.wFormatTag], cx
0x180057186  mov     [rbp+57h+pWaveFormat.nBlockAlign], si
0x18005718a  cmp     dword ptr [rax+5Ch], 3
0x18005718e  jnz     short loc_180057196
0x180057190  mov     [rbp+57h+pWaveFormat.nChannels], si
0x180057194  jmp     short loc_18005719F
0x180057196  mov     ecx, 2
0x18005719b  mov     [rbp+57h+pWaveFormat.nChannels], cx
0x18005719f  mov     eax, [rax+94h]
0x1800571a5  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x1800571a9  mov     [rbp+57h+pWaveFormat.nSamplesPerSec], eax
0x1800571ac  call    cs:__imp_MFCreateMediaType
0x1800571b2  mov     ebx, eax
0x1800571b4  test    eax, eax
0x1800571b6  jns     short loc_18005720E
0x1800571b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800571bf  test    rcx, rcx
0x1800571c2  jnz     short loc_1800571D0
0x1800571c4  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800571c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800571d0  cmp     [rcx+8], r12b
0x1800571d4  jz      short loc_1800571F7
0x1800571d6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800571db  cmp     [rax+7CCh], ebx
0x1800571e1  jz      short loc_1800571F7
0x1800571e3  mov     r9d, ebx; int
0x1800571e6  mov     r8d, 9B8h; int
0x1800571ec  mov     rdx, r13; char *
0x1800571ef  mov     rcx, rax; this
0x1800571f2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800571f7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800571fe  jb      loc_1800576CE
0x180057204  mov     edx, 0F3h
0x180057209  jmp     loc_1800576B4
0x18005720e  mov     rcx, [rbp+57h+ppMFType]; pMFType
0x180057212  lea     rdx, [rbp+57h+pWaveFormat]; pWaveFormat
0x180057216  mov     r8d, 12h; cbBufSize
0x18005721c  call    cs:__imp_MFInitMediaTypeFromWaveFormatEx
0x180057222  mov     ebx, eax
0x180057224  test    eax, eax
0x180057226  jns     loc_1800572B7
0x18005722c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057233  test    rcx, rcx
0x180057236  jnz     short loc_180057279
0x180057238  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005723e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180057245  mov     rcx, rax
0x180057248  test    rax, rax
0x18005724b  jz      short loc_18005726B
0x18005724d  mov     rax, [rax]
0x180057250  mov     edx, 7F0h
0x180057255  mov     rax, [rax+8]
0x180057259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005725e  test    eax, eax
0x180057260  jz      short loc_18005726B
0x180057262  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057269  jmp     short loc_180057279
0x18005726b  lea     rcx, qword_1801B07E0; this
0x180057272  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180057279  cmp     [rcx+8], r12b
0x18005727d  jz      short loc_1800572A0
0x18005727f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180057284  cmp     [rax+7CCh], ebx
0x18005728a  jz      short loc_1800572A0
0x18005728c  mov     r9d, ebx; int
0x18005728f  mov     r8d, 9B9h; int
0x180057295  mov     rdx, r13; char *
0x180057298  mov     rcx, rax; this
0x18005729b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800572a0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800572a7  jb      loc_1800576CE
0x1800572ad  mov     edx, 0F4h
0x1800572b2  jmp     loc_1800576B4
0x1800572b7  lea     r9, [rbp+57h+ppDescriptor]; ppDescriptor
0x1800572bb  mov     edx, esi; cMediaTypes
0x1800572bd  lea     r8, [rbp+57h+ppMFType]; apMediaTypes
0x1800572c1  xor     ecx, ecx; dwStreamIdentifier
0x1800572c3  call    cs:__imp_MFCreateStreamDescriptor
0x1800572c9  mov     ebx, eax
0x1800572cb  test    eax, eax
0x1800572cd  jns     loc_18005735E
0x1800572d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800572da  test    rcx, rcx
0x1800572dd  jnz     short loc_180057320
0x1800572df  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800572e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800572ec  mov     rcx, rax
0x1800572ef  test    rax, rax
0x1800572f2  jz      short loc_180057312
0x1800572f4  mov     rax, [rax]
0x1800572f7  mov     edx, 7F0h
0x1800572fc  mov     rax, [rax+8]
0x180057300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057305  test    eax, eax
0x180057307  jz      short loc_180057312
0x180057309  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057310  jmp     short loc_180057320
0x180057312  lea     rcx, qword_1801B07E0; this
0x180057319  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180057320  cmp     [rcx+8], r12b
0x180057324  jz      short loc_180057347
0x180057326  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005732b  cmp     [rax+7CCh], ebx
0x180057331  jz      short loc_180057347
0x180057333  mov     r9d, ebx; int
0x180057336  mov     r8d, 9BBh; int
0x18005733c  mov     rdx, r13; char *
0x18005733f  mov     rcx, rax; this
0x180057342  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180057347  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18005734e  jb      loc_1800576CE
0x180057354  mov     edx, 0F5h
0x180057359  jmp     loc_1800576B4
0x18005735e  lea     r15, [rdi+0B8h]
0x180057365  mov     ecx, esi; cStreamDescriptors
0x180057367  mov     r8, r15; ppPresentationDescriptor
0x18005736a  lea     rdx, [rbp+57h+ppDescriptor]; apStreamDescriptors
0x18005736e  call    cs:__imp_MFCreatePresentationDescriptor
0x180057374  mov     ebx, eax
0x180057376  test    eax, eax
0x180057378  jns     loc_180057409
0x18005737e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057385  test    rcx, rcx
0x180057388  jnz     short loc_1800573CB
0x18005738a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180057390  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180057397  mov     rcx, rax
0x18005739a  test    rax, rax
0x18005739d  jz      short loc_1800573BD
0x18005739f  mov     rax, [rax]
0x1800573a2  mov     edx, 7F0h
0x1800573a7  mov     rax, [rax+8]
0x1800573ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800573b0  test    eax, eax
  ... truncated ...
```
