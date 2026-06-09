# Microsoft.Crm.Tools.ReportProvisioning.Reports::UpdateReportView

- ea: `0x68c0`
- end: `0x6995`
- name: `Microsoft.Crm.Tools.ReportProvisioning.Reports::UpdateReportView`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x6870`

## callees

- `0x68c0`

## string_xrefs

- `0x68da`: `layoutxml`
- `0x6903`: `layoutxml`
- `0x697b`: `layoutxml`

## pseudocode

```c

```

## disassembly

```asm
0x68c0  ldstr    aSavedquery// "SavedQuery"
0x68c5  ldarg.1
0x68c6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x68cb  stloc.0
0x68cc  ldloc.0
0x68cd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x68d2  ldc.i4.1
0x68d3  newarr   [mscorlib]System.String
0x68d8  dup
0x68d9  ldc.i4.0
0x68da  ldstr    aLayoutxml// "layoutxml"
0x68df  stelem.ref
0x68e0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x68e5  ldarg.0
0x68e6  ldstr    aSavedquery// "SavedQuery"
0x68eb  ldarg.1
0x68ec  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x68f1  stloc.1
0x68f2  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SavedQueryService::.ctor()
0x68f7  stloc.2
0x68f8  ldloc.2
0x68f9  ldloc.1
0x68fa  ldloc.0
0x68fb  ldarg.1
0x68fc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6901  stloc.3
0x6902  ldloc.3
0x6903  ldstr    aLayoutxml// "layoutxml"
0x6908  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x690d  castclass [mscorlib]System.String
0x6912  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x6917  stloc.s  4
0x6919  ldloc.s  4
0x691b  ldstr    aGridRowCellNam// "/grid/row/cell[@name='languagecode']"
0x6920  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6925  brtrue.s loc_6994
0x6927  ldloc.s  4
0x6929  ldstr    aCell// "cell"
0x692e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x6933  stloc.s  5
0x6935  ldloc.s  5
0x6937  ldstr    aName// "name"
0x693c  ldstr    aLanguagecode// "languagecode"
0x6941  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x6946  ldloc.s  5
0x6948  ldstr    aWidth// "width"
0x694d  ldstr    a100_0// "100"
0x6952  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x6957  ldloc.s  4
0x6959  ldstr    aGridRow// "/grid/row"
0x695e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6963  dup
0x6964  ldstr    aCellNameModifi// "cell[@name='modifiedon']"
0x6969  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x696e  stloc.s  6
0x6970  ldloc.s  5
0x6972  ldloc.s  6
0x6974  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertAfter(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0x6979  pop
0x697a  ldloc.3
0x697b  ldstr    aLayoutxml// "layoutxml"
0x6980  ldloc.s  4
0x6982  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x6987  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x698c  ldloc.2
0x698d  ldloc.3
0x698e  ldarg.1
0x698f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6994  ret
```
