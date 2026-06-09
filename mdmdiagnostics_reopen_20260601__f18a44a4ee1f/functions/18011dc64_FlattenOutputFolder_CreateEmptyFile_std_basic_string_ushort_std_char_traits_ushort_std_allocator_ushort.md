# FlattenOutputFolder::CreateEmptyFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18011dc64`
- end: `0x18011ddc2`
- name: `?CreateEmptyFile@FlattenOutputFolder@@AEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

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
- `0x18011dc64`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18011dd11`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18011dd11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011dd50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011dd50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011dd77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011dd77`

## string_xrefs

- `0x18011dd23`: `CreateEmptyFile: Could not create empty file: `

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
0x18011dc64  mov     [rsp-8+arg_10], rbx
0x18011dc69  mov     [rsp-8+arg_18], rdi
0x18011dc6e  push    rbp
0x18011dc6f  lea     rbp, [rsp-57h]
0x18011dc74  sub     rsp, 0B0h
0x18011dc7b  mov     rax, cs:__security_cookie
0x18011dc82  xor     rax, rsp
0x18011dc85  mov     [rbp+57h+var_10], rax
0x18011dc89  mov     rdi, rdx
0x18011dc8c  mov     rbx, rcx
0x18011dc8f  mov     [rbp+57h+var_58], rdx
0x18011dc93  lea     rcx, [rbp+57h+var_30]
0x18011dc97  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18011dc9c  nop
0x18011dc9d  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x18011dca5  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], 1
0x18011dcad  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], 0
0x18011dcb5  lea     rdx, [rbx+10h]
0x18011dcb9  lea     rcx, [rbp+57h+var_50]
0x18011dcbd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18011dcc2  nop
0x18011dcc3  lea     rdx, psz; "\\"
0x18011dcca  lea     rcx, [rbp+57h+var_50]
0x18011dcce  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011dcd3  mov     rdx, rdi
0x18011dcd6  lea     rcx, [rbp+57h+var_50]
0x18011dcda  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011dcdf  lea     rcx, [rbp+57h+var_50]
0x18011dce3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011dce8  mov     rcx, rax; lpFileName
0x18011dceb  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x18011dcf4  mov     [rsp+0B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18011dcfc  mov     [rsp+0B0h+dwCreationDisposition], 2; dwCreationDisposition
0x18011dd04  lea     r9, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18011dd08  mov     edx, 4; dwDesiredAccess
0x18011dd0d  lea     r8d, [rdx-1]; dwShareMode
0x18011dd11  call    cs:__imp_CreateFileW
0x18011dd18  nop     dword ptr [rax+rax+00h]
0x18011dd1d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18011dd21  jnz     short loc_18011DD74
0x18011dd23  lea     rdx, aCreateemptyfil; "CreateEmptyFile: Could not create empty"...
0x18011dd2a  lea     rcx, [rbp+57h+var_30]
0x18011dd2e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011dd33  lea     rdx, [rbp+57h+var_50]
0x18011dd37  lea     rcx, [rbp+57h+var_30]
0x18011dd3b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011dd40  lea     rdx, aError_0; ". Error: "
0x18011dd47  lea     rcx, [rbp+57h+var_30]
0x18011dd4b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011dd50  call    cs:__imp_GetLastError
0x18011dd57  nop     dword ptr [rax+rax+00h]
0x18011dd5c  mov     ebx, eax
0x18011dd5e  lea     rcx, [rbp+57h+var_30]
0x18011dd62  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011dd67  mov     rdx, rax; unsigned __int16 *
0x18011dd6a  mov     r8d, ebx; int
0x18011dd6d  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x18011dd72  jmp     short loc_18011DD84
0x18011dd74  mov     rcx, rax; hObject
0x18011dd77  call    cs:__imp_CloseHandle
0x18011dd7e  nop     dword ptr [rax+rax+00h]
0x18011dd83  nop
0x18011dd84  lea     rcx, [rbp+57h+var_50]
0x18011dd88  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011dd8d  nop
0x18011dd8e  lea     rcx, [rbp+57h+var_30]
0x18011dd92  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011dd97  nop
0x18011dd98  mov     rcx, rdi
0x18011dd9b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011dda0  mov     rcx, [rbp+57h+var_10]
0x18011dda4  xor     rcx, rsp; StackCookie
0x18011dda7  call    __security_check_cookie
0x18011ddac  lea     r11, [rsp+0B0h+var_s0]
0x18011ddb4  mov     rbx, [r11+20h]
0x18011ddb8  mov     rdi, [r11+28h]
0x18011ddbc  mov     rsp, r11
0x18011ddbf  pop     rbp
0x18011ddc0  retn
```
