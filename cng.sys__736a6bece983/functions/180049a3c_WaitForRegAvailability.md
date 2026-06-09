# WaitForRegAvailability

- ea: `0x180049a3c`
- end: `0x180049b0b`
- name: `WaitForRegAvailability`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, service_task`

## callers

- `0x180045cb0`

## callees

- `0x180049a3c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180049a57`
- `ntoskrnl!RtlInitUnicodeString` at `0x180049a57`
- `ntoskrnl!ZwClose` at `0x180049af8`
- `ntoskrnl!ZwClose` at `0x180049af8`
- `ntoskrnl!ZwOpenEvent` at `0x180049acf`
- `ntoskrnl!ZwOpenEvent` at `0x180049acf`
- `ntoskrnl!ZwWaitForSingleObject` at `0x180049ae8`
- `ntoskrnl!ZwWaitForSingleObject` at `0x180049ae8`
- `ntoskrnl!ZwCreateEvent` at `0x180049aa8`
- `ntoskrnl!ZwCreateEvent` at `0x180049aa8`

## string_xrefs

- `0x180049a48`: `\SAM_SERVICE_STARTED`

## pseudocode

```c
int WaitForRegAvailability()
{
  int result; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+80h] [rbp+10h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\SAM_SERVICE_STARTED");
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  memset(&ObjectAttributes.Attributes, 0, 24);
  ObjectAttributes.RootDirectory = 0;
  EventHandle = 0;
  result = ZwCreateEvent(&EventHandle, 0x100000u, &ObjectAttributes, NotificationEvent, 0);
  if ( result == 0x40000000 || result == -1073741771 )
    result = ZwOpenEvent(&EventHandle, 0x100000u, &ObjectAttributes);
  if ( result >= 0 )
  {
    ZwWaitForSingleObject(EventHandle, 0, 0);
    return ZwClose(EventHandle);
  }
  return result;
}

```

## disassembly

```asm
0x180049a3c  push    rbp
0x180049a3e  mov     rbp, rsp
0x180049a41  sub     rsp, 70h
0x180049a45  xorps   xmm0, xmm0
0x180049a48  lea     rdx, aSamServiceStar; "\\SAM_SERVICE_STARTED"
0x180049a4f  lea     rcx, [rbp+DestinationString]; DestinationString
0x180049a53  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180049a57  call    cs:__imp_RtlInitUnicodeString
0x180049a5e  nop     dword ptr [rax+rax+00h]
0x180049a63  lea     rax, [rbp+DestinationString]
0x180049a67  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180049a6f  xorps   xmm0, xmm0
0x180049a72  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180049a76  xor     r9d, r9d; EventType
0x180049a79  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0
0x180049a81  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180049a85  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180049a8d  mov     edx, 100000h; DesiredAccess
0x180049a92  mov     [rbp+EventHandle], 0
0x180049a9a  lea     rcx, [rbp+EventHandle]; EventHandle
0x180049a9e  mov     [rsp+70h+InitialState], 0; InitialState
0x180049aa3  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180049aa8  call    cs:__imp_ZwCreateEvent
0x180049aaf  nop     dword ptr [rax+rax+00h]
0x180049ab4  cmp     eax, 40000000h
0x180049ab9  jz      short loc_180049AC2
0x180049abb  cmp     eax, 0C0000035h
0x180049ac0  jnz     short loc_180049ADB
0x180049ac2  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180049ac6  mov     edx, 100000h; DesiredAccess
0x180049acb  lea     rcx, [rbp+EventHandle]; EventHandle
0x180049acf  call    cs:__imp_ZwOpenEvent
0x180049ad6  nop     dword ptr [rax+rax+00h]
0x180049adb  test    eax, eax
0x180049add  js      short loc_180049B04
0x180049adf  mov     rcx, [rbp+EventHandle]; Handle
0x180049ae3  xor     r8d, r8d; Timeout
0x180049ae6  xor     edx, edx; Alertable
0x180049ae8  call    cs:__imp_ZwWaitForSingleObject
0x180049aef  nop     dword ptr [rax+rax+00h]
0x180049af4  mov     rcx, [rbp+EventHandle]; Handle
0x180049af8  call    cs:__imp_ZwClose
0x180049aff  nop     dword ptr [rax+rax+00h]
0x180049b04  add     rsp, 70h
0x180049b08  pop     rbp
0x180049b09  retn
```
