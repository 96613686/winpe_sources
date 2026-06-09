# Dns64TcpTransportReceiveComplete

- ea: `0x18006e680`
- end: `0x18006ea28`
- name: `Dns64TcpTransportReceiveComplete`
- size: `936`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006e400`

## callees

- `0x180004c54`
- `0x180012dbc`
- `0x1800159c4`
- `0x180045da4`
- `0x18004c1c8`
- `0x180061694`
- `0x18006a870`
- `0x18006bdac`
- `0x18006e680`
- `0x18006eb68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006e863`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006e8b5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006e863`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006e8b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e760`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e770`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e760`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e770`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e8ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e903`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e8ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e903`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006e845`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006e845`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006e7ed`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006e7ed`
- `WS2_32!WSARecv` at `0x18006e81a`
- `WS2_32!WSARecv` at `0x18006e81a`
- `WS2_32!__imp_htons` at `0x18006e6af`
- `WS2_32!__imp_htons` at `0x18006e6af`
- `WS2_32!__imp_WSAGetLastError` at `0x18006e82a`
- `WS2_32!__imp_WSAGetLastError` at `0x18006e82a`
- `DNSAPI!Dns_ParseMessage` at `0x18006e9bb`
- `DNSAPI!Dns_ParseMessage` at `0x18006e9bb`

## string_xrefs

- `0x18006e7c4`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006e878`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006e91c`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006e9fa`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`

## pseudocode

```c
__int64 __fastcall Dns64TcpTransportReceiveComplete(__int64 a1)
{
  __int64 *v1; // rsi
  __int64 v2; // r13
  u_short v4; // ax
  bool v5; // zf
  void *v6; // rax
  void *v7; // rbp
  int v8; // ebx
  volatile signed __int32 *v9; // rbx
  int v10; // ecx
  int v11; // ebx
  __int64 *v12; // rax
  __int64 **v13; // rcx
  int v14; // ecx
  int Error; // eax
  int v16; // ecx
  int v17; // r14d
  int v18; // ecx
  _WORD *v19; // rdx
  int v21; // ecx

  v1 = (__int64 *)(a1 + 232);
  v2 = *(_QWORD *)(a1 + 976);
  if ( !*(_QWORD *)(a1 + 56) )
  {
    v4 = htons(*(_WORD *)(a1 + 64));
    v5 = *(_DWORD *)(a1 + 68) == 2;
    *(_WORD *)(a1 + 64) = v4;
    if ( v5 && v4 >= 0xCu )
    {
      v6 = (void *)MALLOC(v4);
      *(_QWORD *)(a1 + 56) = v6;
      v7 = v6;
      if ( v6 )
      {
        v8 = *(unsigned __int16 *)(a1 + 64);
        memset_0(v6, 0, *(unsigned __int16 *)(a1 + 64));
        *(_QWORD *)(a1 + 176) = v7;
        *(_DWORD *)(a1 + 168) = v8;
        *(_DWORD *)(a1 + 68) = 0;
        *(_DWORD *)(a1 + 184) = 8;
        v9 = (volatile signed __int32 *)(a1 + 40);
        *(_OWORD *)(a1 + 192) = 0;
        *(_OWORD *)(a1 + 208) = 0;
        if ( (unsigned __int8)RoReferenceEx(a1 + 40) )
        {
          if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
            McTemplateU0psq_EventWriteTransfer(
              v10,
              (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE,
              (_DWORD)v1,
              (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
              181);
          _InterlockedIncrement((volatile signed __int32 *)v1 + 184);
          StartThreadpoolIo(*(PTP_IO *)(a1 + 32));
          if ( !WSARecv(
                  *(_QWORD *)(a1 + 24),
                  (LPWSABUF)(a1 + 168),
                  1u,
                  0,
                  (LPDWORD)(a1 + 184),
                  (LPWSAOVERLAPPED)(a1 + 192),
                  0)
            || (Error = WSAGetLastError()) == 0
            || Error == 997 )
          {
            if ( _InterlockedExchangeAdd(v9, 0xFFFFFFFE) == 3 )
              SetEvent(*(HANDLE *)(a1 + 48));
            if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
              McTemplateU0psq_EventWriteTransfer(
                v14,
                (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
                (_DWORD)v1,
                (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
                213);
            return Dns64RequestDereferenceEx(v1);
          }
          CancelThreadpoolIo(*(PTP_IO *)(a1 + 32));
          if ( _InterlockedExchangeAdd(v9, 0xFFFFFFFE) == 3 )
            SetEvent(*(HANDLE *)(a1 + 48));
          if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
            McTemplateU0psq_EventWriteTransfer(
              v16,
              (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
              (_DWORD)v1,
              (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
              205);
          Dns64RequestDereferenceEx(v1);
        }
        else
        {
          FREE(*(_QWORD *)(a1 + 56));
          *(_QWORD *)(a1 + 56) = 0;
        }
      }
    }
  }
  v11 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 256));
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 344));
  if ( *(_DWORD *)(a1 + 248) )
  {
    v12 = (__int64 *)*v1;
    if ( *(__int64 **)(*v1 + 8) != v1 || (v13 = (__int64 **)v1[1], *v13 != v1) )
      __fastfail(3u);
    *v13 = v12;
    v12[1] = (__int64)v13;
    *(_DWORD *)(a1 + 248) = 0;
    v11 = 1;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 344));
  v17 = *(_DWORD *)(a1 + 8);
  *(_DWORD *)(a1 + 4) = 1;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 256));
  if ( v11 )
  {
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v18,
        (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
        (_DWORD)v1,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
        238);
    Dns64RequestDereferenceEx(v1);
  }
  Dns64TimerEntryStop(v1[93] + 16, v1 + 80);
  if ( !v17 )
  {
    v19 = *(_WORD **)(a1 + 56);
    if ( v19 )
    {
      if ( *(_DWORD *)(a1 + 68) == *(unsigned __int16 *)(a1 + 64) )
      {
        *v19 = __ROR2__(*v19, 8);
        v19[2] = __ROR2__(v19[2], 8);
        v19[3] = __ROR2__(v19[3], 8);
        v19[4] = __ROR2__(v19[4], 8);
        v19[5] = __ROR2__(v19[5], 8);
        if ( !(unsigned int)Dns_ParseMessage(v1 + 9, v19, *(unsigned __int16 *)(a1 + 68), 0, 1) )
        {
          *(_BYTE *)(a1 + 376) = 1;
          return Dns64ProcessReceivedRequest(v1);
        }
      }
    }
  }
  Dns64TcpTransportRefillPostedAcceptRequests(v2 + 272, 0);
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v21,
      (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
      (_DWORD)v1,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
      33);
  return Dns64RequestDereferenceEx(v1);
}

```

## disassembly

```asm
0x18006e680  push    rbx
0x18006e682  push    rbp
0x18006e683  push    rsi
0x18006e684  push    rdi
0x18006e685  push    r13
0x18006e687  push    r14
0x18006e689  push    r15
0x18006e68b  sub     rsp, 40h
0x18006e68f  cmp     qword ptr [rcx+38h], 0
0x18006e694  lea     rsi, [rcx+0E8h]
0x18006e69b  mov     r13, [rcx+3D0h]
0x18006e6a2  mov     rdi, rcx
0x18006e6a5  jnz     loc_18006E74D
0x18006e6ab  movzx   ecx, word ptr [rcx+40h]; hostshort
0x18006e6af  call    cs:__imp_htons
0x18006e6b6  nop     dword ptr [rax+rax+00h]
0x18006e6bb  cmp     dword ptr [rdi+44h], 2
0x18006e6bf  mov     [rdi+40h], ax
0x18006e6c3  jnz     loc_18006E74D
0x18006e6c9  cmp     ax, 0Ch
0x18006e6cd  jb      short loc_18006E74D
0x18006e6cf  movzx   ecx, ax; dwBytes
0x18006e6d2  call    MALLOC
0x18006e6d7  mov     [rdi+38h], rax
0x18006e6db  mov     rbp, rax
0x18006e6de  test    rax, rax
0x18006e6e1  jz      short loc_18006E74D
0x18006e6e3  movzx   ebx, word ptr [rdi+40h]
0x18006e6e7  xor     edx, edx; Val
0x18006e6e9  mov     r8d, ebx; Size
0x18006e6ec  mov     rcx, rax; void *
0x18006e6ef  call    memset_0
0x18006e6f4  mov     [rdi+0B0h], rbp
0x18006e6fb  lea     r14, [rdi+0A8h]
0x18006e702  mov     [r14], ebx
0x18006e705  lea     rbp, [rdi+0C0h]
0x18006e70c  mov     dword ptr [rdi+44h], 0
0x18006e713  lea     r15, [rdi+0B8h]
0x18006e71a  mov     dword ptr [r15], 8
0x18006e721  lea     rbx, [rdi+28h]
0x18006e725  xorps   xmm0, xmm0
0x18006e728  mov     rcx, rbx
0x18006e72b  movups  xmmword ptr [rbp+0], xmm0
0x18006e72f  movups  xmmword ptr [rbp+10h], xmm0
0x18006e733  call    RoReferenceEx
0x18006e738  test    al, al
0x18006e73a  jnz     short loc_18006E7BB
0x18006e73c  mov     rcx, [rdi+38h]
0x18006e740  call    FREE
0x18006e745  mov     qword ptr [rdi+38h], 0
0x18006e74d  lea     rbp, [rdi+100h]
0x18006e754  xor     ebx, ebx
0x18006e756  mov     rcx, rbp; lpCriticalSection
0x18006e759  lea     r15, [r13+110h]
0x18006e760  call    cs:__imp_EnterCriticalSection
0x18006e767  nop     dword ptr [rax+rax+00h]
0x18006e76c  lea     rcx, [r15+48h]; lpCriticalSection
0x18006e770  call    cs:__imp_EnterCriticalSection
0x18006e777  nop     dword ptr [rax+rax+00h]
0x18006e77c  cmp     [rdi+0F8h], ebx
0x18006e782  jz      loc_18006E8E2
0x18006e788  mov     rax, [rsi]
0x18006e78b  cmp     [rax+8], rsi
0x18006e78f  jnz     loc_18006E8DB
0x18006e795  mov     rcx, [rsi+8]
0x18006e799  cmp     [rcx], rsi
0x18006e79c  jnz     loc_18006E8DB
0x18006e7a2  mov     [rcx], rax
0x18006e7a5  lea     r13d, [rbx+1]
0x18006e7a9  mov     [rax+8], rcx
0x18006e7ad  mov     [rdi+0F8h], ebx
0x18006e7b3  mov     ebx, r13d
0x18006e7b6  jmp     loc_18006E8E8
0x18006e7bb  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e7c2  jz      short loc_18006E7E2
0x18006e7c4  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006e7cb  mov     dword ptr [rsp+78h+lpFlags], 3B5h
0x18006e7d3  mov     r8, rsi
0x18006e7d6  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006e7dd  call    McTemplateU0psq_EventWriteTransfer
0x18006e7e2  lock inc dword ptr [rsi+2E0h]
0x18006e7e9  mov     rcx, [rdi+20h]; pio
0x18006e7ed  call    cs:__imp_StartThreadpoolIo
0x18006e7f4  nop     dword ptr [rax+rax+00h]
0x18006e7f9  mov     rcx, [rdi+18h]; s
0x18006e7fd  xor     r9d, r9d; lpNumberOfBytesRecvd
0x18006e800  mov     [rsp+78h+lpCompletionRoutine], 0; lpCompletionRoutine
0x18006e809  mov     rdx, r14; lpBuffers
0x18006e80c  mov     [rsp+78h+lpOverlapped], rbp; lpOverlapped
0x18006e811  mov     [rsp+78h+lpFlags], r15; lpFlags
0x18006e816  lea     r8d, [r9+1]; dwBufferCount
0x18006e81a  call    cs:__imp_WSARecv
0x18006e821  nop     dword ptr [rax+rax+00h]
0x18006e826  test    eax, eax
0x18006e828  jz      short loc_18006E8A3
0x18006e82a  call    cs:__imp_WSAGetLastError
0x18006e831  nop     dword ptr [rax+rax+00h]
0x18006e836  test    eax, eax
0x18006e838  jz      short loc_18006E8A3
0x18006e83a  cmp     eax, 3E5h
0x18006e83f  jz      short loc_18006E8A3
0x18006e841  mov     rcx, [rdi+20h]; pio
0x18006e845  call    cs:__imp_CancelThreadpoolIo
0x18006e84c  nop     dword ptr [rax+rax+00h]
0x18006e851  mov     eax, 0FFFFFFFEh
0x18006e856  lock xadd [rbx], eax
0x18006e85a  cmp     eax, 3
0x18006e85d  jnz     short loc_18006E86F
0x18006e85f  mov     rcx, [rdi+30h]; hEvent
0x18006e863  call    cs:__imp_SetEvent
0x18006e86a  nop     dword ptr [rax+rax+00h]
0x18006e86f  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e876  jz      short loc_18006E896
0x18006e878  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006e87f  mov     dword ptr [rsp+78h+lpFlags], 3CDh
0x18006e887  mov     r8, rsi
0x18006e88a  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006e891  call    McTemplateU0psq_EventWriteTransfer
0x18006e896  mov     rcx, rsi
0x18006e899  call    Dns64RequestDereferenceEx
0x18006e89e  jmp     loc_18006E74D
0x18006e8a3  mov     eax, 0FFFFFFFEh
0x18006e8a8  lock xadd [rbx], eax
0x18006e8ac  cmp     eax, 3
0x18006e8af  jnz     short loc_18006E8C1
0x18006e8b1  mov     rcx, [rdi+30h]; hEvent
0x18006e8b5  call    cs:__imp_SetEvent
0x18006e8bc  nop     dword ptr [rax+rax+00h]
0x18006e8c1  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e8c8  jz      loc_18006EA10
0x18006e8ce  mov     dword ptr [rsp+78h+lpFlags], 3D5h
0x18006e8d6  jmp     loc_18006E9FA
0x18006e8db  mov     ecx, 3
0x18006e8e0  int     29h; Win8: RtlFailFast(ecx)
0x18006e8e2  mov     r13d, 1
0x18006e8e8  lea     rcx, [r15+48h]; lpCriticalSection
0x18006e8ec  call    cs:__imp_LeaveCriticalSection
0x18006e8f3  nop     dword ptr [rax+rax+00h]
0x18006e8f8  mov     r14d, [rdi+8]
0x18006e8fc  mov     rcx, rbp; lpCriticalSection
0x18006e8ff  mov     [rdi+4], r13d
0x18006e903  call    cs:__imp_LeaveCriticalSection
0x18006e90a  nop     dword ptr [rax+rax+00h]
0x18006e90f  test    ebx, ebx
0x18006e911  jz      short loc_18006E942
0x18006e913  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006e91a  jz      short loc_18006E93A
0x18006e91c  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006e923  mov     dword ptr [rsp+78h+lpFlags], 3EEh
0x18006e92b  mov     r8, rsi
0x18006e92e  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006e935  call    McTemplateU0psq_EventWriteTransfer
0x18006e93a  mov     rcx, rsi
0x18006e93d  call    Dns64RequestDereferenceEx
0x18006e942  mov     rcx, [rsi+2E8h]
0x18006e949  lea     rdx, [rsi+280h]
0x18006e950  add     rcx, 10h
0x18006e954  call    Dns64TimerEntryStop
0x18006e959  test    r14d, r14d
0x18006e95c  jnz     short loc_18006E9DC
0x18006e95e  mov     rdx, [rdi+38h]
0x18006e962  test    rdx, rdx
0x18006e965  jz      short loc_18006E9DC
0x18006e967  movzx   eax, word ptr [rdi+40h]
0x18006e96b  cmp     [rdi+44h], eax
0x18006e96e  jnz     short loc_18006E9DC
0x18006e970  movzx   eax, word ptr [rdx]
0x18006e973  lea     rcx, [rsi+48h]
0x18006e977  ror     ax, 8
0x18006e97b  xor     r9d, r9d
0x18006e97e  mov     [rdx], ax
0x18006e981  movzx   eax, word ptr [rdx+4]
0x18006e985  ror     ax, 8
0x18006e989  mov     [rdx+4], ax
0x18006e98d  movzx   eax, word ptr [rdx+6]
0x18006e991  ror     ax, 8
0x18006e995  mov     [rdx+6], ax
0x18006e999  movzx   eax, word ptr [rdx+8]
0x18006e99d  ror     ax, 8
0x18006e9a1  mov     [rdx+8], ax
0x18006e9a5  movzx   eax, word ptr [rdx+0Ah]
0x18006e9a9  ror     ax, 8
0x18006e9ad  mov     [rdx+0Ah], ax
0x18006e9b1  movzx   r8d, word ptr [rdi+44h]
0x18006e9b6  mov     dword ptr [rsp+78h+lpFlags], r13d
0x18006e9bb  call    cs:__imp_Dns_ParseMessage
0x18006e9c2  nop     dword ptr [rax+rax+00h]
0x18006e9c7  test    eax, eax
0x18006e9c9  jnz     short loc_18006E9DC
0x18006e9cb  mov     rcx, rsi
0x18006e9ce  mov     [rdi+178h], r13b
0x18006e9d5  call    Dns64ProcessReceivedRequest
0x18006e9da  jmp     short loc_18006EA18
0x18006e9dc  mov     r8d, r13d
0x18006e9df  xor     edx, edx
0x18006e9e1  mov     rcx, r15
0x18006e9e4  call    Dns64TcpTransportRefillPostedAcceptRequests
0x18006e9e9  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006e9f0  jz      short loc_18006EA10
0x18006e9f2  mov     dword ptr [rsp+78h+lpFlags], 421h
0x18006e9fa  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006ea01  mov     r8, rsi
0x18006ea04  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006ea0b  call    McTemplateU0psq_EventWriteTransfer
0x18006ea10  mov     rcx, rsi
0x18006ea13  call    Dns64RequestDereferenceEx
0x18006ea18  add     rsp, 40h
0x18006ea1c  pop     r15
0x18006ea1e  pop     r14
0x18006ea20  pop     r13
0x18006ea22  pop     rdi
0x18006ea23  pop     rsi
0x18006ea24  pop     rbp
0x18006ea25  pop     rbx
0x18006ea26  retn
```
