# SendBufferOnContext

- ea: `0x1800671c8`
- end: `0x1800675bb`
- name: `SendBufferOnContext`
- size: `1011`
- prototype: ``
- caller_count: `6`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180043660`
- `0x180049b88`
- `0x180064358`
- `0x18006534c`
- `0x180065e80`
- `0x180066178`

## callees

- `0x180004c64`
- `0x18000d7c0`
- `0x180012dcc`
- `0x1800159d4`
- `0x180030d34`
- `0x180031c4c`
- `0x180040d90`
- `0x1800616b4`
- `0x1800646d8`
- `0x180066148`
- `0x1800671c8`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180067591`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180067591`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180067259`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800674f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180067259`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800674f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800672ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800672d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067536`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800672ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800672d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067536`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006747d`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006747d`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800673c1`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800673c1`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x180067416`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x180067416`

## string_xrefs

- `0x18006728a`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x1800672f0`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

## pseudocode

```c
__int64 __fastcall SendBufferOnContext(__int64 a1, __int64 a2, ULONG_PTR a3, unsigned int a4, DWORD a5)
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
0x1800671c8  push    rbx
0x1800671ca  push    rbp
0x1800671cb  push    rsi
0x1800671cc  push    rdi
0x1800671cd  push    r12
0x1800671cf  push    r13
0x1800671d1  push    r14
0x1800671d3  push    r15
0x1800671d5  sub     rsp, 78h
0x1800671d9  xorps   xmm0, xmm0
0x1800671dc  mov     ebp, r9d
0x1800671df  xor     eax, eax
0x1800671e1  mov     r12, r8
0x1800671e4  mov     rdi, rdx
0x1800671e7  mov     rbx, rcx
0x1800671ea  movups  xmmword ptr [rsp+0B8h+var_68.DataChunkType], xmm0
0x1800671ef  movups  xmmword ptr [rsp+0B8h+var_68.8+4], xmm0
0x1800671f4  test    rdx, rdx
0x1800671f7  jnz     short loc_180067218
0x1800671f9  mov     rdx, [rcx+120h]
0x180067200  mov     r8d, ebp
0x180067203  mov     r9d, [rsp+0B8h+arg_20]
0x18006720b  mov     rcx, r12
0x18006720e  call    IpTlsSendPacketsOnTunnel
0x180067213  jmp     loc_1800675A9
0x180067218  test    byte ptr [rdx+50h], 4
0x18006721c  jnz     loc_1800675A9
0x180067222  mov     r9d, [rdx+54h]
0x180067226  cmp     r9d, [rdx+58h]
0x18006722a  jl      short loc_18006724F
0x18006722c  mov     r8, [rcx+120h]
0x180067233  lea     rdx, aSDroppingPacke; "%s: Dropping packet due to too many out"...
0x18006723a  add     r8, 38h ; '8'
0x18006723e  mov     ecx, 10000000h
0x180067243  call    EventWrite0
0x180067248  xor     eax, eax
0x18006724a  jmp     loc_1800675A9
0x18006724f  lea     r15, [rcx+0F0h]
0x180067256  mov     rcx, r15; lpCriticalSection
0x180067259  call    cs:__imp_EnterCriticalSection
0x180067260  nop     dword ptr [rax+rax+00h]
0x180067265  mov     rsi, [rbx+308h]
0x18006726c  test    rsi, rsi
0x18006726f  jnz     short loc_1800672C1
0x180067271  lea     ecx, [rsi+50h]; dwBytes
0x180067274  call    MALLOC
0x180067279  mov     rsi, rax
0x18006727c  test    rax, rax
0x18006727f  jnz     short loc_1800672D2
0x180067281  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180067288  jz      short loc_1800672A8
0x18006728a  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180067291  mov     dword ptr [rsp+0B8h+EntityChunks], 1240h
0x180067299  xor     r8d, r8d
0x18006729c  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x1800672a3  call    McTemplateU0psq_EventWriteTransfer
0x1800672a8  mov     rcx, r15; lpCriticalSection
0x1800672ab  call    cs:__imp_LeaveCriticalSection
0x1800672b2  nop     dword ptr [rax+rax+00h]
0x1800672b7  mov     eax, 8
0x1800672bc  jmp     loc_1800675A9
0x1800672c1  mov     rax, [rsi]
0x1800672c4  mov     [rbx+308h], rax
0x1800672cb  lock dec dword ptr [rbx+310h]
0x1800672d2  mov     rcx, r15; lpCriticalSection
0x1800672d5  call    cs:__imp_LeaveCriticalSection
0x1800672dc  nop     dword ptr [rax+rax+00h]
0x1800672e1  xorps   xmm0, xmm0
0x1800672e4  mov     dword ptr [rsp+0B8h+EntityChunks], 124Eh
0x1800672ec  movups  xmmword ptr [rsi+10h], xmm0
0x1800672f0  lea     r14, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800672f7  mov     r8, r12
0x1800672fa  movups  xmmword ptr [rsi+20h], xmm0
0x1800672fe  mov     dword ptr [rsi+30h], 0E478h
0x180067305  lea     rdx, aReferenceIptls; "(Reference IPTLS Buffer(%p) %S:%d"
0x18006730c  mov     r9, r14
0x18006730f  mov     [rsp+0B8h+var_68.DataChunkType], 0
0x180067317  mov     ecx, 20000000h
0x18006731c  call    EventWrite0
0x180067321  lock inc dword ptr [r12+50h]
0x180067327  mov     rax, [rdi+28h]
0x18006732b  lea     rdx, aSReferenceClie; "(%s: Reference client context (%p)%S:%d"
0x180067332  mov     r13d, 124Fh
0x180067338  mov     r9, rdi
0x18006733b  mov     dword ptr [rsp+0B8h+BytesSent], r13d
0x180067340  mov     ecx, 20000000h
0x180067345  mov     [rsp+0B8h+EntityChunks], r14
0x18006734a  mov     r8, [rax+120h]
0x180067351  add     r8, 38h ; '8'
0x180067355  call    EventWrite0
0x18006735a  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180067361  jz      short loc_18006737A
0x180067363  mov     r9, r14
0x180067366  mov     dword ptr [rsp+0B8h+EntityChunks], r13d
0x18006736b  mov     r8, rdi
0x18006736e  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_REFERENCE
0x180067375  call    McTemplateU0psq_EventWriteTransfer
0x18006737a  lock inc dword ptr [rdi+38h]
0x18006737e  mov     r13d, [rsp+0B8h+arg_20]
0x180067386  lock add [rdi+54h], r13d
0x18006738b  mov     [rsi+40h], rdi
0x18006738f  lea     rcx, [rbp+98h]
0x180067396  mov     [rsi+48h], r13d
0x18006739a  add     rcx, r12
0x18006739d  mov     qword ptr [rsp+0B8h+var_68.8], rcx
0x1800673a2  mov     dword ptr [rsp+0B8h+var_68.8+8], r13d
0x1800673a7  mov     [rsi+38h], r12
0x1800673ab  inc     qword ptr [rdi+188h]
0x1800673b2  inc     cs:g_IpTlsGlobalStatsPacketsOut
0x1800673b9  mov     rcx, [rdi+28h]
0x1800673bd  mov     rcx, [rcx+60h]; pio
0x1800673c1  call    cs:__imp_StartThreadpoolIo
0x1800673c8  nop     dword ptr [rax+rax+00h]
0x1800673cd  lea     rcx, [rbx+50h]
0x1800673d1  call    RoReferenceEx
0x1800673d6  xor     edx, edx
0x1800673d8  test    al, al
0x1800673da  jz      short loc_180067442
0x1800673dc  mov     rcx, [rdi+28h]
0x1800673e0  lea     rax, [rsi+10h]
0x1800673e4  mov     [rsp+0B8h+LogData], rdx; LogData
0x1800673e9  lea     r9d, [rdx+1]; EntityChunkCount
0x1800673ed  mov     [rsp+0B8h+Overlapped], rax; Overlapped
0x1800673f2  lea     r8d, [rdx+2]; Flags
0x1800673f6  mov     [rsp+0B8h+Reserved2], edx; Reserved2
0x1800673fa  lea     rax, [rsp+0B8h+var_68]
0x1800673ff  mov     rcx, [rcx+48h]; RequestQueueHandle
0x180067403  mov     [rsp+0B8h+Reserved1], rdx; Reserved1
0x180067408  mov     [rsp+0B8h+BytesSent], rdx; BytesSent
0x18006740d  mov     rdx, [rdi+30h]; RequestId
0x180067411  mov     [rsp+0B8h+EntityChunks], rax; EntityChunks
0x180067416  call    cs:__imp_HttpSendResponseEntityBody
0x18006741d  nop     dword ptr [rax+rax+00h]
0x180067422  mov     ebp, eax
0x180067424  cmp     eax, 3E5h
0x180067429  jz      loc_180067577
0x18006742f  test    eax, eax
0x180067431  jz      loc_180067577
0x180067437  mov     rcx, [rdi+28h]
0x18006743b  call    IpTlsServerDereferenceHttpQueue
0x180067440  jmp     short loc_180067447
0x180067442  mov     ebp, 6
0x180067447  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18006744e  jz      short loc_180067475
0x180067450  mov     rax, [rdi+28h]
0x180067454  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_SEND_ENTITY
0x18006745b  mov     r9d, ebp
0x18006745e  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180067465  mov     r8, [rax+120h]
0x18006746c  add     r8, 38h ; '8'
0x180067470  call    McTemplateU0zq_EventWriteTransfer
0x180067475  mov     rcx, [rdi+28h]
0x180067479  mov     rcx, [rcx+60h]; pio
0x18006747d  call    cs:__imp_CancelThreadpoolIo
0x180067484  nop     dword ptr [rax+rax+00h]
0x180067489  mov     eax, r13d
0x18006748c  neg     eax
0x18006748e  lock add [rdi+54h], eax
0x180067492  mov     r9, [rsi+40h]
0x180067496  lea     rdx, aSDereferenceCl; "(%s: Dereference client context (%p) %S"...
0x18006749d  mov     dword ptr [rsp+0B8h+BytesSent], 127Eh
0x1800674a5  mov     ecx, 20000000h
0x1800674aa  mov     [rsp+0B8h+EntityChunks], r14
0x1800674af  mov     rax, [r9+28h]
0x1800674b3  mov     r8, [rax+120h]
0x1800674ba  add     r8, 38h ; '8'
0x1800674be  call    EventWrite0
0x1800674c3  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x1800674ca  jz      short loc_1800674E7
0x1800674cc  mov     r8, [rsi+40h]
0x1800674d0  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE
0x1800674d7  mov     r9, r14
0x1800674da  mov     dword ptr [rsp+0B8h+EntityChunks], 127Eh
0x1800674e2  call    McTemplateU0psq_EventWriteTransfer
0x1800674e7  mov     rcx, [rsi+40h]
0x1800674eb  call    DereferenceClientContextEx
0x1800674f0  mov     rcx, r15; lpCriticalSection
0x1800674f3  call    cs:__imp_EnterCriticalSection
0x1800674fa  nop     dword ptr [rax+rax+00h]
0x1800674ff  cmp     dword ptr [rbx+310h], 32h ; '2'
0x180067506  ja      short loc_18006752B
0x180067508  test    byte ptr [rbx+170h], 20h
0x18006750f  jnz     short loc_18006752B
0x180067511  mov     rax, [rbx+308h]
0x180067518  mov     [rsi], rax
0x18006751b  mov     [rbx+308h], rsi
0x180067522  lock inc dword ptr [rbx+310h]
0x180067529  jmp     short loc_180067533
0x18006752b  mov     rcx, rsi
0x18006752e  call    FREE
0x180067533  mov     rcx, r15; lpCriticalSection
0x180067536  call    cs:__imp_LeaveCriticalSection
0x18006753d  nop     dword ptr [rax+rax+00h]
0x180067542  mov     r9, r14
0x180067545  mov     dword ptr [rsp+0B8h+EntityChunks], 1289h
0x18006754d  mov     r8, r12
0x180067550  lea     rdx, aDereferenceIpt; "(Dereference IPTLS Buffer(%p)%S:%d"
0x180067557  mov     ecx, 20000000h
0x18006755c  call    EventWrite0
0x180067561  mov     rcx, r12
0x180067564  call    IpTlsDereferenceBufferEx
0x180067569  inc     qword ptr [rdi+1A0h]
0x180067570  inc     cs:g_IpTlsGlobalStatsTransmitErrors
0x180067577  mov     rax, r13
0x18006757a  xor     ecx, ecx; Time
0x18006757c  add     cs:g_IpTlsGlobalStatsBytesOut, rax
0x180067583  add     [rdi+198h], rax
0x18006758a  mov     rbx, [rdi+1B0h]
0x180067591  call    cs:__imp__time64
0x180067598  nop     dword ptr [rax+rax+00h]
0x18006759d  sub     rax, rbx
0x1800675a0  mov     [rdi+1B8h], rax
0x1800675a7  mov     eax, ebp
0x1800675a9  add     rsp, 78h
0x1800675ad  pop     r15
0x1800675af  pop     r14
0x1800675b1  pop     r13
0x1800675b3  pop     r12
0x1800675b5  pop     rdi
0x1800675b6  pop     rsi
0x1800675b7  pop     rbp
0x1800675b8  pop     rbx
0x1800675b9  retn
```
