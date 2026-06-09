# IASDynamicInfoInitialize

- ea: `0x18002a088`
- end: `0x18002a1ac`
- name: `IASDynamicInfoInitialize`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800291bc`

## callees

- `0x18002a088`
- `0x18002a248`
- `0x18002a748`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002a118`
- `ntdll!RtlNtStatusToDosError` at `0x18002a118`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18002a0a2`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18002a0a2`
- `KERNEL32!CreateThread` at `0x18002a14e`
- `KERNEL32!CreateThread` at `0x18002a14e`
- `KERNEL32!CreateEventA` at `0x18002a0d0`
- `KERNEL32!CreateEventA` at `0x18002a0d0`
- `KERNEL32!GetLastError` at `0x18002a0ac`
- `KERNEL32!GetLastError` at `0x18002a0e2`
- `KERNEL32!GetLastError` at `0x18002a0ac`
- `KERNEL32!GetLastError` at `0x18002a0e2`
- `KERNEL32!DeleteCriticalSection` at `0x18002a181`
- `KERNEL32!DeleteCriticalSection` at `0x18002a181`
- `KERNEL32!CloseHandle` at `0x18002a105`
- `KERNEL32!CloseHandle` at `0x18002a105`
- `ADVAPI32!LsaFreeMemory` at `0x18002a193`
- `ADVAPI32!LsaFreeMemory` at `0x18002a193`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x18002a0f2`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x18002a0f2`

## pseudocode

```c
DWORD IASDynamicInfoInitialize()
{
  ULONG v1; // ebx
  HANDLE EventA; // rax
  ULONG LastError; // eax
  int v4; // ebx
  ULONG v5; // eax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  ThreadId = 0;
  if ( !InitializeCriticalSectionAndSpinCount(&critSec, 0x1000u) )
    return GetLastError();
  v1 = IASQueryPrimaryDomain();
  if ( v1 )
    goto LABEL_12;
  EventA = CreateEventA(0, 0, 0, 0);
  theChangeEvent = EventA;
  if ( EventA )
  {
    v4 = LsaRegisterPolicyChangeNotification(PolicyNotifyDnsDomainInformation, EventA);
    if ( v4 >= 0 )
      goto LABEL_9;
    CloseHandle(theChangeEvent);
    theChangeEvent = 0;
    LastError = RtlNtStatusToDosError(v4);
  }
  else
  {
    LastError = GetLastError();
  }
  v1 = LastError;
  if ( LastError )
    goto LABEL_12;
LABEL_9:
  theShutdownFlag = 0;
  theNotificationThread = CreateThread(0, 0, NotificationProc, 0, 0, &ThreadId);
  if ( !theNotificationThread )
  {
    v5 = IASUnregisterDomainNameChangeNotification();
    theChangeEvent = 0;
    v1 = v5;
    if ( !v5 )
      return v1;
LABEL_12:
    DeleteCriticalSection(&critSec);
    if ( ppdi )
    {
      LsaFreeMemory(ppdi);
      ppdi = 0;
    }
    return v1;
  }
  return 0;
}

```

## disassembly

```asm
0x18002a088  push    rbx
0x18002a08a  sub     rsp, 30h
0x18002a08e  mov     edx, 1000h; dwSpinCount
0x18002a093  mov     [rsp+38h+ThreadId], 0
0x18002a09b  lea     rcx, critSec; lpCriticalSection
0x18002a0a2  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18002a0a8  test    eax, eax
0x18002a0aa  jnz     short loc_18002A0B7
0x18002a0ac  call    cs:__imp_GetLastError
0x18002a0b2  jmp     loc_18002A1A6
0x18002a0b7  call    IASQueryPrimaryDomain
0x18002a0bc  mov     ebx, eax
0x18002a0be  test    eax, eax
0x18002a0c0  jnz     loc_18002A17A
0x18002a0c6  xor     r9d, r9d; lpName
0x18002a0c9  xor     r8d, r8d; bInitialState
0x18002a0cc  xor     edx, edx; bManualReset
0x18002a0ce  xor     ecx, ecx; lpEventAttributes
0x18002a0d0  call    cs:__imp_CreateEventA
0x18002a0d6  mov     cs:theChangeEvent, rax
0x18002a0dd  test    rax, rax
0x18002a0e0  jnz     short loc_18002A0EA
0x18002a0e2  call    cs:__imp_GetLastError
0x18002a0e8  jmp     short loc_18002A11E
0x18002a0ea  mov     rdx, rax; NotificationEventHandle
0x18002a0ed  mov     ecx, 4; InformationClass
0x18002a0f2  call    cs:__imp_LsaRegisterPolicyChangeNotification
0x18002a0f8  mov     ebx, eax
0x18002a0fa  test    eax, eax
0x18002a0fc  jns     short loc_18002A124
0x18002a0fe  mov     rcx, cs:theChangeEvent; hObject
0x18002a105  call    cs:__imp_CloseHandle
0x18002a10b  mov     ecx, ebx; Status
0x18002a10d  mov     cs:theChangeEvent, 0
0x18002a118  call    cs:__imp_RtlNtStatusToDosError
0x18002a11e  mov     ebx, eax
0x18002a120  test    eax, eax
0x18002a122  jnz     short loc_18002A17A
0x18002a124  lea     rax, [rsp+38h+ThreadId]
0x18002a129  mov     cs:theShutdownFlag, 0
0x18002a133  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18002a138  lea     r8, NotificationProc; lpStartAddress
0x18002a13f  xor     r9d, r9d; lpParameter
0x18002a142  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18002a14a  xor     edx, edx; dwStackSize
0x18002a14c  xor     ecx, ecx; lpThreadAttributes
0x18002a14e  call    cs:__imp_CreateThread
0x18002a154  mov     cs:theNotificationThread, rax
0x18002a15b  test    rax, rax
0x18002a15e  jz      short loc_18002A164
0x18002a160  xor     ebx, ebx
0x18002a162  jmp     short loc_18002A1A4
0x18002a164  call    IASUnregisterDomainNameChangeNotification
0x18002a169  mov     cs:theChangeEvent, 0
0x18002a174  mov     ebx, eax
0x18002a176  test    eax, eax
0x18002a178  jz      short loc_18002A1A4
0x18002a17a  lea     rcx, critSec; lpCriticalSection
0x18002a181  call    cs:__imp_DeleteCriticalSection
0x18002a187  mov     rcx, cs:ppdi; Buffer
0x18002a18e  test    rcx, rcx
0x18002a191  jz      short loc_18002A1A4
0x18002a193  call    cs:__imp_LsaFreeMemory
0x18002a199  mov     cs:ppdi, 0
0x18002a1a4  mov     eax, ebx
0x18002a1a6  add     rsp, 30h
0x18002a1aa  pop     rbx
0x18002a1ab  retn
```
