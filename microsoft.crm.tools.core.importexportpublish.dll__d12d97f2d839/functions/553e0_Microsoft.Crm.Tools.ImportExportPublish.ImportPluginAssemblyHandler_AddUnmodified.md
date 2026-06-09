# Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::AddUnmodified

- ea: `0x553e0`
- end: `0x554bd`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::AddUnmodified`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x54950`

## callees

- `0x508e0`
- `0x50be0`
- `0x50c30`
- `0x50fd0`
- `0x54f10`
- `0x55040`
- `0x553e0`
- `0x554f0`
- `0x686f0`

## string_xrefs

- `0x5540c`: `PluginAssemblyId`
- `0x5541e`: `PluginAssemblyId`
- `0x5543d`: `PluginAssemblyId`

## pseudocode

```c

```

## disassembly

```asm
0x553e0  ldarg.0
0x553e1  ldarg.1
0x553e2  call     instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginAssembly Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::GetPluginAssemblyFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x553e7  stloc.0
0x553e8  ldarg.0
0x553e9  ldloc.0
0x553ea  ldarg.2
0x553eb  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::RetrievePluginAssembliesFromAssemblyId(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginAssembly pluginAssembly, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject service)
0x553f0  stloc.1
0x553f1  ldloc.1
0x553f2  brfalse.s loc_553FD
0x553f4  ldloc.1
0x553f5  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x553fa  ldc.i4.1
0x553fb  bge.s    loc_55406
0x553fd  ldarg.0
0x553fe  ldloc.0
0x553ff  ldarg.2
0x55400  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::RetrievePluginAssembliesFromFQN(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginAssembly pluginAssembly, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject service)
0x55405  stloc.1
0x55406  ldarg.1
0x55407  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5540c  ldstr    aPluginassembly// "PluginAssemblyId"
0x55411  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x55416  brfalse.s loc_55458
0x55418  ldarg.1
0x55419  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5541e  ldstr    aPluginassembly// "PluginAssemblyId"
0x55423  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x55428  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5542d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x55432  brtrue.s loc_55458
0x55434  ldarg.0
0x55435  ldc.i4.s 0x5B
0x55437  ldarg.1
0x55438  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5543d  ldstr    aPluginassembly// "PluginAssemblyId"
0x55442  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x55447  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5544c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x55451  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::RemoveFromRootComponentsList(int32 componentType, valuetype [mscorlib]System.Guid objectId)
0x55456  br.s     loc_55475
0x55458  ldarg.0
0x55459  ldc.i4.s 0x5B
0x5545b  ldarg.1
0x5545c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x55461  ldstr    aFullname// "FullName"
0x55466  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5546b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x55470  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::RemoveFromRootComponentsList(int32 componentType, string schemaName)
0x55475  ldc.i4   0x8004847C
0x5547a  ldc.i4.0
0x5547b  newarr   [mscorlib]System.Object
0x55480  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x55485  stloc.2
0x55486  ldarg.0
0x55487  ldarg.0
0x55488  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetParameterXPath()
0x5548d  ldstr    aWarning// "warning"
0x55492  ldloc.2
0x55493  ldc.i4.1
0x55494  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed)
0x55499  ldloc.1
0x5549a  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x5549f  ldc.i4.0
0x554a0  ble.s    loc_554BC
0x554a2  ldarg.0
0x554a3  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x554a8  ldarg.0
0x554a9  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetParameterXPath()
0x554ae  ldstr    aSuccess// "success"
0x554b3  ldnull
0x554b4  ldc.i4.1
0x554b5  ldc.i4.0
0x554b6  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, [opt] int32 errorCode)
0x554bb  ret
0x554bc  ret
```
