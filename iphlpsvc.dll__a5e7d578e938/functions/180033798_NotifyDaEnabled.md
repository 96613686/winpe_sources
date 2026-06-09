# NotifyDaEnabled

- ea: `0x180033798`
- end: `0x1800338ee`
- name: `NotifyDaEnabled`
- size: `342`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800036e0`
- `0x18003f1e0`

## callees

- `0x18000d7c0`
- `0x180033798`
- `0x1800338f4`
- `0x180042e9c`
- `0x18004de14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800337bb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800337bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800337d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003384c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800338b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800337d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003384c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800338b2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180033827`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180033827`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180033867`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180033867`
- `ext-ms-win-gpapi-grouppolicy-l1-1-0!RegisterGPNotificationInternalWorker` at `0x1800338a2`
- `ext-ms-win-gpapi-grouppolicy-l1-1-0!RegisterGPNotificationInternalWorker` at `0x1800338a2`

## string_xrefs

- `0x1800337e2`: `NotifyDaEnabled: Failed to create event (0x%x)`

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
0x180033798  push    rbx
0x18003379a  sub     rsp, 20h
0x18003379e  mov     rbx, cs:DaEnabledEvent
0x1800337a5  mov     cs:DaEnabledWaitCanceled, 0
0x1800337ac  test    rbx, rbx
0x1800337af  jnz     short loc_180033806
0x1800337b1  xor     r9d, r9d; lpName
0x1800337b4  xor     r8d, r8d; bInitialState
0x1800337b7  xor     edx, edx; bManualReset
0x1800337b9  xor     ecx, ecx; lpEventAttributes
0x1800337bb  call    cs:__imp_CreateEventW
0x1800337c2  nop     dword ptr [rax+rax+00h]
0x1800337c7  mov     cs:DaEnabledEvent, rax
0x1800337ce  mov     rbx, rax
0x1800337d1  test    rax, rax
0x1800337d4  jnz     short loc_180033806
0x1800337d6  call    cs:__imp_GetLastError
0x1800337dd  nop     dword ptr [rax+rax+00h]
0x1800337e2  lea     rdx, aNotifydaenable_2; "NotifyDaEnabled: Failed to create event"...
0x1800337e9  mov     ebx, eax
0x1800337eb  mov     r8d, eax
0x1800337ee  mov     ecx, 10000000h
0x1800337f3  call    EventWrite0
0x1800337f8  mov     cl, 1
0x1800337fa  call    StopDaEnabledNotification
0x1800337ff  mov     eax, ebx
0x180033801  jmp     loc_1800338D3
0x180033806  mov     rcx, cs:DaEnabledWait; pwa
0x18003380d  test    rcx, rcx
0x180033810  jnz     short loc_180033861
0x180033812  lea     r8, CallbackEnvironment; pcbe
0x180033819  lea     rdx, DaEnabledWaitCanceled; pv
0x180033820  lea     rcx, IpTlsDaRegistryChangeListener; pfnwa
0x180033827  call    cs:__imp_CreateThreadpoolWait
0x18003382e  nop     dword ptr [rax+rax+00h]
0x180033833  mov     cs:DaEnabledWait, rax
0x18003383a  test    rax, rax
0x18003383d  jz      short loc_18003384C
0x18003383f  mov     rdx, rbx
0x180033842  mov     rcx, rax
0x180033845  call    TpclSetThreadpoolWait
0x18003384a  jmp     short loc_180033884
0x18003384c  call    cs:__imp_GetLastError
0x180033853  nop     dword ptr [rax+rax+00h]
0x180033858  lea     rdx, aNotifydaenable; "NotifyDaEnabled: Failed to register wai"...
0x18003385f  jmp     short loc_1800337E9
0x180033861  xor     r8d, r8d; pftTimeout
0x180033864  mov     rdx, rbx; h
0x180033867  call    cs:__imp_SetThreadpoolWait
0x18003386e  nop     dword ptr [rax+rax+00h]
0x180033873  lea     rdx, aReArmingExisti; "Re-arming existing DA-enabled waiter..."
0x18003387a  mov     ecx, 10000000h
0x18003387f  call    EventWrite0
0x180033884  cmp     cs:GpNotificationArmed, 0
0x18003388b  jnz     short loc_1800338D1
0x18003388d  call    IsRegisterGPNotificationInternalWorkerPresent
0x180033892  test    al, al
0x180033894  jz      short loc_1800338DA
0x180033896  mov     rcx, cs:DaEnabledEvent
0x18003389d  mov     edx, 1
0x1800338a2  call    cs:__imp_RegisterGPNotificationInternalWorker
0x1800338a9  nop     dword ptr [rax+rax+00h]
0x1800338ae  test    eax, eax
0x1800338b0  jnz     short loc_1800338CA
0x1800338b2  call    cs:__imp_GetLastError
0x1800338b9  nop     dword ptr [rax+rax+00h]
0x1800338be  lea     rdx, aNotifydaenable_1; "NotifyDaEnabledFailed to register for G"...
0x1800338c5  jmp     loc_1800337E9
0x1800338ca  mov     cs:GpNotificationArmed, 1
0x1800338d1  xor     eax, eax
0x1800338d3  add     rsp, 20h
0x1800338d7  pop     rbx
0x1800338d8  retn
0x1800338da  mov     ebx, 7Fh
0x1800338df  lea     rdx, aNotifydaenable_0; "NotifyDaEnabledRegisterGPNotification i"...
0x1800338e6  mov     r8d, ebx
0x1800338e9  jmp     loc_1800337EE
```
