# Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::CheckIfDependentComponentHasHigherVersionDependencyFeatureRequirement

- ea: `0x3a6f0`
- end: `0x3a754`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::CheckIfDependentComponentHasHigherVersionDependencyFeatureRequirement`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x84e70`

## callees

- `0x3a6f0`

## string_xrefs

- `0x3a6f1`: `requiredcomponenttype`
- `0x3a6fe`: `requiredcomponenttype`
- `0x3a715`: `requiredcomponentintroducedversion`
- `0x3a722`: `requiredcomponentintroducedversion`

## pseudocode

```c

```

## disassembly

```asm
0x3a6f0  ldarg.1
0x3a6f1  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x3a6f6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x3a6fb  brtrue.s loc_3A752
0x3a6fd  ldarg.1
0x3a6fe  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x3a703  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3a708  unbox.any [mscorlib]System.Int32
0x3a70d  ldc.i4   0xA0
0x3a712  bne.un.s loc_3A752
0x3a714  ldarg.1
0x3a715  ldstr    aRequiredcompon_1// "requiredcomponentintroducedversion"
0x3a71a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x3a71f  brtrue.s loc_3A752
0x3a721  ldarg.1
0x3a722  ldstr    aRequiredcompon_1// "requiredcomponentintroducedversion"
0x3a727  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3a72c  unbox.any [mscorlib]System.Double
0x3a731  stloc.0
0x3a732  ldloca.s 0
0x3a734  ldstr    a00// "0.0"
0x3a739  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3a73e  call     instance string [mscorlib]System.Double::ToString(string, class [mscorlib]System.IFormatProvider)
0x3a743  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x3a748  ldarg.2
0x3a749  call     bool [mscorlib]System.Version::op_GreaterThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x3a74e  brfalse.s loc_3A752
0x3a750  ldc.i4.1
0x3a751  ret
0x3a752  ldc.i4.0
0x3a753  ret
```
