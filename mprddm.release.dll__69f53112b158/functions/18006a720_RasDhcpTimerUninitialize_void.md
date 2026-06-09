# RasDhcpTimerUninitialize(void)

- ea: `0x18006a720`
- end: `0x18006a7b7`
- name: `?RasDhcpTimerUninitialize@@YAXXZ`
- size: `151`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800609bc`
- `0x180060cac`

## callees

- `0x18006a720`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18006a74d`
- `KERNEL32!SetEvent` at `0x18006a74d`
- `KERNEL32!SetEvent` at `0x18006a7ab`
- `KERNEL32!CloseHandle` at `0x18006a784`
- `KERNEL32!CloseHandle` at `0x18006a784`
- `KERNEL32!WaitForSingleObject` at `0x18006a72e`
- `KERNEL32!WaitForSingleObject` at `0x18006a72e`
- `ntdll!RtlDeleteTimerQueueEx` at `0x18006a764`
- `ntdll!RtlDeleteTimerQueueEx` at `0x18006a764`

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
0x18006a720  sub     rsp, 28h
0x18006a724  mov     rcx, cs:?EventDhcpTimerUninitializing@@3PEAXEA; hHandle
0x18006a72b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18006a72e  call    cs:__imp_WaitForSingleObject
0x18006a735  nop     dword ptr [rax+rax+00h]
0x18006a73a  xor     eax, eax
0x18006a73c  xchg    eax, cs:?IsDhcpTimerQueueActive@@3JA; long IsDhcpTimerQueueActive
0x18006a742  test    eax, eax
0x18006a744  jz      short loc_18006A7A0
0x18006a746  mov     rcx, cs:?RasDhcpTimerShutdown@@3PEAXEA; hEvent
0x18006a74d  call    cs:__imp_SetEvent
0x18006a754  nop     dword ptr [rax+rax+00h]
0x18006a759  mov     rcx, cs:?RasDhcpTimerQueueHandle@@3PEAXEA; TimerQueue
0x18006a760  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18006a764  call    cs:__imp_RtlDeleteTimerQueueEx
0x18006a76b  nop     dword ptr [rax+rax+00h]
0x18006a770  mov     rcx, cs:?RasDhcpTimerShutdown@@3PEAXEA; hObject
0x18006a777  and     cs:?RasDhcpTimerQueueHandle@@3PEAXEA, 0; void * RasDhcpTimerQueueHandle
0x18006a77f  test    rcx, rcx
0x18006a782  jz      short loc_18006A798
0x18006a784  call    cs:__imp_CloseHandle
0x18006a78b  nop     dword ptr [rax+rax+00h]
0x18006a790  and     cs:?RasDhcpTimerShutdown@@3PEAXEA, 0; void * RasDhcpTimerShutdown
0x18006a798  and     cs:?RasDhcpTimerListHead@@3PEAU_TimerList@@EA, 0; _TimerList * RasDhcpTimerListHead
0x18006a7a0  mov     rcx, cs:?EventDhcpTimerUninitializing@@3PEAXEA; void * EventDhcpTimerUninitializing
0x18006a7a7  add     rsp, 28h
0x18006a7ab  jmp     cs:__imp_SetEvent
```
