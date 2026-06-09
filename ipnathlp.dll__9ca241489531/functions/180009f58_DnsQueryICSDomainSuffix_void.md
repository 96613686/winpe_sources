# DnsQueryICSDomainSuffix(void)

- ea: `0x180009f58`
- end: `0x18000a2a8`
- name: `?DnsQueryICSDomainSuffix@@YAKXZ`
- size: `848`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008300`
- `0x180024c90`

## callees

- `0x180009f58`
- `0x18000a2b0`
- `0x18000b900`
- `0x18000bad0`
- `0x18000c110`
- `0x18000c750`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000a0e0`
- `ntdll!RtlInitUnicodeString` at `0x18000a0e0`
- `ntdll!RtlRegisterWait` at `0x18000a022`
- `ntdll!RtlRegisterWait` at `0x18000a022`
- `ntdll!NtCreateEvent` at `0x180009fea`
- `ntdll!NtCreateEvent` at `0x180009fea`
- `ntdll!NtNotifyChangeKey` at `0x18000a075`
- `ntdll!NtNotifyChangeKey` at `0x18000a075`
- `ntdll!RtlDeregisterWait` at `0x18000a211`
- `ntdll!RtlDeregisterWait` at `0x18000a211`
- `ntdll!NtOpenKey` at `0x18000a11c`
- `ntdll!NtOpenKey` at `0x18000a11c`
- `ntdll!RtlNtStatusToDosError` at `0x18000a12e`
- `ntdll!RtlNtStatusToDosError` at `0x18000a270`
- `ntdll!RtlNtStatusToDosError` at `0x18000a12e`
- `ntdll!RtlNtStatusToDosError` at `0x18000a270`
- `ntdll!NtClose` at `0x18000a1d2`
- `ntdll!NtClose` at `0x18000a229`
- `ntdll!NtClose` at `0x18000a1d2`
- `ntdll!NtClose` at `0x18000a229`

## string_xrefs

- `0x18000a0d5`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c
__int64 DnsQueryICSDomainSuffix(void)
{
  int Event; // ebx
  int v2; // eax
  unsigned int v3; // edi
  ULONG v4; // ebx
  PVOID *v5; // rcx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_1162121ddabf3385a9c607de51c938f1_Traceguids);
  }
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( !DnsTcpipParametersKey )
  {
    RtlInitUnicodeString(
      &DestinationString,
      L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v2 = NtOpenKey(&DnsTcpipParametersKey, 0x20019u, &ObjectAttributes);
    v3 = v2;
    if ( v2 < 0 )
    {
      v4 = RtlNtStatusToDosError(v2);
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_1162121ddabf3385a9c607de51c938f1_Traceguids, v3);
          v5 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x10) != 0 && *((_BYTE *)v5 + 25) >= 6u )
          WPP_SF_d(v5[2], 132, &WPP_1162121ddabf3385a9c607de51c938f1_Traceguids, v4);
      }
      return v4;
    }
  }
  if ( !DnsNotifyChangeKeyICSDomainEvent && AcquireComponentReference(&DnsComponentReference) )
  {
    Event = NtCreateEvent(&DnsNotifyChangeKeyICSDomainEvent, 0x1F0003u, 0, SynchronizationEvent, 0);
    if ( Event < 0 )
    {
      ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&DnsComponentReference);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v7 = 133;
    }
    else
    {
      Event = RtlRegisterWait(
                &DnsNotifyChangeKeyICSDomainWaitHandle,
                DnsNotifyChangeKeyICSDomainEvent,
                DnsNotifyChangeKeyICSDomainCallbackRoutine,
                0,
                0xFFFFFFFF,
                0);
      if ( Event < 0 )
      {
        NtClose(DnsNotifyChangeKeyICSDomainEvent);
        DnsNotifyChangeKeyICSDomainEvent = 0;
        ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&DnsComponentReference);
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_36;
        }
        v7 = 134;
      }
      else
      {
        Event = NtNotifyChangeKey(
                  DnsTcpipParametersKey,
                  DnsNotifyChangeKeyICSDomainEvent,
                  0,
                  0,
                  &DnsNotifyChangeKeyICSDomainIoStatus,
                  4u,
                  0,
                  0,
                  0,
                  1u);
        if ( Event >= 0 )
          goto LABEL_8;
        RtlDeregisterWait(DnsNotifyChangeKeyICSDomainWaitHandle);
        DnsNotifyChangeKeyICSDomainWaitHandle = 0;
        NtClose(DnsNotifyChangeKeyICSDomainEvent);
        DnsNotifyChangeKeyICSDomainEvent = 0;
        ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&DnsComponentReference);
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_36;
        }
        v7 = 135;
      }
    }
    WPP_SF_d(v6[2], v7, &WPP_1162121ddabf3385a9c607de51c938f1_Traceguids, (unsigned int)Event);
LABEL_36:
    RtlNtStatusToDosError(Event);
  }
LABEL_8:
  DnsQueryRegistryICSDomainSuffix();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, &WPP_1162121ddabf3385a9c607de51c938f1_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180009f58  push    rbp
0x180009f5a  push    rbx
0x180009f5b  push    rdi
0x180009f5c  push    r12
0x180009f5e  push    r15
0x180009f60  lea     rbp, [rsp-37h]
0x180009f65  sub     rsp, 90h
0x180009f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f73  lea     r15, WPP_GLOBAL_Control
0x180009f7a  lea     r12, WPP_1162121ddabf3385a9c607de51c938f1_Traceguids
0x180009f81  cmp     rcx, r15
0x180009f84  jnz     loc_18000A0AB
0x180009f8a  cmp     cs:?DnsTcpipParametersKey@@3PEAXEA, 0; void * DnsTcpipParametersKey
0x180009f92  xorps   xmm0, xmm0
0x180009f95  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180009f99  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180009f9d  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180009fa1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180009fa5  jz      loc_18000A0D5
0x180009fab  cmp     cs:?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA, 0; void * DnsNotifyChangeKeyICSDomainEvent
0x180009fb3  jnz     loc_18000A085
0x180009fb9  lea     rdi, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; _COMPONENT_REFERENCE DnsComponentReference
0x180009fc0  mov     rcx, rdi; lpCriticalSection
0x180009fc3  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x180009fc8  test    al, al
0x180009fca  jz      loc_18000A085
0x180009fd0  mov     r9d, 1; EventType
0x180009fd6  mov     [rsp+0B0h+InitialState], 0; InitialState
0x180009fdb  xor     r8d, r8d; ObjectAttributes
0x180009fde  lea     rcx, ?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA; EventHandle
0x180009fe5  mov     edx, 1F0003h; DesiredAccess
0x180009fea  call    cs:__imp_NtCreateEvent
0x180009ff0  mov     ebx, eax
0x180009ff2  test    eax, eax
0x180009ff4  js      loc_18000A195
0x180009ffa  mov     rdx, cs:?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA; hObject
0x18000a001  lea     r8, ?DnsNotifyChangeKeyICSDomainCallbackRoutine@@YAXPEAXE@Z; Callback
0x18000a008  mov     [rsp+0B0h+ulFlags], 0; ulFlags
0x18000a010  lea     rcx, ?DnsNotifyChangeKeyICSDomainWaitHandle@@3PEAXEA; phNewWaitObject
0x18000a017  xor     r9d, r9d; pvContext
0x18000a01a  mov     dword ptr [rsp+0B0h+InitialState], 0FFFFFFFFh; ulMilliseconds
0x18000a022  call    cs:__imp_RtlRegisterWait
0x18000a028  mov     ebx, eax
0x18000a02a  test    eax, eax
0x18000a02c  js      loc_18000A1CB
0x18000a032  mov     rdx, cs:?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA; Event
0x18000a039  lea     rax, ?DnsNotifyChangeKeyICSDomainIoStatus@@3U_IO_STATUS_BLOCK@@A; _IO_STATUS_BLOCK DnsNotifyChangeKeyICSDomainIoStatus
0x18000a040  mov     rcx, cs:?DnsTcpipParametersKey@@3PEAXEA; KeyHandle
0x18000a047  xor     r9d, r9d; ApcContext
0x18000a04a  mov     [rsp+0B0h+WatchSubtree], 1; WatchSubtree
0x18000a04f  xor     r8d, r8d; ApcRoutine
0x18000a052  mov     [rsp+0B0h+Length], 0; Length
0x18000a05a  mov     [rsp+0B0h+ChangeBuffer], 0; ChangeBuffer
0x18000a063  mov     [rsp+0B0h+Asynchroneous], 0; Asynchroneous
0x18000a068  mov     [rsp+0B0h+ulFlags], 4; CompletionFilter
0x18000a070  mov     qword ptr [rsp+0B0h+InitialState], rax; IoStatusBlock
0x18000a075  call    cs:__imp_NtNotifyChangeKey
0x18000a07b  mov     ebx, eax
0x18000a07d  test    eax, eax
0x18000a07f  js      loc_18000A20A
0x18000a085  call    ?DnsQueryRegistryICSDomainSuffix@@YAXXZ; DnsQueryRegistryICSDomainSuffix(void)
0x18000a08a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a091  cmp     rcx, r15
0x18000a094  jnz     loc_18000A27B
0x18000a09a  xor     eax, eax
0x18000a09c  add     rsp, 90h
0x18000a0a3  pop     r15
0x18000a0a5  pop     r12
0x18000a0a7  pop     rdi
0x18000a0a8  pop     rbx
0x18000a0a9  pop     rbp
0x18000a0aa  retn
0x18000a0ab  test    byte ptr [rcx+1Ch], 10h
0x18000a0af  jz      loc_180009F8A
0x18000a0b5  cmp     byte ptr [rcx+19h], 6
0x18000a0b9  jb      loc_180009F8A
0x18000a0bf  mov     rcx, [rcx+10h]
0x18000a0c3  mov     edx, 82h
0x18000a0c8  mov     r8, r12
0x18000a0cb  call    WPP_SF_
0x18000a0d0  jmp     loc_180009F8A
0x18000a0d5  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000a0dc  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000a0e0  call    cs:__imp_RtlInitUnicodeString
0x18000a0e6  lea     rax, [rbp+57h+DestinationString]
0x18000a0ea  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000a0f1  xorps   xmm0, xmm0
0x18000a0f4  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000a0f8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000a0fc  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18000a104  mov     edx, 20019h; DesiredAccess
0x18000a109  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000a110  lea     rcx, ?DnsTcpipParametersKey@@3PEAXEA; KeyHandle
0x18000a117  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a11c  call    cs:__imp_NtOpenKey
0x18000a122  mov     edi, eax
0x18000a124  test    eax, eax
0x18000a126  jns     loc_180009FAB
0x18000a12c  mov     ecx, eax; Status
0x18000a12e  call    cs:__imp_RtlNtStatusToDosError
0x18000a134  mov     ebx, eax
0x18000a136  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a13d  cmp     rcx, r15
0x18000a140  jz      short loc_18000A18E
0x18000a142  test    byte ptr [rcx+1Ch], 10h
0x18000a146  jz      short loc_18000A169
0x18000a148  cmp     byte ptr [rcx+19h], 2
0x18000a14c  jb      short loc_18000A169
0x18000a14e  mov     rcx, [rcx+10h]
0x18000a152  mov     edx, 83h
0x18000a157  mov     r9d, edi
0x18000a15a  mov     r8, r12
0x18000a15d  call    WPP_SF_d
0x18000a162  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a169  cmp     rcx, r15
0x18000a16c  jz      short loc_18000A18E
0x18000a16e  test    byte ptr [rcx+1Ch], 10h
0x18000a172  jz      short loc_18000A18E
0x18000a174  cmp     byte ptr [rcx+19h], 6
0x18000a178  jb      short loc_18000A18E
0x18000a17a  mov     rcx, [rcx+10h]
0x18000a17e  mov     edx, 84h
0x18000a183  mov     r9d, ebx
0x18000a186  mov     r8, r12
0x18000a189  call    WPP_SF_d
0x18000a18e  mov     eax, ebx
0x18000a190  jmp     loc_18000A09C
0x18000a195  mov     rcx, rdi; struct _COMPONENT_REFERENCE *
0x18000a198  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18000a19d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1a4  cmp     rcx, r15
0x18000a1a7  jz      loc_18000A26E
0x18000a1ad  test    byte ptr [rcx+1Ch], 10h
0x18000a1b1  jz      loc_18000A26E
0x18000a1b7  cmp     byte ptr [rcx+19h], 2
0x18000a1bb  jb      loc_18000A26E
0x18000a1c1  mov     edx, 85h
0x18000a1c6  jmp     loc_18000A25F
0x18000a1cb  mov     rcx, cs:?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA; Handle
0x18000a1d2  call    cs:__imp_NtClose
0x18000a1d8  mov     rcx, rdi; struct _COMPONENT_REFERENCE *
0x18000a1db  mov     cs:?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA, 0; void * DnsNotifyChangeKeyICSDomainEvent
0x18000a1e6  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18000a1eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1f2  cmp     rcx, r15
0x18000a1f5  jz      short loc_18000A26E
0x18000a1f7  test    byte ptr [rcx+1Ch], 10h
0x18000a1fb  jz      short loc_18000A26E
0x18000a1fd  cmp     byte ptr [rcx+19h], 2
0x18000a201  jb      short loc_18000A26E
0x18000a203  mov     edx, 86h
0x18000a208  jmp     short loc_18000A25F
0x18000a20a  mov     rcx, cs:?DnsNotifyChangeKeyICSDomainWaitHandle@@3PEAXEA; hWaitHandle
0x18000a211  call    cs:__imp_RtlDeregisterWait
0x18000a217  mov     rcx, cs:?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA; Handle
0x18000a21e  mov     cs:?DnsNotifyChangeKeyICSDomainWaitHandle@@3PEAXEA, 0; void * DnsNotifyChangeKeyICSDomainWaitHandle
0x18000a229  call    cs:__imp_NtClose
0x18000a22f  mov     rcx, rdi; struct _COMPONENT_REFERENCE *
0x18000a232  mov     cs:?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA, 0; void * DnsNotifyChangeKeyICSDomainEvent
0x18000a23d  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18000a242  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a249  cmp     rcx, r15
0x18000a24c  jz      short loc_18000A26E
0x18000a24e  test    byte ptr [rcx+1Ch], 10h
0x18000a252  jz      short loc_18000A26E
0x18000a254  cmp     byte ptr [rcx+19h], 2
0x18000a258  jb      short loc_18000A26E
0x18000a25a  mov     edx, 87h
0x18000a25f  mov     rcx, [rcx+10h]
0x18000a263  mov     r9d, ebx
0x18000a266  mov     r8, r12
0x18000a269  call    WPP_SF_d
0x18000a26e  mov     ecx, ebx; Status
0x18000a270  call    cs:__imp_RtlNtStatusToDosError
0x18000a276  jmp     loc_18000A085
0x18000a27b  test    byte ptr [rcx+1Ch], 10h
0x18000a27f  jz      loc_18000A09A
0x18000a285  cmp     byte ptr [rcx+19h], 6
0x18000a289  jb      loc_18000A09A
0x18000a28f  mov     rcx, [rcx+10h]
0x18000a293  mov     edx, 88h
0x18000a298  xor     r9d, r9d
0x18000a29b  mov     r8, r12
0x18000a29e  call    WPP_SF_d
0x18000a2a3  jmp     loc_18000A09A
```
