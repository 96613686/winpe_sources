# CreateDesktopIni(ushort const *)

- ea: `0x18000beb8`
- end: `0x18000c026`
- name: `?CreateDesktopIni@@YAJPEBG@Z`
- size: `366`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800069e8`

## callees

- `0x180001840`
- `0x180006f90`
- `0x18000beb8`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfe2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000bfcf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000bfcf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000bf47`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000bf47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bffa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bffa`

## string_xrefs

- `0x18000bf71`: `[.ShellClassInfo]\nCLSID={d6277990-4c6a-11cf-8d87-00aa0060f5bf}\n`

## pseudocode

```c
signed int __fastcall CreateDesktopIni(const unsigned __int16 *a1)
{
  unsigned int v2; // r10d
  HANDLE FileW; // rdi
  signed int result; // eax
  unsigned int v5; // ebx
  signed int LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD Buffer[5]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+A0h] [rbp-60h] BYREF

  memset_0(FileName, 0, 0x20Au);
  StringCchCopyW(FileName, 0x105u, a1);
  StringCchCatW(FileName, v2, L"\\desktop.ini");
  FileW = CreateFileW(FileName, 0x40000000u, 1u, 0, 1u, 3u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    strcpy((char *)Buffer, "[.ShellClassInfo]\r\nCLSID={d6277990-4c6a-11cf-8d87-00aa0060f5bf}\r\n");
    NumberOfBytesWritten = 0;
    if ( !WriteFile(FileW, Buffer, 0x41u, &NumberOfBytesWritten, 0) || (v5 = 0, NumberOfBytesWritten != 65) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(FileW);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18000beb8  mov     [rsp-8+arg_8], rbx
0x18000bebd  mov     [rsp-8+arg_10], rdi
0x18000bec2  push    rbp
0x18000bec3  lea     rbp, [rsp-1C0h]
0x18000becb  sub     rsp, 2C0h
0x18000bed2  mov     rax, cs:__security_cookie
0x18000bed9  xor     rax, rsp
0x18000bedc  mov     [rbp+1C0h+var_10], rax
0x18000bee3  mov     rbx, rcx
0x18000bee6  xor     edx, edx; Val
0x18000bee8  lea     rcx, [rbp+1C0h+FileName]; void *
0x18000beec  mov     r8d, 20Ah; Size
0x18000bef2  call    memset_0
0x18000bef7  mov     r10d, 105h
0x18000befd  lea     rcx, [rbp+1C0h+FileName]; unsigned __int16 *
0x18000bf01  mov     edx, r10d; unsigned __int64
0x18000bf04  mov     r8, rbx; unsigned __int16 *
0x18000bf07  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bf0c  lea     r8, aDesktopIni; "\\desktop.ini"
0x18000bf13  mov     edx, r10d; unsigned __int64
0x18000bf16  lea     rcx, [rbp+1C0h+FileName]; unsigned __int16 *
0x18000bf1a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bf1f  mov     r8d, 1; dwShareMode
0x18000bf25  mov     [rsp+2C0h+hTemplateFile], 0; hTemplateFile
0x18000bf2e  mov     [rsp+2C0h+dwFlagsAndAttributes], 3; dwFlagsAndAttributes
0x18000bf36  lea     rcx, [rbp+1C0h+FileName]; lpFileName
0x18000bf3a  xor     r9d, r9d; lpSecurityAttributes
0x18000bf3d  mov     [rsp+2C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000bf42  mov     edx, 40000000h; dwDesiredAccess
0x18000bf47  call    cs:__imp_CreateFileW
0x18000bf4d  mov     rdi, rax
0x18000bf50  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000bf54  jnz     short loc_18000BF71
0x18000bf56  call    cs:__imp_GetLastError
0x18000bf5c  test    eax, eax
0x18000bf5e  jle     loc_18000C002
0x18000bf64  movzx   eax, ax
0x18000bf67  or      eax, 80070000h
0x18000bf6c  jmp     loc_18000C002
0x18000bf71  movaps  xmm0, xmmword ptr cs:aShellclassinfo; "[.ShellClassInfo]\r\nCLSID={d6277990-4c"...
0x18000bf78  lea     r9, [rsp+2C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000bf7d  movaps  xmm1, xmmword ptr cs:aShellclassinfo+10h; "]\r\nCLSID={d6277990-4c6a-11cf-8d87-00a"...
0x18000bf84  lea     rdx, [rsp+2C0h+Buffer]; lpBuffer
0x18000bf89  movzx   eax, word ptr cs:aShellclassinfo+40h; "\n"
0x18000bf90  mov     r8d, 41h ; 'A'; nNumberOfBytesToWrite
0x18000bf96  movaps  [rsp+2C0h+Buffer], xmm0
0x18000bf9b  mov     rcx, rdi; hFile
0x18000bf9e  movaps  xmm0, xmmword ptr cs:aShellclassinfo+20h; "90-4c6a-11cf-8d87-00aa0060f5bf}\r\n"
0x18000bfa5  movaps  [rsp+2C0h+var_260], xmm1
0x18000bfaa  movaps  xmm1, xmmword ptr cs:aShellclassinfo+30h; "7-00aa0060f5bf}\r\n"
0x18000bfb1  movaps  [rsp+2C0h+var_250], xmm0
0x18000bfb6  movaps  [rbp+1C0h+var_240], xmm1
0x18000bfba  mov     [rbp+1C0h+var_230], ax
0x18000bfbe  mov     [rsp+2C0h+NumberOfBytesWritten], 0
0x18000bfc6  mov     qword ptr [rsp+2C0h+dwCreationDisposition], 0; lpOverlapped
0x18000bfcf  call    cs:__imp_WriteFile
0x18000bfd5  test    eax, eax
0x18000bfd7  jz      short loc_18000BFE2
0x18000bfd9  xor     ebx, ebx
0x18000bfdb  cmp     [rsp+2C0h+NumberOfBytesWritten], 41h ; 'A'
0x18000bfe0  jz      short loc_18000BFF7
0x18000bfe2  call    cs:__imp_GetLastError
0x18000bfe8  mov     ebx, eax
0x18000bfea  test    eax, eax
0x18000bfec  jle     short loc_18000BFF7
0x18000bfee  movzx   ebx, ax
0x18000bff1  or      ebx, 80070000h
0x18000bff7  mov     rcx, rdi; hObject
0x18000bffa  call    cs:__imp_CloseHandle
0x18000c000  mov     eax, ebx
0x18000c002  mov     rcx, [rbp+1C0h+var_10]
0x18000c009  xor     rcx, rsp; StackCookie
0x18000c00c  call    __security_check_cookie
0x18000c011  lea     r11, [rsp+2C0h+var_s0]
0x18000c019  mov     rbx, [r11+18h]
0x18000c01d  mov     rdi, [r11+20h]
0x18000c021  mov     rsp, r11
0x18000c024  pop     rbp
0x18000c025  retn
```
