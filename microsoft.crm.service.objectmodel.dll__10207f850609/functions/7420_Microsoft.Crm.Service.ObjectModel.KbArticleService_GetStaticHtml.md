# Microsoft.Crm.Service.ObjectModel.KbArticleService::GetStaticHtml

- ea: `0x7420`
- end: `0x7592`
- name: `Microsoft.Crm.Service.ObjectModel.KbArticleService::GetStaticHtml`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6e20`

## callees

- `0x7420`

## string_xrefs

- `0x7421`: `articlexml`
- `0x7443`: `articlexml`
- `0x7454`: `formatxml`
- `0x7476`: `formatxml`
- `0x7487`: `structurexml`
- `0x74a9`: `structurexml`
- `0x74be`: `<combinedxml>{0}{1}</combinedxml>`

## pseudocode

```c

```

## disassembly

```asm
0x7420  ldarg.1
0x7421  ldstr    aArticlexml// "articlexml"
0x7426  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x742b  brfalse.s loc_7442
0x742d  ldc.i4   0x800404F7
0x7432  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x7437  ldc.i4   0x800404F7
0x743c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x7441  throw
0x7442  ldarg.1
0x7443  ldstr    aArticlexml// "articlexml"
0x7448  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x744d  castclass [mscorlib]System.String
0x7452  stloc.0
0x7453  ldarg.2
0x7454  ldstr    aFormatxml// "formatxml"
0x7459  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x745e  brfalse.s loc_7475
0x7460  ldc.i4   0x800404F8
0x7465  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x746a  ldc.i4   0x800404F8
0x746f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x7474  throw
0x7475  ldarg.2
0x7476  ldstr    aFormatxml// "formatxml"
0x747b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7480  castclass [mscorlib]System.String
0x7485  stloc.1
0x7486  ldarg.2
0x7487  ldstr    aStructurexml// "structurexml"
0x748c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x7491  brfalse.s loc_74A8
0x7493  ldc.i4   0x800404F9
0x7498  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x749d  ldc.i4   0x800404F9
0x74a2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x74a7  throw
0x74a8  ldarg.2
0x74a9  ldstr    aStructurexml// "structurexml"
0x74ae  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x74b3  castclass [mscorlib]System.String
0x74b8  stloc.2
0x74b9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x74be  ldstr    aCombinedxml01C// "<combinedxml>{0}{1}</combinedxml>"
0x74c3  ldc.i4.2
0x74c4  newarr   [mscorlib]System.Object
0x74c9  dup
0x74ca  ldc.i4.0
0x74cb  ldloc.0
0x74cc  stelem.ref
0x74cd  dup
0x74ce  ldc.i4.1
0x74cf  ldloc.2
0x74d0  stelem.ref
0x74d1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x74d6  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x74db  stloc.3
0x74dc  ldnull
0x74dd  stloc.s  4
0x74df  ldsfld   string [mscorlib]System.String::Empty
0x74e4  stloc.s  5
0x74e6  ldarg.1
0x74e7  ldstr    aTitle// "title"
0x74ec  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x74f1  brtrue.s loc_7505
0x74f3  ldarg.1
0x74f4  ldstr    aTitle// "title"
0x74f9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x74fe  castclass [mscorlib]System.String
0x7503  stloc.s  5
0x7505  ldsfld   string [mscorlib]System.String::Empty
0x750a  stloc.s  6
0x750c  ldarg.1
0x750d  ldstr    aNumber// "number"
0x7512  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x7517  brtrue.s loc_752B
0x7519  ldarg.1
0x751a  ldstr    aNumber// "number"
0x751f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7524  castclass [mscorlib]System.String
0x7529  stloc.s  6
0x752b  newobj   instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::.ctor()
0x7530  stloc.s  7
0x7532  ldloc.s  7
0x7534  ldstr    aTitle// "title"
0x7539  ldstr    asc_1EEAE// ""
0x753e  ldloc.s  5
0x7540  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x7545  ldloc.s  7
0x7547  ldstr    aNumber// "number"
0x754c  ldstr    asc_1EEAE// ""
0x7551  ldloc.s  6
0x7553  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x7558  ldloc.1
0x7559  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x755e  newobj   instance void [System.Xml]System.Xml.XPath.XPathDocument::.ctor(class [mscorlib]System.IO.TextReader)
0x7563  stloc.s  4
0x7565  newobj   instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::.ctor()
0x756a  dup
0x756b  ldloc.s  4
0x756d  ldnull
0x756e  ldnull
0x756f  callvirt instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::Load(class [System.Xml]System.Xml.XPath.IXPathNavigable, class [System.Xml]System.Xml.Xsl.XsltSettings, class [System.Xml]System.Xml.XmlResolver)
0x7574  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7579  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x757e  stloc.s  8
0x7580  ldloc.3
0x7581  ldloc.s  7
0x7583  ldloc.s  8
0x7585  callvirt instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::Transform(class [System.Xml]System.Xml.XPath.IXPathNavigable, class [System.Xml]System.Xml.Xsl.XsltArgumentList, class [mscorlib]System.IO.TextWriter)
0x758a  ldloc.s  8
0x758c  callvirt instance string [mscorlib]System.Object::ToString()
0x7591  ret
```
