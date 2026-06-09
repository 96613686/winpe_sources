# _dynamic_initializer_for__PackageCollector::s_registryCache__

- ea: `0x140001660`
- end: `0x14000166c`
- name: `_dynamic_initializer_for__PackageCollector::s_registryCache__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001b14`

## pseudocode

```c
int dynamic_initializer_for__PackageCollector::s_registryCache__()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__PackageCollector::s_registryCache__);
}

```

## disassembly

```asm
0x140001660  lea     rcx, _dynamic_atexit_destructor_for__PackageCollector__s_registryCache__
0x140001667  jmp     atexit
```
