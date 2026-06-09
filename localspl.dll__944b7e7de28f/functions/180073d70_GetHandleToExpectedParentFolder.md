# GetHandleToExpectedParentFolder

- ea: `0x180073d70`
- end: `0x180073f72`
- name: `GetHandleToExpectedParentFolder`
- size: `514`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800a7f24`
- `0x1800a8068`

## callees

- `0x18003ea2c`
- `0x180046650`
- `0x180047330`
- `0x180073d70`
- `0x1800e0a14`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180073e96`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180073ea9`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180073ec1`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180073e96`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180073ea9`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180073ec1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180073ed4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180073ed4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180073ddb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180073ddb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073e38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073e38`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180073e6e`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180073e6e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180073e2a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180073e2a`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180073df5`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180073df5`
- `SPOOLSS!DllFreeSplMem` at `0x180073f08`
- `SPOOLSS!DllFreeSplMem` at `0x180073f08`

## string_xrefs

- `0x180073f13`: `GetFinalPathNameByHandleW failed, Count(%d)`
- `0x180073e46`: `CreateFile(%ws) called failed, Error %d`
- `0x180073ee8`: `Path string comparison failed: Expected(%ws) Actual(%ws)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetHandleToExpectedParentFolder(const wchar_t *a1)
{
  __int64 v2; // rsi
  HANDLE FileW; // rax
  __int64 v4; // r14
  DWORD LastError; // eax
  DWORD FinalPathNameByHandleW; // eax
  const wchar_t *v7; // rdi
  size_t v8; // rbx
  size_t v9; // rax
  WCHAR *v10; // rcx
  size_t v11; // rax
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR szFilePath[264]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(pszPath, 0, 0x208u);
  memset_0(szFilePath, 0, 0x208u);
  if ( !a1 || (unsigned int)_o_wcscpy_s(pszPath, 260, a1) )
  {
    if ( !a1 )
      a1 = L"NULL";
    LocalSpoolerTelemetry::WriteDbgTraceError("GetHandleToExpectedParentFolder", L"Invalid argument: %ws", a1);
    return -1;
  }
  else
  {
    v2 = -1;
    if ( PathCchRemoveFileSpec(pszPath, 0x104u) >= 0 )
    {
      FileW = CreateFileW(pszPath, 0x80000000, 3u, 0, 3u, 0x2000080u, 0);
      v4 = (__int64)FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "GetHandleToExpectedParentFolder",
          L"CreateFile(%ws) called failed, Error %d",
          pszPath,
          LastError);
      }
      else
      {
        FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, szFilePath, 0x104u, 0);
        if ( FinalPathNameByHandleW - 1 > 0x103 )
        {
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "GetHandleToExpectedParentFolder",
            L"GetFinalPathNameByHandleW failed, Count(%d)",
            FinalPathNameByHandleW);
        }
        else
        {
          v7 = (const wchar_t *)ConvertFullPathToLongUNC(pszPath);
          v8 = wcsnlen(v7, 0x104u);
          v9 = wcsnlen(szFilePath, 0x104u);
          v10 = szFilePath;
          if ( v9 >= v8 )
            v10 = (WCHAR *)v7;
          v11 = wcsnlen(v10, 0x104u);
          if ( (unsigned int)_o__wcsnicmp(szFilePath, v7, v11) )
            LocalSpoolerTelemetry::WriteDbgTraceError(
              "GetHandleToExpectedParentFolder",
              L"Path string comparison failed: Expected(%ws) Actual(%ws)",
              v7,
              szFilePath);
          else
            v2 = v4;
          if ( v7 )
            DllFreeSplMem(v7);
        }
      }
    }
    return v2;
  }
}

```

## disassembly

```asm
0x180073d70  push    rbp
0x180073d72  push    rbx
0x180073d73  push    rsi
0x180073d74  push    rdi
0x180073d75  push    r14
0x180073d77  push    r15
0x180073d79  lea     rbp, [rsp-378h]
0x180073d81  sub     rsp, 478h
0x180073d88  mov     rax, cs:__security_cookie
0x180073d8f  xor     rax, rsp
0x180073d92  mov     [rbp+3A0h+var_40], rax
0x180073d99  mov     rbx, rcx
0x180073d9c  mov     edi, 208h
0x180073da1  mov     r8d, edi; Size
0x180073da4  lea     rcx, [rsp+4A0h+pszPath]; void *
0x180073da9  xor     edx, edx; Val
0x180073dab  call    memset_0
0x180073db0  mov     r8d, edi; Size
0x180073db3  lea     rcx, [rbp+3A0h+szFilePath]; void *
0x180073dba  xor     edx, edx; Val
0x180073dbc  call    memset_0
0x180073dc1  test    rbx, rbx
0x180073dc4  jz      loc_180073F2B
0x180073dca  mov     r15d, 104h
0x180073dd0  lea     rcx, [rsp+4A0h+pszPath]
0x180073dd5  mov     edx, r15d
0x180073dd8  mov     r8, rbx
0x180073ddb  call    cs:__imp__o_wcscpy_s
0x180073de1  test    eax, eax
0x180073de3  jnz     loc_180073F2B
0x180073de9  mov     edx, r15d; cchPath
0x180073dec  lea     rcx, [rsp+4A0h+pszPath]; pszPath
0x180073df1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180073df5  call    cs:__imp_PathCchRemoveFileSpec
0x180073dfb  test    eax, eax
0x180073dfd  js      loc_180073F26
0x180073e03  mov     [rsp+4A0h+hTemplateFile], 0; hTemplateFile
0x180073e0c  lea     r8d, [rsi+4]; dwShareMode
0x180073e10  mov     [rsp+4A0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x180073e18  lea     rcx, [rsp+4A0h+pszPath]; lpFileName
0x180073e1d  xor     r9d, r9d; lpSecurityAttributes
0x180073e20  mov     [rsp+4A0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180073e25  mov     edx, 80000000h; dwDesiredAccess
0x180073e2a  call    cs:__imp_CreateFileW
0x180073e30  mov     r14, rax
0x180073e33  cmp     rax, rsi
0x180073e36  jnz     short loc_180073E5E
0x180073e38  call    cs:__imp_GetLastError
0x180073e3e  mov     r9d, eax
0x180073e41  lea     r8, [rsp+4A0h+pszPath]
0x180073e46  lea     rdx, aCreatefileWsCa; "CreateFile(%ws) called failed, Error %d"
0x180073e4d  lea     rcx, aGethandletoexp; "GetHandleToExpectedParentFolder"
0x180073e54  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180073e59  jmp     loc_180073F26
0x180073e5e  xor     r9d, r9d; dwFlags
0x180073e61  lea     rdx, [rbp+3A0h+szFilePath]; lpszFilePath
0x180073e68  mov     r8d, r15d; cchFilePath
0x180073e6b  mov     rcx, r14; hFile
0x180073e6e  call    cs:__imp_GetFinalPathNameByHandleW
0x180073e74  lea     ecx, [rax-1]
0x180073e77  cmp     ecx, 103h
0x180073e7d  ja      loc_180073F10
0x180073e83  lea     rcx, [rsp+4A0h+pszPath]
0x180073e88  call    ConvertFullPathToLongUNC
0x180073e8d  mov     rdx, r15; MaxCount
0x180073e90  mov     rcx, rax; Source
0x180073e93  mov     rdi, rax
0x180073e96  call    cs:__imp_wcsnlen
0x180073e9c  mov     rdx, r15; MaxCount
0x180073e9f  lea     rcx, [rbp+3A0h+szFilePath]; Source
0x180073ea6  mov     rbx, rax
0x180073ea9  call    cs:__imp_wcsnlen
0x180073eaf  mov     rdx, r15; MaxCount
0x180073eb2  lea     rcx, [rbp+3A0h+szFilePath]
0x180073eb9  cmp     rax, rbx
0x180073ebc  jb      short loc_180073EC1
0x180073ebe  mov     rcx, rdi; Source
0x180073ec1  call    cs:__imp_wcsnlen
0x180073ec7  mov     rdx, rdi
0x180073eca  lea     rcx, [rbp+3A0h+szFilePath]
0x180073ed1  mov     r8, rax
0x180073ed4  call    cs:__imp__o__wcsnicmp
0x180073eda  test    eax, eax
0x180073edc  jz      short loc_180073EFD
0x180073ede  lea     r9, [rbp+3A0h+szFilePath]
0x180073ee5  mov     r8, rdi
0x180073ee8  lea     rdx, aPathStringComp; "Path string comparison failed: Expected"...
0x180073eef  lea     rcx, aGethandletoexp; "GetHandleToExpectedParentFolder"
0x180073ef6  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180073efb  jmp     short loc_180073F00
0x180073efd  mov     rsi, r14
0x180073f00  test    rdi, rdi
0x180073f03  jz      short loc_180073F26
0x180073f05  mov     rcx, rdi
0x180073f08  call    cs:__imp_DllFreeSplMem
0x180073f0e  jmp     short loc_180073F26
0x180073f10  mov     r8d, eax
0x180073f13  lea     rdx, aGetfinalpathna; "GetFinalPathNameByHandleW failed, Count"...
0x180073f1a  lea     rcx, aGethandletoexp; "GetHandleToExpectedParentFolder"
0x180073f21  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180073f26  mov     rax, rsi
0x180073f29  jmp     short loc_180073F53
0x180073f2b  lea     rax, aNull_0; "NULL"
0x180073f32  test    rbx, rbx
0x180073f35  lea     rdx, aInvalidArgumen; "Invalid argument: %ws"
0x180073f3c  cmovz   rbx, rax
0x180073f40  lea     rcx, aGethandletoexp; "GetHandleToExpectedParentFolder"
0x180073f47  mov     r8, rbx
0x180073f4a  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180073f4f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180073f53  mov     rcx, [rbp+3A0h+var_40]
0x180073f5a  xor     rcx, rsp; StackCookie
0x180073f5d  call    __security_check_cookie
0x180073f62  add     rsp, 478h
0x180073f69  pop     r15
0x180073f6b  pop     r14
0x180073f6d  pop     rdi
0x180073f6e  pop     rsi
0x180073f6f  pop     rbx
0x180073f70  pop     rbp
0x180073f71  retn
```
