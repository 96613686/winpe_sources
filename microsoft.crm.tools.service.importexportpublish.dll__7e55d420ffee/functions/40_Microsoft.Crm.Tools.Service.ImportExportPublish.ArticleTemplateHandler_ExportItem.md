# Microsoft.Crm.Tools.Service.ImportExportPublish.ArticleTemplateHandler::ExportItem

- ea: `0x40`
- end: `0x2f2`
- name: `Microsoft.Crm.Tools.Service.ImportExportPublish.ArticleTemplateHandler::ExportItem`
- size: `690`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x40`

## string_xrefs

- `0x59`: `Templates`
- `0x65`: `KBArticleTemplates`
- `0x76`: `KbArticleTemplate`
- `0x98`: `kbarticletemplateid`
- `0x143`: `kbarticletemplateid`
- `0xa0`: `structurexml`
- `0xa8`: `formatxml`
- `0x1f5`: `kbarticletemplate`
- `0x23a`: `KBArticleTemplate`
- `0x264`: `KBArticleTemplateAttributes`

## pseudocode

```c

```

## disassembly

```asm
0x40  ldarg.0
0x41  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.Service.ImportExportPublish.ArticleTemplateHandler::_solutionComponentTemplateSet
0x46  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x4b  ldc.i4.0
0x4c  ble      loc_2F1
0x51  ldc.i4.0
0x52  stloc.0
0x53  ldarg.1
0x54  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x59  ldstr    aTemplates// "Templates"
0x5e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x63  stloc.1
0x64  ldarg.1
0x65  ldstr    aKbarticletempl// "KBArticleTemplates"
0x6a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x6f  stloc.2
0x70  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::.ctor()
0x75  stloc.3
0x76  ldstr    aKbarticletempl_0// "KbArticleTemplate"
0x7b  ldarg.0
0x7c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ArticleTemplateHandler::context
0x81  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x86  stloc.s  4
0x88  ldloc.s  4
0x8a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x8f  ldc.i4.s 0xA
0x91  newarr   [mscorlib]System.String
0x96  dup
0x97  ldc.i4.0
0x98  ldstr    aKbarticletempl_1// "kbarticletemplateid"
0x9d  stelem.ref
0x9e  dup
0x9f  ldc.i4.1
0xa0  ldstr    aStructurexml// "structurexml"
0xa5  stelem.ref
0xa6  dup
0xa7  ldc.i4.2
0xa8  ldstr    aFormatxml// "formatxml"
0xad  stelem.ref
0xae  dup
0xaf  ldc.i4.3
0xb0  ldstr    aTitle// "title"
0xb5  stelem.ref
0xb6  dup
0xb7  ldc.i4.4
0xb8  ldstr    aDescription// "description"
0xbd  stelem.ref
0xbe  dup
0xbf  ldc.i4.5
0xc0  ldstr    aLanguagecode// "languagecode"
0xc5  stelem.ref
0xc6  dup
0xc7  ldc.i4.6
0xc8  ldstr    aSolutionid// "solutionid"
0xcd  stelem.ref
0xce  dup
0xcf  ldc.i4.7
0xd0  ldstr    aIsmanaged// "ismanaged"
0xd5  stelem.ref
0xd6  dup
0xd7  ldc.i4.8
0xd8  ldstr    aIscustomizable// "iscustomizable"
0xdd  stelem.ref
0xde  dup
0xdf  ldc.i4.s 9
0xe1  ldstr    aIntroducedvers// "introducedversion"
0xe6  stelem.ref
0xe7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xec  ldloc.3
0xed  ldloc.s  4
0xef  ldarg.0
0xf0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ArticleTemplateHandler::context
0xf5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xfa  ldstr    aOrganization// "Organization"
0xff  ldarg.0
0x100  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ArticleTemplateHandler::context
0x105  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x10a  ldarg.0
0x10b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ArticleTemplateHandler::context
0x110  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveRelated(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x115  stloc.s  5
0x117  ldloc.s  5
0x119  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x11e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/Item>::.ctor(int32)
0x123  stloc.s  6
0x125  ldc.i4.0
0x126  stloc.s  7
0x128  ldloc.s  5
0x12a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x12f  stloc.s  8
0x131  br.s     loc_19E
0x133  ldloc.s  8
0x135  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x13a  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x13f  stloc.s  9
0x141  ldloc.s  9
0x143  ldstr    aKbarticletempl_1// "kbarticletemplateid"
0x148  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14d  unbox.any [mscorlib]System.Guid
0x152  stloc.s  0xA
0x154  ldarg.0
0x155  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.Service.ImportExportPublish.ArticleTemplateHandler::_solutionComponentTemplateSet
0x15a  ldloc.s  0xA
0x15c  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x161  brfalse.s loc_198
0x163  ldloc.s  9
0x165  ldstr    aTitle// "title"
0x16a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x16f  castclass [mscorlib]System.String
0x174  ldloca.s 0xA
0x176  constrained. [mscorlib]System.Guid
0x17c  callvirt instance string [mscorlib]System.Object::ToString()
0x181  call     string [mscorlib]System.String::Concat(string, string)
0x186  stloc.s  0xB
0x188  ldloc.s  6
0x18a  ldloc.s  0xB
0x18c  ldloc.s  7
0x18e  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/Item::.ctor(string, int32)
0x193  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/Item>::Add(var<u1>)
0x198  ldloc.s  7
0x19a  ldc.i4.1
0x19b  add
0x19c  stloc.s  7
0x19e  ldloc.s  8
0x1a0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1a5  brtrue.s loc_133
0x1a7  leave.s  loc_1BE
0x1a9  ldloc.s  8
0x1ab  isinst   [mscorlib]System.IDisposable
0x1b0  stloc.s  0xC
0x1b2  ldloc.s  0xC
0x1b4  brfalse.s loc_1BD
0x1b6  ldloc.s  0xC
0x1b8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1bd  endfinally
0x1be  ldloc.s  6
0x1c0  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/ListComparer::.ctor()
0x1c5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/Item>::Sort(class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>>)
0x1ca  ldloc.s  6
0x1cc  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/Item>::GetEnumerator()
0x1d1  stloc.s  0xD
0x1d3  br       loc_2B2
0x1d8  ldloca.s 0xD
0x1da  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/Item>::get_Current()
0x1df  stloc.s  0xE
0x1e1  ldloc.s  5
0x1e3  ldloc.s  0xE
0x1e5  callvirt instance int32 [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/Item::get_Index()
0x1ea  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1ef  stloc.s  0xF
0x1f1  ldc.i4.0
0x1f2  stloc.s  0x10
0x1f4  ldarg.1
0x1f5  ldstr    aKbarticletempl_2// "kbarticletemplate"
0x1fa  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x1ff  stloc.s  0x11
0x201  ldloc.s  0xF
0x203  ldstr    aSolutionid// "solutionid"
0x208  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x20d  unbox.any [mscorlib]System.Guid
0x212  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x217  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x21c  brtrue.s loc_226
0x21e  ldarg.0
0x21f  ldfld    bool [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x224  brfalse.s loc_255
0x226  ldloc.s  0xF
0x228  ldstr    aIsmanaged// "ismanaged"
0x22d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x232  unbox.any [mscorlib]System.Boolean
0x237  stloc.s  0x12
0x239  ldarg.0
0x23a  ldstr    aKbarticletempl_3// "KBArticleTemplate"
0x23f  ldarg.1
0x240  ldloc.s  0x11
0x242  ldloc.s  0xF
0x244  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity)
0x249  ldloc.s  0x12
0x24b  call     instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string, class [System.Xml]System.Xml.XmlDocument, class [System.Xml]System.Xml.XmlNode, class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.GenericType, bool)
0x250  ldc.i4.1
0x251  stloc.s  0x10
0x253  br.s     loc_2A3
0x255  ldarg.1
0x256  ldarg.0
0x257  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ArticleTemplateHandler::context
0x25c  call     bool [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::ExportAsUnmodified(class [System.Xml]System.Xml.XmlDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x261  brfalse.s loc_2A3
0x263  ldarg.0
0x264  ldstr    aKbarticletempl_4// "KBArticleTemplateAttributes"
0x269  ldarg.1
0x26a  ldloc.s  0x11
0x26c  ldloc.s  0xF
0x26e  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity)
0x273  call     instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlAttributes(string, class [System.Xml]System.Xml.XmlDocument, class [System.Xml]System.Xml.XmlNode, class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.GenericType)
0x278  ldarg.1
0x279  ldstr    aUnmodified// "unmodified"
0x27e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x283  stloc.s  0x13
0x285  ldloc.s  0x13
0x287  ldstr    a1// "1"
0x28c  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x291  ldloc.s  0x11
0x293  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x298  ldloc.s  0x13
0x29a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x29f  pop
0x2a0  ldc.i4.1
0x2a1  stloc.s  0x10
0x2a3  ldloc.s  0x10
0x2a5  brfalse.s loc_2B2
0x2a7  ldc.i4.1
0x2a8  stloc.0
0x2a9  ldloc.2
0x2aa  ldloc.s  0x11
0x2ac  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x2b1  pop
0x2b2  ldloca.s 0xD
0x2b4  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/Item>::MoveNext()
0x2b9  brtrue   loc_1D8
0x2be  leave.s  loc_2CE
0x2c0  ldloca.s 0xD
0x2c2  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler/Item>
0x2c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2cd  endfinally
0x2ce  ldloc.0
0x2cf  brtrue.s loc_2D9
0x2d1  ldarg.0
0x2d2  ldfld    bool [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x2d7  brfalse.s loc_2F1
0x2d9  ldloc.1
0x2da  ldloc.2
0x2db  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x2e0  pop
0x2e1  ldarg.0
0x2e2  ldfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.Service.ImportExportPublish.ArticleTemplateHandler::tracer
0x2e7  ldsfld   string [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ArticleExportSuccessMessage
0x2ec  callvirt instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string)
0x2f1  ret
```
