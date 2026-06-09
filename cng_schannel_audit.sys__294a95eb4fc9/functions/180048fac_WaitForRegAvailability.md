# WaitForRegAvailability

- ea: `0x180048fac`
- end: `0x18004907b`
- name: `WaitForRegAvailability`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, service_task`

## callers

- `0x180045220`

## callees

- `0x180048fac`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180048fc7`
- `ntoskrnl!RtlInitUnicodeString` at `0x180048fc7`
- `ntoskrnl!ZwClose` at `0x180049068`
- `ntoskrnl!ZwClose` at `0x180049068`
- `ntoskrnl!ZwOpenEvent` at `0x18004903f`
- `ntoskrnl!ZwOpenEvent` at `0x18004903f`
- `ntoskrnl!ZwWaitForSingleObject` at `0x180049058`
- `ntoskrnl!ZwWaitForSingleObject` at `0x180049058`
- `ntoskrnl!ZwCreateEvent` at `0x180049018`
- `ntoskrnl!ZwCreateEvent` at `0x180049018`

## string_xrefs

- `0x180048fb8`: `\SAM_SERVICE_STARTED`

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
0x180048fac  push    rbp
0x180048fae  mov     rbp, rsp
0x180048fb1  sub     rsp, 70h
0x180048fb5  xorps   xmm0, xmm0
0x180048fb8  lea     rdx, aSamServiceStar; "\\SAM_SERVICE_STARTED"
0x180048fbf  lea     rcx, [rbp+DestinationString]; DestinationString
0x180048fc3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180048fc7  call    cs:__imp_RtlInitUnicodeString
0x180048fce  nop     dword ptr [rax+rax+00h]
0x180048fd3  lea     rax, [rbp+DestinationString]
0x180048fd7  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180048fdf  xorps   xmm0, xmm0
0x180048fe2  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180048fe6  xor     r9d, r9d; EventType
0x180048fe9  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0
0x180048ff1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180048ff5  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180048ffd  mov     edx, 100000h; DesiredAccess
0x180049002  mov     [rbp+EventHandle], 0
0x18004900a  lea     rcx, [rbp+EventHandle]; EventHandle
0x18004900e  mov     [rsp+70h+InitialState], 0; InitialState
0x180049013  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180049018  call    cs:__imp_ZwCreateEvent
0x18004901f  nop     dword ptr [rax+rax+00h]
0x180049024  cmp     eax, 40000000h
0x180049029  jz      short loc_180049032
0x18004902b  cmp     eax, 0C0000035h
0x180049030  jnz     short loc_18004904B
0x180049032  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180049036  mov     edx, 100000h; DesiredAccess
0x18004903b  lea     rcx, [rbp+EventHandle]; EventHandle
0x18004903f  call    cs:__imp_ZwOpenEvent
0x180049046  nop     dword ptr [rax+rax+00h]
0x18004904b  test    eax, eax
0x18004904d  js      short loc_180049074
0x18004904f  mov     rcx, [rbp+EventHandle]; Handle
0x180049053  xor     r8d, r8d; Timeout
0x180049056  xor     edx, edx; Alertable
0x180049058  call    cs:__imp_ZwWaitForSingleObject
0x18004905f  nop     dword ptr [rax+rax+00h]
0x180049064  mov     rcx, [rbp+EventHandle]; Handle
0x180049068  call    cs:__imp_ZwClose
0x18004906f  nop     dword ptr [rax+rax+00h]
0x180049074  add     rsp, 70h
0x180049078  pop     rbp
0x180049079  retn
```
