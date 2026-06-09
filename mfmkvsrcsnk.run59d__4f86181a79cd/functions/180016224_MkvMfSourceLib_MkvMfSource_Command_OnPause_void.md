# MkvMfSourceLib::MkvMfSource::Command::OnPause(void)

- ea: `0x180016224`
- end: `0x180016517`
- name: `?OnPause@Command@MkvMfSource@MkvMfSourceLib@@QEBAJXZ`
- size: `755`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource::Command *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180015b5c`

## callees

- `0x180002400`
- `0x180009b04`
- `0x180009bec`
- `0x18000d554`
- `0x18000ddc0`
- `0x18000e148`
- `0x180011720`
- `0x180016224`
- `0x180021b9c`
- `0x180024ca8`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001634b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016442`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001634b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016442`

## string_xrefs

- `0x180016245`: `MkvMfSourceLib::MkvMfSource::Command::OnPause`
- `0x1800163ae`: `MkvMfSourceLib::MkvMfSource::Command::OnPause`
- `0x1800164a5`: `MkvMfSourceLib::MkvMfSource::Command::OnPause`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MkvMfSourceLib::MkvMfSource::Command::OnPause(MkvMfSourceLib::MkvMfSource::Command *this)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v3; // ebx
  __int64 *v4; // rdi
  __int64 v5; // rbx
  MkvMfSourceLib::MkvMfStream *v6; // rbx
  __int64 v7; // rdx
  int v8; // esi
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  _BYTE v21[8]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v22; // [rsp+38h] [rbp-50h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v21,
    "MkvMfSourceLib::MkvMfSource::Command::OnPause",
    3614);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 2) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 296LL))(*((_QWORD *)this + 2));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 2) + 280LL))(
                                                            *((_QWORD *)this + 2),
                                                            v23);
    *((_DWORD *)ThreadRelativeContext + 504) = v3;
  }
  v4 = *(__int64 **)(*((_QWORD *)this + 1) + 576LL);
  v5 = *v4;
  v22 = *v4;
  while ( (__int64 *)v5 != v4 )
  {
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(&v22);
    v6 = *(MkvMfSourceLib::MkvMfStream **)(v5 + 40);
    v23[0] = v6;
    Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(v23);
    if ( (*(unsigned __int8 (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v6 + 120LL))(v6) )
    {
      if ( v6 )
        (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    else
    {
      v8 = MkvMfSourceLib::MkvMfStream::Pause(v6);
      if ( v8 < 0 )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v9, v10);
          CallStackTracing::s_wpInstance = v12;
          if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
          {
            v11 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v11 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v11 + 8) )
        {
          v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
          if ( *((_DWORD *)v13 + 499) != v8 )
            CallStackContext::TraceFailure(v13, "MkvMfSourceLib::MkvMfSource::Command::OnPause", 3636, v8);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            232,
            &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
            this,
            v8);
        if ( v6 )
          (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v6 + 16LL))(v6);
        goto LABEL_38;
      }
      if ( v6 )
        (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    v5 = v22;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, _QWORD, char *))(**((_QWORD **)this + 1) + 48LL))(
         *((_QWORD *)this + 1),
         209,
         &GUID_00000000_0000_0000_0000_000000000000,
         0,
         (char *)this + 32);
  if ( v8 >= 0 )
    goto LABEL_39;
  v17 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
    CallStackTracing::s_wpInstance = v18;
    if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v17 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v17 + 8) )
  {
    v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
    if ( *((_DWORD *)v19 + 499) != v8 )
      CallStackContext::TraceFailure(v19, "MkvMfSourceLib::MkvMfSource::Command::OnPause", 3639, v8);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v8);
LABEL_38:
  MkvMfSourceLib::MkvMfSource::Error(*((MkvMfSourceLib::MkvMfSource **)this + 1), L"Error pausing source.", v8);
LABEL_39:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v21);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180016224  push    rbx
0x180016226  push    rbp
0x180016227  push    rsi
0x180016228  push    rdi
0x180016229  sub     rsp, 68h
0x18001622d  mov     rax, cs:__security_cookie
0x180016234  xor     rax, rsp
0x180016237  mov     [rsp+88h+var_38], rax
0x18001623c  mov     rbp, rcx
0x18001623f  mov     r8d, 0E1Eh; int
0x180016245  lea     rdx, aMkvmfsourcelib_92; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x18001624c  lea     rcx, [rsp+88h+var_58]; this
0x180016251  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180016256  nop
0x180016257  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001625e  cmp     byte ptr [rcx+8], 0
0x180016262  jz      short loc_1800162B1
0x180016264  cmp     qword ptr [rbp+10h], 0
0x180016269  jz      short loc_1800162B1
0x18001626b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016270  mov     rdi, rax
0x180016273  mov     rcx, [rbp+10h]
0x180016277  mov     rdx, [rcx]
0x18001627a  mov     rax, [rdx+128h]
0x180016281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016286  mov     ebx, eax
0x180016288  mov     rcx, [rbp+10h]
0x18001628c  mov     rdx, [rcx]
0x18001628f  mov     rax, [rdx+118h]
0x180016296  lea     rdx, [rsp+88h+var_48]
0x18001629b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162a0  movups  xmm0, xmmword ptr [rax]
0x1800162a3  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800162ab  mov     [rdi+7E0h], ebx
0x1800162b1  mov     rdi, [rbp+8]
0x1800162b5  mov     rdi, [rdi+240h]
0x1800162bc  mov     rbx, [rdi]
0x1800162bf  mov     [rsp+88h+var_50], rbx
0x1800162c4  cmp     rbx, rdi
0x1800162c7  jz      loc_180016404
0x1800162cd  lea     rcx, [rsp+88h+var_50]
0x1800162d2  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(void)
0x1800162d7  mov     rbx, [rbx+28h]
0x1800162db  mov     [rsp+88h+var_48], rbx
0x1800162e0  lea     rcx, [rsp+88h+var_48]
0x1800162e5  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x1800162ea  nop
0x1800162eb  mov     rax, [rbx]
0x1800162ee  mov     rcx, rbx
0x1800162f1  mov     rax, [rax+78h]
0x1800162f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162fa  test    al, al
0x1800162fc  jz      short loc_18001631A
0x1800162fe  test    rbx, rbx
0x180016301  jz      short loc_180016313
0x180016303  mov     rax, [rbx]
0x180016306  mov     rcx, rbx
0x180016309  mov     rax, [rax+10h]
0x18001630d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016312  nop
0x180016313  mov     rbx, [rsp+88h+var_50]
0x180016318  jmp     short loc_1800162C4
0x18001631a  mov     rcx, rbx; this
0x18001631d  call    ?Pause@MkvMfStream@MkvMfSourceLib@@QEAAJXZ; MkvMfSourceLib::MkvMfStream::Pause(void)
0x180016322  mov     esi, eax
0x180016324  test    eax, eax
0x180016326  js      short loc_18001633F
0x180016328  test    rbx, rbx
0x18001632b  jz      short loc_18001633D
0x18001632d  mov     rax, [rbx]
0x180016330  mov     rcx, rbx
0x180016333  mov     rax, [rax+10h]
0x180016337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001633c  nop
0x18001633d  jmp     short loc_180016313
0x18001633f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016346  test    rcx, rcx
0x180016349  jnz     short loc_180016392
0x18001634b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180016352  nop     dword ptr [rax+rax+00h]
0x180016357  mov     rcx, rax
0x18001635a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180016361  test    rax, rax
0x180016364  jz      short loc_180016384
0x180016366  mov     rax, [rax]
0x180016369  mov     edx, 7F0h
0x18001636e  mov     rax, [rax+8]
0x180016372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016377  test    eax, eax
0x180016379  jz      short loc_180016384
0x18001637b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016382  jmp     short loc_180016392
0x180016384  lea     rcx, qword_1800DBF70; this
0x18001638b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180016392  cmp     byte ptr [rcx+8], 0
0x180016396  jz      short loc_1800163BD
0x180016398  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001639d  cmp     [rax+7CCh], esi
0x1800163a3  jz      short loc_1800163BD
0x1800163a5  mov     r9d, esi; int
0x1800163a8  mov     r8d, 0E34h; int
0x1800163ae  lea     rdx, aMkvmfsourcelib_92; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800163b5  mov     rcx, rax; this
0x1800163b8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800163bd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800163c4  jb      short loc_1800163EA
0x1800163c6  mov     edx, 0E8h
0x1800163cb  mov     dword ptr [rsp+88h+var_68], esi
0x1800163cf  mov     r9, rbp
0x1800163d2  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x1800163d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163e0  mov     rcx, [rcx+10h]
0x1800163e4  call    WPP_SF_qD
0x1800163e9  nop
0x1800163ea  test    rbx, rbx
0x1800163ed  jz      short loc_1800163FF
0x1800163ef  mov     rax, [rbx]
0x1800163f2  mov     rcx, rbx
0x1800163f5  mov     rax, [rax+10h]
0x1800163f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163fe  nop
0x1800163ff  jmp     loc_1800164E0
0x180016404  mov     rcx, [rbp+8]
0x180016408  mov     rax, [rcx]
0x18001640b  lea     rdx, [rbp+20h]
0x18001640f  mov     [rsp+88h+var_68], rdx
0x180016414  xor     r9d, r9d
0x180016417  lea     r8, _GUID_00000000_0000_0000_0000_000000000000
0x18001641e  mov     edx, 0D1h
0x180016423  mov     rax, [rax+30h]
0x180016427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001642c  mov     esi, eax
0x18001642e  test    eax, eax
0x180016430  jns     loc_1800164F4
0x180016436  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001643d  test    rcx, rcx
0x180016440  jnz     short loc_180016489
0x180016442  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180016449  nop     dword ptr [rax+rax+00h]
0x18001644e  mov     rcx, rax
0x180016451  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180016458  test    rax, rax
0x18001645b  jz      short loc_18001647B
0x18001645d  mov     rax, [rax]
0x180016460  mov     edx, 7F0h
0x180016465  mov     rax, [rax+8]
0x180016469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001646e  test    eax, eax
0x180016470  jz      short loc_18001647B
0x180016472  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016479  jmp     short loc_180016489
0x18001647b  lea     rcx, qword_1800DBF70; this
0x180016482  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180016489  cmp     byte ptr [rcx+8], 0
0x18001648d  jz      short loc_1800164B4
0x18001648f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016494  cmp     [rax+7CCh], esi
0x18001649a  jz      short loc_1800164B4
0x18001649c  mov     r9d, esi; int
0x18001649f  mov     r8d, 0E37h; int
0x1800164a5  lea     rdx, aMkvmfsourcelib_92; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800164ac  mov     rcx, rax; this
0x1800164af  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800164b4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800164bb  jb      short loc_1800164E0
0x1800164bd  mov     edx, 0E9h
0x1800164c2  mov     dword ptr [rsp+88h+var_68], esi
0x1800164c6  mov     r9, rbp
0x1800164c9  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x1800164d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800164d7  mov     rcx, [rcx+10h]
0x1800164db  call    WPP_SF_qD
0x1800164e0  mov     r8d, esi; int
0x1800164e3  lea     rdx, aErrorPausingSo; "Error pausing source."
0x1800164ea  mov     rcx, [rbp+8]; this
0x1800164ee  call    ?Error@MkvMfSource@MkvMfSourceLib@@AEAAJPEBGJ@Z; MkvMfSourceLib::MkvMfSource::Error(ushort const *,long)
0x1800164f3  nop
0x1800164f4  lea     rcx, [rsp+88h+var_58]; this
0x1800164f9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800164fe  mov     eax, esi
0x180016500  mov     rcx, [rsp+88h+var_38]
0x180016505  xor     rcx, rsp; StackCookie
0x180016508  call    __security_check_cookie
0x18001650d  add     rsp, 68h
0x180016511  pop     rdi
0x180016512  pop     rsi
0x180016513  pop     rbp
0x180016514  pop     rbx
0x180016515  retn
```
