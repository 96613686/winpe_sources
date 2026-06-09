# IpTlsClientScheduleReconnect

- ea: `0x1800492cc`
- end: `0x180049553`
- name: `IpTlsClientScheduleReconnect`
- size: `647`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800311e0`
- `0x180048a0c`
- `0x180062418`
- `0x1800632a0`
- `0x180063680`

## callees

- `0x180008210`
- `0x18000d7c0`
- `0x180040d90`
- `0x18004901c`
- `0x1800492cc`
- `0x18005b4c8`
- `0x180060b70`
- `0x1800616b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049307`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049307`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049398`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049531`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049398`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049531`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180049519`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180049519`

## string_xrefs

- `0x1800494a4`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x1800494e8`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`

## pseudocode

```c
__int64 __fastcall IpTlsClientScheduleReconnect(__int64 a1)
{
  unsigned __int32 v2; // ebx
  unsigned int v3; // ebx
  unsigned __int32 v4; // eax
  __int64 v5; // rbx
  int v6; // ebx
  unsigned int v7; // eax
  __int64 v8; // rbx
  __int64 v9; // r8
  int v10; // ecx
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  pftDueTime = 0;
  EventWriteEnterEx(0x20000, L"Entered: IpTlsClientScheduleReconnect");
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 176));
  v2 = *(_DWORD *)(a1 + 120);
  IpTlsInterfaceIndicateDisconnect(*(_QWORD *)(a1 + 128));
  if ( !v2 )
  {
    EventWrite0(0x10000000, L"IpTlsClientScheduleReconnect: Invalid State:%d. Aborting Reconnect", 0);
    v3 = 5023;
LABEL_18:
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 176));
    return v3;
  }
  if ( (*(_BYTE *)(a1 + 148) & 1) != 0 )
  {
    EventWrite0(0x10000000, L"IpTlsClientScheduleReconnect: Invalid State:%d. Aborting Reconnect", v2);
    v3 = 21;
    goto LABEL_18;
  }
  v4 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 120), 2, v2);
  if ( *(_DWORD *)(a1 + 120) == 2 )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 128) + 1192LL) = 11;
    IpTlsStoreInterfacePersistentValues(*(const BYTE **)(a1 + 128), *(_DWORD *)(*(_QWORD *)(a1 + 128) + 1024LL), 12);
    pftDueTime.dwHighDateTime = -1;
    if ( *(_QWORD *)(a1 + 168) )
    {
      v6 = *(_DWORD *)(a1 + 168);
      v7 = time(0) - v6;
      v8 = 900;
      if ( v7 <= 0x384uLL )
      {
        v8 = v7;
        if ( !v7 )
          v8 = 1;
      }
      v5 = -v8;
    }
    else
    {
      time((time_t *const)(a1 + 168));
      v5 = -30;
    }
    EventWrite0(
      0x10000000,
      L"IpTlsClientScheduleReconnect: Scheduling a reconnect after %d seconds",
      (unsigned int)-(int)v5);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_SCHEDULING_RECONNECT,
        *(_QWORD *)(a1 + 128) + 56LL,
        (unsigned int)-(int)v5);
    v9 = *(_QWORD *)(a1 + 128);
    pftDueTime = (struct _FILETIME)(10000000 * v5);
    EventWrite0(
      0x20000000,
      L"(%s: Reference IPTLS client interface %S:%d",
      v9 + 56,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsclient.c",
      2699);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v10,
        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_INTERFACE_REFERENCE,
        a1,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsclient.c",
        139);
    _InterlockedAdd((volatile signed __int32 *)(a1 + 124), 1u);
    SetThreadpoolTimer(*(PTP_TIMER *)(a1 + 160), &pftDueTime, 0, 0);
    v3 = 0;
    *(_BYTE *)(a1 + 216) = 1;
    goto LABEL_18;
  }
  EventWrite0(0x10000000, L"IpTlsClientScheduleReconnect: Invalid State:%d. Aborting Reconnect", v4);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 176));
  v3 = 5023;
  *(_DWORD *)(*(_QWORD *)(a1 + 128) + 1192LL) = 8;
  *(_DWORD *)(*(_QWORD *)(a1 + 128) + 1196LL) = 5023;
  IpTlsStoreInterfacePersistentValues(*(const BYTE **)(a1 + 128), *(_DWORD *)(*(_QWORD *)(a1 + 128) + 1024LL), 12);
  return v3;
}

```

## disassembly

```asm
0x1800492cc  mov     [rsp+arg_8], rbx
0x1800492d1  mov     [rsp+arg_10], rbp
0x1800492d6  push    rsi
0x1800492d7  push    rdi
0x1800492d8  push    r14
0x1800492da  sub     rsp, 30h
0x1800492de  mov     rdi, rcx
0x1800492e1  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0
0x1800492ea  mov     ecx, 20000h
0x1800492ef  lea     rdx, aEnteredIptlscl_0; "Entered: IpTlsClientScheduleReconnect"
0x1800492f6  xor     esi, esi
0x1800492f8  call    EventWriteEnterEx
0x1800492fd  lea     rbp, [rdi+0B0h]
0x180049304  mov     rcx, rbp; lpCriticalSection
0x180049307  call    cs:__imp_EnterCriticalSection
0x18004930e  nop     dword ptr [rax+rax+00h]
0x180049313  mov     ebx, [rdi+78h]
0x180049316  mov     rcx, [rdi+80h]
0x18004931d  call    IpTlsInterfaceIndicateDisconnect
0x180049322  test    ebx, ebx
0x180049324  jnz     short loc_180049344
0x180049326  xor     r8d, r8d
0x180049329  lea     rdx, aIptlsclientsch_0; "IpTlsClientScheduleReconnect: Invalid S"...
0x180049330  mov     ecx, 10000000h
0x180049335  call    EventWrite0
0x18004933a  mov     ebx, 139Fh
0x18004933f  jmp     loc_18004952E
0x180049344  mov     r14d, 1
0x18004934a  test    [rdi+94h], r14b
0x180049351  jz      short loc_180049370
0x180049353  mov     r8d, ebx
0x180049356  lea     rdx, aIptlsclientsch_0; "IpTlsClientScheduleReconnect: Invalid S"...
0x18004935d  mov     ecx, 10000000h
0x180049362  call    EventWrite0
0x180049367  lea     ebx, [r14+14h]
0x18004936b  jmp     loc_18004952E
0x180049370  mov     ecx, 2
0x180049375  mov     eax, ebx
0x180049377  lock cmpxchg [rdi+78h], ecx
0x18004937c  cmp     [rdi+78h], ecx
0x18004937f  jz      short loc_1800493E6
0x180049381  mov     r8d, eax
0x180049384  lea     rdx, aIptlsclientsch_0; "IpTlsClientScheduleReconnect: Invalid S"...
0x18004938b  mov     ecx, 10000000h
0x180049390  call    EventWrite0
0x180049395  mov     rcx, rbp; lpCriticalSection
0x180049398  call    cs:__imp_LeaveCriticalSection
0x18004939f  nop     dword ptr [rax+rax+00h]
0x1800493a4  mov     rax, [rdi+80h]
0x1800493ab  or      si, 0Ch
0x1800493af  mov     ebx, 139Fh
0x1800493b4  movzx   r8d, si
0x1800493b8  mov     dword ptr [rax+4A8h], 8
0x1800493c2  mov     rax, [rdi+80h]
0x1800493c9  mov     [rax+4ACh], ebx
0x1800493cf  mov     rcx, [rdi+80h]
0x1800493d6  mov     edx, [rcx+400h]
0x1800493dc  call    IpTlsStoreInterfacePersistentValues
0x1800493e1  jmp     loc_18004953D
0x1800493e6  mov     rax, [rdi+80h]
0x1800493ed  or      si, 0Ch
0x1800493f1  movzx   r8d, si
0x1800493f5  mov     dword ptr [rax+4A8h], 0Bh
0x1800493ff  mov     rcx, [rdi+80h]
0x180049406  mov     edx, [rcx+400h]
0x18004940c  call    IpTlsStoreInterfacePersistentValues
0x180049411  lea     rbx, [rdi+0A8h]
0x180049418  mov     [rsp+48h+pftDueTime.dwHighDateTime], 0FFFFFFFFh
0x180049420  cmp     qword ptr [rbx], 0
0x180049424  jnz     short loc_180049437
0x180049426  mov     rcx, rbx; Time
0x180049429  call    time
0x18004942e  mov     rbx, 0FFFFFFFFFFFFFFE2h
0x180049435  jmp     short loc_180049459
0x180049437  mov     ebx, [rbx]
0x180049439  xor     ecx, ecx; Time
0x18004943b  call    time
0x180049440  sub     eax, ebx
0x180049442  mov     ebx, 384h
0x180049447  mov     ecx, eax
0x180049449  cmp     rcx, rbx
0x18004944c  ja      short loc_180049456
0x18004944e  test    eax, eax
0x180049450  mov     ebx, ecx
0x180049452  cmovz   rbx, r14
0x180049456  neg     rbx
0x180049459  mov     eax, ebx
0x18004945b  lea     rdx, aIptlsclientsch; "IpTlsClientScheduleReconnect: Schedulin"...
0x180049462  neg     eax
0x180049464  mov     ecx, 10000000h
0x180049469  mov     r8d, eax
0x18004946c  mov     esi, eax
0x18004946e  call    EventWrite0
0x180049473  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18004947a  jz      short loc_18004949D
0x18004947c  mov     r8, [rdi+80h]
0x180049483  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_SCHEDULING_RECONNECT
0x18004948a  add     r8, 38h ; '8'
0x18004948e  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180049495  mov     r9d, esi
0x180049498  call    McTemplateU0zq_EventWriteTransfer
0x18004949d  mov     r8, [rdi+80h]
0x1800494a4  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800494ab  imul    rax, rbx, 989680h
0x1800494b2  mov     ebx, 0A8Bh
0x1800494b7  lea     rdx, aSReferenceIptl; "(%s: Reference IPTLS client interface %"...
0x1800494be  mov     rcx, rax
0x1800494c1  mov     [rsp+48h+pftDueTime.dwLowDateTime], eax
0x1800494c5  shr     rcx, 20h
0x1800494c9  add     r8, 38h ; '8'
0x1800494cd  mov     [rsp+48h+pftDueTime.dwHighDateTime], ecx
0x1800494d1  mov     ecx, 20000000h
0x1800494d6  mov     [rsp+48h+var_28], ebx
0x1800494da  call    EventWrite0
0x1800494df  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x1800494e6  jz      short loc_180049502
0x1800494e8  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800494ef  mov     [rsp+48h+var_28], ebx
0x1800494f3  mov     r8, rdi
0x1800494f6  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_INTERFACE_REFERENCE
0x1800494fd  call    McTemplateU0psq_EventWriteTransfer
0x180049502  lock add [rdi+7Ch], r14d
0x180049507  mov     rcx, [rdi+0A0h]; pti
0x18004950e  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180049513  xor     r9d, r9d; msWindowLength
0x180049516  xor     r8d, r8d; msPeriod
0x180049519  call    cs:__imp_SetThreadpoolTimer
0x180049520  nop     dword ptr [rax+rax+00h]
0x180049525  xor     ebx, ebx
0x180049527  mov     [rdi+0D8h], r14b
0x18004952e  mov     rcx, rbp; lpCriticalSection
0x180049531  call    cs:__imp_LeaveCriticalSection
0x180049538  nop     dword ptr [rax+rax+00h]
0x18004953d  mov     rbp, [rsp+48h+arg_10]
0x180049542  mov     eax, ebx
0x180049544  mov     rbx, [rsp+48h+arg_8]
0x180049549  add     rsp, 30h
0x18004954d  pop     r14
0x18004954f  pop     rdi
0x180049550  pop     rsi
0x180049551  retn
```
