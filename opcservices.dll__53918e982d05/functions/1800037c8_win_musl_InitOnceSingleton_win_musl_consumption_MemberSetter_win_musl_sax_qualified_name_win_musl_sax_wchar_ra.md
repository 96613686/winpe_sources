# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationships>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationships>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationships>)

- ea: `0x1800037c8`
- end: `0x180003992`
- name: `??$Get@V?$SingletonInitializer@VRelationships@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VRelationships@Model@win_musl@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VRelationships@Model@win_musl@@@341@@Z`
- size: `458`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180003998`
- `0x1800b4978`

## callees

- `0x1800037c8`
- `0x18002db70`
- `0x18006554c`
- `0x180099234`
- `0x1800adbd8`
- `0x1800cd6fc`
- `0x1800cd9dc`
- `0x1800e64f0`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180003819`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180003819`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800038f7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800038f7`

## string_xrefs

- `0x180003950`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationships>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationships>>()
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationships>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationships>>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationships>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationships>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationships>>::store'::`2'::s_storage,
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
0x1800037c8  mov     rax, rsp
0x1800037cb  push    rbp
0x1800037cc  lea     rbp, [rax-28h]
0x1800037d0  sub     rsp, 120h
0x1800037d7  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1800037e0  mov     [rax+8], rdi
0x1800037e4  mov     rax, cs:__security_cookie
0x1800037eb  xor     rax, rsp
0x1800037ee  mov     [rbp+20h+var_10], rax
0x1800037f2  mov     [rsp+120h+fPending], 0
0x1800037fa  mov     [rsp+120h+Context], 0
0x180003803  lea     r9, [rsp+120h+Context]; lpContext
0x180003808  lea     r8, [rsp+120h+fPending]; fPending
0x18000380d  xor     edx, edx; dwFlags
0x18000380f  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VRelationships@Model@win_musl@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationships>>::store(void)'::`2'::s_storage
0x180003816  mov     rcx, rdi; lpInitOnce
0x180003819  call    cs:__imp_InitOnceBeginInitialize
0x18000381f  test    eax, eax
0x180003821  jnz     short loc_18000386A
0x180003823  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180003828  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x18000382f  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180003834  mov     [rsp+120h+var_F8], eax; unsigned int
0x180003838  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x180003840  lea     r9, word_180139126
0x180003847  lea     r8, aNoFilename; "(no filename)"
0x18000384e  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180003853  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180003858  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18000385f  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180003864  call    _CxxThrowException_0
0x18000386a  cmp     [rsp+120h+fPending], 0
0x18000386f  jz      loc_180003928
0x180003875  mov     [rsp+120h+var_C8], rdi
0x18000387a  mov     dword ptr [rsp+120h+var_C0], 0
0x180003882  lea     rdx, [rsp+120h+var_D0]
0x180003887  call    ??R?$SingletonInitializer@VRelationships@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationships>::operator()(void)
0x18000388c  nop
0x18000388d  mov     rax, [rsp+120h+var_D0]
0x180003892  mov     [rsp+120h+Context], rax
0x180003897  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VRelationships@Model@win_musl@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x18000389e  call    atexit
0x1800038a3  test    eax, eax
0x1800038a5  jz      short loc_1800038ED
0x1800038a7  lea     rax, aAtexitFailed; "atexit() failed"
0x1800038ae  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x1800038b3  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x1800038bb  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x1800038c3  lea     r9, word_180139126
0x1800038ca  lea     r8, aNoFilename; "(no filename)"
0x1800038d1  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800038d6  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800038db  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800038e2  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800038e7  call    _CxxThrowException_0
0x1800038ed  mov     r8, [rsp+120h+Context]; lpContext
0x1800038f2  xor     edx, edx; dwFlags
0x1800038f4  mov     rcx, rdi; lpInitOnce
0x1800038f7  call    cs:__imp_InitOnceComplete
0x1800038fd  test    eax, eax
0x1800038ff  jz      short loc_18000394A
0x180003901  mov     [rsp+120h+var_D0], 0
0x18000390a  mov     [rsp+120h+var_C8], 0
0x180003913  lea     rcx, [rsp+120h+var_D0]
0x180003918  call    ??1?$auto_ptr@UMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(void)
0x18000391d  nop
0x18000391e  lea     rcx, [rsp+120h+var_C8]; this
0x180003923  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x180003928  mov     rax, [rsp+120h+Context]
0x18000392d  mov     rcx, [rbp+20h+var_10]
0x180003931  xor     rcx, rsp; StackCookie
0x180003934  call    __security_check_cookie
0x180003939  mov     rdi, [rsp+120h+arg_0]
0x180003941  add     rsp, 120h
0x180003948  pop     rbp
0x180003949  retn
0x18000394a  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18000394f  nop
0x180003950  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x180003957  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x18000395c  mov     [rsp+120h+var_F8], eax; unsigned int
0x180003960  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x180003968  lea     r9, word_180139126
0x18000396f  lea     r8, aNoFilename; "(no filename)"
0x180003976  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18000397b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180003980  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180003987  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18000398c  call    _CxxThrowException_0
```
