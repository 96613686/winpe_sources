# TeredoRioCreateSecondarySockets

- ea: `0x180056c38`
- end: `0x1800571aa`
- name: `TeredoRioCreateSecondarySockets`
- size: `1394`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800589f8`

## callees

- `0x180008210`
- `0x180009010`
- `0x18000d7c0`
- `0x1800159d4`
- `0x1800190f0`
- `0x18001cab8`
- `0x180024250`
- `0x180041454`
- `0x18004b5f0`
- `0x180055f4c`
- `0x180056c38`
- `0x1800571b0`
- `0x180057660`
- `0x180057b44`
- `0x180058844`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056d24`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056d24`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056ce4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056ce4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056cfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ebd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056f1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056f84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056cfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ebd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056f1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056f84`
- `WS2_32!WSASocketW` at `0x180056ddb`
- `WS2_32!WSASocketW` at `0x180056ddb`
- `WS2_32!WSAIoctl` at `0x180056e21`
- `WS2_32!WSAIoctl` at `0x180056e21`
- `WS2_32!__imp_bind` at `0x180056e70`
- `WS2_32!__imp_bind` at `0x180056e70`
- `WS2_32!__imp_htonl` at `0x180056cbb`
- `WS2_32!__imp_htonl` at `0x180056cbb`
- `WS2_32!__imp_setsockopt` at `0x180056eac`
- `WS2_32!__imp_setsockopt` at `0x180056f09`
- `WS2_32!__imp_setsockopt` at `0x180056eac`
- `WS2_32!__imp_setsockopt` at `0x180056f09`
- `WS2_32!__imp_WSAGetLastError` at `0x180056e31`
- `WS2_32!__imp_WSAGetLastError` at `0x180056fb4`
- `WS2_32!__imp_WSAGetLastError` at `0x180056e31`
- `WS2_32!__imp_WSAGetLastError` at `0x180056fb4`

## string_xrefs

- `0x1800570ed`: `Created Secondary Socket.`
- `0x180056c62`: `TeredoRioCreateSecondarySockets`
- `0x180057176`: `TeredoRioCreateSecondarySockets`
- `0x180056f90`: `Failed to create Results. Error (%d)`
- `0x180057149`: `Failed TeredoRioCreateWorkerThreads. Error (%d)`

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
0x180056c38  push    rbp
0x180056c3a  push    rbx
0x180056c3b  push    rsi
0x180056c3c  push    rdi
0x180056c3d  push    r12
0x180056c3f  push    r13
0x180056c41  push    r14
0x180056c43  push    r15
0x180056c45  lea     rbp, [rsp-1Fh]
0x180056c4a  sub     rsp, 88h
0x180056c51  mov     rax, cs:__security_cookie
0x180056c58  xor     rax, rsp
0x180056c5b  mov     [rbp+57h+var_48], rax
0x180056c5f  mov     rdi, [rcx]
0x180056c62  lea     rdx, aTeredoriocreat_2; "TeredoRioCreateSecondarySockets"
0x180056c69  xor     ebx, ebx
0x180056c6b  mov     r14, rcx
0x180056c6e  xorps   xmm0, xmm0
0x180056c71  mov     dword ptr [rbp+57h+optval], ebx
0x180056c74  mov     r13d, 100000h
0x180056c7a  mov     qword ptr [rbp+57h+var_60], rbx
0x180056c7e  mov     ecx, r13d
0x180056c81  mov     [rbp+57h+vInBuffer], bx
0x180056c85  movups  xmmword ptr [rbp+57h+name.sa_family], xmm0
0x180056c89  mov     [rbp+57h+cbBytesReturned], ebx
0x180056c8c  call    EventWriteEnterEx
0x180056c91  mov     rax, [rdi+0A78h]
0x180056c98  mov     esi, [rdi+0B54h]
0x180056c9e  mov     r15d, [rdi+0B50h]
0x180056ca5  mov     r12d, [rdi+0B4Ch]
0x180056cac  test    rax, rax
0x180056caf  jz      short loc_180056CCC
0x180056cb1  movups  xmm0, xmmword ptr [rax]
0x180056cb4  xor     ecx, ecx; hostlong
0x180056cb6  movdqu  xmmword ptr [rbp+57h+name.sa_family], xmm0
0x180056cbb  call    cs:__imp_htonl
0x180056cc2  nop     dword ptr [rax+rax+00h]
0x180056cc7  mov     dword ptr [rbp+57h+name.sa_data+2], eax
0x180056cca  jmp     short loc_180056CD8
0x180056ccc  movups  xmm0, xmmword ptr [rdi+0A44h]
0x180056cd3  movdqu  xmmword ptr [rbp+57h+name.sa_family], xmm0
0x180056cd8  xor     r9d, r9d; lpName
0x180056cdb  xor     r8d, r8d; bInitialState
0x180056cde  xor     ecx, ecx; lpEventAttributes
0x180056ce0  lea     edx, [r9+1]; bManualReset
0x180056ce4  call    cs:__imp_CreateEventW
0x180056ceb  nop     dword ptr [rax+rax+00h]
0x180056cf0  mov     [r14+98h], rax
0x180056cf7  test    rax, rax
0x180056cfa  jnz     short loc_180056D0D
0x180056cfc  call    cs:__imp_GetLastError
0x180056d03  nop     dword ptr [rax+rax+00h]
0x180056d08  jmp     loc_180056FC0
0x180056d0d  mov     r8d, [rdi+0B44h]
0x180056d14  mov     edx, 8; dwFlags
0x180056d19  mov     rcx, [rdi+0A10h]; hHeap
0x180056d20  shl     r8, 3; dwBytes
0x180056d24  call    cs:__imp_HeapAlloc
0x180056d2b  nop     dword ptr [rax+rax+00h]
0x180056d30  mov     [r14+88h], rax
0x180056d37  test    rax, rax
0x180056d3a  jnz     short loc_180056D52
0x180056d3c  mov     eax, 8
0x180056d41  lea     rdx, aHeapallocForRi; "HeapAlloc for Rio socket pointers faile"...
0x180056d48  mov     ebx, eax
0x180056d4a  mov     ecx, r13d
0x180056d4d  jmp     loc_180057155
0x180056d52  xor     eax, eax
0x180056d54  lea     r13d, [r12+r15]
0x180056d58  add     r13d, esi
0x180056d5b  lea     r12, [rdi+0B58h]
0x180056d62  xor     ecx, ecx
0x180056d64  lea     esi, [rax+1]
0x180056d67  mov     [rbp+57h+vInBuffer], ax
0x180056d6b  movzx   eax, cx
0x180056d6e  cmp     eax, [rdi+0B44h]
0x180056d74  jnb     loc_180056FE2
0x180056d7a  movzx   ecx, cx
0x180056d7d  lea     r12, [rdi+0B58h]
0x180056d84  mov     rax, [r12]
0x180056d88  mov     r15, [rax+rcx*8]
0x180056d8c  mov     ecx, 0C0h; Size
0x180056d91  movzx   edx, word ptr [r15+18h]; nndPreferred
0x180056d96  call    TeredoRioAllocateNumaMemory
0x180056d9b  xor     ebx, ebx
0x180056d9d  mov     rsi, rax
0x180056da0  test    rax, rax
0x180056da3  jz      loc_180056FCF
0x180056da9  movzx   edx, [rbp+57h+vInBuffer]
0x180056dad  xor     r9d, r9d; lpProtocolInfo
0x180056db0  mov     rcx, [r14+88h]
0x180056db7  xor     r8d, r8d; protocol
0x180056dba  mov     [rsp+0C0h+dwFlags], 100h; dwFlags
0x180056dc2  mov     [rsp+0C0h+g], ebx; g
0x180056dc6  mov     [rcx+rdx*8], rax
0x180056dca  mov     [rax], r14
0x180056dcd  movzx   ecx, [rbp+57h+vInBuffer]
0x180056dd1  mov     [rax+10h], ecx
0x180056dd4  lea     eax, [rbx+2]
0x180056dd7  mov     edx, eax; type
0x180056dd9  mov     ecx, eax; af
0x180056ddb  call    cs:__imp_WSASocketW
0x180056de2  nop     dword ptr [rax+rax+00h]
0x180056de7  mov     [rsi+8], rax
0x180056deb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180056def  jz      loc_180056FB4
0x180056df5  mov     [rsp+0C0h+lpCompletionRoutine], rbx; lpCompletionRoutine
0x180056dfa  lea     rcx, [rbp+57h+cbBytesReturned]
0x180056dfe  mov     [rsp+0C0h+lpOverlapped], rbx; lpOverlapped
0x180056e03  lea     r9d, [rbx+2]; cbInBuffer
0x180056e07  mov     [rsp+0C0h+lpcbBytesReturned], rcx; lpcbBytesReturned
0x180056e0c  lea     r8, [rbp+57h+vInBuffer]; lpvInBuffer
0x180056e10  mov     [rsp+0C0h+dwFlags], ebx; cbOutBuffer
0x180056e14  mov     rcx, rax; s
0x180056e17  mov     edx, 98000015h; dwIoControlCode
0x180056e1c  mov     qword ptr [rsp+0C0h+g], rbx; lpvOutBuffer
0x180056e21  call    cs:__imp_WSAIoctl
0x180056e28  nop     dword ptr [rax+rax+00h]
0x180056e2d  test    eax, eax
0x180056e2f  jz      short loc_180056E51
0x180056e31  call    cs:__imp_WSAGetLastError
0x180056e38  nop     dword ptr [rax+rax+00h]
0x180056e3d  lea     rdx, aSetsockoptPort; "setsockopt port sharing failed: %u"
0x180056e44  mov     ecx, 100000h
0x180056e49  mov     r8d, eax
0x180056e4c  call    EventWriteError0
0x180056e51  mov     rcx, [rsi+8]
0x180056e55  call    TeredoEnableRealArrivalIf
0x180056e5a  mov     ebx, eax
0x180056e5c  test    eax, eax
0x180056e5e  jnz     loc_18005715D
0x180056e64  mov     rcx, [rsi+8]; s
0x180056e68  lea     r8d, [rax+10h]; namelen
0x180056e6c  lea     rdx, [rbp+57h+name]; name
0x180056e70  call    cs:__imp_bind
0x180056e77  nop     dword ptr [rax+rax+00h]
0x180056e7c  cmp     eax, 0FFFFFFFFh
0x180056e7f  jz      loc_180056FB4
0x180056e85  cmp     qword ptr [rdi+0A78h], 0
0x180056e8d  jz      loc_180056F3A
0x180056e93  mov     dword ptr [rbp+57h+optval], ebx
0x180056e96  lea     r9, [rbp+57h+optval]; optval
0x180056e9a  mov     rcx, [rsi+8]; s
0x180056e9e  lea     r8d, [rbx+0Bh]; optname
0x180056ea2  xor     edx, edx; level
0x180056ea4  mov     [rsp+0C0h+g], 4; optlen
0x180056eac  call    cs:__imp_setsockopt
0x180056eb3  nop     dword ptr [rax+rax+00h]
0x180056eb8  cmp     eax, 0FFFFFFFFh
0x180056ebb  jnz     short loc_180056EDD
0x180056ebd  call    cs:__imp_GetLastError
0x180056ec4  nop     dword ptr [rax+rax+00h]
0x180056ec9  lea     rdx, aIpMulticastLoo; "IP_MULTICAST_LOOP: %u"
0x180056ed0  mov     ecx, 100000h
0x180056ed5  mov     r8d, eax
0x180056ed8  call    EventWrite0
0x180056edd  mov     rax, [rdi+0A78h]
0x180056ee4  lea     r9, [rbp+57h+var_60]; optval
0x180056ee8  xor     edx, edx; level
0x180056eea  mov     [rsp+0C0h+g], 8; optlen
0x180056ef2  mov     ecx, [rax+4]
0x180056ef5  mov     dword ptr [rbp+57h+var_60], ecx
0x180056ef8  lea     r8d, [rdx+0Ch]; optname
0x180056efc  mov     eax, [rdi+0A68h]
0x180056f02  mov     dword ptr [rbp+57h+var_60+4], eax
0x180056f05  mov     rcx, [rsi+8]; s
0x180056f09  call    cs:__imp_setsockopt
0x180056f10  nop     dword ptr [rax+rax+00h]
0x180056f15  cmp     eax, 0FFFFFFFFh
0x180056f18  jnz     short loc_180056F3A
0x180056f1a  call    cs:__imp_GetLastError
0x180056f21  nop     dword ptr [rax+rax+00h]
0x180056f26  lea     rdx, aIpAddMembershi; "IP_ADD_MEMBERSHIP: %u"
0x180056f2d  mov     ecx, 100000h
0x180056f32  mov     r8d, eax
0x180056f35  call    EventWrite0
0x180056f3a  mov     edx, 1
0x180056f3f  mov     rcx, rsi
0x180056f42  call    TeredoRioSocketSetupHelper
0x180056f47  mov     ebx, eax
0x180056f49  test    eax, eax
0x180056f4b  jnz     short loc_180056FA8
0x180056f4d  movzx   edx, word ptr [r15+18h]; nndPreferred
0x180056f52  lea     rcx, ds:0[r13*2]
0x180056f5a  add     rcx, r13
0x180056f5d  shl     rcx, 3; Size
0x180056f61  call    TeredoRioAllocateNumaMemory
0x180056f66  mov     [rsi+0A0h], rax
0x180056f6d  test    rax, rax
0x180056f70  jz      short loc_180056F84
0x180056f72  movzx   eax, [rbp+57h+vInBuffer]
0x180056f76  lea     esi, [rbx+1]
0x180056f79  add     ax, si
0x180056f7c  movzx   ecx, ax
0x180056f7f  jmp     loc_180056D67
0x180056f84  call    cs:__imp_GetLastError
0x180056f8b  nop     dword ptr [rax+rax+00h]
0x180056f90  lea     rdx, aFailedToCreate_1; "Failed to create Results. Error (%d)"
0x180056f97  mov     ecx, 100000h
0x180056f9c  mov     r8d, eax
0x180056f9f  mov     ebx, eax
0x180056fa1  call    EventWriteError0
0x180056fa6  jmp     short loc_180056FC2
0x180056fa8  lea     rdx, aFailedTeredori_1; "Failed TeredoRioSocketSetupHelper. Erro"...
0x180056faf  jmp     loc_180057150
0x180056fb4  call    cs:__imp_WSAGetLastError
0x180056fbb  nop     dword ptr [rax+rax+00h]
0x180056fc0  mov     ebx, eax
0x180056fc2  test    ebx, ebx
0x180056fc4  jz      loc_180057176
0x180056fca  jmp     loc_18005715D
0x180056fcf  mov     eax, 8
0x180056fd4  lea     rdx, aTeredorioalloc_0; "TeredoRioAllocateNumaMemory for Rio soc"...
0x180056fdb  mov     ebx, eax
0x180056fdd  jmp     loc_180057150
0x180056fe2  lea     rcx, [r14+90h]
0x180056fe9  mov     dword ptr [rcx], 2
0x180056fef  call    RoReferenceEx
0x180056ff4  xor     ecx, ecx
0x180056ff6  mov     [rbp+57h+vInBuffer], cx
0x180056ffa  xor     edx, edx
0x180056ffc  movzx   r8d, cx
0x180057000  cmp     r8d, [rdi+0B44h]
0x180057007  jnb     loc_180057176
0x18005700d  mov     rax, [r14+88h]
0x180057014  xor     r9d, r9d
0x180057017  movzx   ecx, cx
0x18005701a  mov     r13, [rax+rcx*8]
0x18005701e  mov     rax, [r12]
0x180057022  movzx   ecx, dx
0x180057025  mov     rdx, r13
0x180057028  mov     r12, [rax+rcx*8]
0x18005702c  mov     rcx, r14
0x18005702f  call    TeredoRioCreateWorkerThreads
0x180057034  mov     ebx, eax
0x180057036  test    eax, eax
0x180057038  jnz     loc_180057149
0x18005703e  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, sil
0x180057045  jz      short loc_180057061
0x180057047  lea     r8, aBeginningToPos_0; "Beginning to post initial packets on Se"...
0x18005704e  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_IO
0x180057055  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18005705c  call    McTemplateU0z_EventWriteTransfer
0x180057061  mov     r15d, [rdi+0B50h]
0x180057068  mov     esi, [rdi+0B4Ch]
0x18005706e  add     r15d, esi
0x180057071  cmp     esi, r15d
0x180057074  jnb     short loc_1800570A3
0x180057076  mov     rdx, [r12]
0x18005707a  mov     r8d, esi
0x18005707d  movzx   r9d, [rbp+57h+vInBuffer]
0x180057082  mov     rcx, r14
0x180057085  mov     eax, esi
0x180057087  mov     byte ptr [rsp+0C0h+g], 0
0x18005708c  mov     rdx, [rdx+rax*8]
0x180057090  call    TeredoRioPostReceive
0x180057095  mov     ebx, eax
0x180057097  test    eax, eax
0x180057099  jnz     loc_18005715D
0x18005709f  inc     esi
0x1800570a1  jmp     short loc_180057071
0x1800570a3  mov     esi, 1
0x1800570a8  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, sil
0x1800570af  jz      short loc_1800570CB
0x1800570b1  lea     r8, aSuccessfullyPo; "Successfully posted initial packets on "...
0x1800570b8  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_IO
0x1800570bf  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800570c6  call    McTemplateU0z_EventWriteTransfer
0x1800570cb  mov     rcx, [r13+98h]
0x1800570d2  mov     rax, [rdi+0B20h]
0x1800570d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800570de  mov     ebx, eax
0x1800570e0  test    eax, eax
0x1800570e2  jnz     short loc_180057124
0x1800570e4  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, sil
0x1800570eb  jz      short loc_180057107
0x1800570ed  lea     r8, aCreatedSeconda; "Created Secondary Socket."
0x1800570f4  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_IO
0x1800570fb  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180057102  call    McTemplateU0z_EventWriteTransfer
0x180057107  movzx   eax, [rbp+57h+vInBuffer]
0x18005710b  lea     r12, [rdi+0B58h]
0x180057112  add     ax, si
0x180057115  mov     [rbp+57h+vInBuffer], ax
0x180057119  movzx   ecx, ax
0x18005711c  movzx   edx, ax
0x18005711f  jmp     loc_180056FFC
0x180057124  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, sil
0x18005712b  jz      short loc_18005715D
0x18005712d  lea     r8, aFailedToPostIn_0; "Failed to post initial notify on second"...
0x180057134  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_IO
0x18005713b  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180057142  call    McTemplateU0z_EventWriteTransfer
0x180057147  jmp     short loc_18005715D
0x180057149  lea     rdx, aFailedTeredori_0; "Failed TeredoRioCreateWorkerThreads. Er"...
0x180057150  mov     ecx, 100000h
0x180057155  mov     r8d, eax
0x180057158  call    EventWriteError0
0x18005715d  test    byte ptr [r14+90h], 1
0x180057165  mov     rcx, r14
  ... truncated ...
```
