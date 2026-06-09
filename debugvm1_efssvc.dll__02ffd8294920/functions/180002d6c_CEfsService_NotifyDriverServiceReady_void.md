# CEfsService::NotifyDriverServiceReady(void)

- ea: `0x180002d6c`
- end: `0x180002e8b`
- name: `?NotifyDriverServiceReady@CEfsService@@AEAAJXZ`
- size: `287`
- prototype: `__int64 __fastcall(CEfsService *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002ee0`

## callees

- `0x180002d6c`
- `0x180003604`

## import_xrefs

- `ntdll!NtSetEvent` at `0x180002e19`
- `ntdll!NtSetEvent` at `0x180002e19`
- `ntdll!NtOpenEvent` at `0x180002e07`
- `ntdll!NtOpenEvent` at `0x180002e07`
- `ntdll!NtCreateEvent` at `0x180002de7`
- `ntdll!NtCreateEvent` at `0x180002de7`
- `ntdll!RtlInitUnicodeString` at `0x180002da7`
- `ntdll!RtlInitUnicodeString` at `0x180002da7`
- `ntdll!RtlNtStatusToDosError` at `0x180002e67`
- `ntdll!RtlNtStatusToDosError` at `0x180002e67`
- `ntdll!NtClose` at `0x180002e3e`
- `ntdll!NtClose` at `0x180002e3e`

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
0x180002d6c  mov     [rsp-8+arg_0], rbx
0x180002d71  mov     [rsp-8+arg_10], rdi
0x180002d76  push    rbp
0x180002d77  mov     rbp, rsp
0x180002d7a  sub     rsp, 70h
0x180002d7e  xorps   xmm0, xmm0
0x180002d81  mov     [rbp+EventHandle], 0
0x180002d89  mov     rdi, rcx
0x180002d8c  lea     rdx, SourceString; "\\EFSInitEvent"
0x180002d93  lea     rcx, [rbp+DestinationString]; DestinationString
0x180002d97  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180002d9b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180002d9f  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180002da3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180002da7  call    cs:__imp_RtlInitUnicodeString
0x180002dad  xor     r9d, r9d; EventType
0x180002db0  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180002db7  lea     rax, [rbp+DestinationString]
0x180002dbb  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180002dc3  xorps   xmm0, xmm0
0x180002dc6  mov     [rbp+ObjectAttributes.Attributes], 0
0x180002dcd  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180002dd1  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180002dd5  lea     edx, [r9+2]; DesiredAccess
0x180002dd9  mov     [rsp+70h+InitialState], 1; InitialState
0x180002dde  lea     rcx, [rbp+EventHandle]; EventHandle
0x180002de2  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180002de7  call    cs:__imp_NtCreateEvent
0x180002ded  mov     ebx, eax
0x180002def  test    eax, eax
0x180002df1  jns     short loc_180002E2B
0x180002df3  cmp     eax, 0C0000035h
0x180002df8  jnz     short loc_180002E25
0x180002dfa  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180002dfe  mov     edx, 2; DesiredAccess
0x180002e03  lea     rcx, [rbp+EventHandle]; EventHandle
0x180002e07  call    cs:__imp_NtOpenEvent
0x180002e0d  mov     ebx, eax
0x180002e0f  test    eax, eax
0x180002e11  js      short loc_180002E25
0x180002e13  mov     rcx, [rbp+EventHandle]; EventHandle
0x180002e17  xor     edx, edx; PreviousState
0x180002e19  call    cs:__imp_NtSetEvent
0x180002e1f  mov     ebx, eax
0x180002e21  test    eax, eax
0x180002e23  jns     short loc_180002E2B
0x180002e25  mov     rcx, [rbp+EventHandle]
0x180002e29  jmp     short loc_180002E39
0x180002e2b  mov     rax, [rbp+EventHandle]
0x180002e2f  xor     ecx, ecx; Handle
0x180002e31  mov     [rdi+30h], rax
0x180002e35  mov     [rbp+EventHandle], rcx
0x180002e39  test    rcx, rcx
0x180002e3c  jz      short loc_180002E44
0x180002e3e  call    cs:__imp_NtClose
0x180002e44  test    ebx, ebx
0x180002e46  jns     short loc_180002E65
0x180002e48  mov     r9d, 12h
0x180002e4e  mov     dword ptr [rsp+70h+InitialState], 2B5h
0x180002e56  mov     r8d, ebx
0x180002e59  lea     rdx, EFS_API_ERROR
0x180002e60  call    fnEfsLogTrace1
0x180002e65  mov     ecx, ebx; Status
0x180002e67  call    cs:__imp_RtlNtStatusToDosError
0x180002e6d  test    eax, eax
0x180002e6f  jle     short loc_180002E79
0x180002e71  movzx   eax, ax
0x180002e74  or      eax, 80070000h
0x180002e79  lea     r11, [rsp+70h+var_s0]
0x180002e7e  mov     rbx, [r11+10h]
0x180002e82  mov     rdi, [r11+20h]
0x180002e86  mov     rsp, r11
0x180002e89  pop     rbp
0x180002e8a  retn
```
