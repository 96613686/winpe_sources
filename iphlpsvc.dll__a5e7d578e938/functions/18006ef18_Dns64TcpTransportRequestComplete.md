# Dns64TcpTransportRequestComplete

- ea: `0x18006ef18`
- end: `0x18006f380`
- name: `Dns64TcpTransportRequestComplete`
- size: `1128`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006c620`

## callees

- `0x1800159d4`
- `0x180045d64`
- `0x180047fc0`
- `0x1800487f8`
- `0x1800616b4`
- `0x18006a890`
- `0x18006eb88`
- `0x18006ef18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006f19b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006f24f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006f19b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006f24f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f293`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f2af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f293`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f2af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f2fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f310`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f2fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f310`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006f17d`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006f17d`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006f11d`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006f11d`
- `WS2_32!WSASend` at `0x18006f146`
- `WS2_32!WSASend` at `0x18006f146`
- `WS2_32!__imp_htons` at `0x18006f067`
- `WS2_32!__imp_htons` at `0x18006f067`
- `WS2_32!__imp_WSAGetLastError` at `0x18006f15a`
- `WS2_32!__imp_WSAGetLastError` at `0x18006f15a`
- `DNSAPI!Dns_BuildPacket` at `0x18006ef8b`
- `DNSAPI!Dns_BuildPacket` at `0x18006ef8b`

## string_xrefs

- `0x18006f083`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006f0f4`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006f1b0`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006f208`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006f264`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006f325`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`

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
0x18006ef18  push    rbx
0x18006ef1a  push    rbp
0x18006ef1b  push    rsi
0x18006ef1c  push    rdi
0x18006ef1d  push    r12
0x18006ef1f  push    r13
0x18006ef21  push    r14
0x18006ef23  push    r15
0x18006ef25  sub     rsp, 48h
0x18006ef29  mov     rbp, [rcx+3D0h]
0x18006ef30  lea     rsi, [rcx+0E8h]
0x18006ef37  add     rbp, 110h
0x18006ef3e  xor     r13d, r13d
0x18006ef41  mov     rdi, rcx
0x18006ef44  cmp     [rcx+1B0h], r13b
0x18006ef4b  jz      loc_18006F1E9
0x18006ef51  mov     eax, [rdi+1ACh]
0x18006ef57  lea     edx, [r13+1]
0x18006ef5b  movzx   r9d, word ptr [rdi+198h]
0x18006ef63  add     rcx, 180h
0x18006ef6a  mov     r8, [rdi+190h]
0x18006ef71  mov     dword ptr [rsp+88h+lpCompletionRoutine], eax
0x18006ef75  mov     eax, [rdi+1A8h]
0x18006ef7b  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x18006ef7f  mov     rax, [rdi+1A0h]
0x18006ef86  mov     qword ptr [rsp+88h+dwFlags], rax
0x18006ef8b  call    cs:__imp_Dns_BuildPacket
0x18006ef92  nop     dword ptr [rax+rax+00h]
0x18006ef97  mov     [rdi+0E0h], rax
0x18006ef9e  test    rax, rax
0x18006efa1  jz      loc_18006F1E9
0x18006efa7  movzx   ecx, word ptr [rax+258h]
0x18006efae  lea     r15, [rdi+0C0h]
0x18006efb5  sub     cx, ax
0x18006efb8  lea     r12, [rdi+0A8h]
0x18006efbf  mov     edx, 2BCh
0x18006efc4  xorps   xmm0, xmm0
0x18006efc7  sub     cx, dx
0x18006efca  mov     [rax+2BAh], cx
0x18006efd1  mov     rcx, [rdi+0E0h]
0x18006efd8  movzx   eax, word ptr [rcx+2BCh]
0x18006efdf  ror     ax, 8
0x18006efe3  mov     [rcx+2BCh], ax
0x18006efea  movzx   eax, word ptr [rcx+2C0h]
0x18006eff1  ror     ax, 8
0x18006eff5  mov     [rcx+2C0h], ax
0x18006effc  movzx   eax, word ptr [rcx+2C2h]
0x18006f003  ror     ax, 8
0x18006f007  mov     [rcx+2C2h], ax
0x18006f00e  movzx   eax, word ptr [rcx+2C4h]
0x18006f015  ror     ax, 8
0x18006f019  mov     [rcx+2C4h], ax
0x18006f020  movzx   eax, word ptr [rcx+2C6h]
0x18006f027  ror     ax, 8
0x18006f02b  mov     [rcx+2C6h], ax
0x18006f032  mov     rax, [rdi+0E0h]
0x18006f039  add     rax, 2BAh
0x18006f03f  mov     [rdi+0B0h], rax
0x18006f046  movzx   eax, word ptr [rax]
0x18006f049  add     eax, 2
0x18006f04c  mov     [r12], eax
0x18006f050  movups  xmmword ptr [r15], xmm0
0x18006f054  movups  xmmword ptr [r15+10h], xmm0
0x18006f059  mov     rbx, [rdi+0E0h]
0x18006f060  movzx   ecx, word ptr [rbx+2BAh]; hostshort
0x18006f067  call    cs:__imp_htons
0x18006f06e  nop     dword ptr [rax+rax+00h]
0x18006f073  mov     [rbx+2BAh], ax
0x18006f07a  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006f081  jz      short loc_18006F0A1
0x18006f083  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006f08a  mov     [rsp+88h+dwFlags], 4A0h
0x18006f092  mov     r8, rsi
0x18006f095  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006f09c  call    McTemplateU0psq_EventWriteTransfer
0x18006f0a1  lock inc dword ptr [rsi+2E0h]
0x18006f0a8  mov     rcx, [rsi+2E8h]
0x18006f0af  lea     rax, Dns64TcpTransportSendTimeoutCallback
0x18006f0b6  lea     r14, [rsi+280h]
0x18006f0bd  mov     qword ptr [rsp+88h+dwFlags], rax
0x18006f0c2  add     rcx, 10h
0x18006f0c6  mov     rdx, r14
0x18006f0c9  mov     r9, rdi
0x18006f0cc  mov     r8d, 0EA60h
0x18006f0d2  call    Dns64TimerEntryStart
0x18006f0d7  lea     rbx, [rdi+28h]
0x18006f0db  mov     rcx, rbx
0x18006f0de  call    RoReferenceEx
0x18006f0e3  test    al, al
0x18006f0e5  jz      loc_18006F1D6
0x18006f0eb  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006f0f2  jz      short loc_18006F112
0x18006f0f4  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006f0fb  mov     [rsp+88h+dwFlags], 4AEh
0x18006f103  mov     r8, rsi
0x18006f106  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006f10d  call    McTemplateU0psq_EventWriteTransfer
0x18006f112  lock inc dword ptr [rsi+2E0h]
0x18006f119  mov     rcx, [rdi+20h]; pio
0x18006f11d  call    cs:__imp_StartThreadpoolIo
0x18006f124  nop     dword ptr [rax+rax+00h]
0x18006f129  mov     rcx, [rdi+18h]; s
0x18006f12d  xor     r9d, r9d; lpNumberOfBytesSent
0x18006f130  mov     [rsp+88h+lpCompletionRoutine], r13; lpCompletionRoutine
0x18006f135  mov     rdx, r12; lpBuffers
0x18006f138  mov     [rsp+88h+lpOverlapped], r15; lpOverlapped
0x18006f13d  mov     [rsp+88h+dwFlags], r13d; dwFlags
0x18006f142  lea     r8d, [r9+1]; dwBufferCount
0x18006f146  call    cs:__imp_WSASend
0x18006f14d  nop     dword ptr [rax+rax+00h]
0x18006f152  test    eax, eax
0x18006f154  jz      loc_18006F238
0x18006f15a  call    cs:__imp_WSAGetLastError
0x18006f161  nop     dword ptr [rax+rax+00h]
0x18006f166  test    eax, eax
0x18006f168  jz      loc_18006F238
0x18006f16e  cmp     eax, 3E5h
0x18006f173  jz      loc_18006F238
0x18006f179  mov     rcx, [rdi+20h]; pio
0x18006f17d  call    cs:__imp_CancelThreadpoolIo
0x18006f184  nop     dword ptr [rax+rax+00h]
0x18006f189  mov     eax, 0FFFFFFFEh
0x18006f18e  lock xadd [rbx], eax
0x18006f192  cmp     eax, 3
0x18006f195  jnz     short loc_18006F1A7
0x18006f197  mov     rcx, [rdi+30h]; hEvent
0x18006f19b  call    cs:__imp_SetEvent
0x18006f1a2  nop     dword ptr [rax+rax+00h]
0x18006f1a7  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006f1ae  jz      short loc_18006F1CE
0x18006f1b0  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006f1b7  mov     [rsp+88h+dwFlags], 4C6h
0x18006f1bf  mov     r8, rsi
0x18006f1c2  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006f1c9  call    McTemplateU0psq_EventWriteTransfer
0x18006f1ce  mov     rcx, rsi
0x18006f1d1  call    Dns64RequestDereferenceEx
0x18006f1d6  mov     rcx, [rsi+2E8h]
0x18006f1dd  mov     rdx, r14
0x18006f1e0  add     rcx, 10h
0x18006f1e4  call    Dns64TimerEntryStop
0x18006f1e9  xor     edx, edx
0x18006f1eb  mov     rcx, rbp
0x18006f1ee  lea     r8d, [rdx+1]
0x18006f1f2  call    Dns64TcpTransportRefillPostedAcceptRequests
0x18006f1f7  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006f1fe  jz      short loc_18006F21E
0x18006f200  mov     [rsp+88h+dwFlags], 501h
0x18006f208  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006f20f  mov     r8, rsi
0x18006f212  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006f219  call    McTemplateU0psq_EventWriteTransfer
0x18006f21e  mov     rcx, rsi
0x18006f221  call    Dns64RequestDereferenceEx
0x18006f226  add     rsp, 48h
0x18006f22a  pop     r15
0x18006f22c  pop     r14
0x18006f22e  pop     r13
0x18006f230  pop     r12
0x18006f232  pop     rdi
0x18006f233  pop     rsi
0x18006f234  pop     rbp
0x18006f235  pop     rbx
0x18006f236  retn
0x18006f238  xor     r14d, r14d
0x18006f23b  xor     r12d, r12d
0x18006f23e  lea     eax, [r14-2]
0x18006f242  lock xadd [rbx], eax
0x18006f246  cmp     eax, 3
0x18006f249  jnz     short loc_18006F25B
0x18006f24b  mov     rcx, [rdi+30h]; hEvent
0x18006f24f  call    cs:__imp_SetEvent
0x18006f256  nop     dword ptr [rax+rax+00h]
0x18006f25b  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006f262  jz      short loc_18006F282
0x18006f264  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006f26b  mov     [rsp+88h+dwFlags], 4D2h
0x18006f273  mov     r8, rsi
0x18006f276  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006f27d  call    McTemplateU0psq_EventWriteTransfer
0x18006f282  lock inc dword ptr [rsi+2E0h]
0x18006f289  lea     r15, [rdi+100h]
0x18006f290  mov     rcx, r15; lpCriticalSection
0x18006f293  call    cs:__imp_EnterCriticalSection
0x18006f29a  nop     dword ptr [rax+rax+00h]
0x18006f29f  cmp     [rdi+0Ch], r12d
0x18006f2a3  jnz     short loc_18006F30D
0x18006f2a5  cmp     [rdi+10h], r12d
0x18006f2a9  jnz     short loc_18006F30D
0x18006f2ab  lea     rcx, [rbp+48h]; lpCriticalSection
0x18006f2af  call    cs:__imp_EnterCriticalSection
0x18006f2b6  nop     dword ptr [rax+rax+00h]
0x18006f2bb  cmp     [rbp+0], r12d
0x18006f2bf  jz      short loc_18006F2F5
0x18006f2c1  lea     rax, [rbp+38h]
0x18006f2c5  mov     rcx, [rax]
0x18006f2c8  cmp     [rcx+8], rax
0x18006f2cc  jz      short loc_18006F2D5
0x18006f2ce  mov     ecx, 3
0x18006f2d3  int     29h; Win8: RtlFailFast(ecx)
0x18006f2d5  mov     [rsi+8], rax
0x18006f2d9  mov     [rsi], rcx
0x18006f2dc  mov     [rcx+8], rsi
0x18006f2e0  mov     [rax], rsi
0x18006f2e3  mov     eax, 1
0x18006f2e8  mov     [rdi+0F8h], eax
0x18006f2ee  mov     r13d, eax
0x18006f2f1  cmp     [rbp+0], r12d
0x18006f2f5  lea     rcx, [rbp+48h]; lpCriticalSection
0x18006f2f9  setz    r14b
0x18006f2fd  call    cs:__imp_LeaveCriticalSection
0x18006f304  nop     dword ptr [rax+rax+00h]
0x18006f309  mov     r12d, [rdi+10h]
0x18006f30d  mov     rcx, r15; lpCriticalSection
0x18006f310  call    cs:__imp_LeaveCriticalSection
0x18006f317  nop     dword ptr [rax+rax+00h]
0x18006f31c  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006f323  jz      short loc_18006F343
0x18006f325  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006f32c  mov     [rsp+88h+dwFlags], 4E4h
0x18006f334  mov     r8, rsi
0x18006f337  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006f33e  call    McTemplateU0psq_EventWriteTransfer
0x18006f343  mov     rcx, rsi
0x18006f346  call    Dns64RequestDereferenceEx
0x18006f34b  test    r13d, r13d
0x18006f34e  jnz     loc_18006F226
0x18006f354  test    r14d, r14d
0x18006f357  jnz     short loc_18006F35E
0x18006f359  test    r12d, r12d
0x18006f35c  jz      short loc_18006F366
0x18006f35e  mov     rcx, rdi
0x18006f361  call    Dns64TcpTransportRequestCloseReceiveSocket
0x18006f366  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006f36d  jz      loc_18006F21E
0x18006f373  mov     [rsp+88h+dwFlags], 4F0h
0x18006f37b  jmp     loc_18006F208
```
