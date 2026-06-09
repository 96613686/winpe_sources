# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DefaultType>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DefaultType>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DefaultType>)

- ea: `0x18008d950`
- end: `0x18008daf3`
- name: `??$Get@V?$SingletonInitializer@VDefaultType@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VDefaultType@Model@win_musl@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VDefaultType@Model@win_musl@@@341@@Z`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18008d810`

## callees

- `0x18002db70`
- `0x18006554c`
- `0x18008d950`
- `0x1800adbf4`
- `0x1800cd6fc`
- `0x1800cd9dc`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18008d9a1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18008d9a1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18008da7f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18008da7f`

## string_xrefs

- `0x18008dab1`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DefaultType>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DefaultType>>()
{
  win_musl::detail *v0; // rcx
  win_musl::detail *v1; // rcx
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DefaultType>>::store'::`2'::s_storage,
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
    v7[2] = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DefaultType>>::store'::`2'::s_storage;
    v8 = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DefaultType>::operator()(
      v0,
      v7);
    Context = (LPVOID)v7[0];
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DefaultType>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DefaultType>>::store'::`2'::s_storage,
            0,
            Context) )
    {
      v3 = win_musl::detail::GetLastErrorAsFailHR(v1);
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
0x18008d950  mov     rax, rsp
0x18008d953  push    rbp
0x18008d954  lea     rbp, [rax-28h]
0x18008d958  sub     rsp, 120h
0x18008d95f  mov     [rsp+120h+var_C8], 0FFFFFFFFFFFFFFFEh
0x18008d968  mov     [rax+8], rdi
0x18008d96c  mov     rax, cs:__security_cookie
0x18008d973  xor     rax, rsp
0x18008d976  mov     [rbp+20h+var_10], rax
0x18008d97a  mov     [rsp+120h+fPending], 0
0x18008d982  mov     [rsp+120h+Context], 0
0x18008d98b  lea     r9, [rsp+120h+Context]; lpContext
0x18008d990  lea     r8, [rsp+120h+fPending]; fPending
0x18008d995  xor     edx, edx; dwFlags
0x18008d997  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VDefaultType@Model@win_musl@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DefaultType>>::store(void)'::`2'::s_storage
0x18008d99e  mov     rcx, rdi; lpInitOnce
0x18008d9a1  call    cs:__imp_InitOnceBeginInitialize
0x18008d9a7  test    eax, eax
0x18008d9a9  jnz     short loc_18008D9F2
0x18008d9ab  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18008d9b0  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x18008d9b7  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x18008d9bc  mov     [rsp+120h+var_F8], eax; unsigned int
0x18008d9c0  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x18008d9c8  lea     r9, word_180139126
0x18008d9cf  lea     r8, aNoFilename; "(no filename)"
0x18008d9d6  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18008d9db  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18008d9e0  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18008d9e7  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18008d9ec  call    _CxxThrowException_0
0x18008d9f2  cmp     [rsp+120h+fPending], 0
0x18008d9f7  jz      loc_18008DA89
0x18008d9fd  mov     qword ptr [rsp+120h+var_C0], rdi
0x18008da02  mov     [rsp+120h+var_B8], 0
0x18008da0a  lea     rdx, [rsp+120h+var_D0]
0x18008da0f  call    ??R?$SingletonInitializer@VDefaultType@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DefaultType>::operator()(void)
0x18008da14  nop
0x18008da15  mov     rax, [rsp+120h+var_D0]
0x18008da1a  mov     [rsp+120h+Context], rax
0x18008da1f  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VDefaultType@Model@win_musl@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x18008da26  call    atexit
0x18008da2b  test    eax, eax
0x18008da2d  jz      short loc_18008DA75
0x18008da2f  lea     rax, aAtexitFailed; "atexit() failed"
0x18008da36  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x18008da3b  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x18008da43  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x18008da4b  lea     r9, word_180139126
0x18008da52  lea     r8, aNoFilename; "(no filename)"
0x18008da59  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18008da5e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18008da63  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18008da6a  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18008da6f  call    _CxxThrowException_0
0x18008da75  mov     r8, [rsp+120h+Context]; lpContext
0x18008da7a  xor     edx, edx; dwFlags
0x18008da7c  mov     rcx, rdi; lpInitOnce
0x18008da7f  call    cs:__imp_InitOnceComplete
0x18008da85  test    eax, eax
0x18008da87  jz      short loc_18008DAAB
0x18008da89  mov     rax, [rsp+120h+Context]
0x18008da8e  mov     rcx, [rbp+20h+var_10]
0x18008da92  xor     rcx, rsp; StackCookie
0x18008da95  call    __security_check_cookie
0x18008da9a  mov     rdi, [rsp+120h+arg_0]
0x18008daa2  add     rsp, 120h
0x18008daa9  pop     rbp
0x18008daaa  retn
0x18008daab  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18008dab0  nop
0x18008dab1  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x18008dab8  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x18008dabd  mov     [rsp+120h+var_F8], eax; unsigned int
0x18008dac1  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x18008dac9  lea     r9, word_180139126
0x18008dad0  lea     r8, aNoFilename; "(no filename)"
0x18008dad7  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18008dadc  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18008dae1  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18008dae8  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18008daed  call    _CxxThrowException_0
```
