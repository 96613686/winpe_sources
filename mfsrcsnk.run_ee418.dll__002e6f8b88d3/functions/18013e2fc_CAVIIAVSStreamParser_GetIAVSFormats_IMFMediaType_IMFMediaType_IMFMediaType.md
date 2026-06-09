# CAVIIAVSStreamParser::GetIAVSFormats(IMFMediaType * *,IMFMediaType * *,IMFMediaType * *)

- ea: `0x18013e2fc`
- end: `0x18013e8f0`
- name: `?GetIAVSFormats@CAVIIAVSStreamParser@@QEBAJPEAPEAUIMFMediaType@@00@Z`
- size: `1524`
- prototype: `__int64 __fastcall(CAVIIAVSStreamParser *__hidden this, struct IMFMediaType **, struct IMFMediaType **, struct IMFMediaType **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18004f918`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x18013e2fc`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013e362`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013e48c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013e55e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013e613`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013e6c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013e76e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013e81d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013e362`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013e48c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013e55e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013e613`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013e6c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013e76e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013e81d`
- `MFPlat!MFCreateVideoMediaTypeFromBitMapInfoHeaderEx` at `0x18013e470`
- `MFPlat!MFCreateVideoMediaTypeFromBitMapInfoHeaderEx` at `0x18013e470`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x18013e6a6`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x18013e801`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x18013e6a6`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x18013e801`
- `MFPlat!MFCreateMediaType` at `0x18013e5f7`
- `MFPlat!MFCreateMediaType` at `0x18013e752`
- `MFPlat!MFCreateMediaType` at `0x18013e5f7`
- `MFPlat!MFCreateMediaType` at `0x18013e752`

## pseudocode

```c
__int64 __fastcall CAVIIAVSStreamParser::GetIAVSFormats(
        CAVIIAVSStreamParser *this,
        struct IMFMediaType **a2,
        struct IMFMediaType **a3,
        struct IMFMediaType **a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  wchar_t *v11; // rcx
  HRESULT v12; // ebx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  const BITMAPINFOHEADER *v16; // r10
  MFVideoInterlaceMode InterlaceMode; // ecx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  wchar_t *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r9
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  IMFMediaType *pMFType; // [rsp+50h] [rbp-28h] BYREF
  IMFMediaType *ppMFType; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v58[3]; // [rsp+60h] [rbp-18h] BYREF
  IMFVideoMediaType *ppIVideoMediaType; // [rsp+C0h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&ppIVideoMediaType,
    "CAVIIAVSStreamParser::GetIAVSFormats",
    69);
  v58[0] = 0;
  ppMFType = 0;
  pMFType = 0;
  if ( !*((_QWORD *)this + 198) )
  {
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    v12 = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v11 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875854 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIIAVSStreamParser::GetIAVSFormats", 76, -1072875854);
    }
    if ( g_wppLevels )
    {
      v15 = 11;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids, this, v12);
      goto LABEL_89;
    }
    goto LABEL_89;
  }
  v16 = (const BITMAPINFOHEADER *)*((_QWORD *)this + 80);
  v12 = 0;
  if ( v16 )
  {
    ppIVideoMediaType = 0;
    if ( *((_DWORD *)this + 399) )
      InterlaceMode = (*((_DWORD *)this + 400) != 0) + 5;
    else
      InterlaceMode = MFVideoInterlace_Progressive;
    v12 = MFCreateVideoMediaTypeFromBitMapInfoHeaderEx(
            v16,
            v16->biSize,
            *((unsigned __int16 *)this + 796),
            *((unsigned __int16 *)this + 797),
            InterlaceMode,
            0,
            *((_DWORD *)this + 8),
            *((_DWORD *)this + 7),
            0,
            &ppIVideoMediaType);
    if ( v12 < 0 )
    {
      v21 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
        if ( *((_DWORD *)v23 + 499) != v12 )
          CallStackContext::TraceFailure(v23, "CAVIIAVSStreamParser::GetIAVSFormats", 107, v12);
      }
      if ( !g_wppLevels )
        goto LABEL_29;
      v24 = 12;
LABEL_28:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids, this, v12);
LABEL_29:
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppIVideoMediaType);
      goto LABEL_89;
    }
    v12 = ((__int64 (__fastcall *)(IMFVideoMediaType *, GUID *, _QWORD *))ppIVideoMediaType->lpVtbl->QueryInterface)(
            ppIVideoMediaType,
            &IID_IMFMediaType,
            v58);
    if ( v12 < 0 )
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
        if ( *((_DWORD *)v30 + 499) != v12 )
          CallStackContext::TraceFailure(v30, "CAVIIAVSStreamParser::GetIAVSFormats", 108, v12);
      }
      if ( !g_wppLevels )
        goto LABEL_29;
      v24 = 13;
      goto LABEL_28;
    }
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppIVideoMediaType);
  }
  if ( !*((_QWORD *)this + 201) )
  {
LABEL_65:
    if ( *((_QWORD *)this + 202) )
    {
      v12 = MFCreateMediaType(&pMFType);
      if ( v12 < 0 )
      {
        v46 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v44, v45);
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
          if ( *((_DWORD *)v48 + 499) != v12 )
            CallStackContext::TraceFailure(v48, "CAVIIAVSStreamParser::GetIAVSFormats", 119, v12);
        }
        if ( g_wppLevels )
        {
          v15 = 16;
          goto LABEL_12;
        }
        goto LABEL_89;
      }
      v12 = MFInitMediaTypeFromWaveFormatEx(
              pMFType,
              *((const WAVEFORMATEX **)this + 202),
              *(unsigned __int16 *)(*((_QWORD *)this + 202) + 16LL) + 18);
      if ( v12 < 0 )
      {
        v52 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49, v50, v51);
          CallStackTracing::s_wpInstance = v53;
          if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
          {
            v52 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v52 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v52 + 8) )
        {
          v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
          if ( *((_DWORD *)v54 + 499) != v12 )
            CallStackContext::TraceFailure(v54, "CAVIIAVSStreamParser::GetIAVSFormats", 120, v12);
        }
        if ( g_wppLevels )
        {
          v15 = 17;
          goto LABEL_12;
        }
        goto LABEL_89;
      }
    }
    *a2 = (struct IMFMediaType *)v58[0];
    *a3 = ppMFType;
    *a4 = pMFType;
    v58[0] = 0;
    ppMFType = 0;
    pMFType = 0;
    goto LABEL_89;
  }
  v12 = MFCreateMediaType(&ppMFType);
  if ( v12 >= 0 )
  {
    v12 = MFInitMediaTypeFromWaveFormatEx(
            ppMFType,
            *((const WAVEFORMATEX **)this + 201),
            *(unsigned __int16 *)(*((_QWORD *)this + 201) + 16LL) + 18);
    if ( v12 < 0 )
    {
      v40 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38, v39);
        CallStackTracing::s_wpInstance = v41;
        if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
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
        if ( *((_DWORD *)v42 + 499) != v12 )
          CallStackContext::TraceFailure(v42, "CAVIIAVSStreamParser::GetIAVSFormats", 114, v12);
      }
      if ( g_wppLevels )
      {
        v15 = 15;
        goto LABEL_12;
      }
      goto LABEL_89;
    }
    goto LABEL_65;
  }
  v34 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
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
    if ( *((_DWORD *)v36 + 499) != v12 )
      CallStackContext::TraceFailure(v36, "CAVIIAVSStreamParser::GetIAVSFormats", 113, v12);
  }
  if ( g_wppLevels )
  {
    v15 = 14;
    goto LABEL_12;
  }
LABEL_89:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&pMFType);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppMFType);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v58);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&ppIVideoMediaType);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18013e2fc  push    rbp
0x18013e2fe  push    rbx
0x18013e2ff  push    rsi
0x18013e300  push    rdi
0x18013e301  push    r12
0x18013e303  push    r13
0x18013e305  push    r14
0x18013e307  push    r15
0x18013e309  mov     rbp, rsp
0x18013e30c  sub     rsp, 78h
0x18013e310  mov     r14, r8
0x18013e313  lea     r13, aCaviiavsstream; "CAVIIAVSStreamParser::GetIAVSFormats"
0x18013e31a  mov     r15, rdx
0x18013e31d  mov     rdi, rcx
0x18013e320  mov     rdx, r13; char *
0x18013e323  lea     rcx, [rbp+arg_0]; this
0x18013e327  mov     r8d, 45h ; 'E'; int
0x18013e32d  mov     rsi, r9
0x18013e330  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18013e335  xor     r12d, r12d
0x18013e338  mov     [rbp+var_18], r12
0x18013e33c  mov     [rbp+ppMFType], r12
0x18013e340  mov     [rbp+pMFType], r12
0x18013e344  cmp     [rdi+630h], r12
0x18013e34b  jnz     loc_18013E3FF
0x18013e351  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e358  mov     ebx, 0C00D36B2h
0x18013e35d  test    rcx, rcx
0x18013e360  jnz     short loc_18013E3A3
0x18013e362  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013e368  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e36f  mov     rcx, rax
0x18013e372  test    rax, rax
0x18013e375  jz      short loc_18013E395
0x18013e377  mov     rax, [rax]
0x18013e37a  mov     edx, 7F0h
0x18013e37f  mov     rax, [rax+8]
0x18013e383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013e388  test    eax, eax
0x18013e38a  jz      short loc_18013E395
0x18013e38c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e393  jmp     short loc_18013E3A3
0x18013e395  lea     rcx, qword_1801B07E0; this
0x18013e39c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e3a3  cmp     [rcx+8], r12b
0x18013e3a7  jz      short loc_18013E3CA
0x18013e3a9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013e3ae  cmp     [rax+7CCh], ebx
0x18013e3b4  jz      short loc_18013E3CA
0x18013e3b6  mov     r9d, ebx; int
0x18013e3b9  mov     r8d, 4Ch ; 'L'; int
0x18013e3bf  mov     rdx, r13; char *
0x18013e3c2  mov     rcx, rax; this
0x18013e3c5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013e3ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013e3d1  jb      loc_18013E8B9
0x18013e3d7  mov     edx, 0Bh
0x18013e3dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18013e3e3  lea     r8, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids
0x18013e3ea  mov     r9, rdi
0x18013e3ed  mov     [rsp+78h+InterlaceMode], ebx
0x18013e3f1  mov     rcx, [rcx+10h]
0x18013e3f5  call    WPP_SF_qD
0x18013e3fa  jmp     loc_18013E8B9
0x18013e3ff  mov     r10, [rdi+280h]
0x18013e406  mov     ebx, r12d
0x18013e409  test    r10, r10
0x18013e40c  jz      loc_18013E5E6
0x18013e412  mov     [rbp+arg_0], r12
0x18013e416  cmp     [rdi+63Ch], r12d
0x18013e41d  jz      short loc_18013E430
0x18013e41f  mov     eax, [rdi+640h]
0x18013e425  neg     eax
0x18013e427  sbb     ecx, ecx
0x18013e429  neg     ecx
0x18013e42b  add     ecx, 5
0x18013e42e  jmp     short loc_18013E435
0x18013e430  mov     ecx, 2
0x18013e435  movzx   r9d, word ptr [rdi+63Ah]; dwPixelAspectRatioY
0x18013e43d  lea     rax, [rbp+arg_0]
0x18013e441  movzx   r8d, word ptr [rdi+638h]; dwPixelAspectRatioX
0x18013e449  mov     edx, [r10]; cbBitMapInfoHeader
0x18013e44c  mov     [rsp+78h+ppIVideoMediaType], rax; ppIVideoMediaType
0x18013e451  mov     eax, [rdi+1Ch]
0x18013e454  mov     [rsp+78h+dwMaxBitRate], r12d; dwMaxBitRate
0x18013e459  mov     [rsp+78h+dwFramesPerSecondDenominator], eax; dwFramesPerSecondDenominator
0x18013e45d  mov     eax, [rdi+20h]
0x18013e460  mov     [rsp+78h+dwFramesPerSecondNumerator], eax; dwFramesPerSecondNumerator
0x18013e464  mov     [rsp+78h+VideoFlags], r12; VideoFlags
0x18013e469  mov     [rsp+78h+InterlaceMode], ecx; InterlaceMode
0x18013e46d  mov     rcx, r10; pbmihBitMapInfoHeader
0x18013e470  call    cs:__imp_MFCreateVideoMediaTypeFromBitMapInfoHeaderEx
0x18013e476  mov     ebx, eax
0x18013e478  test    eax, eax
0x18013e47a  jns     loc_18013E52E
0x18013e480  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e487  test    rcx, rcx
0x18013e48a  jnz     short loc_18013E4CD
0x18013e48c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013e492  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e499  mov     rcx, rax
0x18013e49c  test    rax, rax
0x18013e49f  jz      short loc_18013E4BF
0x18013e4a1  mov     rax, [rax]
0x18013e4a4  mov     edx, 7F0h
0x18013e4a9  mov     rax, [rax+8]
0x18013e4ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013e4b2  test    eax, eax
0x18013e4b4  jz      short loc_18013E4BF
0x18013e4b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e4bd  jmp     short loc_18013E4CD
0x18013e4bf  lea     rcx, qword_1801B07E0; this
0x18013e4c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e4cd  cmp     [rcx+8], r12b
0x18013e4d1  jz      short loc_18013E4F4
0x18013e4d3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013e4d8  cmp     [rax+7CCh], ebx
0x18013e4de  jz      short loc_18013E4F4
0x18013e4e0  mov     r9d, ebx; int
0x18013e4e3  mov     r8d, 6Bh ; 'k'; int
0x18013e4e9  mov     rdx, r13; char *
0x18013e4ec  mov     rcx, rax; this
0x18013e4ef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013e4f4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013e4fb  jb      short loc_18013E520
0x18013e4fd  mov     edx, 0Ch
0x18013e502  mov     rcx, cs:WPP_GLOBAL_Control
0x18013e509  lea     r8, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids
0x18013e510  mov     r9, rdi
0x18013e513  mov     [rsp+78h+InterlaceMode], ebx
0x18013e517  mov     rcx, [rcx+10h]
0x18013e51b  call    WPP_SF_qD
0x18013e520  lea     rcx, [rbp+arg_0]; void *
0x18013e524  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18013e529  jmp     loc_18013E8B9
0x18013e52e  mov     rcx, [rbp+arg_0]
0x18013e532  lea     r8, [rbp+var_18]
0x18013e536  lea     rdx, IID_IMFMediaType
0x18013e53d  mov     rax, [rcx]
0x18013e540  mov     rax, [rax]
0x18013e543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013e548  mov     ebx, eax
0x18013e54a  test    eax, eax
0x18013e54c  jns     loc_18013E5DD
0x18013e552  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e559  test    rcx, rcx
0x18013e55c  jnz     short loc_18013E59F
0x18013e55e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013e564  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e56b  mov     rcx, rax
0x18013e56e  test    rax, rax
0x18013e571  jz      short loc_18013E591
0x18013e573  mov     rax, [rax]
0x18013e576  mov     edx, 7F0h
0x18013e57b  mov     rax, [rax+8]
0x18013e57f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013e584  test    eax, eax
0x18013e586  jz      short loc_18013E591
0x18013e588  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e58f  jmp     short loc_18013E59F
0x18013e591  lea     rcx, qword_1801B07E0; this
0x18013e598  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e59f  cmp     [rcx+8], r12b
0x18013e5a3  jz      short loc_18013E5C6
0x18013e5a5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013e5aa  cmp     [rax+7CCh], ebx
0x18013e5b0  jz      short loc_18013E5C6
0x18013e5b2  mov     r9d, ebx; int
0x18013e5b5  mov     r8d, 6Ch ; 'l'; int
0x18013e5bb  mov     rdx, r13; char *
0x18013e5be  mov     rcx, rax; this
0x18013e5c1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013e5c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013e5cd  jb      loc_18013E520
0x18013e5d3  mov     edx, 0Dh
0x18013e5d8  jmp     loc_18013E502
0x18013e5dd  lea     rcx, [rbp+arg_0]; void *
0x18013e5e1  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18013e5e6  cmp     [rdi+648h], r12
0x18013e5ed  jz      loc_18013E741
0x18013e5f3  lea     rcx, [rbp+ppMFType]; ppMFType
0x18013e5f7  call    cs:__imp_MFCreateMediaType
0x18013e5fd  mov     ebx, eax
0x18013e5ff  test    eax, eax
0x18013e601  jns     loc_18013E692
0x18013e607  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e60e  test    rcx, rcx
0x18013e611  jnz     short loc_18013E654
0x18013e613  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013e619  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e620  mov     rcx, rax
0x18013e623  test    rax, rax
0x18013e626  jz      short loc_18013E646
0x18013e628  mov     rax, [rax]
0x18013e62b  mov     edx, 7F0h
0x18013e630  mov     rax, [rax+8]
0x18013e634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013e639  test    eax, eax
0x18013e63b  jz      short loc_18013E646
0x18013e63d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e644  jmp     short loc_18013E654
0x18013e646  lea     rcx, qword_1801B07E0; this
0x18013e64d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e654  cmp     [rcx+8], r12b
0x18013e658  jz      short loc_18013E67B
0x18013e65a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013e65f  cmp     [rax+7CCh], ebx
0x18013e665  jz      short loc_18013E67B
0x18013e667  mov     r9d, ebx; int
0x18013e66a  mov     r8d, 71h ; 'q'; int
0x18013e670  mov     rdx, r13; char *
0x18013e673  mov     rcx, rax; this
0x18013e676  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013e67b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013e682  jb      loc_18013E8B9
0x18013e688  mov     edx, 0Eh
0x18013e68d  jmp     loc_18013E3DC
0x18013e692  mov     rdx, [rdi+648h]; pWaveFormat
0x18013e699  mov     rcx, [rbp+ppMFType]; pMFType
0x18013e69d  movzx   r8d, word ptr [rdx+10h]
0x18013e6a2  add     r8d, 12h; cbBufSize
0x18013e6a6  call    cs:__imp_MFInitMediaTypeFromWaveFormatEx
0x18013e6ac  mov     ebx, eax
0x18013e6ae  test    eax, eax
0x18013e6b0  jns     loc_18013E741
0x18013e6b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e6bd  test    rcx, rcx
0x18013e6c0  jnz     short loc_18013E703
0x18013e6c2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013e6c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e6cf  mov     rcx, rax
0x18013e6d2  test    rax, rax
0x18013e6d5  jz      short loc_18013E6F5
0x18013e6d7  mov     rax, [rax]
0x18013e6da  mov     edx, 7F0h
0x18013e6df  mov     rax, [rax+8]
0x18013e6e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013e6e8  test    eax, eax
0x18013e6ea  jz      short loc_18013E6F5
0x18013e6ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e6f3  jmp     short loc_18013E703
0x18013e6f5  lea     rcx, qword_1801B07E0; this
0x18013e6fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e703  cmp     [rcx+8], r12b
0x18013e707  jz      short loc_18013E72A
0x18013e709  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013e70e  cmp     [rax+7CCh], ebx
0x18013e714  jz      short loc_18013E72A
0x18013e716  mov     r9d, ebx; int
0x18013e719  mov     r8d, 72h ; 'r'; int
0x18013e71f  mov     rdx, r13; char *
0x18013e722  mov     rcx, rax; this
0x18013e725  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013e72a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013e731  jb      loc_18013E8B9
0x18013e737  mov     edx, 0Fh
0x18013e73c  jmp     loc_18013E3DC
0x18013e741  cmp     [rdi+650h], r12
0x18013e748  jz      loc_18013E898
0x18013e74e  lea     rcx, [rbp+pMFType]; ppMFType
0x18013e752  call    cs:__imp_MFCreateMediaType
0x18013e758  mov     ebx, eax
0x18013e75a  test    eax, eax
0x18013e75c  jns     loc_18013E7ED
0x18013e762  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e769  test    rcx, rcx
0x18013e76c  jnz     short loc_18013E7AF
0x18013e76e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013e774  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e77b  mov     rcx, rax
0x18013e77e  test    rax, rax
0x18013e781  jz      short loc_18013E7A1
0x18013e783  mov     rax, [rax]
0x18013e786  mov     edx, 7F0h
0x18013e78b  mov     rax, [rax+8]
0x18013e78f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013e794  test    eax, eax
0x18013e796  jz      short loc_18013E7A1
0x18013e798  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e79f  jmp     short loc_18013E7AF
0x18013e7a1  lea     rcx, qword_1801B07E0; this
0x18013e7a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013e7af  cmp     [rcx+8], r12b
0x18013e7b3  jz      short loc_18013E7D6
0x18013e7b5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013e7ba  cmp     [rax+7CCh], ebx
0x18013e7c0  jz      short loc_18013E7D6
0x18013e7c2  mov     r9d, ebx; int
0x18013e7c5  mov     r8d, 77h ; 'w'; int
0x18013e7cb  mov     rdx, r13; char *
0x18013e7ce  mov     rcx, rax; this
0x18013e7d1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013e7d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013e7dd  jb      loc_18013E8B9
0x18013e7e3  mov     edx, 10h
0x18013e7e8  jmp     loc_18013E3DC
0x18013e7ed  mov     rdx, [rdi+650h]; pWaveFormat
0x18013e7f4  mov     rcx, [rbp+pMFType]; pMFType
0x18013e7f8  movzx   r8d, word ptr [rdx+10h]
0x18013e7fd  add     r8d, 12h; cbBufSize
  ... truncated ...
```
