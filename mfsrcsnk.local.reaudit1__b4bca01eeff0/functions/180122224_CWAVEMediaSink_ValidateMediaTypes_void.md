# CWAVEMediaSink::ValidateMediaTypes(void)

- ea: `0x180122224`
- end: `0x180122853`
- name: `?ValidateMediaTypes@CWAVEMediaSink@@AEAAJXZ`
- size: `1583`
- prototype: `__int64 __fastcall(CWAVEMediaSink *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ac744`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180079680`
- `0x180110ed0`
- `0x18011cbac`
- `0x180122224`
- `0x18017b734`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801222a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180122413`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801224f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012258e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180122626`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801226be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180122756`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801222a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180122413`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801224f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012258e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180122626`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801226be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180122756`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x1801223f1`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x1801223f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180122816`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180122816`

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
        v4 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v28 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v25 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v12 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v22 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v19 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v15 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  if ( (unsigned __int8)byte_1801BA10A >= 2u )
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
0x180122224  mov     [rsp-28h+arg_8], rbx
0x180122229  mov     [rsp-28h+arg_10], rsi
0x18012222e  push    rbp
0x18012222f  push    rdi
0x180122230  push    r12
0x180122232  push    r14
0x180122234  push    r15
0x180122236  mov     rbp, rsp
0x180122239  sub     rsp, 70h
0x18012223d  mov     rax, cs:__security_cookie
0x180122244  xor     rax, rsp
0x180122247  mov     [rbp+var_10], rax
0x18012224b  mov     rsi, rcx
0x18012224e  lea     r15, aCwavemediasink_2; "CWAVEMediaSink::ValidateMediaTypes"
0x180122255  mov     rdx, r15; char *
0x180122258  lea     rcx, [rbp+var_40]; this
0x18012225c  mov     r8d, 0E6h; int
0x180122262  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180122267  mov     rcx, [rsi+300h]
0x18012226e  lea     r12, WPP_57ba707931523bdb17a9f4f557745fef_Traceguids
0x180122275  xor     r14d, r14d
0x180122278  xorps   xmm0, xmm0
0x18012227b  mov     [rbp+ppWF], r14
0x18012227f  xorps   xmm1, xmm1
0x180122282  mov     [rbp+pcbSize], r14d
0x180122286  movups  [rbp+Buf1], xmm0
0x18012228a  movups  [rbp+var_30], xmm1
0x18012228e  test    rcx, rcx
0x180122291  jnz     loc_180122331
0x180122297  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012229e  mov     edi, 80070057h
0x1801222a3  test    rcx, rcx
0x1801222a6  jnz     short loc_1801222EF
0x1801222a8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801222af  nop     dword ptr [rax+rax+00h]
0x1801222b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801222bb  mov     rcx, rax
0x1801222be  test    rax, rax
0x1801222c1  jz      short loc_1801222E1
0x1801222c3  mov     rax, [rax]
0x1801222c6  mov     edx, 7F0h
0x1801222cb  mov     rax, [rax+8]
0x1801222cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801222d4  test    eax, eax
0x1801222d6  jz      short loc_1801222E1
0x1801222d8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801222df  jmp     short loc_1801222EF
0x1801222e1  lea     rcx, qword_1801B97E0; this
0x1801222e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801222ef  cmp     [rcx+8], r14b
0x1801222f3  jz      short loc_180122316
0x1801222f5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801222fa  cmp     [rax+7CCh], edi
0x180122300  jz      short loc_180122316
0x180122302  mov     r9d, edi; int
0x180122305  mov     r8d, 0EDh; int
0x18012230b  mov     rdx, r15; char *
0x18012230e  mov     rcx, rax; this
0x180122311  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180122316  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18012231d  jb      loc_1801227EC
0x180122323  mov     edx, 24h ; '$'
0x180122328  mov     [rsp+70h+var_50], edi
0x18012232c  jmp     loc_1801227D6
0x180122331  mov     rax, [rcx]
0x180122334  lea     r8, [rbp+Buf1]
0x180122338  lea     rdx, MF_MT_MAJOR_TYPE
0x18012233f  mov     rax, [rax+50h]
0x180122343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122348  test    eax, eax
0x18012234a  js      loc_180122743
0x180122350  mov     ebx, 10h
0x180122355  lea     rdx, MFMediaType_Audio; Buf2
0x18012235c  mov     r8d, ebx; Size
0x18012235f  lea     rcx, [rbp+Buf1]; Buf1
0x180122363  call    memcmp_0
0x180122368  test    eax, eax
0x18012236a  jnz     loc_180122743
0x180122370  mov     rcx, [rsi+300h]
0x180122377  lea     r8, [rbp+var_30]
0x18012237b  lea     rdx, MF_MT_SUBTYPE
0x180122382  mov     rax, [rcx]
0x180122385  mov     rax, [rax+50h]
0x180122389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012238e  test    eax, eax
0x180122390  js      loc_1801226AB
0x180122396  mov     r8d, ebx; Size
0x180122399  lea     rdx, MFAudioFormat_PCM; Buf2
0x1801223a0  lea     rcx, [rbp+var_30]; Buf1
0x1801223a4  call    memcmp_0
0x1801223a9  test    eax, eax
0x1801223ab  jz      short loc_1801223DF
0x1801223ad  mov     r8d, ebx; Size
0x1801223b0  lea     rdx, MFAudioFormat_Float; Buf2
0x1801223b7  lea     rcx, [rbp+var_30]; Buf1
0x1801223bb  call    memcmp_0
0x1801223c0  test    eax, eax
0x1801223c2  jz      short loc_1801223DF
0x1801223c4  mov     r8d, ebx; Size
0x1801223c7  lea     rdx, MFAudioFormat_MP3; Buf2
0x1801223ce  lea     rcx, [rbp+var_30]; Buf1
0x1801223d2  call    memcmp_0
0x1801223d7  test    eax, eax
0x1801223d9  jnz     loc_1801226AB
0x1801223df  mov     rcx, [rsi+300h]; pMFType
0x1801223e6  lea     r8, [rbp+pcbSize]; pcbSize
0x1801223ea  xor     r9d, r9d; Flags
0x1801223ed  lea     rdx, [rbp+ppWF]; ppWF
0x1801223f1  call    cs:__imp_MFCreateWaveFormatExFromMFMediaType
0x1801223f8  nop     dword ptr [rax+rax+00h]
0x1801223fd  mov     edi, eax
0x1801223ff  test    eax, eax
0x180122401  jns     loc_180122498
0x180122407  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012240e  test    rcx, rcx
0x180122411  jnz     short loc_18012245A
0x180122413  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18012241a  nop     dword ptr [rax+rax+00h]
0x18012241f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180122426  mov     rcx, rax
0x180122429  test    rax, rax
0x18012242c  jz      short loc_18012244C
0x18012242e  mov     rax, [rax]
0x180122431  mov     edx, 7F0h
0x180122436  mov     rax, [rax+8]
0x18012243a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012243f  test    eax, eax
0x180122441  jz      short loc_18012244C
0x180122443  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012244a  jmp     short loc_18012245A
0x18012244c  lea     rcx, qword_1801B97E0; this
0x180122453  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012245a  cmp     [rcx+8], r14b
0x18012245e  jz      short loc_180122481
0x180122460  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180122465  cmp     [rax+7CCh], edi
0x18012246b  jz      short loc_180122481
0x18012246d  mov     r9d, edi; int
0x180122470  mov     r8d, 0FFh; int
0x180122476  mov     rdx, r15; char *
0x180122479  mov     rcx, rax; this
0x18012247c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180122481  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180122488  jb      loc_1801227EC
0x18012248e  mov     edx, 27h ; '''
0x180122493  jmp     loc_180122328
0x180122498  mov     rcx, [rbp+ppWF]
0x18012249c  test    rcx, rcx
0x18012249f  jz      loc_180122613
0x1801224a5  cmp     [rbp+pcbSize], r14d
0x1801224a9  jz      loc_180122613
0x1801224af  cmp     [rcx+4], r14d
0x1801224b3  jz      loc_18012257B
0x1801224b9  cmp     [rcx+2], r14w
0x1801224be  jz      loc_18012257B
0x1801224c4  movzx   eax, word ptr [rcx]
0x1801224c7  mov     edx, 0FFFDh
0x1801224cc  dec     ax
0x1801224cf  test    dx, ax
0x1801224d2  jnz     loc_18012280D
0x1801224d8  cmp     [rcx+0Eh], r14w
0x1801224dd  jnz     loc_18012280D
0x1801224e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801224ea  mov     ebx, 0C00D36B4h
0x1801224ef  mov     edi, ebx
0x1801224f1  test    rcx, rcx
0x1801224f4  jnz     short loc_18012253D
0x1801224f6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801224fd  nop     dword ptr [rax+rax+00h]
0x180122502  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180122509  mov     rcx, rax
0x18012250c  test    rax, rax
0x18012250f  jz      short loc_18012252F
0x180122511  mov     rax, [rax]
0x180122514  mov     edx, 7F0h
0x180122519  mov     rax, [rax+8]
0x18012251d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122522  test    eax, eax
0x180122524  jz      short loc_18012252F
0x180122526  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012252d  jmp     short loc_18012253D
0x18012252f  lea     rcx, qword_1801B97E0; this
0x180122536  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012253d  cmp     [rcx+8], r14b
0x180122541  jz      short loc_180122564
0x180122543  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180122548  cmp     [rax+7CCh], ebx
0x18012254e  jz      short loc_180122564
0x180122550  mov     r9d, ebx; int
0x180122553  mov     r8d, 112h; int
0x180122559  mov     rdx, r15; char *
0x18012255c  mov     rcx, rax; this
0x18012255f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180122564  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18012256b  jb      loc_1801227EC
0x180122571  mov     edx, 2Ah ; '*'
0x180122576  jmp     loc_1801227D2
0x18012257b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180122582  mov     ebx, 0C00D36B4h
0x180122587  mov     edi, ebx
0x180122589  test    rcx, rcx
0x18012258c  jnz     short loc_1801225D5
0x18012258e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180122595  nop     dword ptr [rax+rax+00h]
0x18012259a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801225a1  mov     rcx, rax
0x1801225a4  test    rax, rax
0x1801225a7  jz      short loc_1801225C7
0x1801225a9  mov     rax, [rax]
0x1801225ac  mov     edx, 7F0h
0x1801225b1  mov     rax, [rax+8]
0x1801225b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801225ba  test    eax, eax
0x1801225bc  jz      short loc_1801225C7
0x1801225be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801225c5  jmp     short loc_1801225D5
0x1801225c7  lea     rcx, qword_1801B97E0; this
0x1801225ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801225d5  cmp     [rcx+8], r14b
0x1801225d9  jz      short loc_1801225FC
0x1801225db  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801225e0  cmp     [rax+7CCh], ebx
0x1801225e6  jz      short loc_1801225FC
0x1801225e8  mov     r9d, ebx; int
0x1801225eb  mov     r8d, 10Ah; int
0x1801225f1  mov     rdx, r15; char *
0x1801225f4  mov     rcx, rax; this
0x1801225f7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801225fc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180122603  jb      loc_1801227EC
0x180122609  mov     edx, 29h ; ')'
0x18012260e  jmp     loc_1801227D2
0x180122613  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012261a  mov     ebx, 0C00D36B4h
0x18012261f  mov     edi, ebx
0x180122621  test    rcx, rcx
0x180122624  jnz     short loc_18012266D
0x180122626  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18012262d  nop     dword ptr [rax+rax+00h]
0x180122632  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180122639  mov     rcx, rax
0x18012263c  test    rax, rax
0x18012263f  jz      short loc_18012265F
0x180122641  mov     rax, [rax]
0x180122644  mov     edx, 7F0h
0x180122649  mov     rax, [rax+8]
0x18012264d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122652  test    eax, eax
0x180122654  jz      short loc_18012265F
0x180122656  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012265d  jmp     short loc_18012266D
0x18012265f  lea     rcx, qword_1801B97E0; this
0x180122666  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012266d  cmp     [rcx+8], r14b
0x180122671  jz      short loc_180122694
0x180122673  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180122678  cmp     [rax+7CCh], ebx
0x18012267e  jz      short loc_180122694
0x180122680  mov     r9d, ebx; int
0x180122683  mov     r8d, 104h; int
0x180122689  mov     rdx, r15; char *
0x18012268c  mov     rcx, rax; this
0x18012268f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180122694  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18012269b  jb      loc_1801227EC
0x1801226a1  mov     edx, 28h ; '('
0x1801226a6  jmp     loc_1801227D2
0x1801226ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801226b2  mov     ebx, 0C00D36B4h
0x1801226b7  mov     edi, ebx
0x1801226b9  test    rcx, rcx
0x1801226bc  jnz     short loc_180122705
0x1801226be  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801226c5  nop     dword ptr [rax+rax+00h]
0x1801226ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801226d1  mov     rcx, rax
0x1801226d4  test    rax, rax
0x1801226d7  jz      short loc_1801226F7
0x1801226d9  mov     rax, [rax]
0x1801226dc  mov     edx, 7F0h
0x1801226e1  mov     rax, [rax+8]
0x1801226e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801226ea  test    eax, eax
0x1801226ec  jz      short loc_1801226F7
0x1801226ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801226f5  jmp     short loc_180122705
0x1801226f7  lea     rcx, qword_1801B97E0; this
0x1801226fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180122705  cmp     [rcx+8], r14b
0x180122709  jz      short loc_18012272C
0x18012270b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180122710  cmp     [rax+7CCh], ebx
0x180122716  jz      short loc_18012272C
0x180122718  mov     r9d, ebx; int
0x18012271b  mov     r8d, 0FAh; int
0x180122721  mov     rdx, r15; char *
0x180122724  mov     rcx, rax; this
0x180122727  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18012272c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180122733  jb      loc_1801227EC
  ... truncated ...
```
