# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::ContentTypes>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::ContentTypes>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::ContentTypes>)

- ea: `0x180099390`
- end: `0x18009955a`
- name: `??$Get@V?$SingletonInitializer@VContentTypes@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VContentTypes@Model@win_musl@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VContentTypes@Model@win_musl@@@341@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180006ae8`

## callees

- `0x18002db70`
- `0x18006554c`
- `0x18007c150`
- `0x180099234`
- `0x180099390`
- `0x1800adbd8`
- `0x1800cd6fc`
- `0x1800cd9dc`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800993e1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800993e1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800994bf`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800994bf`

## string_xrefs

- `0x180099518`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::ContentTypes>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::ContentTypes>>()
{
  win_musl::detail *v0; // rcx
  win_musl::detail *v1; // rcx
  unsigned int LastErrorAsFailHR; // [rsp+30h] [rbp-D8h]
  unsigned int v4; // [rsp+30h] [rbp-D8h]
  BOOL fPending[2]; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID Context; // [rsp+50h] [rbp-B8h] BYREF
  void *v7; // [rsp+58h] [rbp-B0h] BYREF
  union _RTL_RUN_ONCE *v8; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v9; // [rsp+68h] [rbp-A0h]
  __int64 v10; // [rsp+70h] [rbp-98h]
  _BYTE pExceptionObject[160]; // [rsp+78h] [rbp-90h] BYREF

  v10 = -2;
  fPending[0] = 0;
  Context = 0;
  if ( !InitOnceBeginInitialize(
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::ContentTypes>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::ContentTypes>>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::ContentTypes>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::ContentTypes>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::ContentTypes>>::store'::`2'::s_storage,
            0,
            Context) )
    {
      v4 = win_musl::detail::GetLastErrorAsFailHR(v1);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1F5u,
        v4,
        (struct win_musl::TStringEllipseBase *)L"InitOnceComplete() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v7 = 0;
    v8 = 0;
    std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(&v7);
    win_musl::InitOnceGuard::~InitOnceGuard((win_musl::InitOnceGuard *)&v8);
  }
  return Context;
}

```

## disassembly

```asm
0x180099390  mov     rax, rsp
0x180099393  push    rbp
0x180099394  lea     rbp, [rax-28h]
0x180099398  sub     rsp, 120h
0x18009939f  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1800993a8  mov     [rax+8], rdi
0x1800993ac  mov     rax, cs:__security_cookie
0x1800993b3  xor     rax, rsp
0x1800993b6  mov     [rbp+20h+var_10], rax
0x1800993ba  mov     [rsp+120h+fPending], 0
0x1800993c2  mov     [rsp+120h+Context], 0
0x1800993cb  lea     r9, [rsp+120h+Context]; lpContext
0x1800993d0  lea     r8, [rsp+120h+fPending]; fPending
0x1800993d5  xor     edx, edx; dwFlags
0x1800993d7  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VContentTypes@Model@win_musl@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::ContentTypes>>::store(void)'::`2'::s_storage
0x1800993de  mov     rcx, rdi; lpInitOnce
0x1800993e1  call    cs:__imp_InitOnceBeginInitialize
0x1800993e7  test    eax, eax
0x1800993e9  jnz     short loc_180099432
0x1800993eb  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800993f0  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x1800993f7  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x1800993fc  mov     [rsp+120h+var_F8], eax; unsigned int
0x180099400  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x180099408  lea     r9, word_180139126
0x18009940f  lea     r8, aNoFilename; "(no filename)"
0x180099416  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18009941b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180099420  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180099427  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18009942c  call    _CxxThrowException_0
0x180099432  cmp     [rsp+120h+fPending], 0
0x180099437  jz      loc_1800994F0
0x18009943d  mov     [rsp+120h+var_C8], rdi
0x180099442  mov     dword ptr [rsp+120h+var_C0], 0
0x18009944a  lea     rdx, [rsp+120h+var_D0]
0x18009944f  call    ??R?$SingletonInitializer@VContentTypes@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::ContentTypes>::operator()(void)
0x180099454  nop
0x180099455  mov     rax, [rsp+120h+var_D0]
0x18009945a  mov     [rsp+120h+Context], rax
0x18009945f  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VContentTypes@Model@win_musl@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x180099466  call    atexit
0x18009946b  test    eax, eax
0x18009946d  jz      short loc_1800994B5
0x18009946f  lea     rax, aAtexitFailed; "atexit() failed"
0x180099476  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x18009947b  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x180099483  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x18009948b  lea     r9, word_180139126
0x180099492  lea     r8, aNoFilename; "(no filename)"
0x180099499  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18009949e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800994a3  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800994aa  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800994af  call    _CxxThrowException_0
0x1800994b5  mov     r8, [rsp+120h+Context]; lpContext
0x1800994ba  xor     edx, edx; dwFlags
0x1800994bc  mov     rcx, rdi; lpInitOnce
0x1800994bf  call    cs:__imp_InitOnceComplete
0x1800994c5  test    eax, eax
0x1800994c7  jz      short loc_180099512
0x1800994c9  mov     [rsp+120h+var_D0], 0
0x1800994d2  mov     [rsp+120h+var_C8], 0
0x1800994db  lea     rcx, [rsp+120h+var_D0]
0x1800994e0  call    ??1?$auto_ptr@UMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(void)
0x1800994e5  nop
0x1800994e6  lea     rcx, [rsp+120h+var_C8]; this
0x1800994eb  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x1800994f0  mov     rax, [rsp+120h+Context]
0x1800994f5  mov     rcx, [rbp+20h+var_10]
0x1800994f9  xor     rcx, rsp; StackCookie
0x1800994fc  call    __security_check_cookie
0x180099501  mov     rdi, [rsp+120h+arg_0]
0x180099509  add     rsp, 120h
0x180099510  pop     rbp
0x180099511  retn
0x180099512  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180099517  nop
0x180099518  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x18009951f  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180099524  mov     [rsp+120h+var_F8], eax; unsigned int
0x180099528  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x180099530  lea     r9, word_180139126
0x180099537  lea     r8, aNoFilename; "(no filename)"
0x18009953e  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180099543  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180099548  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009954f  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180099554  call    _CxxThrowException_0
```
