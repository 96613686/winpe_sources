# Dns64TcpTransportAcceptComplete

- ea: `0x18006df00`
- end: `0x18006e347`
- name: `Dns64TcpTransportAcceptComplete`
- size: `1095`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800159c4`
- `0x180045da4`
- `0x180048000`
- `0x180048838`
- `0x180061694`
- `0x18006a870`
- `0x18006df00`
- `0x18006eb68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006e163`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006e21d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006e163`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006e21d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006df47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006df5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e261`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e27a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006df47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006df5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e261`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e27a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006dfa8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006dfbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e2c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e2d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006dfa8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006dfbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e2c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e2d8`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006e144`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006e144`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006e0e0`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006e0e0`
- `WS2_32!WSARecv` at `0x18006e10d`
- `WS2_32!WSARecv` at `0x18006e10d`
- `WS2_32!__imp_WSAGetLastError` at `0x18006e121`
- `WS2_32!__imp_WSAGetLastError` at `0x18006e121`

## string_xrefs

- `0x18006dfd6`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006e049`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006e0b7`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006e178`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006e1d4`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006e232`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006e2ed`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`

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
0x18006df00  push    rbx
0x18006df02  push    rbp
0x18006df03  push    rsi
0x18006df04  push    rdi
0x18006df05  push    r12
0x18006df07  push    r13
0x18006df09  push    r14
0x18006df0b  push    r15
0x18006df0d  sub     rsp, 48h
0x18006df11  lea     rdi, [r8-0C0h]
0x18006df18  mov     r15, r8
0x18006df1b  mov     rbp, [rdi+3D0h]
0x18006df22  xor     r8d, r8d
0x18006df25  add     rbp, 110h
0x18006df2c  mov     r12d, r9d
0x18006df2f  mov     rcx, rbp
0x18006df32  lea     esi, [r8+1]
0x18006df36  mov     edx, esi
0x18006df38  call    Dns64TcpTransportRefillPostedAcceptRequests
0x18006df3d  lea     r14, [rdi+100h]
0x18006df44  mov     rcx, r14; lpCriticalSection
0x18006df47  call    cs:__imp_EnterCriticalSection
0x18006df4e  nop     dword ptr [rax+rax+00h]
0x18006df53  lea     r13, [rbp+48h]
0x18006df57  mov     rcx, r13; lpCriticalSection
0x18006df5a  call    cs:__imp_EnterCriticalSection
0x18006df61  nop     dword ptr [rax+rax+00h]
0x18006df66  cmp     dword ptr [rdi+0F8h], 0
0x18006df6d  lea     rbx, [rdi+0E8h]
0x18006df74  jz      short loc_18006DFA3
0x18006df76  mov     rax, [rbx]
0x18006df79  cmp     [rax+8], rbx
0x18006df7d  jnz     loc_18006E298
0x18006df83  mov     rcx, [rbx+8]
0x18006df87  cmp     [rcx], rbx
0x18006df8a  jnz     loc_18006E298
0x18006df90  mov     [rcx], rax
0x18006df93  mov     [rax+8], rcx
0x18006df97  mov     dword ptr [rdi+0F8h], 0
0x18006dfa1  jmp     short loc_18006DFA5
0x18006dfa3  xor     esi, esi
0x18006dfa5  mov     rcx, r13; lpCriticalSection
0x18006dfa8  call    cs:__imp_LeaveCriticalSection
0x18006dfaf  nop     dword ptr [rax+rax+00h]
0x18006dfb4  mov     rcx, r14; lpCriticalSection
0x18006dfb7  mov     dword ptr [rdi], 1
0x18006dfbd  call    cs:__imp_LeaveCriticalSection
0x18006dfc4  nop     dword ptr [rax+rax+00h]
0x18006dfc9  test    esi, esi
0x18006dfcb  jz      short loc_18006DFFC
0x18006dfcd  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006dfd4  jz      short loc_18006DFF4
0x18006dfd6  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006dfdd  mov     dword ptr [rsp+88h+lpFlags], 2A3h
0x18006dfe5  mov     r8, rbx
0x18006dfe8  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006dfef  call    McTemplateU0psq_EventWriteTransfer
0x18006dff4  mov     rcx, rbx
0x18006dff7  call    Dns64RequestDereferenceEx
0x18006dffc  test    r12d, r12d
0x18006dfff  jnz     loc_18006E1B5
0x18006e005  xor     ecx, ecx
0x18006e007  lea     rax, [rdi+40h]
0x18006e00b  mov     [rax], cx
0x18006e00e  lea     rsi, [rdi+0A8h]
0x18006e015  mov     [rdi+0B0h], rax
0x18006e01c  lea     r12, [rdi+0B8h]
0x18006e023  mov     dword ptr [rsi], 2
0x18006e029  xorps   xmm0, xmm0
0x18006e02c  mov     [rdi+44h], ecx
0x18006e02f  mov     dword ptr [r12], 8
0x18006e037  movups  xmmword ptr [r15], xmm0
0x18006e03b  movups  xmmword ptr [r15+10h], xmm0
0x18006e040  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e047  jz      short loc_18006E067
0x18006e049  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006e050  mov     dword ptr [rsp+88h+lpFlags], 2B7h
0x18006e058  mov     r8, rbx
0x18006e05b  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006e062  call    McTemplateU0psq_EventWriteTransfer
0x18006e067  lock inc dword ptr [rbx+2E0h]
0x18006e06e  mov     rcx, [rbx+2E8h]
0x18006e075  lea     rdx, Dns64TcpTransportReceiveTimeoutCallback
0x18006e07c  mov     [rsp+88h+lpFlags], rdx
0x18006e081  add     rcx, 10h
0x18006e085  lea     rdx, [rbx+280h]
0x18006e08c  mov     r9, rdi
0x18006e08f  mov     r8d, 0EA60h
0x18006e095  call    Dns64TimerEntryStart
0x18006e09a  lea     r14, [rdi+28h]
0x18006e09e  mov     rcx, r14
0x18006e0a1  call    RoReferenceEx
0x18006e0a6  test    al, al
0x18006e0a8  jz      loc_18006E19E
0x18006e0ae  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e0b5  jz      short loc_18006E0D5
0x18006e0b7  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006e0be  mov     dword ptr [rsp+88h+lpFlags], 2C5h
0x18006e0c6  mov     r8, rbx
0x18006e0c9  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006e0d0  call    McTemplateU0psq_EventWriteTransfer
0x18006e0d5  lock inc dword ptr [rbx+2E0h]
0x18006e0dc  mov     rcx, [rdi+20h]; pio
0x18006e0e0  call    cs:__imp_StartThreadpoolIo
0x18006e0e7  nop     dword ptr [rax+rax+00h]
0x18006e0ec  mov     rcx, [rdi+18h]; s
0x18006e0f0  xor     r9d, r9d; lpNumberOfBytesRecvd
0x18006e0f3  mov     [rsp+88h+lpCompletionRoutine], 0; lpCompletionRoutine
0x18006e0fc  mov     rdx, rsi; lpBuffers
0x18006e0ff  mov     [rsp+88h+lpOverlapped], r15; lpOverlapped
0x18006e104  mov     [rsp+88h+lpFlags], r12; lpFlags
0x18006e109  lea     r8d, [r9+1]; dwBufferCount
0x18006e10d  call    cs:__imp_WSARecv
0x18006e114  nop     dword ptr [rax+rax+00h]
0x18006e119  test    eax, eax
0x18006e11b  jz      loc_18006E204
0x18006e121  call    cs:__imp_WSAGetLastError
0x18006e128  nop     dword ptr [rax+rax+00h]
0x18006e12d  test    eax, eax
0x18006e12f  jz      loc_18006E204
0x18006e135  cmp     eax, 3E5h
0x18006e13a  jz      loc_18006E204
0x18006e140  mov     rcx, [rdi+20h]; pio
0x18006e144  call    cs:__imp_CancelThreadpoolIo
0x18006e14b  nop     dword ptr [rax+rax+00h]
0x18006e150  mov     eax, 0FFFFFFFEh
0x18006e155  lock xadd [r14], eax
0x18006e15a  cmp     eax, 3
0x18006e15d  jnz     short loc_18006E16F
0x18006e15f  mov     rcx, [rdi+30h]; hEvent
0x18006e163  call    cs:__imp_SetEvent
0x18006e16a  nop     dword ptr [rax+rax+00h]
0x18006e16f  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e176  jz      short loc_18006E196
0x18006e178  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006e17f  mov     dword ptr [rsp+88h+lpFlags], 2DCh
0x18006e187  mov     r8, rbx
0x18006e18a  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006e191  call    McTemplateU0psq_EventWriteTransfer
0x18006e196  mov     rcx, rbx
0x18006e199  call    Dns64RequestDereferenceEx
0x18006e19e  mov     rcx, [rbx+2E8h]
0x18006e1a5  lea     rdx, [rbx+280h]
0x18006e1ac  add     rcx, 10h
0x18006e1b0  call    Dns64TimerEntryStop
0x18006e1b5  xor     edx, edx
0x18006e1b7  mov     rcx, rbp
0x18006e1ba  lea     r8d, [rdx+1]
0x18006e1be  call    Dns64TcpTransportRefillPostedAcceptRequests
0x18006e1c3  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e1ca  jz      short loc_18006E1EA
0x18006e1cc  mov     dword ptr [rsp+88h+lpFlags], 314h
0x18006e1d4  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006e1db  mov     r8, rbx
0x18006e1de  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006e1e5  call    McTemplateU0psq_EventWriteTransfer
0x18006e1ea  mov     rcx, rbx
0x18006e1ed  call    Dns64RequestDereferenceEx
0x18006e1f2  add     rsp, 48h
0x18006e1f6  pop     r15
0x18006e1f8  pop     r14
0x18006e1fa  pop     r13
0x18006e1fc  pop     r12
0x18006e1fe  pop     rdi
0x18006e1ff  pop     rsi
0x18006e200  pop     rbp
0x18006e201  pop     rbx
0x18006e202  retn
0x18006e204  xor     esi, esi
0x18006e206  xor     r12d, r12d
0x18006e209  xor     r15d, r15d
0x18006e20c  lea     eax, [rsi-2]
0x18006e20f  lock xadd [r14], eax
0x18006e214  cmp     eax, 3
0x18006e217  jnz     short loc_18006E229
0x18006e219  mov     rcx, [rdi+30h]; hEvent
0x18006e21d  call    cs:__imp_SetEvent
0x18006e224  nop     dword ptr [rax+rax+00h]
0x18006e229  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e230  jz      short loc_18006E250
0x18006e232  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006e239  mov     dword ptr [rsp+88h+lpFlags], 2E8h
0x18006e241  mov     r8, rbx
0x18006e244  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006e24b  call    McTemplateU0psq_EventWriteTransfer
0x18006e250  lock inc dword ptr [rbx+2E0h]
0x18006e257  lea     r14, [rdi+100h]
0x18006e25e  mov     rcx, r14; lpCriticalSection
0x18006e261  call    cs:__imp_EnterCriticalSection
0x18006e268  nop     dword ptr [rax+rax+00h]
0x18006e26d  cmp     [rdi+4], esi
0x18006e270  jnz     short loc_18006E2D5
0x18006e272  cmp     [rdi+8], esi
0x18006e275  jnz     short loc_18006E2D5
0x18006e277  mov     rcx, r13; lpCriticalSection
0x18006e27a  call    cs:__imp_EnterCriticalSection
0x18006e281  nop     dword ptr [rax+rax+00h]
0x18006e286  cmp     [rbp+0], esi
0x18006e289  jz      short loc_18006E2BE
0x18006e28b  lea     rax, [rbp+38h]
0x18006e28f  mov     rdx, [rax]
0x18006e292  cmp     [rdx+8], rax
0x18006e296  jz      short loc_18006E29F
0x18006e298  mov     ecx, 3
0x18006e29d  int     29h; Win8: RtlFailFast(ecx)
0x18006e29f  mov     [rbx+8], rax
0x18006e2a3  mov     [rbx], rdx
0x18006e2a6  mov     [rdx+8], rbx
0x18006e2aa  mov     [rax], rbx
0x18006e2ad  mov     eax, 1
0x18006e2b2  mov     [rdi+0F8h], eax
0x18006e2b8  mov     r12d, eax
0x18006e2bb  cmp     [rbp+0], esi
0x18006e2be  mov     rcx, r13; lpCriticalSection
0x18006e2c1  setz    sil
0x18006e2c5  call    cs:__imp_LeaveCriticalSection
0x18006e2cc  nop     dword ptr [rax+rax+00h]
0x18006e2d1  mov     r15d, [rdi+8]
0x18006e2d5  mov     rcx, r14; lpCriticalSection
0x18006e2d8  call    cs:__imp_LeaveCriticalSection
0x18006e2df  nop     dword ptr [rax+rax+00h]
0x18006e2e4  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e2eb  jz      short loc_18006E30B
0x18006e2ed  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006e2f4  mov     dword ptr [rsp+88h+lpFlags], 2FBh
0x18006e2fc  mov     r8, rbx
0x18006e2ff  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006e306  call    McTemplateU0psq_EventWriteTransfer
0x18006e30b  mov     rcx, rbx
0x18006e30e  call    Dns64RequestDereferenceEx
0x18006e313  test    r12d, r12d
0x18006e316  jnz     loc_18006E1F2
0x18006e31c  test    esi, esi
0x18006e31e  jnz     short loc_18006E325
0x18006e320  test    r15d, r15d
0x18006e323  jz      short loc_18006E32D
0x18006e325  mov     rcx, rdi
0x18006e328  call    Dns64TcpTransportRequestCloseReceiveSocket
0x18006e32d  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 1
0x18006e334  jz      loc_18006E1EA
0x18006e33a  mov     dword ptr [rsp+88h+lpFlags], 307h
0x18006e342  jmp     loc_18006E1D4
```
