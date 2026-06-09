# ResetServerStats(void)

- ea: `0x180022ee8`
- end: `0x180022f6d`
- name: `?ResetServerStats@@YAKXZ`
- size: `133`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180013a78`

## callees

- `0x180022ee8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180022f5d`
- `KERNEL32!GetLastError` at `0x180022f5d`
- `KERNEL32!CreateFileW` at `0x180022f1f`
- `KERNEL32!CreateFileW` at `0x180022f1f`
- `KERNEL32!DeviceIoControl` at `0x180022f53`
- `KERNEL32!DeviceIoControl` at `0x180022f53`

## pseudocode

```c
__int64 ResetServerStats(void)
{
  HANDLE FileW; // rax
  unsigned int v1; // ebx
  DWORD BytesReturned; // [rsp+50h] [rbp+8h] BYREF

  BytesReturned = 0;
  FileW = CreateFileW(L"\\\\.\\NfsSvr", 0xC0000000, 0, 0, 3u, 0x1000080u, 0);
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  v1 = 0;
  if ( !DeviceIoControl(FileW, 0x10008410u, 0, 0, 0, 0, &BytesReturned, 0) )
    return GetLastError();
  return v1;
}

```

## disassembly

```asm
0x180022ee8  mov     rax, rsp
0x180022eeb  push    rbx
0x180022eec  sub     rsp, 40h
0x180022ef0  mov     qword ptr [rax-18h], 0
0x180022ef8  lea     rcx, aNfssvr; "\\\\.\\NfsSvr"
0x180022eff  mov     dword ptr [rax-20h], 1000080h
0x180022f06  xor     r9d, r9d; lpSecurityAttributes
0x180022f09  xor     r8d, r8d; dwShareMode
0x180022f0c  mov     dword ptr [rax-28h], 3
0x180022f13  mov     edx, 0C0000000h; dwDesiredAccess
0x180022f18  mov     dword ptr [rax+8], 0
0x180022f1f  call    cs:__imp_CreateFileW
0x180022f25  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022f29  jz      short loc_180022F5D
0x180022f2b  xor     ebx, ebx
0x180022f2d  lea     rcx, [rsp+48h+BytesReturned]
0x180022f32  mov     [rsp+48h+lpOverlapped], rbx; lpOverlapped
0x180022f37  xor     r9d, r9d; nInBufferSize
0x180022f3a  mov     [rsp+48h+lpBytesReturned], rcx; lpBytesReturned
0x180022f3f  xor     r8d, r8d; lpInBuffer
0x180022f42  mov     [rsp+48h+nOutBufferSize], ebx; nOutBufferSize
0x180022f46  mov     rcx, rax; hDevice
0x180022f49  mov     edx, 10008410h; dwIoControlCode
0x180022f4e  mov     [rsp+48h+lpOutBuffer], rbx; lpOutBuffer
0x180022f53  call    cs:__imp_DeviceIoControl
0x180022f59  test    eax, eax
0x180022f5b  jnz     short loc_180022F65
0x180022f5d  call    cs:__imp_GetLastError
0x180022f63  mov     ebx, eax
0x180022f65  mov     eax, ebx
0x180022f67  add     rsp, 40h
0x180022f6b  pop     rbx
0x180022f6c  retn
```
