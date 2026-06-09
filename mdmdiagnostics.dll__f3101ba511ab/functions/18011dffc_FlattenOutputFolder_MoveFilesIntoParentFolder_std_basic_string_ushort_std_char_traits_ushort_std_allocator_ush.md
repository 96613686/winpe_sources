# FlattenOutputFolder::MoveFilesIntoParentFolder(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18011dffc`
- end: `0x18011e338`
- name: `?MoveFilesIntoParentFolder@FlattenOutputFolder@@AEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `828`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x18011e340`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800e6838`
- `0x1800e688c`
- `0x1800edd78`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00ac`
- `0x1800f00e4`
- `0x1801055a4`
- `0x18011a1f4`
- `0x18011a270`
- `0x18011ddc8`
- `0x18011dffc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18011e1f0`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18011e1f0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18011e083`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18011e083`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18011e296`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18011e296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011e0c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011e259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011e0c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011e259`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18011e1c5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18011e1c5`

## string_xrefs

- `0x18011e098`: `MoveFilesIntoParentFolder: The folder cannot be processed. Output directory `
- `0x18011e209`: `MoveFilesIntoParentFolder: Move File failed: Old file: `
- `0x18011e2be`: `MoveFilesIntoParentFolder: One or more files could not be moved to parent folder, keeping folder structure as is. Folder: `

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x18011dffc  push    rbp
0x18011dffe  push    rbx
0x18011dfff  push    rsi
0x18011e000  push    rdi
0x18011e001  push    r13
0x18011e003  push    r14
0x18011e005  push    r15
0x18011e007  lea     rbp, [rsp-440h]
0x18011e00f  sub     rsp, 540h
0x18011e016  mov     rax, cs:__security_cookie
0x18011e01d  xor     rax, rsp
0x18011e020  mov     [rbp+470h+var_40], rax
0x18011e027  mov     rsi, r8
0x18011e02a  mov     rdi, rdx
0x18011e02d  mov     r13, rcx
0x18011e030  mov     [rsp+570h+var_538], rdx
0x18011e035  mov     [rsp+570h+var_530], r8
0x18011e03a  lea     rcx, [rsp+570h+var_528]
0x18011e03f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18011e044  nop
0x18011e045  mov     rdx, rdi
0x18011e048  lea     rcx, [rbp+470h+var_4C8]
0x18011e04c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18011e051  nop
0x18011e052  lea     rdx, asc_1801D5540; "\\*"
0x18011e059  lea     rcx, [rbp+470h+var_4C8]
0x18011e05d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011e062  xor     edx, edx; Val
0x18011e064  mov     r8d, 250h; Size
0x18011e06a  lea     rcx, [rbp+470h+FindFileData]; void *
0x18011e06e  call    memset_0
0x18011e073  lea     rcx, [rbp+470h+var_4C8]
0x18011e077  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011e07c  mov     rcx, rax; lpFileName
0x18011e07f  lea     rdx, [rbp+470h+FindFileData]; lpFindFileData
0x18011e083  call    cs:__imp_FindFirstFileW
0x18011e08a  nop     dword ptr [rax+rax+00h]
0x18011e08f  mov     r14, rax
0x18011e092  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18011e096  jnz     short loc_18011E0F0
0x18011e098  lea     rdx, aMovefilesintop; "MoveFilesIntoParentFolder: The folder c"...
0x18011e09f  lea     rcx, [rsp+570h+var_528]
0x18011e0a4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011e0a9  lea     rdx, [rbp+470h+var_4C8]
0x18011e0ad  lea     rcx, [rsp+570h+var_528]
0x18011e0b2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011e0b7  lea     rdx, aNotFound_0; " not found:"
0x18011e0be  lea     rcx, [rsp+570h+var_528]
0x18011e0c3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011e0c8  call    cs:__imp_GetLastError
0x18011e0cf  nop     dword ptr [rax+rax+00h]
0x18011e0d4  mov     ebx, eax
0x18011e0d6  lea     rcx, [rsp+570h+var_528]
0x18011e0db  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011e0e0  mov     rdx, rax; unsigned __int16 *
0x18011e0e3  mov     r8d, ebx; int
0x18011e0e6  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x18011e0eb  jmp     loc_18011E2F0
0x18011e0f0  mov     r15b, 1
0x18011e0f3  test    byte ptr [rbp+470h+FindFileData.dwFileAttributes], 10h
0x18011e0f7  jnz     loc_18011E1E9
0x18011e0fd  lea     rcx, [rbp+470h+FindFileData.cFileName]; this
0x18011e101  call    ?path_is_dot_or_dotdot@wil@@YA_NPEBG@Z; wil::path_is_dot_or_dotdot(ushort const *)
0x18011e106  test    al, al
0x18011e108  jnz     loc_18011E1E9
0x18011e10e  mov     rdx, rdi
0x18011e111  lea     rcx, [rsp+570h+var_508]
0x18011e116  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18011e11b  nop
0x18011e11c  lea     rdx, psz; "\\"
0x18011e123  lea     rcx, [rsp+570h+var_508]
0x18011e128  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011e12d  lea     rdx, [rbp+470h+FindFileData.cFileName]
0x18011e131  lea     rcx, [rsp+570h+var_508]
0x18011e136  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011e13b  xor     edx, edx; Val
0x18011e13d  mov     r8d, 208h; Size
0x18011e143  lea     rcx, [rbp+470h+var_250]; void *
0x18011e14a  call    memset_0
0x18011e14f  mov     rcx, rsi
0x18011e152  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011e157  lea     rcx, [rbp+470h+FindFileData.cFileName]
0x18011e15b  mov     [rsp+570h+var_550], rcx
0x18011e160  mov     r9, rax
0x18011e163  lea     r8, aSS; "%s %s"
0x18011e16a  mov     edx, 104h; unsigned __int64
0x18011e16f  lea     rcx, [rbp+470h+var_250]; unsigned __int16 *
0x18011e176  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18011e17b  lea     rdx, [r13+10h]
0x18011e17f  lea     rcx, [rbp+470h+var_4E8]
0x18011e183  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18011e188  nop
0x18011e189  lea     rdx, psz; "\\"
0x18011e190  lea     rcx, [rbp+470h+var_4E8]
0x18011e194  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011e199  lea     rdx, [rbp+470h+var_250]
0x18011e1a0  lea     rcx, [rbp+470h+var_4E8]
0x18011e1a4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011e1a9  lea     rcx, [rbp+470h+var_4E8]
0x18011e1ad  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011e1b2  mov     rbx, rax
0x18011e1b5  lea     rcx, [rsp+570h+var_508]
0x18011e1ba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011e1bf  mov     rcx, rax; lpExistingFileName
0x18011e1c2  mov     rdx, rbx; lpNewFileName
0x18011e1c5  call    cs:__imp_MoveFileW
0x18011e1cc  nop     dword ptr [rax+rax+00h]
0x18011e1d1  test    eax, eax
0x18011e1d3  jz      short loc_18011E209
0x18011e1d5  lea     rcx, [rbp+470h+var_4E8]
0x18011e1d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011e1de  nop
0x18011e1df  lea     rcx, [rsp+570h+var_508]
0x18011e1e4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011e1e9  lea     rdx, [rbp+470h+FindFileData]; lpFindFileData
0x18011e1ed  mov     rcx, r14; hFindFile
0x18011e1f0  call    cs:__imp_FindNextFileW
0x18011e1f7  nop     dword ptr [rax+rax+00h]
0x18011e1fc  test    eax, eax
0x18011e1fe  jnz     loc_18011E0F3
0x18011e204  jmp     loc_18011E293
0x18011e209  lea     rdx, aMovefilesintop_1; "MoveFilesIntoParentFolder: Move File fa"...
0x18011e210  lea     rcx, [rsp+570h+var_528]
0x18011e215  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011e21a  lea     rdx, [rsp+570h+var_508]
0x18011e21f  lea     rcx, [rsp+570h+var_528]
0x18011e224  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011e229  lea     rdx, aNewFile; ", New file: "
0x18011e230  lea     rcx, [rsp+570h+var_528]
0x18011e235  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011e23a  lea     rdx, [rbp+470h+var_4E8]
0x18011e23e  lea     rcx, [rsp+570h+var_528]
0x18011e243  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011e248  lea     rdx, aError_0; ". Error: "
0x18011e24f  lea     rcx, [rsp+570h+var_528]
0x18011e254  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011e259  call    cs:__imp_GetLastError
0x18011e260  nop     dword ptr [rax+rax+00h]
0x18011e265  mov     ebx, eax
0x18011e267  lea     rcx, [rsp+570h+var_528]
0x18011e26c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011e271  mov     rdx, rax; unsigned __int16 *
0x18011e274  mov     r8d, ebx; int
0x18011e277  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x18011e27c  xor     r15b, r15b
0x18011e27f  lea     rcx, [rbp+470h+var_4E8]
0x18011e283  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011e288  nop
0x18011e289  lea     rcx, [rsp+570h+var_508]
0x18011e28e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011e293  mov     rcx, r14; hFindFile
0x18011e296  call    cs:__imp_FindClose
0x18011e29d  nop     dword ptr [rax+rax+00h]
0x18011e2a2  test    r15b, r15b
0x18011e2a5  jz      short loc_18011E2BE
0x18011e2a7  mov     rdx, rdi
0x18011e2aa  lea     rcx, [rsp+570h+var_508]
0x18011e2af  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18011e2b4  mov     rdx, rax
0x18011e2b7  call    ?DeleteCurrentDirectory@FlattenOutputFolder@@AEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FlattenOutputFolder::DeleteCurrentDirectory(std::wstring)
0x18011e2bc  jmp     short loc_18011E2F0
0x18011e2be  lea     rdx, aMovefilesintop_0; "MoveFilesIntoParentFolder: One or more "...
0x18011e2c5  lea     rcx, [rsp+570h+var_528]
0x18011e2ca  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18011e2cf  lea     rdx, [rbp+470h+var_4C8]
0x18011e2d3  lea     rcx, [rsp+570h+var_528]
0x18011e2d8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18011e2dd  lea     rcx, [rsp+570h+var_528]
0x18011e2e2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011e2e7  mov     rdx, rax; unsigned __int16 *
0x18011e2ea  call    ?Write@TelemetryWriter@@QEAAXPEBG@Z; TelemetryWriter::Write(ushort const *)
0x18011e2ef  nop
0x18011e2f0  lea     rcx, [rbp+470h+var_4C8]
0x18011e2f4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011e2f9  nop
0x18011e2fa  lea     rcx, [rsp+570h+var_528]
0x18011e2ff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011e304  nop
0x18011e305  mov     rcx, rdi
0x18011e308  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011e30d  nop
0x18011e30e  mov     rcx, rsi
0x18011e311  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011e316  mov     rcx, [rbp+470h+var_40]
0x18011e31d  xor     rcx, rsp; StackCookie
0x18011e320  call    __security_check_cookie
0x18011e325  add     rsp, 540h
0x18011e32c  pop     r15
0x18011e32e  pop     r14
0x18011e330  pop     r13
0x18011e332  pop     rdi
0x18011e333  pop     rsi
0x18011e334  pop     rbx
0x18011e335  pop     rbp
0x18011e336  retn
```
