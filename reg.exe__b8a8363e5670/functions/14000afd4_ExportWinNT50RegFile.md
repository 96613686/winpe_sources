# ExportWinNT50RegFile

- ea: `0x14000afd4`
- end: `0x14000b243`
- name: `ExportWinNT50RegFile`
- size: `623`
- prototype: `int __fastcall(LPCWSTR lpFileName, const WCHAR *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x140009c68`

## callees

- `0x140001340`
- `0x14000ae58`
- `0x14000afd4`
- `0x14000b24c`
- `0x14000c5c0`
- `0x14000caac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b210`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b210`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000b0b1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000b0b1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000b06e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000b06e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b1ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b1ee`

## string_xrefs

- `0x14000b0bd`: `Windows Registry Editor Version`

## pseudocode

```c
int __fastcall ExportWinNT50RegFile(LPCWSTR lpFileName, const WCHAR *a2)
{
  HANDLE FileW; // rax
  _WORD *v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rbx
  const WCHAR *v8; // rcx
  _WORD *v9; // rcx
  HKEY v10; // rcx
  const WCHAR *v11; // r8
  __int64 v12; // rcx
  __int64 v13; // rdx
  _WORD *v14; // rcx
  const WCHAR *v15; // rcx
  _WORD *v16; // rax
  _WORD *v17; // rcx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v21[592]; // [rsp+50h] [rbp-B0h] BYREF

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
      qword_140055248 = 0;
      WriteFile(FileW, &s_UnicodeByteOrderMark, 2u, &NumberOfBytesWritten, 0);
      PutLiteral(L"Windows Registry Editor Version");
      PutLiteral(L" ");
      PutLiteral(L"5.00");
      PutLiteral(L"\n\n");
      v5 = v21;
      v6 = 2147483646;
      v7 = 296;
      if ( a2 )
      {
        v8 = a2;
        do
        {
          if ( !v6 )
            break;
          if ( !*v8 )
            break;
          *v5++ = *v8++;
          --v6;
          --v7;
        }
        while ( v7 );
        v9 = v5 - 1;
        if ( v7 )
          v9 = v5;
        *v9 = 0;
        v10 = hKey;
      }
      else
      {
        v11 = L"HKEY_LOCAL_MACHINE";
        v12 = 2147483646;
        v13 = 296;
        do
        {
          if ( !v12 )
            break;
          if ( !*v11 )
            break;
          *v5++ = *v11++;
          --v12;
          --v13;
        }
        while ( v13 );
        v14 = v5 - 1;
        if ( v13 )
          v14 = v5;
        *v14 = 0;
        PutBranch(HKEY_LOCAL_MACHINE);
        v15 = L"HKEY_USERS";
        v16 = v21;
        do
        {
          if ( !v6 )
            break;
          if ( !*v15 )
            break;
          *v16++ = *v15++;
          --v6;
          --v7;
        }
        while ( v7 );
        v17 = v16 - 1;
        if ( v7 )
          v17 = v16;
        *v17 = 0;
        v10 = HKEY_USERS;
      }
      PutBranch(v10);
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
0x14000afd4  mov     [rsp-8+arg_18], rbx
0x14000afd9  push    rbp
0x14000afda  push    rsi
0x14000afdb  push    rdi
0x14000afdc  push    r14
0x14000afde  push    r15
0x14000afe0  lea     rbp, [rsp-1B0h]
0x14000afe8  sub     rsp, 2B0h
0x14000afef  mov     rax, cs:__security_cookie
0x14000aff6  xor     rax, rsp
0x14000aff9  mov     [rbp+1D0h+var_30], rax
0x14000b000  xor     r15d, r15d
0x14000b003  mov     [rsp+2D0h+hKey], 0FFFFFFFFFFFFFFFFh
0x14000b00c  mov     cs:g_FileErrorStringID, r15d
0x14000b013  mov     r14d, r8d
0x14000b016  mov     rsi, rdx
0x14000b019  mov     rbx, rcx
0x14000b01c  test    rdx, rdx
0x14000b01f  jz      short loc_14000B044
0x14000b021  mov     r9d, r8d
0x14000b024  lea     rcx, [rsp+2D0h+hKey]; phkResult
0x14000b029  xor     r8d, r8d
0x14000b02c  call    EditRegistryKey
0x14000b031  test    eax, eax
0x14000b033  jz      short loc_14000B044
0x14000b035  mov     cs:g_FileErrorStringID, 3F2h
0x14000b03f  jmp     loc_14000B21C
0x14000b044  mov     [rsp+2D0h+hTemplateFile], r15; hTemplateFile
0x14000b049  xor     r9d, r9d; lpSecurityAttributes
0x14000b04c  mov     [rsp+2D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14000b054  xor     r8d, r8d; dwShareMode
0x14000b057  mov     edx, 40000000h; dwDesiredAccess
0x14000b05c  mov     [rsp+2D0h+dwCreationDisposition], 2; dwCreationDisposition
0x14000b064  mov     rcx, rbx; lpFileName
0x14000b067  mov     cs:g_dwTotalKeysSaved, r15d
0x14000b06e  call    cs:__imp_CreateFileW
0x14000b075  nop     dword ptr [rax+rax+00h]
0x14000b07a  mov     cs:hObject, rax
0x14000b081  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000b085  jz      loc_14000B1FC
0x14000b08b  lea     r9, [rsp+2D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000b090  mov     [rsp+2D0h+NumberOfBytesWritten], r15d
0x14000b095  mov     r8d, 2; nNumberOfBytesToWrite
0x14000b09b  mov     cs:qword_140055248, r15
0x14000b0a2  lea     rdx, s_UnicodeByteOrderMark; lpBuffer
0x14000b0a9  mov     qword ptr [rsp+2D0h+dwCreationDisposition], r15; lpOverlapped
0x14000b0ae  mov     rcx, rax; hFile
0x14000b0b1  call    cs:__imp_WriteFile
0x14000b0b8  nop     dword ptr [rax+rax+00h]
0x14000b0bd  lea     rcx, s_WinNT50RegFileHeader; "Windows Registry Editor Version"
0x14000b0c4  call    PutLiteral
0x14000b0c9  lea     rcx, asc_140011954; " "
0x14000b0d0  call    PutLiteral
0x14000b0d5  lea     rcx, s_WinNT50RegFileVersion; "5.00"
0x14000b0dc  call    PutLiteral
0x14000b0e1  lea     rcx, asc_140012174; "\n\n"
0x14000b0e8  call    PutLiteral
0x14000b0ed  lea     rax, [rsp+2D0h+var_280]
0x14000b0f2  mov     edi, 7FFFFFFEh
0x14000b0f7  mov     ebx, 128h
0x14000b0fc  test    rsi, rsi
0x14000b0ff  jz      short loc_14000B13E
0x14000b101  mov     rcx, rsi
0x14000b104  test    rdi, rdi
0x14000b107  jz      short loc_14000B125
0x14000b109  movzx   edx, word ptr [rcx]
0x14000b10c  test    dx, dx
0x14000b10f  jz      short loc_14000B125
0x14000b111  mov     [rax], dx
0x14000b114  add     rcx, 2
0x14000b118  add     rax, 2
0x14000b11c  dec     rdi
0x14000b11f  sub     rbx, 1
0x14000b123  jnz     short loc_14000B104
0x14000b125  test    rbx, rbx
0x14000b128  lea     rcx, [rax-2]
0x14000b12c  cmovnz  rcx, rax
0x14000b130  mov     [rcx], r15w
0x14000b134  mov     rcx, [rsp+2D0h+hKey]
0x14000b139  jmp     loc_14000B1D5
0x14000b13e  mov     r8, cs:off_1400110E0; "HKEY_LOCAL_MACHINE"
0x14000b145  mov     rcx, rdi
0x14000b148  mov     rdx, rbx
0x14000b14b  test    rcx, rcx
0x14000b14e  jz      short loc_14000B16F
0x14000b150  movzx   r9d, word ptr [r8]
0x14000b154  test    r9w, r9w
0x14000b158  jz      short loc_14000B16F
0x14000b15a  mov     [rax], r9w
0x14000b15e  add     r8, 2
0x14000b162  add     rax, 2
0x14000b166  dec     rcx
0x14000b169  sub     rdx, 1
0x14000b16d  jnz     short loc_14000B14B
0x14000b16f  test    rdx, rdx
0x14000b172  lea     rcx, [rax-2]
0x14000b176  mov     r8d, r14d
0x14000b179  lea     rdx, [rsp+2D0h+var_280]
0x14000b17e  cmovnz  rcx, rax
0x14000b182  mov     [rcx], r15w
0x14000b186  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000b18d  call    PutBranch
0x14000b192  mov     rcx, cs:off_1400110F0; "HKEY_USERS"
0x14000b199  lea     rax, [rsp+2D0h+var_280]
0x14000b19e  test    rdi, rdi
0x14000b1a1  jz      short loc_14000B1BF
0x14000b1a3  movzx   edx, word ptr [rcx]
0x14000b1a6  test    dx, dx
0x14000b1a9  jz      short loc_14000B1BF
0x14000b1ab  mov     [rax], dx
0x14000b1ae  add     rcx, 2
0x14000b1b2  add     rax, 2
0x14000b1b6  dec     rdi
0x14000b1b9  sub     rbx, 1
0x14000b1bd  jnz     short loc_14000B19E
0x14000b1bf  test    rbx, rbx
0x14000b1c2  lea     rcx, [rax-2]
0x14000b1c6  cmovnz  rcx, rax
0x14000b1ca  mov     [rcx], r15w
0x14000b1ce  mov     rcx, 0FFFFFFFF80000003h; hKey
0x14000b1d5  mov     r8d, r14d
0x14000b1d8  lea     rdx, [rsp+2D0h+var_280]
0x14000b1dd  call    PutBranch
0x14000b1e2  call    FlushIoBuffer
0x14000b1e7  mov     rcx, cs:hObject; hObject
0x14000b1ee  call    cs:__imp_CloseHandle
0x14000b1f5  nop     dword ptr [rax+rax+00h]
0x14000b1fa  jmp     short loc_14000B206
0x14000b1fc  mov     cs:g_FileErrorStringID, 6Eh ; 'n'
0x14000b206  test    rsi, rsi
0x14000b209  jz      short loc_14000B21C
0x14000b20b  mov     rcx, [rsp+2D0h+hKey]; hKey
0x14000b210  call    cs:__imp_RegCloseKey
0x14000b217  nop     dword ptr [rax+rax+00h]
0x14000b21c  mov     rcx, [rbp+1D0h+var_30]
0x14000b223  xor     rcx, rsp; StackCookie
0x14000b226  call    __security_check_cookie
0x14000b22b  mov     rbx, [rsp+2D0h+arg_18]
0x14000b233  add     rsp, 2B0h
0x14000b23a  pop     r15
0x14000b23c  pop     r14
0x14000b23e  pop     rdi
0x14000b23f  pop     rsi
0x14000b240  pop     rbp
0x14000b241  retn
```
