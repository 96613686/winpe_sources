# cxl::ImpersonateUser::~ImpersonateUser(void)

- ea: `0x1800a38d0`
- end: `0x1800a3998`
- name: `??1ImpersonateUser@cxl@@QEAA@XZ`
- size: `200`
- prototype: `void __fastcall(cxl::ImpersonateUser *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x1800a68bc`

## callees

- `0x180002f50`
- `0x18001cc08`
- `0x180028f30`
- `0x180029578`
- `0x180071978`
- `0x1800926d4`
- `0x180092d1c`
- `0x1800a32d8`
- `0x1800a38d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3903`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a38f9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a38f9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a3950`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a3950`

## pseudocode

```c
void __fastcall cxl::ImpersonateUser::~ImpersonateUser(HANDLE *this)
{
  const WCHAR *v2; // rax
  int v3; // [rsp+28h] [rbp-11h]
  unsigned int LastError; // [rsp+40h] [rbp+7h] BYREF
  int v5; // [rsp+44h] [rbp+Bh] BYREF
  _QWORD v6[4]; // [rsp+48h] [rbp+Fh] BYREF
  _BYTE v7[32]; // [rsp+68h] [rbp+2Fh] BYREF

  if ( !SetThreadToken(0, this[1]) )
  {
    LastError = GetLastError();
    std::wstring::wstring(v7);
    cxl::StringWriter::StringWriter(v6, v7);
    v5 = 758;
    cxl::TextWriter::WriteLine<char,char [48],char [44],int,char [39],unsigned long>(
      (struct cxl::TextWriter *)v6,
      (__int64)&v5,
      v3,
      (__int64)&LastError);
    v2 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7);
    OutputDebugStringW(v2);
    cxl::Debug::StopIfIsDebuggedOrCrash(LastError);
    v6[0] = &cxl::RefCounted::`vftable';
    std::wstring::_Tidy_deallocate(v7);
  }
  cxl::Token::Clear((cxl::Token *)this);
}

```

## disassembly

```asm
0x1800a38d0  mov     [rsp-8+arg_8], rbx
0x1800a38d5  push    rbp
0x1800a38d6  lea     rbp, [rsp-57h]
0x1800a38db  sub     rsp, 90h
0x1800a38e2  mov     rax, cs:__security_cookie
0x1800a38e9  xor     rax, rsp
0x1800a38ec  mov     [rbp+57h+var_8], rax
0x1800a38f0  mov     rbx, rcx
0x1800a38f3  mov     rdx, [rcx+8]; Token
0x1800a38f7  xor     ecx, ecx; Thread
0x1800a38f9  call    cs:__imp_SetThreadToken
0x1800a38ff  test    eax, eax
0x1800a3901  jnz     short loc_1800A3972
0x1800a3903  call    cs:__imp_GetLastError
0x1800a3909  mov     [rbp+57h+var_50], eax
0x1800a390c  lea     rcx, [rbp+57h+var_28]
0x1800a3910  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a3915  lea     rdx, [rbp+57h+var_28]
0x1800a3919  lea     rcx, [rbp+57h+var_4C+4]
0x1800a391d  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800a3922  mov     dword ptr [rbp+57h+var_4C], 2F6h
0x1800a3929  lea     rax, [rbp+57h+var_50]
0x1800a392d  mov     [rsp+90h+var_60], rax; __int64
0x1800a3932  lea     rax, [rbp+57h+var_4C]
0x1800a3936  mov     [rsp+90h+var_70], rax; __int64
0x1800a393b  lea     rcx, [rbp+57h+var_4C+4]; struct cxl::TextWriter *
0x1800a393f  call    ??$WriteLine@D$$BY0DA@D$$BY0CM@DH$$BY0CH@DK@TextWriter@cxl@@QEAAXPEBDAEAY0DA@$$CBDAEAY0CM@$$CBDAEBHAEAY0CH@$$CBDAEBK@Z; cxl::TextWriter::WriteLine<char,char [48],char [44],int,char [39],ulong>(char const *,char const (&)[48],char const (&)[44],int const &,char const (&)[39],ulong const &)
0x1800a3944  lea     rcx, [rbp+57h+var_28]
0x1800a3948  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800a394d  mov     rcx, rax; lpOutputString
0x1800a3950  call    cs:__imp_OutputDebugStringW
0x1800a3956  mov     ecx, [rbp+57h+var_50]; unsigned int
0x1800a3959  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x1800a395e  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x1800a3965  mov     [rbp+57h+var_4C+4], rax
0x1800a3969  lea     rcx, [rbp+57h+var_28]
0x1800a396d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3972  mov     rcx, rbx; this
0x1800a3975  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x1800a397a  nop
0x1800a397b  mov     rcx, [rbp+57h+var_8]
0x1800a397f  xor     rcx, rsp; StackCookie
0x1800a3982  call    __security_check_cookie
0x1800a3987  mov     rbx, [rsp+90h+arg_8]
0x1800a398f  add     rsp, 90h
0x1800a3996  pop     rbp
0x1800a3997  retn
```
