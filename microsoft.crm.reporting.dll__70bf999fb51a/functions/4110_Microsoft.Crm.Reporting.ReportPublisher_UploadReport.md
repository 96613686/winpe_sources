# Microsoft.Crm.Reporting.ReportPublisher::UploadReport

- ea: `0x4110`
- end: `0x419f`
- name: `Microsoft.Crm.Reporting.ReportPublisher::UploadReport`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x3a90`

## callees

- `0x4110`
- `0x41a0`
- `0x4260`

## string_xrefs

- `0x411f`: `The report file "{0}" has already been published. It cannot be published again under the name "{1}".`

## pseudocode

```c

```

## disassembly

```asm
0x4110  ldarg.s  0xD
0x4112  ldarg.3
0x4113  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x4118  brfalse.s loc_413D
0x411a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x411f  ldstr    aTheReportFile0// "The report file \"{0}\" has already bee"...
0x4124  ldc.i4.2
0x4125  newarr   [mscorlib]System.Object
0x412a  dup
0x412b  ldc.i4.0
0x412c  ldarg.3
0x412d  stelem.ref
0x412e  dup
0x412f  ldc.i4.1
0x4130  ldarg.2
0x4131  stelem.ref
0x4132  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4137  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x413c  throw
0x413d  ldarg.1
0x413e  ldstr    aMscrm_0// "MSCRM"
0x4143  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x4148  ldarg.3
0x4149  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x414e  dup
0x414f  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::LoadXmlDocumentFromFile(string)
0x4154  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x4159  stloc.0
0x415a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.IO.File::GetLastWriteTimeUtc(string)
0x415f  stloc.1
0x4160  ldarg.0
0x4161  ldloc.0
0x4162  ldarg.2
0x4163  ldarg.3
0x4164  ldarg.s  4
0x4166  ldarg.s  5
0x4168  ldarg.s  9
0x416a  ldarg.s  0xA
0x416c  ldarg.s  0xB
0x416e  ldloc.1
0x416f  ldarg.s  0xC
0x4171  ldarg.s  0xE
0x4173  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Reporting.ReportPublisher::CreateReportEntity(string bodyText, string reportName, string fileName, string description, int32 languageCode, object parentId, valuetype [mscorlib]System.Guid signatureId, class [mscorlib]System.Version version, valuetype [mscorlib]System.DateTime fileDate, valuetype [mscorlib]System.Guid organizationId, string reportNameOnSrs)
0x4178  stloc.2
0x4179  ldarg.0
0x417a  ldloc.2
0x417b  ldarg.s  7
0x417d  ldarg.s  6
0x417f  ldarg.s  8
0x4181  ldarg.s  0xC
0x4183  ldarg.s  0xF
0x4185  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.Reporting.ReportPublisher::UploadReportInternal(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity report, int32[] relatedEntitiesArray, int32[] categoriesArray, int32[] visibilitiesArray, valuetype [mscorlib]System.Guid organizationId, bool isProvisioning)
0x418a  stloc.3
0x418b  ldarg.s  0xD
0x418d  ldarg.3
0x418e  ldloc.3
0x418f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x4194  box      [mscorlib]System.Guid
0x4199  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x419e  ret
```
