# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureTime>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureTime>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureTime>)

- ea: `0x180107694`
- end: `0x18010785e`
- name: `??$Get@V?$SingletonInitializer@VSignatureTime@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VSignatureTime@Model@win_dox@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VSignatureTime@Model@win_dox@@@341@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180108cf0`

## callees

- `0x18002db70`
- `0x18006554c`
- `0x180099234`
- `0x1800adbd8`
- `0x1800cd6fc`
- `0x1800cd9dc`
- `0x180107694`
- `0x180108834`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1801076e5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1801076e5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1801077c3`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1801077c3`

## string_xrefs

- `0x18010781c`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureTime>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureTime>>()
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureTime>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureTime>>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureTime>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureTime>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureTime>>::store'::`2'::s_storage,
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
0x180107694  mov     rax, rsp
0x180107697  push    rbp
0x180107698  lea     rbp, [rax-28h]
0x18010769c  sub     rsp, 120h
0x1801076a3  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1801076ac  mov     [rax+8], rdi
0x1801076b0  mov     rax, cs:__security_cookie
0x1801076b7  xor     rax, rsp
0x1801076ba  mov     [rbp+20h+var_10], rax
0x1801076be  mov     [rsp+120h+fPending], 0
0x1801076c6  mov     [rsp+120h+Context], 0
0x1801076cf  lea     r9, [rsp+120h+Context]; lpContext
0x1801076d4  lea     r8, [rsp+120h+fPending]; fPending
0x1801076d9  xor     edx, edx; dwFlags
0x1801076db  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VSignatureTime@Model@win_dox@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureTime>>::store(void)'::`2'::s_storage
0x1801076e2  mov     rcx, rdi; lpInitOnce
0x1801076e5  call    cs:__imp_InitOnceBeginInitialize
0x1801076eb  test    eax, eax
0x1801076ed  jnz     short loc_180107736
0x1801076ef  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1801076f4  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x1801076fb  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180107700  mov     [rsp+120h+var_F8], eax; unsigned int
0x180107704  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x18010770c  lea     r9, word_180139126
0x180107713  lea     r8, aNoFilename; "(no filename)"
0x18010771a  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18010771f  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180107724  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18010772b  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180107730  call    _CxxThrowException_0
0x180107736  cmp     [rsp+120h+fPending], 0
0x18010773b  jz      loc_1801077F4
0x180107741  mov     [rsp+120h+var_C8], rdi
0x180107746  mov     dword ptr [rsp+120h+var_C0], 0
0x18010774e  lea     rdx, [rsp+120h+var_D0]
0x180107753  call    ??R?$SingletonInitializer@VSignatureTime@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureTime>::operator()(void)
0x180107758  nop
0x180107759  mov     rax, [rsp+120h+var_D0]
0x18010775e  mov     [rsp+120h+Context], rax
0x180107763  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VSignatureTime@Model@win_dox@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x18010776a  call    atexit
0x18010776f  test    eax, eax
0x180107771  jz      short loc_1801077B9
0x180107773  lea     rax, aAtexitFailed; "atexit() failed"
0x18010777a  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x18010777f  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x180107787  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x18010778f  lea     r9, word_180139126
0x180107796  lea     r8, aNoFilename; "(no filename)"
0x18010779d  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1801077a2  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1801077a7  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1801077ae  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1801077b3  call    _CxxThrowException_0
0x1801077b9  mov     r8, [rsp+120h+Context]; lpContext
0x1801077be  xor     edx, edx; dwFlags
0x1801077c0  mov     rcx, rdi; lpInitOnce
0x1801077c3  call    cs:__imp_InitOnceComplete
0x1801077c9  test    eax, eax
0x1801077cb  jz      short loc_180107816
0x1801077cd  mov     [rsp+120h+var_D0], 0
0x1801077d6  mov     [rsp+120h+var_C8], 0
0x1801077df  lea     rcx, [rsp+120h+var_D0]
0x1801077e4  call    ??1?$auto_ptr@UMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(void)
0x1801077e9  nop
0x1801077ea  lea     rcx, [rsp+120h+var_C8]; this
0x1801077ef  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x1801077f4  mov     rax, [rsp+120h+Context]
0x1801077f9  mov     rcx, [rbp+20h+var_10]
0x1801077fd  xor     rcx, rsp; StackCookie
0x180107800  call    __security_check_cookie
0x180107805  mov     rdi, [rsp+120h+arg_0]
0x18010780d  add     rsp, 120h
0x180107814  pop     rbp
0x180107815  retn
0x180107816  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18010781b  nop
0x18010781c  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x180107823  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180107828  mov     [rsp+120h+var_F8], eax; unsigned int
0x18010782c  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x180107834  lea     r9, word_180139126
0x18010783b  lea     r8, aNoFilename; "(no filename)"
0x180107842  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180107847  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18010784c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180107853  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180107858  call    _CxxThrowException_0
```
