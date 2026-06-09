# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetDecimalInfo

- ea: `0x1580`
- end: `0x164b`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetDecimalInfo`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x430`

## callees

- `0x190`
- `0x220`
- `0x240`
- `0x270`
- `0x2c0`
- `0x1580`
- `0x1b90`

## pseudocode

```c

```

## disassembly

```asm
0x1580  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1585  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x158a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x158f  stloc.0
0x1590  ldnull
0x1591  stloc.1
0x1592  ldarg.1
0x1593  brtrue.s loc_15D1
0x1595  ldarg.0
0x1596  ldstr    aPrecision// "precision"
0x159b  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x15a0  ldarg.0
0x15a1  ldstr    aMinvalue// "minvalue"
0x15a6  ldc.r8   0.0
0x15af  callvirt instance float64 Microsoft.Crm.Application.WebServices.ParameterBag::GetDouble(string name, float64 defaultValue)
0x15b4  ldarg.0
0x15b5  ldstr    aMaxvalue// "maxvalue"
0x15ba  ldc.r8   1.0e9
0x15c3  callvirt instance float64 Microsoft.Crm.Application.WebServices.ParameterBag::GetDouble(string name, float64 defaultValue)
0x15c8  ldloc.0
0x15c9  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.DecimalAttributeInfo::.ctor(int32, float64, float64, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x15ce  stloc.1
0x15cf  br.s     loc_1612
0x15d1  ldarg.1
0x15d2  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DecimalAttributeMetadata
0x15d7  stloc.2
0x15d8  ldarg.0
0x15d9  ldstr    aPrecision// "precision"
0x15de  ldloc.2
0x15df  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_Precision()
0x15e4  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name, int32 defaultValue)
0x15e9  ldarg.0
0x15ea  ldstr    aMinvalue// "minvalue"
0x15ef  ldloc.2
0x15f0  callvirt instance float64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_MinValue()
0x15f5  callvirt instance float64 Microsoft.Crm.Application.WebServices.ParameterBag::GetDouble(string name, float64 defaultValue)
0x15fa  ldarg.0
0x15fb  ldstr    aMaxvalue// "maxvalue"
0x1600  ldloc.2
0x1601  callvirt instance float64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_MaxValue()
0x1606  callvirt instance float64 Microsoft.Crm.Application.WebServices.ParameterBag::GetDouble(string name, float64 defaultValue)
0x160b  ldloc.0
0x160c  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.DecimalAttributeInfo::.ctor(int32, float64, float64, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1611  stloc.1
0x1612  ldarg.0
0x1613  ldstr    aSourcetype// "sourcetype"
0x1618  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x161d  brfalse.s loc_162B
0x161f  ldloc.1
0x1620  ldarg.0
0x1621  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDataSourceType Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetDataSourceFromParameterBag(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag)
0x1626  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_SourceType(int32)
0x162b  ldarg.0
0x162c  ldstr    aFormuladefinit// "formuladefinition"
0x1631  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x1636  brfalse.s loc_1649
0x1638  ldloc.1
0x1639  ldarg.0
0x163a  ldstr    aFormuladefinit// "formuladefinition"
0x163f  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x1644  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_FormulaDefinition(string)
0x1649  ldloc.1
0x164a  ret
```
