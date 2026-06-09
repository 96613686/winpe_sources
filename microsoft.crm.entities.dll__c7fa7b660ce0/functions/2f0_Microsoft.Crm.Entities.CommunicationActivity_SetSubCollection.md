# Microsoft.Crm.Entities.CommunicationActivity::SetSubCollection

- ea: `0x2f0`
- end: `0x332`
- name: `Microsoft.Crm.Entities.CommunicationActivity::SetSubCollection`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xc60`
- `0xdb0`

## pseudocode

```c

```

## disassembly

```asm
0x2f0  ldarg.0
0x2f1  ldfld    class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::partyMappingCollection
0x2f6  ldarg.1
0x2f7  callvirt instance class Microsoft.Crm.Entities.PartyMappingItem Microsoft.Crm.Entities.PartyMappingCollection::Find(string logicalName)
0x2fc  stloc.0
0x2fd  ldloc.0
0x2fe  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x303  ldstr    a0IsNotAValidSu// "'{0}' is not a valid sub collection for"...
0x308  ldc.i4.2
0x309  newarr   [mscorlib]System.Object
0x30e  dup
0x30f  ldc.i4.0
0x310  ldarg.1
0x311  stelem.ref
0x312  dup
0x313  ldc.i4.1
0x314  ldarg.0
0x315  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x31a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x31f  stelem.ref
0x320  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x325  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x32a  ldloc.0
0x32b  ldarg.2
0x32c  callvirt instance void Microsoft.Crm.Entities.PartyMappingItem::set_Parties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection value)
0x331  ret
```
