# MkvMfSourceLib::MkvMfStream::RuntimeClassInitialize(MkvMfSourceLib::MkvMfSource *,mkvparser::Track const *)

- ea: `0x180025470`
- end: `0x180025c0e`
- name: `?RuntimeClassInitialize@MkvMfStream@MkvMfSourceLib@@UEAAJPEAVMkvMfSource@2@PEBVTrack@mkvparser@@@Z`
- size: `1950`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStream *__hidden this, struct MkvMfSourceLib::MkvMfSource *, const struct mkvparser::Track *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180037170`
- `0x180037310`

## callees

- `0x180001fd0`
- `0x180005ab8`
- `0x1800066a4`
- `0x180007e1c`
- `0x1800090dc`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180014814`
- `0x180020d84`
- `0x180025470`
- `0x18004613c`
- `0x180071330`
- `0x180084b34`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800254bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002555f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002565e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002584b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025984`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025ac4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800254bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002555f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002565e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002584b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025984`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025ac4`
- `MFPlat!MFCreateEventQueue` at `0x180025642`
- `MFPlat!MFCreateEventQueue` at `0x180025642`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MkvMfSourceLib::MkvMfStream::RuntimeClassInitialize(
        MkvMfSourceLib::MkvMfStream *this,
        struct MkvMfSourceLib::MkvMfSource *a2,
        const struct mkvparser::Track *a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  HRESULT v12; // ebx
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  volatile int *v17; // rdx
  __int64 v18; // r10
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 result; // rax
  __int64 v26; // rbx
  const char *v27; // rdx
  _QWORD *v28; // r9
  __int64 v29; // rcx
  __int64 v30; // rax
  unsigned int v31; // r8d
  __int64 *v32; // rcx
  __int64 v33; // r10
  __int64 v34; // r11
  _DWORD *v35; // rcx
  const CHAR *v36; // rcx
  unsigned __int16 *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // r8
  const char *v45; // rdx
  const CHAR *v46; // rcx
  unsigned __int16 *v47; // rax
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  __int64 *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  __int64 v54; // r8
  const char *v55; // rdx
  const CHAR *v56; // rcx
  unsigned __int16 *v57; // rax
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  const char *v64; // r9
  void *v65; // [rsp+30h] [rbp-48h] BYREF
  void *v66[4]; // [rsp+38h] [rbp-40h] BYREF
  char v67; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v69; // [rsp+88h] [rbp+10h] BYREF
  void *Block; // [rsp+98h] [rbp+20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v69,
    "MkvMfSourceLib::MkvMfStream::RuntimeClassInitialize",
    52);
  if ( !a2 )
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      v12 = -2147467261;
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "MkvMfSourceLib::MkvMfStream::RuntimeClassInitialize",
          52,
          -2147467261);
    }
    else
    {
      v12 = -2147467261;
    }
    if ( !g_wppLevels )
      goto LABEL_41;
    v13 = 10;
LABEL_40:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v12);
LABEL_41:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v69);
    return (unsigned int)v12;
  }
  if ( !a3 )
  {
    v14 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7, v8);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      v12 = -2147467261;
      if ( *((_DWORD *)v16 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v16, "MkvMfSourceLib::MkvMfStream::RuntimeClassInitialize", 53, -2147467261);
    }
    else
    {
      v12 = -2147467261;
    }
    if ( !g_wppLevels )
      goto LABEL_41;
    v13 = 11;
    goto LABEL_40;
  }
  Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfSource>::operator=((char *)this + 56, a2);
  *((_QWORD *)this + 9) = a3;
  v18 = *((_QWORD *)a2 + 85);
  if ( *((_QWORD *)this + 52) != v18 )
  {
    if ( v18 )
      Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(v18 + 12), v17);
    v69 = *((_QWORD *)this + 52);
    *((_QWORD *)this + 52) = v18;
    Microsoft::WRL::ComPtr<MkvSourceTelemetryLogger>::InternalRelease(&v69);
  }
  v12 = MFCreateEventQueue((IMFMediaEventQueue **)this + 56);
  if ( v12 < 0 )
  {
    v22 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
      CallStackTracing::s_wpInstance = v23;
      if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v22 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v22 + 8) )
    {
      v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
      if ( *((_DWORD *)v24 + 499) != v12 )
        CallStackContext::TraceFailure(v24, "MkvMfSourceLib::MkvMfStream::RuntimeClassInitialize", 59, v12);
    }
    if ( !g_wppLevels )
      goto LABEL_41;
    v13 = 12;
    goto LABEL_40;
  }
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  v26 = -1;
  *((_DWORD *)this + 44) = -1;
  *((_QWORD *)this + 23) = 0;
  *((_BYTE *)this + 224) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 39) = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 320);
  v28 = (_QWORD *)*((_QWORD *)this + 9);
  v29 = v28[21];
  v30 = (v28[22] - v29) >> 3;
  if ( (_DWORD)v30 )
  {
    v31 = 0;
    do
    {
      if ( *((_QWORD *)this + 39) )
        break;
      if ( v31 < (unsigned int)v30 )
      {
        v32 = *(__int64 **)(v29 + 8LL * v31);
        if ( v32 )
        {
          if ( v32[5] == 1 )
          {
            v27 = 0;
            v33 = *v32;
            v34 = v32[1];
            while ( (unsigned int)v27 < (unsigned int)((v34 - v33) >> 3) )
            {
              v35 = *(_DWORD **)(v33 + 8LL * (unsigned int)v27);
              if ( v35 && (*v35 == 3 || !*v35) )
              {
                *((_QWORD *)this + 39) = v35;
                break;
              }
              v27 = (const char *)(unsigned int)((_DWORD)v27 + 1);
            }
          }
        }
      }
      ++v31;
      v29 = v28[21];
      v30 = (v28[22] - v29) >> 3;
    }
    while ( v31 < (unsigned int)v30 );
  }
  try
  {
    Block = 0;
    v65 = 0;
    v66[0] = 0;
    v66[1] = &Block;
    v66[2] = &v65;
    v66[3] = v66;
    v67 = 1;
    v36 = (const CHAR *)v28[9];
    if ( v36 )
    {
      v37 = mkvparser::ConvertFromUTF8(v36, v27);
      Block = v37;
      if ( !v37 )
      {
        v41 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39, v40);
          CallStackTracing::s_wpInstance = v42;
          if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
          {
            v41 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v41 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v41 + 8) )
        {
          v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
          if ( *((_DWORD *)v43 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v43, "MkvMfSourceLib::MkvMfStream::RuntimeClassInitialize", 103, -2147024882);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
            this,
            -2147024882);
LABEL_101:
        operator delete(Block);
        operator delete(v65);
        operator delete(v66[0]);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v69);
        return 2147942414LL;
      }
      v44 = -1;
      do
        ++v44;
      while ( v37[v44] );
      std::wstring::_Assign<unsigned short>((char *)this + 80, v37);
    }
    std::wstring::_Assign<unsigned short>((char *)this + 112, L"en");
    v46 = *(const CHAR **)(*((_QWORD *)this + 9) + 80LL);
    if ( v46 )
    {
      v47 = mkvparser::ConvertFromUTF8(v46, v45);
      v65 = v47;
      if ( !v47 )
      {
        v51 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48, v49, v50);
          CallStackTracing::s_wpInstance = v52;
          if ( v52 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
          {
            v51 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v51 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v51 + 8) )
        {
          v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
          if ( *((_DWORD *)v53 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v53, "MkvMfSourceLib::MkvMfStream::RuntimeClassInitialize", 112, -2147024882);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
            this,
            -2147024882);
        goto LABEL_101;
      }
      v54 = -1;
      do
        ++v54;
      while ( v47[v54] );
      std::wstring::_Assign<unsigned short>((char *)this + 112, v47);
      MkvMfSourceLib::ConvertMKVLanguageStringToRFC1766((char *)this + 112);
    }
    std::wstring::_Assign<unsigned short>((char *)this + 144, &word_1800B72F8);
    v56 = *(const CHAR **)(*((_QWORD *)this + 9) + 88LL);
    if ( v56 )
    {
      v57 = mkvparser::ConvertFromUTF8(v56, v55);
      v66[0] = v57;
      if ( !v57 )
      {
        v61 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58, v59, v60);
          CallStackTracing::s_wpInstance = v62;
          if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
          {
            v61 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v61 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v61 + 8) )
        {
          v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
          if ( *((_DWORD *)v63 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v63, "MkvMfSourceLib::MkvMfStream::RuntimeClassInitialize", 122, -2147024882);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
            this,
            -2147024882);
        goto LABEL_101;
      }
      do
        ++v26;
      while ( v57[v26] );
      std::wstring::_Assign<unsigned short>((char *)this + 144, v57);
    }
    operator delete(Block);
    operator delete(v65);
    operator delete(v66[0]);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v69);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(Block) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x7E,
                       (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvmfstream.cpp",
                       v64);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v69);
    return (unsigned int)Block;
  }
  return result;
}

```

## disassembly

```asm
0x180025470  mov     rax, rsp
0x180025473  mov     [rax+8], rbx
0x180025477  mov     [rax+18h], rsi
0x18002547b  push    rdi
0x18002547c  push    r12
0x18002547e  push    r14
0x180025480  sub     rsp, 60h
0x180025484  mov     rsi, r8
0x180025487  mov     rbx, rdx
0x18002548a  mov     rdi, rcx
0x18002548d  mov     r8d, 34h ; '4'; int
0x180025493  lea     r12, aMkvmfsourcelib_7; "MkvMfSourceLib::MkvMfStream::RuntimeCla"...
0x18002549a  mov     rdx, r12; char *
0x18002549d  lea     rcx, [rax+10h]; this
0x1800254a1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800254a6  nop
0x1800254a7  xor     r14d, r14d
0x1800254aa  test    rbx, rbx
0x1800254ad  jnz     loc_18002554A
0x1800254b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800254ba  test    rcx, rcx
0x1800254bd  jnz     short loc_180025500
0x1800254bf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800254c5  mov     rcx, rax
0x1800254c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800254cf  test    rax, rax
0x1800254d2  jz      short loc_1800254F2
0x1800254d4  mov     rax, [rax]
0x1800254d7  mov     edx, 7F0h
0x1800254dc  mov     rax, [rax+8]
0x1800254e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254e5  test    eax, eax
0x1800254e7  jz      short loc_1800254F2
0x1800254e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800254f0  jmp     short loc_180025500
0x1800254f2  lea     rcx, qword_1800D6F70; this
0x1800254f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180025500  cmp     [rcx+8], r14b
0x180025504  jz      short loc_18002552E
0x180025506  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002550b  mov     ebx, 80004003h
0x180025510  cmp     [rax+7CCh], ebx
0x180025516  jz      short loc_180025533
0x180025518  mov     r9d, ebx; int
0x18002551b  mov     r8d, 34h ; '4'; int
0x180025521  mov     rdx, r12; char *
0x180025524  mov     rcx, rax; this
0x180025527  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002552c  jmp     short loc_180025533
0x18002552e  mov     ebx, 80004003h
0x180025533  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002553a  jb      loc_1800256F3
0x180025540  mov     edx, 0Ah
0x180025545  jmp     loc_1800256D4
0x18002554a  test    rsi, rsi
0x18002554d  jnz     loc_1800255EA
0x180025553  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002555a  test    rcx, rcx
0x18002555d  jnz     short loc_1800255A0
0x18002555f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180025565  mov     rcx, rax
0x180025568  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002556f  test    rax, rax
0x180025572  jz      short loc_180025592
0x180025574  mov     rax, [rax]
0x180025577  mov     edx, 7F0h
0x18002557c  mov     rax, [rax+8]
0x180025580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025585  test    eax, eax
0x180025587  jz      short loc_180025592
0x180025589  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025590  jmp     short loc_1800255A0
0x180025592  lea     rcx, qword_1800D6F70; this
0x180025599  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800255a0  cmp     [rcx+8], r14b
0x1800255a4  jz      short loc_1800255CE
0x1800255a6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800255ab  mov     ebx, 80004003h
0x1800255b0  cmp     [rax+7CCh], ebx
0x1800255b6  jz      short loc_1800255D3
0x1800255b8  mov     r9d, ebx; int
0x1800255bb  mov     r8d, 35h ; '5'; int
0x1800255c1  mov     rdx, r12; char *
0x1800255c4  mov     rcx, rax; this
0x1800255c7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800255cc  jmp     short loc_1800255D3
0x1800255ce  mov     ebx, 80004003h
0x1800255d3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800255da  jb      loc_1800256F3
0x1800255e0  mov     edx, 0Bh
0x1800255e5  jmp     loc_1800256D4
0x1800255ea  lea     rcx, [rdi+38h]
0x1800255ee  mov     rdx, rbx
0x1800255f1  call    ??4?$ComPtr@VMkvMfSource@MkvMfSourceLib@@@WRL@Microsoft@@QEAAAEAV012@PEAVMkvMfSource@MkvMfSourceLib@@@Z; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfSource>::operator=(MkvMfSourceLib::MkvMfSource *)
0x1800255f6  mov     [rdi+48h], rsi
0x1800255fa  mov     r10, [rbx+2A8h]
0x180025601  cmp     [rdi+1A0h], r10
0x180025608  jz      short loc_18002563B
0x18002560a  test    r10, r10
0x18002560d  jz      short loc_180025618
0x18002560f  lea     rcx, [r10+0Ch]; this
0x180025613  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180025618  mov     rax, [rdi+1A0h]
0x18002561f  mov     [rsp+78h+arg_8], rax
0x180025627  mov     [rdi+1A0h], r10
0x18002562e  lea     rcx, [rsp+78h+arg_8]
0x180025636  call    ?InternalRelease@?$ComPtr@VMkvSourceTelemetryLogger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<MkvSourceTelemetryLogger>::InternalRelease(void)
0x18002563b  lea     rcx, [rdi+1C0h]; ppMediaEventQueue
0x180025642  call    cs:__imp_MFCreateEventQueue
0x180025648  mov     ebx, eax
0x18002564a  test    eax, eax
0x18002564c  jns     loc_180025707
0x180025652  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025659  test    rcx, rcx
0x18002565c  jnz     short loc_18002569F
0x18002565e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180025664  mov     rcx, rax
0x180025667  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002566e  test    rax, rax
0x180025671  jz      short loc_180025691
0x180025673  mov     rax, [rax]
0x180025676  mov     edx, 7F0h
0x18002567b  mov     rax, [rax+8]
0x18002567f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025684  test    eax, eax
0x180025686  jz      short loc_180025691
0x180025688  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002568f  jmp     short loc_18002569F
0x180025691  lea     rcx, qword_1800D6F70; this
0x180025698  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002569f  cmp     [rcx+8], r14b
0x1800256a3  jz      short loc_1800256C6
0x1800256a5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800256aa  cmp     [rax+7CCh], ebx
0x1800256b0  jz      short loc_1800256C6
0x1800256b2  mov     r9d, ebx; int
0x1800256b5  mov     r8d, 3Bh ; ';'; int
0x1800256bb  mov     rdx, r12; char *
0x1800256be  mov     rcx, rax; this
0x1800256c1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800256c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800256cd  jb      short loc_1800256F3
0x1800256cf  mov     edx, 0Ch
0x1800256d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256db  mov     [rsp+78h+var_58], ebx
0x1800256df  mov     r9, rdi
0x1800256e2  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x1800256e9  mov     rcx, [rcx+10h]
0x1800256ed  call    WPP_SF_qD
0x1800256f2  nop
0x1800256f3  lea     rcx, [rsp+78h+arg_8]; this
0x1800256fb  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180025700  mov     eax, ebx
0x180025702  jmp     loc_180025BF8
0x180025707  mov     [rdi+0C0h], r14
0x18002570e  mov     [rdi+0C8h], r14
0x180025715  mov     [rdi+0D0h], r14
0x18002571c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180025720  mov     [rdi+0B0h], ebx
0x180025726  mov     [rdi+0B8h], r14
0x18002572d  mov     [rdi+0E0h], r14b
0x180025734  mov     [rdi+0D8h], r14
0x18002573b  mov     [rdi+138h], r14
0x180025742  lea     rcx, [rdi+140h]
0x180025749  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002574e  mov     r9, [rdi+48h]
0x180025752  mov     rcx, [r9+0A8h]
0x180025759  mov     rax, [r9+0B0h]
0x180025760  sub     rax, rcx
0x180025763  sar     rax, 3
0x180025767  test    eax, eax
0x180025769  jz      short loc_1800257E4
0x18002576b  mov     r8d, r14d
0x18002576e  cmp     [rdi+138h], r14
0x180025775  jnz     short loc_1800257E4
0x180025777  cmp     r8d, eax
0x18002577a  jnb     short loc_1800257C7
0x18002577c  mov     eax, r8d
0x18002577f  mov     rcx, [rcx+rax*8]
0x180025783  test    rcx, rcx
0x180025786  jz      short loc_1800257C7
0x180025788  cmp     qword ptr [rcx+28h], 1
0x18002578d  jnz     short loc_1800257C7
0x18002578f  mov     edx, r14d; char *
0x180025792  mov     r10, [rcx]
0x180025795  mov     r11, [rcx+8]
0x180025799  mov     rax, r11
0x18002579c  sub     rax, r10
0x18002579f  sar     rax, 3
0x1800257a3  cmp     edx, eax
0x1800257a5  jnb     short loc_1800257C7
0x1800257a7  mov     eax, edx
0x1800257a9  mov     rcx, [r10+rax*8]
0x1800257ad  test    rcx, rcx
0x1800257b0  jz      short loc_1800257BC
0x1800257b2  cmp     dword ptr [rcx], 3
0x1800257b5  jz      short loc_1800257C0
0x1800257b7  cmp     [rcx], r14d
0x1800257ba  jz      short loc_1800257C0
0x1800257bc  inc     edx
0x1800257be  jmp     short loc_180025799
0x1800257c0  mov     [rdi+138h], rcx
0x1800257c7  inc     r8d
0x1800257ca  mov     rcx, [r9+0A8h]
0x1800257d1  mov     rax, [r9+0B0h]
0x1800257d8  sub     rax, rcx
0x1800257db  sar     rax, 3
0x1800257df  cmp     r8d, eax
0x1800257e2  jb      short loc_18002576E
0x1800257e4  mov     [rsp+78h+Block], r14
0x1800257ec  mov     [rsp+78h+var_48], r14
0x1800257f1  mov     [rsp+78h+var_40], r14
0x1800257f6  lea     rax, [rsp+78h+Block]
0x1800257fe  mov     [rsp+78h+var_38], rax
0x180025803  lea     rax, [rsp+78h+var_48]
0x180025808  mov     [rsp+78h+var_30], rax
0x18002580d  lea     rax, [rsp+78h+var_40]
0x180025812  mov     [rsp+78h+var_28], rax
0x180025817  mov     [rsp+78h+var_20], 1
0x18002581c  mov     rcx, [r9+48h]; lpMultiByteStr
0x180025820  test    rcx, rcx
0x180025823  jz      loc_18002593B
0x180025829  call    ?ConvertFromUTF8@mkvparser@@YAPEAGPEBD@Z; mkvparser::ConvertFromUTF8(char const *)
0x18002582e  mov     [rsp+78h+Block], rax
0x180025836  test    rax, rax
0x180025839  jnz     loc_180025922
0x18002583f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025846  test    rcx, rcx
0x180025849  jnz     short loc_18002588C
0x18002584b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180025851  mov     rcx, rax
0x180025854  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002585b  test    rax, rax
0x18002585e  jz      short loc_18002587E
0x180025860  mov     rax, [rax]
0x180025863  mov     edx, 7F0h
0x180025868  mov     rax, [rax+8]
0x18002586c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025871  test    eax, eax
0x180025873  jz      short loc_18002587E
0x180025875  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002587c  jmp     short loc_18002588C
0x18002587e  lea     rcx, qword_1800D6F70; this
0x180025885  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002588c  cmp     [rcx+8], r14b
0x180025890  jz      short loc_1800258BA
0x180025892  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180025897  mov     ebx, 8007000Eh
0x18002589c  cmp     [rax+7CCh], ebx
0x1800258a2  jz      short loc_1800258BF
0x1800258a4  mov     r9d, ebx; int
0x1800258a7  mov     r8d, 67h ; 'g'; int
0x1800258ad  mov     rdx, r12; char *
0x1800258b0  mov     rcx, rax; this
0x1800258b3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800258b8  jmp     short loc_1800258BF
0x1800258ba  mov     ebx, 8007000Eh
0x1800258bf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800258c6  jb      short loc_1800258EC
0x1800258c8  mov     edx, 0Dh
0x1800258cd  mov     [rsp+78h+var_58], ebx
0x1800258d1  mov     r9, rdi
0x1800258d4  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x1800258db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800258e2  mov     rcx, [rcx+10h]
0x1800258e6  call    WPP_SF_qD
0x1800258eb  nop
0x1800258ec  mov     rcx, [rsp+78h+Block]; Block
0x1800258f4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800258f9  mov     rcx, [rsp+78h+var_48]; Block
0x1800258fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025903  mov     rcx, [rsp+78h+var_40]; Block
0x180025908  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002590d  nop
0x18002590e  lea     rcx, [rsp+78h+arg_8]; this
0x180025916  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002591b  mov     eax, ebx
0x18002591d  jmp     loc_180025BF8
0x180025922  mov     r8, rbx
0x180025925  inc     r8
0x180025928  cmp     [rax+r8*2], r14w
0x18002592d  jnz     short loc_180025925
0x18002592f  lea     rcx, [rdi+50h]
0x180025933  mov     rdx, rax
0x180025936  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002593b  lea     rsi, [rdi+70h]
0x18002593f  mov     r8d, 2
0x180025945  lea     rdx, aEn; "en"
0x18002594c  mov     rcx, rsi
0x18002594f  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180025954  mov     rax, [rdi+48h]
0x180025958  mov     rcx, [rax+50h]; lpMultiByteStr
0x18002595c  test    rcx, rcx
0x18002595f  jz      loc_180025A7B
0x180025965  call    ?ConvertFromUTF8@mkvparser@@YAPEAGPEBD@Z; mkvparser::ConvertFromUTF8(char const *)
0x18002596a  mov     [rsp+78h+var_48], rax
0x18002596f  test    rax, rax
0x180025972  jnz     loc_180025A5B
0x180025978  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002597f  test    rcx, rcx
  ... truncated ...
```
