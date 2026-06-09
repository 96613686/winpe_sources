# MkvMfSourceLib::MkvMfSource::OnCommand(bool,bool *)

- ea: `0x180015154`
- end: `0x180015495`
- name: `?OnCommand@MkvMfSource@MkvMfSourceLib@@AEAAJ_NPEA_N@Z`
- size: `833`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this, bool, bool *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18001fd1c`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000c854`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180015154`
- `0x1800157e4`
- `0x180016ba0`
- `0x180016dd8`
- `0x180017460`
- `0x180018f04`
- `0x180020be4`
- `0x180020d84`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001532d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001537f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001532d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001537f`

## string_xrefs

- `0x180015184`: `MkvMfSourceLib::MkvMfSource::OnCommand`
- `0x1800153dc`: `MkvMfSourceLib::MkvMfSource::OnCommand`
- `0x180015425`: `MkvMfSourceLib::MkvMfSource::OnCommand`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MkvMfSourceLib::MkvMfSource::OnCommand(MkvMfSourceLib::MkvMfSource *this, char a2, bool *a3)
{
  int v6; // esi
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v11; // ebx
  bool v12; // di
  _QWORD *v13; // rbx
  _DWORD *v14; // rdi
  int v15; // eax
  __int64 *v16; // rdx
  __int64 v17; // rcx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  struct CallStackContext *v24; // rax
  _BYTE v26[8]; // [rsp+30h] [rbp-58h] BYREF
  MkvMfSourceLib::MkvMfSource *v27; // [rsp+38h] [rbp-50h]
  _BYTE v28[16]; // [rsp+40h] [rbp-48h] BYREF

  v6 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v26, "MkvMfSourceLib::MkvMfSource::OnCommand", 1859);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 86) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 86) + 296LL))(*((_QWORD *)this + 86));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 86) + 280LL))(
                                                            *((_QWORD *)this + 86),
                                                            v28);
    *((_DWORD *)ThreadRelativeContext + 504) = v11;
  }
  v27 = this;
  if ( !*((_QWORD *)this + 18) )
  {
    std::list<MkvMfSourceLib::MkvMfSource::Command>::clear((char *)this + 664);
    v12 = 1;
    goto LABEL_53;
  }
  v12 = 0;
  if ( *((_QWORD *)this + 84) > 1u )
  {
    v13 = (_QWORD *)**((_QWORD **)this + 83);
    while ( 1 )
    {
      v13 = (_QWORD *)*v13;
      if ( v13 == *((_QWORD **)this + 83) )
        goto LABEL_53;
      v14 = v13 + 2;
      if ( (unsigned __int8)byte_1800D78D3 >= 4u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          181,
          &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
          this,
          *v14);
      if ( !*v14 )
      {
        if ( a2 )
          goto LABEL_27;
        v15 = MkvMfSourceLib::MkvMfSource::Command::OnStart((MkvMfSourceLib::MkvMfSource::Command *)(v13 + 2));
        goto LABEL_26;
      }
      if ( *v14 == 1 )
        break;
      switch ( *v14 )
      {
        case 2:
          if ( a2 )
            goto LABEL_27;
          v15 = MkvMfSourceLib::MkvMfSource::Command::OnRestart((MkvMfSourceLib::MkvMfSource::Command *)(v13 + 2));
LABEL_26:
          v6 = v15;
          goto LABEL_27;
        case 3:
          v6 = MkvMfSourceLib::MkvMfSource::Command::OnPause((MkvMfSourceLib::MkvMfSource::Command *)(v13 + 2));
          break;
        case 4:
          if ( !a2 )
          {
            v15 = MkvMfSourceLib::MkvMfSource::Command::OnStop((MkvMfSourceLib::MkvMfSource::Command *)(v13 + 2));
            goto LABEL_26;
          }
LABEL_27:
          v12 = 1;
          goto LABEL_28;
      }
      v12 = 0;
LABEL_28:
      if ( a2 && v12 )
      {
        if ( v6 < 0 )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v8, v9);
            CallStackTracing::s_wpInstance = v21;
            if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
            {
              v20 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v20 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v20 + 8) )
          {
            v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
            if ( *((_DWORD *)v22 + 499) != v6 )
              CallStackContext::TraceFailure(v22, "MkvMfSourceLib::MkvMfSource::OnCommand", 1928, v6);
          }
          if ( g_wppLevels )
          {
            v23 = 182;
LABEL_52:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v23,
              &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
              this,
              v6);
            goto LABEL_53;
          }
        }
        goto LABEL_53;
      }
      v16 = (__int64 *)**((_QWORD **)this + 83);
      v17 = *v16;
      --*((_QWORD *)this + 84);
      *(_QWORD *)v16[1] = v17;
      *(_QWORD *)(v17 + 8) = v16[1];
      std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *>::_Freenode<std::allocator<std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *>>>();
      if ( v6 < 0 )
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v8, v9);
          CallStackTracing::s_wpInstance = v19;
          if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
          {
            v18 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v18 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v18 + 8) )
        {
          v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
          if ( *((_DWORD *)v24 + 499) != v6 )
            CallStackContext::TraceFailure(v24, "MkvMfSourceLib::MkvMfSource::OnCommand", 1935, v6);
        }
        if ( g_wppLevels )
        {
          v23 = 183;
          goto LABEL_52;
        }
        goto LABEL_53;
      }
    }
    if ( a2 )
      goto LABEL_27;
    v15 = MkvMfSourceLib::MkvMfSource::Command::OnSeek((MkvMfSourceLib::MkvMfSource::Command *)(v13 + 2));
    goto LABEL_26;
  }
LABEL_53:
  if ( a3 )
    *a3 = v12;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v26);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180015154  mov     [rsp+arg_8], rbx
0x180015159  push    rbp
0x18001515a  push    rsi
0x18001515b  push    rdi
0x18001515c  push    r14
0x18001515e  push    r15
0x180015160  sub     rsp, 60h
0x180015164  mov     rax, cs:__security_cookie
0x18001516b  xor     rax, rsp
0x18001516e  mov     [rsp+88h+var_38], rax
0x180015173  mov     r15, r8
0x180015176  mov     r14b, dl
0x180015179  mov     rbp, rcx
0x18001517c  xor     esi, esi
0x18001517e  mov     r8d, 743h; int
0x180015184  lea     rdx, aMkvmfsourcelib_20; "MkvMfSourceLib::MkvMfSource::OnCommand"
0x18001518b  lea     rcx, [rsp+88h+var_58]; this
0x180015190  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180015195  nop
0x180015196  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001519d  cmp     [rcx+8], sil
0x1800151a1  jz      short loc_1800151F8
0x1800151a3  cmp     [rbp+2B0h], rsi
0x1800151aa  jz      short loc_1800151F8
0x1800151ac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800151b1  mov     rdi, rax
0x1800151b4  mov     rcx, [rbp+2B0h]
0x1800151bb  mov     rax, [rcx]
0x1800151be  mov     rax, [rax+128h]
0x1800151c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151ca  mov     ebx, eax
0x1800151cc  mov     rcx, [rbp+2B0h]
0x1800151d3  mov     rax, [rcx]
0x1800151d6  lea     rdx, [rsp+88h+var_48]
0x1800151db  mov     rax, [rax+118h]
0x1800151e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151e7  movups  xmm0, xmmword ptr [rax]
0x1800151ea  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800151f2  mov     [rdi+7E0h], ebx
0x1800151f8  mov     [rsp+88h+var_50], rbp
0x1800151fd  cmp     qword ptr [rbp+90h], 0
0x180015205  jnz     short loc_18001521B
0x180015207  lea     rcx, [rbp+298h]
0x18001520e  call    ?clear@?$list@VCommand@MkvMfSource@MkvMfSourceLib@@V?$allocator@VCommand@MkvMfSource@MkvMfSourceLib@@@std@@@std@@QEAAXXZ; std::list<MkvMfSourceLib::MkvMfSource::Command>::clear(void)
0x180015213  mov     dil, 1
0x180015216  jmp     loc_180015460
0x18001521b  xor     dil, dil
0x18001521e  cmp     qword ptr [rbp+2A0h], 1
0x180015226  jbe     loc_180015460
0x18001522c  mov     rax, [rbp+298h]
0x180015233  mov     rbx, [rax]
0x180015236  mov     rbx, [rbx]
0x180015239  cmp     rbx, [rbp+298h]
0x180015240  jz      loc_180015460
0x180015246  lea     rdi, [rbx+10h]
0x18001524a  cmp     cs:byte_1800D78D3, 4
0x180015251  jb      short loc_18001527B
0x180015253  mov     edx, 0B5h
0x180015258  mov     eax, [rdi]
0x18001525a  mov     [rsp+88h+var_68], eax
0x18001525e  mov     r9, rbp
0x180015261  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180015268  mov     rcx, cs:WPP_GLOBAL_Control
0x18001526f  mov     rcx, [rcx+88h]
0x180015276  call    WPP_SF_qD
0x18001527b  mov     ecx, [rdi]
0x18001527d  test    ecx, ecx
0x18001527f  jz      short loc_1800152D1
0x180015281  sub     ecx, 1
0x180015284  jz      short loc_1800152C2
0x180015286  sub     ecx, 1
0x180015289  jz      short loc_1800152B3
0x18001528b  sub     ecx, 1
0x18001528e  jz      short loc_1800152A4
0x180015290  cmp     ecx, 1
0x180015293  jnz     short loc_1800152AE
0x180015295  test    r14b, r14b
0x180015298  jnz     short loc_1800152E0
0x18001529a  mov     rcx, rdi; this
0x18001529d  call    ?OnStop@Command@MkvMfSource@MkvMfSourceLib@@QEBAJXZ; MkvMfSourceLib::MkvMfSource::Command::OnStop(void)
0x1800152a2  jmp     short loc_1800152DE
0x1800152a4  mov     rcx, rdi; this
0x1800152a7  call    ?OnPause@Command@MkvMfSource@MkvMfSourceLib@@QEBAJXZ; MkvMfSourceLib::MkvMfSource::Command::OnPause(void)
0x1800152ac  mov     esi, eax
0x1800152ae  xor     dil, dil
0x1800152b1  jmp     short loc_1800152E3
0x1800152b3  test    r14b, r14b
0x1800152b6  jnz     short loc_1800152E0
0x1800152b8  mov     rcx, rdi; this
0x1800152bb  call    ?OnRestart@Command@MkvMfSource@MkvMfSourceLib@@QEAAJXZ; MkvMfSourceLib::MkvMfSource::Command::OnRestart(void)
0x1800152c0  jmp     short loc_1800152DE
0x1800152c2  test    r14b, r14b
0x1800152c5  jnz     short loc_1800152E0
0x1800152c7  mov     rcx, rdi; this
0x1800152ca  call    ?OnSeek@Command@MkvMfSource@MkvMfSourceLib@@QEBAJXZ; MkvMfSourceLib::MkvMfSource::Command::OnSeek(void)
0x1800152cf  jmp     short loc_1800152DE
0x1800152d1  test    r14b, r14b
0x1800152d4  jnz     short loc_1800152E0
0x1800152d6  mov     rcx, rdi; this
0x1800152d9  call    ?OnStart@Command@MkvMfSource@MkvMfSourceLib@@QEAAJXZ; MkvMfSourceLib::MkvMfSource::Command::OnStart(void)
0x1800152de  mov     esi, eax
0x1800152e0  mov     dil, 1
0x1800152e3  test    r14b, r14b
0x1800152e6  jz      short loc_1800152ED
0x1800152e8  test    dil, dil
0x1800152eb  jnz     short loc_18001536B
0x1800152ed  mov     rax, [rbp+298h]
0x1800152f4  mov     rdx, [rax]
0x1800152f7  mov     rcx, [rdx]
0x1800152fa  dec     qword ptr [rbp+2A0h]
0x180015301  mov     rax, [rdx+8]
0x180015305  mov     [rax], rcx
0x180015308  mov     rax, [rdx+8]
0x18001530c  mov     [rcx+8], rax
0x180015310  call    ??$_Freenode@V?$allocator@U?$_List_node@VCommand@MkvMfSource@MkvMfSourceLib@@PEAX@std@@@std@@@?$_List_node@VCommand@MkvMfSource@MkvMfSourceLib@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VCommand@MkvMfSource@MkvMfSourceLib@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *>::_Freenode<std::allocator<std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *>>>(std::allocator<std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *>> &,std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *> *)
0x180015315  test    esi, esi
0x180015317  jns     loc_180015236
0x18001531d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015324  test    rcx, rcx
0x180015327  jnz     loc_180015409
0x18001532d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180015333  mov     rcx, rax
0x180015336  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001533d  test    rax, rax
0x180015340  jz      loc_1800153FB
0x180015346  mov     rax, [rax]
0x180015349  mov     edx, 7F0h
0x18001534e  mov     rax, [rax+8]
0x180015352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015357  test    eax, eax
0x180015359  jz      loc_1800153FB
0x18001535f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015366  jmp     loc_180015409
0x18001536b  test    esi, esi
0x18001536d  jns     loc_180015460
0x180015373  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001537a  test    rcx, rcx
0x18001537d  jnz     short loc_1800153C0
0x18001537f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180015385  mov     rcx, rax
0x180015388  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001538f  test    rax, rax
0x180015392  jz      short loc_1800153B2
0x180015394  mov     rax, [rax]
0x180015397  mov     edx, 7F0h
0x18001539c  mov     rax, [rax+8]
0x1800153a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153a5  test    eax, eax
0x1800153a7  jz      short loc_1800153B2
0x1800153a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800153b0  jmp     short loc_1800153C0
0x1800153b2  lea     rcx, qword_1800D6F70; this
0x1800153b9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800153c0  cmp     byte ptr [rcx+8], 0
0x1800153c4  jz      short loc_1800153EB
0x1800153c6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800153cb  cmp     [rax+7CCh], esi
0x1800153d1  jz      short loc_1800153EB
0x1800153d3  mov     r9d, esi; int
0x1800153d6  mov     r8d, 788h; int
0x1800153dc  lea     rdx, aMkvmfsourcelib_20; "MkvMfSourceLib::MkvMfSource::OnCommand"
0x1800153e3  mov     rcx, rax; this
0x1800153e6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800153eb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800153f2  jb      short loc_180015460
0x1800153f4  mov     edx, 0B6h
0x1800153f9  jmp     short loc_180015442
0x1800153fb  lea     rcx, qword_1800D6F70; this
0x180015402  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180015409  cmp     byte ptr [rcx+8], 0
0x18001540d  jz      short loc_180015434
0x18001540f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015414  cmp     [rax+7CCh], esi
0x18001541a  jz      short loc_180015434
0x18001541c  mov     r9d, esi; int
0x18001541f  mov     r8d, 78Fh; int
0x180015425  lea     rdx, aMkvmfsourcelib_20; "MkvMfSourceLib::MkvMfSource::OnCommand"
0x18001542c  mov     rcx, rax; this
0x18001542f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180015434  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001543b  jb      short loc_180015460
0x18001543d  mov     edx, 0B7h
0x180015442  mov     rcx, cs:WPP_GLOBAL_Control
0x180015449  mov     [rsp+88h+var_68], esi
0x18001544d  mov     r9, rbp
0x180015450  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180015457  mov     rcx, [rcx+10h]
0x18001545b  call    WPP_SF_qD
0x180015460  test    r15, r15
0x180015463  jz      short loc_180015468
0x180015465  mov     [r15], dil
0x180015468  lea     rcx, [rsp+88h+var_58]; this
0x18001546d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180015472  mov     eax, esi
0x180015474  mov     rcx, [rsp+88h+var_38]
0x180015479  xor     rcx, rsp; StackCookie
0x18001547c  call    __security_check_cookie
0x180015481  mov     rbx, [rsp+88h+arg_8]
0x180015489  add     rsp, 60h
0x18001548d  pop     r15
0x18001548f  pop     r14
0x180015491  pop     rdi
0x180015492  pop     rsi
0x180015493  pop     rbp
0x180015494  retn
```
