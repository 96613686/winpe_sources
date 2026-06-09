# DiscpRescanInitiator

- ea: `0x18000b2dc`
- end: `0x18000b3bf`
- name: `DiscpRescanInitiator`
- size: `227`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ae70`

## callees

- `0x18000629c`
- `0x18000b2dc`

## import_xrefs

- `ISCSIUM!DiscpFreeMemory` at `0x18000b3a7`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b3a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b37c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b38f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b37c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b38f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000b372`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000b372`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b335`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b335`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b387`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b387`

## pseudocode

```c
__int64 __fastcall DiscpRescanInitiator(__int64 a1)
{
  DWORD InitiatorInstance; // ebx
  __int64 v2; // rdi
  HANDLE FileW; // rsi
  DWORD BytesReturned; // [rsp+58h] [rbp+10h] BYREF
  __int64 v6; // [rsp+60h] [rbp+18h] BYREF

  BytesReturned = 0;
  v6 = 0;
  InitiatorInstance = DiscpFindInitiatorInstance(a1, &v6);
  if ( !InitiatorInstance )
  {
    v2 = v6;
    FileW = CreateFileW(*(LPCWSTR *)(v6 + 48), 0x80000000, 3u, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      InitiatorInstance = GetLastError();
    }
    else
    {
      if ( !DeviceIoControl(FileW, 0x4101Cu, 0, 0, 0, 0, &BytesReturned, 0) )
        InitiatorInstance = GetLastError();
      CloseHandle(FileW);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 16), 0xFFFFFFFF) == 1 )
      DiscpFreeMemory(v2);
  }
  return InitiatorInstance;
}

```

## disassembly

```asm
0x18000b2dc  mov     rax, rsp
0x18000b2df  mov     [rax+8], rbx
0x18000b2e3  mov     [rax+20h], rsi
0x18000b2e7  push    rdi
0x18000b2e8  sub     rsp, 40h
0x18000b2ec  lea     rdx, [rax+18h]
0x18000b2f0  mov     dword ptr [rax+10h], 0
0x18000b2f7  mov     qword ptr [rax+18h], 0
0x18000b2ff  call    DiscpFindInitiatorInstance
0x18000b304  mov     ebx, eax
0x18000b306  test    eax, eax
0x18000b308  jnz     loc_18000B3AD
0x18000b30e  mov     rdi, [rsp+48h+arg_10]
0x18000b313  lea     r8d, [rax+3]; dwShareMode
0x18000b317  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000b320  xor     r9d, r9d; lpSecurityAttributes
0x18000b323  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18000b327  mov     edx, 80000000h; dwDesiredAccess
0x18000b32c  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000b331  mov     rcx, [rdi+30h]; lpFileName
0x18000b335  call    cs:__imp_CreateFileW
0x18000b33b  mov     rsi, rax
0x18000b33e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b342  jz      short loc_18000B38F
0x18000b344  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x18000b34d  lea     rax, [rsp+48h+BytesReturned]
0x18000b352  mov     [rsp+48h+hTemplateFile], rax; lpBytesReturned
0x18000b357  xor     r9d, r9d; nInBufferSize
0x18000b35a  mov     [rsp+48h+dwFlagsAndAttributes], ebx; nOutBufferSize
0x18000b35e  xor     r8d, r8d; lpInBuffer
0x18000b361  mov     edx, 4101Ch; dwIoControlCode
0x18000b366  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOutBuffer
0x18000b36f  mov     rcx, rsi; hDevice
0x18000b372  call    cs:__imp_DeviceIoControl
0x18000b378  test    eax, eax
0x18000b37a  jnz     short loc_18000B384
0x18000b37c  call    cs:__imp_GetLastError
0x18000b382  mov     ebx, eax
0x18000b384  mov     rcx, rsi; hObject
0x18000b387  call    cs:__imp_CloseHandle
0x18000b38d  jmp     short loc_18000B397
0x18000b38f  call    cs:__imp_GetLastError
0x18000b395  mov     ebx, eax
0x18000b397  or      eax, 0FFFFFFFFh
0x18000b39a  lock xadd [rdi+10h], eax
0x18000b39f  cmp     eax, 1
0x18000b3a2  jnz     short loc_18000B3AD
0x18000b3a4  mov     rcx, rdi
0x18000b3a7  call    cs:__imp_DiscpFreeMemory
0x18000b3ad  mov     rsi, [rsp+48h+arg_18]
0x18000b3b2  mov     eax, ebx
0x18000b3b4  mov     rbx, [rsp+48h+arg_0]
0x18000b3b9  add     rsp, 40h
0x18000b3bd  pop     rdi
0x18000b3be  retn
```
