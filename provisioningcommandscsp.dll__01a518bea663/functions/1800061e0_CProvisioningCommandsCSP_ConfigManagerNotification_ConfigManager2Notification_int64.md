# CProvisioningCommandsCSP::ConfigManagerNotification(ConfigManager2Notification,__int64)

- ea: `0x1800061e0`
- end: `0x1800061e5`
- name: `?ConfigManagerNotification@CProvisioningCommandsCSP@@UEAAJW4ConfigManager2Notification@@_J@Z`
- size: `5`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180007fa0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CProvisioningCommandsCSP::ConfigManagerNotification(__int64 a1, int a2, __int64 a3)
{
  return CConfigServiceProvider2Impl::ConfigManagerNotification(a1, a2, a3);
}

```

## disassembly

```asm
0x1800061e0  jmp     ?ConfigManagerNotification@CConfigServiceProvider2Impl@@UEAAJW4ConfigManager2Notification@@_J@Z; CConfigServiceProvider2Impl::ConfigManagerNotification(ConfigManager2Notification,__int64)
```
