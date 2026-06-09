# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::ObjectBlob>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::ObjectBlob>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::ObjectBlob>)

- ea: `0x180107124`
- end: `0x1801072ee`
- name: `??$Get@V?$SingletonInitializer@VObjectBlob@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VObjectBlob@Model@win_dox@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VObjectBlob@Model@win_dox@@@341@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180108ed4`

## callees

- `0x18002db70`
- `0x18006554c`
- `0x180099234`
- `0x1800adbd8`
- `0x1800cd6fc`
- `0x1800cd9dc`
- `0x180107124`
- `0x1801085b4`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180107175`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180107175`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180107253`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180107253`

## string_xrefs

- `0x1801072ac`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::ObjectBlob>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::ObjectBlob>>()
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::ObjectBlob>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::ObjectBlob>>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::ObjectBlob>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::ObjectBlob>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::ObjectBlob>>::store'::`2'::s_storage,
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
0x180107124  mov     rax, rsp
0x180107127  push    rbp
0x180107128  lea     rbp, [rax-28h]
0x18010712c  sub     rsp, 120h
0x180107133  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x18010713c  mov     [rax+8], rdi
0x180107140  mov     rax, cs:__security_cookie
0x180107147  xor     rax, rsp
0x18010714a  mov     [rbp+20h+var_10], rax
0x18010714e  mov     [rsp+120h+fPending], 0
0x180107156  mov     [rsp+120h+Context], 0
0x18010715f  lea     r9, [rsp+120h+Context]; lpContext
0x180107164  lea     r8, [rsp+120h+fPending]; fPending
0x180107169  xor     edx, edx; dwFlags
0x18010716b  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VObjectBlob@Model@win_dox@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::ObjectBlob>>::store(void)'::`2'::s_storage
0x180107172  mov     rcx, rdi; lpInitOnce
0x180107175  call    cs:__imp_InitOnceBeginInitialize
0x18010717b  test    eax, eax
0x18010717d  jnz     short loc_1801071C6
0x18010717f  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180107184  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x18010718b  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180107190  mov     [rsp+120h+var_F8], eax; unsigned int
0x180107194  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x18010719c  lea     r9, word_180139126
0x1801071a3  lea     r8, aNoFilename; "(no filename)"
0x1801071aa  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1801071af  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1801071b4  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1801071bb  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1801071c0  call    _CxxThrowException_0
0x1801071c6  cmp     [rsp+120h+fPending], 0
0x1801071cb  jz      loc_180107284
0x1801071d1  mov     [rsp+120h+var_C8], rdi
0x1801071d6  mov     dword ptr [rsp+120h+var_C0], 0
0x1801071de  lea     rdx, [rsp+120h+var_D0]
0x1801071e3  call    ??R?$SingletonInitializer@VObjectBlob@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::ObjectBlob>::operator()(void)
0x1801071e8  nop
0x1801071e9  mov     rax, [rsp+120h+var_D0]
0x1801071ee  mov     [rsp+120h+Context], rax
0x1801071f3  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VObjectBlob@Model@win_dox@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x1801071fa  call    atexit
0x1801071ff  test    eax, eax
0x180107201  jz      short loc_180107249
0x180107203  lea     rax, aAtexitFailed; "atexit() failed"
0x18010720a  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x18010720f  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x180107217  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x18010721f  lea     r9, word_180139126
0x180107226  lea     r8, aNoFilename; "(no filename)"
0x18010722d  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180107232  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180107237  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18010723e  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180107243  call    _CxxThrowException_0
0x180107249  mov     r8, [rsp+120h+Context]; lpContext
0x18010724e  xor     edx, edx; dwFlags
0x180107250  mov     rcx, rdi; lpInitOnce
0x180107253  call    cs:__imp_InitOnceComplete
0x180107259  test    eax, eax
0x18010725b  jz      short loc_1801072A6
0x18010725d  mov     [rsp+120h+var_D0], 0
0x180107266  mov     [rsp+120h+var_C8], 0
0x18010726f  lea     rcx, [rsp+120h+var_D0]
0x180107274  call    ??1?$auto_ptr@UMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(void)
0x180107279  nop
0x18010727a  lea     rcx, [rsp+120h+var_C8]; this
0x18010727f  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x180107284  mov     rax, [rsp+120h+Context]
0x180107289  mov     rcx, [rbp+20h+var_10]
0x18010728d  xor     rcx, rsp; StackCookie
0x180107290  call    __security_check_cookie
0x180107295  mov     rdi, [rsp+120h+arg_0]
0x18010729d  add     rsp, 120h
0x1801072a4  pop     rbp
0x1801072a5  retn
0x1801072a6  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1801072ab  nop
0x1801072ac  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x1801072b3  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x1801072b8  mov     [rsp+120h+var_F8], eax; unsigned int
0x1801072bc  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x1801072c4  lea     r9, word_180139126
0x1801072cb  lea     r8, aNoFilename; "(no filename)"
0x1801072d2  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1801072d7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1801072dc  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1801072e3  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1801072e8  call    _CxxThrowException_0
```
