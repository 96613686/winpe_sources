# ServiceManager::CommonControlHandler(ulong,ulong,void *,void *)

- ea: `0x18000e200`
- end: `0x18000e213`
- name: `?CommonControlHandler@ServiceManager@@CAKKKPEAX0@Z`
- size: `19`
- prototype: `DWORD __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, ServiceManager *lpContext)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000e21c`

## pseudocode

```c
DWORD __fastcall ServiceManager::CommonControlHandler(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        ServiceManager *lpContext)
{
  return ServiceManager::ControlHandler(lpContext, dwControl, dwEventType, lpEventData);
}

```

## disassembly

```asm
0x18000e200  mov     rax, r9
0x18000e203  mov     r9, r8; void *
0x18000e206  mov     r8d, edx; unsigned int
0x18000e209  mov     edx, ecx; unsigned int
0x18000e20b  mov     rcx, rax; this
0x18000e20e  jmp     ?ControlHandler@ServiceManager@@AEAAKKKPEAX@Z; ServiceManager::ControlHandler(ulong,ulong,void *)
```
