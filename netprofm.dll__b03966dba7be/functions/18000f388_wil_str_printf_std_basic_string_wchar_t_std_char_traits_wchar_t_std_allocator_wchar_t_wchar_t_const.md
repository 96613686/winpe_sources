# wil::str_printf<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(wchar_t const *,...)

- ea: `0x18000f388`
- end: `0x18000f41e`
- name: `??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ`
- size: `150`
- prototype: `__int64(__int64, __int64, ...)`
- caller_count: `52`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d654`
- `0x18000f0ec`
- `0x18000f234`
- `0x180010164`
- `0x1800104b8`
- `0x180010ce0`
- `0x18001101c`
- `0x18001136c`
- `0x180034de8`
- `0x18003500c`
- `0x1800351d0`
- `0x1800353a4`
- `0x1800355a4`
- `0x18003580c`
- `0x18003640c`
- `0x180036950`
- `0x180036a3c`
- `0x180037430`
- `0x180037c74`
- `0x180037d5c`
- `0x180038b08`
- `0x1800391a4`
- `0x180039b84`
- `0x180039f70`
- `0x18003a624`
- `0x18003c0b8`
- `0x18003c818`
- `0x18003cd24`
- `0x18003d000`
- `0x18003d084`
- `0x18003d140`
- `0x18003d25c`
- `0x18003d4c4`
- `0x18003d5ec`
- `0x18003d6e8`
- `0x18003d7dc`
- `0x18003d880`
- `0x18003d980`
- `0x18003da38`
- `0x18003db10`
- `0x18003db70`
- `0x18003dc4c`
- `0x18003dd38`
- `0x18003dd98`
- `0x18003de20`
- `0x18003dec4`
- `0x18003e040`
- `0x18003e114`
- `0x18003e3bc`
- `0x18003e780`

## callees

- `0x18000f388`
- `0x18000f700`
- `0x18000f724`
- `0x1800120d0`
- `0x18002a928`

## string_xrefs

- `0x18000f3f5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 wil::str_printf<std::wstring>(__int64 a1, __int64 a2, ...)
{
  __int64 v3; // rcx
  int v4; // eax
  va_list v6; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  va_list va; // [rsp+60h] [rbp+18h] BYREF

  va_start(va, a2);
  std::wstring::wstring(a1, a2);
  va_copy(v6, va);
  v4 = wil::details::str_vprintf_nothrow<std::wstring>(v3, a2, &v6);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7F0,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v4,
      1);
  return a1;
}

```

## disassembly

```asm
0x18000f388  mov     r11, rsp
0x18000f38b  mov     [r11+10h], rdx
0x18000f38f  mov     [r11+18h], r8
0x18000f393  mov     [r11+20h], r9
0x18000f397  push    rbx
0x18000f398  sub     rsp, 40h
0x18000f39c  mov     rax, cs:__security_cookie
0x18000f3a3  xor     rax, rsp
0x18000f3a6  mov     [rsp+48h+var_10], rax
0x18000f3ab  mov     rbx, rcx
0x18000f3ae  mov     [r11-20h], rcx
0x18000f3b2  mov     [rsp+48h+var_28], 0
0x18000f3ba  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f3bf  mov     [rsp+48h+var_28], 1; int
0x18000f3c7  mov     [rsp+48h+var_18], 0
0x18000f3d0  lea     rax, [rsp+48h+arg_10]
0x18000f3d5  mov     [rsp+48h+var_18], rax
0x18000f3da  lea     r8, [rsp+48h+var_18]
0x18000f3df  mov     rdx, [rsp+48h+arg_8]
0x18000f3e4  call    ??$str_vprintf_nothrow@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@details@wil@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WAEAPEAD@Z; wil::details::str_vprintf_nothrow<std::wstring>(std::wstring &,wchar_t const *,char * &)
0x18000f3e9  test    eax, eax
0x18000f3eb  jns     short loc_18000F407
0x18000f3ed  mov     rcx, [rsp+48h]; this
0x18000f3f2  mov     r9d, eax; char *
0x18000f3f5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f3fc  mov     edx, 7F0h; void *
0x18000f401  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f407  mov     rax, rbx
0x18000f40a  mov     rcx, [rsp+48h+var_10]
0x18000f40f  xor     rcx, rsp; StackCookie
0x18000f412  call    __security_check_cookie
0x18000f417  add     rsp, 40h
0x18000f41b  pop     rbx
0x18000f41c  retn
```
