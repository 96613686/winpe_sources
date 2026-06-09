# DsRoleOpenEvent

- ea: `0x180009bfc`
- end: `0x180009cb3`
- name: `DsRoleOpenEvent`
- size: `183`
- prototype: `void *()`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009cf0`

## callees

- `0x180009bfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c9f`
- `ntdll!RtlNtStatusToDosError` at `0x180009c97`
- `ntdll!RtlNtStatusToDosError` at `0x180009c97`
- `ntdll!NtCreateEvent` at `0x180009c6d`
- `ntdll!NtCreateEvent` at `0x180009c6d`
- `ntdll!RtlInitUnicodeString` at `0x180009c2d`
- `ntdll!RtlInitUnicodeString` at `0x180009c2d`
- `ntdll!NtOpenEvent` at `0x180009c8b`
- `ntdll!NtOpenEvent` at `0x180009c8b`

## string_xrefs

- `0x180009c0c`: `Global\DsRoleServiceStartEvent`

## pseudocode

```c
void *DsRoleOpenEvent()
{
  int v0; // eax
  ULONG v1; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+90h] [rbp+20h] BYREF

  EventHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"Global\\DsRoleServiceStartEvent");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtCreateEvent(&EventHandle, 2u, &ObjectAttributes, NotificationEvent, 0);
  if ( v0 >= 0 )
    return EventHandle;
  if ( v0 == -1073741771 )
  {
    v0 = NtOpenEvent(&EventHandle, 2u, &ObjectAttributes);
    if ( v0 >= 0 )
      return EventHandle;
  }
  v1 = RtlNtStatusToDosError(v0);
  SetLastError(v1);
  return 0;
}

```

## disassembly

```asm
0x180009bfc  mov     [rsp-8+EventHandle], r8
0x180009c01  push    rbp
0x180009c02  mov     rbp, rsp
0x180009c05  sub     rsp, 70h
0x180009c09  xorps   xmm0, xmm0
0x180009c0c  lea     rdx, aGlobalDsrolese; "Global\\DsRoleServiceStartEvent"
0x180009c13  xor     eax, eax
0x180009c15  lea     rcx, [rbp+DestinationString]; DestinationString
0x180009c19  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180009c1d  mov     [rbp+EventHandle], rax
0x180009c21  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180009c25  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180009c29  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180009c2d  call    cs:__imp_RtlInitUnicodeString
0x180009c33  xor     r9d, r9d; EventType
0x180009c36  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180009c3d  lea     rax, [rbp+DestinationString]
0x180009c41  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180009c49  xorps   xmm0, xmm0
0x180009c4c  mov     [rbp+ObjectAttributes.Attributes], 0
0x180009c53  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180009c57  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180009c5b  lea     edx, [r9+2]; DesiredAccess
0x180009c5f  mov     [rsp+70h+InitialState], 0; InitialState
0x180009c64  lea     rcx, [rbp+EventHandle]; EventHandle
0x180009c68  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180009c6d  call    cs:__imp_NtCreateEvent
0x180009c73  test    eax, eax
0x180009c75  jns     short loc_180009CA9
0x180009c77  cmp     eax, 0C0000035h
0x180009c7c  jnz     short loc_180009C95
0x180009c7e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180009c82  mov     edx, 2; DesiredAccess
0x180009c87  lea     rcx, [rbp+EventHandle]; EventHandle
0x180009c8b  call    cs:__imp_NtOpenEvent
0x180009c91  test    eax, eax
0x180009c93  jns     short loc_180009CA9
0x180009c95  mov     ecx, eax; Status
0x180009c97  call    cs:__imp_RtlNtStatusToDosError
0x180009c9d  mov     ecx, eax; dwErrCode
0x180009c9f  call    cs:__imp_SetLastError
0x180009ca5  xor     eax, eax
0x180009ca7  jmp     short loc_180009CAD
0x180009ca9  mov     rax, [rbp+EventHandle]
0x180009cad  add     rsp, 70h
0x180009cb1  pop     rbp
0x180009cb2  retn
```
