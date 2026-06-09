# Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::BuildActivitiesMenu

- ea: `0x1500`
- end: `0x16b8`
- name: `Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::BuildActivitiesMenu`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14f0`

## callees

- `0x1500`
- `0x16c0`
- `0x1a50`

## string_xrefs

- `0x1580`: `serviceappointment`

## pseudocode

```c

```

## disassembly

```asm
0x1500  ldarg.0
0x1501  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_commands
0x1506  brfalse.s loc_1509
0x1508  ret
0x1509  ldarg.0
0x150a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x150f  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_controlToCommandMap
0x1514  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::.ctor()
0x1519  stloc.0
0x151a  ldarg.0
0x151b  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_IdPrefix()
0x1520  ldstr    aMenu// "Menu"
0x1525  call     string [mscorlib]System.String::Concat(string, string)
0x152a  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Menu::.ctor(string)
0x152f  stloc.1
0x1530  ldc.i4   0x1068
0x1535  ldc.i4.s 0x20
0x1537  ldarg.0
0x1538  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_Context()
0x153d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1542  brfalse  loc_1690
0x1547  ldc.i4   0x1068
0x154c  ldc.i4.1
0x154d  ldarg.0
0x154e  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_Context()
0x1553  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1558  brfalse  loc_1690
0x155d  ldc.i4.s 0xA
0x155f  stloc.2
0x1560  ldc.i4.1
0x1561  stloc.3
0x1562  ldc.i4.6
0x1563  newarr   [mscorlib]System.Int32
0x1568  dup
0x1569  ldtoken  valuetype __StaticArrayInitTypeSize=24 <PrivateImplementationDetails>::B99CCDF09350011F82700089BE41C734E293EF9D
0x156e  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x1573  stloc.s  4
0x1575  ldarg.0
0x1576  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_Context()
0x157b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1580  ldstr    aServiceappoint// "serviceappointment"
0x1585  ldc.i4.1
0x1586  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x158b  brfalse.s loc_15B3
0x158d  ldloca.s 4
0x158f  ldloc.s  4
0x1591  ldlen
0x1592  conv.i4
0x1593  ldc.i4.1
0x1594  add
0x1595  call     T0x2B000001
0x159a  ldloc.s  4
0x159c  ldc.i4   0x1076
0x15a1  box      [mscorlib]System.Int32
0x15a6  ldloc.s  4
0x15a8  ldc.i4.0
0x15a9  callvirt instance int32 [mscorlib]System.Array::GetUpperBound(int32)
0x15ae  callvirt instance void [mscorlib]System.Array::SetValue(object, int32)
0x15b3  ldarg.0
0x15b4  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_Context()
0x15b9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x15be  ldstr    aCampaignrespon// "campaignresponse"
0x15c3  ldc.i4.1
0x15c4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x15c9  brfalse.s loc_15F1
0x15cb  ldloca.s 4
0x15cd  ldloc.s  4
0x15cf  ldlen
0x15d0  conv.i4
0x15d1  ldc.i4.1
0x15d2  add
0x15d3  call     T0x2B000001
0x15d8  ldloc.s  4
0x15da  ldc.i4   0x1131
0x15df  box      [mscorlib]System.Int32
0x15e4  ldloc.s  4
0x15e6  ldc.i4.0
0x15e7  callvirt instance int32 [mscorlib]System.Array::GetUpperBound(int32)
0x15ec  callvirt instance void [mscorlib]System.Array::SetValue(object, int32)
0x15f1  ldloca.s 4
0x15f3  ldloc.s  4
0x15f5  ldlen
0x15f6  conv.i4
0x15f7  ldc.i4.1
0x15f8  add
0x15f9  call     T0x2B000001
0x15fe  ldloc.s  4
0x1600  ldc.i4   0x109B
0x1605  box      [mscorlib]System.Int32
0x160a  ldloc.s  4
0x160c  ldc.i4.0
0x160d  callvirt instance int32 [mscorlib]System.Array::GetUpperBound(int32)
0x1612  callvirt instance void [mscorlib]System.Array::SetValue(object, int32)
0x1617  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::.ctor()
0x161c  stloc.s  5
0x161e  ldloc.s  4
0x1620  stloc.s  7
0x1622  ldc.i4.0
0x1623  stloc.s  8
0x1625  br.s     loc_165B
0x1627  ldloc.s  7
0x1629  ldloc.s  8
0x162b  ldelem.i4
0x162c  stloc.s  9
0x162e  ldarg.0
0x162f  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_Context()
0x1634  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1639  ldloc.s  9
0x163b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x1640  stloc.s  0xA
0x1642  ldarg.0
0x1643  ldloc.s  9
0x1645  call     instance bool Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::CheckPrivilege(int32 activityTypeCode)
0x164a  brfalse.s loc_1655
0x164c  ldloc.s  5
0x164e  ldloc.s  0xA
0x1650  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::Add(var<u1>)
0x1655  ldloc.s  8
0x1657  ldc.i4.1
0x1658  add
0x1659  stloc.s  8
0x165b  ldloc.s  8
0x165d  ldloc.s  7
0x165f  ldlen
0x1660  conv.i4
0x1661  blt.s    loc_1627
0x1663  ldarg.0
0x1664  ldloc.1
0x1665  ldloc.0
0x1666  ldloc.s  5
0x1668  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::ToArray()
0x166d  ldloc.2
0x166e  ldloc.3
0x166f  call     instance void Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::AddNewActivityButtons(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Menu menu, class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition> commands, class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata> activities, int32 menuSectionSequence, int32 menuSectionIndex)
0x1674  ldloc.2
0x1675  ldc.i4.s 0xA
0x1677  add
0x1678  stloc.2
0x1679  ldloc.3
0x167a  ldc.i4.1
0x167b  add
0x167c  stloc.3
0x167d  call     class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::get_CustomActivitiesByName()
0x1682  stloc.s  6
0x1684  ldarg.0
0x1685  ldloc.1
0x1686  ldloc.0
0x1687  ldloc.s  6
0x1689  ldloc.2
0x168a  ldloc.3
0x168b  call     instance void Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::AddNewActivityButtons(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Menu menu, class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition> commands, class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata> activities, int32 menuSectionSequence, int32 menuSectionIndex)
0x1690  ldarg.0
0x1691  ldloc.0
0x1692  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::ToArray()
0x1697  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_commands
0x169c  ldarg.0
0x169d  ldloc.1
0x169e  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::RenderXml(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer)
0x16a3  stfld    string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_layoutXml
0x16a8  ldarg.0
0x16a9  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_commands
0x16ae  ldlen
0x16af  brtrue.s loc_16B7
0x16b1  ldarg.0
0x16b2  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::AddRootNodeDisableDisplayRule()
0x16b7  ret
```
