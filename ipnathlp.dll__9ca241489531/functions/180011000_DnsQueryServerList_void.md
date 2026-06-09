# DnsQueryServerList(void)

- ea: `0x180011000`
- end: `0x180011733`
- name: `?DnsQueryServerList@@YAKXZ`
- size: `1843`
- prototype: `unsigned int(void)`
- caller_count: `3`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010b00`
- `0x180010d90`
- `0x180024c90`

## callees

- `0x18000b900`
- `0x18000bad0`
- `0x18000c110`
- `0x18000c750`
- `0x180011000`
- `0x180011a70`
- `0x18001ec08`

## import_xrefs

- `IPHLPAPI!NotifyAddrChange` at `0x1800115e4`
- `IPHLPAPI!NotifyAddrChange` at `0x1800115e4`
- `NSI!NsiRequestChangeNotification` at `0x180011195`
- `NSI!NsiRequestChangeNotification` at `0x180011195`
- `ntdll!RtlInitUnicodeString` at `0x180011229`
- `ntdll!RtlInitUnicodeString` at `0x180011229`
- `ntdll!RtlRegisterWait` at `0x180011142`
- `ntdll!RtlRegisterWait` at `0x18001138a`
- `ntdll!RtlRegisterWait` at `0x180011544`
- `ntdll!RtlRegisterWait` at `0x180011142`
- `ntdll!RtlRegisterWait` at `0x18001138a`
- `ntdll!RtlRegisterWait` at `0x180011544`
- `ntdll!NtCreateEvent` at `0x18001110e`
- `ntdll!NtCreateEvent` at `0x180011320`
- `ntdll!NtCreateEvent` at `0x1800114dd`
- `ntdll!NtCreateEvent` at `0x18001110e`
- `ntdll!NtCreateEvent` at `0x180011320`
- `ntdll!NtCreateEvent` at `0x1800114dd`
- `ntdll!NtNotifyChangeKey` at `0x18001142e`
- `ntdll!NtNotifyChangeKey` at `0x18001142e`
- `ntdll!RtlDeregisterWait` at `0x1800111af`
- `ntdll!RtlDeregisterWait` at `0x180011445`
- `ntdll!RtlDeregisterWait` at `0x1800115fc`
- `ntdll!RtlDeregisterWait` at `0x1800111af`
- `ntdll!RtlDeregisterWait` at `0x180011445`
- `ntdll!RtlDeregisterWait` at `0x1800115fc`
- `ntdll!NtOpenKey` at `0x18001126b`
- `ntdll!NtOpenKey` at `0x18001126b`
- `ntdll!RtlNtStatusToDosError` at `0x18001127d`
- `ntdll!RtlNtStatusToDosError` at `0x1800113c8`
- `ntdll!RtlNtStatusToDosError` at `0x1800114a4`
- `ntdll!RtlNtStatusToDosError` at `0x1800115a2`
- `ntdll!RtlNtStatusToDosError` at `0x18001127d`
- `ntdll!RtlNtStatusToDosError` at `0x1800113c8`
- `ntdll!RtlNtStatusToDosError` at `0x1800114a4`
- `ntdll!RtlNtStatusToDosError` at `0x1800115a2`
- `ntdll!NtClose` at `0x1800111c3`
- `ntdll!NtClose` at `0x1800113d5`
- `ntdll!NtClose` at `0x180011459`
- `ntdll!NtClose` at `0x180011557`
- `ntdll!NtClose` at `0x180011610`
- `ntdll!NtClose` at `0x1800116a8`
- `ntdll!NtClose` at `0x1800111c3`
- `ntdll!NtClose` at `0x1800113d5`
- `ntdll!NtClose` at `0x180011459`
- `ntdll!NtClose` at `0x180011557`
- `ntdll!NtClose` at `0x180011610`
- `ntdll!NtClose` at `0x1800116a8`

## string_xrefs

- `0x18001121d`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`

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
    qword_1800A7AE0 = (__int64)v6DnsNotifyChangeAddressEvent;
    Dnsv6NotifyChangeAddressOverlapped.Internal = 0;
    xmmword_1800A7AD0 = 0;
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
0x180011000  push    rbp
0x180011002  push    rsi
0x180011003  sub     rsp, 98h
0x18001100a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011011  lea     rsi, WPP_GLOBAL_Control
0x180011018  cmp     rcx, rsi
0x18001101b  jnz     loc_1800110B6
0x180011021  xorps   xmm0, xmm0
0x180011024  mov     [rsp+0A8h+arg_10], rbx
0x18001102c  xor     ebp, ebp
0x18001102e  mov     [rsp+0A8h+var_18], rdi
0x180011036  cmp     cs:?DnsTcpipInterfacesKey@@3PEAXEA, rbp; void * DnsTcpipInterfacesKey
0x18001103d  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x180011042  mov     [rsp+0A8h+arg_8], rbp
0x18001104a  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x18001104f  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180011057  movups  xmmword ptr [rsp+0A8h+DestinationString.Length], xmm0
0x18001105c  jz      loc_18001121D
0x180011062  cmp     cs:?DnsNotifyChangeKeyEvent@@3PEAXEA, rbp; void * DnsNotifyChangeKeyEvent
0x180011069  jz      loc_1800112F2
0x18001106f  cmp     cs:?DnsNotifyChangeAddressEvent@@3PEAXEA, rbp; void * DnsNotifyChangeAddressEvent
0x180011076  jz      loc_1800114AF
0x18001107c  cmp     cs:?v6DnsNotifyChangeAddressEvent@@3PEAXEA, rbp; void * v6DnsNotifyChangeAddressEvent
0x180011083  jz      short loc_1800110E4
0x180011085  call    ?FillInDnsServerList@@YAXXZ; FillInDnsServerList(void)
0x18001108a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011091  cmp     rcx, rsi
0x180011094  jnz     loc_180011702
0x18001109a  xor     eax, eax
0x18001109c  mov     rdi, [rsp+0A8h+var_18]
0x1800110a4  mov     rbx, [rsp+0A8h+arg_10]
0x1800110ac  add     rsp, 98h
0x1800110b3  pop     rsi
0x1800110b4  pop     rbp
0x1800110b5  retn
0x1800110b6  test    byte ptr [rcx+1Ch], 10h
0x1800110ba  jz      loc_180011021
0x1800110c0  cmp     byte ptr [rcx+19h], 6
0x1800110c4  jb      loc_180011021
0x1800110ca  mov     rcx, [rcx+10h]
0x1800110ce  lea     r8, WPP_1162121ddabf3385a9c607de51c938f1_Traceguids
0x1800110d5  mov     edx, 56h ; 'V'
0x1800110da  call    WPP_SF_
0x1800110df  jmp     loc_180011021
0x1800110e4  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x1800110eb  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x1800110f0  test    al, al
0x1800110f2  jz      short loc_180011085
0x1800110f4  mov     r9d, 1; EventType
0x1800110fa  mov     [rsp+0A8h+InitialState], bpl; InitialState
0x1800110ff  xor     r8d, r8d; ObjectAttributes
0x180011102  lea     rcx, ?v6DnsNotifyChangeAddressEvent@@3PEAXEA; EventHandle
0x180011109  mov     edx, 1F0003h; DesiredAccess
0x18001110e  call    cs:__imp_NtCreateEvent
0x180011114  mov     ebx, eax
0x180011116  test    eax, eax
0x180011118  js      loc_18001166A
0x18001111e  mov     rdx, cs:?v6DnsNotifyChangeAddressEvent@@3PEAXEA; hObject
0x180011125  lea     r8, ?Dnsv6NotifyChangeAddressCallbackRoutine@@YAXPEAXE@Z; Callback
0x18001112c  mov     [rsp+0A8h+ulFlags], ebp; ulFlags
0x180011130  lea     rcx, ?v6DnsNotifyChangeAddressWaitHandle@@3PEAXEA; phNewWaitObject
0x180011137  xor     r9d, r9d; pvContext
0x18001113a  mov     dword ptr [rsp+0A8h+InitialState], 0FFFFFFFFh; ulMilliseconds
0x180011142  call    cs:__imp_RtlRegisterWait
0x180011148  mov     ebx, eax
0x18001114a  test    eax, eax
0x18001114c  js      loc_1800116A1
0x180011152  mov     rax, cs:?v6DnsNotifyChangeAddressEvent@@3PEAXEA; void * v6DnsNotifyChangeAddressEvent
0x180011159  lea     r9, ?Dnsv6NotifyChangeAddressOverlapped@@3U_OVERLAPPED@@A; _OVERLAPPED Dnsv6NotifyChangeAddressOverlapped
0x180011160  mov     cs:qword_1800A7AE0, rax
0x180011167  lea     rdx, NPI_MS_IPV6_MODULEID
0x18001116e  lea     rax, [rsp+0A8h+arg_8]
0x180011176  mov     cs:?Dnsv6NotifyChangeAddressOverlapped@@3U_OVERLAPPED@@A, rbp; _OVERLAPPED Dnsv6NotifyChangeAddressOverlapped
0x18001117d  xorps   xmm0, xmm0
0x180011180  mov     qword ptr [rsp+0A8h+InitialState], rax
0x180011185  mov     r8d, 0Ah
0x18001118b  xor     ecx, ecx
0x18001118d  movdqu  cs:xmmword_1800A7AD0, xmm0
0x180011195  call    cs:__imp_NsiRequestChangeNotification
0x18001119b  mov     ebx, eax
0x18001119d  cmp     eax, 3E5h
0x1800111a2  jz      loc_180011085
0x1800111a8  mov     rcx, cs:?v6DnsNotifyChangeAddressWaitHandle@@3PEAXEA; hWaitHandle
0x1800111af  call    cs:__imp_RtlDeregisterWait
0x1800111b5  mov     rcx, cs:?v6DnsNotifyChangeAddressEvent@@3PEAXEA; Handle
0x1800111bc  mov     cs:?v6DnsNotifyChangeAddressWaitHandle@@3PEAXEA, rbp; void * v6DnsNotifyChangeAddressWaitHandle
0x1800111c3  call    cs:__imp_NtClose
0x1800111c9  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x1800111d0  mov     cs:?v6DnsNotifyChangeAddressEvent@@3PEAXEA, rbp; void * v6DnsNotifyChangeAddressEvent
0x1800111d7  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x1800111dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111e3  cmp     rcx, rsi
0x1800111e6  jz      loc_180011085
0x1800111ec  test    byte ptr [rcx+1Ch], 10h
0x1800111f0  jz      loc_180011085
0x1800111f6  cmp     byte ptr [rcx+19h], 3
0x1800111fa  jb      loc_180011085
0x180011200  mov     rcx, [rcx+10h]
0x180011204  lea     r8, WPP_1162121ddabf3385a9c607de51c938f1_Traceguids
0x18001120b  mov     edx, 61h ; 'a'
0x180011210  mov     r9d, ebx
0x180011213  call    WPP_SF_d
0x180011218  jmp     loc_180011085
0x18001121d  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x180011224  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x180011229  call    cs:__imp_RtlInitUnicodeString
0x18001122f  lea     rax, [rsp+0A8h+DestinationString]
0x180011234  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x18001123c  xorps   xmm0, xmm0
0x18001123f  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x180011244  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x180011249  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], rbp
0x18001124e  mov     edx, 20019h; DesiredAccess
0x180011253  mov     [rsp+0A8h+ObjectAttributes.Attributes], 40h ; '@'
0x18001125b  lea     rcx, ?DnsTcpipInterfacesKey@@3PEAXEA; KeyHandle
0x180011262  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001126b  call    cs:__imp_NtOpenKey
0x180011271  mov     edi, eax
0x180011273  test    eax, eax
0x180011275  jns     loc_180011062
0x18001127b  mov     ecx, eax; Status
0x18001127d  call    cs:__imp_RtlNtStatusToDosError
0x180011283  mov     ebx, eax
0x180011285  mov     rcx, cs:WPP_GLOBAL_Control
0x18001128c  cmp     rcx, rsi
0x18001128f  jnz     short loc_180011298
0x180011291  mov     eax, ebx
0x180011293  jmp     loc_18001109C
0x180011298  test    byte ptr [rcx+1Ch], 10h
0x18001129c  jz      short loc_1800112C7
0x18001129e  cmp     byte ptr [rcx+19h], 2
0x1800112a2  jb      short loc_1800112C7
0x1800112a4  mov     rcx, [rcx+10h]
0x1800112a8  lea     r8, WPP_1162121ddabf3385a9c607de51c938f1_Traceguids
0x1800112af  mov     edx, 57h ; 'W'
0x1800112b4  mov     dword ptr [rsp+0A8h+InitialState], ebx
0x1800112b8  mov     r9d, edi
0x1800112bb  call    WPP_SF_Dd
0x1800112c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800112c7  cmp     rcx, rsi
0x1800112ca  jz      short loc_180011291
0x1800112cc  test    byte ptr [rcx+1Ch], 10h
0x1800112d0  jz      short loc_180011291
0x1800112d2  cmp     byte ptr [rcx+19h], 6
0x1800112d6  jb      short loc_180011291
0x1800112d8  mov     rcx, [rcx+10h]
0x1800112dc  lea     r8, WPP_1162121ddabf3385a9c607de51c938f1_Traceguids
0x1800112e3  mov     edx, 58h ; 'X'
0x1800112e8  mov     r9d, ebx
0x1800112eb  call    WPP_SF_d
0x1800112f0  jmp     short loc_180011291
0x1800112f2  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x1800112f9  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x1800112fe  test    al, al
0x180011300  jz      loc_18001106F
0x180011306  mov     r9d, 1; EventType
0x18001130c  mov     [rsp+0A8h+InitialState], bpl; InitialState
0x180011311  xor     r8d, r8d; ObjectAttributes
0x180011314  lea     rcx, ?DnsNotifyChangeKeyEvent@@3PEAXEA; EventHandle
0x18001131b  mov     edx, 1F0003h; DesiredAccess
0x180011320  call    cs:__imp_NtCreateEvent
0x180011326  mov     ebx, eax
0x180011328  test    eax, eax
0x18001132a  jns     short loc_180011366
0x18001132c  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x180011333  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x180011338  mov     rcx, cs:WPP_GLOBAL_Control
0x18001133f  cmp     rcx, rsi
0x180011342  jz      loc_1800114A2
0x180011348  test    byte ptr [rcx+1Ch], 10h
0x18001134c  jz      loc_1800114A2
0x180011352  cmp     byte ptr [rcx+19h], 3
0x180011356  jb      loc_1800114A2
0x18001135c  mov     edx, 59h ; 'Y'
0x180011361  jmp     loc_18001148F
0x180011366  mov     rdx, cs:?DnsNotifyChangeKeyEvent@@3PEAXEA; hObject
0x18001136d  lea     r8, ?DnsNotifyChangeKeyCallbackRoutine@@YAXPEAXE@Z; Callback
0x180011374  mov     [rsp+0A8h+ulFlags], ebp; ulFlags
0x180011378  lea     rcx, ?DnsNotifyChangeKeyWaitHandle@@3PEAXEA; phNewWaitObject
0x18001137f  xor     r9d, r9d; pvContext
0x180011382  mov     dword ptr [rsp+0A8h+InitialState], 0FFFFFFFFh; ulMilliseconds
0x18001138a  call    cs:__imp_RtlRegisterWait
0x180011390  mov     ebx, eax
0x180011392  test    eax, eax
0x180011394  jns     short loc_1800113F3
0x180011396  mov     rcx, cs:WPP_GLOBAL_Control
0x18001139d  cmp     rcx, rsi
0x1800113a0  jz      short loc_1800113C6
0x1800113a2  test    byte ptr [rcx+1Ch], 10h
0x1800113a6  jz      short loc_1800113C6
0x1800113a8  cmp     byte ptr [rcx+19h], 3
0x1800113ac  jb      short loc_1800113C6
0x1800113ae  mov     rcx, [rcx+10h]
0x1800113b2  lea     r8, WPP_1162121ddabf3385a9c607de51c938f1_Traceguids
0x1800113b9  mov     edx, 5Ah ; 'Z'
0x1800113be  mov     r9d, eax
0x1800113c1  call    WPP_SF_d
0x1800113c6  mov     ecx, ebx; Status
0x1800113c8  call    cs:__imp_RtlNtStatusToDosError
0x1800113ce  mov     rcx, cs:?DnsNotifyChangeKeyEvent@@3PEAXEA; Handle
0x1800113d5  call    cs:__imp_NtClose
0x1800113db  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x1800113e2  mov     cs:?DnsNotifyChangeKeyEvent@@3PEAXEA, rbp; void * DnsNotifyChangeKeyEvent
0x1800113e9  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x1800113ee  jmp     loc_18001106F
0x1800113f3  mov     rdx, cs:?DnsNotifyChangeKeyEvent@@3PEAXEA; Event
0x1800113fa  lea     rax, ?DnsNotifyChangeKeyIoStatus@@3U_IO_STATUS_BLOCK@@A; _IO_STATUS_BLOCK DnsNotifyChangeKeyIoStatus
0x180011401  mov     rcx, cs:?DnsTcpipInterfacesKey@@3PEAXEA; KeyHandle
0x180011408  xor     r9d, r9d; ApcContext
0x18001140b  mov     [rsp+0A8h+WatchSubtree], 1; WatchSubtree
0x180011410  xor     r8d, r8d; ApcRoutine
0x180011413  mov     [rsp+0A8h+Length], ebp; Length
0x180011417  mov     [rsp+0A8h+ChangeBuffer], rbp; ChangeBuffer
0x18001141c  mov     [rsp+0A8h+Asynchroneous], 1; Asynchroneous
0x180011421  mov     [rsp+0A8h+ulFlags], 4; CompletionFilter
0x180011429  mov     qword ptr [rsp+0A8h+InitialState], rax; IoStatusBlock
0x18001142e  call    cs:__imp_NtNotifyChangeKey
0x180011434  mov     ebx, eax
0x180011436  test    eax, eax
0x180011438  jns     loc_18001106F
0x18001143e  mov     rcx, cs:?DnsNotifyChangeKeyWaitHandle@@3PEAXEA; hWaitHandle
0x180011445  call    cs:__imp_RtlDeregisterWait
0x18001144b  mov     rcx, cs:?DnsNotifyChangeKeyEvent@@3PEAXEA; Handle
0x180011452  mov     cs:?DnsNotifyChangeKeyWaitHandle@@3PEAXEA, rbp; void * DnsNotifyChangeKeyWaitHandle
0x180011459  call    cs:__imp_NtClose
0x18001145f  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x180011466  mov     cs:?DnsNotifyChangeKeyEvent@@3PEAXEA, rbp; void * DnsNotifyChangeKeyEvent
0x18001146d  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x180011472  mov     rcx, cs:WPP_GLOBAL_Control
0x180011479  cmp     rcx, rsi
0x18001147c  jz      short loc_1800114A2
0x18001147e  test    byte ptr [rcx+1Ch], 10h
0x180011482  jz      short loc_1800114A2
0x180011484  cmp     byte ptr [rcx+19h], 3
0x180011488  jb      short loc_1800114A2
0x18001148a  mov     edx, 5Bh ; '['
0x18001148f  mov     rcx, [rcx+10h]
0x180011493  lea     r8, WPP_1162121ddabf3385a9c607de51c938f1_Traceguids
0x18001149a  mov     r9d, ebx
0x18001149d  call    WPP_SF_d
0x1800114a2  mov     ecx, ebx; Status
0x1800114a4  call    cs:__imp_RtlNtStatusToDosError
0x1800114aa  jmp     loc_18001106F
0x1800114af  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x1800114b6  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x1800114bb  test    al, al
0x1800114bd  jz      loc_18001107C
0x1800114c3  mov     r9d, 1; EventType
0x1800114c9  mov     [rsp+0A8h+InitialState], bpl; InitialState
0x1800114ce  xor     r8d, r8d; ObjectAttributes
0x1800114d1  lea     rcx, ?DnsNotifyChangeAddressEvent@@3PEAXEA; EventHandle
0x1800114d8  mov     edx, 1F0003h; DesiredAccess
0x1800114dd  call    cs:__imp_NtCreateEvent
0x1800114e3  mov     ebx, eax
0x1800114e5  test    eax, eax
0x1800114e7  jns     short loc_180011520
0x1800114e9  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x1800114f0  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x1800114f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800114fc  cmp     rcx, rsi
0x1800114ff  jz      loc_1800115A0
0x180011505  test    byte ptr [rcx+1Ch], 10h
0x180011509  jz      loc_1800115A0
0x18001150f  cmp     byte ptr [rcx+19h], 3
0x180011513  jb      loc_1800115A0
0x180011519  mov     edx, 5Ch ; '\'
0x18001151e  jmp     short loc_18001158D
0x180011520  mov     rdx, cs:?DnsNotifyChangeAddressEvent@@3PEAXEA; hObject
0x180011527  lea     r8, ?DnsNotifyChangeAddressCallbackRoutine@@YAXPEAXE@Z; Callback
0x18001152e  mov     [rsp+0A8h+ulFlags], ebp; ulFlags
0x180011532  lea     rcx, ?DnsNotifyChangeAddressWaitHandle@@3PEAXEA; phNewWaitObject
0x180011539  xor     r9d, r9d; pvContext
0x18001153c  mov     dword ptr [rsp+0A8h+InitialState], 0FFFFFFFFh; ulMilliseconds
0x180011544  call    cs:__imp_RtlRegisterWait
0x18001154a  mov     ebx, eax
0x18001154c  test    eax, eax
0x18001154e  jns     short loc_1800115AD
0x180011550  mov     rcx, cs:?DnsNotifyChangeAddressEvent@@3PEAXEA; Handle
0x180011557  call    cs:__imp_NtClose
0x18001155d  lea     rcx, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x180011564  mov     cs:?DnsNotifyChangeAddressEvent@@3PEAXEA, rbp; void * DnsNotifyChangeAddressEvent
0x18001156b  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x180011570  mov     rcx, cs:WPP_GLOBAL_Control
0x180011577  cmp     rcx, rsi
0x18001157a  jz      short loc_1800115A0
0x18001157c  test    byte ptr [rcx+1Ch], 10h
0x180011580  jz      short loc_1800115A0
0x180011582  cmp     byte ptr [rcx+19h], 3
0x180011586  jb      short loc_1800115A0
0x180011588  mov     edx, 5Dh ; ']'
0x18001158d  mov     rcx, [rcx+10h]
0x180011591  lea     r8, WPP_1162121ddabf3385a9c607de51c938f1_Traceguids
0x180011598  mov     r9d, ebx
0x18001159b  call    WPP_SF_d
0x1800115a0  mov     ecx, ebx; Status
0x1800115a2  call    cs:__imp_RtlNtStatusToDosError
0x1800115a8  jmp     loc_18001107C
0x1800115ad  mov     rax, cs:?DnsNotifyChangeAddressEvent@@3PEAXEA; void * DnsNotifyChangeAddressEvent
0x1800115b4  lea     rdx, ?DnsNotifyChangeAddressOverlapped@@3U_OVERLAPPED@@A; overlapped
0x1800115bb  xorps   xmm0, xmm0
  ... truncated ...
```
