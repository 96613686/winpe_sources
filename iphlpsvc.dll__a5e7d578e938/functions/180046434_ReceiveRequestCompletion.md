# ReceiveRequestCompletion

- ea: `0x180046434`
- end: `0x180046c3b`
- name: `ReceiveRequestCompletion`
- size: `2055`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180064a40`

## callees

- `0x180004c64`
- `0x18000d7c0`
- `0x180012dcc`
- `0x1800159d4`
- `0x180040d90`
- `0x180046434`
- `0x180046c44`
- `0x1800496f0`
- `0x18004b5f0`
- `0x18004c188`
- `0x1800616b4`
- `0x1800647ac`
- `0x180066148`
- `0x180066818`
- `0x180082274`

## import_xrefs

- `ntdll!RtlIpv4AddressToStringW` at `0x1800468eb`
- `ntdll!RtlIpv4AddressToStringW` at `0x1800468eb`
- `ntdll!RtlIpv6AddressToStringW` at `0x1800468fe`
- `ntdll!RtlIpv6AddressToStringW` at `0x1800468fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800469a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800469a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800469d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800469d8`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800465dc`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18004681b`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180046aec`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800465dc`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18004681b`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180046aec`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180046566`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18004677c`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180046a7d`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180046566`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18004677c`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180046a7d`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x1800465a8`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x1800467b7`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x1800465a8`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x1800467b7`
- `HTTPAPI!HttpReceiveClientCertificate` at `0x180046ab9`
- `HTTPAPI!HttpReceiveClientCertificate` at `0x180046ab9`

## string_xrefs

- `0x18004650b`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x1800465eb`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180046654`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x1800466f1`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x18004673b`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x18004676f`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180046a2e`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180046bc7`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180046b71`: `%s: ReceiveRequestCompletion: %d.`

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
0x180046434  mov     [rsp+arg_8], rbx
0x180046439  push    rbp
0x18004643a  push    rsi
0x18004643b  push    rdi
0x18004643c  push    r12
0x18004643e  push    r13
0x180046440  push    r14
0x180046442  push    r15
0x180046444  sub     rsp, 170h
0x18004644b  mov     rax, cs:__security_cookie
0x180046452  xor     rax, rsp
0x180046455  mov     [rsp+1A8h+var_48], rax
0x18004645d  mov     r14, r8
0x180046460  mov     [rsp+1A8h+dwBytes], rdx
0x180046465  mov     edi, ecx
0x180046467  mov     ebx, 80h
0x18004646c  mov     r8d, ebx; Size
0x18004646f  lea     rcx, [rsp+1A8h+var_148]; void *
0x180046474  xor     edx, edx; Val
0x180046476  call    memset_0
0x18004647b  mov     r8d, ebx; Size
0x18004647e  lea     rcx, [rsp+1A8h+var_C8]; void *
0x180046486  xor     edx, edx; Val
0x180046488  call    memset_0
0x18004648d  mov     rax, [r14+30h]
0x180046491  mov     rsi, [r14+28h]
0x180046495  mov     rcx, [rax+10h]
0x180046499  mov     rax, [rax+8]
0x18004649d  mov     [rsp+1A8h+RequestId], rcx
0x1800464a2  mov     rcx, rsi
0x1800464a5  mov     [rsp+1A8h+ConnectionId], rax
0x1800464aa  call    IpTlsServerDereferenceHttpQueue
0x1800464af  lea     r15, [rsi+120h]
0x1800464b6  lea     r12, [rsi+118h]
0x1800464bd  lea     rbp, [rsi+60h]
0x1800464c1  lea     r13, [rsi+50h]
0x1800464c5  mov     rbx, r15
0x1800464c8  mov     [rsp+1A8h+var_168], rbx
0x1800464cd  cmp     edi, 0EAh
0x1800464d3  jnz     loc_180046677
0x1800464d9  mov     rcx, [r14+30h]
0x1800464dd  call    FREE
0x1800464e2  mov     ecx, dword ptr [rsp+1A8h+dwBytes]; dwBytes
0x1800464e6  mov     [r14+38h], ecx
0x1800464ea  call    MALLOC
0x1800464ef  mov     [r14+30h], rax
0x1800464f3  test    rax, rax
0x1800464f6  jz      loc_180046647
0x1800464fc  lea     r15, [rsi+120h]
0x180046503  mov     ebp, 0BB4h
0x180046508  mov     r8, [r15]
0x18004650b  lea     rdi, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180046512  add     r8, 38h ; '8'
0x180046516  mov     dword ptr [rsp+1A8h+BytesReturned], ebp
0x18004651a  mov     r9, rsi
0x18004651d  mov     qword ptr [rsp+1A8h+RequestBufferLength], rdi
0x180046522  lea     rdx, aSReferenceServ; "(%s: Reference Server interface(%p)%S:%"...
0x180046529  mov     ecx, 20000000h
0x18004652e  call    EventWrite0
0x180046533  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18004653a  jz      short loc_180046552
0x18004653c  mov     r9, rdi
0x18004653f  mov     [rsp+1A8h+RequestBufferLength], ebp
0x180046543  mov     r8, rsi
0x180046546  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_REFERENCE
0x18004654d  call    McTemplateU0psq_EventWriteTransfer
0x180046552  lea     r12, [rsi+118h]
0x180046559  lock inc dword ptr [r12]
0x18004655e  lea     rbp, [rsi+60h]
0x180046562  mov     rcx, [rbp+0]; pio
0x180046566  call    cs:__imp_StartThreadpoolIo
0x18004656d  nop     dword ptr [rax+rax+00h]
0x180046572  lea     r13, [rsi+50h]
0x180046576  mov     rcx, r13
0x180046579  call    RoReferenceEx
0x18004657e  test    al, al
0x180046580  jz      short loc_1800465D3
0x180046582  mov     eax, [r14+38h]
0x180046586  xor     r8d, r8d; Flags
0x180046589  mov     r9, [r14+30h]; RequestBuffer
0x18004658d  mov     rdx, [rsp+1A8h+RequestId]; RequestId
0x180046592  mov     rcx, [rsi+48h]; RequestQueueHandle
0x180046596  mov     [rsp+1A8h+Overlapped], r14; Overlapped
0x18004659b  mov     [rsp+1A8h+BytesReturned], 0; BytesReturned
0x1800465a4  mov     [rsp+1A8h+RequestBufferLength], eax; RequestBufferLength
0x1800465a8  call    cs:__imp_HttpReceiveHttpRequest
0x1800465af  nop     dword ptr [rax+rax+00h]
0x1800465b4  mov     edi, eax
0x1800465b6  cmp     eax, 3E5h
0x1800465bb  jz      loc_180046BB8
0x1800465c1  test    eax, eax
0x1800465c3  jz      loc_180046BB8
0x1800465c9  mov     rcx, rsi
0x1800465cc  call    IpTlsServerDereferenceHttpQueue
0x1800465d1  jmp     short loc_1800465D8
0x1800465d3  mov     edi, 6
0x1800465d8  mov     rcx, [rbp+0]; pio
0x1800465dc  call    cs:__imp_CancelThreadpoolIo
0x1800465e3  nop     dword ptr [rax+rax+00h]
0x1800465e8  mov     r8, [r15]
0x1800465eb  lea     rbx, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800465f2  add     r8, 38h ; '8'
0x1800465f6  mov     dword ptr [rsp+1A8h+BytesReturned], 0BD3h
0x1800465fe  mov     r9, rsi
0x180046601  mov     qword ptr [rsp+1A8h+RequestBufferLength], rbx
0x180046606  lea     rdx, aSDereferenceSe; "(%s: Dereference Server interface(%p) %"...
0x18004660d  mov     ecx, 20000000h
0x180046612  call    EventWrite0
0x180046617  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18004661e  jz      short loc_18004663A
0x180046620  mov     r9, rbx
0x180046623  mov     [rsp+1A8h+RequestBufferLength], 0BD3h
0x18004662b  mov     r8, rsi
0x18004662e  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_DEREFERENCE
0x180046635  call    McTemplateU0psq_EventWriteTransfer
0x18004663a  mov     rcx, rsi
0x18004663d  call    DereferenceServerInterfaceEx
0x180046642  jmp     loc_1800464C5
0x180046647  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x18004664e  jz      loc_180046B9D
0x180046654  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18004665b  mov     [rsp+1A8h+RequestBufferLength], 0BAEh
0x180046663  xor     r8d, r8d
0x180046666  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x18004666d  call    McTemplateU0psq_EventWriteTransfer
0x180046672  jmp     loc_180046B9D
0x180046677  xor     ebx, ebx
0x180046679  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180046680  jz      short loc_1800466AE
0x180046682  mov     r8, [r15]
0x180046685  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_RECEIVE_REQUEST
0x18004668c  add     r8, 38h ; '8'
0x180046690  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180046697  mov     r9d, edi
0x18004669a  call    McTemplateU0zq_EventWriteTransfer
0x18004669f  lea     r12, [rsi+118h]
0x1800466a6  lea     rbp, [rsi+60h]
0x1800466aa  lea     r13, [rsi+50h]
0x1800466ae  test    edi, edi
0x1800466b0  jnz     loc_180046B5C
0x1800466b6  mov     rdi, [r14+30h]
0x1800466ba  lea     rcx, [rsp+1A8h+var_148]; void *
0x1800466bf  mov     ebx, 10h
0x1800466c4  mov     rdx, [rdi+68h]; Src
0x1800466c8  lea     eax, [rbx+0Ch]
0x1800466cb  cmp     word ptr [rdx], 2
0x1800466cf  cmovnz  ebx, eax
0x1800466d2  mov     r8d, ebx; Size
0x1800466d5  call    memcpy_0
0x1800466da  mov     rdx, [rdi+70h]; Src
0x1800466de  lea     rcx, [rsp+1A8h+var_C8]; void *
0x1800466e6  mov     r8d, ebx; Size
0x1800466e9  call    memcpy_0
0x1800466ee  xorps   xmm0, xmm0
0x1800466f1  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800466f8  movups  xmmword ptr [r14], xmm0
0x1800466fc  mov     ebx, 0BF1h
0x180046701  lea     rdx, aSReferenceServ; "(%s: Reference Server interface(%p)%S:%"...
0x180046708  movups  xmmword ptr [r14+10h], xmm0
0x18004670d  mov     dword ptr [r14+20h], 0E475h
0x180046715  mov     ecx, 20000000h
0x18004671a  mov     r8, [r15]
0x18004671d  mov     dword ptr [rsp+1A8h+BytesReturned], ebx
0x180046721  add     r8, 38h ; '8'
0x180046725  mov     qword ptr [rsp+1A8h+RequestBufferLength], r9
0x18004672a  mov     r9, rsi
0x18004672d  call    EventWrite0
0x180046732  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180046739  jz      short loc_180046769
0x18004673b  lea     rbp, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180046742  mov     [rsp+1A8h+RequestBufferLength], ebx
0x180046746  mov     r9, rbp
0x180046749  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_REFERENCE
0x180046750  mov     r8, rsi
0x180046753  call    McTemplateU0psq_EventWriteTransfer
0x180046758  lea     r15, [rsi+60h]
0x18004675c  lea     rdi, [rsi+118h]
0x180046763  lea     r13, [rsi+50h]
0x180046767  jmp     short loc_180046776
0x180046769  mov     r15, rbp
0x18004676c  mov     rdi, r12
0x18004676f  lea     rbp, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180046776  lock inc dword ptr [rdi]
0x180046779  mov     rcx, [r15]; pio
0x18004677c  call    cs:__imp_StartThreadpoolIo
0x180046783  nop     dword ptr [rax+rax+00h]
0x180046788  mov     rcx, r13
0x18004678b  call    RoReferenceEx
0x180046790  test    al, al
0x180046792  jz      short loc_1800467E7
0x180046794  mov     eax, [r14+38h]
0x180046798  xor     r8d, r8d; Flags
0x18004679b  mov     r9, [r14+30h]; RequestBuffer
0x18004679f  xor     edx, edx; RequestId
0x1800467a1  mov     rcx, [rsi+48h]; RequestQueueHandle
0x1800467a5  mov     [rsp+1A8h+Overlapped], r14; Overlapped
0x1800467aa  mov     [rsp+1A8h+BytesReturned], 0; BytesReturned
0x1800467b3  mov     [rsp+1A8h+RequestBufferLength], eax; RequestBufferLength
0x1800467b7  call    cs:__imp_HttpReceiveHttpRequest
0x1800467be  nop     dword ptr [rax+rax+00h]
0x1800467c3  mov     ebx, eax
0x1800467c5  cmp     eax, 3E5h
0x1800467ca  jz      short loc_1800467DA
0x1800467cc  test    eax, eax
0x1800467ce  jz      short loc_1800467DA
0x1800467d0  mov     rcx, rsi
0x1800467d3  call    IpTlsServerDereferenceHttpQueue
0x1800467d8  jmp     short loc_1800467EC
0x1800467da  mov     r12, [rsp+1A8h+var_168]
0x1800467df  xor     r14d, r14d
0x1800467e2  jmp     loc_180046878
0x1800467e7  mov     ebx, 6
0x1800467ec  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x1800467f3  mov     r12, [rsp+1A8h+var_168]
0x1800467f8  jz      short loc_180046818
0x1800467fa  mov     r8, [r12]
0x1800467fe  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_RECEIVE_REQUEST
0x180046805  add     r8, 38h ; '8'
0x180046809  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180046810  mov     r9d, ebx
0x180046813  call    McTemplateU0zq_EventWriteTransfer
0x180046818  mov     rcx, [r15]; pio
0x18004681b  call    cs:__imp_CancelThreadpoolIo
0x180046822  nop     dword ptr [rax+rax+00h]
0x180046827  mov     r8, [r12]
0x18004682b  lea     rdx, aSDereferenceSe; "(%s: Dereference Server interface(%p) %"...
0x180046832  mov     ebx, 0C0Dh
0x180046837  add     r8, 38h ; '8'
0x18004683b  mov     dword ptr [rsp+1A8h+BytesReturned], ebx
0x18004683f  mov     r9, rsi
0x180046842  mov     ecx, 20000000h
0x180046847  mov     qword ptr [rsp+1A8h+RequestBufferLength], rbp
0x18004684c  call    EventWrite0
0x180046851  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180046858  jz      short loc_180046870
0x18004685a  mov     r9, rbp
0x18004685d  mov     [rsp+1A8h+RequestBufferLength], ebx
0x180046861  mov     r8, rsi
0x180046864  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_DEREFERENCE
0x18004686b  call    McTemplateU0psq_EventWriteTransfer
0x180046870  mov     rcx, rsi
0x180046873  call    DereferenceServerInterfaceEx
0x180046878  mov     ecx, 1D0h; dwBytes
0x18004687d  call    MALLOC
0x180046882  mov     rbx, rax
0x180046885  test    rax, rax
0x180046888  jnz     short loc_1800468B6
0x18004688a  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180046891  jz      loc_180046B98
0x180046897  mov     r9, rbp
0x18004689a  mov     [rsp+1A8h+RequestBufferLength], 0C18h
0x1800468a2  xor     r8d, r8d
0x1800468a5  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x1800468ac  call    McTemplateU0psq_EventWriteTransfer
0x1800468b1  jmp     loc_180046B98
0x1800468b6  xor     edx, edx; Val
0x1800468b8  mov     r8d, 1D0h; Size
0x1800468be  mov     rcx, rbx; void *
0x1800468c1  call    memset_0
0x1800468c6  mov     rax, [rsp+1A8h+RequestId]
0x1800468cb  lea     rdx, [rbx+7Ch]; S
0x1800468cf  and     dword ptr [rbx+50h], 0FFFFFFFEh
0x1800468d3  mov     [rbx+30h], rax
0x1800468d7  mov     dword ptr [rbx+38h], 1
0x1800468de  cmp     [rsp+1A8h+var_148], 2
0x1800468e4  jnz     short loc_1800468F9
0x1800468e6  lea     rcx, [rsp+1A8h+Addr]; Addr
0x1800468eb  call    cs:__imp_RtlIpv4AddressToStringW
0x1800468f2  nop     dword ptr [rax+rax+00h]
0x1800468f7  jmp     short loc_18004690A
0x1800468f9  lea     rcx, [rsp+1A8h+var_140]; Addr
0x1800468fe  call    cs:__imp_RtlIpv6AddressToStringW
0x180046905  nop     dword ptr [rax+rax+00h]
0x18004690a  mov     dword ptr [rbx+58h], 10000h
0x180046911  lea     rdx, aSReferenceServ; "(%s: Reference Server interface(%p)%S:%"...
0x180046918  mov     [rbx+28h], rsi
0x18004691c  mov     r9, rsi
0x18004691f  mov     r8, [r12]
0x180046923  mov     ecx, 20000000h
0x180046928  add     r8, 38h ; '8'
0x18004692c  mov     dword ptr [rsp+1A8h+BytesReturned], 0C36h
0x180046934  mov     qword ptr [rsp+1A8h+RequestBufferLength], rbp
0x180046939  call    EventWrite0
0x18004693e  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180046945  jz      short loc_180046961
0x180046947  mov     r9, rbp
0x18004694a  mov     [rsp+1A8h+RequestBufferLength], 0C36h
0x180046952  mov     r8, rsi
0x180046955  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_REFERENCE
0x18004695c  call    McTemplateU0psq_EventWriteTransfer
0x180046961  lock inc dword ptr [rdi]
0x180046964  or      dword ptr [rbx+50h], 4
0x180046968  lea     r8, [rsp+1A8h+var_C8]
0x180046970  lea     rdx, [rsp+1A8h+var_148]
0x180046975  mov     byte ptr [rbx+20h], 0
0x180046979  mov     rcx, rsi
0x18004697c  call    IpTlsCalculateReceiveQueueId
0x180046981  mov     [rbx+1C8h], eax
0x180046987  lea     rax, [rbx+10h]
0x18004698b  mov     [rax+8], rax
  ... truncated ...
```
