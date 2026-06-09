# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationship>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationship>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationship>)

- ea: `0x18000284c`
- end: `0x180002a16`
- name: `??$Get@V?$SingletonInitializer@VRelationship@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VRelationship@Model@win_musl@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VRelationship@Model@win_musl@@@341@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800018b0`

## callees

- `0x18000284c`
- `0x18002db70`
- `0x18006554c`
- `0x180099234`
- `0x1800adbd8`
- `0x1800cd6fc`
- `0x1800cd9dc`
- `0x1800e643c`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000289d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000289d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000297b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000297b`

## string_xrefs

- `0x1800029d4`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationship>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationship>>()
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationship>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationship>>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationship>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationship>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationship>>::store'::`2'::s_storage,
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
0x18000284c  mov     rax, rsp
0x18000284f  push    rbp
0x180002850  lea     rbp, [rax-28h]
0x180002854  sub     rsp, 120h
0x18000285b  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180002864  mov     [rax+8], rdi
0x180002868  mov     rax, cs:__security_cookie
0x18000286f  xor     rax, rsp
0x180002872  mov     [rbp+20h+var_10], rax
0x180002876  mov     [rsp+120h+fPending], 0
0x18000287e  mov     [rsp+120h+Context], 0
0x180002887  lea     r9, [rsp+120h+Context]; lpContext
0x18000288c  lea     r8, [rsp+120h+fPending]; fPending
0x180002891  xor     edx, edx; dwFlags
0x180002893  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VRelationship@Model@win_musl@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationship>>::store(void)'::`2'::s_storage
0x18000289a  mov     rcx, rdi; lpInitOnce
0x18000289d  call    cs:__imp_InitOnceBeginInitialize
0x1800028a3  test    eax, eax
0x1800028a5  jnz     short loc_1800028EE
0x1800028a7  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800028ac  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x1800028b3  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x1800028b8  mov     [rsp+120h+var_F8], eax; unsigned int
0x1800028bc  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x1800028c4  lea     r9, word_180139126
0x1800028cb  lea     r8, aNoFilename; "(no filename)"
0x1800028d2  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800028d7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800028dc  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800028e3  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800028e8  call    _CxxThrowException_0
0x1800028ee  cmp     [rsp+120h+fPending], 0
0x1800028f3  jz      loc_1800029AC
0x1800028f9  mov     [rsp+120h+var_C8], rdi
0x1800028fe  mov     dword ptr [rsp+120h+var_C0], 0
0x180002906  lea     rdx, [rsp+120h+var_D0]
0x18000290b  call    ??R?$SingletonInitializer@VRelationship@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationship>::operator()(void)
0x180002910  nop
0x180002911  mov     rax, [rsp+120h+var_D0]
0x180002916  mov     [rsp+120h+Context], rax
0x18000291b  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VRelationship@Model@win_musl@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x180002922  call    atexit
0x180002927  test    eax, eax
0x180002929  jz      short loc_180002971
0x18000292b  lea     rax, aAtexitFailed; "atexit() failed"
0x180002932  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x180002937  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x18000293f  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x180002947  lea     r9, word_180139126
0x18000294e  lea     r8, aNoFilename; "(no filename)"
0x180002955  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18000295a  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18000295f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180002966  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18000296b  call    _CxxThrowException_0
0x180002971  mov     r8, [rsp+120h+Context]; lpContext
0x180002976  xor     edx, edx; dwFlags
0x180002978  mov     rcx, rdi; lpInitOnce
0x18000297b  call    cs:__imp_InitOnceComplete
0x180002981  test    eax, eax
0x180002983  jz      short loc_1800029CE
0x180002985  mov     [rsp+120h+var_D0], 0
0x18000298e  mov     [rsp+120h+var_C8], 0
0x180002997  lea     rcx, [rsp+120h+var_D0]
0x18000299c  call    ??1?$auto_ptr@UMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(void)
0x1800029a1  nop
0x1800029a2  lea     rcx, [rsp+120h+var_C8]; this
0x1800029a7  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x1800029ac  mov     rax, [rsp+120h+Context]
0x1800029b1  mov     rcx, [rbp+20h+var_10]
0x1800029b5  xor     rcx, rsp; StackCookie
0x1800029b8  call    __security_check_cookie
0x1800029bd  mov     rdi, [rsp+120h+arg_0]
0x1800029c5  add     rsp, 120h
0x1800029cc  pop     rbp
0x1800029cd  retn
0x1800029ce  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800029d3  nop
0x1800029d4  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x1800029db  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x1800029e0  mov     [rsp+120h+var_F8], eax; unsigned int
0x1800029e4  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x1800029ec  lea     r9, word_180139126
0x1800029f3  lea     r8, aNoFilename; "(no filename)"
0x1800029fa  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800029ff  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180002a04  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180002a0b  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180002a10  call    _CxxThrowException_0
```
