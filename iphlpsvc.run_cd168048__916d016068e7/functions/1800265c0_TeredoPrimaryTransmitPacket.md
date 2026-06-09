# TeredoPrimaryTransmitPacket

- ea: `0x1800265c0`
- end: `0x180026748`
- name: `TeredoPrimaryTransmitPacket`
- size: `392`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000d7b0`
- `0x1800265c0`
- `0x18003aac4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800266f2`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800266f2`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180026686`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180026686`
- `WS2_32!WSASendTo` at `0x180026637`
- `WS2_32!WSASendTo` at `0x1800266cb`
- `WS2_32!WSASendTo` at `0x180026637`
- `WS2_32!WSASendTo` at `0x1800266cb`
- `WS2_32!__imp_WSAGetLastError` at `0x18002666f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800266db`
- `WS2_32!__imp_WSAGetLastError` at `0x18002666f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800266db`

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
0x1800265c0  mov     [rsp+arg_8], rbx
0x1800265c5  mov     [rsp+arg_10], rbp
0x1800265ca  push    rsi
0x1800265cb  push    rdi
0x1800265cc  push    r14
0x1800265ce  sub     rsp, 50h
0x1800265d2  mov     rbx, rdx
0x1800265d5  mov     rdi, rcx
0x1800265d8  mov     r8, rdx
0x1800265db  xor     r14d, r14d
0x1800265de  lea     rdx, aTeredoPrimaryT_0; "Teredo primary transmit packet: 0x%p"
0x1800265e5  mov     [rsp+68h+NumberOfBytesSent], r14d
0x1800265ea  mov     ecx, 100000h
0x1800265ef  call    EventWrite0
0x1800265f4  mov     [rsp+68h+lpCompletionRoutine], r14; lpCompletionRoutine
0x1800265f9  lea     rbp, [rbx+178h]
0x180026600  mov     [rsp+68h+lpOverlapped], r14; lpOverlapped
0x180026605  lea     r9, [rsp+68h+NumberOfBytesSent]; lpNumberOfBytesSent
0x18002660a  mov     [rsp+68h+iTolen], 10h; iTolen
0x180026612  lea     rdx, [rbx+198h]; lpBuffers
0x180026619  mov     dword ptr [rbx+120h], 1
0x180026623  mov     r8d, 1; dwBufferCount
0x180026629  mov     rcx, [rdi+18h]; s
0x18002662d  mov     [rsp+68h+lpTo], rbp; lpTo
0x180026632  mov     [rsp+68h+dwFlags], r14d; dwFlags
0x180026637  call    cs:__imp_WSASendTo
0x18002663e  nop     dword ptr [rax+rax+00h]
0x180026643  cmp     eax, 0FFFFFFFFh
0x180026646  jz      short loc_18002666F
0x180026648  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x18002664f  jnz     loc_18002672B
0x180026655  mov     rax, rbx
0x180026658  mov     rbx, [rsp+68h+arg_8]
0x18002665d  mov     rbp, [rsp+68h+arg_10]
0x180026665  add     rsp, 50h
0x180026669  pop     r14
0x18002666b  pop     rdi
0x18002666c  pop     rsi
0x18002666d  retn
0x18002666f  call    cs:__imp_WSAGetLastError
0x180026676  nop     dword ptr [rax+rax+00h]
0x18002667b  cmp     eax, 2733h
0x180026680  jnz     short loc_180026655
0x180026682  mov     rcx, [rdi+10h]; pio
0x180026686  call    cs:__imp_StartThreadpoolIo
0x18002668d  nop     dword ptr [rax+rax+00h]
0x180026692  mov     rcx, [rdi+18h]; s
0x180026696  lea     rax, [rbx+100h]
0x18002669d  mov     [rsp+68h+lpCompletionRoutine], r14; lpCompletionRoutine
0x1800266a2  lea     r9, [rsp+68h+NumberOfBytesSent]; lpNumberOfBytesSent
0x1800266a7  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x1800266ac  lea     rdx, [rbx+198h]; lpBuffers
0x1800266b3  mov     [rsp+68h+iTolen], 10h; iTolen
0x1800266bb  mov     r8d, 1; dwBufferCount
0x1800266c1  mov     [rsp+68h+lpTo], rbp; lpTo
0x1800266c6  mov     [rsp+68h+dwFlags], r14d; dwFlags
0x1800266cb  call    cs:__imp_WSASendTo
0x1800266d2  nop     dword ptr [rax+rax+00h]
0x1800266d7  test    eax, eax
0x1800266d9  jz      short loc_180026703
0x1800266db  call    cs:__imp_WSAGetLastError
0x1800266e2  nop     dword ptr [rax+rax+00h]
0x1800266e7  cmp     eax, 3E5h
0x1800266ec  jz      short loc_180026703
0x1800266ee  mov     rcx, [rdi+10h]; pio
0x1800266f2  call    cs:__imp_CancelThreadpoolIo
0x1800266f9  nop     dword ptr [rax+rax+00h]
0x1800266fe  jmp     loc_180026655
0x180026703  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x18002670a  jz      short loc_180026724
0x18002670c  lea     r9, aPrimarySocket; "Primary Socket"
0x180026713  mov     qword ptr [rsp+68h+dwFlags], rbp
0x180026718  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_SEND_PACKET
0x18002671f  call    McTemplateU0qzbr0_EventWriteTransfer
0x180026724  xor     eax, eax
0x180026726  jmp     loc_180026658
0x18002672b  lea     r9, aPrimarySocket; "Primary Socket"
0x180026732  mov     qword ptr [rsp+68h+dwFlags], rbp
0x180026737  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_SEND_PACKET
0x18002673e  call    McTemplateU0qzbr0_EventWriteTransfer
0x180026743  jmp     loc_180026655
```
