# DsRoleStartServiceIdleCheckTimer

- ea: `0x18000a020`
- end: `0x18000a0a7`
- name: `DsRoleStartServiceIdleCheckTimer`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180009cf0`

## callees

- `0x18000a020`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a083`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a06c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a06c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a039`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a039`

## string_xrefs

- `0x18000a072`: `Created service idle timer callback\n`
- `0x18000a089`: `Failed to create service idle timer callback 0x%x\n`

## pseudocode

```c
__int64 DsRoleStartServiceIdleCheckTimer()
{
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp+10h] BYREF

  LastError = 0;
  pftDueTime = 0;
  ThreadpoolTimer = CreateThreadpoolTimer((PTP_TIMER_CALLBACK)DsRolepCheckServiceTimeout, 0, 0);
  DsRoleNotificationTimer = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    pftDueTime.dwHighDateTime = -17;
    pftDueTime.dwLowDateTime = 1014444032;
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0x6DDD00u, 0);
    DsRolepLogPrintRoutine(4, "Created service idle timer callback\n");
  }
  else
  {
    LastError = GetLastError();
    DsRolepLogPrintRoutine(4, "Failed to create service idle timer callback 0x%x\n", LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000a020  push    rbx
0x18000a022  sub     rsp, 20h
0x18000a026  xor     ebx, ebx
0x18000a028  lea     rcx, DsRolepCheckServiceTimeout; pfnti
0x18000a02f  xor     r8d, r8d; pcbe
0x18000a032  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rbx
0x18000a037  xor     edx, edx; pv
0x18000a039  call    cs:__imp_CreateThreadpoolTimer
0x18000a03f  mov     cs:DsRoleNotificationTimer, rax
0x18000a046  test    rax, rax
0x18000a049  jz      short loc_18000A083
0x18000a04b  xor     r9d, r9d; msWindowLength
0x18000a04e  mov     [rsp+28h+pftDueTime.dwHighDateTime], 0FFFFFFEFh
0x18000a056  mov     r8d, 6DDD00h; msPeriod
0x18000a05c  mov     [rsp+28h+pftDueTime.dwLowDateTime], 3C773000h
0x18000a064  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000a069  mov     rcx, rax; pti
0x18000a06c  call    cs:__imp_SetThreadpoolTimer
0x18000a072  lea     rdx, aCreatedService; "Created service idle timer callback\n"
0x18000a079  lea     ecx, [rbx+4]
0x18000a07c  call    DsRolepLogPrintRoutine
0x18000a081  jmp     short loc_18000A09F
0x18000a083  call    cs:__imp_GetLastError
0x18000a089  lea     rdx, aFailedToCreate_5; "Failed to create service idle timer cal"...
0x18000a090  mov     ecx, 4
0x18000a095  mov     r8d, eax
0x18000a098  mov     ebx, eax
0x18000a09a  call    DsRolepLogPrintRoutine
0x18000a09f  mov     eax, ebx
0x18000a0a1  add     rsp, 20h
0x18000a0a5  pop     rbx
0x18000a0a6  retn
```
