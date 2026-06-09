# win_musl::InitOnceSingleton<win_musl::ContentType,win_dox::OpcPartSetImplementation::RelationshipsContentTypeSingleton_tag>::Get<win_dox::OpcPartSetImplementation::SingletonInitializer>(win_dox::OpcPartSetImplementation::SingletonInitializer)

- ea: `0x1800f3d80`
- end: `0x1800f3f4a`
- name: `??$Get@VSingletonInitializer@OpcPartSetImplementation@win_dox@@@?$InitOnceSingleton@UContentType@win_musl@@URelationshipsContentTypeSingleton_tag@OpcPartSetImplementation@win_dox@@@win_musl@@SAPEAUContentType@1@VSingletonInitializer@OpcPartSetImplementation@win_dox@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800f429c`

## callees

- `0x18002db70`
- `0x18006554c`
- `0x180099234`
- `0x1800b6f6c`
- `0x1800cd6fc`
- `0x1800cd9dc`
- `0x1800f3d80`
- `0x1800f4034`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800f3dd1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800f3dd1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800f3eaf`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800f3eaf`

## string_xrefs

- `0x1800f3f08`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::ContentType,win_dox::OpcPartSetImplementation::RelationshipsContentTypeSingleton_tag>::Get<win_dox::OpcPartSetImplementation::SingletonInitializer>()
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
          &`win_musl::InitOnceSingleton<win_musl::ContentType,win_dox::OpcPartSetImplementation::RelationshipsContentTypeSingleton_tag>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::ContentType,win_dox::OpcPartSetImplementation::RelationshipsContentTypeSingleton_tag>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_dox::OpcPartSetImplementation::SingletonInitializer::operator()(v0, &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::ContentType,win_dox::OpcPartSetImplementation::RelationshipsContentTypeSingleton_tag>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::ContentType,win_dox::OpcPartSetImplementation::RelationshipsContentTypeSingleton_tag>::store'::`2'::s_storage,
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
    std::auto_ptr<win_musl::ContentType>::~auto_ptr<win_musl::ContentType>(&v7);
    win_musl::InitOnceGuard::~InitOnceGuard((win_musl::InitOnceGuard *)&v8);
  }
  return Context;
}

```

## disassembly

```asm
0x1800f3d80  mov     rax, rsp
0x1800f3d83  push    rbp
0x1800f3d84  lea     rbp, [rax-28h]
0x1800f3d88  sub     rsp, 120h
0x1800f3d8f  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1800f3d98  mov     [rax+8], rdi
0x1800f3d9c  mov     rax, cs:__security_cookie
0x1800f3da3  xor     rax, rsp
0x1800f3da6  mov     [rbp+20h+var_10], rax
0x1800f3daa  mov     [rsp+120h+fPending], 0
0x1800f3db2  mov     [rsp+120h+Context], 0
0x1800f3dbb  lea     r9, [rsp+120h+Context]; lpContext
0x1800f3dc0  lea     r8, [rsp+120h+fPending]; fPending
0x1800f3dc5  xor     edx, edx; dwFlags
0x1800f3dc7  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@UContentType@win_musl@@URelationshipsContentTypeSingleton_tag@OpcPartSetImplementation@win_dox@@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::ContentType,win_dox::OpcPartSetImplementation::RelationshipsContentTypeSingleton_tag>::store(void)'::`2'::s_storage
0x1800f3dce  mov     rcx, rdi; lpInitOnce
0x1800f3dd1  call    cs:__imp_InitOnceBeginInitialize
0x1800f3dd7  test    eax, eax
0x1800f3dd9  jnz     short loc_1800F3E22
0x1800f3ddb  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800f3de0  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x1800f3de7  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x1800f3dec  mov     [rsp+120h+var_F8], eax; unsigned int
0x1800f3df0  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x1800f3df8  lea     r9, word_180139126
0x1800f3dff  lea     r8, aNoFilename; "(no filename)"
0x1800f3e06  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800f3e0b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800f3e10  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800f3e17  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800f3e1c  call    _CxxThrowException_0
0x1800f3e22  cmp     [rsp+120h+fPending], 0
0x1800f3e27  jz      loc_1800F3EE0
0x1800f3e2d  mov     [rsp+120h+var_C8], rdi
0x1800f3e32  mov     dword ptr [rsp+120h+var_C0], 0
0x1800f3e3a  lea     rdx, [rsp+120h+var_D0]
0x1800f3e3f  call    ??RSingletonInitializer@OpcPartSetImplementation@win_dox@@QEBA?AV?$auto_ptr@UContentType@win_musl@@@std@@XZ; win_dox::OpcPartSetImplementation::SingletonInitializer::operator()(void)
0x1800f3e44  nop
0x1800f3e45  mov     rax, [rsp+120h+var_D0]
0x1800f3e4a  mov     [rsp+120h+Context], rax
0x1800f3e4f  lea     rcx, ?Cleanup@?$InitOnceSingleton@UContentType@win_musl@@URelationshipsContentTypeSingleton_tag@OpcPartSetImplementation@win_dox@@@win_musl@@CAXXZ; void (__cdecl *)()
0x1800f3e56  call    atexit
0x1800f3e5b  test    eax, eax
0x1800f3e5d  jz      short loc_1800F3EA5
0x1800f3e5f  lea     rax, aAtexitFailed; "atexit() failed"
0x1800f3e66  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x1800f3e6b  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x1800f3e73  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x1800f3e7b  lea     r9, word_180139126
0x1800f3e82  lea     r8, aNoFilename; "(no filename)"
0x1800f3e89  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800f3e8e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800f3e93  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800f3e9a  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800f3e9f  call    _CxxThrowException_0
0x1800f3ea5  mov     r8, [rsp+120h+Context]; lpContext
0x1800f3eaa  xor     edx, edx; dwFlags
0x1800f3eac  mov     rcx, rdi; lpInitOnce
0x1800f3eaf  call    cs:__imp_InitOnceComplete
0x1800f3eb5  test    eax, eax
0x1800f3eb7  jz      short loc_1800F3F02
0x1800f3eb9  mov     [rsp+120h+var_D0], 0
0x1800f3ec2  mov     [rsp+120h+var_C8], 0
0x1800f3ecb  lea     rcx, [rsp+120h+var_D0]
0x1800f3ed0  call    ??1?$auto_ptr@UContentType@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::ContentType>::~auto_ptr<win_musl::ContentType>(void)
0x1800f3ed5  nop
0x1800f3ed6  lea     rcx, [rsp+120h+var_C8]; this
0x1800f3edb  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x1800f3ee0  mov     rax, [rsp+120h+Context]
0x1800f3ee5  mov     rcx, [rbp+20h+var_10]
0x1800f3ee9  xor     rcx, rsp; StackCookie
0x1800f3eec  call    __security_check_cookie
0x1800f3ef1  mov     rdi, [rsp+120h+arg_0]
0x1800f3ef9  add     rsp, 120h
0x1800f3f00  pop     rbp
0x1800f3f01  retn
0x1800f3f02  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800f3f07  nop
0x1800f3f08  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x1800f3f0f  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x1800f3f14  mov     [rsp+120h+var_F8], eax; unsigned int
0x1800f3f18  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x1800f3f20  lea     r9, word_180139126
0x1800f3f27  lea     r8, aNoFilename; "(no filename)"
0x1800f3f2e  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800f3f33  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800f3f38  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800f3f3f  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800f3f44  call    _CxxThrowException_0
```
