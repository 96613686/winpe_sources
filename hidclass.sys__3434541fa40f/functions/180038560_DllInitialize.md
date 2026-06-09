# DllInitialize

- ea: `0x180038560`
- end: `0x1800385d7`
- name: `DllInitialize`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180045044`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1800385a8`
- `ntoskrnl!KeInitializeEvent` at `0x1800385a8`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800385c3`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800385c3`

## pseudocode

```c
__int64 DllInitialize()
{
  _security_init_cookie();
  WPP_MAIN_CB.Queue.Wcb.DeviceRoutine = 0;
  WPP_MAIN_CB.Queue.ListEntry.Blink = &WPP_MAIN_CB.Queue.ListEntry;
  WPP_MAIN_CB.Queue.ListEntry.Flink = &WPP_MAIN_CB.Queue.ListEntry;
  WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.SortKey = 1;
  LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) = 0;
  KeInitializeEvent((PRKEVENT)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters, SynchronizationEvent, 0);
  _InterlockedExchange(&g_HidId, 0);
  KeInitializeSpinLock(&allFdoExtensionsSpinLock);
  return 0;
}

```

## disassembly

```asm
0x180038560  sub     rsp, 28h
0x180038564  call    __security_init_cookie
0x180038569  lea     rax, WPP_MAIN_CB.Queue
0x180038570  mov     qword ptr cs:WPP_MAIN_CB.Queue+18h, 0
0x18003857b  mov     edx, 1; Type
0x180038580  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x180038587  xor     r8d, r8d; State
0x18003858a  mov     qword ptr cs:WPP_MAIN_CB.Queue, rax
0x180038591  lea     rcx, WPP_MAIN_CB.Queue+28h; Event
0x180038598  mov     dword ptr cs:WPP_MAIN_CB.Queue+10h, edx
0x18003859e  mov     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x1800385a8  call    cs:__imp_KeInitializeEvent
0x1800385af  nop     dword ptr [rax+rax+00h]
0x1800385b4  xor     eax, eax
0x1800385b6  lea     rcx, allFdoExtensionsSpinLock; SpinLock
0x1800385bd  xchg    eax, cs:g_HidId
0x1800385c3  call    cs:__imp_KeInitializeSpinLock
0x1800385ca  nop     dword ptr [rax+rax+00h]
0x1800385cf  xor     eax, eax
0x1800385d1  add     rsp, 28h
0x1800385d5  retn
```
