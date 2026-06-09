# MkvMfSourceLib::MkvMfSource::Command::OnStop(void)

- ea: `0x180018f04`
- end: `0x1800192b1`
- name: `?OnStop@Command@MkvMfSource@MkvMfSourceLib@@QEBAJXZ`
- size: `941`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource::Command *__hidden this)`
- caller_count: `1`
- callee_count: `14`
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
- `0x180018f04`
- `0x18001be98`
- `0x180020d84`
- `0x1800268f0`
- `0x180044d58`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001902c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001911d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800191e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001902c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001911d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800191e2`

## string_xrefs

- `0x180018f26`: `MkvMfSourceLib::MkvMfSource::Command::OnStop`
- `0x180019089`: `MkvMfSourceLib::MkvMfSource::Command::OnStop`
- `0x18001917a`: `MkvMfSourceLib::MkvMfSource::Command::OnStop`
- `0x18001923f`: `MkvMfSourceLib::MkvMfSource::Command::OnStop`

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
            v11 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v17 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v24 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180018f04  push    rbx
0x180018f06  push    rsi
0x180018f07  push    rdi
0x180018f08  push    r14
0x180018f0a  sub     rsp, 68h
0x180018f0e  mov     rax, cs:__security_cookie
0x180018f15  xor     rax, rsp
0x180018f18  mov     [rsp+88h+var_38], rax
0x180018f1d  mov     rsi, rcx
0x180018f20  mov     r8d, 0E44h; int
0x180018f26  lea     rdx, aMkvmfsourcelib_106; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180018f2d  lea     rcx, [rsp+88h+var_58]; this
0x180018f32  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180018f37  nop
0x180018f38  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180018f3f  cmp     byte ptr [rcx+8], 0
0x180018f43  jz      short loc_180018F92
0x180018f45  cmp     qword ptr [rsi+10h], 0
0x180018f4a  jz      short loc_180018F92
0x180018f4c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018f51  mov     rdi, rax
0x180018f54  mov     rcx, [rsi+10h]
0x180018f58  mov     rdx, [rcx]
0x180018f5b  mov     rax, [rdx+128h]
0x180018f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f67  mov     ebx, eax
0x180018f69  mov     rcx, [rsi+10h]
0x180018f6d  mov     rdx, [rcx]
0x180018f70  mov     rax, [rdx+118h]
0x180018f77  lea     rdx, [rsp+88h+var_48]
0x180018f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f81  movups  xmm0, xmmword ptr [rax]
0x180018f84  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180018f8c  mov     [rdi+7E0h], ebx
0x180018f92  mov     rax, [rsi+8]
0x180018f96  mov     r14, [rax+240h]
0x180018f9d  mov     rbx, [r14]
0x180018fa0  mov     [rsp+88h+var_50], rbx
0x180018fa5  cmp     rbx, r14
0x180018fa8  jz      loc_1800190DF
0x180018fae  lea     rcx, [rsp+88h+var_50]
0x180018fb3  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(void)
0x180018fb8  mov     rbx, [rbx+28h]
0x180018fbc  mov     [rsp+88h+var_48], rbx
0x180018fc1  lea     rcx, [rsp+88h+var_48]
0x180018fc6  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x180018fcb  nop
0x180018fcc  mov     rax, [rbx]
0x180018fcf  mov     rcx, rbx
0x180018fd2  mov     rax, [rax+78h]
0x180018fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fdb  test    al, al
0x180018fdd  jz      short loc_180018FFB
0x180018fdf  test    rbx, rbx
0x180018fe2  jz      short loc_180018FF4
0x180018fe4  mov     rax, [rbx]
0x180018fe7  mov     rcx, rbx
0x180018fea  mov     rax, [rax+10h]
0x180018fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ff3  nop
0x180018ff4  mov     rbx, [rsp+88h+var_50]
0x180018ff9  jmp     short loc_180018FA5
0x180018ffb  mov     rcx, rbx; this
0x180018ffe  call    ?Stop@MkvMfStream@MkvMfSourceLib@@QEAAJXZ; MkvMfSourceLib::MkvMfStream::Stop(void)
0x180019003  mov     edi, eax
0x180019005  test    eax, eax
0x180019007  js      short loc_180019020
0x180019009  test    rbx, rbx
0x18001900c  jz      short loc_18001901E
0x18001900e  mov     rax, [rbx]
0x180019011  mov     rcx, rbx
0x180019014  mov     rax, [rax+10h]
0x180019018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001901d  nop
0x18001901e  jmp     short loc_180018FF4
0x180019020  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019027  test    rcx, rcx
0x18001902a  jnz     short loc_18001906D
0x18001902c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019032  mov     rcx, rax
0x180019035  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001903c  test    rax, rax
0x18001903f  jz      short loc_18001905F
0x180019041  mov     rax, [rax]
0x180019044  mov     edx, 7F0h
0x180019049  mov     rax, [rax+8]
0x18001904d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019052  test    eax, eax
0x180019054  jz      short loc_18001905F
0x180019056  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001905d  jmp     short loc_18001906D
0x18001905f  lea     rcx, qword_1800D6F70; this
0x180019066  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001906d  cmp     byte ptr [rcx+8], 0
0x180019071  jz      short loc_180019098
0x180019073  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019078  cmp     [rax+7CCh], edi
0x18001907e  jz      short loc_180019098
0x180019080  mov     r9d, edi; int
0x180019083  mov     r8d, 0E5Ah; int
0x180019089  lea     rdx, aMkvmfsourcelib_106; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180019090  mov     rcx, rax; this
0x180019093  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019098  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001909f  jb      short loc_1800190C5
0x1800190a1  mov     edx, 0EAh
0x1800190a6  mov     dword ptr [rsp+88h+var_68], edi
0x1800190aa  mov     r9, rsi
0x1800190ad  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x1800190b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800190bb  mov     rcx, [rcx+10h]
0x1800190bf  call    WPP_SF_qD
0x1800190c4  nop
0x1800190c5  test    rbx, rbx
0x1800190c8  jz      short loc_1800190DA
0x1800190ca  mov     rax, [rbx]
0x1800190cd  mov     rcx, rbx
0x1800190d0  mov     rax, [rax+10h]
0x1800190d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190d9  nop
0x1800190da  jmp     loc_18001927A
0x1800190df  mov     rcx, [rsi+8]
0x1800190e3  mov     rax, [rcx]
0x1800190e6  lea     rdx, [rsi+20h]
0x1800190ea  mov     [rsp+88h+var_68], rdx
0x1800190ef  xor     r9d, r9d
0x1800190f2  lea     r8, _GUID_00000000_0000_0000_0000_000000000000
0x1800190f9  mov     edx, 0CFh
0x1800190fe  mov     rax, [rax+30h]
0x180019102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019107  mov     edi, eax
0x180019109  test    eax, eax
0x18001910b  jns     loc_1800191A0
0x180019111  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019118  test    rcx, rcx
0x18001911b  jnz     short loc_18001915E
0x18001911d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019123  mov     rcx, rax
0x180019126  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001912d  test    rax, rax
0x180019130  jz      short loc_180019150
0x180019132  mov     rax, [rax]
0x180019135  mov     edx, 7F0h
0x18001913a  mov     rax, [rax+8]
0x18001913e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019143  test    eax, eax
0x180019145  jz      short loc_180019150
0x180019147  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001914e  jmp     short loc_18001915E
0x180019150  lea     rcx, qword_1800D6F70; this
0x180019157  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001915e  cmp     byte ptr [rcx+8], 0
0x180019162  jz      short loc_180019189
0x180019164  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019169  cmp     [rax+7CCh], edi
0x18001916f  jz      short loc_180019189
0x180019171  mov     r9d, edi; int
0x180019174  mov     r8d, 0E5Dh; int
0x18001917a  lea     rdx, aMkvmfsourcelib_106; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180019181  mov     rcx, rax; this
0x180019184  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019189  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019190  jb      loc_18001927A
0x180019196  mov     edx, 0EBh
0x18001919b  jmp     loc_18001925C
0x1800191a0  mov     rax, [rsi+8]
0x1800191a4  mov     qword ptr [rax+188h], 0
0x1800191af  mov     rcx, [rsi+8]
0x1800191b3  add     rcx, 0B8h; this
0x1800191ba  xor     edx, edx; __int64
0x1800191bc  call    ?Seek@MkvReader@@QEAAJ_J@Z; MkvReader::Seek(__int64)
0x1800191c1  xor     edx, edx; bool
0x1800191c3  mov     rcx, [rsi+8]; this
0x1800191c7  call    ?SetEOP@MkvMfSource@MkvMfSourceLib@@AEAAJ_N@Z; MkvMfSourceLib::MkvMfSource::SetEOP(bool)
0x1800191cc  mov     edi, eax
0x1800191ce  test    eax, eax
0x1800191d0  jns     loc_18001928E
0x1800191d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800191dd  test    rcx, rcx
0x1800191e0  jnz     short loc_180019223
0x1800191e2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800191e8  mov     rcx, rax
0x1800191eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800191f2  test    rax, rax
0x1800191f5  jz      short loc_180019215
0x1800191f7  mov     rax, [rax]
0x1800191fa  mov     edx, 7F0h
0x1800191ff  mov     rax, [rax+8]
0x180019203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019208  test    eax, eax
0x18001920a  jz      short loc_180019215
0x18001920c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019213  jmp     short loc_180019223
0x180019215  lea     rcx, qword_1800D6F70; this
0x18001921c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019223  cmp     byte ptr [rcx+8], 0
0x180019227  jz      short loc_18001924E
0x180019229  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001922e  cmp     [rax+7CCh], edi
0x180019234  jz      short loc_18001924E
0x180019236  mov     r9d, edi; int
0x180019239  mov     r8d, 0E61h; int
0x18001923f  lea     rdx, aMkvmfsourcelib_106; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180019246  mov     rcx, rax; this
0x180019249  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001924e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019255  jb      short loc_18001927A
0x180019257  mov     edx, 0ECh
0x18001925c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019263  mov     dword ptr [rsp+88h+var_68], edi
0x180019267  mov     r9, rsi
0x18001926a  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180019271  mov     rcx, [rcx+10h]
0x180019275  call    WPP_SF_qD
0x18001927a  mov     r8d, edi; int
0x18001927d  lea     rdx, aErrorStoppingS; "Error stopping source."
0x180019284  mov     rcx, [rsi+8]; this
0x180019288  call    ?Error@MkvMfSource@MkvMfSourceLib@@AEAAJPEBGJ@Z; MkvMfSourceLib::MkvMfSource::Error(ushort const *,long)
0x18001928d  nop
0x18001928e  lea     rcx, [rsp+88h+var_58]; this
0x180019293  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180019298  mov     eax, edi
0x18001929a  mov     rcx, [rsp+88h+var_38]
0x18001929f  xor     rcx, rsp; StackCookie
0x1800192a2  call    __security_check_cookie
0x1800192a7  add     rsp, 68h
0x1800192ab  pop     r14
0x1800192ad  pop     rdi
0x1800192ae  pop     rsi
0x1800192af  pop     rbx
0x1800192b0  retn
```
