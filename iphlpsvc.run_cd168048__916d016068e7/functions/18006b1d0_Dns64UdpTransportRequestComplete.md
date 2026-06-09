# Dns64UdpTransportRequestComplete

- ea: `0x18006b1d0`
- end: `0x18006b5ff`
- name: `Dns64UdpTransportRequestComplete`
- size: `1071`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006c600`

## callees

- `0x1800159c4`
- `0x180045da4`
- `0x180061694`
- `0x18006adf0`
- `0x18006b1d0`
- `0x18006b608`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b4a4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b4f8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b4a4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b4f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b201`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b536`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b54f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b201`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b536`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b54f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b21f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b277`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b592`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b5a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b21f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b277`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b592`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b5a1`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006b486`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006b486`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006b429`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006b429`
- `WS2_32!WSASendMsg` at `0x18006b45b`
- `WS2_32!WSASendMsg` at `0x18006b45b`
- `WS2_32!__imp_WSAGetLastError` at `0x18006b46b`
- `WS2_32!__imp_WSAGetLastError` at `0x18006b46b`
- `DNSAPI!Dns_BuildPacket` at `0x18006b2bf`
- `DNSAPI!Dns_BuildPacket` at `0x18006b35a`
- `DNSAPI!Dns_BuildPacket` at `0x18006b2bf`
- `DNSAPI!Dns_BuildPacket` at `0x18006b35a`
- `DNSAPI!Dns_FreeMsgBuf` at `0x18006b312`
- `DNSAPI!Dns_FreeMsgBuf` at `0x18006b312`

## string_xrefs

- `0x18006b249`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`
- `0x18006b3ff`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`
- `0x18006b4b9`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`
- `0x18006b50d`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`
- `0x18006b5b6`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`

## pseudocode

```c
__int64 __fastcall Dns64UdpTransportRequestComplete(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // r14
  __int64 v3; // rdi
  __int64 v4; // rbp
  int v5; // ecx
  __int64 result; // rax
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // eax
  __int64 v10; // rbx
  int v11; // eax
  _WORD *v12; // rcx
  volatile signed __int32 *v13; // rbx
  int v14; // ecx
  int v15; // ecx
  int Error; // eax
  int v17; // ecx
  int v18; // r15d
  struct _RTL_CRITICAL_SECTION *v19; // rbx
  __int64 v20; // rbp
  __int64 v21; // rax
  int v22; // ecx
  int v23; // ecx

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 1296);
  v3 = a1 + 1272;
  v4 = *(_QWORD *)(a1 + 2016) + 152LL;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1296));
  if ( *(_BYTE *)(a1 + 1472) )
  {
    LeaveCriticalSection(v1);
    v7 = Dns_BuildPacket(
           a1 + 1424,
           1,
           *(_QWORD *)(a1 + 1440),
           *(unsigned __int16 *)(a1 + 1448),
           *(_QWORD *)(a1 + 1456),
           *(_DWORD *)(a1 + 1464),
           *(_DWORD *)(a1 + 1468));
    while ( 1 )
    {
      *(_QWORD *)(a1 + 1256) = v7;
      v8 = v7;
      if ( !v7 )
        break;
      v9 = *(_DWORD *)(v7 + 600) - v7 - 700;
      if ( v9 <= *(_DWORD *)(a1 + 1264) )
      {
        *(_WORD *)(v8 + 698) = v9;
        Dns64UdpTransportRequestControlSendPrepare(a1);
        v12 = *(_WORD **)(a1 + 1256);
        v13 = (volatile signed __int32 *)(v4 + 24);
        v12[350] = __ROR2__(v12[350], 8);
        v12[352] = __ROR2__(v12[352], 8);
        v12[353] = __ROR2__(v12[353], 8);
        v12[354] = __ROR2__(v12[354], 8);
        v12[355] = __ROR2__(v12[355], 8);
        if ( !(unsigned __int8)RoReferenceEx(v4 + 24) )
          break;
        if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
          McTemplateU0psq_EventWriteTransfer(
            v14,
            (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE,
            v3,
            (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64udp.c",
            152);
        _InterlockedAdd((volatile signed __int32 *)(v3 + 736), 1u);
        StartThreadpoolIo(*(PTP_IO *)(v4 + 16));
        if ( WSASendMsg(*(_QWORD *)(v4 + 8), (LPWSAMSG)(a1 + 1168), 0, 0, (LPWSAOVERLAPPED)(a1 + 1224), 0) )
        {
          Error = WSAGetLastError();
          if ( Error )
          {
            if ( Error != 997 )
            {
              CancelThreadpoolIo(*(PTP_IO *)(v4 + 16));
              if ( _InterlockedExchangeAdd(v13, 0xFFFFFFFE) == 3 )
                SetEvent(*(HANDLE *)(v4 + 32));
              if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
                McTemplateU0psq_EventWriteTransfer(
                  v17,
                  (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
                  v3,
                  (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64udp.c",
                  175);
              Dns64RequestDereferenceEx(v3);
              break;
            }
          }
        }
        v18 = 0;
        if ( _InterlockedExchangeAdd(v13, 0xFFFFFFFE) == 3 )
          SetEvent(*(HANDLE *)(v4 + 32));
        if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
          McTemplateU0psq_EventWriteTransfer(
            v15,
            (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE,
            v3,
            (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64udp.c",
            186);
        _InterlockedAdd((volatile signed __int32 *)(v3 + 736), 1u);
        EnterCriticalSection(v1);
        if ( !*(_DWORD *)(a1 + 4) )
        {
          v19 = (struct _RTL_CRITICAL_SECTION *)(v4 + 56);
          EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 56));
          if ( *(_DWORD *)v4 )
          {
            v20 = v4 + 40;
            *(_DWORD *)(a1 + 1288) = 1;
            v21 = *(_QWORD *)v20;
            if ( *(_QWORD *)(*(_QWORD *)v20 + 8LL) != v20 )
              __fastfail(3u);
            *(_QWORD *)v3 = v21;
            v18 = 1;
            *(_QWORD *)(v3 + 8) = v20;
            *(_QWORD *)(v21 + 8) = v3;
            *(_QWORD *)v20 = v3;
          }
          LeaveCriticalSection(v19);
        }
        LeaveCriticalSection(v1);
        if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
          McTemplateU0psq_EventWriteTransfer(
            v22,
            (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
            v3,
            (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64udp.c",
            203);
        result = Dns64RequestDereferenceEx(v3);
        if ( !v18 )
        {
          if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
            McTemplateU0psq_EventWriteTransfer(
              v23,
              (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
              v3,
              (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64udp.c",
              206);
          return Dns64RequestDereferenceEx(v3);
        }
        return result;
      }
      if ( (*(_BYTE *)(a1 + 1426) & 2) != 0 )
        break;
      v10 = *(_QWORD *)(a1 + 1456);
      *(_QWORD *)(a1 + 1456) = 0;
      Dns_FreeMsgBuf(v8);
      v11 = *(_DWORD *)(a1 + 1468);
      *(_BYTE *)(a1 + 1426) |= 2u;
      v7 = Dns_BuildPacket(
             a1 + 1424,
             1,
             *(_QWORD *)(a1 + 1440),
             *(unsigned __int16 *)(a1 + 1448),
             *(_QWORD *)(a1 + 1456),
             *(_DWORD *)(a1 + 1464),
             v11);
      *(_QWORD *)(a1 + 1456) = v10;
    }
  }
  else
  {
    LeaveCriticalSection(v1);
  }
  Dns64UdpTransportRefillPostedRequests(v4, 0, 1);
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v5,
      (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
      v3,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64udp.c",
      216);
  return Dns64RequestDereferenceEx(v3);
}

```

## disassembly

```asm
0x18006b1d0  push    rbx
0x18006b1d2  push    rbp
0x18006b1d3  push    rsi
0x18006b1d4  push    rdi
0x18006b1d5  push    r12
0x18006b1d7  push    r14
0x18006b1d9  push    r15
0x18006b1db  sub     rsp, 40h
0x18006b1df  mov     rbp, [rcx+7E0h]
0x18006b1e6  lea     r14, [rcx+510h]
0x18006b1ed  mov     rsi, rcx
0x18006b1f0  lea     rdi, [rcx+4F8h]
0x18006b1f7  mov     rcx, r14; lpCriticalSection
0x18006b1fa  add     rbp, 98h
0x18006b201  call    cs:__imp_EnterCriticalSection
0x18006b208  nop     dword ptr [rax+rax+00h]
0x18006b20d  cmp     byte ptr [rsi+5C0h], 0
0x18006b214  mov     r12d, 1
0x18006b21a  mov     rcx, r14; lpCriticalSection
0x18006b21d  jnz     short loc_18006B277
0x18006b21f  call    cs:__imp_LeaveCriticalSection
0x18006b226  nop     dword ptr [rax+rax+00h]
0x18006b22b  mov     r8d, r12d
0x18006b22e  xor     edx, edx
0x18006b230  mov     rcx, rbp
0x18006b233  call    Dns64UdpTransportRefillPostedRequests
0x18006b238  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r12b
0x18006b23f  jz      short loc_18006B25F
0x18006b241  mov     dword ptr [rsp+78h+lpOverlapped], 4D8h
0x18006b249  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006b250  mov     r8, rdi
0x18006b253  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006b25a  call    McTemplateU0psq_EventWriteTransfer
0x18006b25f  mov     rcx, rdi
0x18006b262  call    Dns64RequestDereferenceEx
0x18006b267  add     rsp, 40h
0x18006b26b  pop     r15
0x18006b26d  pop     r14
0x18006b26f  pop     r12
0x18006b271  pop     rdi
0x18006b272  pop     rsi
0x18006b273  pop     rbp
0x18006b274  pop     rbx
0x18006b275  retn
0x18006b277  call    cs:__imp_LeaveCriticalSection
0x18006b27e  nop     dword ptr [rax+rax+00h]
0x18006b283  mov     eax, [rsi+5BCh]
0x18006b289  lea     r15, [rsi+590h]
0x18006b290  movzx   r9d, word ptr [rsi+5A8h]
0x18006b298  mov     edx, r12d
0x18006b29b  mov     r8, [rsi+5A0h]
0x18006b2a2  mov     rcx, r15
0x18006b2a5  mov     [rsp+78h+var_48], eax
0x18006b2a9  mov     eax, [rsi+5B8h]
0x18006b2af  mov     dword ptr [rsp+78h+lpCompletionRoutine], eax
0x18006b2b3  mov     rax, [rsi+5B0h]
0x18006b2ba  mov     [rsp+78h+lpOverlapped], rax
0x18006b2bf  call    cs:__imp_Dns_BuildPacket
0x18006b2c6  nop     dword ptr [rax+rax+00h]
0x18006b2cb  mov     [rsi+4E8h], rax
0x18006b2d2  mov     rcx, rax
0x18006b2d5  test    rax, rax
0x18006b2d8  jz      loc_18006B22B
0x18006b2de  mov     eax, [rax+258h]
0x18006b2e4  sub     eax, ecx
0x18006b2e6  add     eax, 0FFFFFD44h
0x18006b2eb  cmp     eax, [rsi+4F0h]
0x18006b2f1  jbe     short loc_18006B372
0x18006b2f3  test    byte ptr [rsi+592h], 2
0x18006b2fa  jnz     loc_18006B22B
0x18006b300  mov     rbx, [rsi+5B0h]
0x18006b307  mov     qword ptr [rsi+5B0h], 0
0x18006b312  call    cs:__imp_Dns_FreeMsgBuf
0x18006b319  nop     dword ptr [rax+rax+00h]
0x18006b31e  mov     eax, [rsi+5BCh]
0x18006b324  mov     edx, r12d
0x18006b327  or      byte ptr [rsi+592h], 2
0x18006b32e  mov     rcx, r15
0x18006b331  movzx   r9d, word ptr [rsi+5A8h]
0x18006b339  mov     r8, [rsi+5A0h]
0x18006b340  mov     [rsp+78h+var_48], eax
0x18006b344  mov     eax, [rsi+5B8h]
0x18006b34a  mov     dword ptr [rsp+78h+lpCompletionRoutine], eax
0x18006b34e  mov     rax, [rsi+5B0h]
0x18006b355  mov     [rsp+78h+lpOverlapped], rax
0x18006b35a  call    cs:__imp_Dns_BuildPacket
0x18006b361  nop     dword ptr [rax+rax+00h]
0x18006b366  mov     [rsi+5B0h], rbx
0x18006b36d  jmp     loc_18006B2CB
0x18006b372  mov     [rcx+2BAh], ax
0x18006b379  mov     rcx, rsi
0x18006b37c  call    Dns64UdpTransportRequestControlSendPrepare
0x18006b381  mov     rcx, [rsi+4E8h]
0x18006b388  lea     rbx, [rbp+18h]
0x18006b38c  movzx   eax, word ptr [rcx+2BCh]
0x18006b393  ror     ax, 8
0x18006b397  mov     [rcx+2BCh], ax
0x18006b39e  movzx   eax, word ptr [rcx+2C0h]
0x18006b3a5  ror     ax, 8
0x18006b3a9  mov     [rcx+2C0h], ax
0x18006b3b0  movzx   eax, word ptr [rcx+2C2h]
0x18006b3b7  ror     ax, 8
0x18006b3bb  mov     [rcx+2C2h], ax
0x18006b3c2  movzx   eax, word ptr [rcx+2C4h]
0x18006b3c9  ror     ax, 8
0x18006b3cd  mov     [rcx+2C4h], ax
0x18006b3d4  movzx   eax, word ptr [rcx+2C6h]
0x18006b3db  ror     ax, 8
0x18006b3df  mov     [rcx+2C6h], ax
0x18006b3e6  mov     rcx, rbx
0x18006b3e9  call    RoReferenceEx
0x18006b3ee  test    al, al
0x18006b3f0  jz      loc_18006B22B
0x18006b3f6  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r12b
0x18006b3fd  jz      short loc_18006B41D
0x18006b3ff  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006b406  mov     dword ptr [rsp+78h+lpOverlapped], 498h
0x18006b40e  mov     r8, rdi
0x18006b411  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006b418  call    McTemplateU0psq_EventWriteTransfer
0x18006b41d  lock add [rdi+2E0h], r12d
0x18006b425  mov     rcx, [rbp+10h]; pio
0x18006b429  call    cs:__imp_StartThreadpoolIo
0x18006b430  nop     dword ptr [rax+rax+00h]
0x18006b435  mov     rcx, [rbp+8]; Handle
0x18006b439  lea     rax, [rsi+4C8h]
0x18006b440  lea     rdx, [rsi+490h]; lpMsg
0x18006b447  mov     [rsp+78h+lpCompletionRoutine], 0; lpCompletionRoutine
0x18006b450  xor     r9d, r9d; lpNumberOfBytesSent
0x18006b453  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x18006b458  xor     r8d, r8d; dwFlags
0x18006b45b  call    cs:__imp_WSASendMsg
0x18006b462  nop     dword ptr [rax+rax+00h]
0x18006b467  test    eax, eax
0x18006b469  jz      short loc_18006B4E4
0x18006b46b  call    cs:__imp_WSAGetLastError
0x18006b472  nop     dword ptr [rax+rax+00h]
0x18006b477  test    eax, eax
0x18006b479  jz      short loc_18006B4E4
0x18006b47b  cmp     eax, 3E5h
0x18006b480  jz      short loc_18006B4E4
0x18006b482  mov     rcx, [rbp+10h]; pio
0x18006b486  call    cs:__imp_CancelThreadpoolIo
0x18006b48d  nop     dword ptr [rax+rax+00h]
0x18006b492  mov     eax, 0FFFFFFFEh
0x18006b497  lock xadd [rbx], eax
0x18006b49b  cmp     eax, 3
0x18006b49e  jnz     short loc_18006B4B0
0x18006b4a0  mov     rcx, [rbp+20h]; hEvent
0x18006b4a4  call    cs:__imp_SetEvent
0x18006b4ab  nop     dword ptr [rax+rax+00h]
0x18006b4b0  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r12b
0x18006b4b7  jz      short loc_18006B4D7
0x18006b4b9  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006b4c0  mov     dword ptr [rsp+78h+lpOverlapped], 4AFh
0x18006b4c8  mov     r8, rdi
0x18006b4cb  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006b4d2  call    McTemplateU0psq_EventWriteTransfer
0x18006b4d7  mov     rcx, rdi
0x18006b4da  call    Dns64RequestDereferenceEx
0x18006b4df  jmp     loc_18006B22B
0x18006b4e4  xor     r15d, r15d
0x18006b4e7  lea     eax, [r15-2]
0x18006b4eb  lock xadd [rbx], eax
0x18006b4ef  cmp     eax, 3
0x18006b4f2  jnz     short loc_18006B504
0x18006b4f4  mov     rcx, [rbp+20h]; hEvent
0x18006b4f8  call    cs:__imp_SetEvent
0x18006b4ff  nop     dword ptr [rax+rax+00h]
0x18006b504  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r12b
0x18006b50b  jz      short loc_18006B52B
0x18006b50d  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006b514  mov     dword ptr [rsp+78h+lpOverlapped], 4BAh
0x18006b51c  mov     r8, rdi
0x18006b51f  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006b526  call    McTemplateU0psq_EventWriteTransfer
0x18006b52b  lock add [rdi+2E0h], r12d
0x18006b533  mov     rcx, r14; lpCriticalSection
0x18006b536  call    cs:__imp_EnterCriticalSection
0x18006b53d  nop     dword ptr [rax+rax+00h]
0x18006b542  cmp     [rsi+4], r15d
0x18006b546  jnz     short loc_18006B59E
0x18006b548  lea     rbx, [rbp+38h]
0x18006b54c  mov     rcx, rbx; lpCriticalSection
0x18006b54f  call    cs:__imp_EnterCriticalSection
0x18006b556  nop     dword ptr [rax+rax+00h]
0x18006b55b  cmp     [rbp+0], r15d
0x18006b55f  jz      short loc_18006B58F
0x18006b561  add     rbp, 28h ; '('
0x18006b565  mov     [rsi+508h], r12d
0x18006b56c  mov     rax, [rbp+0]
0x18006b570  cmp     [rax+8], rbp
0x18006b574  jz      short loc_18006B57D
0x18006b576  mov     ecx, 3
0x18006b57b  int     29h; Win8: RtlFailFast(ecx)
0x18006b57d  mov     [rdi], rax
0x18006b580  mov     r15d, r12d
0x18006b583  mov     [rdi+8], rbp
0x18006b587  mov     [rax+8], rdi
0x18006b58b  mov     [rbp+0], rdi
0x18006b58f  mov     rcx, rbx; lpCriticalSection
0x18006b592  call    cs:__imp_LeaveCriticalSection
0x18006b599  nop     dword ptr [rax+rax+00h]
0x18006b59e  mov     rcx, r14; lpCriticalSection
0x18006b5a1  call    cs:__imp_LeaveCriticalSection
0x18006b5a8  nop     dword ptr [rax+rax+00h]
0x18006b5ad  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r12b
0x18006b5b4  jz      short loc_18006B5D4
0x18006b5b6  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006b5bd  mov     dword ptr [rsp+78h+lpOverlapped], 4CBh
0x18006b5c5  mov     r8, rdi
0x18006b5c8  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006b5cf  call    McTemplateU0psq_EventWriteTransfer
0x18006b5d4  mov     rcx, rdi
0x18006b5d7  call    Dns64RequestDereferenceEx
0x18006b5dc  test    r15d, r15d
0x18006b5df  jnz     loc_18006B267
0x18006b5e5  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r12b
0x18006b5ec  jz      loc_18006B25F
0x18006b5f2  mov     dword ptr [rsp+78h+lpOverlapped], 4CEh
0x18006b5fa  jmp     loc_18006B249
```
