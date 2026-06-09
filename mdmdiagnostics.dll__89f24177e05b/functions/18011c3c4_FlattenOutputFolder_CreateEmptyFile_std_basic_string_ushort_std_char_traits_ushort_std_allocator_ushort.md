# FlattenOutputFolder::CreateEmptyFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18011c3c4`
- end: `0x18011c50f`
- name: `?CreateEmptyFile@FlattenOutputFolder@@AEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `331`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

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
- `0x18011c3c4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18011c471`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18011c471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c4aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c4aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011c4cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011c4cb`

## string_xrefs

- `0x18011c47d`: `CreateEmptyFile: Could not create empty file: `

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FlattenOutputFolder::CreateEmptyFile(__int64 a1, __int64 a2)
{
  const WCHAR *v4; // rax
  HANDLE v5; // rax
  DWORD LastError; // ebx
  const unsigned __int16 *v7; // rax
  TelemetryWriter *v8; // rcx
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-19h] BYREF
  __int64 v11; // [rsp+58h] [rbp-1h]
  _BYTE v12[32]; // [rsp+60h] [rbp+7h] BYREF
  _BYTE v13[32]; // [rsp+80h] [rbp+27h] BYREF

  v11 = a2;
  std::wstring::wstring(v13);
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 1;
  SecurityAttributes.lpSecurityDescriptor = 0;
  std::wstring::wstring(v12, a1 + 16);
  std::wstring::append(v12, L"\\");
  std::wstring::append(v12, a2);
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
  v5 = CreateFileW(v4, 4u, 3u, &SecurityAttributes, 2u, 0x80u, 0);
  if ( v5 == (HANDLE)-1LL )
  {
    std::wstring::append(v13, L"CreateEmptyFile: Could not create empty file: ");
    std::wstring::append(v13, v12);
    std::wstring::append(v13, L". Error: ");
    LastError = GetLastError();
    v7 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
    TelemetryWriter::Write(v8, v7, LastError);
  }
  else
  {
    CloseHandle(v5);
  }
  std::wstring::_Tidy_deallocate(v12);
  std::wstring::_Tidy_deallocate(v13);
  return std::wstring::_Tidy_deallocate(a2);
}

```

## disassembly

```asm
0x18011c3c4  mov     [rsp-8+arg_10], rbx
0x18011c3c9  mov     [rsp-8+arg_18], rdi
0x18011c3ce  push    rbp
0x18011c3cf  lea     rbp, [rsp-57h]
0x18011c3d4  sub     rsp, 0B0h
0x18011c3db  mov     rax, cs:__security_cookie
0x18011c3e2  xor     rax, rsp
0x18011c3e5  mov     [rbp+57h+var_10], rax
0x18011c3e9  mov     rdi, rdx
0x18011c3ec  mov     rbx, rcx
0x18011c3ef  mov     [rbp+57h+var_58], rdx
0x18011c3f3  lea     rcx, [rbp+57h+var_30]
0x18011c3f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18011c3fc  nop
0x18011c3fd  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x18011c405  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], 1
0x18011c40d  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], 0
0x18011c415  lea     rdx, [rbx+10h]
0x18011c419  lea     rcx, [rbp+57h+var_50]
0x18011c41d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18011c422  nop
0x18011c423  lea     rdx, psz; "\\"
0x18011c42a  lea     rcx, [rbp+57h+var_50]
0x18011c42e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011c433  mov     rdx, rdi
0x18011c436  lea     rcx, [rbp+57h+var_50]
0x18011c43a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011c43f  lea     rcx, [rbp+57h+var_50]
0x18011c443  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011c448  mov     rcx, rax; lpFileName
0x18011c44b  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x18011c454  mov     [rsp+0B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18011c45c  mov     [rsp+0B0h+dwCreationDisposition], 2; dwCreationDisposition
0x18011c464  lea     r9, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18011c468  mov     edx, 4; dwDesiredAccess
0x18011c46d  lea     r8d, [rdx-1]; dwShareMode
0x18011c471  call    cs:__imp_CreateFileW
0x18011c477  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18011c47b  jnz     short loc_18011C4C8
0x18011c47d  lea     rdx, aCreateemptyfil; "CreateEmptyFile: Could not create empty"...
0x18011c484  lea     rcx, [rbp+57h+var_30]
0x18011c488  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011c48d  lea     rdx, [rbp+57h+var_50]
0x18011c491  lea     rcx, [rbp+57h+var_30]
0x18011c495  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011c49a  lea     rdx, aError_0; ". Error: "
0x18011c4a1  lea     rcx, [rbp+57h+var_30]
0x18011c4a5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011c4aa  call    cs:__imp_GetLastError
0x18011c4b0  mov     ebx, eax
0x18011c4b2  lea     rcx, [rbp+57h+var_30]
0x18011c4b6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011c4bb  mov     rdx, rax; unsigned __int16 *
0x18011c4be  mov     r8d, ebx; int
0x18011c4c1  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x18011c4c6  jmp     short loc_18011C4D2
0x18011c4c8  mov     rcx, rax; hObject
0x18011c4cb  call    cs:__imp_CloseHandle
0x18011c4d1  nop
0x18011c4d2  lea     rcx, [rbp+57h+var_50]
0x18011c4d6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011c4db  nop
0x18011c4dc  lea     rcx, [rbp+57h+var_30]
0x18011c4e0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011c4e5  nop
0x18011c4e6  mov     rcx, rdi
0x18011c4e9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011c4ee  mov     rcx, [rbp+57h+var_10]
0x18011c4f2  xor     rcx, rsp; StackCookie
0x18011c4f5  call    __security_check_cookie
0x18011c4fa  lea     r11, [rsp+0B0h+var_s0]
0x18011c502  mov     rbx, [r11+20h]
0x18011c506  mov     rdi, [r11+28h]
0x18011c50a  mov     rsp, r11
0x18011c50d  pop     rbp
0x18011c50e  retn
```
