# Microsoft.Crm.Metadata.EntityKeyDescription::FillPropertiesFromXml_0

- ea: `0x34730`
- end: `0x348f5`
- name: `Microsoft.Crm.Metadata.EntityKeyDescription::FillPropertiesFromXml_0`
- size: `453`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0xbc60`
- `0xbc80`
- `0x18a80`
- `0x34730`
- `0x34940`
- `0x34960`
- `0x34980`
- `0x349a0`
- `0x349c0`
- `0x34a20`
- `0x34a40`
- `0x34a60`
- `0x34a80`

## string_xrefs

- `0x34742`: `EntityKey XML must contain the EntityKeyid`
- `0x3475f`: `EntityKey XML must contain the EntityId`

## pseudocode

```c

```

## disassembly

```asm
0x34730  ldarg.1
0x34731  ldstr    aEntitykeyid// "EntityKeyId"
0x34736  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3473b  ldnull
0x3473c  ceq
0x3473e  ldarg.2
0x3473f  and
0x34740  brfalse.s loc_3474D
0x34742  ldstr    aEntitykeyXmlMu// "EntityKey XML must contain the EntityKe"...
0x34747  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x3474c  throw
0x3474d  ldarg.1
0x3474e  ldstr    aEntityid// "EntityId"
0x34753  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x34758  ldnull
0x34759  ceq
0x3475b  ldarg.2
0x3475c  and
0x3475d  brfalse.s loc_3476A
0x3475f  ldstr    aEntitykeyXmlMu_0// "EntityKey XML must contain the EntityId"
0x34764  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x34769  throw
0x3476a  ldarg.0
0x3476b  ldarg.1
0x3476c  ldstr    aEntitykeyid// "EntityKeyId"
0x34771  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x34776  brfalse.s loc_3478F
0x34778  ldarg.1
0x34779  ldstr    aEntitykeyid// "EntityKeyId"
0x3477e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x34783  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x34788  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3478d  br.s     loc_34794
0x3478f  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x34794  callvirt instance void Microsoft.Crm.Metadata.EntityKeyDescription::set_EntityKeyId(valuetype [mscorlib]System.Guid value)
0x34799  ldarg.1
0x3479a  ldstr    aEntityid// "EntityId"
0x3479f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x347a4  brfalse.s loc_347C1
0x347a6  ldarg.0
0x347a7  ldarg.1
0x347a8  ldstr    aEntityid// "EntityId"
0x347ad  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x347b2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x347b7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x347bc  callvirt instance void Microsoft.Crm.Metadata.EntityKeyDescription::set_EntityId(valuetype [mscorlib]System.Guid value)
0x347c1  ldarg.1
0x347c2  ldstr    aName// "Name"
0x347c7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x347cc  brfalse.s loc_347E4
0x347ce  ldarg.0
0x347cf  ldarg.1
0x347d0  ldstr    aName// "Name"
0x347d5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x347da  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x347df  callvirt instance void Microsoft.Crm.Metadata.EntityKeyDescription::set_Name(string value)
0x347e4  ldarg.1
0x347e5  ldstr    aLogicalname// "LogicalName"
0x347ea  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x347ef  brfalse.s loc_34807
0x347f1  ldarg.0
0x347f2  ldarg.1
0x347f3  ldstr    aLogicalname// "LogicalName"
0x347f8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x347fd  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x34802  callvirt instance void Microsoft.Crm.Metadata.EntityKeyDescription::set_LogicalName(string value)
0x34807  ldarg.1
0x34808  ldstr    aIndexid// "IndexId"
0x3480d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x34812  brfalse.s loc_3482F
0x34814  ldarg.0
0x34815  ldarg.1
0x34816  ldstr    aIndexid// "IndexId"
0x3481b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x34820  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x34825  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3482a  callvirt instance void Microsoft.Crm.Metadata.EntityKeyDescription::set_IndexId(valuetype [mscorlib]System.Guid value)
0x3482f  ldarg.1
0x34830  ldstr    aIscustomizable// "IsCustomizable"
0x34835  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3483a  brfalse.s loc_34853
0x3483c  ldarg.0
0x3483d  ldarg.1
0x3483e  ldstr    aIscustomizable// "IsCustomizable"
0x34843  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x34848  ldc.i4.0
0x34849  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node, bool defaultValue)
0x3484e  callvirt instance void Microsoft.Crm.Metadata.EntityKeyDescription::set_IsCustomizable(bool value)
0x34853  ldarg.1
0x34854  ldstr    aIsmanaged// "IsManaged"
0x34859  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3485e  brfalse.s loc_34877
0x34860  ldarg.0
0x34861  ldarg.1
0x34862  ldstr    aIsmanaged// "IsManaged"
0x34867  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3486c  ldc.i4.0
0x3486d  call     bool Microsoft.Crm.Platform.ConvertHelper::ToBooleanFromXmlNode(class [System.Xml]System.Xml.XmlNode node, bool defaultValue)
0x34872  callvirt instance void Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::set_IsManaged(bool value)
0x34877  ldarg.1
0x34878  ldstr    aIntroducedvers// "IntroducedVersion"
0x3487d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x34882  brfalse.s loc_3489F
0x34884  ldarg.0
0x34885  ldarg.1
0x34886  ldstr    aIntroducedvers// "IntroducedVersion"
0x3488b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x34890  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x34895  call     class [mscorlib]System.Version Microsoft.Crm.Platform.ConvertHelper::ToVersionFromString(string value)
0x3489a  callvirt instance void Microsoft.Crm.Metadata.EntityKeyDescription::set_IntroducedVersion(class [mscorlib]System.Version value)
0x3489f  ldarg.1
0x348a0  ldstr    aEntitykeyindex// "EntityKeyIndexStatus"
0x348a5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x348aa  brfalse.s loc_348CC
0x348ac  ldarg.0
0x348ad  ldarg.1
0x348ae  ldstr    aEntitykeyindex// "EntityKeyIndexStatus"
0x348b3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x348b8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x348bd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x348c2  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x348c7  callvirt instance void Microsoft.Crm.Metadata.EntityKeyDescription::set_EntityKeyIndexStatus(int32 value)
0x348cc  ldarg.1
0x348cd  ldstr    aAsyncjobid// "AsyncJobId"
0x348d2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x348d7  brfalse.s loc_348F4
0x348d9  ldarg.0
0x348da  ldarg.1
0x348db  ldstr    aAsyncjobid// "AsyncJobId"
0x348e0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x348e5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x348ea  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x348ef  callvirt instance void Microsoft.Crm.Metadata.EntityKeyDescription::set_AsyncJobId(valuetype [mscorlib]System.Guid value)
0x348f4  ret
```
