# ExportWinNT50RegFileFromPath

- ea: `0x18009bb68`
- end: `0x18009bcfa`
- name: `ExportWinNT50RegFileFromPath`
- size: `402`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001d098`

## callees

- `0x18009ba88`
- `0x18009bb68`
- `0x18009bd00`
- `0x18009c6f0`
- `0x1800cc9e0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18009bcc2`
- `ADVAPI32!RegCloseKey` at `0x18009bcc2`
- `KERNEL32!WriteFile` at `0x18009bc2b`
- `KERNEL32!WriteFile` at `0x18009bc2b`
- `KERNEL32!GetLastError` at `0x18009bca6`
- `KERNEL32!GetLastError` at `0x18009bca6`
- `KERNEL32!CloseHandle` at `0x18009bc98`
- `KERNEL32!CloseHandle` at `0x18009bc98`
- `KERNEL32!CreateFileW` at `0x18009bbe9`
- `KERNEL32!CreateFileW` at `0x18009bbe9`

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
      qword_18013EE88 = 0;
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
0x18009bb68  mov     [rsp+arg_10], rbx
0x18009bb6d  mov     [rsp+arg_18], rsi
0x18009bb72  push    rdi
0x18009bb73  sub     rsp, 2B0h
0x18009bb7a  mov     rax, cs:__security_cookie
0x18009bb81  xor     rax, rsp
0x18009bb84  mov     [rsp+2B8h+var_18], rax
0x18009bb8c  xor     esi, esi
0x18009bb8e  mov     rbx, rdx
0x18009bb91  mov     [rsp+2B8h+hKey], rsi
0x18009bb96  mov     rdi, rcx
0x18009bb99  mov     cs:g_FileErrorStringID, esi
0x18009bb9f  test    rdx, rdx
0x18009bba2  jz      short loc_18009BBBF
0x18009bba4  xor     r8d, r8d
0x18009bba7  lea     rcx, [rsp+2B8h+hKey]; phkResult
0x18009bbac  call    EditRegistryKey
0x18009bbb1  mov     cs:g_FileErrorStringID, eax
0x18009bbb7  test    eax, eax
0x18009bbb9  jnz     loc_18009BCCE
0x18009bbbf  mov     [rsp+2B8h+hTemplateFile], rsi; hTemplateFile
0x18009bbc4  lea     r9, DhcpGlobalDirSecurityAttr; lpSecurityAttributes
0x18009bbcb  mov     [rsp+2B8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18009bbd3  mov     edx, 40000000h; dwDesiredAccess
0x18009bbd8  mov     r8d, 1; dwShareMode
0x18009bbde  mov     [rsp+2B8h+dwCreationDisposition], 2; dwCreationDisposition
0x18009bbe6  mov     rcx, rdi; lpFileName
0x18009bbe9  call    cs:__imp_CreateFileW
0x18009bbf0  nop     dword ptr [rax+rax+00h]
0x18009bbf5  mov     cs:hFile, rax
0x18009bbfc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009bc00  jz      loc_18009BCA6
0x18009bc06  lea     r9, [rsp+2B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18009bc0b  mov     [rsp+2B8h+NumberOfBytesWritten], esi
0x18009bc0f  mov     r8d, 2; nNumberOfBytesToWrite
0x18009bc15  mov     cs:qword_18013EE88, rsi
0x18009bc1c  lea     rdx, s_UnicodeByteOrderMark; lpBuffer
0x18009bc23  mov     qword ptr [rsp+2B8h+dwCreationDisposition], rsi; lpOverlapped
0x18009bc28  mov     rcx, rax; hFile
0x18009bc2b  call    cs:__imp_WriteFile
0x18009bc32  nop     dword ptr [rax+rax+00h]
0x18009bc37  lea     rax, [rsp+2B8h+var_268]
0x18009bc3c  mov     r8, rbx
0x18009bc3f  sub     r8, rax
0x18009bc42  lea     rcx, [rsp+2B8h+var_268]
0x18009bc47  mov     edx, 128h
0x18009bc4c  lea     rax, [rdx+7FFFFED6h]
0x18009bc53  test    rax, rax
0x18009bc56  jz      short loc_18009BC6F
0x18009bc58  movzx   eax, word ptr [r8+rcx]
0x18009bc5d  test    ax, ax
0x18009bc60  jz      short loc_18009BC6F
0x18009bc62  mov     [rcx], ax
0x18009bc65  add     rcx, 2
0x18009bc69  sub     rdx, 1
0x18009bc6d  jnz     short loc_18009BC4C
0x18009bc6f  test    rdx, rdx
0x18009bc72  lea     rax, [rcx-2]
0x18009bc76  lea     rdx, [rsp+2B8h+var_268]
0x18009bc7b  cmovnz  rax, rcx
0x18009bc7f  mov     rcx, [rsp+2B8h+hKey]
0x18009bc84  mov     [rax], si
0x18009bc87  call    PutBranch
0x18009bc8c  call    FlushIoBuffer
0x18009bc91  mov     rcx, cs:hFile; hObject
0x18009bc98  call    cs:__imp_CloseHandle
0x18009bc9f  nop     dword ptr [rax+rax+00h]
0x18009bca4  jmp     short loc_18009BCB8
0x18009bca6  call    cs:__imp_GetLastError
0x18009bcad  nop     dword ptr [rax+rax+00h]
0x18009bcb2  mov     cs:g_FileErrorStringID, eax
0x18009bcb8  test    rbx, rbx
0x18009bcbb  jz      short loc_18009BCCE
0x18009bcbd  mov     rcx, [rsp+2B8h+hKey]; hKey
0x18009bcc2  call    cs:__imp_RegCloseKey
0x18009bcc9  nop     dword ptr [rax+rax+00h]
0x18009bcce  mov     eax, cs:g_FileErrorStringID
0x18009bcd4  mov     rcx, [rsp+2B8h+var_18]
0x18009bcdc  xor     rcx, rsp; StackCookie
0x18009bcdf  call    __security_check_cookie
0x18009bce4  lea     r11, [rsp+2B8h+var_8]
0x18009bcec  mov     rbx, [r11+20h]
0x18009bcf0  mov     rsi, [r11+28h]
0x18009bcf4  mov     rsp, r11
0x18009bcf7  pop     rdi
0x18009bcf8  retn
```
