# ClusterInternalIsVolumeCsv

- ea: `0x1800a9168`
- end: `0x1800a9211`
- name: `ClusterInternalIsVolumeCsv`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800a8f44`

## callees

- `0x1800a9168`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a91b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a91b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a91f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a91f5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a919d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a919d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a91ec`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a91ec`

## pseudocode

```c
__int64 __fastcall ClusterInternalIsVolumeCsv(const WCHAR *a1)
{
  HANDLE FileW; // rdi
  unsigned int v2; // ebx
  char OutBuffer; // [rsp+58h] [rbp+10h] BYREF
  DWORD BytesReturned; // [rsp+60h] [rbp+18h] BYREF

  BytesReturned = 0;
  OutBuffer = 0;
  FileW = CreateFileW(a1, 0x80u, 7u, 0, 3u, 0x80u, 0);
  v2 = 1;
  if ( FileW == (HANDLE)-1LL )
  {
    if ( GetLastError() )
      return 0;
  }
  else
  {
    DeviceIoControl(FileW, 0x560060u, 0, 0, &OutBuffer, 1u, &BytesReturned, 0);
    CloseHandle(FileW);
  }
  if ( !OutBuffer )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x1800a9168  mov     rax, rsp
0x1800a916b  mov     [rax+8], rbx
0x1800a916f  push    rdi
0x1800a9170  sub     rsp, 40h
0x1800a9174  mov     edx, 80h; dwDesiredAccess
0x1800a9179  mov     qword ptr [rax-18h], 0
0x1800a9181  mov     [rax-20h], edx
0x1800a9184  xor     r9d, r9d; lpSecurityAttributes
0x1800a9187  mov     dword ptr [rax+18h], 0
0x1800a918e  mov     byte ptr [rax+10h], 0
0x1800a9192  lea     r8d, [rdx-79h]; dwShareMode
0x1800a9196  mov     dword ptr [rax-28h], 3
0x1800a919d  call    cs:__imp_CreateFileW
0x1800a91a3  mov     rdi, rax
0x1800a91a6  mov     ebx, 1
0x1800a91ab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a91af  jnz     short loc_1800A91BD
0x1800a91b1  call    cs:__imp_GetLastError
0x1800a91b7  test    eax, eax
0x1800a91b9  jnz     short loc_1800A9202
0x1800a91bb  jmp     short loc_1800A91FB
0x1800a91bd  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1800a91c6  lea     rax, [rsp+48h+BytesReturned]
0x1800a91cb  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x1800a91d0  xor     r9d, r9d; nInBufferSize
0x1800a91d3  lea     rax, [rsp+48h+OutBuffer]
0x1800a91d8  mov     [rsp+48h+nOutBufferSize], ebx; nOutBufferSize
0x1800a91dc  xor     r8d, r8d; lpInBuffer
0x1800a91df  mov     [rsp+48h+lpOutBuffer], rax; lpOutBuffer
0x1800a91e4  mov     edx, 560060h; dwIoControlCode
0x1800a91e9  mov     rcx, rdi; hDevice
0x1800a91ec  call    cs:__imp_DeviceIoControl
0x1800a91f2  mov     rcx, rdi; hObject
0x1800a91f5  call    cs:__imp_CloseHandle
0x1800a91fb  cmp     [rsp+48h+OutBuffer], 0
0x1800a9200  jnz     short loc_1800A9204
0x1800a9202  xor     ebx, ebx
0x1800a9204  mov     eax, ebx
0x1800a9206  mov     rbx, [rsp+48h+arg_0]
0x1800a920b  add     rsp, 40h
0x1800a920f  pop     rdi
0x1800a9210  retn
```
