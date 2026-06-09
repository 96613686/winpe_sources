# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetIntegerInfo

- ea: `0x1400`
- end: `0x14df`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetIntegerInfo`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x430`

## callees

- `0x190`
- `0x200`
- `0x220`
- `0x240`
- `0x1400`
- `0x1b90`

## pseudocode

```c

```

## disassembly

```asm
0x1400  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1405  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x140a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x140f  stloc.0
0x1410  ldarg.1
0x1411  brfalse.s loc_141B
0x1413  ldarg.1
0x1414  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x1419  br.s     loc_142B
0x141b  ldarg.0
0x141c  ldstr    aFormat// "format"
0x1421  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IntegerAttributeFormats::get_DefaultFormat()
0x1426  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x142b  stloc.1
0x142c  ldnull
0x142d  stloc.2
0x142e  ldloc.1
0x142f  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IntegerAttributeFormats::get_None()
0x1434  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1439  brfalse.s loc_1445
0x143b  ldloc.1
0x143c  ldloc.0
0x143d  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.IntAttributeInfo::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1442  stloc.2
0x1443  br.s     loc_14A6
0x1445  ldarg.1
0x1446  brtrue.s loc_146D
0x1448  ldarg.0
0x1449  ldstr    aMinvalue// "minvalue"
0x144e  ldc.i4   0x80000000
0x1453  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name, int32 defaultValue)
0x1458  stloc.3
0x1459  ldarg.0
0x145a  ldstr    aMaxvalue// "maxvalue"
0x145f  ldc.i4   0x7FFFFFFF
0x1464  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name, int32 defaultValue)
0x1469  stloc.s  4
0x146b  br.s     loc_149C
0x146d  ldarg.1
0x146e  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IntegerAttributeMetadata
0x1473  stloc.s  5
0x1475  ldarg.0
0x1476  ldstr    aMinvalue// "minvalue"
0x147b  ldloc.s  5
0x147d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IntegerAttributeMetadata::get_MinValue()
0x1482  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name, int32 defaultValue)
0x1487  stloc.3
0x1488  ldarg.0
0x1489  ldstr    aMaxvalue// "maxvalue"
0x148e  ldloc.s  5
0x1490  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IntegerAttributeMetadata::get_MaxValue()
0x1495  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name, int32 defaultValue)
0x149a  stloc.s  4
0x149c  ldloc.3
0x149d  ldloc.s  4
0x149f  ldloc.0
0x14a0  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.IntAttributeInfo::.ctor(int32, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14a5  stloc.2
0x14a6  ldarg.0
0x14a7  ldstr    aSourcetype// "sourcetype"
0x14ac  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x14b1  brfalse.s loc_14BF
0x14b3  ldloc.2
0x14b4  ldarg.0
0x14b5  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDataSourceType Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetDataSourceFromParameterBag(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag)
0x14ba  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_SourceType(int32)
0x14bf  ldarg.0
0x14c0  ldstr    aFormuladefinit// "formuladefinition"
0x14c5  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x14ca  brfalse.s loc_14DD
0x14cc  ldloc.2
0x14cd  ldarg.0
0x14ce  ldstr    aFormuladefinit// "formuladefinition"
0x14d3  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x14d8  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_FormulaDefinition(string)
0x14dd  ldloc.2
0x14de  ret
```
