# SockSanInitialize

- ea: `0x18001e5a4`
- end: `0x18001ea5c`
- name: `SockSanInitialize`
- size: `1208`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000cc50`
- `0x18003b008`
- `0x180042c70`

## callees

- `0x18001e5a4`
- `0x1800231f0`
- `0x180038104`
- `0x18003ae8c`

## import_xrefs

- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x18001e930`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x18001e930`
- `ntdll!NtOpenKey` at `0x18001e622`
- `ntdll!NtOpenKey` at `0x18001e622`
- `ntdll!NtClose` at `0x18001e661`
- `ntdll!NtClose` at `0x18001e661`
- `ntdll!RtlInitUnicodeString` at `0x18001e5dc`
- `ntdll!RtlInitUnicodeString` at `0x18001e5dc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e983`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e983`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001e96c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001e96c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e949`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e996`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e949`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e996`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001e6ea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001e6ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001e688`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001e688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e6b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e77f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e6b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e77f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001e6ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001e6f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001e6ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001e6f8`

## string_xrefs

- `0x18001e5d1`: `\Registry\Machine\System\CurrentControlSet\Services\Winsock\Parameters\TCP on SAN`

## pseudocode

```c
__int64 SockSanInitialize()
{
  DWORD LastError; // eax
  __int64 v1; // rdx
  unsigned int v2; // r14d
  DWORD TickCount; // ebx
  DWORD v4; // esi
  NTSTATUS v6; // ebx
  struct _UNICODE_STRING v7; // [rsp+20h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-58h] BYREF
  void *KeyHandle; // [rsp+90h] [rbp+8h] BYREF

  v7 = 0;
  memset(&ObjectAttributes, 0, 44);
  KeyHandle = 0;
  RtlInitUnicodeString(
    &v7,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Winsock\\Parameters\\TCP on SAN");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &v7;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_(1025, 10, WPP_098f04338e83369a94575ae92ed301d7_Traceguids);
    return 0;
  }
  NtClose(KeyHandle);
  KeyHandle = 0;
  if ( SockSanCleanUpCompleteEvent )
  {
    v2 = 0;
    while ( 1 )
    {
      TickCount = GetTickCount();
      v4 = WaitForSingleObjectEx(SockSanCleanUpCompleteEvent, 0x2BF20u, 1);
      v2 += GetTickCount() - TickCount;
      if ( v4 != 192 )
        break;
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_(1025, 12, WPP_098f04338e83369a94575ae92ed301d7_Traceguids);
      if ( v2 > 0x2BF20 )
      {
        v4 = 258;
        break;
      }
    }
    if ( v4 == 258 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_(1025, 13, WPP_098f04338e83369a94575ae92ed301d7_Traceguids);
      return 3221225473LL;
    }
    if ( v4 == -1 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
      {
        LastError = GetLastError();
        v1 = 14;
        goto LABEL_20;
      }
      return 3221225473LL;
    }
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_(1025, 15, WPP_098f04338e83369a94575ae92ed301d7_Traceguids);
  }
  else
  {
    SockSanCleanUpCompleteEvent = CreateEventA(0, 0, 0, 0);
    if ( !SockSanCleanUpCompleteEvent )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
      {
        LastError = GetLastError();
        v1 = 11;
LABEL_20:
        WPP_SF_d(1025, v1, WPP_098f04338e83369a94575ae92ed301d7_Traceguids, LastError);
        return 3221225473LL;
      }
      return 3221225473LL;
    }
  }
  SockSanCleanUpCompleteCount = 0;
  TcpBypassFlag = GetEnvVariableULONG(L"SanTcpBypass");
  ResizeEnabled = GetEnvVariableULONG(L"SanResizeDisable");
  SanRecvPollCount = GetEnvVariableULONG(L"SanRecvPollCount");
  SockSanAddressNotifyStatusBlock = 0;
  qword_180064748 = -1;
  SockSanAddressNotifyStatusBlockV6 = 0;
  qword_180064758 = 0;
  SockSanAddressNotifyContext = 0;
  SockUpcallTable2 = *(_OWORD *)SockUpcallTable;
  xmmword_1800647F0 = *(_OWORD *)(SockUpcallTable + 16);
  xmmword_180064800 = *(_OWORD *)(SockUpcallTable + 32);
  xmmword_180064810 = *(_OWORD *)(SockUpcallTable + 48);
  xmmword_180064820 = *(_OWORD *)(SockUpcallTable + 64);
  xmmword_180064830 = *(_OWORD *)(SockUpcallTable + 80);
  xmmword_180064840 = *(_OWORD *)(SockUpcallTable + 96);
  qword_180064850 = *(_QWORD *)(SockUpcallTable + 112);
  *((_QWORD *)&xmmword_1800647F0 + 1) = SockSanCreateSocketHandle;
  *((_QWORD *)&SockUpcallTable2 + 1) = SockSanCloseSocketHandle;
  *((_QWORD *)&xmmword_180064820 + 1) = SockSanQuerySocketHandleContext;
  qword_180064858 = (__int64)SockSanCompleteOverlappedRequest;
  SockSanStartup = 1;
  SockSanHelperHandle = 0;
  SockSanEvent = 0;
  SockSanSubnetMap = 0;
  SockSanSubnetCount = 0;
  SockSanV6AddressMap = 0;
  SockSanV6AddressCount = 0;
  qword_180064738 = (__int64)&SockSanProviderList;
  SockSanProviderList = &SockSanProviderList;
  SockSanSCAutostartEvent = 0;
  NumOpenSanSocks = 0;
  SockSanDeleteListCritSec = 0;
  v6 = RtlInitializeCriticalSectionAndSpinCount(&SockSanListCritSec, 0xFA0u);
  if ( v6 < 0 )
  {
    SetEvent(SockSanCleanUpCompleteEvent);
    return (unsigned int)v6;
  }
  if ( !SockSanCacheCallbackRegistered )
    InitializeCriticalSection(&SockSanProvListCritSec);
  if ( !DontReinitClosingSockList )
  {
    qword_1800646D8 = (__int64)&SockSanClosingList;
    SockSanClosingList = (__int64)&SockSanClosingList;
  }
  qword_1800646E8 = (__int64)&SockSanOpenList;
  SockSanOpenList = (__int64)&SockSanOpenList;
  qword_1800646F8 = (__int64)&SockSanListenList;
  SockSanListenList = &SockSanListenList;
  qword_180064708 = (__int64)&SockSanTrackerList;
  SockSanTrackerList = &SockSanTrackerList;
  qword_180064718 = (__int64)&SockSanRedirectorList;
  SockSanRedirectorList = (__int64)&SockSanRedirectorList;
  RdmaThreshold = 2048;
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_(1025, 16, WPP_098f04338e83369a94575ae92ed301d7_Traceguids);
  SockSanEnabled = 1;
  return 0;
}

```

## disassembly

```asm
0x18001e5a4  mov     r11, rsp
0x18001e5a7  push    rbx
0x18001e5a8  push    rsi
0x18001e5a9  push    r14
0x18001e5ab  push    r15
0x18001e5ad  sub     rsp, 68h
0x18001e5b1  xorps   xmm0, xmm0
0x18001e5b4  movups  [rsp+88h+var_68], xmm0
0x18001e5b9  xor     eax, eax
0x18001e5bb  movups  xmmword ptr [rsp+88h+ObjectAttributes.Length], xmm0
0x18001e5c0  movups  xmmword ptr [rsp+88h+ObjectAttributes.ObjectName], xmm0
0x18001e5c5  movups  xmmword ptr [rsp+88h+ObjectAttributes+1Ch], xmm0
0x18001e5ca  xor     r15d, r15d
0x18001e5cd  mov     [r11+8], r15
0x18001e5d1  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x18001e5d8  lea     rcx, [r11-68h]; DestinationString
0x18001e5dc  call    cs:__imp_RtlInitUnicodeString
0x18001e5e3  nop     dword ptr [rax+rax+00h]
0x18001e5e8  mov     [rsp+88h+ObjectAttributes.Length], 30h ; '0'
0x18001e5f0  mov     [rsp+88h+ObjectAttributes.RootDirectory], r15
0x18001e5f5  mov     [rsp+88h+ObjectAttributes.Attributes], 40h ; '@'
0x18001e5fd  lea     rax, [rsp+88h+var_68]
0x18001e602  mov     [rsp+88h+ObjectAttributes.ObjectName], rax
0x18001e607  xorps   xmm0, xmm0
0x18001e60a  movdqu  xmmword ptr [rsp+88h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001e610  lea     r8, [rsp+88h+ObjectAttributes]; ObjectAttributes
0x18001e615  mov     edx, 20019h; DesiredAccess
0x18001e61a  lea     rcx, [rsp+88h+KeyHandle]; KeyHandle
0x18001e622  call    cs:__imp_NtOpenKey
0x18001e629  nop     dword ptr [rax+rax+00h]
0x18001e62e  test    eax, eax
0x18001e630  jns     short loc_18001E659
0x18001e632  test    byte ptr cs:xmmword_180063D60, 2
0x18001e639  jz      loc_18001EA4E
0x18001e63f  lea     edx, [r15+0Ah]
0x18001e643  mov     ecx, 401h
0x18001e648  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x18001e64f  call    WPP_SF_
0x18001e654  jmp     loc_18001EA4E
0x18001e659  mov     rcx, [rsp+88h+KeyHandle]; Handle
0x18001e661  call    cs:__imp_NtClose
0x18001e668  nop     dword ptr [rax+rax+00h]
0x18001e66d  mov     [rsp+88h+KeyHandle], r15
0x18001e675  cmp     cs:SockSanCleanUpCompleteEvent, r15
0x18001e67c  jnz     short loc_18001E6C7
0x18001e67e  xor     r9d, r9d; lpName
0x18001e681  xor     r8d, r8d; bInitialState
0x18001e684  xor     edx, edx; bManualReset
0x18001e686  xor     ecx, ecx; lpEventAttributes
0x18001e688  call    cs:__imp_CreateEventA
0x18001e68f  nop     dword ptr [rax+rax+00h]
0x18001e694  mov     cs:SockSanCleanUpCompleteEvent, rax
0x18001e69b  test    rax, rax
0x18001e69e  jnz     loc_18001E7CD
0x18001e6a4  test    byte ptr cs:xmmword_180063D60, 2
0x18001e6ab  jz      loc_18001E7A4
0x18001e6b1  call    cs:__imp_GetLastError
0x18001e6b8  nop     dword ptr [rax+rax+00h]
0x18001e6bd  mov     edx, 0Bh
0x18001e6c2  jmp     loc_18001E790
0x18001e6c7  mov     r14d, r15d
0x18001e6ca  call    cs:__imp_GetTickCount
0x18001e6d1  nop     dword ptr [rax+rax+00h]
0x18001e6d6  mov     ebx, eax
0x18001e6d8  mov     edx, 2BF20h; dwMilliseconds
0x18001e6dd  mov     r8d, 1; bAlertable
0x18001e6e3  mov     rcx, cs:SockSanCleanUpCompleteEvent; hHandle
0x18001e6ea  call    cs:__imp_WaitForSingleObjectEx
0x18001e6f1  nop     dword ptr [rax+rax+00h]
0x18001e6f6  mov     esi, eax
0x18001e6f8  call    cs:__imp_GetTickCount
0x18001e6ff  nop     dword ptr [rax+rax+00h]
0x18001e704  sub     eax, ebx
0x18001e706  add     r14d, eax
0x18001e709  cmp     esi, 0C0h
0x18001e70f  jnz     short loc_18001E748
0x18001e711  test    byte ptr cs:xmmword_180063D60, 2
0x18001e718  jz      short loc_18001E730
0x18001e71a  mov     edx, 0Ch
0x18001e71f  mov     ecx, 401h
0x18001e724  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x18001e72b  call    WPP_SF_
0x18001e730  cmp     r14d, 2BF20h
0x18001e737  ja      short loc_18001E743
0x18001e739  cmp     esi, 0C0h
0x18001e73f  jz      short loc_18001E6CA
0x18001e741  jmp     short loc_18001E748
0x18001e743  mov     esi, 102h
0x18001e748  cmp     esi, 102h
0x18001e74e  jnz     short loc_18001E771
0x18001e750  test    byte ptr cs:xmmword_180063D60, 2
0x18001e757  jz      short loc_18001E7A4
0x18001e759  mov     edx, 0Dh
0x18001e75e  mov     ecx, 401h
0x18001e763  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x18001e76a  call    WPP_SF_
0x18001e76f  jmp     short loc_18001E7A4
0x18001e771  cmp     esi, 0FFFFFFFFh
0x18001e774  jnz     short loc_18001E7AE
0x18001e776  test    byte ptr cs:xmmword_180063D60, 2
0x18001e77d  jz      short loc_18001E7A4
0x18001e77f  call    cs:__imp_GetLastError
0x18001e786  nop     dword ptr [rax+rax+00h]
0x18001e78b  mov     edx, 0Eh
0x18001e790  mov     r9d, eax
0x18001e793  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x18001e79a  mov     ecx, 401h
0x18001e79f  call    WPP_SF_d
0x18001e7a4  mov     eax, 0C0000001h
0x18001e7a9  jmp     loc_18001EA50
0x18001e7ae  test    byte ptr cs:xmmword_180063D60, 2
0x18001e7b5  jz      short loc_18001E7CD
0x18001e7b7  mov     edx, 0Fh
0x18001e7bc  mov     ecx, 401h
0x18001e7c1  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x18001e7c8  call    WPP_SF_
0x18001e7cd  mov     cs:SockSanCleanUpCompleteCount, r15d
0x18001e7d4  lea     rcx, aSantcpbypass; "SanTcpBypass"
0x18001e7db  call    GetEnvVariableULONG
0x18001e7e0  mov     cs:TcpBypassFlag, eax
0x18001e7e6  lea     rcx, aSanresizedisab; "SanResizeDisable"
0x18001e7ed  call    GetEnvVariableULONG
0x18001e7f2  mov     cs:ResizeEnabled, eax
0x18001e7f8  lea     rcx, aSanrecvpollcou; "SanRecvPollCount"
0x18001e7ff  call    GetEnvVariableULONG
0x18001e804  mov     cs:SanRecvPollCount, eax
0x18001e80a  mov     cs:SockSanAddressNotifyStatusBlock, r15d
0x18001e811  mov     cs:qword_180064748, 0FFFFFFFFFFFFFFFFh
0x18001e81c  mov     cs:SockSanAddressNotifyStatusBlockV6, r15d
0x18001e823  mov     cs:qword_180064758, r15
0x18001e82a  mov     cs:SockSanAddressNotifyContext, r15
0x18001e831  mov     rax, cs:SockUpcallTable
0x18001e838  movups  xmm0, xmmword ptr [rax]
0x18001e83b  movups  cs:SockUpcallTable2, xmm0
0x18001e842  movups  xmm1, xmmword ptr [rax+10h]
0x18001e846  movups  cs:xmmword_1800647F0, xmm1
0x18001e84d  movups  xmm0, xmmword ptr [rax+20h]
0x18001e851  movups  cs:xmmword_180064800, xmm0
0x18001e858  movups  xmm1, xmmword ptr [rax+30h]
0x18001e85c  movups  cs:xmmword_180064810, xmm1
0x18001e863  movups  xmm0, xmmword ptr [rax+40h]
0x18001e867  movups  cs:xmmword_180064820, xmm0
0x18001e86e  movups  xmm1, xmmword ptr [rax+50h]
0x18001e872  movups  cs:xmmword_180064830, xmm1
0x18001e879  movups  xmm0, xmmword ptr [rax+60h]
0x18001e87d  movups  cs:xmmword_180064840, xmm0
0x18001e884  movsd   xmm1, qword ptr [rax+70h]
0x18001e889  movsd   cs:qword_180064850, xmm1
0x18001e891  lea     rax, SockSanCreateSocketHandle
0x18001e898  mov     qword ptr cs:xmmword_1800647F0+8, rax
0x18001e89f  lea     rax, SockSanCloseSocketHandle
0x18001e8a6  mov     qword ptr cs:SockUpcallTable2+8, rax
0x18001e8ad  lea     rax, SockSanQuerySocketHandleContext
0x18001e8b4  mov     qword ptr cs:xmmword_180064820+8, rax
0x18001e8bb  lea     rax, SockSanCompleteOverlappedRequest
0x18001e8c2  mov     cs:qword_180064858, rax
0x18001e8c9  mov     cs:SockSanStartup, 1
0x18001e8d0  mov     cs:SockSanHelperHandle, r15
0x18001e8d7  mov     cs:SockSanEvent, r15
0x18001e8de  mov     cs:SockSanSubnetMap, r15
0x18001e8e5  mov     cs:SockSanSubnetCount, r15d
0x18001e8ec  mov     cs:SockSanV6AddressMap, r15
0x18001e8f3  mov     cs:SockSanV6AddressCount, r15d
0x18001e8fa  lea     rax, SockSanProviderList
0x18001e901  mov     cs:qword_180064738, rax
0x18001e908  mov     cs:SockSanProviderList, rax
0x18001e90f  mov     cs:SockSanSCAutostartEvent, r15
0x18001e916  mov     cs:NumOpenSanSocks, r15d
0x18001e91d  mov     cs:SockSanDeleteListCritSec, r15b
0x18001e924  mov     edx, 0FA0h; SpinCount
0x18001e929  lea     rcx, SockSanListCritSec; CriticalSection
0x18001e930  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x18001e937  nop     dword ptr [rax+rax+00h]
0x18001e93c  mov     ebx, eax
0x18001e93e  test    eax, eax
0x18001e940  jns     short loc_18001E95C
0x18001e942  mov     rcx, cs:SockSanCleanUpCompleteEvent; hEvent
0x18001e949  call    cs:__imp_SetEvent
0x18001e950  nop     dword ptr [rax+rax+00h]
0x18001e955  mov     eax, ebx
0x18001e957  jmp     loc_18001EA50
0x18001e95c  cmp     cs:SockSanCacheCallbackRegistered, r15b
0x18001e963  jnz     short loc_18001E9A9
0x18001e965  lea     rcx, SockSanProvListCritSec; lpCriticalSection
0x18001e96c  call    cs:__imp_InitializeCriticalSection
0x18001e973  nop     dword ptr [rax+rax+00h]
0x18001e978  jmp     short loc_18001E9A9
0x18001e97a  mov     ebx, eax
0x18001e97c  lea     rcx, SockSanListCritSec; lpCriticalSection
0x18001e983  call    cs:__imp_DeleteCriticalSection
0x18001e98a  nop     dword ptr [rax+rax+00h]
0x18001e98f  mov     rcx, cs:SockSanCleanUpCompleteEvent; hEvent
0x18001e996  call    cs:__imp_SetEvent
0x18001e99d  nop     dword ptr [rax+rax+00h]
0x18001e9a2  mov     eax, ebx
0x18001e9a4  jmp     loc_18001EA50
0x18001e9a9  cmp     cs:DontReinitClosingSockList, r15b
0x18001e9b0  jnz     short loc_18001E9C7
0x18001e9b2  lea     rax, SockSanClosingList
0x18001e9b9  mov     cs:qword_1800646D8, rax
0x18001e9c0  mov     cs:SockSanClosingList, rax
0x18001e9c7  lea     rax, SockSanOpenList
0x18001e9ce  mov     cs:qword_1800646E8, rax
0x18001e9d5  mov     cs:SockSanOpenList, rax
0x18001e9dc  lea     rax, SockSanListenList
0x18001e9e3  mov     cs:qword_1800646F8, rax
0x18001e9ea  mov     cs:SockSanListenList, rax
0x18001e9f1  lea     rax, SockSanTrackerList
0x18001e9f8  mov     cs:qword_180064708, rax
0x18001e9ff  mov     cs:SockSanTrackerList, rax
0x18001ea06  lea     rax, SockSanRedirectorList
0x18001ea0d  mov     cs:qword_180064718, rax
0x18001ea14  mov     cs:SockSanRedirectorList, rax
0x18001ea1b  mov     cs:RdmaThreshold, 800h
0x18001ea25  test    byte ptr cs:xmmword_180063D60, 2
0x18001ea2c  jz      short loc_18001EA44
0x18001ea2e  mov     edx, 10h
0x18001ea33  mov     ecx, 401h
0x18001ea38  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x18001ea3f  call    WPP_SF_
0x18001ea44  mov     cs:SockSanEnabled, 1
0x18001ea4e  xor     eax, eax
0x18001ea50  add     rsp, 68h
0x18001ea54  pop     r15
0x18001ea56  pop     r14
0x18001ea58  pop     rsi
0x18001ea59  pop     rbx
0x18001ea5a  retn
```
