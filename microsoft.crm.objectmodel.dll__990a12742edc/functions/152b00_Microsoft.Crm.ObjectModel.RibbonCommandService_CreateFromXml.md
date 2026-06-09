# Microsoft.Crm.ObjectModel.RibbonCommandService::CreateFromXml

- ea: `0x152b00`
- end: `0x152d31`
- name: `Microsoft.Crm.ObjectModel.RibbonCommandService::CreateFromXml`
- size: `561`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1543c0`

## callees

- `0x152b00`
- `0x155dc0`
- `0x155e60`

## string_xrefs

- `0x152b40`: `RibbonCommand`
- `0x152d1e`: `RibbonCommand`
- `0x152b70`: `command`
- `0x152c26`: `command`
- `0x152bbd`: `ribboncommandid`
- `0x152d0f`: `ribboncommandid`
- `0x152b01`: `commandDefinition`
- `0x152b11`: `CommandDefinition`
- `0x152b20`: `Expecting xml element to be node of type 'CommandDefinition'.`
- `0x152bc5`: `commanddefinition`
- `0x152c33`: `commanddefinition`
- `0x152c96`: `commanddefinition`
- `0x152cb6`: `commanddefinition`
- `0x152cd5`: `commanddefinition`
- `0x152be6`: `Found more than one RibbonCommand with command {0}, entity {1}, and parent RibbonCustomization {2}`

## pseudocode

```c

```

## disassembly

```asm
0x152b00  ldarg.1
0x152b01  ldstr    aCommanddefinit// "commandDefinition"
0x152b06  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x152b0b  ldarg.1
0x152b0c  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XElement::get_Name()
0x152b11  ldstr    aCommanddefinit_0// "CommandDefinition"
0x152b16  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x152b1b  call     bool [System.Xml.Linq]System.Xml.Linq.XName::op_Equality(class [System.Xml.Linq]System.Xml.Linq.XName, class [System.Xml.Linq]System.Xml.Linq.XName)
0x152b20  ldstr    aExpectingXmlEl// "Expecting xml element to be node of typ"...
0x152b25  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x152b2a  ldarg.1
0x152b2b  ldstr    aId_0// "Id"
0x152b30  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x152b35  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x152b3a  call     string [System.Xml.Linq]System.Xml.Linq.XAttribute::op_Explicit(class [System.Xml.Linq]System.Xml.Linq.XAttribute)
0x152b3f  stloc.0
0x152b40  ldstr    aRibboncommand// "RibbonCommand"
0x152b45  ldarg.s  5
0x152b47  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x152b4c  stloc.1
0x152b4d  ldloc.1
0x152b4e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x152b53  ldstr    aRibboncustomiz_0// "ribboncustomizationid"
0x152b58  ldc.i4.0
0x152b59  ldarg.2
0x152b5a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x152b5f  box      [mscorlib]System.Guid
0x152b64  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x152b69  pop
0x152b6a  ldloc.1
0x152b6b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x152b70  ldstr    aCommand// "command"
0x152b75  ldc.i4.0
0x152b76  ldloc.0
0x152b77  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x152b7c  pop
0x152b7d  ldarg.s  4
0x152b7f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x152b84  brfalse.s loc_152B9B
0x152b86  ldloc.1
0x152b87  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x152b8c  ldstr    aEntity_0// "entity"
0x152b91  ldc.i4.s 0xC
0x152b93  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x152b98  pop
0x152b99  br.s     loc_152BAF
0x152b9b  ldloc.1
0x152b9c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x152ba1  ldstr    aEntity_0// "entity"
0x152ba6  ldc.i4.0
0x152ba7  ldarg.s  4
0x152ba9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x152bae  pop
0x152baf  ldloc.1
0x152bb0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x152bb5  ldc.i4.2
0x152bb6  newarr   [mscorlib]System.String
0x152bbb  dup
0x152bbc  ldc.i4.0
0x152bbd  ldstr    aRibboncommandi// "ribboncommandid"
0x152bc2  stelem.ref
0x152bc3  dup
0x152bc4  ldc.i4.1
0x152bc5  ldstr    aCommanddefinit_1// "commanddefinition"
0x152bca  stelem.ref
0x152bcb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x152bd0  ldarg.0
0x152bd1  ldloc.1
0x152bd2  ldarg.s  5
0x152bd4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x152bd9  stloc.2
0x152bda  ldloc.2
0x152bdb  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x152be0  ldc.i4.1
0x152be1  cgt
0x152be3  ldc.i4.0
0x152be4  ceq
0x152be6  ldstr    aFoundMoreThanO// "Found more than one RibbonCommand with "...
0x152beb  ldc.i4.3
0x152bec  newarr   [mscorlib]System.Object
0x152bf1  dup
0x152bf2  ldc.i4.0
0x152bf3  ldloc.0
0x152bf4  stelem.ref
0x152bf5  dup
0x152bf6  ldc.i4.1
0x152bf7  ldarg.s  4
0x152bf9  stelem.ref
0x152bfa  dup
0x152bfb  ldc.i4.2
0x152bfc  ldarg.2
0x152bfd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x152c02  box      [mscorlib]System.Guid
0x152c07  stelem.ref
0x152c08  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x152c0d  newobj   instance void Microsoft.Crm.ObjectModel.RibbonImportResult::.ctor()
0x152c12  stloc.3
0x152c13  ldloc.2
0x152c14  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x152c19  brtrue.s loc_152C83
0x152c1b  ldarg.s  5
0x152c1d  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.RibbonCommand::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x152c22  stloc.s  4
0x152c24  ldloc.s  4
0x152c26  ldstr    aCommand// "command"
0x152c2b  ldloc.0
0x152c2c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x152c31  ldloc.s  4
0x152c33  ldstr    aCommanddefinit_1// "commanddefinition"
0x152c38  ldarg.1
0x152c39  ldc.i4.1
0x152c3a  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XNode::ToString(valuetype [System.Xml.Linq]System.Xml.Linq.SaveOptions)
0x152c3f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x152c44  ldloc.s  4
0x152c46  ldstr    aEntity_0// "entity"
0x152c4b  ldarg.s  4
0x152c4d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x152c52  ldloc.s  4
0x152c54  ldstr    aRibboncustomiz_0// "ribboncustomizationid"
0x152c59  ldarg.2
0x152c5a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x152c5f  box      [mscorlib]System.Guid
0x152c64  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x152c69  ldloc.3
0x152c6a  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker> Microsoft.Crm.ObjectModel.RibbonImportResult::get_Monikers()
0x152c6f  ldarg.0
0x152c70  ldloc.s  4
0x152c72  ldarg.s  5
0x152c74  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x152c79  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker>::Add(var<u1>)
0x152c7e  br       loc_152D2F
0x152c83  ldloc.2
0x152c84  ldc.i4.0
0x152c85  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x152c8a  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.RibbonCommand
0x152c8f  stloc.s  5
0x152c91  ldarg.3
0x152c92  brtrue.s loc_152CD3
0x152c94  ldloc.s  5
0x152c96  ldstr    aCommanddefinit_1// "commanddefinition"
0x152c9b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x152ca0  castclass [mscorlib]System.String
0x152ca5  ldarg.1
0x152ca6  ldc.i4.1
0x152ca7  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XNode::ToString(valuetype [System.Xml.Linq]System.Xml.Linq.SaveOptions)
0x152cac  ldc.i4.5
0x152cad  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x152cb2  brtrue.s loc_152D07
0x152cb4  ldloc.s  5
0x152cb6  ldstr    aCommanddefinit_1// "commanddefinition"
0x152cbb  ldarg.1
0x152cbc  ldc.i4.1
0x152cbd  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XNode::ToString(valuetype [System.Xml.Linq]System.Xml.Linq.SaveOptions)
0x152cc2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x152cc7  ldarg.0
0x152cc8  ldloc.s  5
0x152cca  ldarg.s  5
0x152ccc  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x152cd1  br.s     loc_152D07
0x152cd3  ldloc.s  5
0x152cd5  ldstr    aCommanddefinit_1// "commanddefinition"
0x152cda  ldarg.1
0x152cdb  ldc.i4.1
0x152cdc  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XNode::ToString(valuetype [System.Xml.Linq]System.Xml.Linq.SaveOptions)
0x152ce1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x152ce6  ldloc.s  5
0x152ce8  ldstr    aRibboncustomiz_0// "ribboncustomizationid"
0x152ced  ldarg.3
0x152cee  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x152cf3  box      [mscorlib]System.Guid
0x152cf8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x152cfd  ldarg.0
0x152cfe  ldloc.s  5
0x152d00  ldarg.s  5
0x152d02  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x152d07  ldloc.3
0x152d08  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker> Microsoft.Crm.ObjectModel.RibbonImportResult::get_Monikers()
0x152d0d  ldloc.s  5
0x152d0f  ldstr    aRibboncommandi// "ribboncommandid"
0x152d14  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x152d19  unbox.any [mscorlib]System.Guid
0x152d1e  ldstr    aRibboncommand// "RibbonCommand"
0x152d23  ldarg.s  5
0x152d25  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x152d2a  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker>::Add(var<u1>)
0x152d2f  ldloc.3
0x152d30  ret
```
