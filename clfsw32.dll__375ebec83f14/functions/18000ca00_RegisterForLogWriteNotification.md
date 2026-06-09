# RegisterForLogWriteNotification

- ea: `0x18000ca00`
- end: `0x18000ca9f`
- name: `RegisterForLogWriteNotification`
- size: `159`
- prototype: `BOOL __stdcall(HANDLE hLog, ULONG cbThreshold, BOOL fEnable)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000ca00`
- `0x180014e00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ca7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ca7e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ca6b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ca6b`

## pseudocode

```c
BOOL __stdcall RegisterForLogWriteNotification(HANDLE hLog, ULONG cbThreshold, BOOL fEnable)
{
  DWORD v3; // ecx
  DWORD BytesReturned; // [rsp+40h] [rbp-28h] BYREF
  _DWORD InBuffer[2]; // [rsp+48h] [rbp-20h] BYREF
  __int64 v7; // [rsp+50h] [rbp-18h]

  BytesReturned = 0;
  if ( (char *)hLog - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v3 = 6;
  }
  else
  {
    if ( cbThreshold )
    {
      v7 = cbThreshold;
      InBuffer[1] = fEnable;
      InBuffer[0] = 3;
      return DeviceIoControl(hLog, 0x80077030, InBuffer, 0x10u, 0, 0, &BytesReturned, 0);
    }
    v3 = 87;
  }
  SetLastError(v3);
  return 0;
}

```

## disassembly

```asm
0x18000ca00  sub     rsp, 68h
0x18000ca04  mov     rax, cs:__security_cookie
0x18000ca0b  xor     rax, rsp
0x18000ca0e  mov     [rsp+68h+var_10], rax
0x18000ca13  xor     r9d, r9d
0x18000ca16  lea     rax, [rcx-1]
0x18000ca1a  mov     [rsp+68h+BytesReturned], r9d
0x18000ca1f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ca23  ja      short loc_18000CA79
0x18000ca25  test    edx, edx
0x18000ca27  jnz     short loc_18000CA2E
0x18000ca29  lea     ecx, [rdx+57h]; hDevice
0x18000ca2c  jmp     short loc_18000CA7E
0x18000ca2e  mov     [rsp+68h+lpOverlapped], r9; lpOverlapped
0x18000ca33  mov     eax, edx
0x18000ca35  mov     edx, 80077030h; dwIoControlCode
0x18000ca3a  mov     [rsp+68h+var_18], rax
0x18000ca3f  lea     rax, [rsp+68h+BytesReturned]
0x18000ca44  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x18000ca49  mov     [rsp+68h+nOutBufferSize], r9d; nOutBufferSize
0x18000ca4e  mov     [rsp+68h+lpOutBuffer], r9; lpOutBuffer
0x18000ca53  mov     r9d, 10h; nInBufferSize
0x18000ca59  mov     [rsp+68h+var_1C], r8d
0x18000ca5e  lea     r8, [rsp+68h+InBuffer]; lpInBuffer
0x18000ca63  mov     [rsp+68h+InBuffer], 3
0x18000ca6b  call    cs:__imp_DeviceIoControl
0x18000ca72  nop     dword ptr [rax+rax+00h]
0x18000ca77  jmp     short loc_18000CA8C
0x18000ca79  mov     ecx, 6; dwErrCode
0x18000ca7e  call    cs:__imp_SetLastError
0x18000ca85  nop     dword ptr [rax+rax+00h]
0x18000ca8a  xor     eax, eax
0x18000ca8c  mov     rcx, [rsp+68h+var_10]
0x18000ca91  xor     rcx, rsp; StackCookie
0x18000ca94  call    __security_check_cookie
0x18000ca99  add     rsp, 68h
0x18000ca9d  retn
```
