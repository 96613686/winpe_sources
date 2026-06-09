# Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::ParsePrivileges

- ea: `0x1f280`
- end: `0x1f522`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::ParsePrivileges`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1f110`

## callees

- `0x1f260`
- `0x1f280`
- `0x1f850`
- `0x1fa50`
- `0x95b80`

## string_xrefs

- `0x1f37c`: `Privilege`
- `0x1f291`: `privilege`
- `0x1f281`: `privileges`
- `0x1f381`: `privilegeid`
- `0x1f3b0`: `privilegeid`
- `0x1f44c`: `Cannot overwrite existing Privilege {0} which already exists another Solution.`

## pseudocode

```c

```

## disassembly

```asm
0x1f280  ldarg.1
0x1f281  ldstr    aPrivileges// "privileges"
0x1f286  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1f28b  stloc.0
0x1f28c  ldloc.0
0x1f28d  brtrue.s loc_1F290
0x1f28f  ret
0x1f290  ldloc.0
0x1f291  ldstr    aPrivilege_0// "privilege"
0x1f296  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x1f29b  stloc.1
0x1f29c  ldloc.1
0x1f29d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x1f2a2  stloc.2
0x1f2a3  br.s     loc_1F30F
0x1f2a5  ldloc.2
0x1f2a6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1f2ab  castclass [System.Xml]System.Xml.XmlNode
0x1f2b0  stloc.3
0x1f2b1  ldarg.0
0x1f2b2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_context
0x1f2b7  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f2bc  stloc.s  4
0x1f2be  ldloc.s  4
0x1f2c0  ldloc.3
0x1f2c1  ldc.i4.1
0x1f2c2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::FillPropertiesFromXml(class [System.Xml]System.Xml.XmlNode, bool)
0x1f2c7  ldarg.0
0x1f2c8  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionFull> Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_privilegeDescriptionsToImport
0x1f2cd  ldloc.s  4
0x1f2cf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionFull>::Add(var<u1>)
0x1f2d4  ldloc.3
0x1f2d5  ldstr    aSystemcustomiz// "systemcustomizable"
0x1f2da  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x1f2df  brfalse.s loc_1F30F
0x1f2e1  ldloc.3
0x1f2e2  ldstr    aSystemcustomiz// "systemcustomizable"
0x1f2e7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x1f2ec  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x1f2f1  ldstr    a0_1// "0"
0x1f2f6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1f2fb  brfalse.s loc_1F30F
0x1f2fd  ldarg.0
0x1f2fe  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_notSystemCustomizablePrivileges
0x1f303  ldloc.s  4
0x1f305  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescription::get_PrivilegeId()
0x1f30a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x1f30f  ldloc.2
0x1f310  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f315  brtrue.s loc_1F2A5
0x1f317  leave.s  loc_1F337
0x1f319  ldloc.2
0x1f31a  isinst   [mscorlib]System.IDisposable
0x1f31f  stloc.s  5
0x1f321  ldloc.s  5
0x1f323  brfalse.s loc_1F32C
0x1f325  ldloc.s  5
0x1f327  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f32c  endfinally
0x1f32d  ldloc.1
0x1f32e  brfalse.s loc_1F336
0x1f330  ldloc.1
0x1f331  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f336  endfinally
0x1f337  ldarg.0
0x1f338  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionFull> Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_privilegeDescriptionsToImport
0x1f33d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionFull>::get_Count()
0x1f342  ldc.i4.0
0x1f343  ble      loc_1F521
0x1f348  newobj   instance void <>c__DisplayClass13_0::.ctor()
0x1f34d  stloc.s  6
0x1f34f  ldarg.0
0x1f350  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionFull> Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_privilegeDescriptionsToImport
0x1f355  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionFull, valuetype [mscorlib]System.Guid> <>c::<>9__13_0
0x1f35a  dup
0x1f35b  brtrue.s loc_1F374
0x1f35d  pop
0x1f35e  ldsfld   class <>c <>c::<>9
0x1f363  ldftn    instance valuetype [mscorlib]System.Guid <>c::<ParsePrivileges>b__13_0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionFull p)
0x1f369  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionFull, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x1f36e  dup
0x1f36f  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionFull, valuetype [mscorlib]System.Guid> <>c::<>9__13_0
0x1f374  call     T0x2B00001E
0x1f379  stloc.s  7
0x1f37b  ldarg.0
0x1f37c  ldstr    aPrivilege// "Privilege"
0x1f381  ldstr    aPrivilegeid// "privilegeid"
0x1f386  ldloc.s  7
0x1f388  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::RetrieveMultiple(string metadatEntityName, string idPropertyName, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> metadataEntityIds)
0x1f38d  ldloc.s  6
0x1f38f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x1f394  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass13_0::existingPrivilegeIds
0x1f399  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x1f39e  stloc.s  8
0x1f3a0  br       loc_1F484
0x1f3a5  ldloc.s  8
0x1f3a7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x1f3ac  stloc.s  9
0x1f3ae  ldloc.s  9
0x1f3b0  ldstr    aPrivilegeid// "privilegeid"
0x1f3b5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1f3ba  unbox.any [mscorlib]System.Guid
0x1f3bf  stloc.s  0xA
0x1f3c1  ldloc.s  9
0x1f3c3  ldstr    aSolutionid// "solutionid"
0x1f3c8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1f3cd  unbox.any [mscorlib]System.Guid
0x1f3d2  stloc.s  0xB
0x1f3d4  ldarg.0
0x1f3d5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_context
0x1f3da  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1f3df  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x1f3e4  stloc.s  0xC
0x1f3e6  ldarg.0
0x1f3e7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_context
0x1f3ec  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1f3f1  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x1f3f6  ldc.i4.8
0x1f3f7  beq.s    loc_1F429
0x1f3f9  ldarg.0
0x1f3fa  ldloc.s  0xA
0x1f3fc  ldc.i4.s 0x10
0x1f3fe  ldloc.s  0xC
0x1f400  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::DoesComponentExistInSolution(valuetype [mscorlib]System.Guid objectId, int32 componentType, valuetype [mscorlib]System.Guid solutionId)
0x1f405  brtrue.s loc_1F429
0x1f407  ldloc.s  0xB
0x1f409  ldloc.s  0xC
0x1f40b  ldarg.0
0x1f40c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_context
0x1f411  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.SolutionHelper::IsHoldingSolution(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f416  brtrue.s loc_1F429
0x1f418  ldloc.s  0xB
0x1f41a  ldloc.s  0xC
0x1f41c  ldarg.0
0x1f41d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_context
0x1f422  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.SolutionHelper::IsInernalSystemConvertedParentOrSiblingSolution(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f427  brfalse.s loc_1F447
0x1f429  ldarg.0
0x1f42a  ldloc.s  0xA
0x1f42c  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::GetPrivlegePropertyBagToImport(valuetype [mscorlib]System.Guid privilegeId)
0x1f431  stloc.s  0xD
0x1f433  ldloc.s  0xD
0x1f435  brfalse.s loc_1F476
0x1f437  ldarg.0
0x1f438  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_metadataHelper
0x1f43d  ldloc.s  0xD
0x1f43f  ldc.i4.1
0x1f440  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IPrivilegeDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType)
0x1f445  br.s     loc_1F476
0x1f447  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f44c  ldstr    aCannotOverwrit// "Cannot overwrite existing Privilege {0}"...
0x1f451  ldc.i4.1
0x1f452  newarr   [mscorlib]System.Object
0x1f457  dup
0x1f458  ldc.i4.0
0x1f459  ldloc.s  9
0x1f45b  ldstr    aName// "name"
0x1f460  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1f465  stelem.ref
0x1f466  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1f46b  ldc.i4   0x80048000
0x1f470  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1f475  throw
0x1f476  ldloc.s  6
0x1f478  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass13_0::existingPrivilegeIds
0x1f47d  ldloc.s  0xA
0x1f47f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x1f484  ldloc.s  8
0x1f486  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f48b  brtrue   loc_1F3A5
0x1f490  leave.s  loc_1F49E
0x1f492  ldloc.s  8
0x1f494  brfalse.s loc_1F49D
0x1f496  ldloc.s  8
0x1f498  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f49d  endfinally
0x1f49e  ldloc.s  7
0x1f4a0  ldloc.s  6
0x1f4a2  ldfld    class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, bool> <>c__DisplayClass13_0::<>9__1
0x1f4a7  dup
0x1f4a8  brtrue.s loc_1F4C4
0x1f4aa  pop
0x1f4ab  ldloc.s  6
0x1f4ad  ldloc.s  6
0x1f4af  ldftn    instance bool <>c__DisplayClass13_0::<ParsePrivileges>b__1(valuetype [mscorlib]System.Guid p)
0x1f4b5  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, bool>::.ctor(object, native int)
0x1f4ba  dup
0x1f4bb  stloc.s  0xF
0x1f4bd  stfld    class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, bool> <>c__DisplayClass13_0::<>9__1
0x1f4c2  ldloc.s  0xF
0x1f4c4  call     T0x2B00001F
0x1f4c9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x1f4ce  stloc.s  0xE
0x1f4d0  br.s     loc_1F50A
0x1f4d2  ldloc.s  0xE
0x1f4d4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0x1f4d9  stloc.s  0x10
0x1f4db  ldarg.0
0x1f4dc  ldloc.s  0x10
0x1f4de  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::GetPrivlegePropertyBagToImport(valuetype [mscorlib]System.Guid privilegeId)
0x1f4e3  stloc.s  0x11
0x1f4e5  ldloc.s  0x11
0x1f4e7  brfalse.s loc_1F50A
0x1f4e9  ldarg.0
0x1f4ea  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege> Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_rolePrivileges
0x1f4ef  ldc.i4.3
0x1f4f0  ldloc.s  0x10
0x1f4f2  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::.ctor(int32, valuetype [mscorlib]System.Guid)
0x1f4f7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege>::Add(var<u1>)
0x1f4fc  ldarg.0
0x1f4fd  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_metadataHelper
0x1f502  ldloc.s  0x11
0x1f504  ldc.i4.0
0x1f505  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IPrivilegeDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType)
0x1f50a  ldloc.s  0xE
0x1f50c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f511  brtrue.s loc_1F4D2
0x1f513  leave.s  loc_1F521
0x1f515  ldloc.s  0xE
0x1f517  brfalse.s loc_1F520
0x1f519  ldloc.s  0xE
0x1f51b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f520  endfinally
0x1f521  ret
```
