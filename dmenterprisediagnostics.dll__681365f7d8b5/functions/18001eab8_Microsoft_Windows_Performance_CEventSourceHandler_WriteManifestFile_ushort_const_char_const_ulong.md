# Microsoft::Windows::Performance::CEventSourceHandler::WriteManifestFile(ushort const *,char const *,ulong)

- ea: `0x18001eab8`
- end: `0x18001eb7e`
- name: `?WriteManifestFile@CEventSourceHandler@Performance@Windows@Microsoft@@AEAAJPEBGPEBDK@Z`
- size: `198`
- prototype: `int(Microsoft::Windows::Performance::CEventSourceHandler *__hidden this, const unsigned __int16 *, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bd94`

## callees

- `0x18001eab8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eb66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eb66`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001eaf1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001eaf1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001eb38`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001eb38`

## pseudocode

```c
int __fastcall Microsoft::Windows::Performance::CEventSourceHandler::WriteManifestFile(
        Microsoft::Windows::Performance::CEventSourceHandler *this,
        const unsigned __int16 *a2,
        const char *a3,
        DWORD a4)
{
  HANDLE FileW; // rax
  void *v7; // rdi
  int result; // eax
  unsigned int v9; // ebx
  signed int LastError; // eax
  Microsoft::Windows::Performance::CEventSourceHandler *NumberOfBytesWritten; // [rsp+70h] [rbp+8h] BYREF

  NumberOfBytesWritten = this;
  FileW = CreateFileW(a2, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v7 = FileW;
  if ( FileW )
  {
    v9 = 0;
    LODWORD(NumberOfBytesWritten) = 0;
    if ( !WriteFile(FileW, a3, a4, (LPDWORD)&NumberOfBytesWritten, 0) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(v7);
    return v9;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18001eab8  mov     rax, rsp
0x18001eabb  mov     [rax+8], rcx
0x18001eabf  push    rbx
0x18001eac0  push    rbp
0x18001eac1  push    rsi
0x18001eac2  push    rdi
0x18001eac3  sub     rsp, 48h
0x18001eac7  mov     qword ptr [rax-38h], 0
0x18001eacf  mov     esi, r9d
0x18001ead2  mov     rbp, r8
0x18001ead5  mov     dword ptr [rax-40h], 80h
0x18001eadc  mov     rcx, rdx; lpFileName
0x18001eadf  mov     dword ptr [rax-48h], 2
0x18001eae6  xor     r9d, r9d; lpSecurityAttributes
0x18001eae9  xor     r8d, r8d; dwShareMode
0x18001eaec  mov     edx, 40000000h; dwDesiredAccess
0x18001eaf1  call    cs:__imp_CreateFileW
0x18001eaf8  nop     dword ptr [rax+rax+00h]
0x18001eafd  mov     rdi, rax
0x18001eb00  test    rax, rax
0x18001eb03  jnz     short loc_18001EB1F
0x18001eb05  call    cs:__imp_GetLastError
0x18001eb0c  nop     dword ptr [rax+rax+00h]
0x18001eb11  test    eax, eax
0x18001eb13  jle     short loc_18001EB74
0x18001eb15  movzx   eax, ax
0x18001eb18  or      eax, 80070000h
0x18001eb1d  jmp     short loc_18001EB74
0x18001eb1f  xor     ebx, ebx
0x18001eb21  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001eb26  mov     r8d, esi; nNumberOfBytesToWrite
0x18001eb29  mov     dword ptr [rsp+68h+NumberOfBytesWritten], ebx
0x18001eb2d  mov     rdx, rbp; lpBuffer
0x18001eb30  mov     [rsp+68h+lpOverlapped], rbx; lpOverlapped
0x18001eb35  mov     rcx, rdi; hFile
0x18001eb38  call    cs:__imp_WriteFile
0x18001eb3f  nop     dword ptr [rax+rax+00h]
0x18001eb44  test    eax, eax
0x18001eb46  jnz     short loc_18001EB63
0x18001eb48  call    cs:__imp_GetLastError
0x18001eb4f  nop     dword ptr [rax+rax+00h]
0x18001eb54  mov     ebx, eax
0x18001eb56  test    eax, eax
0x18001eb58  jle     short loc_18001EB63
0x18001eb5a  movzx   ebx, ax
0x18001eb5d  or      ebx, 80070000h
0x18001eb63  mov     rcx, rdi; hObject
0x18001eb66  call    cs:__imp_CloseHandle
0x18001eb6d  nop     dword ptr [rax+rax+00h]
0x18001eb72  mov     eax, ebx
0x18001eb74  add     rsp, 48h
0x18001eb78  pop     rdi
0x18001eb79  pop     rsi
0x18001eb7a  pop     rbp
0x18001eb7b  pop     rbx
0x18001eb7c  retn
```
