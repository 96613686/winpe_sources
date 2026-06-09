# ExportWinNT50RegFileFromPath

- ea: `0x18009c828`
- end: `0x18009c9ba`
- name: `ExportWinNT50RegFileFromPath`
- size: `402`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001c63c`

## callees

- `0x18009c748`
- `0x18009c828`
- `0x18009c9c0`
- `0x18009d3b8`
- `0x1800cdac0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18009c982`
- `ADVAPI32!RegCloseKey` at `0x18009c982`
- `KERNEL32!WriteFile` at `0x18009c8eb`
- `KERNEL32!WriteFile` at `0x18009c8eb`
- `KERNEL32!GetLastError` at `0x18009c966`
- `KERNEL32!GetLastError` at `0x18009c966`
- `KERNEL32!CloseHandle` at `0x18009c958`
- `KERNEL32!CloseHandle` at `0x18009c958`
- `KERNEL32!CreateFileW` at `0x18009c8a9`
- `KERNEL32!CreateFileW` at `0x18009c8a9`

## pseudocode

```c
__int64 __fastcall ExportWinNT50RegFileFromPath(LPCWSTR lpFileName, WCHAR *a2)
{
  HANDLE FileW; // rax
  signed __int64 v5; // r8
  _WORD *v6; // rcx
  __int64 v7; // rdx
  __int16 v8; // ax
  _WORD *v9; // rax
  HKEY v10; // rcx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-278h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-270h] BYREF
  _BYTE v14[592]; // [rsp+50h] [rbp-268h] BYREF

  hKey = 0;
  g_FileErrorStringID = 0;
  if ( !a2 || (g_FileErrorStringID = EditRegistryKey(&hKey, a2)) == 0 )
  {
    FileW = CreateFileW(lpFileName, 0x40000000u, 1u, &DhcpGlobalDirSecurityAttr, 2u, 0x80u, 0);
    hFile = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      g_FileErrorStringID = GetLastError();
    }
    else
    {
      NumberOfBytesWritten = 0;
      qword_180140E68 = 0;
      WriteFile(FileW, &s_UnicodeByteOrderMark, 2u, &NumberOfBytesWritten, 0);
      v5 = (char *)a2 - v14;
      v6 = v14;
      v7 = 296;
      do
      {
        if ( v7 == -2147483350 )
          break;
        v8 = *(_WORD *)((char *)v6 + v5);
        if ( !v8 )
          break;
        *v6++ = v8;
        --v7;
      }
      while ( v7 );
      v9 = v6 - 1;
      if ( v7 )
        v9 = v6;
      v10 = hKey;
      *v9 = 0;
      PutBranch(v10, v14, v5);
      FlushIoBuffer();
      CloseHandle(hFile);
    }
    if ( a2 )
      RegCloseKey(hKey);
  }
  return (unsigned int)g_FileErrorStringID;
}

```

## disassembly

```asm
0x18009c828  mov     [rsp+arg_10], rbx
0x18009c82d  mov     [rsp+arg_18], rsi
0x18009c832  push    rdi
0x18009c833  sub     rsp, 2B0h
0x18009c83a  mov     rax, cs:__security_cookie
0x18009c841  xor     rax, rsp
0x18009c844  mov     [rsp+2B8h+var_18], rax
0x18009c84c  xor     esi, esi
0x18009c84e  mov     rbx, rdx
0x18009c851  mov     [rsp+2B8h+hKey], rsi
0x18009c856  mov     rdi, rcx
0x18009c859  mov     cs:g_FileErrorStringID, esi
0x18009c85f  test    rdx, rdx
0x18009c862  jz      short loc_18009C87F
0x18009c864  xor     r8d, r8d
0x18009c867  lea     rcx, [rsp+2B8h+hKey]; phkResult
0x18009c86c  call    EditRegistryKey
0x18009c871  mov     cs:g_FileErrorStringID, eax
0x18009c877  test    eax, eax
0x18009c879  jnz     loc_18009C98E
0x18009c87f  mov     [rsp+2B8h+hTemplateFile], rsi; hTemplateFile
0x18009c884  lea     r9, DhcpGlobalDirSecurityAttr; lpSecurityAttributes
0x18009c88b  mov     [rsp+2B8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18009c893  mov     edx, 40000000h; dwDesiredAccess
0x18009c898  mov     r8d, 1; dwShareMode
0x18009c89e  mov     [rsp+2B8h+dwCreationDisposition], 2; dwCreationDisposition
0x18009c8a6  mov     rcx, rdi; lpFileName
0x18009c8a9  call    cs:__imp_CreateFileW
0x18009c8b0  nop     dword ptr [rax+rax+00h]
0x18009c8b5  mov     cs:hFile, rax
0x18009c8bc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009c8c0  jz      loc_18009C966
0x18009c8c6  lea     r9, [rsp+2B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18009c8cb  mov     [rsp+2B8h+NumberOfBytesWritten], esi
0x18009c8cf  mov     r8d, 2; nNumberOfBytesToWrite
0x18009c8d5  mov     cs:qword_180140E68, rsi
0x18009c8dc  lea     rdx, s_UnicodeByteOrderMark; lpBuffer
0x18009c8e3  mov     qword ptr [rsp+2B8h+dwCreationDisposition], rsi; lpOverlapped
0x18009c8e8  mov     rcx, rax; hFile
0x18009c8eb  call    cs:__imp_WriteFile
0x18009c8f2  nop     dword ptr [rax+rax+00h]
0x18009c8f7  lea     rax, [rsp+2B8h+var_268]
0x18009c8fc  mov     r8, rbx
0x18009c8ff  sub     r8, rax
0x18009c902  lea     rcx, [rsp+2B8h+var_268]
0x18009c907  mov     edx, 128h
0x18009c90c  lea     rax, [rdx+7FFFFED6h]
0x18009c913  test    rax, rax
0x18009c916  jz      short loc_18009C92F
0x18009c918  movzx   eax, word ptr [r8+rcx]
0x18009c91d  test    ax, ax
0x18009c920  jz      short loc_18009C92F
0x18009c922  mov     [rcx], ax
0x18009c925  add     rcx, 2
0x18009c929  sub     rdx, 1
0x18009c92d  jnz     short loc_18009C90C
0x18009c92f  test    rdx, rdx
0x18009c932  lea     rax, [rcx-2]
0x18009c936  lea     rdx, [rsp+2B8h+var_268]
0x18009c93b  cmovnz  rax, rcx
0x18009c93f  mov     rcx, [rsp+2B8h+hKey]
0x18009c944  mov     [rax], si
0x18009c947  call    PutBranch
0x18009c94c  call    FlushIoBuffer
0x18009c951  mov     rcx, cs:hFile; hObject
0x18009c958  call    cs:__imp_CloseHandle
0x18009c95f  nop     dword ptr [rax+rax+00h]
0x18009c964  jmp     short loc_18009C978
0x18009c966  call    cs:__imp_GetLastError
0x18009c96d  nop     dword ptr [rax+rax+00h]
0x18009c972  mov     cs:g_FileErrorStringID, eax
0x18009c978  test    rbx, rbx
0x18009c97b  jz      short loc_18009C98E
0x18009c97d  mov     rcx, [rsp+2B8h+hKey]; hKey
0x18009c982  call    cs:__imp_RegCloseKey
0x18009c989  nop     dword ptr [rax+rax+00h]
0x18009c98e  mov     eax, cs:g_FileErrorStringID
0x18009c994  mov     rcx, [rsp+2B8h+var_18]
0x18009c99c  xor     rcx, rsp; StackCookie
0x18009c99f  call    __security_check_cookie
0x18009c9a4  lea     r11, [rsp+2B8h+var_8]
0x18009c9ac  mov     rbx, [r11+20h]
0x18009c9b0  mov     rsi, [r11+28h]
0x18009c9b4  mov     rsp, r11
0x18009c9b7  pop     rdi
0x18009c9b8  retn
```
