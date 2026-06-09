# SendIoctlToDriver

- ea: `0x1400065b0`
- end: `0x140006643`
- name: `SendIoctlToDriver`
- size: `147`
- prototype: `__int64 __fastcall(DWORD dwIoControlCode)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140005f30`

## callees

- `0x1400065b0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000662b`
- `KERNEL32!CloseHandle` at `0x14000662b`
- `KERNEL32!DeviceIoControl` at `0x14000661d`
- `KERNEL32!DeviceIoControl` at `0x14000661d`
- `KERNEL32!CreateFileW` at `0x1400065eb`
- `KERNEL32!CreateFileW` at `0x1400065eb`

## pseudocode

```c
__int64 __fastcall SendIoctlToDriver(DWORD dwIoControlCode)
{
  unsigned int v1; // ebx
  HANDLE FileW; // rdi
  DWORD BytesReturned; // [rsp+58h] [rbp+10h] BYREF

  v1 = 0;
  BytesReturned = 0;
  FileW = CreateFileW(L"\\\\.\\NfsRdr", 0xC0000000, 0, 0, 3u, 0x1000080u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    LOBYTE(v1) = DeviceIoControl(FileW, dwIoControlCode, 0, 0, 0, 0, &BytesReturned, 0);
    CloseHandle(FileW);
  }
  return v1;
}

```

## disassembly

```asm
0x1400065b0  mov     rax, rsp
0x1400065b3  mov     [rax+8], rbx
0x1400065b7  mov     [rax+18h], rsi
0x1400065bb  push    rdi
0x1400065bc  sub     rsp, 40h
0x1400065c0  xor     ebx, ebx
0x1400065c2  mov     esi, ecx
0x1400065c4  mov     [rax-18h], rbx
0x1400065c8  lea     rcx, FileName; "\\\\.\\NfsRdr"
0x1400065cf  mov     dword ptr [rax-20h], 1000080h
0x1400065d6  xor     r9d, r9d; lpSecurityAttributes
0x1400065d9  xor     r8d, r8d; dwShareMode
0x1400065dc  mov     dword ptr [rax-28h], 3
0x1400065e3  mov     edx, 0C0000000h; dwDesiredAccess
0x1400065e8  mov     [rax+10h], ebx
0x1400065eb  call    cs:__imp_CreateFileW
0x1400065f1  mov     rdi, rax
0x1400065f4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400065f8  jz      short loc_140006631
0x1400065fa  mov     [rsp+48h+lpOverlapped], rbx; lpOverlapped
0x1400065ff  lea     rax, [rsp+48h+BytesReturned]
0x140006604  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x140006609  xor     r9d, r9d; nInBufferSize
0x14000660c  mov     [rsp+48h+nOutBufferSize], ebx; nOutBufferSize
0x140006610  xor     r8d, r8d; lpInBuffer
0x140006613  mov     edx, esi; dwIoControlCode
0x140006615  mov     [rsp+48h+lpOutBuffer], rbx; lpOutBuffer
0x14000661a  mov     rcx, rdi; hDevice
0x14000661d  call    cs:__imp_DeviceIoControl
0x140006623  test    eax, eax
0x140006625  mov     rcx, rdi; hObject
0x140006628  setnz   bl
0x14000662b  call    cs:__imp_CloseHandle
0x140006631  mov     rsi, [rsp+48h+arg_10]
0x140006636  mov     eax, ebx
0x140006638  mov     rbx, [rsp+48h+arg_0]
0x14000663d  add     rsp, 40h
0x140006641  pop     rdi
0x140006642  retn
```
