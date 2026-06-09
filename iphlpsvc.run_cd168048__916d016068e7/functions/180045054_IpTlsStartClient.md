# IpTlsStartClient

- ea: `0x180045054`
- end: `0x180045587`
- name: `IpTlsStartClient`
- size: `1331`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005fa9c`

## callees

- `0x18000d7b0`
- `0x180012dbc`
- `0x180031688`
- `0x180031e28`
- `0x180045054`
- `0x180045590`
- `0x180045614`
- `0x180048a4c`
- `0x18004c1c8`
- `0x180061694`
- `0x180062c9c`
- `0x180062d88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180045211`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180045211`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004537f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004537f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800451a4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800451a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800451ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800454d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800451ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800454d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800451d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045248`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045512`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800451d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045248`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045512`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453c3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180045261`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180045261`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800452db`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800452db`
- `bcrypt!BCryptAddContextFunction` at `0x180045471`
- `bcrypt!BCryptAddContextFunction` at `0x180045471`
- `webio!__imp_WebCreateUri` at `0x18004532b`
- `webio!__imp_WebCreateUri` at `0x18004532b`

## string_xrefs

- `0x1800450ab`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x1800450ff`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x180045347`: `%s:WebCreateUri failed: %d`

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
0x180045054  push    rbx
0x180045056  push    rbp
0x180045057  push    rsi
0x180045058  push    rdi
0x180045059  push    r12
0x18004505b  push    r13
0x18004505d  push    r14
0x18004505f  push    r15
0x180045061  sub     rsp, 38h
0x180045065  mov     r13, rcx
0x180045068  mov     qword ptr [r8+450h], 0FFFFFFFFFFFFFFFFh
0x180045073  mov     ebp, 0F0h
0x180045078  mov     rsi, r8
0x18004507b  mov     ecx, ebp; dwBytes
0x18004507d  call    MALLOC
0x180045082  xor     r12d, r12d
0x180045085  mov     rbx, rax
0x180045088  test    rax, rax
0x18004508b  jnz     short loc_1800450F2
0x18004508d  lea     r8, [rsi+38h]
0x180045091  mov     ecx, 10000000h
0x180045096  lea     rdx, aSIptlsstartcli_4; "%s:IpTlsStartClient allocation failed"
0x18004509d  call    EventWrite0
0x1800450a2  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x1800450a9  jz      short loc_1800450C9
0x1800450ab  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800450b2  mov     dword ptr [rsp+78h+dwPosition], 583h
0x1800450ba  xor     r8d, r8d
0x1800450bd  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x1800450c4  call    McTemplateU0psq_EventWriteTransfer
0x1800450c9  mov     edi, 8
0x1800450ce  mov     dword ptr [rsi+4A8h], 1
0x1800450d8  mov     [rsi+4ACh], edi
0x1800450de  mov     eax, edi
0x1800450e0  add     rsp, 38h
0x1800450e4  pop     r15
0x1800450e6  pop     r14
0x1800450e8  pop     r13
0x1800450ea  pop     r12
0x1800450ec  pop     rdi
0x1800450ed  pop     rsi
0x1800450ee  pop     rbp
0x1800450ef  pop     rbx
0x1800450f0  retn
0x1800450f2  mov     r8, rbp; Size
0x1800450f5  xor     edx, edx; Val
0x1800450f7  mov     rcx, rbx; void *
0x1800450fa  call    memset_0
0x1800450ff  lea     r15, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180045106  mov     ebp, 1
0x18004510b  mov     r14d, 58Bh
0x180045111  mov     [rbx+7Ch], ebp
0x180045114  mov     r9, r15
0x180045117  mov     dword ptr [rsp+78h+dwPosition], r14d
0x18004511c  lea     r8, [rsi+38h]
0x180045120  mov     ecx, 20000000h
0x180045125  lea     rdx, aSReferenceIptl_0; "(%s: Reference IPTLS interface %S:%d"
0x18004512c  call    EventWrite0
0x180045131  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180045138  jz      short loc_180045151
0x18004513a  mov     r9, r15
0x18004513d  mov     dword ptr [rsp+78h+dwPosition], r14d
0x180045142  mov     r8, rsi
0x180045145  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_REFERENCE
0x18004514c  call    McTemplateU0psq_EventWriteTransfer
0x180045151  lock add [rsi+40Ch], ebp
0x180045158  mov     [rbx+80h], rsi
0x18004515f  lea     r14, [rbx+68h]
0x180045163  xorps   xmm0, xmm0
0x180045166  lea     rcx, [rbx+0B0h]; lpCriticalSection
0x18004516d  movups  xmmword ptr [rbx+58h], xmm0
0x180045171  mov     [rbx+8], r12
0x180045175  mov     [rbx], r12
0x180045178  mov     [rbx+78h], ebp
0x18004517b  mov     [rbx+3Ch], r12b
0x18004517f  mov     dword ptr [rbx+50h], 20h ; ' '
0x180045186  mov     [rbx+0E0h], bpl
0x18004518d  mov     [rbx+94h], ebp
0x180045193  mov     [r14+8], r14
0x180045197  mov     [r14], r14
0x18004519a  mov     dword ptr [rsi+4A8h], 0Ah
0x1800451a4  call    cs:__imp_InitializeCriticalSection
0x1800451ab  nop     dword ptr [rax+rax+00h]
0x1800451b0  lea     rdi, stru_1800CC350
0x1800451b7  mov     rcx, rdi; lpCriticalSection
0x1800451ba  call    cs:__imp_EnterCriticalSection
0x1800451c1  nop     dword ptr [rax+rax+00h]
0x1800451c6  cmp     cs:byte_1800CC378, r12b
0x1800451cd  jz      short loc_180045204
0x1800451cf  mov     rcx, rdi; lpCriticalSection
0x1800451d2  call    cs:__imp_LeaveCriticalSection
0x1800451d9  nop     dword ptr [rax+rax+00h]
0x1800451de  mov     r8, [rbx+80h]
0x1800451e5  lea     rdx, aSIptlsstartcli; "%s:IpTlsStartClient. Aborted due to shu"...
0x1800451ec  add     r8, 38h ; '8'
0x1800451f0  mov     ecx, 10000000h
0x1800451f5  call    EventWrite0
0x1800451fa  mov     edi, 3E3h
0x1800451ff  jmp     loc_1800454C0
0x180045204  mov     rcx, cs:qword_1800CC338; hEvent
0x18004520b  add     cs:dword_1800CC330, ebp
0x180045211  call    cs:__imp_ResetEvent
0x180045218  nop     dword ptr [rax+rax+00h]
0x18004521d  mov     rax, cs:qword_1800CC348
0x180045224  lea     rcx, qword_1800CC340
0x18004522b  cmp     [rax], rcx
0x18004522e  jnz     loc_180045580
0x180045234  mov     [r14], rcx
0x180045237  mov     rcx, rdi; lpCriticalSection
0x18004523a  mov     [r14+8], rax
0x18004523e  mov     [rax], r14
0x180045241  mov     cs:qword_1800CC348, r14
0x180045248  call    cs:__imp_LeaveCriticalSection
0x18004524f  nop     dword ptr [rax+rax+00h]
0x180045254  xor     r8d, r8d; pcbe
0x180045257  lea     rcx, IpTlsCleanupClientTimer; pfnwk
0x18004525e  mov     rdx, rbx; pv
0x180045261  call    cs:__imp_CreateThreadpoolWork
0x180045268  nop     dword ptr [rax+rax+00h]
0x18004526d  mov     [rbx+88h], rax
0x180045274  test    rax, rax
0x180045277  jnz     short loc_1800452CE
0x180045279  mov     r8, [rbx+80h]
0x180045280  lea     rdx, aSIptlsstartcli_4; "%s:IpTlsStartClient allocation failed"
0x180045287  add     r8, 38h ; '8'
0x18004528b  mov     ecx, 10000000h
0x180045290  call    EventWrite0
0x180045295  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x18004529c  jz      short loc_1800452B8
0x18004529e  mov     dword ptr [rsp+78h+dwPosition], 5B6h
0x1800452a6  mov     r9, r15
0x1800452a9  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x1800452b0  xor     r8d, r8d
0x1800452b3  call    McTemplateU0psq_EventWriteTransfer
0x1800452b8  mov     edi, 8
0x1800452bd  mov     [rsi+4A8h], ebp
0x1800452c3  mov     [rsi+4ACh], edi
0x1800452c9  jmp     loc_1800454C0
0x1800452ce  xor     r8d, r8d; pcbe
0x1800452d1  lea     rcx, IpTlsClientReconnectTimeout; pfnti
0x1800452d8  mov     rdx, rbx; pv
0x1800452db  call    cs:__imp_CreateThreadpoolTimer
0x1800452e2  nop     dword ptr [rax+rax+00h]
0x1800452e7  mov     [rbx+0A0h], rax
0x1800452ee  test    rax, rax
0x1800452f1  jnz     short loc_180045322
0x1800452f3  mov     r8, [rbx+80h]
0x1800452fa  lea     rdx, aSIptlsstartcli_4; "%s:IpTlsStartClient allocation failed"
0x180045301  add     r8, 38h ; '8'
0x180045305  mov     ecx, 10000000h
0x18004530a  call    EventWrite0
0x18004530f  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180045316  jz      short loc_1800452B8
0x180045318  mov     dword ptr [rsp+78h+dwPosition], 5CAh
0x180045320  jmp     short loc_1800452A6
0x180045322  lea     r8, [rbx+10h]
0x180045326  xor     edx, edx
0x180045328  mov     rcx, r13
0x18004532b  call    cs:__imp_WebCreateUri
0x180045332  nop     dword ptr [rax+rax+00h]
0x180045337  mov     edi, eax
0x180045339  test    eax, eax
0x18004533b  jz      short loc_180045375
0x18004533d  mov     dword ptr [rsi+4A8h], 3
0x180045347  lea     rdx, aSWebcreateuriF; "%s:WebCreateUri failed: %d"
0x18004534e  mov     [rsi+4ACh], eax
0x180045354  mov     r9d, eax
0x180045357  mov     r8, [rbx+80h]
0x18004535e  mov     ecx, 10000000h
0x180045363  add     r8, 38h ; '8'
0x180045367  call    EventWrite0
0x18004536c  mov     [rbx+10h], r12
0x180045370  jmp     loc_1800454C0
0x180045375  xor     r9d, r9d; lpName
0x180045378  xor     r8d, r8d; bInitialState
0x18004537b  xor     edx, edx; bManualReset
0x18004537d  xor     ecx, ecx; lpEventAttributes
0x18004537f  call    cs:__imp_CreateEventW
0x180045386  nop     dword ptr [rax+rax+00h]
0x18004538b  mov     [rbx+98h], rax
0x180045392  test    rax, rax
0x180045395  jnz     short loc_1800453D6
0x180045397  mov     r8, [rbx+80h]
0x18004539e  lea     rdx, aSIptlsstartcli_4; "%s:IpTlsStartClient allocation failed"
0x1800453a5  add     r8, 38h ; '8'
0x1800453a9  mov     ecx, 10000000h
0x1800453ae  call    EventWrite0
0x1800453b3  mov     [rsi+4A8h], ebp
0x1800453b9  mov     dword ptr [rsi+4ACh], 8
0x1800453c3  call    cs:__imp_GetLastError
0x1800453ca  nop     dword ptr [rax+rax+00h]
0x1800453cf  mov     edi, eax
0x1800453d1  jmp     loc_1800454C0
0x1800453d6  lea     r8, IpTlsQueryProxyInformation
0x1800453dd  xor     edx, edx
0x1800453df  mov     rcx, rbx
0x1800453e2  call    IpTlsClientScheduleWorkItem
0x1800453e7  mov     edi, eax
0x1800453e9  test    eax, eax
0x1800453eb  jz      short loc_180045411
0x1800453ed  lea     rdx, aSIptlsstartcli_3; "%s:IpTlsStartClient IpTlsClientSchedule"...
0x1800453f4  mov     r8, [rbx+80h]
0x1800453fb  mov     ecx, 10000000h
0x180045400  add     r8, 38h ; '8'
0x180045404  mov     r9d, eax
0x180045407  call    EventWrite0
0x18004540c  jmp     loc_1800454C0
0x180045411  mov     rcx, rbx
0x180045414  call    IpTlsRegisterForProxyNotifications
0x180045419  mov     edi, eax
0x18004541b  test    eax, eax
0x18004541d  jz      short loc_180045428
0x18004541f  lea     rdx, aSIptlsstartcli_0; "%s:IpTlsStartClient IpTlsRegisterForPro"...
0x180045426  jmp     short loc_1800453F4
0x180045428  mov     rcx, rbx
0x18004542b  call    IpTlsRegisterCSNotification
0x180045430  test    eax, eax
0x180045432  jz      short loc_180045453
0x180045434  mov     r8, [rbx+80h]
0x18004543b  lea     rdx, aSIptlsstartcli_2; "%s:IpTlsStartClient IpTlsRegisterCSNoti"...
0x180045442  add     r8, 38h ; '8'
0x180045446  mov     r9d, eax
0x180045449  mov     ecx, 10000000h
0x18004544e  call    EventWrite0
0x180045453  lea     r9, pszFunction; "TLS_RSA_WITH_NULL_MD5"
0x18004545a  mov     dword ptr [rsp+78h+dwPosition], 0FFFFFFFFh; dwPosition
0x180045462  mov     r8d, 10002h; dwInterface
0x180045468  lea     rdx, pszContext; "SSL"
0x18004546f  mov     ecx, ebp; dwTable
0x180045471  call    cs:__imp_BCryptAddContextFunction
0x180045478  nop     dword ptr [rax+rax+00h]
0x18004547d  mov     r8, [rbx+80h]
0x180045484  mov     ecx, 10000000h
0x180045489  add     r8, 38h ; '8'
0x18004548d  mov     edi, eax
0x18004548f  test    eax, eax
0x180045491  jz      short loc_18004549F
0x180045493  lea     rdx, aSIptlsstartcli_1; "%s:IpTlsStartClient BCryptAddContextFun"...
0x18004549a  jmp     loc_180045404
0x18004549f  lea     rdx, aSStartingClien; "%s:Starting Client"
0x1800454a6  call    EventWrite0
0x1800454ab  mov     dl, bpl
0x1800454ae  mov     rcx, rbx
0x1800454b1  call    IpTlsRestartClient
0x1800454b6  mov     edi, eax
0x1800454b8  test    eax, eax
0x1800454ba  jz      loc_180045572
0x1800454c0  mov     rcx, rbx
0x1800454c3  call    IpTlsDeregisterCSNotification
0x1800454c8  mov     rcx, rbx
0x1800454cb  call    IpTlsDeregisterProxyNotifications
0x1800454d0  lea     rcx, stru_1800CC350; lpCriticalSection
0x1800454d7  call    cs:__imp_EnterCriticalSection
0x1800454de  nop     dword ptr [rax+rax+00h]
0x1800454e3  mov     rdx, [r14]
0x1800454e6  cmp     [rdx+8], r14
0x1800454ea  jnz     loc_180045580
0x1800454f0  mov     rax, [r14+8]
0x1800454f4  cmp     [rax], r14
0x1800454f7  jnz     loc_180045580
0x1800454fd  mov     [rax], rdx
0x180045500  lea     rcx, stru_1800CC350; lpCriticalSection
0x180045507  mov     [rdx+8], rax
0x18004550b  mov     [r14+8], r14
0x18004550f  mov     [r14], r14
0x180045512  call    cs:__imp_LeaveCriticalSection
0x180045519  nop     dword ptr [rax+rax+00h]
0x18004551e  mov     r8, [rbx+80h]
0x180045525  lea     rdx, aSDereferenceIp; "(%s: Dereference IPTLS client interface"...
0x18004552c  mov     esi, 63Dh
0x180045531  add     r8, 38h ; '8'
0x180045535  mov     r9, r15
0x180045538  mov     dword ptr [rsp+78h+dwPosition], esi
0x18004553c  mov     ecx, 20000000h
0x180045541  call    EventWrite0
0x180045546  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18004554d  jz      short loc_180045565
0x18004554f  mov     r9, r15
0x180045552  mov     dword ptr [rsp+78h+dwPosition], esi
0x180045556  mov     r8, rbx
0x180045559  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_INTERFACE_DEREFERENCE
0x180045560  call    McTemplateU0psq_EventWriteTransfer
0x180045565  mov     rcx, rbx
0x180045568  call    DereferenceInterfaceEx
0x18004556d  jmp     loc_1800450DE
0x180045572  mov     [rsi+450h], rbx
0x180045579  xor     eax, eax
0x18004557b  jmp     loc_1800450E0
0x180045580  mov     ecx, 3
0x180045585  int     29h; Win8: RtlFailFast(ecx)
```
