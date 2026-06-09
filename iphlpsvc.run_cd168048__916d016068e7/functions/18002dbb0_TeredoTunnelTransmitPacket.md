# TeredoTunnelTransmitPacket

- ea: `0x18002dbb0`
- end: `0x18002dc9e`
- name: `TeredoTunnelTransmitPacket`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task`

## callees

- `0x18000d7b0`
- `0x18002dbb0`
- `0x18002e0c0`
- `0x18002ec40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc58`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002dc25`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002dc25`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18002dc6f`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18002dc6f`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18002dbed`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18002dbed`

## string_xrefs

- `0x18002dc47`: `onecoreuap\net\netio\iphlpsvc\service\io.c`
- `0x18002dc8a`: `onecoreuap\net\netio\iphlpsvc\service\io.c`

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
0x18002dbb0  push    rbx
0x18002dbb2  push    rbp
0x18002dbb3  push    rsi
0x18002dbb4  push    rdi
0x18002dbb5  sub     rsp, 38h
0x18002dbb9  mov     rbp, [rcx]
0x18002dbbc  mov     rbx, rdx
0x18002dbbf  mov     rdi, rcx
0x18002dbc2  mov     r8, rdx
0x18002dbc5  lea     rdx, aTeredoTunnelTr; "Teredo tunnel transmit packet: 0x%p"
0x18002dbcc  mov     ecx, 100000h
0x18002dbd1  call    EventWrite0
0x18002dbd6  mov     dword ptr [rbx+120h], 1
0x18002dbe0  cmp     byte ptr [rbp+0B40h], 0
0x18002dbe7  jnz     short loc_18002DC41
0x18002dbe9  mov     rcx, [rdi+10h]; pio
0x18002dbed  call    cs:__imp_StartThreadpoolIo
0x18002dbf4  nop     dword ptr [rax+rax+00h]
0x18002dbf9  mov     r8d, [rbx+198h]
0x18002dc00  lea     r9, [rbx+100h]
0x18002dc07  mov     rcx, [rdi+18h]; hFile
0x18002dc0b  lea     rdx, [rbx+1B0h]; lpBuffer
0x18002dc12  add     r8d, 50h ; 'P'
0x18002dc16  mov     [rsp+58h+lpOverlapped], r9; lpOverlapped
0x18002dc1b  add     r8d, [rbx+1E8h]; nNumberOfBytesToWrite
0x18002dc22  xor     r9d, r9d; lpNumberOfBytesWritten
0x18002dc25  call    cs:__imp_WriteFile
0x18002dc2c  nop     dword ptr [rax+rax+00h]
0x18002dc31  test    eax, eax
0x18002dc33  jz      short loc_18002DC58
0x18002dc35  xor     eax, eax
0x18002dc37  add     rsp, 38h
0x18002dc3b  pop     rdi
0x18002dc3c  pop     rsi
0x18002dc3d  pop     rbp
0x18002dc3e  pop     rbx
0x18002dc3f  retn
0x18002dc41  mov     r8d, 0A86h
0x18002dc47  lea     rdx, aOnecoreuapNetN_22; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18002dc4e  mov     rcx, rbp
0x18002dc51  call    TeredoReferenceIoEx
0x18002dc56  jmp     short loc_18002DBE9
0x18002dc58  call    cs:__imp_GetLastError
0x18002dc5f  nop     dword ptr [rax+rax+00h]
0x18002dc64  cmp     eax, 3E5h
0x18002dc69  jz      short loc_18002DC35
0x18002dc6b  mov     rcx, [rdi+10h]; pio
0x18002dc6f  call    cs:__imp_CancelThreadpoolIo
0x18002dc76  nop     dword ptr [rax+rax+00h]
0x18002dc7b  cmp     byte ptr [rbp+0B40h], 0
0x18002dc82  jz      short loc_18002DC99
0x18002dc84  mov     r8d, 0A9Bh
0x18002dc8a  lea     rdx, aOnecoreuapNetN_22; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18002dc91  mov     rcx, rbp
0x18002dc94  call    TeredoDereferenceIoEx
0x18002dc99  mov     rax, rbx
0x18002dc9c  jmp     short loc_18002DC37
```
