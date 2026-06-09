# _dynamic_initializer_for__g_AclCache__

- ea: `0x180001050`
- end: `0x18000105c`
- name: `_dynamic_initializer_for__g_AclCache__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001634`

## pseudocode

```c
int dynamic_initializer_for__g_AclCache__()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_AclCache__);
}

```

## disassembly

```asm
0x180001050  lea     rcx, _dynamic_atexit_destructor_for__g_AclCache__
0x180001057  jmp     atexit
```
