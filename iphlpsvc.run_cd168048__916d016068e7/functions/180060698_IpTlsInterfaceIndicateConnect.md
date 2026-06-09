# IpTlsInterfaceIndicateConnect

- ea: `0x180060698`
- end: `0x180060b47`
- name: `IpTlsInterfaceIndicateConnect`
- size: `1199`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18005fa9c`
- `0x180063280`

## callees

- `0x18000d7b0`
- `0x180013570`
- `0x1800159c4`
- `0x180030b10`
- `0x180031df0`
- `0x180040dd0`
- `0x18004b630`
- `0x18004c1c8`
- `0x1800502b4`
- `0x18005fe8c`
- `0x180060698`
- `0x180068e3c`
- `0x18006909c`

## import_xrefs

- `IPHLPAPI!GetBestRoute2` at `0x180060a22`
- `IPHLPAPI!GetBestRoute2` at `0x180060a22`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800607d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800608b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180060932`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180060a62`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180060b0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800607d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800608b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180060932`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180060a62`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180060b0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060869`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006097b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060ac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060869`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006097b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060ac4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006084c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006084c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180060ab4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180060ab4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x18006091b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x18006091b`
- `webio!__imp_WebQueryHttpRequestOption` at `0x180060730`
- `webio!__imp_WebQueryHttpRequestOption` at `0x180060730`

## string_xrefs

- `0x180060881`: `%s:CreateFile faied. Status:%d`

## pseudocode

```c
DWORD __fastcall IpTlsInterfaceIndicateConnect(__int64 a1, unsigned int a2)
{
  _QWORD *LastError; // rsi
  __int64 v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // eax
  HANDLE FileW; // rax
  DWORD v10; // eax
  int v11; // ebx
  unsigned int BestRoute2; // eax
  void *v13; // rcx
  DWORD v14; // esi
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  SOCKADDR_INET BestSourceAddress; // [rsp+50h] [rbp-B0h] BYREF
  struct _MIB_IPFORWARD_ROW2 BestRoute; // [rsp+70h] [rbp-90h] BYREF
  SOCKADDR_INET SourceAddress; // [rsp+E0h] [rbp-20h] BYREF
  SOCKADDR_INET DestinationAddress; // [rsp+160h] [rbp+60h] BYREF

  memset_0(&SourceAddress, 0, 0x100u);
  LastError = *(_QWORD **)(a1 + 1104);
  v16 = 0;
  memset_0(&BestRoute, 0, sizeof(BestRoute));
  IpTlsAdjustCorpConnectivityTimeout(v5, a2);
  if ( !*(_DWORD *)(a1 + 1012) )
  {
    v6 = WebQueryHttpRequestOption(*LastError, 22, &SourceAddress, 256, &v16);
    LODWORD(LastError) = v6;
    if ( v6 )
    {
      EventWrite0(0x10000000, L"%s:WebQueryHttpRequestOption faied. Status:%d", a1 + 56, v6);
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEDIA_CONNECT,
          a1 + 56,
          (unsigned int)LastError);
      return (unsigned int)LastError;
    }
    v7 = SplTunMgrTunnelConnect(a1 + 1056, &SourceAddress, &DestinationAddress);
    LODWORD(LastError) = v7;
    if ( v7 )
    {
      EventWrite0(0x10000000, L"%s:SplTunMgrTunnelConnect faied. Status:%d", a1 + 56, v7);
      return (unsigned int)LastError;
    }
  }
  IpTlsAcquireLock(g_IpTlsInterfaceListLock);
  if ( (*(_BYTE *)(a1 + 1032) & 2) != 0 )
  {
    ReleaseMutex(g_IpTlsInterfaceListLock);
    if ( !*(_DWORD *)(a1 + 1012) )
      SplTunMgrTunnelDisconnect();
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEDIA_CONNECT,
        a1 + 56,
        5023);
    return 5023;
  }
  *(_QWORD *)(a1 + 1096) = 0;
  FileW = CreateFileW(g_IpTlsTunnelDeviceName, 0xC0000000, 0, 0, 3u, 0x40000000u, 0);
  *(_QWORD *)(a1 + 1072) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = (_QWORD *)GetLastError();
    EventWrite0(0x10000000, L"%s:CreateFile faied. Status:%d", a1 + 56, LastError);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEDIA_CONNECT,
        a1 + 56,
        (unsigned int)LastError);
    ReleaseMutex(g_IpTlsInterfaceListLock);
    if ( *(_DWORD *)(a1 + 1012) )
    {
      if ( (Microsoft_Windows_IphlpsvcEnableBits & 2) != 0 )
        McTemplateU0qq_EventWriteTransfer(
          MS_IPHLPSVC_EVENTS_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_IPHTTPS_SERVER_START_FAILED,
          (unsigned int)LastError,
          2);
      return (unsigned int)LastError;
    }
    goto LABEL_37;
  }
  *(_DWORD *)(a1 + 1080) = 2;
  if ( BindIoCompletionCallback(FileW, IpTlsTunnelIoCompletionHandler, 0) )
  {
    if ( (*(_BYTE *)(a1 + 1032) & 1) != 0 )
    {
      v11 = 100;
      do
      {
        IpTlsPrepostBufferUnderLock(a1);
        --v11;
      }
      while ( v11 );
    }
    EventWrite0(0x10000000, L"%s:Interface media connect indicated", a1 + 56);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEDIA_CONNECT,
        a1 + 56,
        0);
    if ( !*(_DWORD *)(a1 + 1012) )
    {
      memset(&BestSourceAddress, 0, sizeof(BestSourceAddress));
      BestRoute2 = GetBestRoute2(0, 0, &SourceAddress, &DestinationAddress, 0, &BestRoute, &BestSourceAddress);
      LODWORD(LastError) = BestRoute2;
      if ( BestRoute2 )
      {
        EventWrite0(0x10000000, L"%s:GetBestRoute2 failed. Status:%d", a1 + 56, BestRoute2);
LABEL_36:
        ReleaseMutex(g_IpTlsInterfaceListLock);
LABEL_37:
        SplTunMgrTunnelDisconnect();
        return (unsigned int)LastError;
      }
      if ( !(unsigned __int8)RoReferenceEx(a1 + 1080) )
      {
        LODWORD(LastError) = 5023;
        goto LABEL_36;
      }
      v13 = *(void **)(a1 + 1072);
      v14 = 0;
      BytesReturned = 0;
      if ( !DeviceIoControl(v13, 0x12CC34u, &BestRoute, 8u, 0, 0, &BytesReturned, 0) )
        v14 = GetLastError();
      EventWrite0(0x10000000, L"Ioctl %d returned Status %d", 1231924, v14);
      if ( v14 )
        EventWrite0(0x10000000, L"%s:IOCTL Plumb Real Interface failed. Status:%d", a1 + 56, v14);
      IpTlsDereferenceTunnelHandle(a1);
    }
    ReleaseMutex(g_IpTlsInterfaceListLock);
    return 0;
  }
  ReleaseMutex(g_IpTlsInterfaceListLock);
  if ( !*(_DWORD *)(a1 + 1012) )
    SplTunMgrTunnelDisconnect();
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
  {
    v10 = GetLastError();
    McTemplateU0zq_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEDIA_CONNECT,
      a1 + 56,
      v10);
  }
  return GetLastError();
}

```

## disassembly

```asm
0x180060698  mov     [rsp-8+arg_10], rbx
0x18006069d  mov     [rsp-8+arg_18], rsi
0x1800606a2  push    rbp
0x1800606a3  push    rdi
0x1800606a4  push    r12
0x1800606a6  push    r14
0x1800606a8  push    r15
0x1800606aa  lea     rbp, [rsp-0F0h]
0x1800606b2  sub     rsp, 1F0h
0x1800606b9  mov     rax, cs:__security_cookie
0x1800606c0  xor     rax, rsp
0x1800606c3  mov     [rbp+110h+var_30], rax
0x1800606ca  mov     ebx, edx
0x1800606cc  mov     rdi, rcx
0x1800606cf  mov     r14d, 100h
0x1800606d5  lea     rcx, [rbp+110h+SourceAddress]; void *
0x1800606d9  mov     r8d, r14d; Size
0x1800606dc  xor     edx, edx; Val
0x1800606de  call    memset_0
0x1800606e3  mov     rsi, [rdi+450h]
0x1800606ea  lea     rcx, [rsp+210h+BestRoute]; void *
0x1800606ef  xor     r12d, r12d
0x1800606f2  xor     edx, edx; Val
0x1800606f4  mov     [rsp+210h+var_1C8], r12
0x1800606f9  lea     r8d, [r12+68h]; Size
0x1800606fe  call    memset_0
0x180060703  mov     edx, ebx
0x180060705  call    IpTlsAdjustCorpConnectivityTimeout
0x18006070a  cmp     [rdi+3F4h], r12d
0x180060711  jnz     loc_1800607B8
0x180060717  mov     rcx, [rsi]
0x18006071a  lea     rax, [rsp+210h+var_1C8]
0x18006071f  mov     r9d, r14d
0x180060722  mov     qword ptr [rsp+210h+dwCreationDisposition], rax
0x180060727  lea     r8, [rbp+110h+SourceAddress]
0x18006072b  lea     edx, [r12+16h]
0x180060730  call    cs:__imp_WebQueryHttpRequestOption
0x180060737  nop     dword ptr [rax+rax+00h]
0x18006073c  mov     esi, eax
0x18006073e  test    eax, eax
0x180060740  jnz     short loc_18006077B
0x180060742  lea     rcx, [rdi+420h]
0x180060749  lea     r8, [rbp+110h+DestinationAddress]
0x18006074d  lea     rdx, [rbp+110h+SourceAddress]
0x180060751  call    SplTunMgrTunnelConnect
0x180060756  mov     esi, eax
0x180060758  test    eax, eax
0x18006075a  jz      short loc_1800607B8
0x18006075c  lea     r8, [rdi+38h]
0x180060760  mov     r9d, eax
0x180060763  lea     rdx, aSSpltunmgrtunn; "%s:SplTunMgrTunnelConnect faied. Status"...
0x18006076a  mov     ecx, 10000000h
0x18006076f  call    EventWrite0
0x180060774  mov     eax, esi
0x180060776  jmp     loc_180060B1B
0x18006077b  mov     r9d, esi
0x18006077e  lea     r8, [rdi+38h]
0x180060782  lea     rdx, aSWebqueryhttpr_1; "%s:WebQueryHttpRequestOption faied. Sta"...
0x180060789  mov     ecx, 10000000h
0x18006078e  call    EventWrite0
0x180060793  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18006079a  jz      short loc_180060774
0x18006079c  mov     r9d, esi
0x18006079f  lea     r8, [rdi+38h]
0x1800607a3  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEDIA_CONNECT
0x1800607aa  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800607b1  call    McTemplateU0zq_EventWriteTransfer
0x1800607b6  jmp     short loc_180060774
0x1800607b8  mov     rcx, cs:g_IpTlsInterfaceListLock
0x1800607bf  call    IpTlsAcquireLock
0x1800607c4  test    byte ptr [rdi+408h], 2
0x1800607cb  jz      short loc_18006081E
0x1800607cd  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x1800607d4  call    cs:__imp_ReleaseMutex
0x1800607db  nop     dword ptr [rax+rax+00h]
0x1800607e0  cmp     [rdi+3F4h], r12d
0x1800607e7  jnz     short loc_1800607EE
0x1800607e9  call    SplTunMgrTunnelDisconnect
0x1800607ee  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x1800607f5  jz      short loc_180060814
0x1800607f7  lea     r8, [rdi+38h]
0x1800607fb  mov     r9d, 139Fh
0x180060801  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEDIA_CONNECT
0x180060808  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18006080f  call    McTemplateU0zq_EventWriteTransfer
0x180060814  mov     eax, 139Fh
0x180060819  jmp     loc_180060B1B
0x18006081e  mov     [rsp+210h+hTemplateFile], r12; hTemplateFile
0x180060823  lea     rcx, g_IpTlsTunnelDeviceName; "\\\\.\\\\IpHttpsDevice"
0x18006082a  mov     [rsp+210h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180060832  xor     r9d, r9d; lpSecurityAttributes
0x180060835  xor     r8d, r8d; dwShareMode
0x180060838  mov     [rsp+210h+dwCreationDisposition], 3; dwCreationDisposition
0x180060840  mov     edx, 0C0000000h; dwDesiredAccess
0x180060845  mov     [rdi+448h], r12
0x18006084c  call    cs:__imp_CreateFileW
0x180060853  nop     dword ptr [rax+rax+00h]
0x180060858  mov     [rdi+430h], rax
0x18006085f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180060863  jnz     loc_180060900
0x180060869  call    cs:__imp_GetLastError
0x180060870  nop     dword ptr [rax+rax+00h]
0x180060875  lea     r8, [rdi+38h]
0x180060879  mov     ecx, 10000000h
0x18006087e  mov     r9d, eax
0x180060881  lea     rdx, aSCreatefileFai; "%s:CreateFile faied. Status:%d"
0x180060888  mov     esi, eax
0x18006088a  call    EventWrite0
0x18006088f  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x180060896  jz      short loc_1800608B2
0x180060898  mov     r9d, esi
0x18006089b  lea     r8, [rdi+38h]
0x18006089f  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEDIA_CONNECT
0x1800608a6  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800608ad  call    McTemplateU0zq_EventWriteTransfer
0x1800608b2  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x1800608b9  call    cs:__imp_ReleaseMutex
0x1800608c0  nop     dword ptr [rax+rax+00h]
0x1800608c5  cmp     [rdi+3F4h], r12d
0x1800608cc  jz      loc_180060A6E
0x1800608d2  test    cs:Microsoft_Windows_IphlpsvcEnableBits, 2
0x1800608d9  jz      loc_180060774
0x1800608df  mov     r9d, 2
0x1800608e5  lea     rdx, EVENT_IPHLPSVC_IPHTTPS_SERVER_START_FAILED
0x1800608ec  mov     r8d, esi
0x1800608ef  lea     rcx, MS_IPHLPSVC_EVENTS_PROVIDER_ID_Context
0x1800608f6  call    McTemplateU0qq_EventWriteTransfer
0x1800608fb  jmp     loc_180060774
0x180060900  lea     r15, [rdi+438h]
0x180060907  xor     r8d, r8d; Flags
0x18006090a  lea     rdx, IpTlsTunnelIoCompletionHandler; Function
0x180060911  mov     dword ptr [r15], 2
0x180060918  mov     rcx, rax; FileHandle
0x18006091b  call    cs:__imp_BindIoCompletionCallback
0x180060922  nop     dword ptr [rax+rax+00h]
0x180060927  test    eax, eax
0x180060929  jnz     short loc_18006098C
0x18006092b  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x180060932  call    cs:__imp_ReleaseMutex
0x180060939  nop     dword ptr [rax+rax+00h]
0x18006093e  cmp     [rdi+3F4h], r12d
0x180060945  jnz     short loc_18006094C
0x180060947  call    SplTunMgrTunnelDisconnect
0x18006094c  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x180060953  jz      short loc_18006097B
0x180060955  call    cs:__imp_GetLastError
0x18006095c  nop     dword ptr [rax+rax+00h]
0x180060961  mov     r9d, eax
0x180060964  lea     r8, [rdi+38h]
0x180060968  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEDIA_CONNECT
0x18006096f  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180060976  call    McTemplateU0zq_EventWriteTransfer
0x18006097b  call    cs:__imp_GetLastError
0x180060982  nop     dword ptr [rax+rax+00h]
0x180060987  jmp     loc_180060B1B
0x18006098c  test    byte ptr [rdi+408h], 1
0x180060993  jz      short loc_1800609A7
0x180060995  mov     ebx, 64h ; 'd'
0x18006099a  mov     rcx, rdi
0x18006099d  call    IpTlsPrepostBufferUnderLock
0x1800609a2  add     ebx, 0FFFFFFFFh
0x1800609a5  jnz     short loc_18006099A
0x1800609a7  lea     r14, [rdi+38h]
0x1800609ab  mov     ebx, 10000000h
0x1800609b0  mov     r8, r14
0x1800609b3  lea     rdx, aSInterfaceMedi_0; "%s:Interface media connect indicated"
0x1800609ba  mov     ecx, ebx
0x1800609bc  call    EventWrite0
0x1800609c1  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x1800609c8  jz      short loc_1800609E3
0x1800609ca  xor     r9d, r9d
0x1800609cd  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEDIA_CONNECT
0x1800609d4  mov     r8, r14
0x1800609d7  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800609de  call    McTemplateU0zq_EventWriteTransfer
0x1800609e3  cmp     [rdi+3F4h], r12d
0x1800609ea  jnz     loc_180060B06
0x1800609f0  xorps   xmm0, xmm0
0x1800609f3  lea     rax, [rsp+210h+BestSourceAddress]
0x1800609f8  mov     [rsp+210h+hTemplateFile], rax; BestSourceAddress
0x1800609fd  lea     r9, [rbp+110h+DestinationAddress]; DestinationAddress
0x180060a01  lea     rax, [rsp+210h+BestRoute]
0x180060a06  xor     edx, edx; InterfaceIndex
0x180060a08  mov     qword ptr [rsp+210h+dwFlagsAndAttributes], rax; BestRoute
0x180060a0d  lea     r8, [rbp+110h+SourceAddress]; SourceAddress
0x180060a11  movups  xmmword ptr [rsp+210h+BestSourceAddress], xmm0
0x180060a16  xor     ecx, ecx; InterfaceLuid
0x180060a18  mov     [rsp+210h+dwCreationDisposition], r12d; AddressSortOptions
0x180060a1d  movups  xmmword ptr [rsp+210h+BestSourceAddress+0Ch], xmm0
0x180060a22  call    cs:__imp_GetBestRoute2
0x180060a29  nop     dword ptr [rax+rax+00h]
0x180060a2e  mov     esi, eax
0x180060a30  test    eax, eax
0x180060a32  jz      short loc_180060A4A
0x180060a34  mov     r9d, eax
0x180060a37  lea     rdx, aSGetbestroute2; "%s:GetBestRoute2 failed. Status:%d"
0x180060a3e  mov     r8, r14
0x180060a41  mov     ecx, ebx
0x180060a43  call    EventWrite0
0x180060a48  jmp     short loc_180060A5B
0x180060a4a  mov     rcx, r15
0x180060a4d  call    RoReferenceEx
0x180060a52  test    al, al
0x180060a54  jnz     short loc_180060A78
0x180060a56  mov     esi, 139Fh
0x180060a5b  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x180060a62  call    cs:__imp_ReleaseMutex
0x180060a69  nop     dword ptr [rax+rax+00h]
0x180060a6e  call    SplTunMgrTunnelDisconnect
0x180060a73  jmp     loc_180060774
0x180060a78  mov     rcx, [rdi+430h]; hDevice
0x180060a7f  lea     rax, [rsp+210h+BytesReturned]
0x180060a84  mov     [rsp+210h+lpOverlapped], r12; lpOverlapped
0x180060a89  lea     r8, [rsp+210h+BestRoute]; lpInBuffer
0x180060a8e  mov     [rsp+210h+hTemplateFile], rax; lpBytesReturned
0x180060a93  mov     r15d, 12CC34h
0x180060a99  mov     [rsp+210h+dwFlagsAndAttributes], r12d; nOutBufferSize
0x180060a9e  mov     r9d, 8; nInBufferSize
0x180060aa4  mov     edx, r15d; dwIoControlCode
0x180060aa7  mov     qword ptr [rsp+210h+dwCreationDisposition], r12; lpOutBuffer
0x180060aac  mov     esi, r12d
0x180060aaf  mov     [rsp+210h+BytesReturned], r12d
0x180060ab4  call    cs:__imp_DeviceIoControl
0x180060abb  nop     dword ptr [rax+rax+00h]
0x180060ac0  test    eax, eax
0x180060ac2  jnz     short loc_180060AD2
0x180060ac4  call    cs:__imp_GetLastError
0x180060acb  nop     dword ptr [rax+rax+00h]
0x180060ad0  mov     esi, eax
0x180060ad2  mov     r9d, esi
0x180060ad5  lea     rdx, aIoctlDReturned; "Ioctl %d returned Status %d"
0x180060adc  mov     r8d, r15d
0x180060adf  mov     ecx, ebx
0x180060ae1  call    EventWrite0
0x180060ae6  test    esi, esi
0x180060ae8  jz      short loc_180060AFE
0x180060aea  mov     r9d, esi
0x180060aed  lea     rdx, aSIoctlPlumbRea; "%s:IOCTL Plumb Real Interface failed. S"...
0x180060af4  mov     r8, r14
0x180060af7  mov     ecx, ebx
0x180060af9  call    EventWrite0
0x180060afe  mov     rcx, rdi
0x180060b01  call    IpTlsDereferenceTunnelHandle
0x180060b06  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x180060b0d  call    cs:__imp_ReleaseMutex
0x180060b14  nop     dword ptr [rax+rax+00h]
0x180060b19  xor     eax, eax
0x180060b1b  mov     rcx, [rbp+110h+var_30]
0x180060b22  xor     rcx, rsp; StackCookie
0x180060b25  call    __security_check_cookie
0x180060b2a  lea     r11, [rsp+210h+var_20]
0x180060b32  mov     rbx, [r11+40h]
0x180060b36  mov     rsi, [r11+48h]
0x180060b3a  mov     rsp, r11
0x180060b3d  pop     r15
0x180060b3f  pop     r14
0x180060b41  pop     r12
0x180060b43  pop     rdi
0x180060b44  pop     rbp
0x180060b45  retn
```
