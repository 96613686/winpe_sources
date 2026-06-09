# Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::get_Instance

- ea: `0x5340`
- end: `0x5357`
- name: `Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::get_Instance`
- size: `23`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x590`
- `0x630`
- `0x1b20`
- `0x2d80`
- `0x4d20`
- `0xdcb0`
- `0xde30`

## callees

- `0x5340`
- `0x5520`

## pseudocode

```c

```

## disassembly

```asm
0x5340  ldsfld   class Microsoft.Crm.Authentication.WebConfigAuthenticationSettings Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::_instance
0x5345  brtrue.s loc_5351
0x5347  newobj   instance void Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::.ctor()
0x534c  stsfld   class Microsoft.Crm.Authentication.WebConfigAuthenticationSettings Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::_instance
0x5351  ldsfld   class Microsoft.Crm.Authentication.WebConfigAuthenticationSettings Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::_instance
0x5356  ret
```
