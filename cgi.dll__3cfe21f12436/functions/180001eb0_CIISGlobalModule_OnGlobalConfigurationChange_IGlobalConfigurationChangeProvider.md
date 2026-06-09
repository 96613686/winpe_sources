# CIISGlobalModule::OnGlobalConfigurationChange(IGlobalConfigurationChangeProvider *)

- ea: `0x180001eb0`
- end: `0x180001eba`
- name: `?OnGlobalConfigurationChange@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalConfigurationChangeProvider@@@Z`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180001b20`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalConfigurationChange(__int64 a1, __int64 a2)
{
  return GlobalDoWork(64, a2);
}

```

## disassembly

```asm
0x180001eb0  mov     ecx, 40h ; '@'
0x180001eb5  jmp     ?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; GlobalDoWork(ulong,IHttpEventProvider *)
```
