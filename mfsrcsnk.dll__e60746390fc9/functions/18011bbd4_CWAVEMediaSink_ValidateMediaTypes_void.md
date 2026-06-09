# CWAVEMediaSink::ValidateMediaTypes(void)

- ea: `0x18011bbd4`
- end: `0x18011c1cc`
- name: `?ValidateMediaTypes@CWAVEMediaSink@@AEAAJXZ`
- size: `1528`
- prototype: `__int64 __fastcall(CWAVEMediaSink *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a7628`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180073b14`
- `0x1801099f0`
- `0x180115a1c`
- `0x18011bbd4`
- `0x1801723d4`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011bc58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011bdb7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011be94`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011bf26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011bfb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011c04a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011c0dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011bc58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011bdb7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011be94`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011bf26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011bfb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011c04a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011c0dc`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x18011bd9b`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x18011bd9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011c196`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011c196`

## pseudocode

```c
__int64 __fastcall CWAVEMediaSink::ValidateMediaTypes(CWAVEMediaSink *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  wchar_t *v4; // rcx
  HRESULT v5; // edi
  CallStackTracing *v6; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  _BYTE v32[4]; // [rsp+30h] [rbp-40h] BYREF
  UINT32 pcbSize; // [rsp+34h] [rbp-3Ch] BYREF
  WAVEFORMATEX *ppWF; // [rsp+38h] [rbp-38h] BYREF
  __int128 v35; // [rsp+40h] [rbp-30h] BYREF
  __int128 Buf1; // [rsp+50h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v32, "CWAVEMediaSink::ValidateMediaTypes", 230);
  v3 = *((_QWORD *)this + 96);
  ppWF = 0;
  pcbSize = 0;
  Buf1 = 0;
  v35 = 0;
  if ( !v3 )
  {
    v4 = (wchar_t *)CallStackTracing::s_wpInstance;
    v5 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2);
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v4 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CWAVEMediaSink::ValidateMediaTypes", 237, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_87;
    v8 = 36;
    goto LABEL_12;
  }
  if ( (*(int (__fastcall **)(__int64, const GUID *, __int128 *))(*(_QWORD *)v3 + 80LL))(v3, &MF_MT_MAJOR_TYPE, &Buf1) < 0
    || memcmp_0(&Buf1, &MFMediaType_Audio, 0x10u) )
  {
    v28 = (wchar_t *)CallStackTracing::s_wpInstance;
    v5 = -1072875852;
    if ( !CallStackTracing::s_wpInstance )
    {
      v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
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
      if ( *((_DWORD *)v30 + 499) != -1072875852 )
        CallStackContext::TraceFailure(v30, "CWAVEMediaSink::ValidateMediaTypes", 242, -1072875852);
    }
    if ( !g_wppLevels )
      goto LABEL_87;
    v18 = 37;
    goto LABEL_86;
  }
  if ( (*(int (__fastcall **)(_QWORD, const GUID *, __int128 *))(**((_QWORD **)this + 96) + 80LL))(
         *((_QWORD *)this + 96),
         &MF_MT_SUBTYPE,
         &v35) < 0
    || memcmp_0(&v35, &MFAudioFormat_PCM, 0x10u)
    && memcmp_0(&v35, &MFAudioFormat_Float, 0x10u)
    && memcmp_0(&v35, &MFAudioFormat_MP3, 0x10u) )
  {
    v25 = (wchar_t *)CallStackTracing::s_wpInstance;
    v5 = -1072875852;
    if ( !CallStackTracing::s_wpInstance )
    {
      v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
      if ( *((_DWORD *)v27 + 499) != -1072875852 )
        CallStackContext::TraceFailure(v27, "CWAVEMediaSink::ValidateMediaTypes", 250, -1072875852);
    }
    if ( !g_wppLevels )
      goto LABEL_87;
    v18 = 38;
    goto LABEL_86;
  }
  v5 = MFCreateWaveFormatExFromMFMediaType(*((IMFMediaType **)this + 96), &ppWF, &pcbSize, 0);
  if ( v5 < 0 )
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
      if ( *((_DWORD *)v14 + 499) != v5 )
        CallStackContext::TraceFailure(v14, "CWAVEMediaSink::ValidateMediaTypes", 255, v5);
    }
    if ( !g_wppLevels )
      goto LABEL_87;
    v8 = 39;
LABEL_12:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_57ba707931523bdb17a9f4f557745fef_Traceguids, this, v5);
    goto LABEL_87;
  }
  if ( !ppWF || !pcbSize )
  {
    v22 = (wchar_t *)CallStackTracing::s_wpInstance;
    v5 = -1072875852;
    if ( !CallStackTracing::s_wpInstance )
    {
      v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
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
      if ( *((_DWORD *)v24 + 499) != -1072875852 )
        CallStackContext::TraceFailure(v24, "CWAVEMediaSink::ValidateMediaTypes", 260, -1072875852);
    }
    if ( !g_wppLevels )
      goto LABEL_87;
    v18 = 40;
    goto LABEL_86;
  }
  if ( !ppWF->nSamplesPerSec || !ppWF->nChannels )
  {
    v19 = (wchar_t *)CallStackTracing::s_wpInstance;
    v5 = -1072875852;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
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
      if ( *((_DWORD *)v21 + 499) != -1072875852 )
        CallStackContext::TraceFailure(v21, "CWAVEMediaSink::ValidateMediaTypes", 266, -1072875852);
    }
    if ( !g_wppLevels )
      goto LABEL_87;
    v18 = 41;
    goto LABEL_86;
  }
  if ( ((ppWF->wFormatTag - 1) & 0xFFFD) != 0 || ppWF->wBitsPerSample )
    goto LABEL_89;
  v15 = (wchar_t *)CallStackTracing::s_wpInstance;
  v5 = -1072875852;
  if ( !CallStackTracing::s_wpInstance )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 65533);
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
    if ( *((_DWORD *)v17 + 499) != -1072875852 )
      CallStackContext::TraceFailure(v17, "CWAVEMediaSink::ValidateMediaTypes", 274, -1072875852);
  }
  if ( g_wppLevels )
  {
    v18 = 42;
LABEL_86:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v18,
      WPP_57ba707931523bdb17a9f4f557745fef_Traceguids,
      this,
      -1072875852);
  }
LABEL_87:
  if ( (unsigned __int8)byte_1801B110A >= 2u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 43, WPP_57ba707931523bdb17a9f4f557745fef_Traceguids);
LABEL_89:
  if ( ppWF )
    CoTaskMemFree(ppWF);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v32);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18011bbd4  mov     [rsp-28h+arg_8], rbx
0x18011bbd9  mov     [rsp-28h+arg_10], rsi
0x18011bbde  push    rbp
0x18011bbdf  push    rdi
0x18011bbe0  push    r12
0x18011bbe2  push    r14
0x18011bbe4  push    r15
0x18011bbe6  mov     rbp, rsp
0x18011bbe9  sub     rsp, 70h
0x18011bbed  mov     rax, cs:__security_cookie
0x18011bbf4  xor     rax, rsp
0x18011bbf7  mov     [rbp+var_10], rax
0x18011bbfb  mov     rsi, rcx
0x18011bbfe  lea     r15, aCwavemediasink_2; "CWAVEMediaSink::ValidateMediaTypes"
0x18011bc05  mov     rdx, r15; char *
0x18011bc08  lea     rcx, [rbp+var_40]; this
0x18011bc0c  mov     r8d, 0E6h; int
0x18011bc12  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18011bc17  mov     rcx, [rsi+300h]
0x18011bc1e  lea     r12, WPP_57ba707931523bdb17a9f4f557745fef_Traceguids
0x18011bc25  xor     r14d, r14d
0x18011bc28  xorps   xmm0, xmm0
0x18011bc2b  mov     [rbp+ppWF], r14
0x18011bc2f  xorps   xmm1, xmm1
0x18011bc32  mov     [rbp+pcbSize], r14d
0x18011bc36  movups  [rbp+Buf1], xmm0
0x18011bc3a  movups  [rbp+var_30], xmm1
0x18011bc3e  test    rcx, rcx
0x18011bc41  jnz     loc_18011BCDB
0x18011bc47  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bc4e  mov     edi, 80070057h
0x18011bc53  test    rcx, rcx
0x18011bc56  jnz     short loc_18011BC99
0x18011bc58  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011bc5e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bc65  mov     rcx, rax
0x18011bc68  test    rax, rax
0x18011bc6b  jz      short loc_18011BC8B
0x18011bc6d  mov     rax, [rax]
0x18011bc70  mov     edx, 7F0h
0x18011bc75  mov     rax, [rax+8]
0x18011bc79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011bc7e  test    eax, eax
0x18011bc80  jz      short loc_18011BC8B
0x18011bc82  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bc89  jmp     short loc_18011BC99
0x18011bc8b  lea     rcx, qword_1801B07E0; this
0x18011bc92  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bc99  cmp     [rcx+8], r14b
0x18011bc9d  jz      short loc_18011BCC0
0x18011bc9f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011bca4  cmp     [rax+7CCh], edi
0x18011bcaa  jz      short loc_18011BCC0
0x18011bcac  mov     r9d, edi; int
0x18011bcaf  mov     r8d, 0EDh; int
0x18011bcb5  mov     rdx, r15; char *
0x18011bcb8  mov     rcx, rax; this
0x18011bcbb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011bcc0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011bcc7  jb      loc_18011C16C
0x18011bccd  mov     edx, 24h ; '$'
0x18011bcd2  mov     [rsp+70h+var_50], edi
0x18011bcd6  jmp     loc_18011C156
0x18011bcdb  mov     rax, [rcx]
0x18011bcde  lea     r8, [rbp+Buf1]
0x18011bce2  lea     rdx, MF_MT_MAJOR_TYPE
0x18011bce9  mov     rax, [rax+50h]
0x18011bced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011bcf2  test    eax, eax
0x18011bcf4  js      loc_18011C0C9
0x18011bcfa  mov     ebx, 10h
0x18011bcff  lea     rdx, MFMediaType_Audio; Buf2
0x18011bd06  mov     r8d, ebx; Size
0x18011bd09  lea     rcx, [rbp+Buf1]; Buf1
0x18011bd0d  call    memcmp_0
0x18011bd12  test    eax, eax
0x18011bd14  jnz     loc_18011C0C9
0x18011bd1a  mov     rcx, [rsi+300h]
0x18011bd21  lea     r8, [rbp+var_30]
0x18011bd25  lea     rdx, MF_MT_SUBTYPE
0x18011bd2c  mov     rax, [rcx]
0x18011bd2f  mov     rax, [rax+50h]
0x18011bd33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011bd38  test    eax, eax
0x18011bd3a  js      loc_18011C037
0x18011bd40  mov     r8d, ebx; Size
0x18011bd43  lea     rdx, MFAudioFormat_PCM; Buf2
0x18011bd4a  lea     rcx, [rbp+var_30]; Buf1
0x18011bd4e  call    memcmp_0
0x18011bd53  test    eax, eax
0x18011bd55  jz      short loc_18011BD89
0x18011bd57  mov     r8d, ebx; Size
0x18011bd5a  lea     rdx, MFAudioFormat_Float; Buf2
0x18011bd61  lea     rcx, [rbp+var_30]; Buf1
0x18011bd65  call    memcmp_0
0x18011bd6a  test    eax, eax
0x18011bd6c  jz      short loc_18011BD89
0x18011bd6e  mov     r8d, ebx; Size
0x18011bd71  lea     rdx, MFAudioFormat_MP3; Buf2
0x18011bd78  lea     rcx, [rbp+var_30]; Buf1
0x18011bd7c  call    memcmp_0
0x18011bd81  test    eax, eax
0x18011bd83  jnz     loc_18011C037
0x18011bd89  mov     rcx, [rsi+300h]; pMFType
0x18011bd90  lea     r8, [rbp+pcbSize]; pcbSize
0x18011bd94  xor     r9d, r9d; Flags
0x18011bd97  lea     rdx, [rbp+ppWF]; ppWF
0x18011bd9b  call    cs:__imp_MFCreateWaveFormatExFromMFMediaType
0x18011bda1  mov     edi, eax
0x18011bda3  test    eax, eax
0x18011bda5  jns     loc_18011BE36
0x18011bdab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bdb2  test    rcx, rcx
0x18011bdb5  jnz     short loc_18011BDF8
0x18011bdb7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011bdbd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bdc4  mov     rcx, rax
0x18011bdc7  test    rax, rax
0x18011bdca  jz      short loc_18011BDEA
0x18011bdcc  mov     rax, [rax]
0x18011bdcf  mov     edx, 7F0h
0x18011bdd4  mov     rax, [rax+8]
0x18011bdd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011bddd  test    eax, eax
0x18011bddf  jz      short loc_18011BDEA
0x18011bde1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bde8  jmp     short loc_18011BDF8
0x18011bdea  lea     rcx, qword_1801B07E0; this
0x18011bdf1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bdf8  cmp     [rcx+8], r14b
0x18011bdfc  jz      short loc_18011BE1F
0x18011bdfe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011be03  cmp     [rax+7CCh], edi
0x18011be09  jz      short loc_18011BE1F
0x18011be0b  mov     r9d, edi; int
0x18011be0e  mov     r8d, 0FFh; int
0x18011be14  mov     rdx, r15; char *
0x18011be17  mov     rcx, rax; this
0x18011be1a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011be1f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011be26  jb      loc_18011C16C
0x18011be2c  mov     edx, 27h ; '''
0x18011be31  jmp     loc_18011BCD2
0x18011be36  mov     rcx, [rbp+ppWF]
0x18011be3a  test    rcx, rcx
0x18011be3d  jz      loc_18011BFA5
0x18011be43  cmp     [rbp+pcbSize], r14d
0x18011be47  jz      loc_18011BFA5
0x18011be4d  cmp     [rcx+4], r14d
0x18011be51  jz      loc_18011BF13
0x18011be57  cmp     [rcx+2], r14w
0x18011be5c  jz      loc_18011BF13
0x18011be62  movzx   eax, word ptr [rcx]
0x18011be65  mov     edx, 0FFFDh
0x18011be6a  dec     ax
0x18011be6d  test    dx, ax
0x18011be70  jnz     loc_18011C18D
0x18011be76  cmp     [rcx+0Eh], r14w
0x18011be7b  jnz     loc_18011C18D
0x18011be81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011be88  mov     ebx, 0C00D36B4h
0x18011be8d  mov     edi, ebx
0x18011be8f  test    rcx, rcx
0x18011be92  jnz     short loc_18011BED5
0x18011be94  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011be9a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bea1  mov     rcx, rax
0x18011bea4  test    rax, rax
0x18011bea7  jz      short loc_18011BEC7
0x18011bea9  mov     rax, [rax]
0x18011beac  mov     edx, 7F0h
0x18011beb1  mov     rax, [rax+8]
0x18011beb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011beba  test    eax, eax
0x18011bebc  jz      short loc_18011BEC7
0x18011bebe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bec5  jmp     short loc_18011BED5
0x18011bec7  lea     rcx, qword_1801B07E0; this
0x18011bece  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bed5  cmp     [rcx+8], r14b
0x18011bed9  jz      short loc_18011BEFC
0x18011bedb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011bee0  cmp     [rax+7CCh], ebx
0x18011bee6  jz      short loc_18011BEFC
0x18011bee8  mov     r9d, ebx; int
0x18011beeb  mov     r8d, 112h; int
0x18011bef1  mov     rdx, r15; char *
0x18011bef4  mov     rcx, rax; this
0x18011bef7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011befc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011bf03  jb      loc_18011C16C
0x18011bf09  mov     edx, 2Ah ; '*'
0x18011bf0e  jmp     loc_18011C152
0x18011bf13  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bf1a  mov     ebx, 0C00D36B4h
0x18011bf1f  mov     edi, ebx
0x18011bf21  test    rcx, rcx
0x18011bf24  jnz     short loc_18011BF67
0x18011bf26  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011bf2c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bf33  mov     rcx, rax
0x18011bf36  test    rax, rax
0x18011bf39  jz      short loc_18011BF59
0x18011bf3b  mov     rax, [rax]
0x18011bf3e  mov     edx, 7F0h
0x18011bf43  mov     rax, [rax+8]
0x18011bf47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011bf4c  test    eax, eax
0x18011bf4e  jz      short loc_18011BF59
0x18011bf50  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bf57  jmp     short loc_18011BF67
0x18011bf59  lea     rcx, qword_1801B07E0; this
0x18011bf60  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bf67  cmp     [rcx+8], r14b
0x18011bf6b  jz      short loc_18011BF8E
0x18011bf6d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011bf72  cmp     [rax+7CCh], ebx
0x18011bf78  jz      short loc_18011BF8E
0x18011bf7a  mov     r9d, ebx; int
0x18011bf7d  mov     r8d, 10Ah; int
0x18011bf83  mov     rdx, r15; char *
0x18011bf86  mov     rcx, rax; this
0x18011bf89  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011bf8e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011bf95  jb      loc_18011C16C
0x18011bf9b  mov     edx, 29h ; ')'
0x18011bfa0  jmp     loc_18011C152
0x18011bfa5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bfac  mov     ebx, 0C00D36B4h
0x18011bfb1  mov     edi, ebx
0x18011bfb3  test    rcx, rcx
0x18011bfb6  jnz     short loc_18011BFF9
0x18011bfb8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011bfbe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bfc5  mov     rcx, rax
0x18011bfc8  test    rax, rax
0x18011bfcb  jz      short loc_18011BFEB
0x18011bfcd  mov     rax, [rax]
0x18011bfd0  mov     edx, 7F0h
0x18011bfd5  mov     rax, [rax+8]
0x18011bfd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011bfde  test    eax, eax
0x18011bfe0  jz      short loc_18011BFEB
0x18011bfe2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bfe9  jmp     short loc_18011BFF9
0x18011bfeb  lea     rcx, qword_1801B07E0; this
0x18011bff2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bff9  cmp     [rcx+8], r14b
0x18011bffd  jz      short loc_18011C020
0x18011bfff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011c004  cmp     [rax+7CCh], ebx
0x18011c00a  jz      short loc_18011C020
0x18011c00c  mov     r9d, ebx; int
0x18011c00f  mov     r8d, 104h; int
0x18011c015  mov     rdx, r15; char *
0x18011c018  mov     rcx, rax; this
0x18011c01b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011c020  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011c027  jb      loc_18011C16C
0x18011c02d  mov     edx, 28h ; '('
0x18011c032  jmp     loc_18011C152
0x18011c037  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011c03e  mov     ebx, 0C00D36B4h
0x18011c043  mov     edi, ebx
0x18011c045  test    rcx, rcx
0x18011c048  jnz     short loc_18011C08B
0x18011c04a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011c050  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011c057  mov     rcx, rax
0x18011c05a  test    rax, rax
0x18011c05d  jz      short loc_18011C07D
0x18011c05f  mov     rax, [rax]
0x18011c062  mov     edx, 7F0h
0x18011c067  mov     rax, [rax+8]
0x18011c06b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c070  test    eax, eax
0x18011c072  jz      short loc_18011C07D
0x18011c074  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011c07b  jmp     short loc_18011C08B
0x18011c07d  lea     rcx, qword_1801B07E0; this
0x18011c084  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011c08b  cmp     [rcx+8], r14b
0x18011c08f  jz      short loc_18011C0B2
0x18011c091  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011c096  cmp     [rax+7CCh], ebx
0x18011c09c  jz      short loc_18011C0B2
0x18011c09e  mov     r9d, ebx; int
0x18011c0a1  mov     r8d, 0FAh; int
0x18011c0a7  mov     rdx, r15; char *
0x18011c0aa  mov     rcx, rax; this
0x18011c0ad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011c0b2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011c0b9  jb      loc_18011C16C
0x18011c0bf  mov     edx, 26h ; '&'
0x18011c0c4  jmp     loc_18011C152
0x18011c0c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011c0d0  mov     ebx, 0C00D36B4h
0x18011c0d5  mov     edi, ebx
0x18011c0d7  test    rcx, rcx
0x18011c0da  jnz     short loc_18011C11D
  ... truncated ...
```
