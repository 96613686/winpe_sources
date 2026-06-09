# TeredoRioCreatePrimarySockets

- ea: `0x1800562a0`
- end: `0x180056c30`
- name: `TeredoRioCreatePrimarySockets`
- size: `2448`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800589f8`

## callees

- `0x180008210`
- `0x180009010`
- `0x1800159d4`
- `0x180016498`
- `0x1800190f0`
- `0x18001cab8`
- `0x18001cb00`
- `0x18001de74`
- `0x18001edc8`
- `0x18001f1d0`
- `0x180024250`
- `0x180041454`
- `0x18004b5f0`
- `0x18004c188`
- `0x180055f4c`
- `0x1800562a0`
- `0x1800571b0`
- `0x180057b44`
- `0x180058844`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005642c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005642c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800563a3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800563a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800563bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800568b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800568d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800563bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800568b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800568d0`
- `WS2_32!WSASocketW` at `0x1800564db`
- `WS2_32!WSASocketW` at `0x1800564db`
- `WS2_32!WSAIoctl` at `0x180056589`
- `WS2_32!WSAIoctl` at `0x180056683`
- `WS2_32!WSAIoctl` at `0x180056589`
- `WS2_32!WSAIoctl` at `0x180056683`
- `WS2_32!__imp_bind` at `0x1800565cb`
- `WS2_32!__imp_bind` at `0x1800565cb`
- `WS2_32!__imp_getsockname` at `0x18005672f`
- `WS2_32!__imp_getsockname` at `0x18005672f`
- `WS2_32!__imp_setsockopt` at `0x180056536`
- `WS2_32!__imp_setsockopt` at `0x18005675f`
- `WS2_32!__imp_setsockopt` at `0x180056783`
- `WS2_32!__imp_setsockopt` at `0x180056536`
- `WS2_32!__imp_setsockopt` at `0x18005675f`
- `WS2_32!__imp_setsockopt` at `0x180056783`
- `WS2_32!__imp_WSAGetLastError` at `0x180056546`
- `WS2_32!__imp_WSAGetLastError` at `0x180056599`
- `WS2_32!__imp_WSAGetLastError` at `0x1800565dd`
- `WS2_32!__imp_WSAGetLastError` at `0x18005687d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800568a3`
- `WS2_32!__imp_WSAGetLastError` at `0x180056546`
- `WS2_32!__imp_WSAGetLastError` at `0x180056599`
- `WS2_32!__imp_WSAGetLastError` at `0x1800565dd`
- `WS2_32!__imp_WSAGetLastError` at `0x18005687d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800568a3`

## string_xrefs

- `0x1800568c4`: `Create socket failed: %u`
- `0x18005688b`: `Failed to read socket name. Error (%d)`
- `0x180056b4a`: `Created Primary Socket.`
- `0x180056871`: `Failed to create Results. Error (%d)`
- `0x180056ba9`: `Failed TeredoRioCreateWorkerThreads. Error (%d)`
- `0x180056313`: `TeredoRioCreatePrimarySockets`
- `0x180056bef`: `TeredoRioCreatePrimarySockets`
- `0x1800563ca`: `CreateEvent for Teredo device failed: %u`
- `0x180056bc0`: `TeredoCreateRioPrimarySocket failed with %u`

## pseudocode

```c
__int64 __fastcall TeredoRioCreatePrimarySockets(__int64 *a1)
{
  __int64 v1; // rdi
  __int64 v2; // r12
  DWORD LastError; // ebx
  int v4; // esi
  int v5; // r14d
  int v6; // r15d
  HANDLE EventW; // rax
  DWORD v8; // eax
  LPVOID v9; // rax
  unsigned __int16 v10; // cx
  int v11; // r14d
  __int64 v12; // r15
  __int64 NumaMemory; // rax
  __int64 v14; // rsi
  SOCKET v15; // rax
  SOCKET v16; // rcx
  unsigned int Error; // eax
  unsigned int v18; // eax
  __int64 v19; // rbx
  __int64 v21; // r13
  DWORD v22; // eax
  __int64 v23; // rax
  unsigned int k; // esi
  unsigned __int16 v25; // cx
  unsigned __int16 i; // dx
  __int64 v27; // r15
  __int64 v28; // rax
  _QWORD *v29; // r13
  DWORD WorkerThreads; // eax
  unsigned int v31; // r14d
  __int64 j; // rsi
  char v33; // al
  __int64 v34; // rbx
  char v35; // r15
  __int64 v36; // rsi
  unsigned int v37; // r12d
  __int64 v38; // rdx
  unsigned __int16 vInBuffer[2]; // [rsp+50h] [rbp-F8h] BYREF
  char optval[4]; // [rsp+54h] [rbp-F4h] BYREF
  DWORD lpcbBytesReturned; // [rsp+58h] [rbp-F0h] BYREF
  int namelen; // [rsp+5Ch] [rbp-ECh] BYREF
  char v44[4]; // [rsp+60h] [rbp-E8h] BYREF
  DWORD cbBytesReturned; // [rsp+64h] [rbp-E4h] BYREF
  unsigned int v46; // [rsp+68h] [rbp-E0h]
  __int64 *v47; // [rsp+70h] [rbp-D8h]
  __int64 v48; // [rsp+78h] [rbp-D0h]
  _OWORD vOutBuffer[7]; // [rsp+80h] [rbp-C8h] BYREF
  _DWORD v50[4]; // [rsp+F0h] [rbp-58h] BYREF
  struct sockaddr name; // [rsp+100h] [rbp-48h] BYREF

  v1 = *a1;
  v2 = (__int64)a1;
  v47 = a1;
  v48 = v1;
  *(_DWORD *)optval = 0;
  *(_DWORD *)v44 = 0;
  namelen = 0;
  vInBuffer[0] = 0;
  name = 0;
  DWORD1(vOutBuffer[0]) = 0;
  memset_0(vOutBuffer, 0, 0x6Cu);
  v50[0] = -2062950271;
  v50[1] = 1074108125;
  v50[2] = 782132657;
  v50[3] = 1067370472;
  lpcbBytesReturned = 0;
  cbBytesReturned = 0;
  EventWriteEnterEx(0x100000, L"TeredoRioCreatePrimarySockets");
  *(_DWORD *)(v2 + 144) = 2;
  RoReferenceEx(v2 + 144);
  if ( !(unsigned int)TeredoTypeServer(*(_QWORD *)(v1 + 2760)) )
  {
    LastError = 50;
    goto LABEL_83;
  }
  v4 = *(_DWORD *)(v1 + 2900);
  v5 = *(_DWORD *)(v1 + 2896);
  v6 = *(_DWORD *)(v1 + 2892);
  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)(v2 + 152) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    EventWriteError0(0x100000, L"CreateEvent for Teredo device failed: %u", LastError);
    goto LABEL_83;
  }
  name = *(struct sockaddr *)(v1 + 2660);
  v8 = TeredoOffloadV4FlowParams(
         *(_QWORD *)(v1 + 3272),
         HIDWORD(*(_QWORD *)&name.sa_family),
         *(_QWORD *)&name.sa_family >> 16);
  LastError = v8;
  if ( v8 )
  {
    EventWriteError0(0x100000, L"TeredoOffloadV4FlowParams failed: %u", v8);
    goto LABEL_83;
  }
  LastError = 8;
  v9 = HeapAlloc(*(HANDLE *)(v1 + 2576), 8u, 8LL * *(unsigned int *)(v1 + 2884));
  *(_QWORD *)(v2 + 136) = v9;
  if ( !v9 )
  {
    EventWriteError0(0x100000, L"HeapAlloc for Rio socket pointers failed: %u", 8);
    goto LABEL_83;
  }
  v46 = v4 + v6 + v5;
  vInBuffer[0] = 0;
  v10 = 0;
  v11 = 1;
LABEL_10:
  if ( (unsigned int)v10 >= *(_DWORD *)(v1 + 2884) )
  {
    vInBuffer[0] = 0;
    v25 = 0;
    for ( i = 0; ; i = vInBuffer[0] )
    {
      if ( (unsigned int)v25 >= *(_DWORD *)(v1 + 2884) )
      {
        LastError = 0;
        goto LABEL_86;
      }
      v27 = *(_QWORD *)(*(_QWORD *)(v2 + 136) + 8LL * v25);
      v28 = *(_QWORD *)(v1 + 2904);
      v48 = v27;
      v29 = *(_QWORD **)(v28 + 8LL * i);
      WorkerThreads = TeredoRioCreateWorkerThreads(v2, v27, v25, 1);
      LastError = WorkerThreads;
      if ( WorkerThreads )
      {
        EventWriteError0(0x100000, L"Failed TeredoRioCreateWorkerThreads. Error (%d)", WorkerThreads);
        goto LABEL_83;
      }
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_TEREDO_IO,
          L"Beginning to post initial packets on Primary Socket.");
      v31 = *(_DWORD *)(v1 + 2892);
      for ( j = 0; (unsigned int)j < v31; j = (unsigned int)(j + 1) )
      {
        LastError = TeredoRioPostReceive(v2, *(_QWORD *)(*v29 + 8 * j), j, vInBuffer[0], 1);
        if ( LastError )
          goto LABEL_83;
      }
      v33 = Microsoft_Windows_Iphlpsvc_TraceEnableBits;
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_TEREDO_IO,
          L"Successfully posted initial packets on Primary Socket.");
        v33 = Microsoft_Windows_Iphlpsvc_TraceEnableBits;
      }
      if ( !(_DWORD)j )
      {
LABEL_81:
        LastError = 30;
        goto LABEL_83;
      }
      v34 = *(_QWORD *)v2 + 3248LL;
      if ( (v33 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_TEREDO_IO,
          L"Beginning to post initial packets on Tunnel device.");
      if ( (unsigned __int8)RoReferenceEx(v34 + 128) )
      {
        v35 = 0;
        v36 = (unsigned int)(*(_DWORD *)(v1 + 2892) + *(_DWORD *)(v1 + 2896));
        v37 = v36 + *(_DWORD *)(v1 + 2900);
        while ( (unsigned int)v36 < v37 )
        {
          v38 = *(_QWORD *)(*v29 + 8 * v36);
          *(_DWORD *)(v38 + 408) = 1472;
          *(_QWORD *)(v38 + 416) = v38 + 524;
          *(_OWORD *)(v38 + 256) = 0;
          *(_OWORD *)(v38 + 272) = 0;
          *(_QWORD *)(v38 + 288) = 0;
          *(_DWORD *)(v38 + 296) = 0;
          *(_QWORD *)(v38 + 32) = TeredoRioPacketCompletionRoutine;
          *(_DWORD *)(v38 + 60) = 2;
          *(_QWORD *)(v38 + 40) = v34;
          if ( (unsigned int)TeredoTunnelPostReceive((__int64 *)v34, (struct _OVERLAPPED *)v38) )
          {
            v35 = 1;
          }
          else if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
          {
            McTemplateU0z_EventWriteTransfer(
              MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
              EVENT_IPHLPSVC_ETW_TEREDO_IO,
              L"Could not post packets on Tunnel device.");
          }
          v36 = (unsigned int)(v36 + 1);
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v34 + 128), 0xFFFFFFFE) == 3 )
        {
          (*(void (__fastcall **)(__int64))(v34 + 104))(v34);
          _InterlockedAdd((volatile signed __int32 *)(v34 + 124), 0xFFFFFFFE);
        }
        if ( !v35 )
          goto LABEL_81;
        v2 = (__int64)v47;
        v27 = v48;
      }
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_TEREDO_IO,
          L"Successfully posted initial packets on Tunnel Device.");
      LastError = (*(__int64 (__fastcall **)(_QWORD))(v1 + 2848))(*(_QWORD *)(v27 + 152));
      if ( LastError )
        break;
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_TEREDO_IO,
          L"Created Primary Socket.");
      v25 = ++vInBuffer[0];
    }
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_TEREDO_IO,
        L"Failed to post initial notify call on primary socket.");
  }
  else
  {
    v12 = *(_QWORD *)(*(_QWORD *)(v1 + 2904) + 8LL * v10);
    NumaMemory = TeredoRioAllocateNumaMemory(0xC0u, *(unsigned __int16 *)(v12 + 24));
    v14 = NumaMemory;
    if ( NumaMemory )
    {
      *(_QWORD *)(*(_QWORD *)(v2 + 136) + 8LL * vInBuffer[0]) = NumaMemory;
      *(_QWORD *)NumaMemory = v2;
      *(_DWORD *)(NumaMemory + 16) = vInBuffer[0];
      v15 = WSASocketW(2, 2, 0, 0, 0, 0x100u);
      *(_QWORD *)(v14 + 8) = v15;
      if ( v15 == -1 )
      {
        LastError = GetLastError();
        EventWriteError0(0x100000, L"Create socket failed: %u", LastError);
      }
      else
      {
        LastError = TeredoEnableRealArrivalIf(v15);
        if ( !LastError )
        {
          do
          {
            v16 = *(_QWORD *)(v14 + 8);
            if ( *(_DWORD *)optval )
            {
              if ( setsockopt(v16, 0xFFFF, 12293, optval, 4) )
              {
                Error = WSAGetLastError();
                EventWriteError0(0x100000, L"setsockopt randomize failed: %u", Error);
              }
            }
            else if ( WSAIoctl(v16, 0x98000015, vInBuffer, 2u, 0, 0, &cbBytesReturned, 0, 0) )
            {
              v18 = WSAGetLastError();
              EventWriteError0(0x100000, L"setsockopt port sharing failed: %u", v18);
            }
            LODWORD(v19) = bind(*(_QWORD *)(v14 + 8), &name, 16);
            if ( (_DWORD)v19 )
            {
              v19 = (unsigned int)WSAGetLastError();
              EventWriteError0(0x100000, L"bind failed: %u", v19);
              *(_DWORD *)optval = 1;
              *(_WORD *)name.sa_data = 0;
            }
            if ( (_DWORD)v19 != -1 )
              break;
          }
          while ( v11-- );
          v1 = v48;
          v2 = (__int64)v47;
          v21 = v46;
          if ( (_DWORD)v19 )
          {
            LastError = WSAGetLastError();
          }
          else
          {
            if ( vInBuffer[0] )
              goto LABEL_27;
            WSAIoctl(*(_QWORD *)(v14 + 8), 0xC8000024, v50, 0x10u, vOutBuffer, 0x70u, &lpcbBytesReturned, 0, 0);
            if ( lpcbBytesReturned == 112 )
            {
              *(_OWORD *)(v1 + 2768) = vOutBuffer[0];
              *(_OWORD *)(v1 + 2784) = vOutBuffer[1];
              *(_OWORD *)(v1 + 2800) = vOutBuffer[2];
              *(_OWORD *)(v1 + 2816) = vOutBuffer[3];
              *(_OWORD *)(v1 + 2832) = vOutBuffer[4];
              *(_OWORD *)(v1 + 2848) = vOutBuffer[5];
              *(_OWORD *)(v1 + 2864) = vOutBuffer[6];
LABEL_27:
              v22 = TeredoRioSocketSetupHelper(v14, 0);
              LastError = v22;
              if ( v22 )
              {
                EventWriteError0(0x100000, L"TeredoRioSocketSetupHelper failed: %u", v22);
              }
              else
              {
                namelen = 16;
                if ( getsockname(*(_QWORD *)(v14 + 8), (struct sockaddr *)(v1 + 2660), &namelen) )
                {
                  LastError = WSAGetLastError();
                  EventWriteError0(0x100000, L"Failed to read socket name. Error (%d)", LastError);
                }
                else
                {
                  setsockopt(*(_QWORD *)(v14 + 8), 0, 9, (const char *)(v1 + 2664), 4);
                  *(_DWORD *)v44 = 0;
                  setsockopt(*(_QWORD *)(v14 + 8), 0, 11, v44, 4);
                  if ( !*(_DWORD *)optval && vInBuffer[0] )
                  {
                    v11 = 1;
                  }
                  else
                  {
                    v11 = 1;
                    TeredoRegisterFirewallExceptions(*(unsigned __int16 *)(v1 + 2662), 1);
                  }
                  v23 = TeredoRioAllocateNumaMemory(24 * v21, *(unsigned __int16 *)(v12 + 24));
                  *(_QWORD *)(v14 + 160) = v23;
                  if ( v23 )
                  {
                    for ( k = 0; ; ++k )
                    {
                      if ( k >= *(_DWORD *)(v12 + 16) )
                      {
                        v10 = ++vInBuffer[0];
                        goto LABEL_10;
                      }
                      *(_QWORD *)(*(_QWORD *)(v12 + 8) + 16LL * k) = (*(__int64 (__fastcall **)(_QWORD, __int64))(v1 + 2856))(
                                                                       *(_QWORD *)(*(_QWORD *)v12 + 8LL * k),
                                                                       1998);
                      if ( *(_QWORD *)(*(_QWORD *)(v12 + 8) + 16LL * k) == 0xFFFFFFFFLL )
                        break;
                    }
                    LastError = 10055;
                    EventWriteError0(0x100000, L"Failed RIORegisterBuffer. Error (%d)", 10055);
                  }
                  else
                  {
                    LastError = GetLastError();
                    EventWriteError0(0x100000, L"Failed to create Results. Error (%d)", LastError);
                  }
                }
              }
              goto LABEL_83;
            }
            LastError = 10022;
            EventWriteError0(0x100000, L"WSAIoctl failed: %u", 10022);
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      EventWriteError0(0x100000, L"TeredoRioAllocateNumaMemory for Rio socket failed: %u", LastError);
    }
  }
LABEL_83:
  EventWriteError0(0x100000, L"TeredoCreateRioPrimarySocket failed with %u", LastError);
  if ( LastError )
  {
    TeredoStopDevice(v1 + 3248);
    TeredoRioStopDevice(v47);
  }
LABEL_86:
  EventWriteLeaveEx(0x100000, L"TeredoRioCreatePrimarySockets");
  return LastError;
}

```

## disassembly

```asm
0x1800562a0  mov     r11, rsp
0x1800562a3  mov     [r11+10h], rbx
0x1800562a7  mov     [r11+18h], rsi
0x1800562ab  push    rdi
0x1800562ac  push    r12
0x1800562ae  push    r13
0x1800562b0  push    r14
0x1800562b2  push    r15
0x1800562b4  sub     rsp, 120h
0x1800562bb  mov     rax, cs:__security_cookie
0x1800562c2  xor     rax, rsp
0x1800562c5  mov     [rsp+148h+var_38], rax
0x1800562cd  mov     rdi, [rcx]
0x1800562d0  xor     ebx, ebx
0x1800562d2  mov     r12, rcx
0x1800562d5  mov     [rsp+148h+var_D8], rcx
0x1800562da  xorps   xmm0, xmm0
0x1800562dd  mov     [rsp+148h+var_D0], rdi
0x1800562e2  xor     eax, eax
0x1800562e4  mov     dword ptr [rsp+148h+optval], ebx
0x1800562e8  lea     r8d, [rbx+6Ch]; Size
0x1800562ec  mov     dword ptr [rsp+148h+var_E8], ebx
0x1800562f0  xor     edx, edx; Val
0x1800562f2  mov     [rsp+148h+namelen], ebx
0x1800562f6  lea     rcx, [r11-0C8h]; void *
0x1800562fd  mov     [rsp+148h+vInBuffer], bx
0x180056302  movups  xmmword ptr [r11-48h], xmm0
0x180056307  mov     dword ptr [rsp+148h+vOutBuffer+4], eax
0x18005630e  call    memset_0
0x180056313  lea     rdx, aTeredoriocreat_0; "TeredoRioCreatePrimarySockets"
0x18005631a  mov     [rsp+148h+var_58], 8509E081h
0x180056325  mov     ecx, 100000h
0x18005632a  mov     [rsp+148h+var_54], 400596DDh
0x180056335  mov     [rsp+148h+var_50], 2E9E65B1h
0x180056340  mov     [rsp+148h+var_4C], 3F9EC7E8h
0x18005634b  mov     [rsp+148h+var_F0], ebx
0x18005634f  mov     [rsp+148h+cbBytesReturned], ebx
0x180056353  call    EventWriteEnterEx
0x180056358  lea     rcx, [r12+90h]
0x180056360  mov     dword ptr [rcx], 2
0x180056366  call    RoReferenceEx
0x18005636b  mov     rcx, [rdi+0AC8h]
0x180056372  call    TeredoTypeServer
0x180056377  test    eax, eax
0x180056379  jnz     short loc_180056383
0x18005637b  lea     ebx, [rax+32h]
0x18005637e  jmp     loc_180056BBD
0x180056383  mov     esi, [rdi+0B54h]
0x180056389  xor     r9d, r9d; lpName
0x18005638c  mov     r14d, [rdi+0B50h]
0x180056393  xor     r8d, r8d; bInitialState
0x180056396  mov     r15d, [rdi+0B4Ch]
0x18005639d  xor     ecx, ecx; lpEventAttributes
0x18005639f  lea     edx, [r9+1]; bManualReset
0x1800563a3  call    cs:__imp_CreateEventW
0x1800563aa  nop     dword ptr [rax+rax+00h]
0x1800563af  mov     [r12+98h], rax
0x1800563b7  test    rax, rax
0x1800563ba  jnz     short loc_1800563D6
0x1800563bc  call    cs:__imp_GetLastError
0x1800563c3  nop     dword ptr [rax+rax+00h]
0x1800563c8  mov     ebx, eax
0x1800563ca  lea     rdx, aCreateeventFor; "CreateEvent for Teredo device failed: %"...
0x1800563d1  jmp     loc_180056BB0
0x1800563d6  movups  xmm0, xmmword ptr [rdi+0A64h]
0x1800563dd  movq    r8, xmm0
0x1800563e2  mov     rdx, r8
0x1800563e5  shr     r8, 10h
0x1800563e9  movups  xmmword ptr [rsp+148h+name.sa_family], xmm0
0x1800563f1  mov     rcx, [rdi+0CC8h]
0x1800563f8  shr     rdx, 20h
0x1800563fc  call    TeredoOffloadV4FlowParams
0x180056401  mov     ebx, eax
0x180056403  test    eax, eax
0x180056405  jz      short loc_180056413
0x180056407  lea     rdx, aTeredooffloadv; "TeredoOffloadV4FlowParams failed: %u"
0x18005640e  jmp     loc_180056BB0
0x180056413  mov     r8d, [rdi+0B44h]
0x18005641a  mov     ebx, 8
0x18005641f  mov     rcx, [rdi+0A10h]; hHeap
0x180056426  mov     edx, ebx; dwFlags
0x180056428  shl     r8, 3; dwBytes
0x18005642c  call    cs:__imp_HeapAlloc
0x180056433  nop     dword ptr [rax+rax+00h]
0x180056438  mov     [r12+88h], rax
0x180056440  test    rax, rax
0x180056443  jnz     short loc_180056454
0x180056445  mov     r8d, ebx
0x180056448  lea     rdx, aHeapallocForRi; "HeapAlloc for Rio socket pointers faile"...
0x18005644f  jmp     loc_180056BB3
0x180056454  lea     r13d, [r15+r14]
0x180056458  add     r13d, esi
0x18005645b  xor     ebx, ebx
0x18005645d  mov     [rsp+148h+var_E0], r13d
0x180056462  mov     [rsp+148h+vInBuffer], bx
0x180056467  mov     ecx, ebx
0x180056469  lea     r14d, [rbx+1]
0x18005646d  movzx   eax, cx
0x180056470  cmp     eax, [rdi+0B44h]
0x180056476  jnb     loc_1800568EA
0x18005647c  mov     rax, [rdi+0B58h]
0x180056483  movzx   ecx, cx
0x180056486  mov     r15, [rax+rcx*8]
0x18005648a  mov     ecx, 0C0h; Size
0x18005648f  movzx   edx, word ptr [r15+18h]; nndPreferred
0x180056494  call    TeredoRioAllocateNumaMemory
0x180056499  mov     rsi, rax
0x18005649c  test    rax, rax
0x18005649f  jz      loc_1800568D0
0x1800564a5  movzx   edx, [rsp+148h+vInBuffer]
0x1800564aa  xor     r9d, r9d; lpProtocolInfo
0x1800564ad  mov     rcx, [r12+88h]
0x1800564b5  xor     r8d, r8d; protocol
0x1800564b8  mov     [rsp+148h+dwFlags], 100h; dwFlags
0x1800564c0  mov     [rsp+148h+g], ebx; g
0x1800564c4  mov     [rcx+rdx*8], rax
0x1800564c8  mov     [rax], r12
0x1800564cb  movzx   ecx, [rsp+148h+vInBuffer]
0x1800564d0  mov     [rax+10h], ecx
0x1800564d3  lea     eax, [r9+2]
0x1800564d7  mov     edx, eax; type
0x1800564d9  mov     ecx, eax; af
0x1800564db  call    cs:__imp_WSASocketW
0x1800564e2  nop     dword ptr [rax+rax+00h]
0x1800564e7  mov     [rsi+8], rax
0x1800564eb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800564ef  jz      loc_1800568B6
0x1800564f5  mov     rcx, rax
0x1800564f8  call    TeredoEnableRealArrivalIf
0x1800564fd  mov     ebx, eax
0x1800564ff  test    eax, eax
0x180056501  jnz     loc_180056BBD
0x180056507  xor     r12d, r12d
0x18005650a  lea     r13d, [rax+1]
0x18005650e  mov     edi, 0FFFFFFFFh
0x180056513  mov     rcx, [rsi+8]; s
0x180056517  cmp     dword ptr [rsp+148h+optval], r12d
0x18005651c  jz      short loc_18005655B
0x18005651e  lea     r9, [rsp+148h+optval]; optval
0x180056523  mov     [rsp+148h+g], 4; optlen
0x18005652b  mov     edx, 0FFFFh; level
0x180056530  mov     r8d, 3005h; optname
0x180056536  call    cs:__imp_setsockopt
0x18005653d  nop     dword ptr [rax+rax+00h]
0x180056542  test    eax, eax
0x180056544  jz      short loc_1800565B9
0x180056546  call    cs:__imp_WSAGetLastError
0x18005654d  nop     dword ptr [rax+rax+00h]
0x180056552  lea     rdx, aSetsockoptRand; "setsockopt randomize failed: %u"
0x180056559  jmp     short loc_1800565AC
0x18005655b  mov     [rsp+148h+lpCompletionRoutine], r12; lpCompletionRoutine
0x180056560  lea     rax, [rsp+148h+cbBytesReturned]
0x180056565  mov     [rsp+148h+lpOverlapped], r12; lpOverlapped
0x18005656a  lea     r8, [rsp+148h+vInBuffer]; lpvInBuffer
0x18005656f  mov     [rsp+148h+lpcbBytesReturned], rax; lpcbBytesReturned
0x180056574  mov     r9d, 2; cbInBuffer
0x18005657a  mov     [rsp+148h+dwFlags], r12d; cbOutBuffer
0x18005657f  mov     edx, 98000015h; dwIoControlCode
0x180056584  mov     qword ptr [rsp+148h+g], r12; lpvOutBuffer
0x180056589  call    cs:__imp_WSAIoctl
0x180056590  nop     dword ptr [rax+rax+00h]
0x180056595  test    eax, eax
0x180056597  jz      short loc_1800565B9
0x180056599  call    cs:__imp_WSAGetLastError
0x1800565a0  nop     dword ptr [rax+rax+00h]
0x1800565a5  lea     rdx, aSetsockoptPort; "setsockopt port sharing failed: %u"
0x1800565ac  mov     r8d, eax
0x1800565af  mov     ecx, 100000h
0x1800565b4  call    EventWriteError0
0x1800565b9  mov     rcx, [rsi+8]; s
0x1800565bd  lea     rdx, [rsp+148h+name]; name
0x1800565c5  mov     r8d, 10h; namelen
0x1800565cb  call    cs:__imp_bind
0x1800565d2  nop     dword ptr [rax+rax+00h]
0x1800565d7  mov     ebx, eax
0x1800565d9  test    eax, eax
0x1800565db  jz      short loc_18005660D
0x1800565dd  call    cs:__imp_WSAGetLastError
0x1800565e4  nop     dword ptr [rax+rax+00h]
0x1800565e9  lea     rdx, aBindFailedU; "bind failed: %u"
0x1800565f0  mov     ecx, 100000h
0x1800565f5  mov     r8d, eax
0x1800565f8  mov     ebx, eax
0x1800565fa  call    EventWriteError0
0x1800565ff  mov     dword ptr [rsp+148h+optval], r13d
0x180056604  mov     word ptr [rsp+148h+name.sa_data], r12w
0x18005660d  cmp     ebx, edi
0x18005660f  jnz     short loc_18005661F
0x180056611  mov     eax, r14d
0x180056614  sub     r14d, r13d
0x180056617  test    eax, eax
0x180056619  jnz     loc_180056513
0x18005661f  mov     rdi, [rsp+148h+var_D0]
0x180056624  mov     r12, [rsp+148h+var_D8]
0x180056629  mov     r13d, [rsp+148h+var_E0]
0x18005662e  test    ebx, ebx
0x180056630  jnz     loc_1800568A3
0x180056636  xor     eax, eax
0x180056638  cmp     [rsp+148h+vInBuffer], ax
0x18005663d  jnz     loc_180056703
0x180056643  mov     rcx, [rsi+8]; s
0x180056647  lea     r8, [rsp+148h+var_58]; lpvInBuffer
0x18005664f  mov     [rsp+148h+lpCompletionRoutine], rax; lpCompletionRoutine
0x180056654  mov     r9d, 10h; cbInBuffer
0x18005665a  mov     [rsp+148h+lpOverlapped], rax; lpOverlapped
0x18005665f  mov     edx, 0C8000024h; dwIoControlCode
0x180056664  lea     rax, [rsp+148h+var_F0]
0x180056669  mov     [rsp+148h+lpcbBytesReturned], rax; lpcbBytesReturned
0x18005666e  lea     rax, [rsp+148h+vOutBuffer]
0x180056676  mov     [rsp+148h+dwFlags], 70h ; 'p'; cbOutBuffer
0x18005667e  mov     qword ptr [rsp+148h+g], rax; lpvOutBuffer
0x180056683  call    cs:__imp_WSAIoctl
0x18005668a  nop     dword ptr [rax+rax+00h]
0x18005668f  cmp     [rsp+148h+var_F0], 70h ; 'p'
0x180056694  jnz     loc_18005683B
0x18005669a  movaps  xmm0, [rsp+148h+vOutBuffer]
0x1800566a2  movups  xmmword ptr [rdi+0AD0h], xmm0
0x1800566a9  movaps  xmm1, [rsp+148h+var_B8]
0x1800566b1  movups  xmmword ptr [rdi+0AE0h], xmm1
0x1800566b8  movaps  xmm0, [rsp+148h+var_A8]
0x1800566c0  movups  xmmword ptr [rdi+0AF0h], xmm0
0x1800566c7  movaps  xmm1, [rsp+148h+var_98]
0x1800566cf  movups  xmmword ptr [rdi+0B00h], xmm1
0x1800566d6  movaps  xmm0, [rsp+148h+var_88]
0x1800566de  movups  xmmword ptr [rdi+0B10h], xmm0
0x1800566e5  movaps  xmm1, [rsp+148h+var_78]
0x1800566ed  movups  xmmword ptr [rdi+0B20h], xmm1
0x1800566f4  movaps  xmm0, [rsp+148h+var_68]
0x1800566fc  movups  xmmword ptr [rdi+0B30h], xmm0
0x180056703  xor     edx, edx
0x180056705  mov     rcx, rsi
0x180056708  call    TeredoRioSocketSetupHelper
0x18005670d  mov     ebx, eax
0x18005670f  test    eax, eax
0x180056711  jnz     loc_180056897
0x180056717  mov     [rsp+148h+namelen], 10h
0x18005671f  lea     r8, [rsp+148h+namelen]; namelen
0x180056724  mov     rcx, [rsi+8]; s
0x180056728  lea     rdx, [rdi+0A64h]; name
0x18005672f  call    cs:__imp_getsockname
0x180056736  nop     dword ptr [rax+rax+00h]
0x18005673b  xor     ebx, ebx
0x18005673d  test    eax, eax
0x18005673f  jnz     loc_18005687D
0x180056745  mov     rcx, [rsi+8]; s
0x180056749  lea     r14d, [rbx+4]
0x18005674d  lea     r9, [rdi+0A68h]; optval
0x180056754  mov     [rsp+148h+g], r14d; optlen
0x180056759  xor     edx, edx; level
0x18005675b  lea     r8d, [rbx+9]; optname
0x18005675f  call    cs:__imp_setsockopt
0x180056766  nop     dword ptr [rax+rax+00h]
0x18005676b  mov     dword ptr [rsp+148h+var_E8], ebx
0x18005676f  lea     r9, [rsp+148h+var_E8]; optval
0x180056774  mov     rcx, [rsi+8]; s
0x180056778  lea     r8d, [rbx+0Bh]; optname
0x18005677c  xor     edx, edx; level
0x18005677e  mov     [rsp+148h+g], r14d; optlen
0x180056783  call    cs:__imp_setsockopt
0x18005678a  nop     dword ptr [rax+rax+00h]
0x18005678f  cmp     dword ptr [rsp+148h+optval], ebx
0x180056793  jnz     short loc_18005679C
0x180056795  cmp     [rsp+148h+vInBuffer], bx
0x18005679a  jnz     short loc_1800567B3
0x18005679c  movzx   ecx, word ptr [rdi+0A66h]
0x1800567a3  mov     r14d, 1
0x1800567a9  mov     edx, r14d
0x1800567ac  call    TeredoRegisterFirewallExceptions
0x1800567b1  jmp     short loc_1800567B9
0x1800567b3  mov     r14d, 1
0x1800567b9  movzx   edx, word ptr [r15+18h]; nndPreferred
0x1800567be  lea     rcx, ds:0[r13*2]
0x1800567c6  add     rcx, r13
0x1800567c9  shl     rcx, 3; Size
0x1800567cd  call    TeredoRioAllocateNumaMemory
0x1800567d2  mov     [rsi+0A0h], rax
0x1800567d9  test    rax, rax
0x1800567dc  jz      loc_180056863
0x1800567e2  mov     esi, ebx
0x1800567e4  cmp     esi, [r15+10h]
0x1800567e8  jnb     short loc_180056823
0x1800567ea  mov     rcx, [r15]
0x1800567ed  mov     edx, 7CEh
0x1800567f2  mov     rax, [rdi+0B28h]
0x1800567f9  mov     ebx, esi
0x1800567fb  mov     rcx, [rcx+rbx*8]
0x1800567ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056804  mov     rcx, [r15+8]
0x180056808  add     rbx, rbx
0x18005680b  mov     [rcx+rbx*8], rax
0x18005680f  mov     ecx, 0FFFFFFFFh
0x180056814  mov     rax, [r15+8]
0x180056818  cmp     [rax+rbx*8], rcx
0x18005681c  jz      short loc_18005684F
0x18005681e  add     esi, r14d
0x180056821  jmp     short loc_1800567E4
0x180056823  movzx   eax, [rsp+148h+vInBuffer]
0x180056828  add     ax, r14w
0x18005682c  mov     [rsp+148h+vInBuffer], ax
0x180056831  movzx   ecx, ax
  ... truncated ...
```
