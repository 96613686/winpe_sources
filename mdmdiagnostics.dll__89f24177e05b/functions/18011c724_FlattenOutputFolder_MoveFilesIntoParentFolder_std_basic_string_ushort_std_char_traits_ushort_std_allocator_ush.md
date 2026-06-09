# FlattenOutputFolder::MoveFilesIntoParentFolder(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18011c724`
- end: `0x18011ca3b`
- name: `?MoveFilesIntoParentFolder@FlattenOutputFolder@@AEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `791`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x18011ca44`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800e6664`
- `0x1800e66b8`
- `0x1800ed730`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef8c8`
- `0x1800ef900`
- `0x18010438c`
- `0x1801189ec`
- `0x180118a64`
- `0x18011c518`
- `0x18011c724`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18011c906`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18011c906`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18011c7ab`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18011c7ab`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18011c9a0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18011c9a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c7ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c7ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c969`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18011c8e1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18011c8e1`

## string_xrefs

- `0x18011c7ba`: `MoveFilesIntoParentFolder: The folder cannot be processed. Output directory `
- `0x18011c919`: `MoveFilesIntoParentFolder: Move File failed: Old file: `
- `0x18011c9c2`: `MoveFilesIntoParentFolder: One or more files could not be moved to parent folder, keeping folder structure as is. Folder: `

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall FlattenOutputFolder::MoveFilesIntoParentFolder(__int64 a1, __int64 a2, __int64 a3)
{
  const WCHAR *v6; // rax
  const unsigned __int16 *v7; // rdx
  HANDLE FirstFileW; // r14
  DWORD LastError; // ebx
  const unsigned __int16 *v10; // rax
  TelemetryWriter *v11; // rcx
  char v12; // r15
  __int64 v13; // rax
  const WCHAR *v14; // rbx
  const WCHAR *v15; // rax
  DWORD v16; // ebx
  const unsigned __int16 *v17; // rax
  TelemetryWriter *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  const unsigned __int16 *v21; // rax
  TelemetryWriter *v22; // rcx
  _BYTE v24[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v25[32]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v26[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v27[40]; // [rsp+A8h] [rbp-58h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v29[264]; // [rsp+320h] [rbp+220h] BYREF

  std::wstring::wstring(v24);
  std::wstring::wstring(v27, a2);
  std::wstring::append(v27, L"\\*");
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
  FirstFileW = FindFirstFileW(v6, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    std::wstring::append(v24, L"MoveFilesIntoParentFolder: The folder cannot be processed. Output directory ");
    std::wstring::append(v24, v27);
    std::wstring::append(v24, L" not found:");
    LastError = GetLastError();
    v10 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
    TelemetryWriter::Write(v11, v10, LastError);
    goto LABEL_14;
  }
  v12 = 1;
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 || wil::path_is_dot_or_dotdot((wil *)FindFileData.cFileName, v7) )
      goto LABEL_8;
    std::wstring::wstring(v25, a2);
    std::wstring::append(v25, L"\\");
    std::wstring::append(v25, FindFileData.cFileName);
    memset_0(v29, 0, 0x208u);
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
    StringCchPrintfW(v29, 0x104u, L"%s %s", v13, FindFileData.cFileName);
    std::wstring::wstring(v26, a1 + 16);
    std::wstring::append(v26, L"\\");
    std::wstring::append(v26, v29);
    v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
    v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
    if ( !MoveFileW(v15, v14) )
      break;
    std::wstring::_Tidy_deallocate(v26);
    std::wstring::_Tidy_deallocate(v25);
LABEL_8:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_11;
  }
  std::wstring::append(v24, L"MoveFilesIntoParentFolder: Move File failed: Old file: ");
  std::wstring::append(v24, v25);
  std::wstring::append(v24, L", New file: ");
  std::wstring::append(v24, v26);
  std::wstring::append(v24, L". Error: ");
  v16 = GetLastError();
  v17 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
  TelemetryWriter::Write(v18, v17, v16);
  v12 = 0;
  std::wstring::_Tidy_deallocate(v26);
  std::wstring::_Tidy_deallocate(v25);
LABEL_11:
  FindClose(FirstFileW);
  if ( v12 )
  {
    v19 = std::wstring::wstring(v25, a2);
    FlattenOutputFolder::DeleteCurrentDirectory(v20, v19);
  }
  else
  {
    std::wstring::append(
      v24,
      L"MoveFilesIntoParentFolder: One or more files could not be moved to parent folder, keeping folder structure as is. Folder: ");
    std::wstring::append(v24, v27);
    v21 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
    TelemetryWriter::Write(v22, v21);
  }
LABEL_14:
  std::wstring::_Tidy_deallocate(v27);
  std::wstring::_Tidy_deallocate(v24);
  std::wstring::_Tidy_deallocate(a2);
  return std::wstring::_Tidy_deallocate(a3);
}

```

## disassembly

```asm
0x18011c724  push    rbp
0x18011c726  push    rbx
0x18011c727  push    rsi
0x18011c728  push    rdi
0x18011c729  push    r13
0x18011c72b  push    r14
0x18011c72d  push    r15
0x18011c72f  lea     rbp, [rsp-440h]
0x18011c737  sub     rsp, 540h
0x18011c73e  mov     rax, cs:__security_cookie
0x18011c745  xor     rax, rsp
0x18011c748  mov     [rbp+470h+var_40], rax
0x18011c74f  mov     rsi, r8
0x18011c752  mov     rdi, rdx
0x18011c755  mov     r13, rcx
0x18011c758  mov     [rsp+570h+var_538], rdx
0x18011c75d  mov     [rsp+570h+var_530], r8
0x18011c762  lea     rcx, [rsp+570h+var_528]
0x18011c767  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18011c76c  nop
0x18011c76d  mov     rdx, rdi
0x18011c770  lea     rcx, [rbp+470h+var_4C8]
0x18011c774  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18011c779  nop
0x18011c77a  lea     rdx, asc_1801D3550; "\\*"
0x18011c781  lea     rcx, [rbp+470h+var_4C8]
0x18011c785  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011c78a  xor     edx, edx; Val
0x18011c78c  mov     r8d, 250h; Size
0x18011c792  lea     rcx, [rbp+470h+FindFileData]; void *
0x18011c796  call    memset_0
0x18011c79b  lea     rcx, [rbp+470h+var_4C8]
0x18011c79f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011c7a4  mov     rcx, rax; lpFileName
0x18011c7a7  lea     rdx, [rbp+470h+FindFileData]; lpFindFileData
0x18011c7ab  call    cs:__imp_FindFirstFileW
0x18011c7b1  mov     r14, rax
0x18011c7b4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18011c7b8  jnz     short loc_18011C80C
0x18011c7ba  lea     rdx, aMovefilesintop; "MoveFilesIntoParentFolder: The folder c"...
0x18011c7c1  lea     rcx, [rsp+570h+var_528]
0x18011c7c6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011c7cb  lea     rdx, [rbp+470h+var_4C8]
0x18011c7cf  lea     rcx, [rsp+570h+var_528]
0x18011c7d4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011c7d9  lea     rdx, aNotFound_0; " not found:"
0x18011c7e0  lea     rcx, [rsp+570h+var_528]
0x18011c7e5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011c7ea  call    cs:__imp_GetLastError
0x18011c7f0  mov     ebx, eax
0x18011c7f2  lea     rcx, [rsp+570h+var_528]
0x18011c7f7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011c7fc  mov     rdx, rax; unsigned __int16 *
0x18011c7ff  mov     r8d, ebx; int
0x18011c802  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x18011c807  jmp     loc_18011C9F4
0x18011c80c  mov     r15b, 1
0x18011c80f  test    byte ptr [rbp+470h+FindFileData.dwFileAttributes], 10h
0x18011c813  jnz     loc_18011C8FF
0x18011c819  lea     rcx, [rbp+470h+FindFileData.cFileName]; this
0x18011c81d  call    ?path_is_dot_or_dotdot@wil@@YA_NPEBG@Z; wil::path_is_dot_or_dotdot(ushort const *)
0x18011c822  test    al, al
0x18011c824  jnz     loc_18011C8FF
0x18011c82a  mov     rdx, rdi
0x18011c82d  lea     rcx, [rsp+570h+var_508]
0x18011c832  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18011c837  nop
0x18011c838  lea     rdx, psz; "\\"
0x18011c83f  lea     rcx, [rsp+570h+var_508]
0x18011c844  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011c849  lea     rdx, [rbp+470h+FindFileData.cFileName]
0x18011c84d  lea     rcx, [rsp+570h+var_508]
0x18011c852  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011c857  xor     edx, edx; Val
0x18011c859  mov     r8d, 208h; Size
0x18011c85f  lea     rcx, [rbp+470h+var_250]; void *
0x18011c866  call    memset_0
0x18011c86b  mov     rcx, rsi
0x18011c86e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011c873  lea     rcx, [rbp+470h+FindFileData.cFileName]
0x18011c877  mov     [rsp+570h+var_550], rcx
0x18011c87c  mov     r9, rax
0x18011c87f  lea     r8, aSS; "%s %s"
0x18011c886  mov     edx, 104h; unsigned __int64
0x18011c88b  lea     rcx, [rbp+470h+var_250]; unsigned __int16 *
0x18011c892  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18011c897  lea     rdx, [r13+10h]
0x18011c89b  lea     rcx, [rbp+470h+var_4E8]
0x18011c89f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18011c8a4  nop
0x18011c8a5  lea     rdx, psz; "\\"
0x18011c8ac  lea     rcx, [rbp+470h+var_4E8]
0x18011c8b0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011c8b5  lea     rdx, [rbp+470h+var_250]
0x18011c8bc  lea     rcx, [rbp+470h+var_4E8]
0x18011c8c0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011c8c5  lea     rcx, [rbp+470h+var_4E8]
0x18011c8c9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011c8ce  mov     rbx, rax
0x18011c8d1  lea     rcx, [rsp+570h+var_508]
0x18011c8d6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011c8db  mov     rcx, rax; lpExistingFileName
0x18011c8de  mov     rdx, rbx; lpNewFileName
0x18011c8e1  call    cs:__imp_MoveFileW
0x18011c8e7  test    eax, eax
0x18011c8e9  jz      short loc_18011C919
0x18011c8eb  lea     rcx, [rbp+470h+var_4E8]
0x18011c8ef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011c8f4  nop
0x18011c8f5  lea     rcx, [rsp+570h+var_508]
0x18011c8fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011c8ff  lea     rdx, [rbp+470h+FindFileData]; lpFindFileData
0x18011c903  mov     rcx, r14; hFindFile
0x18011c906  call    cs:__imp_FindNextFileW
0x18011c90c  test    eax, eax
0x18011c90e  jnz     loc_18011C80F
0x18011c914  jmp     loc_18011C99D
0x18011c919  lea     rdx, aMovefilesintop_1; "MoveFilesIntoParentFolder: Move File fa"...
0x18011c920  lea     rcx, [rsp+570h+var_528]
0x18011c925  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011c92a  lea     rdx, [rsp+570h+var_508]
0x18011c92f  lea     rcx, [rsp+570h+var_528]
0x18011c934  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011c939  lea     rdx, aNewFile; ", New file: "
0x18011c940  lea     rcx, [rsp+570h+var_528]
0x18011c945  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011c94a  lea     rdx, [rbp+470h+var_4E8]
0x18011c94e  lea     rcx, [rsp+570h+var_528]
0x18011c953  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011c958  lea     rdx, aError_0; ". Error: "
0x18011c95f  lea     rcx, [rsp+570h+var_528]
0x18011c964  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011c969  call    cs:__imp_GetLastError
0x18011c96f  mov     ebx, eax
0x18011c971  lea     rcx, [rsp+570h+var_528]
0x18011c976  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011c97b  mov     rdx, rax; unsigned __int16 *
0x18011c97e  mov     r8d, ebx; int
0x18011c981  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x18011c986  xor     r15b, r15b
0x18011c989  lea     rcx, [rbp+470h+var_4E8]
0x18011c98d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011c992  nop
0x18011c993  lea     rcx, [rsp+570h+var_508]
0x18011c998  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011c99d  mov     rcx, r14; hFindFile
0x18011c9a0  call    cs:__imp_FindClose
0x18011c9a6  test    r15b, r15b
0x18011c9a9  jz      short loc_18011C9C2
0x18011c9ab  mov     rdx, rdi
0x18011c9ae  lea     rcx, [rsp+570h+var_508]
0x18011c9b3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18011c9b8  mov     rdx, rax
0x18011c9bb  call    ?DeleteCurrentDirectory@FlattenOutputFolder@@AEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FlattenOutputFolder::DeleteCurrentDirectory(std::wstring)
0x18011c9c0  jmp     short loc_18011C9F4
0x18011c9c2  lea     rdx, aMovefilesintop_0; "MoveFilesIntoParentFolder: One or more "...
0x18011c9c9  lea     rcx, [rsp+570h+var_528]
0x18011c9ce  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011c9d3  lea     rdx, [rbp+470h+var_4C8]
0x18011c9d7  lea     rcx, [rsp+570h+var_528]
0x18011c9dc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011c9e1  lea     rcx, [rsp+570h+var_528]
0x18011c9e6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011c9eb  mov     rdx, rax; unsigned __int16 *
0x18011c9ee  call    ?Write@TelemetryWriter@@QEAAXPEBG@Z; TelemetryWriter::Write(ushort const *)
0x18011c9f3  nop
0x18011c9f4  lea     rcx, [rbp+470h+var_4C8]
0x18011c9f8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011c9fd  nop
0x18011c9fe  lea     rcx, [rsp+570h+var_528]
0x18011ca03  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011ca08  nop
0x18011ca09  mov     rcx, rdi
0x18011ca0c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011ca11  nop
0x18011ca12  mov     rcx, rsi
0x18011ca15  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011ca1a  mov     rcx, [rbp+470h+var_40]
0x18011ca21  xor     rcx, rsp; StackCookie
0x18011ca24  call    __security_check_cookie
0x18011ca29  add     rsp, 540h
0x18011ca30  pop     r15
0x18011ca32  pop     r14
0x18011ca34  pop     r13
0x18011ca36  pop     rdi
0x18011ca37  pop     rsi
0x18011ca38  pop     rbx
0x18011ca39  pop     rbp
0x18011ca3a  retn
```
