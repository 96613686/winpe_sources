# FlattenOutputFolder::RenameFolder(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18011eab0`
- end: `0x18011ebf0`
- name: `?RenameFolder@FlattenOutputFolder@@AEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18011e340`

## callees

- `0x180019080`
- `0x1800e6838`
- `0x1800e688c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00ac`
- `0x1800f00e4`
- `0x18011a270`
- `0x18011eab0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011eb88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011eb88`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18011eb2f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18011eb2f`

## string_xrefs

- `0x18011eb3f`: `RenameFolder: Rename folder failed. Old Folder name: `

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
0x18011eab0  mov     [rsp-18h+arg_18], rbx
0x18011eab5  push    rbp
0x18011eab6  push    rsi
0x18011eab7  push    rdi
0x18011eab8  mov     rbp, rsp
0x18011eabb  sub     rsp, 80h
0x18011eac2  mov     rax, cs:__security_cookie
0x18011eac9  xor     rax, rsp
0x18011eacc  mov     [rbp+var_10], rax
0x18011ead0  mov     rsi, r8
0x18011ead3  mov     rdi, rdx
0x18011ead6  mov     rbx, rcx
0x18011ead9  mov     [rbp+var_60], rdx
0x18011eadd  mov     [rbp+var_58], r8
0x18011eae1  lea     rcx, [rbp+var_50]
0x18011eae5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18011eaea  nop
0x18011eaeb  lea     rdx, [rbx+10h]
0x18011eaef  lea     rcx, [rbp+var_30]
0x18011eaf3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18011eaf8  nop
0x18011eaf9  lea     rdx, psz; "\\"
0x18011eb00  lea     rcx, [rbp+var_30]
0x18011eb04  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011eb09  mov     rdx, rsi
0x18011eb0c  lea     rcx, [rbp+var_30]
0x18011eb10  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011eb15  mov     rcx, rdi
0x18011eb18  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011eb1d  mov     rbx, rax
0x18011eb20  lea     rcx, [rbp+var_30]
0x18011eb24  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011eb29  mov     rdx, rax; lpNewFileName
0x18011eb2c  mov     rcx, rbx; lpExistingFileName
0x18011eb2f  call    cs:__imp_MoveFileW
0x18011eb36  nop     dword ptr [rax+rax+00h]
0x18011eb3b  test    eax, eax
0x18011eb3d  jnz     short loc_18011EBAB
0x18011eb3f  lea     rdx, aRenamefolderRe; "RenameFolder: Rename folder failed. Old"...
0x18011eb46  lea     rcx, [rbp+var_50]
0x18011eb4a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011eb4f  mov     rdx, rdi
0x18011eb52  lea     rcx, [rbp+var_50]
0x18011eb56  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011eb5b  lea     rdx, aNewFolderName; ", New Folder name: "
0x18011eb62  lea     rcx, [rbp+var_50]
0x18011eb66  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011eb6b  lea     rdx, [rbp+var_30]
0x18011eb6f  lea     rcx, [rbp+var_50]
0x18011eb73  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011eb78  lea     rdx, aError_0; ". Error: "
0x18011eb7f  lea     rcx, [rbp+var_50]
0x18011eb83  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011eb88  call    cs:__imp_GetLastError
0x18011eb8f  nop     dword ptr [rax+rax+00h]
0x18011eb94  mov     ebx, eax
0x18011eb96  lea     rcx, [rbp+var_50]
0x18011eb9a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011eb9f  mov     rdx, rax; unsigned __int16 *
0x18011eba2  mov     r8d, ebx; int
0x18011eba5  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x18011ebaa  nop
0x18011ebab  lea     rcx, [rbp+var_30]
0x18011ebaf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011ebb4  nop
0x18011ebb5  lea     rcx, [rbp+var_50]
0x18011ebb9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011ebbe  nop
0x18011ebbf  mov     rcx, rdi
0x18011ebc2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011ebc7  nop
0x18011ebc8  mov     rcx, rsi
0x18011ebcb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011ebd0  mov     rcx, [rbp+var_10]
0x18011ebd4  xor     rcx, rsp; StackCookie
0x18011ebd7  call    __security_check_cookie
0x18011ebdc  mov     rbx, [rsp+80h+arg_18]
0x18011ebe4  add     rsp, 80h
0x18011ebeb  pop     rdi
0x18011ebec  pop     rsi
0x18011ebed  pop     rbp
0x18011ebee  retn
```
