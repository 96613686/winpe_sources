# SendBufferOnContext

- ea: `0x1800671a8`
- end: `0x18006759b`
- name: `SendBufferOnContext`
- size: `1011`
- prototype: ``
- caller_count: `6`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800436a0`
- `0x180049bc8`
- `0x180064338`
- `0x18006532c`
- `0x180065e60`
- `0x180066158`

## callees

- `0x180004c54`
- `0x18000d7b0`
- `0x180012dbc`
- `0x1800159c4`
- `0x180030d24`
- `0x180031c3c`
- `0x180040dd0`
- `0x180061694`
- `0x1800646b8`
- `0x180066128`
- `0x1800671a8`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180067571`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180067571`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180067239`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800674d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180067239`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800674d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006728b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800672b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067516`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006728b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800672b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067516`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006745d`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006745d`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800673a1`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800673a1`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x1800673f6`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x1800673f6`

## string_xrefs

- `0x18006726a`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x1800672d0`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

## pseudocode

```c
__int64 __fastcall SendBufferOnContext(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, unsigned int a5)
{
  __int64 v5; // rbp
  __int64 result; // rax
  struct _RTL_CRITICAL_SECTION *v10; // r15
  __int64 v11; // rsi
  int v12; // ecx
  int v13; // ecx
  ULONG v14; // eax
  unsigned int v15; // ebp
  int v16; // ecx
  __int64 v17; // rbx
  PHTTP_DATA_CHUNK EntityChunks; // [rsp+20h] [rbp-98h]
  struct _HTTP_DATA_CHUNK v19; // [rsp+50h] [rbp-68h] BYREF

  v5 = a4;
  result = 0;
  memset(&v19, 0, 28);
  if ( !a2 )
    return IpTlsSendPacketsOnTunnel(a3, *(_QWORD *)(a1 + 288), a4, a5);
  if ( (*(_BYTE *)(a2 + 80) & 4) == 0 )
  {
    if ( *(_DWORD *)(a2 + 84) >= *(_DWORD *)(a2 + 88) )
    {
      EventWrite0(
        0x10000000,
        L"%s: Dropping packet due to too many outstanding bytes  %d.",
        *(_QWORD *)(a1 + 288) + 56LL);
      return 0;
    }
    v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 240);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 240));
    v11 = *(_QWORD *)(a1 + 776);
    if ( v11 )
    {
      *(_QWORD *)(a1 + 776) = *(_QWORD *)v11;
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 784));
    }
    else
    {
      v11 = MALLOC(0x50u);
      if ( !v11 )
      {
        if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
          McTemplateU0psq_EventWriteTransfer(
            v12,
            (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE,
            0,
            (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
            64);
        LeaveCriticalSection(v10);
        return 8;
      }
    }
    LeaveCriticalSection(v10);
    *(_OWORD *)(v11 + 16) = 0;
    *(_OWORD *)(v11 + 32) = 0;
    *(_DWORD *)(v11 + 48) = 58488;
    v19.DataChunkType = HttpDataChunkFromMemory;
    EventWrite0(
      0x20000000,
      L"(Reference IPTLS Buffer(%p) %S:%d",
      a3,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      4686);
    _InterlockedIncrement((volatile signed __int32 *)(a3 + 80));
    EventWrite0(
      0x20000000,
      L"(%s: Reference client context (%p)%S:%d",
      *(_QWORD *)(*(_QWORD *)(a2 + 40) + 288LL) + 56LL,
      a2,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      4687);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v13,
        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_REFERENCE,
        a2,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
        79);
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 56));
    _InterlockedAdd((volatile signed __int32 *)(a2 + 84), a5);
    *(_QWORD *)(v11 + 64) = a2;
    *(_DWORD *)(v11 + 72) = a5;
    v19.FromFileHandle.ByteRange.StartingOffset.QuadPart = a3 + v5 + 152;
    v19.FromMemory.BufferLength = a5;
    *(_QWORD *)(v11 + 56) = a3;
    ++*(_QWORD *)(a2 + 392);
    ++g_IpTlsGlobalStatsPacketsOut;
    StartThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(a2 + 40) + 96LL));
    if ( (unsigned __int8)RoReferenceEx(a1 + 80) )
    {
      v14 = HttpSendResponseEntityBody(
              *(HANDLE *)(*(_QWORD *)(a2 + 40) + 72LL),
              *(_QWORD *)(a2 + 48),
              2u,
              1u,
              &v19,
              0,
              0,
              0,
              (LPOVERLAPPED)(v11 + 16),
              0);
      v15 = v14;
      if ( v14 == 997 || !v14 )
      {
LABEL_28:
        g_IpTlsGlobalStatsBytesOut += a5;
        *(_QWORD *)(a2 + 408) += a5;
        v17 = *(_QWORD *)(a2 + 432);
        *(_QWORD *)(a2 + 440) = _time64(0) - v17;
        return v15;
      }
      IpTlsServerDereferenceHttpQueue(*(_QWORD *)(a2 + 40));
    }
    else
    {
      v15 = 6;
    }
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_SEND_ENTITY,
        *(_QWORD *)(*(_QWORD *)(a2 + 40) + 288LL) + 56LL,
        v15);
    CancelThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(a2 + 40) + 96LL));
    _InterlockedAdd((volatile signed __int32 *)(a2 + 84), -a5);
    EntityChunks = (PHTTP_DATA_CHUNK)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c";
    EventWrite0(
      0x20000000,
      L"(%s: Dereference client context (%p) %S:%d",
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v11 + 64) + 40LL) + 288LL) + 56LL);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v16,
        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE,
        *(_QWORD *)(v11 + 64),
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
        126);
    DereferenceClientContextEx(*(_QWORD *)(v11 + 64));
    EnterCriticalSection(v10);
    if ( *(_DWORD *)(a1 + 784) > 0x32u || (*(_BYTE *)(a1 + 368) & 0x20) != 0 )
    {
      FREE(v11);
    }
    else
    {
      *(_QWORD *)v11 = *(_QWORD *)(a1 + 776);
      *(_QWORD *)(a1 + 776) = v11;
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 784));
    }
    LeaveCriticalSection(v10);
    LODWORD(EntityChunks) = 4745;
    EventWrite0(
      0x20000000,
      L"(Dereference IPTLS Buffer(%p)%S:%d",
      a3,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      EntityChunks);
    IpTlsDereferenceBufferEx(a3);
    ++*(_QWORD *)(a2 + 416);
    ++g_IpTlsGlobalStatsTransmitErrors;
    goto LABEL_28;
  }
  return result;
}

```

## disassembly

```asm
0x1800671a8  push    rbx
0x1800671aa  push    rbp
0x1800671ab  push    rsi
0x1800671ac  push    rdi
0x1800671ad  push    r12
0x1800671af  push    r13
0x1800671b1  push    r14
0x1800671b3  push    r15
0x1800671b5  sub     rsp, 78h
0x1800671b9  xorps   xmm0, xmm0
0x1800671bc  mov     ebp, r9d
0x1800671bf  xor     eax, eax
0x1800671c1  mov     r12, r8
0x1800671c4  mov     rdi, rdx
0x1800671c7  mov     rbx, rcx
0x1800671ca  movups  xmmword ptr [rsp+0B8h+var_68.DataChunkType], xmm0
0x1800671cf  movups  xmmword ptr [rsp+0B8h+var_68.8+4], xmm0
0x1800671d4  test    rdx, rdx
0x1800671d7  jnz     short loc_1800671F8
0x1800671d9  mov     rdx, [rcx+120h]
0x1800671e0  mov     r8d, ebp
0x1800671e3  mov     r9d, [rsp+0B8h+arg_20]
0x1800671eb  mov     rcx, r12
0x1800671ee  call    IpTlsSendPacketsOnTunnel
0x1800671f3  jmp     loc_180067589
0x1800671f8  test    byte ptr [rdx+50h], 4
0x1800671fc  jnz     loc_180067589
0x180067202  mov     r9d, [rdx+54h]
0x180067206  cmp     r9d, [rdx+58h]
0x18006720a  jl      short loc_18006722F
0x18006720c  mov     r8, [rcx+120h]
0x180067213  lea     rdx, aSDroppingPacke; "%s: Dropping packet due to too many out"...
0x18006721a  add     r8, 38h ; '8'
0x18006721e  mov     ecx, 10000000h
0x180067223  call    EventWrite0
0x180067228  xor     eax, eax
0x18006722a  jmp     loc_180067589
0x18006722f  lea     r15, [rcx+0F0h]
0x180067236  mov     rcx, r15; lpCriticalSection
0x180067239  call    cs:__imp_EnterCriticalSection
0x180067240  nop     dword ptr [rax+rax+00h]
0x180067245  mov     rsi, [rbx+308h]
0x18006724c  test    rsi, rsi
0x18006724f  jnz     short loc_1800672A1
0x180067251  lea     ecx, [rsi+50h]; dwBytes
0x180067254  call    MALLOC
0x180067259  mov     rsi, rax
0x18006725c  test    rax, rax
0x18006725f  jnz     short loc_1800672B2
0x180067261  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180067268  jz      short loc_180067288
0x18006726a  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180067271  mov     dword ptr [rsp+0B8h+EntityChunks], 1240h
0x180067279  xor     r8d, r8d
0x18006727c  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x180067283  call    McTemplateU0psq_EventWriteTransfer
0x180067288  mov     rcx, r15; lpCriticalSection
0x18006728b  call    cs:__imp_LeaveCriticalSection
0x180067292  nop     dword ptr [rax+rax+00h]
0x180067297  mov     eax, 8
0x18006729c  jmp     loc_180067589
0x1800672a1  mov     rax, [rsi]
0x1800672a4  mov     [rbx+308h], rax
0x1800672ab  lock dec dword ptr [rbx+310h]
0x1800672b2  mov     rcx, r15; lpCriticalSection
0x1800672b5  call    cs:__imp_LeaveCriticalSection
0x1800672bc  nop     dword ptr [rax+rax+00h]
0x1800672c1  xorps   xmm0, xmm0
0x1800672c4  mov     dword ptr [rsp+0B8h+EntityChunks], 124Eh
0x1800672cc  movups  xmmword ptr [rsi+10h], xmm0
0x1800672d0  lea     r14, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800672d7  mov     r8, r12
0x1800672da  movups  xmmword ptr [rsi+20h], xmm0
0x1800672de  mov     dword ptr [rsi+30h], 0E478h
0x1800672e5  lea     rdx, aReferenceIptls; "(Reference IPTLS Buffer(%p) %S:%d"
0x1800672ec  mov     r9, r14
0x1800672ef  mov     [rsp+0B8h+var_68.DataChunkType], 0
0x1800672f7  mov     ecx, 20000000h
0x1800672fc  call    EventWrite0
0x180067301  lock inc dword ptr [r12+50h]
0x180067307  mov     rax, [rdi+28h]
0x18006730b  lea     rdx, aSReferenceClie; "(%s: Reference client context (%p)%S:%d"
0x180067312  mov     r13d, 124Fh
0x180067318  mov     r9, rdi
0x18006731b  mov     dword ptr [rsp+0B8h+BytesSent], r13d
0x180067320  mov     ecx, 20000000h
0x180067325  mov     [rsp+0B8h+EntityChunks], r14
0x18006732a  mov     r8, [rax+120h]
0x180067331  add     r8, 38h ; '8'
0x180067335  call    EventWrite0
0x18006733a  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180067341  jz      short loc_18006735A
0x180067343  mov     r9, r14
0x180067346  mov     dword ptr [rsp+0B8h+EntityChunks], r13d
0x18006734b  mov     r8, rdi
0x18006734e  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_REFERENCE
0x180067355  call    McTemplateU0psq_EventWriteTransfer
0x18006735a  lock inc dword ptr [rdi+38h]
0x18006735e  mov     r13d, [rsp+0B8h+arg_20]
0x180067366  lock add [rdi+54h], r13d
0x18006736b  mov     [rsi+40h], rdi
0x18006736f  lea     rcx, [rbp+98h]
0x180067376  mov     [rsi+48h], r13d
0x18006737a  add     rcx, r12
0x18006737d  mov     qword ptr [rsp+0B8h+var_68.8], rcx
0x180067382  mov     dword ptr [rsp+0B8h+var_68.8+8], r13d
0x180067387  mov     [rsi+38h], r12
0x18006738b  inc     qword ptr [rdi+188h]
0x180067392  inc     cs:g_IpTlsGlobalStatsPacketsOut
0x180067399  mov     rcx, [rdi+28h]
0x18006739d  mov     rcx, [rcx+60h]; pio
0x1800673a1  call    cs:__imp_StartThreadpoolIo
0x1800673a8  nop     dword ptr [rax+rax+00h]
0x1800673ad  lea     rcx, [rbx+50h]
0x1800673b1  call    RoReferenceEx
0x1800673b6  xor     edx, edx
0x1800673b8  test    al, al
0x1800673ba  jz      short loc_180067422
0x1800673bc  mov     rcx, [rdi+28h]
0x1800673c0  lea     rax, [rsi+10h]
0x1800673c4  mov     [rsp+0B8h+LogData], rdx; LogData
0x1800673c9  lea     r9d, [rdx+1]; EntityChunkCount
0x1800673cd  mov     [rsp+0B8h+Overlapped], rax; Overlapped
0x1800673d2  lea     r8d, [rdx+2]; Flags
0x1800673d6  mov     [rsp+0B8h+Reserved2], edx; Reserved2
0x1800673da  lea     rax, [rsp+0B8h+var_68]
0x1800673df  mov     rcx, [rcx+48h]; RequestQueueHandle
0x1800673e3  mov     [rsp+0B8h+Reserved1], rdx; Reserved1
0x1800673e8  mov     [rsp+0B8h+BytesSent], rdx; BytesSent
0x1800673ed  mov     rdx, [rdi+30h]; RequestId
0x1800673f1  mov     [rsp+0B8h+EntityChunks], rax; EntityChunks
0x1800673f6  call    cs:__imp_HttpSendResponseEntityBody
0x1800673fd  nop     dword ptr [rax+rax+00h]
0x180067402  mov     ebp, eax
0x180067404  cmp     eax, 3E5h
0x180067409  jz      loc_180067557
0x18006740f  test    eax, eax
0x180067411  jz      loc_180067557
0x180067417  mov     rcx, [rdi+28h]
0x18006741b  call    IpTlsServerDereferenceHttpQueue
0x180067420  jmp     short loc_180067427
0x180067422  mov     ebp, 6
0x180067427  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18006742e  jz      short loc_180067455
0x180067430  mov     rax, [rdi+28h]
0x180067434  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_SEND_ENTITY
0x18006743b  mov     r9d, ebp
0x18006743e  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180067445  mov     r8, [rax+120h]
0x18006744c  add     r8, 38h ; '8'
0x180067450  call    McTemplateU0zq_EventWriteTransfer
0x180067455  mov     rcx, [rdi+28h]
0x180067459  mov     rcx, [rcx+60h]; pio
0x18006745d  call    cs:__imp_CancelThreadpoolIo
0x180067464  nop     dword ptr [rax+rax+00h]
0x180067469  mov     eax, r13d
0x18006746c  neg     eax
0x18006746e  lock add [rdi+54h], eax
0x180067472  mov     r9, [rsi+40h]
0x180067476  lea     rdx, aSDereferenceCl; "(%s: Dereference client context (%p) %S"...
0x18006747d  mov     dword ptr [rsp+0B8h+BytesSent], 127Eh
0x180067485  mov     ecx, 20000000h
0x18006748a  mov     [rsp+0B8h+EntityChunks], r14
0x18006748f  mov     rax, [r9+28h]
0x180067493  mov     r8, [rax+120h]
0x18006749a  add     r8, 38h ; '8'
0x18006749e  call    EventWrite0
0x1800674a3  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x1800674aa  jz      short loc_1800674C7
0x1800674ac  mov     r8, [rsi+40h]
0x1800674b0  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE
0x1800674b7  mov     r9, r14
0x1800674ba  mov     dword ptr [rsp+0B8h+EntityChunks], 127Eh
0x1800674c2  call    McTemplateU0psq_EventWriteTransfer
0x1800674c7  mov     rcx, [rsi+40h]
0x1800674cb  call    DereferenceClientContextEx
0x1800674d0  mov     rcx, r15; lpCriticalSection
0x1800674d3  call    cs:__imp_EnterCriticalSection
0x1800674da  nop     dword ptr [rax+rax+00h]
0x1800674df  cmp     dword ptr [rbx+310h], 32h ; '2'
0x1800674e6  ja      short loc_18006750B
0x1800674e8  test    byte ptr [rbx+170h], 20h
0x1800674ef  jnz     short loc_18006750B
0x1800674f1  mov     rax, [rbx+308h]
0x1800674f8  mov     [rsi], rax
0x1800674fb  mov     [rbx+308h], rsi
0x180067502  lock inc dword ptr [rbx+310h]
0x180067509  jmp     short loc_180067513
0x18006750b  mov     rcx, rsi
0x18006750e  call    FREE
0x180067513  mov     rcx, r15; lpCriticalSection
0x180067516  call    cs:__imp_LeaveCriticalSection
0x18006751d  nop     dword ptr [rax+rax+00h]
0x180067522  mov     r9, r14
0x180067525  mov     dword ptr [rsp+0B8h+EntityChunks], 1289h
0x18006752d  mov     r8, r12
0x180067530  lea     rdx, aDereferenceIpt; "(Dereference IPTLS Buffer(%p)%S:%d"
0x180067537  mov     ecx, 20000000h
0x18006753c  call    EventWrite0
0x180067541  mov     rcx, r12
0x180067544  call    IpTlsDereferenceBufferEx
0x180067549  inc     qword ptr [rdi+1A0h]
0x180067550  inc     cs:g_IpTlsGlobalStatsTransmitErrors
0x180067557  mov     rax, r13
0x18006755a  xor     ecx, ecx; Time
0x18006755c  add     cs:g_IpTlsGlobalStatsBytesOut, rax
0x180067563  add     [rdi+198h], rax
0x18006756a  mov     rbx, [rdi+1B0h]
0x180067571  call    cs:__imp__time64
0x180067578  nop     dword ptr [rax+rax+00h]
0x18006757d  sub     rax, rbx
0x180067580  mov     [rdi+1B8h], rax
0x180067587  mov     eax, ebp
0x180067589  add     rsp, 78h
0x18006758d  pop     r15
0x18006758f  pop     r14
0x180067591  pop     r13
0x180067593  pop     r12
0x180067595  pop     rdi
0x180067596  pop     rsi
0x180067597  pop     rbp
0x180067598  pop     rbx
0x180067599  retn
```
