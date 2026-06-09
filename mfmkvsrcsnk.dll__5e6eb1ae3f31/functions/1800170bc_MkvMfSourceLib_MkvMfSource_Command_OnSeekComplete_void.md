# MkvMfSourceLib::MkvMfSource::Command::OnSeekComplete(void)

- ea: `0x1800170bc`
- end: `0x180017459`
- name: `?OnSeekComplete@Command@MkvMfSource@MkvMfSourceLib@@AEBAJXZ`
- size: `925`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource::Command *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180016dd8`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x1800098b8`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x18000db40`
- `0x1800170bc`
- `0x18001be98`
- `0x180020d84`
- `0x180025c14`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017170`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017255`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017381`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017170`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017255`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017381`

## string_xrefs

- `0x1800170e3`: `MkvMfSourceLib::MkvMfSource::Command::OnSeekComplete`
- `0x1800171ca`: `MkvMfSourceLib::MkvMfSource::Command::OnSeekComplete`
- `0x1800172b2`: `MkvMfSourceLib::MkvMfSource::Command::OnSeekComplete`
- `0x1800173de`: `MkvMfSourceLib::MkvMfSource::Command::OnSeekComplete`

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
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v16 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v27 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x1800170bc  push    rbx
0x1800170be  push    rbp
0x1800170bf  push    rsi
0x1800170c0  push    rdi
0x1800170c1  push    r14
0x1800170c3  push    r15
0x1800170c5  sub     rsp, 68h
0x1800170c9  mov     rax, cs:__security_cookie
0x1800170d0  xor     rax, rsp
0x1800170d3  mov     [rsp+98h+var_48], rax
0x1800170d8  mov     rsi, rcx
0x1800170db  mov     ebp, 0F70h
0x1800170e0  mov     r8d, ebp; int
0x1800170e3  lea     rdx, aMkvmfsourcelib_64; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800170ea  lea     rcx, [rsp+98h+var_68]; this
0x1800170ef  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800170f4  nop
0x1800170f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800170fc  cmp     byte ptr [rcx+8], 0
0x180017100  jz      short loc_18001714F
0x180017102  cmp     qword ptr [rsi+10h], 0
0x180017107  jz      short loc_18001714F
0x180017109  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001710e  mov     rdi, rax
0x180017111  mov     rcx, [rsi+10h]
0x180017115  mov     rdx, [rcx]
0x180017118  mov     rax, [rdx+128h]
0x18001711f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017124  mov     ebx, eax
0x180017126  mov     rcx, [rsi+10h]
0x18001712a  mov     rdx, [rcx]
0x18001712d  mov     rax, [rdx+118h]
0x180017134  lea     rdx, [rsp+98h+var_58]
0x180017139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001713e  movups  xmm0, xmmword ptr [rax]
0x180017141  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180017149  mov     [rdi+7E0h], ebx
0x18001714f  xor     edx, edx; bool
0x180017151  mov     rcx, [rsi+8]; this
0x180017155  call    ?SetEOP@MkvMfSource@MkvMfSourceLib@@AEAAJ_N@Z; MkvMfSourceLib::MkvMfSource::SetEOP(bool)
0x18001715a  mov     ebx, eax
0x18001715c  test    eax, eax
0x18001715e  jns     loc_180017217
0x180017164  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001716b  test    rcx, rcx
0x18001716e  jnz     short loc_1800171B1
0x180017170  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180017176  mov     rcx, rax
0x180017179  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017180  test    rax, rax
0x180017183  jz      short loc_1800171A3
0x180017185  mov     rax, [rax]
0x180017188  mov     edx, 7F0h
0x18001718d  mov     rax, [rax+8]
0x180017191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017196  test    eax, eax
0x180017198  jz      short loc_1800171A3
0x18001719a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800171a1  jmp     short loc_1800171B1
0x1800171a3  lea     rcx, qword_1800D6F70; this
0x1800171aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800171b1  cmp     byte ptr [rcx+8], 0
0x1800171b5  jz      short loc_1800171D9
0x1800171b7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800171bc  cmp     [rax+7CCh], ebx
0x1800171c2  jz      short loc_1800171D9
0x1800171c4  mov     r9d, ebx; int
0x1800171c7  mov     r8d, ebp; int
0x1800171ca  lea     rdx, aMkvmfsourcelib_64; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800171d1  mov     rcx, rax; this
0x1800171d4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800171d9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800171e0  jb      short loc_180017206
0x1800171e2  mov     edx, 102h
0x1800171e7  mov     dword ptr [rsp+98h+var_78], ebx
0x1800171eb  mov     r9, rsi
0x1800171ee  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x1800171f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171fc  mov     rcx, [rcx+10h]
0x180017200  call    WPP_SF_qD
0x180017205  nop
0x180017206  lea     rcx, [rsp+98h+var_68]; this
0x18001720b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180017210  mov     eax, ebx
0x180017212  jmp     loc_18001743F
0x180017217  mov     rcx, [rsi+8]
0x18001721b  lea     r14, [rsi+20h]
0x18001721f  mov     rax, [rcx]
0x180017222  mov     [rsp+98h+var_78], r14
0x180017227  xor     r9d, r9d
0x18001722a  lea     r8, _GUID_00000000_0000_0000_0000_000000000000
0x180017231  mov     edx, 0CBh
0x180017236  mov     rax, [rax+30h]
0x18001723a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001723f  mov     ebx, eax
0x180017241  test    eax, eax
0x180017243  jns     loc_1800172D8
0x180017249  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017250  test    rcx, rcx
0x180017253  jnz     short loc_180017296
0x180017255  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001725b  mov     rcx, rax
0x18001725e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017265  test    rax, rax
0x180017268  jz      short loc_180017288
0x18001726a  mov     rax, [rax]
0x18001726d  mov     edx, 7F0h
0x180017272  mov     rax, [rax+8]
0x180017276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001727b  test    eax, eax
0x18001727d  jz      short loc_180017288
0x18001727f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017286  jmp     short loc_180017296
0x180017288  lea     rcx, qword_1800D6F70; this
0x18001728f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180017296  cmp     byte ptr [rcx+8], 0
0x18001729a  jz      short loc_1800172C1
0x18001729c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800172a1  cmp     [rax+7CCh], ebx
0x1800172a7  jz      short loc_1800172C1
0x1800172a9  mov     r9d, ebx; int
0x1800172ac  mov     r8d, 0F72h; int
0x1800172b2  lea     rdx, aMkvmfsourcelib_64; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800172b9  mov     rcx, rax; this
0x1800172bc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800172c1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800172c8  jb      loc_180017206
0x1800172ce  mov     edx, 103h
0x1800172d3  jmp     loc_1800171E7
0x1800172d8  mov     rdi, [rsi+8]
0x1800172dc  mov     rdi, [rdi+240h]
0x1800172e3  mov     rbx, [rdi]
0x1800172e6  mov     [rsp+98h+var_60], rbx
0x1800172eb  imul    r15, [rsi+28h], 64h ; 'd'
0x1800172f0  cmp     rbx, rdi
0x1800172f3  jz      loc_180017431
0x1800172f9  lea     rcx, [rsp+98h+var_60]
0x1800172fe  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(void)
0x180017303  mov     rbx, [rbx+28h]
0x180017307  mov     [rsp+98h+var_58], rbx
0x18001730c  lea     rcx, [rsp+98h+var_58]
0x180017311  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x180017316  nop
0x180017317  mov     rax, [rbx]
0x18001731a  mov     rcx, rbx
0x18001731d  mov     rax, [rax+78h]
0x180017321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017326  test    al, al
0x180017328  jz      short loc_180017346
0x18001732a  test    rbx, rbx
0x18001732d  jz      short loc_18001733F
0x18001732f  mov     rax, [rbx]
0x180017332  mov     rcx, rbx
0x180017335  mov     rax, [rax+10h]
0x180017339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001733e  nop
0x18001733f  mov     rbx, [rsp+98h+var_60]
0x180017344  jmp     short loc_1800172F0
0x180017346  mov     rdx, r14; struct tagPROPVARIANT *
0x180017349  mov     rcx, rbx; this
0x18001734c  call    ?Seek@MkvMfStream@MkvMfSourceLib@@QEAAJAEBUtagPROPVARIANT@@@Z; MkvMfSourceLib::MkvMfStream::Seek(tagPROPVARIANT const &)
0x180017351  mov     ebp, eax
0x180017353  test    eax, eax
0x180017355  js      short loc_180017375
0x180017357  mov     [rbx+108h], r15
0x18001735e  test    rbx, rbx
0x180017361  jz      short loc_180017373
0x180017363  mov     rax, [rbx]
0x180017366  mov     rcx, rbx
0x180017369  mov     rax, [rax+10h]
0x18001736d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017372  nop
0x180017373  jmp     short loc_18001733F
0x180017375  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001737c  test    rcx, rcx
0x18001737f  jnz     short loc_1800173C2
0x180017381  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180017387  mov     rcx, rax
0x18001738a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017391  test    rax, rax
0x180017394  jz      short loc_1800173B4
0x180017396  mov     rax, [rax]
0x180017399  mov     edx, 7F0h
0x18001739e  mov     rax, [rax+8]
0x1800173a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173a7  test    eax, eax
0x1800173a9  jz      short loc_1800173B4
0x1800173ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800173b2  jmp     short loc_1800173C2
0x1800173b4  lea     rcx, qword_1800D6F70; this
0x1800173bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800173c2  cmp     byte ptr [rcx+8], 0
0x1800173c6  jz      short loc_1800173ED
0x1800173c8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800173cd  cmp     [rax+7CCh], ebp
0x1800173d3  jz      short loc_1800173ED
0x1800173d5  mov     r9d, ebp; int
0x1800173d8  mov     r8d, 0F88h; int
0x1800173de  lea     rdx, aMkvmfsourcelib_64; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800173e5  mov     rcx, rax; this
0x1800173e8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800173ed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800173f4  jb      short loc_18001741A
0x1800173f6  mov     edx, 104h
0x1800173fb  mov     dword ptr [rsp+98h+var_78], ebp
0x1800173ff  mov     r9, rsi
0x180017402  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180017409  mov     rcx, cs:WPP_GLOBAL_Control
0x180017410  mov     rcx, [rcx+10h]
0x180017414  call    WPP_SF_qD
0x180017419  nop
0x18001741a  test    rbx, rbx
0x18001741d  jz      short loc_18001742F
0x18001741f  mov     rax, [rbx]
0x180017422  mov     rcx, rbx
0x180017425  mov     rax, [rax+10h]
0x180017429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001742e  nop
0x18001742f  jmp     short loc_180017433
0x180017431  xor     ebp, ebp
0x180017433  lea     rcx, [rsp+98h+var_68]; this
0x180017438  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001743d  mov     eax, ebp
0x18001743f  mov     rcx, [rsp+98h+var_48]
0x180017444  xor     rcx, rsp; StackCookie
0x180017447  call    __security_check_cookie
0x18001744c  add     rsp, 68h
0x180017450  pop     r15
0x180017452  pop     r14
0x180017454  pop     rdi
0x180017455  pop     rsi
0x180017456  pop     rbp
0x180017457  pop     rbx
0x180017458  retn
```
