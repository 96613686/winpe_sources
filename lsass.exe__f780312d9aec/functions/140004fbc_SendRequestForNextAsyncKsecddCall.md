# SendRequestForNextAsyncKsecddCall

- ea: `0x140004fbc`
- end: `0x14000503e`
- name: `SendRequestForNextAsyncKsecddCall`
- size: `130`
- prototype: `DWORD()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140004cb0`
- `0x14000508c`

## callees

- `0x140004fbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005012`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005012`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140005008`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140005008`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140005026`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140005026`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x140004fc7`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x140004fc7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140005031`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140005031`

## pseudocode

```c
DWORD SendRequestForNextAsyncKsecddCall()
{
  DWORD result; // eax

  while ( 1 )
  {
    StartThreadpoolIo(pio);
    result = DeviceIoControl(fl, 0x39006Au, 0, 0, &OutBuffer, 8u, 0, &Overlapped);
    if ( result )
      break;
    result = GetLastError();
    if ( result == 997 )
      break;
    CancelThreadpoolIo(pio);
    Sleep(0x7Du);
  }
  return result;
}

```

## disassembly

```asm
0x140004fbc  sub     rsp, 48h
0x140004fc0  mov     rcx, cs:pio; pio
0x140004fc7  call    cs:__imp_StartThreadpoolIo
0x140004fcd  mov     rcx, cs:fl; hDevice
0x140004fd4  lea     rax, Overlapped
0x140004fdb  mov     [rsp+48h+lpOverlapped], rax; lpOverlapped
0x140004fe0  xor     r9d, r9d; nInBufferSize
0x140004fe3  mov     [rsp+48h+lpBytesReturned], 0; lpBytesReturned
0x140004fec  lea     rax, OutBuffer
0x140004ff3  mov     [rsp+48h+nOutBufferSize], 8; nOutBufferSize
0x140004ffb  xor     r8d, r8d; lpInBuffer
0x140004ffe  mov     edx, 39006Ah; dwIoControlCode
0x140005003  mov     [rsp+48h+lpOutBuffer], rax; lpOutBuffer
0x140005008  call    cs:__imp_DeviceIoControl
0x14000500e  test    eax, eax
0x140005010  jnz     short loc_140005039
0x140005012  call    cs:__imp_GetLastError
0x140005018  cmp     eax, 3E5h
0x14000501d  jz      short loc_140005039
0x14000501f  mov     rcx, cs:pio; pio
0x140005026  call    cs:__imp_CancelThreadpoolIo
0x14000502c  mov     ecx, 7Dh ; '}'; dwMilliseconds
0x140005031  call    cs:__imp_Sleep
0x140005037  jmp     short loc_140004FC0
0x140005039  add     rsp, 48h
0x14000503d  retn
```
