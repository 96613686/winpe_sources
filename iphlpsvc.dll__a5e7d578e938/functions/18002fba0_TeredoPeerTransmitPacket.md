# TeredoPeerTransmitPacket

- ea: `0x18002fba0`
- end: `0x18002fcdd`
- name: `TeredoPeerTransmitPacket`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d7c0`
- `0x18002fba0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18002fcc5`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18002fcc5`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18002fc59`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18002fc59`
- `WS2_32!WSASendTo` at `0x18002fc17`
- `WS2_32!WSASendTo` at `0x18002fc9e`
- `WS2_32!WSASendTo` at `0x18002fc17`
- `WS2_32!WSASendTo` at `0x18002fc9e`
- `WS2_32!__imp_WSAGetLastError` at `0x18002fc42`
- `WS2_32!__imp_WSAGetLastError` at `0x18002fcae`
- `WS2_32!__imp_WSAGetLastError` at `0x18002fc42`
- `WS2_32!__imp_WSAGetLastError` at `0x18002fcae`

## pseudocode

```c
__int64 __fastcall TeredoPeerTransmitPacket(__int64 a1, __int64 a2)
{
  DWORD NumberOfBytesSent; // [rsp+70h] [rbp+8h] BYREF

  NumberOfBytesSent = 0;
  EventWrite0(0x100000, L"Teredo transmit packet on peer socket: 0x%p", a2);
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
         0) != -1
    || WSAGetLastError() != 10035 )
  {
    return a2;
  }
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
  return 0;
}

```

## disassembly

```asm
0x18002fba0  mov     [rsp+arg_8], rbx
0x18002fba5  mov     [rsp+arg_10], rbp
0x18002fbaa  push    rsi
0x18002fbab  push    rdi
0x18002fbac  push    r14
0x18002fbae  sub     rsp, 50h
0x18002fbb2  mov     rbx, rdx
0x18002fbb5  mov     rdi, rcx
0x18002fbb8  mov     r8, rdx
0x18002fbbb  xor     r14d, r14d
0x18002fbbe  lea     rdx, aTeredoTransmit; "Teredo transmit packet on peer socket: "...
0x18002fbc5  mov     [rsp+68h+NumberOfBytesSent], r14d
0x18002fbca  mov     ecx, 100000h
0x18002fbcf  call    EventWrite0
0x18002fbd4  mov     [rsp+68h+lpCompletionRoutine], r14; lpCompletionRoutine
0x18002fbd9  lea     rsi, [rbx+178h]
0x18002fbe0  mov     [rsp+68h+lpOverlapped], r14; lpOverlapped
0x18002fbe5  lea     r9, [rsp+68h+NumberOfBytesSent]; lpNumberOfBytesSent
0x18002fbea  mov     [rsp+68h+iTolen], 10h; iTolen
0x18002fbf2  lea     rdx, [rbx+198h]; lpBuffers
0x18002fbf9  mov     dword ptr [rbx+120h], 1
0x18002fc03  mov     r8d, 1; dwBufferCount
0x18002fc09  mov     rcx, [rdi+18h]; s
0x18002fc0d  mov     [rsp+68h+lpTo], rsi; lpTo
0x18002fc12  mov     [rsp+68h+dwFlags], r14d; dwFlags
0x18002fc17  call    cs:__imp_WSASendTo
0x18002fc1e  nop     dword ptr [rax+rax+00h]
0x18002fc23  cmp     eax, 0FFFFFFFFh
0x18002fc26  jz      short loc_18002FC42
0x18002fc28  mov     rax, rbx
0x18002fc2b  mov     rbx, [rsp+68h+arg_8]
0x18002fc30  mov     rbp, [rsp+68h+arg_10]
0x18002fc38  add     rsp, 50h
0x18002fc3c  pop     r14
0x18002fc3e  pop     rdi
0x18002fc3f  pop     rsi
0x18002fc40  retn
0x18002fc42  call    cs:__imp_WSAGetLastError
0x18002fc49  nop     dword ptr [rax+rax+00h]
0x18002fc4e  cmp     eax, 2733h
0x18002fc53  jnz     short loc_18002FC28
0x18002fc55  mov     rcx, [rdi+10h]; pio
0x18002fc59  call    cs:__imp_StartThreadpoolIo
0x18002fc60  nop     dword ptr [rax+rax+00h]
0x18002fc65  mov     rcx, [rdi+18h]; s
0x18002fc69  lea     rax, [rbx+100h]
0x18002fc70  mov     [rsp+68h+lpCompletionRoutine], r14; lpCompletionRoutine
0x18002fc75  lea     r9, [rsp+68h+NumberOfBytesSent]; lpNumberOfBytesSent
0x18002fc7a  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x18002fc7f  lea     rdx, [rbx+198h]; lpBuffers
0x18002fc86  mov     [rsp+68h+iTolen], 10h; iTolen
0x18002fc8e  mov     r8d, 1; dwBufferCount
0x18002fc94  mov     [rsp+68h+lpTo], rsi; lpTo
0x18002fc99  mov     [rsp+68h+dwFlags], r14d; dwFlags
0x18002fc9e  call    cs:__imp_WSASendTo
0x18002fca5  nop     dword ptr [rax+rax+00h]
0x18002fcaa  test    eax, eax
0x18002fcac  jz      short loc_18002FCD6
0x18002fcae  call    cs:__imp_WSAGetLastError
0x18002fcb5  nop     dword ptr [rax+rax+00h]
0x18002fcba  cmp     eax, 3E5h
0x18002fcbf  jz      short loc_18002FCD6
0x18002fcc1  mov     rcx, [rdi+10h]; pio
0x18002fcc5  call    cs:__imp_CancelThreadpoolIo
0x18002fccc  nop     dword ptr [rax+rax+00h]
0x18002fcd1  jmp     loc_18002FC28
0x18002fcd6  xor     eax, eax
0x18002fcd8  jmp     loc_18002FC2B
```
