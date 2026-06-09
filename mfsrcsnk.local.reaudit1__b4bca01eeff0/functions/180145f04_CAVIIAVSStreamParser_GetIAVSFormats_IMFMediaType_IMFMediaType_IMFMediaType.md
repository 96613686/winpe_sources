# CAVIIAVSStreamParser::GetIAVSFormats(IMFMediaType * *,IMFMediaType * *,IMFMediaType * *)

- ea: `0x180145f04`
- end: `0x180146541`
- name: `?GetIAVSFormats@CAVIIAVSStreamParser@@QEBAJPEAPEAUIMFMediaType@@00@Z`
- size: `1597`
- prototype: `__int64 __fastcall(CAVIIAVSStreamParser *__hidden this, struct IMFMediaType **, struct IMFMediaType **, struct IMFMediaType **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180054228`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180079680`
- `0x180145f04`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145f6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801460a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180146178`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180146239`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801462f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801463ac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180146467`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145f6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801460a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180146178`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180146239`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801462f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801463ac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180146467`
- `MFPlat!MFCreateVideoMediaTypeFromBitMapInfoHeaderEx` at `0x18014607e`
- `MFPlat!MFCreateVideoMediaTypeFromBitMapInfoHeaderEx` at `0x18014607e`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x1801462d2`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x180146445`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x1801462d2`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x180146445`
- `MFPlat!MFCreateMediaType` at `0x180146217`
- `MFPlat!MFCreateMediaType` at `0x18014638a`
- `MFPlat!MFCreateMediaType` at `0x180146217`
- `MFPlat!MFCreateMediaType` at `0x18014638a`

## pseudocode

```c
__int64 __fastcall CAVIIAVSStreamParser::GetIAVSFormats(
        CAVIIAVSStreamParser *this,
        struct IMFMediaType **a2,
        struct IMFMediaType **a3,
        struct IMFMediaType **a4)
{
  __int64 v8; // rdx
  wchar_t *v9; // rcx
  HRESULT v10; // ebx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  const BITMAPINFOHEADER *v14; // r10
  MFVideoInterlaceMode InterlaceMode; // ecx
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rdx
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
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
  __int64 v37; // rdx
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  IMFMediaType *pMFType; // [rsp+50h] [rbp-28h] BYREF
  IMFMediaType *ppMFType; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v44[3]; // [rsp+60h] [rbp-18h] BYREF
  IMFVideoMediaType *ppIVideoMediaType; // [rsp+C0h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&ppIVideoMediaType,
    "CAVIIAVSStreamParser::GetIAVSFormats",
    69);
  v44[0] = 0;
  ppMFType = 0;
  pMFType = 0;
  if ( !*((_QWORD *)this + 198) )
  {
    v9 = (wchar_t *)CallStackTracing::s_wpInstance;
    v10 = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v9 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875854 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIIAVSStreamParser::GetIAVSFormats", 76, -1072875854);
    }
    if ( g_wppLevels )
    {
      v13 = 11;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids, this, v10);
      goto LABEL_89;
    }
    goto LABEL_89;
  }
  v14 = (const BITMAPINFOHEADER *)*((_QWORD *)this + 80);
  v10 = 0;
  if ( v14 )
  {
    ppIVideoMediaType = 0;
    if ( *((_DWORD *)this + 399) )
      InterlaceMode = (*((_DWORD *)this + 400) != 0) + 5;
    else
      InterlaceMode = MFVideoInterlace_Progressive;
    v10 = MFCreateVideoMediaTypeFromBitMapInfoHeaderEx(
            v14,
            v14->biSize,
            *((unsigned __int16 *)this + 796),
            *((unsigned __int16 *)this + 797),
            InterlaceMode,
            0,
            *((_DWORD *)this + 8),
            *((_DWORD *)this + 7),
            0,
            &ppIVideoMediaType);
    if ( v10 < 0 )
    {
      v17 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != v10 )
          CallStackContext::TraceFailure(v19, "CAVIIAVSStreamParser::GetIAVSFormats", 107, v10);
      }
      if ( !g_wppLevels )
        goto LABEL_29;
      v20 = 12;
LABEL_28:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids, this, v10);
LABEL_29:
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppIVideoMediaType);
      goto LABEL_89;
    }
    v10 = ((__int64 (__fastcall *)(IMFVideoMediaType *, GUID *, _QWORD *))ppIVideoMediaType->lpVtbl->QueryInterface)(
            ppIVideoMediaType,
            &IID_IMFMediaType,
            v44);
    if ( v10 < 0 )
    {
      v22 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
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
        if ( *((_DWORD *)v24 + 499) != v10 )
          CallStackContext::TraceFailure(v24, "CAVIIAVSStreamParser::GetIAVSFormats", 108, v10);
      }
      if ( !g_wppLevels )
        goto LABEL_29;
      v20 = 13;
      goto LABEL_28;
    }
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppIVideoMediaType);
  }
  if ( !*((_QWORD *)this + 201) )
  {
LABEL_65:
    if ( *((_QWORD *)this + 202) )
    {
      v10 = MFCreateMediaType(&pMFType);
      if ( v10 < 0 )
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
          if ( *((_DWORD *)v36 + 499) != v10 )
            CallStackContext::TraceFailure(v36, "CAVIIAVSStreamParser::GetIAVSFormats", 119, v10);
        }
        if ( g_wppLevels )
        {
          v13 = 16;
          goto LABEL_12;
        }
        goto LABEL_89;
      }
      v10 = MFInitMediaTypeFromWaveFormatEx(
              pMFType,
              *((const WAVEFORMATEX **)this + 202),
              *(unsigned __int16 *)(*((_QWORD *)this + 202) + 16LL) + 18);
      if ( v10 < 0 )
      {
        v38 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
          CallStackTracing::s_wpInstance = v39;
          if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
          {
            v38 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v38 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v38 + 8) )
        {
          v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
          if ( *((_DWORD *)v40 + 499) != v10 )
            CallStackContext::TraceFailure(v40, "CAVIIAVSStreamParser::GetIAVSFormats", 120, v10);
        }
        if ( g_wppLevels )
        {
          v13 = 17;
          goto LABEL_12;
        }
        goto LABEL_89;
      }
    }
    *a2 = (struct IMFMediaType *)v44[0];
    *a3 = ppMFType;
    *a4 = pMFType;
    v44[0] = 0;
    ppMFType = 0;
    pMFType = 0;
    goto LABEL_89;
  }
  v10 = MFCreateMediaType(&ppMFType);
  if ( v10 >= 0 )
  {
    v10 = MFInitMediaTypeFromWaveFormatEx(
            ppMFType,
            *((const WAVEFORMATEX **)this + 201),
            *(unsigned __int16 *)(*((_QWORD *)this + 201) + 16LL) + 18);
    if ( v10 < 0 )
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
        if ( *((_DWORD *)v32 + 499) != v10 )
          CallStackContext::TraceFailure(v32, "CAVIIAVSStreamParser::GetIAVSFormats", 114, v10);
      }
      if ( g_wppLevels )
      {
        v13 = 15;
        goto LABEL_12;
      }
      goto LABEL_89;
    }
    goto LABEL_65;
  }
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
    if ( *((_DWORD *)v28 + 499) != v10 )
      CallStackContext::TraceFailure(v28, "CAVIIAVSStreamParser::GetIAVSFormats", 113, v10);
  }
  if ( g_wppLevels )
  {
    v13 = 14;
    goto LABEL_12;
  }
LABEL_89:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&pMFType);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppMFType);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v44);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&ppIVideoMediaType);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180145f04  push    rbp
0x180145f06  push    rbx
0x180145f07  push    rsi
0x180145f08  push    rdi
0x180145f09  push    r12
0x180145f0b  push    r13
0x180145f0d  push    r14
0x180145f0f  push    r15
0x180145f11  mov     rbp, rsp
0x180145f14  sub     rsp, 78h
0x180145f18  mov     r14, r8
0x180145f1b  lea     r13, aCaviiavsstream; "CAVIIAVSStreamParser::GetIAVSFormats"
0x180145f22  mov     r15, rdx
0x180145f25  mov     rdi, rcx
0x180145f28  mov     rdx, r13; char *
0x180145f2b  lea     rcx, [rbp+arg_0]; this
0x180145f2f  mov     r8d, 45h ; 'E'; int
0x180145f35  mov     rsi, r9
0x180145f38  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180145f3d  xor     r12d, r12d
0x180145f40  mov     [rbp+var_18], r12
0x180145f44  mov     [rbp+ppMFType], r12
0x180145f48  mov     [rbp+pMFType], r12
0x180145f4c  cmp     [rdi+630h], r12
0x180145f53  jnz     loc_18014600D
0x180145f59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145f60  mov     ebx, 0C00D36B2h
0x180145f65  test    rcx, rcx
0x180145f68  jnz     short loc_180145FB1
0x180145f6a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180145f71  nop     dword ptr [rax+rax+00h]
0x180145f76  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180145f7d  mov     rcx, rax
0x180145f80  test    rax, rax
0x180145f83  jz      short loc_180145FA3
0x180145f85  mov     rax, [rax]
0x180145f88  mov     edx, 7F0h
0x180145f8d  mov     rax, [rax+8]
0x180145f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145f96  test    eax, eax
0x180145f98  jz      short loc_180145FA3
0x180145f9a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145fa1  jmp     short loc_180145FB1
0x180145fa3  lea     rcx, qword_1801B97E0; this
0x180145faa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180145fb1  cmp     [rcx+8], r12b
0x180145fb5  jz      short loc_180145FD8
0x180145fb7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180145fbc  cmp     [rax+7CCh], ebx
0x180145fc2  jz      short loc_180145FD8
0x180145fc4  mov     r9d, ebx; int
0x180145fc7  mov     r8d, 4Ch ; 'L'; int
0x180145fcd  mov     rdx, r13; char *
0x180145fd0  mov     rcx, rax; this
0x180145fd3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180145fd8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180145fdf  jb      loc_180146509
0x180145fe5  mov     edx, 0Bh
0x180145fea  mov     rcx, cs:WPP_GLOBAL_Control
0x180145ff1  lea     r8, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids
0x180145ff8  mov     r9, rdi
0x180145ffb  mov     [rsp+78h+InterlaceMode], ebx
0x180145fff  mov     rcx, [rcx+10h]
0x180146003  call    WPP_SF_qD
0x180146008  jmp     loc_180146509
0x18014600d  mov     r10, [rdi+280h]
0x180146014  mov     ebx, r12d
0x180146017  test    r10, r10
0x18014601a  jz      loc_180146206
0x180146020  mov     [rbp+arg_0], r12
0x180146024  cmp     [rdi+63Ch], r12d
0x18014602b  jz      short loc_18014603E
0x18014602d  mov     eax, [rdi+640h]
0x180146033  neg     eax
0x180146035  sbb     ecx, ecx
0x180146037  neg     ecx
0x180146039  add     ecx, 5
0x18014603c  jmp     short loc_180146043
0x18014603e  mov     ecx, 2
0x180146043  movzx   r9d, word ptr [rdi+63Ah]; dwPixelAspectRatioY
0x18014604b  lea     rax, [rbp+arg_0]
0x18014604f  movzx   r8d, word ptr [rdi+638h]; dwPixelAspectRatioX
0x180146057  mov     edx, [r10]; cbBitMapInfoHeader
0x18014605a  mov     [rsp+78h+ppIVideoMediaType], rax; ppIVideoMediaType
0x18014605f  mov     eax, [rdi+1Ch]
0x180146062  mov     [rsp+78h+dwMaxBitRate], r12d; dwMaxBitRate
0x180146067  mov     [rsp+78h+dwFramesPerSecondDenominator], eax; dwFramesPerSecondDenominator
0x18014606b  mov     eax, [rdi+20h]
0x18014606e  mov     [rsp+78h+dwFramesPerSecondNumerator], eax; dwFramesPerSecondNumerator
0x180146072  mov     [rsp+78h+VideoFlags], r12; VideoFlags
0x180146077  mov     [rsp+78h+InterlaceMode], ecx; InterlaceMode
0x18014607b  mov     rcx, r10; pbmihBitMapInfoHeader
0x18014607e  call    cs:__imp_MFCreateVideoMediaTypeFromBitMapInfoHeaderEx
0x180146085  nop     dword ptr [rax+rax+00h]
0x18014608a  mov     ebx, eax
0x18014608c  test    eax, eax
0x18014608e  jns     loc_180146148
0x180146094  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014609b  test    rcx, rcx
0x18014609e  jnz     short loc_1801460E7
0x1801460a0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801460a7  nop     dword ptr [rax+rax+00h]
0x1801460ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801460b3  mov     rcx, rax
0x1801460b6  test    rax, rax
0x1801460b9  jz      short loc_1801460D9
0x1801460bb  mov     rax, [rax]
0x1801460be  mov     edx, 7F0h
0x1801460c3  mov     rax, [rax+8]
0x1801460c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801460cc  test    eax, eax
0x1801460ce  jz      short loc_1801460D9
0x1801460d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801460d7  jmp     short loc_1801460E7
0x1801460d9  lea     rcx, qword_1801B97E0; this
0x1801460e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801460e7  cmp     [rcx+8], r12b
0x1801460eb  jz      short loc_18014610E
0x1801460ed  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801460f2  cmp     [rax+7CCh], ebx
0x1801460f8  jz      short loc_18014610E
0x1801460fa  mov     r9d, ebx; int
0x1801460fd  mov     r8d, 6Bh ; 'k'; int
0x180146103  mov     rdx, r13; char *
0x180146106  mov     rcx, rax; this
0x180146109  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014610e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180146115  jb      short loc_18014613A
0x180146117  mov     edx, 0Ch
0x18014611c  mov     rcx, cs:WPP_GLOBAL_Control
0x180146123  lea     r8, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids
0x18014612a  mov     r9, rdi
0x18014612d  mov     [rsp+78h+InterlaceMode], ebx
0x180146131  mov     rcx, [rcx+10h]
0x180146135  call    WPP_SF_qD
0x18014613a  lea     rcx, [rbp+arg_0]; void *
0x18014613e  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180146143  jmp     loc_180146509
0x180146148  mov     rcx, [rbp+arg_0]
0x18014614c  lea     r8, [rbp+var_18]
0x180146150  lea     rdx, IID_IMFMediaType
0x180146157  mov     rax, [rcx]
0x18014615a  mov     rax, [rax]
0x18014615d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146162  mov     ebx, eax
0x180146164  test    eax, eax
0x180146166  jns     loc_1801461FD
0x18014616c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180146173  test    rcx, rcx
0x180146176  jnz     short loc_1801461BF
0x180146178  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014617f  nop     dword ptr [rax+rax+00h]
0x180146184  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014618b  mov     rcx, rax
0x18014618e  test    rax, rax
0x180146191  jz      short loc_1801461B1
0x180146193  mov     rax, [rax]
0x180146196  mov     edx, 7F0h
0x18014619b  mov     rax, [rax+8]
0x18014619f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801461a4  test    eax, eax
0x1801461a6  jz      short loc_1801461B1
0x1801461a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801461af  jmp     short loc_1801461BF
0x1801461b1  lea     rcx, qword_1801B97E0; this
0x1801461b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801461bf  cmp     [rcx+8], r12b
0x1801461c3  jz      short loc_1801461E6
0x1801461c5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801461ca  cmp     [rax+7CCh], ebx
0x1801461d0  jz      short loc_1801461E6
0x1801461d2  mov     r9d, ebx; int
0x1801461d5  mov     r8d, 6Ch ; 'l'; int
0x1801461db  mov     rdx, r13; char *
0x1801461de  mov     rcx, rax; this
0x1801461e1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801461e6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801461ed  jb      loc_18014613A
0x1801461f3  mov     edx, 0Dh
0x1801461f8  jmp     loc_18014611C
0x1801461fd  lea     rcx, [rbp+arg_0]; void *
0x180146201  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180146206  cmp     [rdi+648h], r12
0x18014620d  jz      loc_180146379
0x180146213  lea     rcx, [rbp+ppMFType]; ppMFType
0x180146217  call    cs:__imp_MFCreateMediaType
0x18014621e  nop     dword ptr [rax+rax+00h]
0x180146223  mov     ebx, eax
0x180146225  test    eax, eax
0x180146227  jns     loc_1801462BE
0x18014622d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180146234  test    rcx, rcx
0x180146237  jnz     short loc_180146280
0x180146239  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180146240  nop     dword ptr [rax+rax+00h]
0x180146245  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014624c  mov     rcx, rax
0x18014624f  test    rax, rax
0x180146252  jz      short loc_180146272
0x180146254  mov     rax, [rax]
0x180146257  mov     edx, 7F0h
0x18014625c  mov     rax, [rax+8]
0x180146260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146265  test    eax, eax
0x180146267  jz      short loc_180146272
0x180146269  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180146270  jmp     short loc_180146280
0x180146272  lea     rcx, qword_1801B97E0; this
0x180146279  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180146280  cmp     [rcx+8], r12b
0x180146284  jz      short loc_1801462A7
0x180146286  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014628b  cmp     [rax+7CCh], ebx
0x180146291  jz      short loc_1801462A7
0x180146293  mov     r9d, ebx; int
0x180146296  mov     r8d, 71h ; 'q'; int
0x18014629c  mov     rdx, r13; char *
0x18014629f  mov     rcx, rax; this
0x1801462a2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801462a7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801462ae  jb      loc_180146509
0x1801462b4  mov     edx, 0Eh
0x1801462b9  jmp     loc_180145FEA
0x1801462be  mov     rdx, [rdi+648h]; pWaveFormat
0x1801462c5  mov     rcx, [rbp+ppMFType]; pMFType
0x1801462c9  movzx   r8d, word ptr [rdx+10h]
0x1801462ce  add     r8d, 12h; cbBufSize
0x1801462d2  call    cs:__imp_MFInitMediaTypeFromWaveFormatEx
0x1801462d9  nop     dword ptr [rax+rax+00h]
0x1801462de  mov     ebx, eax
0x1801462e0  test    eax, eax
0x1801462e2  jns     loc_180146379
0x1801462e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801462ef  test    rcx, rcx
0x1801462f2  jnz     short loc_18014633B
0x1801462f4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801462fb  nop     dword ptr [rax+rax+00h]
0x180146300  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180146307  mov     rcx, rax
0x18014630a  test    rax, rax
0x18014630d  jz      short loc_18014632D
0x18014630f  mov     rax, [rax]
0x180146312  mov     edx, 7F0h
0x180146317  mov     rax, [rax+8]
0x18014631b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146320  test    eax, eax
0x180146322  jz      short loc_18014632D
0x180146324  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014632b  jmp     short loc_18014633B
0x18014632d  lea     rcx, qword_1801B97E0; this
0x180146334  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014633b  cmp     [rcx+8], r12b
0x18014633f  jz      short loc_180146362
0x180146341  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180146346  cmp     [rax+7CCh], ebx
0x18014634c  jz      short loc_180146362
0x18014634e  mov     r9d, ebx; int
0x180146351  mov     r8d, 72h ; 'r'; int
0x180146357  mov     rdx, r13; char *
0x18014635a  mov     rcx, rax; this
0x18014635d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180146362  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180146369  jb      loc_180146509
0x18014636f  mov     edx, 0Fh
0x180146374  jmp     loc_180145FEA
0x180146379  cmp     [rdi+650h], r12
0x180146380  jz      loc_1801464E8
0x180146386  lea     rcx, [rbp+pMFType]; ppMFType
0x18014638a  call    cs:__imp_MFCreateMediaType
0x180146391  nop     dword ptr [rax+rax+00h]
0x180146396  mov     ebx, eax
0x180146398  test    eax, eax
0x18014639a  jns     loc_180146431
0x1801463a0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801463a7  test    rcx, rcx
0x1801463aa  jnz     short loc_1801463F3
0x1801463ac  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801463b3  nop     dword ptr [rax+rax+00h]
0x1801463b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801463bf  mov     rcx, rax
0x1801463c2  test    rax, rax
0x1801463c5  jz      short loc_1801463E5
0x1801463c7  mov     rax, [rax]
0x1801463ca  mov     edx, 7F0h
0x1801463cf  mov     rax, [rax+8]
0x1801463d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801463d8  test    eax, eax
0x1801463da  jz      short loc_1801463E5
0x1801463dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801463e3  jmp     short loc_1801463F3
0x1801463e5  lea     rcx, qword_1801B97E0; this
0x1801463ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801463f3  cmp     [rcx+8], r12b
0x1801463f7  jz      short loc_18014641A
0x1801463f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801463fe  cmp     [rax+7CCh], ebx
0x180146404  jz      short loc_18014641A
0x180146406  mov     r9d, ebx; int
0x180146409  mov     r8d, 77h ; 'w'; int
0x18014640f  mov     rdx, r13; char *
  ... truncated ...
```
