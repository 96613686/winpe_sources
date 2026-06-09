# SystemSettings::DataModel::Details::_dynamic_initializer_for__s_handlersResourceMapCache__

- ea: `0x1800013f0`
- end: `0x1800013fc`
- name: `SystemSettings::DataModel::Details::_dynamic_initializer_for__s_handlersResourceMapCache__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001c24`

## pseudocode

```c
int SystemSettings::DataModel::Details::_dynamic_initializer_for__s_handlersResourceMapCache__()
{
  return atexit((void (__cdecl *)())SystemSettings::DataModel::Details::_dynamic_atexit_destructor_for__s_handlersResourceMapCache__);
}

```

## disassembly

```asm
0x1800013f0  lea     rcx, SystemSettings__DataModel__Details___dynamic_atexit_destructor_for__s_handlersResourceMapCache__
0x1800013f7  jmp     atexit
```
