# NlWaitForSamService(uchar)

- ea: `0x1800416f4`
- end: `0x180041874`
- name: `?NlWaitForSamService@@YAEE@Z`
- size: `384`
- prototype: `unsigned __int8 __fastcall(unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800747cc`

## callees

- `0x180007518`
- `0x180029c68`
- `0x1800416f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800417e7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800417e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041830`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041830`
- `ntdll!NtClose` at `0x180041820`
- `ntdll!NtClose` at `0x180041857`
- `ntdll!NtClose` at `0x180041820`
- `ntdll!NtClose` at `0x180041857`
- `ntdll!NtOpenEvent` at `0x180041768`
- `ntdll!NtOpenEvent` at `0x1800417b5`
- `ntdll!NtOpenEvent` at `0x180041768`
- `ntdll!NtOpenEvent` at `0x1800417b5`
- `ntdll!RtlInitUnicodeString` at `0x180041727`
- `ntdll!RtlInitUnicodeString` at `0x180041727`
- `ntdll!NtCreateEvent` at `0x180041791`
- `ntdll!NtCreateEvent` at `0x180041791`

## string_xrefs

- `0x18004170c`: `\SAM_SERVICE_STARTED`
- `0x1800417c8`: `NlWaitForSamService couldn't make the event handle : %lx\n`
- `0x1800417fc`: `NlWaitForSamService 5-second timeout (Rewaiting)\n`
- `0x18004183f`: `NlWaitForSamService: error %ld %ld\n`

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
0x1800416f4  mov     [rsp-8+arg_0], rbx
0x1800416f9  push    rbp
0x1800416fa  mov     rbp, rsp
0x1800416fd  sub     rsp, 70h
0x180041701  xorps   xmm0, xmm0
0x180041704  mov     [rbp+EventHandle], 0
0x18004170c  lea     rdx, aSamServiceStar; "\\SAM_SERVICE_STARTED"
0x180041713  lea     rcx, [rbp+DestinationString]; DestinationString
0x180041717  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004171b  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18004171f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180041723  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180041727  call    cs:__imp_RtlInitUnicodeString
0x18004172e  nop     dword ptr [rax+rax+00h]
0x180041733  lea     rax, [rbp+DestinationString]
0x180041737  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18004173e  xorps   xmm0, xmm0
0x180041741  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180041745  mov     ebx, 100002h
0x18004174a  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180041752  mov     edx, ebx; DesiredAccess
0x180041754  mov     [rbp+ObjectAttributes.Attributes], 0
0x18004175b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18004175f  lea     rcx, [rbp+EventHandle]; EventHandle
0x180041763  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180041768  call    cs:__imp_NtOpenEvent
0x18004176f  nop     dword ptr [rax+rax+00h]
0x180041774  test    eax, eax
0x180041776  jns     short loc_1800417DE
0x180041778  cmp     eax, 0C0000034h
0x18004177d  jnz     short loc_1800417C5
0x18004177f  xor     r9d, r9d; EventType
0x180041782  mov     [rsp+70h+InitialState], 0; InitialState
0x180041787  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18004178b  mov     edx, ebx; DesiredAccess
0x18004178d  lea     rcx, [rbp+EventHandle]; EventHandle
0x180041791  call    cs:__imp_NtCreateEvent
0x180041798  nop     dword ptr [rax+rax+00h]
0x18004179d  cmp     eax, 40000000h
0x1800417a2  jz      short loc_1800417AB
0x1800417a4  cmp     eax, 0C0000035h
0x1800417a9  jnz     short loc_1800417C1
0x1800417ab  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800417af  mov     edx, ebx; DesiredAccess
0x1800417b1  lea     rcx, [rbp+EventHandle]; EventHandle
0x1800417b5  call    cs:__imp_NtOpenEvent
0x1800417bc  nop     dword ptr [rax+rax+00h]
0x1800417c1  test    eax, eax
0x1800417c3  jns     short loc_1800417DE
0x1800417c5  mov     r8d, eax
0x1800417c8  lea     rdx, aNlwaitforsamse_0; "NlWaitForSamService couldn't make the e"...
0x1800417cf  mov     ecx, 100h; unsigned int
0x1800417d4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800417d9  jmp     loc_180041863
0x1800417de  mov     rcx, [rbp+EventHandle]; hHandle
0x1800417e2  mov     edx, 1388h; dwMilliseconds
0x1800417e7  call    cs:__imp_WaitForSingleObject
0x1800417ee  nop     dword ptr [rax+rax+00h]
0x1800417f3  mov     ebx, eax
0x1800417f5  cmp     eax, 102h
0x1800417fa  jnz     short loc_180041818
0x1800417fc  lea     rdx, aNlwaitforsamse_1; "NlWaitForSamService 5-second timeout (R"...
0x180041803  lea     ecx, [rax-2]; unsigned int
0x180041806  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004180b  xor     ecx, ecx; int
0x18004180d  call    ?GiveInstallHints@@YAHH@Z; GiveInstallHints(int)
0x180041812  test    eax, eax
0x180041814  jnz     short loc_1800417DE
0x180041816  jmp     short loc_180041853
0x180041818  test    ebx, ebx
0x18004181a  jnz     short loc_180041830
0x18004181c  mov     rcx, [rbp+EventHandle]; Handle
0x180041820  call    cs:__imp_NtClose
0x180041827  nop     dword ptr [rax+rax+00h]
0x18004182c  mov     al, 1
0x18004182e  jmp     short loc_180041865
0x180041830  call    cs:__imp_GetLastError
0x180041837  nop     dword ptr [rax+rax+00h]
0x18004183c  mov     r9d, ebx
0x18004183f  lea     rdx, aNlwaitforsamse; "NlWaitForSamService: error %ld %ld\n"
0x180041846  mov     r8d, eax
0x180041849  mov     ecx, 100h; unsigned int
0x18004184e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180041853  mov     rcx, [rbp+EventHandle]; Handle
0x180041857  call    cs:__imp_NtClose
0x18004185e  nop     dword ptr [rax+rax+00h]
0x180041863  xor     al, al
0x180041865  mov     rbx, [rsp+70h+arg_0]
0x18004186d  add     rsp, 70h
0x180041871  pop     rbp
0x180041872  retn
```
