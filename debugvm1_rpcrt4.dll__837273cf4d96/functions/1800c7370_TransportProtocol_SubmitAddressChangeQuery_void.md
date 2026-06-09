# TransportProtocol::SubmitAddressChangeQuery(void)

- ea: `0x1800c7370`
- end: `0x1800c7430`
- name: `?SubmitAddressChangeQuery@TransportProtocol@@AEAAHXZ`
- size: `192`
- prototype: `__int64 __fastcall(TransportProtocol *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800c7074`
- `0x1800c7204`
- `0x1800c74d8`

## callees

- `0x180021ce0`
- `0x1800c7370`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800c73b7`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800c73b7`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800c7416`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800c7416`
- `WS2_32!WSAIoctl` at `0x1800c73f7`
- `WS2_32!WSAIoctl` at `0x1800c73f7`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c7402`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c7402`

## pseudocode

```c
__int64 __fastcall TransportProtocol::SubmitAddressChangeQuery(TransportProtocol *this)
{
  PTP_IO *v2; // rcx
  DWORD cbOutBuffer; // [rsp+28h] [rbp-30h]
  int lpcbBytesReturned; // [rsp+30h] [rbp-28h]

  LogEvent(0x57u, 0x45u, this, 0, 0, cbOutBuffer, lpcbBytesReturned);
  v2 = (PTP_IO *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  StartThreadpoolIo(*v2);
  if ( WSAIoctl(*((_QWORD *)this + 3), 0x28000017u, 0, 0, 0, 0, &cbBytesReturned, (LPWSAOVERLAPPED)this + 1, 0) != -1
    || WSAGetLastError() == 997 )
  {
    return 1;
  }
  CancelThreadpoolIo(**((PTP_IO **)this + 8));
  return 0;
}

```

## disassembly

```asm
0x1800c7370  mov     [rsp+arg_0], rbx
0x1800c7375  push    rdi
0x1800c7376  sub     rsp, 50h
0x1800c737a  mov     rdi, rcx
0x1800c737d  mov     [rsp+58h+lpvOutBuffer], 0; unsigned __int64
0x1800c7386  mov     r8, rcx; void *
0x1800c7389  xor     r9d, r9d; void *
0x1800c738c  mov     cl, 57h ; 'W'; unsigned __int8
0x1800c738e  mov     dl, 45h ; 'E'; unsigned __int8
0x1800c7390  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x1800c7395  mov     rcx, [rdi+40h]
0x1800c7399  lea     rbx, [rdi+20h]
0x1800c739d  mov     qword ptr [rbx+18h], 0
0x1800c73a5  mov     qword ptr [rdi+30h], 0
0x1800c73ad  mov     qword ptr [rbx], 0
0x1800c73b4  mov     rcx, [rcx]; pio
0x1800c73b7  call    cs:__imp_StartThreadpoolIo
0x1800c73bd  mov     rcx, [rdi+18h]; s
0x1800c73c1  lea     rax, cbBytesReturned
0x1800c73c8  mov     [rsp+58h+lpCompletionRoutine], 0; lpCompletionRoutine
0x1800c73d1  xor     r9d, r9d; cbInBuffer
0x1800c73d4  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x1800c73d9  xor     r8d, r8d; lpvInBuffer
0x1800c73dc  mov     [rsp+58h+lpcbBytesReturned], rax; lpcbBytesReturned
0x1800c73e1  mov     edx, 28000017h; dwIoControlCode
0x1800c73e6  mov     [rsp+58h+cbOutBuffer], 0; cbOutBuffer
0x1800c73ee  mov     [rsp+58h+lpvOutBuffer], 0; lpvOutBuffer
0x1800c73f7  call    cs:__imp_WSAIoctl
0x1800c73fd  cmp     eax, 0FFFFFFFFh
0x1800c7400  jnz     short loc_1800C7420
0x1800c7402  call    cs:__imp_WSAGetLastError
0x1800c7408  cmp     eax, 3E5h
0x1800c740d  jz      short loc_1800C7420
0x1800c740f  mov     rcx, [rdi+40h]
0x1800c7413  mov     rcx, [rcx]; pio
0x1800c7416  call    cs:__imp_CancelThreadpoolIo
0x1800c741c  xor     eax, eax
0x1800c741e  jmp     short loc_1800C7425
0x1800c7420  mov     eax, 1
0x1800c7425  mov     rbx, [rsp+58h+arg_0]
0x1800c742a  add     rsp, 50h
0x1800c742e  pop     rdi
0x1800c742f  retn
```
