# WaitForRegAvailability

- ea: `0x1800530ac`
- end: `0x18005317b`
- name: `WaitForRegAvailability`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, service_task`

## callers

- `0x18004f310`

## callees

- `0x1800530ac`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800530c7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800530c7`
- `ntoskrnl!ZwClose` at `0x180053168`
- `ntoskrnl!ZwClose` at `0x180053168`
- `ntoskrnl!ZwOpenEvent` at `0x18005313f`
- `ntoskrnl!ZwOpenEvent` at `0x18005313f`
- `ntoskrnl!ZwWaitForSingleObject` at `0x180053158`
- `ntoskrnl!ZwWaitForSingleObject` at `0x180053158`
- `ntoskrnl!ZwCreateEvent` at `0x180053118`
- `ntoskrnl!ZwCreateEvent` at `0x180053118`

## string_xrefs

- `0x1800530b8`: `\SAM_SERVICE_STARTED`

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
0x1800530ac  push    rbp
0x1800530ae  mov     rbp, rsp
0x1800530b1  sub     rsp, 70h
0x1800530b5  xorps   xmm0, xmm0
0x1800530b8  lea     rdx, aSamServiceStar; "\\SAM_SERVICE_STARTED"
0x1800530bf  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800530c3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800530c7  call    cs:__imp_RtlInitUnicodeString
0x1800530ce  nop     dword ptr [rax+rax+00h]
0x1800530d3  lea     rax, [rbp+DestinationString]
0x1800530d7  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800530df  xorps   xmm0, xmm0
0x1800530e2  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800530e6  xor     r9d, r9d; EventType
0x1800530e9  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0
0x1800530f1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800530f5  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800530fd  mov     edx, 100000h; DesiredAccess
0x180053102  mov     [rbp+EventHandle], 0
0x18005310a  lea     rcx, [rbp+EventHandle]; EventHandle
0x18005310e  mov     [rsp+70h+InitialState], 0; InitialState
0x180053113  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180053118  call    cs:__imp_ZwCreateEvent
0x18005311f  nop     dword ptr [rax+rax+00h]
0x180053124  cmp     eax, 40000000h
0x180053129  jz      short loc_180053132
0x18005312b  cmp     eax, 0C0000035h
0x180053130  jnz     short loc_18005314B
0x180053132  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180053136  mov     edx, 100000h; DesiredAccess
0x18005313b  lea     rcx, [rbp+EventHandle]; EventHandle
0x18005313f  call    cs:__imp_ZwOpenEvent
0x180053146  nop     dword ptr [rax+rax+00h]
0x18005314b  test    eax, eax
0x18005314d  js      short loc_180053174
0x18005314f  mov     rcx, [rbp+EventHandle]; Handle
0x180053153  xor     r8d, r8d; Timeout
0x180053156  xor     edx, edx; Alertable
0x180053158  call    cs:__imp_ZwWaitForSingleObject
0x18005315f  nop     dword ptr [rax+rax+00h]
0x180053164  mov     rcx, [rbp+EventHandle]; Handle
0x180053168  call    cs:__imp_ZwClose
0x18005316f  nop     dword ptr [rax+rax+00h]
0x180053174  add     rsp, 70h
0x180053178  pop     rbp
0x180053179  retn
```
