# SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)

- ea: `0x18000fab0`
- end: `0x18000fb66`
- name: `?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ`
- size: `182`
- prototype: `void(wchar_t *this, const wchar_t *, unsigned int, const wchar_t *, ...)`
- caller_count: `29`
- callee_count: `8`
- tags: ``

## callers

- `0x180009a90`
- `0x18000d6fc`
- `0x18000dd68`
- `0x18000e344`
- `0x18000e664`
- `0x18000e6f0`
- `0x18000e9f0`
- `0x18000eac8`
- `0x18000f98c`
- `0x18000fb70`
- `0x180010010`
- `0x1800100ec`
- `0x180011a90`
- `0x1800121b4`
- `0x1800123c4`
- `0x180012488`
- `0x180012584`
- `0x180012b70`
- `0x180012f30`
- `0x1800213e0`
- `0x1800215b0`
- `0x1800217a0`
- `0x180023547`
- `0x18002363d`
- `0x1800238d9`
- `0x18002393b`
- `0x18002399d`
- `0x1800239ff`
- `0x180024841`

## callees

- `0x18000fab0`
- `0x180013440`
- `0x1800139ac`
- `0x180014130`
- `0x18001a610`
- `0x18001c76c`
- `0x18001cb54`
- `0x18001cc20`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000fae2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000fae2`

## pseudocode

```c
void SearchIndexerDebug::Error(wchar_t *this, const wchar_t *a2, __int64 a3, const wchar_t *a4, ...)
{
  unsigned int v5; // edi
  char v6; // al
  wchar_t **v7; // r9
  char v8; // al
  const wchar_t *v9; // r8
  wchar_t *v10[4]; // [rsp+28h] [rbp-28h] BYREF
  const wchar_t *v12; // [rsp+88h] [rbp+38h] BYREF

  v12 = a4;
  v5 = (unsigned int)a2;
  if ( SearchIndexerTraceProvider::IsEnabled(2u, (unsigned __int64)a2) || IsDebuggerPresent() )
  {
    format_string::format_va(v10, a3, &v12);
    v6 = std::_String_val<std::_Simple_types<wchar_t>>::_Large_mode_engaged(v10);
    v7 = v10;
    if ( v6 )
      LODWORD(v7) = v10[0];
    SearchIndexerDebugImpl::WriteToDebuggerOutput(
      (SearchIndexerDebugImpl *)L"ERROR",
      this,
      (const wchar_t *)v5,
      (unsigned int)v7,
      0);
    v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Large_mode_engaged(v10);
    v9 = (const wchar_t *)v10;
    if ( v8 )
      v9 = v10[0];
    SearchIndexerTraceProvider::Error(this, v5, v9);
    std::wstring::_Tidy_deallocate(v10);
  }
}

```

## disassembly

```asm
0x18000fab0  mov     [rsp-18h+arg_10], r8
0x18000fab5  mov     [rsp-18h+arg_18], r9
0x18000faba  push    rbp
0x18000fabb  push    rbx
0x18000fabc  push    rdi
0x18000fabd  mov     rbp, rsp
0x18000fac0  sub     rsp, 50h
0x18000fac4  mov     rax, cs:__security_cookie
0x18000facb  xor     rax, rsp
0x18000face  mov     [rbp+var_8], rax
0x18000fad2  mov     rbx, rcx
0x18000fad5  mov     edi, edx
0x18000fad7  mov     cl, 2; unsigned __int8
0x18000fad9  call    ?IsEnabled@SearchIndexerTraceProvider@@SA_NE_K@Z; SearchIndexerTraceProvider::IsEnabled(uchar,unsigned __int64)
0x18000fade  test    al, al
0x18000fae0  jnz     short loc_18000FAEC
0x18000fae2  call    cs:__imp_IsDebuggerPresent
0x18000fae8  test    eax, eax
0x18000faea  jz      short loc_18000FB52
0x18000faec  mov     rdx, [rbp+arg_10]
0x18000faf0  lea     r8, [rbp+arg_18]
0x18000faf4  lea     rcx, [rbp+var_28]
0x18000faf8  mov     [rbp+var_30], 0
0x18000fb00  call    ?format_va@format_string@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WPEAD@Z; format_string::format_va(wchar_t const *,char *)
0x18000fb05  lea     rcx, [rbp+var_28]
0x18000fb09  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Large_mode_engaged(void)
0x18000fb0e  test    al, al
0x18000fb10  lea     r9, [rbp+var_28]
0x18000fb14  mov     r8d, edi; wchar_t *
0x18000fb17  lea     rcx, aError; "ERROR"
0x18000fb1e  cmovnz  r9, [rbp+var_28]; unsigned int
0x18000fb23  mov     rdx, rbx; wchar_t *
0x18000fb26  call    ?WriteToDebuggerOutput@SearchIndexerDebugImpl@@YAXPEB_W0I0@Z; SearchIndexerDebugImpl::WriteToDebuggerOutput(wchar_t const *,wchar_t const *,uint,wchar_t const *)
0x18000fb2b  lea     rcx, [rbp+var_28]
0x18000fb2f  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Large_mode_engaged(void)
0x18000fb34  test    al, al
0x18000fb36  lea     r8, [rbp+var_28]
0x18000fb3a  mov     edx, edi; unsigned int
0x18000fb3c  mov     rcx, rbx; wchar_t *
0x18000fb3f  cmovnz  r8, [rbp+var_28]; wchar_t *
0x18000fb44  call    ?Error@SearchIndexerTraceProvider@@SAXPEB_WI0@Z; SearchIndexerTraceProvider::Error(wchar_t const *,uint,wchar_t const *)
0x18000fb49  lea     rcx, [rbp+var_28]
0x18000fb4d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fb52  mov     rcx, [rbp+var_8]
0x18000fb56  xor     rcx, rsp; StackCookie
0x18000fb59  call    __security_check_cookie
0x18000fb5e  add     rsp, 50h
0x18000fb62  pop     rdi
0x18000fb63  pop     rbx
0x18000fb64  pop     rbp
0x18000fb65  retn
```
