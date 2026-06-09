# Dns64TcpTransportReceiveComplete

- ea: `0x18006e6a0`
- end: `0x18006ea48`
- name: `Dns64TcpTransportReceiveComplete`
- size: `936`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006e420`

## callees

- `0x180004c64`
- `0x180012dcc`
- `0x1800159d4`
- `0x180045d64`
- `0x18004c188`
- `0x1800616b4`
- `0x18006a890`
- `0x18006bdcc`
- `0x18006e6a0`
- `0x18006eb88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006e883`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006e8d5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006e883`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006e8d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e780`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e790`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e780`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e790`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e90c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e923`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e90c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e923`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006e865`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006e865`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006e80d`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006e80d`
- `WS2_32!WSARecv` at `0x18006e83a`
- `WS2_32!WSARecv` at `0x18006e83a`
- `WS2_32!__imp_htons` at `0x18006e6cf`
- `WS2_32!__imp_htons` at `0x18006e6cf`
- `WS2_32!__imp_WSAGetLastError` at `0x18006e84a`
- `WS2_32!__imp_WSAGetLastError` at `0x18006e84a`
- `DNSAPI!Dns_ParseMessage` at `0x18006e9db`
- `DNSAPI!Dns_ParseMessage` at `0x18006e9db`

## string_xrefs

- `0x18006e7e4`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006e898`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006e93c`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006ea1a`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`

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
0x18006e6a0  push    rbx
0x18006e6a2  push    rbp
0x18006e6a3  push    rsi
0x18006e6a4  push    rdi
0x18006e6a5  push    r13
0x18006e6a7  push    r14
0x18006e6a9  push    r15
0x18006e6ab  sub     rsp, 40h
0x18006e6af  cmp     qword ptr [rcx+38h], 0
0x18006e6b4  lea     rsi, [rcx+0E8h]
0x18006e6bb  mov     r13, [rcx+3D0h]
0x18006e6c2  mov     rdi, rcx
0x18006e6c5  jnz     loc_18006E76D
0x18006e6cb  movzx   ecx, word ptr [rcx+40h]; hostshort
0x18006e6cf  call    cs:__imp_htons
0x18006e6d6  nop     dword ptr [rax+rax+00h]
0x18006e6db  cmp     dword ptr [rdi+44h], 2
0x18006e6df  mov     [rdi+40h], ax
0x18006e6e3  jnz     loc_18006E76D
0x18006e6e9  cmp     ax, 0Ch
0x18006e6ed  jb      short loc_18006E76D
0x18006e6ef  movzx   ecx, ax; dwBytes
0x18006e6f2  call    MALLOC
0x18006e6f7  mov     [rdi+38h], rax
0x18006e6fb  mov     rbp, rax
0x18006e6fe  test    rax, rax
0x18006e701  jz      short loc_18006E76D
0x18006e703  movzx   ebx, word ptr [rdi+40h]
0x18006e707  xor     edx, edx; Val
0x18006e709  mov     r8d, ebx; Size
0x18006e70c  mov     rcx, rax; void *
0x18006e70f  call    memset_0
0x18006e714  mov     [rdi+0B0h], rbp
0x18006e71b  lea     r14, [rdi+0A8h]
0x18006e722  mov     [r14], ebx
0x18006e725  lea     rbp, [rdi+0C0h]
0x18006e72c  mov     dword ptr [rdi+44h], 0
0x18006e733  lea     r15, [rdi+0B8h]
0x18006e73a  mov     dword ptr [r15], 8
0x18006e741  lea     rbx, [rdi+28h]
0x18006e745  xorps   xmm0, xmm0
0x18006e748  mov     rcx, rbx
0x18006e74b  movups  xmmword ptr [rbp+0], xmm0
0x18006e74f  movups  xmmword ptr [rbp+10h], xmm0
0x18006e753  call    RoReferenceEx
0x18006e758  test    al, al
0x18006e75a  jnz     short loc_18006E7DB
0x18006e75c  mov     rcx, [rdi+38h]
0x18006e760  call    FREE
0x18006e765  mov     qword ptr [rdi+38h], 0
0x18006e76d  lea     rbp, [rdi+100h]
0x18006e774  xor     ebx, ebx
0x18006e776  mov     rcx, rbp; lpCriticalSection
0x18006e779  lea     r15, [r13+110h]
0x18006e780  call    cs:__imp_EnterCriticalSection
0x18006e787  nop     dword ptr [rax+rax+00h]
0x18006e78c  lea     rcx, [r15+48h]; lpCriticalSection
0x18006e790  call    cs:__imp_EnterCriticalSection
0x18006e797  nop     dword ptr [rax+rax+00h]
0x18006e79c  cmp     [rdi+0F8h], ebx
0x18006e7a2  jz      loc_18006E902
0x18006e7a8  mov     rax, [rsi]
0x18006e7ab  cmp     [rax+8], rsi
0x18006e7af  jnz     loc_18006E8FB
0x18006e7b5  mov     rcx, [rsi+8]
0x18006e7b9  cmp     [rcx], rsi
0x18006e7bc  jnz     loc_18006E8FB
0x18006e7c2  mov     [rcx], rax
0x18006e7c5  lea     r13d, [rbx+1]
0x18006e7c9  mov     [rax+8], rcx
0x18006e7cd  mov     [rdi+0F8h], ebx
0x18006e7d3  mov     ebx, r13d
0x18006e7d6  jmp     loc_18006E908
0x18006e7db  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e7e2  jz      short loc_18006E802
0x18006e7e4  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006e7eb  mov     dword ptr [rsp+78h+lpFlags], 3B5h
0x18006e7f3  mov     r8, rsi
0x18006e7f6  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006e7fd  call    McTemplateU0psq_EventWriteTransfer
0x18006e802  lock inc dword ptr [rsi+2E0h]
0x18006e809  mov     rcx, [rdi+20h]; pio
0x18006e80d  call    cs:__imp_StartThreadpoolIo
0x18006e814  nop     dword ptr [rax+rax+00h]
0x18006e819  mov     rcx, [rdi+18h]; s
0x18006e81d  xor     r9d, r9d; lpNumberOfBytesRecvd
0x18006e820  mov     [rsp+78h+lpCompletionRoutine], 0; lpCompletionRoutine
0x18006e829  mov     rdx, r14; lpBuffers
0x18006e82c  mov     [rsp+78h+lpOverlapped], rbp; lpOverlapped
0x18006e831  mov     [rsp+78h+lpFlags], r15; lpFlags
0x18006e836  lea     r8d, [r9+1]; dwBufferCount
0x18006e83a  call    cs:__imp_WSARecv
0x18006e841  nop     dword ptr [rax+rax+00h]
0x18006e846  test    eax, eax
0x18006e848  jz      short loc_18006E8C3
0x18006e84a  call    cs:__imp_WSAGetLastError
0x18006e851  nop     dword ptr [rax+rax+00h]
0x18006e856  test    eax, eax
0x18006e858  jz      short loc_18006E8C3
0x18006e85a  cmp     eax, 3E5h
0x18006e85f  jz      short loc_18006E8C3
0x18006e861  mov     rcx, [rdi+20h]; pio
0x18006e865  call    cs:__imp_CancelThreadpoolIo
0x18006e86c  nop     dword ptr [rax+rax+00h]
0x18006e871  mov     eax, 0FFFFFFFEh
0x18006e876  lock xadd [rbx], eax
0x18006e87a  cmp     eax, 3
0x18006e87d  jnz     short loc_18006E88F
0x18006e87f  mov     rcx, [rdi+30h]; hEvent
0x18006e883  call    cs:__imp_SetEvent
0x18006e88a  nop     dword ptr [rax+rax+00h]
0x18006e88f  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e896  jz      short loc_18006E8B6
0x18006e898  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006e89f  mov     dword ptr [rsp+78h+lpFlags], 3CDh
0x18006e8a7  mov     r8, rsi
0x18006e8aa  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006e8b1  call    McTemplateU0psq_EventWriteTransfer
0x18006e8b6  mov     rcx, rsi
0x18006e8b9  call    Dns64RequestDereferenceEx
0x18006e8be  jmp     loc_18006E76D
0x18006e8c3  mov     eax, 0FFFFFFFEh
0x18006e8c8  lock xadd [rbx], eax
0x18006e8cc  cmp     eax, 3
0x18006e8cf  jnz     short loc_18006E8E1
0x18006e8d1  mov     rcx, [rdi+30h]; hEvent
0x18006e8d5  call    cs:__imp_SetEvent
0x18006e8dc  nop     dword ptr [rax+rax+00h]
0x18006e8e1  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e8e8  jz      loc_18006EA30
0x18006e8ee  mov     dword ptr [rsp+78h+lpFlags], 3D5h
0x18006e8f6  jmp     loc_18006EA1A
0x18006e8fb  mov     ecx, 3
0x18006e900  int     29h; Win8: RtlFailFast(ecx)
0x18006e902  mov     r13d, 1
0x18006e908  lea     rcx, [r15+48h]; lpCriticalSection
0x18006e90c  call    cs:__imp_LeaveCriticalSection
0x18006e913  nop     dword ptr [rax+rax+00h]
0x18006e918  mov     r14d, [rdi+8]
0x18006e91c  mov     rcx, rbp; lpCriticalSection
0x18006e91f  mov     [rdi+4], r13d
0x18006e923  call    cs:__imp_LeaveCriticalSection
0x18006e92a  nop     dword ptr [rax+rax+00h]
0x18006e92f  test    ebx, ebx
0x18006e931  jz      short loc_18006E962
0x18006e933  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006e93a  jz      short loc_18006E95A
0x18006e93c  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006e943  mov     dword ptr [rsp+78h+lpFlags], 3EEh
0x18006e94b  mov     r8, rsi
0x18006e94e  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006e955  call    McTemplateU0psq_EventWriteTransfer
0x18006e95a  mov     rcx, rsi
0x18006e95d  call    Dns64RequestDereferenceEx
0x18006e962  mov     rcx, [rsi+2E8h]
0x18006e969  lea     rdx, [rsi+280h]
0x18006e970  add     rcx, 10h
0x18006e974  call    Dns64TimerEntryStop
0x18006e979  test    r14d, r14d
0x18006e97c  jnz     short loc_18006E9FC
0x18006e97e  mov     rdx, [rdi+38h]
0x18006e982  test    rdx, rdx
0x18006e985  jz      short loc_18006E9FC
0x18006e987  movzx   eax, word ptr [rdi+40h]
0x18006e98b  cmp     [rdi+44h], eax
0x18006e98e  jnz     short loc_18006E9FC
0x18006e990  movzx   eax, word ptr [rdx]
0x18006e993  lea     rcx, [rsi+48h]
0x18006e997  ror     ax, 8
0x18006e99b  xor     r9d, r9d
0x18006e99e  mov     [rdx], ax
0x18006e9a1  movzx   eax, word ptr [rdx+4]
0x18006e9a5  ror     ax, 8
0x18006e9a9  mov     [rdx+4], ax
0x18006e9ad  movzx   eax, word ptr [rdx+6]
0x18006e9b1  ror     ax, 8
0x18006e9b5  mov     [rdx+6], ax
0x18006e9b9  movzx   eax, word ptr [rdx+8]
0x18006e9bd  ror     ax, 8
0x18006e9c1  mov     [rdx+8], ax
0x18006e9c5  movzx   eax, word ptr [rdx+0Ah]
0x18006e9c9  ror     ax, 8
0x18006e9cd  mov     [rdx+0Ah], ax
0x18006e9d1  movzx   r8d, word ptr [rdi+44h]
0x18006e9d6  mov     dword ptr [rsp+78h+lpFlags], r13d
0x18006e9db  call    cs:__imp_Dns_ParseMessage
0x18006e9e2  nop     dword ptr [rax+rax+00h]
0x18006e9e7  test    eax, eax
0x18006e9e9  jnz     short loc_18006E9FC
0x18006e9eb  mov     rcx, rsi
0x18006e9ee  mov     [rdi+178h], r13b
0x18006e9f5  call    Dns64ProcessReceivedRequest
0x18006e9fa  jmp     short loc_18006EA38
0x18006e9fc  mov     r8d, r13d
0x18006e9ff  xor     edx, edx
0x18006ea01  mov     rcx, r15
0x18006ea04  call    Dns64TcpTransportRefillPostedAcceptRequests
0x18006ea09  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006ea10  jz      short loc_18006EA30
0x18006ea12  mov     dword ptr [rsp+78h+lpFlags], 421h
0x18006ea1a  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006ea21  mov     r8, rsi
0x18006ea24  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006ea2b  call    McTemplateU0psq_EventWriteTransfer
0x18006ea30  mov     rcx, rsi
0x18006ea33  call    Dns64RequestDereferenceEx
0x18006ea38  add     rsp, 40h
0x18006ea3c  pop     r15
0x18006ea3e  pop     r14
0x18006ea40  pop     r13
0x18006ea42  pop     rdi
0x18006ea43  pop     rsi
0x18006ea44  pop     rbp
0x18006ea45  pop     rbx
0x18006ea46  retn
```
