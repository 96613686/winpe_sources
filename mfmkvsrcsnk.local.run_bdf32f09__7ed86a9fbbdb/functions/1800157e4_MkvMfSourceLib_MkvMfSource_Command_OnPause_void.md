# MkvMfSourceLib::MkvMfSource::Command::OnPause(void)

- ea: `0x1800157e4`
- end: `0x180015aca`
- name: `?OnPause@Command@MkvMfSource@MkvMfSourceLib@@QEBAJXZ`
- size: `742`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource::Command *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180015154`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x1800098b8`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x18000db40`
- `0x180010fd0`
- `0x1800157e4`
- `0x180020d84`
- `0x180023d18`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001590b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800159fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001590b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800159fc`

## string_xrefs

- `0x180015805`: `MkvMfSourceLib::MkvMfSource::Command::OnPause`
- `0x180015968`: `MkvMfSourceLib::MkvMfSource::Command::OnPause`
- `0x180015a59`: `MkvMfSourceLib::MkvMfSource::Command::OnPause`

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
            v11 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v17 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x1800157e4  push    rbx
0x1800157e6  push    rbp
0x1800157e7  push    rsi
0x1800157e8  push    rdi
0x1800157e9  sub     rsp, 68h
0x1800157ed  mov     rax, cs:__security_cookie
0x1800157f4  xor     rax, rsp
0x1800157f7  mov     [rsp+88h+var_38], rax
0x1800157fc  mov     rbp, rcx
0x1800157ff  mov     r8d, 0E1Eh; int
0x180015805  lea     rdx, aMkvmfsourcelib_92; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x18001580c  lea     rcx, [rsp+88h+var_58]; this
0x180015811  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180015816  nop
0x180015817  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001581e  cmp     byte ptr [rcx+8], 0
0x180015822  jz      short loc_180015871
0x180015824  cmp     qword ptr [rbp+10h], 0
0x180015829  jz      short loc_180015871
0x18001582b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015830  mov     rdi, rax
0x180015833  mov     rcx, [rbp+10h]
0x180015837  mov     rdx, [rcx]
0x18001583a  mov     rax, [rdx+128h]
0x180015841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015846  mov     ebx, eax
0x180015848  mov     rcx, [rbp+10h]
0x18001584c  mov     rdx, [rcx]
0x18001584f  mov     rax, [rdx+118h]
0x180015856  lea     rdx, [rsp+88h+var_48]
0x18001585b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015860  movups  xmm0, xmmword ptr [rax]
0x180015863  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18001586b  mov     [rdi+7E0h], ebx
0x180015871  mov     rdi, [rbp+8]
0x180015875  mov     rdi, [rdi+240h]
0x18001587c  mov     rbx, [rdi]
0x18001587f  mov     [rsp+88h+var_50], rbx
0x180015884  cmp     rbx, rdi
0x180015887  jz      loc_1800159BE
0x18001588d  lea     rcx, [rsp+88h+var_50]
0x180015892  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(void)
0x180015897  mov     rbx, [rbx+28h]
0x18001589b  mov     [rsp+88h+var_48], rbx
0x1800158a0  lea     rcx, [rsp+88h+var_48]
0x1800158a5  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x1800158aa  nop
0x1800158ab  mov     rax, [rbx]
0x1800158ae  mov     rcx, rbx
0x1800158b1  mov     rax, [rax+78h]
0x1800158b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158ba  test    al, al
0x1800158bc  jz      short loc_1800158DA
0x1800158be  test    rbx, rbx
0x1800158c1  jz      short loc_1800158D3
0x1800158c3  mov     rax, [rbx]
0x1800158c6  mov     rcx, rbx
0x1800158c9  mov     rax, [rax+10h]
0x1800158cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158d2  nop
0x1800158d3  mov     rbx, [rsp+88h+var_50]
0x1800158d8  jmp     short loc_180015884
0x1800158da  mov     rcx, rbx; this
0x1800158dd  call    ?Pause@MkvMfStream@MkvMfSourceLib@@QEAAJXZ; MkvMfSourceLib::MkvMfStream::Pause(void)
0x1800158e2  mov     esi, eax
0x1800158e4  test    eax, eax
0x1800158e6  js      short loc_1800158FF
0x1800158e8  test    rbx, rbx
0x1800158eb  jz      short loc_1800158FD
0x1800158ed  mov     rax, [rbx]
0x1800158f0  mov     rcx, rbx
0x1800158f3  mov     rax, [rax+10h]
0x1800158f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158fc  nop
0x1800158fd  jmp     short loc_1800158D3
0x1800158ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015906  test    rcx, rcx
0x180015909  jnz     short loc_18001594C
0x18001590b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180015911  mov     rcx, rax
0x180015914  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001591b  test    rax, rax
0x18001591e  jz      short loc_18001593E
0x180015920  mov     rax, [rax]
0x180015923  mov     edx, 7F0h
0x180015928  mov     rax, [rax+8]
0x18001592c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015931  test    eax, eax
0x180015933  jz      short loc_18001593E
0x180015935  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001593c  jmp     short loc_18001594C
0x18001593e  lea     rcx, qword_1800D6F70; this
0x180015945  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001594c  cmp     byte ptr [rcx+8], 0
0x180015950  jz      short loc_180015977
0x180015952  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015957  cmp     [rax+7CCh], esi
0x18001595d  jz      short loc_180015977
0x18001595f  mov     r9d, esi; int
0x180015962  mov     r8d, 0E34h; int
0x180015968  lea     rdx, aMkvmfsourcelib_92; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x18001596f  mov     rcx, rax; this
0x180015972  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180015977  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001597e  jb      short loc_1800159A4
0x180015980  mov     edx, 0E8h
0x180015985  mov     dword ptr [rsp+88h+var_68], esi
0x180015989  mov     r9, rbp
0x18001598c  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180015993  mov     rcx, cs:WPP_GLOBAL_Control
0x18001599a  mov     rcx, [rcx+10h]
0x18001599e  call    WPP_SF_qD
0x1800159a3  nop
0x1800159a4  test    rbx, rbx
0x1800159a7  jz      short loc_1800159B9
0x1800159a9  mov     rax, [rbx]
0x1800159ac  mov     rcx, rbx
0x1800159af  mov     rax, [rax+10h]
0x1800159b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159b8  nop
0x1800159b9  jmp     loc_180015A94
0x1800159be  mov     rcx, [rbp+8]
0x1800159c2  mov     rax, [rcx]
0x1800159c5  lea     rdx, [rbp+20h]
0x1800159c9  mov     [rsp+88h+var_68], rdx
0x1800159ce  xor     r9d, r9d
0x1800159d1  lea     r8, _GUID_00000000_0000_0000_0000_000000000000
0x1800159d8  mov     edx, 0D1h
0x1800159dd  mov     rax, [rax+30h]
0x1800159e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159e6  mov     esi, eax
0x1800159e8  test    eax, eax
0x1800159ea  jns     loc_180015AA8
0x1800159f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800159f7  test    rcx, rcx
0x1800159fa  jnz     short loc_180015A3D
0x1800159fc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180015a02  mov     rcx, rax
0x180015a05  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180015a0c  test    rax, rax
0x180015a0f  jz      short loc_180015A2F
0x180015a11  mov     rax, [rax]
0x180015a14  mov     edx, 7F0h
0x180015a19  mov     rax, [rax+8]
0x180015a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a22  test    eax, eax
0x180015a24  jz      short loc_180015A2F
0x180015a26  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015a2d  jmp     short loc_180015A3D
0x180015a2f  lea     rcx, qword_1800D6F70; this
0x180015a36  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180015a3d  cmp     byte ptr [rcx+8], 0
0x180015a41  jz      short loc_180015A68
0x180015a43  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015a48  cmp     [rax+7CCh], esi
0x180015a4e  jz      short loc_180015A68
0x180015a50  mov     r9d, esi; int
0x180015a53  mov     r8d, 0E37h; int
0x180015a59  lea     rdx, aMkvmfsourcelib_92; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180015a60  mov     rcx, rax; this
0x180015a63  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180015a68  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015a6f  jb      short loc_180015A94
0x180015a71  mov     edx, 0E9h
0x180015a76  mov     dword ptr [rsp+88h+var_68], esi
0x180015a7a  mov     r9, rbp
0x180015a7d  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180015a84  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a8b  mov     rcx, [rcx+10h]
0x180015a8f  call    WPP_SF_qD
0x180015a94  mov     r8d, esi; int
0x180015a97  lea     rdx, aErrorPausingSo; "Error pausing source."
0x180015a9e  mov     rcx, [rbp+8]; this
0x180015aa2  call    ?Error@MkvMfSource@MkvMfSourceLib@@AEAAJPEBGJ@Z; MkvMfSourceLib::MkvMfSource::Error(ushort const *,long)
0x180015aa7  nop
0x180015aa8  lea     rcx, [rsp+88h+var_58]; this
0x180015aad  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180015ab2  mov     eax, esi
0x180015ab4  mov     rcx, [rsp+88h+var_38]
0x180015ab9  xor     rcx, rsp; StackCookie
0x180015abc  call    __security_check_cookie
0x180015ac1  add     rsp, 68h
0x180015ac5  pop     rdi
0x180015ac6  pop     rsi
0x180015ac7  pop     rbp
0x180015ac8  pop     rbx
0x180015ac9  retn
```
