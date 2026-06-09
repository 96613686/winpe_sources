# MkvMfSourceLib::MkvMfSource::Command::OnStop(void)

- ea: `0x180019a74`
- end: `0x180019e34`
- name: `?OnStop@Command@MkvMfSource@MkvMfSourceLib@@QEBAJXZ`
- size: `960`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource::Command *__hidden this)`
- caller_count: `1`
- callee_count: `14`
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
- `0x180019a74`
- `0x18001cb78`
- `0x180021b9c`
- `0x18002791c`
- `0x180046bc4`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019b9c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019c93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019d5e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019b9c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019c93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019d5e`

## string_xrefs

- `0x180019a96`: `MkvMfSourceLib::MkvMfSource::Command::OnStop`
- `0x180019bff`: `MkvMfSourceLib::MkvMfSource::Command::OnStop`
- `0x180019cf6`: `MkvMfSourceLib::MkvMfSource::Command::OnStop`
- `0x180019dc1`: `MkvMfSourceLib::MkvMfSource::Command::OnStop`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MkvMfSourceLib::MkvMfSource::Command::OnStop(MkvMfSourceLib::MkvMfSource::Command *this)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v3; // ebx
  __int64 *v4; // r14
  __int64 v5; // rbx
  MkvMfSourceLib::MkvMfStream *v6; // rbx
  __int64 v7; // rdx
  int v8; // edi
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
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  _BYTE v28[8]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v29; // [rsp+38h] [rbp-50h] BYREF
  _QWORD v30[2]; // [rsp+40h] [rbp-48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v28,
    "MkvMfSourceLib::MkvMfSource::Command::OnStop",
    3652);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 2) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 296LL))(*((_QWORD *)this + 2));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 2) + 280LL))(
                                                            *((_QWORD *)this + 2),
                                                            v30);
    *((_DWORD *)ThreadRelativeContext + 504) = v3;
  }
  v4 = *(__int64 **)(*((_QWORD *)this + 1) + 576LL);
  v5 = *v4;
  v29 = *v4;
  while ( (__int64 *)v5 != v4 )
  {
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(&v29);
    v6 = *(MkvMfSourceLib::MkvMfStream **)(v5 + 40);
    v30[0] = v6;
    Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(v30);
    if ( (*(unsigned __int8 (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v6 + 120LL))(v6) )
    {
      if ( v6 )
        (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    else
    {
      v8 = MkvMfSourceLib::MkvMfStream::Stop(v6);
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
            CallStackContext::TraceFailure(v13, "MkvMfSourceLib::MkvMfSource::Command::OnStop", 3674, v8);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            234,
            &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
            this,
            v8);
        if ( v6 )
          (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v6 + 16LL))(v6);
        goto LABEL_50;
      }
      if ( v6 )
        (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    v5 = v29;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, _QWORD, char *))(**((_QWORD **)this + 1) + 48LL))(
         *((_QWORD *)this + 1),
         207,
         &GUID_00000000_0000_0000_0000_000000000000,
         0,
         (char *)this + 32);
  if ( v8 < 0 )
  {
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
        CallStackContext::TraceFailure(v19, "MkvMfSourceLib::MkvMfSource::Command::OnStop", 3677, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_50;
    v20 = 235;
LABEL_49:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v8);
    goto LABEL_50;
  }
  *(_QWORD *)(*((_QWORD *)this + 1) + 392LL) = 0;
  MkvReader::Seek((MkvReader *)(*((_QWORD *)this + 1) + 184LL), 0);
  v8 = MkvMfSourceLib::MkvMfSource::SetEOP(*((MkvMfSourceLib::MkvMfSource **)this + 1), 0);
  if ( v8 >= 0 )
    goto LABEL_51;
  v24 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
    CallStackTracing::s_wpInstance = v25;
    if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v24 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v24 + 8) )
  {
    v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
    if ( *((_DWORD *)v26 + 499) != v8 )
      CallStackContext::TraceFailure(v26, "MkvMfSourceLib::MkvMfSource::Command::OnStop", 3681, v8);
  }
  if ( g_wppLevels )
  {
    v20 = 236;
    goto LABEL_49;
  }
LABEL_50:
  MkvMfSourceLib::MkvMfSource::Error(*((MkvMfSourceLib::MkvMfSource **)this + 1), L"Error stopping source.", v8);
LABEL_51:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v28);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180019a74  push    rbx
0x180019a76  push    rsi
0x180019a77  push    rdi
0x180019a78  push    r14
0x180019a7a  sub     rsp, 68h
0x180019a7e  mov     rax, cs:__security_cookie
0x180019a85  xor     rax, rsp
0x180019a88  mov     [rsp+88h+var_38], rax
0x180019a8d  mov     rsi, rcx
0x180019a90  mov     r8d, 0E44h; int
0x180019a96  lea     rdx, aMkvmfsourcelib_106; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180019a9d  lea     rcx, [rsp+88h+var_58]; this
0x180019aa2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180019aa7  nop
0x180019aa8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180019aaf  cmp     byte ptr [rcx+8], 0
0x180019ab3  jz      short loc_180019B02
0x180019ab5  cmp     qword ptr [rsi+10h], 0
0x180019aba  jz      short loc_180019B02
0x180019abc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019ac1  mov     rdi, rax
0x180019ac4  mov     rcx, [rsi+10h]
0x180019ac8  mov     rdx, [rcx]
0x180019acb  mov     rax, [rdx+128h]
0x180019ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ad7  mov     ebx, eax
0x180019ad9  mov     rcx, [rsi+10h]
0x180019add  mov     rdx, [rcx]
0x180019ae0  mov     rax, [rdx+118h]
0x180019ae7  lea     rdx, [rsp+88h+var_48]
0x180019aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019af1  movups  xmm0, xmmword ptr [rax]
0x180019af4  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180019afc  mov     [rdi+7E0h], ebx
0x180019b02  mov     rax, [rsi+8]
0x180019b06  mov     r14, [rax+240h]
0x180019b0d  mov     rbx, [r14]
0x180019b10  mov     [rsp+88h+var_50], rbx
0x180019b15  cmp     rbx, r14
0x180019b18  jz      loc_180019C55
0x180019b1e  lea     rcx, [rsp+88h+var_50]
0x180019b23  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(void)
0x180019b28  mov     rbx, [rbx+28h]
0x180019b2c  mov     [rsp+88h+var_48], rbx
0x180019b31  lea     rcx, [rsp+88h+var_48]
0x180019b36  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x180019b3b  nop
0x180019b3c  mov     rax, [rbx]
0x180019b3f  mov     rcx, rbx
0x180019b42  mov     rax, [rax+78h]
0x180019b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b4b  test    al, al
0x180019b4d  jz      short loc_180019B6B
0x180019b4f  test    rbx, rbx
0x180019b52  jz      short loc_180019B64
0x180019b54  mov     rax, [rbx]
0x180019b57  mov     rcx, rbx
0x180019b5a  mov     rax, [rax+10h]
0x180019b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b63  nop
0x180019b64  mov     rbx, [rsp+88h+var_50]
0x180019b69  jmp     short loc_180019B15
0x180019b6b  mov     rcx, rbx; this
0x180019b6e  call    ?Stop@MkvMfStream@MkvMfSourceLib@@QEAAJXZ; MkvMfSourceLib::MkvMfStream::Stop(void)
0x180019b73  mov     edi, eax
0x180019b75  test    eax, eax
0x180019b77  js      short loc_180019B90
0x180019b79  test    rbx, rbx
0x180019b7c  jz      short loc_180019B8E
0x180019b7e  mov     rax, [rbx]
0x180019b81  mov     rcx, rbx
0x180019b84  mov     rax, [rax+10h]
0x180019b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b8d  nop
0x180019b8e  jmp     short loc_180019B64
0x180019b90  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019b97  test    rcx, rcx
0x180019b9a  jnz     short loc_180019BE3
0x180019b9c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019ba3  nop     dword ptr [rax+rax+00h]
0x180019ba8  mov     rcx, rax
0x180019bab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019bb2  test    rax, rax
0x180019bb5  jz      short loc_180019BD5
0x180019bb7  mov     rax, [rax]
0x180019bba  mov     edx, 7F0h
0x180019bbf  mov     rax, [rax+8]
0x180019bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bc8  test    eax, eax
0x180019bca  jz      short loc_180019BD5
0x180019bcc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019bd3  jmp     short loc_180019BE3
0x180019bd5  lea     rcx, qword_1800DBF70; this
0x180019bdc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019be3  cmp     byte ptr [rcx+8], 0
0x180019be7  jz      short loc_180019C0E
0x180019be9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019bee  cmp     [rax+7CCh], edi
0x180019bf4  jz      short loc_180019C0E
0x180019bf6  mov     r9d, edi; int
0x180019bf9  mov     r8d, 0E5Ah; int
0x180019bff  lea     rdx, aMkvmfsourcelib_106; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180019c06  mov     rcx, rax; this
0x180019c09  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019c0e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019c15  jb      short loc_180019C3B
0x180019c17  mov     edx, 0EAh
0x180019c1c  mov     dword ptr [rsp+88h+var_68], edi
0x180019c20  mov     r9, rsi
0x180019c23  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180019c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c31  mov     rcx, [rcx+10h]
0x180019c35  call    WPP_SF_qD
0x180019c3a  nop
0x180019c3b  test    rbx, rbx
0x180019c3e  jz      short loc_180019C50
0x180019c40  mov     rax, [rbx]
0x180019c43  mov     rcx, rbx
0x180019c46  mov     rax, [rax+10h]
0x180019c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c4f  nop
0x180019c50  jmp     loc_180019DFC
0x180019c55  mov     rcx, [rsi+8]
0x180019c59  mov     rax, [rcx]
0x180019c5c  lea     rdx, [rsi+20h]
0x180019c60  mov     [rsp+88h+var_68], rdx
0x180019c65  xor     r9d, r9d
0x180019c68  lea     r8, _GUID_00000000_0000_0000_0000_000000000000
0x180019c6f  mov     edx, 0CFh
0x180019c74  mov     rax, [rax+30h]
0x180019c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c7d  mov     edi, eax
0x180019c7f  test    eax, eax
0x180019c81  jns     loc_180019D1C
0x180019c87  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019c8e  test    rcx, rcx
0x180019c91  jnz     short loc_180019CDA
0x180019c93  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019c9a  nop     dword ptr [rax+rax+00h]
0x180019c9f  mov     rcx, rax
0x180019ca2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019ca9  test    rax, rax
0x180019cac  jz      short loc_180019CCC
0x180019cae  mov     rax, [rax]
0x180019cb1  mov     edx, 7F0h
0x180019cb6  mov     rax, [rax+8]
0x180019cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cbf  test    eax, eax
0x180019cc1  jz      short loc_180019CCC
0x180019cc3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019cca  jmp     short loc_180019CDA
0x180019ccc  lea     rcx, qword_1800DBF70; this
0x180019cd3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019cda  cmp     byte ptr [rcx+8], 0
0x180019cde  jz      short loc_180019D05
0x180019ce0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019ce5  cmp     [rax+7CCh], edi
0x180019ceb  jz      short loc_180019D05
0x180019ced  mov     r9d, edi; int
0x180019cf0  mov     r8d, 0E5Dh; int
0x180019cf6  lea     rdx, aMkvmfsourcelib_106; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180019cfd  mov     rcx, rax; this
0x180019d00  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019d05  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019d0c  jb      loc_180019DFC
0x180019d12  mov     edx, 0EBh
0x180019d17  jmp     loc_180019DDE
0x180019d1c  mov     rax, [rsi+8]
0x180019d20  mov     qword ptr [rax+188h], 0
0x180019d2b  mov     rcx, [rsi+8]
0x180019d2f  add     rcx, 0B8h; this
0x180019d36  xor     edx, edx; __int64
0x180019d38  call    ?Seek@MkvReader@@QEAAJ_J@Z; MkvReader::Seek(__int64)
0x180019d3d  xor     edx, edx; bool
0x180019d3f  mov     rcx, [rsi+8]; this
0x180019d43  call    ?SetEOP@MkvMfSource@MkvMfSourceLib@@AEAAJ_N@Z; MkvMfSourceLib::MkvMfSource::SetEOP(bool)
0x180019d48  mov     edi, eax
0x180019d4a  test    eax, eax
0x180019d4c  jns     loc_180019E10
0x180019d52  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019d59  test    rcx, rcx
0x180019d5c  jnz     short loc_180019DA5
0x180019d5e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019d65  nop     dword ptr [rax+rax+00h]
0x180019d6a  mov     rcx, rax
0x180019d6d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019d74  test    rax, rax
0x180019d77  jz      short loc_180019D97
0x180019d79  mov     rax, [rax]
0x180019d7c  mov     edx, 7F0h
0x180019d81  mov     rax, [rax+8]
0x180019d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d8a  test    eax, eax
0x180019d8c  jz      short loc_180019D97
0x180019d8e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019d95  jmp     short loc_180019DA5
0x180019d97  lea     rcx, qword_1800DBF70; this
0x180019d9e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019da5  cmp     byte ptr [rcx+8], 0
0x180019da9  jz      short loc_180019DD0
0x180019dab  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019db0  cmp     [rax+7CCh], edi
0x180019db6  jz      short loc_180019DD0
0x180019db8  mov     r9d, edi; int
0x180019dbb  mov     r8d, 0E61h; int
0x180019dc1  lea     rdx, aMkvmfsourcelib_106; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180019dc8  mov     rcx, rax; this
0x180019dcb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019dd0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019dd7  jb      short loc_180019DFC
0x180019dd9  mov     edx, 0ECh
0x180019dde  mov     rcx, cs:WPP_GLOBAL_Control
0x180019de5  mov     dword ptr [rsp+88h+var_68], edi
0x180019de9  mov     r9, rsi
0x180019dec  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180019df3  mov     rcx, [rcx+10h]
0x180019df7  call    WPP_SF_qD
0x180019dfc  mov     r8d, edi; int
0x180019dff  lea     rdx, aErrorStoppingS; "Error stopping source."
0x180019e06  mov     rcx, [rsi+8]; this
0x180019e0a  call    ?Error@MkvMfSource@MkvMfSourceLib@@AEAAJPEBGJ@Z; MkvMfSourceLib::MkvMfSource::Error(ushort const *,long)
0x180019e0f  nop
0x180019e10  lea     rcx, [rsp+88h+var_58]; this
0x180019e15  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180019e1a  mov     eax, edi
0x180019e1c  mov     rcx, [rsp+88h+var_38]
0x180019e21  xor     rcx, rsp; StackCookie
0x180019e24  call    __security_check_cookie
0x180019e29  add     rsp, 68h
0x180019e2d  pop     r14
0x180019e2f  pop     rdi
0x180019e30  pop     rsi
0x180019e31  pop     rbx
0x180019e32  retn
```
