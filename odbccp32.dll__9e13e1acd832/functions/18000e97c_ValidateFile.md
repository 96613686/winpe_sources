# ValidateFile

- ea: `0x18000e97c`
- end: `0x18000ea93`
- name: `ValidateFile`
- size: `279`
- prototype: `__int64 __fastcall(HWND hWnd, __int64, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000c440`
- `0x18000dc70`

## callees

- `0x180002e4c`
- `0x18000b784`
- `0x18000e97c`
- `0x180014814`
- `0x180014ae0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000ea68`
- `KERNEL32!CloseHandle` at `0x18000ea68`
- `KERNEL32!OutputDebugStringW` at `0x18000ea5f`
- `KERNEL32!OutputDebugStringW` at `0x18000ea5f`
- `KERNEL32!SetFileInformationByHandle` at `0x18000ea29`
- `KERNEL32!SetFileInformationByHandle` at `0x18000ea29`
- `KERNEL32!GetLastError` at `0x18000e9bf`
- `KERNEL32!GetLastError` at `0x18000e9e2`
- `KERNEL32!GetLastError` at `0x18000ea33`
- `KERNEL32!GetLastError` at `0x18000e9bf`
- `KERNEL32!GetLastError` at `0x18000e9e2`
- `KERNEL32!GetLastError` at `0x18000ea33`

## string_xrefs

- `0x18000ea40`: `ODBC: ValidateFile cleanup failed (non-critical) - Path: %s, Error: 0x%08X (%u)\n`

## pseudocode

```c
__int64 __fastcall ValidateFile(HWND hWnd, __int64 a2, int a3, int a4)
{
  int v6; // esi
  void *v7; // rbx
  DWORD LastError; // eax
  int v9; // r8d
  int v10; // r9d
  DWORD v12; // [rsp+20h] [rbp-478h]
  char FileInformation[16]; // [rsp+40h] [rbp-458h] BYREF
  wchar_t pszDest[512]; // [rsp+50h] [rbp-448h] BYREF

  v6 = 1;
  v7 = (void *)ODBCCreateFile(a2, -1073676288, a3, a4);
  LastError = GetLastError();
  if ( v7 == (void *)-1LL
    && (LastError != 5
     || (v6 = 0, v7 = (void *)ODBCCreateFile(a2, -1073741824, v9, v10), LastError = GetLastError(), v7 == (void *)-1LL)) )
  {
    CpanelError(hWnd, LastError);
    return 0;
  }
  else
  {
    if ( LastError != 183 && v6 )
    {
      FileInformation[0] = 1;
      if ( !SetFileInformationByHandle(v7, FileDispositionInfo, FileInformation, 1u) )
      {
        v12 = GetLastError();
        StringCchPrintfW(
          pszDest,
          0x200u,
          L"ODBC: ValidateFile cleanup failed (non-critical) - Path: %s, Error: 0x%08X (%u)\n",
          a2,
          v12,
          v12);
        OutputDebugStringW(pszDest);
      }
    }
    CloseHandle(v7);
    return 1;
  }
}

```

## disassembly

```asm
0x18000e97c  push    rbx
0x18000e97e  push    rbp
0x18000e97f  push    rsi
0x18000e980  push    rdi
0x18000e981  push    r14
0x18000e983  push    r15
0x18000e985  sub     rsp, 468h
0x18000e98c  mov     rax, cs:__security_cookie
0x18000e993  xor     rax, rsp
0x18000e996  mov     [rsp+498h+var_48], rax
0x18000e99e  mov     rdi, rdx
0x18000e9a1  mov     rbp, rcx
0x18000e9a4  mov     rcx, rdi
0x18000e9a7  mov     edx, 0C0010000h
0x18000e9ac  mov     r15d, r9d
0x18000e9af  mov     r14d, r8d
0x18000e9b2  mov     esi, 1
0x18000e9b7  call    ODBCCreateFile
0x18000e9bc  mov     rbx, rax
0x18000e9bf  call    cs:__imp_GetLastError
0x18000e9c5  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000e9c9  jnz     short loc_18000EA07
0x18000e9cb  cmp     eax, 5
0x18000e9ce  jnz     short loc_18000E9EE
0x18000e9d0  mov     edx, 0C0000000h
0x18000e9d5  mov     rcx, rdi
0x18000e9d8  xor     esi, esi
0x18000e9da  call    ODBCCreateFile
0x18000e9df  mov     rbx, rax
0x18000e9e2  call    cs:__imp_GetLastError
0x18000e9e8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000e9ec  jnz     short loc_18000EA07
0x18000e9ee  mov     r9, rdi
0x18000e9f1  mov     [rsp+498h+var_478], eax; int
0x18000e9f5  mov     r8d, r15d
0x18000e9f8  mov     edx, r14d
0x18000e9fb  mov     rcx, rbp; hWnd
0x18000e9fe  call    CpanelError
0x18000ea03  xor     eax, eax
0x18000ea05  jmp     short loc_18000EA73
0x18000ea07  cmp     eax, 0B7h
0x18000ea0c  jz      short loc_18000EA65
0x18000ea0e  test    esi, esi
0x18000ea10  jz      short loc_18000EA65
0x18000ea12  mov     r9d, 1; dwBufferSize
0x18000ea18  mov     [rsp+498h+FileInformation], 1
0x18000ea1d  lea     r8, [rsp+498h+FileInformation]; lpFileInformation
0x18000ea22  mov     rcx, rbx; hFile
0x18000ea25  lea     edx, [r9+3]; FileInformationClass
0x18000ea29  call    cs:__imp_SetFileInformationByHandle
0x18000ea2f  test    eax, eax
0x18000ea31  jnz     short loc_18000EA65
0x18000ea33  call    cs:__imp_GetLastError
0x18000ea39  mov     [rsp+498h+var_470], eax
0x18000ea3d  mov     r9, rdi
0x18000ea40  lea     r8, aOdbcValidatefi; "ODBC: ValidateFile cleanup failed (non-"...
0x18000ea47  mov     [rsp+498h+var_478], eax
0x18000ea4b  mov     edx, 200h; cchDest
0x18000ea50  lea     rcx, [rsp+498h+pszDest]; pszDest
0x18000ea55  call    StringCchPrintfW
0x18000ea5a  lea     rcx, [rsp+498h+pszDest]; lpOutputString
0x18000ea5f  call    cs:__imp_OutputDebugStringW
0x18000ea65  mov     rcx, rbx; hObject
0x18000ea68  call    cs:__imp_CloseHandle
0x18000ea6e  mov     eax, 1
0x18000ea73  mov     rcx, [rsp+498h+var_48]
0x18000ea7b  xor     rcx, rsp; StackCookie
0x18000ea7e  call    __security_check_cookie
0x18000ea83  add     rsp, 468h
0x18000ea8a  pop     r15
0x18000ea8c  pop     r14
0x18000ea8e  pop     rdi
0x18000ea8f  pop     rsi
0x18000ea90  pop     rbp
0x18000ea91  pop     rbx
0x18000ea92  retn
```
