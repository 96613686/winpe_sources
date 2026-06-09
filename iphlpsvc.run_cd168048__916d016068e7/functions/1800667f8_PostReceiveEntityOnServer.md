# PostReceiveEntityOnServer

- ea: `0x1800667f8`
- end: `0x180066b8d`
- name: `PostReceiveEntityOnServer`
- size: `917`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180046474`
- `0x180065840`
- `0x180066b94`

## callees

- `0x18000d7b0`
- `0x180012dbc`
- `0x180013570`
- `0x1800159c4`
- `0x180030d24`
- `0x180040dd0`
- `0x18004c1c8`
- `0x180061694`
- `0x180066128`
- `0x1800667f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006693b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800669d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006693b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800669d5`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180066b4b`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180066b4b`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180066a78`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180066a78`
- `HTTPAPI!HttpSendHttpResponse` at `0x1800668be`
- `HTTPAPI!HttpSendHttpResponse` at `0x1800668be`
- `HTTPAPI!HttpReceiveRequestEntityBody` at `0x180066ac1`
- `HTTPAPI!HttpReceiveRequestEntityBody` at `0x180066ac1`

## string_xrefs

- `0x180066916`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x1800669f5`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

## pseudocode

```c
__int64 __fastcall PostReceiveEntityOnServer(__int64 a1, _QWORD *a2, char a3)
{
  __int64 v6; // rax
  __int64 v7; // rbp
  __int64 v8; // rcx
  ULONG v9; // r8d
  ULONG v10; // ebx
  _QWORD *v11; // rax
  __int64 v12; // rax
  int v13; // ecx
  struct _OVERLAPPED *v14; // rdi
  int v16; // ecx
  ULONG v17; // eax
  PHTTP_CACHE_POLICY CachePolicy; // [rsp+20h] [rbp-298h]
  PULONG BytesSent; // [rsp+28h] [rbp-290h]
  HTTP_RESPONSE HttpResponse; // [rsp+50h] [rbp-268h] BYREF
  ULONG v21; // [rsp+2D0h] [rbp+18h] BYREF

  memset_0(&HttpResponse, 0, sizeof(HttpResponse));
  v6 = *(_QWORD *)(a1 + 40);
  v21 = 0;
  v7 = *(_QWORD *)(v6 + 288);
  *a2 = 0;
  if ( a3 )
  {
    v8 = *(_QWORD *)(a1 + 40) + 80LL;
    *(_DWORD *)&HttpResponse.StatusCode = 131272;
    HttpResponse.pReason = "OK";
    if ( (unsigned __int8)RoReferenceEx(v8) )
    {
      v10 = HttpSendHttpResponse(
              *(HANDLE *)(*(_QWORD *)(a1 + 40) + 72LL),
              *(_QWORD *)(a1 + 48),
              v9,
              &HttpResponse,
              0,
              &v21,
              0,
              0,
              0,
              0);
      IpTlsServerDereferenceHttpQueue(*(_QWORD *)(a1 + 40));
      if ( !v10 )
        goto LABEL_4;
    }
    else
    {
      v10 = 6;
    }
    EventWrite0(0x10000000, L"%s: HttpSendHttpResponse: %d.", *(_QWORD *)(*(_QWORD *)(a1 + 40) + 288LL) + 56LL, v10);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_SEND_RESPONSE,
        *(_QWORD *)(*(_QWORD *)(a1 + 40) + 288LL) + 56LL,
        v10);
    return v10;
  }
LABEL_4:
  IpTlsAcquireLock(g_IpTlsInterfaceListLock);
  v11 = *(_QWORD **)(v7 + 1176);
  if ( v11 )
  {
    v14 = (struct _OVERLAPPED *)(v11 - 6);
    *(_QWORD *)(v7 + 1176) = *v11;
    _InterlockedDecrement((volatile signed __int32 *)(v7 + 1188));
LABEL_14:
    ReleaseMutex(g_IpTlsInterfaceListLock);
    memset_0(v14, 0, 0x80A0u);
    HIDWORD(v14[3].Internal) = 48928;
    LODWORD(v14[1].Internal) = 58486;
    LODWORD(BytesSent) = 2802;
    EventWrite0(
      0x20000000,
      L"(%s: Reference client context (%p)%S:%d",
      *(_QWORD *)(*(_QWORD *)(a1 + 40) + 288LL) + 56LL,
      a1,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      BytesSent);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v16,
        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_REFERENCE,
        a1,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
        242);
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 56));
    v14[2].hEvent = (HANDLE)a1;
    v14[4].InternalHigh = (ULONG_PTR)SendBufferCleanup;
    v14[2].Offset = 1;
    StartThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(a1 + 40) + 96LL));
    if ( (unsigned __int8)RoReferenceEx(*(_QWORD *)(a1 + 40) + 80LL) )
    {
      v17 = HttpReceiveRequestEntityBody(
              *(HANDLE *)(*(_QWORD *)(a1 + 40) + 72LL),
              *(_QWORD *)(a1 + 48),
              0,
              &v14[68].hEvent,
              0x7800u,
              0,
              v14);
      v10 = v17;
      if ( v17 == 997 || !v17 )
        return v10;
      IpTlsServerDereferenceHttpQueue(*(_QWORD *)(a1 + 40));
    }
    else
    {
      v10 = 6;
    }
    EventWrite0(
      0x10000000,
      L"%s: HttpReceiveRequestEntityBody: %d.",
      *(_QWORD *)(*(_QWORD *)(a1 + 40) + 288LL) + 56LL,
      v10);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_RECEIVE_ENTITY,
        *(_QWORD *)(*(_QWORD *)(a1 + 40) + 288LL) + 56LL,
        v10);
    CancelThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(a1 + 40) + 96LL));
    LODWORD(CachePolicy) = 2841;
    EventWrite0(
      0x20000000,
      L"(Dereference IPTLS Buffer(%p)%S:%d",
      v14,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      CachePolicy);
    IpTlsDereferenceBufferEx(v14);
    return v10;
  }
  v12 = MALLOC(0x80A0u);
  v14 = (struct _OVERLAPPED *)v12;
  if ( v12 )
  {
    *(_DWORD *)(v12 + 100) = 48925;
    goto LABEL_14;
  }
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v13,
      (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE,
      0,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      223);
  ReleaseMutex(g_IpTlsInterfaceListLock);
  return 8;
}

```

## disassembly

```asm
0x1800667f8  push    rbx
0x1800667fa  push    rbp
0x1800667fb  push    rsi
0x1800667fc  push    rdi
0x1800667fd  sub     rsp, 298h
0x180066804  mov     dil, r8b
0x180066807  mov     rbx, rdx
0x18006680a  mov     rsi, rcx
0x18006680d  xor     edx, edx; Val
0x18006680f  mov     r8d, 238h; Size
0x180066815  lea     rcx, [rsp+2B8h+HttpResponse]; void *
0x18006681a  call    memset_0
0x18006681f  mov     rax, [rsi+28h]
0x180066823  mov     [rsp+2B8h+arg_10], 0
0x18006682e  mov     rbp, [rax+120h]
0x180066835  mov     qword ptr [rbx], 0
0x18006683c  test    dil, dil
0x18006683f  jz      loc_1800668D9
0x180066845  mov     rcx, [rsi+28h]
0x180066849  lea     rax, aOk; "OK"
0x180066850  add     rcx, 50h ; 'P'
0x180066854  mov     dword ptr [rsp+2B8h+HttpResponse.StatusCode], 200C8h
0x18006685c  mov     [rsp+2B8h+HttpResponse.pReason], rax
0x180066861  mov     r8d, 2
0x180066867  call    RoReferenceEx
0x18006686c  test    al, al
0x18006686e  jz      loc_180066951
0x180066874  mov     rcx, [rsi+28h]
0x180066878  lea     rax, [rsp+2B8h+arg_10]
0x180066880  mov     rdx, [rsi+30h]; RequestId
0x180066884  lea     r9, [rsp+2B8h+HttpResponse]; HttpResponse
0x180066889  mov     [rsp+2B8h+LogData], 0; LogData
0x180066892  mov     [rsp+2B8h+Overlapped], 0; Overlapped
0x18006689b  mov     rcx, [rcx+48h]; RequestQueueHandle
0x18006689f  mov     [rsp+2B8h+Reserved2], 0; Reserved2
0x1800668a7  mov     [rsp+2B8h+Reserved1], 0; Reserved1
0x1800668b0  mov     [rsp+2B8h+BytesSent], rax; BytesSent
0x1800668b5  mov     [rsp+2B8h+CachePolicy], 0; CachePolicy
0x1800668be  call    cs:__imp_HttpSendHttpResponse
0x1800668c5  nop     dword ptr [rax+rax+00h]
0x1800668ca  mov     rcx, [rsi+28h]
0x1800668ce  mov     ebx, eax
0x1800668d0  call    IpTlsServerDereferenceHttpQueue
0x1800668d5  test    ebx, ebx
0x1800668d7  jnz     short loc_180066956
0x1800668d9  mov     rcx, cs:g_IpTlsInterfaceListLock
0x1800668e0  call    IpTlsAcquireLock
0x1800668e5  mov     rax, [rbp+498h]
0x1800668ec  mov     ebx, 80A0h
0x1800668f1  test    rax, rax
0x1800668f4  jnz     loc_1800669B9
0x1800668fa  mov     ecx, ebx; dwBytes
0x1800668fc  call    MALLOC
0x180066901  mov     rdi, rax
0x180066904  test    rax, rax
0x180066907  jnz     loc_1800669B0
0x18006690d  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180066914  jz      short loc_180066934
0x180066916  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006691d  mov     dword ptr [rsp+2B8h+CachePolicy], 0ADFh
0x180066925  xor     r8d, r8d
0x180066928  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x18006692f  call    McTemplateU0psq_EventWriteTransfer
0x180066934  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x18006693b  call    cs:__imp_ReleaseMutex
0x180066942  nop     dword ptr [rax+rax+00h]
0x180066947  mov     eax, 8
0x18006694c  jmp     loc_180066B80
0x180066951  mov     ebx, 6
0x180066956  mov     rax, [rsi+28h]
0x18006695a  lea     rdx, aSHttpsendhttpr; "%s: HttpSendHttpResponse: %d."
0x180066961  mov     r9d, ebx
0x180066964  mov     ecx, 10000000h
0x180066969  mov     r8, [rax+120h]
0x180066970  add     r8, 38h ; '8'
0x180066974  call    EventWrite0
0x180066979  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180066980  jz      loc_180066B7E
0x180066986  mov     rax, [rsi+28h]
0x18006698a  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_SEND_RESPONSE
0x180066991  mov     r9d, ebx
0x180066994  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18006699b  mov     r8, [rax+120h]
0x1800669a2  add     r8, 38h ; '8'
0x1800669a6  call    McTemplateU0zq_EventWriteTransfer
0x1800669ab  jmp     loc_180066B7E
0x1800669b0  mov     dword ptr [rax+64h], 0BF1Dh
0x1800669b7  jmp     short loc_1800669CE
0x1800669b9  lea     rdi, [rax-30h]
0x1800669bd  mov     rax, [rax]
0x1800669c0  mov     [rbp+498h], rax
0x1800669c7  lock dec dword ptr [rbp+4A4h]
0x1800669ce  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x1800669d5  call    cs:__imp_ReleaseMutex
0x1800669dc  nop     dword ptr [rax+rax+00h]
0x1800669e1  mov     r8, rbx; Size
0x1800669e4  xor     edx, edx; Val
0x1800669e6  mov     rcx, rdi; void *
0x1800669e9  call    memset_0
0x1800669ee  mov     dword ptr [rdi+64h], 0BF20h
0x1800669f5  lea     rbp, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800669fc  mov     dword ptr [rdi+20h], 0E476h
0x180066a03  lea     rdx, aSReferenceClie; "(%s: Reference client context (%p)%S:%d"
0x180066a0a  mov     rax, [rsi+28h]
0x180066a0e  mov     ebx, 0AF2h
0x180066a13  mov     dword ptr [rsp+2B8h+BytesSent], ebx
0x180066a17  mov     r9, rsi
0x180066a1a  mov     ecx, 20000000h
0x180066a1f  mov     [rsp+2B8h+CachePolicy], rbp
0x180066a24  mov     r8, [rax+120h]
0x180066a2b  add     r8, 38h ; '8'
0x180066a2f  call    EventWrite0
0x180066a34  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180066a3b  jz      short loc_180066A53
0x180066a3d  mov     r9, rbp
0x180066a40  mov     dword ptr [rsp+2B8h+CachePolicy], ebx
0x180066a44  mov     r8, rsi
0x180066a47  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_REFERENCE
0x180066a4e  call    McTemplateU0psq_EventWriteTransfer
0x180066a53  lock inc dword ptr [rsi+38h]
0x180066a57  mov     [rdi+58h], rsi
0x180066a5b  lea     rax, SendBufferCleanup
0x180066a62  mov     [rdi+88h], rax
0x180066a69  mov     dword ptr [rdi+50h], 1
0x180066a70  mov     rcx, [rsi+28h]
0x180066a74  mov     rcx, [rcx+60h]; pio
0x180066a78  call    cs:__imp_StartThreadpoolIo
0x180066a7f  nop     dword ptr [rax+rax+00h]
0x180066a84  mov     rcx, [rsi+28h]
0x180066a88  add     rcx, 50h ; 'P'
0x180066a8c  call    RoReferenceEx
0x180066a91  test    al, al
0x180066a93  jz      short loc_180066AED
0x180066a95  mov     rcx, [rsi+28h]
0x180066a99  lea     r9, [rdi+898h]; EntityBuffer
0x180066aa0  mov     rdx, [rsi+30h]; RequestId
0x180066aa4  xor     r8d, r8d; Flags
0x180066aa7  mov     [rsp+2B8h+Reserved1], rdi; Overlapped
0x180066aac  mov     [rsp+2B8h+BytesSent], 0; BytesReturned
0x180066ab5  mov     rcx, [rcx+48h]; RequestQueueHandle
0x180066ab9  mov     dword ptr [rsp+2B8h+CachePolicy], 7800h; EntityBufferLength
0x180066ac1  call    cs:__imp_HttpReceiveRequestEntityBody
0x180066ac8  nop     dword ptr [rax+rax+00h]
0x180066acd  mov     ebx, eax
0x180066acf  cmp     eax, 3E5h
0x180066ad4  jz      loc_180066B7E
0x180066ada  test    eax, eax
0x180066adc  jz      loc_180066B7E
0x180066ae2  mov     rcx, [rsi+28h]
0x180066ae6  call    IpTlsServerDereferenceHttpQueue
0x180066aeb  jmp     short loc_180066AF2
0x180066aed  mov     ebx, 6
0x180066af2  mov     rax, [rsi+28h]
0x180066af6  lea     rdx, aSHttpreceivere; "%s: HttpReceiveRequestEntityBody: %d."
0x180066afd  mov     r9d, ebx
0x180066b00  mov     ecx, 10000000h
0x180066b05  mov     r8, [rax+120h]
0x180066b0c  add     r8, 38h ; '8'
0x180066b10  call    EventWrite0
0x180066b15  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180066b1c  jz      short loc_180066B43
0x180066b1e  mov     rax, [rsi+28h]
0x180066b22  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_RECEIVE_ENTITY
0x180066b29  mov     r9d, ebx
0x180066b2c  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180066b33  mov     r8, [rax+120h]
0x180066b3a  add     r8, 38h ; '8'
0x180066b3e  call    McTemplateU0zq_EventWriteTransfer
0x180066b43  mov     rcx, [rsi+28h]
0x180066b47  mov     rcx, [rcx+60h]; pio
0x180066b4b  call    cs:__imp_CancelThreadpoolIo
0x180066b52  nop     dword ptr [rax+rax+00h]
0x180066b57  mov     r9, rbp
0x180066b5a  mov     dword ptr [rsp+2B8h+CachePolicy], 0B19h
0x180066b62  mov     r8, rdi
0x180066b65  lea     rdx, aDereferenceIpt; "(Dereference IPTLS Buffer(%p)%S:%d"
0x180066b6c  mov     ecx, 20000000h
0x180066b71  call    EventWrite0
0x180066b76  mov     rcx, rdi
0x180066b79  call    IpTlsDereferenceBufferEx
0x180066b7e  mov     eax, ebx
0x180066b80  add     rsp, 298h
0x180066b87  pop     rdi
0x180066b88  pop     rsi
0x180066b89  pop     rbp
0x180066b8a  pop     rbx
0x180066b8b  retn
```
