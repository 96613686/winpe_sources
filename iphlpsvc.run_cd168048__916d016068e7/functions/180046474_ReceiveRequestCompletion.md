# ReceiveRequestCompletion

- ea: `0x180046474`
- end: `0x180046c7b`
- name: `ReceiveRequestCompletion`
- size: `2055`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180064a20`

## callees

- `0x180004c54`
- `0x18000d7b0`
- `0x180012dbc`
- `0x1800159c4`
- `0x180040dd0`
- `0x180046474`
- `0x180046c84`
- `0x180049730`
- `0x18004b630`
- `0x18004c1c8`
- `0x180061694`
- `0x18006478c`
- `0x180066128`
- `0x1800667f8`
- `0x180082084`

## import_xrefs

- `ntdll!RtlIpv4AddressToStringW` at `0x18004692b`
- `ntdll!RtlIpv4AddressToStringW` at `0x18004692b`
- `ntdll!RtlIpv6AddressToStringW` at `0x18004693e`
- `ntdll!RtlIpv6AddressToStringW` at `0x18004693e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800469e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800469e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046a18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046a18`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18004661c`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18004685b`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180046b2c`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18004661c`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18004685b`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180046b2c`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800465a6`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800467bc`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180046abd`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800465a6`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800467bc`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180046abd`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x1800465e8`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x1800467f7`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x1800465e8`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x1800467f7`
- `HTTPAPI!HttpReceiveClientCertificate` at `0x180046af9`
- `HTTPAPI!HttpReceiveClientCertificate` at `0x180046af9`

## string_xrefs

- `0x18004654b`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x18004662b`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180046694`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180046731`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x18004677b`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x1800467af`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180046a6e`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180046c07`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180046bb1`: `%s: ReceiveRequestCompletion: %d.`

## pseudocode

```c
__int64 __fastcall ReceiveRequestCompletion(unsigned int a1, SIZE_T a2, __int64 a3)
{
  __int64 v5; // rax
  __int64 v6; // rsi
  _QWORD *v7; // r15
  volatile signed __int32 *v8; // r12
  PTP_IO *v9; // rbp
  __int64 v10; // r13
  _QWORD *v11; // rbx
  SIZE_T v12; // rcx
  __int64 v13; // rax
  int v14; // ecx
  int v15; // ecx
  ULONG v16; // eax
  int v17; // ecx
  char *v18; // rbx
  __int64 v19; // rdi
  unsigned int v20; // ebx
  _WORD *v21; // rdx
  int v22; // ecx
  PTP_IO *v23; // r15
  volatile signed __int32 *v24; // rdi
  ULONG v25; // eax
  unsigned int v26; // ebx
  _QWORD *v27; // r12
  int v28; // ecx
  char *v29; // rax
  int v30; // ecx
  WCHAR *v31; // rdx
  int v32; // ecx
  _QWORD *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // r8
  char *v36; // rax
  int v37; // ecx
  char *v38; // rbp
  HTTP_CONNECTION_ID v39; // rdi
  ULONG v40; // eax
  __int64 (__fastcall *v41)(); // rax
  __int64 v42; // rcx
  int v43; // ecx
  PULONG BytesReturned; // [rsp+28h] [rbp-180h]
  _QWORD *v46; // [rsp+40h] [rbp-168h]
  HTTP_REQUEST_ID RequestId; // [rsp+48h] [rbp-160h]
  HTTP_CONNECTION_ID ConnectionId; // [rsp+50h] [rbp-158h] BYREF
  SIZE_T dwBytes; // [rsp+58h] [rbp-150h]
  _WORD v50[2]; // [rsp+60h] [rbp-148h] BYREF
  struct in_addr Addr; // [rsp+64h] [rbp-144h] BYREF
  struct in6_addr v52; // [rsp+68h] [rbp-140h] BYREF
  _BYTE v53[128]; // [rsp+E0h] [rbp-C8h] BYREF

  dwBytes = a2;
  memset_0(v50, 0, 0x80u);
  memset_0(v53, 0, sizeof(v53));
  v5 = *(_QWORD *)(a3 + 48);
  v6 = *(_QWORD *)(a3 + 40);
  RequestId = *(_QWORD *)(v5 + 16);
  ConnectionId = *(_QWORD *)(v5 + 8);
  IpTlsServerDereferenceHttpQueue(v6);
  v7 = (_QWORD *)(v6 + 288);
  v8 = (volatile signed __int32 *)(v6 + 280);
  v9 = (PTP_IO *)(v6 + 96);
  v10 = v6 + 80;
  while ( 1 )
  {
    v11 = v7;
    v46 = v7;
    if ( a1 != 234 )
    {
      v18 = 0;
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_RECEIVE_REQUEST,
          *v7 + 56LL,
          a1);
        v8 = (volatile signed __int32 *)(v6 + 280);
        v9 = (PTP_IO *)(v6 + 96);
        v10 = v6 + 80;
      }
      if ( a1 )
        goto LABEL_60;
      v19 = *(_QWORD *)(a3 + 48);
      v20 = 16;
      v21 = *(_WORD **)(v19 + 104);
      if ( *v21 != 2 )
        v20 = 28;
      memcpy_0(v50, v21, v20);
      memcpy_0(v53, *(const void **)(v19 + 112), v20);
      *(_OWORD *)a3 = 0;
      *(_OWORD *)(a3 + 16) = 0;
      *(_DWORD *)(a3 + 32) = 58485;
      LODWORD(BytesReturned) = 3057;
      EventWrite0(
        0x20000000,
        L"(%s: Reference Server interface(%p)%S:%d",
        *v7 + 56LL,
        v6,
        "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
        BytesReturned);
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
      {
        McTemplateU0psq_EventWriteTransfer(
          v22,
          (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_REFERENCE,
          v6,
          (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
          241);
        v23 = (PTP_IO *)(v6 + 96);
        v24 = (volatile signed __int32 *)(v6 + 280);
        v10 = v6 + 80;
      }
      else
      {
        v23 = v9;
        v24 = v8;
      }
      _InterlockedIncrement(v24);
      StartThreadpoolIo(*v23);
      if ( (unsigned __int8)RoReferenceEx(v10) )
      {
        v25 = HttpReceiveHttpRequest(
                *(HANDLE *)(v6 + 72),
                0,
                0,
                *(PHTTP_REQUEST *)(a3 + 48),
                *(_DWORD *)(a3 + 56),
                0,
                (LPOVERLAPPED)a3);
        v26 = v25;
        if ( v25 == 997 || !v25 )
        {
          v27 = v46;
          a3 = 0;
LABEL_35:
          v29 = (char *)MALLOC(0x1D0u);
          v18 = v29;
          if ( !v29 )
          {
            if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
              McTemplateU0psq_EventWriteTransfer(
                v30,
                (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE,
                0,
                (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
                24);
            goto LABEL_64;
          }
          memset_0(v29, 0, 0x1D0u);
          v31 = (WCHAR *)(v18 + 124);
          *((_DWORD *)v18 + 20) &= ~1u;
          *((_QWORD *)v18 + 6) = RequestId;
          *((_DWORD *)v18 + 14) = 1;
          if ( v50[0] == 2 )
            RtlIpv4AddressToStringW(&Addr, v31);
          else
            RtlIpv6AddressToStringW(&v52, v31);
          *((_DWORD *)v18 + 22) = 0x10000;
          *((_QWORD *)v18 + 5) = v6;
          LODWORD(BytesReturned) = 3126;
          EventWrite0(
            0x20000000,
            L"(%s: Reference Server interface(%p)%S:%d",
            *v27 + 56LL,
            v6,
            "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
            BytesReturned);
          if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
            McTemplateU0psq_EventWriteTransfer(
              v32,
              (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_REFERENCE,
              v6,
              (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
              54);
          _InterlockedIncrement(v24);
          *((_DWORD *)v18 + 20) |= 4u;
          v18[32] = 0;
          *((_DWORD *)v18 + 114) = IpTlsCalculateReceiveQueueId(v6, v50, v53);
          *((_QWORD *)v18 + 3) = v18 + 16;
          *((_QWORD *)v18 + 2) = v18 + 16;
          _InterlockedIncrement64(&g_IpTlsGlobalStatsSessions);
          EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 240));
          v33 = (_QWORD *)(v6 + 224);
          v34 = *(_QWORD *)(v6 + 224);
          if ( *(_QWORD *)(v34 + 8) != v6 + 224 )
            __fastfail(3u);
          *(_QWORD *)v18 = v34;
          *((_QWORD *)v18 + 1) = v33;
          *(_QWORD *)(v34 + 8) = v18;
          *v33 = v18;
          LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 240));
          if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v18 + 5) + 288LL) + 1016LL) == 1 )
          {
            *((_QWORD *)v18 + 56) = PacketHeaderCallbackServer;
            v36 = (char *)MALLOC(0x840u);
            v38 = v36;
            if ( !v36 )
            {
              a1 = 8;
              if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
                McTemplateU0psq_EventWriteTransfer(
                  v37,
                  (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE,
                  0,
                  (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
                  86);
LABEL_63:
              EventWrite0(
                0x10000000,
                L"%s: ReceiveRequestCompletion: %d.",
                *(_QWORD *)(*((_QWORD *)v18 + 5) + 288LL) + 56LL,
                a1);
              ShutdownClientContext(v18);
              goto LABEL_64;
            }
            memset_0(v36, 0, 0x840u);
            v39 = ConnectionId;
            *((_QWORD *)v38 + 7) = v38 + 64;
            *((_QWORD *)v38 + 5) = v18;
            *((_QWORD *)v38 + 6) = v39;
            *((_DWORD *)v38 + 8) = 58487;
            StartThreadpoolIo(*v23);
            if ( (unsigned __int8)RoReferenceEx(v10) )
            {
              v40 = HttpReceiveClientCertificate(
                      *(HANDLE *)(v6 + 72),
                      v39,
                      0,
                      *((PHTTP_SSL_CLIENT_CERT_INFO *)v38 + 7),
                      0x800u,
                      0,
                      (LPOVERLAPPED)v38);
              a1 = v40;
              if ( v40 == 997 || !v40 )
                goto LABEL_64;
              IpTlsServerDereferenceHttpQueue(v6);
            }
            else
            {
              a1 = 6;
            }
            CancelThreadpoolIo(*v23);
            if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
              McTemplateU0zq_EventWriteTransfer(
                MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
                EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_RECEIVE_CLIENT_CERT,
                *v27 + 56LL,
                a1);
            FREE(v38);
            ++g_IpTlsGlobalStatsAuthErrors;
LABEL_61:
            if ( !a1 || !v18 )
              goto LABEL_64;
            goto LABEL_63;
          }
          *((_DWORD *)v18 + 20) &= ~4u;
          v41 = RestrictedPacketHeaderCallbackServer;
          LOBYTE(v35) = 1;
          if ( !*(_BYTE *)(v6 + 48) )
            v41 = PacketHeaderCallbackServer;
          *((_QWORD *)v18 + 56) = v41;
          a1 = PostReceiveEntityOnServer(v18, &ConnectionId, v35);
LABEL_60:
          if ( a1 == 997 )
          {
LABEL_64:
            v11 = v46;
            goto LABEL_65;
          }
          goto LABEL_61;
        }
        IpTlsServerDereferenceHttpQueue(v6);
      }
      else
      {
        v26 = 6;
      }
      v27 = v46;
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_RECEIVE_REQUEST,
          *v46 + 56LL,
          v26);
      CancelThreadpoolIo(*v23);
      LODWORD(BytesReturned) = 3085;
      EventWrite0(
        0x20000000,
        L"(%s: Dereference Server interface(%p) %S:%d",
        *v46 + 56LL,
        v6,
        "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
        BytesReturned);
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
        McTemplateU0psq_EventWriteTransfer(
          v28,
          (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_DEREFERENCE,
          v6,
          (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
          13);
      DereferenceServerInterfaceEx(v6);
      goto LABEL_35;
    }
    FREE(*(_QWORD *)(a3 + 48));
    v12 = (unsigned int)dwBytes;
    *(_DWORD *)(a3 + 56) = dwBytes;
    v13 = MALLOC(v12);
    *(_QWORD *)(a3 + 48) = v13;
    if ( !v13 )
      break;
    v7 = (_QWORD *)(v6 + 288);
    LODWORD(BytesReturned) = 2996;
    EventWrite0(
      0x20000000,
      L"(%s: Reference Server interface(%p)%S:%d",
      *(_QWORD *)(v6 + 288) + 56LL,
      v6,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      BytesReturned);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v15,
        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_REFERENCE,
        v6,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
        180);
    v8 = (volatile signed __int32 *)(v6 + 280);
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 280));
    v9 = (PTP_IO *)(v6 + 96);
    StartThreadpoolIo(*(PTP_IO *)(v6 + 96));
    v10 = v6 + 80;
    if ( (unsigned __int8)RoReferenceEx(v6 + 80) )
    {
      v16 = HttpReceiveHttpRequest(
              *(HANDLE *)(v6 + 72),
              RequestId,
              0,
              *(PHTTP_REQUEST *)(a3 + 48),
              *(_DWORD *)(a3 + 56),
              0,
              (LPOVERLAPPED)a3);
      a1 = v16;
      if ( v16 == 997 || !v16 )
        goto LABEL_69;
      IpTlsServerDereferenceHttpQueue(v6);
    }
    else
    {
      a1 = 6;
    }
    CancelThreadpoolIo(*v9);
    LODWORD(BytesReturned) = 3027;
    EventWrite0(
      0x20000000,
      L"(%s: Dereference Server interface(%p) %S:%d",
      *v7 + 56LL,
      v6,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      BytesReturned);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v17,
        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_DEREFERENCE,
        v6,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
        211);
    DereferenceServerInterfaceEx(v6);
  }
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v14,
      (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE,
      0,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      174);
LABEL_65:
  if ( a3 )
  {
    v42 = *(_QWORD *)(a3 + 48);
    if ( v42 )
      FREE(v42);
    FREE(a3);
  }
LABEL_69:
  LODWORD(BytesReturned) = 3241;
  EventWrite0(
    0x20000000,
    L"(%s: Dereference Server interface(%p) %S:%d",
    *v11 + 56LL,
    v6,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
    BytesReturned);
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v43,
      (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_DEREFERENCE,
      v6,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      169);
  return DereferenceServerInterfaceEx(v6);
}

```

## disassembly

```asm
0x180046474  mov     [rsp+arg_8], rbx
0x180046479  push    rbp
0x18004647a  push    rsi
0x18004647b  push    rdi
0x18004647c  push    r12
0x18004647e  push    r13
0x180046480  push    r14
0x180046482  push    r15
0x180046484  sub     rsp, 170h
0x18004648b  mov     rax, cs:__security_cookie
0x180046492  xor     rax, rsp
0x180046495  mov     [rsp+1A8h+var_48], rax
0x18004649d  mov     r14, r8
0x1800464a0  mov     [rsp+1A8h+dwBytes], rdx
0x1800464a5  mov     edi, ecx
0x1800464a7  mov     ebx, 80h
0x1800464ac  mov     r8d, ebx; Size
0x1800464af  lea     rcx, [rsp+1A8h+var_148]; void *
0x1800464b4  xor     edx, edx; Val
0x1800464b6  call    memset_0
0x1800464bb  mov     r8d, ebx; Size
0x1800464be  lea     rcx, [rsp+1A8h+var_C8]; void *
0x1800464c6  xor     edx, edx; Val
0x1800464c8  call    memset_0
0x1800464cd  mov     rax, [r14+30h]
0x1800464d1  mov     rsi, [r14+28h]
0x1800464d5  mov     rcx, [rax+10h]
0x1800464d9  mov     rax, [rax+8]
0x1800464dd  mov     [rsp+1A8h+RequestId], rcx
0x1800464e2  mov     rcx, rsi
0x1800464e5  mov     [rsp+1A8h+ConnectionId], rax
0x1800464ea  call    IpTlsServerDereferenceHttpQueue
0x1800464ef  lea     r15, [rsi+120h]
0x1800464f6  lea     r12, [rsi+118h]
0x1800464fd  lea     rbp, [rsi+60h]
0x180046501  lea     r13, [rsi+50h]
0x180046505  mov     rbx, r15
0x180046508  mov     [rsp+1A8h+var_168], rbx
0x18004650d  cmp     edi, 0EAh
0x180046513  jnz     loc_1800466B7
0x180046519  mov     rcx, [r14+30h]
0x18004651d  call    FREE
0x180046522  mov     ecx, dword ptr [rsp+1A8h+dwBytes]; dwBytes
0x180046526  mov     [r14+38h], ecx
0x18004652a  call    MALLOC
0x18004652f  mov     [r14+30h], rax
0x180046533  test    rax, rax
0x180046536  jz      loc_180046687
0x18004653c  lea     r15, [rsi+120h]
0x180046543  mov     ebp, 0BB4h
0x180046548  mov     r8, [r15]
0x18004654b  lea     rdi, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180046552  add     r8, 38h ; '8'
0x180046556  mov     dword ptr [rsp+1A8h+BytesReturned], ebp
0x18004655a  mov     r9, rsi
0x18004655d  mov     qword ptr [rsp+1A8h+RequestBufferLength], rdi
0x180046562  lea     rdx, aSReferenceServ; "(%s: Reference Server interface(%p)%S:%"...
0x180046569  mov     ecx, 20000000h
0x18004656e  call    EventWrite0
0x180046573  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18004657a  jz      short loc_180046592
0x18004657c  mov     r9, rdi
0x18004657f  mov     [rsp+1A8h+RequestBufferLength], ebp
0x180046583  mov     r8, rsi
0x180046586  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_REFERENCE
0x18004658d  call    McTemplateU0psq_EventWriteTransfer
0x180046592  lea     r12, [rsi+118h]
0x180046599  lock inc dword ptr [r12]
0x18004659e  lea     rbp, [rsi+60h]
0x1800465a2  mov     rcx, [rbp+0]; pio
0x1800465a6  call    cs:__imp_StartThreadpoolIo
0x1800465ad  nop     dword ptr [rax+rax+00h]
0x1800465b2  lea     r13, [rsi+50h]
0x1800465b6  mov     rcx, r13
0x1800465b9  call    RoReferenceEx
0x1800465be  test    al, al
0x1800465c0  jz      short loc_180046613
0x1800465c2  mov     eax, [r14+38h]
0x1800465c6  xor     r8d, r8d; Flags
0x1800465c9  mov     r9, [r14+30h]; RequestBuffer
0x1800465cd  mov     rdx, [rsp+1A8h+RequestId]; RequestId
0x1800465d2  mov     rcx, [rsi+48h]; RequestQueueHandle
0x1800465d6  mov     [rsp+1A8h+Overlapped], r14; Overlapped
0x1800465db  mov     [rsp+1A8h+BytesReturned], 0; BytesReturned
0x1800465e4  mov     [rsp+1A8h+RequestBufferLength], eax; RequestBufferLength
0x1800465e8  call    cs:__imp_HttpReceiveHttpRequest
0x1800465ef  nop     dword ptr [rax+rax+00h]
0x1800465f4  mov     edi, eax
0x1800465f6  cmp     eax, 3E5h
0x1800465fb  jz      loc_180046BF8
0x180046601  test    eax, eax
0x180046603  jz      loc_180046BF8
0x180046609  mov     rcx, rsi
0x18004660c  call    IpTlsServerDereferenceHttpQueue
0x180046611  jmp     short loc_180046618
0x180046613  mov     edi, 6
0x180046618  mov     rcx, [rbp+0]; pio
0x18004661c  call    cs:__imp_CancelThreadpoolIo
0x180046623  nop     dword ptr [rax+rax+00h]
0x180046628  mov     r8, [r15]
0x18004662b  lea     rbx, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180046632  add     r8, 38h ; '8'
0x180046636  mov     dword ptr [rsp+1A8h+BytesReturned], 0BD3h
0x18004663e  mov     r9, rsi
0x180046641  mov     qword ptr [rsp+1A8h+RequestBufferLength], rbx
0x180046646  lea     rdx, aSDereferenceSe; "(%s: Dereference Server interface(%p) %"...
0x18004664d  mov     ecx, 20000000h
0x180046652  call    EventWrite0
0x180046657  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18004665e  jz      short loc_18004667A
0x180046660  mov     r9, rbx
0x180046663  mov     [rsp+1A8h+RequestBufferLength], 0BD3h
0x18004666b  mov     r8, rsi
0x18004666e  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_DEREFERENCE
0x180046675  call    McTemplateU0psq_EventWriteTransfer
0x18004667a  mov     rcx, rsi
0x18004667d  call    DereferenceServerInterfaceEx
0x180046682  jmp     loc_180046505
0x180046687  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x18004668e  jz      loc_180046BDD
0x180046694  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18004669b  mov     [rsp+1A8h+RequestBufferLength], 0BAEh
0x1800466a3  xor     r8d, r8d
0x1800466a6  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x1800466ad  call    McTemplateU0psq_EventWriteTransfer
0x1800466b2  jmp     loc_180046BDD
0x1800466b7  xor     ebx, ebx
0x1800466b9  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x1800466c0  jz      short loc_1800466EE
0x1800466c2  mov     r8, [r15]
0x1800466c5  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_RECEIVE_REQUEST
0x1800466cc  add     r8, 38h ; '8'
0x1800466d0  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800466d7  mov     r9d, edi
0x1800466da  call    McTemplateU0zq_EventWriteTransfer
0x1800466df  lea     r12, [rsi+118h]
0x1800466e6  lea     rbp, [rsi+60h]
0x1800466ea  lea     r13, [rsi+50h]
0x1800466ee  test    edi, edi
0x1800466f0  jnz     loc_180046B9C
0x1800466f6  mov     rdi, [r14+30h]
0x1800466fa  lea     rcx, [rsp+1A8h+var_148]; void *
0x1800466ff  mov     ebx, 10h
0x180046704  mov     rdx, [rdi+68h]; Src
0x180046708  lea     eax, [rbx+0Ch]
0x18004670b  cmp     word ptr [rdx], 2
0x18004670f  cmovnz  ebx, eax
0x180046712  mov     r8d, ebx; Size
0x180046715  call    memcpy_0
0x18004671a  mov     rdx, [rdi+70h]; Src
0x18004671e  lea     rcx, [rsp+1A8h+var_C8]; void *
0x180046726  mov     r8d, ebx; Size
0x180046729  call    memcpy_0
0x18004672e  xorps   xmm0, xmm0
0x180046731  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180046738  movups  xmmword ptr [r14], xmm0
0x18004673c  mov     ebx, 0BF1h
0x180046741  lea     rdx, aSReferenceServ; "(%s: Reference Server interface(%p)%S:%"...
0x180046748  movups  xmmword ptr [r14+10h], xmm0
0x18004674d  mov     dword ptr [r14+20h], 0E475h
0x180046755  mov     ecx, 20000000h
0x18004675a  mov     r8, [r15]
0x18004675d  mov     dword ptr [rsp+1A8h+BytesReturned], ebx
0x180046761  add     r8, 38h ; '8'
0x180046765  mov     qword ptr [rsp+1A8h+RequestBufferLength], r9
0x18004676a  mov     r9, rsi
0x18004676d  call    EventWrite0
0x180046772  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180046779  jz      short loc_1800467A9
0x18004677b  lea     rbp, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180046782  mov     [rsp+1A8h+RequestBufferLength], ebx
0x180046786  mov     r9, rbp
0x180046789  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_REFERENCE
0x180046790  mov     r8, rsi
0x180046793  call    McTemplateU0psq_EventWriteTransfer
0x180046798  lea     r15, [rsi+60h]
0x18004679c  lea     rdi, [rsi+118h]
0x1800467a3  lea     r13, [rsi+50h]
0x1800467a7  jmp     short loc_1800467B6
0x1800467a9  mov     r15, rbp
0x1800467ac  mov     rdi, r12
0x1800467af  lea     rbp, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800467b6  lock inc dword ptr [rdi]
0x1800467b9  mov     rcx, [r15]; pio
0x1800467bc  call    cs:__imp_StartThreadpoolIo
0x1800467c3  nop     dword ptr [rax+rax+00h]
0x1800467c8  mov     rcx, r13
0x1800467cb  call    RoReferenceEx
0x1800467d0  test    al, al
0x1800467d2  jz      short loc_180046827
0x1800467d4  mov     eax, [r14+38h]
0x1800467d8  xor     r8d, r8d; Flags
0x1800467db  mov     r9, [r14+30h]; RequestBuffer
0x1800467df  xor     edx, edx; RequestId
0x1800467e1  mov     rcx, [rsi+48h]; RequestQueueHandle
0x1800467e5  mov     [rsp+1A8h+Overlapped], r14; Overlapped
0x1800467ea  mov     [rsp+1A8h+BytesReturned], 0; BytesReturned
0x1800467f3  mov     [rsp+1A8h+RequestBufferLength], eax; RequestBufferLength
0x1800467f7  call    cs:__imp_HttpReceiveHttpRequest
0x1800467fe  nop     dword ptr [rax+rax+00h]
0x180046803  mov     ebx, eax
0x180046805  cmp     eax, 3E5h
0x18004680a  jz      short loc_18004681A
0x18004680c  test    eax, eax
0x18004680e  jz      short loc_18004681A
0x180046810  mov     rcx, rsi
0x180046813  call    IpTlsServerDereferenceHttpQueue
0x180046818  jmp     short loc_18004682C
0x18004681a  mov     r12, [rsp+1A8h+var_168]
0x18004681f  xor     r14d, r14d
0x180046822  jmp     loc_1800468B8
0x180046827  mov     ebx, 6
0x18004682c  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180046833  mov     r12, [rsp+1A8h+var_168]
0x180046838  jz      short loc_180046858
0x18004683a  mov     r8, [r12]
0x18004683e  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_RECEIVE_REQUEST
0x180046845  add     r8, 38h ; '8'
0x180046849  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180046850  mov     r9d, ebx
0x180046853  call    McTemplateU0zq_EventWriteTransfer
0x180046858  mov     rcx, [r15]; pio
0x18004685b  call    cs:__imp_CancelThreadpoolIo
0x180046862  nop     dword ptr [rax+rax+00h]
0x180046867  mov     r8, [r12]
0x18004686b  lea     rdx, aSDereferenceSe; "(%s: Dereference Server interface(%p) %"...
0x180046872  mov     ebx, 0C0Dh
0x180046877  add     r8, 38h ; '8'
0x18004687b  mov     dword ptr [rsp+1A8h+BytesReturned], ebx
0x18004687f  mov     r9, rsi
0x180046882  mov     ecx, 20000000h
0x180046887  mov     qword ptr [rsp+1A8h+RequestBufferLength], rbp
0x18004688c  call    EventWrite0
0x180046891  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180046898  jz      short loc_1800468B0
0x18004689a  mov     r9, rbp
0x18004689d  mov     [rsp+1A8h+RequestBufferLength], ebx
0x1800468a1  mov     r8, rsi
0x1800468a4  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_DEREFERENCE
0x1800468ab  call    McTemplateU0psq_EventWriteTransfer
0x1800468b0  mov     rcx, rsi
0x1800468b3  call    DereferenceServerInterfaceEx
0x1800468b8  mov     ecx, 1D0h; dwBytes
0x1800468bd  call    MALLOC
0x1800468c2  mov     rbx, rax
0x1800468c5  test    rax, rax
0x1800468c8  jnz     short loc_1800468F6
0x1800468ca  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x1800468d1  jz      loc_180046BD8
0x1800468d7  mov     r9, rbp
0x1800468da  mov     [rsp+1A8h+RequestBufferLength], 0C18h
0x1800468e2  xor     r8d, r8d
0x1800468e5  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x1800468ec  call    McTemplateU0psq_EventWriteTransfer
0x1800468f1  jmp     loc_180046BD8
0x1800468f6  xor     edx, edx; Val
0x1800468f8  mov     r8d, 1D0h; Size
0x1800468fe  mov     rcx, rbx; void *
0x180046901  call    memset_0
0x180046906  mov     rax, [rsp+1A8h+RequestId]
0x18004690b  lea     rdx, [rbx+7Ch]; S
0x18004690f  and     dword ptr [rbx+50h], 0FFFFFFFEh
0x180046913  mov     [rbx+30h], rax
0x180046917  mov     dword ptr [rbx+38h], 1
0x18004691e  cmp     [rsp+1A8h+var_148], 2
0x180046924  jnz     short loc_180046939
0x180046926  lea     rcx, [rsp+1A8h+Addr]; Addr
0x18004692b  call    cs:__imp_RtlIpv4AddressToStringW
0x180046932  nop     dword ptr [rax+rax+00h]
0x180046937  jmp     short loc_18004694A
0x180046939  lea     rcx, [rsp+1A8h+var_140]; Addr
0x18004693e  call    cs:__imp_RtlIpv6AddressToStringW
0x180046945  nop     dword ptr [rax+rax+00h]
0x18004694a  mov     dword ptr [rbx+58h], 10000h
0x180046951  lea     rdx, aSReferenceServ; "(%s: Reference Server interface(%p)%S:%"...
0x180046958  mov     [rbx+28h], rsi
0x18004695c  mov     r9, rsi
0x18004695f  mov     r8, [r12]
0x180046963  mov     ecx, 20000000h
0x180046968  add     r8, 38h ; '8'
0x18004696c  mov     dword ptr [rsp+1A8h+BytesReturned], 0C36h
0x180046974  mov     qword ptr [rsp+1A8h+RequestBufferLength], rbp
0x180046979  call    EventWrite0
0x18004697e  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180046985  jz      short loc_1800469A1
0x180046987  mov     r9, rbp
0x18004698a  mov     [rsp+1A8h+RequestBufferLength], 0C36h
0x180046992  mov     r8, rsi
0x180046995  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_REFERENCE
0x18004699c  call    McTemplateU0psq_EventWriteTransfer
0x1800469a1  lock inc dword ptr [rdi]
0x1800469a4  or      dword ptr [rbx+50h], 4
0x1800469a8  lea     r8, [rsp+1A8h+var_C8]
0x1800469b0  lea     rdx, [rsp+1A8h+var_148]
0x1800469b5  mov     byte ptr [rbx+20h], 0
0x1800469b9  mov     rcx, rsi
0x1800469bc  call    IpTlsCalculateReceiveQueueId
0x1800469c1  mov     [rbx+1C8h], eax
0x1800469c7  lea     rax, [rbx+10h]
0x1800469cb  mov     [rax+8], rax
  ... truncated ...
```
