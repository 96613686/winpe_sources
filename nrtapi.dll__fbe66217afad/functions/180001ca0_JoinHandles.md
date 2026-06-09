# JoinHandles

- ea: `0x180001ca0`
- end: `0x180001d30`
- name: `JoinHandles`
- size: `144`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001ca0`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001cdb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001cdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ceb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001cfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ceb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001cfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d0b`

## pseudocode

```c
__int64 __fastcall JoinHandles(__int64 a1, void *a2)
{
  unsigned int v2; // ebx
  __int64 v4; // [rsp+50h] [rbp+8h] BYREF

  v4 = a1;
  if ( a2 && a1 )
  {
    v2 = 0;
    if ( !DeviceIoControl(a2, 0x128004u, &v4, 8u, 0, 0, 0, 0) )
    {
      if ( (int)GetLastError() > 0 )
        return (unsigned __int16)GetLastError() | 0xC0070000;
      else
        return GetLastError();
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v2;
}

```

## disassembly

```asm
0x180001ca0  mov     r11, rsp
0x180001ca3  mov     [r11+8], rcx
0x180001ca7  push    rbx
0x180001ca8  sub     rsp, 40h
0x180001cac  mov     rax, rdx
0x180001caf  test    rdx, rdx
0x180001cb2  jz      short loc_180001D22
0x180001cb4  test    rcx, rcx
0x180001cb7  jz      short loc_180001D22
0x180001cb9  xor     ebx, ebx
0x180001cbb  lea     r8, [r11+8]; lpInBuffer
0x180001cbf  mov     [r11-10h], rbx
0x180001cc3  mov     edx, 128004h; dwIoControlCode
0x180001cc8  mov     [r11-18h], rbx
0x180001ccc  mov     rcx, rax; hDevice
0x180001ccf  mov     [rsp+48h+nOutBufferSize], ebx; nOutBufferSize
0x180001cd3  lea     r9d, [rbx+8]; nInBufferSize
0x180001cd7  mov     [r11-28h], rbx
0x180001cdb  call    cs:__imp_DeviceIoControl
0x180001ce2  nop     dword ptr [rax+rax+00h]
0x180001ce7  test    eax, eax
0x180001ce9  jnz     short loc_180001D27
0x180001ceb  call    cs:__imp_GetLastError
0x180001cf2  nop     dword ptr [rax+rax+00h]
0x180001cf7  test    eax, eax
0x180001cf9  jg      short loc_180001D0B
0x180001cfb  call    cs:__imp_GetLastError
0x180001d02  nop     dword ptr [rax+rax+00h]
0x180001d07  mov     ebx, eax
0x180001d09  jmp     short loc_180001D27
0x180001d0b  call    cs:__imp_GetLastError
0x180001d12  nop     dword ptr [rax+rax+00h]
0x180001d17  movzx   ebx, ax
0x180001d1a  or      ebx, 0C0070000h
0x180001d20  jmp     short loc_180001D27
0x180001d22  mov     ebx, 0C000000Dh
0x180001d27  mov     eax, ebx
0x180001d29  add     rsp, 40h
0x180001d2d  pop     rbx
0x180001d2e  retn
```
