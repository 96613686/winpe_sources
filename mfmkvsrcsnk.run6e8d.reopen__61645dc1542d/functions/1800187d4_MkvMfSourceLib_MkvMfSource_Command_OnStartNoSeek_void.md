# MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek(void)

- ea: `0x1800187d4`
- end: `0x180018efd`
- name: `?OnStartNoSeek@Command@MkvMfSource@MkvMfSourceLib@@AEBAJXZ`
- size: `1833`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource::Command *__hidden this)`
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180016ba0`
- `0x180016dd8`
- `0x180017460`

## callees

- `0x1800023e0`
- `0x180005ab8`
- `0x1800097f0`
- `0x1800098b8`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x1800187d4`
- `0x18001b044`
- `0x180020c18`
- `0x180020d84`
- `0x1800217b0`
- `0x180025e34`
- `0x180044d58`
- `0x180071330`
- `0x18008ac78`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800188bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018b2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018be9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018cb2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018d71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018e00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800188bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018b2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018be9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018cb2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018d71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018e00`

## string_xrefs

- `0x18001881f`: `MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek`
- `0x180018919`: `MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek`
- `0x180018b87`: `MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek`
- `0x180018c46`: `MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek`
- `0x180018d0f`: `MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek`
- `0x180018dce`: `MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek`
- `0x180018e5d`: `MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek`

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
        v12 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v48 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v44 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v35 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v38 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v41 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x1800187d4  push    rbp
0x1800187d6  push    rbx
0x1800187d7  push    rsi
0x1800187d8  push    rdi
0x1800187d9  push    r12
0x1800187db  push    r13
0x1800187dd  push    r14
0x1800187df  push    r15
0x1800187e1  lea     rbp, [rsp-1Fh]
0x1800187e6  sub     rsp, 0F8h
0x1800187ed  mov     rax, cs:__security_cookie
0x1800187f4  xor     rax, rsp
0x1800187f7  mov     [rbp+57h+var_50], rax
0x1800187fb  mov     rsi, rcx
0x1800187fe  mov     rax, [rcx+8]
0x180018802  mov     r12, [rax+1A0h]
0x180018809  mov     r13, [rax+240h]
0x180018810  xor     edi, edi
0x180018812  mov     [rsp+130h+var_F0], edi
0x180018816  mov     r14d, 0E79h
0x18001881c  mov     r8d, r14d; int
0x18001881f  lea     rdx, aMkvmfsourcelib_99; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180018826  lea     rcx, [rsp+130h+var_100]; this
0x18001882b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180018830  nop
0x180018831  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180018838  cmp     [rcx+8], dil
0x18001883c  jz      short loc_180018891
0x18001883e  cmp     [rsi+10h], rdi
0x180018842  jz      short loc_180018891
0x180018844  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018849  mov     rdi, rax
0x18001884c  mov     rdx, [rsi+10h]
0x180018850  mov     rcx, [rdx]
0x180018853  mov     rax, [rcx+128h]
0x18001885a  mov     rcx, rdx
0x18001885d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018862  mov     ebx, eax
0x180018864  mov     r8, [rsi+10h]
0x180018868  mov     rcx, [r8]
0x18001886b  mov     rax, [rcx+118h]
0x180018872  lea     rdx, [rbp+57h+var_60]
0x180018876  mov     rcx, r8
0x180018879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001887e  movups  xmm0, xmmword ptr [rax]
0x180018881  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180018889  mov     [rdi+7E0h], ebx
0x18001888f  xor     edi, edi
0x180018891  mov     rcx, [rsi+18h]
0x180018895  mov     rax, [rcx]
0x180018898  lea     rdx, [rsp+130h+var_F0]
0x18001889d  mov     rax, [rax+108h]
0x1800188a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188a9  mov     ebx, eax
0x1800188ab  test    eax, eax
0x1800188ad  jns     loc_180018966
0x1800188b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800188ba  test    rcx, rcx
0x1800188bd  jnz     short loc_180018900
0x1800188bf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800188c5  mov     rcx, rax
0x1800188c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800188cf  test    rax, rax
0x1800188d2  jz      short loc_1800188F2
0x1800188d4  mov     rax, [rax]
0x1800188d7  mov     edx, 7F0h
0x1800188dc  mov     rax, [rax+8]
0x1800188e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188e5  test    eax, eax
0x1800188e7  jz      short loc_1800188F2
0x1800188e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800188f0  jmp     short loc_180018900
0x1800188f2  lea     rcx, qword_1800D6F70; this
0x1800188f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018900  cmp     [rcx+8], dil
0x180018904  jz      short loc_180018928
0x180018906  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001890b  cmp     [rax+7CCh], ebx
0x180018911  jz      short loc_180018928
0x180018913  mov     r9d, ebx; int
0x180018916  mov     r8d, r14d; int
0x180018919  lea     rdx, aMkvmfsourcelib_99; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180018920  mov     rcx, rax; this
0x180018923  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018928  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001892f  jb      short loc_180018955
0x180018931  mov     edx, 0EDh
0x180018936  mov     [rsp+130h+var_110], ebx
0x18001893a  mov     r9, rsi
0x18001893d  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180018944  mov     rcx, cs:WPP_GLOBAL_Control
0x18001894b  mov     rcx, [rcx+10h]
0x18001894f  call    WPP_SF_qD
0x180018954  nop
0x180018955  lea     rcx, [rsp+130h+var_100]; this
0x18001895a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001895f  mov     eax, ebx
0x180018961  jmp     loc_180018EDD
0x180018966  mov     r15b, dil
0x180018969  mov     r14d, edi
0x18001896c  cmp     r14d, [rsp+130h+var_F0]
0x180018971  jnb     loc_180018EA8
0x180018977  mov     [rsp+130h+var_E8], edi
0x18001897b  mov     [rsp+130h+var_F8], rdi
0x180018980  mov     rcx, [rsi+18h]
0x180018984  mov     rax, [rcx]
0x180018987  lea     r9, [rsp+130h+var_F8]
0x18001898c  lea     r8, [rsp+130h+var_E8]
0x180018991  mov     edx, r14d
0x180018994  mov     rax, [rax+110h]
0x18001899b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189a0  mov     ebx, eax
0x1800189a2  test    eax, eax
0x1800189a4  js      loc_180018DF4
0x1800189aa  mov     [rsp+130h+var_EC], edi
0x1800189ae  mov     rcx, [rsp+130h+var_F8]
0x1800189b3  mov     rax, [rcx]
0x1800189b6  lea     rdx, [rsp+130h+var_EC]
0x1800189bb  mov     rax, [rax+108h]
0x1800189c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189c7  mov     ebx, eax
0x1800189c9  test    eax, eax
0x1800189cb  js      loc_180018D65
0x1800189d1  mov     rcx, [rsi+8]
0x1800189d5  add     rcx, 240h
0x1800189dc  lea     r8, [rsp+130h+var_EC]
0x1800189e1  lea     rdx, [rbp+57h+var_60]
0x1800189e5  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>,0>>::find(ulong const &)
0x1800189ea  mov     rbx, [rax]
0x1800189ed  cmp     rbx, r13
0x1800189f0  jz      loc_180018B0C
0x1800189f6  mov     rbx, [rbx+28h]
0x1800189fa  mov     [rsp+130h+var_E0], rbx
0x1800189ff  lea     rcx, [rsp+130h+var_E0]
0x180018a04  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x180018a09  nop
0x180018a0a  mov     rcx, rbx; this
0x180018a0d  cmp     [rsp+130h+var_E8], edi
0x180018a11  jnz     short loc_180018A3E
0x180018a13  call    ?Deselect@MkvMfStream@MkvMfSourceLib@@QEAAJXZ; MkvMfSourceLib::MkvMfStream::Deselect(void)
0x180018a18  mov     edi, eax
0x180018a1a  test    eax, eax
0x180018a1c  js      loc_180018B1E
0x180018a22  xor     edi, edi
0x180018a24  test    rbx, rbx
0x180018a27  jz      short loc_180018A39
0x180018a29  mov     rax, [rbx]
0x180018a2c  mov     rcx, rbx
0x180018a2f  mov     rax, [rax+10h]
0x180018a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a38  nop
0x180018a39  jmp     loc_180018B0C
0x180018a3e  mov     [rsp+130h+var_E4], edi
0x180018a42  lea     rdx, [rsp+130h+var_E4]; unsigned int *
0x180018a47  call    ?Select@MkvMfStream@MkvMfSourceLib@@QEAAJPEAK@Z; MkvMfSourceLib::MkvMfStream::Select(ulong *)
0x180018a4c  mov     edi, eax
0x180018a4e  test    eax, eax
0x180018a50  js      loc_180018CA6
0x180018a56  mov     r8, rbx; struct MkvMfSourceLib::MkvMfStream *
0x180018a59  mov     edx, [rsp+130h+var_E4]; unsigned int
0x180018a5d  mov     rcx, [rsi+8]; this
0x180018a61  call    ?QueueStreamEvent@MkvMfSource@MkvMfSourceLib@@AEBAJKPEAVMkvMfStream@2@@Z; MkvMfSourceLib::MkvMfSource::QueueStreamEvent(ulong,MkvMfSourceLib::MkvMfStream *)
0x180018a66  mov     edi, eax
0x180018a68  test    eax, eax
0x180018a6a  js      loc_180018BDD
0x180018a70  xor     edi, edi
0x180018a72  cmp     [rbx+0C0h], rdi
0x180018a79  jnz     short loc_180018AEC
0x180018a7b  mov     dword ptr [rbp+57h+var_D8+4], edi
0x180018a7e  mov     dword ptr [rbp+57h+var_A8+1], edi
0x180018a81  mov     word ptr [rbp+57h+var_A8+5], di
0x180018a85  mov     byte ptr [rbp+57h+var_A8+7], dil
0x180018a89  mov     rax, [rbx+0E8h]
0x180018a90  mov     qword ptr [rbp+57h+var_C8], rax
0x180018a94  xorps   xmm0, xmm0
0x180018a97  movdqu  xmmword ptr [rbp+57h+var_C8+8], xmm0
0x180018a9c  mov     dword ptr [rsp+130h+var_D8], 0FFFFFFFFh
0x180018aa4  mov     qword ptr [rbp+57h+var_D8+8], rdi
0x180018aa8  mov     byte ptr [rbp+57h+var_A8], dil
0x180018aac  mov     [rbp+57h+var_B0], rdi
0x180018ab0  movups  xmm0, [rsp+130h+var_D8]
0x180018ab5  movaps  [rbp+57h+var_A0], xmm0
0x180018ab9  movups  xmm1, xmmword ptr [rbp+57h+var_C8]
0x180018abd  movaps  [rbp+57h+var_90], xmm1
0x180018ac1  movups  xmm0, xmmword ptr [rbp-61h]
0x180018ac5  movaps  [rbp+57h+var_80], xmm0
0x180018ac9  movsd   xmm1, [rbp+57h+var_A8]
0x180018ace  movsd   [rbp+57h+var_70], xmm1
0x180018ad3  mov     rax, [rbx]
0x180018ad6  lea     rdx, [rbp+57h+var_A0]
0x180018ada  mov     rcx, rbx
0x180018add  mov     rax, [rax+98h]
0x180018ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ae9  mov     r15b, 1
0x180018aec  mov     qword ptr [rbx+110h], 4C4B40h
0x180018af7  test    rbx, rbx
0x180018afa  jz      short loc_180018B0C
0x180018afc  mov     rax, [rbx]
0x180018aff  mov     rcx, rbx
0x180018b02  mov     rax, [rax+10h]
0x180018b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b0b  nop
0x180018b0c  lea     rcx, [rsp+130h+var_F8]
0x180018b11  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018b16  inc     r14d
0x180018b19  jmp     loc_18001896C
0x180018b1e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018b25  test    rcx, rcx
0x180018b28  jnz     short loc_180018B6B
0x180018b2a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018b30  mov     rcx, rax
0x180018b33  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018b3a  test    rax, rax
0x180018b3d  jz      short loc_180018B5D
0x180018b3f  mov     rax, [rax]
0x180018b42  mov     edx, 7F0h
0x180018b47  mov     rax, [rax+8]
0x180018b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b50  test    eax, eax
0x180018b52  jz      short loc_180018B5D
0x180018b54  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018b5b  jmp     short loc_180018B6B
0x180018b5d  lea     rcx, qword_1800D6F70; this
0x180018b64  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018b6b  cmp     byte ptr [rcx+8], 0
0x180018b6f  jz      short loc_180018B96
0x180018b71  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018b76  cmp     [rax+7CCh], edi
0x180018b7c  jz      short loc_180018B96
0x180018b7e  mov     r9d, edi; int
0x180018b81  mov     r8d, 0EA0h; int
0x180018b87  lea     rdx, aMkvmfsourcelib_99; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180018b8e  mov     rcx, rax; this
0x180018b91  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018b96  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180018b9d  jb      short loc_180018BC3
0x180018b9f  mov     edx, 0F0h
0x180018ba4  mov     [rsp+130h+var_110], edi
0x180018ba8  mov     r9, rsi
0x180018bab  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180018bb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180018bb9  mov     rcx, [rcx+10h]
0x180018bbd  call    WPP_SF_qD
0x180018bc2  nop
0x180018bc3  test    rbx, rbx
0x180018bc6  jz      short loc_180018BD8
0x180018bc8  mov     rax, [rbx]
0x180018bcb  mov     rcx, rbx
0x180018bce  mov     rax, [rax+10h]
0x180018bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bd7  nop
0x180018bd8  jmp     loc_180018C97
0x180018bdd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018be4  test    rcx, rcx
0x180018be7  jnz     short loc_180018C2A
0x180018be9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018bef  mov     rcx, rax
0x180018bf2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018bf9  test    rax, rax
0x180018bfc  jz      short loc_180018C1C
0x180018bfe  mov     rax, [rax]
0x180018c01  mov     edx, 7F0h
0x180018c06  mov     rax, [rax+8]
0x180018c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c0f  test    eax, eax
0x180018c11  jz      short loc_180018C1C
0x180018c13  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018c1a  jmp     short loc_180018C2A
0x180018c1c  lea     rcx, qword_1800D6F70; this
0x180018c23  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018c2a  cmp     byte ptr [rcx+8], 0
0x180018c2e  jz      short loc_180018C55
0x180018c30  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018c35  cmp     [rax+7CCh], edi
0x180018c3b  jz      short loc_180018C55
0x180018c3d  mov     r9d, edi; int
0x180018c40  mov     r8d, 0EA7h; int
0x180018c46  lea     rdx, aMkvmfsourcelib_99; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180018c4d  mov     rcx, rax; this
0x180018c50  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018c55  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180018c5c  jb      short loc_180018C82
0x180018c5e  mov     edx, 0F2h
0x180018c63  mov     [rsp+130h+var_110], edi
0x180018c67  mov     r9, rsi
0x180018c6a  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180018c71  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c78  mov     rcx, [rcx+10h]
0x180018c7c  call    WPP_SF_qD
0x180018c81  nop
0x180018c82  test    rbx, rbx
0x180018c85  jz      short loc_180018C97
0x180018c87  mov     rax, [rbx]
0x180018c8a  mov     rcx, rbx
0x180018c8d  mov     rax, [rax+10h]
0x180018c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c96  nop
0x180018c97  lea     rcx, [rsp+130h+var_F8]
0x180018c9c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018ca1  jmp     loc_180018ED1
  ... truncated ...
```
