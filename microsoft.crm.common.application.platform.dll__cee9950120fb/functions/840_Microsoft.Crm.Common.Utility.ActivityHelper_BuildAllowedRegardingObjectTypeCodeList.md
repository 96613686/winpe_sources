# Microsoft.Crm.Common.Utility.ActivityHelper::BuildAllowedRegardingObjectTypeCodeList

- ea: `0x840`
- end: `0x89c`
- name: `Microsoft.Crm.Common.Utility.ActivityHelper::BuildAllowedRegardingObjectTypeCodeList`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x7d0`
- `0x840`

## pseudocode

```c

```

## disassembly

```asm
0x840  ldarg.1
0x841  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x846  ldarg.0
0x847  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x84c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x851  ldstr    aRegardingobjec// "regardingobjectid"
0x856  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x85b  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata
0x860  stloc.0
0x861  ldloc.0
0x862  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata::get_LookupTypes()
0x867  stloc.1
0x868  ldloc.1
0x869  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::get_Count()
0x86e  newarr   [mscorlib]System.Int32
0x873  stloc.2
0x874  ldc.i4.0
0x875  stloc.3
0x876  br.s     loc_88B
0x878  ldloc.2
0x879  ldloc.3
0x87a  ldloc.0
0x87b  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata::get_LookupTypes()
0x880  ldloc.3
0x881  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::get_Item(!!T0)
0x886  stelem.i4
0x887  ldloc.3
0x888  ldc.i4.1
0x889  add
0x88a  stloc.3
0x88b  ldloc.3
0x88c  ldloc.1
0x88d  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::get_Count()
0x892  blt.s    loc_878
0x894  ldloc.2
0x895  ldarg.1
0x896  call     int32[] Microsoft.Crm.Common.Utility.ActivityHelper::BuildAllowedObjectTypeCodeList(int32[] objectTypeCodes, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x89b  ret
```
