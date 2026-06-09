# IpTlsClientScheduleReconnect

- ea: `0x18004930c`
- end: `0x180049593`
- name: `IpTlsClientScheduleReconnect`
- size: `647`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800311d0`
- `0x180048a4c`
- `0x1800623f8`
- `0x180063280`
- `0x180063660`

## callees

- `0x180008200`
- `0x18000d7b0`
- `0x180040dd0`
- `0x18004905c`
- `0x18004930c`
- `0x18005b4a8`
- `0x180060b50`
- `0x180061694`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049347`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049347`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800493d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049571`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800493d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049571`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180049559`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180049559`

## string_xrefs

- `0x1800494e4`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x180049528`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`

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
0x18004930c  mov     [rsp+arg_8], rbx
0x180049311  mov     [rsp+arg_10], rbp
0x180049316  push    rsi
0x180049317  push    rdi
0x180049318  push    r14
0x18004931a  sub     rsp, 30h
0x18004931e  mov     rdi, rcx
0x180049321  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0
0x18004932a  mov     ecx, 20000h
0x18004932f  lea     rdx, aEnteredIptlscl_0; "Entered: IpTlsClientScheduleReconnect"
0x180049336  xor     esi, esi
0x180049338  call    EventWriteEnterEx
0x18004933d  lea     rbp, [rdi+0B0h]
0x180049344  mov     rcx, rbp; lpCriticalSection
0x180049347  call    cs:__imp_EnterCriticalSection
0x18004934e  nop     dword ptr [rax+rax+00h]
0x180049353  mov     ebx, [rdi+78h]
0x180049356  mov     rcx, [rdi+80h]
0x18004935d  call    IpTlsInterfaceIndicateDisconnect
0x180049362  test    ebx, ebx
0x180049364  jnz     short loc_180049384
0x180049366  xor     r8d, r8d
0x180049369  lea     rdx, aIptlsclientsch_0; "IpTlsClientScheduleReconnect: Invalid S"...
0x180049370  mov     ecx, 10000000h
0x180049375  call    EventWrite0
0x18004937a  mov     ebx, 139Fh
0x18004937f  jmp     loc_18004956E
0x180049384  mov     r14d, 1
0x18004938a  test    [rdi+94h], r14b
0x180049391  jz      short loc_1800493B0
0x180049393  mov     r8d, ebx
0x180049396  lea     rdx, aIptlsclientsch_0; "IpTlsClientScheduleReconnect: Invalid S"...
0x18004939d  mov     ecx, 10000000h
0x1800493a2  call    EventWrite0
0x1800493a7  lea     ebx, [r14+14h]
0x1800493ab  jmp     loc_18004956E
0x1800493b0  mov     ecx, 2
0x1800493b5  mov     eax, ebx
0x1800493b7  lock cmpxchg [rdi+78h], ecx
0x1800493bc  cmp     [rdi+78h], ecx
0x1800493bf  jz      short loc_180049426
0x1800493c1  mov     r8d, eax
0x1800493c4  lea     rdx, aIptlsclientsch_0; "IpTlsClientScheduleReconnect: Invalid S"...
0x1800493cb  mov     ecx, 10000000h
0x1800493d0  call    EventWrite0
0x1800493d5  mov     rcx, rbp; lpCriticalSection
0x1800493d8  call    cs:__imp_LeaveCriticalSection
0x1800493df  nop     dword ptr [rax+rax+00h]
0x1800493e4  mov     rax, [rdi+80h]
0x1800493eb  or      si, 0Ch
0x1800493ef  mov     ebx, 139Fh
0x1800493f4  movzx   r8d, si
0x1800493f8  mov     dword ptr [rax+4A8h], 8
0x180049402  mov     rax, [rdi+80h]
0x180049409  mov     [rax+4ACh], ebx
0x18004940f  mov     rcx, [rdi+80h]
0x180049416  mov     edx, [rcx+400h]
0x18004941c  call    IpTlsStoreInterfacePersistentValues
0x180049421  jmp     loc_18004957D
0x180049426  mov     rax, [rdi+80h]
0x18004942d  or      si, 0Ch
0x180049431  movzx   r8d, si
0x180049435  mov     dword ptr [rax+4A8h], 0Bh
0x18004943f  mov     rcx, [rdi+80h]
0x180049446  mov     edx, [rcx+400h]
0x18004944c  call    IpTlsStoreInterfacePersistentValues
0x180049451  lea     rbx, [rdi+0A8h]
0x180049458  mov     [rsp+48h+pftDueTime.dwHighDateTime], 0FFFFFFFFh
0x180049460  cmp     qword ptr [rbx], 0
0x180049464  jnz     short loc_180049477
0x180049466  mov     rcx, rbx; Time
0x180049469  call    time
0x18004946e  mov     rbx, 0FFFFFFFFFFFFFFE2h
0x180049475  jmp     short loc_180049499
0x180049477  mov     ebx, [rbx]
0x180049479  xor     ecx, ecx; Time
0x18004947b  call    time
0x180049480  sub     eax, ebx
0x180049482  mov     ebx, 384h
0x180049487  mov     ecx, eax
0x180049489  cmp     rcx, rbx
0x18004948c  ja      short loc_180049496
0x18004948e  test    eax, eax
0x180049490  mov     ebx, ecx
0x180049492  cmovz   rbx, r14
0x180049496  neg     rbx
0x180049499  mov     eax, ebx
0x18004949b  lea     rdx, aIptlsclientsch; "IpTlsClientScheduleReconnect: Schedulin"...
0x1800494a2  neg     eax
0x1800494a4  mov     ecx, 10000000h
0x1800494a9  mov     r8d, eax
0x1800494ac  mov     esi, eax
0x1800494ae  call    EventWrite0
0x1800494b3  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x1800494ba  jz      short loc_1800494DD
0x1800494bc  mov     r8, [rdi+80h]
0x1800494c3  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_SCHEDULING_RECONNECT
0x1800494ca  add     r8, 38h ; '8'
0x1800494ce  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800494d5  mov     r9d, esi
0x1800494d8  call    McTemplateU0zq_EventWriteTransfer
0x1800494dd  mov     r8, [rdi+80h]
0x1800494e4  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800494eb  imul    rax, rbx, 989680h
0x1800494f2  mov     ebx, 0A8Bh
0x1800494f7  lea     rdx, aSReferenceIptl; "(%s: Reference IPTLS client interface %"...
0x1800494fe  mov     rcx, rax
0x180049501  mov     [rsp+48h+pftDueTime.dwLowDateTime], eax
0x180049505  shr     rcx, 20h
0x180049509  add     r8, 38h ; '8'
0x18004950d  mov     [rsp+48h+pftDueTime.dwHighDateTime], ecx
0x180049511  mov     ecx, 20000000h
0x180049516  mov     [rsp+48h+var_28], ebx
0x18004951a  call    EventWrite0
0x18004951f  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180049526  jz      short loc_180049542
0x180049528  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18004952f  mov     [rsp+48h+var_28], ebx
0x180049533  mov     r8, rdi
0x180049536  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_INTERFACE_REFERENCE
0x18004953d  call    McTemplateU0psq_EventWriteTransfer
0x180049542  lock add [rdi+7Ch], r14d
0x180049547  mov     rcx, [rdi+0A0h]; pti
0x18004954e  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180049553  xor     r9d, r9d; msWindowLength
0x180049556  xor     r8d, r8d; msPeriod
0x180049559  call    cs:__imp_SetThreadpoolTimer
0x180049560  nop     dword ptr [rax+rax+00h]
0x180049565  xor     ebx, ebx
0x180049567  mov     [rdi+0D8h], r14b
0x18004956e  mov     rcx, rbp; lpCriticalSection
0x180049571  call    cs:__imp_LeaveCriticalSection
0x180049578  nop     dword ptr [rax+rax+00h]
0x18004957d  mov     rbp, [rsp+48h+arg_10]
0x180049582  mov     eax, ebx
0x180049584  mov     rbx, [rsp+48h+arg_8]
0x180049589  add     rsp, 30h
0x18004958d  pop     r14
0x18004958f  pop     rdi
0x180049590  pop     rsi
0x180049591  retn
```
