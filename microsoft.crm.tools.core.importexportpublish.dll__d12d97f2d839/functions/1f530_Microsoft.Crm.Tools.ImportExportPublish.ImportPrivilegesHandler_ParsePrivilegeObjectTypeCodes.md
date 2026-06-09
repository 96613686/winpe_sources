# Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::ParsePrivilegeObjectTypeCodes

- ea: `0x1f530`
- end: `0x1f84c`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::ParsePrivilegeObjectTypeCodes`
- size: `796`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1f110`

## callees

- `0x1f260`
- `0x1f530`
- `0x1f890`
- `0x1fab0`
- `0x95bf0`

## string_xrefs

- `0x1f66d`: `privilegeid`
- `0x1f531`: `privilegeobjecttypecodeslist`
- `0x1f54d`: `privilegeobjecttypecodes`
- `0x1f693`: `privilegeobjecttypecodeid`
- `0x1f76b`: `Cannot overwrite existing PrivilegeObjectTypeCode for privilege {0} and object typ code {1} which already exists with Solution {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x1f530  ldarg.1
0x1f531  ldstr    aPrivilegeobjec_2// "privilegeobjecttypecodeslist"
0x1f536  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1f53b  stloc.0
0x1f53c  ldloc.0
0x1f53d  brtrue.s loc_1F540
0x1f53f  ret
0x1f540  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::.ctor()
0x1f545  stloc.1
0x1f546  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x1f54b  stloc.2
0x1f54c  ldloc.0
0x1f54d  ldstr    aPrivilegeobjec_3// "privilegeobjecttypecodes"
0x1f552  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x1f557  stloc.3
0x1f558  ldloc.3
0x1f559  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x1f55e  stloc.s  4
0x1f560  br       loc_1F5FE
0x1f565  ldloc.s  4
0x1f567  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1f56c  castclass [System.Xml]System.Xml.XmlNode
0x1f571  stloc.s  5
0x1f573  ldarg.0
0x1f574  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_context
0x1f579  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionFull::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f57e  stloc.s  6
0x1f580  ldloc.s  6
0x1f582  ldloc.s  5
0x1f584  ldc.i4.1
0x1f585  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::FillPropertiesFromXml(class [System.Xml]System.Xml.XmlNode, bool)
0x1f58a  ldarg.0
0x1f58b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionFull> Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_privilegeOtcDescriptionsToImport
0x1f590  ldloc.s  6
0x1f592  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionFull>::Add(var<u1>)
0x1f597  ldloc.s  6
0x1f599  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::get_PrivilegeId()
0x1f59e  stloc.s  8
0x1f5a0  ldloca.s 8
0x1f5a2  constrained. [mscorlib]System.Guid
0x1f5a8  callvirt instance string [mscorlib]System.Object::ToString()
0x1f5ad  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x1f5b2  ldloc.s  6
0x1f5b4  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::get_ObjectTypeCode()
0x1f5b9  stloc.s  9
0x1f5bb  ldloca.s 9
0x1f5bd  call     instance string [mscorlib]System.Int32::ToString()
0x1f5c2  call     string [mscorlib]System.String::Concat(string, string)
0x1f5c7  stloc.s  7
0x1f5c9  ldloc.1
0x1f5ca  ldloc.s  7
0x1f5cc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::ContainsKey(var<u1>)
0x1f5d1  brtrue.s loc_1F5E2
0x1f5d3  ldloc.1
0x1f5d4  ldloc.s  7
0x1f5d6  ldloc.s  6
0x1f5d8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::get_PrivilegeObjectTypeCodeId()
0x1f5dd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x1f5e2  ldloc.2
0x1f5e3  ldloc.s  6
0x1f5e5  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::get_ObjectTypeCode()
0x1f5ea  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<int32>::Contains(var<u1>)
0x1f5ef  brtrue.s loc_1F5FE
0x1f5f1  ldloc.2
0x1f5f2  ldloc.s  6
0x1f5f4  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::get_ObjectTypeCode()
0x1f5f9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x1f5fe  ldloc.s  4
0x1f600  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f605  brtrue   loc_1F565
0x1f60a  leave.s  loc_1F62B
0x1f60c  ldloc.s  4
0x1f60e  isinst   [mscorlib]System.IDisposable
0x1f613  stloc.s  0xA
0x1f615  ldloc.s  0xA
0x1f617  brfalse.s loc_1F620
0x1f619  ldloc.s  0xA
0x1f61b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f620  endfinally
0x1f621  ldloc.3
0x1f622  brfalse.s loc_1F62A
0x1f624  ldloc.3
0x1f625  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f62a  endfinally
0x1f62b  ldarg.0
0x1f62c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionFull> Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_privilegeOtcDescriptionsToImport
0x1f631  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionFull>::get_Count()
0x1f636  ldc.i4.0
0x1f637  ble      loc_1F84B
0x1f63c  newobj   instance void <>c__DisplayClass14_0::.ctor()
0x1f641  stloc.s  0xB
0x1f643  ldarg.0
0x1f644  ldloc.2
0x1f645  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::RetrieveExistingPrivilegeOtcs(class [mscorlib]System.Collections.Generic.List`1<int32> objectTypeCodes)
0x1f64a  ldloc.s  0xB
0x1f64c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x1f651  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass14_0::privilegeOtcsToExcludeFromCreate
0x1f656  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x1f65b  stloc.s  0xC
0x1f65d  br       loc_1F7BD
0x1f662  ldloc.s  0xC
0x1f664  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x1f669  stloc.s  0xD
0x1f66b  ldloc.s  0xD
0x1f66d  ldstr    aPrivilegeid// "privilegeid"
0x1f672  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1f677  unbox.any [mscorlib]System.Guid
0x1f67c  stloc.s  0xE
0x1f67e  ldloc.s  0xD
0x1f680  ldstr    aObjecttypecode_0// "objecttypecode"
0x1f685  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1f68a  unbox.any [mscorlib]System.Int32
0x1f68f  stloc.s  0xF
0x1f691  ldloc.s  0xD
0x1f693  ldstr    aPrivilegeobjec_5// "privilegeobjecttypecodeid"
0x1f698  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1f69d  unbox.any [mscorlib]System.Guid
0x1f6a2  stloc.s  0x10
0x1f6a4  ldloc.s  0xD
0x1f6a6  ldstr    aSolutionid// "solutionid"
0x1f6ab  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1f6b0  unbox.any [mscorlib]System.Guid
0x1f6b5  stloc.s  0x11
0x1f6b7  ldarg.0
0x1f6b8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_context
0x1f6bd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1f6c2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x1f6c7  stloc.s  0x12
0x1f6c9  ldloca.s 0xE
0x1f6cb  constrained. [mscorlib]System.Guid
0x1f6d1  callvirt instance string [mscorlib]System.Object::ToString()
0x1f6d6  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x1f6db  ldloca.s 0xF
0x1f6dd  call     instance string [mscorlib]System.Int32::ToString()
0x1f6e2  call     string [mscorlib]System.String::Concat(string, string)
0x1f6e7  stloc.s  0x13
0x1f6e9  ldloc.1
0x1f6ea  ldloc.s  0x13
0x1f6ec  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::ContainsKey(var<u1>)
0x1f6f1  brfalse  loc_1F7BD
0x1f6f6  ldarg.0
0x1f6f7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_context
0x1f6fc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1f701  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x1f706  ldc.i4.8
0x1f707  beq.s    loc_1F739
0x1f709  ldarg.0
0x1f70a  ldloc.s  0x10
0x1f70c  ldc.i4.s 0x11
0x1f70e  ldloc.s  0x12
0x1f710  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::DoesComponentExistInSolution(valuetype [mscorlib]System.Guid objectId, int32 componentType, valuetype [mscorlib]System.Guid solutionId)
0x1f715  brtrue.s loc_1F739
0x1f717  ldloc.s  0x11
0x1f719  ldloc.s  0x12
0x1f71b  ldarg.0
0x1f71c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_context
0x1f721  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.SolutionHelper::IsHoldingSolution(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f726  brtrue.s loc_1F739
0x1f728  ldloc.s  0x11
0x1f72a  ldloc.s  0x12
0x1f72c  ldarg.0
0x1f72d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_context
0x1f732  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.SolutionHelper::IsInernalSystemConvertedParentOrSiblingSolution(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f737  brfalse.s loc_1F766
0x1f739  ldarg.0
0x1f73a  ldloc.1
0x1f73b  ldloc.s  0x13
0x1f73d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::get_Item(void)
0x1f742  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionPropertyBag Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::GetPrivlegeOtcPropertyBagToImport(valuetype [mscorlib]System.Guid privilegeOtcId)
0x1f747  stloc.s  0x14
0x1f749  ldloc.s  0x14
0x1f74b  brfalse.s loc_1F7A9
0x1f74d  ldloc.s  0x14
0x1f74f  ldloc.s  0x10
0x1f751  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::set_PrivilegeObjectTypeCodeId(valuetype [mscorlib]System.Guid)
0x1f756  ldarg.0
0x1f757  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_metadataHelper
0x1f75c  ldloc.s  0x14
0x1f75e  ldc.i4.1
0x1f75f  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IPrivilegeObjectTypeCodeDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType)
0x1f764  br.s     loc_1F7A9
0x1f766  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f76b  ldstr    aCannotOverwrit_0// "Cannot overwrite existing PrivilegeObje"...
0x1f770  ldc.i4.3
0x1f771  newarr   [mscorlib]System.Object
0x1f776  dup
0x1f777  ldc.i4.0
0x1f778  ldloc.s  0xE
0x1f77a  box      [mscorlib]System.Guid
0x1f77f  stelem.ref
0x1f780  dup
0x1f781  ldc.i4.1
0x1f782  ldloc.s  0xF
0x1f784  box      [mscorlib]System.Int32
0x1f789  stelem.ref
0x1f78a  dup
0x1f78b  ldc.i4.2
0x1f78c  ldloc.s  0xD
0x1f78e  ldstr    aSolutionid// "solutionid"
0x1f793  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1f798  stelem.ref
0x1f799  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1f79e  ldc.i4   0x80048000
0x1f7a3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1f7a8  throw
0x1f7a9  ldloc.s  0xB
0x1f7ab  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass14_0::privilegeOtcsToExcludeFromCreate
0x1f7b0  ldloc.1
0x1f7b1  ldloc.s  0x13
0x1f7b3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::get_Item(void)
0x1f7b8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x1f7bd  ldloc.s  0xC
0x1f7bf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f7c4  brtrue   loc_1F662
0x1f7c9  leave.s  loc_1F7D7
0x1f7cb  ldloc.s  0xC
0x1f7cd  brfalse.s loc_1F7D6
0x1f7cf  ldloc.s  0xC
0x1f7d1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f7d6  endfinally
0x1f7d7  ldloc.1
0x1f7d8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::get_Values()
0x1f7dd  ldloc.s  0xB
0x1f7df  ldfld    class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, bool> <>c__DisplayClass14_0::<>9__0
0x1f7e4  dup
0x1f7e5  brtrue.s loc_1F801
0x1f7e7  pop
0x1f7e8  ldloc.s  0xB
0x1f7ea  ldloc.s  0xB
0x1f7ec  ldftn    instance bool <>c__DisplayClass14_0::<ParsePrivilegeObjectTypeCodes>b__0(valuetype [mscorlib]System.Guid p)
0x1f7f2  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, bool>::.ctor(object, native int)
0x1f7f7  dup
0x1f7f8  stloc.s  0x16
0x1f7fa  stfld    class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, bool> <>c__DisplayClass14_0::<>9__0
0x1f7ff  ldloc.s  0x16
0x1f801  call     T0x2B00001F
0x1f806  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x1f80b  stloc.s  0x15
0x1f80d  br.s     loc_1F834
0x1f80f  ldloc.s  0x15
0x1f811  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0x1f816  stloc.s  0x17
0x1f818  ldarg.0
0x1f819  ldloc.s  0x17
0x1f81b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionPropertyBag Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::GetPrivlegeOtcPropertyBagToImport(valuetype [mscorlib]System.Guid privilegeOtcId)
0x1f820  stloc.s  0x18
0x1f822  ldloc.s  0x18
0x1f824  brfalse.s loc_1F834
0x1f826  ldarg.0
0x1f827  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper Microsoft.Crm.Tools.ImportExportPublish.ImportPrivilegesHandler::_metadataHelper
0x1f82c  ldloc.s  0x18
0x1f82e  ldc.i4.0
0x1f82f  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IPrivilegeObjectTypeCodeDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType)
0x1f834  ldloc.s  0x15
0x1f836  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f83b  brtrue.s loc_1F80F
0x1f83d  leave.s  loc_1F84B
0x1f83f  ldloc.s  0x15
0x1f841  brfalse.s loc_1F84A
0x1f843  ldloc.s  0x15
0x1f845  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f84a  endfinally
0x1f84b  ret
```
