# Microsoft.Crm.Sdk.Metadata.AttributeDataBuilderFactory::GetAttributeDataBuilder

- ea: `0x1590`
- end: `0x169e`
- name: `Microsoft.Crm.Sdk.Metadata.AttributeDataBuilderFactory::GetAttributeDataBuilder`
- size: `270`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x8be0`
- `0x8ec0`

## callees

- `0x1590`
- `0x16b0`
- `0x2190`
- `0x24c0`
- `0x28a0`
- `0x29b0`
- `0x2ae0`
- `0x2b20`
- `0x2b50`
- `0x2d30`
- `0x2e00`
- `0x3010`
- `0x3310`
- `0x35b0`
- `0x3870`
- `0x3a90`

## string_xrefs

- `0x1660`: `State attributes cannot be created through the SDK`
- `0x1683`: `Status attributes cannot be created through the SDK`

## pseudocode

```c

```

## disassembly

```asm
0x1590  ldarg.1
0x1591  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringAttributeMetadata
0x1596  brfalse.s loc_15A0
0x1598  ldarg.0
0x1599  ldarg.3
0x159a  newobj   instance void Microsoft.Crm.Sdk.Metadata.StringAttributeDataBuilder::.ctor(class Microsoft.Crm.Sdk.Metadata.MetadataConverter converter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x159f  ret
0x15a0  ldarg.1
0x15a1  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MemoAttributeMetadata
0x15a6  brfalse.s loc_15B0
0x15a8  ldarg.0
0x15a9  ldarg.3
0x15aa  newobj   instance void Microsoft.Crm.Sdk.Metadata.MemoAttributeDataBuilder::.ctor(class Microsoft.Crm.Sdk.Metadata.MetadataConverter converter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x15af  ret
0x15b0  ldarg.1
0x15b1  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.PicklistAttributeMetadata
0x15b6  brfalse.s loc_15C0
0x15b8  ldarg.0
0x15b9  ldarg.3
0x15ba  newobj   instance void Microsoft.Crm.Sdk.Metadata.PicklistAttributeDataBuilder::.ctor(class Microsoft.Crm.Sdk.Metadata.MetadataConverter converter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x15bf  ret
0x15c0  ldarg.1
0x15c1  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.BooleanAttributeMetadata
0x15c6  brfalse.s loc_15D0
0x15c8  ldarg.0
0x15c9  ldarg.3
0x15ca  newobj   instance void Microsoft.Crm.Sdk.Metadata.BooleanAttributeDataBuilder::.ctor(class Microsoft.Crm.Sdk.Metadata.MetadataConverter converter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x15cf  ret
0x15d0  ldarg.1
0x15d1  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.DateTimeAttributeMetadata
0x15d6  brfalse.s loc_15E0
0x15d8  ldarg.0
0x15d9  ldarg.3
0x15da  newobj   instance void Microsoft.Crm.Sdk.Metadata.DateTimeAttributeDataBuilder::.ctor(class Microsoft.Crm.Sdk.Metadata.MetadataConverter converter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x15df  ret
0x15e0  ldarg.1
0x15e1  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.IntegerAttributeMetadata
0x15e6  brfalse.s loc_15F0
0x15e8  ldarg.0
0x15e9  ldarg.3
0x15ea  newobj   instance void Microsoft.Crm.Sdk.Metadata.IntegerAttributeDataBuilder::.ctor(class Microsoft.Crm.Sdk.Metadata.MetadataConverter converter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x15ef  ret
0x15f0  ldarg.1
0x15f1  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MoneyAttributeMetadata
0x15f6  brfalse.s loc_1600
0x15f8  ldarg.0
0x15f9  ldarg.3
0x15fa  newobj   instance void Microsoft.Crm.Sdk.Metadata.MoneyAttributeDataBuilder::.ctor(class Microsoft.Crm.Sdk.Metadata.MetadataConverter converter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x15ff  ret
0x1600  ldarg.1
0x1601  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.DecimalAttributeMetadata
0x1606  brfalse.s loc_1610
0x1608  ldarg.0
0x1609  ldarg.3
0x160a  newobj   instance void Microsoft.Crm.Sdk.Metadata.DecimalAttributeDataBuilder::.ctor(class Microsoft.Crm.Sdk.Metadata.MetadataConverter converter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x160f  ret
0x1610  ldarg.1
0x1611  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.DoubleAttributeMetadata
0x1616  brfalse.s loc_1620
0x1618  ldarg.0
0x1619  ldarg.3
0x161a  newobj   instance void Microsoft.Crm.Sdk.Metadata.DoubleAttributeDataBuilder::.ctor(class Microsoft.Crm.Sdk.Metadata.MetadataConverter converter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x161f  ret
0x1620  ldarg.1
0x1621  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ImageAttributeMetadata
0x1626  brfalse.s loc_1630
0x1628  ldarg.0
0x1629  ldarg.3
0x162a  newobj   instance void Microsoft.Crm.Sdk.Metadata.ImageAttributeDataBuilder::.ctor(class Microsoft.Crm.Sdk.Metadata.MetadataConverter converter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x162f  ret
0x1630  ldarg.1
0x1631  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MultiSelectPicklistAttributeMetadata
0x1636  brfalse.s loc_1640
0x1638  ldarg.0
0x1639  ldarg.3
0x163a  newobj   instance void Microsoft.Crm.Sdk.Metadata.MultiSelectPicklistAttributeDataBuilder::.ctor(class Microsoft.Crm.Sdk.Metadata.MetadataConverter converter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x163f  ret
0x1640  ldarg.1
0x1641  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.LookupAttributeMetadata
0x1646  brfalse.s loc_1650
0x1648  ldarg.0
0x1649  ldarg.3
0x164a  newobj   instance void Microsoft.Crm.Sdk.Metadata.LookupAttributeDataBuilder::.ctor(class Microsoft.Crm.Sdk.Metadata.MetadataConverter converter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x164f  ret
0x1650  ldarg.1
0x1651  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StateAttributeMetadata
0x1656  brfalse.s loc_1673
0x1658  ldarg.2
0x1659  ldc.i4   0x1004
0x165e  bne.un.s loc_166B
0x1660  ldstr    aStateAttribute// "State attributes cannot be created thro"...
0x1665  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x166a  throw
0x166b  ldarg.0
0x166c  ldarg.3
0x166d  newobj   instance void Microsoft.Crm.Sdk.Metadata.StateAttributeDataBuilder::.ctor(class Microsoft.Crm.Sdk.Metadata.MetadataConverter converter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x1672  ret
0x1673  ldarg.1
0x1674  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StatusAttributeMetadata
0x1679  brfalse.s loc_1696
0x167b  ldarg.2
0x167c  ldc.i4   0x1004
0x1681  bne.un.s loc_168E
0x1683  ldstr    aStatusAttribut// "Status attributes cannot be created thr"...
0x1688  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x168d  throw
0x168e  ldarg.0
0x168f  ldarg.3
0x1690  newobj   instance void Microsoft.Crm.Sdk.Metadata.StatusAttributeDataBuilder::.ctor(class Microsoft.Crm.Sdk.Metadata.MetadataConverter converter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x1695  ret
0x1696  ldarg.0
0x1697  ldarg.3
0x1698  newobj   instance void Microsoft.Crm.Sdk.Metadata.BaseAttributeDataBuilder::.ctor(class Microsoft.Crm.Sdk.Metadata.MetadataConverter converter, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x169d  ret
```
