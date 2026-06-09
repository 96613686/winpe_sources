# Microsoft.Crm.EndUserNotification.SlugService::ValidateForCreateUpdateInternal

- ea: `0x7ce0`
- end: `0x7e79`
- name: `Microsoft.Crm.EndUserNotification.SlugService::ValidateForCreateUpdateInternal`
- size: `409`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x7b60`
- `0x7b70`

## callees

- `0x78a0`
- `0x7940`
- `0x7ce0`
- `0x7e80`
- `0x7ea0`
- `0x7f80`

## string_xrefs

- `0x7d26`: `SlugXml for template name [{0}] version [{1}] not present`
- `0x7db6`: `Template name [{0}] version [{1}] requires an invalid system slug [{2}]`

## pseudocode

```c

```

## disassembly

```asm
0x7ce0  ldarg.2
0x7ce1  ldstr    aParameternames// "parameterNames"
0x7ce6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7ceb  ldarg.3
0x7cec  ldstr    aParametervalue// "parameterValues"
0x7cf1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7cf6  ldarg.2
0x7cf7  ldlen
0x7cf8  conv.i4
0x7cf9  ldarg.3
0x7cfa  ldlen
0x7cfb  conv.i4
0x7cfc  beq.s    loc_7D09
0x7cfe  ldstr    aNameAndValuesL// "Name and values lists have different le"...
0x7d03  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x7d08  throw
0x7d09  newobj   instance void Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::.ctor()
0x7d0e  ldarg.0
0x7d0f  ldarg.1
0x7d10  callvirt instance string Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::RetrieveSlugXml(string templateName, int32 version)
0x7d15  stloc.0
0x7d16  ldloc.0
0x7d17  brfalse.s loc_7D26
0x7d19  ldloc.0
0x7d1a  callvirt instance string [mscorlib]System.String::Trim()
0x7d1f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7d24  brfalse.s loc_7D44
0x7d26  ldstr    aSlugxmlForTemp// "SlugXml for template name [{0}] version"...
0x7d2b  ldc.i4.2
0x7d2c  newarr   [mscorlib]System.Object
0x7d31  dup
0x7d32  ldc.i4.0
0x7d33  ldarg.0
0x7d34  stelem.ref
0x7d35  dup
0x7d36  ldc.i4.1
0x7d37  ldarg.1
0x7d38  box      [mscorlib]System.Int32
0x7d3d  stelem.ref
0x7d3e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Warning(string, object[])
0x7d43  ret
0x7d44  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x7d49  stloc.1
0x7d4a  ldloc.0
0x7d4b  call     class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.EndUserNotification.SlugService::BuildSlugNodes(string slugXml)
0x7d50  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x7d55  stloc.2
0x7d56  br       loc_7E15
0x7d5b  ldloc.2
0x7d5c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7d61  castclass [System.Xml]System.Xml.XmlNode
0x7d66  dup
0x7d67  ldstr    aName_0// "name"
0x7d6c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x7d71  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x7d76  stloc.3
0x7d77  dup
0x7d78  ldstr    aSource// "source"
0x7d7d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x7d82  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x7d87  stloc.s  4
0x7d89  ldstr    aDatatype// "datatype"
0x7d8e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x7d93  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x7d98  stloc.s  5
0x7d9a  ldloc.s  4
0x7d9c  ldstr    aGenerated// "generated"
0x7da1  ldc.i4.5
0x7da2  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x7da7  brfalse.s loc_7DDD
0x7da9  ldloc.3
0x7daa  call     bool Microsoft.Crm.EndUserNotification.SlugService::IsValidSystemSlug(string slugName)
0x7daf  brtrue.s loc_7E15
0x7db1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7db6  ldstr    aTemplateName0V// "Template name [{0}] version [{1}] requi"...
0x7dbb  ldc.i4.3
0x7dbc  newarr   [mscorlib]System.Object
0x7dc1  dup
0x7dc2  ldc.i4.0
0x7dc3  ldarg.0
0x7dc4  stelem.ref
0x7dc5  dup
0x7dc6  ldc.i4.1
0x7dc7  ldarg.1
0x7dc8  box      [mscorlib]System.Int32
0x7dcd  stelem.ref
0x7dce  dup
0x7dcf  ldc.i4.2
0x7dd0  ldloc.3
0x7dd1  stelem.ref
0x7dd2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7dd7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x7ddc  throw
0x7ddd  ldloc.s  4
0x7ddf  ldstr    aOperator// "operator"
0x7de4  ldc.i4.5
0x7de5  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x7dea  brfalse.s loc_7E03
0x7dec  ldloc.1
0x7ded  ldloc.3
0x7dee  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7df3  ldarg.0
0x7df4  ldarg.1
0x7df5  ldloc.3
0x7df6  ldloc.s  5
0x7df8  ldarg.2
0x7df9  ldarg.3
0x7dfa  ldarg.s  4
0x7dfc  call     void Microsoft.Crm.EndUserNotification.SlugService::ValidateOperatorSlug(string templateName, int32 version, string slugName, string datatype, string[] parameterNames, string[] parameterValues, bool createCheck)
0x7e01  br.s     loc_7E15
0x7e03  ldstr    aInvalidSlugSou// "Invalid slug source type : "
0x7e08  ldloc.s  4
0x7e0a  call     string [mscorlib]System.String::Concat(string, string)
0x7e0f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x7e14  throw
0x7e15  ldloc.2
0x7e16  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7e1b  brtrue   loc_7D5B
0x7e20  leave.s  loc_7E36
0x7e22  ldloc.2
0x7e23  isinst   [mscorlib]System.IDisposable
0x7e28  stloc.s  6
0x7e2a  ldloc.s  6
0x7e2c  brfalse.s loc_7E35
0x7e2e  ldloc.s  6
0x7e30  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7e35  endfinally
0x7e36  ldc.i4.0
0x7e37  stloc.s  7
0x7e39  br.s     loc_7E71
0x7e3b  ldarg.2
0x7e3c  ldloc.s  7
0x7e3e  ldelem.ref
0x7e3f  stloc.s  8
0x7e41  ldloc.1
0x7e42  ldloc.s  8
0x7e44  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x7e49  brtrue.s loc_7E6B
0x7e4b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7e50  ldstr    aExtraSlug0WasP// "Extra slug [{0}] was present"
0x7e55  ldc.i4.1
0x7e56  newarr   [mscorlib]System.Object
0x7e5b  dup
0x7e5c  ldc.i4.0
0x7e5d  ldloc.s  8
0x7e5f  stelem.ref
0x7e60  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7e65  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x7e6a  throw
0x7e6b  ldloc.s  7
0x7e6d  ldc.i4.1
0x7e6e  add
0x7e6f  stloc.s  7
0x7e71  ldloc.s  7
0x7e73  ldarg.2
0x7e74  ldlen
0x7e75  conv.i4
0x7e76  blt.s    loc_7E3B
0x7e78  ret
```
