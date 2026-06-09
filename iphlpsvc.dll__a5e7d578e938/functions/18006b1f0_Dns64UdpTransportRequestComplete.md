# Dns64UdpTransportRequestComplete

- ea: `0x18006b1f0`
- end: `0x18006b61f`
- name: `Dns64UdpTransportRequestComplete`
- size: `1071`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006c620`

## callees

- `0x1800159d4`
- `0x180045d64`
- `0x1800616b4`
- `0x18006ae10`
- `0x18006b1f0`
- `0x18006b628`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b4c4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b518`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b4c4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b518`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b221`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b556`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b56f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b221`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b556`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b56f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b23f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b297`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b5b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b5c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b23f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b297`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b5b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b5c1`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006b4a6`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006b4a6`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006b449`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006b449`
- `WS2_32!WSASendMsg` at `0x18006b47b`
- `WS2_32!WSASendMsg` at `0x18006b47b`
- `WS2_32!__imp_WSAGetLastError` at `0x18006b48b`
- `WS2_32!__imp_WSAGetLastError` at `0x18006b48b`
- `DNSAPI!Dns_BuildPacket` at `0x18006b2df`
- `DNSAPI!Dns_BuildPacket` at `0x18006b37a`
- `DNSAPI!Dns_BuildPacket` at `0x18006b2df`
- `DNSAPI!Dns_BuildPacket` at `0x18006b37a`
- `DNSAPI!Dns_FreeMsgBuf` at `0x18006b332`
- `DNSAPI!Dns_FreeMsgBuf` at `0x18006b332`

## string_xrefs

- `0x18006b269`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`
- `0x18006b41f`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`
- `0x18006b4d9`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`
- `0x18006b52d`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`
- `0x18006b5d6`: `onecoreuap\net\netio\iphlpsvc\service\dns64udp.c`

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
0x18006b1f0  push    rbx
0x18006b1f2  push    rbp
0x18006b1f3  push    rsi
0x18006b1f4  push    rdi
0x18006b1f5  push    r12
0x18006b1f7  push    r14
0x18006b1f9  push    r15
0x18006b1fb  sub     rsp, 40h
0x18006b1ff  mov     rbp, [rcx+7E0h]
0x18006b206  lea     r14, [rcx+510h]
0x18006b20d  mov     rsi, rcx
0x18006b210  lea     rdi, [rcx+4F8h]
0x18006b217  mov     rcx, r14; lpCriticalSection
0x18006b21a  add     rbp, 98h
0x18006b221  call    cs:__imp_EnterCriticalSection
0x18006b228  nop     dword ptr [rax+rax+00h]
0x18006b22d  cmp     byte ptr [rsi+5C0h], 0
0x18006b234  mov     r12d, 1
0x18006b23a  mov     rcx, r14; lpCriticalSection
0x18006b23d  jnz     short loc_18006B297
0x18006b23f  call    cs:__imp_LeaveCriticalSection
0x18006b246  nop     dword ptr [rax+rax+00h]
0x18006b24b  mov     r8d, r12d
0x18006b24e  xor     edx, edx
0x18006b250  mov     rcx, rbp
0x18006b253  call    Dns64UdpTransportRefillPostedRequests
0x18006b258  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r12b
0x18006b25f  jz      short loc_18006B27F
0x18006b261  mov     dword ptr [rsp+78h+lpOverlapped], 4D8h
0x18006b269  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006b270  mov     r8, rdi
0x18006b273  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006b27a  call    McTemplateU0psq_EventWriteTransfer
0x18006b27f  mov     rcx, rdi
0x18006b282  call    Dns64RequestDereferenceEx
0x18006b287  add     rsp, 40h
0x18006b28b  pop     r15
0x18006b28d  pop     r14
0x18006b28f  pop     r12
0x18006b291  pop     rdi
0x18006b292  pop     rsi
0x18006b293  pop     rbp
0x18006b294  pop     rbx
0x18006b295  retn
0x18006b297  call    cs:__imp_LeaveCriticalSection
0x18006b29e  nop     dword ptr [rax+rax+00h]
0x18006b2a3  mov     eax, [rsi+5BCh]
0x18006b2a9  lea     r15, [rsi+590h]
0x18006b2b0  movzx   r9d, word ptr [rsi+5A8h]
0x18006b2b8  mov     edx, r12d
0x18006b2bb  mov     r8, [rsi+5A0h]
0x18006b2c2  mov     rcx, r15
0x18006b2c5  mov     [rsp+78h+var_48], eax
0x18006b2c9  mov     eax, [rsi+5B8h]
0x18006b2cf  mov     dword ptr [rsp+78h+lpCompletionRoutine], eax
0x18006b2d3  mov     rax, [rsi+5B0h]
0x18006b2da  mov     [rsp+78h+lpOverlapped], rax
0x18006b2df  call    cs:__imp_Dns_BuildPacket
0x18006b2e6  nop     dword ptr [rax+rax+00h]
0x18006b2eb  mov     [rsi+4E8h], rax
0x18006b2f2  mov     rcx, rax
0x18006b2f5  test    rax, rax
0x18006b2f8  jz      loc_18006B24B
0x18006b2fe  mov     eax, [rax+258h]
0x18006b304  sub     eax, ecx
0x18006b306  add     eax, 0FFFFFD44h
0x18006b30b  cmp     eax, [rsi+4F0h]
0x18006b311  jbe     short loc_18006B392
0x18006b313  test    byte ptr [rsi+592h], 2
0x18006b31a  jnz     loc_18006B24B
0x18006b320  mov     rbx, [rsi+5B0h]
0x18006b327  mov     qword ptr [rsi+5B0h], 0
0x18006b332  call    cs:__imp_Dns_FreeMsgBuf
0x18006b339  nop     dword ptr [rax+rax+00h]
0x18006b33e  mov     eax, [rsi+5BCh]
0x18006b344  mov     edx, r12d
0x18006b347  or      byte ptr [rsi+592h], 2
0x18006b34e  mov     rcx, r15
0x18006b351  movzx   r9d, word ptr [rsi+5A8h]
0x18006b359  mov     r8, [rsi+5A0h]
0x18006b360  mov     [rsp+78h+var_48], eax
0x18006b364  mov     eax, [rsi+5B8h]
0x18006b36a  mov     dword ptr [rsp+78h+lpCompletionRoutine], eax
0x18006b36e  mov     rax, [rsi+5B0h]
0x18006b375  mov     [rsp+78h+lpOverlapped], rax
0x18006b37a  call    cs:__imp_Dns_BuildPacket
0x18006b381  nop     dword ptr [rax+rax+00h]
0x18006b386  mov     [rsi+5B0h], rbx
0x18006b38d  jmp     loc_18006B2EB
0x18006b392  mov     [rcx+2BAh], ax
0x18006b399  mov     rcx, rsi
0x18006b39c  call    Dns64UdpTransportRequestControlSendPrepare
0x18006b3a1  mov     rcx, [rsi+4E8h]
0x18006b3a8  lea     rbx, [rbp+18h]
0x18006b3ac  movzx   eax, word ptr [rcx+2BCh]
0x18006b3b3  ror     ax, 8
0x18006b3b7  mov     [rcx+2BCh], ax
0x18006b3be  movzx   eax, word ptr [rcx+2C0h]
0x18006b3c5  ror     ax, 8
0x18006b3c9  mov     [rcx+2C0h], ax
0x18006b3d0  movzx   eax, word ptr [rcx+2C2h]
0x18006b3d7  ror     ax, 8
0x18006b3db  mov     [rcx+2C2h], ax
0x18006b3e2  movzx   eax, word ptr [rcx+2C4h]
0x18006b3e9  ror     ax, 8
0x18006b3ed  mov     [rcx+2C4h], ax
0x18006b3f4  movzx   eax, word ptr [rcx+2C6h]
0x18006b3fb  ror     ax, 8
0x18006b3ff  mov     [rcx+2C6h], ax
0x18006b406  mov     rcx, rbx
0x18006b409  call    RoReferenceEx
0x18006b40e  test    al, al
0x18006b410  jz      loc_18006B24B
0x18006b416  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r12b
0x18006b41d  jz      short loc_18006B43D
0x18006b41f  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006b426  mov     dword ptr [rsp+78h+lpOverlapped], 498h
0x18006b42e  mov     r8, rdi
0x18006b431  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006b438  call    McTemplateU0psq_EventWriteTransfer
0x18006b43d  lock add [rdi+2E0h], r12d
0x18006b445  mov     rcx, [rbp+10h]; pio
0x18006b449  call    cs:__imp_StartThreadpoolIo
0x18006b450  nop     dword ptr [rax+rax+00h]
0x18006b455  mov     rcx, [rbp+8]; Handle
0x18006b459  lea     rax, [rsi+4C8h]
0x18006b460  lea     rdx, [rsi+490h]; lpMsg
0x18006b467  mov     [rsp+78h+lpCompletionRoutine], 0; lpCompletionRoutine
0x18006b470  xor     r9d, r9d; lpNumberOfBytesSent
0x18006b473  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x18006b478  xor     r8d, r8d; dwFlags
0x18006b47b  call    cs:__imp_WSASendMsg
0x18006b482  nop     dword ptr [rax+rax+00h]
0x18006b487  test    eax, eax
0x18006b489  jz      short loc_18006B504
0x18006b48b  call    cs:__imp_WSAGetLastError
0x18006b492  nop     dword ptr [rax+rax+00h]
0x18006b497  test    eax, eax
0x18006b499  jz      short loc_18006B504
0x18006b49b  cmp     eax, 3E5h
0x18006b4a0  jz      short loc_18006B504
0x18006b4a2  mov     rcx, [rbp+10h]; pio
0x18006b4a6  call    cs:__imp_CancelThreadpoolIo
0x18006b4ad  nop     dword ptr [rax+rax+00h]
0x18006b4b2  mov     eax, 0FFFFFFFEh
0x18006b4b7  lock xadd [rbx], eax
0x18006b4bb  cmp     eax, 3
0x18006b4be  jnz     short loc_18006B4D0
0x18006b4c0  mov     rcx, [rbp+20h]; hEvent
0x18006b4c4  call    cs:__imp_SetEvent
0x18006b4cb  nop     dword ptr [rax+rax+00h]
0x18006b4d0  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r12b
0x18006b4d7  jz      short loc_18006B4F7
0x18006b4d9  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006b4e0  mov     dword ptr [rsp+78h+lpOverlapped], 4AFh
0x18006b4e8  mov     r8, rdi
0x18006b4eb  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006b4f2  call    McTemplateU0psq_EventWriteTransfer
0x18006b4f7  mov     rcx, rdi
0x18006b4fa  call    Dns64RequestDereferenceEx
0x18006b4ff  jmp     loc_18006B24B
0x18006b504  xor     r15d, r15d
0x18006b507  lea     eax, [r15-2]
0x18006b50b  lock xadd [rbx], eax
0x18006b50f  cmp     eax, 3
0x18006b512  jnz     short loc_18006B524
0x18006b514  mov     rcx, [rbp+20h]; hEvent
0x18006b518  call    cs:__imp_SetEvent
0x18006b51f  nop     dword ptr [rax+rax+00h]
0x18006b524  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r12b
0x18006b52b  jz      short loc_18006B54B
0x18006b52d  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006b534  mov     dword ptr [rsp+78h+lpOverlapped], 4BAh
0x18006b53c  mov     r8, rdi
0x18006b53f  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006b546  call    McTemplateU0psq_EventWriteTransfer
0x18006b54b  lock add [rdi+2E0h], r12d
0x18006b553  mov     rcx, r14; lpCriticalSection
0x18006b556  call    cs:__imp_EnterCriticalSection
0x18006b55d  nop     dword ptr [rax+rax+00h]
0x18006b562  cmp     [rsi+4], r15d
0x18006b566  jnz     short loc_18006B5BE
0x18006b568  lea     rbx, [rbp+38h]
0x18006b56c  mov     rcx, rbx; lpCriticalSection
0x18006b56f  call    cs:__imp_EnterCriticalSection
0x18006b576  nop     dword ptr [rax+rax+00h]
0x18006b57b  cmp     [rbp+0], r15d
0x18006b57f  jz      short loc_18006B5AF
0x18006b581  add     rbp, 28h ; '('
0x18006b585  mov     [rsi+508h], r12d
0x18006b58c  mov     rax, [rbp+0]
0x18006b590  cmp     [rax+8], rbp
0x18006b594  jz      short loc_18006B59D
0x18006b596  mov     ecx, 3
0x18006b59b  int     29h; Win8: RtlFailFast(ecx)
0x18006b59d  mov     [rdi], rax
0x18006b5a0  mov     r15d, r12d
0x18006b5a3  mov     [rdi+8], rbp
0x18006b5a7  mov     [rax+8], rdi
0x18006b5ab  mov     [rbp+0], rdi
0x18006b5af  mov     rcx, rbx; lpCriticalSection
0x18006b5b2  call    cs:__imp_LeaveCriticalSection
0x18006b5b9  nop     dword ptr [rax+rax+00h]
0x18006b5be  mov     rcx, r14; lpCriticalSection
0x18006b5c1  call    cs:__imp_LeaveCriticalSection
0x18006b5c8  nop     dword ptr [rax+rax+00h]
0x18006b5cd  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r12b
0x18006b5d4  jz      short loc_18006B5F4
0x18006b5d6  lea     r9, aOnecoreuapNetN_31; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006b5dd  mov     dword ptr [rsp+78h+lpOverlapped], 4CBh
0x18006b5e5  mov     r8, rdi
0x18006b5e8  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006b5ef  call    McTemplateU0psq_EventWriteTransfer
0x18006b5f4  mov     rcx, rdi
0x18006b5f7  call    Dns64RequestDereferenceEx
0x18006b5fc  test    r15d, r15d
0x18006b5ff  jnz     loc_18006B287
0x18006b605  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r12b
0x18006b60c  jz      loc_18006B27F
0x18006b612  mov     dword ptr [rsp+78h+lpOverlapped], 4CEh
0x18006b61a  jmp     loc_18006B269
```
