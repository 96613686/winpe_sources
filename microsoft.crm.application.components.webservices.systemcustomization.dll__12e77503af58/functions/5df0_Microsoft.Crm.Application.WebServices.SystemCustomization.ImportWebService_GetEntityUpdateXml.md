# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::GetEntityUpdateXml

- ea: `0x5df0`
- end: `0x5e47`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::GetEntityUpdateXml`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x5d20`

## string_xrefs

- `0x5df5`: `\n			<entity xmlns="http://schemas.microsoft.com/crm/2006/WebServices">\n				<entityid>{0}</entityid>\n				<singularname>{1}</singularname>\n				<pluralname>{2}</pluralname>\n				<displayareas>\n					<displayarea id="Workplace" displayed="true" />\n				</displayareas>\n				<mailmergecheck>false</mailmergecheck>\n				<connection>\n					<connection>false</connection>\n				</connection>\n				<collaboration>false</collaboration>\n				<autoroutetoownerqueue>false</autoroutetoownerqueue>`

## pseudocode

```c

```

## disassembly

```asm
0x5df0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5df5  ldstr    aEntityXmlnsHtt// "\r\n\t\t\t<entity xmlns=\"http://schema"...
0x5dfa  ldc.i4.5
0x5dfb  newarr   [mscorlib]System.Object
0x5e00  dup
0x5e01  ldc.i4.0
0x5e02  ldarg.1
0x5e03  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x5e08  box      [mscorlib]System.Guid
0x5e0d  stelem.ref
0x5e0e  dup
0x5e0f  ldc.i4.1
0x5e10  ldarg.1
0x5e11  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_OriginalLocalizedName()
0x5e16  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0x5e1b  stelem.ref
0x5e1c  dup
0x5e1d  ldc.i4.2
0x5e1e  ldarg.1
0x5e1f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_OriginalLocalizedCollectionName()
0x5e24  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0x5e29  stelem.ref
0x5e2a  dup
0x5e2b  ldc.i4.3
0x5e2c  ldc.i4.0
0x5e2d  box      [mscorlib]System.Boolean
0x5e32  stelem.ref
0x5e33  dup
0x5e34  ldc.i4.4
0x5e35  ldarg.1
0x5e36  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsDuplicateCheckSupported()
0x5e3b  box      [mscorlib]System.Boolean
0x5e40  stelem.ref
0x5e41  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5e46  ret
```
