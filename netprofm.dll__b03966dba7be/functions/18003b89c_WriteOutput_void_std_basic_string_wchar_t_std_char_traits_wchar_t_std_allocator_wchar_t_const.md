# WriteOutput(void *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18003b89c`
- end: `0x18003b9ee`
- name: `?WriteOutput@@YAKPEAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `338`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000f888`

## callees

- `0x180010124`
- `0x180011614`
- `0x1800120d0`
- `0x18002b7c0`
- `0x180034c2c`
- `0x18003b89c`
- `0x18003ba74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b8f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b99b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b8f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b99b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003b8ec`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003b991`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003b8ec`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003b991`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
DWORD __fastcall WriteOutput(HANDLE hFile, __int64 a2)
{
  __int64 v5; // rax
  const void *v6; // rax
  DWORD v7; // r8d
  DWORD LastError; // ebx
  _BYTE v9[32]; // [rsp+38h] [rbp-A0h] BYREF
  _BYTE v10[32]; // [rsp+58h] [rbp-80h] BYREF
  _BYTE v11[32]; // [rsp+78h] [rbp-60h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+98h] [rbp-40h] BYREF
  __int16 v13; // [rsp+9Ch] [rbp-3Ch] BYREF
  _BYTE v14[16]; // [rsp+A0h] [rbp-38h] BYREF

  v13 = -257;
  NumberOfBytesWritten = 0;
  if ( !WriteFile(hFile, &v13, 2u, &NumberOfBytesWritten, 0) )
    return GetLastError();
  std::wstring::wstring((__int64)v10, (__int64)L"\r\n");
  std::wstring::wstring((__int64)v9, (__int64)L"\n");
  v5 = std::wstring::wstring(v11, a2);
  replace_all_copy(v14, v5, v9, v10);
  std::wstring::_Tidy_deallocate((__int64)v9);
  std::wstring::_Tidy_deallocate((__int64)v10);
  v6 = (const void *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  if ( WriteFile(hFile, v6, v7, &NumberOfBytesWritten, 0) )
  {
    std::wstring::_Tidy_deallocate((__int64)v14);
    return 0;
  }
  else
  {
    LastError = GetLastError();
    std::wstring::_Tidy_deallocate((__int64)v14);
    return LastError;
  }
}

```

## disassembly

```asm
0x18003b89c  mov     r11, rsp
0x18003b89f  mov     [r11+18h], rbx
0x18003b8a3  push    rdi
0x18003b8a4  sub     rsp, 0D0h
0x18003b8ab  mov     rax, cs:__security_cookie
0x18003b8b2  xor     rax, rsp
0x18003b8b5  mov     [rsp+0D8h+var_18], rax
0x18003b8bd  mov     rdi, rdx
0x18003b8c0  mov     rbx, rcx
0x18003b8c3  mov     eax, 0FEFFh
0x18003b8c8  mov     [r11-3Ch], ax
0x18003b8cd  mov     dword ptr [r11-40h], 0
0x18003b8d5  mov     [rsp+0D8h+lpOverlapped], 0; lpOverlapped
0x18003b8de  lea     r9, [r11-40h]; lpNumberOfBytesWritten
0x18003b8e2  mov     r8d, 2; nNumberOfBytesToWrite
0x18003b8e8  lea     rdx, [r11-3Ch]; lpBuffer
0x18003b8ec  call    cs:__imp_WriteFile
0x18003b8f2  test    eax, eax
0x18003b8f4  jnz     short loc_18003B901
0x18003b8f6  call    cs:__imp_GetLastError
0x18003b8fc  jmp     loc_18003B9CC
0x18003b901  lea     rdx, asc_18004C298; "\r\n"
0x18003b908  lea     rcx, [rsp+0D8h+var_80]
0x18003b90d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18003b912  nop
0x18003b913  lea     rdx, asc_180047810; "\n"
0x18003b91a  lea     rcx, [rsp+0D8h+var_A0]
0x18003b91f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18003b924  nop
0x18003b925  mov     rdx, rdi
0x18003b928  lea     rcx, [rsp+0D8h+var_60]
0x18003b92d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003b932  lea     r9, [rsp+0D8h+var_80]
0x18003b937  lea     r8, [rsp+0D8h+var_A0]
0x18003b93c  mov     rdx, rax
0x18003b93f  lea     rcx, [rsp+0D8h+var_38]
0x18003b947  call    ?replace_all_copy@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@AEBV12@1@Z; replace_all_copy(std::wstring,std::wstring const &,std::wstring const &)
0x18003b94c  nop
0x18003b94d  lea     rcx, [rsp+0D8h+var_A0]
0x18003b952  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003b957  nop
0x18003b958  lea     rcx, [rsp+0D8h+var_80]
0x18003b95d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003b962  mov     r8d, [rsp+0D8h+var_28]
0x18003b96a  add     r8d, r8d
0x18003b96d  lea     rcx, [rsp+0D8h+var_38]
0x18003b975  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003b97a  mov     rdx, rax; lpBuffer
0x18003b97d  mov     [rsp+0D8h+lpOverlapped], 0; lpOverlapped
0x18003b986  lea     r9, [rsp+0D8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003b98e  mov     rcx, rbx; hFile
0x18003b991  call    cs:__imp_WriteFile
0x18003b997  test    eax, eax
0x18003b999  jnz     short loc_18003B9B4
0x18003b99b  call    cs:__imp_GetLastError
0x18003b9a1  mov     ebx, eax
0x18003b9a3  lea     rcx, [rsp+0D8h+var_38]
0x18003b9ab  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003b9b0  mov     eax, ebx
0x18003b9b2  jmp     short loc_18003B9CC
0x18003b9b4  lea     rcx, [rsp+0D8h+var_38]
0x18003b9bc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003b9c1  xor     eax, eax
0x18003b9c3  jmp     short loc_18003B9CC
0x18003b9c5  mov     eax, [rsp+0D8h+NumberOfBytesWritten]
0x18003b9cc  mov     rcx, [rsp+0D8h+var_18]
0x18003b9d4  xor     rcx, rsp; StackCookie
0x18003b9d7  call    __security_check_cookie
0x18003b9dc  mov     rbx, [rsp+0D8h+arg_10]
0x18003b9e4  add     rsp, 0D0h
0x18003b9eb  pop     rdi
0x18003b9ec  retn
```
