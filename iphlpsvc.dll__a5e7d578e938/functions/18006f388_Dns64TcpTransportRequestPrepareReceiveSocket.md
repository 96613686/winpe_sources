# Dns64TcpTransportRequestPrepareReceiveSocket

- ea: `0x18006f388`
- end: `0x18006f448`
- name: `Dns64TcpTransportRequestPrepareReceiveSocket`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18006eb88`

## callees

- `0x1800355d4`
- `0x18006f388`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f40c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f40c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f3c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f3c6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18006f425`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18006f425`
- `WS2_32!WSASocketW` at `0x18006f3b0`
- `WS2_32!WSASocketW` at `0x18006f3b0`
- `WS2_32!__imp_closesocket` at `0x18006f3ef`
- `WS2_32!__imp_closesocket` at `0x18006f3ef`

## pseudocode

```c
DWORD __fastcall Dns64TcpTransportRequestPrepareReceiveSocket(__int64 a1)
{
  SOCKET v2; // rax
  HANDLE EventW; // rax

  v2 = WSASocketW(23, 1, 6, 0, 0, 1u);
  *(_QWORD *)(a1 + 24) = v2;
  if ( v2 == -1 )
    return GetLastError();
  if ( !(unsigned int)TpclCreateIo(a1 + 32, v2, Dns64TcpTransportIoComplete) )
    goto LABEL_4;
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 48) = EventW;
  if ( !EventW )
  {
    CloseThreadpoolIo(*(PTP_IO *)(a1 + 32));
LABEL_4:
    closesocket(*(_QWORD *)(a1 + 24));
    return 31;
  }
  *(_DWORD *)(a1 + 40) = 2;
  return 0;
}

```

## disassembly

```asm
0x18006f388  mov     [rsp+arg_0], rbx
0x18006f38d  push    rdi
0x18006f38e  sub     rsp, 30h
0x18006f392  mov     edx, 1; type
0x18006f397  mov     rbx, rcx
0x18006f39a  mov     [rsp+38h+dwFlags], edx; dwFlags
0x18006f39e  xor     r9d, r9d; lpProtocolInfo
0x18006f3a1  mov     [rsp+38h+g], 0; g
0x18006f3a9  lea     ecx, [rdx+16h]; af
0x18006f3ac  lea     r8d, [rdx+5]; protocol
0x18006f3b0  call    cs:__imp_WSASocketW
0x18006f3b7  nop     dword ptr [rax+rax+00h]
0x18006f3bc  mov     [rbx+18h], rax
0x18006f3c0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006f3c4  jnz     short loc_18006F3D4
0x18006f3c6  call    cs:__imp_GetLastError
0x18006f3cd  nop     dword ptr [rax+rax+00h]
0x18006f3d2  jmp     short loc_18006F43C
0x18006f3d4  lea     r8, Dns64TcpTransportIoComplete
0x18006f3db  mov     rdx, rax
0x18006f3de  lea     rcx, [rbx+20h]
0x18006f3e2  call    TpclCreateIo
0x18006f3e7  test    eax, eax
0x18006f3e9  jnz     short loc_18006F402
0x18006f3eb  mov     rcx, [rbx+18h]; s
0x18006f3ef  call    cs:__imp_closesocket
0x18006f3f6  nop     dword ptr [rax+rax+00h]
0x18006f3fb  mov     eax, 1Fh
0x18006f400  jmp     short loc_18006F43C
0x18006f402  xor     r9d, r9d; lpName
0x18006f405  xor     r8d, r8d; bInitialState
0x18006f408  xor     edx, edx; bManualReset
0x18006f40a  xor     ecx, ecx; lpEventAttributes
0x18006f40c  call    cs:__imp_CreateEventW
0x18006f413  nop     dword ptr [rax+rax+00h]
0x18006f418  mov     [rbx+30h], rax
0x18006f41c  test    rax, rax
0x18006f41f  jnz     short loc_18006F433
0x18006f421  mov     rcx, [rbx+20h]; pio
0x18006f425  call    cs:__imp_CloseThreadpoolIo
0x18006f42c  nop     dword ptr [rax+rax+00h]
0x18006f431  jmp     short loc_18006F3EB
0x18006f433  mov     dword ptr [rbx+28h], 2
0x18006f43a  xor     eax, eax
0x18006f43c  mov     rbx, [rsp+38h+arg_0]
0x18006f441  add     rsp, 30h
0x18006f445  pop     rdi
0x18006f446  retn
```
