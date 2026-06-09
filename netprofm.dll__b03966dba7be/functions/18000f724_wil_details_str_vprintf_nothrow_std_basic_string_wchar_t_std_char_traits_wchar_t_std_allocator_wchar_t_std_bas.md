# wil::details::str_vprintf_nothrow<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,wchar_t const *,char * &)

- ea: `0x18000f724`
- end: `0x18000f880`
- name: `??$str_vprintf_nothrow@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@details@wil@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WAEAPEAD@Z`
- size: `348`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, va_list *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18000f388`

## callees

- `0x18000c5d4`
- `0x18000f700`
- `0x18000f724`
- `0x180010124`
- `0x180011614`
- `0x1800120d0`
- `0x180012f58`
- `0x180012fac`
- `0x180034dac`
- `0x180038488`
- `0x18003850c`

## string_xrefs

- `0x18000f77f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000f83d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall wil::details::str_vprintf_nothrow<std::wstring>(__int64 a1, const wchar_t *a2, va_list *a3)
{
  size_t v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned int v12; // edi
  wchar_t *v13; // rax
  unsigned __int64 v14; // rsi
  wchar_t *v15; // rdi
  unsigned int v16; // ebx
  int v17; // eax
  __int64 v18; // rax
  int v20[8]; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v21[32]; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v6 = vscwprintf(a2, *a3);
  std::wstring::wstring(v21, v7);
  v9 = wil::details::string_maker<std::wstring>::make(v21, v8, v6);
  v12 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7CD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v9,
      v20[0]);
    goto LABEL_16;
  }
  v13 = (wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v21, v10, v11);
  v14 = v6 + 1;
  v15 = v13;
  if ( v6 == -1 )
  {
    v16 = -2147024809;
    if ( v14 )
      goto LABEL_14;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)v16,
      v20[0]);
    v12 = v16;
    goto LABEL_16;
  }
  if ( v14 > 0x7FFFFFFF )
  {
    v16 = -2147024809;
LABEL_14:
    *v15 = 0;
    goto LABEL_15;
  }
  v17 = vsnwprintf(v13, v6, a2, *a3);
  if ( v17 < 0 || v17 > v6 )
  {
    v15[v6] = 0;
    v16 = -2147024774;
    if ( (v14 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
      goto LABEL_14;
    goto LABEL_15;
  }
  if ( v17 == v6 )
    v15[v6] = 0;
  v18 = wil::details::string_maker<std::wstring>::release(v21, v20);
  std::wstring::operator=(a1, v18);
  std::wstring::_Tidy_deallocate(v20);
  v12 = 0;
LABEL_16:
  std::wstring::_Tidy_deallocate(v21);
  return v12;
}

```

## disassembly

```asm
0x18000f724  mov     [rsp+arg_18], rbx
0x18000f729  push    rbp
0x18000f72a  push    rsi
0x18000f72b  push    rdi
0x18000f72c  push    r14
0x18000f72e  push    r15
0x18000f730  sub     rsp, 70h
0x18000f734  mov     rax, cs:__security_cookie
0x18000f73b  xor     rax, rsp
0x18000f73e  mov     [rsp+98h+var_38], rax
0x18000f743  mov     rbp, rdx
0x18000f746  mov     r15, rcx
0x18000f749  mov     rdx, [r8]; ArgList
0x18000f74c  mov     rcx, rbp; Format
0x18000f74f  mov     r14, r8
0x18000f752  call    _vscwprintf
0x18000f757  lea     rcx, [rsp+98h+var_58]
0x18000f75c  movsxd  rbx, eax
0x18000f75f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f764  mov     r8, rbx
0x18000f767  lea     rcx, [rsp+98h+var_58]
0x18000f76c  call    ?make@?$string_maker@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<std::wstring>::make(wchar_t const *,unsigned __int64)
0x18000f771  mov     edi, eax
0x18000f773  test    eax, eax
0x18000f775  jns     short loc_18000F798
0x18000f777  mov     rcx, [rsp+98h]; this
0x18000f77f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f786  mov     r9d, eax; char *
0x18000f789  mov     edx, 7CDh; void *
0x18000f78e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f793  jmp     loc_18000F853
0x18000f798  lea     rcx, [rsp+98h+var_58]
0x18000f79d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18000f7a2  lea     rsi, [rbx+1]
0x18000f7a6  mov     rdi, rax
0x18000f7a9  test    rsi, rsi
0x18000f7ac  jz      short loc_18000F826
0x18000f7ae  cmp     rsi, 7FFFFFFFh
0x18000f7b5  jbe     short loc_18000F7BE
0x18000f7b7  mov     ebx, 80070057h
0x18000f7bc  jmp     short loc_18000F830
0x18000f7be  mov     r9, [r14]; Args
0x18000f7c1  mov     r8, rbp; Format
0x18000f7c4  mov     rdx, rbx; BufferCount
0x18000f7c7  mov     rcx, rdi; Buffer
0x18000f7ca  call    _vsnwprintf
0x18000f7cf  test    eax, eax
0x18000f7d1  js      short loc_18000F80A
0x18000f7d3  cdqe
0x18000f7d5  cmp     rax, rbx
0x18000f7d8  ja      short loc_18000F80A
0x18000f7da  jnz     short loc_18000F7E2
0x18000f7dc  xor     eax, eax
0x18000f7de  mov     [rdi+rbx*2], ax
0x18000f7e2  lea     rdx, [rsp+98h+var_78]
0x18000f7e7  lea     rcx, [rsp+98h+var_58]
0x18000f7ec  call    ?release@?$string_maker@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@details@wil@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; wil::details::string_maker<std::wstring>::release(void)
0x18000f7f1  mov     rdx, rax
0x18000f7f4  mov     rcx, r15
0x18000f7f7  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000f7fc  lea     rcx, [rsp+98h+var_78]
0x18000f801  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f806  xor     edi, edi
0x18000f808  jmp     short loc_18000F853
0x18000f80a  xor     eax, eax
0x18000f80c  mov     [rdi+rbx*2], ax
0x18000f810  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000f81a  mov     ebx, 8007007Ah
0x18000f81f  test    rax, rsi
0x18000f822  jbe     short loc_18000F835
0x18000f824  jmp     short loc_18000F830
0x18000f826  mov     ebx, 80070057h
0x18000f82b  test    rsi, rsi
0x18000f82e  jz      short loc_18000F835
0x18000f830  xor     eax, eax
0x18000f832  mov     [rdi], ax
0x18000f835  mov     rcx, [rsp+98h]; this
0x18000f83d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f844  mov     r9d, ebx; char *
0x18000f847  mov     edx, 7D1h; void *
0x18000f84c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f851  mov     edi, ebx
0x18000f853  lea     rcx, [rsp+98h+var_58]
0x18000f858  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f85d  mov     eax, edi
0x18000f85f  mov     rcx, [rsp+98h+var_38]
0x18000f864  xor     rcx, rsp; StackCookie
0x18000f867  call    __security_check_cookie
0x18000f86c  mov     rbx, [rsp+98h+arg_18]
0x18000f874  add     rsp, 70h
0x18000f878  pop     r15
0x18000f87a  pop     r14
0x18000f87c  pop     rdi
0x18000f87d  pop     rsi
0x18000f87e  pop     rbp
0x18000f87f  retn
```
