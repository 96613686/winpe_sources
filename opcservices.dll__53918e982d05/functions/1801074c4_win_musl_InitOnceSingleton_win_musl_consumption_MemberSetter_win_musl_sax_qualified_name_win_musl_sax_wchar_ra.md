# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperty>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperty>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperty>)

- ea: `0x1801074c4`
- end: `0x18010768e`
- name: `??$Get@V?$SingletonInitializer@VSignatureProperty@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VSignatureProperty@Model@win_dox@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VSignatureProperty@Model@win_dox@@@341@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180108c10`

## callees

- `0x18002db70`
- `0x18006554c`
- `0x180099234`
- `0x1800adbd8`
- `0x1800cd6fc`
- `0x1800cd9dc`
- `0x1801074c4`
- `0x180108780`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180107515`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180107515`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1801075f3`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1801075f3`

## string_xrefs

- `0x18010764c`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperty>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperty>>()
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperty>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperty>>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperty>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperty>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperty>>::store'::`2'::s_storage,
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
0x1801074c4  mov     rax, rsp
0x1801074c7  push    rbp
0x1801074c8  lea     rbp, [rax-28h]
0x1801074cc  sub     rsp, 120h
0x1801074d3  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1801074dc  mov     [rax+8], rdi
0x1801074e0  mov     rax, cs:__security_cookie
0x1801074e7  xor     rax, rsp
0x1801074ea  mov     [rbp+20h+var_10], rax
0x1801074ee  mov     [rsp+120h+fPending], 0
0x1801074f6  mov     [rsp+120h+Context], 0
0x1801074ff  lea     r9, [rsp+120h+Context]; lpContext
0x180107504  lea     r8, [rsp+120h+fPending]; fPending
0x180107509  xor     edx, edx; dwFlags
0x18010750b  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VSignatureProperty@Model@win_dox@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperty>>::store(void)'::`2'::s_storage
0x180107512  mov     rcx, rdi; lpInitOnce
0x180107515  call    cs:__imp_InitOnceBeginInitialize
0x18010751b  test    eax, eax
0x18010751d  jnz     short loc_180107566
0x18010751f  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180107524  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x18010752b  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180107530  mov     [rsp+120h+var_F8], eax; unsigned int
0x180107534  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x18010753c  lea     r9, word_180139126
0x180107543  lea     r8, aNoFilename; "(no filename)"
0x18010754a  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18010754f  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180107554  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18010755b  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180107560  call    _CxxThrowException_0
0x180107566  cmp     [rsp+120h+fPending], 0
0x18010756b  jz      loc_180107624
0x180107571  mov     [rsp+120h+var_C8], rdi
0x180107576  mov     dword ptr [rsp+120h+var_C0], 0
0x18010757e  lea     rdx, [rsp+120h+var_D0]
0x180107583  call    ??R?$SingletonInitializer@VSignatureProperty@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperty>::operator()(void)
0x180107588  nop
0x180107589  mov     rax, [rsp+120h+var_D0]
0x18010758e  mov     [rsp+120h+Context], rax
0x180107593  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VSignatureProperty@Model@win_dox@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x18010759a  call    atexit
0x18010759f  test    eax, eax
0x1801075a1  jz      short loc_1801075E9
0x1801075a3  lea     rax, aAtexitFailed; "atexit() failed"
0x1801075aa  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x1801075af  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x1801075b7  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x1801075bf  lea     r9, word_180139126
0x1801075c6  lea     r8, aNoFilename; "(no filename)"
0x1801075cd  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1801075d2  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1801075d7  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1801075de  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1801075e3  call    _CxxThrowException_0
0x1801075e9  mov     r8, [rsp+120h+Context]; lpContext
0x1801075ee  xor     edx, edx; dwFlags
0x1801075f0  mov     rcx, rdi; lpInitOnce
0x1801075f3  call    cs:__imp_InitOnceComplete
0x1801075f9  test    eax, eax
0x1801075fb  jz      short loc_180107646
0x1801075fd  mov     [rsp+120h+var_D0], 0
0x180107606  mov     [rsp+120h+var_C8], 0
0x18010760f  lea     rcx, [rsp+120h+var_D0]
0x180107614  call    ??1?$auto_ptr@UMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(void)
0x180107619  nop
0x18010761a  lea     rcx, [rsp+120h+var_C8]; this
0x18010761f  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x180107624  mov     rax, [rsp+120h+Context]
0x180107629  mov     rcx, [rbp+20h+var_10]
0x18010762d  xor     rcx, rsp; StackCookie
0x180107630  call    __security_check_cookie
0x180107635  mov     rdi, [rsp+120h+arg_0]
0x18010763d  add     rsp, 120h
0x180107644  pop     rbp
0x180107645  retn
0x180107646  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18010764b  nop
0x18010764c  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x180107653  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180107658  mov     [rsp+120h+var_F8], eax; unsigned int
0x18010765c  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x180107664  lea     r9, word_180139126
0x18010766b  lea     r8, aNoFilename; "(no filename)"
0x180107672  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180107677  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18010767c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180107683  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180107688  call    _CxxThrowException_0
```
