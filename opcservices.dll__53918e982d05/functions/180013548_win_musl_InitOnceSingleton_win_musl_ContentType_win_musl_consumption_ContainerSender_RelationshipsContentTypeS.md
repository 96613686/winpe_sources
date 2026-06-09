# win_musl::InitOnceSingleton<win_musl::ContentType,win_musl::consumption::ContainerSender::RelationshipsContentTypeSingleton_tag>::Get<win_musl::consumption::ContainerSender::SingletonInitializer>(win_musl::consumption::ContainerSender::SingletonInitializer)

- ea: `0x180013548`
- end: `0x1800136ec`
- name: `??$Get@VSingletonInitializer@ContainerSender@consumption@win_musl@@@?$InitOnceSingleton@UContentType@win_musl@@URelationshipsContentTypeSingleton_tag@ContainerSender@consumption@2@@win_musl@@SAPEAUContentType@1@VSingletonInitializer@ContainerSender@consumption@1@@Z`
- size: `420`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800127c0`
- `0x1800444f0`

## callees

- `0x180013548`
- `0x18002db70`
- `0x18006554c`
- `0x180093fa8`
- `0x1800cd6fc`
- `0x1800cd9dc`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180013599`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180013599`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180013608`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180013608`

## string_xrefs

- `0x1800136aa`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::ContentType,win_musl::consumption::ContainerSender::RelationshipsContentTypeSingleton_tag>::Get<win_musl::consumption::ContainerSender::SingletonInitializer>()
{
  win_musl::detail *v0; // rcx
  win_musl::detail *v2; // rcx
  unsigned int v3; // eax
  unsigned int LastErrorAsFailHR; // [rsp+30h] [rbp-D8h]
  BOOL fPending[2]; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID Context; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v7[3]; // [rsp+58h] [rbp-B0h] BYREF
  int v8; // [rsp+70h] [rbp-98h]
  _BYTE pExceptionObject[160]; // [rsp+78h] [rbp-90h] BYREF

  v7[1] = -2;
  fPending[0] = 0;
  Context = 0;
  if ( !InitOnceBeginInitialize(
          &`win_musl::InitOnceSingleton<win_musl::ContentType,win_musl::consumption::ContainerSender::RelationshipsContentTypeSingleton_tag>::store'::`2'::s_storage,
          0,
          fPending,
          &Context) )
  {
    LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v0);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x1DCu,
      LastErrorAsFailHR,
      (struct win_musl::TStringEllipseBase *)L"InitOnceBeginInitialize() failed");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( fPending[0] )
  {
    v7[2] = &`win_musl::InitOnceSingleton<win_musl::ContentType,win_musl::consumption::ContainerSender::RelationshipsContentTypeSingleton_tag>::store'::`2'::s_storage;
    v8 = 0;
    win_musl::consumption::ContainerSender::SingletonInitializer::operator()(v0, v7);
    Context = (LPVOID)v7[0];
    if ( atexit(win_musl::InitOnceSingleton<win_musl::ContentType,win_musl::consumption::ContainerSender::RelationshipsContentTypeSingleton_tag>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::ContentType,win_musl::consumption::ContainerSender::RelationshipsContentTypeSingleton_tag>::store'::`2'::s_storage,
            0,
            Context) )
    {
      v3 = win_musl::detail::GetLastErrorAsFailHR(v2);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1F5u,
        v3,
        (struct win_musl::TStringEllipseBase *)L"InitOnceComplete() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  return Context;
}

```

## disassembly

```asm
0x180013548  mov     rax, rsp
0x18001354b  push    rbp
0x18001354c  lea     rbp, [rax-28h]
0x180013550  sub     rsp, 120h
0x180013557  mov     [rsp+120h+var_C8], 0FFFFFFFFFFFFFFFEh
0x180013560  mov     [rax+8], rdi
0x180013564  mov     rax, cs:__security_cookie
0x18001356b  xor     rax, rsp
0x18001356e  mov     [rbp+20h+var_10], rax
0x180013572  mov     [rsp+120h+fPending], 0
0x18001357a  mov     [rsp+120h+Context], 0
0x180013583  lea     r9, [rsp+120h+Context]; lpContext
0x180013588  lea     r8, [rsp+120h+fPending]; fPending
0x18001358d  xor     edx, edx; dwFlags
0x18001358f  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@UContentType@win_musl@@URelationshipsContentTypeSingleton_tag@ContainerSender@consumption@2@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::ContentType,win_musl::consumption::ContainerSender::RelationshipsContentTypeSingleton_tag>::store(void)'::`2'::s_storage
0x180013596  mov     rcx, rdi; lpInitOnce
0x180013599  call    cs:__imp_InitOnceBeginInitialize
0x18001359f  test    eax, eax
0x1800135a1  jz      short loc_180013618
0x1800135a3  cmp     [rsp+120h+fPending], 0
0x1800135a8  jnz     short loc_1800135CC
0x1800135aa  mov     rax, [rsp+120h+Context]
0x1800135af  mov     rcx, [rbp+20h+var_10]
0x1800135b3  xor     rcx, rsp; StackCookie
0x1800135b6  call    __security_check_cookie
0x1800135bb  mov     rdi, [rsp+120h+arg_0]
0x1800135c3  add     rsp, 120h
0x1800135ca  pop     rbp
0x1800135cb  retn
0x1800135cc  mov     qword ptr [rsp+120h+var_C0], rdi
0x1800135d1  mov     [rsp+120h+var_B8], 0
0x1800135d9  lea     rdx, [rsp+120h+var_D0]
0x1800135de  call    ??RSingletonInitializer@ContainerSender@consumption@win_musl@@QEBA?AV?$auto_ptr@UContentType@win_musl@@@std@@XZ; win_musl::consumption::ContainerSender::SingletonInitializer::operator()(void)
0x1800135e3  nop
0x1800135e4  mov     rax, [rsp+120h+var_D0]
0x1800135e9  mov     [rsp+120h+Context], rax
0x1800135ee  lea     rcx, ?Cleanup@?$InitOnceSingleton@UContentType@win_musl@@URelationshipsContentTypeSingleton_tag@ContainerSender@consumption@2@@win_musl@@CAXXZ; void (__cdecl *)()
0x1800135f5  call    atexit
0x1800135fa  test    eax, eax
0x1800135fc  jnz     short loc_18001365F
0x1800135fe  mov     r8, [rsp+120h+Context]; lpContext
0x180013603  xor     edx, edx; dwFlags
0x180013605  mov     rcx, rdi; lpInitOnce
0x180013608  call    cs:__imp_InitOnceComplete
0x18001360e  test    eax, eax
0x180013610  jz      loc_1800136A5
0x180013616  jmp     short loc_1800135AA
0x180013618  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18001361d  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x180013624  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180013629  mov     [rsp+120h+var_F8], eax; unsigned int
0x18001362d  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x180013635  lea     r9, word_180139126
0x18001363c  lea     r8, aNoFilename; "(no filename)"
0x180013643  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180013648  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18001364d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180013654  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180013659  call    _CxxThrowException_0
0x18001365f  lea     rax, aAtexitFailed; "atexit() failed"
0x180013666  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x18001366b  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x180013673  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x18001367b  lea     r9, word_180139126
0x180013682  lea     r8, aNoFilename; "(no filename)"
0x180013689  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18001368e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180013693  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18001369a  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18001369f  call    _CxxThrowException_0
0x1800136a5  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800136aa  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x1800136b1  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x1800136b6  mov     [rsp+120h+var_F8], eax; unsigned int
0x1800136ba  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x1800136c2  lea     r9, word_180139126
0x1800136c9  lea     r8, aNoFilename; "(no filename)"
0x1800136d0  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800136d5  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800136da  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800136e1  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800136e6  call    _CxxThrowException_0
```
