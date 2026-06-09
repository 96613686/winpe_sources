# DnsQueryICSDomainSuffix(void)

- ea: `0x18000a640`
- end: `0x18000a9d1`
- name: `?DnsQueryICSDomainSuffix@@YAKXZ`
- size: `913`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800087c0`
- `0x1800271d0`

## callees

- `0x18000a640`
- `0x18000a9d8`
- `0x18000c1e0`
- `0x18000c3c0`
- `0x18000ca20`
- `0x18000d090`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000a7db`
- `ntdll!RtlInitUnicodeString` at `0x18000a7db`
- `ntdll!RtlRegisterWait` at `0x18000a710`
- `ntdll!RtlRegisterWait` at `0x18000a710`
- `ntdll!NtCreateEvent` at `0x18000a6d2`
- `ntdll!NtCreateEvent` at `0x18000a6d2`
- `ntdll!NtNotifyChangeKey` at `0x18000a769`
- `ntdll!NtNotifyChangeKey` at `0x18000a769`
- `ntdll!RtlDeregisterWait` at `0x18000a928`
- `ntdll!RtlDeregisterWait` at `0x18000a928`
- `ntdll!NtOpenKey` at `0x18000a81d`
- `ntdll!NtOpenKey` at `0x18000a81d`
- `ntdll!RtlNtStatusToDosError` at `0x18000a835`
- `ntdll!RtlNtStatusToDosError` at `0x18000a993`
- `ntdll!RtlNtStatusToDosError` at `0x18000a835`
- `ntdll!RtlNtStatusToDosError` at `0x18000a993`
- `ntdll!NtClose` at `0x18000a8df`
- `ntdll!NtClose` at `0x18000a946`
- `ntdll!NtClose` at `0x18000a8df`
- `ntdll!NtClose` at `0x18000a946`

## string_xrefs

- `0x18000a7d0`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip\Parameters`

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
0x18000a640  push    rbp
0x18000a642  push    rbx
0x18000a643  push    rdi
0x18000a644  push    r12
0x18000a646  push    r15
0x18000a648  lea     rbp, [rsp-37h]
0x18000a64d  sub     rsp, 90h
0x18000a654  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a65b  lea     r15, WPP_GLOBAL_Control
0x18000a662  lea     r12, WPP_1162121ddabf3385a9c607de51c938f1_Traceguids
0x18000a669  cmp     rcx, r15
0x18000a66c  jnz     loc_18000A7A6
0x18000a672  cmp     cs:?DnsTcpipParametersKey@@3PEAXEA, 0; void * DnsTcpipParametersKey
0x18000a67a  xorps   xmm0, xmm0
0x18000a67d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000a681  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000a685  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a689  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000a68d  jz      loc_18000A7D0
0x18000a693  cmp     cs:?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA, 0; void * DnsNotifyChangeKeyICSDomainEvent
0x18000a69b  jnz     loc_18000A77F
0x18000a6a1  lea     rdi, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; _COMPONENT_REFERENCE DnsComponentReference
0x18000a6a8  mov     rcx, rdi; lpCriticalSection
0x18000a6ab  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x18000a6b0  test    al, al
0x18000a6b2  jz      loc_18000A77F
0x18000a6b8  mov     r9d, 1; EventType
0x18000a6be  mov     [rsp+0B0h+InitialState], 0; InitialState
0x18000a6c3  xor     r8d, r8d; ObjectAttributes
0x18000a6c6  lea     rcx, ?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA; EventHandle
0x18000a6cd  mov     edx, 1F0003h; DesiredAccess
0x18000a6d2  call    cs:__imp_NtCreateEvent
0x18000a6d9  nop     dword ptr [rax+rax+00h]
0x18000a6de  mov     ebx, eax
0x18000a6e0  test    eax, eax
0x18000a6e2  js      loc_18000A8A2
0x18000a6e8  mov     rdx, cs:?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA; hObject
0x18000a6ef  lea     r8, ?DnsNotifyChangeKeyICSDomainCallbackRoutine@@YAXPEAXE@Z; Callback
0x18000a6f6  mov     [rsp+0B0h+ulFlags], 0; ulFlags
0x18000a6fe  lea     rcx, ?DnsNotifyChangeKeyICSDomainWaitHandle@@3PEAXEA; phNewWaitObject
0x18000a705  xor     r9d, r9d; pvContext
0x18000a708  mov     dword ptr [rsp+0B0h+InitialState], 0FFFFFFFFh; ulMilliseconds
0x18000a710  call    cs:__imp_RtlRegisterWait
0x18000a717  nop     dword ptr [rax+rax+00h]
0x18000a71c  mov     ebx, eax
0x18000a71e  test    eax, eax
0x18000a720  js      loc_18000A8D8
0x18000a726  mov     rdx, cs:?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA; Event
0x18000a72d  lea     rax, ?DnsNotifyChangeKeyICSDomainIoStatus@@3U_IO_STATUS_BLOCK@@A; _IO_STATUS_BLOCK DnsNotifyChangeKeyICSDomainIoStatus
0x18000a734  mov     rcx, cs:?DnsTcpipParametersKey@@3PEAXEA; KeyHandle
0x18000a73b  xor     r9d, r9d; ApcContext
0x18000a73e  mov     [rsp+0B0h+WatchSubtree], 1; WatchSubtree
0x18000a743  xor     r8d, r8d; ApcRoutine
0x18000a746  mov     [rsp+0B0h+Length], 0; Length
0x18000a74e  mov     [rsp+0B0h+ChangeBuffer], 0; ChangeBuffer
0x18000a757  mov     [rsp+0B0h+Asynchroneous], 0; Asynchroneous
0x18000a75c  mov     [rsp+0B0h+ulFlags], 4; CompletionFilter
0x18000a764  mov     qword ptr [rsp+0B0h+InitialState], rax; IoStatusBlock
0x18000a769  call    cs:__imp_NtNotifyChangeKey
0x18000a770  nop     dword ptr [rax+rax+00h]
0x18000a775  mov     ebx, eax
0x18000a777  test    eax, eax
0x18000a779  js      loc_18000A921
0x18000a77f  call    ?DnsQueryRegistryICSDomainSuffix@@YAXXZ; DnsQueryRegistryICSDomainSuffix(void)
0x18000a784  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a78b  cmp     rcx, r15
0x18000a78e  jnz     loc_18000A9A4
0x18000a794  xor     eax, eax
0x18000a796  add     rsp, 90h
0x18000a79d  pop     r15
0x18000a79f  pop     r12
0x18000a7a1  pop     rdi
0x18000a7a2  pop     rbx
0x18000a7a3  pop     rbp
0x18000a7a4  retn
0x18000a7a6  test    byte ptr [rcx+1Ch], 10h
0x18000a7aa  jz      loc_18000A672
0x18000a7b0  cmp     byte ptr [rcx+19h], 6
0x18000a7b4  jb      loc_18000A672
0x18000a7ba  mov     rcx, [rcx+10h]
0x18000a7be  mov     edx, 82h
0x18000a7c3  mov     r8, r12
0x18000a7c6  call    WPP_SF_
0x18000a7cb  jmp     loc_18000A672
0x18000a7d0  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000a7d7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000a7db  call    cs:__imp_RtlInitUnicodeString
0x18000a7e2  nop     dword ptr [rax+rax+00h]
0x18000a7e7  lea     rax, [rbp+57h+DestinationString]
0x18000a7eb  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000a7f2  xorps   xmm0, xmm0
0x18000a7f5  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000a7f9  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000a7fd  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18000a805  mov     edx, 20019h; DesiredAccess
0x18000a80a  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000a811  lea     rcx, ?DnsTcpipParametersKey@@3PEAXEA; KeyHandle
0x18000a818  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a81d  call    cs:__imp_NtOpenKey
0x18000a824  nop     dword ptr [rax+rax+00h]
0x18000a829  mov     edi, eax
0x18000a82b  test    eax, eax
0x18000a82d  jns     loc_18000A693
0x18000a833  mov     ecx, eax; Status
0x18000a835  call    cs:__imp_RtlNtStatusToDosError
0x18000a83c  nop     dword ptr [rax+rax+00h]
0x18000a841  mov     ebx, eax
0x18000a843  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a84a  cmp     rcx, r15
0x18000a84d  jz      short loc_18000A89B
0x18000a84f  test    byte ptr [rcx+1Ch], 10h
0x18000a853  jz      short loc_18000A876
0x18000a855  cmp     byte ptr [rcx+19h], 2
0x18000a859  jb      short loc_18000A876
0x18000a85b  mov     rcx, [rcx+10h]
0x18000a85f  mov     edx, 83h
0x18000a864  mov     r9d, edi
0x18000a867  mov     r8, r12
0x18000a86a  call    WPP_SF_d
0x18000a86f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a876  cmp     rcx, r15
0x18000a879  jz      short loc_18000A89B
0x18000a87b  test    byte ptr [rcx+1Ch], 10h
0x18000a87f  jz      short loc_18000A89B
0x18000a881  cmp     byte ptr [rcx+19h], 6
0x18000a885  jb      short loc_18000A89B
0x18000a887  mov     rcx, [rcx+10h]
0x18000a88b  mov     edx, 84h
0x18000a890  mov     r9d, ebx
0x18000a893  mov     r8, r12
0x18000a896  call    WPP_SF_d
0x18000a89b  mov     eax, ebx
0x18000a89d  jmp     loc_18000A796
0x18000a8a2  mov     rcx, rdi; struct _COMPONENT_REFERENCE *
0x18000a8a5  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18000a8aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8b1  cmp     rcx, r15
0x18000a8b4  jz      loc_18000A991
0x18000a8ba  test    byte ptr [rcx+1Ch], 10h
0x18000a8be  jz      loc_18000A991
0x18000a8c4  cmp     byte ptr [rcx+19h], 2
0x18000a8c8  jb      loc_18000A991
0x18000a8ce  mov     edx, 85h
0x18000a8d3  jmp     loc_18000A982
0x18000a8d8  mov     rcx, cs:?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA; Handle
0x18000a8df  call    cs:__imp_NtClose
0x18000a8e6  nop     dword ptr [rax+rax+00h]
0x18000a8eb  mov     rcx, rdi; struct _COMPONENT_REFERENCE *
0x18000a8ee  mov     cs:?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA, 0; void * DnsNotifyChangeKeyICSDomainEvent
0x18000a8f9  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18000a8fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a905  cmp     rcx, r15
0x18000a908  jz      loc_18000A991
0x18000a90e  test    byte ptr [rcx+1Ch], 10h
0x18000a912  jz      short loc_18000A991
0x18000a914  cmp     byte ptr [rcx+19h], 2
0x18000a918  jb      short loc_18000A991
0x18000a91a  mov     edx, 86h
0x18000a91f  jmp     short loc_18000A982
0x18000a921  mov     rcx, cs:?DnsNotifyChangeKeyICSDomainWaitHandle@@3PEAXEA; hWaitHandle
0x18000a928  call    cs:__imp_RtlDeregisterWait
0x18000a92f  nop     dword ptr [rax+rax+00h]
0x18000a934  mov     rcx, cs:?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA; Handle
0x18000a93b  mov     cs:?DnsNotifyChangeKeyICSDomainWaitHandle@@3PEAXEA, 0; void * DnsNotifyChangeKeyICSDomainWaitHandle
0x18000a946  call    cs:__imp_NtClose
0x18000a94d  nop     dword ptr [rax+rax+00h]
0x18000a952  mov     rcx, rdi; struct _COMPONENT_REFERENCE *
0x18000a955  mov     cs:?DnsNotifyChangeKeyICSDomainEvent@@3PEAXEA, 0; void * DnsNotifyChangeKeyICSDomainEvent
0x18000a960  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18000a965  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a96c  cmp     rcx, r15
0x18000a96f  jz      short loc_18000A991
0x18000a971  test    byte ptr [rcx+1Ch], 10h
0x18000a975  jz      short loc_18000A991
0x18000a977  cmp     byte ptr [rcx+19h], 2
0x18000a97b  jb      short loc_18000A991
0x18000a97d  mov     edx, 87h
0x18000a982  mov     rcx, [rcx+10h]
0x18000a986  mov     r9d, ebx
0x18000a989  mov     r8, r12
0x18000a98c  call    WPP_SF_d
0x18000a991  mov     ecx, ebx; Status
0x18000a993  call    cs:__imp_RtlNtStatusToDosError
0x18000a99a  nop     dword ptr [rax+rax+00h]
0x18000a99f  jmp     loc_18000A77F
0x18000a9a4  test    byte ptr [rcx+1Ch], 10h
0x18000a9a8  jz      loc_18000A794
0x18000a9ae  cmp     byte ptr [rcx+19h], 6
0x18000a9b2  jb      loc_18000A794
0x18000a9b8  mov     rcx, [rcx+10h]
0x18000a9bc  mov     edx, 88h
0x18000a9c1  xor     r9d, r9d
0x18000a9c4  mov     r8, r12
0x18000a9c7  call    WPP_SF_d
0x18000a9cc  jmp     loc_18000A794
```
