# EnsureACILCanReadFile(ushort const *,ushort const *)

- ea: `0x140009b50`
- end: `0x140009c41`
- name: `?EnsureACILCanReadFile@@YAJPEBG0@Z`
- size: `241`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140004e20`

## callees

- `0x140006070`
- `0x140009b50`
- `0x1400109c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140009bf4`
- `KERNEL32!CloseHandle` at `0x140009bf4`
- `KERNEL32!CreateFileW` at `0x140009bc0`
- `KERNEL32!CreateFileW` at `0x140009bc0`
- `KERNEL32!GetLastError` at `0x140009c02`
- `KERNEL32!GetLastError` at `0x140009c02`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x140009be3`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x140009be3`

## pseudocode

```c
__int64 __fastcall EnsureACILCanReadFile(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int v2; // ebx
  HANDLE FileW; // rax
  void *v4; // rdi
  signed int LastError; // eax
  WCHAR FileName[264]; // [rsp+40h] [rbp-228h] BYREF

  v2 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", a1, a2);
  if ( v2 >= 0 )
  {
    FileW = CreateFileW(FileName, 0x1F0000u, 0, 0, 3u, 0x2000000u, 0);
    v4 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v2 = SetWindowsHandleAccess(FileW, 0x1240u, 0x1200A9u);
      CloseHandle(v4);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140009b50  mov     [rsp+arg_10], rbx
0x140009b55  push    rdi
0x140009b56  sub     rsp, 260h
0x140009b5d  mov     rax, cs:__security_cookie
0x140009b64  xor     rax, rsp
0x140009b67  mov     [rsp+268h+var_18], rax
0x140009b6f  mov     qword ptr [rsp+268h+dwCreationDisposition], rdx
0x140009b74  lea     r8, aSS; "%s\\%s"
0x140009b7b  mov     r9, rcx
0x140009b7e  mov     edx, 104h; unsigned __int64
0x140009b83  lea     rcx, [rsp+268h+FileName]; unsigned __int16 *
0x140009b88  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140009b8d  mov     ebx, eax
0x140009b8f  test    eax, eax
0x140009b91  js      loc_140009C1D
0x140009b97  mov     [rsp+268h+hTemplateFile], 0; hTemplateFile
0x140009ba0  lea     rcx, [rsp+268h+FileName]; lpFileName
0x140009ba5  mov     [rsp+268h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x140009bad  xor     r9d, r9d; lpSecurityAttributes
0x140009bb0  xor     r8d, r8d; dwShareMode
0x140009bb3  mov     [rsp+268h+dwCreationDisposition], 3; dwCreationDisposition
0x140009bbb  mov     edx, 1F0000h; dwDesiredAccess
0x140009bc0  call    cs:__imp_CreateFileW
0x140009bc7  nop     dword ptr [rax+rax+00h]
0x140009bcc  mov     rdi, rax
0x140009bcf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140009bd3  jz      short loc_140009C02
0x140009bd5  mov     edx, 1240h
0x140009bda  mov     r8d, 1200A9h
0x140009be0  mov     rcx, rax
0x140009be3  call    cs:__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z; SetWindowsHandleAccess(void *,ulong,ulong)
0x140009bea  nop     dword ptr [rax+rax+00h]
0x140009bef  mov     rcx, rdi; hObject
0x140009bf2  mov     ebx, eax
0x140009bf4  call    cs:__imp_CloseHandle
0x140009bfb  nop     dword ptr [rax+rax+00h]
0x140009c00  jmp     short loc_140009C1D
0x140009c02  call    cs:__imp_GetLastError
0x140009c09  nop     dword ptr [rax+rax+00h]
0x140009c0e  mov     ebx, eax
0x140009c10  test    eax, eax
0x140009c12  jle     short loc_140009C1D
0x140009c14  movzx   ebx, ax
0x140009c17  or      ebx, 80070000h
0x140009c1d  mov     eax, ebx
0x140009c1f  mov     rcx, [rsp+268h+var_18]
0x140009c27  xor     rcx, rsp; StackCookie
0x140009c2a  call    __security_check_cookie
0x140009c2f  mov     rbx, [rsp+268h+arg_10]
0x140009c37  add     rsp, 260h
0x140009c3e  pop     rdi
0x140009c3f  retn
```
