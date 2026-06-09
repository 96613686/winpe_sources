# TeredoPeerTransmitPacket

- ea: `0x18002fb90`
- end: `0x18002fccd`
- name: `TeredoPeerTransmitPacket`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d7b0`
- `0x18002fb90`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18002fcb5`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18002fcb5`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18002fc49`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18002fc49`
- `WS2_32!WSASendTo` at `0x18002fc07`
- `WS2_32!WSASendTo` at `0x18002fc8e`
- `WS2_32!WSASendTo` at `0x18002fc07`
- `WS2_32!WSASendTo` at `0x18002fc8e`
- `WS2_32!__imp_WSAGetLastError` at `0x18002fc32`
- `WS2_32!__imp_WSAGetLastError` at `0x18002fc9e`
- `WS2_32!__imp_WSAGetLastError` at `0x18002fc32`
- `WS2_32!__imp_WSAGetLastError` at `0x18002fc9e`

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
0x18002fb90  mov     [rsp+arg_8], rbx
0x18002fb95  mov     [rsp+arg_10], rbp
0x18002fb9a  push    rsi
0x18002fb9b  push    rdi
0x18002fb9c  push    r14
0x18002fb9e  sub     rsp, 50h
0x18002fba2  mov     rbx, rdx
0x18002fba5  mov     rdi, rcx
0x18002fba8  mov     r8, rdx
0x18002fbab  xor     r14d, r14d
0x18002fbae  lea     rdx, aTeredoTransmit; "Teredo transmit packet on peer socket: "...
0x18002fbb5  mov     [rsp+68h+NumberOfBytesSent], r14d
0x18002fbba  mov     ecx, 100000h
0x18002fbbf  call    EventWrite0
0x18002fbc4  mov     [rsp+68h+lpCompletionRoutine], r14; lpCompletionRoutine
0x18002fbc9  lea     rsi, [rbx+178h]
0x18002fbd0  mov     [rsp+68h+lpOverlapped], r14; lpOverlapped
0x18002fbd5  lea     r9, [rsp+68h+NumberOfBytesSent]; lpNumberOfBytesSent
0x18002fbda  mov     [rsp+68h+iTolen], 10h; iTolen
0x18002fbe2  lea     rdx, [rbx+198h]; lpBuffers
0x18002fbe9  mov     dword ptr [rbx+120h], 1
0x18002fbf3  mov     r8d, 1; dwBufferCount
0x18002fbf9  mov     rcx, [rdi+18h]; s
0x18002fbfd  mov     [rsp+68h+lpTo], rsi; lpTo
0x18002fc02  mov     [rsp+68h+dwFlags], r14d; dwFlags
0x18002fc07  call    cs:__imp_WSASendTo
0x18002fc0e  nop     dword ptr [rax+rax+00h]
0x18002fc13  cmp     eax, 0FFFFFFFFh
0x18002fc16  jz      short loc_18002FC32
0x18002fc18  mov     rax, rbx
0x18002fc1b  mov     rbx, [rsp+68h+arg_8]
0x18002fc20  mov     rbp, [rsp+68h+arg_10]
0x18002fc28  add     rsp, 50h
0x18002fc2c  pop     r14
0x18002fc2e  pop     rdi
0x18002fc2f  pop     rsi
0x18002fc30  retn
0x18002fc32  call    cs:__imp_WSAGetLastError
0x18002fc39  nop     dword ptr [rax+rax+00h]
0x18002fc3e  cmp     eax, 2733h
0x18002fc43  jnz     short loc_18002FC18
0x18002fc45  mov     rcx, [rdi+10h]; pio
0x18002fc49  call    cs:__imp_StartThreadpoolIo
0x18002fc50  nop     dword ptr [rax+rax+00h]
0x18002fc55  mov     rcx, [rdi+18h]; s
0x18002fc59  lea     rax, [rbx+100h]
0x18002fc60  mov     [rsp+68h+lpCompletionRoutine], r14; lpCompletionRoutine
0x18002fc65  lea     r9, [rsp+68h+NumberOfBytesSent]; lpNumberOfBytesSent
0x18002fc6a  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x18002fc6f  lea     rdx, [rbx+198h]; lpBuffers
0x18002fc76  mov     [rsp+68h+iTolen], 10h; iTolen
0x18002fc7e  mov     r8d, 1; dwBufferCount
0x18002fc84  mov     [rsp+68h+lpTo], rsi; lpTo
0x18002fc89  mov     [rsp+68h+dwFlags], r14d; dwFlags
0x18002fc8e  call    cs:__imp_WSASendTo
0x18002fc95  nop     dword ptr [rax+rax+00h]
0x18002fc9a  test    eax, eax
0x18002fc9c  jz      short loc_18002FCC6
0x18002fc9e  call    cs:__imp_WSAGetLastError
0x18002fca5  nop     dword ptr [rax+rax+00h]
0x18002fcaa  cmp     eax, 3E5h
0x18002fcaf  jz      short loc_18002FCC6
0x18002fcb1  mov     rcx, [rdi+10h]; pio
0x18002fcb5  call    cs:__imp_CancelThreadpoolIo
0x18002fcbc  nop     dword ptr [rax+rax+00h]
0x18002fcc1  jmp     loc_18002FC18
0x18002fcc6  xor     eax, eax
0x18002fcc8  jmp     loc_18002FC1B
```
