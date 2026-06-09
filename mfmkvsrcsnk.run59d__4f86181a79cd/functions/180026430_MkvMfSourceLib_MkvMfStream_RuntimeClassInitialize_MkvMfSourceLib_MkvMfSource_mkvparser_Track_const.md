# MkvMfSourceLib::MkvMfStream::RuntimeClassInitialize(MkvMfSourceLib::MkvMfSource *,mkvparser::Track const *)

- ea: `0x180026430`
- end: `0x180026c00`
- name: `?RuntimeClassInitialize@MkvMfStream@MkvMfSourceLib@@UEAAJPEAVMkvMfSource@2@PEBVTrack@mkvparser@@@Z`
- size: `2000`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStream *__hidden this, struct MkvMfSourceLib::MkvMfSource *, const struct mkvparser::Track *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180038a10`
- `0x180038bc0`

## callees

- `0x180001ff0`
- `0x180005c68`
- `0x180008154`
- `0x180009414`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x1800151a4`
- `0x1800151c8`
- `0x180021b9c`
- `0x180026430`
- `0x180047fec`
- `0x1800744d8`
- `0x18008867c`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002647f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026525`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026637`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002682a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026969`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026aaf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002647f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026525`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026637`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002682a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026969`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026aaf`
- `MFPlat!MFCreateEventQueue` at `0x180026615`
- `MFPlat!MFCreateEventQueue` at `0x180026615`

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
  __int64 v17; // r11
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 result; // rax
  __int64 v25; // rbx
  const char *v26; // rdx
  _QWORD *v27; // r9
  __int64 v28; // rcx
  __int64 v29; // rax
  unsigned int v30; // r8d
  __int64 *v31; // rcx
  __int64 v32; // r10
  __int64 v33; // r11
  _DWORD *v34; // rcx
  const CHAR *v35; // rcx
  unsigned __int16 *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // r8
  const char *v44; // rdx
  const CHAR *v45; // rcx
  unsigned __int16 *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // r8
  const char *v54; // rdx
  const CHAR *v55; // rcx
  unsigned __int16 *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // r9
  __int64 *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  const char *v63; // r9
  void *v64; // [rsp+30h] [rbp-48h] BYREF
  void *v65[4]; // [rsp+38h] [rbp-40h] BYREF
  char v66; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v68; // [rsp+88h] [rbp+10h] BYREF
  void *Block; // [rsp+98h] [rbp+20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v68,
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
        v9 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      goto LABEL_39;
    v13 = 10;
LABEL_38:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v12);
LABEL_39:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v68);
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
        v14 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      goto LABEL_39;
    v13 = 11;
    goto LABEL_38;
  }
  Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfSource>::operator=((char *)this + 56, a2);
  *((_QWORD *)this + 9) = a3;
  if ( *((_QWORD *)this + 52) != *((_QWORD *)a2 + 85) )
  {
    v68 = *((_QWORD *)a2 + 85);
    Microsoft::WRL::ComPtr<MkvSourceTelemetryLogger>::InternalAddRef(&v68);
    v68 = *((_QWORD *)this + 52);
    *((_QWORD *)this + 52) = v17;
    Microsoft::WRL::ComPtr<MkvSourceTelemetryLogger>::InternalRelease(&v68);
  }
  v12 = MFCreateEventQueue((IMFMediaEventQueue **)this + 56);
  if ( v12 < 0 )
  {
    v21 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
      CallStackTracing::s_wpInstance = v22;
      if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
      {
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v21 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v21 + 8) )
    {
      v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
      if ( *((_DWORD *)v23 + 499) != v12 )
        CallStackContext::TraceFailure(v23, "MkvMfSourceLib::MkvMfStream::RuntimeClassInitialize", 59, v12);
    }
    if ( !g_wppLevels )
      goto LABEL_39;
    v13 = 12;
    goto LABEL_38;
  }
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  v25 = -1;
  *((_DWORD *)this + 44) = -1;
  *((_QWORD *)this + 23) = 0;
  *((_BYTE *)this + 224) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 39) = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 320);
  v27 = (_QWORD *)*((_QWORD *)this + 9);
  v28 = v27[21];
  v29 = (v27[22] - v28) >> 3;
  if ( (_DWORD)v29 )
  {
    v30 = 0;
    do
    {
      if ( *((_QWORD *)this + 39) )
        break;
      if ( v30 < (unsigned int)v29 )
      {
        v31 = *(__int64 **)(v28 + 8LL * v30);
        if ( v31 )
        {
          if ( v31[5] == 1 )
          {
            v26 = 0;
            v32 = *v31;
            v33 = v31[1];
            while ( (unsigned int)v26 < (unsigned int)((v33 - v32) >> 3) )
            {
              v34 = *(_DWORD **)(v32 + 8LL * (unsigned int)v26);
              if ( v34 && (*v34 == 3 || !*v34) )
              {
                *((_QWORD *)this + 39) = v34;
                break;
              }
              v26 = (const char *)(unsigned int)((_DWORD)v26 + 1);
            }
          }
        }
      }
      ++v30;
      v28 = v27[21];
      v29 = (v27[22] - v28) >> 3;
    }
    while ( v30 < (unsigned int)v29 );
  }
  try
  {
    Block = 0;
    v64 = 0;
    v65[0] = 0;
    v65[1] = &Block;
    v65[2] = &v64;
    v65[3] = v65;
    v66 = 1;
    v35 = (const CHAR *)v27[9];
    if ( v35 )
    {
      v36 = mkvparser::ConvertFromUTF8(v35, v26);
      Block = v36;
      if ( !v36 )
      {
        v40 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38, v39);
          CallStackTracing::s_wpInstance = v41;
          if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
          {
            v40 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v40 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v40 + 8) )
        {
          v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
          if ( *((_DWORD *)v42 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v42, "MkvMfSourceLib::MkvMfStream::RuntimeClassInitialize", 103, -2147024882);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
            this,
            -2147024882);
LABEL_99:
        operator delete(Block);
        operator delete(v64);
        operator delete(v65[0]);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v68);
        return 2147942414LL;
      }
      v43 = -1;
      do
        ++v43;
      while ( v36[v43] );
      std::wstring::_Assign<unsigned short>((char *)this + 80, v36);
    }
    std::wstring::_Assign<unsigned short>((char *)this + 112, L"en");
    v45 = *(const CHAR **)(*((_QWORD *)this + 9) + 80LL);
    if ( v45 )
    {
      v46 = mkvparser::ConvertFromUTF8(v45, v44);
      v64 = v46;
      if ( !v46 )
      {
        v50 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47, v48, v49);
          CallStackTracing::s_wpInstance = v51;
          if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
          {
            v50 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v50 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v50 + 8) )
        {
          v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
          if ( *((_DWORD *)v52 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v52, "MkvMfSourceLib::MkvMfStream::RuntimeClassInitialize", 112, -2147024882);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
            this,
            -2147024882);
        goto LABEL_99;
      }
      v53 = -1;
      do
        ++v53;
      while ( v46[v53] );
      std::wstring::_Assign<unsigned short>((char *)this + 112, v46);
      MkvMfSourceLib::ConvertMKVLanguageStringToRFC1766((char *)this + 112);
    }
    std::wstring::_Assign<unsigned short>((char *)this + 144, &word_1800BC2F8);
    v55 = *(const CHAR **)(*((_QWORD *)this + 9) + 88LL);
    if ( v55 )
    {
      v56 = mkvparser::ConvertFromUTF8(v55, v54);
      v65[0] = v56;
      if ( !v56 )
      {
        v60 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v57, v58, v59);
          CallStackTracing::s_wpInstance = v61;
          if ( v61 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
          {
            v60 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v60 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v60 + 8) )
        {
          v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
          if ( *((_DWORD *)v62 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v62, "MkvMfSourceLib::MkvMfStream::RuntimeClassInitialize", 122, -2147024882);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
            this,
            -2147024882);
        goto LABEL_99;
      }
      do
        ++v25;
      while ( v56[v25] );
      std::wstring::_Assign<unsigned short>((char *)this + 144, v56);
    }
    operator delete(Block);
    operator delete(v64);
    operator delete(v65[0]);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v68);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(Block) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x7E,
                       (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvmfstream.cpp",
                       v63);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v68);
    return (unsigned int)Block;
  }
  return result;
}

```

## disassembly

```asm
0x180026430  mov     rax, rsp
0x180026433  mov     [rax+8], rbx
0x180026437  mov     [rax+18h], rsi
0x18002643b  push    rdi
0x18002643c  push    r12
0x18002643e  push    r14
0x180026440  sub     rsp, 60h
0x180026444  mov     rsi, r8
0x180026447  mov     rbx, rdx
0x18002644a  mov     rdi, rcx
0x18002644d  mov     r8d, 34h ; '4'; int
0x180026453  lea     r12, aMkvmfsourcelib_7; "MkvMfSourceLib::MkvMfStream::RuntimeCla"...
0x18002645a  mov     rdx, r12; char *
0x18002645d  lea     rcx, [rax+10h]; this
0x180026461  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180026466  nop
0x180026467  xor     r14d, r14d
0x18002646a  test    rbx, rbx
0x18002646d  jnz     loc_180026510
0x180026473  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002647a  test    rcx, rcx
0x18002647d  jnz     short loc_1800264C6
0x18002647f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026486  nop     dword ptr [rax+rax+00h]
0x18002648b  mov     rcx, rax
0x18002648e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026495  test    rax, rax
0x180026498  jz      short loc_1800264B8
0x18002649a  mov     rax, [rax]
0x18002649d  mov     edx, 7F0h
0x1800264a2  mov     rax, [rax+8]
0x1800264a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264ab  test    eax, eax
0x1800264ad  jz      short loc_1800264B8
0x1800264af  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800264b6  jmp     short loc_1800264C6
0x1800264b8  lea     rcx, qword_1800DBF70; this
0x1800264bf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800264c6  cmp     [rcx+8], r14b
0x1800264ca  jz      short loc_1800264F4
0x1800264cc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800264d1  mov     ebx, 80004003h
0x1800264d6  cmp     [rax+7CCh], ebx
0x1800264dc  jz      short loc_1800264F9
0x1800264de  mov     r9d, ebx; int
0x1800264e1  mov     r8d, 34h ; '4'; int
0x1800264e7  mov     rdx, r12; char *
0x1800264ea  mov     rcx, rax; this
0x1800264ed  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800264f2  jmp     short loc_1800264F9
0x1800264f4  mov     ebx, 80004003h
0x1800264f9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180026500  jb      loc_1800266D2
0x180026506  mov     edx, 0Ah
0x18002650b  jmp     loc_1800266B3
0x180026510  test    rsi, rsi
0x180026513  jnz     loc_1800265B6
0x180026519  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026520  test    rcx, rcx
0x180026523  jnz     short loc_18002656C
0x180026525  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002652c  nop     dword ptr [rax+rax+00h]
0x180026531  mov     rcx, rax
0x180026534  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002653b  test    rax, rax
0x18002653e  jz      short loc_18002655E
0x180026540  mov     rax, [rax]
0x180026543  mov     edx, 7F0h
0x180026548  mov     rax, [rax+8]
0x18002654c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026551  test    eax, eax
0x180026553  jz      short loc_18002655E
0x180026555  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002655c  jmp     short loc_18002656C
0x18002655e  lea     rcx, qword_1800DBF70; this
0x180026565  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002656c  cmp     [rcx+8], r14b
0x180026570  jz      short loc_18002659A
0x180026572  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026577  mov     ebx, 80004003h
0x18002657c  cmp     [rax+7CCh], ebx
0x180026582  jz      short loc_18002659F
0x180026584  mov     r9d, ebx; int
0x180026587  mov     r8d, 35h ; '5'; int
0x18002658d  mov     rdx, r12; char *
0x180026590  mov     rcx, rax; this
0x180026593  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180026598  jmp     short loc_18002659F
0x18002659a  mov     ebx, 80004003h
0x18002659f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800265a6  jb      loc_1800266D2
0x1800265ac  mov     edx, 0Bh
0x1800265b1  jmp     loc_1800266B3
0x1800265b6  lea     rcx, [rdi+38h]
0x1800265ba  mov     rdx, rbx
0x1800265bd  call    ??4?$ComPtr@VMkvMfSource@MkvMfSourceLib@@@WRL@Microsoft@@QEAAAEAV012@PEAVMkvMfSource@MkvMfSourceLib@@@Z; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfSource>::operator=(MkvMfSourceLib::MkvMfSource *)
0x1800265c2  mov     [rdi+48h], rsi
0x1800265c6  mov     r11, [rbx+2A8h]
0x1800265cd  cmp     [rdi+1A0h], r11
0x1800265d4  jz      short loc_18002660E
0x1800265d6  mov     [rsp+78h+arg_8], r11
0x1800265de  lea     rcx, [rsp+78h+arg_8]
0x1800265e6  call    ?InternalAddRef@?$ComPtr@VMkvSourceTelemetryLogger@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvSourceTelemetryLogger>::InternalAddRef(void)
0x1800265eb  mov     r10, [rdi+1A0h]
0x1800265f2  mov     [rsp+78h+arg_8], r10
0x1800265fa  mov     [rdi+1A0h], r11
0x180026601  lea     rcx, [rsp+78h+arg_8]
0x180026609  call    ?InternalRelease@?$ComPtr@VMkvSourceTelemetryLogger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<MkvSourceTelemetryLogger>::InternalRelease(void)
0x18002660e  lea     rcx, [rdi+1C0h]; ppMediaEventQueue
0x180026615  call    cs:__imp_MFCreateEventQueue
0x18002661c  nop     dword ptr [rax+rax+00h]
0x180026621  mov     ebx, eax
0x180026623  test    eax, eax
0x180026625  jns     loc_1800266E6
0x18002662b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026632  test    rcx, rcx
0x180026635  jnz     short loc_18002667E
0x180026637  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002663e  nop     dword ptr [rax+rax+00h]
0x180026643  mov     rcx, rax
0x180026646  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002664d  test    rax, rax
0x180026650  jz      short loc_180026670
0x180026652  mov     rax, [rax]
0x180026655  mov     edx, 7F0h
0x18002665a  mov     rax, [rax+8]
0x18002665e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026663  test    eax, eax
0x180026665  jz      short loc_180026670
0x180026667  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002666e  jmp     short loc_18002667E
0x180026670  lea     rcx, qword_1800DBF70; this
0x180026677  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002667e  cmp     [rcx+8], r14b
0x180026682  jz      short loc_1800266A5
0x180026684  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026689  cmp     [rax+7CCh], ebx
0x18002668f  jz      short loc_1800266A5
0x180026691  mov     r9d, ebx; int
0x180026694  mov     r8d, 3Bh ; ';'; int
0x18002669a  mov     rdx, r12; char *
0x18002669d  mov     rcx, rax; this
0x1800266a0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800266a5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800266ac  jb      short loc_1800266D2
0x1800266ae  mov     edx, 0Ch
0x1800266b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800266ba  mov     [rsp+78h+var_58], ebx
0x1800266be  mov     r9, rdi
0x1800266c1  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x1800266c8  mov     rcx, [rcx+10h]
0x1800266cc  call    WPP_SF_qD
0x1800266d1  nop
0x1800266d2  lea     rcx, [rsp+78h+arg_8]; this
0x1800266da  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800266df  mov     eax, ebx
0x1800266e1  jmp     loc_180026BE9
0x1800266e6  mov     [rdi+0C0h], r14
0x1800266ed  mov     [rdi+0C8h], r14
0x1800266f4  mov     [rdi+0D0h], r14
0x1800266fb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800266ff  mov     [rdi+0B0h], ebx
0x180026705  mov     [rdi+0B8h], r14
0x18002670c  mov     [rdi+0E0h], r14b
0x180026713  mov     [rdi+0D8h], r14
0x18002671a  mov     [rdi+138h], r14
0x180026721  lea     rcx, [rdi+140h]
0x180026728  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002672d  mov     r9, [rdi+48h]
0x180026731  mov     rcx, [r9+0A8h]
0x180026738  mov     rax, [r9+0B0h]
0x18002673f  sub     rax, rcx
0x180026742  sar     rax, 3
0x180026746  test    eax, eax
0x180026748  jz      short loc_1800267C3
0x18002674a  mov     r8d, r14d
0x18002674d  cmp     [rdi+138h], r14
0x180026754  jnz     short loc_1800267C3
0x180026756  cmp     r8d, eax
0x180026759  jnb     short loc_1800267A6
0x18002675b  mov     eax, r8d
0x18002675e  mov     rcx, [rcx+rax*8]
0x180026762  test    rcx, rcx
0x180026765  jz      short loc_1800267A6
0x180026767  cmp     qword ptr [rcx+28h], 1
0x18002676c  jnz     short loc_1800267A6
0x18002676e  mov     edx, r14d; char *
0x180026771  mov     r10, [rcx]
0x180026774  mov     r11, [rcx+8]
0x180026778  mov     rax, r11
0x18002677b  sub     rax, r10
0x18002677e  sar     rax, 3
0x180026782  cmp     edx, eax
0x180026784  jnb     short loc_1800267A6
0x180026786  mov     eax, edx
0x180026788  mov     rcx, [r10+rax*8]
0x18002678c  test    rcx, rcx
0x18002678f  jz      short loc_18002679B
0x180026791  cmp     dword ptr [rcx], 3
0x180026794  jz      short loc_18002679F
0x180026796  cmp     [rcx], r14d
0x180026799  jz      short loc_18002679F
0x18002679b  inc     edx
0x18002679d  jmp     short loc_180026778
0x18002679f  mov     [rdi+138h], rcx
0x1800267a6  inc     r8d
0x1800267a9  mov     rcx, [r9+0A8h]
0x1800267b0  mov     rax, [r9+0B0h]
0x1800267b7  sub     rax, rcx
0x1800267ba  sar     rax, 3
0x1800267be  cmp     r8d, eax
0x1800267c1  jb      short loc_18002674D
0x1800267c3  mov     [rsp+78h+Block], r14
0x1800267cb  mov     [rsp+78h+var_48], r14
0x1800267d0  mov     [rsp+78h+var_40], r14
0x1800267d5  lea     rax, [rsp+78h+Block]
0x1800267dd  mov     [rsp+78h+var_38], rax
0x1800267e2  lea     rax, [rsp+78h+var_48]
0x1800267e7  mov     [rsp+78h+var_30], rax
0x1800267ec  lea     rax, [rsp+78h+var_40]
0x1800267f1  mov     [rsp+78h+var_28], rax
0x1800267f6  mov     [rsp+78h+var_20], 1
0x1800267fb  mov     rcx, [r9+48h]; lpMultiByteStr
0x1800267ff  test    rcx, rcx
0x180026802  jz      loc_180026920
0x180026808  call    ?ConvertFromUTF8@mkvparser@@YAPEAGPEBD@Z; mkvparser::ConvertFromUTF8(char const *)
0x18002680d  mov     [rsp+78h+Block], rax
0x180026815  test    rax, rax
0x180026818  jnz     loc_180026907
0x18002681e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026825  test    rcx, rcx
0x180026828  jnz     short loc_180026871
0x18002682a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026831  nop     dword ptr [rax+rax+00h]
0x180026836  mov     rcx, rax
0x180026839  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026840  test    rax, rax
0x180026843  jz      short loc_180026863
0x180026845  mov     rax, [rax]
0x180026848  mov     edx, 7F0h
0x18002684d  mov     rax, [rax+8]
0x180026851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026856  test    eax, eax
0x180026858  jz      short loc_180026863
0x18002685a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026861  jmp     short loc_180026871
0x180026863  lea     rcx, qword_1800DBF70; this
0x18002686a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026871  cmp     [rcx+8], r14b
0x180026875  jz      short loc_18002689F
0x180026877  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002687c  mov     ebx, 8007000Eh
0x180026881  cmp     [rax+7CCh], ebx
0x180026887  jz      short loc_1800268A4
0x180026889  mov     r9d, ebx; int
0x18002688c  mov     r8d, 67h ; 'g'; int
0x180026892  mov     rdx, r12; char *
0x180026895  mov     rcx, rax; this
0x180026898  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002689d  jmp     short loc_1800268A4
0x18002689f  mov     ebx, 8007000Eh
0x1800268a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800268ab  jb      short loc_1800268D1
0x1800268ad  mov     edx, 0Dh
0x1800268b2  mov     [rsp+78h+var_58], ebx
0x1800268b6  mov     r9, rdi
0x1800268b9  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x1800268c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800268c7  mov     rcx, [rcx+10h]
0x1800268cb  call    WPP_SF_qD
0x1800268d0  nop
0x1800268d1  mov     rcx, [rsp+78h+Block]; Block
0x1800268d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800268de  mov     rcx, [rsp+78h+var_48]; Block
0x1800268e3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800268e8  mov     rcx, [rsp+78h+var_40]; Block
0x1800268ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800268f2  nop
0x1800268f3  lea     rcx, [rsp+78h+arg_8]; this
0x1800268fb  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180026900  mov     eax, ebx
0x180026902  jmp     loc_180026BE9
0x180026907  mov     r8, rbx
0x18002690a  inc     r8
0x18002690d  cmp     [rax+r8*2], r14w
0x180026912  jnz     short loc_18002690A
0x180026914  lea     rcx, [rdi+50h]
0x180026918  mov     rdx, rax
0x18002691b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180026920  lea     rsi, [rdi+70h]
0x180026924  mov     r8d, 2
0x18002692a  lea     rdx, aEn; "en"
0x180026931  mov     rcx, rsi
0x180026934  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180026939  mov     rax, [rdi+48h]
0x18002693d  mov     rcx, [rax+50h]; lpMultiByteStr
0x180026941  test    rcx, rcx
0x180026944  jz      loc_180026A66
0x18002694a  call    ?ConvertFromUTF8@mkvparser@@YAPEAGPEBD@Z; mkvparser::ConvertFromUTF8(char const *)
0x18002694f  mov     [rsp+78h+var_48], rax
  ... truncated ...
```
