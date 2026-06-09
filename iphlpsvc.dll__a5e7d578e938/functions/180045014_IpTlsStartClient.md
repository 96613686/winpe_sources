# IpTlsStartClient

- ea: `0x180045014`
- end: `0x180045547`
- name: `IpTlsStartClient`
- size: `1331`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005fabc`

## callees

- `0x18000d7c0`
- `0x180012dcc`
- `0x180031698`
- `0x180031e38`
- `0x180045014`
- `0x180045550`
- `0x1800455d4`
- `0x180048a0c`
- `0x18004c188`
- `0x1800616b4`
- `0x180062cbc`
- `0x180062da8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800451d1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800451d1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004533f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004533f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180045164`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180045164`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004517a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045497`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004517a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045497`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045192`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045208`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800454d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045192`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045208`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800454d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045383`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045383`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180045221`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180045221`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004529b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004529b`
- `bcrypt!BCryptAddContextFunction` at `0x180045431`
- `bcrypt!BCryptAddContextFunction` at `0x180045431`
- `webio!__imp_WebCreateUri` at `0x1800452eb`
- `webio!__imp_WebCreateUri` at `0x1800452eb`

## string_xrefs

- `0x18004506b`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x1800450bf`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x180045307`: `%s:WebCreateUri failed: %d`

## pseudocode

```c
__int64 __fastcall IpTlsStartClient(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  int v7; // ecx
  DWORD LastError; // edi
  int v10; // ecx
  _QWORD *v11; // r14
  _QWORD *v12; // rax
  PTP_WORK ThreadpoolWork; // rax
  int v14; // ecx
  PTP_TIMER ThreadpoolTimer; // rax
  int v16; // ecx
  DWORD Uri; // eax
  HANDLE EventW; // rax
  DWORD v19; // eax
  const wchar_t *v20; // rdx
  unsigned int v21; // eax
  unsigned int v22; // eax
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // rdx
  _QWORD *v26; // rax
  int v27; // ecx
  __int64 dwPosition; // [rsp+20h] [rbp-58h]

  *(_QWORD *)(a3 + 1104) = -1;
  v5 = (_QWORD *)MALLOC(0xF0u);
  v6 = v5;
  if ( !v5 )
  {
    EventWrite0(0x10000000, L"%s:IpTlsStartClient allocation failed", a3 + 56);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v7,
        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE,
        0,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsclient.c",
        131);
    LastError = 8;
    *(_DWORD *)(a3 + 1192) = 1;
    *(_DWORD *)(a3 + 1196) = 8;
    return LastError;
  }
  memset_0(v5, 0, 0xF0u);
  *((_DWORD *)v6 + 31) = 1;
  EventWrite0(
    0x20000000,
    L"(%s: Reference IPTLS interface %S:%d",
    a3 + 56,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsclient.c",
    1419);
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v10,
      (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_REFERENCE,
      a3,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsclient.c",
      139);
  _InterlockedAdd((volatile signed __int32 *)(a3 + 1036), 1u);
  v6[16] = a3;
  v11 = v6 + 13;
  *(_OWORD *)(v6 + 11) = 0;
  v6[1] = 0;
  *v6 = 0;
  *((_DWORD *)v6 + 30) = 1;
  *((_BYTE *)v6 + 60) = 0;
  *((_DWORD *)v6 + 20) = 32;
  *((_BYTE *)v6 + 224) = 1;
  *((_DWORD *)v6 + 37) = 1;
  v6[14] = v6 + 13;
  v6[13] = v6 + 13;
  *(_DWORD *)(a3 + 1192) = 10;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v6 + 22));
  EnterCriticalSection(&stru_1800CC350);
  if ( byte_1800CC378 )
  {
    LeaveCriticalSection(&stru_1800CC350);
    EventWrite0(0x10000000, L"%s:IpTlsStartClient. Aborted due to shutdown", v6[16] + 56LL);
    LastError = 995;
LABEL_33:
    IpTlsDeregisterCSNotification(v6);
    IpTlsDeregisterProxyNotifications(v6);
    EnterCriticalSection(&stru_1800CC350);
    v25 = *v11;
    if ( *(_QWORD **)(*v11 + 8LL) == v11 )
    {
      v26 = (_QWORD *)v6[14];
      if ( (_QWORD *)*v26 == v11 )
      {
        *v26 = v25;
        *(_QWORD *)(v25 + 8) = v26;
        v6[14] = v6 + 13;
        *v11 = v11;
        LeaveCriticalSection(&stru_1800CC350);
        LODWORD(dwPosition) = 1597;
        EventWrite0(
          0x20000000,
          L"(%s: Dereference IPTLS client interface %S:%d",
          v6[16] + 56LL,
          "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsclient.c",
          dwPosition);
        if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
          McTemplateU0psq_EventWriteTransfer(
            v27,
            (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_INTERFACE_DEREFERENCE,
            (_DWORD)v6,
            (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsclient.c",
            61);
        DereferenceInterfaceEx(v6);
        return LastError;
      }
    }
LABEL_39:
    __fastfail(3u);
  }
  ++dword_1800CC330;
  ResetEvent(qword_1800CC338);
  v12 = (_QWORD *)qword_1800CC348;
  if ( *(__int64 **)qword_1800CC348 != &qword_1800CC340 )
    goto LABEL_39;
  *v11 = &qword_1800CC340;
  v6[14] = v12;
  *v12 = v11;
  qword_1800CC348 = (__int64)(v6 + 13);
  LeaveCriticalSection(&stru_1800CC350);
  ThreadpoolWork = CreateThreadpoolWork(IpTlsCleanupClientTimer, v6, 0);
  v6[17] = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    EventWrite0(0x10000000, L"%s:IpTlsStartClient allocation failed", v6[16] + 56LL);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v14,
        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE,
        0,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsclient.c",
        182);
LABEL_14:
    LastError = 8;
    *(_DWORD *)(a3 + 1192) = 1;
    *(_DWORD *)(a3 + 1196) = 8;
    goto LABEL_33;
  }
  ThreadpoolTimer = CreateThreadpoolTimer(IpTlsClientReconnectTimeout, v6, 0);
  v6[20] = ThreadpoolTimer;
  if ( !ThreadpoolTimer )
  {
    EventWrite0(0x10000000, L"%s:IpTlsStartClient allocation failed", v6[16] + 56LL);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v16,
        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE,
        0,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsclient.c",
        202);
    goto LABEL_14;
  }
  Uri = WebCreateUri(a1, 0, v6 + 2);
  LastError = Uri;
  if ( Uri )
  {
    *(_DWORD *)(a3 + 1192) = 3;
    *(_DWORD *)(a3 + 1196) = Uri;
    EventWrite0(0x10000000, L"%s:WebCreateUri failed: %d", v6[16] + 56LL, Uri);
    v6[2] = 0;
    goto LABEL_33;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v6[19] = EventW;
  if ( !EventW )
  {
    EventWrite0(0x10000000, L"%s:IpTlsStartClient allocation failed", v6[16] + 56LL);
    *(_DWORD *)(a3 + 1192) = 1;
    *(_DWORD *)(a3 + 1196) = 8;
    LastError = GetLastError();
    goto LABEL_33;
  }
  v19 = IpTlsClientScheduleWorkItem(v6, 0, IpTlsQueryProxyInformation);
  LastError = v19;
  if ( v19 )
  {
    v20 = L"%s:IpTlsStartClient IpTlsClientScheduleWorkItem failed: %d";
LABEL_24:
    EventWrite0(0x10000000, v20, v6[16] + 56LL, v19);
    goto LABEL_33;
  }
  v19 = IpTlsRegisterForProxyNotifications(v6);
  LastError = v19;
  if ( v19 )
  {
    v20 = L"%s:IpTlsStartClient IpTlsRegisterForProxyNotifications failed: %d";
    goto LABEL_24;
  }
  v21 = IpTlsRegisterCSNotification(v6);
  if ( v21 )
    EventWrite0(0x10000000, L"%s:IpTlsStartClient IpTlsRegisterCSNotification failed: %d", v6[16] + 56LL, v21);
  v22 = BCryptAddContextFunction(1u, L"SSL", 0x10002u, L"TLS_RSA_WITH_NULL_MD5", 0xFFFFFFFF);
  v23 = v6[16] + 56LL;
  LastError = v22;
  if ( v22 )
  {
    EventWrite0(0x10000000, L"%s:IpTlsStartClient BCryptAddContextFunction failed: %d", v23, v22);
    goto LABEL_33;
  }
  EventWrite0(0x10000000, L"%s:Starting Client", v23);
  LOBYTE(v24) = 1;
  LastError = IpTlsRestartClient(v6, v24);
  if ( LastError )
    goto LABEL_33;
  *(_QWORD *)(a3 + 1104) = v6;
  return 0;
}

```

## disassembly

```asm
0x180045014  push    rbx
0x180045016  push    rbp
0x180045017  push    rsi
0x180045018  push    rdi
0x180045019  push    r12
0x18004501b  push    r13
0x18004501d  push    r14
0x18004501f  push    r15
0x180045021  sub     rsp, 38h
0x180045025  mov     r13, rcx
0x180045028  mov     qword ptr [r8+450h], 0FFFFFFFFFFFFFFFFh
0x180045033  mov     ebp, 0F0h
0x180045038  mov     rsi, r8
0x18004503b  mov     ecx, ebp; dwBytes
0x18004503d  call    MALLOC
0x180045042  xor     r12d, r12d
0x180045045  mov     rbx, rax
0x180045048  test    rax, rax
0x18004504b  jnz     short loc_1800450B2
0x18004504d  lea     r8, [rsi+38h]
0x180045051  mov     ecx, 10000000h
0x180045056  lea     rdx, aSIptlsstartcli_4; "%s:IpTlsStartClient allocation failed"
0x18004505d  call    EventWrite0
0x180045062  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180045069  jz      short loc_180045089
0x18004506b  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180045072  mov     dword ptr [rsp+78h+dwPosition], 583h
0x18004507a  xor     r8d, r8d
0x18004507d  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x180045084  call    McTemplateU0psq_EventWriteTransfer
0x180045089  mov     edi, 8
0x18004508e  mov     dword ptr [rsi+4A8h], 1
0x180045098  mov     [rsi+4ACh], edi
0x18004509e  mov     eax, edi
0x1800450a0  add     rsp, 38h
0x1800450a4  pop     r15
0x1800450a6  pop     r14
0x1800450a8  pop     r13
0x1800450aa  pop     r12
0x1800450ac  pop     rdi
0x1800450ad  pop     rsi
0x1800450ae  pop     rbp
0x1800450af  pop     rbx
0x1800450b0  retn
0x1800450b2  mov     r8, rbp; Size
0x1800450b5  xor     edx, edx; Val
0x1800450b7  mov     rcx, rbx; void *
0x1800450ba  call    memset_0
0x1800450bf  lea     r15, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800450c6  mov     ebp, 1
0x1800450cb  mov     r14d, 58Bh
0x1800450d1  mov     [rbx+7Ch], ebp
0x1800450d4  mov     r9, r15
0x1800450d7  mov     dword ptr [rsp+78h+dwPosition], r14d
0x1800450dc  lea     r8, [rsi+38h]
0x1800450e0  mov     ecx, 20000000h
0x1800450e5  lea     rdx, aSReferenceIptl_0; "(%s: Reference IPTLS interface %S:%d"
0x1800450ec  call    EventWrite0
0x1800450f1  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x1800450f8  jz      short loc_180045111
0x1800450fa  mov     r9, r15
0x1800450fd  mov     dword ptr [rsp+78h+dwPosition], r14d
0x180045102  mov     r8, rsi
0x180045105  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_REFERENCE
0x18004510c  call    McTemplateU0psq_EventWriteTransfer
0x180045111  lock add [rsi+40Ch], ebp
0x180045118  mov     [rbx+80h], rsi
0x18004511f  lea     r14, [rbx+68h]
0x180045123  xorps   xmm0, xmm0
0x180045126  lea     rcx, [rbx+0B0h]; lpCriticalSection
0x18004512d  movups  xmmword ptr [rbx+58h], xmm0
0x180045131  mov     [rbx+8], r12
0x180045135  mov     [rbx], r12
0x180045138  mov     [rbx+78h], ebp
0x18004513b  mov     [rbx+3Ch], r12b
0x18004513f  mov     dword ptr [rbx+50h], 20h ; ' '
0x180045146  mov     [rbx+0E0h], bpl
0x18004514d  mov     [rbx+94h], ebp
0x180045153  mov     [r14+8], r14
0x180045157  mov     [r14], r14
0x18004515a  mov     dword ptr [rsi+4A8h], 0Ah
0x180045164  call    cs:__imp_InitializeCriticalSection
0x18004516b  nop     dword ptr [rax+rax+00h]
0x180045170  lea     rdi, stru_1800CC350
0x180045177  mov     rcx, rdi; lpCriticalSection
0x18004517a  call    cs:__imp_EnterCriticalSection
0x180045181  nop     dword ptr [rax+rax+00h]
0x180045186  cmp     cs:byte_1800CC378, r12b
0x18004518d  jz      short loc_1800451C4
0x18004518f  mov     rcx, rdi; lpCriticalSection
0x180045192  call    cs:__imp_LeaveCriticalSection
0x180045199  nop     dword ptr [rax+rax+00h]
0x18004519e  mov     r8, [rbx+80h]
0x1800451a5  lea     rdx, aSIptlsstartcli; "%s:IpTlsStartClient. Aborted due to shu"...
0x1800451ac  add     r8, 38h ; '8'
0x1800451b0  mov     ecx, 10000000h
0x1800451b5  call    EventWrite0
0x1800451ba  mov     edi, 3E3h
0x1800451bf  jmp     loc_180045480
0x1800451c4  mov     rcx, cs:qword_1800CC338; hEvent
0x1800451cb  add     cs:dword_1800CC330, ebp
0x1800451d1  call    cs:__imp_ResetEvent
0x1800451d8  nop     dword ptr [rax+rax+00h]
0x1800451dd  mov     rax, cs:qword_1800CC348
0x1800451e4  lea     rcx, qword_1800CC340
0x1800451eb  cmp     [rax], rcx
0x1800451ee  jnz     loc_180045540
0x1800451f4  mov     [r14], rcx
0x1800451f7  mov     rcx, rdi; lpCriticalSection
0x1800451fa  mov     [r14+8], rax
0x1800451fe  mov     [rax], r14
0x180045201  mov     cs:qword_1800CC348, r14
0x180045208  call    cs:__imp_LeaveCriticalSection
0x18004520f  nop     dword ptr [rax+rax+00h]
0x180045214  xor     r8d, r8d; pcbe
0x180045217  lea     rcx, IpTlsCleanupClientTimer; pfnwk
0x18004521e  mov     rdx, rbx; pv
0x180045221  call    cs:__imp_CreateThreadpoolWork
0x180045228  nop     dword ptr [rax+rax+00h]
0x18004522d  mov     [rbx+88h], rax
0x180045234  test    rax, rax
0x180045237  jnz     short loc_18004528E
0x180045239  mov     r8, [rbx+80h]
0x180045240  lea     rdx, aSIptlsstartcli_4; "%s:IpTlsStartClient allocation failed"
0x180045247  add     r8, 38h ; '8'
0x18004524b  mov     ecx, 10000000h
0x180045250  call    EventWrite0
0x180045255  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x18004525c  jz      short loc_180045278
0x18004525e  mov     dword ptr [rsp+78h+dwPosition], 5B6h
0x180045266  mov     r9, r15
0x180045269  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x180045270  xor     r8d, r8d
0x180045273  call    McTemplateU0psq_EventWriteTransfer
0x180045278  mov     edi, 8
0x18004527d  mov     [rsi+4A8h], ebp
0x180045283  mov     [rsi+4ACh], edi
0x180045289  jmp     loc_180045480
0x18004528e  xor     r8d, r8d; pcbe
0x180045291  lea     rcx, IpTlsClientReconnectTimeout; pfnti
0x180045298  mov     rdx, rbx; pv
0x18004529b  call    cs:__imp_CreateThreadpoolTimer
0x1800452a2  nop     dword ptr [rax+rax+00h]
0x1800452a7  mov     [rbx+0A0h], rax
0x1800452ae  test    rax, rax
0x1800452b1  jnz     short loc_1800452E2
0x1800452b3  mov     r8, [rbx+80h]
0x1800452ba  lea     rdx, aSIptlsstartcli_4; "%s:IpTlsStartClient allocation failed"
0x1800452c1  add     r8, 38h ; '8'
0x1800452c5  mov     ecx, 10000000h
0x1800452ca  call    EventWrite0
0x1800452cf  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x1800452d6  jz      short loc_180045278
0x1800452d8  mov     dword ptr [rsp+78h+dwPosition], 5CAh
0x1800452e0  jmp     short loc_180045266
0x1800452e2  lea     r8, [rbx+10h]
0x1800452e6  xor     edx, edx
0x1800452e8  mov     rcx, r13
0x1800452eb  call    cs:__imp_WebCreateUri
0x1800452f2  nop     dword ptr [rax+rax+00h]
0x1800452f7  mov     edi, eax
0x1800452f9  test    eax, eax
0x1800452fb  jz      short loc_180045335
0x1800452fd  mov     dword ptr [rsi+4A8h], 3
0x180045307  lea     rdx, aSWebcreateuriF; "%s:WebCreateUri failed: %d"
0x18004530e  mov     [rsi+4ACh], eax
0x180045314  mov     r9d, eax
0x180045317  mov     r8, [rbx+80h]
0x18004531e  mov     ecx, 10000000h
0x180045323  add     r8, 38h ; '8'
0x180045327  call    EventWrite0
0x18004532c  mov     [rbx+10h], r12
0x180045330  jmp     loc_180045480
0x180045335  xor     r9d, r9d; lpName
0x180045338  xor     r8d, r8d; bInitialState
0x18004533b  xor     edx, edx; bManualReset
0x18004533d  xor     ecx, ecx; lpEventAttributes
0x18004533f  call    cs:__imp_CreateEventW
0x180045346  nop     dword ptr [rax+rax+00h]
0x18004534b  mov     [rbx+98h], rax
0x180045352  test    rax, rax
0x180045355  jnz     short loc_180045396
0x180045357  mov     r8, [rbx+80h]
0x18004535e  lea     rdx, aSIptlsstartcli_4; "%s:IpTlsStartClient allocation failed"
0x180045365  add     r8, 38h ; '8'
0x180045369  mov     ecx, 10000000h
0x18004536e  call    EventWrite0
0x180045373  mov     [rsi+4A8h], ebp
0x180045379  mov     dword ptr [rsi+4ACh], 8
0x180045383  call    cs:__imp_GetLastError
0x18004538a  nop     dword ptr [rax+rax+00h]
0x18004538f  mov     edi, eax
0x180045391  jmp     loc_180045480
0x180045396  lea     r8, IpTlsQueryProxyInformation
0x18004539d  xor     edx, edx
0x18004539f  mov     rcx, rbx
0x1800453a2  call    IpTlsClientScheduleWorkItem
0x1800453a7  mov     edi, eax
0x1800453a9  test    eax, eax
0x1800453ab  jz      short loc_1800453D1
0x1800453ad  lea     rdx, aSIptlsstartcli_3; "%s:IpTlsStartClient IpTlsClientSchedule"...
0x1800453b4  mov     r8, [rbx+80h]
0x1800453bb  mov     ecx, 10000000h
0x1800453c0  add     r8, 38h ; '8'
0x1800453c4  mov     r9d, eax
0x1800453c7  call    EventWrite0
0x1800453cc  jmp     loc_180045480
0x1800453d1  mov     rcx, rbx
0x1800453d4  call    IpTlsRegisterForProxyNotifications
0x1800453d9  mov     edi, eax
0x1800453db  test    eax, eax
0x1800453dd  jz      short loc_1800453E8
0x1800453df  lea     rdx, aSIptlsstartcli_0; "%s:IpTlsStartClient IpTlsRegisterForPro"...
0x1800453e6  jmp     short loc_1800453B4
0x1800453e8  mov     rcx, rbx
0x1800453eb  call    IpTlsRegisterCSNotification
0x1800453f0  test    eax, eax
0x1800453f2  jz      short loc_180045413
0x1800453f4  mov     r8, [rbx+80h]
0x1800453fb  lea     rdx, aSIptlsstartcli_2; "%s:IpTlsStartClient IpTlsRegisterCSNoti"...
0x180045402  add     r8, 38h ; '8'
0x180045406  mov     r9d, eax
0x180045409  mov     ecx, 10000000h
0x18004540e  call    EventWrite0
0x180045413  lea     r9, pszFunction; "TLS_RSA_WITH_NULL_MD5"
0x18004541a  mov     dword ptr [rsp+78h+dwPosition], 0FFFFFFFFh; dwPosition
0x180045422  mov     r8d, 10002h; dwInterface
0x180045428  lea     rdx, pszContext; "SSL"
0x18004542f  mov     ecx, ebp; dwTable
0x180045431  call    cs:__imp_BCryptAddContextFunction
0x180045438  nop     dword ptr [rax+rax+00h]
0x18004543d  mov     r8, [rbx+80h]
0x180045444  mov     ecx, 10000000h
0x180045449  add     r8, 38h ; '8'
0x18004544d  mov     edi, eax
0x18004544f  test    eax, eax
0x180045451  jz      short loc_18004545F
0x180045453  lea     rdx, aSIptlsstartcli_1; "%s:IpTlsStartClient BCryptAddContextFun"...
0x18004545a  jmp     loc_1800453C4
0x18004545f  lea     rdx, aSStartingClien; "%s:Starting Client"
0x180045466  call    EventWrite0
0x18004546b  mov     dl, bpl
0x18004546e  mov     rcx, rbx
0x180045471  call    IpTlsRestartClient
0x180045476  mov     edi, eax
0x180045478  test    eax, eax
0x18004547a  jz      loc_180045532
0x180045480  mov     rcx, rbx
0x180045483  call    IpTlsDeregisterCSNotification
0x180045488  mov     rcx, rbx
0x18004548b  call    IpTlsDeregisterProxyNotifications
0x180045490  lea     rcx, stru_1800CC350; lpCriticalSection
0x180045497  call    cs:__imp_EnterCriticalSection
0x18004549e  nop     dword ptr [rax+rax+00h]
0x1800454a3  mov     rdx, [r14]
0x1800454a6  cmp     [rdx+8], r14
0x1800454aa  jnz     loc_180045540
0x1800454b0  mov     rax, [r14+8]
0x1800454b4  cmp     [rax], r14
0x1800454b7  jnz     loc_180045540
0x1800454bd  mov     [rax], rdx
0x1800454c0  lea     rcx, stru_1800CC350; lpCriticalSection
0x1800454c7  mov     [rdx+8], rax
0x1800454cb  mov     [r14+8], r14
0x1800454cf  mov     [r14], r14
0x1800454d2  call    cs:__imp_LeaveCriticalSection
0x1800454d9  nop     dword ptr [rax+rax+00h]
0x1800454de  mov     r8, [rbx+80h]
0x1800454e5  lea     rdx, aSDereferenceIp; "(%s: Dereference IPTLS client interface"...
0x1800454ec  mov     esi, 63Dh
0x1800454f1  add     r8, 38h ; '8'
0x1800454f5  mov     r9, r15
0x1800454f8  mov     dword ptr [rsp+78h+dwPosition], esi
0x1800454fc  mov     ecx, 20000000h
0x180045501  call    EventWrite0
0x180045506  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18004550d  jz      short loc_180045525
0x18004550f  mov     r9, r15
0x180045512  mov     dword ptr [rsp+78h+dwPosition], esi
0x180045516  mov     r8, rbx
0x180045519  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_INTERFACE_DEREFERENCE
0x180045520  call    McTemplateU0psq_EventWriteTransfer
0x180045525  mov     rcx, rbx
0x180045528  call    DereferenceInterfaceEx
0x18004552d  jmp     loc_18004509E
0x180045532  mov     [rsi+450h], rbx
0x180045539  xor     eax, eax
0x18004553b  jmp     loc_1800450A0
0x180045540  mov     ecx, 3
0x180045545  int     29h; Win8: RtlFailFast(ecx)
```
