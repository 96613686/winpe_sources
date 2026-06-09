# StartAccept

- ea: `0x180035494`
- end: `0x1800355be`
- name: `StartAccept`
- size: `298`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18003523c`
- `0x18003e1e8`
- `0x18003e254`

## callees

- `0x18000d7b0`
- `0x180035494`
- `0x18003e1e8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18003558e`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18003558e`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18003552e`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18003552e`
- `MSWSOCK!AcceptEx` at `0x180035565`
- `MSWSOCK!AcceptEx` at `0x180035565`
- `WS2_32!__imp_socket` at `0x1800354c3`
- `WS2_32!__imp_socket` at `0x1800354c3`
- `WS2_32!__imp_WSAGetLastError` at `0x1800354e0`
- `WS2_32!__imp_WSAGetLastError` at `0x180035575`
- `WS2_32!__imp_WSAGetLastError` at `0x1800354e0`
- `WS2_32!__imp_WSAGetLastError` at `0x180035575`

## pseudocode

```c
__int64 __fastcall StartAccept(__int64 a1)
{
  SOCKET v2; // rax
  unsigned int Error; // eax
  __int64 v4; // rdx
  unsigned int v5; // ebx
  struct _TP_IO *v7; // rcx
  unsigned int v8; // edi
  DWORD dwBytesReceived; // [rsp+50h] [rbp+8h] BYREF

  dwBytesReceived = 0;
  _InterlockedAdd((volatile signed __int32 *)(a1 + 16), 1u);
  v2 = socket(*(unsigned __int16 *)(a1 + 184), 1, 0);
  *(_QWORD *)(a1 + 32) = v2;
  if ( v2 == -1 )
  {
    Error = WSAGetLastError();
    v4 = a1 + 144;
    v5 = Error;
    ProcessAcceptError(0, v4, Error);
    return v5;
  }
  else
  {
    EventWrite0(0x80000, L"Starting an accept with new socket %Ix ovl %p", v2, a1 + 144);
    v7 = *(struct _TP_IO **)(a1 + 40);
    *(_QWORD *)(a1 + 168) = 0;
    *(_DWORD *)(a1 + 176) = 1;
    StartThreadpoolIo(v7);
    if ( AcceptEx(
           *(_QWORD *)(a1 + 24),
           *(_QWORD *)(a1 + 32),
           (PVOID)(a1 + 56),
           0,
           0x2Cu,
           0x2Cu,
           &dwBytesReceived,
           (LPOVERLAPPED)(a1 + 144)) )
    {
      return 0;
    }
    v8 = WSAGetLastError();
    if ( v8 == 997 )
    {
      return 0;
    }
    else
    {
      CancelThreadpoolIo(*(PTP_IO *)(a1 + 40));
      ProcessAcceptError(0, a1 + 144, v8);
      return v8;
    }
  }
}

```

## disassembly

```asm
0x180035494  mov     [rsp+arg_8], rbx
0x180035499  mov     [rsp+arg_10], rsi
0x18003549e  push    rdi
0x18003549f  sub     rsp, 40h
0x1800354a3  mov     rbx, rcx
0x1800354a6  mov     [rsp+48h+dwBytesReceived], 0
0x1800354ae  mov     edi, 1
0x1800354b3  lock add [rcx+10h], edi
0x1800354b7  movzx   ecx, word ptr [rcx+0B8h]; af
0x1800354be  xor     r8d, r8d; protocol
0x1800354c1  mov     edx, edi; type
0x1800354c3  call    cs:__imp_socket
0x1800354ca  nop     dword ptr [rax+rax+00h]
0x1800354cf  mov     [rbx+20h], rax
0x1800354d3  lea     rsi, [rbx+90h]
0x1800354da  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800354de  jnz     short loc_180035502
0x1800354e0  call    cs:__imp_WSAGetLastError
0x1800354e7  nop     dword ptr [rax+rax+00h]
0x1800354ec  mov     rdx, rsi
0x1800354ef  xor     ecx, ecx
0x1800354f1  mov     r8d, eax
0x1800354f4  mov     ebx, eax
0x1800354f6  call    ProcessAcceptError
0x1800354fb  mov     eax, ebx
0x1800354fd  jmp     loc_1800355AD
0x180035502  mov     r9, rsi
0x180035505  lea     rdx, aStartingAnAcce; "Starting an accept with new socket %Ix "...
0x18003550c  mov     r8, rax
0x18003550f  mov     ecx, 80000h
0x180035514  call    EventWrite0
0x180035519  mov     rcx, [rbx+28h]; pio
0x18003551d  mov     qword ptr [rbx+0A8h], 0
0x180035528  mov     [rbx+0B0h], edi
0x18003552e  call    cs:__imp_StartThreadpoolIo
0x180035535  nop     dword ptr [rax+rax+00h]
0x18003553a  mov     rdx, [rbx+20h]; sAcceptSocket
0x18003553e  lea     rax, [rsp+48h+dwBytesReceived]
0x180035543  mov     rcx, [rbx+18h]; sListenSocket
0x180035547  lea     r8, [rbx+38h]; lpOutputBuffer
0x18003554b  mov     [rsp+48h+lpOverlapped], rsi; lpOverlapped
0x180035550  xor     r9d, r9d; dwReceiveDataLength
0x180035553  mov     [rsp+48h+lpdwBytesReceived], rax; lpdwBytesReceived
0x180035558  mov     eax, 2Ch ; ','
0x18003555d  mov     [rsp+48h+dwRemoteAddressLength], eax; dwRemoteAddressLength
0x180035561  mov     [rsp+48h+dwLocalAddressLength], eax; dwLocalAddressLength
0x180035565  call    cs:__imp_AcceptEx
0x18003556c  nop     dword ptr [rax+rax+00h]
0x180035571  test    eax, eax
0x180035573  jnz     short loc_1800355AB
0x180035575  call    cs:__imp_WSAGetLastError
0x18003557c  nop     dword ptr [rax+rax+00h]
0x180035581  mov     edi, eax
0x180035583  cmp     eax, 3E5h
0x180035588  jz      short loc_1800355AB
0x18003558a  mov     rcx, [rbx+28h]; pio
0x18003558e  call    cs:__imp_CancelThreadpoolIo
0x180035595  nop     dword ptr [rax+rax+00h]
0x18003559a  mov     r8d, edi
0x18003559d  mov     rdx, rsi
0x1800355a0  xor     ecx, ecx
0x1800355a2  call    ProcessAcceptError
0x1800355a7  mov     eax, edi
0x1800355a9  jmp     short loc_1800355AD
0x1800355ab  xor     eax, eax
0x1800355ad  mov     rbx, [rsp+48h+arg_8]
0x1800355b2  mov     rsi, [rsp+48h+arg_10]
0x1800355b7  add     rsp, 40h
0x1800355bb  pop     rdi
0x1800355bc  retn
```
