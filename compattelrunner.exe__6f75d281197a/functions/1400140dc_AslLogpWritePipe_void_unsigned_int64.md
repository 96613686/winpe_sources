# AslLogpWritePipe(void *,unsigned __int64)

- ea: `0x1400140dc`
- end: `0x1400141e1`
- name: `?AslLogpWritePipe@@YAXPEAX_K@Z`
- size: `261`
- prototype: `void __fastcall(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140014870`

## callees

- `0x1400140dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014129`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014129`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400141cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400141cb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14001411a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140014174`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14001411a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140014174`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400141c2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400141c2`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x140014143`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x140014143`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x140014199`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x140014199`

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
0x1400140dc  mov     rax, rsp
0x1400140df  mov     [rax+8], rbx
0x1400140e3  mov     [rax+10h], rsi
0x1400140e7  push    rdi
0x1400140e8  sub     rsp, 40h
0x1400140ec  mov     qword ptr [rax-18h], 0
0x1400140f4  mov     rdi, rdx
0x1400140f7  mov     rsi, rcx
0x1400140fa  mov     dword ptr [rax-20h], 0
0x140014101  mov     edx, 40000000h; dwDesiredAccess
0x140014106  mov     dword ptr [rax-28h], 3
0x14001410d  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x140014114  xor     r9d, r9d; lpSecurityAttributes
0x140014117  xor     r8d, r8d; dwShareMode
0x14001411a  call    cs:__imp_CreateFileW
0x140014120  mov     rbx, rax
0x140014123  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140014127  jnz     short loc_140014183
0x140014129  call    cs:__imp_GetLastError
0x14001412f  cmp     eax, 0E7h
0x140014134  jnz     loc_1400141D1
0x14001413a  xor     edx, edx; nTimeOut
0x14001413c  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x140014143  call    cs:__imp_WaitNamedPipeW
0x140014149  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x140014152  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x140014159  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x140014161  xor     r9d, r9d; lpSecurityAttributes
0x140014164  xor     r8d, r8d; dwShareMode
0x140014167  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x14001416f  mov     edx, 40000000h; dwDesiredAccess
0x140014174  call    cs:__imp_CreateFileW
0x14001417a  mov     rbx, rax
0x14001417d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140014181  jz      short loc_1400141D1
0x140014183  xor     r9d, r9d; lpCollectDataTimeout
0x140014186  mov     [rsp+48h+Mode], 2
0x14001418e  xor     r8d, r8d; lpMaxCollectionCount
0x140014191  lea     rdx, [rsp+48h+Mode]; lpMode
0x140014196  mov     rcx, rbx; hNamedPipe
0x140014199  call    cs:__imp_SetNamedPipeHandleState
0x14001419f  test    eax, eax
0x1400141a1  jz      short loc_1400141D1
0x1400141a3  mov     r8d, edi; nNumberOfBytesToWrite
0x1400141a6  mov     [rsp+48h+NumberOfBytesWritten], 0
0x1400141ae  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400141b3  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x1400141bc  mov     rdx, rsi; lpBuffer
0x1400141bf  mov     rcx, rbx; hFile
0x1400141c2  call    cs:__imp_WriteFile
0x1400141c8  mov     rcx, rbx; hObject
0x1400141cb  call    cs:__imp_CloseHandle
0x1400141d1  mov     rbx, [rsp+48h+arg_0]
0x1400141d6  mov     rsi, [rsp+48h+arg_8]
0x1400141db  add     rsp, 40h
0x1400141df  pop     rdi
0x1400141e0  retn
```
