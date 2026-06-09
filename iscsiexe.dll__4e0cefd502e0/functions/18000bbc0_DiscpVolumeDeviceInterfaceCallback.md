# DiscpVolumeDeviceInterfaceCallback

- ea: `0x18000bbc0`
- end: `0x18000bc9f`
- name: `DiscpVolumeDeviceInterfaceCallback`
- size: `223`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18000bbc0`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x18000bc13`
- `ISCSIUM!DiscpAllocMemory` at `0x18000bc13`
- `ISCSIUM!DiscpFreeMemory` at `0x18000bc62`
- `ISCSIUM!DiscpFreeMemory` at `0x18000bc62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc8a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000bc50`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000bc50`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000bbff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000bbff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bc82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bc82`

## pseudocode

```c
__int64 __fastcall DiscpVolumeDeviceInterfaceCallback(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  const WCHAR *v5; // rcx
  HANDLE FileW; // rdi
  void *lpOutBuffer; // rax
  DWORD LastError; // ebx
  DWORD BytesReturned; // [rsp+68h] [rbp+20h] BYREF

  v5 = (const WCHAR *)(*(_QWORD *)(a4 + 80) + 4LL);
  BytesReturned = 0;
  FileW = CreateFileW(v5, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    return GetLastError();
  }
  else
  {
    lpOutBuffer = (void *)DiscpAllocMemory(24608);
    *(_QWORD *)(a4 + 88) = lpOutBuffer;
    if ( lpOutBuffer )
    {
      if ( DeviceIoControl(FileW, 0x560000u, 0, 0, lpOutBuffer, 0x6020u, &BytesReturned, 0) )
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
0x18000bbc0  mov     rax, rsp
0x18000bbc3  mov     [rax+8], rbx
0x18000bbc7  push    rdi
0x18000bbc8  sub     rsp, 40h
0x18000bbcc  mov     rcx, [r9+50h]
0x18000bbd0  mov     rbx, r9
0x18000bbd3  mov     qword ptr [rax-18h], 0
0x18000bbdb  mov     r8d, 3; dwShareMode
0x18000bbe1  mov     dword ptr [rax-20h], 80h
0x18000bbe8  add     rcx, 4; lpFileName
0x18000bbec  xor     r9d, r9d; lpSecurityAttributes
0x18000bbef  mov     dword ptr [rax+20h], 0
0x18000bbf6  mov     edx, 80000000h; dwDesiredAccess
0x18000bbfb  mov     [rax-28h], r8d
0x18000bbff  call    cs:__imp_CreateFileW
0x18000bc05  mov     rdi, rax
0x18000bc08  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000bc0c  jz      short loc_18000BC8A
0x18000bc0e  mov     ecx, 6020h
0x18000bc13  call    cs:__imp_DiscpAllocMemory
0x18000bc19  mov     [rbx+58h], rax
0x18000bc1d  test    rax, rax
0x18000bc20  jz      short loc_18000BC7A
0x18000bc22  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x18000bc2b  lea     rcx, [rsp+48h+BytesReturned]
0x18000bc30  mov     [rsp+48h+lpBytesReturned], rcx; lpBytesReturned
0x18000bc35  xor     r9d, r9d; nInBufferSize
0x18000bc38  mov     [rsp+48h+nOutBufferSize], 6020h; nOutBufferSize
0x18000bc40  mov     rcx, rdi; hDevice
0x18000bc43  xor     r8d, r8d; lpInBuffer
0x18000bc46  mov     [rsp+48h+lpOutBuffer], rax; lpOutBuffer
0x18000bc4b  mov     edx, 560000h; dwIoControlCode
0x18000bc50  call    cs:__imp_DeviceIoControl
0x18000bc56  test    eax, eax
0x18000bc58  jz      short loc_18000BC5E
0x18000bc5a  xor     ebx, ebx
0x18000bc5c  jmp     short loc_18000BC7F
0x18000bc5e  mov     rcx, [rbx+58h]
0x18000bc62  call    cs:__imp_DiscpFreeMemory
0x18000bc68  mov     qword ptr [rbx+58h], 0
0x18000bc70  call    cs:__imp_GetLastError
0x18000bc76  mov     ebx, eax
0x18000bc78  jmp     short loc_18000BC7F
0x18000bc7a  mov     ebx, 8
0x18000bc7f  mov     rcx, rdi; hObject
0x18000bc82  call    cs:__imp_CloseHandle
0x18000bc88  jmp     short loc_18000BC92
0x18000bc8a  call    cs:__imp_GetLastError
0x18000bc90  mov     ebx, eax
0x18000bc92  mov     eax, ebx
0x18000bc94  mov     rbx, [rsp+48h+arg_0]
0x18000bc99  add     rsp, 40h
0x18000bc9d  pop     rdi
0x18000bc9e  retn
```
