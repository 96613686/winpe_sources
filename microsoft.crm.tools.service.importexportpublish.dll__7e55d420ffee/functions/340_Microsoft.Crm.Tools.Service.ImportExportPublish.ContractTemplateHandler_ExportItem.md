# Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateHandler::ExportItem

- ea: `0x340`
- end: `0x60d`
- name: `Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateHandler::ExportItem`
- size: `717`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x340`

## string_xrefs

- `0x359`: `Templates`
- `0x365`: `ContractTemplates`
- `0x376`: `ContractTemplate`
- `0x555`: `ContractTemplate`
- `0x398`: `contracttemplateid`
- `0x45e`: `contracttemplateid`
- `0x3b8`: `contractservicelevelcode`
- `0x510`: `contracttemplate`
- `0x57f`: `ContractTemplateAttributes`

## pseudocode

```c

```

## disassembly

```asm
0x340  ldarg.0
0x341  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateHandler::_solutionComponentTemplateSet
0x346  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x34b  ldc.i4.0
0x34c  ble      loc_60C
0x351  ldc.i4.0
0x352  stloc.0
0x353  ldarg.1
0x354  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x359  ldstr    aTemplates// "Templates"
0x35e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x363  stloc.1
0x364  ldarg.1
0x365  ldstr    aContracttempla// "ContractTemplates"
0x36a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x36f  stloc.2
0x370  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::.ctor()
0x375  stloc.3
0x376  ldstr    aContracttempla_0// "ContractTemplate"
0x37b  ldarg.0
0x37c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateHandler::context
0x381  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x386  stloc.s  4
0x388  ldloc.s  4
0x38a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x38f  ldc.i4.s 0xD
0x391  newarr   [mscorlib]System.String
0x396  dup
0x397  ldc.i4.0
0x398  ldstr    aContracttempla_1// "contracttemplateid"
0x39d  stelem.ref
0x39e  dup
0x39f  ldc.i4.1
0x3a0  ldstr    aName// "name"
0x3a5  stelem.ref
0x3a6  dup
0x3a7  ldc.i4.2
0x3a8  ldstr    aAbbreviation// "abbreviation"
0x3ad  stelem.ref
0x3ae  dup
0x3af  ldc.i4.3
0x3b0  ldstr    aDescription// "description"
0x3b5  stelem.ref
0x3b6  dup
0x3b7  ldc.i4.4
0x3b8  ldstr    aContractservic// "contractservicelevelcode"
0x3bd  stelem.ref
0x3be  dup
0x3bf  ldc.i4.5
0x3c0  ldstr    aBillingfrequen// "billingfrequencycode"
0x3c5  stelem.ref
0x3c6  dup
0x3c7  ldc.i4.6
0x3c8  ldstr    aAllotmenttypec// "allotmenttypecode"
0x3cd  stelem.ref
0x3ce  dup
0x3cf  ldc.i4.7
0x3d0  ldstr    aUsediscountasp// "usediscountaspercentage"
0x3d5  stelem.ref
0x3d6  dup
0x3d7  ldc.i4.8
0x3d8  ldstr    aEffectivitycal// "effectivitycalendar"
0x3dd  stelem.ref
0x3de  dup
0x3df  ldc.i4.s 9
0x3e1  ldstr    aSolutionid// "solutionid"
0x3e6  stelem.ref
0x3e7  dup
0x3e8  ldc.i4.s 0xA
0x3ea  ldstr    aIsmanaged// "ismanaged"
0x3ef  stelem.ref
0x3f0  dup
0x3f1  ldc.i4.s 0xB
0x3f3  ldstr    aIscustomizable// "iscustomizable"
0x3f8  stelem.ref
0x3f9  dup
0x3fa  ldc.i4.s 0xC
0x3fc  ldstr    aIntroducedvers// "introducedversion"
0x401  stelem.ref
0x402  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x407  ldloc.3
0x408  ldloc.s  4
0x40a  ldarg.0
0x40b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateHandler::context
0x410  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x415  ldstr    aOrganization// "Organization"
0x41a  ldarg.0
0x41b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateHandler::context
0x420  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x425  ldarg.0
0x426  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateHandler::context
0x42b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveRelated(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x430  stloc.s  5
0x432  ldloc.s  5
0x434  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x439  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/Item>::.ctor(int32)
0x43e  stloc.s  6
0x440  ldc.i4.0
0x441  stloc.s  7
0x443  ldloc.s  5
0x445  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x44a  stloc.s  8
0x44c  br.s     loc_4B9
0x44e  ldloc.s  8
0x450  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x455  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x45a  stloc.s  9
0x45c  ldloc.s  9
0x45e  ldstr    aContracttempla_1// "contracttemplateid"
0x463  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x468  unbox.any [mscorlib]System.Guid
0x46d  stloc.s  0xA
0x46f  ldarg.0
0x470  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateHandler::_solutionComponentTemplateSet
0x475  ldloc.s  0xA
0x477  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x47c  brfalse.s loc_4B3
0x47e  ldloc.s  9
0x480  ldstr    aName// "name"
0x485  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x48a  castclass [mscorlib]System.String
0x48f  ldloca.s 0xA
0x491  constrained. [mscorlib]System.Guid
0x497  callvirt instance string [mscorlib]System.Object::ToString()
0x49c  call     string [mscorlib]System.String::Concat(string, string)
0x4a1  stloc.s  0xB
0x4a3  ldloc.s  6
0x4a5  ldloc.s  0xB
0x4a7  ldloc.s  7
0x4a9  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/Item::.ctor(string, int32)
0x4ae  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/Item>::Add(var<u1>)
0x4b3  ldloc.s  7
0x4b5  ldc.i4.1
0x4b6  add
0x4b7  stloc.s  7
0x4b9  ldloc.s  8
0x4bb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4c0  brtrue.s loc_44E
0x4c2  leave.s  loc_4D9
0x4c4  ldloc.s  8
0x4c6  isinst   [mscorlib]System.IDisposable
0x4cb  stloc.s  0xC
0x4cd  ldloc.s  0xC
0x4cf  brfalse.s loc_4D8
0x4d1  ldloc.s  0xC
0x4d3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d8  endfinally
0x4d9  ldloc.s  6
0x4db  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/ListComparer::.ctor()
0x4e0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/Item>::Sort(class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>>)
0x4e5  ldloc.s  6
0x4e7  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/Item>::GetEnumerator()
0x4ec  stloc.s  0xD
0x4ee  br       loc_5CD
0x4f3  ldloca.s 0xD
0x4f5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/Item>::get_Current()
0x4fa  stloc.s  0xE
0x4fc  ldloc.s  5
0x4fe  ldloc.s  0xE
0x500  callvirt instance int32 [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/Item::get_Index()
0x505  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x50a  stloc.s  0xF
0x50c  ldc.i4.0
0x50d  stloc.s  0x10
0x50f  ldarg.1
0x510  ldstr    aContracttempla_2// "contracttemplate"
0x515  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x51a  stloc.s  0x11
0x51c  ldloc.s  0xF
0x51e  ldstr    aSolutionid// "solutionid"
0x523  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x528  unbox.any [mscorlib]System.Guid
0x52d  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x532  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x537  brtrue.s loc_541
0x539  ldarg.0
0x53a  ldfld    bool [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x53f  brfalse.s loc_570
0x541  ldloc.s  0xF
0x543  ldstr    aIsmanaged// "ismanaged"
0x548  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x54d  unbox.any [mscorlib]System.Boolean
0x552  stloc.s  0x12
0x554  ldarg.0
0x555  ldstr    aContracttempla_0// "ContractTemplate"
0x55a  ldarg.1
0x55b  ldloc.s  0x11
0x55d  ldloc.s  0xF
0x55f  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity)
0x564  ldloc.s  0x12
0x566  call     instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string, class [System.Xml]System.Xml.XmlDocument, class [System.Xml]System.Xml.XmlNode, class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.GenericType, bool)
0x56b  ldc.i4.1
0x56c  stloc.s  0x10
0x56e  br.s     loc_5BE
0x570  ldarg.1
0x571  ldarg.0
0x572  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateHandler::context
0x577  call     bool [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::ExportAsUnmodified(class [System.Xml]System.Xml.XmlDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x57c  brfalse.s loc_5BE
0x57e  ldarg.0
0x57f  ldstr    aContracttempla_3// "ContractTemplateAttributes"
0x584  ldarg.1
0x585  ldloc.s  0x11
0x587  ldloc.s  0xF
0x589  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity)
0x58e  call     instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlAttributes(string, class [System.Xml]System.Xml.XmlDocument, class [System.Xml]System.Xml.XmlNode, class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.GenericType)
0x593  ldarg.1
0x594  ldstr    aUnmodified// "unmodified"
0x599  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x59e  stloc.s  0x13
0x5a0  ldloc.s  0x13
0x5a2  ldstr    a1// "1"
0x5a7  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x5ac  ldloc.s  0x11
0x5ae  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5b3  ldloc.s  0x13
0x5b5  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x5ba  pop
0x5bb  ldc.i4.1
0x5bc  stloc.s  0x10
0x5be  ldloc.s  0x10
0x5c0  brfalse.s loc_5CD
0x5c2  ldc.i4.1
0x5c3  stloc.0
0x5c4  ldloc.2
0x5c5  ldloc.s  0x11
0x5c7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5cc  pop
0x5cd  ldloca.s 0xD
0x5cf  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/Item>::MoveNext()
0x5d4  brtrue   loc_4F3
0x5d9  leave.s  loc_5E9
0x5db  ldloca.s 0xD
0x5dd  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/Item>
0x5e3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5e8  endfinally
0x5e9  ldloc.0
0x5ea  brtrue.s loc_5F4
0x5ec  ldarg.0
0x5ed  ldfld    bool [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x5f2  brfalse.s loc_60C
0x5f4  ldloc.1
0x5f5  ldloc.2
0x5f6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5fb  pop
0x5fc  ldarg.0
0x5fd  ldfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateHandler::tracer
0x602  ldsfld   string [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ContractExportSuccessMessage
0x607  callvirt instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string)
0x60c  ret
```
