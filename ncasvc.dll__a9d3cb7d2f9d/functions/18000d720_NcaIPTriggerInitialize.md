# NcaIPTriggerInitialize

- ea: `0x18000d720`
- end: `0x18000db21`
- name: `NcaIPTriggerInitialize`
- size: `1025`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180004f34`
- `0x180006544`
- `0x1800065c8`
- `0x18000b488`
- `0x18000d720`
- `0x18000db90`
- `0x180018ffc`
- `0x180019784`
- `0x18001cc3e`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d7f9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d854`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d907`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d7f9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d854`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d907`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18000d8ac`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18000d8ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d86c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d91f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d86c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d91f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d988`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000d970`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000d970`
- `IPHLPAPI!NotifyRouteChange2` at `0x18000d9f5`
- `IPHLPAPI!NotifyRouteChange2` at `0x18000d9f5`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x18000da4d`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x18000da4d`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x18000da9a`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x18000da9a`

## pseudocode

```c
__int64 __fastcall NcaIPTriggerInitialize(__int64 a1)
{
  int v1; // eax
  unsigned int LastError; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  int v5; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx

  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)ModuleInitializeStart, L"IPTrigger");
  memset_0(&gNcaIpTriggerComp, 0, 0xD8u);
  v1 = NcaSyncedListCreate(&stru_180029900);
  LastError = NcaHResultToWindowsError(v1);
  if ( LastError )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_47;
    v4 = 18;
    goto LABEL_46;
  }
  v5 = NcaCriticalSectionCreate(&stru_1800298B8);
  LastError = NcaHResultToWindowsError(v5);
  if ( LastError )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_47;
    v4 = 19;
    goto LABEL_46;
  }
  gNcaIpTriggerComp = CreateEventW(0, 0, 0, 0);
  if ( !gNcaIpTriggerComp )
  {
    LastError = GetLastError();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 20;
LABEL_31:
      WPP_SF_d(v6[2], v7, &WPP_b6091e6574da34fd67da549d87f23c15_Traceguids, LastError);
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  qword_180029878 = CreateEventW(0, 1, 0, 0);
  if ( !qword_180029878 )
  {
    LastError = GetLastError();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 21;
      goto LABEL_31;
    }
LABEL_32:
    if ( !LastError )
      goto LABEL_48;
    goto LABEL_47;
  }
  qword_180029880 = (__int64)CreateWaitableTimerW(0, 1, 0);
  if ( !qword_180029880 )
  {
    LastError = GetLastError();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 22;
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  qword_1800298A8 = (__int64)CreateEventW(0, 0, 0, 0);
  if ( !qword_1800298A8 )
  {
    LastError = GetLastError();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 23;
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  qword_1800298A0 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)NVNWorkerThread, &gNcaIpTriggerComp, 0, 0);
  if ( !qword_1800298A0 )
  {
    LastError = GetLastError();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 24;
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  dword_1800298B0 = 1;
  LastError = NotifyRouteChange2(0, NotifyRouteCallback, &gNcaIpTriggerComp, 0, &NotificationHandle);
  if ( LastError )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_47;
    v4 = 25;
    goto LABEL_46;
  }
  LastError = NotifyIpInterfaceChange(0, NotifyIpInterfaceCallback, &gNcaIpTriggerComp, 0, &qword_180029890);
  if ( LastError )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_47;
    v4 = 26;
    goto LABEL_46;
  }
  LastError = NotifyUnicastIpAddressChange(0, NotifyIpUnicastAddrCallback, &gNcaIpTriggerComp, 0, &qword_180029898);
  if ( !LastError )
    goto LABEL_48;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v4 = 27;
LABEL_46:
    WPP_SF_d(v3[2], v4, &WPP_b6091e6574da34fd67da549d87f23c15_Traceguids, LastError);
  }
LABEL_47:
  NcaIPTriggerShutdown();
LABEL_48:
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0zx_EventWriteTransfer(
      (__int64)v6,
      (const EVENT_DESCRIPTOR *)ModuleInitializeEnd,
      L"IPTrigger",
      LastError);
  if ( (int)LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x18000d720  mov     [rsp+arg_0], rbx
0x18000d725  mov     [rsp+arg_8], rsi
0x18000d72a  push    rdi
0x18000d72b  sub     rsp, 30h
0x18000d72f  mov     edi, 1
0x18000d734  test    cs:Microsoft_Windows_NcasvcEnableBits, dil
0x18000d73b  jz      short loc_18000D750
0x18000d73d  lea     r8, aIptrigger; "IPTrigger"
0x18000d744  lea     rdx, ModuleInitializeStart
0x18000d74b  call    McTemplateU0z_EventWriteTransfer
0x18000d750  lea     rsi, ?gNcaIpTriggerComp@@3UNCA_IP_TRIGGER_COMP_@@A; NCA_IP_TRIGGER_COMP_ gNcaIpTriggerComp
0x18000d757  xor     edx, edx; Val
0x18000d759  mov     rcx, rsi; void *
0x18000d75c  mov     r8d, 0D8h; Size
0x18000d762  call    memset_0
0x18000d767  lea     rcx, stru_180029900
0x18000d76e  call    NcaSyncedListCreate
0x18000d773  mov     ecx, eax
0x18000d775  call    NcaHResultToWindowsError
0x18000d77a  mov     ebx, eax
0x18000d77c  test    eax, eax
0x18000d77e  jz      short loc_18000D7AB
0x18000d780  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d787  lea     rax, WPP_GLOBAL_Control
0x18000d78e  cmp     rcx, rax
0x18000d791  jz      loc_18000DADD
0x18000d797  test    [rcx+1Ch], dil
0x18000d79b  jz      loc_18000DADD
0x18000d7a1  mov     edx, 12h
0x18000d7a6  jmp     loc_18000DACA
0x18000d7ab  lea     rcx, stru_1800298B8; lpCriticalSection
0x18000d7b2  call    NcaCriticalSectionCreate
0x18000d7b7  mov     ecx, eax
0x18000d7b9  call    NcaHResultToWindowsError
0x18000d7be  mov     ebx, eax
0x18000d7c0  test    eax, eax
0x18000d7c2  jz      short loc_18000D7EF
0x18000d7c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7cb  lea     rax, WPP_GLOBAL_Control
0x18000d7d2  cmp     rcx, rax
0x18000d7d5  jz      loc_18000DADD
0x18000d7db  test    [rcx+1Ch], dil
0x18000d7df  jz      loc_18000DADD
0x18000d7e5  mov     edx, 13h
0x18000d7ea  jmp     loc_18000DACA
0x18000d7ef  xor     r9d, r9d; lpName
0x18000d7f2  xor     r8d, r8d; bInitialState
0x18000d7f5  xor     edx, edx; bManualReset
0x18000d7f7  xor     ecx, ecx; lpEventAttributes
0x18000d7f9  call    cs:__imp_CreateEventW
0x18000d800  nop     dword ptr [rax+rax+00h]
0x18000d805  mov     cs:?gNcaIpTriggerComp@@3UNCA_IP_TRIGGER_COMP_@@A, rax; NCA_IP_TRIGGER_COMP_ gNcaIpTriggerComp
0x18000d80c  test    rax, rax
0x18000d80f  jnz     short loc_18000D84A
0x18000d811  call    cs:__imp_GetLastError
0x18000d818  nop     dword ptr [rax+rax+00h]
0x18000d81d  mov     ebx, eax
0x18000d81f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d826  lea     rax, WPP_GLOBAL_Control
0x18000d82d  cmp     rcx, rax
0x18000d830  jz      loc_18000D9C7
0x18000d836  test    [rcx+1Ch], dil
0x18000d83a  jz      loc_18000D9C7
0x18000d840  mov     edx, 14h
0x18000d845  jmp     loc_18000D9B4
0x18000d84a  xor     r9d, r9d; lpName
0x18000d84d  xor     r8d, r8d; bInitialState
0x18000d850  mov     edx, edi; bManualReset
0x18000d852  xor     ecx, ecx; lpEventAttributes
0x18000d854  call    cs:__imp_CreateEventW
0x18000d85b  nop     dword ptr [rax+rax+00h]
0x18000d860  mov     cs:qword_180029878, rax
0x18000d867  test    rax, rax
0x18000d86a  jnz     short loc_18000D8A5
0x18000d86c  call    cs:__imp_GetLastError
0x18000d873  nop     dword ptr [rax+rax+00h]
0x18000d878  mov     ebx, eax
0x18000d87a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d881  lea     rax, WPP_GLOBAL_Control
0x18000d888  cmp     rcx, rax
0x18000d88b  jz      loc_18000D9C7
0x18000d891  test    [rcx+1Ch], dil
0x18000d895  jz      loc_18000D9C7
0x18000d89b  mov     edx, 15h
0x18000d8a0  jmp     loc_18000D9B4
0x18000d8a5  xor     r8d, r8d; lpTimerName
0x18000d8a8  mov     edx, edi; bManualReset
0x18000d8aa  xor     ecx, ecx; lpTimerAttributes
0x18000d8ac  call    cs:__imp_CreateWaitableTimerW
0x18000d8b3  nop     dword ptr [rax+rax+00h]
0x18000d8b8  mov     cs:qword_180029880, rax
0x18000d8bf  test    rax, rax
0x18000d8c2  jnz     short loc_18000D8FD
0x18000d8c4  call    cs:__imp_GetLastError
0x18000d8cb  nop     dword ptr [rax+rax+00h]
0x18000d8d0  mov     ebx, eax
0x18000d8d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8d9  lea     rax, WPP_GLOBAL_Control
0x18000d8e0  cmp     rcx, rax
0x18000d8e3  jz      loc_18000D9C7
0x18000d8e9  test    [rcx+1Ch], dil
0x18000d8ed  jz      loc_18000D9C7
0x18000d8f3  mov     edx, 16h
0x18000d8f8  jmp     loc_18000D9B4
0x18000d8fd  xor     r9d, r9d; lpName
0x18000d900  xor     r8d, r8d; bInitialState
0x18000d903  xor     edx, edx; bManualReset
0x18000d905  xor     ecx, ecx; lpEventAttributes
0x18000d907  call    cs:__imp_CreateEventW
0x18000d90e  nop     dword ptr [rax+rax+00h]
0x18000d913  mov     cs:qword_1800298A8, rax
0x18000d91a  test    rax, rax
0x18000d91d  jnz     short loc_18000D951
0x18000d91f  call    cs:__imp_GetLastError
0x18000d926  nop     dword ptr [rax+rax+00h]
0x18000d92b  mov     ebx, eax
0x18000d92d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d934  lea     rax, WPP_GLOBAL_Control
0x18000d93b  cmp     rcx, rax
0x18000d93e  jz      loc_18000D9C7
0x18000d944  test    [rcx+1Ch], dil
0x18000d948  jz      short loc_18000D9C7
0x18000d94a  mov     edx, 17h
0x18000d94f  jmp     short loc_18000D9B4
0x18000d951  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18000d95a  lea     r8, ?NVNWorkerThread@@YAKPEAX@Z; lpStartAddress
0x18000d961  mov     r9, rsi; lpParameter
0x18000d964  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18000d96c  xor     edx, edx; dwStackSize
0x18000d96e  xor     ecx, ecx; lpThreadAttributes
0x18000d970  call    cs:__imp_CreateThread
0x18000d977  nop     dword ptr [rax+rax+00h]
0x18000d97c  mov     cs:qword_1800298A0, rax
0x18000d983  test    rax, rax
0x18000d986  jnz     short loc_18000D9D4
0x18000d988  call    cs:__imp_GetLastError
0x18000d98f  nop     dword ptr [rax+rax+00h]
0x18000d994  mov     ebx, eax
0x18000d996  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d99d  lea     rax, WPP_GLOBAL_Control
0x18000d9a4  cmp     rcx, rax
0x18000d9a7  jz      short loc_18000D9C7
0x18000d9a9  test    [rcx+1Ch], dil
0x18000d9ad  jz      short loc_18000D9C7
0x18000d9af  mov     edx, 18h
0x18000d9b4  mov     rcx, [rcx+10h]
0x18000d9b8  lea     r8, WPP_b6091e6574da34fd67da549d87f23c15_Traceguids
0x18000d9bf  mov     r9d, ebx
0x18000d9c2  call    WPP_SF_d
0x18000d9c7  test    ebx, ebx
0x18000d9c9  jz      loc_18000DAE2
0x18000d9cf  jmp     loc_18000DADD
0x18000d9d4  lea     rax, NotificationHandle
0x18000d9db  mov     cs:dword_1800298B0, edi
0x18000d9e1  xor     ecx, ecx; AddressFamily
0x18000d9e3  mov     qword ptr [rsp+38h+dwCreationFlags], rax; NotificationHandle
0x18000d9e8  xor     r9d, r9d; InitialNotification
0x18000d9eb  lea     rdx, ?NotifyRouteCallback@@YAXPEAXPEAU_MIB_IPFORWARD_ROW2@@W4_MIB_NOTIFICATION_TYPE@@@Z; Callback
0x18000d9f2  mov     r8, rsi; CallerContext
0x18000d9f5  call    cs:__imp_NotifyRouteChange2
0x18000d9fc  nop     dword ptr [rax+rax+00h]
0x18000da01  mov     ebx, eax
0x18000da03  test    eax, eax
0x18000da05  jz      short loc_18000DA32
0x18000da07  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da0e  lea     rax, WPP_GLOBAL_Control
0x18000da15  cmp     rcx, rax
0x18000da18  jz      loc_18000DADD
0x18000da1e  test    [rcx+1Ch], dil
0x18000da22  jz      loc_18000DADD
0x18000da28  mov     edx, 19h
0x18000da2d  jmp     loc_18000DACA
0x18000da32  lea     rax, qword_180029890
0x18000da39  xor     ecx, ecx; Family
0x18000da3b  xor     r9d, r9d; InitialNotification
0x18000da3e  mov     qword ptr [rsp+38h+dwCreationFlags], rax; NotificationHandle
0x18000da43  mov     r8, rsi; CallerContext
0x18000da46  lea     rdx, ?NotifyIpInterfaceCallback@@YAXPEAXPEAU_MIB_IPFORWARD_ROW2@@W4_MIB_NOTIFICATION_TYPE@@@Z; Callback
0x18000da4d  call    cs:__imp_NotifyIpInterfaceChange
0x18000da54  nop     dword ptr [rax+rax+00h]
0x18000da59  mov     ebx, eax
0x18000da5b  test    eax, eax
0x18000da5d  jz      short loc_18000DA7F
0x18000da5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da66  lea     rax, WPP_GLOBAL_Control
0x18000da6d  cmp     rcx, rax
0x18000da70  jz      short loc_18000DADD
0x18000da72  test    [rcx+1Ch], dil
0x18000da76  jz      short loc_18000DADD
0x18000da78  mov     edx, 1Ah
0x18000da7d  jmp     short loc_18000DACA
0x18000da7f  lea     rax, qword_180029898
0x18000da86  xor     ecx, ecx; Family
0x18000da88  xor     r9d, r9d; InitialNotification
0x18000da8b  mov     qword ptr [rsp+38h+dwCreationFlags], rax; NotificationHandle
0x18000da90  mov     r8, rsi; CallerContext
0x18000da93  lea     rdx, ?NotifyIpUnicastAddrCallback@@YAXPEAXPEAU_MIB_IPFORWARD_ROW2@@W4_MIB_NOTIFICATION_TYPE@@@Z; Callback
0x18000da9a  call    cs:__imp_NotifyUnicastIpAddressChange
0x18000daa1  nop     dword ptr [rax+rax+00h]
0x18000daa6  mov     ebx, eax
0x18000daa8  test    eax, eax
0x18000daaa  jz      short loc_18000DAE2
0x18000daac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dab3  lea     rax, WPP_GLOBAL_Control
0x18000daba  cmp     rcx, rax
0x18000dabd  jz      short loc_18000DADD
0x18000dabf  test    [rcx+1Ch], dil
0x18000dac3  jz      short loc_18000DADD
0x18000dac5  mov     edx, 1Bh
0x18000daca  mov     rcx, [rcx+10h]
0x18000dace  lea     r8, WPP_b6091e6574da34fd67da549d87f23c15_Traceguids
0x18000dad5  mov     r9d, ebx
0x18000dad8  call    WPP_SF_d
0x18000dadd  call    NcaIPTriggerShutdown
0x18000dae2  test    cs:Microsoft_Windows_NcasvcEnableBits, dil
0x18000dae9  jz      short loc_18000DB01
0x18000daeb  mov     r9d, ebx
0x18000daee  lea     r8, aIptrigger; "IPTrigger"
0x18000daf5  lea     rdx, ModuleInitializeEnd
0x18000dafc  call    McTemplateU0zx_EventWriteTransfer
0x18000db01  test    ebx, ebx
0x18000db03  jle     short loc_18000DB0E
0x18000db05  movzx   ebx, bx
0x18000db08  or      ebx, 80070000h
0x18000db0e  mov     rsi, [rsp+38h+arg_8]
0x18000db13  mov     eax, ebx
0x18000db15  mov     rbx, [rsp+38h+arg_0]
0x18000db1a  add     rsp, 30h
0x18000db1e  pop     rdi
0x18000db1f  retn
```
