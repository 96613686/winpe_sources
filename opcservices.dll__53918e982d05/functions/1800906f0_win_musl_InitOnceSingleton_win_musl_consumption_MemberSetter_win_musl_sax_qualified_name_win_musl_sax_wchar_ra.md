# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::OverrideType>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::OverrideType>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::OverrideType>)

- ea: `0x1800906f0`
- end: `0x1800908ba`
- name: `??$Get@V?$SingletonInitializer@VOverrideType@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VOverrideType@Model@win_musl@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VOverrideType@Model@win_musl@@@341@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180046fb0`

## callees

- `0x18002db70`
- `0x18006554c`
- `0x1800906f0`
- `0x180099234`
- `0x1800adbd8`
- `0x1800cd6fc`
- `0x1800cd9dc`
- `0x1800e6318`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180090741`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180090741`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18009083d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18009083d`

## string_xrefs

- `0x180090878`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::OverrideType>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::OverrideType>>()
{
  win_musl::detail *v0; // rcx
  unsigned int LastErrorAsFailHR; // eax
  win_musl::detail *v3; // rcx
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::OverrideType>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::OverrideType>>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::OverrideType>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::OverrideType>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::OverrideType>>::store'::`2'::s_storage,
            0,
            Context) )
    {
      v4 = win_musl::detail::GetLastErrorAsFailHR(v3);
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
0x1800906f0  mov     rax, rsp
0x1800906f3  push    rbp
0x1800906f4  lea     rbp, [rax-28h]
0x1800906f8  sub     rsp, 120h
0x1800906ff  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180090708  mov     [rax+8], rdi
0x18009070c  mov     rax, cs:__security_cookie
0x180090713  xor     rax, rsp
0x180090716  mov     [rbp+20h+var_10], rax
0x18009071a  mov     [rsp+120h+fPending], 0
0x180090722  mov     [rsp+120h+Context], 0
0x18009072b  lea     r9, [rsp+120h+Context]; lpContext
0x180090730  lea     r8, [rsp+120h+fPending]; fPending
0x180090735  xor     edx, edx; dwFlags
0x180090737  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VOverrideType@Model@win_musl@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::OverrideType>>::store(void)'::`2'::s_storage
0x18009073e  mov     rcx, rdi; lpInitOnce
0x180090741  call    cs:__imp_InitOnceBeginInitialize
0x180090747  test    eax, eax
0x180090749  jz      short loc_180090774
0x18009074b  cmp     [rsp+120h+fPending], 0
0x180090750  jnz     short loc_1800907BB
0x180090752  mov     rax, [rsp+120h+Context]
0x180090757  mov     rcx, [rbp+20h+var_10]
0x18009075b  xor     rcx, rsp; StackCookie
0x18009075e  call    __security_check_cookie
0x180090763  mov     rdi, [rsp+120h+arg_0]
0x18009076b  add     rsp, 120h
0x180090772  pop     rbp
0x180090773  retn
0x180090774  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180090779  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x180090780  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180090785  mov     [rsp+120h+var_F8], eax; unsigned int
0x180090789  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x180090791  lea     r9, word_180139126
0x180090798  lea     r8, aNoFilename; "(no filename)"
0x18009079f  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800907a4  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800907a9  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800907b0  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800907b5  call    _CxxThrowException_0
0x1800907bb  mov     [rsp+120h+var_C8], rdi
0x1800907c0  mov     dword ptr [rsp+120h+var_C0], 0
0x1800907c8  lea     rdx, [rsp+120h+var_D0]
0x1800907cd  call    ??R?$SingletonInitializer@VOverrideType@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::OverrideType>::operator()(void)
0x1800907d2  nop
0x1800907d3  mov     rax, [rsp+120h+var_D0]
0x1800907d8  mov     [rsp+120h+Context], rax
0x1800907dd  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VOverrideType@Model@win_musl@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x1800907e4  call    atexit
0x1800907e9  test    eax, eax
0x1800907eb  jz      short loc_180090833
0x1800907ed  lea     rax, aAtexitFailed; "atexit() failed"
0x1800907f4  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x1800907f9  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x180090801  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x180090809  lea     r9, word_180139126
0x180090810  lea     r8, aNoFilename; "(no filename)"
0x180090817  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18009081c  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180090821  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180090828  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18009082d  call    _CxxThrowException_0
0x180090833  mov     r8, [rsp+120h+Context]; lpContext
0x180090838  xor     edx, edx; dwFlags
0x18009083a  mov     rcx, rdi; lpInitOnce
0x18009083d  call    cs:__imp_InitOnceComplete
0x180090843  test    eax, eax
0x180090845  jz      short loc_180090873
0x180090847  mov     [rsp+120h+var_D0], 0
0x180090850  mov     [rsp+120h+var_C8], 0
0x180090859  lea     rcx, [rsp+120h+var_D0]
0x18009085e  call    ??1?$auto_ptr@UMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(void)
0x180090863  nop
0x180090864  lea     rcx, [rsp+120h+var_C8]; this
0x180090869  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x18009086e  jmp     loc_180090752
0x180090873  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180090878  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x18009087f  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180090884  mov     [rsp+120h+var_F8], eax; unsigned int
0x180090888  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x180090890  lea     r9, word_180139126
0x180090897  lea     r8, aNoFilename; "(no filename)"
0x18009089e  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800908a3  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800908a8  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800908af  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800908b4  call    _CxxThrowException_0
```
