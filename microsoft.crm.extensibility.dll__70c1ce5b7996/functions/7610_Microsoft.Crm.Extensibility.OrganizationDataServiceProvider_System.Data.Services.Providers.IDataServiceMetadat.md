# Microsoft.Crm.Extensibility.OrganizationDataServiceProvider::System.Data.Services.Providers.IDataServiceMetadataProvider.GetResourceAssociationSet

- ea: `0x7610`
- end: `0x7651`
- name: `Microsoft.Crm.Extensibility.OrganizationDataServiceProvider::System.Data.Services.Providers.IDataServiceMetadataProvider.GetResourceAssociationSet`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x7610`

## string_xrefs

- `0x7633`: `Attempt to get a ResourceAssociationSet for a non-related ResourceProperty {0} on type {1}`

## pseudocode

```c

```

## disassembly

```asm
0x7610  ldarg.3
0x7611  callvirt instance object [System.Data.Services]System.Data.Services.Providers.ResourceProperty::get_CustomState()
0x7616  isinst   class [mscorlib]System.Tuple`3<class [System.Data.Services]System.Data.Services.Providers.ResourceAssociationSet, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole>
0x761b  stloc.0
0x761c  ldloc.0
0x761d  brfalse.s loc_7626
0x761f  ldloc.0
0x7620  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [System.Data.Services]System.Data.Services.Providers.ResourceAssociationSet, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole>::get_Item1()
0x7625  ret
0x7626  ldc.i4   0x80040216
0x762b  ldc.i4.3
0x762c  newarr   [mscorlib]System.Object
0x7631  dup
0x7632  ldc.i4.0
0x7633  ldstr    aAttemptToGetAR// "Attempt to get a ResourceAssociationSet"...
0x7638  stelem.ref
0x7639  dup
0x763a  ldc.i4.1
0x763b  ldarg.3
0x763c  callvirt instance string [System.Data.Services]System.Data.Services.Providers.ResourceProperty::get_Name()
0x7641  stelem.ref
0x7642  dup
0x7643  ldc.i4.2
0x7644  ldarg.2
0x7645  callvirt instance string [System.Data.Services]System.Data.Services.Providers.ResourceType::get_Name()
0x764a  stelem.ref
0x764b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x7650  throw
```
