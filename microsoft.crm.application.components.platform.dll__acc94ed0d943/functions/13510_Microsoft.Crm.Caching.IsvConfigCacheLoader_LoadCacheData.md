# Microsoft.Crm.Caching.IsvConfigCacheLoader::LoadCacheData

- ea: `0x13510`
- end: `0x13613`
- name: `Microsoft.Crm.Caching.IsvConfigCacheLoader::LoadCacheData`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0xbd0`
- `0x11590`
- `0x13370`
- `0x13500`
- `0x13510`
- `0x59810`
- `0x5be20`

## string_xrefs

- `0x13540`: `isvconfig`
- `0x13550`: `configxml`
- `0x135bc`: `configxml`
- `0x13597`: `Found more than one ISVConfigXML for organization with id = {0}`
- `0x135de`: `Loading ISV.config.xml : {0}`

## pseudocode

```c

```

## disassembly

```asm
0x13510  ldnull
0x13511  stloc.0
0x13512  newobj   instance void [System.Xml]System.Xml.XmlReaderSettings::.ctor()
0x13517  stloc.1
0x13518  ldloc.1
0x13519  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x1351e  ldnull
0x1351f  ldarg.0
0x13520  call     instance string Microsoft.Crm.Caching.IsvConfigCacheLoader::get__xsdPath()
0x13525  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x1352a  pop
0x1352b  ldloc.1
0x1352c  ldc.i4.4
0x1352d  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_ValidationType(valuetype [System.Xml]System.Xml.ValidationType)
0x13532  ldloc.1
0x13533  ldnull
0x13534  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x13539  ldloc.1
0x1353a  ldc.i4.0
0x1353b  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_ConformanceLevel(valuetype [System.Xml]System.Xml.ConformanceLevel)
0x13540  ldstr    aIsvconfig// "isvconfig"
0x13545  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x1354a  dup
0x1354b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x13550  ldstr    aConfigxml// "configxml"
0x13555  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x1355a  dup
0x1355b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x13560  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x13565  ldstr    aOrganizationid// "organizationid"
0x1356a  ldc.i4.0
0x1356b  ldarg.1
0x1356c  box      [mscorlib]System.Guid
0x13571  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x13576  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x1357b  pop
0x1357c  ldc.i4.0
0x1357d  ldc.i4.1
0x1357e  ldarg.2
0x1357f  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, bool retrieveLatest, bool useSystemUserContext, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x13584  stloc.2
0x13585  ldloc.2
0x13586  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x1358b  ldc.i4.0
0x1358c  ble.s    loc_13603
0x1358e  ldloc.2
0x1358f  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x13594  ldc.i4.1
0x13595  ceq
0x13597  ldstr    aFoundMoreThanO// "Found more than one ISVConfigXML for or"...
0x1359c  ldc.i4.1
0x1359d  newarr   [mscorlib]System.Object
0x135a2  dup
0x135a3  ldc.i4.0
0x135a4  ldarg.2
0x135a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x135aa  box      [mscorlib]System.Guid
0x135af  stelem.ref
0x135b0  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message, object[] args)
0x135b5  ldloc.2
0x135b6  ldc.i4.0
0x135b7  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x135bc  ldstr    aConfigxml// "configxml"
0x135c1  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x135c6  castclass [mscorlib]System.String
0x135cb  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x135d0  ldloc.1
0x135d1  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader, class [System.Xml]System.Xml.XmlReaderSettings)
0x135d6  stloc.3
0x135d7  ldloc.3
0x135d8  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(class [System.Xml]System.Xml.XmlReader)
0x135dd  stloc.0
0x135de  ldstr    aLoadingIsvConf// "Loading ISV.config.xml : {0}"
0x135e3  ldc.i4.1
0x135e4  newarr   [mscorlib]System.Object
0x135e9  dup
0x135ea  ldc.i4.0
0x135eb  ldloc.0
0x135ec  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x135f1  stelem.ref
0x135f2  call     void Microsoft.Crm.Util::TraceInfo(string message, object[] args)
0x135f7  leave.s  loc_13603
0x135f9  ldloc.3
0x135fa  brfalse.s loc_13602
0x135fc  ldloc.3
0x135fd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13602  endfinally
0x13603  ldloc.0
0x13604  brtrue.s loc_1360C
0x13606  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x1360b  stloc.0
0x1360c  ldloc.0
0x1360d  call     class Microsoft.Crm.Caching.SerializableXmlDocument Microsoft.Crm.Caching.SerializableXmlDocument::op_Implicit(class [System.Xml]System.Xml.XmlDocument input)
0x13612  ret
```
