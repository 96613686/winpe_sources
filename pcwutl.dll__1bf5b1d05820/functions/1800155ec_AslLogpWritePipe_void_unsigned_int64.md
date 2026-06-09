# AslLogpWritePipe(void *,unsigned __int64)

- ea: `0x1800155ec`
- end: `0x1800156f1`
- name: `?AslLogpWritePipe@@YAXPEAX_K@Z`
- size: `261`
- prototype: `void __fastcall(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180016880`

## callees

- `0x1800155ec`

## import_xrefs

- `KERNEL32!SetNamedPipeHandleState` at `0x1800156a9`
- `KERNEL32!SetNamedPipeHandleState` at `0x1800156a9`
- `KERNEL32!WriteFile` at `0x1800156d2`
- `KERNEL32!WriteFile` at `0x1800156d2`
- `KERNEL32!WaitNamedPipeW` at `0x180015653`
- `KERNEL32!WaitNamedPipeW` at `0x180015653`
- `KERNEL32!GetLastError` at `0x180015639`
- `KERNEL32!GetLastError` at `0x180015639`
- `KERNEL32!CloseHandle` at `0x1800156db`
- `KERNEL32!CloseHandle` at `0x1800156db`
- `KERNEL32!CreateFileW` at `0x18001562a`
- `KERNEL32!CreateFileW` at `0x180015684`
- `KERNEL32!CreateFileW` at `0x18001562a`
- `KERNEL32!CreateFileW` at `0x180015684`

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
0x1800155ec  mov     rax, rsp
0x1800155ef  mov     [rax+8], rbx
0x1800155f3  mov     [rax+10h], rsi
0x1800155f7  push    rdi
0x1800155f8  sub     rsp, 40h
0x1800155fc  mov     qword ptr [rax-18h], 0
0x180015604  mov     rdi, rdx
0x180015607  mov     rsi, rcx
0x18001560a  mov     dword ptr [rax-20h], 0
0x180015611  mov     edx, 40000000h; dwDesiredAccess
0x180015616  mov     dword ptr [rax-28h], 3
0x18001561d  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x180015624  xor     r9d, r9d; lpSecurityAttributes
0x180015627  xor     r8d, r8d; dwShareMode
0x18001562a  call    cs:__imp_CreateFileW
0x180015630  mov     rbx, rax
0x180015633  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015637  jnz     short loc_180015693
0x180015639  call    cs:__imp_GetLastError
0x18001563f  cmp     eax, 0E7h
0x180015644  jnz     loc_1800156E1
0x18001564a  xor     edx, edx; nTimeOut
0x18001564c  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x180015653  call    cs:__imp_WaitNamedPipeW
0x180015659  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180015662  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x180015669  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180015671  xor     r9d, r9d; lpSecurityAttributes
0x180015674  xor     r8d, r8d; dwShareMode
0x180015677  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18001567f  mov     edx, 40000000h; dwDesiredAccess
0x180015684  call    cs:__imp_CreateFileW
0x18001568a  mov     rbx, rax
0x18001568d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015691  jz      short loc_1800156E1
0x180015693  xor     r9d, r9d; lpCollectDataTimeout
0x180015696  mov     [rsp+48h+Mode], 2
0x18001569e  xor     r8d, r8d; lpMaxCollectionCount
0x1800156a1  lea     rdx, [rsp+48h+Mode]; lpMode
0x1800156a6  mov     rcx, rbx; hNamedPipe
0x1800156a9  call    cs:__imp_SetNamedPipeHandleState
0x1800156af  test    eax, eax
0x1800156b1  jz      short loc_1800156E1
0x1800156b3  mov     r8d, edi; nNumberOfBytesToWrite
0x1800156b6  mov     [rsp+48h+NumberOfBytesWritten], 0
0x1800156be  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800156c3  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x1800156cc  mov     rdx, rsi; lpBuffer
0x1800156cf  mov     rcx, rbx; hFile
0x1800156d2  call    cs:__imp_WriteFile
0x1800156d8  mov     rcx, rbx; hObject
0x1800156db  call    cs:__imp_CloseHandle
0x1800156e1  mov     rbx, [rsp+48h+arg_0]
0x1800156e6  mov     rsi, [rsp+48h+arg_8]
0x1800156eb  add     rsp, 40h
0x1800156ef  pop     rdi
0x1800156f0  retn
```
