# NlWaitForSamService(uchar)

- ea: `0x18003ee4c`
- end: `0x18003ef98`
- name: `?NlWaitForSamService@@YAEE@Z`
- size: `332`
- prototype: `unsigned __int8 __fastcall(unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006f490`

## callees

- `0x180007278`
- `0x180028750`
- `0x18003ee4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003ef24`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003ef24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef61`
- `ntdll!NtClose` at `0x18003ef57`
- `ntdll!NtClose` at `0x18003ef82`
- `ntdll!NtClose` at `0x18003ef57`
- `ntdll!NtClose` at `0x18003ef82`
- `ntdll!NtOpenEvent` at `0x18003eeba`
- `ntdll!NtOpenEvent` at `0x18003eefb`
- `ntdll!NtOpenEvent` at `0x18003eeba`
- `ntdll!NtOpenEvent` at `0x18003eefb`
- `ntdll!RtlInitUnicodeString` at `0x18003ee7f`
- `ntdll!RtlInitUnicodeString` at `0x18003ee7f`
- `ntdll!NtCreateEvent` at `0x18003eedd`
- `ntdll!NtCreateEvent` at `0x18003eedd`

## string_xrefs

- `0x18003ee64`: `\SAM_SERVICE_STARTED`
- `0x18003ef08`: `NlWaitForSamService couldn't make the event handle : %lx\n`
- `0x18003ef33`: `NlWaitForSamService 5-second timeout (Rewaiting)\n`
- `0x18003ef6a`: `NlWaitForSamService: error %ld %ld\n`

## pseudocode

```c
unsigned __int8 __fastcall NlWaitForSamService()
{
  NTSTATUS v0; // eax
  DWORD v1; // ebx
  DWORD LastError; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+88h] [rbp+18h] BYREF

  EventHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, L"\\SAM_SERVICE_STARTED");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtOpenEvent(&EventHandle, 0x100002u, &ObjectAttributes);
  if ( v0 >= 0 )
    goto LABEL_18;
  if ( v0 != -1073741772 )
    goto LABEL_7;
  v0 = NtCreateEvent(&EventHandle, 0x100002u, &ObjectAttributes, NotificationEvent, 0);
  if ( v0 == 0x40000000 || v0 == -1073741771 )
    v0 = NtOpenEvent(&EventHandle, 0x100002u, &ObjectAttributes);
  if ( v0 >= 0 )
  {
LABEL_18:
    while ( 1 )
    {
      v1 = WaitForSingleObject(EventHandle, 0x1388u);
      if ( v1 != 258 )
        break;
      NlPrintRoutine(0x100u, L"NlWaitForSamService 5-second timeout (Rewaiting)\n");
      if ( !(unsigned int)GiveInstallHints(0) )
        goto LABEL_14;
    }
    if ( !v1 )
    {
      NtClose(EventHandle);
      return 1;
    }
    LastError = GetLastError();
    NlPrintRoutine(0x100u, L"NlWaitForSamService: error %ld %ld\n", LastError, v1);
LABEL_14:
    NtClose(EventHandle);
  }
  else
  {
LABEL_7:
    NlPrintRoutine(0x100u, L"NlWaitForSamService couldn't make the event handle : %lx\n", (unsigned int)v0);
  }
  return 0;
}

```

## disassembly

```asm
0x18003ee4c  mov     [rsp-8+arg_0], rbx
0x18003ee51  push    rbp
0x18003ee52  mov     rbp, rsp
0x18003ee55  sub     rsp, 70h
0x18003ee59  xorps   xmm0, xmm0
0x18003ee5c  mov     [rbp+EventHandle], 0
0x18003ee64  lea     rdx, aSamServiceStar; "\\SAM_SERVICE_STARTED"
0x18003ee6b  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003ee6f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18003ee73  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18003ee77  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18003ee7b  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18003ee7f  call    cs:__imp_RtlInitUnicodeString
0x18003ee85  lea     rax, [rbp+DestinationString]
0x18003ee89  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18003ee90  xorps   xmm0, xmm0
0x18003ee93  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18003ee97  mov     ebx, 100002h
0x18003ee9c  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18003eea4  mov     edx, ebx; DesiredAccess
0x18003eea6  mov     [rbp+ObjectAttributes.Attributes], 0
0x18003eead  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18003eeb1  lea     rcx, [rbp+EventHandle]; EventHandle
0x18003eeb5  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18003eeba  call    cs:__imp_NtOpenEvent
0x18003eec0  test    eax, eax
0x18003eec2  jns     short loc_18003EF1B
0x18003eec4  cmp     eax, 0C0000034h
0x18003eec9  jnz     short loc_18003EF05
0x18003eecb  xor     r9d, r9d; EventType
0x18003eece  mov     [rsp+70h+InitialState], 0; InitialState
0x18003eed3  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18003eed7  mov     edx, ebx; DesiredAccess
0x18003eed9  lea     rcx, [rbp+EventHandle]; EventHandle
0x18003eedd  call    cs:__imp_NtCreateEvent
0x18003eee3  cmp     eax, 40000000h
0x18003eee8  jz      short loc_18003EEF1
0x18003eeea  cmp     eax, 0C0000035h
0x18003eeef  jnz     short loc_18003EF01
0x18003eef1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18003eef5  mov     edx, ebx; DesiredAccess
0x18003eef7  lea     rcx, [rbp+EventHandle]; EventHandle
0x18003eefb  call    cs:__imp_NtOpenEvent
0x18003ef01  test    eax, eax
0x18003ef03  jns     short loc_18003EF1B
0x18003ef05  mov     r8d, eax
0x18003ef08  lea     rdx, aNlwaitforsamse_0; "NlWaitForSamService couldn't make the e"...
0x18003ef0f  mov     ecx, 100h; unsigned int
0x18003ef14  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ef19  jmp     short loc_18003EF88
0x18003ef1b  mov     rcx, [rbp+EventHandle]; hHandle
0x18003ef1f  mov     edx, 1388h; dwMilliseconds
0x18003ef24  call    cs:__imp_WaitForSingleObject
0x18003ef2a  mov     ebx, eax
0x18003ef2c  cmp     eax, 102h
0x18003ef31  jnz     short loc_18003EF4F
0x18003ef33  lea     rdx, aNlwaitforsamse_1; "NlWaitForSamService 5-second timeout (R"...
0x18003ef3a  lea     ecx, [rax-2]; unsigned int
0x18003ef3d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ef42  xor     ecx, ecx; int
0x18003ef44  call    ?GiveInstallHints@@YAHH@Z; GiveInstallHints(int)
0x18003ef49  test    eax, eax
0x18003ef4b  jnz     short loc_18003EF1B
0x18003ef4d  jmp     short loc_18003EF7E
0x18003ef4f  test    ebx, ebx
0x18003ef51  jnz     short loc_18003EF61
0x18003ef53  mov     rcx, [rbp+EventHandle]; Handle
0x18003ef57  call    cs:__imp_NtClose
0x18003ef5d  mov     al, 1
0x18003ef5f  jmp     short loc_18003EF8A
0x18003ef61  call    cs:__imp_GetLastError
0x18003ef67  mov     r9d, ebx
0x18003ef6a  lea     rdx, aNlwaitforsamse; "NlWaitForSamService: error %ld %ld\n"
0x18003ef71  mov     r8d, eax
0x18003ef74  mov     ecx, 100h; unsigned int
0x18003ef79  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ef7e  mov     rcx, [rbp+EventHandle]; Handle
0x18003ef82  call    cs:__imp_NtClose
0x18003ef88  xor     al, al
0x18003ef8a  mov     rbx, [rsp+70h+arg_0]
0x18003ef92  add     rsp, 70h
0x18003ef96  pop     rbp
0x18003ef97  retn
```
