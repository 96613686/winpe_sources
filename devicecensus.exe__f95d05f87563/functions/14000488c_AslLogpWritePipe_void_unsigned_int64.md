# AslLogpWritePipe(void *,unsigned __int64)

- ea: `0x14000488c`
- end: `0x14000498f`
- name: `?AslLogpWritePipe@@YAXPEAX_K@Z`
- size: `259`
- prototype: `void __fastcall(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1400050a0`

## callees

- `0x1400023a2`
- `0x1400023ae`
- `0x14000488c`

## import_xrefs

- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x1400048f2`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x1400048f2`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x140004948`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x140004948`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400048ca`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140004923`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400048ca`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140004923`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140004971`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140004971`

## pseudocode

```c
void __fastcall AslLogpWritePipe(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)
{
  HANDLE FileW; // rbx
  DWORD Mode; // [rsp+60h] [rbp+18h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp+20h] BYREF

  FileW = CreateFileW(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0);
  if ( FileW != (HANDLE)-1LL
    || GetLastError_0() == 231
    && (WaitNamedPipeW(L"\\\\.\\pipe\\GmdAslLogger", 0),
        FileW = CreateFileW(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0),
        FileW != (HANDLE)-1LL) )
  {
    Mode = 2;
    if ( SetNamedPipeHandleState(FileW, &Mode, 0, 0) )
    {
      NumberOfBytesWritten = 0;
      WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
      CloseHandle_0(FileW);
    }
  }
}

```

## disassembly

```asm
0x14000488c  mov     rax, rsp
0x14000488f  mov     [rax+8], rbx
0x140004893  mov     [rax+10h], rsi
0x140004897  push    rdi
0x140004898  sub     rsp, 40h
0x14000489c  mov     qword ptr [rax-18h], 0
0x1400048a4  mov     rdi, rdx
0x1400048a7  mov     rsi, rcx
0x1400048aa  mov     dword ptr [rax-20h], 0
0x1400048b1  mov     edx, 40000000h; dwDesiredAccess
0x1400048b6  mov     dword ptr [rax-28h], 3
0x1400048bd  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x1400048c4  xor     r9d, r9d; lpSecurityAttributes
0x1400048c7  xor     r8d, r8d; dwShareMode
0x1400048ca  call    cs:__imp_CreateFileW
0x1400048d0  mov     rbx, rax
0x1400048d3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400048d7  jnz     short loc_140004932
0x1400048d9  call    GetLastError_0
0x1400048de  cmp     eax, 0E7h
0x1400048e3  jnz     loc_14000497F
0x1400048e9  xor     edx, edx; nTimeOut
0x1400048eb  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x1400048f2  call    cs:__imp_WaitNamedPipeW
0x1400048f8  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x140004901  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x140004908  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x140004910  xor     r9d, r9d; lpSecurityAttributes
0x140004913  xor     r8d, r8d; dwShareMode
0x140004916  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x14000491e  mov     edx, 40000000h; dwDesiredAccess
0x140004923  call    cs:__imp_CreateFileW
0x140004929  mov     rbx, rax
0x14000492c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140004930  jz      short loc_14000497F
0x140004932  xor     r9d, r9d; lpCollectDataTimeout
0x140004935  mov     [rsp+48h+Mode], 2
0x14000493d  xor     r8d, r8d; lpMaxCollectionCount
0x140004940  lea     rdx, [rsp+48h+Mode]; lpMode
0x140004945  mov     rcx, rbx; hNamedPipe
0x140004948  call    cs:__imp_SetNamedPipeHandleState
0x14000494e  test    eax, eax
0x140004950  jz      short loc_14000497F
0x140004952  mov     r8d, edi; nNumberOfBytesToWrite
0x140004955  mov     [rsp+48h+NumberOfBytesWritten], 0
0x14000495d  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140004962  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x14000496b  mov     rdx, rsi; lpBuffer
0x14000496e  mov     rcx, rbx; hFile
0x140004971  call    cs:__imp_WriteFile
0x140004977  mov     rcx, rbx; hObject
0x14000497a  call    CloseHandle_0
0x14000497f  mov     rbx, [rsp+48h+arg_0]
0x140004984  mov     rsi, [rsp+48h+arg_8]
0x140004989  add     rsp, 40h
0x14000498d  pop     rdi
0x14000498e  retn
```
