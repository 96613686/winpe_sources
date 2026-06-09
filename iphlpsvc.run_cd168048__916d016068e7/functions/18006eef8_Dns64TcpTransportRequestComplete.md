# Dns64TcpTransportRequestComplete

- ea: `0x18006eef8`
- end: `0x18006f360`
- name: `Dns64TcpTransportRequestComplete`
- size: `1128`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006c600`

## callees

- `0x1800159c4`
- `0x180045da4`
- `0x180048000`
- `0x180048838`
- `0x180061694`
- `0x18006a870`
- `0x18006eb68`
- `0x18006eef8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006f17b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006f22f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006f17b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006f22f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f273`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f28f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f273`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f28f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f2dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f2f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f2dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f2f0`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006f15d`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006f15d`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006f0fd`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006f0fd`
- `WS2_32!WSASend` at `0x18006f126`
- `WS2_32!WSASend` at `0x18006f126`
- `WS2_32!__imp_htons` at `0x18006f047`
- `WS2_32!__imp_htons` at `0x18006f047`
- `WS2_32!__imp_WSAGetLastError` at `0x18006f13a`
- `WS2_32!__imp_WSAGetLastError` at `0x18006f13a`
- `DNSAPI!Dns_BuildPacket` at `0x18006ef6b`
- `DNSAPI!Dns_BuildPacket` at `0x18006ef6b`

## string_xrefs

- `0x18006f063`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006f0d4`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006f190`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006f1e8`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006f244`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006f305`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`

## pseudocode

```c
__int64 __fastcall Dns64TcpTransportRequestComplete(__int64 a1)
{
  __int64 v1; // rsi
  __int64 v2; // rbp
  int v3; // r13d
  __int64 v5; // rax
  _WORD *v6; // rcx
  unsigned __int16 *v7; // rax
  __int64 v8; // rbx
  int v9; // ecx
  volatile signed __int32 *v10; // rbx
  int v11; // ecx
  int v12; // ecx
  int Error; // eax
  int v14; // ecx
  int v15; // ecx
  __int64 result; // rax
  int v17; // r14d
  int v18; // r12d
  bool v19; // zf
  _QWORD *v20; // rax
  __int64 v21; // rcx
  int v22; // ecx
  int v23; // ecx

  v1 = a1 + 232;
  v2 = *(_QWORD *)(a1 + 976) + 272LL;
  v3 = 0;
  if ( !*(_BYTE *)(a1 + 432) )
    goto LABEL_17;
  v5 = Dns_BuildPacket(
         a1 + 384,
         1,
         *(_QWORD *)(a1 + 400),
         *(unsigned __int16 *)(a1 + 408),
         *(_QWORD *)(a1 + 416),
         *(_DWORD *)(a1 + 424),
         *(_DWORD *)(a1 + 428));
  *(_QWORD *)(a1 + 224) = v5;
  if ( !v5 )
    goto LABEL_17;
  *(_WORD *)(v5 + 698) = *(_WORD *)(v5 + 600) - v5 - 700;
  v6 = *(_WORD **)(a1 + 224);
  v6[350] = __ROR2__(v6[350], 8);
  v6[352] = __ROR2__(v6[352], 8);
  v6[353] = __ROR2__(v6[353], 8);
  v6[354] = __ROR2__(v6[354], 8);
  v6[355] = __ROR2__(v6[355], 8);
  v7 = (unsigned __int16 *)(*(_QWORD *)(a1 + 224) + 698LL);
  *(_QWORD *)(a1 + 176) = v7;
  *(_DWORD *)(a1 + 168) = *v7 + 2;
  *(_OWORD *)(a1 + 192) = 0;
  *(_OWORD *)(a1 + 208) = 0;
  v8 = *(_QWORD *)(a1 + 224);
  *(_WORD *)(v8 + 698) = htons(*(_WORD *)(v8 + 698));
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v9,
      (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE,
      v1,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
      160);
  _InterlockedIncrement((volatile signed __int32 *)(v1 + 736));
  Dns64TimerEntryStart(*(_QWORD *)(v1 + 744) + 16, v1 + 640, 60000, a1, (__int64)Dns64TcpTransportSendTimeoutCallback);
  v10 = (volatile signed __int32 *)(a1 + 40);
  if ( !(unsigned __int8)RoReferenceEx(a1 + 40) )
  {
LABEL_16:
    Dns64TimerEntryStop(*(_QWORD *)(v1 + 744) + 16LL, v1 + 640);
LABEL_17:
    Dns64TcpTransportRefillPostedAcceptRequests(v2, 0);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v15,
        (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
        v1,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
        1);
    return Dns64RequestDereferenceEx(v1);
  }
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v11,
      (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE,
      v1,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
      174);
  _InterlockedIncrement((volatile signed __int32 *)(v1 + 736));
  StartThreadpoolIo(*(PTP_IO *)(a1 + 32));
  if ( WSASend(*(_QWORD *)(a1 + 24), (LPWSABUF)(a1 + 168), 1u, 0, 0, (LPWSAOVERLAPPED)(a1 + 192), 0) )
  {
    Error = WSAGetLastError();
    if ( Error )
    {
      if ( Error != 997 )
      {
        CancelThreadpoolIo(*(PTP_IO *)(a1 + 32));
        if ( _InterlockedExchangeAdd(v10, 0xFFFFFFFE) == 3 )
          SetEvent(*(HANDLE *)(a1 + 48));
        if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
          McTemplateU0psq_EventWriteTransfer(
            v14,
            (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
            v1,
            (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
            198);
        Dns64RequestDereferenceEx(v1);
        goto LABEL_16;
      }
    }
  }
  v17 = 0;
  v18 = 0;
  if ( _InterlockedExchangeAdd(v10, 0xFFFFFFFE) == 3 )
    SetEvent(*(HANDLE *)(a1 + 48));
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v12,
      (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE,
      v1,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
      210);
  _InterlockedIncrement((volatile signed __int32 *)(v1 + 736));
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 256));
  if ( !*(_DWORD *)(a1 + 12) && !*(_DWORD *)(a1 + 16) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 72));
    v19 = *(_DWORD *)v2 == 0;
    if ( *(_DWORD *)v2 )
    {
      v20 = (_QWORD *)(v2 + 56);
      v21 = *(_QWORD *)(v2 + 56);
      if ( *(_QWORD *)(v21 + 8) != v2 + 56 )
        __fastfail(3u);
      *(_QWORD *)(v1 + 8) = v20;
      *(_QWORD *)v1 = v21;
      *(_QWORD *)(v21 + 8) = v1;
      *v20 = v1;
      *(_DWORD *)(a1 + 248) = 1;
      v3 = 1;
      v19 = *(_DWORD *)v2 == 0;
    }
    LOBYTE(v17) = v19;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 72));
    v18 = *(_DWORD *)(a1 + 16);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 256));
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v22,
      (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
      v1,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
      228);
  result = Dns64RequestDereferenceEx(v1);
  if ( !v3 )
  {
    if ( v17 || v18 )
      Dns64TcpTransportRequestCloseReceiveSocket(a1);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v23,
        (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
        v1,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
        240);
    return Dns64RequestDereferenceEx(v1);
  }
  return result;
}

```

## disassembly

```asm
0x18006eef8  push    rbx
0x18006eefa  push    rbp
0x18006eefb  push    rsi
0x18006eefc  push    rdi
0x18006eefd  push    r12
0x18006eeff  push    r13
0x18006ef01  push    r14
0x18006ef03  push    r15
0x18006ef05  sub     rsp, 48h
0x18006ef09  mov     rbp, [rcx+3D0h]
0x18006ef10  lea     rsi, [rcx+0E8h]
0x18006ef17  add     rbp, 110h
0x18006ef1e  xor     r13d, r13d
0x18006ef21  mov     rdi, rcx
0x18006ef24  cmp     [rcx+1B0h], r13b
0x18006ef2b  jz      loc_18006F1C9
0x18006ef31  mov     eax, [rdi+1ACh]
0x18006ef37  lea     edx, [r13+1]
0x18006ef3b  movzx   r9d, word ptr [rdi+198h]
0x18006ef43  add     rcx, 180h
0x18006ef4a  mov     r8, [rdi+190h]
0x18006ef51  mov     dword ptr [rsp+88h+lpCompletionRoutine], eax
0x18006ef55  mov     eax, [rdi+1A8h]
0x18006ef5b  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x18006ef5f  mov     rax, [rdi+1A0h]
0x18006ef66  mov     qword ptr [rsp+88h+dwFlags], rax
0x18006ef6b  call    cs:__imp_Dns_BuildPacket
0x18006ef72  nop     dword ptr [rax+rax+00h]
0x18006ef77  mov     [rdi+0E0h], rax
0x18006ef7e  test    rax, rax
0x18006ef81  jz      loc_18006F1C9
0x18006ef87  movzx   ecx, word ptr [rax+258h]
0x18006ef8e  lea     r15, [rdi+0C0h]
0x18006ef95  sub     cx, ax
0x18006ef98  lea     r12, [rdi+0A8h]
0x18006ef9f  mov     edx, 2BCh
0x18006efa4  xorps   xmm0, xmm0
0x18006efa7  sub     cx, dx
0x18006efaa  mov     [rax+2BAh], cx
0x18006efb1  mov     rcx, [rdi+0E0h]
0x18006efb8  movzx   eax, word ptr [rcx+2BCh]
0x18006efbf  ror     ax, 8
0x18006efc3  mov     [rcx+2BCh], ax
0x18006efca  movzx   eax, word ptr [rcx+2C0h]
0x18006efd1  ror     ax, 8
0x18006efd5  mov     [rcx+2C0h], ax
0x18006efdc  movzx   eax, word ptr [rcx+2C2h]
0x18006efe3  ror     ax, 8
0x18006efe7  mov     [rcx+2C2h], ax
0x18006efee  movzx   eax, word ptr [rcx+2C4h]
0x18006eff5  ror     ax, 8
0x18006eff9  mov     [rcx+2C4h], ax
0x18006f000  movzx   eax, word ptr [rcx+2C6h]
0x18006f007  ror     ax, 8
0x18006f00b  mov     [rcx+2C6h], ax
0x18006f012  mov     rax, [rdi+0E0h]
0x18006f019  add     rax, 2BAh
0x18006f01f  mov     [rdi+0B0h], rax
0x18006f026  movzx   eax, word ptr [rax]
0x18006f029  add     eax, 2
0x18006f02c  mov     [r12], eax
0x18006f030  movups  xmmword ptr [r15], xmm0
0x18006f034  movups  xmmword ptr [r15+10h], xmm0
0x18006f039  mov     rbx, [rdi+0E0h]
0x18006f040  movzx   ecx, word ptr [rbx+2BAh]; hostshort
0x18006f047  call    cs:__imp_htons
0x18006f04e  nop     dword ptr [rax+rax+00h]
0x18006f053  mov     [rbx+2BAh], ax
0x18006f05a  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006f061  jz      short loc_18006F081
0x18006f063  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006f06a  mov     [rsp+88h+dwFlags], 4A0h
0x18006f072  mov     r8, rsi
0x18006f075  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006f07c  call    McTemplateU0psq_EventWriteTransfer
0x18006f081  lock inc dword ptr [rsi+2E0h]
0x18006f088  mov     rcx, [rsi+2E8h]
0x18006f08f  lea     rax, Dns64TcpTransportSendTimeoutCallback
0x18006f096  lea     r14, [rsi+280h]
0x18006f09d  mov     qword ptr [rsp+88h+dwFlags], rax
0x18006f0a2  add     rcx, 10h
0x18006f0a6  mov     rdx, r14
0x18006f0a9  mov     r9, rdi
0x18006f0ac  mov     r8d, 0EA60h
0x18006f0b2  call    Dns64TimerEntryStart
0x18006f0b7  lea     rbx, [rdi+28h]
0x18006f0bb  mov     rcx, rbx
0x18006f0be  call    RoReferenceEx
0x18006f0c3  test    al, al
0x18006f0c5  jz      loc_18006F1B6
0x18006f0cb  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006f0d2  jz      short loc_18006F0F2
0x18006f0d4  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006f0db  mov     [rsp+88h+dwFlags], 4AEh
0x18006f0e3  mov     r8, rsi
0x18006f0e6  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006f0ed  call    McTemplateU0psq_EventWriteTransfer
0x18006f0f2  lock inc dword ptr [rsi+2E0h]
0x18006f0f9  mov     rcx, [rdi+20h]; pio
0x18006f0fd  call    cs:__imp_StartThreadpoolIo
0x18006f104  nop     dword ptr [rax+rax+00h]
0x18006f109  mov     rcx, [rdi+18h]; s
0x18006f10d  xor     r9d, r9d; lpNumberOfBytesSent
0x18006f110  mov     [rsp+88h+lpCompletionRoutine], r13; lpCompletionRoutine
0x18006f115  mov     rdx, r12; lpBuffers
0x18006f118  mov     [rsp+88h+lpOverlapped], r15; lpOverlapped
0x18006f11d  mov     [rsp+88h+dwFlags], r13d; dwFlags
0x18006f122  lea     r8d, [r9+1]; dwBufferCount
0x18006f126  call    cs:__imp_WSASend
0x18006f12d  nop     dword ptr [rax+rax+00h]
0x18006f132  test    eax, eax
0x18006f134  jz      loc_18006F218
0x18006f13a  call    cs:__imp_WSAGetLastError
0x18006f141  nop     dword ptr [rax+rax+00h]
0x18006f146  test    eax, eax
0x18006f148  jz      loc_18006F218
0x18006f14e  cmp     eax, 3E5h
0x18006f153  jz      loc_18006F218
0x18006f159  mov     rcx, [rdi+20h]; pio
0x18006f15d  call    cs:__imp_CancelThreadpoolIo
0x18006f164  nop     dword ptr [rax+rax+00h]
0x18006f169  mov     eax, 0FFFFFFFEh
0x18006f16e  lock xadd [rbx], eax
0x18006f172  cmp     eax, 3
0x18006f175  jnz     short loc_18006F187
0x18006f177  mov     rcx, [rdi+30h]; hEvent
0x18006f17b  call    cs:__imp_SetEvent
0x18006f182  nop     dword ptr [rax+rax+00h]
0x18006f187  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006f18e  jz      short loc_18006F1AE
0x18006f190  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006f197  mov     [rsp+88h+dwFlags], 4C6h
0x18006f19f  mov     r8, rsi
0x18006f1a2  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006f1a9  call    McTemplateU0psq_EventWriteTransfer
0x18006f1ae  mov     rcx, rsi
0x18006f1b1  call    Dns64RequestDereferenceEx
0x18006f1b6  mov     rcx, [rsi+2E8h]
0x18006f1bd  mov     rdx, r14
0x18006f1c0  add     rcx, 10h
0x18006f1c4  call    Dns64TimerEntryStop
0x18006f1c9  xor     edx, edx
0x18006f1cb  mov     rcx, rbp
0x18006f1ce  lea     r8d, [rdx+1]
0x18006f1d2  call    Dns64TcpTransportRefillPostedAcceptRequests
0x18006f1d7  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006f1de  jz      short loc_18006F1FE
0x18006f1e0  mov     [rsp+88h+dwFlags], 501h
0x18006f1e8  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006f1ef  mov     r8, rsi
0x18006f1f2  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006f1f9  call    McTemplateU0psq_EventWriteTransfer
0x18006f1fe  mov     rcx, rsi
0x18006f201  call    Dns64RequestDereferenceEx
0x18006f206  add     rsp, 48h
0x18006f20a  pop     r15
0x18006f20c  pop     r14
0x18006f20e  pop     r13
0x18006f210  pop     r12
0x18006f212  pop     rdi
0x18006f213  pop     rsi
0x18006f214  pop     rbp
0x18006f215  pop     rbx
0x18006f216  retn
0x18006f218  xor     r14d, r14d
0x18006f21b  xor     r12d, r12d
0x18006f21e  lea     eax, [r14-2]
0x18006f222  lock xadd [rbx], eax
0x18006f226  cmp     eax, 3
0x18006f229  jnz     short loc_18006F23B
0x18006f22b  mov     rcx, [rdi+30h]; hEvent
0x18006f22f  call    cs:__imp_SetEvent
0x18006f236  nop     dword ptr [rax+rax+00h]
0x18006f23b  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006f242  jz      short loc_18006F262
0x18006f244  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006f24b  mov     [rsp+88h+dwFlags], 4D2h
0x18006f253  mov     r8, rsi
0x18006f256  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006f25d  call    McTemplateU0psq_EventWriteTransfer
0x18006f262  lock inc dword ptr [rsi+2E0h]
0x18006f269  lea     r15, [rdi+100h]
0x18006f270  mov     rcx, r15; lpCriticalSection
0x18006f273  call    cs:__imp_EnterCriticalSection
0x18006f27a  nop     dword ptr [rax+rax+00h]
0x18006f27f  cmp     [rdi+0Ch], r12d
0x18006f283  jnz     short loc_18006F2ED
0x18006f285  cmp     [rdi+10h], r12d
0x18006f289  jnz     short loc_18006F2ED
0x18006f28b  lea     rcx, [rbp+48h]; lpCriticalSection
0x18006f28f  call    cs:__imp_EnterCriticalSection
0x18006f296  nop     dword ptr [rax+rax+00h]
0x18006f29b  cmp     [rbp+0], r12d
0x18006f29f  jz      short loc_18006F2D5
0x18006f2a1  lea     rax, [rbp+38h]
0x18006f2a5  mov     rcx, [rax]
0x18006f2a8  cmp     [rcx+8], rax
0x18006f2ac  jz      short loc_18006F2B5
0x18006f2ae  mov     ecx, 3
0x18006f2b3  int     29h; Win8: RtlFailFast(ecx)
0x18006f2b5  mov     [rsi+8], rax
0x18006f2b9  mov     [rsi], rcx
0x18006f2bc  mov     [rcx+8], rsi
0x18006f2c0  mov     [rax], rsi
0x18006f2c3  mov     eax, 1
0x18006f2c8  mov     [rdi+0F8h], eax
0x18006f2ce  mov     r13d, eax
0x18006f2d1  cmp     [rbp+0], r12d
0x18006f2d5  lea     rcx, [rbp+48h]; lpCriticalSection
0x18006f2d9  setz    r14b
0x18006f2dd  call    cs:__imp_LeaveCriticalSection
0x18006f2e4  nop     dword ptr [rax+rax+00h]
0x18006f2e9  mov     r12d, [rdi+10h]
0x18006f2ed  mov     rcx, r15; lpCriticalSection
0x18006f2f0  call    cs:__imp_LeaveCriticalSection
0x18006f2f7  nop     dword ptr [rax+rax+00h]
0x18006f2fc  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006f303  jz      short loc_18006F323
0x18006f305  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006f30c  mov     [rsp+88h+dwFlags], 4E4h
0x18006f314  mov     r8, rsi
0x18006f317  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006f31e  call    McTemplateU0psq_EventWriteTransfer
0x18006f323  mov     rcx, rsi
0x18006f326  call    Dns64RequestDereferenceEx
0x18006f32b  test    r13d, r13d
0x18006f32e  jnz     loc_18006F206
0x18006f334  test    r14d, r14d
0x18006f337  jnz     short loc_18006F33E
0x18006f339  test    r12d, r12d
0x18006f33c  jz      short loc_18006F346
0x18006f33e  mov     rcx, rdi
0x18006f341  call    Dns64TcpTransportRequestCloseReceiveSocket
0x18006f346  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006f34d  jz      loc_18006F1FE
0x18006f353  mov     [rsp+88h+dwFlags], 4F0h
0x18006f35b  jmp     loc_18006F1E8
```
