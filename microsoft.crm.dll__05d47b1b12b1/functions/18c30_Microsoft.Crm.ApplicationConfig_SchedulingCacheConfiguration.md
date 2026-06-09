# Microsoft.Crm.ApplicationConfig::SchedulingCacheConfiguration

- ea: `0x18c30`
- end: `0x18c69`
- name: `Microsoft.Crm.ApplicationConfig::SchedulingCacheConfiguration`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x18c4a`: `SchedulingCacheConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x18c30  ldarg.0
0x18c31  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x18c36  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x18c3b  ldstr    aOrganizationId// "Organization Id not specified"
0x18c40  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x18c45  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x18c4a  ldstr    aSchedulingcach_0// "SchedulingCacheConfiguration"
0x18c4f  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x18c54  callvirt instance string [mscorlib]System.Object::ToString()
0x18c59  ldsfld   string [mscorlib]System.String::Empty
0x18c5e  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x18c63  isinst   [mscorlib]System.String
0x18c68  ret
```
