# CEfsService::NotifyDriverServiceReady(void)

- ea: `0x180002e10`
- end: `0x180002f54`
- name: `?NotifyDriverServiceReady@CEfsService@@AEAAJXZ`
- size: `324`
- prototype: `__int64 __fastcall(CEfsService *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002fb0`

## callees

- `0x180002e10`
- `0x1800037b8`

## import_xrefs

- `ntdll!NtSetEvent` at `0x180002ecf`
- `ntdll!NtSetEvent` at `0x180002ecf`
- `ntdll!NtOpenEvent` at `0x180002eb7`
- `ntdll!NtOpenEvent` at `0x180002eb7`
- `ntdll!NtCreateEvent` at `0x180002e91`
- `ntdll!NtCreateEvent` at `0x180002e91`
- `ntdll!RtlInitUnicodeString` at `0x180002e4b`
- `ntdll!RtlInitUnicodeString` at `0x180002e4b`
- `ntdll!RtlNtStatusToDosError` at `0x180002f29`
- `ntdll!RtlNtStatusToDosError` at `0x180002f29`
- `ntdll!NtClose` at `0x180002efa`
- `ntdll!NtClose` at `0x180002efa`

## pseudocode

```c
signed int __fastcall CEfsService::NotifyDriverServiceReady(CEfsService *this)
{
  NTSTATUS v2; // eax
  int v3; // ebx
  void *v4; // rcx
  signed int result; // eax
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+88h] [rbp+18h] BYREF

  EventHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\EFSInitEvent");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = NtCreateEvent(&EventHandle, 2u, &ObjectAttributes, NotificationEvent, 1u);
  v3 = v2;
  if ( v2 >= 0
    || v2 == -1073741771
    && (v3 = NtOpenEvent(&EventHandle, 2u, &ObjectAttributes), v3 >= 0)
    && (v3 = NtSetEvent(EventHandle, 0), v3 >= 0) )
  {
    v4 = 0;
    *((_QWORD *)this + 6) = EventHandle;
    EventHandle = 0;
  }
  else
  {
    v4 = EventHandle;
  }
  if ( v4 )
    NtClose(v4);
  if ( v3 < 0 )
    fnEfsLogTrace1((_DWORD)v4, (unsigned int)EFS_API_ERROR, v3, 18, 181);
  result = RtlNtStatusToDosError(v3);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180002e10  mov     [rsp-8+arg_0], rbx
0x180002e15  mov     [rsp-8+arg_10], rdi
0x180002e1a  push    rbp
0x180002e1b  mov     rbp, rsp
0x180002e1e  sub     rsp, 70h
0x180002e22  xorps   xmm0, xmm0
0x180002e25  mov     [rbp+EventHandle], 0
0x180002e2d  mov     rdi, rcx
0x180002e30  lea     rdx, SourceString; "\\EFSInitEvent"
0x180002e37  lea     rcx, [rbp+DestinationString]; DestinationString
0x180002e3b  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180002e3f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180002e43  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180002e47  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180002e4b  call    cs:__imp_RtlInitUnicodeString
0x180002e52  nop     dword ptr [rax+rax+00h]
0x180002e57  xor     r9d, r9d; EventType
0x180002e5a  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180002e61  lea     rax, [rbp+DestinationString]
0x180002e65  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180002e6d  xorps   xmm0, xmm0
0x180002e70  mov     [rbp+ObjectAttributes.Attributes], 0
0x180002e77  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180002e7b  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180002e7f  lea     edx, [r9+2]; DesiredAccess
0x180002e83  mov     [rsp+70h+InitialState], 1; InitialState
0x180002e88  lea     rcx, [rbp+EventHandle]; EventHandle
0x180002e8c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180002e91  call    cs:__imp_NtCreateEvent
0x180002e98  nop     dword ptr [rax+rax+00h]
0x180002e9d  mov     ebx, eax
0x180002e9f  test    eax, eax
0x180002ea1  jns     short loc_180002EE7
0x180002ea3  cmp     eax, 0C0000035h
0x180002ea8  jnz     short loc_180002EE1
0x180002eaa  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180002eae  mov     edx, 2; DesiredAccess
0x180002eb3  lea     rcx, [rbp+EventHandle]; EventHandle
0x180002eb7  call    cs:__imp_NtOpenEvent
0x180002ebe  nop     dword ptr [rax+rax+00h]
0x180002ec3  mov     ebx, eax
0x180002ec5  test    eax, eax
0x180002ec7  js      short loc_180002EE1
0x180002ec9  mov     rcx, [rbp+EventHandle]; EventHandle
0x180002ecd  xor     edx, edx; PreviousState
0x180002ecf  call    cs:__imp_NtSetEvent
0x180002ed6  nop     dword ptr [rax+rax+00h]
0x180002edb  mov     ebx, eax
0x180002edd  test    eax, eax
0x180002edf  jns     short loc_180002EE7
0x180002ee1  mov     rcx, [rbp+EventHandle]
0x180002ee5  jmp     short loc_180002EF5
0x180002ee7  mov     rax, [rbp+EventHandle]
0x180002eeb  xor     ecx, ecx; Handle
0x180002eed  mov     [rdi+30h], rax
0x180002ef1  mov     [rbp+EventHandle], rcx
0x180002ef5  test    rcx, rcx
0x180002ef8  jz      short loc_180002F06
0x180002efa  call    cs:__imp_NtClose
0x180002f01  nop     dword ptr [rax+rax+00h]
0x180002f06  test    ebx, ebx
0x180002f08  jns     short loc_180002F27
0x180002f0a  mov     r9d, 12h
0x180002f10  mov     dword ptr [rsp+70h+InitialState], 2B5h
0x180002f18  mov     r8d, ebx
0x180002f1b  lea     rdx, EFS_API_ERROR
0x180002f22  call    fnEfsLogTrace1
0x180002f27  mov     ecx, ebx; Status
0x180002f29  call    cs:__imp_RtlNtStatusToDosError
0x180002f30  nop     dword ptr [rax+rax+00h]
0x180002f35  test    eax, eax
0x180002f37  jle     short loc_180002F41
0x180002f39  movzx   eax, ax
0x180002f3c  or      eax, 80070000h
0x180002f41  lea     r11, [rsp+70h+var_s0]
0x180002f46  mov     rbx, [r11+10h]
0x180002f4a  mov     rdi, [r11+20h]
0x180002f4e  mov     rsp, r11
0x180002f51  pop     rbp
0x180002f52  retn
```
