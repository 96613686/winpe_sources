# FlattenOutputFolder::RenameFolder(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18011d188`
- end: `0x18011d2bb`
- name: `?RenameFolder@FlattenOutputFolder@@AEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18011ca44`

## callees

- `0x180019000`
- `0x1800e6664`
- `0x1800e66b8`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef8c8`
- `0x1800ef900`
- `0x180118a64`
- `0x18011d188`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d25a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d25a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18011d207`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18011d207`

## string_xrefs

- `0x18011d211`: `RenameFolder: Rename folder failed. Old Folder name: `

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FlattenOutputFolder::RenameFolder(__int64 a1, __int64 a2, __int64 a3)
{
  const WCHAR *v6; // rbx
  const WCHAR *v7; // rax
  DWORD LastError; // ebx
  const unsigned __int16 *v9; // rax
  TelemetryWriter *v10; // rcx
  _BYTE v12[32]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v13[32]; // [rsp+50h] [rbp-30h] BYREF

  std::wstring::wstring(v12);
  std::wstring::wstring(v13, a1 + 16);
  std::wstring::append(v13, L"\\");
  std::wstring::append(v13, a3);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
  if ( !MoveFileW(v6, v7) )
  {
    std::wstring::append(v12, L"RenameFolder: Rename folder failed. Old Folder name: ");
    std::wstring::append(v12, a2);
    std::wstring::append(v12, L", New Folder name: ");
    std::wstring::append(v12, v13);
    std::wstring::append(v12, L". Error: ");
    LastError = GetLastError();
    v9 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
    TelemetryWriter::Write(v10, v9, LastError);
  }
  std::wstring::_Tidy_deallocate(v13);
  std::wstring::_Tidy_deallocate(v12);
  std::wstring::_Tidy_deallocate(a2);
  return std::wstring::_Tidy_deallocate(a3);
}

```

## disassembly

```asm
0x18011d188  mov     [rsp-18h+arg_18], rbx
0x18011d18d  push    rbp
0x18011d18e  push    rsi
0x18011d18f  push    rdi
0x18011d190  mov     rbp, rsp
0x18011d193  sub     rsp, 80h
0x18011d19a  mov     rax, cs:__security_cookie
0x18011d1a1  xor     rax, rsp
0x18011d1a4  mov     [rbp+var_10], rax
0x18011d1a8  mov     rsi, r8
0x18011d1ab  mov     rdi, rdx
0x18011d1ae  mov     rbx, rcx
0x18011d1b1  mov     [rbp+var_60], rdx
0x18011d1b5  mov     [rbp+var_58], r8
0x18011d1b9  lea     rcx, [rbp+var_50]
0x18011d1bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18011d1c2  nop
0x18011d1c3  lea     rdx, [rbx+10h]
0x18011d1c7  lea     rcx, [rbp+var_30]
0x18011d1cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18011d1d0  nop
0x18011d1d1  lea     rdx, psz; "\\"
0x18011d1d8  lea     rcx, [rbp+var_30]
0x18011d1dc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011d1e1  mov     rdx, rsi
0x18011d1e4  lea     rcx, [rbp+var_30]
0x18011d1e8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011d1ed  mov     rcx, rdi
0x18011d1f0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011d1f5  mov     rbx, rax
0x18011d1f8  lea     rcx, [rbp+var_30]
0x18011d1fc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011d201  mov     rdx, rax; lpNewFileName
0x18011d204  mov     rcx, rbx; lpExistingFileName
0x18011d207  call    cs:__imp_MoveFileW
0x18011d20d  test    eax, eax
0x18011d20f  jnz     short loc_18011D277
0x18011d211  lea     rdx, aRenamefolderRe; "RenameFolder: Rename folder failed. Old"...
0x18011d218  lea     rcx, [rbp+var_50]
0x18011d21c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011d221  mov     rdx, rdi
0x18011d224  lea     rcx, [rbp+var_50]
0x18011d228  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011d22d  lea     rdx, aNewFolderName; ", New Folder name: "
0x18011d234  lea     rcx, [rbp+var_50]
0x18011d238  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011d23d  lea     rdx, [rbp+var_30]
0x18011d241  lea     rcx, [rbp+var_50]
0x18011d245  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011d24a  lea     rdx, aError_0; ". Error: "
0x18011d251  lea     rcx, [rbp+var_50]
0x18011d255  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011d25a  call    cs:__imp_GetLastError
0x18011d260  mov     ebx, eax
0x18011d262  lea     rcx, [rbp+var_50]
0x18011d266  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011d26b  mov     rdx, rax; unsigned __int16 *
0x18011d26e  mov     r8d, ebx; int
0x18011d271  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x18011d276  nop
0x18011d277  lea     rcx, [rbp+var_30]
0x18011d27b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011d280  nop
0x18011d281  lea     rcx, [rbp+var_50]
0x18011d285  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011d28a  nop
0x18011d28b  mov     rcx, rdi
0x18011d28e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011d293  nop
0x18011d294  mov     rcx, rsi
0x18011d297  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011d29c  mov     rcx, [rbp+var_10]
0x18011d2a0  xor     rcx, rsp; StackCookie
0x18011d2a3  call    __security_check_cookie
0x18011d2a8  mov     rbx, [rsp+80h+arg_18]
0x18011d2b0  add     rsp, 80h
0x18011d2b7  pop     rdi
0x18011d2b8  pop     rsi
0x18011d2b9  pop     rbp
0x18011d2ba  retn
```
