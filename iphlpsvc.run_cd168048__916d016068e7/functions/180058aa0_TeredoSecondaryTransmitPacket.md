# TeredoSecondaryTransmitPacket

- ea: `0x180058aa0`
- end: `0x180058c23`
- name: `TeredoSecondaryTransmitPacket`
- size: `387`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000d7b0`
- `0x18003aac4`
- `0x180058aa0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180058bc2`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180058bc2`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180058b50`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180058b50`
- `WS2_32!WSASendTo` at `0x180058b20`
- `WS2_32!WSASendTo` at `0x180058b9b`
- `WS2_32!WSASendTo` at `0x180058b20`
- `WS2_32!WSASendTo` at `0x180058b9b`
- `WS2_32!__imp_WSAGetLastError` at `0x180058b35`
- `WS2_32!__imp_WSAGetLastError` at `0x180058bab`
- `WS2_32!__imp_WSAGetLastError` at `0x180058b35`
- `WS2_32!__imp_WSAGetLastError` at `0x180058bab`

## pseudocode

```c
__int64 __fastcall TeredoSecondaryTransmitPacket(__int64 a1, __int64 a2)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // ecx
  int v7; // r8d
  DWORD NumberOfBytesSent; // [rsp+80h] [rbp+8h] BYREF

  NumberOfBytesSent = 0;
  EventWrite0(0x100000, L"Teredo secondary transmit packet: 0x%p", a2);
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
        (unsigned int)L"Secondary Socket",
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
      v6,
      (unsigned int)EVENT_IPHLPSVC_ETW_TEREDO_SEND_PACKET,
      v7,
      (unsigned int)L"Secondary Socket",
      a2 + 376);
  return 0;
}

```

## disassembly

```asm
0x180058aa0  mov     rax, rsp
0x180058aa3  push    rbx
0x180058aa4  push    rbp
0x180058aa5  push    rsi
0x180058aa6  push    rdi
0x180058aa7  sub     rsp, 58h
0x180058aab  mov     rbx, rdx
0x180058aae  mov     dword ptr [rax+8], 0
0x180058ab5  mov     rsi, rcx
0x180058ab8  mov     r8, rdx
0x180058abb  lea     rdx, aTeredoSecondar_0; "Teredo secondary transmit packet: 0x%p"
0x180058ac2  mov     ecx, 100000h
0x180058ac7  call    EventWrite0
0x180058acc  mov     [rsp+78h+lpCompletionRoutine], 0; lpCompletionRoutine
0x180058ad5  lea     rdi, [rbx+178h]
0x180058adc  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x180058ae5  lea     rbp, [rbx+198h]
0x180058aec  mov     [rsp+78h+iTolen], 10h; iTolen
0x180058af4  lea     r9, [rsp+78h+NumberOfBytesSent]; lpNumberOfBytesSent
0x180058afc  mov     dword ptr [rbx+120h], 1
0x180058b06  mov     r8d, 1; dwBufferCount
0x180058b0c  mov     rcx, [rsi+18h]; s
0x180058b10  mov     rdx, rbp; lpBuffers
0x180058b13  mov     [rsp+78h+lpTo], rdi; lpTo
0x180058b18  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180058b20  call    cs:__imp_WSASendTo
0x180058b27  nop     dword ptr [rax+rax+00h]
0x180058b2c  cmp     eax, 0FFFFFFFFh
0x180058b2f  jnz     loc_180058BF5
0x180058b35  call    cs:__imp_WSAGetLastError
0x180058b3c  nop     dword ptr [rax+rax+00h]
0x180058b41  cmp     eax, 2733h
0x180058b46  jnz     loc_180058C16
0x180058b4c  mov     rcx, [rsi+10h]; pio
0x180058b50  call    cs:__imp_StartThreadpoolIo
0x180058b57  nop     dword ptr [rax+rax+00h]
0x180058b5c  mov     rcx, [rsi+18h]; s
0x180058b60  lea     rax, [rbx+100h]
0x180058b67  mov     [rsp+78h+lpCompletionRoutine], 0; lpCompletionRoutine
0x180058b70  lea     r9, [rsp+78h+NumberOfBytesSent]; lpNumberOfBytesSent
0x180058b78  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x180058b7d  mov     r8d, 1; dwBufferCount
0x180058b83  mov     [rsp+78h+iTolen], 10h; iTolen
0x180058b8b  mov     rdx, rbp; lpBuffers
0x180058b8e  mov     [rsp+78h+lpTo], rdi; lpTo
0x180058b93  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180058b9b  call    cs:__imp_WSASendTo
0x180058ba2  nop     dword ptr [rax+rax+00h]
0x180058ba7  test    eax, eax
0x180058ba9  jz      short loc_180058BD0
0x180058bab  call    cs:__imp_WSAGetLastError
0x180058bb2  nop     dword ptr [rax+rax+00h]
0x180058bb7  cmp     eax, 3E5h
0x180058bbc  jz      short loc_180058BD0
0x180058bbe  mov     rcx, [rsi+10h]; pio
0x180058bc2  call    cs:__imp_CancelThreadpoolIo
0x180058bc9  nop     dword ptr [rax+rax+00h]
0x180058bce  jmp     short loc_180058C16
0x180058bd0  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x180058bd7  jz      short loc_180058BF1
0x180058bd9  lea     r9, aSecondarySocke; "Secondary Socket"
0x180058be0  mov     qword ptr [rsp+78h+dwFlags], rdi
0x180058be5  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_SEND_PACKET
0x180058bec  call    McTemplateU0qzbr0_EventWriteTransfer
0x180058bf1  xor     eax, eax
0x180058bf3  jmp     short loc_180058C19
0x180058bf5  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x180058bfc  jz      short loc_180058C16
0x180058bfe  lea     r9, aSecondarySocke; "Secondary Socket"
0x180058c05  mov     qword ptr [rsp+78h+dwFlags], rdi
0x180058c0a  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_SEND_PACKET
0x180058c11  call    McTemplateU0qzbr0_EventWriteTransfer
0x180058c16  mov     rax, rbx
0x180058c19  add     rsp, 58h
0x180058c1d  pop     rdi
0x180058c1e  pop     rsi
0x180058c1f  pop     rbp
0x180058c20  pop     rbx
0x180058c21  retn
```
