# DnsQueryServerList(void)

- ea: `0x180011db0`
- end: `0x180012574`
- name: `?DnsQueryServerList@@YAKXZ`
- size: `1988`
- prototype: `unsigned int(void)`
- caller_count: `3`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011860`
- `0x180011b20`
- `0x1800271d0`

## callees

- `0x18000c1e0`
- `0x18000c3c0`
- `0x18000ca20`
- `0x18000d090`
- `0x180011db0`
- `0x1800128f0`
- `0x1800202e0`

## import_xrefs

- `IPHLPAPI!NotifyAddrChange` at `0x18001240d`
- `IPHLPAPI!NotifyAddrChange` at `0x18001240d`
- `NSI!NsiRequestChangeNotification` at `0x180011f52`
- `NSI!NsiRequestChangeNotification` at `0x180011f52`
- `ntdll!RtlInitUnicodeString` at `0x180011ff8`
- `ntdll!RtlInitUnicodeString` at `0x180011ff8`
- `ntdll!RtlRegisterWait` at `0x180011ef9`
- `ntdll!RtlRegisterWait` at `0x180012171`
- `ntdll!RtlRegisterWait` at `0x18001235b`
- `ntdll!RtlRegisterWait` at `0x180011ef9`
- `ntdll!RtlRegisterWait` at `0x180012171`
- `ntdll!RtlRegisterWait` at `0x18001235b`
- `ntdll!NtCreateEvent` at `0x180011ebf`
- `ntdll!NtCreateEvent` at `0x180012101`
- `ntdll!NtCreateEvent` at `0x1800122ee`
- `ntdll!NtCreateEvent` at `0x180011ebf`
- `ntdll!NtCreateEvent` at `0x180012101`
- `ntdll!NtCreateEvent` at `0x1800122ee`
- `ntdll!NtNotifyChangeKey` at `0x180012227`
- `ntdll!NtNotifyChangeKey` at `0x180012227`
- `ntdll!RtlDeregisterWait` at `0x180011f72`
- `ntdll!RtlDeregisterWait` at `0x180012244`
- `ntdll!RtlDeregisterWait` at `0x18001242b`
- `ntdll!RtlDeregisterWait` at `0x180011f72`
- `ntdll!RtlDeregisterWait` at `0x180012244`
- `ntdll!RtlDeregisterWait` at `0x18001242b`
- `ntdll!NtOpenKey` at `0x180012040`
- `ntdll!NtOpenKey` at `0x180012040`
- `ntdll!RtlNtStatusToDosError` at `0x180012058`
- `ntdll!RtlNtStatusToDosError` at `0x1800121b5`
- `ntdll!RtlNtStatusToDosError` at `0x1800122af`
- `ntdll!RtlNtStatusToDosError` at `0x1800123c5`
- `ntdll!RtlNtStatusToDosError` at `0x180012058`
- `ntdll!RtlNtStatusToDosError` at `0x1800121b5`
- `ntdll!RtlNtStatusToDosError` at `0x1800122af`
- `ntdll!RtlNtStatusToDosError` at `0x1800123c5`
- `ntdll!NtClose` at `0x180011f8c`
- `ntdll!NtClose` at `0x1800121c8`
- `ntdll!NtClose` at `0x18001225e`
- `ntdll!NtClose` at `0x180012374`
- `ntdll!NtClose` at `0x180012445`
- `ntdll!NtClose` at `0x1800124e3`
- `ntdll!NtClose` at `0x180011f8c`
- `ntdll!NtClose` at `0x1800121c8`
- `ntdll!NtClose` at `0x18001225e`
- `ntdll!NtClose` at `0x180012374`
- `ntdll!NtClose` at `0x180012445`
- `ntdll!NtClose` at `0x1800124e3`

## string_xrefs

- `0x180011fec`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`

## pseudocode

```c
__int64 DnsQueryServerList(void)
{
  NTSTATUS v1; // ebx
  unsigned int v2; // ebx
  int v3; // eax
  unsigned int v4; // edi
  ULONG v5; // eax
  ULONG v6; // ebx
  PVOID *v7; // rcx
  int Event; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  NTSTATUS v11; // eax
  NTSTATUS v12; // ebx
  int v13; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-48h] BYREF
  void *Handle; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v21; // [rsp+B8h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_1162121ddabf3385a9c607de51c938f1_Traceguids);
  }
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v21 = 0;
  DestinationString = 0;
  if ( !DnsTcpipInterfacesKey )
  {
    RtlInitUnicodeString(
      &DestinationString,
      L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v3 = NtOpenKey(&DnsTcpipInterfacesKey, 0x20019u, &ObjectAttributes);
    v4 = v3;
    if ( v3 < 0 )
    {
      v5 = RtlNtStatusToDosError(v3);
      v6 = v5;
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_1162121ddabf3385a9c607de51c938f1_Traceguids, v4, v5);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 && *((_BYTE *)v7 + 25) >= 6u )
          WPP_SF_d(v7[2], 88, &WPP_1162121ddabf3385a9c607de51c938f1_Traceguids, v6);
      }
      return v6;
    }
  }
  if ( !DnsNotifyChangeKeyEvent && AcquireComponentReference(&DnsComponentReference) )
  {
    Event = NtCreateEvent(&DnsNotifyChangeKeyEvent, 0x1F0003u, 0, SynchronizationEvent, 0);
    if ( Event < 0 )
    {
      ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&DnsComponentReference);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        goto LABEL_48;
      }
      v10 = 89;
LABEL_47:
      WPP_SF_d(v9[2], v10, &WPP_1162121ddabf3385a9c607de51c938f1_Traceguids, (unsigned int)Event);
LABEL_48:
      RtlNtStatusToDosError(Event);
      goto LABEL_4;
    }
    v11 = RtlRegisterWait(
            &DnsNotifyChangeKeyWaitHandle,
            DnsNotifyChangeKeyEvent,
            DnsNotifyChangeKeyCallbackRoutine,
            0,
            0xFFFFFFFF,
            0);
    v12 = v11;
    if ( v11 >= 0 )
    {
      Event = NtNotifyChangeKey(
                DnsTcpipInterfacesKey,
                DnsNotifyChangeKeyEvent,
                0,
                0,
                &DnsNotifyChangeKeyIoStatus,
                4u,
                1u,
                0,
                0,
                1u);
      if ( Event < 0 )
      {
        RtlDeregisterWait(DnsNotifyChangeKeyWaitHandle);
        DnsNotifyChangeKeyWaitHandle = 0;
        NtClose(DnsNotifyChangeKeyEvent);
        DnsNotifyChangeKeyEvent = 0;
        ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&DnsComponentReference);
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        {
          goto LABEL_48;
        }
        v10 = 91;
        goto LABEL_47;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          90,
          &WPP_1162121ddabf3385a9c607de51c938f1_Traceguids,
          (unsigned int)v11);
      }
      RtlNtStatusToDosError(v12);
      NtClose(DnsNotifyChangeKeyEvent);
      DnsNotifyChangeKeyEvent = 0;
      ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&DnsComponentReference);
    }
  }
LABEL_4:
  if ( !DnsNotifyChangeAddressEvent && AcquireComponentReference(&DnsComponentReference) )
  {
    v13 = NtCreateEvent(&DnsNotifyChangeAddressEvent, 0x1F0003u, 0, SynchronizationEvent, 0);
    if ( v13 < 0 )
    {
      ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&DnsComponentReference);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        goto LABEL_61;
      }
      v15 = 92;
LABEL_60:
      WPP_SF_d(v14[2], v15, &WPP_1162121ddabf3385a9c607de51c938f1_Traceguids, (unsigned int)v13);
LABEL_61:
      RtlNtStatusToDosError(v13);
      goto LABEL_5;
    }
    v13 = RtlRegisterWait(
            &DnsNotifyChangeAddressWaitHandle,
            DnsNotifyChangeAddressEvent,
            DnsNotifyChangeAddressCallbackRoutine,
            0,
            0xFFFFFFFF,
            0);
    if ( v13 < 0 )
    {
      NtClose(DnsNotifyChangeAddressEvent);
      DnsNotifyChangeAddressEvent = 0;
      ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&DnsComponentReference);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        goto LABEL_61;
      }
      v15 = 93;
      goto LABEL_60;
    }
    DnsNotifyChangeAddressOverlapped.hEvent = DnsNotifyChangeAddressEvent;
    Handle = 0;
    *(_OWORD *)&DnsNotifyChangeAddressOverlapped.InternalHigh = 0;
    DnsNotifyChangeAddressOverlapped.Internal = 0;
    if ( NotifyAddrChange(&Handle, &DnsNotifyChangeAddressOverlapped) != 997 )
    {
      RtlDeregisterWait(DnsNotifyChangeAddressWaitHandle);
      DnsNotifyChangeAddressWaitHandle = 0;
      NtClose(DnsNotifyChangeAddressEvent);
      DnsNotifyChangeAddressEvent = 0;
      ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&DnsComponentReference);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          94,
          &WPP_1162121ddabf3385a9c607de51c938f1_Traceguids,
          (unsigned int)v13);
      }
    }
  }
LABEL_5:
  if ( v6DnsNotifyChangeAddressEvent || !AcquireComponentReference(&DnsComponentReference) )
    goto LABEL_6;
  v1 = NtCreateEvent(&v6DnsNotifyChangeAddressEvent, 0x1F0003u, 0, SynchronizationEvent, 0);
  if ( v1 < 0 )
  {
    ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&DnsComponentReference);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_6;
    }
    v17 = 95;
    goto LABEL_75;
  }
  v1 = RtlRegisterWait(
         &v6DnsNotifyChangeAddressWaitHandle,
         v6DnsNotifyChangeAddressEvent,
         Dnsv6NotifyChangeAddressCallbackRoutine,
         0,
         0xFFFFFFFF,
         0);
  if ( v1 >= 0 )
  {
    qword_1800AEBA0 = (__int64)v6DnsNotifyChangeAddressEvent;
    Dnsv6NotifyChangeAddressOverlapped.Internal = 0;
    xmmword_1800AEB90 = 0;
    v2 = NsiRequestChangeNotification(0, &NPI_MS_IPV6_MODULEID, 10, &Dnsv6NotifyChangeAddressOverlapped, &v21);
    if ( v2 != 997 )
    {
      RtlDeregisterWait(v6DnsNotifyChangeAddressWaitHandle);
      v6DnsNotifyChangeAddressWaitHandle = 0;
      NtClose(v6DnsNotifyChangeAddressEvent);
      v6DnsNotifyChangeAddressEvent = 0;
      ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&DnsComponentReference);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_1162121ddabf3385a9c607de51c938f1_Traceguids, v2);
      }
    }
    goto LABEL_6;
  }
  NtClose(v6DnsNotifyChangeAddressEvent);
  v6DnsNotifyChangeAddressEvent = 0;
  ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&DnsComponentReference);
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v17 = 96;
LABEL_75:
    WPP_SF_d(v16[2], v17, &WPP_1162121ddabf3385a9c607de51c938f1_Traceguids, (unsigned int)v1);
  }
LABEL_6:
  FillInDnsServerList();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_1162121ddabf3385a9c607de51c938f1_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180011db0  push    rbp
0x180011db2  push    rsi
0x180011db3  sub     rsp, 98h
0x180011dba  mov     rcx, cs:WPP_GLOBAL_Control
0x180011dc1  lea     rsi, WPP_GLOBAL_Control
0x180011dc8  cmp     rcx, rsi
0x180011dcb  jnz     loc_180011E67
0x180011dd1  xorps   xmm0, xmm0
0x180011dd4  mov     [rsp+0A8h+arg_10], rbx
0x180011ddc  xor     ebp, ebp
0x180011dde  mov     [rsp+0A8h+var_18], rdi
0x180011de6  cmp     cs:?DnsTcpipInterfacesKey@@3PEAXEA, rbp; void * DnsTcpipInterfacesKey
0x180011ded  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x180011df2  mov     [rsp+0A8h+arg_8], rbp
0x180011dfa  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x180011dff  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180011e07  movups  xmmword ptr [rsp+0A8h+DestinationString.Length], xmm0
0x180011e0c  jz      loc_180011FEC
0x180011e12  cmp     cs:?DnsNotifyChangeKeyEvent@@3PEAXEA, rbp; void * DnsNotifyChangeKeyEvent
0x180011e19  jz      loc_1800120D3
0x180011e1f  cmp     cs:?DnsNotifyChangeAddressEvent@@3PEAXEA, rbp; void * DnsNotifyChangeAddressEvent
0x180011e26  jz      loc_1800122C0
0x180011e2c  cmp     cs:?v6DnsNotifyChangeAddressEvent@@3PEAXEA, rbp; void * v6DnsNotifyChangeAddressEvent
0x180011e33  jz      short loc_180011E95
0x180011e35  call    ?FillInDnsServerList@@YAXXZ; FillInDnsServerList(void)
0x180011e3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e41  cmp     rcx, rsi
0x180011e44  jnz     loc_180012543
0x180011e4a  xor     eax, eax
0x180011e4c  mov     rdi, [rsp+0A8h+var_18]
0x180011e54  mov     rbx, [rsp+0A8h+arg_10]
0x180011e5c  add     rsp, 98h
0x180011e63  pop     rsi
0x180011e64  pop     rbp
0x180011e65  retn
0x180011e67  test    byte ptr [rcx+1Ch], 10h
0x180011e6b  jz      loc_180011DD1
0x180011e71  cmp     byte ptr [rcx+19h], 6
0x180011e75  jb      loc_180011DD1
0x180011e7b  mov     rcx, [rcx+10h]
0x180011e7f  lea     r8, WPP_1162121ddabf3385a9c607de51c938f1_Traceguids
0x180011e86  mov     edx, 56h ; 'V'
0x180011e8b  call    WPP_SF_
0x180011e90  jmp     loc_180011DD1
0x180011e95  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x180011e9c  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x180011ea1  test    al, al
0x180011ea3  jz      short loc_180011E35
0x180011ea5  mov     r9d, 1; EventType
0x180011eab  mov     [rsp+0A8h+InitialState], bpl; InitialState
0x180011eb0  xor     r8d, r8d; ObjectAttributes
0x180011eb3  lea     rcx, ?v6DnsNotifyChangeAddressEvent@@3PEAXEA; EventHandle
0x180011eba  mov     edx, 1F0003h; DesiredAccess
0x180011ebf  call    cs:__imp_NtCreateEvent
0x180011ec6  nop     dword ptr [rax+rax+00h]
0x180011ecb  mov     ebx, eax
0x180011ecd  test    eax, eax
0x180011ecf  js      loc_1800124A5
0x180011ed5  mov     rdx, cs:?v6DnsNotifyChangeAddressEvent@@3PEAXEA; hObject
0x180011edc  lea     r8, ?Dnsv6NotifyChangeAddressCallbackRoutine@@YAXPEAXE@Z; Callback
0x180011ee3  mov     [rsp+0A8h+ulFlags], ebp; ulFlags
0x180011ee7  lea     rcx, ?v6DnsNotifyChangeAddressWaitHandle@@3PEAXEA; phNewWaitObject
0x180011eee  xor     r9d, r9d; pvContext
0x180011ef1  mov     dword ptr [rsp+0A8h+InitialState], 0FFFFFFFFh; ulMilliseconds
0x180011ef9  call    cs:__imp_RtlRegisterWait
0x180011f00  nop     dword ptr [rax+rax+00h]
0x180011f05  mov     ebx, eax
0x180011f07  test    eax, eax
0x180011f09  js      loc_1800124DC
0x180011f0f  mov     rax, cs:?v6DnsNotifyChangeAddressEvent@@3PEAXEA; void * v6DnsNotifyChangeAddressEvent
0x180011f16  lea     r9, ?Dnsv6NotifyChangeAddressOverlapped@@3U_OVERLAPPED@@A; _OVERLAPPED Dnsv6NotifyChangeAddressOverlapped
0x180011f1d  mov     cs:qword_1800AEBA0, rax
0x180011f24  lea     rdx, NPI_MS_IPV6_MODULEID
0x180011f2b  lea     rax, [rsp+0A8h+arg_8]
0x180011f33  mov     cs:?Dnsv6NotifyChangeAddressOverlapped@@3U_OVERLAPPED@@A, rbp; _OVERLAPPED Dnsv6NotifyChangeAddressOverlapped
0x180011f3a  xorps   xmm0, xmm0
0x180011f3d  mov     qword ptr [rsp+0A8h+InitialState], rax
0x180011f42  mov     r8d, 0Ah
0x180011f48  xor     ecx, ecx
0x180011f4a  movdqu  cs:xmmword_1800AEB90, xmm0
0x180011f52  call    cs:__imp_NsiRequestChangeNotification
0x180011f59  nop     dword ptr [rax+rax+00h]
0x180011f5e  mov     ebx, eax
0x180011f60  cmp     eax, 3E5h
0x180011f65  jz      loc_180011E35
0x180011f6b  mov     rcx, cs:?v6DnsNotifyChangeAddressWaitHandle@@3PEAXEA; hWaitHandle
0x180011f72  call    cs:__imp_RtlDeregisterWait
0x180011f79  nop     dword ptr [rax+rax+00h]
0x180011f7e  mov     rcx, cs:?v6DnsNotifyChangeAddressEvent@@3PEAXEA; Handle
0x180011f85  mov     cs:?v6DnsNotifyChangeAddressWaitHandle@@3PEAXEA, rbp; void * v6DnsNotifyChangeAddressWaitHandle
0x180011f8c  call    cs:__imp_NtClose
0x180011f93  nop     dword ptr [rax+rax+00h]
0x180011f98  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x180011f9f  mov     cs:?v6DnsNotifyChangeAddressEvent@@3PEAXEA, rbp; void * v6DnsNotifyChangeAddressEvent
0x180011fa6  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x180011fab  mov     rcx, cs:WPP_GLOBAL_Control
0x180011fb2  cmp     rcx, rsi
0x180011fb5  jz      loc_180011E35
0x180011fbb  test    byte ptr [rcx+1Ch], 10h
0x180011fbf  jz      loc_180011E35
0x180011fc5  cmp     byte ptr [rcx+19h], 3
0x180011fc9  jb      loc_180011E35
0x180011fcf  mov     rcx, [rcx+10h]
0x180011fd3  lea     r8, WPP_1162121ddabf3385a9c607de51c938f1_Traceguids
0x180011fda  mov     edx, 61h ; 'a'
0x180011fdf  mov     r9d, ebx
0x180011fe2  call    WPP_SF_d
0x180011fe7  jmp     loc_180011E35
0x180011fec  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x180011ff3  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x180011ff8  call    cs:__imp_RtlInitUnicodeString
0x180011fff  nop     dword ptr [rax+rax+00h]
0x180012004  lea     rax, [rsp+0A8h+DestinationString]
0x180012009  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x180012011  xorps   xmm0, xmm0
0x180012014  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x180012019  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x18001201e  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], rbp
0x180012023  mov     edx, 20019h; DesiredAccess
0x180012028  mov     [rsp+0A8h+ObjectAttributes.Attributes], 40h ; '@'
0x180012030  lea     rcx, ?DnsTcpipInterfacesKey@@3PEAXEA; KeyHandle
0x180012037  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180012040  call    cs:__imp_NtOpenKey
0x180012047  nop     dword ptr [rax+rax+00h]
0x18001204c  mov     edi, eax
0x18001204e  test    eax, eax
0x180012050  jns     loc_180011E12
0x180012056  mov     ecx, eax; Status
0x180012058  call    cs:__imp_RtlNtStatusToDosError
0x18001205f  nop     dword ptr [rax+rax+00h]
0x180012064  mov     ebx, eax
0x180012066  mov     rcx, cs:WPP_GLOBAL_Control
0x18001206d  cmp     rcx, rsi
0x180012070  jnz     short loc_180012079
0x180012072  mov     eax, ebx
0x180012074  jmp     loc_180011E4C
0x180012079  test    byte ptr [rcx+1Ch], 10h
0x18001207d  jz      short loc_1800120A8
0x18001207f  cmp     byte ptr [rcx+19h], 2
0x180012083  jb      short loc_1800120A8
0x180012085  mov     rcx, [rcx+10h]
0x180012089  lea     r8, WPP_1162121ddabf3385a9c607de51c938f1_Traceguids
0x180012090  mov     edx, 57h ; 'W'
0x180012095  mov     dword ptr [rsp+0A8h+InitialState], ebx
0x180012099  mov     r9d, edi
0x18001209c  call    WPP_SF_Dd
0x1800120a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800120a8  cmp     rcx, rsi
0x1800120ab  jz      short loc_180012072
0x1800120ad  test    byte ptr [rcx+1Ch], 10h
0x1800120b1  jz      short loc_180012072
0x1800120b3  cmp     byte ptr [rcx+19h], 6
0x1800120b7  jb      short loc_180012072
0x1800120b9  mov     rcx, [rcx+10h]
0x1800120bd  lea     r8, WPP_1162121ddabf3385a9c607de51c938f1_Traceguids
0x1800120c4  mov     edx, 58h ; 'X'
0x1800120c9  mov     r9d, ebx
0x1800120cc  call    WPP_SF_d
0x1800120d1  jmp     short loc_180012072
0x1800120d3  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x1800120da  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x1800120df  test    al, al
0x1800120e1  jz      loc_180011E1F
0x1800120e7  mov     r9d, 1; EventType
0x1800120ed  mov     [rsp+0A8h+InitialState], bpl; InitialState
0x1800120f2  xor     r8d, r8d; ObjectAttributes
0x1800120f5  lea     rcx, ?DnsNotifyChangeKeyEvent@@3PEAXEA; EventHandle
0x1800120fc  mov     edx, 1F0003h; DesiredAccess
0x180012101  call    cs:__imp_NtCreateEvent
0x180012108  nop     dword ptr [rax+rax+00h]
0x18001210d  mov     ebx, eax
0x18001210f  test    eax, eax
0x180012111  jns     short loc_18001214D
0x180012113  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x18001211a  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18001211f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012126  cmp     rcx, rsi
0x180012129  jz      loc_1800122AD
0x18001212f  test    byte ptr [rcx+1Ch], 10h
0x180012133  jz      loc_1800122AD
0x180012139  cmp     byte ptr [rcx+19h], 3
0x18001213d  jb      loc_1800122AD
0x180012143  mov     edx, 59h ; 'Y'
0x180012148  jmp     loc_18001229A
0x18001214d  mov     rdx, cs:?DnsNotifyChangeKeyEvent@@3PEAXEA; hObject
0x180012154  lea     r8, ?DnsNotifyChangeKeyCallbackRoutine@@YAXPEAXE@Z; Callback
0x18001215b  mov     [rsp+0A8h+ulFlags], ebp; ulFlags
0x18001215f  lea     rcx, ?DnsNotifyChangeKeyWaitHandle@@3PEAXEA; phNewWaitObject
0x180012166  xor     r9d, r9d; pvContext
0x180012169  mov     dword ptr [rsp+0A8h+InitialState], 0FFFFFFFFh; ulMilliseconds
0x180012171  call    cs:__imp_RtlRegisterWait
0x180012178  nop     dword ptr [rax+rax+00h]
0x18001217d  mov     ebx, eax
0x18001217f  test    eax, eax
0x180012181  jns     short loc_1800121EC
0x180012183  mov     rcx, cs:WPP_GLOBAL_Control
0x18001218a  cmp     rcx, rsi
0x18001218d  jz      short loc_1800121B3
0x18001218f  test    byte ptr [rcx+1Ch], 10h
0x180012193  jz      short loc_1800121B3
0x180012195  cmp     byte ptr [rcx+19h], 3
0x180012199  jb      short loc_1800121B3
0x18001219b  mov     rcx, [rcx+10h]
0x18001219f  lea     r8, WPP_1162121ddabf3385a9c607de51c938f1_Traceguids
0x1800121a6  mov     edx, 5Ah ; 'Z'
0x1800121ab  mov     r9d, eax
0x1800121ae  call    WPP_SF_d
0x1800121b3  mov     ecx, ebx; Status
0x1800121b5  call    cs:__imp_RtlNtStatusToDosError
0x1800121bc  nop     dword ptr [rax+rax+00h]
0x1800121c1  mov     rcx, cs:?DnsNotifyChangeKeyEvent@@3PEAXEA; Handle
0x1800121c8  call    cs:__imp_NtClose
0x1800121cf  nop     dword ptr [rax+rax+00h]
0x1800121d4  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x1800121db  mov     cs:?DnsNotifyChangeKeyEvent@@3PEAXEA, rbp; void * DnsNotifyChangeKeyEvent
0x1800121e2  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x1800121e7  jmp     loc_180011E1F
0x1800121ec  mov     rdx, cs:?DnsNotifyChangeKeyEvent@@3PEAXEA; Event
0x1800121f3  lea     rax, ?DnsNotifyChangeKeyIoStatus@@3U_IO_STATUS_BLOCK@@A; _IO_STATUS_BLOCK DnsNotifyChangeKeyIoStatus
0x1800121fa  mov     rcx, cs:?DnsTcpipInterfacesKey@@3PEAXEA; KeyHandle
0x180012201  xor     r9d, r9d; ApcContext
0x180012204  mov     [rsp+0A8h+WatchSubtree], 1; WatchSubtree
0x180012209  xor     r8d, r8d; ApcRoutine
0x18001220c  mov     [rsp+0A8h+Length], ebp; Length
0x180012210  mov     [rsp+0A8h+ChangeBuffer], rbp; ChangeBuffer
0x180012215  mov     [rsp+0A8h+Asynchroneous], 1; Asynchroneous
0x18001221a  mov     [rsp+0A8h+ulFlags], 4; CompletionFilter
0x180012222  mov     qword ptr [rsp+0A8h+InitialState], rax; IoStatusBlock
0x180012227  call    cs:__imp_NtNotifyChangeKey
0x18001222e  nop     dword ptr [rax+rax+00h]
0x180012233  mov     ebx, eax
0x180012235  test    eax, eax
0x180012237  jns     loc_180011E1F
0x18001223d  mov     rcx, cs:?DnsNotifyChangeKeyWaitHandle@@3PEAXEA; hWaitHandle
0x180012244  call    cs:__imp_RtlDeregisterWait
0x18001224b  nop     dword ptr [rax+rax+00h]
0x180012250  mov     rcx, cs:?DnsNotifyChangeKeyEvent@@3PEAXEA; Handle
0x180012257  mov     cs:?DnsNotifyChangeKeyWaitHandle@@3PEAXEA, rbp; void * DnsNotifyChangeKeyWaitHandle
0x18001225e  call    cs:__imp_NtClose
0x180012265  nop     dword ptr [rax+rax+00h]
0x18001226a  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x180012271  mov     cs:?DnsNotifyChangeKeyEvent@@3PEAXEA, rbp; void * DnsNotifyChangeKeyEvent
0x180012278  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18001227d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012284  cmp     rcx, rsi
0x180012287  jz      short loc_1800122AD
0x180012289  test    byte ptr [rcx+1Ch], 10h
0x18001228d  jz      short loc_1800122AD
0x18001228f  cmp     byte ptr [rcx+19h], 3
0x180012293  jb      short loc_1800122AD
0x180012295  mov     edx, 5Bh ; '['
0x18001229a  mov     rcx, [rcx+10h]
0x18001229e  lea     r8, WPP_1162121ddabf3385a9c607de51c938f1_Traceguids
0x1800122a5  mov     r9d, ebx
0x1800122a8  call    WPP_SF_d
0x1800122ad  mov     ecx, ebx; Status
0x1800122af  call    cs:__imp_RtlNtStatusToDosError
0x1800122b6  nop     dword ptr [rax+rax+00h]
0x1800122bb  jmp     loc_180011E1F
0x1800122c0  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x1800122c7  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x1800122cc  test    al, al
0x1800122ce  jz      loc_180011E2C
0x1800122d4  mov     r9d, 1; EventType
0x1800122da  mov     [rsp+0A8h+InitialState], bpl; InitialState
0x1800122df  xor     r8d, r8d; ObjectAttributes
0x1800122e2  lea     rcx, ?DnsNotifyChangeAddressEvent@@3PEAXEA; EventHandle
0x1800122e9  mov     edx, 1F0003h; DesiredAccess
0x1800122ee  call    cs:__imp_NtCreateEvent
0x1800122f5  nop     dword ptr [rax+rax+00h]
0x1800122fa  mov     ebx, eax
0x1800122fc  test    eax, eax
0x1800122fe  jns     short loc_180012337
0x180012300  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x180012307  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18001230c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012313  cmp     rcx, rsi
0x180012316  jz      loc_1800123C3
0x18001231c  test    byte ptr [rcx+1Ch], 10h
0x180012320  jz      loc_1800123C3
0x180012326  cmp     byte ptr [rcx+19h], 3
0x18001232a  jb      loc_1800123C3
0x180012330  mov     edx, 5Ch ; '\'
0x180012335  jmp     short loc_1800123B0
0x180012337  mov     rdx, cs:?DnsNotifyChangeAddressEvent@@3PEAXEA; hObject
0x18001233e  lea     r8, ?DnsNotifyChangeAddressCallbackRoutine@@YAXPEAXE@Z; Callback
0x180012345  mov     [rsp+0A8h+ulFlags], ebp; ulFlags
0x180012349  lea     rcx, ?DnsNotifyChangeAddressWaitHandle@@3PEAXEA; phNewWaitObject
0x180012350  xor     r9d, r9d; pvContext
0x180012353  mov     dword ptr [rsp+0A8h+InitialState], 0FFFFFFFFh; ulMilliseconds
0x18001235b  call    cs:__imp_RtlRegisterWait
0x180012362  nop     dword ptr [rax+rax+00h]
0x180012367  mov     ebx, eax
0x180012369  test    eax, eax
0x18001236b  jns     short loc_1800123D6
0x18001236d  mov     rcx, cs:?DnsNotifyChangeAddressEvent@@3PEAXEA; Handle
0x180012374  call    cs:__imp_NtClose
0x18001237b  nop     dword ptr [rax+rax+00h]
0x180012380  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x180012387  mov     cs:?DnsNotifyChangeAddressEvent@@3PEAXEA, rbp; void * DnsNotifyChangeAddressEvent
  ... truncated ...
```
