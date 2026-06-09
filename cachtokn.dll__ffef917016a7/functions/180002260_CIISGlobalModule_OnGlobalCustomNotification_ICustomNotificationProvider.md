# CIISGlobalModule::OnGlobalCustomNotification(ICustomNotificationProvider *)

- ea: `0x180002260`
- end: `0x18000226a`
- name: `?OnGlobalCustomNotification@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVICustomNotificationProvider@@@Z`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001280`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalCustomNotification(__int64 a1, __int64 *a2)
{
  return GlobalDoWork(0x4000, a2);
}

```

## disassembly

```asm
0x180002260  mov     ecx, 4000h
0x180002265  jmp     ?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; GlobalDoWork(ulong,IHttpEventProvider *)
```
