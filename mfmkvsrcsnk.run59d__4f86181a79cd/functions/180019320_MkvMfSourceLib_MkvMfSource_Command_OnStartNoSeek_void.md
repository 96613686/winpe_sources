# MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek(void)

- ea: `0x180019320`
- end: `0x180019a6e`
- name: `?OnStartNoSeek@Command@MkvMfSource@MkvMfSourceLib@@AEBAJXZ`
- size: `1870`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource::Command *__hidden this)`
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180017658`
- `0x18001789c`
- `0x180017f48`

## callees

- `0x180002400`
- `0x180005c68`
- `0x180009b04`
- `0x180009bec`
- `0x18000d554`
- `0x18000ddc0`
- `0x180019320`
- `0x18001bca0`
- `0x180021abc`
- `0x180021b9c`
- `0x180022640`
- `0x180026e34`
- `0x180046bc4`
- `0x1800744d8`
- `0x18008ea70`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001940b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001967c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019741`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019810`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800198d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001996a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001940b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001967c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019741`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019810`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800198d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001996a`

## string_xrefs

- `0x18001936b`: `MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek`
- `0x18001946b`: `MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek`
- `0x1800196df`: `MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek`
- `0x1800197a4`: `MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek`
- `0x180019873`: `MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek`
- `0x180019938`: `MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek`
- `0x1800199cd`: `MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek(MkvMfSourceLib::MkvMfSource::Command *this)
{
  __int64 v2; // rax
  mkvparser::Segment *v3; // r12
  __int64 v4; // r13
  int v5; // edi
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v7; // ebx
  __int64 v8; // rdx
  int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  char v16; // r15
  unsigned int i; // r14d
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rbx
  MkvMfSourceLib::MkvMfStream *v25; // rbx
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  const struct Cluster *First; // rax
  MkvReader *v52; // rcx
  _BYTE v53[8]; // [rsp+30h] [rbp-A9h] BYREF
  __int64 v54; // [rsp+38h] [rbp-A1h] BYREF
  unsigned int v55; // [rsp+40h] [rbp-99h] BYREF
  int v56; // [rsp+44h] [rbp-95h] BYREF
  int v57; // [rsp+48h] [rbp-91h] BYREF
  unsigned int v58; // [rsp+4Ch] [rbp-8Dh] BYREF
  MkvMfSourceLib::MkvMfStream *v59; // [rsp+50h] [rbp-89h] BYREF
  __int128 v60; // [rsp+58h] [rbp-81h]
  _BYTE v61[24]; // [rsp+68h] [rbp-71h]
  __int64 v62; // [rsp+80h] [rbp-59h]
  char v63; // [rsp+88h] [rbp-51h]
  int v64; // [rsp+89h] [rbp-50h]
  __int16 v65; // [rsp+8Dh] [rbp-4Ch]
  char v66; // [rsp+8Fh] [rbp-4Ah]
  _OWORD v67[3]; // [rsp+90h] [rbp-49h] BYREF
  __int64 v68; // [rsp+C0h] [rbp-19h]
  _BYTE v69[16]; // [rsp+D0h] [rbp-9h] BYREF

  v2 = *((_QWORD *)this + 1);
  v3 = *(mkvparser::Segment **)(v2 + 416);
  v4 = *(_QWORD *)(v2 + 576);
  v5 = 0;
  v55 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v53,
    "MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek",
    3705);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 2) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 296LL))(*((_QWORD *)this + 2));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 2) + 280LL))(
                                                            *((_QWORD *)this + 2),
                                                            v69);
    *((_DWORD *)ThreadRelativeContext + 504) = v7;
    v5 = 0;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 3) + 264LL))(
         *((_QWORD *)this + 3),
         &v55);
  if ( v9 < 0 )
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v10, v11);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v14 + 499) != v9 )
        CallStackContext::TraceFailure(v14, "MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek", 3705, v9);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v9);
LABEL_15:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v53);
    return (unsigned int)v9;
  }
  v16 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= v55 )
    {
      if ( v16 )
      {
        First = mkvparser::Segment::GetFirst(v3);
        v52 = (MkvReader *)(*((_QWORD *)this + 1) + 184LL);
        *((_QWORD *)v52 + 26) = 0;
        MkvReader::Seek(v52, *((_QWORD *)First + 1));
      }
      goto LABEL_96;
    }
    v57 = 0;
    v54 = 0;
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, __int64 *))(**((_QWORD **)this + 3) + 272LL))(
           *((_QWORD *)this + 3),
           i,
           &v57,
           &v54);
    if ( v9 < 0 )
    {
      v48 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
        CallStackTracing::s_wpInstance = v49;
        if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
        {
          v48 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v48 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v48 + 8) )
      {
        v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
        if ( *((_DWORD *)v50 + 499) != v9 )
          CallStackContext::TraceFailure(v50, "MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek", 3718, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_93;
      v47 = 238;
      goto LABEL_92;
    }
    v56 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v54 + 264LL))(v54, &v56);
    if ( v9 < 0 )
    {
      v44 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
        CallStackTracing::s_wpInstance = v45;
        if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
        {
          v44 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v44 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v44 + 8) )
      {
        v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
        if ( *((_DWORD *)v46 + 499) != v9 )
          CallStackContext::TraceFailure(v46, "MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek", 3722, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_93;
      v47 = 239;
LABEL_92:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v47, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v9);
LABEL_93:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54);
      goto LABEL_15;
    }
    v24 = *(_QWORD *)std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>,0>>::find(
                       *((_QWORD *)this + 1) + 576LL,
                       v69,
                       &v56);
    if ( v24 == v4 )
      goto LABEL_32;
    v25 = *(MkvMfSourceLib::MkvMfStream **)(v24 + 40);
    v59 = v25;
    Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(&v59);
    if ( !v57 )
    {
      v5 = MkvMfSourceLib::MkvMfStream::Deselect(v25);
      if ( v5 < 0 )
      {
        v35 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
          CallStackTracing::s_wpInstance = v36;
          if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
          {
            v35 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v35 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v35 + 8) )
        {
          v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
          if ( *((_DWORD *)v37 + 499) != v5 )
            CallStackContext::TraceFailure(v37, "MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek", 3744, v5);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            240,
            &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
            this,
            v5);
        if ( v25 )
          (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v25 + 16LL))(v25);
        goto LABEL_58;
      }
      v5 = 0;
      if ( v25 )
        (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v25 + 16LL))(v25);
      goto LABEL_32;
    }
    v58 = 0;
    v5 = MkvMfSourceLib::MkvMfStream::Select(v25, &v58);
    if ( v5 < 0 )
      break;
    v5 = MkvMfSourceLib::MkvMfSource::QueueStreamEvent(*((MkvMfSourceLib::MkvMfSource **)this + 1), v58, v25);
    if ( v5 < 0 )
    {
      v38 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
        CallStackTracing::s_wpInstance = v39;
        if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
        {
          v38 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v38 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v38 + 8) )
      {
        v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
        if ( *((_DWORD *)v40 + 499) != v5 )
          CallStackContext::TraceFailure(v40, "MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek", 3751, v5);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 242, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v5);
      if ( v25 )
        (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v25 + 16LL))(v25);
      goto LABEL_58;
    }
    v5 = 0;
    if ( !*((_QWORD *)v25 + 24) )
    {
      v64 = 0;
      v65 = 0;
      v66 = 0;
      *(_QWORD *)v61 = *((_QWORD *)v25 + 29);
      *(_OWORD *)&v61[8] = 0;
      v60 = 0xFFFFFFFF;
      v63 = 0;
      v62 = 0;
      v67[0] = 0xFFFFFFFF;
      v67[1] = *(_OWORD *)v61;
      v67[2] = 0u;
      v68 = 0;
      (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *, _OWORD *))(*(_QWORD *)v25 + 152LL))(v25, v67);
      v16 = 1;
    }
    *((_QWORD *)v25 + 34) = 5000000;
    if ( v25 )
      (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v25 + 16LL))(v25);
LABEL_32:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54);
  }
  v41 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
    CallStackTracing::s_wpInstance = v42;
    if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
    {
      v41 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v41 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v41 + 8) )
  {
    v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
    if ( *((_DWORD *)v43 + 499) != v5 )
      CallStackContext::TraceFailure(v43, "MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek", 3749, v5);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 241, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v5);
  if ( v25 )
    (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v25 + 16LL))(v25);
LABEL_58:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54);
LABEL_96:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v53);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180019320  push    rbp
0x180019322  push    rbx
0x180019323  push    rsi
0x180019324  push    rdi
0x180019325  push    r12
0x180019327  push    r13
0x180019329  push    r14
0x18001932b  push    r15
0x18001932d  lea     rbp, [rsp-1Fh]
0x180019332  sub     rsp, 0F8h
0x180019339  mov     rax, cs:__security_cookie
0x180019340  xor     rax, rsp
0x180019343  mov     [rbp+57h+var_50], rax
0x180019347  mov     rsi, rcx
0x18001934a  mov     rax, [rcx+8]
0x18001934e  mov     r12, [rax+1A0h]
0x180019355  mov     r13, [rax+240h]
0x18001935c  xor     edi, edi
0x18001935e  mov     [rsp+130h+var_F0], edi
0x180019362  mov     r14d, 0E79h
0x180019368  mov     r8d, r14d; int
0x18001936b  lea     rdx, aMkvmfsourcelib_99; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180019372  lea     rcx, [rsp+130h+var_100]; this
0x180019377  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001937c  nop
0x18001937d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180019384  cmp     [rcx+8], dil
0x180019388  jz      short loc_1800193DD
0x18001938a  cmp     [rsi+10h], rdi
0x18001938e  jz      short loc_1800193DD
0x180019390  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019395  mov     rdi, rax
0x180019398  mov     rdx, [rsi+10h]
0x18001939c  mov     rcx, [rdx]
0x18001939f  mov     rax, [rcx+128h]
0x1800193a6  mov     rcx, rdx
0x1800193a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193ae  mov     ebx, eax
0x1800193b0  mov     r8, [rsi+10h]
0x1800193b4  mov     rcx, [r8]
0x1800193b7  mov     rax, [rcx+118h]
0x1800193be  lea     rdx, [rbp+57h+var_60]
0x1800193c2  mov     rcx, r8
0x1800193c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193ca  movups  xmm0, xmmword ptr [rax]
0x1800193cd  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800193d5  mov     [rdi+7E0h], ebx
0x1800193db  xor     edi, edi
0x1800193dd  mov     rcx, [rsi+18h]
0x1800193e1  mov     rax, [rcx]
0x1800193e4  lea     rdx, [rsp+130h+var_F0]
0x1800193e9  mov     rax, [rax+108h]
0x1800193f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193f5  mov     ebx, eax
0x1800193f7  test    eax, eax
0x1800193f9  jns     loc_1800194B8
0x1800193ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019406  test    rcx, rcx
0x180019409  jnz     short loc_180019452
0x18001940b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019412  nop     dword ptr [rax+rax+00h]
0x180019417  mov     rcx, rax
0x18001941a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019421  test    rax, rax
0x180019424  jz      short loc_180019444
0x180019426  mov     rax, [rax]
0x180019429  mov     edx, 7F0h
0x18001942e  mov     rax, [rax+8]
0x180019432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019437  test    eax, eax
0x180019439  jz      short loc_180019444
0x18001943b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019442  jmp     short loc_180019452
0x180019444  lea     rcx, qword_1800DBF70; this
0x18001944b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019452  cmp     [rcx+8], dil
0x180019456  jz      short loc_18001947A
0x180019458  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001945d  cmp     [rax+7CCh], ebx
0x180019463  jz      short loc_18001947A
0x180019465  mov     r9d, ebx; int
0x180019468  mov     r8d, r14d; int
0x18001946b  lea     rdx, aMkvmfsourcelib_99; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180019472  mov     rcx, rax; this
0x180019475  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001947a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019481  jb      short loc_1800194A7
0x180019483  mov     edx, 0EDh
0x180019488  mov     [rsp+130h+var_110], ebx
0x18001948c  mov     r9, rsi
0x18001948f  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180019496  mov     rcx, cs:WPP_GLOBAL_Control
0x18001949d  mov     rcx, [rcx+10h]
0x1800194a1  call    WPP_SF_qD
0x1800194a6  nop
0x1800194a7  lea     rcx, [rsp+130h+var_100]; this
0x1800194ac  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800194b1  mov     eax, ebx
0x1800194b3  jmp     loc_180019A4D
0x1800194b8  mov     r15b, dil
0x1800194bb  mov     r14d, edi
0x1800194be  cmp     r14d, [rsp+130h+var_F0]
0x1800194c3  jnb     loc_180019A18
0x1800194c9  mov     [rsp+130h+var_E8], edi
0x1800194cd  mov     [rsp+130h+var_F8], rdi
0x1800194d2  mov     rcx, [rsi+18h]
0x1800194d6  mov     rax, [rcx]
0x1800194d9  lea     r9, [rsp+130h+var_F8]
0x1800194de  lea     r8, [rsp+130h+var_E8]
0x1800194e3  mov     edx, r14d
0x1800194e6  mov     rax, [rax+110h]
0x1800194ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194f2  mov     ebx, eax
0x1800194f4  test    eax, eax
0x1800194f6  js      loc_18001995E
0x1800194fc  mov     [rsp+130h+var_EC], edi
0x180019500  mov     rcx, [rsp+130h+var_F8]
0x180019505  mov     rax, [rcx]
0x180019508  lea     rdx, [rsp+130h+var_EC]
0x18001950d  mov     rax, [rax+108h]
0x180019514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019519  mov     ebx, eax
0x18001951b  test    eax, eax
0x18001951d  js      loc_1800198C9
0x180019523  mov     rcx, [rsi+8]
0x180019527  add     rcx, 240h
0x18001952e  lea     r8, [rsp+130h+var_EC]
0x180019533  lea     rdx, [rbp+57h+var_60]
0x180019537  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>,0>>::find(ulong const &)
0x18001953c  mov     rbx, [rax]
0x18001953f  cmp     rbx, r13
0x180019542  jz      loc_18001965E
0x180019548  mov     rbx, [rbx+28h]
0x18001954c  mov     [rsp+130h+var_E0], rbx
0x180019551  lea     rcx, [rsp+130h+var_E0]
0x180019556  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x18001955b  nop
0x18001955c  mov     rcx, rbx; this
0x18001955f  cmp     [rsp+130h+var_E8], edi
0x180019563  jnz     short loc_180019590
0x180019565  call    ?Deselect@MkvMfStream@MkvMfSourceLib@@QEAAJXZ; MkvMfSourceLib::MkvMfStream::Deselect(void)
0x18001956a  mov     edi, eax
0x18001956c  test    eax, eax
0x18001956e  js      loc_180019670
0x180019574  xor     edi, edi
0x180019576  test    rbx, rbx
0x180019579  jz      short loc_18001958B
0x18001957b  mov     rax, [rbx]
0x18001957e  mov     rcx, rbx
0x180019581  mov     rax, [rax+10h]
0x180019585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001958a  nop
0x18001958b  jmp     loc_18001965E
0x180019590  mov     [rsp+130h+var_E4], edi
0x180019594  lea     rdx, [rsp+130h+var_E4]; unsigned int *
0x180019599  call    ?Select@MkvMfStream@MkvMfSourceLib@@QEAAJPEAK@Z; MkvMfSourceLib::MkvMfStream::Select(ulong *)
0x18001959e  mov     edi, eax
0x1800195a0  test    eax, eax
0x1800195a2  js      loc_180019804
0x1800195a8  mov     r8, rbx; struct MkvMfSourceLib::MkvMfStream *
0x1800195ab  mov     edx, [rsp+130h+var_E4]; unsigned int
0x1800195af  mov     rcx, [rsi+8]; this
0x1800195b3  call    ?QueueStreamEvent@MkvMfSource@MkvMfSourceLib@@AEBAJKPEAVMkvMfStream@2@@Z; MkvMfSourceLib::MkvMfSource::QueueStreamEvent(ulong,MkvMfSourceLib::MkvMfStream *)
0x1800195b8  mov     edi, eax
0x1800195ba  test    eax, eax
0x1800195bc  js      loc_180019735
0x1800195c2  xor     edi, edi
0x1800195c4  cmp     [rbx+0C0h], rdi
0x1800195cb  jnz     short loc_18001963E
0x1800195cd  mov     dword ptr [rbp+57h+var_D8+4], edi
0x1800195d0  mov     dword ptr [rbp+57h+var_A8+1], edi
0x1800195d3  mov     word ptr [rbp+57h+var_A8+5], di
0x1800195d7  mov     byte ptr [rbp+57h+var_A8+7], dil
0x1800195db  mov     rax, [rbx+0E8h]
0x1800195e2  mov     qword ptr [rbp+57h+var_C8], rax
0x1800195e6  xorps   xmm0, xmm0
0x1800195e9  movdqu  xmmword ptr [rbp+57h+var_C8+8], xmm0
0x1800195ee  mov     dword ptr [rsp+130h+var_D8], 0FFFFFFFFh
0x1800195f6  mov     qword ptr [rbp+57h+var_D8+8], rdi
0x1800195fa  mov     byte ptr [rbp+57h+var_A8], dil
0x1800195fe  mov     [rbp+57h+var_B0], rdi
0x180019602  movups  xmm0, [rsp+130h+var_D8]
0x180019607  movaps  [rbp+57h+var_A0], xmm0
0x18001960b  movups  xmm1, xmmword ptr [rbp+57h+var_C8]
0x18001960f  movaps  [rbp+57h+var_90], xmm1
0x180019613  movups  xmm0, xmmword ptr [rbp-61h]
0x180019617  movaps  [rbp+57h+var_80], xmm0
0x18001961b  movsd   xmm1, [rbp+57h+var_A8]
0x180019620  movsd   [rbp+57h+var_70], xmm1
0x180019625  mov     rax, [rbx]
0x180019628  lea     rdx, [rbp+57h+var_A0]
0x18001962c  mov     rcx, rbx
0x18001962f  mov     rax, [rax+98h]
0x180019636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001963b  mov     r15b, 1
0x18001963e  mov     qword ptr [rbx+110h], 4C4B40h
0x180019649  test    rbx, rbx
0x18001964c  jz      short loc_18001965E
0x18001964e  mov     rax, [rbx]
0x180019651  mov     rcx, rbx
0x180019654  mov     rax, [rax+10h]
0x180019658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001965d  nop
0x18001965e  lea     rcx, [rsp+130h+var_F8]
0x180019663  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019668  inc     r14d
0x18001966b  jmp     loc_1800194BE
0x180019670  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019677  test    rcx, rcx
0x18001967a  jnz     short loc_1800196C3
0x18001967c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019683  nop     dword ptr [rax+rax+00h]
0x180019688  mov     rcx, rax
0x18001968b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019692  test    rax, rax
0x180019695  jz      short loc_1800196B5
0x180019697  mov     rax, [rax]
0x18001969a  mov     edx, 7F0h
0x18001969f  mov     rax, [rax+8]
0x1800196a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196a8  test    eax, eax
0x1800196aa  jz      short loc_1800196B5
0x1800196ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800196b3  jmp     short loc_1800196C3
0x1800196b5  lea     rcx, qword_1800DBF70; this
0x1800196bc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800196c3  cmp     byte ptr [rcx+8], 0
0x1800196c7  jz      short loc_1800196EE
0x1800196c9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800196ce  cmp     [rax+7CCh], edi
0x1800196d4  jz      short loc_1800196EE
0x1800196d6  mov     r9d, edi; int
0x1800196d9  mov     r8d, 0EA0h; int
0x1800196df  lea     rdx, aMkvmfsourcelib_99; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800196e6  mov     rcx, rax; this
0x1800196e9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800196ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800196f5  jb      short loc_18001971B
0x1800196f7  mov     edx, 0F0h
0x1800196fc  mov     [rsp+130h+var_110], edi
0x180019700  mov     r9, rsi
0x180019703  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001970a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019711  mov     rcx, [rcx+10h]
0x180019715  call    WPP_SF_qD
0x18001971a  nop
0x18001971b  test    rbx, rbx
0x18001971e  jz      short loc_180019730
0x180019720  mov     rax, [rbx]
0x180019723  mov     rcx, rbx
0x180019726  mov     rax, [rax+10h]
0x18001972a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001972f  nop
0x180019730  jmp     loc_1800197F5
0x180019735  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001973c  test    rcx, rcx
0x18001973f  jnz     short loc_180019788
0x180019741  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019748  nop     dword ptr [rax+rax+00h]
0x18001974d  mov     rcx, rax
0x180019750  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019757  test    rax, rax
0x18001975a  jz      short loc_18001977A
0x18001975c  mov     rax, [rax]
0x18001975f  mov     edx, 7F0h
0x180019764  mov     rax, [rax+8]
0x180019768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001976d  test    eax, eax
0x18001976f  jz      short loc_18001977A
0x180019771  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019778  jmp     short loc_180019788
0x18001977a  lea     rcx, qword_1800DBF70; this
0x180019781  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019788  cmp     byte ptr [rcx+8], 0
0x18001978c  jz      short loc_1800197B3
0x18001978e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019793  cmp     [rax+7CCh], edi
0x180019799  jz      short loc_1800197B3
0x18001979b  mov     r9d, edi; int
0x18001979e  mov     r8d, 0EA7h; int
0x1800197a4  lea     rdx, aMkvmfsourcelib_99; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800197ab  mov     rcx, rax; this
0x1800197ae  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800197b3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800197ba  jb      short loc_1800197E0
0x1800197bc  mov     edx, 0F2h
0x1800197c1  mov     [rsp+130h+var_110], edi
0x1800197c5  mov     r9, rsi
0x1800197c8  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x1800197cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197d6  mov     rcx, [rcx+10h]
0x1800197da  call    WPP_SF_qD
0x1800197df  nop
0x1800197e0  test    rbx, rbx
0x1800197e3  jz      short loc_1800197F5
0x1800197e5  mov     rax, [rbx]
0x1800197e8  mov     rcx, rbx
0x1800197eb  mov     rax, [rax+10h]
0x1800197ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197f4  nop
  ... truncated ...
```
