# Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_ServiceAssembly

- ea: `0x32320`
- end: `0x3234a`
- name: `Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_ServiceAssembly`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x32320`
- `0x6fd40`
- `0x6fe70`

## string_xrefs

- `0x32326`: `serviceassembly`
- `0x3233a`: `serviceassembly`

## pseudocode

```c

```

## disassembly

```asm
0x32320  ldarg.0
0x32321  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::_entityData
0x32326  ldstr    aServiceassembl_0// "serviceassembly"
0x3232b  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string propertyName)
0x32330  brfalse.s loc_32334
0x32332  ldnull
0x32333  ret
0x32334  ldarg.0
0x32335  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::_entityData
0x3233a  ldstr    aServiceassembl_0// "serviceassembly"
0x3233f  callvirt instance object Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string propertyName)
0x32344  castclass [mscorlib]System.String
0x32349  ret
```
