# TSPI_providerCreateLineDevice

- ea: `0x180007680`
- end: `0x180007748`
- name: `TSPI_providerCreateLineDevice`
- size: `200`
- prototype: `LONG __stdcall(DWORD_PTR dwTempID, DWORD dwDeviceID)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001400`
- `0x180007680`
- `0x180007df8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000770c`
- `KERNEL32!GetLastError` at `0x18000770c`
- `KERNEL32!DeviceIoControl` at `0x1800076fc`
- `KERNEL32!DeviceIoControl` at `0x1800076fc`

## string_xrefs

- `0x1800076a2`: `providerCreateLineDevice: tempID(%x), deviceID(%x)`
- `0x180007718`: `providerCreateLineDevice: failed(%ld) to create`

## pseudocode

```c
LONG __stdcall TSPI_providerCreateLineDevice(DWORD_PTR dwTempID, DWORD dwDeviceID)
{
  DWORD LastError; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-28h] BYREF
  DWORD_PTR OutBuffer; // [rsp+48h] [rbp-20h] BYREF
  DWORD v6; // [rsp+50h] [rbp-18h]
  int v7; // [rsp+54h] [rbp-14h]

  OutBuffer = dwTempID;
  v6 = dwDeviceID;
  BytesReturned = 0;
  v7 = 0;
  TspLog(8, "providerCreateLineDevice: tempID(%x), deviceID(%x)", dwTempID, dwDeviceID);
  if ( DeviceIoControl(ghDriverSync, 0x8FFF23D4, &OutBuffer, 0x10u, &OutBuffer, 0x10u, &BytesReturned, 0) )
    return 0;
  LastError = GetLastError();
  TspLog(1, "providerCreateLineDevice: failed(%ld) to create", LastError);
  return -2147483576;
}

```

## disassembly

```asm
0x180007680  sub     rsp, 68h
0x180007684  mov     rax, cs:__security_cookie
0x18000768b  xor     rax, rsp
0x18000768e  mov     [rsp+68h+var_10], rax
0x180007693  mov     [rsp+68h+OutBuffer], rcx
0x180007698  mov     r9d, edx
0x18000769b  mov     [rsp+68h+var_18], edx
0x18000769f  mov     r8, rcx
0x1800076a2  lea     rdx, aProvidercreate_0; "providerCreateLineDevice: tempID(%x), d"...
0x1800076a9  mov     [rsp+68h+BytesReturned], 0
0x1800076b1  mov     ecx, 8
0x1800076b6  mov     [rsp+68h+var_14], 0
0x1800076be  call    TspLog
0x1800076c3  mov     rcx, cs:ghDriverSync; hDevice
0x1800076ca  lea     rax, [rsp+68h+BytesReturned]
0x1800076cf  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1800076d8  lea     r8, [rsp+68h+OutBuffer]; lpInBuffer
0x1800076dd  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x1800076e2  mov     r9d, 10h; nInBufferSize
0x1800076e8  lea     rax, [rsp+68h+OutBuffer]
0x1800076ed  mov     [rsp+68h+nOutBufferSize], r9d; nOutBufferSize
0x1800076f2  mov     edx, 8FFF23D4h; dwIoControlCode
0x1800076f7  mov     [rsp+68h+lpOutBuffer], rax; lpOutBuffer
0x1800076fc  call    cs:__imp_DeviceIoControl
0x180007703  nop     dword ptr [rax+rax+00h]
0x180007708  test    eax, eax
0x18000770a  jnz     short loc_180007733
0x18000770c  call    cs:__imp_GetLastError
0x180007713  nop     dword ptr [rax+rax+00h]
0x180007718  lea     rdx, aProvidercreate; "providerCreateLineDevice: failed(%ld) t"...
0x18000771f  mov     ecx, 1
0x180007724  mov     r8d, eax
0x180007727  call    TspLog
0x18000772c  mov     eax, 80000048h
0x180007731  jmp     short loc_180007735
0x180007733  xor     eax, eax
0x180007735  mov     rcx, [rsp+68h+var_10]
0x18000773a  xor     rcx, rsp; StackCookie
0x18000773d  call    __security_check_cookie
0x180007742  add     rsp, 68h
0x180007746  retn
```
