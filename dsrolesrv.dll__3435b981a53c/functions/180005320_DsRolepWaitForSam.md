# DsRolepWaitForSam

- ea: `0x180005320`
- end: `0x1800053f2`
- name: `DsRolepWaitForSam`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012460`

## callees

- `0x180005320`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800053de`
- `ntdll!RtlNtStatusToDosError` at `0x1800053de`
- `ntdll!NtCreateEvent` at `0x180005392`
- `ntdll!NtCreateEvent` at `0x180005392`
- `ntdll!NtClose` at `0x1800053d6`
- `ntdll!NtClose` at `0x1800053d6`
- `ntdll!RtlInitUnicodeString` at `0x180005351`
- `ntdll!RtlInitUnicodeString` at `0x180005351`
- `ntdll!NtOpenEvent` at `0x1800053b5`
- `ntdll!NtOpenEvent` at `0x1800053b5`
- `ntdll!NtWaitForSingleObject` at `0x1800053ca`
- `ntdll!NtWaitForSingleObject` at `0x1800053ca`

## string_xrefs

- `0x180005330`: `\SAM_SERVICE_STARTED`

## pseudocode

```c
ULONG DsRolepWaitForSam()
{
  NTSTATUS v0; // eax
  int v1; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+80h] [rbp+10h] BYREF

  EventHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, L"\\SAM_SERVICE_STARTED");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtCreateEvent(&EventHandle, 0x100000u, &ObjectAttributes, NotificationEvent, 0);
  v1 = v0;
  if ( v0 == 0x40000000 || v0 == -1073741771 )
    v1 = NtOpenEvent(&EventHandle, 0x100000u, &ObjectAttributes);
  if ( v1 >= 0 )
  {
    v1 = NtWaitForSingleObject(EventHandle, 1u, 0);
    NtClose(EventHandle);
  }
  return RtlNtStatusToDosError(v1);
}

```

## disassembly

```asm
0x180005320  mov     [rsp-8+arg_8], rbx
0x180005325  push    rbp
0x180005326  mov     rbp, rsp
0x180005329  sub     rsp, 70h
0x18000532d  xorps   xmm0, xmm0
0x180005330  lea     rdx, SourceString; "\\SAM_SERVICE_STARTED"
0x180005337  xor     eax, eax
0x180005339  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000533d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180005341  mov     [rbp+EventHandle], rax
0x180005345  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180005349  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000534d  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180005351  call    cs:__imp_RtlInitUnicodeString
0x180005357  lea     rax, [rbp+DestinationString]
0x18000535b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180005362  xorps   xmm0, xmm0
0x180005365  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180005369  xor     r9d, r9d; EventType
0x18000536c  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180005374  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180005378  mov     [rbp+ObjectAttributes.Attributes], 0
0x18000537f  mov     edx, 100000h; DesiredAccess
0x180005384  mov     [rsp+70h+InitialState], 0; InitialState
0x180005389  lea     rcx, [rbp+EventHandle]; EventHandle
0x18000538d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180005392  call    cs:__imp_NtCreateEvent
0x180005398  mov     ebx, eax
0x18000539a  cmp     eax, 40000000h
0x18000539f  jz      short loc_1800053A8
0x1800053a1  cmp     eax, 0C0000035h
0x1800053a6  jnz     short loc_1800053BD
0x1800053a8  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800053ac  mov     edx, 100000h; DesiredAccess
0x1800053b1  lea     rcx, [rbp+EventHandle]; EventHandle
0x1800053b5  call    cs:__imp_NtOpenEvent
0x1800053bb  mov     ebx, eax
0x1800053bd  test    ebx, ebx
0x1800053bf  js      short loc_1800053DC
0x1800053c1  mov     rcx, [rbp+EventHandle]; Handle
0x1800053c5  xor     r8d, r8d; Timeout
0x1800053c8  mov     dl, 1; Alertable
0x1800053ca  call    cs:__imp_NtWaitForSingleObject
0x1800053d0  mov     rcx, [rbp+EventHandle]; Handle
0x1800053d4  mov     ebx, eax
0x1800053d6  call    cs:__imp_NtClose
0x1800053dc  mov     ecx, ebx; Status
0x1800053de  call    cs:__imp_RtlNtStatusToDosError
0x1800053e4  mov     rbx, [rsp+70h+arg_8]
0x1800053ec  add     rsp, 70h
0x1800053f0  pop     rbp
0x1800053f1  retn
```
