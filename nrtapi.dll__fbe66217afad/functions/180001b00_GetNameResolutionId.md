# GetNameResolutionId

- ea: `0x180001b00`
- end: `0x180001bab`
- name: `GetNameResolutionId`
- size: `171`
- prototype: `__int64 __fastcall(void *, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001b00`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001b46`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001b46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b76`

## pseudocode

```c
__int64 __fastcall GetNameResolutionId(void *a1, _QWORD *a2)
{
  unsigned int v3; // ebx
  DWORD v5; // [rsp+50h] [rbp+8h] BYREF

  v5 = 0;
  if ( !a1 || !a2 )
  {
    v3 = -1073741811;
LABEL_10:
    *a2 = 0;
    return v3;
  }
  v3 = 0;
  if ( !DeviceIoControl(a1, 0x124000u, 0, 0, a2, 8u, &v5, 0) )
  {
    v3 = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
    if ( (v3 & 0x80000000) != 0 )
      goto LABEL_10;
  }
  return v3;
}

```

## disassembly

```asm
0x180001b00  mov     r11, rsp
0x180001b03  mov     [r11+10h], rbx
0x180001b07  push    rdi
0x180001b08  sub     rsp, 40h
0x180001b0c  mov     [rsp+48h+arg_0], 0
0x180001b14  mov     rdi, rdx
0x180001b17  test    rcx, rcx
0x180001b1a  jz      short loc_180001B91
0x180001b1c  test    rdx, rdx
0x180001b1f  jz      short loc_180001B91
0x180001b21  lea     rax, [r11+8]
0x180001b25  xor     ebx, ebx
0x180001b27  mov     [r11-10h], rbx
0x180001b2b  xor     r9d, r9d; nInBufferSize
0x180001b2e  mov     [r11-18h], rax
0x180001b32  xor     r8d, r8d; lpInBuffer
0x180001b35  mov     [rsp+48h+nOutBufferSize], 8; nOutBufferSize
0x180001b3d  mov     [r11-28h], rdx
0x180001b41  mov     edx, 124000h; dwIoControlCode
0x180001b46  call    cs:__imp_DeviceIoControl
0x180001b4d  nop     dword ptr [rax+rax+00h]
0x180001b52  test    eax, eax
0x180001b54  jnz     short loc_180001B9D
0x180001b56  call    cs:__imp_GetLastError
0x180001b5d  nop     dword ptr [rax+rax+00h]
0x180001b62  test    eax, eax
0x180001b64  jg      short loc_180001B76
0x180001b66  call    cs:__imp_GetLastError
0x180001b6d  nop     dword ptr [rax+rax+00h]
0x180001b72  mov     ebx, eax
0x180001b74  jmp     short loc_180001B8B
0x180001b76  call    cs:__imp_GetLastError
0x180001b7d  nop     dword ptr [rax+rax+00h]
0x180001b82  movzx   ebx, ax
0x180001b85  or      ebx, 0C0070000h
0x180001b8b  test    ebx, ebx
0x180001b8d  jns     short loc_180001B9D
0x180001b8f  jmp     short loc_180001B96
0x180001b91  mov     ebx, 0C000000Dh
0x180001b96  mov     qword ptr [rdi], 0
0x180001b9d  mov     eax, ebx
0x180001b9f  mov     rbx, [rsp+48h+arg_8]
0x180001ba4  add     rsp, 40h
0x180001ba8  pop     rdi
0x180001ba9  retn
```
