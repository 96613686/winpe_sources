# Dns64TcpTransportRequestPrepareReceiveSocket

- ea: `0x18006f368`
- end: `0x18006f428`
- name: `Dns64TcpTransportRequestPrepareReceiveSocket`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18006eb68`

## callees

- `0x1800355c4`
- `0x18006f368`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f3ec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f3ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f3a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f3a6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18006f405`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18006f405`
- `WS2_32!WSASocketW` at `0x18006f390`
- `WS2_32!WSASocketW` at `0x18006f390`
- `WS2_32!__imp_closesocket` at `0x18006f3cf`
- `WS2_32!__imp_closesocket` at `0x18006f3cf`

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
0x18006f368  mov     [rsp+arg_0], rbx
0x18006f36d  push    rdi
0x18006f36e  sub     rsp, 30h
0x18006f372  mov     edx, 1; type
0x18006f377  mov     rbx, rcx
0x18006f37a  mov     [rsp+38h+dwFlags], edx; dwFlags
0x18006f37e  xor     r9d, r9d; lpProtocolInfo
0x18006f381  mov     [rsp+38h+g], 0; g
0x18006f389  lea     ecx, [rdx+16h]; af
0x18006f38c  lea     r8d, [rdx+5]; protocol
0x18006f390  call    cs:__imp_WSASocketW
0x18006f397  nop     dword ptr [rax+rax+00h]
0x18006f39c  mov     [rbx+18h], rax
0x18006f3a0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006f3a4  jnz     short loc_18006F3B4
0x18006f3a6  call    cs:__imp_GetLastError
0x18006f3ad  nop     dword ptr [rax+rax+00h]
0x18006f3b2  jmp     short loc_18006F41C
0x18006f3b4  lea     r8, Dns64TcpTransportIoComplete
0x18006f3bb  mov     rdx, rax
0x18006f3be  lea     rcx, [rbx+20h]
0x18006f3c2  call    TpclCreateIo
0x18006f3c7  test    eax, eax
0x18006f3c9  jnz     short loc_18006F3E2
0x18006f3cb  mov     rcx, [rbx+18h]; s
0x18006f3cf  call    cs:__imp_closesocket
0x18006f3d6  nop     dword ptr [rax+rax+00h]
0x18006f3db  mov     eax, 1Fh
0x18006f3e0  jmp     short loc_18006F41C
0x18006f3e2  xor     r9d, r9d; lpName
0x18006f3e5  xor     r8d, r8d; bInitialState
0x18006f3e8  xor     edx, edx; bManualReset
0x18006f3ea  xor     ecx, ecx; lpEventAttributes
0x18006f3ec  call    cs:__imp_CreateEventW
0x18006f3f3  nop     dword ptr [rax+rax+00h]
0x18006f3f8  mov     [rbx+30h], rax
0x18006f3fc  test    rax, rax
0x18006f3ff  jnz     short loc_18006F413
0x18006f401  mov     rcx, [rbx+20h]; pio
0x18006f405  call    cs:__imp_CloseThreadpoolIo
0x18006f40c  nop     dword ptr [rax+rax+00h]
0x18006f411  jmp     short loc_18006F3CB
0x18006f413  mov     dword ptr [rbx+28h], 2
0x18006f41a  xor     eax, eax
0x18006f41c  mov     rbx, [rsp+38h+arg_0]
0x18006f421  add     rsp, 30h
0x18006f425  pop     rdi
0x18006f426  retn
```
