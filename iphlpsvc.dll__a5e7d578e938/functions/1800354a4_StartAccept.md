# StartAccept

- ea: `0x1800354a4`
- end: `0x1800355ce`
- name: `StartAccept`
- size: `298`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18003524c`
- `0x18003e1a4`
- `0x18003e210`

## callees

- `0x18000d7c0`
- `0x1800354a4`
- `0x18003e1a4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18003559e`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18003559e`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18003553e`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18003553e`
- `MSWSOCK!AcceptEx` at `0x180035575`
- `MSWSOCK!AcceptEx` at `0x180035575`
- `WS2_32!__imp_socket` at `0x1800354d3`
- `WS2_32!__imp_socket` at `0x1800354d3`
- `WS2_32!__imp_WSAGetLastError` at `0x1800354f0`
- `WS2_32!__imp_WSAGetLastError` at `0x180035585`
- `WS2_32!__imp_WSAGetLastError` at `0x1800354f0`
- `WS2_32!__imp_WSAGetLastError` at `0x180035585`

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
0x1800354a4  mov     [rsp+arg_8], rbx
0x1800354a9  mov     [rsp+arg_10], rsi
0x1800354ae  push    rdi
0x1800354af  sub     rsp, 40h
0x1800354b3  mov     rbx, rcx
0x1800354b6  mov     [rsp+48h+dwBytesReceived], 0
0x1800354be  mov     edi, 1
0x1800354c3  lock add [rcx+10h], edi
0x1800354c7  movzx   ecx, word ptr [rcx+0B8h]; af
0x1800354ce  xor     r8d, r8d; protocol
0x1800354d1  mov     edx, edi; type
0x1800354d3  call    cs:__imp_socket
0x1800354da  nop     dword ptr [rax+rax+00h]
0x1800354df  mov     [rbx+20h], rax
0x1800354e3  lea     rsi, [rbx+90h]
0x1800354ea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800354ee  jnz     short loc_180035512
0x1800354f0  call    cs:__imp_WSAGetLastError
0x1800354f7  nop     dword ptr [rax+rax+00h]
0x1800354fc  mov     rdx, rsi
0x1800354ff  xor     ecx, ecx
0x180035501  mov     r8d, eax
0x180035504  mov     ebx, eax
0x180035506  call    ProcessAcceptError
0x18003550b  mov     eax, ebx
0x18003550d  jmp     loc_1800355BD
0x180035512  mov     r9, rsi
0x180035515  lea     rdx, aStartingAnAcce; "Starting an accept with new socket %Ix "...
0x18003551c  mov     r8, rax
0x18003551f  mov     ecx, 80000h
0x180035524  call    EventWrite0
0x180035529  mov     rcx, [rbx+28h]; pio
0x18003552d  mov     qword ptr [rbx+0A8h], 0
0x180035538  mov     [rbx+0B0h], edi
0x18003553e  call    cs:__imp_StartThreadpoolIo
0x180035545  nop     dword ptr [rax+rax+00h]
0x18003554a  mov     rdx, [rbx+20h]; sAcceptSocket
0x18003554e  lea     rax, [rsp+48h+dwBytesReceived]
0x180035553  mov     rcx, [rbx+18h]; sListenSocket
0x180035557  lea     r8, [rbx+38h]; lpOutputBuffer
0x18003555b  mov     [rsp+48h+lpOverlapped], rsi; lpOverlapped
0x180035560  xor     r9d, r9d; dwReceiveDataLength
0x180035563  mov     [rsp+48h+lpdwBytesReceived], rax; lpdwBytesReceived
0x180035568  mov     eax, 2Ch ; ','
0x18003556d  mov     [rsp+48h+dwRemoteAddressLength], eax; dwRemoteAddressLength
0x180035571  mov     [rsp+48h+dwLocalAddressLength], eax; dwLocalAddressLength
0x180035575  call    cs:__imp_AcceptEx
0x18003557c  nop     dword ptr [rax+rax+00h]
0x180035581  test    eax, eax
0x180035583  jnz     short loc_1800355BB
0x180035585  call    cs:__imp_WSAGetLastError
0x18003558c  nop     dword ptr [rax+rax+00h]
0x180035591  mov     edi, eax
0x180035593  cmp     eax, 3E5h
0x180035598  jz      short loc_1800355BB
0x18003559a  mov     rcx, [rbx+28h]; pio
0x18003559e  call    cs:__imp_CancelThreadpoolIo
0x1800355a5  nop     dword ptr [rax+rax+00h]
0x1800355aa  mov     r8d, edi
0x1800355ad  mov     rdx, rsi
0x1800355b0  xor     ecx, ecx
0x1800355b2  call    ProcessAcceptError
0x1800355b7  mov     eax, edi
0x1800355b9  jmp     short loc_1800355BD
0x1800355bb  xor     eax, eax
0x1800355bd  mov     rbx, [rsp+48h+arg_8]
0x1800355c2  mov     rsi, [rsp+48h+arg_10]
0x1800355c7  add     rsp, 40h
0x1800355cb  pop     rdi
0x1800355cc  retn
```
