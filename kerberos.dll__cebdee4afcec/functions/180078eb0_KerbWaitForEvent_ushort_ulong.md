# KerbWaitForEvent(ushort *,ulong)

- ea: `0x180078eb0`
- end: `0x180078f9e`
- name: `?KerbWaitForEvent@@YAJPEAGK@Z`
- size: `238`
- prototype: `__int64 __fastcall(PCWSTR SourceString, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180078fa4`
- `0x180079338`

## callees

- `0x180078eb0`

## import_xrefs

- `ntdll!NtClose` at `0x180078f73`
- `ntdll!NtClose` at `0x180078f73`
- `ntdll!NtWaitForSingleObject` at `0x180078f67`
- `ntdll!NtWaitForSingleObject` at `0x180078f67`
- `ntdll!NtOpenEvent` at `0x180078f48`
- `ntdll!NtOpenEvent` at `0x180078f48`
- `ntdll!NtCreateEvent` at `0x180078f2a`
- `ntdll!NtCreateEvent` at `0x180078f2a`
- `ntdll!RtlInitUnicodeString` at `0x180078ee9`
- `ntdll!RtlInitUnicodeString` at `0x180078ee9`

## pseudocode

```c
NTSTATUS __fastcall KerbWaitForEvent(PCWSTR SourceString, unsigned int a2)
{
  __int64 v2; // rbx
  NTSTATUS result; // eax
  NTSTATUS v4; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+90h] [rbp+20h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+98h] [rbp+28h] BYREF

  v2 = a2;
  EventHandle = 0;
  Timeout.QuadPart = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtCreateEvent(&EventHandle, 0x100000u, &ObjectAttributes, NotificationEvent, 0);
  if ( result >= 0
    || result == -1073741771 && (result = NtOpenEvent(&EventHandle, 0x100000u, &ObjectAttributes), result >= 0) )
  {
    Timeout.QuadPart = -10000000 * v2;
    v4 = NtWaitForSingleObject(EventHandle, 0, &Timeout);
    NtClose(EventHandle);
    if ( v4 >= 0 )
    {
      if ( v4 != 258 )
        return 0;
      return -1073741422;
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180078eb0  mov     [rsp-8+arg_0], rbx
0x180078eb5  push    rbp
0x180078eb6  mov     rbp, rsp
0x180078eb9  sub     rsp, 70h
0x180078ebd  xorps   xmm0, xmm0
0x180078ec0  mov     ebx, edx
0x180078ec2  mov     rdx, rcx; SourceString
0x180078ec5  mov     [rbp+EventHandle], 0
0x180078ecd  lea     rcx, [rbp+DestinationString]; DestinationString
0x180078ed1  mov     qword ptr [rbp+Timeout], 0
0x180078ed9  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180078edd  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180078ee1  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180078ee5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180078ee9  call    cs:__imp_RtlInitUnicodeString
0x180078eef  lea     rax, [rbp+DestinationString]
0x180078ef3  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180078efa  xorps   xmm0, xmm0
0x180078efd  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180078f01  xor     r9d, r9d; EventType
0x180078f04  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180078f0c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180078f10  mov     [rbp+ObjectAttributes.Attributes], 0
0x180078f17  mov     edx, 100000h; DesiredAccess
0x180078f1c  mov     [rsp+70h+InitialState], 0; InitialState
0x180078f21  lea     rcx, [rbp+EventHandle]; EventHandle
0x180078f25  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180078f2a  call    cs:__imp_NtCreateEvent
0x180078f30  test    eax, eax
0x180078f32  jns     short loc_180078F52
0x180078f34  cmp     eax, 0C0000035h
0x180078f39  jnz     short loc_180078F90
0x180078f3b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180078f3f  mov     edx, 100000h; DesiredAccess
0x180078f44  lea     rcx, [rbp+EventHandle]; EventHandle
0x180078f48  call    cs:__imp_NtOpenEvent
0x180078f4e  test    eax, eax
0x180078f50  js      short loc_180078F90
0x180078f52  imul    rcx, rbx, 0FFFFFFFFFF676980h
0x180078f59  lea     r8, [rbp+Timeout]; Timeout
0x180078f5d  xor     edx, edx; Alertable
0x180078f5f  mov     qword ptr [rbp+Timeout], rcx
0x180078f63  mov     rcx, [rbp+EventHandle]; Handle
0x180078f67  call    cs:__imp_NtWaitForSingleObject
0x180078f6d  mov     rcx, [rbp+EventHandle]; Handle
0x180078f71  mov     ebx, eax
0x180078f73  call    cs:__imp_NtClose
0x180078f79  test    ebx, ebx
0x180078f7b  js      short loc_180078F8E
0x180078f7d  cmp     ebx, 102h
0x180078f83  jz      short loc_180078F89
0x180078f85  xor     eax, eax
0x180078f87  jmp     short loc_180078F90
0x180078f89  mov     ebx, 0C0000192h
0x180078f8e  mov     eax, ebx
0x180078f90  mov     rbx, [rsp+70h+arg_0]
0x180078f98  add     rsp, 70h
0x180078f9c  pop     rbp
0x180078f9d  retn
```
