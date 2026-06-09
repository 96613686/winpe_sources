# TeredoRioCreateSecondarySockets

- ea: `0x180056c18`
- end: `0x18005718a`
- name: `TeredoRioCreateSecondarySockets`
- size: `1394`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800589d8`

## callees

- `0x180008200`
- `0x180009000`
- `0x18000d7b0`
- `0x1800159c4`
- `0x1800190e0`
- `0x18001caa8`
- `0x180024240`
- `0x180041494`
- `0x18004b630`
- `0x180055f2c`
- `0x180056c18`
- `0x180057190`
- `0x180057640`
- `0x180057b24`
- `0x180058824`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056d04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056d04`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056cc4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056cc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056cdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056efa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056cdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056efa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056f64`
- `WS2_32!WSASocketW` at `0x180056dbb`
- `WS2_32!WSASocketW` at `0x180056dbb`
- `WS2_32!WSAIoctl` at `0x180056e01`
- `WS2_32!WSAIoctl` at `0x180056e01`
- `WS2_32!__imp_bind` at `0x180056e50`
- `WS2_32!__imp_bind` at `0x180056e50`
- `WS2_32!__imp_htonl` at `0x180056c9b`
- `WS2_32!__imp_htonl` at `0x180056c9b`
- `WS2_32!__imp_setsockopt` at `0x180056e8c`
- `WS2_32!__imp_setsockopt` at `0x180056ee9`
- `WS2_32!__imp_setsockopt` at `0x180056e8c`
- `WS2_32!__imp_setsockopt` at `0x180056ee9`
- `WS2_32!__imp_WSAGetLastError` at `0x180056e11`
- `WS2_32!__imp_WSAGetLastError` at `0x180056f94`
- `WS2_32!__imp_WSAGetLastError` at `0x180056e11`
- `WS2_32!__imp_WSAGetLastError` at `0x180056f94`

## string_xrefs

- `0x1800570cd`: `Created Secondary Socket.`
- `0x180056c42`: `TeredoRioCreateSecondarySockets`
- `0x180057156`: `TeredoRioCreateSecondarySockets`
- `0x180056f70`: `Failed to create Results. Error (%d)`
- `0x180057129`: `Failed TeredoRioCreateWorkerThreads. Error (%d)`

## pseudocode

```c
__int64 __fastcall TeredoRioCreateSecondarySockets(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // rbx
  struct sockaddr *v4; // rax
  int v5; // esi
  int v6; // r15d
  int v7; // r12d
  HANDLE EventW; // rax
  DWORD v9; // eax
  LPVOID v10; // rax
  unsigned __int16 v11; // ax
  __int64 v12; // r13
  _QWORD *v13; // r12
  unsigned __int16 v14; // cx
  char v15; // si
  __int64 v16; // r15
  __int64 NumaMemory; // rax
  __int64 v18; // rsi
  SOCKET v19; // rax
  unsigned int Error; // eax
  DWORD LastError; // eax
  DWORD v22; // eax
  unsigned int WorkerThreads; // eax
  __int64 v24; // rax
  const wchar_t *v25; // rdx
  unsigned __int16 v26; // cx
  unsigned __int16 v27; // dx
  __int64 v28; // r13
  _QWORD *v29; // r12
  unsigned int v30; // esi
  unsigned int v31; // r15d
  _WORD vInBuffer[2]; // [rsp+50h] [rbp-19h] BYREF
  char optval[4]; // [rsp+54h] [rbp-15h] BYREF
  DWORD cbBytesReturned; // [rsp+58h] [rbp-11h] BYREF
  char v36[8]; // [rsp+60h] [rbp-9h] BYREF
  struct sockaddr name; // [rsp+68h] [rbp-1h] BYREF

  v1 = *(_QWORD *)a1;
  LODWORD(v2) = 0;
  *(_DWORD *)optval = 0;
  *(_QWORD *)v36 = 0;
  vInBuffer[0] = 0;
  name = 0;
  cbBytesReturned = 0;
  EventWriteEnterEx(0x100000, L"TeredoRioCreateSecondarySockets");
  v4 = *(struct sockaddr **)(v1 + 2680);
  v5 = *(_DWORD *)(v1 + 2900);
  v6 = *(_DWORD *)(v1 + 2896);
  v7 = *(_DWORD *)(v1 + 2892);
  if ( v4 )
  {
    name = *v4;
    *(_DWORD *)&name.sa_data[2] = htonl(0);
  }
  else
  {
    name = *(struct sockaddr *)(v1 + 2628);
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)(a1 + 152) = EventW;
  if ( EventW )
  {
    v10 = HeapAlloc(*(HANDLE *)(v1 + 2576), 8u, 8LL * *(unsigned int *)(v1 + 2884));
    *(_QWORD *)(a1 + 136) = v10;
    if ( !v10 )
    {
      LODWORD(v2) = 8;
      EventWriteError0(0x100000, L"HeapAlloc for Rio socket pointers failed: %u", 8);
LABEL_50:
      if ( (*(_BYTE *)(a1 + 144) & 1) != 0 )
        TeredoRioDestroySockets((__int64 *)a1);
      else
        TeredoRioStopDevice(a1);
      goto LABEL_53;
    }
    v11 = 0;
    v12 = (unsigned int)(v5 + v7 + v6);
    v13 = (_QWORD *)(v1 + 2904);
    v14 = 0;
    v15 = 1;
    while ( 1 )
    {
      vInBuffer[0] = v11;
      if ( (unsigned int)v14 >= *(_DWORD *)(v1 + 2884) )
        break;
      v13 = (_QWORD *)(v1 + 2904);
      v16 = *(_QWORD *)(*(_QWORD *)(v1 + 2904) + 8LL * v14);
      NumaMemory = TeredoRioAllocateNumaMemory(0xC0u, *(unsigned __int16 *)(v16 + 24));
      v18 = NumaMemory;
      if ( !NumaMemory )
      {
        WorkerThreads = 8;
        v25 = L"TeredoRioAllocateNumaMemory for Rio socket failed: %u";
        LODWORD(v2) = 8;
        goto LABEL_49;
      }
      *(_QWORD *)(*(_QWORD *)(a1 + 136) + 8LL * vInBuffer[0]) = NumaMemory;
      *(_QWORD *)NumaMemory = a1;
      *(_DWORD *)(NumaMemory + 16) = vInBuffer[0];
      v19 = WSASocketW(2, 2, 0, 0, 0, 0x100u);
      *(_QWORD *)(v18 + 8) = v19;
      if ( v19 == -1 )
        goto LABEL_26;
      if ( WSAIoctl(v19, 0x98000015, vInBuffer, 2u, 0, 0, &cbBytesReturned, 0, 0) )
      {
        Error = WSAGetLastError();
        EventWriteError0(0x100000, L"setsockopt port sharing failed: %u", Error);
      }
      LODWORD(v2) = TeredoEnableRealArrivalIf(*(_QWORD *)(v18 + 8));
      if ( (_DWORD)v2 )
        goto LABEL_50;
      if ( bind(*(_QWORD *)(v18 + 8), &name, 16) == -1 )
      {
LABEL_26:
        v9 = WSAGetLastError();
        goto LABEL_27;
      }
      if ( *(_QWORD *)(v1 + 2680) )
      {
        *(_DWORD *)optval = v2;
        if ( setsockopt(*(_QWORD *)(v18 + 8), 0, v2 + 11, optval, 4) == -1 )
        {
          LastError = GetLastError();
          EventWrite0(0x100000, L"IP_MULTICAST_LOOP: %u", LastError);
        }
        *(_DWORD *)v36 = *(_DWORD *)(*(_QWORD *)(v1 + 2680) + 4LL);
        *(_DWORD *)&v36[4] = *(_DWORD *)(v1 + 2664);
        if ( setsockopt(*(_QWORD *)(v18 + 8), 0, 12, v36, 8) == -1 )
        {
          v22 = GetLastError();
          EventWrite0(0x100000, L"IP_ADD_MEMBERSHIP: %u", v22);
        }
      }
      WorkerThreads = TeredoRioSocketSetupHelper(v18, 1);
      LODWORD(v2) = WorkerThreads;
      if ( WorkerThreads )
      {
        v25 = L"Failed TeredoRioSocketSetupHelper. Error (%d)";
LABEL_49:
        EventWriteError0(0x100000, v25, WorkerThreads);
        goto LABEL_50;
      }
      v24 = TeredoRioAllocateNumaMemory(24 * v12, *(unsigned __int16 *)(v16 + 24));
      *(_QWORD *)(v18 + 160) = v24;
      if ( !v24 )
      {
        v2 = GetLastError();
        EventWriteError0(0x100000, L"Failed to create Results. Error (%d)", v2);
        goto LABEL_28;
      }
      v15 = v2 + 1;
      v11 = v2 + 1 + vInBuffer[0];
      v14 = v11;
    }
    *(_DWORD *)(a1 + 144) = 2;
    RoReferenceEx(a1 + 144);
    v26 = 0;
    vInBuffer[0] = 0;
    v27 = 0;
    while ( (unsigned int)v26 < *(_DWORD *)(v1 + 2884) )
    {
      v28 = *(_QWORD *)(*(_QWORD *)(a1 + 136) + 8LL * v26);
      v29 = *(_QWORD **)(*v13 + 8LL * v27);
      WorkerThreads = TeredoRioCreateWorkerThreads(a1, v28, v26, 0);
      LODWORD(v2) = WorkerThreads;
      if ( WorkerThreads )
      {
        v25 = L"Failed TeredoRioCreateWorkerThreads. Error (%d)";
        goto LABEL_49;
      }
      if ( ((unsigned __int8)v15 & (unsigned __int8)Microsoft_Windows_Iphlpsvc_TraceEnableBits) != 0 )
        McTemplateU0z_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_TEREDO_IO,
          L"Beginning to post initial packets on Secondary Socket.");
      v30 = *(_DWORD *)(v1 + 2892);
      v31 = v30 + *(_DWORD *)(v1 + 2896);
      while ( v30 < v31 )
      {
        LODWORD(v2) = TeredoRioPostReceive(a1, *(_QWORD *)(*v29 + 8LL * v30), v30, vInBuffer[0], 0);
        if ( (_DWORD)v2 )
          goto LABEL_50;
        ++v30;
      }
      v15 = 1;
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_TEREDO_IO,
          L"Successfully posted initial packets on Secondary Socket.");
      LODWORD(v2) = (*(__int64 (__fastcall **)(_QWORD))(v1 + 2848))(*(_QWORD *)(v28 + 152));
      if ( (_DWORD)v2 )
      {
        if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(
            MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
            EVENT_IPHLPSVC_ETW_TEREDO_IO,
            L"Failed to post initial notify on secondary socket.");
        goto LABEL_50;
      }
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_TEREDO_IO,
          L"Created Secondary Socket.");
      v13 = (_QWORD *)(v1 + 2904);
      v26 = ++vInBuffer[0];
      v27 = vInBuffer[0];
    }
  }
  else
  {
    v9 = GetLastError();
LABEL_27:
    LODWORD(v2) = v9;
LABEL_28:
    if ( (_DWORD)v2 )
      goto LABEL_50;
  }
LABEL_53:
  EventWriteLeaveEx(0x100000, L"TeredoRioCreateSecondarySockets");
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180056c18  push    rbp
0x180056c1a  push    rbx
0x180056c1b  push    rsi
0x180056c1c  push    rdi
0x180056c1d  push    r12
0x180056c1f  push    r13
0x180056c21  push    r14
0x180056c23  push    r15
0x180056c25  lea     rbp, [rsp-1Fh]
0x180056c2a  sub     rsp, 88h
0x180056c31  mov     rax, cs:__security_cookie
0x180056c38  xor     rax, rsp
0x180056c3b  mov     [rbp+57h+var_48], rax
0x180056c3f  mov     rdi, [rcx]
0x180056c42  lea     rdx, aTeredoriocreat_2; "TeredoRioCreateSecondarySockets"
0x180056c49  xor     ebx, ebx
0x180056c4b  mov     r14, rcx
0x180056c4e  xorps   xmm0, xmm0
0x180056c51  mov     dword ptr [rbp+57h+optval], ebx
0x180056c54  mov     r13d, 100000h
0x180056c5a  mov     qword ptr [rbp+57h+var_60], rbx
0x180056c5e  mov     ecx, r13d
0x180056c61  mov     [rbp+57h+vInBuffer], bx
0x180056c65  movups  xmmword ptr [rbp+57h+name.sa_family], xmm0
0x180056c69  mov     [rbp+57h+cbBytesReturned], ebx
0x180056c6c  call    EventWriteEnterEx
0x180056c71  mov     rax, [rdi+0A78h]
0x180056c78  mov     esi, [rdi+0B54h]
0x180056c7e  mov     r15d, [rdi+0B50h]
0x180056c85  mov     r12d, [rdi+0B4Ch]
0x180056c8c  test    rax, rax
0x180056c8f  jz      short loc_180056CAC
0x180056c91  movups  xmm0, xmmword ptr [rax]
0x180056c94  xor     ecx, ecx; hostlong
0x180056c96  movdqu  xmmword ptr [rbp+57h+name.sa_family], xmm0
0x180056c9b  call    cs:__imp_htonl
0x180056ca2  nop     dword ptr [rax+rax+00h]
0x180056ca7  mov     dword ptr [rbp+57h+name.sa_data+2], eax
0x180056caa  jmp     short loc_180056CB8
0x180056cac  movups  xmm0, xmmword ptr [rdi+0A44h]
0x180056cb3  movdqu  xmmword ptr [rbp+57h+name.sa_family], xmm0
0x180056cb8  xor     r9d, r9d; lpName
0x180056cbb  xor     r8d, r8d; bInitialState
0x180056cbe  xor     ecx, ecx; lpEventAttributes
0x180056cc0  lea     edx, [r9+1]; bManualReset
0x180056cc4  call    cs:__imp_CreateEventW
0x180056ccb  nop     dword ptr [rax+rax+00h]
0x180056cd0  mov     [r14+98h], rax
0x180056cd7  test    rax, rax
0x180056cda  jnz     short loc_180056CED
0x180056cdc  call    cs:__imp_GetLastError
0x180056ce3  nop     dword ptr [rax+rax+00h]
0x180056ce8  jmp     loc_180056FA0
0x180056ced  mov     r8d, [rdi+0B44h]
0x180056cf4  mov     edx, 8; dwFlags
0x180056cf9  mov     rcx, [rdi+0A10h]; hHeap
0x180056d00  shl     r8, 3; dwBytes
0x180056d04  call    cs:__imp_HeapAlloc
0x180056d0b  nop     dword ptr [rax+rax+00h]
0x180056d10  mov     [r14+88h], rax
0x180056d17  test    rax, rax
0x180056d1a  jnz     short loc_180056D32
0x180056d1c  mov     eax, 8
0x180056d21  lea     rdx, aHeapallocForRi; "HeapAlloc for Rio socket pointers faile"...
0x180056d28  mov     ebx, eax
0x180056d2a  mov     ecx, r13d
0x180056d2d  jmp     loc_180057135
0x180056d32  xor     eax, eax
0x180056d34  lea     r13d, [r12+r15]
0x180056d38  add     r13d, esi
0x180056d3b  lea     r12, [rdi+0B58h]
0x180056d42  xor     ecx, ecx
0x180056d44  lea     esi, [rax+1]
0x180056d47  mov     [rbp+57h+vInBuffer], ax
0x180056d4b  movzx   eax, cx
0x180056d4e  cmp     eax, [rdi+0B44h]
0x180056d54  jnb     loc_180056FC2
0x180056d5a  movzx   ecx, cx
0x180056d5d  lea     r12, [rdi+0B58h]
0x180056d64  mov     rax, [r12]
0x180056d68  mov     r15, [rax+rcx*8]
0x180056d6c  mov     ecx, 0C0h; Size
0x180056d71  movzx   edx, word ptr [r15+18h]; nndPreferred
0x180056d76  call    TeredoRioAllocateNumaMemory
0x180056d7b  xor     ebx, ebx
0x180056d7d  mov     rsi, rax
0x180056d80  test    rax, rax
0x180056d83  jz      loc_180056FAF
0x180056d89  movzx   edx, [rbp+57h+vInBuffer]
0x180056d8d  xor     r9d, r9d; lpProtocolInfo
0x180056d90  mov     rcx, [r14+88h]
0x180056d97  xor     r8d, r8d; protocol
0x180056d9a  mov     [rsp+0C0h+dwFlags], 100h; dwFlags
0x180056da2  mov     [rsp+0C0h+g], ebx; g
0x180056da6  mov     [rcx+rdx*8], rax
0x180056daa  mov     [rax], r14
0x180056dad  movzx   ecx, [rbp+57h+vInBuffer]
0x180056db1  mov     [rax+10h], ecx
0x180056db4  lea     eax, [rbx+2]
0x180056db7  mov     edx, eax; type
0x180056db9  mov     ecx, eax; af
0x180056dbb  call    cs:__imp_WSASocketW
0x180056dc2  nop     dword ptr [rax+rax+00h]
0x180056dc7  mov     [rsi+8], rax
0x180056dcb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180056dcf  jz      loc_180056F94
0x180056dd5  mov     [rsp+0C0h+lpCompletionRoutine], rbx; lpCompletionRoutine
0x180056dda  lea     rcx, [rbp+57h+cbBytesReturned]
0x180056dde  mov     [rsp+0C0h+lpOverlapped], rbx; lpOverlapped
0x180056de3  lea     r9d, [rbx+2]; cbInBuffer
0x180056de7  mov     [rsp+0C0h+lpcbBytesReturned], rcx; lpcbBytesReturned
0x180056dec  lea     r8, [rbp+57h+vInBuffer]; lpvInBuffer
0x180056df0  mov     [rsp+0C0h+dwFlags], ebx; cbOutBuffer
0x180056df4  mov     rcx, rax; s
0x180056df7  mov     edx, 98000015h; dwIoControlCode
0x180056dfc  mov     qword ptr [rsp+0C0h+g], rbx; lpvOutBuffer
0x180056e01  call    cs:__imp_WSAIoctl
0x180056e08  nop     dword ptr [rax+rax+00h]
0x180056e0d  test    eax, eax
0x180056e0f  jz      short loc_180056E31
0x180056e11  call    cs:__imp_WSAGetLastError
0x180056e18  nop     dword ptr [rax+rax+00h]
0x180056e1d  lea     rdx, aSetsockoptPort; "setsockopt port sharing failed: %u"
0x180056e24  mov     ecx, 100000h
0x180056e29  mov     r8d, eax
0x180056e2c  call    EventWriteError0
0x180056e31  mov     rcx, [rsi+8]
0x180056e35  call    TeredoEnableRealArrivalIf
0x180056e3a  mov     ebx, eax
0x180056e3c  test    eax, eax
0x180056e3e  jnz     loc_18005713D
0x180056e44  mov     rcx, [rsi+8]; s
0x180056e48  lea     r8d, [rax+10h]; namelen
0x180056e4c  lea     rdx, [rbp+57h+name]; name
0x180056e50  call    cs:__imp_bind
0x180056e57  nop     dword ptr [rax+rax+00h]
0x180056e5c  cmp     eax, 0FFFFFFFFh
0x180056e5f  jz      loc_180056F94
0x180056e65  cmp     qword ptr [rdi+0A78h], 0
0x180056e6d  jz      loc_180056F1A
0x180056e73  mov     dword ptr [rbp+57h+optval], ebx
0x180056e76  lea     r9, [rbp+57h+optval]; optval
0x180056e7a  mov     rcx, [rsi+8]; s
0x180056e7e  lea     r8d, [rbx+0Bh]; optname
0x180056e82  xor     edx, edx; level
0x180056e84  mov     [rsp+0C0h+g], 4; optlen
0x180056e8c  call    cs:__imp_setsockopt
0x180056e93  nop     dword ptr [rax+rax+00h]
0x180056e98  cmp     eax, 0FFFFFFFFh
0x180056e9b  jnz     short loc_180056EBD
0x180056e9d  call    cs:__imp_GetLastError
0x180056ea4  nop     dword ptr [rax+rax+00h]
0x180056ea9  lea     rdx, aIpMulticastLoo; "IP_MULTICAST_LOOP: %u"
0x180056eb0  mov     ecx, 100000h
0x180056eb5  mov     r8d, eax
0x180056eb8  call    EventWrite0
0x180056ebd  mov     rax, [rdi+0A78h]
0x180056ec4  lea     r9, [rbp+57h+var_60]; optval
0x180056ec8  xor     edx, edx; level
0x180056eca  mov     [rsp+0C0h+g], 8; optlen
0x180056ed2  mov     ecx, [rax+4]
0x180056ed5  mov     dword ptr [rbp+57h+var_60], ecx
0x180056ed8  lea     r8d, [rdx+0Ch]; optname
0x180056edc  mov     eax, [rdi+0A68h]
0x180056ee2  mov     dword ptr [rbp+57h+var_60+4], eax
0x180056ee5  mov     rcx, [rsi+8]; s
0x180056ee9  call    cs:__imp_setsockopt
0x180056ef0  nop     dword ptr [rax+rax+00h]
0x180056ef5  cmp     eax, 0FFFFFFFFh
0x180056ef8  jnz     short loc_180056F1A
0x180056efa  call    cs:__imp_GetLastError
0x180056f01  nop     dword ptr [rax+rax+00h]
0x180056f06  lea     rdx, aIpAddMembershi; "IP_ADD_MEMBERSHIP: %u"
0x180056f0d  mov     ecx, 100000h
0x180056f12  mov     r8d, eax
0x180056f15  call    EventWrite0
0x180056f1a  mov     edx, 1
0x180056f1f  mov     rcx, rsi
0x180056f22  call    TeredoRioSocketSetupHelper
0x180056f27  mov     ebx, eax
0x180056f29  test    eax, eax
0x180056f2b  jnz     short loc_180056F88
0x180056f2d  movzx   edx, word ptr [r15+18h]; nndPreferred
0x180056f32  lea     rcx, ds:0[r13*2]
0x180056f3a  add     rcx, r13
0x180056f3d  shl     rcx, 3; Size
0x180056f41  call    TeredoRioAllocateNumaMemory
0x180056f46  mov     [rsi+0A0h], rax
0x180056f4d  test    rax, rax
0x180056f50  jz      short loc_180056F64
0x180056f52  movzx   eax, [rbp+57h+vInBuffer]
0x180056f56  lea     esi, [rbx+1]
0x180056f59  add     ax, si
0x180056f5c  movzx   ecx, ax
0x180056f5f  jmp     loc_180056D47
0x180056f64  call    cs:__imp_GetLastError
0x180056f6b  nop     dword ptr [rax+rax+00h]
0x180056f70  lea     rdx, aFailedToCreate_1; "Failed to create Results. Error (%d)"
0x180056f77  mov     ecx, 100000h
0x180056f7c  mov     r8d, eax
0x180056f7f  mov     ebx, eax
0x180056f81  call    EventWriteError0
0x180056f86  jmp     short loc_180056FA2
0x180056f88  lea     rdx, aFailedTeredori_1; "Failed TeredoRioSocketSetupHelper. Erro"...
0x180056f8f  jmp     loc_180057130
0x180056f94  call    cs:__imp_WSAGetLastError
0x180056f9b  nop     dword ptr [rax+rax+00h]
0x180056fa0  mov     ebx, eax
0x180056fa2  test    ebx, ebx
0x180056fa4  jz      loc_180057156
0x180056faa  jmp     loc_18005713D
0x180056faf  mov     eax, 8
0x180056fb4  lea     rdx, aTeredorioalloc_0; "TeredoRioAllocateNumaMemory for Rio soc"...
0x180056fbb  mov     ebx, eax
0x180056fbd  jmp     loc_180057130
0x180056fc2  lea     rcx, [r14+90h]
0x180056fc9  mov     dword ptr [rcx], 2
0x180056fcf  call    RoReferenceEx
0x180056fd4  xor     ecx, ecx
0x180056fd6  mov     [rbp+57h+vInBuffer], cx
0x180056fda  xor     edx, edx
0x180056fdc  movzx   r8d, cx
0x180056fe0  cmp     r8d, [rdi+0B44h]
0x180056fe7  jnb     loc_180057156
0x180056fed  mov     rax, [r14+88h]
0x180056ff4  xor     r9d, r9d
0x180056ff7  movzx   ecx, cx
0x180056ffa  mov     r13, [rax+rcx*8]
0x180056ffe  mov     rax, [r12]
0x180057002  movzx   ecx, dx
0x180057005  mov     rdx, r13
0x180057008  mov     r12, [rax+rcx*8]
0x18005700c  mov     rcx, r14
0x18005700f  call    TeredoRioCreateWorkerThreads
0x180057014  mov     ebx, eax
0x180057016  test    eax, eax
0x180057018  jnz     loc_180057129
0x18005701e  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, sil
0x180057025  jz      short loc_180057041
0x180057027  lea     r8, aBeginningToPos_0; "Beginning to post initial packets on Se"...
0x18005702e  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_IO
0x180057035  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18005703c  call    McTemplateU0z_EventWriteTransfer
0x180057041  mov     r15d, [rdi+0B50h]
0x180057048  mov     esi, [rdi+0B4Ch]
0x18005704e  add     r15d, esi
0x180057051  cmp     esi, r15d
0x180057054  jnb     short loc_180057083
0x180057056  mov     rdx, [r12]
0x18005705a  mov     r8d, esi
0x18005705d  movzx   r9d, [rbp+57h+vInBuffer]
0x180057062  mov     rcx, r14
0x180057065  mov     eax, esi
0x180057067  mov     byte ptr [rsp+0C0h+g], 0
0x18005706c  mov     rdx, [rdx+rax*8]
0x180057070  call    TeredoRioPostReceive
0x180057075  mov     ebx, eax
0x180057077  test    eax, eax
0x180057079  jnz     loc_18005713D
0x18005707f  inc     esi
0x180057081  jmp     short loc_180057051
0x180057083  mov     esi, 1
0x180057088  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, sil
0x18005708f  jz      short loc_1800570AB
0x180057091  lea     r8, aSuccessfullyPo; "Successfully posted initial packets on "...
0x180057098  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_IO
0x18005709f  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800570a6  call    McTemplateU0z_EventWriteTransfer
0x1800570ab  mov     rcx, [r13+98h]
0x1800570b2  mov     rax, [rdi+0B20h]
0x1800570b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800570be  mov     ebx, eax
0x1800570c0  test    eax, eax
0x1800570c2  jnz     short loc_180057104
0x1800570c4  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, sil
0x1800570cb  jz      short loc_1800570E7
0x1800570cd  lea     r8, aCreatedSeconda; "Created Secondary Socket."
0x1800570d4  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_IO
0x1800570db  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800570e2  call    McTemplateU0z_EventWriteTransfer
0x1800570e7  movzx   eax, [rbp+57h+vInBuffer]
0x1800570eb  lea     r12, [rdi+0B58h]
0x1800570f2  add     ax, si
0x1800570f5  mov     [rbp+57h+vInBuffer], ax
0x1800570f9  movzx   ecx, ax
0x1800570fc  movzx   edx, ax
0x1800570ff  jmp     loc_180056FDC
0x180057104  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, sil
0x18005710b  jz      short loc_18005713D
0x18005710d  lea     r8, aFailedToPostIn_0; "Failed to post initial notify on second"...
0x180057114  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_IO
0x18005711b  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180057122  call    McTemplateU0z_EventWriteTransfer
0x180057127  jmp     short loc_18005713D
0x180057129  lea     rdx, aFailedTeredori_0; "Failed TeredoRioCreateWorkerThreads. Er"...
0x180057130  mov     ecx, 100000h
0x180057135  mov     r8d, eax
0x180057138  call    EventWriteError0
0x18005713d  test    byte ptr [r14+90h], 1
0x180057145  mov     rcx, r14
  ... truncated ...
```
