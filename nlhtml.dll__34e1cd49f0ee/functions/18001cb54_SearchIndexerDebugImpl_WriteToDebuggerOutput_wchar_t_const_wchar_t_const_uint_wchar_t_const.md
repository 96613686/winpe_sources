# SearchIndexerDebugImpl::WriteToDebuggerOutput(wchar_t const *,wchar_t const *,uint,wchar_t const *)

- ea: `0x18001cb54`
- end: `0x18001cbe0`
- name: `?WriteToDebuggerOutput@SearchIndexerDebugImpl@@YAXPEB_W0I0@Z`
- size: `140`
- prototype: `void __fastcall(SearchIndexerDebugImpl *__hidden this, const wchar_t *, const wchar_t *, unsigned int, const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000fab0`
- `0x180010288`

## callees

- `0x1800139ac`
- `0x180014130`
- `0x18001a610`
- `0x18001cb54`
- `0x18001cbe8`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001cbba`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001cbba`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001cb78`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001cb78`

## pseudocode

```c
void __fastcall SearchIndexerDebugImpl::WriteToDebuggerOutput(
        SearchIndexerDebugImpl *this,
        const wchar_t *a2,
        const wchar_t *a3,
        __int64 a4)
{
  unsigned int v5; // esi
  char v8; // al
  const WCHAR *v9; // rcx
  LPCWSTR lpOutputString[4]; // [rsp+30h] [rbp-58h] BYREF

  v5 = (unsigned int)a3;
  if ( IsDebuggerPresent() )
  {
    format_string::format(lpOutputString, L"%s(%u) %s : %s", a2, v5, this, a4);
    v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Large_mode_engaged(lpOutputString);
    v9 = (const WCHAR *)lpOutputString;
    if ( v8 )
      v9 = lpOutputString[0];
    OutputDebugStringW(v9);
    std::wstring::_Tidy_deallocate(lpOutputString);
  }
}

```

## disassembly

```asm
0x18001cb54  push    rbx
0x18001cb56  push    rbp
0x18001cb57  push    rsi
0x18001cb58  push    rdi
0x18001cb59  sub     rsp, 68h
0x18001cb5d  mov     rax, cs:__security_cookie
0x18001cb64  xor     rax, rsp
0x18001cb67  mov     [rsp+88h+var_38], rax
0x18001cb6c  mov     rbp, r9
0x18001cb6f  mov     esi, r8d
0x18001cb72  mov     rdi, rdx
0x18001cb75  mov     rbx, rcx
0x18001cb78  call    cs:__imp_IsDebuggerPresent
0x18001cb7e  test    eax, eax
0x18001cb80  jz      short loc_18001CBCA
0x18001cb82  mov     [rsp+88h+var_60], rbp
0x18001cb87  lea     rdx, aSUSS; "%s(%u) %s : %s"
0x18001cb8e  mov     r9d, esi
0x18001cb91  mov     [rsp+88h+var_68], rbx
0x18001cb96  mov     r8, rdi
0x18001cb99  lea     rcx, [rsp+88h+lpOutputString]
0x18001cb9e  call    ?format@format_string@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; format_string::format(wchar_t const *,...)
0x18001cba3  lea     rcx, [rsp+88h+lpOutputString]
0x18001cba8  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Large_mode_engaged(void)
0x18001cbad  test    al, al
0x18001cbaf  lea     rcx, [rsp+88h+lpOutputString]
0x18001cbb4  cmovnz  rcx, [rsp+88h+lpOutputString]; lpOutputString
0x18001cbba  call    cs:__imp_OutputDebugStringW
0x18001cbc0  lea     rcx, [rsp+88h+lpOutputString]
0x18001cbc5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cbca  mov     rcx, [rsp+88h+var_38]
0x18001cbcf  xor     rcx, rsp; StackCookie
0x18001cbd2  call    __security_check_cookie
0x18001cbd7  add     rsp, 68h
0x18001cbdb  pop     rdi
0x18001cbdc  pop     rsi
0x18001cbdd  pop     rbp
0x18001cbde  pop     rbx
0x18001cbdf  retn
```
