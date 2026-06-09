# IpTlsInterfaceIndicateConnect

- ea: `0x1800606b8`
- end: `0x180060b67`
- name: `IpTlsInterfaceIndicateConnect`
- size: `1199`
- prototype: `DWORD __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18005fabc`
- `0x1800632a0`

## callees

- `0x18000d7c0`
- `0x180013580`
- `0x1800159d4`
- `0x180030b20`
- `0x180031e00`
- `0x180040d90`
- `0x18004b5f0`
- `0x18004c188`
- `0x180050274`
- `0x18005feac`
- `0x1800606b8`
- `0x180068e5c`
- `0x1800690bc`

## import_xrefs

- `IPHLPAPI!GetBestRoute2` at `0x180060a42`
- `IPHLPAPI!GetBestRoute2` at `0x180060a42`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800607f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800608d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180060952`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180060a82`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180060b2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800607f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800608d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180060952`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180060a82`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180060b2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060889`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060975`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006099b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060ae4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060889`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060975`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006099b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060ae4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006086c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006086c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180060ad4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180060ad4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x18006093b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x18006093b`
- `webio!__imp_WebQueryHttpRequestOption` at `0x180060750`
- `webio!__imp_WebQueryHttpRequestOption` at `0x180060750`

## string_xrefs

- `0x1800608a1`: `%s:CreateFile faied. Status:%d`

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
0x1800606b8  mov     [rsp-8+arg_10], rbx
0x1800606bd  mov     [rsp-8+arg_18], rsi
0x1800606c2  push    rbp
0x1800606c3  push    rdi
0x1800606c4  push    r12
0x1800606c6  push    r14
0x1800606c8  push    r15
0x1800606ca  lea     rbp, [rsp-0F0h]
0x1800606d2  sub     rsp, 1F0h
0x1800606d9  mov     rax, cs:__security_cookie
0x1800606e0  xor     rax, rsp
0x1800606e3  mov     [rbp+110h+var_30], rax
0x1800606ea  mov     ebx, edx
0x1800606ec  mov     rdi, rcx
0x1800606ef  mov     r14d, 100h
0x1800606f5  lea     rcx, [rbp+110h+SourceAddress]; void *
0x1800606f9  mov     r8d, r14d; Size
0x1800606fc  xor     edx, edx; Val
0x1800606fe  call    memset_0
0x180060703  mov     rsi, [rdi+450h]
0x18006070a  lea     rcx, [rsp+210h+BestRoute]; void *
0x18006070f  xor     r12d, r12d
0x180060712  xor     edx, edx; Val
0x180060714  mov     [rsp+210h+var_1C8], r12
0x180060719  lea     r8d, [r12+68h]; Size
0x18006071e  call    memset_0
0x180060723  mov     edx, ebx
0x180060725  call    IpTlsAdjustCorpConnectivityTimeout
0x18006072a  cmp     [rdi+3F4h], r12d
0x180060731  jnz     loc_1800607D8
0x180060737  mov     rcx, [rsi]
0x18006073a  lea     rax, [rsp+210h+var_1C8]
0x18006073f  mov     r9d, r14d
0x180060742  mov     qword ptr [rsp+210h+dwCreationDisposition], rax
0x180060747  lea     r8, [rbp+110h+SourceAddress]
0x18006074b  lea     edx, [r12+16h]
0x180060750  call    cs:__imp_WebQueryHttpRequestOption
0x180060757  nop     dword ptr [rax+rax+00h]
0x18006075c  mov     esi, eax
0x18006075e  test    eax, eax
0x180060760  jnz     short loc_18006079B
0x180060762  lea     rcx, [rdi+420h]
0x180060769  lea     r8, [rbp+110h+DestinationAddress]
0x18006076d  lea     rdx, [rbp+110h+SourceAddress]
0x180060771  call    SplTunMgrTunnelConnect
0x180060776  mov     esi, eax
0x180060778  test    eax, eax
0x18006077a  jz      short loc_1800607D8
0x18006077c  lea     r8, [rdi+38h]
0x180060780  mov     r9d, eax
0x180060783  lea     rdx, aSSpltunmgrtunn; "%s:SplTunMgrTunnelConnect faied. Status"...
0x18006078a  mov     ecx, 10000000h
0x18006078f  call    EventWrite0
0x180060794  mov     eax, esi
0x180060796  jmp     loc_180060B3B
0x18006079b  mov     r9d, esi
0x18006079e  lea     r8, [rdi+38h]
0x1800607a2  lea     rdx, aSWebqueryhttpr_1; "%s:WebQueryHttpRequestOption faied. Sta"...
0x1800607a9  mov     ecx, 10000000h
0x1800607ae  call    EventWrite0
0x1800607b3  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x1800607ba  jz      short loc_180060794
0x1800607bc  mov     r9d, esi
0x1800607bf  lea     r8, [rdi+38h]
0x1800607c3  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEDIA_CONNECT
0x1800607ca  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800607d1  call    McTemplateU0zq_EventWriteTransfer
0x1800607d6  jmp     short loc_180060794
0x1800607d8  mov     rcx, cs:g_IpTlsInterfaceListLock
0x1800607df  call    IpTlsAcquireLock
0x1800607e4  test    byte ptr [rdi+408h], 2
0x1800607eb  jz      short loc_18006083E
0x1800607ed  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x1800607f4  call    cs:__imp_ReleaseMutex
0x1800607fb  nop     dword ptr [rax+rax+00h]
0x180060800  cmp     [rdi+3F4h], r12d
0x180060807  jnz     short loc_18006080E
0x180060809  call    SplTunMgrTunnelDisconnect
0x18006080e  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x180060815  jz      short loc_180060834
0x180060817  lea     r8, [rdi+38h]
0x18006081b  mov     r9d, 139Fh
0x180060821  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEDIA_CONNECT
0x180060828  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18006082f  call    McTemplateU0zq_EventWriteTransfer
0x180060834  mov     eax, 139Fh
0x180060839  jmp     loc_180060B3B
0x18006083e  mov     [rsp+210h+hTemplateFile], r12; hTemplateFile
0x180060843  lea     rcx, g_IpTlsTunnelDeviceName; "\\\\.\\\\IpHttpsDevice"
0x18006084a  mov     [rsp+210h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180060852  xor     r9d, r9d; lpSecurityAttributes
0x180060855  xor     r8d, r8d; dwShareMode
0x180060858  mov     [rsp+210h+dwCreationDisposition], 3; dwCreationDisposition
0x180060860  mov     edx, 0C0000000h; dwDesiredAccess
0x180060865  mov     [rdi+448h], r12
0x18006086c  call    cs:__imp_CreateFileW
0x180060873  nop     dword ptr [rax+rax+00h]
0x180060878  mov     [rdi+430h], rax
0x18006087f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180060883  jnz     loc_180060920
0x180060889  call    cs:__imp_GetLastError
0x180060890  nop     dword ptr [rax+rax+00h]
0x180060895  lea     r8, [rdi+38h]
0x180060899  mov     ecx, 10000000h
0x18006089e  mov     r9d, eax
0x1800608a1  lea     rdx, aSCreatefileFai; "%s:CreateFile faied. Status:%d"
0x1800608a8  mov     esi, eax
0x1800608aa  call    EventWrite0
0x1800608af  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x1800608b6  jz      short loc_1800608D2
0x1800608b8  mov     r9d, esi
0x1800608bb  lea     r8, [rdi+38h]
0x1800608bf  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEDIA_CONNECT
0x1800608c6  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800608cd  call    McTemplateU0zq_EventWriteTransfer
0x1800608d2  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x1800608d9  call    cs:__imp_ReleaseMutex
0x1800608e0  nop     dword ptr [rax+rax+00h]
0x1800608e5  cmp     [rdi+3F4h], r12d
0x1800608ec  jz      loc_180060A8E
0x1800608f2  test    cs:Microsoft_Windows_IphlpsvcEnableBits, 2
0x1800608f9  jz      loc_180060794
0x1800608ff  mov     r9d, 2
0x180060905  lea     rdx, EVENT_IPHLPSVC_IPHTTPS_SERVER_START_FAILED
0x18006090c  mov     r8d, esi
0x18006090f  lea     rcx, MS_IPHLPSVC_EVENTS_PROVIDER_ID_Context
0x180060916  call    McTemplateU0qq_EventWriteTransfer
0x18006091b  jmp     loc_180060794
0x180060920  lea     r15, [rdi+438h]
0x180060927  xor     r8d, r8d; Flags
0x18006092a  lea     rdx, IpTlsTunnelIoCompletionHandler; Function
0x180060931  mov     dword ptr [r15], 2
0x180060938  mov     rcx, rax; FileHandle
0x18006093b  call    cs:__imp_BindIoCompletionCallback
0x180060942  nop     dword ptr [rax+rax+00h]
0x180060947  test    eax, eax
0x180060949  jnz     short loc_1800609AC
0x18006094b  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x180060952  call    cs:__imp_ReleaseMutex
0x180060959  nop     dword ptr [rax+rax+00h]
0x18006095e  cmp     [rdi+3F4h], r12d
0x180060965  jnz     short loc_18006096C
0x180060967  call    SplTunMgrTunnelDisconnect
0x18006096c  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x180060973  jz      short loc_18006099B
0x180060975  call    cs:__imp_GetLastError
0x18006097c  nop     dword ptr [rax+rax+00h]
0x180060981  mov     r9d, eax
0x180060984  lea     r8, [rdi+38h]
0x180060988  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEDIA_CONNECT
0x18006098f  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180060996  call    McTemplateU0zq_EventWriteTransfer
0x18006099b  call    cs:__imp_GetLastError
0x1800609a2  nop     dword ptr [rax+rax+00h]
0x1800609a7  jmp     loc_180060B3B
0x1800609ac  test    byte ptr [rdi+408h], 1
0x1800609b3  jz      short loc_1800609C7
0x1800609b5  mov     ebx, 64h ; 'd'
0x1800609ba  mov     rcx, rdi
0x1800609bd  call    IpTlsPrepostBufferUnderLock
0x1800609c2  add     ebx, 0FFFFFFFFh
0x1800609c5  jnz     short loc_1800609BA
0x1800609c7  lea     r14, [rdi+38h]
0x1800609cb  mov     ebx, 10000000h
0x1800609d0  mov     r8, r14
0x1800609d3  lea     rdx, aSInterfaceMedi_0; "%s:Interface media connect indicated"
0x1800609da  mov     ecx, ebx
0x1800609dc  call    EventWrite0
0x1800609e1  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x1800609e8  jz      short loc_180060A03
0x1800609ea  xor     r9d, r9d
0x1800609ed  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEDIA_CONNECT
0x1800609f4  mov     r8, r14
0x1800609f7  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800609fe  call    McTemplateU0zq_EventWriteTransfer
0x180060a03  cmp     [rdi+3F4h], r12d
0x180060a0a  jnz     loc_180060B26
0x180060a10  xorps   xmm0, xmm0
0x180060a13  lea     rax, [rsp+210h+BestSourceAddress]
0x180060a18  mov     [rsp+210h+hTemplateFile], rax; BestSourceAddress
0x180060a1d  lea     r9, [rbp+110h+DestinationAddress]; DestinationAddress
0x180060a21  lea     rax, [rsp+210h+BestRoute]
0x180060a26  xor     edx, edx; InterfaceIndex
0x180060a28  mov     qword ptr [rsp+210h+dwFlagsAndAttributes], rax; BestRoute
0x180060a2d  lea     r8, [rbp+110h+SourceAddress]; SourceAddress
0x180060a31  movups  xmmword ptr [rsp+210h+BestSourceAddress], xmm0
0x180060a36  xor     ecx, ecx; InterfaceLuid
0x180060a38  mov     [rsp+210h+dwCreationDisposition], r12d; AddressSortOptions
0x180060a3d  movups  xmmword ptr [rsp+210h+BestSourceAddress+0Ch], xmm0
0x180060a42  call    cs:__imp_GetBestRoute2
0x180060a49  nop     dword ptr [rax+rax+00h]
0x180060a4e  mov     esi, eax
0x180060a50  test    eax, eax
0x180060a52  jz      short loc_180060A6A
0x180060a54  mov     r9d, eax
0x180060a57  lea     rdx, aSGetbestroute2; "%s:GetBestRoute2 failed. Status:%d"
0x180060a5e  mov     r8, r14
0x180060a61  mov     ecx, ebx
0x180060a63  call    EventWrite0
0x180060a68  jmp     short loc_180060A7B
0x180060a6a  mov     rcx, r15
0x180060a6d  call    RoReferenceEx
0x180060a72  test    al, al
0x180060a74  jnz     short loc_180060A98
0x180060a76  mov     esi, 139Fh
0x180060a7b  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x180060a82  call    cs:__imp_ReleaseMutex
0x180060a89  nop     dword ptr [rax+rax+00h]
0x180060a8e  call    SplTunMgrTunnelDisconnect
0x180060a93  jmp     loc_180060794
0x180060a98  mov     rcx, [rdi+430h]; hDevice
0x180060a9f  lea     rax, [rsp+210h+BytesReturned]
0x180060aa4  mov     [rsp+210h+lpOverlapped], r12; lpOverlapped
0x180060aa9  lea     r8, [rsp+210h+BestRoute]; lpInBuffer
0x180060aae  mov     [rsp+210h+hTemplateFile], rax; lpBytesReturned
0x180060ab3  mov     r15d, 12CC34h
0x180060ab9  mov     [rsp+210h+dwFlagsAndAttributes], r12d; nOutBufferSize
0x180060abe  mov     r9d, 8; nInBufferSize
0x180060ac4  mov     edx, r15d; dwIoControlCode
0x180060ac7  mov     qword ptr [rsp+210h+dwCreationDisposition], r12; lpOutBuffer
0x180060acc  mov     esi, r12d
0x180060acf  mov     [rsp+210h+BytesReturned], r12d
0x180060ad4  call    cs:__imp_DeviceIoControl
0x180060adb  nop     dword ptr [rax+rax+00h]
0x180060ae0  test    eax, eax
0x180060ae2  jnz     short loc_180060AF2
0x180060ae4  call    cs:__imp_GetLastError
0x180060aeb  nop     dword ptr [rax+rax+00h]
0x180060af0  mov     esi, eax
0x180060af2  mov     r9d, esi
0x180060af5  lea     rdx, aIoctlDReturned; "Ioctl %d returned Status %d"
0x180060afc  mov     r8d, r15d
0x180060aff  mov     ecx, ebx
0x180060b01  call    EventWrite0
0x180060b06  test    esi, esi
0x180060b08  jz      short loc_180060B1E
0x180060b0a  mov     r9d, esi
0x180060b0d  lea     rdx, aSIoctlPlumbRea; "%s:IOCTL Plumb Real Interface failed. S"...
0x180060b14  mov     r8, r14
0x180060b17  mov     ecx, ebx
0x180060b19  call    EventWrite0
0x180060b1e  mov     rcx, rdi
0x180060b21  call    IpTlsDereferenceTunnelHandle
0x180060b26  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x180060b2d  call    cs:__imp_ReleaseMutex
0x180060b34  nop     dword ptr [rax+rax+00h]
0x180060b39  xor     eax, eax
0x180060b3b  mov     rcx, [rbp+110h+var_30]
0x180060b42  xor     rcx, rsp; StackCookie
0x180060b45  call    __security_check_cookie
0x180060b4a  lea     r11, [rsp+210h+var_20]
0x180060b52  mov     rbx, [r11+40h]
0x180060b56  mov     rsi, [r11+48h]
0x180060b5a  mov     rsp, r11
0x180060b5d  pop     r15
0x180060b5f  pop     r14
0x180060b61  pop     r12
0x180060b63  pop     rdi
0x180060b64  pop     rbp
0x180060b65  retn
```
