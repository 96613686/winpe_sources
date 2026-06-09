# NotifyDaEnabled

- ea: `0x180033788`
- end: `0x1800338de`
- name: `NotifyDaEnabled`
- size: `342`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800036d0`
- `0x18003f220`

## callees

- `0x18000d7b0`
- `0x180033788`
- `0x1800338e4`
- `0x180042edc`
- `0x18004de54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800337ab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800337ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800337c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003383c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800338a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800337c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003383c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800338a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180033817`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180033817`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180033857`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180033857`
- `ext-ms-win-gpapi-grouppolicy-l1-1-0!RegisterGPNotificationInternalWorker` at `0x180033892`
- `ext-ms-win-gpapi-grouppolicy-l1-1-0!RegisterGPNotificationInternalWorker` at `0x180033892`

## string_xrefs

- `0x1800337d2`: `NotifyDaEnabled: Failed to create event (0x%x)`

## pseudocode

```c
__int64 NotifyDaEnabled()
{
  HANDLE v0; // rbx
  DWORD LastError; // eax
  const wchar_t *v2; // rdx
  unsigned int v3; // ebx
  __int64 v4; // rcx
  struct _TP_WAIT *ThreadpoolWait; // rax

  v0 = DaEnabledEvent;
  DaEnabledWaitCanceled = 0;
  if ( !DaEnabledEvent )
  {
    DaEnabledEvent = CreateEventW(0, 0, 0, 0);
    v0 = DaEnabledEvent;
    if ( !DaEnabledEvent )
    {
      LastError = GetLastError();
      v2 = L"NotifyDaEnabled: Failed to create event (0x%x)";
LABEL_4:
      v3 = LastError;
      EventWrite0(0x10000000, v2, LastError);
LABEL_5:
      LOBYTE(v4) = 1;
      StopDaEnabledNotification(v4);
      return v3;
    }
  }
  if ( DaEnabledWait )
  {
    SetThreadpoolWait(DaEnabledWait, v0, 0);
    EventWrite0(0x10000000, L"Re-arming existing DA-enabled waiter...");
  }
  else
  {
    ThreadpoolWait = CreateThreadpoolWait(IpTlsDaRegistryChangeListener, &DaEnabledWaitCanceled, &CallbackEnvironment);
    DaEnabledWait = ThreadpoolWait;
    if ( !ThreadpoolWait )
    {
      LastError = GetLastError();
      v2 = L"NotifyDaEnabled: Failed to register wait (0x%x)";
      goto LABEL_4;
    }
    TpclSetThreadpoolWait(ThreadpoolWait, v0);
  }
  if ( !GpNotificationArmed )
  {
    if ( !(unsigned __int8)IsRegisterGPNotificationInternalWorkerPresent() )
    {
      v3 = 127;
      EventWrite0(0x10000000, L"NotifyDaEnabledRegisterGPNotification is not present on this system! (0x%x)", 127);
      goto LABEL_5;
    }
    if ( !(unsigned int)RegisterGPNotificationInternalWorker(DaEnabledEvent, 1) )
    {
      LastError = GetLastError();
      v2 = L"NotifyDaEnabledFailed to register for GP notifications: 0x%x";
      goto LABEL_4;
    }
    GpNotificationArmed = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180033788  push    rbx
0x18003378a  sub     rsp, 20h
0x18003378e  mov     rbx, cs:DaEnabledEvent
0x180033795  mov     cs:DaEnabledWaitCanceled, 0
0x18003379c  test    rbx, rbx
0x18003379f  jnz     short loc_1800337F6
0x1800337a1  xor     r9d, r9d; lpName
0x1800337a4  xor     r8d, r8d; bInitialState
0x1800337a7  xor     edx, edx; bManualReset
0x1800337a9  xor     ecx, ecx; lpEventAttributes
0x1800337ab  call    cs:__imp_CreateEventW
0x1800337b2  nop     dword ptr [rax+rax+00h]
0x1800337b7  mov     cs:DaEnabledEvent, rax
0x1800337be  mov     rbx, rax
0x1800337c1  test    rax, rax
0x1800337c4  jnz     short loc_1800337F6
0x1800337c6  call    cs:__imp_GetLastError
0x1800337cd  nop     dword ptr [rax+rax+00h]
0x1800337d2  lea     rdx, aNotifydaenable_2; "NotifyDaEnabled: Failed to create event"...
0x1800337d9  mov     ebx, eax
0x1800337db  mov     r8d, eax
0x1800337de  mov     ecx, 10000000h
0x1800337e3  call    EventWrite0
0x1800337e8  mov     cl, 1
0x1800337ea  call    StopDaEnabledNotification
0x1800337ef  mov     eax, ebx
0x1800337f1  jmp     loc_1800338C3
0x1800337f6  mov     rcx, cs:DaEnabledWait; pwa
0x1800337fd  test    rcx, rcx
0x180033800  jnz     short loc_180033851
0x180033802  lea     r8, CallbackEnvironment; pcbe
0x180033809  lea     rdx, DaEnabledWaitCanceled; pv
0x180033810  lea     rcx, IpTlsDaRegistryChangeListener; pfnwa
0x180033817  call    cs:__imp_CreateThreadpoolWait
0x18003381e  nop     dword ptr [rax+rax+00h]
0x180033823  mov     cs:DaEnabledWait, rax
0x18003382a  test    rax, rax
0x18003382d  jz      short loc_18003383C
0x18003382f  mov     rdx, rbx
0x180033832  mov     rcx, rax
0x180033835  call    TpclSetThreadpoolWait
0x18003383a  jmp     short loc_180033874
0x18003383c  call    cs:__imp_GetLastError
0x180033843  nop     dword ptr [rax+rax+00h]
0x180033848  lea     rdx, aNotifydaenable; "NotifyDaEnabled: Failed to register wai"...
0x18003384f  jmp     short loc_1800337D9
0x180033851  xor     r8d, r8d; pftTimeout
0x180033854  mov     rdx, rbx; h
0x180033857  call    cs:__imp_SetThreadpoolWait
0x18003385e  nop     dword ptr [rax+rax+00h]
0x180033863  lea     rdx, aReArmingExisti; "Re-arming existing DA-enabled waiter..."
0x18003386a  mov     ecx, 10000000h
0x18003386f  call    EventWrite0
0x180033874  cmp     cs:GpNotificationArmed, 0
0x18003387b  jnz     short loc_1800338C1
0x18003387d  call    IsRegisterGPNotificationInternalWorkerPresent
0x180033882  test    al, al
0x180033884  jz      short loc_1800338CA
0x180033886  mov     rcx, cs:DaEnabledEvent
0x18003388d  mov     edx, 1
0x180033892  call    cs:__imp_RegisterGPNotificationInternalWorker
0x180033899  nop     dword ptr [rax+rax+00h]
0x18003389e  test    eax, eax
0x1800338a0  jnz     short loc_1800338BA
0x1800338a2  call    cs:__imp_GetLastError
0x1800338a9  nop     dword ptr [rax+rax+00h]
0x1800338ae  lea     rdx, aNotifydaenable_1; "NotifyDaEnabledFailed to register for G"...
0x1800338b5  jmp     loc_1800337D9
0x1800338ba  mov     cs:GpNotificationArmed, 1
0x1800338c1  xor     eax, eax
0x1800338c3  add     rsp, 20h
0x1800338c7  pop     rbx
0x1800338c8  retn
0x1800338ca  mov     ebx, 7Fh
0x1800338cf  lea     rdx, aNotifydaenable_0; "NotifyDaEnabledRegisterGPNotification i"...
0x1800338d6  mov     r8d, ebx
0x1800338d9  jmp     loc_1800337DE
```
