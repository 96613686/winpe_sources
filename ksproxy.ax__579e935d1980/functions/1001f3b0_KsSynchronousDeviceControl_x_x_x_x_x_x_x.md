# KsSynchronousDeviceControl(x,x,x,x,x,x,x)

- ea: `0x1001f3b0`
- end: `0x1001f4b4`
- name: `_KsSynchronousDeviceControl@28`
- size: `260`
- prototype: `int __stdcall(HANDLE hDevice, DWORD dwIoControlCode, LPVOID lpInBuffer, DWORD nInBufferSize, LPVOID lpOutBuffer, DWORD nOutBufferSize, LPDWORD lpBytesReturned)`
- caller_count: `84`
- callee_count: `1`
- tags: ``

## callers

- `0x10008430`
- `0x10009eb3`
- `0x10009f00`
- `0x10009f60`
- `0x1000a516`
- `0x1000b1eb`
- `0x1000b860`
- `0x1000b910`
- `0x1000ba10`
- `0x1000bb10`
- `0x1000bb90`
- `0x1000c030`
- `0x1000c200`
- `0x1000c350`
- `0x1000c4a0`
- `0x1000c5f0`
- `0x1000c740`
- `0x1000c970`
- `0x1000cc20`
- `0x1000ce10`
- `0x1000cf60`
- `0x1000dda5`
- `0x1000def7`
- `0x1000e05b`
- `0x1000e356`
- `0x1000e6b0`
- `0x1000e700`
- `0x1000e730`
- `0x1000eb20`
- `0x1000eb50`
- `0x1000eb80`
- `0x10012080`
- `0x10012c50`
- `0x10012d00`
- `0x10013940`
- `0x10013970`
- `0x100139a0`
- `0x100147ad`
- `0x10016250`
- `0x10017e60`
- `0x10017e90`
- `0x10017ec0`
- `0x100193e0`
- `0x10019490`
- `0x10019540`
- `0x100195f0`
- `0x1001e8ef`
- `0x1001f4ba`
- `0x1001f57f`
- `0x1001f846`

## callees

- `0x1001f3b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1001f3ec`
- `KERNEL32!GetLastError` at `0x1001f429`
- `KERNEL32!GetLastError` at `0x1001f459`
- `KERNEL32!GetLastError` at `0x1001f3ec`
- `KERNEL32!GetLastError` at `0x1001f429`
- `KERNEL32!GetLastError` at `0x1001f459`
- `KERNEL32!CreateEventW` at `0x1001f3df`
- `KERNEL32!CreateEventW` at `0x1001f3df`
- `KERNEL32!CloseHandle` at `0x1001f49e`
- `KERNEL32!CloseHandle` at `0x1001f49e`
- `KERNEL32!GetOverlappedResult` at `0x1001f44f`
- `KERNEL32!GetOverlappedResult` at `0x1001f44f`
- `KERNEL32!DeviceIoControl` at `0x1001f41f`
- `KERNEL32!DeviceIoControl` at `0x1001f41f`

## pseudocode

```c
int __stdcall KsSynchronousDeviceControl(
        HANDLE hDevice,
        DWORD dwIoControlCode,
        LPVOID lpInBuffer,
        DWORD nInBufferSize,
        LPVOID lpOutBuffer,
        DWORD nOutBufferSize,
        LPDWORD lpBytesReturned)
{
  signed int v7; // eax
  unsigned int v8; // ecx
  signed int LastError; // eax
  unsigned int v11; // esi
  signed int v12; // eax
  _OVERLAPPED Overlapped; // [esp+8h] [ebp-14h] BYREF

  if ( !hDevice || hDevice == (HANDLE)-1 )
    return -2147024890;
  memset(&Overlapped, 0, 16);
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( Overlapped.hEvent )
  {
    if ( DeviceIoControl(
           hDevice,
           dwIoControlCode,
           lpInBuffer,
           nInBufferSize,
           lpOutBuffer,
           nOutBufferSize,
           lpBytesReturned,
           &Overlapped) )
    {
      switch ( Overlapped.Internal )
      {
        case 0x101u:
          v11 = -2147024875;
          goto LABEL_22;
        case 0x105u:
          v11 = -2147024662;
          goto LABEL_22;
        case 0x107u:
          v11 = -2147023595;
          goto LABEL_22;
      }
    }
    else
    {
      LastError = GetLastError();
      v11 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v11 = LastError;
      if ( v11 != -2147023899 )
        goto LABEL_22;
      if ( !GetOverlappedResult(hDevice, &Overlapped, lpBytesReturned, 1) )
      {
        v12 = GetLastError();
        v11 = (unsigned __int16)v12 | 0x80070000;
        if ( v12 <= 0 )
          v11 = v12;
        goto LABEL_22;
      }
    }
    v11 = 0;
LABEL_22:
    CloseHandle(Overlapped.hEvent);
    return v11;
  }
  v7 = GetLastError();
  v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v7 <= 0 )
    return v7;
  return v8;
}

```

## disassembly

```asm
0x1001f3b0  mov     edi, edi
0x1001f3b2  push    ebp
0x1001f3b3  mov     ebp, esp
0x1001f3b5  sub     esp, 14h
0x1001f3b8  push    ebx
0x1001f3b9  mov     ebx, [ebp+hDevice]
0x1001f3bc  push    edi
0x1001f3bd  test    ebx, ebx
0x1001f3bf  jz      loc_1001F4A9
0x1001f3c5  cmp     ebx, 0FFFFFFFFh
0x1001f3c8  jz      loc_1001F4A9
0x1001f3ce  xor     eax, eax
0x1001f3d0  lea     edi, [ebp+Overlapped]
0x1001f3d3  stosd
0x1001f3d4  stosd
0x1001f3d5  stosd
0x1001f3d6  stosd
0x1001f3d7  stosd
0x1001f3d8  xor     edi, edi
0x1001f3da  push    edi; lpName
0x1001f3db  push    edi; bInitialState
0x1001f3dc  push    1; bManualReset
0x1001f3de  push    edi; lpEventAttributes
0x1001f3df  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x1001f3e5  mov     [ebp+Overlapped.hEvent], eax
0x1001f3e8  test    eax, eax
0x1001f3ea  jnz     short loc_1001F407
0x1001f3ec  call    ds:__imp__GetLastError@0; GetLastError()
0x1001f3f2  movzx   ecx, ax
0x1001f3f5  or      ecx, 80070000h
0x1001f3fb  test    eax, eax
0x1001f3fd  cmovle  ecx, eax
0x1001f400  mov     eax, ecx
0x1001f402  jmp     loc_1001F4AE
0x1001f407  push    esi
0x1001f408  lea     eax, [ebp+Overlapped]
0x1001f40b  push    eax; lpOverlapped
0x1001f40c  push    [ebp+lpBytesReturned]; lpBytesReturned
0x1001f40f  push    [ebp+nOutBufferSize]; nOutBufferSize
0x1001f412  push    [ebp+lpOutBuffer]; lpOutBuffer
0x1001f415  push    [ebp+nInBufferSize]; nInBufferSize
0x1001f418  push    [ebp+lpInBuffer]; lpInBuffer
0x1001f41b  push    [ebp+dwIoControlCode]; dwIoControlCode
0x1001f41e  push    ebx; hDevice
0x1001f41f  call    ds:__imp__DeviceIoControl@32; DeviceIoControl(x,x,x,x,x,x,x,x)
0x1001f425  test    eax, eax
0x1001f427  jnz     short loc_1001F46F
0x1001f429  call    ds:__imp__GetLastError@0; GetLastError()
0x1001f42f  movzx   esi, ax
0x1001f432  or      esi, 80070000h
0x1001f438  test    eax, eax
0x1001f43a  cmovle  esi, eax
0x1001f43d  cmp     esi, 800703E5h
0x1001f443  jnz     short loc_1001F49B
0x1001f445  push    1; bWait
0x1001f447  push    [ebp+lpBytesReturned]; lpNumberOfBytesTransferred
0x1001f44a  lea     eax, [ebp+Overlapped]
0x1001f44d  push    eax; lpOverlapped
0x1001f44e  push    ebx; hFile
0x1001f44f  call    ds:__imp__GetOverlappedResult@16; GetOverlappedResult(x,x,x,x)
0x1001f455  test    eax, eax
0x1001f457  jnz     short loc_1001F484
0x1001f459  call    ds:__imp__GetLastError@0; GetLastError()
0x1001f45f  movzx   esi, ax
0x1001f462  or      esi, 80070000h
0x1001f468  test    eax, eax
0x1001f46a  cmovle  esi, eax
0x1001f46d  jmp     short loc_1001F49B
0x1001f46f  mov     eax, [ebp+Overlapped.Internal]
0x1001f472  sub     eax, 101h
0x1001f477  jz      short loc_1001F496
0x1001f479  sub     eax, 4
0x1001f47c  jz      short loc_1001F48F
0x1001f47e  dec     eax
0x1001f47f  sub     eax, 1
0x1001f482  jz      short loc_1001F488
0x1001f484  mov     esi, edi
0x1001f486  jmp     short loc_1001F49B
0x1001f488  mov     esi, 80070515h
0x1001f48d  jmp     short loc_1001F49B
0x1001f48f  mov     esi, 800700EAh
0x1001f494  jmp     short loc_1001F49B
0x1001f496  mov     esi, 80070015h
0x1001f49b  push    [ebp+Overlapped.hEvent]; hObject
0x1001f49e  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1001f4a4  mov     eax, esi
0x1001f4a6  pop     esi
0x1001f4a7  jmp     short loc_1001F4AE
0x1001f4a9  mov     eax, 80070006h
0x1001f4ae  pop     edi
0x1001f4af  pop     ebx
0x1001f4b0  leave
0x1001f4b1  retn    1Ch
```
