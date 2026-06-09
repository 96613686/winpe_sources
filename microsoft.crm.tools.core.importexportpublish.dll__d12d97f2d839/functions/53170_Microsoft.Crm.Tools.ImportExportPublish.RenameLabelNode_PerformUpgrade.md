# Microsoft.Crm.Tools.ImportExportPublish.RenameLabelNode::PerformUpgrade

- ea: `0x53170`
- end: `0x532db`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RenameLabelNode::PerformUpgrade`
- size: `363`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x53170`
- `0x532e0`

## string_xrefs

- `0x53170`: `IsvConfig`
- `0x5326b`: `isvconfigid`
- `0x531ab`: `configxml`
- `0x53227`: `configxml`
- `0x5328d`: `configxml`
- `0x5320a`: `No ISV Config row is found for organization with id {0}. Skip upgrade action.`
- `0x5324e`: `ISV Config Xml value is null or empty. Skip upgrade action.`
- `0x532be`: `RenameLabelNode Action is failed with error message {0}`

## pseudocode

```c

```

## disassembly

```asm
0x53170  ldstr    aIsvconfig// "IsvConfig"
0x53175  ldarg.0
0x53176  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RenameLabelNode::context
0x5317b  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x53180  stloc.0
0x53181  ldarg.0
0x53182  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RenameLabelNode::context
0x53187  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5318c  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.IsvConfig::.ctor(valuetype [mscorlib]System.Guid)
0x53191  stloc.1
0x53192  ldloc.1
0x53193  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x53198  ldarg.0
0x53199  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RenameLabelNode::context
0x5319e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x531a3  stloc.2
0x531a4  ldloc.2
0x531a5  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x531aa  ldloc.2
0x531ab  ldstr    aConfigxml// "configxml"
0x531b0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x531b5  ldloc.1
0x531b6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x531bb  ldarg.0
0x531bc  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RenameLabelNode::context
0x531c1  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x531c6  stloc.3
0x531c7  ldloc.3
0x531c8  ldstr    aOrganizationid// "organizationid"
0x531cd  ldc.i4.0
0x531ce  ldarg.0
0x531cf  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RenameLabelNode::context
0x531d4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x531d9  box      [mscorlib]System.Guid
0x531de  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x531e3  pop
0x531e4  ldloc.0
0x531e5  ldloc.3
0x531e6  ldloc.2
0x531e7  ldarg.0
0x531e8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RenameLabelNode::context
0x531ed  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x531f2  stloc.s  4
0x531f4  ldloc.s  4
0x531f6  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x531fb  brtrue.s loc_5321F
0x531fd  ldarg.0
0x531fe  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RenameLabelNode::context
0x53203  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x53208  ldc.i4.s 0x11
0x5320a  ldstr    aNoIsvConfigRow// "No ISV Config row is found for organiza"...
0x5320f  ldc.i4.0
0x53210  newarr   [mscorlib]System.Object
0x53215  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5321a  leave    loc_532DA
0x5321f  ldloc.s  4
0x53221  ldc.i4.0
0x53222  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x53227  ldstr    aConfigxml// "configxml"
0x5322c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x53231  castclass [mscorlib]System.String
0x53236  stloc.s  5
0x53238  ldloc.s  5
0x5323a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5323f  brfalse.s loc_53260
0x53241  ldarg.0
0x53242  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RenameLabelNode::context
0x53247  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5324c  ldc.i4.s 0x11
0x5324e  ldstr    aIsvConfigXmlVa// "ISV Config Xml value is null or empty. "...
0x53253  ldc.i4.0
0x53254  newarr   [mscorlib]System.Object
0x53259  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5325e  leave.s  loc_532DA
0x53260  ldarg.0
0x53261  ldloc.s  5
0x53263  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RenameLabelNode::DoAction(string configXml)
0x53268  stloc.s  6
0x5326a  ldloc.1
0x5326b  ldstr    aIsvconfigid// "isvconfigid"
0x53270  ldloc.s  4
0x53272  ldc.i4.0
0x53273  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x53278  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x5327d  unbox.any [mscorlib]System.Guid
0x53282  box      [mscorlib]System.Guid
0x53287  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5328c  ldloc.1
0x5328d  ldstr    aConfigxml// "configxml"
0x53292  ldloc.s  6
0x53294  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x53299  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5329e  ldloc.0
0x5329f  ldloc.1
0x532a0  ldarg.0
0x532a1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RenameLabelNode::context
0x532a6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x532ab  leave.s  loc_532DA
0x532ad  stloc.s  7
0x532af  ldloc.s  7
0x532b1  ldarg.0
0x532b2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RenameLabelNode::context
0x532b7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x532bc  ldc.i4.s 0x11
0x532be  ldstr    aRenamelabelnod// "RenameLabelNode Action is failed with e"...
0x532c3  ldc.i4.1
0x532c4  newarr   [mscorlib]System.Object
0x532c9  dup
0x532ca  ldc.i4.0
0x532cb  ldloc.s  7
0x532cd  callvirt instance string [mscorlib]System.Exception::get_Message()
0x532d2  stelem.ref
0x532d3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x532d8  leave.s  loc_532DA
0x532da  ret
```
