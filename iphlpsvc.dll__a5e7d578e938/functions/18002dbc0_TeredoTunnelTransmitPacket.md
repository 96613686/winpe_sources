# TeredoTunnelTransmitPacket

- ea: `0x18002dbc0`
- end: `0x18002dcae`
- name: `TeredoTunnelTransmitPacket`
- size: `238`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task`

## callees

- `0x18000d7c0`
- `0x18002dbc0`
- `0x18002e0d0`
- `0x18002ec50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc68`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002dc35`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002dc35`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18002dc7f`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18002dc7f`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18002dbfd`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18002dbfd`

## string_xrefs

- `0x18002dc57`: `onecoreuap\net\netio\iphlpsvc\service\io.c`
- `0x18002dc9a`: `onecoreuap\net\netio\iphlpsvc\service\io.c`

## pseudocode

```c
__int64 __fastcall TeredoTunnelTransmitPacket(__int64 *a1, __int64 a2)
{
  __int64 v2; // rbp

  v2 = *a1;
  EventWrite0(0x100000, L"Teredo tunnel transmit packet: 0x%p", a2);
  *(_DWORD *)(a2 + 288) = 1;
  if ( *(_BYTE *)(v2 + 2880) )
    TeredoReferenceIoEx(v2, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\io.c", 2694);
  StartThreadpoolIo((PTP_IO)a1[2]);
  if ( WriteFile(
         (HANDLE)a1[3],
         (LPCVOID)(a2 + 432),
         *(_DWORD *)(a2 + 488) + *(_DWORD *)(a2 + 408) + 80,
         0,
         (LPOVERLAPPED)(a2 + 256))
    || GetLastError() == 997 )
  {
    return 0;
  }
  CancelThreadpoolIo((PTP_IO)a1[2]);
  if ( *(_BYTE *)(v2 + 2880) )
    TeredoDereferenceIoEx(v2, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\io.c", 2715);
  return a2;
}

```

## disassembly

```asm
0x18002dbc0  push    rbx
0x18002dbc2  push    rbp
0x18002dbc3  push    rsi
0x18002dbc4  push    rdi
0x18002dbc5  sub     rsp, 38h
0x18002dbc9  mov     rbp, [rcx]
0x18002dbcc  mov     rbx, rdx
0x18002dbcf  mov     rdi, rcx
0x18002dbd2  mov     r8, rdx
0x18002dbd5  lea     rdx, aTeredoTunnelTr; "Teredo tunnel transmit packet: 0x%p"
0x18002dbdc  mov     ecx, 100000h
0x18002dbe1  call    EventWrite0
0x18002dbe6  mov     dword ptr [rbx+120h], 1
0x18002dbf0  cmp     byte ptr [rbp+0B40h], 0
0x18002dbf7  jnz     short loc_18002DC51
0x18002dbf9  mov     rcx, [rdi+10h]; pio
0x18002dbfd  call    cs:__imp_StartThreadpoolIo
0x18002dc04  nop     dword ptr [rax+rax+00h]
0x18002dc09  mov     r8d, [rbx+198h]
0x18002dc10  lea     r9, [rbx+100h]
0x18002dc17  mov     rcx, [rdi+18h]; hFile
0x18002dc1b  lea     rdx, [rbx+1B0h]; lpBuffer
0x18002dc22  add     r8d, 50h ; 'P'
0x18002dc26  mov     [rsp+58h+lpOverlapped], r9; lpOverlapped
0x18002dc2b  add     r8d, [rbx+1E8h]; nNumberOfBytesToWrite
0x18002dc32  xor     r9d, r9d; lpNumberOfBytesWritten
0x18002dc35  call    cs:__imp_WriteFile
0x18002dc3c  nop     dword ptr [rax+rax+00h]
0x18002dc41  test    eax, eax
0x18002dc43  jz      short loc_18002DC68
0x18002dc45  xor     eax, eax
0x18002dc47  add     rsp, 38h
0x18002dc4b  pop     rdi
0x18002dc4c  pop     rsi
0x18002dc4d  pop     rbp
0x18002dc4e  pop     rbx
0x18002dc4f  retn
0x18002dc51  mov     r8d, 0A86h
0x18002dc57  lea     rdx, aOnecoreuapNetN_22; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18002dc5e  mov     rcx, rbp
0x18002dc61  call    TeredoReferenceIoEx
0x18002dc66  jmp     short loc_18002DBF9
0x18002dc68  call    cs:__imp_GetLastError
0x18002dc6f  nop     dword ptr [rax+rax+00h]
0x18002dc74  cmp     eax, 3E5h
0x18002dc79  jz      short loc_18002DC45
0x18002dc7b  mov     rcx, [rdi+10h]; pio
0x18002dc7f  call    cs:__imp_CancelThreadpoolIo
0x18002dc86  nop     dword ptr [rax+rax+00h]
0x18002dc8b  cmp     byte ptr [rbp+0B40h], 0
0x18002dc92  jz      short loc_18002DCA9
0x18002dc94  mov     r8d, 0A9Bh
0x18002dc9a  lea     rdx, aOnecoreuapNetN_22; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18002dca1  mov     rcx, rbp
0x18002dca4  call    TeredoDereferenceIoEx
0x18002dca9  mov     rax, rbx
0x18002dcac  jmp     short loc_18002DC47
```
