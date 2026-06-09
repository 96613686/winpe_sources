# MkvMfSourceLib::MkvMfSource::Command::OnSeekComplete(void)

- ea: `0x180017b90`
- end: `0x180017f40`
- name: `?OnSeekComplete@Command@MkvMfSource@MkvMfSourceLib@@AEBAJXZ`
- size: `944`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource::Command *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001789c`

## callees

- `0x180002400`
- `0x180009b04`
- `0x180009bec`
- `0x18000d554`
- `0x18000ddc0`
- `0x18000e148`
- `0x180017b90`
- `0x18001cb78`
- `0x180021b9c`
- `0x180026c08`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017c44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017d2f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017e61`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017c44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017d2f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017e61`

## string_xrefs

- `0x180017bb7`: `MkvMfSourceLib::MkvMfSource::Command::OnSeekComplete`
- `0x180017ca4`: `MkvMfSourceLib::MkvMfSource::Command::OnSeekComplete`
- `0x180017d92`: `MkvMfSourceLib::MkvMfSource::Command::OnSeekComplete`
- `0x180017ec4`: `MkvMfSourceLib::MkvMfSource::Command::OnSeekComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MkvMfSourceLib::MkvMfSource::Command::OnSeekComplete(MkvMfSourceLib::MkvMfSource::Command *this)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v3; // ebx
  __int64 v4; // rdx
  int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  _QWORD *v19; // rdi
  _QWORD *v20; // rbx
  __int64 v21; // r15
  MkvMfSourceLib::MkvMfStream *v22; // rbx
  __int64 v23; // rdx
  int v24; // ebp
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  char v30[8]; // [rsp+30h] [rbp-68h] BYREF
  _QWORD *v31; // [rsp+38h] [rbp-60h] BYREF
  _QWORD v32[2]; // [rsp+40h] [rbp-58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v30,
    "MkvMfSourceLib::MkvMfSource::Command::OnSeekComplete",
    3952);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 2) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 296LL))(*((_QWORD *)this + 2));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 2) + 280LL))(
                                                            *((_QWORD *)this + 2),
                                                            v32);
    *((_DWORD *)ThreadRelativeContext + 504) = v3;
  }
  v5 = MkvMfSourceLib::MkvMfSource::SetEOP(*((MkvMfSourceLib::MkvMfSource **)this + 1), 0);
  if ( v5 < 0 )
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v10 + 499) != v5 )
        CallStackContext::TraceFailure(v10, "MkvMfSourceLib::MkvMfSource::Command::OnSeekComplete", 3952, v5);
    }
    if ( !g_wppLevels )
      goto LABEL_16;
    v11 = 258;
LABEL_15:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v5);
LABEL_16:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v30);
    return (unsigned int)v5;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, _QWORD, char *))(**((_QWORD **)this + 1) + 48LL))(
         *((_QWORD *)this + 1),
         203,
         &GUID_00000000_0000_0000_0000_000000000000,
         0,
         (char *)this + 32);
  if ( v5 < 0 )
  {
    v16 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)v18 + 499) != v5 )
        CallStackContext::TraceFailure(v18, "MkvMfSourceLib::MkvMfSource::Command::OnSeekComplete", 3954, v5);
    }
    if ( !g_wppLevels )
      goto LABEL_16;
    v11 = 259;
    goto LABEL_15;
  }
  v19 = *(_QWORD **)(*((_QWORD *)this + 1) + 576LL);
  v20 = (_QWORD *)*v19;
  v31 = (_QWORD *)*v19;
  v21 = 100LL * *((_QWORD *)this + 5);
  while ( 1 )
  {
    if ( v20 == v19 )
    {
      v24 = 0;
      goto LABEL_52;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(&v31);
    v22 = (MkvMfSourceLib::MkvMfStream *)v20[5];
    v32[0] = v22;
    Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(v32);
    if ( (*(unsigned __int8 (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v22 + 120LL))(v22) )
    {
      if ( v22 )
        (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v22 + 16LL))(v22);
      goto LABEL_33;
    }
    v24 = MkvMfSourceLib::MkvMfStream::Seek(v22, (const struct tagPROPVARIANT *)((char *)this + 32));
    if ( v24 < 0 )
      break;
    *((_QWORD *)v22 + 33) = v21;
    if ( v22 )
      (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v22 + 16LL))(v22);
LABEL_33:
    v20 = v31;
  }
  v27 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v25, v26);
    CallStackTracing::s_wpInstance = v28;
    if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
    {
      v27 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v27 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v27 + 8) )
  {
    v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
    if ( *((_DWORD *)v29 + 499) != v24 )
      CallStackContext::TraceFailure(v29, "MkvMfSourceLib::MkvMfSource::Command::OnSeekComplete", 3976, v24);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 260, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v24);
  if ( v22 )
    (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v22 + 16LL))(v22);
LABEL_52:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v30);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x180017b90  push    rbx
0x180017b92  push    rbp
0x180017b93  push    rsi
0x180017b94  push    rdi
0x180017b95  push    r14
0x180017b97  push    r15
0x180017b99  sub     rsp, 68h
0x180017b9d  mov     rax, cs:__security_cookie
0x180017ba4  xor     rax, rsp
0x180017ba7  mov     [rsp+98h+var_48], rax
0x180017bac  mov     rsi, rcx
0x180017baf  mov     ebp, 0F70h
0x180017bb4  mov     r8d, ebp; int
0x180017bb7  lea     rdx, aMkvmfsourcelib_64; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180017bbe  lea     rcx, [rsp+98h+var_68]; this
0x180017bc3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180017bc8  nop
0x180017bc9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180017bd0  cmp     byte ptr [rcx+8], 0
0x180017bd4  jz      short loc_180017C23
0x180017bd6  cmp     qword ptr [rsi+10h], 0
0x180017bdb  jz      short loc_180017C23
0x180017bdd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017be2  mov     rdi, rax
0x180017be5  mov     rcx, [rsi+10h]
0x180017be9  mov     rdx, [rcx]
0x180017bec  mov     rax, [rdx+128h]
0x180017bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bf8  mov     ebx, eax
0x180017bfa  mov     rcx, [rsi+10h]
0x180017bfe  mov     rdx, [rcx]
0x180017c01  mov     rax, [rdx+118h]
0x180017c08  lea     rdx, [rsp+98h+var_58]
0x180017c0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c12  movups  xmm0, xmmword ptr [rax]
0x180017c15  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180017c1d  mov     [rdi+7E0h], ebx
0x180017c23  xor     edx, edx; bool
0x180017c25  mov     rcx, [rsi+8]; this
0x180017c29  call    ?SetEOP@MkvMfSource@MkvMfSourceLib@@AEAAJ_N@Z; MkvMfSourceLib::MkvMfSource::SetEOP(bool)
0x180017c2e  mov     ebx, eax
0x180017c30  test    eax, eax
0x180017c32  jns     loc_180017CF1
0x180017c38  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017c3f  test    rcx, rcx
0x180017c42  jnz     short loc_180017C8B
0x180017c44  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180017c4b  nop     dword ptr [rax+rax+00h]
0x180017c50  mov     rcx, rax
0x180017c53  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017c5a  test    rax, rax
0x180017c5d  jz      short loc_180017C7D
0x180017c5f  mov     rax, [rax]
0x180017c62  mov     edx, 7F0h
0x180017c67  mov     rax, [rax+8]
0x180017c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c70  test    eax, eax
0x180017c72  jz      short loc_180017C7D
0x180017c74  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017c7b  jmp     short loc_180017C8B
0x180017c7d  lea     rcx, qword_1800DBF70; this
0x180017c84  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180017c8b  cmp     byte ptr [rcx+8], 0
0x180017c8f  jz      short loc_180017CB3
0x180017c91  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017c96  cmp     [rax+7CCh], ebx
0x180017c9c  jz      short loc_180017CB3
0x180017c9e  mov     r9d, ebx; int
0x180017ca1  mov     r8d, ebp; int
0x180017ca4  lea     rdx, aMkvmfsourcelib_64; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180017cab  mov     rcx, rax; this
0x180017cae  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180017cb3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180017cba  jb      short loc_180017CE0
0x180017cbc  mov     edx, 102h
0x180017cc1  mov     dword ptr [rsp+98h+var_78], ebx
0x180017cc5  mov     r9, rsi
0x180017cc8  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180017ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180017cd6  mov     rcx, [rcx+10h]
0x180017cda  call    WPP_SF_qD
0x180017cdf  nop
0x180017ce0  lea     rcx, [rsp+98h+var_68]; this
0x180017ce5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180017cea  mov     eax, ebx
0x180017cec  jmp     loc_180017F25
0x180017cf1  mov     rcx, [rsi+8]
0x180017cf5  lea     r14, [rsi+20h]
0x180017cf9  mov     rax, [rcx]
0x180017cfc  mov     [rsp+98h+var_78], r14
0x180017d01  xor     r9d, r9d
0x180017d04  lea     r8, _GUID_00000000_0000_0000_0000_000000000000
0x180017d0b  mov     edx, 0CBh
0x180017d10  mov     rax, [rax+30h]
0x180017d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d19  mov     ebx, eax
0x180017d1b  test    eax, eax
0x180017d1d  jns     loc_180017DB8
0x180017d23  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017d2a  test    rcx, rcx
0x180017d2d  jnz     short loc_180017D76
0x180017d2f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180017d36  nop     dword ptr [rax+rax+00h]
0x180017d3b  mov     rcx, rax
0x180017d3e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017d45  test    rax, rax
0x180017d48  jz      short loc_180017D68
0x180017d4a  mov     rax, [rax]
0x180017d4d  mov     edx, 7F0h
0x180017d52  mov     rax, [rax+8]
0x180017d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d5b  test    eax, eax
0x180017d5d  jz      short loc_180017D68
0x180017d5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017d66  jmp     short loc_180017D76
0x180017d68  lea     rcx, qword_1800DBF70; this
0x180017d6f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180017d76  cmp     byte ptr [rcx+8], 0
0x180017d7a  jz      short loc_180017DA1
0x180017d7c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017d81  cmp     [rax+7CCh], ebx
0x180017d87  jz      short loc_180017DA1
0x180017d89  mov     r9d, ebx; int
0x180017d8c  mov     r8d, 0F72h; int
0x180017d92  lea     rdx, aMkvmfsourcelib_64; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180017d99  mov     rcx, rax; this
0x180017d9c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180017da1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180017da8  jb      loc_180017CE0
0x180017dae  mov     edx, 103h
0x180017db3  jmp     loc_180017CC1
0x180017db8  mov     rdi, [rsi+8]
0x180017dbc  mov     rdi, [rdi+240h]
0x180017dc3  mov     rbx, [rdi]
0x180017dc6  mov     [rsp+98h+var_60], rbx
0x180017dcb  imul    r15, [rsi+28h], 64h ; 'd'
0x180017dd0  cmp     rbx, rdi
0x180017dd3  jz      loc_180017F17
0x180017dd9  lea     rcx, [rsp+98h+var_60]
0x180017dde  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(void)
0x180017de3  mov     rbx, [rbx+28h]
0x180017de7  mov     [rsp+98h+var_58], rbx
0x180017dec  lea     rcx, [rsp+98h+var_58]
0x180017df1  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x180017df6  nop
0x180017df7  mov     rax, [rbx]
0x180017dfa  mov     rcx, rbx
0x180017dfd  mov     rax, [rax+78h]
0x180017e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e06  test    al, al
0x180017e08  jz      short loc_180017E26
0x180017e0a  test    rbx, rbx
0x180017e0d  jz      short loc_180017E1F
0x180017e0f  mov     rax, [rbx]
0x180017e12  mov     rcx, rbx
0x180017e15  mov     rax, [rax+10h]
0x180017e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e1e  nop
0x180017e1f  mov     rbx, [rsp+98h+var_60]
0x180017e24  jmp     short loc_180017DD0
0x180017e26  mov     rdx, r14; struct tagPROPVARIANT *
0x180017e29  mov     rcx, rbx; this
0x180017e2c  call    ?Seek@MkvMfStream@MkvMfSourceLib@@QEAAJAEBUtagPROPVARIANT@@@Z; MkvMfSourceLib::MkvMfStream::Seek(tagPROPVARIANT const &)
0x180017e31  mov     ebp, eax
0x180017e33  test    eax, eax
0x180017e35  js      short loc_180017E55
0x180017e37  mov     [rbx+108h], r15
0x180017e3e  test    rbx, rbx
0x180017e41  jz      short loc_180017E53
0x180017e43  mov     rax, [rbx]
0x180017e46  mov     rcx, rbx
0x180017e49  mov     rax, [rax+10h]
0x180017e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e52  nop
0x180017e53  jmp     short loc_180017E1F
0x180017e55  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017e5c  test    rcx, rcx
0x180017e5f  jnz     short loc_180017EA8
0x180017e61  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180017e68  nop     dword ptr [rax+rax+00h]
0x180017e6d  mov     rcx, rax
0x180017e70  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017e77  test    rax, rax
0x180017e7a  jz      short loc_180017E9A
0x180017e7c  mov     rax, [rax]
0x180017e7f  mov     edx, 7F0h
0x180017e84  mov     rax, [rax+8]
0x180017e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e8d  test    eax, eax
0x180017e8f  jz      short loc_180017E9A
0x180017e91  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017e98  jmp     short loc_180017EA8
0x180017e9a  lea     rcx, qword_1800DBF70; this
0x180017ea1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180017ea8  cmp     byte ptr [rcx+8], 0
0x180017eac  jz      short loc_180017ED3
0x180017eae  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017eb3  cmp     [rax+7CCh], ebp
0x180017eb9  jz      short loc_180017ED3
0x180017ebb  mov     r9d, ebp; int
0x180017ebe  mov     r8d, 0F88h; int
0x180017ec4  lea     rdx, aMkvmfsourcelib_64; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180017ecb  mov     rcx, rax; this
0x180017ece  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180017ed3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180017eda  jb      short loc_180017F00
0x180017edc  mov     edx, 104h
0x180017ee1  mov     dword ptr [rsp+98h+var_78], ebp
0x180017ee5  mov     r9, rsi
0x180017ee8  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180017eef  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ef6  mov     rcx, [rcx+10h]
0x180017efa  call    WPP_SF_qD
0x180017eff  nop
0x180017f00  test    rbx, rbx
0x180017f03  jz      short loc_180017F15
0x180017f05  mov     rax, [rbx]
0x180017f08  mov     rcx, rbx
0x180017f0b  mov     rax, [rax+10h]
0x180017f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f14  nop
0x180017f15  jmp     short loc_180017F19
0x180017f17  xor     ebp, ebp
0x180017f19  lea     rcx, [rsp+98h+var_68]; this
0x180017f1e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180017f23  mov     eax, ebp
0x180017f25  mov     rcx, [rsp+98h+var_48]
0x180017f2a  xor     rcx, rsp; StackCookie
0x180017f2d  call    __security_check_cookie
0x180017f32  add     rsp, 68h
0x180017f36  pop     r15
0x180017f38  pop     r14
0x180017f3a  pop     rdi
0x180017f3b  pop     rsi
0x180017f3c  pop     rbp
0x180017f3d  pop     rbx
0x180017f3e  retn
```
