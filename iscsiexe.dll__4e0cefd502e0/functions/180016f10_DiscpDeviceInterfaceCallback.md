# DiscpDeviceInterfaceCallback

- ea: `0x180016f10`
- end: `0x180016ff0`
- name: `DiscpDeviceInterfaceCallback`
- size: `224`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180016f10`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x180016f64`
- `ISCSIUM!DiscpAllocMemory` at `0x180016f64`
- `ISCSIUM!DiscpFreeMemory` at `0x180016fb3`
- `ISCSIUM!DiscpFreeMemory` at `0x180016fb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016fc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016fc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016fdb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180016fa1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180016fa1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016f50`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016f50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016fd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016fd3`

## pseudocode

```c
__int64 __fastcall DiscpDeviceInterfaceCallback(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rcx
  HANDLE FileW; // rdi
  void *lpOutBuffer; // rax
  DWORD LastError; // ebx
  DWORD BytesReturned; // [rsp+68h] [rbp+20h] BYREF

  v4 = *(_QWORD *)(a4 + 80);
  BytesReturned = 0;
  FileW = CreateFileW((LPCWSTR)(v4 + 4), 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    return GetLastError();
  }
  else
  {
    lpOutBuffer = (void *)DiscpAllocMemory(12);
    *(_QWORD *)(a4 + 88) = lpOutBuffer;
    if ( lpOutBuffer )
    {
      if ( DeviceIoControl(FileW, 0x2D1080u, 0, 0, lpOutBuffer, 0xCu, &BytesReturned, 0) )
      {
        LastError = 0;
      }
      else
      {
        DiscpFreeMemory(*(_QWORD *)(a4 + 88));
        *(_QWORD *)(a4 + 88) = 0;
        LastError = GetLastError();
      }
    }
    else
    {
      LastError = 8;
    }
    CloseHandle(FileW);
  }
  return LastError;
}

```

## disassembly

```asm
0x180016f10  mov     rax, rsp
0x180016f13  mov     [rax+8], rbx
0x180016f17  push    rdi
0x180016f18  sub     rsp, 40h
0x180016f1c  mov     rcx, [r9+50h]
0x180016f20  mov     rbx, r9
0x180016f23  mov     qword ptr [rax-18h], 0
0x180016f2b  xor     r9d, r9d; lpSecurityAttributes
0x180016f2e  mov     dword ptr [rax-20h], 80h
0x180016f35  add     rcx, 4; lpFileName
0x180016f39  mov     edx, 80000000h; dwDesiredAccess
0x180016f3e  mov     dword ptr [rax+20h], 0
0x180016f45  mov     dword ptr [rax-28h], 3
0x180016f4c  lea     r8d, [r9+1]; dwShareMode
0x180016f50  call    cs:__imp_CreateFileW
0x180016f56  mov     rdi, rax
0x180016f59  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016f5d  jz      short loc_180016FDB
0x180016f5f  mov     ecx, 0Ch
0x180016f64  call    cs:__imp_DiscpAllocMemory
0x180016f6a  mov     [rbx+58h], rax
0x180016f6e  test    rax, rax
0x180016f71  jz      short loc_180016FCB
0x180016f73  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180016f7c  lea     rcx, [rsp+48h+BytesReturned]
0x180016f81  mov     [rsp+48h+lpBytesReturned], rcx; lpBytesReturned
0x180016f86  xor     r9d, r9d; nInBufferSize
0x180016f89  mov     [rsp+48h+nOutBufferSize], 0Ch; nOutBufferSize
0x180016f91  mov     rcx, rdi; hDevice
0x180016f94  xor     r8d, r8d; lpInBuffer
0x180016f97  mov     [rsp+48h+lpOutBuffer], rax; lpOutBuffer
0x180016f9c  mov     edx, 2D1080h; dwIoControlCode
0x180016fa1  call    cs:__imp_DeviceIoControl
0x180016fa7  test    eax, eax
0x180016fa9  jz      short loc_180016FAF
0x180016fab  xor     ebx, ebx
0x180016fad  jmp     short loc_180016FD0
0x180016faf  mov     rcx, [rbx+58h]
0x180016fb3  call    cs:__imp_DiscpFreeMemory
0x180016fb9  mov     qword ptr [rbx+58h], 0
0x180016fc1  call    cs:__imp_GetLastError
0x180016fc7  mov     ebx, eax
0x180016fc9  jmp     short loc_180016FD0
0x180016fcb  mov     ebx, 8
0x180016fd0  mov     rcx, rdi; hObject
0x180016fd3  call    cs:__imp_CloseHandle
0x180016fd9  jmp     short loc_180016FE3
0x180016fdb  call    cs:__imp_GetLastError
0x180016fe1  mov     ebx, eax
0x180016fe3  mov     eax, ebx
0x180016fe5  mov     rbx, [rsp+48h+arg_0]
0x180016fea  add     rsp, 40h
0x180016fee  pop     rdi
0x180016fef  retn
```
