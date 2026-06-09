# Windows::Internal::SyncRootHelpers::_dynamic_initializer_for__s_syncRootManagerRegistryPath__

- ea: `0x180002210`
- end: `0x18000221c`
- name: `Windows::Internal::SyncRootHelpers::_dynamic_initializer_for__s_syncRootManagerRegistryPath__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800029dc`

## pseudocode

```c
int Windows::Internal::SyncRootHelpers::_dynamic_initializer_for__s_syncRootManagerRegistryPath__()
{
  return atexit(Windows::Internal::SyncRootHelpers::_dynamic_atexit_destructor_for__s_syncRootManagerRegistryPath__);
}

```

## disassembly

```asm
0x180002210  lea     rcx, Windows__Internal__SyncRootHelpers___dynamic_atexit_destructor_for__s_syncRootManagerRegistryPath__
0x180002217  jmp     atexit
```
