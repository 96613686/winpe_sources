# TeredoPrimaryTransmitPacket

- ea: `0x1800265d0`
- end: `0x180026758`
- name: `TeredoPrimaryTransmitPacket`
- size: `392`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000d7c0`
- `0x1800265d0`
- `0x18003aad4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180026702`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180026702`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180026696`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180026696`
- `WS2_32!WSASendTo` at `0x180026647`
- `WS2_32!WSASendTo` at `0x1800266db`
- `WS2_32!WSASendTo` at `0x180026647`
- `WS2_32!WSASendTo` at `0x1800266db`
- `WS2_32!__imp_WSAGetLastError` at `0x18002667f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800266eb`
- `WS2_32!__imp_WSAGetLastError` at `0x18002667f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800266eb`

## pseudocode

```c
__int64 __fastcall TeredoPrimaryTransmitPacket(__int64 a1, __int64 a2)
{
  int v4; // ecx
  int v5; // r8d
  int v7; // ecx
  int v8; // r8d
  DWORD NumberOfBytesSent; // [rsp+70h] [rbp+8h] BYREF

  NumberOfBytesSent = 0;
  EventWrite0(0x100000, L"Teredo primary transmit packet: 0x%p", a2);
  *(_DWORD *)(a2 + 288) = 1;
  if ( WSASendTo(
         *(_QWORD *)(a1 + 24),
         (LPWSABUF)(a2 + 408),
         1u,
         &NumberOfBytesSent,
         0,
         (const struct sockaddr *)(a2 + 376),
         16,
         0,
         0) != -1 )
  {
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
      McTemplateU0qzbr0_EventWriteTransfer(
        v4,
        (unsigned int)EVENT_IPHLPSVC_ETW_TEREDO_SEND_PACKET,
        v5,
        (unsigned int)L"Primary Socket",
        a2 + 376);
    return a2;
  }
  if ( WSAGetLastError() != 10035 )
    return a2;
  StartThreadpoolIo(*(PTP_IO *)(a1 + 16));
  if ( WSASendTo(
         *(_QWORD *)(a1 + 24),
         (LPWSABUF)(a2 + 408),
         1u,
         &NumberOfBytesSent,
         0,
         (const struct sockaddr *)(a2 + 376),
         16,
         (LPWSAOVERLAPPED)(a2 + 256),
         0)
    && WSAGetLastError() != 997 )
  {
    CancelThreadpoolIo(*(PTP_IO *)(a1 + 16));
    return a2;
  }
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
    McTemplateU0qzbr0_EventWriteTransfer(
      v7,
      (unsigned int)EVENT_IPHLPSVC_ETW_TEREDO_SEND_PACKET,
      v8,
      (unsigned int)L"Primary Socket",
      a2 + 376);
  return 0;
}

```

## disassembly

```asm
0x1800265d0  mov     [rsp+arg_8], rbx
0x1800265d5  mov     [rsp+arg_10], rbp
0x1800265da  push    rsi
0x1800265db  push    rdi
0x1800265dc  push    r14
0x1800265de  sub     rsp, 50h
0x1800265e2  mov     rbx, rdx
0x1800265e5  mov     rdi, rcx
0x1800265e8  mov     r8, rdx
0x1800265eb  xor     r14d, r14d
0x1800265ee  lea     rdx, aTeredoPrimaryT_0; "Teredo primary transmit packet: 0x%p"
0x1800265f5  mov     [rsp+68h+NumberOfBytesSent], r14d
0x1800265fa  mov     ecx, 100000h
0x1800265ff  call    EventWrite0
0x180026604  mov     [rsp+68h+lpCompletionRoutine], r14; lpCompletionRoutine
0x180026609  lea     rbp, [rbx+178h]
0x180026610  mov     [rsp+68h+lpOverlapped], r14; lpOverlapped
0x180026615  lea     r9, [rsp+68h+NumberOfBytesSent]; lpNumberOfBytesSent
0x18002661a  mov     [rsp+68h+iTolen], 10h; iTolen
0x180026622  lea     rdx, [rbx+198h]; lpBuffers
0x180026629  mov     dword ptr [rbx+120h], 1
0x180026633  mov     r8d, 1; dwBufferCount
0x180026639  mov     rcx, [rdi+18h]; s
0x18002663d  mov     [rsp+68h+lpTo], rbp; lpTo
0x180026642  mov     [rsp+68h+dwFlags], r14d; dwFlags
0x180026647  call    cs:__imp_WSASendTo
0x18002664e  nop     dword ptr [rax+rax+00h]
0x180026653  cmp     eax, 0FFFFFFFFh
0x180026656  jz      short loc_18002667F
0x180026658  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x18002665f  jnz     loc_18002673B
0x180026665  mov     rax, rbx
0x180026668  mov     rbx, [rsp+68h+arg_8]
0x18002666d  mov     rbp, [rsp+68h+arg_10]
0x180026675  add     rsp, 50h
0x180026679  pop     r14
0x18002667b  pop     rdi
0x18002667c  pop     rsi
0x18002667d  retn
0x18002667f  call    cs:__imp_WSAGetLastError
0x180026686  nop     dword ptr [rax+rax+00h]
0x18002668b  cmp     eax, 2733h
0x180026690  jnz     short loc_180026665
0x180026692  mov     rcx, [rdi+10h]; pio
0x180026696  call    cs:__imp_StartThreadpoolIo
0x18002669d  nop     dword ptr [rax+rax+00h]
0x1800266a2  mov     rcx, [rdi+18h]; s
0x1800266a6  lea     rax, [rbx+100h]
0x1800266ad  mov     [rsp+68h+lpCompletionRoutine], r14; lpCompletionRoutine
0x1800266b2  lea     r9, [rsp+68h+NumberOfBytesSent]; lpNumberOfBytesSent
0x1800266b7  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x1800266bc  lea     rdx, [rbx+198h]; lpBuffers
0x1800266c3  mov     [rsp+68h+iTolen], 10h; iTolen
0x1800266cb  mov     r8d, 1; dwBufferCount
0x1800266d1  mov     [rsp+68h+lpTo], rbp; lpTo
0x1800266d6  mov     [rsp+68h+dwFlags], r14d; dwFlags
0x1800266db  call    cs:__imp_WSASendTo
0x1800266e2  nop     dword ptr [rax+rax+00h]
0x1800266e7  test    eax, eax
0x1800266e9  jz      short loc_180026713
0x1800266eb  call    cs:__imp_WSAGetLastError
0x1800266f2  nop     dword ptr [rax+rax+00h]
0x1800266f7  cmp     eax, 3E5h
0x1800266fc  jz      short loc_180026713
0x1800266fe  mov     rcx, [rdi+10h]; pio
0x180026702  call    cs:__imp_CancelThreadpoolIo
0x180026709  nop     dword ptr [rax+rax+00h]
0x18002670e  jmp     loc_180026665
0x180026713  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x18002671a  jz      short loc_180026734
0x18002671c  lea     r9, aPrimarySocket; "Primary Socket"
0x180026723  mov     qword ptr [rsp+68h+dwFlags], rbp
0x180026728  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_SEND_PACKET
0x18002672f  call    McTemplateU0qzbr0_EventWriteTransfer
0x180026734  xor     eax, eax
0x180026736  jmp     loc_180026668
0x18002673b  lea     r9, aPrimarySocket; "Primary Socket"
0x180026742  mov     qword ptr [rsp+68h+dwFlags], rbp
0x180026747  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_SEND_PACKET
0x18002674e  call    McTemplateU0qzbr0_EventWriteTransfer
0x180026753  jmp     loc_180026665
```
