# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::StringElement>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::StringElement>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::StringElement>)

- ea: `0x180107864`
- end: `0x180107a2e`
- name: `??$Get@V?$SingletonInitializer@VStringElement@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VStringElement@Model@win_dox@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VStringElement@Model@win_dox@@@341@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180108db0`

## callees

- `0x18002db70`
- `0x18006554c`
- `0x180099234`
- `0x1800adae4`
- `0x1800adbd8`
- `0x1800cd6fc`
- `0x1800cd9dc`
- `0x180107864`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1801078b5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1801078b5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180107993`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180107993`

## string_xrefs

- `0x1801079ec`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::StringElement>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::StringElement>>()
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::StringElement>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::StringElement>>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::StringElement>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::StringElement>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::StringElement>>::store'::`2'::s_storage,
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
0x180107864  mov     rax, rsp
0x180107867  push    rbp
0x180107868  lea     rbp, [rax-28h]
0x18010786c  sub     rsp, 120h
0x180107873  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x18010787c  mov     [rax+8], rdi
0x180107880  mov     rax, cs:__security_cookie
0x180107887  xor     rax, rsp
0x18010788a  mov     [rbp+20h+var_10], rax
0x18010788e  mov     [rsp+120h+fPending], 0
0x180107896  mov     [rsp+120h+Context], 0
0x18010789f  lea     r9, [rsp+120h+Context]; lpContext
0x1801078a4  lea     r8, [rsp+120h+fPending]; fPending
0x1801078a9  xor     edx, edx; dwFlags
0x1801078ab  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VStringElement@Model@win_dox@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::StringElement>>::store(void)'::`2'::s_storage
0x1801078b2  mov     rcx, rdi; lpInitOnce
0x1801078b5  call    cs:__imp_InitOnceBeginInitialize
0x1801078bb  test    eax, eax
0x1801078bd  jnz     short loc_180107906
0x1801078bf  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1801078c4  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x1801078cb  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x1801078d0  mov     [rsp+120h+var_F8], eax; unsigned int
0x1801078d4  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x1801078dc  lea     r9, word_180139126
0x1801078e3  lea     r8, aNoFilename; "(no filename)"
0x1801078ea  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1801078ef  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1801078f4  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1801078fb  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180107900  call    _CxxThrowException_0
0x180107906  cmp     [rsp+120h+fPending], 0
0x18010790b  jz      loc_1801079C4
0x180107911  mov     [rsp+120h+var_C8], rdi
0x180107916  mov     dword ptr [rsp+120h+var_C0], 0
0x18010791e  lea     rdx, [rsp+120h+var_D0]
0x180107923  call    ??R?$SingletonInitializer@VStringElement@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::StringElement>::operator()(void)
0x180107928  nop
0x180107929  mov     rax, [rsp+120h+var_D0]
0x18010792e  mov     [rsp+120h+Context], rax
0x180107933  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VStringElement@Model@win_dox@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x18010793a  call    atexit
0x18010793f  test    eax, eax
0x180107941  jz      short loc_180107989
0x180107943  lea     rax, aAtexitFailed; "atexit() failed"
0x18010794a  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x18010794f  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x180107957  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x18010795f  lea     r9, word_180139126
0x180107966  lea     r8, aNoFilename; "(no filename)"
0x18010796d  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180107972  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180107977  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18010797e  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180107983  call    _CxxThrowException_0
0x180107989  mov     r8, [rsp+120h+Context]; lpContext
0x18010798e  xor     edx, edx; dwFlags
0x180107990  mov     rcx, rdi; lpInitOnce
0x180107993  call    cs:__imp_InitOnceComplete
0x180107999  test    eax, eax
0x18010799b  jz      short loc_1801079E6
0x18010799d  mov     [rsp+120h+var_D0], 0
0x1801079a6  mov     [rsp+120h+var_C8], 0
0x1801079af  lea     rcx, [rsp+120h+var_D0]
0x1801079b4  call    ??1?$auto_ptr@UMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(void)
0x1801079b9  nop
0x1801079ba  lea     rcx, [rsp+120h+var_C8]; this
0x1801079bf  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x1801079c4  mov     rax, [rsp+120h+Context]
0x1801079c9  mov     rcx, [rbp+20h+var_10]
0x1801079cd  xor     rcx, rsp; StackCookie
0x1801079d0  call    __security_check_cookie
0x1801079d5  mov     rdi, [rsp+120h+arg_0]
0x1801079dd  add     rsp, 120h
0x1801079e4  pop     rbp
0x1801079e5  retn
0x1801079e6  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1801079eb  nop
0x1801079ec  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x1801079f3  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x1801079f8  mov     [rsp+120h+var_F8], eax; unsigned int
0x1801079fc  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x180107a04  lea     r9, word_180139126
0x180107a0b  lea     r8, aNoFilename; "(no filename)"
0x180107a12  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180107a17  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180107a1c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180107a23  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180107a28  call    _CxxThrowException_0
```
