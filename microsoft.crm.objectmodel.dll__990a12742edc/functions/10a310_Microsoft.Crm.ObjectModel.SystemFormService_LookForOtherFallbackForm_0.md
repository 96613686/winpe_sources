# Microsoft.Crm.ObjectModel.SystemFormService::LookForOtherFallbackForm_0

- ea: `0x10a310`
- end: `0x10a660`
- name: `Microsoft.Crm.ObjectModel.SystemFormService::LookForOtherFallbackForm_0`
- size: `848`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1091c0`
- `0x10a1d0`

## callees

- `0x107c90`
- `0x108430`
- `0x109660`
- `0x109a40`
- `0x10a310`

## string_xrefs

- `0x10a37a`: `formxml`
- `0x10a415`: `formxml`
- `0x10a538`: `formxml`
- `0x10a5d3`: `formxml`
- `0x10a5f1`: `formjson`
- `0x10a5ff`: `formjson`

## pseudocode

```c

```

## disassembly

```asm
0x10a310  ldarg.2
0x10a311  ldc.i4.2
0x10a312  beq.s    loc_10A319
0x10a314  ldarg.2
0x10a315  ldc.i4.5
0x10a316  beq.s    loc_10A319
0x10a318  ret
0x10a319  ldarg.s  4
0x10a31b  stloc.3
0x10a31c  ldc.i4   0x8004F654
0x10a321  stloc.s  4
0x10a323  ldloca.s 3
0x10a325  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x10a32a  ldloc.s  4
0x10a32c  ceq
0x10a32e  ldloca.s 3
0x10a330  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x10a335  and
0x10a336  brtrue.s loc_10A344
0x10a338  ldarga.s 4
0x10a33a  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x10a33f  ldc.i4.0
0x10a340  ceq
0x10a342  br.s     loc_10A345
0x10a344  ldc.i4.1
0x10a345  ldstr    aExpectingError// "Expecting error code to be either Error"...
0x10a34a  ldc.i4.1
0x10a34b  newarr   [mscorlib]System.Object
0x10a350  dup
0x10a351  ldc.i4.0
0x10a352  ldarg.s  4
0x10a354  box      valuetype [mscorlib]System.Nullable`1<int32>
0x10a359  stelem.ref
0x10a35a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x10a35f  ldstr    aSystemform// "SystemForm"
0x10a364  ldarg.s  5
0x10a366  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x10a36b  stloc.0
0x10a36c  ldloc.0
0x10a36d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x10a372  ldc.i4.2
0x10a373  newarr   [mscorlib]System.String
0x10a378  dup
0x10a379  ldc.i4.0
0x10a37a  ldstr    aFormxml// "formxml"
0x10a37f  stelem.ref
0x10a380  dup
0x10a381  ldc.i4.1
0x10a382  ldstr    aFormid// "formid"
0x10a387  stelem.ref
0x10a388  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x10a38d  ldloc.0
0x10a38e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x10a393  ldstr    aObjecttypecode// "objecttypecode"
0x10a398  ldc.i4.0
0x10a399  ldarg.1
0x10a39a  box      [mscorlib]System.Int32
0x10a39f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x10a3a4  pop
0x10a3a5  ldloc.0
0x10a3a6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x10a3ab  ldstr    aType// "type"
0x10a3b0  ldc.i4.0
0x10a3b1  ldarg.2
0x10a3b2  box      [mscorlib]System.Int32
0x10a3b7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x10a3bc  pop
0x10a3bd  ldloc.0
0x10a3be  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Order()
0x10a3c3  ldstr    aPublishedon// "publishedon"
0x10a3c8  ldc.i4.0
0x10a3c9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x10a3ce  ldarg.3
0x10a3cf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10a3d4  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x10a3d9  brfalse.s loc_10A3F3
0x10a3db  ldloc.0
0x10a3dc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x10a3e1  ldstr    aFormid// "formid"
0x10a3e6  ldc.i4.1
0x10a3e7  ldarg.3
0x10a3e8  box      [mscorlib]System.Guid
0x10a3ed  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x10a3f2  pop
0x10a3f3  ldarg.0
0x10a3f4  ldloc.0
0x10a3f5  ldarg.s  5
0x10a3f7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x10a3fc  stloc.1
0x10a3fd  ldc.i4.0
0x10a3fe  stloc.2
0x10a3ff  ldloc.1
0x10a400  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x10a405  stloc.s  5
0x10a407  br.s     loc_10A441
0x10a409  ldloc.s  5
0x10a40b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x10a410  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x10a415  ldstr    aFormxml// "formxml"
0x10a41a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x10a41f  castclass [mscorlib]System.String
0x10a424  stloc.s  6
0x10a426  ldloc.s  6
0x10a428  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10a42d  brtrue.s loc_10A441
0x10a42f  ldloc.s  6
0x10a431  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Parse(string)
0x10a436  call     bool Microsoft.Crm.ObjectModel.SystemFormService::IsFallbackForm(class [System.Xml.Linq]System.Xml.Linq.XElement formXml)
0x10a43b  brfalse.s loc_10A441
0x10a43d  ldc.i4.1
0x10a43e  stloc.2
0x10a43f  leave.s  loc_10A461
0x10a441  ldloc.s  5
0x10a443  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10a448  brtrue.s loc_10A409
0x10a44a  leave.s  loc_10A461
0x10a44c  ldloc.s  5
0x10a44e  isinst   [mscorlib]System.IDisposable
0x10a453  stloc.s  7
0x10a455  ldloc.s  7
0x10a457  brfalse.s loc_10A460
0x10a459  ldloc.s  7
0x10a45b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10a460  endfinally
0x10a461  ldloc.2
0x10a462  brtrue   loc_10A65F
0x10a467  ldarg.s  5
0x10a469  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x10a46e  ldarg.1
0x10a46f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x10a474  stloc.s  8
0x10a476  ldarga.s 4
0x10a478  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x10a47d  brfalse.s loc_10A4AD
0x10a47f  ldarg.2
0x10a480  call     string Microsoft.Crm.ObjectModel.SystemFormService::GetFormTypeXmlName(int32 formType)
0x10a485  stloc.s  9
0x10a487  ldloc.s  8
0x10a489  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x10a48e  stloc.s  0xA
0x10a490  ldarga.s 4
0x10a492  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x10a497  ldc.i4.2
0x10a498  newarr   [mscorlib]System.Object
0x10a49d  dup
0x10a49e  ldc.i4.0
0x10a49f  ldloc.s  9
0x10a4a1  stelem.ref
0x10a4a2  dup
0x10a4a3  ldc.i4.1
0x10a4a4  ldloc.s  0xA
0x10a4a6  stelem.ref
0x10a4a7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x10a4ac  throw
0x10a4ad  ldnull
0x10a4ae  stloc.s  0xB
0x10a4b0  ldloc.s  8
0x10a4b2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomEntity()
0x10a4b7  brfalse.s loc_10A4C9
0x10a4b9  ldloc.1
0x10a4ba  ldc.i4.0
0x10a4bb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x10a4c0  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SystemForm
0x10a4c5  stloc.s  0xB
0x10a4c7  br.s     loc_10A536
0x10a4c9  ldc.i4.0
0x10a4ca  stloc.s  0xF
0x10a4cc  br.s     loc_10A501
0x10a4ce  ldloc.1
0x10a4cf  ldloc.s  0xF
0x10a4d1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x10a4d6  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SystemForm
0x10a4db  stloc.s  0x10
0x10a4dd  ldloc.s  0x10
0x10a4df  ldstr    aFormid// "formid"
0x10a4e4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x10a4e9  unbox.any [mscorlib]System.Guid
0x10a4ee  ldarg.s  5
0x10a4f0  call     bool Microsoft.Crm.ObjectModel.SystemFormService::IsOutOfBoxForm(valuetype [mscorlib]System.Guid systemFormId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10a4f5  brfalse.s loc_10A4FB
0x10a4f7  ldloc.s  0x10
0x10a4f9  stloc.s  0xB
0x10a4fb  ldloc.s  0xF
0x10a4fd  ldc.i4.1
0x10a4fe  add
0x10a4ff  stloc.s  0xF
0x10a501  ldloc.s  0xF
0x10a503  ldloc.1
0x10a504  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x10a509  bge.s    loc_10A50F
0x10a50b  ldloc.s  0xB
0x10a50d  brfalse.s loc_10A4CE
0x10a50f  ldloc.s  0xB
0x10a511  ldnull
0x10a512  cgt.un
0x10a514  ldstr    aExpectedToFind_0// "Expected to find an out-of-box form for"...
0x10a519  ldc.i4.2
0x10a51a  newarr   [mscorlib]System.Object
0x10a51f  dup
0x10a520  ldc.i4.0
0x10a521  ldarg.2
0x10a522  box      [mscorlib]System.Int32
0x10a527  stelem.ref
0x10a528  dup
0x10a529  ldc.i4.1
0x10a52a  ldarg.1
0x10a52b  box      [mscorlib]System.Int32
0x10a530  stelem.ref
0x10a531  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x10a536  ldloc.s  0xB
0x10a538  ldstr    aFormxml// "formxml"
0x10a53d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x10a542  castclass [mscorlib]System.String
0x10a547  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Parse(string)
0x10a54c  stloc.s  0xC
0x10a54e  ldloc.s  0xC
0x10a550  ldstr    aDisplayconditi// "DisplayConditions"
0x10a555  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x10a55a  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x10a55f  stloc.s  0xD
0x10a561  ldloc.s  0xD
0x10a563  brtrue.s loc_10A58E
0x10a565  ldstr    aDisplayconditi// "DisplayConditions"
0x10a56a  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x10a56f  ldstr    aEveryone// "Everyone"
0x10a574  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x10a579  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XElement::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName)
0x10a57e  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XElement::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x10a583  stloc.s  0xD
0x10a585  ldloc.s  0xC
0x10a587  ldloc.s  0xD
0x10a589  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XContainer::Add(object)
0x10a58e  ldloc.s  0xD
0x10a590  ldstr    aFallbackform// "FallbackForm"
0x10a595  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x10a59a  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x10a59f  stloc.s  0xE
0x10a5a1  ldloc.s  0xE
0x10a5a3  brtrue.s loc_10A5C5
0x10a5a5  ldstr    aFallbackform// "FallbackForm"
0x10a5aa  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x10a5af  ldc.i4.1
0x10a5b0  box      [mscorlib]System.Boolean
0x10a5b5  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x10a5ba  stloc.s  0xE
0x10a5bc  ldloc.s  0xD
0x10a5be  ldloc.s  0xE
0x10a5c0  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XContainer::Add(object)
0x10a5c5  ldloc.s  0xE
0x10a5c7  ldstr    aTrue// "true"
0x10a5cc  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::set_Value(string)
0x10a5d1  ldloc.s  0xB
0x10a5d3  ldstr    aFormxml// "formxml"
0x10a5d8  ldloc.s  0xC
0x10a5da  ldc.i4.1
0x10a5db  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XNode::ToString(valuetype [System.Xml.Linq]System.Xml.Linq.SaveOptions)
0x10a5e0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x10a5e5  ldloc.s  0xB
0x10a5e7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x10a5ec  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x10a5f1  ldstr    aFormjson// "formjson"
0x10a5f6  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x10a5fb  brfalse.s loc_10A613
0x10a5fd  ldloc.s  0xB
0x10a5ff  ldstr    aFormjson// "formjson"
0x10a604  ldarg.0
0x10a605  ldloc.s  0xB
0x10a607  ldarg.s  5
0x10a609  call     instance string Microsoft.Crm.ObjectModel.SystemFormService::GetFormJson(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10a60e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x10a613  ldarg.s  5
0x10a615  ldc.i4.0
0x10a616  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x10a61b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoSolutionOperationContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext, valuetype [mscorlib]System.Guid)
0x10a620  stloc.s  0x11
0x10a622  ldarg.0
0x10a623  ldloc.s  0xB
0x10a625  ldarg.s  5
0x10a627  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x10a62c  ldarg.0
0x10a62d  ldloc.s  0xB
0x10a62f  ldstr    aFormid// "formid"
0x10a634  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x10a639  unbox.any [mscorlib]System.Guid
0x10a63e  ldstr    aSystemform// "SystemForm"
0x10a643  ldarg.s  5
0x10a645  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x10a64a  ldarg.s  5
0x10a64c  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::PublishShared(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x10a651  leave.s  loc_10A65F
0x10a653  ldloc.s  0x11
0x10a655  brfalse.s loc_10A65E
0x10a657  ldloc.s  0x11
0x10a659  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10a65e  endfinally
0x10a65f  ret
```
