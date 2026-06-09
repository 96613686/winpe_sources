# AslLogpWritePipe(void *,unsigned __int64)

- ea: `0x180008d4c`
- end: `0x180008e4c`
- name: `?AslLogpWritePipe@@YAXPEAX_K@Z`
- size: `256`
- prototype: `void __fastcall(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800092ac`

## callees

- `0x1800081f6`
- `0x180008202`
- `0x18000826e`
- `0x18000827a`
- `0x180008d4c`

## import_xrefs

- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x180008db1`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x180008db1`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x180008e06`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x180008e06`

## pseudocode

```c
void __fastcall AslLogpWritePipe(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)
{
  HANDLE FileW_0; // rbx
  DWORD Mode; // [rsp+60h] [rbp+18h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp+20h] BYREF

  FileW_0 = CreateFileW_0(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0);
  if ( FileW_0 != (HANDLE)-1LL
    || GetLastError_0() == 231
    && (WaitNamedPipeW(L"\\\\.\\pipe\\GmdAslLogger", 0),
        FileW_0 = CreateFileW_0(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0),
        FileW_0 != (HANDLE)-1LL) )
  {
    Mode = 2;
    if ( SetNamedPipeHandleState(FileW_0, &Mode, 0, 0) )
    {
      NumberOfBytesWritten = 0;
      WriteFile_0(FileW_0, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
      CloseHandle_0(FileW_0);
    }
  }
}

```

## disassembly

```asm
0x180008d4c  mov     rax, rsp
0x180008d4f  mov     [rax+8], rbx
0x180008d53  mov     [rax+10h], rsi
0x180008d57  push    rdi
0x180008d58  sub     rsp, 40h
0x180008d5c  mov     qword ptr [rax-18h], 0
0x180008d64  mov     rdi, rdx
0x180008d67  mov     rsi, rcx
0x180008d6a  mov     dword ptr [rax-20h], 0
0x180008d71  mov     edx, 40000000h; dwDesiredAccess
0x180008d76  mov     dword ptr [rax-28h], 3
0x180008d7d  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x180008d84  xor     r9d, r9d; lpSecurityAttributes
0x180008d87  xor     r8d, r8d; dwShareMode
0x180008d8a  call    CreateFileW_0
0x180008d8f  mov     rbx, rax
0x180008d92  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008d96  jnz     short loc_180008DF0
0x180008d98  call    GetLastError_0
0x180008d9d  cmp     eax, 0E7h
0x180008da2  jnz     loc_180008E3C
0x180008da8  xor     edx, edx; nTimeOut
0x180008daa  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x180008db1  call    cs:__imp_WaitNamedPipeW
0x180008db7  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180008dc0  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x180008dc7  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180008dcf  xor     r9d, r9d; lpSecurityAttributes
0x180008dd2  xor     r8d, r8d; dwShareMode
0x180008dd5  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180008ddd  mov     edx, 40000000h; dwDesiredAccess
0x180008de2  call    CreateFileW_0
0x180008de7  mov     rbx, rax
0x180008dea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008dee  jz      short loc_180008E3C
0x180008df0  xor     r9d, r9d; lpCollectDataTimeout
0x180008df3  mov     [rsp+48h+Mode], 2
0x180008dfb  xor     r8d, r8d; lpMaxCollectionCount
0x180008dfe  lea     rdx, [rsp+48h+Mode]; lpMode
0x180008e03  mov     rcx, rbx; hNamedPipe
0x180008e06  call    cs:__imp_SetNamedPipeHandleState
0x180008e0c  test    eax, eax
0x180008e0e  jz      short loc_180008E3C
0x180008e10  mov     r8d, edi; nNumberOfBytesToWrite
0x180008e13  mov     [rsp+48h+NumberOfBytesWritten], 0
0x180008e1b  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180008e20  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x180008e29  mov     rdx, rsi; lpBuffer
0x180008e2c  mov     rcx, rbx; hFile
0x180008e2f  call    WriteFile_0
0x180008e34  mov     rcx, rbx; hObject
0x180008e37  call    CloseHandle_0
0x180008e3c  mov     rbx, [rsp+48h+arg_0]
0x180008e41  mov     rsi, [rsp+48h+arg_8]
0x180008e46  add     rsp, 40h
0x180008e4a  pop     rdi
0x180008e4b  retn
```
