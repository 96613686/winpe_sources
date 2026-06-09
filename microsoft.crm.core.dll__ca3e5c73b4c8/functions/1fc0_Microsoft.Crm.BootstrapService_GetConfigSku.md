# Microsoft.Crm.BootstrapService::GetConfigSku

- ea: `0x1fc0`
- end: `0x1ff9`
- name: `Microsoft.Crm.BootstrapService::GetConfigSku`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1f80`

## callees

- `0x1fc0`
- `0x2d930`
- `0x34790`

## string_xrefs

- `0x1fc0`: `ConfigSku`
- `0x1fda`: `ConfigSku`

## pseudocode

```c

```

## disassembly

```asm
0x1fc0  ldstr    aConfigsku// "ConfigSku"
0x1fc5  call     object Microsoft.Crm.RegistryCache::GetValue(string key)
0x1fca  stloc.0
0x1fcb  ldloc.0
0x1fcc  brtrue.s loc_1FD0
0x1fce  ldc.i4.0
0x1fcf  ret
0x1fd0  ldtoken  Microsoft.Crm.SharedDatabase.ConfigSku
0x1fd5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1fda  ldstr    aConfigsku// "ConfigSku"
0x1fdf  call     object Microsoft.Crm.RegistryCache::GetValue(string key)
0x1fe4  castclass [mscorlib]System.String
0x1fe9  callvirt instance string [mscorlib]System.String::Trim()
0x1fee  call     object Microsoft.Crm.CrmEnumUtility::ParseSingleValue(class [mscorlib]System.Type enumType, string value)
0x1ff3  unbox.any Microsoft.Crm.SharedDatabase.ConfigSku
0x1ff8  ret
```
