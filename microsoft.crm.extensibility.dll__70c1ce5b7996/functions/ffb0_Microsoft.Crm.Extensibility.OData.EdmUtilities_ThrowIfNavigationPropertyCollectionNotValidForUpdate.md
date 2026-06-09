# Microsoft.Crm.Extensibility.OData.EdmUtilities::ThrowIfNavigationPropertyCollectionNotValidForUpdate

- ea: `0xffb0`
- end: `0xffec`
- name: `Microsoft.Crm.Extensibility.OData.EdmUtilities::ThrowIfNavigationPropertyCollectionNotValidForUpdate`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1e790`

## callees

- `0xffb0`
- `0x1f210`

## string_xrefs

- `0xffda`: `Update Navigation Property is only supported for activity parties.`

## pseudocode

```c

```

## disassembly

```asm
0xffb0  ldnull
0xffb1  stloc.0
0xffb2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetMetadataCache()
0xffb7  ldc.i4   0x87
0xffbc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xffc1  stloc.0
0xffc2  leave.s  loc_FFC7
0xffc4  pop
0xffc5  leave.s  loc_FFEB
0xffc7  ldarg.0
0xffc8  ldloc.0
0xffc9  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ODataV4NameFormatter::GetEdmEntityNameForEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata)
0xffce  callvirt instance bool [mscorlib]System.String::Equals(string)
0xffd3  brtrue.s loc_FFEB
0xffd5  ldc.i4   0x190
0xffda  ldstr    aUpdateNavigati// "Update Navigation Property is only supp"...
0xffdf  ldc.i4.0
0xffe0  newarr   [mscorlib]System.Object
0xffe5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0xffea  throw
0xffeb  ret
```
