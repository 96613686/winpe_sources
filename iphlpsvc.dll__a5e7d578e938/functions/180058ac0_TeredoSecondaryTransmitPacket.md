# TeredoSecondaryTransmitPacket

- ea: `0x180058ac0`
- end: `0x180058c43`
- name: `TeredoSecondaryTransmitPacket`
- size: `387`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000d7c0`
- `0x18003aad4`
- `0x180058ac0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180058be2`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180058be2`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180058b70`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180058b70`
- `WS2_32!WSASendTo` at `0x180058b40`
- `WS2_32!WSASendTo` at `0x180058bbb`
- `WS2_32!WSASendTo` at `0x180058b40`
- `WS2_32!WSASendTo` at `0x180058bbb`
- `WS2_32!__imp_WSAGetLastError` at `0x180058b55`
- `WS2_32!__imp_WSAGetLastError` at `0x180058bcb`
- `WS2_32!__imp_WSAGetLastError` at `0x180058b55`
- `WS2_32!__imp_WSAGetLastError` at `0x180058bcb`

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
0x180058ac0  mov     rax, rsp
0x180058ac3  push    rbx
0x180058ac4  push    rbp
0x180058ac5  push    rsi
0x180058ac6  push    rdi
0x180058ac7  sub     rsp, 58h
0x180058acb  mov     rbx, rdx
0x180058ace  mov     dword ptr [rax+8], 0
0x180058ad5  mov     rsi, rcx
0x180058ad8  mov     r8, rdx
0x180058adb  lea     rdx, aTeredoSecondar_0; "Teredo secondary transmit packet: 0x%p"
0x180058ae2  mov     ecx, 100000h
0x180058ae7  call    EventWrite0
0x180058aec  mov     [rsp+78h+lpCompletionRoutine], 0; lpCompletionRoutine
0x180058af5  lea     rdi, [rbx+178h]
0x180058afc  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x180058b05  lea     rbp, [rbx+198h]
0x180058b0c  mov     [rsp+78h+iTolen], 10h; iTolen
0x180058b14  lea     r9, [rsp+78h+NumberOfBytesSent]; lpNumberOfBytesSent
0x180058b1c  mov     dword ptr [rbx+120h], 1
0x180058b26  mov     r8d, 1; dwBufferCount
0x180058b2c  mov     rcx, [rsi+18h]; s
0x180058b30  mov     rdx, rbp; lpBuffers
0x180058b33  mov     [rsp+78h+lpTo], rdi; lpTo
0x180058b38  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180058b40  call    cs:__imp_WSASendTo
0x180058b47  nop     dword ptr [rax+rax+00h]
0x180058b4c  cmp     eax, 0FFFFFFFFh
0x180058b4f  jnz     loc_180058C15
0x180058b55  call    cs:__imp_WSAGetLastError
0x180058b5c  nop     dword ptr [rax+rax+00h]
0x180058b61  cmp     eax, 2733h
0x180058b66  jnz     loc_180058C36
0x180058b6c  mov     rcx, [rsi+10h]; pio
0x180058b70  call    cs:__imp_StartThreadpoolIo
0x180058b77  nop     dword ptr [rax+rax+00h]
0x180058b7c  mov     rcx, [rsi+18h]; s
0x180058b80  lea     rax, [rbx+100h]
0x180058b87  mov     [rsp+78h+lpCompletionRoutine], 0; lpCompletionRoutine
0x180058b90  lea     r9, [rsp+78h+NumberOfBytesSent]; lpNumberOfBytesSent
0x180058b98  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x180058b9d  mov     r8d, 1; dwBufferCount
0x180058ba3  mov     [rsp+78h+iTolen], 10h; iTolen
0x180058bab  mov     rdx, rbp; lpBuffers
0x180058bae  mov     [rsp+78h+lpTo], rdi; lpTo
0x180058bb3  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180058bbb  call    cs:__imp_WSASendTo
0x180058bc2  nop     dword ptr [rax+rax+00h]
0x180058bc7  test    eax, eax
0x180058bc9  jz      short loc_180058BF0
0x180058bcb  call    cs:__imp_WSAGetLastError
0x180058bd2  nop     dword ptr [rax+rax+00h]
0x180058bd7  cmp     eax, 3E5h
0x180058bdc  jz      short loc_180058BF0
0x180058bde  mov     rcx, [rsi+10h]; pio
0x180058be2  call    cs:__imp_CancelThreadpoolIo
0x180058be9  nop     dword ptr [rax+rax+00h]
0x180058bee  jmp     short loc_180058C36
0x180058bf0  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x180058bf7  jz      short loc_180058C11
0x180058bf9  lea     r9, aSecondarySocke; "Secondary Socket"
0x180058c00  mov     qword ptr [rsp+78h+dwFlags], rdi
0x180058c05  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_SEND_PACKET
0x180058c0c  call    McTemplateU0qzbr0_EventWriteTransfer
0x180058c11  xor     eax, eax
0x180058c13  jmp     short loc_180058C39
0x180058c15  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x180058c1c  jz      short loc_180058C36
0x180058c1e  lea     r9, aSecondarySocke; "Secondary Socket"
0x180058c25  mov     qword ptr [rsp+78h+dwFlags], rdi
0x180058c2a  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_SEND_PACKET
0x180058c31  call    McTemplateU0qzbr0_EventWriteTransfer
0x180058c36  mov     rax, rbx
0x180058c39  add     rsp, 58h
0x180058c3d  pop     rdi
0x180058c3e  pop     rsi
0x180058c3f  pop     rbp
0x180058c40  pop     rbx
0x180058c41  retn
```
