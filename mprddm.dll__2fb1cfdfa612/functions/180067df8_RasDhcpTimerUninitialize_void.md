# RasDhcpTimerUninitialize(void)

- ea: `0x180067df8`
- end: `0x180067e7b`
- name: `?RasDhcpTimerUninitialize@@YAXXZ`
- size: `131`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18005e578`
- `0x18005e838`

## callees

- `0x180067df8`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180067e1f`
- `KERNEL32!SetEvent` at `0x180067e1f`
- `KERNEL32!SetEvent` at `0x180067e74`
- `KERNEL32!CloseHandle` at `0x180067e4d`
- `KERNEL32!CloseHandle` at `0x180067e4d`
- `KERNEL32!WaitForSingleObject` at `0x180067e06`
- `KERNEL32!WaitForSingleObject` at `0x180067e06`
- `ntdll!RtlDeleteTimerQueueEx` at `0x180067e30`
- `ntdll!RtlDeleteTimerQueueEx` at `0x180067e30`

## pseudocode

```c
void RasDhcpTimerUninitialize(void)
{
  WaitForSingleObject(EventDhcpTimerUninitializing, 0xFFFFFFFF);
  if ( _InterlockedExchange(&IsDhcpTimerQueueActive, 0) )
  {
    SetEvent(RasDhcpTimerShutdown);
    RtlDeleteTimerQueueEx(RasDhcpTimerQueueHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    RasDhcpTimerQueueHandle = 0;
    if ( RasDhcpTimerShutdown )
    {
      CloseHandle(RasDhcpTimerShutdown);
      RasDhcpTimerShutdown = 0;
    }
    RasDhcpTimerListHead = 0;
  }
  SetEvent(EventDhcpTimerUninitializing);
}

```

## disassembly

```asm
0x180067df8  sub     rsp, 28h
0x180067dfc  mov     rcx, cs:?EventDhcpTimerUninitializing@@3PEAXEA; hHandle
0x180067e03  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180067e06  call    cs:__imp_WaitForSingleObject
0x180067e0c  xor     eax, eax
0x180067e0e  xchg    eax, cs:?IsDhcpTimerQueueActive@@3JA; long IsDhcpTimerQueueActive
0x180067e14  test    eax, eax
0x180067e16  jz      short loc_180067E69
0x180067e18  mov     rcx, cs:?RasDhcpTimerShutdown@@3PEAXEA; hEvent
0x180067e1f  call    cs:__imp_SetEvent
0x180067e25  mov     rcx, cs:?RasDhcpTimerQueueHandle@@3PEAXEA; TimerQueue
0x180067e2c  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180067e30  call    cs:__imp_RtlDeleteTimerQueueEx
0x180067e36  mov     rcx, cs:?RasDhcpTimerShutdown@@3PEAXEA; hObject
0x180067e3d  mov     cs:?RasDhcpTimerQueueHandle@@3PEAXEA, 0; void * RasDhcpTimerQueueHandle
0x180067e48  test    rcx, rcx
0x180067e4b  jz      short loc_180067E5E
0x180067e4d  call    cs:__imp_CloseHandle
0x180067e53  mov     cs:?RasDhcpTimerShutdown@@3PEAXEA, 0; void * RasDhcpTimerShutdown
0x180067e5e  mov     cs:?RasDhcpTimerListHead@@3PEAU_TimerList@@EA, 0; _TimerList * RasDhcpTimerListHead
0x180067e69  mov     rcx, cs:?EventDhcpTimerUninitializing@@3PEAXEA; void * EventDhcpTimerUninitializing
0x180067e70  add     rsp, 28h
0x180067e74  jmp     cs:__imp_SetEvent
```
