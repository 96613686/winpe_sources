# CIISGlobalModule::OnGlobalThreadCleanup(IGlobalThreadCleanupProvider *)

- ea: `0x180009750`
- end: `0x18000975a`
- name: `?OnGlobalThreadCleanup@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalThreadCleanupProvider@@@Z`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002fc0`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalThreadCleanup(__int64 a1, __int64 a2)
{
  return GlobalDoWork(0x8000, a2);
}

```

## disassembly

```asm
0x180009750  mov     ecx, 8000h
0x180009755  jmp     ?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; GlobalDoWork(ulong,IHttpEventProvider *)
```
