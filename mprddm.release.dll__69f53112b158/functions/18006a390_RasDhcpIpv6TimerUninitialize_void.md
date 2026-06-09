# RasDhcpIpv6TimerUninitialize(void)

- ea: `0x18006a390`
- end: `0x18006a427`
- name: `?RasDhcpIpv6TimerUninitialize@@YAXXZ`
- size: `151`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18005d378`
- `0x18005d498`

## callees

- `0x18006a390`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18006a3bd`
- `KERNEL32!SetEvent` at `0x18006a3bd`
- `KERNEL32!SetEvent` at `0x18006a41b`
- `KERNEL32!CloseHandle` at `0x18006a3f4`
- `KERNEL32!CloseHandle` at `0x18006a3f4`
- `KERNEL32!WaitForSingleObject` at `0x18006a39e`
- `KERNEL32!WaitForSingleObject` at `0x18006a39e`
- `ntdll!RtlDeleteTimerQueueEx` at `0x18006a3d4`
- `ntdll!RtlDeleteTimerQueueEx` at `0x18006a3d4`

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
0x18006a390  sub     rsp, 28h
0x18006a394  mov     rcx, cs:?EventDhcpIpv6TimerUninitializing@@3PEAXEA; hHandle
0x18006a39b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18006a39e  call    cs:__imp_WaitForSingleObject
0x18006a3a5  nop     dword ptr [rax+rax+00h]
0x18006a3aa  xor     eax, eax
0x18006a3ac  xchg    eax, cs:?IsDhcpIpv6TimerQueueActive@@3JA; long IsDhcpIpv6TimerQueueActive
0x18006a3b2  test    eax, eax
0x18006a3b4  jz      short loc_18006A410
0x18006a3b6  mov     rcx, cs:?RasDhcpIpv6TimerShutdown@@3PEAXEA; hEvent
0x18006a3bd  call    cs:__imp_SetEvent
0x18006a3c4  nop     dword ptr [rax+rax+00h]
0x18006a3c9  mov     rcx, cs:?RasDhcpIpv6TimerQueueHandle@@3PEAXEA; TimerQueue
0x18006a3d0  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18006a3d4  call    cs:__imp_RtlDeleteTimerQueueEx
0x18006a3db  nop     dword ptr [rax+rax+00h]
0x18006a3e0  mov     rcx, cs:?RasDhcpIpv6TimerShutdown@@3PEAXEA; hObject
0x18006a3e7  and     cs:?RasDhcpIpv6TimerQueueHandle@@3PEAXEA, 0; void * RasDhcpIpv6TimerQueueHandle
0x18006a3ef  test    rcx, rcx
0x18006a3f2  jz      short loc_18006A408
0x18006a3f4  call    cs:__imp_CloseHandle
0x18006a3fb  nop     dword ptr [rax+rax+00h]
0x18006a400  and     cs:?RasDhcpIpv6TimerShutdown@@3PEAXEA, 0; void * RasDhcpIpv6TimerShutdown
0x18006a408  and     cs:?RasDhcpIpv6TimerListHead@@3PEAU_TimerList@@EA, 0; _TimerList * RasDhcpIpv6TimerListHead
0x18006a410  mov     rcx, cs:?EventDhcpIpv6TimerUninitializing@@3PEAXEA; void * EventDhcpIpv6TimerUninitializing
0x18006a417  add     rsp, 28h
0x18006a41b  jmp     cs:__imp_SetEvent
```
