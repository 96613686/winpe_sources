# Dns64TcpTransportAcceptComplete

- ea: `0x18006df20`
- end: `0x18006e367`
- name: `Dns64TcpTransportAcceptComplete`
- size: `1095`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800159d4`
- `0x180045d64`
- `0x180047fc0`
- `0x1800487f8`
- `0x1800616b4`
- `0x18006a890`
- `0x18006df20`
- `0x18006eb88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006e183`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006e23d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006e183`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006e23d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006df67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006df7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e281`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e29a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006df67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006df7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e281`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e29a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006dfc8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006dfdd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e2e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e2f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006dfc8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006dfdd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e2e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e2f8`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006e164`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006e164`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006e100`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006e100`
- `WS2_32!WSARecv` at `0x18006e12d`
- `WS2_32!WSARecv` at `0x18006e12d`
- `WS2_32!__imp_WSAGetLastError` at `0x18006e141`
- `WS2_32!__imp_WSAGetLastError` at `0x18006e141`

## string_xrefs

- `0x18006dff6`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006e069`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006e0d7`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006e198`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006e1f4`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006e252`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006e30d`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`

## pseudocode

```c
__int64 __fastcall Dns64TcpTransportAcceptComplete(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v4; // rdi
  __int64 v6; // rbp
  int v8; // esi
  __int64 *v9; // rbx
  __int64 *v10; // rax
  __int64 **v11; // rcx
  int v12; // ecx
  volatile signed __int32 *v13; // r14
  int v14; // ecx
  int v15; // ecx
  int Error; // eax
  int v17; // ecx
  int v18; // ecx
  __int64 result; // rax
  int v20; // esi
  int v21; // r12d
  int v22; // r15d
  bool v23; // zf
  __int64 **v24; // rax
  __int64 v25; // rdx
  int v26; // ecx
  int v27; // ecx

  v4 = a3 - 192;
  v6 = *(_QWORD *)(a3 - 192 + 976) + 272LL;
  v8 = 1;
  Dns64TcpTransportRefillPostedAcceptRequests(v6, 1);
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 256));
  EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 72));
  v9 = (__int64 *)(v4 + 232);
  if ( *(_DWORD *)(v4 + 248) )
  {
    v10 = (__int64 *)*v9;
    if ( *(__int64 **)(*v9 + 8) != v9 || (v11 = *(__int64 ***)(v4 + 240), *v11 != v9) )
LABEL_37:
      __fastfail(3u);
    *v11 = v10;
    v10[1] = (__int64)v11;
    *(_DWORD *)(v4 + 248) = 0;
  }
  else
  {
    v8 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 72));
  *(_DWORD *)v4 = 1;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 256));
  if ( v8 )
  {
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v12,
        (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
        v4 + 232,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
        163);
    Dns64RequestDereferenceEx(v4 + 232);
  }
  if ( a4 )
    goto LABEL_25;
  *(_WORD *)(v4 + 64) = 0;
  *(_QWORD *)(v4 + 176) = v4 + 64;
  *(_DWORD *)(v4 + 168) = 2;
  *(_DWORD *)(v4 + 68) = 0;
  *(_DWORD *)(v4 + 184) = 8;
  *(_OWORD *)a3 = 0;
  *(_OWORD *)(a3 + 16) = 0;
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      0,
      (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE,
      v4 + 232,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
      183);
  _InterlockedIncrement((volatile signed __int32 *)(v4 + 968));
  Dns64TimerEntryStart(
    *(_QWORD *)(v4 + 976) + 16,
    v4 + 872,
    60000,
    v4,
    (__int64)Dns64TcpTransportReceiveTimeoutCallback);
  v13 = (volatile signed __int32 *)(v4 + 40);
  if ( !(unsigned __int8)RoReferenceEx(v4 + 40) )
  {
LABEL_24:
    Dns64TimerEntryStop(*(_QWORD *)(v4 + 976) + 16LL, v4 + 872);
LABEL_25:
    Dns64TcpTransportRefillPostedAcceptRequests(v6, 0);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v18,
        (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
        v4 + 232,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
        20);
    return Dns64RequestDereferenceEx(v4 + 232);
  }
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v14,
      (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE,
      v4 + 232,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
      197);
  _InterlockedIncrement((volatile signed __int32 *)(v4 + 968));
  StartThreadpoolIo(*(PTP_IO *)(v4 + 32));
  if ( WSARecv(*(_QWORD *)(v4 + 24), (LPWSABUF)(v4 + 168), 1u, 0, (LPDWORD)(v4 + 184), (LPWSAOVERLAPPED)a3, 0) )
  {
    Error = WSAGetLastError();
    if ( Error )
    {
      if ( Error != 997 )
      {
        CancelThreadpoolIo(*(PTP_IO *)(v4 + 32));
        if ( _InterlockedExchangeAdd(v13, 0xFFFFFFFE) == 3 )
          SetEvent(*(HANDLE *)(v4 + 48));
        if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
          McTemplateU0psq_EventWriteTransfer(
            v17,
            (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
            v4 + 232,
            (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
            220);
        Dns64RequestDereferenceEx(v4 + 232);
        goto LABEL_24;
      }
    }
  }
  v20 = 0;
  v21 = 0;
  v22 = 0;
  if ( _InterlockedExchangeAdd(v13, 0xFFFFFFFE) == 3 )
    SetEvent(*(HANDLE *)(v4 + 48));
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v15,
      (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE,
      v4 + 232,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
      232);
  _InterlockedIncrement((volatile signed __int32 *)(v4 + 968));
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 256));
  if ( !*(_DWORD *)(v4 + 4) && !*(_DWORD *)(v4 + 8) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 72));
    v23 = *(_DWORD *)v6 == 0;
    if ( *(_DWORD *)v6 )
    {
      v24 = (__int64 **)(v6 + 56);
      v25 = *(_QWORD *)(v6 + 56);
      if ( *(_QWORD *)(v25 + 8) != v6 + 56 )
        goto LABEL_37;
      *(_QWORD *)(v4 + 240) = v24;
      *v9 = v25;
      *(_QWORD *)(v25 + 8) = v9;
      *v24 = v9;
      *(_DWORD *)(v4 + 248) = 1;
      v21 = 1;
      v23 = *(_DWORD *)v6 == 0;
    }
    LOBYTE(v20) = v23;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 72));
    v22 = *(_DWORD *)(v4 + 8);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 256));
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v26,
      (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
      v4 + 232,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
      251);
  result = Dns64RequestDereferenceEx(v4 + 232);
  if ( !v21 )
  {
    if ( v20 || v22 )
      Dns64TcpTransportRequestCloseReceiveSocket(v4);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v27,
        (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
        v4 + 232,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
        7);
    return Dns64RequestDereferenceEx(v4 + 232);
  }
  return result;
}

```

## disassembly

```asm
0x18006df20  push    rbx
0x18006df22  push    rbp
0x18006df23  push    rsi
0x18006df24  push    rdi
0x18006df25  push    r12
0x18006df27  push    r13
0x18006df29  push    r14
0x18006df2b  push    r15
0x18006df2d  sub     rsp, 48h
0x18006df31  lea     rdi, [r8-0C0h]
0x18006df38  mov     r15, r8
0x18006df3b  mov     rbp, [rdi+3D0h]
0x18006df42  xor     r8d, r8d
0x18006df45  add     rbp, 110h
0x18006df4c  mov     r12d, r9d
0x18006df4f  mov     rcx, rbp
0x18006df52  lea     esi, [r8+1]
0x18006df56  mov     edx, esi
0x18006df58  call    Dns64TcpTransportRefillPostedAcceptRequests
0x18006df5d  lea     r14, [rdi+100h]
0x18006df64  mov     rcx, r14; lpCriticalSection
0x18006df67  call    cs:__imp_EnterCriticalSection
0x18006df6e  nop     dword ptr [rax+rax+00h]
0x18006df73  lea     r13, [rbp+48h]
0x18006df77  mov     rcx, r13; lpCriticalSection
0x18006df7a  call    cs:__imp_EnterCriticalSection
0x18006df81  nop     dword ptr [rax+rax+00h]
0x18006df86  cmp     dword ptr [rdi+0F8h], 0
0x18006df8d  lea     rbx, [rdi+0E8h]
0x18006df94  jz      short loc_18006DFC3
0x18006df96  mov     rax, [rbx]
0x18006df99  cmp     [rax+8], rbx
0x18006df9d  jnz     loc_18006E2B8
0x18006dfa3  mov     rcx, [rbx+8]
0x18006dfa7  cmp     [rcx], rbx
0x18006dfaa  jnz     loc_18006E2B8
0x18006dfb0  mov     [rcx], rax
0x18006dfb3  mov     [rax+8], rcx
0x18006dfb7  mov     dword ptr [rdi+0F8h], 0
0x18006dfc1  jmp     short loc_18006DFC5
0x18006dfc3  xor     esi, esi
0x18006dfc5  mov     rcx, r13; lpCriticalSection
0x18006dfc8  call    cs:__imp_LeaveCriticalSection
0x18006dfcf  nop     dword ptr [rax+rax+00h]
0x18006dfd4  mov     rcx, r14; lpCriticalSection
0x18006dfd7  mov     dword ptr [rdi], 1
0x18006dfdd  call    cs:__imp_LeaveCriticalSection
0x18006dfe4  nop     dword ptr [rax+rax+00h]
0x18006dfe9  test    esi, esi
0x18006dfeb  jz      short loc_18006E01C
0x18006dfed  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006dff4  jz      short loc_18006E014
0x18006dff6  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006dffd  mov     dword ptr [rsp+88h+lpFlags], 2A3h
0x18006e005  mov     r8, rbx
0x18006e008  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006e00f  call    McTemplateU0psq_EventWriteTransfer
0x18006e014  mov     rcx, rbx
0x18006e017  call    Dns64RequestDereferenceEx
0x18006e01c  test    r12d, r12d
0x18006e01f  jnz     loc_18006E1D5
0x18006e025  xor     ecx, ecx
0x18006e027  lea     rax, [rdi+40h]
0x18006e02b  mov     [rax], cx
0x18006e02e  lea     rsi, [rdi+0A8h]
0x18006e035  mov     [rdi+0B0h], rax
0x18006e03c  lea     r12, [rdi+0B8h]
0x18006e043  mov     dword ptr [rsi], 2
0x18006e049  xorps   xmm0, xmm0
0x18006e04c  mov     [rdi+44h], ecx
0x18006e04f  mov     dword ptr [r12], 8
0x18006e057  movups  xmmword ptr [r15], xmm0
0x18006e05b  movups  xmmword ptr [r15+10h], xmm0
0x18006e060  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e067  jz      short loc_18006E087
0x18006e069  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006e070  mov     dword ptr [rsp+88h+lpFlags], 2B7h
0x18006e078  mov     r8, rbx
0x18006e07b  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006e082  call    McTemplateU0psq_EventWriteTransfer
0x18006e087  lock inc dword ptr [rbx+2E0h]
0x18006e08e  mov     rcx, [rbx+2E8h]
0x18006e095  lea     rdx, Dns64TcpTransportReceiveTimeoutCallback
0x18006e09c  mov     [rsp+88h+lpFlags], rdx
0x18006e0a1  add     rcx, 10h
0x18006e0a5  lea     rdx, [rbx+280h]
0x18006e0ac  mov     r9, rdi
0x18006e0af  mov     r8d, 0EA60h
0x18006e0b5  call    Dns64TimerEntryStart
0x18006e0ba  lea     r14, [rdi+28h]
0x18006e0be  mov     rcx, r14
0x18006e0c1  call    RoReferenceEx
0x18006e0c6  test    al, al
0x18006e0c8  jz      loc_18006E1BE
0x18006e0ce  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e0d5  jz      short loc_18006E0F5
0x18006e0d7  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006e0de  mov     dword ptr [rsp+88h+lpFlags], 2C5h
0x18006e0e6  mov     r8, rbx
0x18006e0e9  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006e0f0  call    McTemplateU0psq_EventWriteTransfer
0x18006e0f5  lock inc dword ptr [rbx+2E0h]
0x18006e0fc  mov     rcx, [rdi+20h]; pio
0x18006e100  call    cs:__imp_StartThreadpoolIo
0x18006e107  nop     dword ptr [rax+rax+00h]
0x18006e10c  mov     rcx, [rdi+18h]; s
0x18006e110  xor     r9d, r9d; lpNumberOfBytesRecvd
0x18006e113  mov     [rsp+88h+lpCompletionRoutine], 0; lpCompletionRoutine
0x18006e11c  mov     rdx, rsi; lpBuffers
0x18006e11f  mov     [rsp+88h+lpOverlapped], r15; lpOverlapped
0x18006e124  mov     [rsp+88h+lpFlags], r12; lpFlags
0x18006e129  lea     r8d, [r9+1]; dwBufferCount
0x18006e12d  call    cs:__imp_WSARecv
0x18006e134  nop     dword ptr [rax+rax+00h]
0x18006e139  test    eax, eax
0x18006e13b  jz      loc_18006E224
0x18006e141  call    cs:__imp_WSAGetLastError
0x18006e148  nop     dword ptr [rax+rax+00h]
0x18006e14d  test    eax, eax
0x18006e14f  jz      loc_18006E224
0x18006e155  cmp     eax, 3E5h
0x18006e15a  jz      loc_18006E224
0x18006e160  mov     rcx, [rdi+20h]; pio
0x18006e164  call    cs:__imp_CancelThreadpoolIo
0x18006e16b  nop     dword ptr [rax+rax+00h]
0x18006e170  mov     eax, 0FFFFFFFEh
0x18006e175  lock xadd [r14], eax
0x18006e17a  cmp     eax, 3
0x18006e17d  jnz     short loc_18006E18F
0x18006e17f  mov     rcx, [rdi+30h]; hEvent
0x18006e183  call    cs:__imp_SetEvent
0x18006e18a  nop     dword ptr [rax+rax+00h]
0x18006e18f  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e196  jz      short loc_18006E1B6
0x18006e198  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006e19f  mov     dword ptr [rsp+88h+lpFlags], 2DCh
0x18006e1a7  mov     r8, rbx
0x18006e1aa  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006e1b1  call    McTemplateU0psq_EventWriteTransfer
0x18006e1b6  mov     rcx, rbx
0x18006e1b9  call    Dns64RequestDereferenceEx
0x18006e1be  mov     rcx, [rbx+2E8h]
0x18006e1c5  lea     rdx, [rbx+280h]
0x18006e1cc  add     rcx, 10h
0x18006e1d0  call    Dns64TimerEntryStop
0x18006e1d5  xor     edx, edx
0x18006e1d7  mov     rcx, rbp
0x18006e1da  lea     r8d, [rdx+1]
0x18006e1de  call    Dns64TcpTransportRefillPostedAcceptRequests
0x18006e1e3  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e1ea  jz      short loc_18006E20A
0x18006e1ec  mov     dword ptr [rsp+88h+lpFlags], 314h
0x18006e1f4  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006e1fb  mov     r8, rbx
0x18006e1fe  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006e205  call    McTemplateU0psq_EventWriteTransfer
0x18006e20a  mov     rcx, rbx
0x18006e20d  call    Dns64RequestDereferenceEx
0x18006e212  add     rsp, 48h
0x18006e216  pop     r15
0x18006e218  pop     r14
0x18006e21a  pop     r13
0x18006e21c  pop     r12
0x18006e21e  pop     rdi
0x18006e21f  pop     rsi
0x18006e220  pop     rbp
0x18006e221  pop     rbx
0x18006e222  retn
0x18006e224  xor     esi, esi
0x18006e226  xor     r12d, r12d
0x18006e229  xor     r15d, r15d
0x18006e22c  lea     eax, [rsi-2]
0x18006e22f  lock xadd [r14], eax
0x18006e234  cmp     eax, 3
0x18006e237  jnz     short loc_18006E249
0x18006e239  mov     rcx, [rdi+30h]; hEvent
0x18006e23d  call    cs:__imp_SetEvent
0x18006e244  nop     dword ptr [rax+rax+00h]
0x18006e249  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e250  jz      short loc_18006E270
0x18006e252  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006e259  mov     dword ptr [rsp+88h+lpFlags], 2E8h
0x18006e261  mov     r8, rbx
0x18006e264  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006e26b  call    McTemplateU0psq_EventWriteTransfer
0x18006e270  lock inc dword ptr [rbx+2E0h]
0x18006e277  lea     r14, [rdi+100h]
0x18006e27e  mov     rcx, r14; lpCriticalSection
0x18006e281  call    cs:__imp_EnterCriticalSection
0x18006e288  nop     dword ptr [rax+rax+00h]
0x18006e28d  cmp     [rdi+4], esi
0x18006e290  jnz     short loc_18006E2F5
0x18006e292  cmp     [rdi+8], esi
0x18006e295  jnz     short loc_18006E2F5
0x18006e297  mov     rcx, r13; lpCriticalSection
0x18006e29a  call    cs:__imp_EnterCriticalSection
0x18006e2a1  nop     dword ptr [rax+rax+00h]
0x18006e2a6  cmp     [rbp+0], esi
0x18006e2a9  jz      short loc_18006E2DE
0x18006e2ab  lea     rax, [rbp+38h]
0x18006e2af  mov     rdx, [rax]
0x18006e2b2  cmp     [rdx+8], rax
0x18006e2b6  jz      short loc_18006E2BF
0x18006e2b8  mov     ecx, 3
0x18006e2bd  int     29h; Win8: RtlFailFast(ecx)
0x18006e2bf  mov     [rbx+8], rax
0x18006e2c3  mov     [rbx], rdx
0x18006e2c6  mov     [rdx+8], rbx
0x18006e2ca  mov     [rax], rbx
0x18006e2cd  mov     eax, 1
0x18006e2d2  mov     [rdi+0F8h], eax
0x18006e2d8  mov     r12d, eax
0x18006e2db  cmp     [rbp+0], esi
0x18006e2de  mov     rcx, r13; lpCriticalSection
0x18006e2e1  setz    sil
0x18006e2e5  call    cs:__imp_LeaveCriticalSection
0x18006e2ec  nop     dword ptr [rax+rax+00h]
0x18006e2f1  mov     r15d, [rdi+8]
0x18006e2f5  mov     rcx, r14; lpCriticalSection
0x18006e2f8  call    cs:__imp_LeaveCriticalSection
0x18006e2ff  nop     dword ptr [rax+rax+00h]
0x18006e304  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e30b  jz      short loc_18006E32B
0x18006e30d  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006e314  mov     dword ptr [rsp+88h+lpFlags], 2FBh
0x18006e31c  mov     r8, rbx
0x18006e31f  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006e326  call    McTemplateU0psq_EventWriteTransfer
0x18006e32b  mov     rcx, rbx
0x18006e32e  call    Dns64RequestDereferenceEx
0x18006e333  test    r12d, r12d
0x18006e336  jnz     loc_18006E212
0x18006e33c  test    esi, esi
0x18006e33e  jnz     short loc_18006E345
0x18006e340  test    r15d, r15d
0x18006e343  jz      short loc_18006E34D
0x18006e345  mov     rcx, rdi
0x18006e348  call    Dns64TcpTransportRequestCloseReceiveSocket
0x18006e34d  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e354  jz      loc_18006E20A
0x18006e35a  mov     dword ptr [rsp+88h+lpFlags], 307h
0x18006e362  jmp     loc_18006E1F4
```
