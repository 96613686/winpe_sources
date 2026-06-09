# TeredoRioCreatePrimarySockets

- ea: `0x180056280`
- end: `0x180056c10`
- name: `TeredoRioCreatePrimarySockets`
- size: `2448`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800589d8`

## callees

- `0x180008200`
- `0x180009000`
- `0x1800159c4`
- `0x180016488`
- `0x1800190e0`
- `0x18001caa8`
- `0x18001caf0`
- `0x18001de64`
- `0x18001edb8`
- `0x18001f1c0`
- `0x180024240`
- `0x180041494`
- `0x18004b630`
- `0x18004c1c8`
- `0x180055f2c`
- `0x180056280`
- `0x180057190`
- `0x180057b24`
- `0x180058824`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005640c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005640c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056383`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056383`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005639c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800568b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005639c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800568b0`
- `WS2_32!WSASocketW` at `0x1800564bb`
- `WS2_32!WSASocketW` at `0x1800564bb`
- `WS2_32!WSAIoctl` at `0x180056569`
- `WS2_32!WSAIoctl` at `0x180056663`
- `WS2_32!WSAIoctl` at `0x180056569`
- `WS2_32!WSAIoctl` at `0x180056663`
- `WS2_32!__imp_bind` at `0x1800565ab`
- `WS2_32!__imp_bind` at `0x1800565ab`
- `WS2_32!__imp_getsockname` at `0x18005670f`
- `WS2_32!__imp_getsockname` at `0x18005670f`
- `WS2_32!__imp_setsockopt` at `0x180056516`
- `WS2_32!__imp_setsockopt` at `0x18005673f`
- `WS2_32!__imp_setsockopt` at `0x180056763`
- `WS2_32!__imp_setsockopt` at `0x180056516`
- `WS2_32!__imp_setsockopt` at `0x18005673f`
- `WS2_32!__imp_setsockopt` at `0x180056763`
- `WS2_32!__imp_WSAGetLastError` at `0x180056526`
- `WS2_32!__imp_WSAGetLastError` at `0x180056579`
- `WS2_32!__imp_WSAGetLastError` at `0x1800565bd`
- `WS2_32!__imp_WSAGetLastError` at `0x18005685d`
- `WS2_32!__imp_WSAGetLastError` at `0x180056883`
- `WS2_32!__imp_WSAGetLastError` at `0x180056526`
- `WS2_32!__imp_WSAGetLastError` at `0x180056579`
- `WS2_32!__imp_WSAGetLastError` at `0x1800565bd`
- `WS2_32!__imp_WSAGetLastError` at `0x18005685d`
- `WS2_32!__imp_WSAGetLastError` at `0x180056883`

## string_xrefs

- `0x1800568a4`: `Create socket failed: %u`
- `0x18005686b`: `Failed to read socket name. Error (%d)`
- `0x180056b2a`: `Created Primary Socket.`
- `0x180056851`: `Failed to create Results. Error (%d)`
- `0x180056b89`: `Failed TeredoRioCreateWorkerThreads. Error (%d)`
- `0x1800562f3`: `TeredoRioCreatePrimarySockets`
- `0x180056bcf`: `TeredoRioCreatePrimarySockets`
- `0x1800563aa`: `CreateEvent for Teredo device failed: %u`
- `0x180056ba0`: `TeredoCreateRioPrimarySocket failed with %u`

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
0x180056280  mov     r11, rsp
0x180056283  mov     [r11+10h], rbx
0x180056287  mov     [r11+18h], rsi
0x18005628b  push    rdi
0x18005628c  push    r12
0x18005628e  push    r13
0x180056290  push    r14
0x180056292  push    r15
0x180056294  sub     rsp, 120h
0x18005629b  mov     rax, cs:__security_cookie
0x1800562a2  xor     rax, rsp
0x1800562a5  mov     [rsp+148h+var_38], rax
0x1800562ad  mov     rdi, [rcx]
0x1800562b0  xor     ebx, ebx
0x1800562b2  mov     r12, rcx
0x1800562b5  mov     [rsp+148h+var_D8], rcx
0x1800562ba  xorps   xmm0, xmm0
0x1800562bd  mov     [rsp+148h+var_D0], rdi
0x1800562c2  xor     eax, eax
0x1800562c4  mov     dword ptr [rsp+148h+optval], ebx
0x1800562c8  lea     r8d, [rbx+6Ch]; Size
0x1800562cc  mov     dword ptr [rsp+148h+var_E8], ebx
0x1800562d0  xor     edx, edx; Val
0x1800562d2  mov     [rsp+148h+namelen], ebx
0x1800562d6  lea     rcx, [r11-0C8h]; void *
0x1800562dd  mov     [rsp+148h+vInBuffer], bx
0x1800562e2  movups  xmmword ptr [r11-48h], xmm0
0x1800562e7  mov     dword ptr [rsp+148h+vOutBuffer+4], eax
0x1800562ee  call    memset_0
0x1800562f3  lea     rdx, aTeredoriocreat_0; "TeredoRioCreatePrimarySockets"
0x1800562fa  mov     [rsp+148h+var_58], 8509E081h
0x180056305  mov     ecx, 100000h
0x18005630a  mov     [rsp+148h+var_54], 400596DDh
0x180056315  mov     [rsp+148h+var_50], 2E9E65B1h
0x180056320  mov     [rsp+148h+var_4C], 3F9EC7E8h
0x18005632b  mov     [rsp+148h+var_F0], ebx
0x18005632f  mov     [rsp+148h+cbBytesReturned], ebx
0x180056333  call    EventWriteEnterEx
0x180056338  lea     rcx, [r12+90h]
0x180056340  mov     dword ptr [rcx], 2
0x180056346  call    RoReferenceEx
0x18005634b  mov     rcx, [rdi+0AC8h]
0x180056352  call    TeredoTypeServer
0x180056357  test    eax, eax
0x180056359  jnz     short loc_180056363
0x18005635b  lea     ebx, [rax+32h]
0x18005635e  jmp     loc_180056B9D
0x180056363  mov     esi, [rdi+0B54h]
0x180056369  xor     r9d, r9d; lpName
0x18005636c  mov     r14d, [rdi+0B50h]
0x180056373  xor     r8d, r8d; bInitialState
0x180056376  mov     r15d, [rdi+0B4Ch]
0x18005637d  xor     ecx, ecx; lpEventAttributes
0x18005637f  lea     edx, [r9+1]; bManualReset
0x180056383  call    cs:__imp_CreateEventW
0x18005638a  nop     dword ptr [rax+rax+00h]
0x18005638f  mov     [r12+98h], rax
0x180056397  test    rax, rax
0x18005639a  jnz     short loc_1800563B6
0x18005639c  call    cs:__imp_GetLastError
0x1800563a3  nop     dword ptr [rax+rax+00h]
0x1800563a8  mov     ebx, eax
0x1800563aa  lea     rdx, aCreateeventFor; "CreateEvent for Teredo device failed: %"...
0x1800563b1  jmp     loc_180056B90
0x1800563b6  movups  xmm0, xmmword ptr [rdi+0A64h]
0x1800563bd  movq    r8, xmm0
0x1800563c2  mov     rdx, r8
0x1800563c5  shr     r8, 10h
0x1800563c9  movups  xmmword ptr [rsp+148h+name.sa_family], xmm0
0x1800563d1  mov     rcx, [rdi+0CC8h]
0x1800563d8  shr     rdx, 20h
0x1800563dc  call    TeredoOffloadV4FlowParams
0x1800563e1  mov     ebx, eax
0x1800563e3  test    eax, eax
0x1800563e5  jz      short loc_1800563F3
0x1800563e7  lea     rdx, aTeredooffloadv; "TeredoOffloadV4FlowParams failed: %u"
0x1800563ee  jmp     loc_180056B90
0x1800563f3  mov     r8d, [rdi+0B44h]
0x1800563fa  mov     ebx, 8
0x1800563ff  mov     rcx, [rdi+0A10h]; hHeap
0x180056406  mov     edx, ebx; dwFlags
0x180056408  shl     r8, 3; dwBytes
0x18005640c  call    cs:__imp_HeapAlloc
0x180056413  nop     dword ptr [rax+rax+00h]
0x180056418  mov     [r12+88h], rax
0x180056420  test    rax, rax
0x180056423  jnz     short loc_180056434
0x180056425  mov     r8d, ebx
0x180056428  lea     rdx, aHeapallocForRi; "HeapAlloc for Rio socket pointers faile"...
0x18005642f  jmp     loc_180056B93
0x180056434  lea     r13d, [r15+r14]
0x180056438  add     r13d, esi
0x18005643b  xor     ebx, ebx
0x18005643d  mov     [rsp+148h+var_E0], r13d
0x180056442  mov     [rsp+148h+vInBuffer], bx
0x180056447  mov     ecx, ebx
0x180056449  lea     r14d, [rbx+1]
0x18005644d  movzx   eax, cx
0x180056450  cmp     eax, [rdi+0B44h]
0x180056456  jnb     loc_1800568CA
0x18005645c  mov     rax, [rdi+0B58h]
0x180056463  movzx   ecx, cx
0x180056466  mov     r15, [rax+rcx*8]
0x18005646a  mov     ecx, 0C0h; Size
0x18005646f  movzx   edx, word ptr [r15+18h]; nndPreferred
0x180056474  call    TeredoRioAllocateNumaMemory
0x180056479  mov     rsi, rax
0x18005647c  test    rax, rax
0x18005647f  jz      loc_1800568B0
0x180056485  movzx   edx, [rsp+148h+vInBuffer]
0x18005648a  xor     r9d, r9d; lpProtocolInfo
0x18005648d  mov     rcx, [r12+88h]
0x180056495  xor     r8d, r8d; protocol
0x180056498  mov     [rsp+148h+dwFlags], 100h; dwFlags
0x1800564a0  mov     [rsp+148h+g], ebx; g
0x1800564a4  mov     [rcx+rdx*8], rax
0x1800564a8  mov     [rax], r12
0x1800564ab  movzx   ecx, [rsp+148h+vInBuffer]
0x1800564b0  mov     [rax+10h], ecx
0x1800564b3  lea     eax, [r9+2]
0x1800564b7  mov     edx, eax; type
0x1800564b9  mov     ecx, eax; af
0x1800564bb  call    cs:__imp_WSASocketW
0x1800564c2  nop     dword ptr [rax+rax+00h]
0x1800564c7  mov     [rsi+8], rax
0x1800564cb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800564cf  jz      loc_180056896
0x1800564d5  mov     rcx, rax
0x1800564d8  call    TeredoEnableRealArrivalIf
0x1800564dd  mov     ebx, eax
0x1800564df  test    eax, eax
0x1800564e1  jnz     loc_180056B9D
0x1800564e7  xor     r12d, r12d
0x1800564ea  lea     r13d, [rax+1]
0x1800564ee  mov     edi, 0FFFFFFFFh
0x1800564f3  mov     rcx, [rsi+8]; s
0x1800564f7  cmp     dword ptr [rsp+148h+optval], r12d
0x1800564fc  jz      short loc_18005653B
0x1800564fe  lea     r9, [rsp+148h+optval]; optval
0x180056503  mov     [rsp+148h+g], 4; optlen
0x18005650b  mov     edx, 0FFFFh; level
0x180056510  mov     r8d, 3005h; optname
0x180056516  call    cs:__imp_setsockopt
0x18005651d  nop     dword ptr [rax+rax+00h]
0x180056522  test    eax, eax
0x180056524  jz      short loc_180056599
0x180056526  call    cs:__imp_WSAGetLastError
0x18005652d  nop     dword ptr [rax+rax+00h]
0x180056532  lea     rdx, aSetsockoptRand; "setsockopt randomize failed: %u"
0x180056539  jmp     short loc_18005658C
0x18005653b  mov     [rsp+148h+lpCompletionRoutine], r12; lpCompletionRoutine
0x180056540  lea     rax, [rsp+148h+cbBytesReturned]
0x180056545  mov     [rsp+148h+lpOverlapped], r12; lpOverlapped
0x18005654a  lea     r8, [rsp+148h+vInBuffer]; lpvInBuffer
0x18005654f  mov     [rsp+148h+lpcbBytesReturned], rax; lpcbBytesReturned
0x180056554  mov     r9d, 2; cbInBuffer
0x18005655a  mov     [rsp+148h+dwFlags], r12d; cbOutBuffer
0x18005655f  mov     edx, 98000015h; dwIoControlCode
0x180056564  mov     qword ptr [rsp+148h+g], r12; lpvOutBuffer
0x180056569  call    cs:__imp_WSAIoctl
0x180056570  nop     dword ptr [rax+rax+00h]
0x180056575  test    eax, eax
0x180056577  jz      short loc_180056599
0x180056579  call    cs:__imp_WSAGetLastError
0x180056580  nop     dword ptr [rax+rax+00h]
0x180056585  lea     rdx, aSetsockoptPort; "setsockopt port sharing failed: %u"
0x18005658c  mov     r8d, eax
0x18005658f  mov     ecx, 100000h
0x180056594  call    EventWriteError0
0x180056599  mov     rcx, [rsi+8]; s
0x18005659d  lea     rdx, [rsp+148h+name]; name
0x1800565a5  mov     r8d, 10h; namelen
0x1800565ab  call    cs:__imp_bind
0x1800565b2  nop     dword ptr [rax+rax+00h]
0x1800565b7  mov     ebx, eax
0x1800565b9  test    eax, eax
0x1800565bb  jz      short loc_1800565ED
0x1800565bd  call    cs:__imp_WSAGetLastError
0x1800565c4  nop     dword ptr [rax+rax+00h]
0x1800565c9  lea     rdx, aBindFailedU; "bind failed: %u"
0x1800565d0  mov     ecx, 100000h
0x1800565d5  mov     r8d, eax
0x1800565d8  mov     ebx, eax
0x1800565da  call    EventWriteError0
0x1800565df  mov     dword ptr [rsp+148h+optval], r13d
0x1800565e4  mov     word ptr [rsp+148h+name.sa_data], r12w
0x1800565ed  cmp     ebx, edi
0x1800565ef  jnz     short loc_1800565FF
0x1800565f1  mov     eax, r14d
0x1800565f4  sub     r14d, r13d
0x1800565f7  test    eax, eax
0x1800565f9  jnz     loc_1800564F3
0x1800565ff  mov     rdi, [rsp+148h+var_D0]
0x180056604  mov     r12, [rsp+148h+var_D8]
0x180056609  mov     r13d, [rsp+148h+var_E0]
0x18005660e  test    ebx, ebx
0x180056610  jnz     loc_180056883
0x180056616  xor     eax, eax
0x180056618  cmp     [rsp+148h+vInBuffer], ax
0x18005661d  jnz     loc_1800566E3
0x180056623  mov     rcx, [rsi+8]; s
0x180056627  lea     r8, [rsp+148h+var_58]; lpvInBuffer
0x18005662f  mov     [rsp+148h+lpCompletionRoutine], rax; lpCompletionRoutine
0x180056634  mov     r9d, 10h; cbInBuffer
0x18005663a  mov     [rsp+148h+lpOverlapped], rax; lpOverlapped
0x18005663f  mov     edx, 0C8000024h; dwIoControlCode
0x180056644  lea     rax, [rsp+148h+var_F0]
0x180056649  mov     [rsp+148h+lpcbBytesReturned], rax; lpcbBytesReturned
0x18005664e  lea     rax, [rsp+148h+vOutBuffer]
0x180056656  mov     [rsp+148h+dwFlags], 70h ; 'p'; cbOutBuffer
0x18005665e  mov     qword ptr [rsp+148h+g], rax; lpvOutBuffer
0x180056663  call    cs:__imp_WSAIoctl
0x18005666a  nop     dword ptr [rax+rax+00h]
0x18005666f  cmp     [rsp+148h+var_F0], 70h ; 'p'
0x180056674  jnz     loc_18005681B
0x18005667a  movaps  xmm0, [rsp+148h+vOutBuffer]
0x180056682  movups  xmmword ptr [rdi+0AD0h], xmm0
0x180056689  movaps  xmm1, [rsp+148h+var_B8]
0x180056691  movups  xmmword ptr [rdi+0AE0h], xmm1
0x180056698  movaps  xmm0, [rsp+148h+var_A8]
0x1800566a0  movups  xmmword ptr [rdi+0AF0h], xmm0
0x1800566a7  movaps  xmm1, [rsp+148h+var_98]
0x1800566af  movups  xmmword ptr [rdi+0B00h], xmm1
0x1800566b6  movaps  xmm0, [rsp+148h+var_88]
0x1800566be  movups  xmmword ptr [rdi+0B10h], xmm0
0x1800566c5  movaps  xmm1, [rsp+148h+var_78]
0x1800566cd  movups  xmmword ptr [rdi+0B20h], xmm1
0x1800566d4  movaps  xmm0, [rsp+148h+var_68]
0x1800566dc  movups  xmmword ptr [rdi+0B30h], xmm0
0x1800566e3  xor     edx, edx
0x1800566e5  mov     rcx, rsi
0x1800566e8  call    TeredoRioSocketSetupHelper
0x1800566ed  mov     ebx, eax
0x1800566ef  test    eax, eax
0x1800566f1  jnz     loc_180056877
0x1800566f7  mov     [rsp+148h+namelen], 10h
0x1800566ff  lea     r8, [rsp+148h+namelen]; namelen
0x180056704  mov     rcx, [rsi+8]; s
0x180056708  lea     rdx, [rdi+0A64h]; name
0x18005670f  call    cs:__imp_getsockname
0x180056716  nop     dword ptr [rax+rax+00h]
0x18005671b  xor     ebx, ebx
0x18005671d  test    eax, eax
0x18005671f  jnz     loc_18005685D
0x180056725  mov     rcx, [rsi+8]; s
0x180056729  lea     r14d, [rbx+4]
0x18005672d  lea     r9, [rdi+0A68h]; optval
0x180056734  mov     [rsp+148h+g], r14d; optlen
0x180056739  xor     edx, edx; level
0x18005673b  lea     r8d, [rbx+9]; optname
0x18005673f  call    cs:__imp_setsockopt
0x180056746  nop     dword ptr [rax+rax+00h]
0x18005674b  mov     dword ptr [rsp+148h+var_E8], ebx
0x18005674f  lea     r9, [rsp+148h+var_E8]; optval
0x180056754  mov     rcx, [rsi+8]; s
0x180056758  lea     r8d, [rbx+0Bh]; optname
0x18005675c  xor     edx, edx; level
0x18005675e  mov     [rsp+148h+g], r14d; optlen
0x180056763  call    cs:__imp_setsockopt
0x18005676a  nop     dword ptr [rax+rax+00h]
0x18005676f  cmp     dword ptr [rsp+148h+optval], ebx
0x180056773  jnz     short loc_18005677C
0x180056775  cmp     [rsp+148h+vInBuffer], bx
0x18005677a  jnz     short loc_180056793
0x18005677c  movzx   ecx, word ptr [rdi+0A66h]
0x180056783  mov     r14d, 1
0x180056789  mov     edx, r14d
0x18005678c  call    TeredoRegisterFirewallExceptions
0x180056791  jmp     short loc_180056799
0x180056793  mov     r14d, 1
0x180056799  movzx   edx, word ptr [r15+18h]; nndPreferred
0x18005679e  lea     rcx, ds:0[r13*2]
0x1800567a6  add     rcx, r13
0x1800567a9  shl     rcx, 3; Size
0x1800567ad  call    TeredoRioAllocateNumaMemory
0x1800567b2  mov     [rsi+0A0h], rax
0x1800567b9  test    rax, rax
0x1800567bc  jz      loc_180056843
0x1800567c2  mov     esi, ebx
0x1800567c4  cmp     esi, [r15+10h]
0x1800567c8  jnb     short loc_180056803
0x1800567ca  mov     rcx, [r15]
0x1800567cd  mov     edx, 7CEh
0x1800567d2  mov     rax, [rdi+0B28h]
0x1800567d9  mov     ebx, esi
0x1800567db  mov     rcx, [rcx+rbx*8]
0x1800567df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800567e4  mov     rcx, [r15+8]
0x1800567e8  add     rbx, rbx
0x1800567eb  mov     [rcx+rbx*8], rax
0x1800567ef  mov     ecx, 0FFFFFFFFh
0x1800567f4  mov     rax, [r15+8]
0x1800567f8  cmp     [rax+rbx*8], rcx
0x1800567fc  jz      short loc_18005682F
0x1800567fe  add     esi, r14d
0x180056801  jmp     short loc_1800567C4
0x180056803  movzx   eax, [rsp+148h+vInBuffer]
0x180056808  add     ax, r14w
0x18005680c  mov     [rsp+148h+vInBuffer], ax
0x180056811  movzx   ecx, ax
  ... truncated ...
```
