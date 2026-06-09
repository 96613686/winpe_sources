# Microsoft.Crm.Tools.ImportExportPublish.TranslationImportHandlerBase::ValidateInformationSheet

- ea: `0x80c70`
- end: `0x80df5`
- name: `Microsoft.Crm.Tools.ImportExportPublish.TranslationImportHandlerBase::ValidateInformationSheet`
- size: `389`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x81820`
- `0x82860`

## callees

- `0x63df0`
- `0x809a0`
- `0x809c0`
- `0x80c70`
- `0x8ba70`
- `0x8c1f0`

## string_xrefs

- `0x80c94`: `Translations xml is invalid. No row found in worksheet {0}.`
- `0x80cf4`: `Translations xml is invalid. Invalid OrgId row found in worksheet {0}.`
- `0x80d59`: `Translations xml is invalid. OrganizationId found in worksheet {0}, Line 0, Column 2 does not match with the current organization's id.`
- `0x80da6`: `Translations xml is invalid. Invalid OrganizationId found in worksheet {0}, Line 0, Column 2. | Details: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x80c70  ldarg.1
0x80c71  ldstr    aInformation// "Information"
0x80c76  ldc.i4.0
0x80c77  ldc.i4.0
0x80c78  call     class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.Tools.ImportExportPublish.TranslationsHelper::ReadRowNodes(class [System.Xml]System.Xml.XmlDocument xdoc, string worksheetName, [opt] int32 pageSize, [opt] int32 startRow)
0x80c7d  stloc.0
0x80c7e  ldloc.0
0x80c7f  brfalse.s loc_80C89
0x80c81  ldloc.0
0x80c82  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x80c87  brtrue.s loc_80CD3
0x80c89  ldarg.0
0x80c8a  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.TranslationImportHandlerBase::get_Tracer()
0x80c8f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x80c94  ldstr    aTranslationsXm_1// "Translations xml is invalid. No row fou"...
0x80c99  ldc.i4.1
0x80c9a  newarr   [mscorlib]System.Object
0x80c9f  dup
0x80ca0  ldc.i4.0
0x80ca1  ldstr    aInformation// "Information"
0x80ca6  stelem.ref
0x80ca7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x80cac  ldc.i4   0x80044249
0x80cb1  ldc.i4.0
0x80cb2  newarr   [mscorlib]System.Object
0x80cb7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x80cbc  ldc.i4.1
0x80cbd  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x80cc2  ldc.i4   0x80044249
0x80cc7  ldc.i4.0
0x80cc8  newarr   [mscorlib]System.Object
0x80ccd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x80cd2  throw
0x80cd3  ldloc.0
0x80cd4  ldc.i4.0
0x80cd5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x80cda  call     string[] Microsoft.Crm.Tools.ImportExportPublish.TranslationsHelper::GetCellValuesFromRow(class [System.Xml]System.Xml.XmlNode row)
0x80cdf  stloc.1
0x80ce0  ldloc.1
0x80ce1  brfalse.s loc_80CE9
0x80ce3  ldloc.1
0x80ce4  ldlen
0x80ce5  conv.i4
0x80ce6  ldc.i4.2
0x80ce7  beq.s    loc_80D33
0x80ce9  ldarg.0
0x80cea  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.TranslationImportHandlerBase::get_Tracer()
0x80cef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x80cf4  ldstr    aTranslationsXm_2// "Translations xml is invalid. Invalid Or"...
0x80cf9  ldc.i4.1
0x80cfa  newarr   [mscorlib]System.Object
0x80cff  dup
0x80d00  ldc.i4.0
0x80d01  ldstr    aInformation// "Information"
0x80d06  stelem.ref
0x80d07  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x80d0c  ldc.i4   0x80044249
0x80d11  ldc.i4.0
0x80d12  newarr   [mscorlib]System.Object
0x80d17  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x80d1c  ldc.i4.1
0x80d1d  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x80d22  ldc.i4   0x80044249
0x80d27  ldc.i4.0
0x80d28  newarr   [mscorlib]System.Object
0x80d2d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x80d32  throw
0x80d33  nop
0x80d34  ldloc.1
0x80d35  ldc.i4.1
0x80d36  ldelem.ref
0x80d37  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x80d3c  ldarg.0
0x80d3d  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.TranslationImportHandlerBase::get_Context()
0x80d42  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x80d47  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x80d4c  brfalse.s loc_80D98
0x80d4e  ldarg.0
0x80d4f  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.TranslationImportHandlerBase::get_Tracer()
0x80d54  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x80d59  ldstr    aTranslationsXm_3// "Translations xml is invalid. Organizati"...
0x80d5e  ldc.i4.1
0x80d5f  newarr   [mscorlib]System.Object
0x80d64  dup
0x80d65  ldc.i4.0
0x80d66  ldstr    aInformation// "Information"
0x80d6b  stelem.ref
0x80d6c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x80d71  ldc.i4   0x80044249
0x80d76  ldc.i4.0
0x80d77  newarr   [mscorlib]System.Object
0x80d7c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x80d81  ldc.i4.1
0x80d82  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x80d87  ldc.i4   0x80044248
0x80d8c  ldc.i4.0
0x80d8d  newarr   [mscorlib]System.Object
0x80d92  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x80d97  throw
0x80d98  leave.s  loc_80DF4
0x80d9a  stloc.2
0x80d9b  ldarg.0
0x80d9c  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.TranslationImportHandlerBase::get_Tracer()
0x80da1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x80da6  ldstr    aTranslationsXm_4// "Translations xml is invalid. Invalid Or"...
0x80dab  ldc.i4.2
0x80dac  newarr   [mscorlib]System.Object
0x80db1  dup
0x80db2  ldc.i4.0
0x80db3  ldstr    aInformation// "Information"
0x80db8  stelem.ref
0x80db9  dup
0x80dba  ldc.i4.1
0x80dbb  ldloc.2
0x80dbc  stelem.ref
0x80dbd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x80dc2  ldc.i4   0x80044249
0x80dc7  ldc.i4.0
0x80dc8  newarr   [mscorlib]System.Object
0x80dcd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x80dd2  ldc.i4.1
0x80dd3  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x80dd8  ldloc.2
0x80dd9  ldc.i4   0x80044249
0x80dde  ldc.i4.0
0x80ddf  newarr   [mscorlib]System.Object
0x80de4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(class [mscorlib]System.Exception, int32, object[])
0x80de9  throw
0x80dea  ldloc.0
0x80deb  brfalse.s loc_80DF3
0x80ded  ldloc.0
0x80dee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x80df3  endfinally
0x80df4  ret
```
