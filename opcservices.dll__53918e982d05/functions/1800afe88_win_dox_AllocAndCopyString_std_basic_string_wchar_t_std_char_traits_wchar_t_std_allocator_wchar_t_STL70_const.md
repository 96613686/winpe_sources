# win_dox::AllocAndCopyString(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &)

- ea: `0x1800afe88`
- end: `0x1800b0002`
- name: `?AllocAndCopyString@win_dox@@YAPEA_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z`
- size: `378`
- prototype: ``
- caller_count: `20`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800afdd0`
- `0x1800c1cec`
- `0x1800da950`
- `0x1800ee768`
- `0x1800f5d20`
- `0x1800f5e10`
- `0x1800fa700`
- `0x1800fab60`
- `0x1800faca0`
- `0x1800fad60`
- `0x1800fb150`
- `0x1800fb810`
- `0x1800fb8c0`
- `0x1800fb9f0`
- `0x1800fbab0`
- `0x1800fc0c0`
- `0x180103be0`
- `0x180103d20`
- `0x180103eb0`
- `0x180104370`

## callees

- `0x18002db70`
- `0x1800afe88`
- `0x1800b0008`
- `0x1800cd6fc`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800afed8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800afed8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aff4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aff4c`

## string_xrefs

- `0x1800afee6`: `Unable to copy string`
- `0x1800aff52`: `StringCchCopy() failed.`

## pseudocode

```c
void *__fastcall win_dox::AllocAndCopyString(__int64 a1)
{
  unsigned __int64 v1; // rax
  unsigned __int64 v3; // rdi
  wchar_t *v4; // rax
  const wchar_t *v5; // r8
  void *v6; // r11
  _BYTE pExceptionObject[160]; // [rsp+50h] [rbp-B8h] BYREF

  v1 = *(_QWORD *)(a1 + 24);
  v3 = v1 + 1;
  if ( v1 + 1 < v1 || !is_mul_ok(v3, 2u) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x34u,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"Overflow - String too long.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v4 = (wchar_t *)CoTaskMemAlloc(2 * v3);
  if ( !v4 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x3Cu,
      0x8007000E,
      (struct win_musl::TStringEllipseBase *)L"Unable to copy string");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v5 = (const wchar_t *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 32) >= 8u )
    v5 = *(const wchar_t **)v5;
  if ( (int)StringCchCopyW(v4, v3, v5) < 0 )
  {
    CoTaskMemFree(v6);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x43u,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"StringCchCopy() failed.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  return v6;
}

```

## disassembly

```asm
0x1800afe88  mov     [rsp+arg_8], rbx
0x1800afe8d  push    rdi
0x1800afe8e  sub     rsp, 100h
0x1800afe95  mov     rax, cs:__security_cookie
0x1800afe9c  xor     rax, rsp
0x1800afe9f  mov     [rsp+108h+var_18], rax
0x1800afea7  mov     rax, [rcx+18h]
0x1800afeab  mov     rbx, rcx
0x1800afeae  lea     rdi, [rax+1]
0x1800afeb2  cmp     rdi, rax
0x1800afeb5  jb      loc_1800AFFBC
0x1800afebb  mov     eax, 2
0x1800afec0  mov     [rsp+108h+var_C8], 0
0x1800afec9  mul     rdi
0x1800afecc  test    rdx, rdx
0x1800afecf  jnz     loc_1800AFFBC
0x1800afed5  mov     rcx, rax; cb
0x1800afed8  call    cs:__imp_CoTaskMemAlloc
0x1800afede  mov     r11, rax
0x1800afee1  test    rax, rax
0x1800afee4  jnz     short loc_1800AFF2C
0x1800afee6  lea     rax, aUnableToCopySt; "Unable to copy string"
0x1800afeed  mov     [rsp+108h+var_D8], rax; struct win_musl::TStringEllipseBase *
0x1800afef2  lea     r9, word_180139126
0x1800afef9  mov     [rsp+108h+var_E0], 8007000Eh; unsigned int
0x1800aff01  lea     r8, aNoFilename; "(no filename)"
0x1800aff08  lea     rcx, [rsp+108h+pExceptionObject]; this
0x1800aff0d  mov     [rsp+108h+var_E8], 3Ch ; '<'; unsigned int
0x1800aff15  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800aff1a  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800aff21  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x1800aff26  call    _CxxThrowException_0
0x1800aff2c  cmp     qword ptr [rbx+20h], 8
0x1800aff31  lea     r8, [rbx+8]
0x1800aff35  jb      short loc_1800AFF3A
0x1800aff37  mov     r8, [r8]; wchar_t *
0x1800aff3a  mov     rdx, rdi; unsigned __int64
0x1800aff3d  mov     rcx, r11; wchar_t *
0x1800aff40  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800aff45  test    eax, eax
0x1800aff47  jns     short loc_1800AFF98
0x1800aff49  mov     rcx, r11; pv
0x1800aff4c  call    cs:__imp_CoTaskMemFree
0x1800aff52  lea     rax, aStringcchcopyF; "StringCchCopy() failed."
0x1800aff59  mov     [rsp+108h+var_D8], rax; struct win_musl::TStringEllipseBase *
0x1800aff5e  lea     r9, word_180139126
0x1800aff65  mov     [rsp+108h+var_E0], 8000FFFFh; unsigned int
0x1800aff6d  lea     r8, aNoFilename; "(no filename)"
0x1800aff74  lea     rcx, [rsp+108h+pExceptionObject]; this
0x1800aff79  mov     [rsp+108h+var_E8], 43h ; 'C'; unsigned int
0x1800aff81  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800aff86  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800aff8d  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x1800aff92  call    _CxxThrowException_0
0x1800aff98  mov     rax, r11
0x1800aff9b  mov     rcx, [rsp+108h+var_18]
0x1800affa3  xor     rcx, rsp; StackCookie
0x1800affa6  call    __security_check_cookie
0x1800affab  mov     rbx, [rsp+108h+arg_8]
0x1800affb3  add     rsp, 100h
0x1800affba  pop     rdi
0x1800affbb  retn
0x1800affbc  lea     rax, aOverflowString; "Overflow - String too long."
0x1800affc3  mov     [rsp+108h+var_D8], rax; struct win_musl::TStringEllipseBase *
0x1800affc8  lea     r9, word_180139126
0x1800affcf  mov     [rsp+108h+var_E0], 8000FFFFh; unsigned int
0x1800affd7  lea     r8, aNoFilename; "(no filename)"
0x1800affde  lea     rcx, [rsp+108h+pExceptionObject]; this
0x1800affe3  mov     [rsp+108h+var_E8], 34h ; '4'; unsigned int
0x1800affeb  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800afff0  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800afff7  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x1800afffc  call    _CxxThrowException_0
```
