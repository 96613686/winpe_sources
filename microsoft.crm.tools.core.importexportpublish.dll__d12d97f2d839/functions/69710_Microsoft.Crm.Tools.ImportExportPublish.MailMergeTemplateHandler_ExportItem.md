# Microsoft.Crm.Tools.ImportExportPublish.MailMergeTemplateHandler::ExportItem

- ea: `0x69710`
- end: `0x698b1`
- name: `Microsoft.Crm.Tools.ImportExportPublish.MailMergeTemplateHandler::ExportItem`
- size: `417`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x3b380`
- `0x695c0`
- `0x69710`
- `0x96600`
- `0x96660`
- `0x966b0`

## string_xrefs

- `0x69729`: `Templates`
- `0x697be`: `mailmergetemplateid`
- `0x69740`: `MailMergeTemplate`
- `0x69750`: `MailMergeTemplate`
- `0x69735`: `MailMergeTemplates`

## pseudocode

```c

```

## disassembly

```asm
0x69710  ldarg.0
0x69711  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.MailMergeTemplateHandler::_solutionComponentTemplateSet
0x69716  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x6971b  ldc.i4.0
0x6971c  ble      loc_698B0
0x69721  ldc.i4.0
0x69722  stloc.0
0x69723  ldarg.1
0x69724  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x69729  ldstr    aTemplates// "Templates"
0x6972e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x69733  stloc.1
0x69734  ldarg.1
0x69735  ldstr    aMailmergetempl_4// "MailMergeTemplates"
0x6973a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x6973f  stloc.2
0x69740  ldstr    aMailmergetempl_2// "MailMergeTemplate"
0x69745  ldarg.0
0x69746  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.MailMergeTemplateHandler::context
0x6974b  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x69750  ldstr    aMailmergetempl_2// "MailMergeTemplate"
0x69755  ldarg.0
0x69756  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.MailMergeTemplateHandler::context
0x6975b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x69760  stloc.3
0x69761  ldloc.3
0x69762  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x69767  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x6976c  ldloc.3
0x6976d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x69772  ldstr    aIspersonal// "ispersonal"
0x69777  ldc.i4.0
0x69778  ldc.i4.0
0x69779  box      [mscorlib]System.Boolean
0x6977e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x69783  pop
0x69784  ldloc.3
0x69785  ldarg.0
0x69786  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.MailMergeTemplateHandler::context
0x6978b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x69790  stloc.s  4
0x69792  ldloc.s  4
0x69794  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x69799  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Item>::.ctor(int32)
0x6979e  stloc.s  5
0x697a0  ldc.i4.0
0x697a1  stloc.s  6
0x697a3  ldloc.s  4
0x697a5  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x697aa  stloc.s  7
0x697ac  br.s     loc_69819
0x697ae  ldloc.s  7
0x697b0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x697b5  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x697ba  stloc.s  8
0x697bc  ldloc.s  8
0x697be  ldstr    aMailmergetempl_1// "mailmergetemplateid"
0x697c3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x697c8  unbox.any [mscorlib]System.Guid
0x697cd  stloc.s  9
0x697cf  ldarg.0
0x697d0  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.MailMergeTemplateHandler::_solutionComponentTemplateSet
0x697d5  ldloc.s  9
0x697d7  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x697dc  brfalse.s loc_69813
0x697de  ldloc.s  8
0x697e0  ldstr    aName// "name"
0x697e5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x697ea  castclass [mscorlib]System.String
0x697ef  ldloca.s 9
0x697f1  constrained. [mscorlib]System.Guid
0x697f7  callvirt instance string [mscorlib]System.Object::ToString()
0x697fc  call     string [mscorlib]System.String::Concat(string, string)
0x69801  stloc.s  0xA
0x69803  ldloc.s  5
0x69805  ldloc.s  0xA
0x69807  ldloc.s  6
0x69809  newobj   instance void Item::.ctor(string key, int32 index)
0x6980e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Item>::Add(var<u1>)
0x69813  ldloc.s  6
0x69815  ldc.i4.1
0x69816  add
0x69817  stloc.s  6
0x69819  ldloc.s  7
0x6981b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x69820  brtrue.s loc_697AE
0x69822  leave.s  loc_69839
0x69824  ldloc.s  7
0x69826  isinst   [mscorlib]System.IDisposable
0x6982b  stloc.s  0xB
0x6982d  ldloc.s  0xB
0x6982f  brfalse.s loc_69838
0x69831  ldloc.s  0xB
0x69833  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69838  endfinally
0x69839  ldloc.s  5
0x6983b  newobj   instance void ListComparer::.ctor()
0x69840  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Item>::Sort(class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>>)
0x69845  ldloc.s  5
0x69847  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Item>::GetEnumerator()
0x6984c  stloc.s  0xC
0x6984e  br.s     loc_69874
0x69850  ldloca.s 0xC
0x69852  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Item>::get_Current()
0x69857  stloc.s  0xD
0x69859  ldloc.s  4
0x6985b  ldloc.s  0xD
0x6985d  callvirt instance int32 Item::get_Index()
0x69862  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x69867  stloc.s  0xE
0x69869  ldarg.0
0x6986a  ldarg.1
0x6986b  ldloc.s  0xE
0x6986d  ldloc.2
0x6986e  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.MailMergeTemplateHandler::PopulateMailMergeNode(class [System.Xml]System.Xml.XmlDocument XDoc, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity template, class [System.Xml]System.Xml.XmlNode mailMergeTemplatesNode)
0x69873  stloc.0
0x69874  ldloca.s 0xC
0x69876  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Item>::MoveNext()
0x6987b  brtrue.s loc_69850
0x6987d  leave.s  loc_6988D
0x6987f  ldloca.s 0xC
0x69881  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Item>
0x69887  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6988c  endfinally
0x6988d  ldloc.0
0x6988e  brtrue.s loc_69898
0x69890  ldarg.0
0x69891  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x69896  brfalse.s loc_698B0
0x69898  ldloc.1
0x69899  ldloc.2
0x6989a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x6989f  pop
0x698a0  ldarg.0
0x698a1  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.MailMergeTemplateHandler::tracer
0x698a6  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::MailMergeExportSuccessMessage
0x698ab  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string successMessage)
0x698b0  ret
```
