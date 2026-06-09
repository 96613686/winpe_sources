# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperties>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperties>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperties>)

- ea: `0x1801072f4`
- end: `0x1801074be`
- name: `??$Get@V?$SingletonInitializer@VSignatureProperties@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VSignatureProperties@Model@win_dox@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VSignatureProperties@Model@win_dox@@@341@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180108b80`

## callees

- `0x18002db70`
- `0x18006554c`
- `0x180099234`
- `0x1800adbd8`
- `0x1800cd6fc`
- `0x1800cd9dc`
- `0x1801072f4`
- `0x1801086c0`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180107345`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180107345`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180107423`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180107423`

## string_xrefs

- `0x18010747c`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperties>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperties>>()
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperties>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperties>>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperties>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperties>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperties>>::store'::`2'::s_storage,
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
0x1801072f4  mov     rax, rsp
0x1801072f7  push    rbp
0x1801072f8  lea     rbp, [rax-28h]
0x1801072fc  sub     rsp, 120h
0x180107303  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x18010730c  mov     [rax+8], rdi
0x180107310  mov     rax, cs:__security_cookie
0x180107317  xor     rax, rsp
0x18010731a  mov     [rbp+20h+var_10], rax
0x18010731e  mov     [rsp+120h+fPending], 0
0x180107326  mov     [rsp+120h+Context], 0
0x18010732f  lea     r9, [rsp+120h+Context]; lpContext
0x180107334  lea     r8, [rsp+120h+fPending]; fPending
0x180107339  xor     edx, edx; dwFlags
0x18010733b  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VSignatureProperties@Model@win_dox@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::SignatureProperties>>::store(void)'::`2'::s_storage
0x180107342  mov     rcx, rdi; lpInitOnce
0x180107345  call    cs:__imp_InitOnceBeginInitialize
0x18010734b  test    eax, eax
0x18010734d  jnz     short loc_180107396
0x18010734f  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180107354  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x18010735b  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180107360  mov     [rsp+120h+var_F8], eax; unsigned int
0x180107364  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x18010736c  lea     r9, word_180139126
0x180107373  lea     r8, aNoFilename; "(no filename)"
0x18010737a  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18010737f  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180107384  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18010738b  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180107390  call    _CxxThrowException_0
0x180107396  cmp     [rsp+120h+fPending], 0
0x18010739b  jz      loc_180107454
0x1801073a1  mov     [rsp+120h+var_C8], rdi
0x1801073a6  mov     dword ptr [rsp+120h+var_C0], 0
0x1801073ae  lea     rdx, [rsp+120h+var_D0]
0x1801073b3  call    ??R?$SingletonInitializer@VSignatureProperties@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::SignatureProperties>::operator()(void)
0x1801073b8  nop
0x1801073b9  mov     rax, [rsp+120h+var_D0]
0x1801073be  mov     [rsp+120h+Context], rax
0x1801073c3  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VSignatureProperties@Model@win_dox@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x1801073ca  call    atexit
0x1801073cf  test    eax, eax
0x1801073d1  jz      short loc_180107419
0x1801073d3  lea     rax, aAtexitFailed; "atexit() failed"
0x1801073da  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x1801073df  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x1801073e7  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x1801073ef  lea     r9, word_180139126
0x1801073f6  lea     r8, aNoFilename; "(no filename)"
0x1801073fd  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180107402  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180107407  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18010740e  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180107413  call    _CxxThrowException_0
0x180107419  mov     r8, [rsp+120h+Context]; lpContext
0x18010741e  xor     edx, edx; dwFlags
0x180107420  mov     rcx, rdi; lpInitOnce
0x180107423  call    cs:__imp_InitOnceComplete
0x180107429  test    eax, eax
0x18010742b  jz      short loc_180107476
0x18010742d  mov     [rsp+120h+var_D0], 0
0x180107436  mov     [rsp+120h+var_C8], 0
0x18010743f  lea     rcx, [rsp+120h+var_D0]
0x180107444  call    ??1?$auto_ptr@UMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(void)
0x180107449  nop
0x18010744a  lea     rcx, [rsp+120h+var_C8]; this
0x18010744f  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x180107454  mov     rax, [rsp+120h+Context]
0x180107459  mov     rcx, [rbp+20h+var_10]
0x18010745d  xor     rcx, rsp; StackCookie
0x180107460  call    __security_check_cookie
0x180107465  mov     rdi, [rsp+120h+arg_0]
0x18010746d  add     rsp, 120h
0x180107474  pop     rbp
0x180107475  retn
0x180107476  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18010747b  nop
0x18010747c  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x180107483  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180107488  mov     [rsp+120h+var_F8], eax; unsigned int
0x18010748c  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x180107494  lea     r9, word_180139126
0x18010749b  lea     r8, aNoFilename; "(no filename)"
0x1801074a2  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1801074a7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1801074ac  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1801074b3  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1801074b8  call    _CxxThrowException_0
```
