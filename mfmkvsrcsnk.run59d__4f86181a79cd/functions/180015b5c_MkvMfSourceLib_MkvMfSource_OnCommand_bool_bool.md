# MkvMfSourceLib::MkvMfSource::OnCommand(bool,bool *)

- ea: `0x180015b5c`
- end: `0x180015eae`
- name: `?OnCommand@MkvMfSource@MkvMfSourceLib@@AEAAJ_NPEA_N@Z`
- size: `850`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this, bool, bool *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180020b30`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000cde4`
- `0x18000d554`
- `0x18000ddc0`
- `0x180015b5c`
- `0x180016224`
- `0x180017658`
- `0x18001789c`
- `0x180017f48`
- `0x180019a74`
- `0x180021a88`
- `0x180021b9c`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015d39`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015d91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015d39`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015d91`

## string_xrefs

- `0x180015b8c`: `MkvMfSourceLib::MkvMfSource::OnCommand`
- `0x180015df4`: `MkvMfSourceLib::MkvMfSource::OnCommand`
- `0x180015e3d`: `MkvMfSourceLib::MkvMfSource::OnCommand`

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
      if ( (unsigned __int8)byte_1800DC8D3 >= 4u )
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
              v20 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v18 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180015b5c  mov     [rsp+arg_8], rbx
0x180015b61  push    rbp
0x180015b62  push    rsi
0x180015b63  push    rdi
0x180015b64  push    r14
0x180015b66  push    r15
0x180015b68  sub     rsp, 60h
0x180015b6c  mov     rax, cs:__security_cookie
0x180015b73  xor     rax, rsp
0x180015b76  mov     [rsp+88h+var_38], rax
0x180015b7b  mov     r15, r8
0x180015b7e  mov     r14b, dl
0x180015b81  mov     rbp, rcx
0x180015b84  xor     esi, esi
0x180015b86  mov     r8d, 743h; int
0x180015b8c  lea     rdx, aMkvmfsourcelib_20; "MkvMfSourceLib::MkvMfSource::OnCommand"
0x180015b93  lea     rcx, [rsp+88h+var_58]; this
0x180015b98  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180015b9d  nop
0x180015b9e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180015ba5  cmp     [rcx+8], sil
0x180015ba9  jz      short loc_180015C00
0x180015bab  cmp     [rbp+2B0h], rsi
0x180015bb2  jz      short loc_180015C00
0x180015bb4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015bb9  mov     rdi, rax
0x180015bbc  mov     rcx, [rbp+2B0h]
0x180015bc3  mov     rax, [rcx]
0x180015bc6  mov     rax, [rax+128h]
0x180015bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bd2  mov     ebx, eax
0x180015bd4  mov     rcx, [rbp+2B0h]
0x180015bdb  mov     rax, [rcx]
0x180015bde  lea     rdx, [rsp+88h+var_48]
0x180015be3  mov     rax, [rax+118h]
0x180015bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bef  movups  xmm0, xmmword ptr [rax]
0x180015bf2  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180015bfa  mov     [rdi+7E0h], ebx
0x180015c00  mov     [rsp+88h+var_50], rbp
0x180015c05  cmp     qword ptr [rbp+90h], 0
0x180015c0d  jnz     short loc_180015C23
0x180015c0f  lea     rcx, [rbp+298h]
0x180015c16  call    ?clear@?$list@VCommand@MkvMfSource@MkvMfSourceLib@@V?$allocator@VCommand@MkvMfSource@MkvMfSourceLib@@@std@@@std@@QEAAXXZ; std::list<MkvMfSourceLib::MkvMfSource::Command>::clear(void)
0x180015c1b  mov     dil, 1
0x180015c1e  jmp     loc_180015E78
0x180015c23  xor     dil, dil
0x180015c26  cmp     qword ptr [rbp+2A0h], 1
0x180015c2e  jbe     loc_180015E78
0x180015c34  mov     rax, [rbp+298h]
0x180015c3b  mov     rbx, [rax]
0x180015c3e  mov     rbx, [rbx]
0x180015c41  cmp     rbx, [rbp+298h]
0x180015c48  jz      loc_180015E78
0x180015c4e  lea     rdi, [rbx+10h]
0x180015c52  cmp     cs:byte_1800DC8D3, 4
0x180015c59  jb      short loc_180015C83
0x180015c5b  mov     edx, 0B5h
0x180015c60  mov     eax, [rdi]
0x180015c62  mov     [rsp+88h+var_68], eax
0x180015c66  mov     r9, rbp
0x180015c69  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180015c70  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c77  mov     rcx, [rcx+88h]
0x180015c7e  call    WPP_SF_qD
0x180015c83  mov     ecx, [rdi]
0x180015c85  test    ecx, ecx
0x180015c87  jz      short loc_180015CD9
0x180015c89  sub     ecx, 1
0x180015c8c  jz      short loc_180015CCA
0x180015c8e  sub     ecx, 1
0x180015c91  jz      short loc_180015CBB
0x180015c93  sub     ecx, 1
0x180015c96  jz      short loc_180015CAC
0x180015c98  cmp     ecx, 1
0x180015c9b  jnz     short loc_180015CB6
0x180015c9d  test    r14b, r14b
0x180015ca0  jnz     short loc_180015CE8
0x180015ca2  mov     rcx, rdi; this
0x180015ca5  call    ?OnStop@Command@MkvMfSource@MkvMfSourceLib@@QEBAJXZ; MkvMfSourceLib::MkvMfSource::Command::OnStop(void)
0x180015caa  jmp     short loc_180015CE6
0x180015cac  mov     rcx, rdi; this
0x180015caf  call    ?OnPause@Command@MkvMfSource@MkvMfSourceLib@@QEBAJXZ; MkvMfSourceLib::MkvMfSource::Command::OnPause(void)
0x180015cb4  mov     esi, eax
0x180015cb6  xor     dil, dil
0x180015cb9  jmp     short loc_180015CEB
0x180015cbb  test    r14b, r14b
0x180015cbe  jnz     short loc_180015CE8
0x180015cc0  mov     rcx, rdi; this
0x180015cc3  call    ?OnRestart@Command@MkvMfSource@MkvMfSourceLib@@QEAAJXZ; MkvMfSourceLib::MkvMfSource::Command::OnRestart(void)
0x180015cc8  jmp     short loc_180015CE6
0x180015cca  test    r14b, r14b
0x180015ccd  jnz     short loc_180015CE8
0x180015ccf  mov     rcx, rdi; this
0x180015cd2  call    ?OnSeek@Command@MkvMfSource@MkvMfSourceLib@@QEBAJXZ; MkvMfSourceLib::MkvMfSource::Command::OnSeek(void)
0x180015cd7  jmp     short loc_180015CE6
0x180015cd9  test    r14b, r14b
0x180015cdc  jnz     short loc_180015CE8
0x180015cde  mov     rcx, rdi; this
0x180015ce1  call    ?OnStart@Command@MkvMfSource@MkvMfSourceLib@@QEAAJXZ; MkvMfSourceLib::MkvMfSource::Command::OnStart(void)
0x180015ce6  mov     esi, eax
0x180015ce8  mov     dil, 1
0x180015ceb  test    r14b, r14b
0x180015cee  jz      short loc_180015CF9
0x180015cf0  test    dil, dil
0x180015cf3  jnz     loc_180015D7D
0x180015cf9  mov     rax, [rbp+298h]
0x180015d00  mov     rdx, [rax]
0x180015d03  mov     rcx, [rdx]
0x180015d06  dec     qword ptr [rbp+2A0h]
0x180015d0d  mov     rax, [rdx+8]
0x180015d11  mov     [rax], rcx
0x180015d14  mov     rax, [rdx+8]
0x180015d18  mov     [rcx+8], rax
0x180015d1c  call    ??$_Freenode@V?$allocator@U?$_List_node@VCommand@MkvMfSource@MkvMfSourceLib@@PEAX@std@@@std@@@?$_List_node@VCommand@MkvMfSource@MkvMfSourceLib@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VCommand@MkvMfSource@MkvMfSourceLib@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *>::_Freenode<std::allocator<std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *>>>(std::allocator<std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *>> &,std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *> *)
0x180015d21  test    esi, esi
0x180015d23  jns     loc_180015C3E
0x180015d29  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015d30  test    rcx, rcx
0x180015d33  jnz     loc_180015E21
0x180015d39  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180015d40  nop     dword ptr [rax+rax+00h]
0x180015d45  mov     rcx, rax
0x180015d48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180015d4f  test    rax, rax
0x180015d52  jz      loc_180015E13
0x180015d58  mov     rax, [rax]
0x180015d5b  mov     edx, 7F0h
0x180015d60  mov     rax, [rax+8]
0x180015d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d69  test    eax, eax
0x180015d6b  jz      loc_180015E13
0x180015d71  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015d78  jmp     loc_180015E21
0x180015d7d  test    esi, esi
0x180015d7f  jns     loc_180015E78
0x180015d85  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015d8c  test    rcx, rcx
0x180015d8f  jnz     short loc_180015DD8
0x180015d91  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180015d98  nop     dword ptr [rax+rax+00h]
0x180015d9d  mov     rcx, rax
0x180015da0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180015da7  test    rax, rax
0x180015daa  jz      short loc_180015DCA
0x180015dac  mov     rax, [rax]
0x180015daf  mov     edx, 7F0h
0x180015db4  mov     rax, [rax+8]
0x180015db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dbd  test    eax, eax
0x180015dbf  jz      short loc_180015DCA
0x180015dc1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015dc8  jmp     short loc_180015DD8
0x180015dca  lea     rcx, qword_1800DBF70; this
0x180015dd1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180015dd8  cmp     byte ptr [rcx+8], 0
0x180015ddc  jz      short loc_180015E03
0x180015dde  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015de3  cmp     [rax+7CCh], esi
0x180015de9  jz      short loc_180015E03
0x180015deb  mov     r9d, esi; int
0x180015dee  mov     r8d, 788h; int
0x180015df4  lea     rdx, aMkvmfsourcelib_20; "MkvMfSourceLib::MkvMfSource::OnCommand"
0x180015dfb  mov     rcx, rax; this
0x180015dfe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180015e03  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015e0a  jb      short loc_180015E78
0x180015e0c  mov     edx, 0B6h
0x180015e11  jmp     short loc_180015E5A
0x180015e13  lea     rcx, qword_1800DBF70; this
0x180015e1a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180015e21  cmp     byte ptr [rcx+8], 0
0x180015e25  jz      short loc_180015E4C
0x180015e27  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015e2c  cmp     [rax+7CCh], esi
0x180015e32  jz      short loc_180015E4C
0x180015e34  mov     r9d, esi; int
0x180015e37  mov     r8d, 78Fh; int
0x180015e3d  lea     rdx, aMkvmfsourcelib_20; "MkvMfSourceLib::MkvMfSource::OnCommand"
0x180015e44  mov     rcx, rax; this
0x180015e47  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180015e4c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015e53  jb      short loc_180015E78
0x180015e55  mov     edx, 0B7h
0x180015e5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e61  mov     [rsp+88h+var_68], esi
0x180015e65  mov     r9, rbp
0x180015e68  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180015e6f  mov     rcx, [rcx+10h]
0x180015e73  call    WPP_SF_qD
0x180015e78  test    r15, r15
0x180015e7b  jz      short loc_180015E80
0x180015e7d  mov     [r15], dil
0x180015e80  lea     rcx, [rsp+88h+var_58]; this
0x180015e85  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180015e8a  mov     eax, esi
0x180015e8c  mov     rcx, [rsp+88h+var_38]
0x180015e91  xor     rcx, rsp; StackCookie
0x180015e94  call    __security_check_cookie
0x180015e99  mov     rbx, [rsp+88h+arg_8]
0x180015ea1  add     rsp, 60h
0x180015ea5  pop     r15
0x180015ea7  pop     r14
0x180015ea9  pop     rdi
0x180015eaa  pop     rsi
0x180015eab  pop     rbp
0x180015eac  retn
```
