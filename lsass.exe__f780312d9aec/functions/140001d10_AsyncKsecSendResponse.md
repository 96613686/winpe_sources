# AsyncKsecSendResponse

- ea: `0x140001d10`
- end: `0x140001d7d`
- name: `AsyncKsecSendResponse`
- size: `109`
- prototype: `__int64 __fastcall(LPVOID lpInBuffer, DWORD nInBufferSize)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000481c`

## callees

- `0x140001d10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001d55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001d55`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140001d4b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140001d4b`

## pseudocode

```c
__int64 __fastcall AsyncKsecSendResponse(LPVOID lpInBuffer, DWORD nInBufferSize)
{
  unsigned int v2; // ebx
  signed int LastError; // eax

  if ( !lpInBuffer || !nInBufferSize )
    return 3221225485LL;
  v2 = 0;
  if ( !DeviceIoControl(fl, 0x39006Fu, lpInBuffer, nInBufferSize, 0, 0, 0, 0) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0xC0070000;
  }
  return v2;
}

```

## disassembly

```asm
0x140001d10  sub     rsp, 48h
0x140001d14  test    rcx, rcx
0x140001d17  jz      short loc_140001D73
0x140001d19  test    edx, edx
0x140001d1b  jz      short loc_140001D73
0x140001d1d  xor     eax, eax
0x140001d1f  mov     [rsp+48h+var_8], rbx
0x140001d24  mov     [rsp+48h+lpOverlapped], rax; lpOverlapped
0x140001d29  mov     r9d, edx; nInBufferSize
0x140001d2c  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x140001d31  mov     r8, rcx; lpInBuffer
0x140001d34  mov     rcx, cs:fl; hDevice
0x140001d3b  mov     edx, 39006Fh; dwIoControlCode
0x140001d40  mov     [rsp+48h+nOutBufferSize], eax; nOutBufferSize
0x140001d44  mov     ebx, eax
0x140001d46  mov     [rsp+48h+lpOutBuffer], rax; lpOutBuffer
0x140001d4b  call    cs:__imp_DeviceIoControl
0x140001d51  test    eax, eax
0x140001d53  jnz     short loc_140001D6A
0x140001d55  call    cs:__imp_GetLastError
0x140001d5b  mov     ebx, eax
0x140001d5d  test    eax, eax
0x140001d5f  jle     short loc_140001D6A
0x140001d61  movzx   ebx, ax
0x140001d64  or      ebx, 0C0070000h
0x140001d6a  mov     eax, ebx
0x140001d6c  mov     rbx, [rsp+48h+var_8]
0x140001d71  jmp     short loc_140001D78
0x140001d73  mov     eax, 0C000000Dh
0x140001d78  add     rsp, 48h
0x140001d7c  retn
```
