# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetMoneyInfo

- ea: `0x1650`
- end: `0x1737`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetMoneyInfo`
- size: `231`
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
- `0x1650`
- `0x1b90`

## pseudocode

```c

```

## disassembly

```asm
0x1650  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1655  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x165a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x165f  stloc.0
0x1660  ldnull
0x1661  stloc.1
0x1662  ldarg.1
0x1663  brtrue.s loc_16AC
0x1665  ldarg.0
0x1666  ldstr    aPrecisionsourc// "precisionsource"
0x166b  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x1670  ldarg.0
0x1671  ldstr    aPrecision// "precision"
0x1676  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x167b  ldarg.0
0x167c  ldstr    aMinvalue// "minvalue"
0x1681  ldc.r8   0.0
0x168a  callvirt instance float64 Microsoft.Crm.Application.WebServices.ParameterBag::GetDouble(string name, float64 defaultValue)
0x168f  ldarg.0
0x1690  ldstr    aMaxvalue// "maxvalue"
0x1695  ldc.r8   1.0e9
0x169e  callvirt instance float64 Microsoft.Crm.Application.WebServices.ParameterBag::GetDouble(string name, float64 defaultValue)
0x16a3  ldloc.0
0x16a4  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.MoneyAttributeInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MoneyPrecisionSource, int32, float64, float64, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x16a9  stloc.1
0x16aa  br.s     loc_16FE
0x16ac  ldarg.1
0x16ad  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MoneyAttributeMetadata
0x16b2  stloc.2
0x16b3  ldarg.0
0x16b4  ldstr    aPrecisionsourc// "precisionsource"
0x16b9  ldloc.2
0x16ba  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MoneyPrecisionSource [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MoneyAttributeMetadata::get_PrecisionSource()
0x16bf  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name, int32 defaultValue)
0x16c4  ldarg.0
0x16c5  ldstr    aPrecision// "precision"
0x16ca  ldloc.2
0x16cb  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_Precision()
0x16d0  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name, int32 defaultValue)
0x16d5  ldarg.0
0x16d6  ldstr    aMinvalue// "minvalue"
0x16db  ldloc.2
0x16dc  callvirt instance float64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_MinValue()
0x16e1  callvirt instance float64 Microsoft.Crm.Application.WebServices.ParameterBag::GetDouble(string name, float64 defaultValue)
0x16e6  ldarg.0
0x16e7  ldstr    aMaxvalue// "maxvalue"
0x16ec  ldloc.2
0x16ed  callvirt instance float64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_MaxValue()
0x16f2  callvirt instance float64 Microsoft.Crm.Application.WebServices.ParameterBag::GetDouble(string name, float64 defaultValue)
0x16f7  ldloc.0
0x16f8  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.MoneyAttributeInfo::.ctor(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MoneyPrecisionSource, int32, float64, float64, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x16fd  stloc.1
0x16fe  ldarg.0
0x16ff  ldstr    aSourcetype// "sourcetype"
0x1704  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x1709  brfalse.s loc_1717
0x170b  ldloc.1
0x170c  ldarg.0
0x170d  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDataSourceType Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetDataSourceFromParameterBag(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag)
0x1712  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_SourceType(int32)
0x1717  ldarg.0
0x1718  ldstr    aFormuladefinit// "formuladefinition"
0x171d  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x1722  brfalse.s loc_1735
0x1724  ldloc.1
0x1725  ldarg.0
0x1726  ldstr    aFormuladefinit// "formuladefinition"
0x172b  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x1730  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_FormulaDefinition(string)
0x1735  ldloc.1
0x1736  ret
```
