# CMP3MediaSourcePlugin::CreatePresentationDescriptor(void)

- ea: `0x18005a29c`
- end: `0x18005ab46`
- name: `?CreatePresentationDescriptor@CMP3MediaSourcePlugin@@AEAAJXZ`
- size: `2218`
- prototype: `__int64 __fastcall(CMP3MediaSourcePlugin *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180056ea0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180053f24`
- `0x18005a29c`
- `0x18006bb54`
- `0x180077708`
- `0x180079680`
- `0x180110ed0`
- `0x180121750`
- `0x18014f9b4`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a322`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a62a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a6dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a794`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a8c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a9a3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005aa5a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a322`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a62a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a6dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a794`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a8c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005a9a3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005aa5a`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x18005a608`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x18005a608`
- `MFPlat!MFCreatePresentationDescriptor` at `0x18005a772`
- `MFPlat!MFCreatePresentationDescriptor` at `0x18005a772`
- `MFPlat!MFCreateStreamDescriptor` at `0x18005a6bb`
- `MFPlat!MFCreateStreamDescriptor` at `0x18005a6bb`
- `MFPlat!MFCreateMediaType` at `0x18005a592`
- `MFPlat!MFCreateMediaType` at `0x18005a592`

## string_xrefs

- `0x18005a2c6`: `CMP3MediaSourcePlugin::CreatePresentationDescriptor`

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
        v3 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
    if ( (unsigned __int8)byte_1801BA10B >= 4u )
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
        if ( (unsigned __int8)byte_1801BA10B < 0x20u )
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
          if ( (unsigned __int8)byte_1801BA10B < 0x20u )
            goto LABEL_36;
          v15 = 241;
          goto LABEL_33;
        }
      }
    }
  }
  if ( (unsigned __int8)byte_1801BA10B >= 0x20u )
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
                      v48 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                      v44 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                  v40 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v34 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v29 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v25 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x18005a29c  push    rbp
0x18005a29e  push    rbx
0x18005a29f  push    rsi
0x18005a2a0  push    rdi
0x18005a2a1  push    r12
0x18005a2a3  push    r13
0x18005a2a5  push    r14
0x18005a2a7  push    r15
0x18005a2a9  lea     rbp, [rsp-1Fh]
0x18005a2ae  sub     rsp, 88h
0x18005a2b5  mov     rax, cs:__security_cookie
0x18005a2bc  xor     rax, rsp
0x18005a2bf  mov     [rbp+57h+var_50], rax
0x18005a2c3  mov     rdi, rcx
0x18005a2c6  lea     r13, aCmp3mediasourc_21; "CMP3MediaSourcePlugin::CreatePresentati"...
0x18005a2cd  xor     r12d, r12d
0x18005a2d0  lea     rcx, [rbp+57h+var_80]; this
0x18005a2d4  xorps   xmm0, xmm0
0x18005a2d7  mov     [rbp+57h+ppDescriptor], r12
0x18005a2db  xor     eax, eax
0x18005a2dd  mov     [rbp+57h+ppMFType], r12
0x18005a2e1  mov     rdx, r13; char *
0x18005a2e4  mov     [rbp+57h+pWaveFormat.cbSize], ax
0x18005a2e8  mov     r8d, 95Dh; int
0x18005a2ee  movups  xmmword ptr [rbp+57h+pWaveFormat.wFormatTag], xmm0
0x18005a2f2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005a2f7  xor     eax, eax
0x18005a2f9  xorps   xmm0, xmm0
0x18005a2fc  movups  xmmword ptr [rbp+57h+pWaveFormat.wFormatTag], xmm0
0x18005a300  mov     [rbp+57h+pWaveFormat.cbSize], ax
0x18005a304  cmp     [rdi+348h], r12
0x18005a30b  jnz     loc_18005A3B3
0x18005a311  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a318  mov     ebx, 0C00D36BEh
0x18005a31d  test    rcx, rcx
0x18005a320  jnz     short loc_18005A369
0x18005a322  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005a329  nop     dword ptr [rax+rax+00h]
0x18005a32e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a335  mov     rcx, rax
0x18005a338  test    rax, rax
0x18005a33b  jz      short loc_18005A35B
0x18005a33d  mov     rax, [rax]
0x18005a340  mov     edx, 7F0h
0x18005a345  mov     rax, [rax+8]
0x18005a349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a34e  test    eax, eax
0x18005a350  jz      short loc_18005A35B
0x18005a352  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a359  jmp     short loc_18005A369
0x18005a35b  lea     rcx, qword_1801B97E0; this
0x18005a362  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a369  cmp     [rcx+8], r12b
0x18005a36d  jz      short loc_18005A390
0x18005a36f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005a374  cmp     [rax+7CCh], ebx
0x18005a37a  jz      short loc_18005A390
0x18005a37c  mov     r9d, ebx; int
0x18005a37f  mov     r8d, 966h; int
0x18005a385  mov     rdx, r13; char *
0x18005a388  mov     rcx, rax; this
0x18005a38b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005a390  mov     esi, 1
0x18005a395  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18005a39c  jb      loc_18005AAF0
0x18005a3a2  mov     edx, 0EEh
0x18005a3a7  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x18005a3ae  jmp     loc_18005AAD9
0x18005a3b3  lea     rbx, [rdi+350h]
0x18005a3ba  mov     rax, [rbx]
0x18005a3bd  lea     r14, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x18005a3c4  cmp     [rax+0A4h], r12d
0x18005a3cb  jz      short loc_18005A3FD
0x18005a3cd  cmp     cs:byte_1801BA10B, 4
0x18005a3d4  jb      short loc_18005A3F4
0x18005a3d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a3dd  mov     edx, 0EFh
0x18005a3e2  mov     r9, rdi
0x18005a3e5  mov     r8, r14
0x18005a3e8  mov     rcx, [rcx+88h]
0x18005a3ef  call    WPP_SF_q
0x18005a3f4  lea     rcx, [rdi+358h]
0x18005a3fb  jmp     short loc_18005A40D
0x18005a3fd  cmp     [rax+128h], r12d
0x18005a404  jz      short loc_18005A415
0x18005a406  lea     rcx, [rdi+360h]
0x18005a40d  mov     rdx, rbx
0x18005a410  call    ??4?$ComSmartPtr@VCMPEGFrame@@@@QEAAPEAVCMPEGFrame@@AEBV0@@Z; ComSmartPtr<CMPEGFrame>::operator=(ComSmartPtr<CMPEGFrame> const &)
0x18005a415  mov     r9d, [rdi+55Ch]; __int64
0x18005a41c  test    r9d, r9d
0x18005a41f  jz      short loc_18005A439
0x18005a421  mov     eax, [rdi+568h]
0x18005a427  xor     edx, edx
0x18005a429  div     r9d
0x18005a42c  mov     r8d, eax
0x18005a42f  shr     r8d, 3
0x18005a433  mov     [rbp+57h+pWaveFormat.nAvgBytesPerSec], r8d
0x18005a437  jmp     short loc_18005A43D
0x18005a439  mov     r8d, [rbp+57h+pWaveFormat.nAvgBytesPerSec]
0x18005a43d  mov     rcx, [rdi+358h]
0x18005a444  test    rcx, rcx
0x18005a447  jz      short loc_18005A493
0x18005a449  mov     eax, [rcx+0ACh]
0x18005a44f  and     eax, 3
0x18005a452  cmp     al, 3
0x18005a454  jnz     short loc_18005A493
0x18005a456  mov     eax, [rcx+98h]
0x18005a45c  test    eax, eax
0x18005a45e  jz      short loc_18005A493
0x18005a460  mov     r8d, [rcx+0A8h]
0x18005a467  mov     edx, [rcx+94h]; __int64
0x18005a46d  mov     ecx, [rcx+0B0h]; __int64
0x18005a473  imul    r8, rax; __int64
0x18005a477  call    ?llMulDiv@@YA_J_J000@Z; llMulDiv(__int64,__int64,__int64,__int64)
0x18005a47c  mov     [rbp+57h+pWaveFormat.nAvgBytesPerSec], eax
0x18005a47f  cmp     cs:byte_1801BA10B, 20h ; ' '
0x18005a486  jb      loc_18005A549
0x18005a48c  mov     edx, 0F0h
0x18005a491  jmp     short loc_18005A4E5
0x18005a493  mov     rcx, [rdi+360h]
0x18005a49a  test    rcx, rcx
0x18005a49d  jz      short loc_18005A507
0x18005a49f  mov     eax, [rcx+138h]
0x18005a4a5  test    eax, eax
0x18005a4a7  jz      short loc_18005A507
0x18005a4a9  mov     r10d, [rcx+134h]
0x18005a4b0  test    r10d, r10d
0x18005a4b3  jz      short loc_18005A507
0x18005a4b5  mov     edx, [rcx+98h]
0x18005a4bb  test    edx, edx
0x18005a4bd  jz      short loc_18005A507
0x18005a4bf  mov     r8d, edx
0x18005a4c2  mov     edx, [rcx+94h]; __int64
0x18005a4c8  imul    r8, rax; __int64
0x18005a4cc  mov     ecx, r10d; __int64
0x18005a4cf  call    ?llMulDiv@@YA_J_J000@Z; llMulDiv(__int64,__int64,__int64,__int64)
0x18005a4d4  mov     [rbp+57h+pWaveFormat.nAvgBytesPerSec], eax
0x18005a4d7  cmp     cs:byte_1801BA10B, 20h ; ' '
0x18005a4de  jb      short loc_18005A549
0x18005a4e0  mov     edx, 0F1h
0x18005a4e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a4ec  mov     r9, rdi
0x18005a4ef  shl     eax, 3
0x18005a4f2  mov     r8, r14
0x18005a4f5  mov     [rsp+0C0h+var_A0], eax
0x18005a4f9  mov     rcx, [rcx+88h]
0x18005a500  call    WPP_SF_qD
0x18005a505  jmp     short loc_18005A549
0x18005a507  cmp     cs:byte_1801BA10B, 20h ; ' '
0x18005a50e  jb      short loc_18005A549
0x18005a510  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a517  lea     eax, ds:0[r8*8]
0x18005a51f  mov     [rsp+0C0h+var_90], eax
0x18005a523  mov     edx, 0F2h
0x18005a528  mov     eax, [rdi+568h]
0x18005a52e  mov     r8, r14
0x18005a531  mov     [rsp+0C0h+var_98], r9d
0x18005a536  mov     r9, rdi
0x18005a539  mov     rcx, [rcx+88h]
0x18005a540  mov     [rsp+0C0h+var_A0], eax
0x18005a544  call    WPP_SF_qddd
0x18005a549  mov     rax, [rdi+348h]
0x18005a550  mov     ecx, 55h ; 'U'
0x18005a555  cmp     dword ptr [rax+8Ch], 3
0x18005a55c  jz      short loc_18005A563
0x18005a55e  mov     ecx, 50h ; 'P'
0x18005a563  mov     esi, 1
0x18005a568  mov     [rbp+57h+pWaveFormat.wFormatTag], cx
0x18005a56c  mov     [rbp+57h+pWaveFormat.nBlockAlign], si
0x18005a570  cmp     dword ptr [rax+5Ch], 3
0x18005a574  jnz     short loc_18005A57C
0x18005a576  mov     [rbp+57h+pWaveFormat.nChannels], si
0x18005a57a  jmp     short loc_18005A585
0x18005a57c  mov     ecx, 2
0x18005a581  mov     [rbp+57h+pWaveFormat.nChannels], cx
0x18005a585  mov     eax, [rax+94h]
0x18005a58b  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x18005a58f  mov     [rbp+57h+pWaveFormat.nSamplesPerSec], eax
0x18005a592  call    cs:__imp_MFCreateMediaType
0x18005a599  nop     dword ptr [rax+rax+00h]
0x18005a59e  mov     ebx, eax
0x18005a5a0  test    eax, eax
0x18005a5a2  jns     short loc_18005A5FA
0x18005a5a4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a5ab  test    rcx, rcx
0x18005a5ae  jnz     short loc_18005A5BC
0x18005a5b0  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005a5b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005a5bc  cmp     [rcx+8], r12b
0x18005a5c0  jz      short loc_18005A5E3
0x18005a5c2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005a5c7  cmp     [rax+7CCh], ebx
0x18005a5cd  jz      short loc_18005A5E3
0x18005a5cf  mov     r9d, ebx; int
0x18005a5d2  mov     r8d, 9B8h; int
0x18005a5d8  mov     rdx, r13; char *
0x18005a5db  mov     rcx, rax; this
0x18005a5de  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005a5e3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18005a5ea  jb      loc_18005AAF0
0x18005a5f0  mov     edx, 0F3h
0x18005a5f5  jmp     loc_18005AAD6
0x18005a5fa  mov     rcx, [rbp+57h+ppMFType]; pMFType
0x18005a5fe  lea     rdx, [rbp+57h+pWaveFormat]; pWaveFormat
0x18005a602  mov     r8d, 12h; cbBufSize
0x18005a608  call    cs:__imp_MFInitMediaTypeFromWaveFormatEx
0x18005a60f  nop     dword ptr [rax+rax+00h]
0x18005a614  mov     ebx, eax
0x18005a616  test    eax, eax
0x18005a618  jns     loc_18005A6AF
0x18005a61e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a625  test    rcx, rcx
0x18005a628  jnz     short loc_18005A671
0x18005a62a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005a631  nop     dword ptr [rax+rax+00h]
0x18005a636  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a63d  mov     rcx, rax
0x18005a640  test    rax, rax
0x18005a643  jz      short loc_18005A663
0x18005a645  mov     rax, [rax]
0x18005a648  mov     edx, 7F0h
0x18005a64d  mov     rax, [rax+8]
0x18005a651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a656  test    eax, eax
0x18005a658  jz      short loc_18005A663
0x18005a65a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a661  jmp     short loc_18005A671
0x18005a663  lea     rcx, qword_1801B97E0; this
0x18005a66a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a671  cmp     [rcx+8], r12b
0x18005a675  jz      short loc_18005A698
0x18005a677  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005a67c  cmp     [rax+7CCh], ebx
0x18005a682  jz      short loc_18005A698
0x18005a684  mov     r9d, ebx; int
0x18005a687  mov     r8d, 9B9h; int
0x18005a68d  mov     rdx, r13; char *
0x18005a690  mov     rcx, rax; this
0x18005a693  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005a698  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18005a69f  jb      loc_18005AAF0
0x18005a6a5  mov     edx, 0F4h
0x18005a6aa  jmp     loc_18005AAD6
0x18005a6af  lea     r9, [rbp+57h+ppDescriptor]; ppDescriptor
0x18005a6b3  mov     edx, esi; cMediaTypes
0x18005a6b5  lea     r8, [rbp+57h+ppMFType]; apMediaTypes
0x18005a6b9  xor     ecx, ecx; dwStreamIdentifier
0x18005a6bb  call    cs:__imp_MFCreateStreamDescriptor
0x18005a6c2  nop     dword ptr [rax+rax+00h]
0x18005a6c7  mov     ebx, eax
0x18005a6c9  test    eax, eax
0x18005a6cb  jns     loc_18005A762
0x18005a6d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a6d8  test    rcx, rcx
0x18005a6db  jnz     short loc_18005A724
0x18005a6dd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005a6e4  nop     dword ptr [rax+rax+00h]
0x18005a6e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a6f0  mov     rcx, rax
0x18005a6f3  test    rax, rax
0x18005a6f6  jz      short loc_18005A716
0x18005a6f8  mov     rax, [rax]
0x18005a6fb  mov     edx, 7F0h
0x18005a700  mov     rax, [rax+8]
0x18005a704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a709  test    eax, eax
0x18005a70b  jz      short loc_18005A716
0x18005a70d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a714  jmp     short loc_18005A724
0x18005a716  lea     rcx, qword_1801B97E0; this
0x18005a71d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a724  cmp     [rcx+8], r12b
0x18005a728  jz      short loc_18005A74B
0x18005a72a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005a72f  cmp     [rax+7CCh], ebx
0x18005a735  jz      short loc_18005A74B
0x18005a737  mov     r9d, ebx; int
0x18005a73a  mov     r8d, 9BBh; int
0x18005a740  mov     rdx, r13; char *
0x18005a743  mov     rcx, rax; this
0x18005a746  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005a74b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18005a752  jb      loc_18005AAF0
0x18005a758  mov     edx, 0F5h
0x18005a75d  jmp     loc_18005AAD6
0x18005a762  lea     r15, [rdi+0B8h]
0x18005a769  mov     ecx, esi; cStreamDescriptors
0x18005a76b  mov     r8, r15; ppPresentationDescriptor
0x18005a76e  lea     rdx, [rbp+57h+ppDescriptor]; apStreamDescriptors
0x18005a772  call    cs:__imp_MFCreatePresentationDescriptor
0x18005a779  nop     dword ptr [rax+rax+00h]
0x18005a77e  mov     ebx, eax
0x18005a780  test    eax, eax
0x18005a782  jns     loc_18005A819
0x18005a788  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005a78f  test    rcx, rcx
0x18005a792  jnz     short loc_18005A7DB
0x18005a794  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005a79b  nop     dword ptr [rax+rax+00h]
0x18005a7a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
