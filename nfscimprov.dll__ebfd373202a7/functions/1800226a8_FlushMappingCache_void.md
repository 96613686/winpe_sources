# FlushMappingCache(void)

- ea: `0x1800226a8`
- end: `0x18002274c`
- name: `?FlushMappingCache@@YAKXZ`
- size: `164`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180012690`

## callees

- `0x1800226a8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180022724`
- `KERNEL32!GetLastError` at `0x180022737`
- `KERNEL32!GetLastError` at `0x180022724`
- `KERNEL32!GetLastError` at `0x180022737`
- `KERNEL32!CloseHandle` at `0x18002272f`
- `KERNEL32!CloseHandle` at `0x18002272f`
- `KERNEL32!CreateFileW` at `0x1800226e3`
- `KERNEL32!CreateFileW` at `0x1800226e3`
- `KERNEL32!DeviceIoControl` at `0x18002271a`
- `KERNEL32!DeviceIoControl` at `0x18002271a`

## pseudocode

```c
__int64 FlushMappingCache(void)
{
  HANDLE FileW; // rdi
  DWORD LastError; // ebx
  DWORD BytesReturned; // [rsp+50h] [rbp+8h] BYREF

  BytesReturned = 0;
  FileW = CreateFileW(L"\\\\.\\NfsSvr", 0xC0000000, 0, 0, 3u, 0x1000080u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    return GetLastError();
  }
  else
  {
    LastError = 0;
    if ( !DeviceIoControl(FileW, 0x10008404u, 0, 0, 0, 0, &BytesReturned, 0) )
      LastError = GetLastError();
    CloseHandle(FileW);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800226a8  mov     rax, rsp
0x1800226ab  mov     [rax+10h], rbx
0x1800226af  push    rdi
0x1800226b0  sub     rsp, 40h
0x1800226b4  mov     qword ptr [rax-18h], 0
0x1800226bc  lea     rcx, aNfssvr; "\\\\.\\NfsSvr"
0x1800226c3  mov     dword ptr [rax-20h], 1000080h
0x1800226ca  xor     r9d, r9d; lpSecurityAttributes
0x1800226cd  xor     r8d, r8d; dwShareMode
0x1800226d0  mov     dword ptr [rax-28h], 3
0x1800226d7  mov     edx, 0C0000000h; dwDesiredAccess
0x1800226dc  mov     dword ptr [rax+8], 0
0x1800226e3  call    cs:__imp_CreateFileW
0x1800226e9  mov     rdi, rax
0x1800226ec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800226f0  jz      short loc_180022737
0x1800226f2  xor     ebx, ebx
0x1800226f4  lea     rax, [rsp+48h+BytesReturned]
0x1800226f9  mov     [rsp+48h+lpOverlapped], rbx; lpOverlapped
0x1800226fe  xor     r9d, r9d; nInBufferSize
0x180022701  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x180022706  xor     r8d, r8d; lpInBuffer
0x180022709  mov     [rsp+48h+nOutBufferSize], ebx; nOutBufferSize
0x18002270d  mov     edx, 10008404h; dwIoControlCode
0x180022712  mov     rcx, rdi; hDevice
0x180022715  mov     [rsp+48h+lpOutBuffer], rbx; lpOutBuffer
0x18002271a  call    cs:__imp_DeviceIoControl
0x180022720  test    eax, eax
0x180022722  jnz     short loc_18002272C
0x180022724  call    cs:__imp_GetLastError
0x18002272a  mov     ebx, eax
0x18002272c  mov     rcx, rdi; hObject
0x18002272f  call    cs:__imp_CloseHandle
0x180022735  jmp     short loc_18002273F
0x180022737  call    cs:__imp_GetLastError
0x18002273d  mov     ebx, eax
0x18002273f  mov     eax, ebx
0x180022741  mov     rbx, [rsp+48h+arg_8]
0x180022746  add     rsp, 40h
0x18002274a  pop     rdi
0x18002274b  retn
```
