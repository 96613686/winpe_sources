# Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::GetTransformedXml

- ea: `0x8c1f0`
- end: `0x8c32f`
- name: `Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::GetTransformedXml`
- size: `319`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x2fb90`
- `0x47920`
- `0x47940`
- `0x59880`
- `0x5be20`
- `0x8c1f0`
- `0x8c330`

## string_xrefs

- `0x8c277`: `ApplicationFile with id={0} is required to export data template/update-via-import file.`
- `0x8c29b`: ` is required to export data template/update-via-import file.`

## pseudocode

```c

```

## disassembly

```asm
0x8c1f0  ldarg.0
0x8c1f1  call     instance string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::GetInputXml()
0x8c1f6  stloc.0
0x8c1f7  ldsfld   string [mscorlib]System.String::Empty
0x8c1fc  stloc.1
0x8c1fd  ldloca.s 2
0x8c1ff  ldstr    a8e81863120724e// "8E818631-2072-4E13-9920-8A2868CC7A3E"
0x8c204  call     instance void [mscorlib]System.Guid::.ctor(string)
0x8c209  ldstr    aApplicationfil// "applicationfile"
0x8c20e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x8c213  stloc.3
0x8c214  ldloc.3
0x8c215  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x8c21a  ldstr    aFileid// "fileid"
0x8c21f  ldc.i4.0
0x8c220  ldc.i4.1
0x8c221  newarr   [mscorlib]System.Object
0x8c226  dup
0x8c227  ldc.i4.0
0x8c228  ldloc.2
0x8c229  box      [mscorlib]System.Guid
0x8c22e  stelem.ref
0x8c22f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x8c234  ldloc.3
0x8c235  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x8c23a  ldc.i4.2
0x8c23b  newarr   [mscorlib]System.String
0x8c240  dup
0x8c241  ldc.i4.0
0x8c242  ldstr    aFileid// "fileid"
0x8c247  stelem.ref
0x8c248  dup
0x8c249  ldc.i4.1
0x8c24a  ldstr    aBody_0// "body"
0x8c24f  stelem.ref
0x8c250  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x8c255  ldloc.3
0x8c256  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8c25b  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x8c260  stloc.s  4
0x8c262  ldloc.s  4
0x8c264  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x8c269  ldc.i4.1
0x8c26a  beq.s    loc_8C2AB
0x8c26c  ldnull
0x8c26d  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x8c272  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x8c277  ldstr    aApplicationfil_0// "ApplicationFile with id={0} is required"...
0x8c27c  ldc.i4.1
0x8c27d  newarr   [mscorlib]System.Object
0x8c282  dup
0x8c283  ldc.i4.0
0x8c284  ldloc.2
0x8c285  box      [mscorlib]System.Guid
0x8c28a  stelem.ref
0x8c28b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8c290  ldstr    aApplicationfil_1// "ApplicationFile with id="
0x8c295  ldloc.2
0x8c296  box      [mscorlib]System.Guid
0x8c29b  ldstr    aIsRequiredToEx// " is required to export data template/up"...
0x8c2a0  call     string [mscorlib]System.String::Concat(object, object, object)
0x8c2a5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x8c2aa  throw
0x8c2ab  ldloc.s  4
0x8c2ad  ldc.i4.0
0x8c2ae  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x8c2b3  ldstr    aBody_0// "body"
0x8c2b8  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x8c2bd  castclass [mscorlib]System.String
0x8c2c2  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x8c2c7  stloc.s  5
0x8c2c9  newobj   instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::.ctor()
0x8c2ce  stloc.s  6
0x8c2d0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x8c2d5  stloc.s  7
0x8c2d7  ldloc.s  7
0x8c2d9  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder)
0x8c2de  stloc.s  8
0x8c2e0  ldloc.s  6
0x8c2e2  ldloc.s  5
0x8c2e4  ldnull
0x8c2e5  ldnull
0x8c2e6  callvirt instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::Load(class [System.Xml]System.Xml.XPath.IXPathNavigable, class [System.Xml]System.Xml.Xsl.XsltSettings, class [System.Xml]System.Xml.XmlResolver)
0x8c2eb  ldloc.s  6
0x8c2ed  ldloc.0
0x8c2ee  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x8c2f3  ldloc.s  8
0x8c2f5  callvirt instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::Transform(class [System.Xml]System.Xml.XPath.IXPathNavigable, class [System.Xml]System.Xml.XmlWriter)
0x8c2fa  ldloc.s  8
0x8c2fc  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x8c301  ldloc.s  8
0x8c303  callvirt instance void [System.Xml]System.Xml.XmlWriter::Close()
0x8c308  ldloc.s  7
0x8c30a  callvirt instance string [mscorlib]System.Object::ToString()
0x8c30f  stloc.1
0x8c310  leave.s  loc_8C31E
0x8c312  ldloc.s  8
0x8c314  brfalse.s loc_8C31D
0x8c316  ldloc.s  8
0x8c318  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8c31d  endfinally
0x8c31e  ldloc.1
0x8c31f  ldstr    aAmp10// "&amp;#10;"
0x8c324  ldstr    a10// "&#10;"
0x8c329  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x8c32e  ret
```
