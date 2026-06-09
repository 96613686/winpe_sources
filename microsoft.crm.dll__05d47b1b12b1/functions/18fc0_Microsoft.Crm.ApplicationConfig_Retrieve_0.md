# Microsoft.Crm.ApplicationConfig::Retrieve_0

- ea: `0x18fc0`
- end: `0x19035`
- name: `Microsoft.Crm.ApplicationConfig::Retrieve_0`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18b80`
- `0x18fb0`

## callees

- `0x18fc0`

## string_xrefs

- `0x18fe3`: `D:\a\1\s\src\Shared\Server\Utils\ApplicationConfig.cs`

## pseudocode

```c

```

## disassembly

```asm
0x18fc0  ldnull
0x18fc1  stloc.0
0x18fc2  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x18fc7  brtrue.s loc_18FEE
0x18fc9  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x18fce  ldarg.2
0x18fcf  ldc.i4.1
0x18fd0  newarr   [mscorlib]System.String
0x18fd5  dup
0x18fd6  ldc.i4.0
0x18fd7  ldarg.0
0x18fd8  stelem.ref
0x18fd9  ldc.i4   0x192
0x18fde  ldstr    aRetrieve// "Retrieve"
0x18fe3  ldstr    aDA1SSrcSharedS_0// "D:\\a\\1\\s\\src\\Shared\\Server\\Utils"...
0x18fe8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganization(valuetype [mscorlib]System.Guid, string[], int32, string, string)
0x18fed  stloc.0
0x18fee  ldloc.0
0x18fef  brfalse.s loc_19019
0x18ff1  ldloc.0
0x18ff2  ldarg.0
0x18ff3  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x18ff8  brfalse.s loc_19019
0x18ffa  ldloc.0
0x18ffb  ldarg.0
0x18ffc  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x19001  brfalse.s loc_19019
0x19003  ldloc.0
0x19004  ldarg.0
0x19005  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1900a  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1900f  beq.s    loc_19019
0x19011  ldloc.0
0x19012  ldarg.0
0x19013  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x19018  ret
0x19019  ldarg.3
0x1901a  brfalse.s loc_19033
0x1901c  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x19021  ldarg.0
0x19022  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x19027  callvirt instance string [mscorlib]System.Object::ToString()
0x1902c  ldarg.1
0x1902d  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x19032  ret
0x19033  ldarg.1
0x19034  ret
```
