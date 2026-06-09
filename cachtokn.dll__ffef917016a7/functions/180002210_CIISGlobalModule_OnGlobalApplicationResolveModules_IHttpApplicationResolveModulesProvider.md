# CIISGlobalModule::OnGlobalApplicationResolveModules(IHttpApplicationResolveModulesProvider *)

- ea: `0x180002210`
- end: `0x18000221a`
- name: `?OnGlobalApplicationResolveModules@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIHttpApplicationResolveModulesProvider@@@Z`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001280`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalApplicationResolveModules(__int64 a1, __int64 *a2)
{
  return GlobalDoWork(1024, a2);
}

```

## disassembly

```asm
0x180002210  mov     ecx, 400h
0x180002215  jmp     ?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; GlobalDoWork(ulong,IHttpEventProvider *)
```
