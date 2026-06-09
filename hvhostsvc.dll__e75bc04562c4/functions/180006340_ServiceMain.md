# ServiceMain

- ea: `0x180006340`
- end: `0x18000641b`
- name: `ServiceMain`
- size: `219`
- prototype: `void()`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x180004928`
- `0x1800049e0`
- `0x180004a80`
- `0x180006340`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800063c2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800063c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006387`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006387`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180006357`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180006357`

## pseudocode

```c
void ServiceMain()
{
  DWORD LastError; // eax
  unsigned int v1; // ebx
  unsigned int v2; // ecx

  hServiceStatus = RegisterServiceCtrlHandlerExW(ServiceName, HvHostControlHandler, 0);
  if ( !hServiceStatus )
    goto LABEL_2;
  HvHostSetStatus(2u, 0);
  if ( !(unsigned int)HvHostInitializeService() )
  {
    if ( !GetLastError() )
    {
LABEL_5:
      v1 = 31;
      goto LABEL_6;
    }
    goto LABEL_2;
  }
  if ( !g_SvcHostGlobals )
    goto LABEL_5;
  g_ServiceStopEvent = CreateEventW(0, 0, 0, 0);
  if ( !g_ServiceStopEvent )
  {
LABEL_2:
    LastError = GetLastError();
    goto LABEL_11;
  }
  LastError = (*((__int64 (__fastcall **)(HANDLE *, WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))g_SvcHostGlobals
               + 24))(
                &g_SvcHostStopWaitHandle,
                ServiceName,
                g_ServiceStopEvent,
                HvHostStopCallback,
                0,
                24);
LABEL_11:
  v1 = LastError;
  if ( !LastError )
  {
    v2 = 4;
    goto LABEL_7;
  }
LABEL_6:
  HvHostTeardownService(0);
  v2 = 1;
LABEL_7:
  HvHostSetStatus(v2, v1);
}

```

## disassembly

```asm
0x180006340  push    rbx
0x180006342  sub     rsp, 40h
0x180006346  xor     r8d, r8d; lpContext
0x180006349  lea     rdx, ?HvHostControlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x180006350  lea     rcx, ServiceName; "hvhost"
0x180006357  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000635d  mov     cs:hServiceStatus, rax
0x180006364  test    rax, rax
0x180006367  jnz     short loc_180006374
0x180006369  call    cs:__imp_GetLastError
0x18000636f  jmp     loc_180006410
0x180006374  xor     edx, edx; unsigned int
0x180006376  lea     ecx, [rdx+2]; unsigned int
0x180006379  call    ?HvHostSetStatus@@YAXKK@Z; HvHostSetStatus(ulong,ulong)
0x18000637e  call    ?HvHostInitializeService@@YAHXZ; HvHostInitializeService(void)
0x180006383  test    eax, eax
0x180006385  jnz     short loc_1800063AE
0x180006387  call    cs:__imp_GetLastError
0x18000638d  test    eax, eax
0x18000638f  jnz     short loc_180006369
0x180006391  mov     ebx, 1Fh
0x180006396  xor     ecx, ecx; unsigned __int8
0x180006398  call    ?HvHostTeardownService@@YAXE@Z; HvHostTeardownService(uchar)
0x18000639d  mov     ecx, 1; unsigned int
0x1800063a2  mov     edx, ebx; unsigned int
0x1800063a4  add     rsp, 40h
0x1800063a8  pop     rbx
0x1800063a9  jmp     ?HvHostSetStatus@@YAXKK@Z; HvHostSetStatus(ulong,ulong)
0x1800063ae  cmp     cs:?g_SvcHostGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, 0; _SVCHOST_GLOBAL_DATA * g_SvcHostGlobals
0x1800063b6  jz      short loc_180006391
0x1800063b8  xor     r9d, r9d; lpName
0x1800063bb  xor     r8d, r8d; bInitialState
0x1800063be  xor     edx, edx; bManualReset
0x1800063c0  xor     ecx, ecx; lpEventAttributes
0x1800063c2  call    cs:__imp_CreateEventW
0x1800063c8  mov     cs:?g_ServiceStopEvent@@3PEAXEA, rax; void * g_ServiceStopEvent
0x1800063cf  mov     r8, rax
0x1800063d2  test    rax, rax
0x1800063d5  jz      short loc_180006369
0x1800063d7  mov     rax, cs:?g_SvcHostGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_SvcHostGlobals
0x1800063de  lea     r9, ?HvHostStopCallback@@YAXPEAXE@Z; HvHostStopCallback(void *,uchar)
0x1800063e5  mov     [rsp+48h+var_20], 18h
0x1800063ed  lea     rdx, ServiceName; "hvhost"
0x1800063f4  lea     rcx, ?g_SvcHostStopWaitHandle@@3PEAXEA; void * g_SvcHostStopWaitHandle
0x1800063fb  mov     [rsp+48h+var_28], 0
0x180006404  mov     rax, [rax+0C0h]
0x18000640b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006410  mov     ebx, eax
0x180006412  test    eax, eax
0x180006414  jnz     short loc_180006396
0x180006416  lea     ecx, [rax+4]
0x180006419  jmp     short loc_1800063A2
```
