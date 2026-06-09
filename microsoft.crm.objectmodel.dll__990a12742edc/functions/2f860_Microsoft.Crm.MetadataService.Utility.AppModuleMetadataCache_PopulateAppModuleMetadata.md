# Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::PopulateAppModuleMetadata

- ea: `0x2f860`
- end: `0x2f995`
- name: `Microsoft.Crm.MetadataService.Utility.AppModuleMetadataCache::PopulateAppModuleMetadata`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x2f790`

## callees

- `0x2c680`
- `0x2c6a0`
- `0x2c6c0`
- `0x2c760`
- `0x2c7e0`
- `0x2c820`
- `0x2c840`
- `0x2c860`
- `0x2c880`
- `0x2c8a0`
- `0x2c8c0`
- `0x2f860`

## string_xrefs

- `0x2f872`: `componenttype`
- `0x2f89e`: `componentid`
- `0x2f888`: `componentsubtype`
- `0x2f8ee`: `parentcomponentid`
- `0x2f8b4`: `componentversion`
- `0x2f8ca`: `componentisdefault`
- `0x2f900`: `componentisquickfindquery`
- `0x2f916`: `componentisuserview`
- `0x2f92c`: `componentisuserchart`
- `0x2f942`: `componentisuserform`
- `0x2f958`: `componentistabletenabled`
- `0x2f96e`: `componentstatecode`

## pseudocode

```c

```

## disassembly

```asm
0x2f860  ldarg.1
0x2f861  ldstr    aAppmoduleid// "appmoduleid"
0x2f866  ldarg.2
0x2f867  box      [mscorlib]System.Guid
0x2f86c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2f871  ldarg.1
0x2f872  ldstr    aComponenttype// "componenttype"
0x2f877  ldarg.3
0x2f878  callvirt instance int32 Microsoft.Crm.MetadataService.Utility.BaseInfo::get_Type()
0x2f87d  box      [mscorlib]System.Int32
0x2f882  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2f887  ldarg.1
0x2f888  ldstr    aComponentsubty// "componentsubtype"
0x2f88d  ldarg.3
0x2f88e  callvirt instance int32 Microsoft.Crm.MetadataService.Utility.NodeInfo::get_SubType()
0x2f893  box      [mscorlib]System.Int32
0x2f898  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2f89d  ldarg.1
0x2f89e  ldstr    aComponentid// "componentid"
0x2f8a3  ldarg.3
0x2f8a4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.MetadataService.Utility.BaseInfo::get_Id()
0x2f8a9  box      [mscorlib]System.Guid
0x2f8ae  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2f8b3  ldarg.1
0x2f8b4  ldstr    aComponentversi// "componentversion"
0x2f8b9  ldarg.3
0x2f8ba  callvirt instance int64 Microsoft.Crm.MetadataService.Utility.BaseInfo::get_Version()
0x2f8bf  box      [mscorlib]System.Int64
0x2f8c4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2f8c9  ldarg.1
0x2f8ca  ldstr    aComponentisdef// "componentisdefault"
0x2f8cf  ldarg.3
0x2f8d0  callvirt instance bool Microsoft.Crm.MetadataService.Utility.RootNodeInfo::get_IsDefault()
0x2f8d5  box      [mscorlib]System.Boolean
0x2f8da  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2f8df  ldarg.s  4
0x2f8e1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2f8e6  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2f8eb  brfalse.s loc_2F8FF
0x2f8ed  ldarg.1
0x2f8ee  ldstr    aParentcomponen// "parentcomponentid"
0x2f8f3  ldarg.s  4
0x2f8f5  box      [mscorlib]System.Guid
0x2f8fa  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2f8ff  ldarg.1
0x2f900  ldstr    aComponentisqui// "componentisquickfindquery"
0x2f905  ldarg.3
0x2f906  callvirt instance bool Microsoft.Crm.MetadataService.Utility.RootNodeInfo::get_IsQuickFindQuery()
0x2f90b  box      [mscorlib]System.Boolean
0x2f910  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2f915  ldarg.1
0x2f916  ldstr    aComponentisuse// "componentisuserview"
0x2f91b  ldarg.3
0x2f91c  callvirt instance bool Microsoft.Crm.MetadataService.Utility.RootNodeInfo::get_IsUserView()
0x2f921  box      [mscorlib]System.Boolean
0x2f926  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2f92b  ldarg.1
0x2f92c  ldstr    aComponentisuse_0// "componentisuserchart"
0x2f931  ldarg.3
0x2f932  callvirt instance bool Microsoft.Crm.MetadataService.Utility.RootNodeInfo::get_IsUserChart()
0x2f937  box      [mscorlib]System.Boolean
0x2f93c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2f941  ldarg.1
0x2f942  ldstr    aComponentisuse_1// "componentisuserform"
0x2f947  ldarg.3
0x2f948  callvirt instance bool Microsoft.Crm.MetadataService.Utility.RootNodeInfo::get_IsUserForm()
0x2f94d  box      [mscorlib]System.Boolean
0x2f952  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2f957  ldarg.1
0x2f958  ldstr    aComponentistab// "componentistabletenabled"
0x2f95d  ldarg.3
0x2f95e  callvirt instance bool Microsoft.Crm.MetadataService.Utility.RootNodeInfo::get_IsTabletEnabled()
0x2f963  box      [mscorlib]System.Boolean
0x2f968  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2f96d  ldarg.1
0x2f96e  ldstr    aComponentstate// "componentstatecode"
0x2f973  ldarg.3
0x2f974  callvirt instance int32 Microsoft.Crm.MetadataService.Utility.RootNodeInfo::get_StateCode()
0x2f979  box      [mscorlib]System.Int32
0x2f97e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2f983  ldarg.1
0x2f984  ldstr    aState_0// "state"
0x2f989  ldc.i4.0
0x2f98a  box      [mscorlib]System.Int32
0x2f98f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2f994  ret
```
