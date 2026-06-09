# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetFloatInfo

- ea: `0x14e0`
- end: `0x1574`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetFloatInfo`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x430`

## callees

- `0x240`
- `0x270`
- `0x2c0`
- `0x14e0`

## pseudocode

```c

```

## disassembly

```asm
0x14e0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x14e5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x14ea  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x14ef  stloc.0
0x14f0  ldnull
0x14f1  stloc.1
0x14f2  ldarg.1
0x14f3  brtrue.s loc_1531
0x14f5  ldarg.0
0x14f6  ldstr    aPrecision// "precision"
0x14fb  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x1500  ldarg.0
0x1501  ldstr    aMinvalue// "minvalue"
0x1506  ldc.r8   0.0
0x150f  callvirt instance float64 Microsoft.Crm.Application.WebServices.ParameterBag::GetDouble(string name, float64 defaultValue)
0x1514  ldarg.0
0x1515  ldstr    aMaxvalue// "maxvalue"
0x151a  ldc.r8   1.0e9
0x1523  callvirt instance float64 Microsoft.Crm.Application.WebServices.ParameterBag::GetDouble(string name, float64 defaultValue)
0x1528  ldloc.0
0x1529  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.FloatAttributeInfo::.ctor(int32, float64, float64, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x152e  stloc.1
0x152f  br.s     loc_1572
0x1531  ldarg.1
0x1532  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.FloatAttributeMetadata
0x1537  stloc.2
0x1538  ldarg.0
0x1539  ldstr    aPrecision// "precision"
0x153e  ldloc.2
0x153f  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_Precision()
0x1544  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name, int32 defaultValue)
0x1549  ldarg.0
0x154a  ldstr    aMinvalue// "minvalue"
0x154f  ldloc.2
0x1550  callvirt instance float64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_MinValue()
0x1555  callvirt instance float64 Microsoft.Crm.Application.WebServices.ParameterBag::GetDouble(string name, float64 defaultValue)
0x155a  ldarg.0
0x155b  ldstr    aMaxvalue// "maxvalue"
0x1560  ldloc.2
0x1561  callvirt instance float64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_MaxValue()
0x1566  callvirt instance float64 Microsoft.Crm.Application.WebServices.ParameterBag::GetDouble(string name, float64 defaultValue)
0x156b  ldloc.0
0x156c  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.FloatAttributeInfo::.ctor(int32, float64, float64, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1571  stloc.1
0x1572  ldloc.1
0x1573  ret
```
