# PostReceiveEntityOnServer

- ea: `0x180066818`
- end: `0x180066bad`
- name: `PostReceiveEntityOnServer`
- size: `917`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180046434`
- `0x180065860`
- `0x180066bb4`

## callees

- `0x18000d7c0`
- `0x180012dcc`
- `0x180013580`
- `0x1800159d4`
- `0x180030d34`
- `0x180040d90`
- `0x18004c188`
- `0x1800616b4`
- `0x180066148`
- `0x180066818`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006695b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800669f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006695b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800669f5`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180066b6b`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180066b6b`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180066a98`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180066a98`
- `HTTPAPI!HttpSendHttpResponse` at `0x1800668de`
- `HTTPAPI!HttpSendHttpResponse` at `0x1800668de`
- `HTTPAPI!HttpReceiveRequestEntityBody` at `0x180066ae1`
- `HTTPAPI!HttpReceiveRequestEntityBody` at `0x180066ae1`

## string_xrefs

- `0x180066936`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180066a15`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

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
0x180066818  push    rbx
0x18006681a  push    rbp
0x18006681b  push    rsi
0x18006681c  push    rdi
0x18006681d  sub     rsp, 298h
0x180066824  mov     dil, r8b
0x180066827  mov     rbx, rdx
0x18006682a  mov     rsi, rcx
0x18006682d  xor     edx, edx; Val
0x18006682f  mov     r8d, 238h; Size
0x180066835  lea     rcx, [rsp+2B8h+HttpResponse]; void *
0x18006683a  call    memset_0
0x18006683f  mov     rax, [rsi+28h]
0x180066843  mov     [rsp+2B8h+arg_10], 0
0x18006684e  mov     rbp, [rax+120h]
0x180066855  mov     qword ptr [rbx], 0
0x18006685c  test    dil, dil
0x18006685f  jz      loc_1800668F9
0x180066865  mov     rcx, [rsi+28h]
0x180066869  lea     rax, aOk; "OK"
0x180066870  add     rcx, 50h ; 'P'
0x180066874  mov     dword ptr [rsp+2B8h+HttpResponse.StatusCode], 200C8h
0x18006687c  mov     [rsp+2B8h+HttpResponse.pReason], rax
0x180066881  mov     r8d, 2
0x180066887  call    RoReferenceEx
0x18006688c  test    al, al
0x18006688e  jz      loc_180066971
0x180066894  mov     rcx, [rsi+28h]
0x180066898  lea     rax, [rsp+2B8h+arg_10]
0x1800668a0  mov     rdx, [rsi+30h]; RequestId
0x1800668a4  lea     r9, [rsp+2B8h+HttpResponse]; HttpResponse
0x1800668a9  mov     [rsp+2B8h+LogData], 0; LogData
0x1800668b2  mov     [rsp+2B8h+Overlapped], 0; Overlapped
0x1800668bb  mov     rcx, [rcx+48h]; RequestQueueHandle
0x1800668bf  mov     [rsp+2B8h+Reserved2], 0; Reserved2
0x1800668c7  mov     [rsp+2B8h+Reserved1], 0; Reserved1
0x1800668d0  mov     [rsp+2B8h+BytesSent], rax; BytesSent
0x1800668d5  mov     [rsp+2B8h+CachePolicy], 0; CachePolicy
0x1800668de  call    cs:__imp_HttpSendHttpResponse
0x1800668e5  nop     dword ptr [rax+rax+00h]
0x1800668ea  mov     rcx, [rsi+28h]
0x1800668ee  mov     ebx, eax
0x1800668f0  call    IpTlsServerDereferenceHttpQueue
0x1800668f5  test    ebx, ebx
0x1800668f7  jnz     short loc_180066976
0x1800668f9  mov     rcx, cs:g_IpTlsInterfaceListLock
0x180066900  call    IpTlsAcquireLock
0x180066905  mov     rax, [rbp+498h]
0x18006690c  mov     ebx, 80A0h
0x180066911  test    rax, rax
0x180066914  jnz     loc_1800669D9
0x18006691a  mov     ecx, ebx; dwBytes
0x18006691c  call    MALLOC
0x180066921  mov     rdi, rax
0x180066924  test    rax, rax
0x180066927  jnz     loc_1800669D0
0x18006692d  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180066934  jz      short loc_180066954
0x180066936  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006693d  mov     dword ptr [rsp+2B8h+CachePolicy], 0ADFh
0x180066945  xor     r8d, r8d
0x180066948  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x18006694f  call    McTemplateU0psq_EventWriteTransfer
0x180066954  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x18006695b  call    cs:__imp_ReleaseMutex
0x180066962  nop     dword ptr [rax+rax+00h]
0x180066967  mov     eax, 8
0x18006696c  jmp     loc_180066BA0
0x180066971  mov     ebx, 6
0x180066976  mov     rax, [rsi+28h]
0x18006697a  lea     rdx, aSHttpsendhttpr; "%s: HttpSendHttpResponse: %d."
0x180066981  mov     r9d, ebx
0x180066984  mov     ecx, 10000000h
0x180066989  mov     r8, [rax+120h]
0x180066990  add     r8, 38h ; '8'
0x180066994  call    EventWrite0
0x180066999  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x1800669a0  jz      loc_180066B9E
0x1800669a6  mov     rax, [rsi+28h]
0x1800669aa  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_SEND_RESPONSE
0x1800669b1  mov     r9d, ebx
0x1800669b4  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800669bb  mov     r8, [rax+120h]
0x1800669c2  add     r8, 38h ; '8'
0x1800669c6  call    McTemplateU0zq_EventWriteTransfer
0x1800669cb  jmp     loc_180066B9E
0x1800669d0  mov     dword ptr [rax+64h], 0BF1Dh
0x1800669d7  jmp     short loc_1800669EE
0x1800669d9  lea     rdi, [rax-30h]
0x1800669dd  mov     rax, [rax]
0x1800669e0  mov     [rbp+498h], rax
0x1800669e7  lock dec dword ptr [rbp+4A4h]
0x1800669ee  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x1800669f5  call    cs:__imp_ReleaseMutex
0x1800669fc  nop     dword ptr [rax+rax+00h]
0x180066a01  mov     r8, rbx; Size
0x180066a04  xor     edx, edx; Val
0x180066a06  mov     rcx, rdi; void *
0x180066a09  call    memset_0
0x180066a0e  mov     dword ptr [rdi+64h], 0BF20h
0x180066a15  lea     rbp, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180066a1c  mov     dword ptr [rdi+20h], 0E476h
0x180066a23  lea     rdx, aSReferenceClie; "(%s: Reference client context (%p)%S:%d"
0x180066a2a  mov     rax, [rsi+28h]
0x180066a2e  mov     ebx, 0AF2h
0x180066a33  mov     dword ptr [rsp+2B8h+BytesSent], ebx
0x180066a37  mov     r9, rsi
0x180066a3a  mov     ecx, 20000000h
0x180066a3f  mov     [rsp+2B8h+CachePolicy], rbp
0x180066a44  mov     r8, [rax+120h]
0x180066a4b  add     r8, 38h ; '8'
0x180066a4f  call    EventWrite0
0x180066a54  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180066a5b  jz      short loc_180066A73
0x180066a5d  mov     r9, rbp
0x180066a60  mov     dword ptr [rsp+2B8h+CachePolicy], ebx
0x180066a64  mov     r8, rsi
0x180066a67  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_REFERENCE
0x180066a6e  call    McTemplateU0psq_EventWriteTransfer
0x180066a73  lock inc dword ptr [rsi+38h]
0x180066a77  mov     [rdi+58h], rsi
0x180066a7b  lea     rax, SendBufferCleanup
0x180066a82  mov     [rdi+88h], rax
0x180066a89  mov     dword ptr [rdi+50h], 1
0x180066a90  mov     rcx, [rsi+28h]
0x180066a94  mov     rcx, [rcx+60h]; pio
0x180066a98  call    cs:__imp_StartThreadpoolIo
0x180066a9f  nop     dword ptr [rax+rax+00h]
0x180066aa4  mov     rcx, [rsi+28h]
0x180066aa8  add     rcx, 50h ; 'P'
0x180066aac  call    RoReferenceEx
0x180066ab1  test    al, al
0x180066ab3  jz      short loc_180066B0D
0x180066ab5  mov     rcx, [rsi+28h]
0x180066ab9  lea     r9, [rdi+898h]; EntityBuffer
0x180066ac0  mov     rdx, [rsi+30h]; RequestId
0x180066ac4  xor     r8d, r8d; Flags
0x180066ac7  mov     [rsp+2B8h+Reserved1], rdi; Overlapped
0x180066acc  mov     [rsp+2B8h+BytesSent], 0; BytesReturned
0x180066ad5  mov     rcx, [rcx+48h]; RequestQueueHandle
0x180066ad9  mov     dword ptr [rsp+2B8h+CachePolicy], 7800h; EntityBufferLength
0x180066ae1  call    cs:__imp_HttpReceiveRequestEntityBody
0x180066ae8  nop     dword ptr [rax+rax+00h]
0x180066aed  mov     ebx, eax
0x180066aef  cmp     eax, 3E5h
0x180066af4  jz      loc_180066B9E
0x180066afa  test    eax, eax
0x180066afc  jz      loc_180066B9E
0x180066b02  mov     rcx, [rsi+28h]
0x180066b06  call    IpTlsServerDereferenceHttpQueue
0x180066b0b  jmp     short loc_180066B12
0x180066b0d  mov     ebx, 6
0x180066b12  mov     rax, [rsi+28h]
0x180066b16  lea     rdx, aSHttpreceivere; "%s: HttpReceiveRequestEntityBody: %d."
0x180066b1d  mov     r9d, ebx
0x180066b20  mov     ecx, 10000000h
0x180066b25  mov     r8, [rax+120h]
0x180066b2c  add     r8, 38h ; '8'
0x180066b30  call    EventWrite0
0x180066b35  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180066b3c  jz      short loc_180066B63
0x180066b3e  mov     rax, [rsi+28h]
0x180066b42  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_RECEIVE_ENTITY
0x180066b49  mov     r9d, ebx
0x180066b4c  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180066b53  mov     r8, [rax+120h]
0x180066b5a  add     r8, 38h ; '8'
0x180066b5e  call    McTemplateU0zq_EventWriteTransfer
0x180066b63  mov     rcx, [rsi+28h]
0x180066b67  mov     rcx, [rcx+60h]; pio
0x180066b6b  call    cs:__imp_CancelThreadpoolIo
0x180066b72  nop     dword ptr [rax+rax+00h]
0x180066b77  mov     r9, rbp
0x180066b7a  mov     dword ptr [rsp+2B8h+CachePolicy], 0B19h
0x180066b82  mov     r8, rdi
0x180066b85  lea     rdx, aDereferenceIpt; "(Dereference IPTLS Buffer(%p)%S:%d"
0x180066b8c  mov     ecx, 20000000h
0x180066b91  call    EventWrite0
0x180066b96  mov     rcx, rdi
0x180066b99  call    IpTlsDereferenceBufferEx
0x180066b9e  mov     eax, ebx
0x180066ba0  add     rsp, 298h
0x180066ba7  pop     rdi
0x180066ba8  pop     rsi
0x180066ba9  pop     rbp
0x180066baa  pop     rbx
0x180066bab  retn
```
