# ReadLogNotification

- ea: `0x18000c460`
- end: `0x18000c4ce`
- name: `ReadLogNotification`
- size: `110`
- prototype: `BOOL __stdcall(HANDLE hLog, PCLFS_MGMT_NOTIFICATION pNotification, LPOVERLAPPED lpOverlapped)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c460`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c4ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c4ba`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000c4a7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000c4a7`

## pseudocode

```c
BOOL __stdcall ReadLogNotification(HANDLE hLog, PCLFS_MGMT_NOTIFICATION pNotification, LPOVERLAPPED lpOverlapped)
{
  DWORD v3; // ecx
  DWORD BytesReturned; // [rsp+50h] [rbp+8h] BYREF

  BytesReturned = 0;
  if ( (char *)hLog - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v3 = 6;
  }
  else
  {
    if ( pNotification )
      return DeviceIoControl(hLog, 0x80077028, 0, 0, pNotification, 0x18u, &BytesReturned, lpOverlapped);
    v3 = 87;
  }
  SetLastError(v3);
  return 0;
}

```

## disassembly

```asm
0x18000c460  sub     rsp, 48h
0x18000c464  lea     rax, [rcx-1]
0x18000c468  mov     [rsp+48h+BytesReturned], 0
0x18000c470  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c474  ja      short loc_18000C4B5
0x18000c476  test    rdx, rdx
0x18000c479  jnz     short loc_18000C480
0x18000c47b  lea     ecx, [rdx+57h]; hDevice
0x18000c47e  jmp     short loc_18000C4BA
0x18000c480  mov     [rsp+48h+lpOverlapped], r8; lpOverlapped
0x18000c485  lea     rax, [rsp+48h+BytesReturned]
0x18000c48a  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x18000c48f  xor     r9d, r9d; nInBufferSize
0x18000c492  mov     [rsp+48h+nOutBufferSize], 18h; nOutBufferSize
0x18000c49a  xor     r8d, r8d; lpInBuffer
0x18000c49d  mov     [rsp+48h+lpOutBuffer], rdx; lpOutBuffer
0x18000c4a2  mov     edx, 80077028h; dwIoControlCode
0x18000c4a7  call    cs:__imp_DeviceIoControl
0x18000c4ae  nop     dword ptr [rax+rax+00h]
0x18000c4b3  jmp     short loc_18000C4C8
0x18000c4b5  mov     ecx, 6; dwErrCode
0x18000c4ba  call    cs:__imp_SetLastError
0x18000c4c1  nop     dword ptr [rax+rax+00h]
0x18000c4c6  xor     eax, eax
0x18000c4c8  add     rsp, 48h
0x18000c4cc  retn
```
