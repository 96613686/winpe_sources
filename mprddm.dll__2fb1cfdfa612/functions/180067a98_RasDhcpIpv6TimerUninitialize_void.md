# RasDhcpIpv6TimerUninitialize(void)

- ea: `0x180067a98`
- end: `0x180067b1b`
- name: `?RasDhcpIpv6TimerUninitialize@@YAXXZ`
- size: `131`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18005b254`
- `0x18005b360`

## callees

- `0x180067a98`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180067abf`
- `KERNEL32!SetEvent` at `0x180067abf`
- `KERNEL32!SetEvent` at `0x180067b14`
- `KERNEL32!CloseHandle` at `0x180067aed`
- `KERNEL32!CloseHandle` at `0x180067aed`
- `KERNEL32!WaitForSingleObject` at `0x180067aa6`
- `KERNEL32!WaitForSingleObject` at `0x180067aa6`
- `ntdll!RtlDeleteTimerQueueEx` at `0x180067ad0`
- `ntdll!RtlDeleteTimerQueueEx` at `0x180067ad0`

## pseudocode

```c
void RasDhcpIpv6TimerUninitialize(void)
{
  WaitForSingleObject(EventDhcpIpv6TimerUninitializing, 0xFFFFFFFF);
  if ( _InterlockedExchange(&IsDhcpIpv6TimerQueueActive, 0) )
  {
    SetEvent(RasDhcpIpv6TimerShutdown);
    RtlDeleteTimerQueueEx(RasDhcpIpv6TimerQueueHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    RasDhcpIpv6TimerQueueHandle = 0;
    if ( RasDhcpIpv6TimerShutdown )
    {
      CloseHandle(RasDhcpIpv6TimerShutdown);
      RasDhcpIpv6TimerShutdown = 0;
    }
    RasDhcpIpv6TimerListHead = 0;
  }
  SetEvent(EventDhcpIpv6TimerUninitializing);
}

```

## disassembly

```asm
0x180067a98  sub     rsp, 28h
0x180067a9c  mov     rcx, cs:?EventDhcpIpv6TimerUninitializing@@3PEAXEA; hHandle
0x180067aa3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180067aa6  call    cs:__imp_WaitForSingleObject
0x180067aac  xor     eax, eax
0x180067aae  xchg    eax, cs:?IsDhcpIpv6TimerQueueActive@@3JA; long IsDhcpIpv6TimerQueueActive
0x180067ab4  test    eax, eax
0x180067ab6  jz      short loc_180067B09
0x180067ab8  mov     rcx, cs:?RasDhcpIpv6TimerShutdown@@3PEAXEA; hEvent
0x180067abf  call    cs:__imp_SetEvent
0x180067ac5  mov     rcx, cs:?RasDhcpIpv6TimerQueueHandle@@3PEAXEA; TimerQueue
0x180067acc  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180067ad0  call    cs:__imp_RtlDeleteTimerQueueEx
0x180067ad6  mov     rcx, cs:?RasDhcpIpv6TimerShutdown@@3PEAXEA; hObject
0x180067add  mov     cs:?RasDhcpIpv6TimerQueueHandle@@3PEAXEA, 0; void * RasDhcpIpv6TimerQueueHandle
0x180067ae8  test    rcx, rcx
0x180067aeb  jz      short loc_180067AFE
0x180067aed  call    cs:__imp_CloseHandle
0x180067af3  mov     cs:?RasDhcpIpv6TimerShutdown@@3PEAXEA, 0; void * RasDhcpIpv6TimerShutdown
0x180067afe  mov     cs:?RasDhcpIpv6TimerListHead@@3PEAU_TimerList@@EA, 0; _TimerList * RasDhcpIpv6TimerListHead
0x180067b09  mov     rcx, cs:?EventDhcpIpv6TimerUninitializing@@3PEAXEA; void * EventDhcpIpv6TimerUninitializing
0x180067b10  add     rsp, 28h
0x180067b14  jmp     cs:__imp_SetEvent
```
