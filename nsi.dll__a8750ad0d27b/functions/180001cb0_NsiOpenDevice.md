# NsiOpenDevice

- ea: `0x180001cb0`
- end: `0x180001d21`
- name: `NsiOpenDevice`
- size: `113`
- prototype: `DWORD()`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800015d0`
- `0x1800016b0`

## callees

- `0x180001cb0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001cf0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001cf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d11`

## pseudocode

```c
DWORD NsiOpenDevice()
{
  HANDLE FileW; // rax

  if ( g_NsiAsyncDeviceHandle != (HANDLE)-1LL )
    return 0;
  FileW = CreateFileW(L"\\\\.\\Nsi", 0, 3u, 0, 3u, 0x40000000u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_NsiAsyncDeviceHandle, (signed __int64)FileW, -1) != -1 )
      CloseHandle(FileW);
    return 0;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x180001cb0  sub     rsp, 48h
0x180001cb4  cmp     cs:g_NsiAsyncDeviceHandle, 0FFFFFFFFFFFFFFFFh
0x180001cbc  jz      short loc_180001CC5
0x180001cbe  xor     eax, eax
0x180001cc0  add     rsp, 48h
0x180001cc4  retn
0x180001cc5  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180001cce  lea     rcx, FileName; "\\\\.\\Nsi"
0x180001cd5  mov     [rsp+48h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180001cdd  xor     r9d, r9d; lpSecurityAttributes
0x180001ce0  xor     edx, edx; dwDesiredAccess
0x180001ce2  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180001cea  mov     r8d, 3; dwShareMode
0x180001cf0  call    cs:__imp_CreateFileW
0x180001cf6  mov     rcx, rax; hObject
0x180001cf9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001cfd  jz      short loc_180001D19
0x180001cff  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001d06  lock cmpxchg cs:g_NsiAsyncDeviceHandle, rcx
0x180001d0f  jz      short loc_180001CBE
0x180001d11  call    cs:__imp_CloseHandle
0x180001d17  jmp     short loc_180001CBE
0x180001d19  call    cs:__imp_GetLastError
0x180001d1f  jmp     short loc_180001CC0
```
