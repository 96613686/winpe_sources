# Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1::CreateRuntimeDependencies

- ea: `0x1bb5f0`
- end: `0x1bb766`
- name: `Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1::CreateRuntimeDependencies`
- size: `374`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x16acc0`
- `0x16ad90`
- `0x1bb5f0`

## string_xrefs

- `0x1bb602`: `fetchxml`
- `0x1bb60f`: `fetchxml`
- `0x1bb61f`: `fetchxml`
- `0x1bb63c`: `columnsetxml`
- `0x1bb649`: `columnsetxml`
- `0x1bb659`: `columnsetxml`
- `0x1bb676`: `layoutxml`
- `0x1bb683`: `layoutxml`
- `0x1bb693`: `layoutxml`

## pseudocode

```c

```

## disassembly

```asm
0x1bb5f0  newobj   instance void Microsoft.Crm.ObjectModel.UserQueryRuntimeDependencyHelper::.ctor()
0x1bb5f5  ldarg.1
0x1bb5f6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x1bb5fb  dup
0x1bb5fc  brtrue.s loc_1BB602
0x1bb5fe  pop
0x1bb5ff  ldc.i4.0
0x1bb600  br.s     loc_1BB60C
0x1bb602  ldstr    aFetchxml// "fetchxml"
0x1bb607  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::Contains(string)
0x1bb60c  brfalse.s loc_1BB61B
0x1bb60e  ldarg.1
0x1bb60f  ldstr    aFetchxml// "fetchxml"
0x1bb614  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1bb619  brfalse.s loc_1BB61E
0x1bb61b  ldnull
0x1bb61c  br.s     loc_1BB62E
0x1bb61e  ldarg.1
0x1bb61f  ldstr    aFetchxml// "fetchxml"
0x1bb624  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1bb629  castclass [mscorlib]System.String
0x1bb62e  stloc.0
0x1bb62f  ldarg.1
0x1bb630  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x1bb635  dup
0x1bb636  brtrue.s loc_1BB63C
0x1bb638  pop
0x1bb639  ldc.i4.0
0x1bb63a  br.s     loc_1BB646
0x1bb63c  ldstr    aColumnsetxml// "columnsetxml"
0x1bb641  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::Contains(string)
0x1bb646  brfalse.s loc_1BB655
0x1bb648  ldarg.1
0x1bb649  ldstr    aColumnsetxml// "columnsetxml"
0x1bb64e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1bb653  brfalse.s loc_1BB658
0x1bb655  ldnull
0x1bb656  br.s     loc_1BB668
0x1bb658  ldarg.1
0x1bb659  ldstr    aColumnsetxml// "columnsetxml"
0x1bb65e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1bb663  castclass [mscorlib]System.String
0x1bb668  stloc.1
0x1bb669  ldarg.1
0x1bb66a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x1bb66f  dup
0x1bb670  brtrue.s loc_1BB676
0x1bb672  pop
0x1bb673  ldc.i4.0
0x1bb674  br.s     loc_1BB680
0x1bb676  ldstr    aLayoutxml// "layoutxml"
0x1bb67b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::Contains(string)
0x1bb680  brfalse.s loc_1BB68F
0x1bb682  ldarg.1
0x1bb683  ldstr    aLayoutxml// "layoutxml"
0x1bb688  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1bb68d  brfalse.s loc_1BB692
0x1bb68f  ldnull
0x1bb690  br.s     loc_1BB6A2
0x1bb692  ldarg.1
0x1bb693  ldstr    aLayoutxml// "layoutxml"
0x1bb698  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1bb69d  castclass [mscorlib]System.String
0x1bb6a2  stloc.2
0x1bb6a3  ldarg.1
0x1bb6a4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x1bb6a9  dup
0x1bb6aa  brtrue.s loc_1BB6B0
0x1bb6ac  pop
0x1bb6ad  ldc.i4.0
0x1bb6ae  br.s     loc_1BB6BA
0x1bb6b0  ldstr    aUserqueryid// "userqueryid"
0x1bb6b5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::Contains(string)
0x1bb6ba  brfalse.s loc_1BB6C9
0x1bb6bc  ldarg.1
0x1bb6bd  ldstr    aUserqueryid// "userqueryid"
0x1bb6c2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1bb6c7  brfalse.s loc_1BB6D0
0x1bb6c9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1bb6ce  br.s     loc_1BB6E0
0x1bb6d0  ldarg.1
0x1bb6d1  ldstr    aUserqueryid// "userqueryid"
0x1bb6d6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1bb6db  unbox.any [mscorlib]System.Guid
0x1bb6e0  stloc.3
0x1bb6e1  ldarg.1
0x1bb6e2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x1bb6e7  dup
0x1bb6e8  brtrue.s loc_1BB6EE
0x1bb6ea  pop
0x1bb6eb  ldc.i4.0
0x1bb6ec  br.s     loc_1BB6F8
0x1bb6ee  ldstr    aReturnedtypeco// "returnedtypecode"
0x1bb6f3  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::Contains(string)
0x1bb6f8  brfalse.s loc_1BB707
0x1bb6fa  ldarg.1
0x1bb6fb  ldstr    aReturnedtypeco// "returnedtypecode"
0x1bb700  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1bb705  brfalse.s loc_1BB70A
0x1bb707  ldc.i4.0
0x1bb708  br.s     loc_1BB71A
0x1bb70a  ldarg.1
0x1bb70b  ldstr    aReturnedtypeco// "returnedtypecode"
0x1bb710  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1bb715  unbox.any [mscorlib]System.Int32
0x1bb71a  stloc.s  4
0x1bb71c  ldarg.1
0x1bb71d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x1bb722  dup
0x1bb723  brtrue.s loc_1BB729
0x1bb725  pop
0x1bb726  ldc.i4.0
0x1bb727  br.s     loc_1BB733
0x1bb729  ldstr    aQuerytype// "querytype"
0x1bb72e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::Contains(string)
0x1bb733  brfalse.s loc_1BB742
0x1bb735  ldarg.1
0x1bb736  ldstr    aQuerytype// "querytype"
0x1bb73b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1bb740  brfalse.s loc_1BB745
0x1bb742  ldc.i4.m1
0x1bb743  br.s     loc_1BB755
0x1bb745  ldarg.1
0x1bb746  ldstr    aQuerytype// "querytype"
0x1bb74b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1bb750  unbox.any Microsoft.Crm.ObjectModel.SavedQueryType
0x1bb755  stloc.s  5
0x1bb757  ldloc.0
0x1bb758  ldloc.1
0x1bb759  ldloc.2
0x1bb75a  ldloc.3
0x1bb75b  ldloc.s  4
0x1bb75d  ldloc.s  5
0x1bb75f  ldarg.2
0x1bb760  callvirt instance void Microsoft.Crm.ObjectModel.UserQueryRuntimeDependencyHelper::SetUserQueryRuntimeDependencies(string fetchXml, string columnsetXml, string layoutXml, valuetype [mscorlib]System.Guid entityId, int32 returnedTypeCode, valuetype Microsoft.Crm.ObjectModel.SavedQueryType queryType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1bb765  ret
```
