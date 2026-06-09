# ExportWinNT50RegFile

- ea: `0x14000a934`
- end: `0x14000ab8a`
- name: `ExportWinNT50RegFile`
- size: `598`
- prototype: `int __fastcall(LPCWSTR lpFileName, const WCHAR *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x1400096a8`

## callees

- `0x140001340`
- `0x14000a7d8`
- `0x14000a934`
- `0x14000ab90`
- `0x14000be00`
- `0x14000c2b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ab5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ab5e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000aa0b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000aa0b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000a9ce`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000a9ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ab42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ab42`

## string_xrefs

- `0x14000aa11`: `Windows Registry Editor Version`

## pseudocode

```c
int __fastcall ExportWinNT50RegFile(LPCWSTR lpFileName, const WCHAR *a2, int a3)
{
  HANDLE FileW; // rax
  _WORD *v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rbx
  const WCHAR *v10; // rcx
  _WORD *v11; // rcx
  HKEY v12; // rcx
  const WCHAR *v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rdx
  _WORD *v16; // rcx
  const WCHAR *v17; // rcx
  _WORD *v18; // rax
  _WORD *v19; // rcx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v23[296]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  g_FileErrorStringID = 0;
  if ( a2 && (LODWORD(FileW) = EditRegistryKey(&hKey, a2), (_DWORD)FileW) )
  {
    g_FileErrorStringID = 1010;
  }
  else
  {
    g_dwTotalKeysSaved = 0;
    FileW = CreateFileW(lpFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    hObject = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      g_FileErrorStringID = 110;
    }
    else
    {
      NumberOfBytesWritten = 0;
      qword_140054248 = 0;
      WriteFile(FileW, &s_UnicodeByteOrderMark, 2u, &NumberOfBytesWritten, 0);
      PutLiteral(L"Windows Registry Editor Version");
      PutLiteral(L" ");
      PutLiteral(L"5.00");
      PutLiteral(L"\n\n");
      v7 = v23;
      v8 = 2147483646;
      v9 = 296;
      if ( a2 )
      {
        v10 = a2;
        do
        {
          if ( !v8 )
            break;
          if ( !*v10 )
            break;
          *v7++ = *v10++;
          --v8;
          --v9;
        }
        while ( v9 );
        v11 = v7 - 1;
        if ( v9 )
          v11 = v7;
        *v11 = 0;
        v12 = hKey;
      }
      else
      {
        v13 = L"HKEY_LOCAL_MACHINE";
        v14 = 2147483646;
        v15 = 296;
        do
        {
          if ( !v14 )
            break;
          if ( !*v13 )
            break;
          *v7++ = *v13++;
          --v14;
          --v15;
        }
        while ( v15 );
        v16 = v7 - 1;
        if ( v15 )
          v16 = v7;
        *v16 = 0;
        PutBranch(HKEY_LOCAL_MACHINE, v23, a3);
        v17 = L"HKEY_USERS";
        v18 = v23;
        do
        {
          if ( !v8 )
            break;
          if ( !*v17 )
            break;
          *v18++ = *v17++;
          --v8;
          --v9;
        }
        while ( v9 );
        v19 = v18 - 1;
        if ( v9 )
          v19 = v18;
        *v19 = 0;
        v12 = HKEY_USERS;
      }
      PutBranch(v12, v23, a3);
      FlushIoBuffer();
      LODWORD(FileW) = CloseHandle(hObject);
    }
    if ( a2 )
      LODWORD(FileW) = RegCloseKey(hKey);
  }
  return (int)FileW;
}

```

## disassembly

```asm
0x14000a934  mov     [rsp-8+arg_18], rbx
0x14000a939  push    rbp
0x14000a93a  push    rsi
0x14000a93b  push    rdi
0x14000a93c  push    r14
0x14000a93e  push    r15
0x14000a940  lea     rbp, [rsp-1B0h]
0x14000a948  sub     rsp, 2B0h
0x14000a94f  mov     rax, cs:__security_cookie
0x14000a956  xor     rax, rsp
0x14000a959  mov     [rbp+1D0h+var_30], rax
0x14000a960  xor     r15d, r15d
0x14000a963  mov     [rsp+2D0h+hKey], 0FFFFFFFFFFFFFFFFh
0x14000a96c  mov     cs:g_FileErrorStringID, r15d
0x14000a973  mov     r14d, r8d
0x14000a976  mov     rsi, rdx
0x14000a979  mov     rbx, rcx
0x14000a97c  test    rdx, rdx
0x14000a97f  jz      short loc_14000A9A4
0x14000a981  mov     r9d, r8d
0x14000a984  lea     rcx, [rsp+2D0h+hKey]; phkResult
0x14000a989  xor     r8d, r8d
0x14000a98c  call    EditRegistryKey
0x14000a991  test    eax, eax
0x14000a993  jz      short loc_14000A9A4
0x14000a995  mov     cs:g_FileErrorStringID, 3F2h
0x14000a99f  jmp     loc_14000AB64
0x14000a9a4  mov     [rsp+2D0h+hTemplateFile], r15; hTemplateFile
0x14000a9a9  xor     r9d, r9d; lpSecurityAttributes
0x14000a9ac  mov     [rsp+2D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14000a9b4  xor     r8d, r8d; dwShareMode
0x14000a9b7  mov     edx, 40000000h; dwDesiredAccess
0x14000a9bc  mov     [rsp+2D0h+dwCreationDisposition], 2; dwCreationDisposition
0x14000a9c4  mov     rcx, rbx; lpFileName
0x14000a9c7  mov     cs:g_dwTotalKeysSaved, r15d
0x14000a9ce  call    cs:__imp_CreateFileW
0x14000a9d4  mov     cs:hObject, rax
0x14000a9db  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000a9df  jz      loc_14000AB4A
0x14000a9e5  lea     r9, [rsp+2D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000a9ea  mov     [rsp+2D0h+NumberOfBytesWritten], r15d
0x14000a9ef  mov     r8d, 2; nNumberOfBytesToWrite
0x14000a9f5  mov     cs:qword_140054248, r15
0x14000a9fc  lea     rdx, s_UnicodeByteOrderMark; lpBuffer
0x14000aa03  mov     qword ptr [rsp+2D0h+dwCreationDisposition], r15; lpOverlapped
0x14000aa08  mov     rcx, rax; hFile
0x14000aa0b  call    cs:__imp_WriteFile
0x14000aa11  lea     rcx, s_WinNT50RegFileHeader; "Windows Registry Editor Version"
0x14000aa18  call    PutLiteral
0x14000aa1d  lea     rcx, asc_140010954; " "
0x14000aa24  call    PutLiteral
0x14000aa29  lea     rcx, s_WinNT50RegFileVersion; "5.00"
0x14000aa30  call    PutLiteral
0x14000aa35  lea     rcx, asc_140011174; "\n\n"
0x14000aa3c  call    PutLiteral
0x14000aa41  lea     rax, [rsp+2D0h+var_280]
0x14000aa46  mov     edi, 7FFFFFFEh
0x14000aa4b  mov     ebx, 128h
0x14000aa50  test    rsi, rsi
0x14000aa53  jz      short loc_14000AA92
0x14000aa55  mov     rcx, rsi
0x14000aa58  test    rdi, rdi
0x14000aa5b  jz      short loc_14000AA79
0x14000aa5d  movzx   edx, word ptr [rcx]
0x14000aa60  test    dx, dx
0x14000aa63  jz      short loc_14000AA79
0x14000aa65  mov     [rax], dx
0x14000aa68  add     rcx, 2
0x14000aa6c  add     rax, 2
0x14000aa70  dec     rdi
0x14000aa73  sub     rbx, 1
0x14000aa77  jnz     short loc_14000AA58
0x14000aa79  test    rbx, rbx
0x14000aa7c  lea     rcx, [rax-2]
0x14000aa80  cmovnz  rcx, rax
0x14000aa84  mov     [rcx], r15w
0x14000aa88  mov     rcx, [rsp+2D0h+hKey]
0x14000aa8d  jmp     loc_14000AB29
0x14000aa92  mov     r8, cs:off_1400100E0; "HKEY_LOCAL_MACHINE"
0x14000aa99  mov     rcx, rdi
0x14000aa9c  mov     rdx, rbx
0x14000aa9f  test    rcx, rcx
0x14000aaa2  jz      short loc_14000AAC3
0x14000aaa4  movzx   r9d, word ptr [r8]
0x14000aaa8  test    r9w, r9w
0x14000aaac  jz      short loc_14000AAC3
0x14000aaae  mov     [rax], r9w
0x14000aab2  add     r8, 2
0x14000aab6  add     rax, 2
0x14000aaba  dec     rcx
0x14000aabd  sub     rdx, 1
0x14000aac1  jnz     short loc_14000AA9F
0x14000aac3  test    rdx, rdx
0x14000aac6  lea     rcx, [rax-2]
0x14000aaca  mov     r8d, r14d
0x14000aacd  lea     rdx, [rsp+2D0h+var_280]
0x14000aad2  cmovnz  rcx, rax
0x14000aad6  mov     [rcx], r15w
0x14000aada  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000aae1  call    PutBranch
0x14000aae6  mov     rcx, cs:off_1400100F0; "HKEY_USERS"
0x14000aaed  lea     rax, [rsp+2D0h+var_280]
0x14000aaf2  test    rdi, rdi
0x14000aaf5  jz      short loc_14000AB13
0x14000aaf7  movzx   edx, word ptr [rcx]
0x14000aafa  test    dx, dx
0x14000aafd  jz      short loc_14000AB13
0x14000aaff  mov     [rax], dx
0x14000ab02  add     rcx, 2
0x14000ab06  add     rax, 2
0x14000ab0a  dec     rdi
0x14000ab0d  sub     rbx, 1
0x14000ab11  jnz     short loc_14000AAF2
0x14000ab13  test    rbx, rbx
0x14000ab16  lea     rcx, [rax-2]
0x14000ab1a  cmovnz  rcx, rax
0x14000ab1e  mov     [rcx], r15w
0x14000ab22  mov     rcx, 0FFFFFFFF80000003h; hKey
0x14000ab29  mov     r8d, r14d
0x14000ab2c  lea     rdx, [rsp+2D0h+var_280]
0x14000ab31  call    PutBranch
0x14000ab36  call    FlushIoBuffer
0x14000ab3b  mov     rcx, cs:hObject; hObject
0x14000ab42  call    cs:__imp_CloseHandle
0x14000ab48  jmp     short loc_14000AB54
0x14000ab4a  mov     cs:g_FileErrorStringID, 6Eh ; 'n'
0x14000ab54  test    rsi, rsi
0x14000ab57  jz      short loc_14000AB64
0x14000ab59  mov     rcx, [rsp+2D0h+hKey]; hKey
0x14000ab5e  call    cs:__imp_RegCloseKey
0x14000ab64  mov     rcx, [rbp+1D0h+var_30]
0x14000ab6b  xor     rcx, rsp; StackCookie
0x14000ab6e  call    __security_check_cookie
0x14000ab73  mov     rbx, [rsp+2D0h+arg_18]
0x14000ab7b  add     rsp, 2B0h
0x14000ab82  pop     r15
0x14000ab84  pop     r14
0x14000ab86  pop     rdi
0x14000ab87  pop     rsi
0x14000ab88  pop     rbp
0x14000ab89  retn
```
