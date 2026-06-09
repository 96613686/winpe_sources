# AslLogpWritePipe(void *,unsigned __int64)

- ea: `0x18006a380`
- end: `0x18006a485`
- name: `?AslLogpWritePipe@@YAXPEAX_K@Z`
- size: `261`
- prototype: `void __fastcall(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18006a9e4`

## callees

- `0x18006a380`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a3cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a3cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a46f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a46f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006a3be`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006a418`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006a3be`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006a418`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006a466`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006a466`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x18006a43d`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x18006a43d`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x18006a3e7`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x18006a3e7`

## pseudocode

```c
void __fastcall AslLogpWritePipe(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)
{
  HANDLE FileW; // rbx
  DWORD Mode; // [rsp+60h] [rbp+18h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp+20h] BYREF

  FileW = CreateFileW(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0);
  if ( FileW != (HANDLE)-1LL
    || GetLastError() == 231
    && (WaitNamedPipeW(L"\\\\.\\pipe\\GmdAslLogger", 0),
        FileW = CreateFileW(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0),
        FileW != (HANDLE)-1LL) )
  {
    Mode = 2;
    if ( SetNamedPipeHandleState(FileW, &Mode, 0, 0) )
    {
      NumberOfBytesWritten = 0;
      WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
      CloseHandle(FileW);
    }
  }
}

```

## disassembly

```asm
0x18006a380  mov     rax, rsp
0x18006a383  mov     [rax+8], rbx
0x18006a387  mov     [rax+10h], rsi
0x18006a38b  push    rdi
0x18006a38c  sub     rsp, 40h
0x18006a390  mov     qword ptr [rax-18h], 0
0x18006a398  mov     rdi, rdx
0x18006a39b  mov     rsi, rcx
0x18006a39e  mov     dword ptr [rax-20h], 0
0x18006a3a5  mov     edx, 40000000h; dwDesiredAccess
0x18006a3aa  mov     dword ptr [rax-28h], 3
0x18006a3b1  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x18006a3b8  xor     r9d, r9d; lpSecurityAttributes
0x18006a3bb  xor     r8d, r8d; dwShareMode
0x18006a3be  call    cs:__imp_CreateFileW
0x18006a3c4  mov     rbx, rax
0x18006a3c7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006a3cb  jnz     short loc_18006A427
0x18006a3cd  call    cs:__imp_GetLastError
0x18006a3d3  cmp     eax, 0E7h
0x18006a3d8  jnz     loc_18006A475
0x18006a3de  xor     edx, edx; nTimeOut
0x18006a3e0  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x18006a3e7  call    cs:__imp_WaitNamedPipeW
0x18006a3ed  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18006a3f6  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x18006a3fd  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18006a405  xor     r9d, r9d; lpSecurityAttributes
0x18006a408  xor     r8d, r8d; dwShareMode
0x18006a40b  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18006a413  mov     edx, 40000000h; dwDesiredAccess
0x18006a418  call    cs:__imp_CreateFileW
0x18006a41e  mov     rbx, rax
0x18006a421  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006a425  jz      short loc_18006A475
0x18006a427  xor     r9d, r9d; lpCollectDataTimeout
0x18006a42a  mov     [rsp+48h+Mode], 2
0x18006a432  xor     r8d, r8d; lpMaxCollectionCount
0x18006a435  lea     rdx, [rsp+48h+Mode]; lpMode
0x18006a43a  mov     rcx, rbx; hNamedPipe
0x18006a43d  call    cs:__imp_SetNamedPipeHandleState
0x18006a443  test    eax, eax
0x18006a445  jz      short loc_18006A475
0x18006a447  mov     r8d, edi; nNumberOfBytesToWrite
0x18006a44a  mov     [rsp+48h+NumberOfBytesWritten], 0
0x18006a452  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18006a457  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x18006a460  mov     rdx, rsi; lpBuffer
0x18006a463  mov     rcx, rbx; hFile
0x18006a466  call    cs:__imp_WriteFile
0x18006a46c  mov     rcx, rbx; hObject
0x18006a46f  call    cs:__imp_CloseHandle
0x18006a475  mov     rbx, [rsp+48h+arg_0]
0x18006a47a  mov     rsi, [rsp+48h+arg_8]
0x18006a47f  add     rsp, 40h
0x18006a483  pop     rdi
0x18006a484  retn
```
