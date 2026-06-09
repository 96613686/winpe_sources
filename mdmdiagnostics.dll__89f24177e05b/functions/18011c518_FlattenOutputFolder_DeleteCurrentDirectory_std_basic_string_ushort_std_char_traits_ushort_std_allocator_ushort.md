# FlattenOutputFolder::DeleteCurrentDirectory(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18011c518`
- end: `0x18011c5d1`
- name: `?DeleteCurrentDirectory@FlattenOutputFolder@@AEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18011c724`
- `0x18011ca44`

## callees

- `0x180019000`
- `0x1800e66b8`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef8c8`
- `0x1800ef900`
- `0x180118a64`
- `0x18011c518`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18011c54f`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18011c54f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c588`

## string_xrefs

- `0x18011c559`: `DeleteCurrentDirectory: Could not delete directory: `

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FlattenOutputFolder::DeleteCurrentDirectory(__int64 a1, __int64 a2)
{
  const WCHAR *v3; // rax
  DWORD LastError; // ebx
  const unsigned __int16 *v5; // rax
  TelemetryWriter *v6; // rcx
  _BYTE v8[32]; // [rsp+28h] [rbp-30h] BYREF

  std::wstring::wstring(v8);
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  if ( !RemoveDirectoryW(v3) )
  {
    std::wstring::append(v8, L"DeleteCurrentDirectory: Could not delete directory: ");
    std::wstring::append(v8, a2);
    std::wstring::append(v8, L". Error: ");
    LastError = GetLastError();
    v5 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
    TelemetryWriter::Write(v6, v5, LastError);
  }
  std::wstring::_Tidy_deallocate(v8);
  return std::wstring::_Tidy_deallocate(a2);
}

```

## disassembly

```asm
0x18011c518  mov     [rsp+arg_0], rbx
0x18011c51d  push    rdi
0x18011c51e  sub     rsp, 50h
0x18011c522  mov     rax, cs:__security_cookie
0x18011c529  xor     rax, rsp
0x18011c52c  mov     [rsp+58h+var_10], rax
0x18011c531  mov     rdi, rdx
0x18011c534  mov     [rsp+58h+var_38], rdx
0x18011c539  lea     rcx, [rsp+58h+var_30]
0x18011c53e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18011c543  nop
0x18011c544  mov     rcx, rdi
0x18011c547  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011c54c  mov     rcx, rax; lpPathName
0x18011c54f  call    cs:__imp_RemoveDirectoryW
0x18011c555  test    eax, eax
0x18011c557  jnz     short loc_18011C5A6
0x18011c559  lea     rdx, aDeletecurrentd; "DeleteCurrentDirectory: Could not delet"...
0x18011c560  lea     rcx, [rsp+58h+var_30]
0x18011c565  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011c56a  mov     rdx, rdi
0x18011c56d  lea     rcx, [rsp+58h+var_30]
0x18011c572  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011c577  lea     rdx, aError_0; ". Error: "
0x18011c57e  lea     rcx, [rsp+58h+var_30]
0x18011c583  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011c588  call    cs:__imp_GetLastError
0x18011c58e  mov     ebx, eax
0x18011c590  lea     rcx, [rsp+58h+var_30]
0x18011c595  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011c59a  mov     rdx, rax; unsigned __int16 *
0x18011c59d  mov     r8d, ebx; int
0x18011c5a0  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x18011c5a5  nop
0x18011c5a6  lea     rcx, [rsp+58h+var_30]
0x18011c5ab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011c5b0  nop
0x18011c5b1  mov     rcx, rdi
0x18011c5b4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011c5b9  mov     rcx, [rsp+58h+var_10]
0x18011c5be  xor     rcx, rsp; StackCookie
0x18011c5c1  call    __security_check_cookie
0x18011c5c6  mov     rbx, [rsp+58h+arg_0]
0x18011c5cb  add     rsp, 50h
0x18011c5cf  pop     rdi
0x18011c5d0  retn
```
