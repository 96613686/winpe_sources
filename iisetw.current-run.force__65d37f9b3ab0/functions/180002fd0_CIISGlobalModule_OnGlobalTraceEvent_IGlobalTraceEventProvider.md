# CIISGlobalModule::OnGlobalTraceEvent(IGlobalTraceEventProvider *)

- ea: `0x180002fd0`
- end: `0x180002fda`
- name: `?OnGlobalTraceEvent@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalTraceEventProvider@@@Z`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000265c`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalTraceEvent(__int64 a1, struct IGlobalTraceEventProvider *a2)
{
  return GlobalDoWork(0x2000, a2);
}

```

## disassembly

```asm
0x180002fd0  mov     ecx, 2000h
0x180002fd5  jmp     ?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; GlobalDoWork(ulong,IHttpEventProvider *)
```
