# FlattenOutputFolder::DeleteCurrentDirectory(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18011ddc8`
- end: `0x18011de8e`
- name: `?DeleteCurrentDirectory@FlattenOutputFolder@@AEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `198`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18011dffc`
- `0x18011e340`

## callees

- `0x180019080`
- `0x1800e688c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00ac`
- `0x1800f00e4`
- `0x18011a270`
- `0x18011ddc8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18011ddff`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18011ddff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011de3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011de3e`

## string_xrefs

- `0x18011de0f`: `DeleteCurrentDirectory: Could not delete directory: `

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
0x18011ddc8  mov     [rsp+arg_0], rbx
0x18011ddcd  push    rdi
0x18011ddce  sub     rsp, 50h
0x18011ddd2  mov     rax, cs:__security_cookie
0x18011ddd9  xor     rax, rsp
0x18011dddc  mov     [rsp+58h+var_10], rax
0x18011dde1  mov     rdi, rdx
0x18011dde4  mov     [rsp+58h+var_38], rdx
0x18011dde9  lea     rcx, [rsp+58h+var_30]
0x18011ddee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18011ddf3  nop
0x18011ddf4  mov     rcx, rdi
0x18011ddf7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011ddfc  mov     rcx, rax; lpPathName
0x18011ddff  call    cs:__imp_RemoveDirectoryW
0x18011de06  nop     dword ptr [rax+rax+00h]
0x18011de0b  test    eax, eax
0x18011de0d  jnz     short loc_18011DE62
0x18011de0f  lea     rdx, aDeletecurrentd; "DeleteCurrentDirectory: Could not delet"...
0x18011de16  lea     rcx, [rsp+58h+var_30]
0x18011de1b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011de20  mov     rdx, rdi
0x18011de23  lea     rcx, [rsp+58h+var_30]
0x18011de28  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011de2d  lea     rdx, aError_0; ". Error: "
0x18011de34  lea     rcx, [rsp+58h+var_30]
0x18011de39  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011de3e  call    cs:__imp_GetLastError
0x18011de45  nop     dword ptr [rax+rax+00h]
0x18011de4a  mov     ebx, eax
0x18011de4c  lea     rcx, [rsp+58h+var_30]
0x18011de51  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011de56  mov     rdx, rax; unsigned __int16 *
0x18011de59  mov     r8d, ebx; int
0x18011de5c  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x18011de61  nop
0x18011de62  lea     rcx, [rsp+58h+var_30]
0x18011de67  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011de6c  nop
0x18011de6d  mov     rcx, rdi
0x18011de70  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011de75  mov     rcx, [rsp+58h+var_10]
0x18011de7a  xor     rcx, rsp; StackCookie
0x18011de7d  call    __security_check_cookie
0x18011de82  mov     rbx, [rsp+58h+arg_0]
0x18011de87  add     rsp, 50h
0x18011de8b  pop     rdi
0x18011de8c  retn
```
