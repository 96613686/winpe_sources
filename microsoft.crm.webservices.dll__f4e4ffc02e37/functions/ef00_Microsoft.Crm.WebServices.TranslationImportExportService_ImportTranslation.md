# Microsoft.Crm.WebServices.TranslationImportExportService::ImportTranslation

- ea: `0xef00`
- end: `0xf094`
- name: `Microsoft.Crm.WebServices.TranslationImportExportService::ImportTranslation`
- size: `404`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xd810`
- `0xe930`

## callees

- `0xef00`
- `0xf0a0`

## string_xrefs

- `0xef01`: `translationXmlFileName`
- `0xeffb`: `Error: The translation file is missing in zip file. The compressed file must contain the following file in its root: {0}. Throwing ImportTranslationsBadZipFileError({1}).`

## pseudocode

```c

```

## disassembly

```asm
0xef00  ldarg.1
0xef01  ldstr    aTranslationxml// "translationXmlFileName"
0xef06  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xef0b  ldarg.2
0xef0c  ldstr    aTranslationfil// "translationFile"
0xef11  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xef16  ldarg.3
0xef17  ldobj    [mscorlib]System.Guid
0xef1c  box      [mscorlib]System.Guid
0xef21  ldstr    aImportjobid// "importJobId"
0xef26  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xef2b  ldc.i4.1
0xef2c  newarr   [mscorlib]System.String
0xef31  dup
0xef32  ldc.i4.0
0xef33  ldarg.1
0xef34  stelem.ref
0xef35  stloc.0
0xef36  ldsfld   string [mscorlib]System.String::Empty
0xef3b  stloc.1
0xef3c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xef41  ldstr    aImportBegin0Im// "Import_BEGIN_{0}.ImportTranslation().Un"...
0xef46  ldc.i4.1
0xef47  newarr   [mscorlib]System.Object
0xef4c  dup
0xef4d  ldc.i4.0
0xef4e  ldarg.0
0xef4f  stelem.ref
0xef50  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xef55  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0xef5a  ldarg.2
0xef5b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.CrmUnzip::.ctor(unsigned int8[])
0xef60  stloc.2
0xef61  ldloc.2
0xef62  callvirt instance class [System]System.Uri[] [Microsoft.Crm]Microsoft.Crm.CrmUnzip::GetDirectory()
0xef67  stloc.3
0xef68  ldc.i4.0
0xef69  stloc.s  4
0xef6b  br.s     loc_EFB3
0xef6d  ldloc.3
0xef6e  ldloc.s  4
0xef70  ldelem.ref
0xef71  stloc.s  5
0xef73  ldloc.s  5
0xef75  callvirt instance string [mscorlib]System.Object::ToString()
0xef7a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xef7f  ldstr    a0_1// "/{0}"
0xef84  ldc.i4.1
0xef85  newarr   [mscorlib]System.Object
0xef8a  dup
0xef8b  ldc.i4.0
0xef8c  ldarg.1
0xef8d  stelem.ref
0xef8e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xef93  call     bool [mscorlib]System.String::op_Equality(string, string)
0xef98  brfalse.s loc_EFAD
0xef9a  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0xef9f  ldloc.2
0xefa0  ldloc.s  5
0xefa2  callvirt instance unsigned int8[] [Microsoft.Crm]Microsoft.Crm.CrmUnzip::GetPart(class [System]System.Uri)
0xefa7  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0xefac  stloc.1
0xefad  ldloc.s  4
0xefaf  ldc.i4.1
0xefb0  add
0xefb1  stloc.s  4
0xefb3  ldloc.s  4
0xefb5  ldloc.3
0xefb6  ldlen
0xefb7  conv.i4
0xefb8  blt.s    loc_EF6D
0xefba  leave.s  loc_EFC6
0xefbc  ldloc.2
0xefbd  brfalse.s loc_EFC5
0xefbf  ldloc.2
0xefc0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xefc5  endfinally
0xefc6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xefcb  ldstr    aImportEnd0Impo// "Import_END_{0}.ImportTranslation().Unzi"...
0xefd0  ldc.i4.1
0xefd1  newarr   [mscorlib]System.Object
0xefd6  dup
0xefd7  ldc.i4.0
0xefd8  ldarg.0
0xefd9  stelem.ref
0xefda  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xefdf  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0xefe4  ldloc.1
0xefe5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xefea  brfalse.s loc_F037
0xefec  ldnull
0xefed  ldarg.s  4
0xefef  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xeff4  ldc.i4.s 0x17
0xeff6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xeffb  ldstr    aErrorTheTransl// "Error: The translation file is missing "...
0xf000  ldc.i4.2
0xf001  newarr   [mscorlib]System.Object
0xf006  dup
0xf007  ldc.i4.0
0xf008  ldarg.1
0xf009  stelem.ref
0xf00a  dup
0xf00b  ldc.i4.1
0xf00c  ldc.i4   0x80048061
0xf011  box      [mscorlib]System.Int32
0xf016  stelem.ref
0xf017  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf01c  ldc.i4.0
0xf01d  newarr   [mscorlib]System.Object
0xf022  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf027  ldc.i4   0x80048061
0xf02c  ldloc.0
0xf02d  stloc.s  6
0xf02f  ldloc.s  6
0xf031  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xf036  throw
0xf037  ldarg.0
0xf038  ldloc.1
0xf039  ldarg.3
0xf03a  ldarg.s  4
0xf03c  call     instance void Microsoft.Crm.WebServices.TranslationImportExportService::ImportTranslationsInternal(string crmTranslationsXml, valuetype [mscorlib]System.Guid& importJobId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xf041  leave.s  loc_F093
0xf043  stloc.s  7
0xf045  ldloc.s  7
0xf047  ldarg.s  4
0xf049  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xf04e  ldc.i4.s 0x17
0xf050  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf055  ldstr    aErrorCaughtFil// "Error: Caught FileFormatException while"...
0xf05a  ldc.i4.2
0xf05b  newarr   [mscorlib]System.Object
0xf060  dup
0xf061  ldc.i4.0
0xf062  ldarg.1
0xf063  stelem.ref
0xf064  dup
0xf065  ldc.i4.1
0xf066  ldc.i4   0x80048061
0xf06b  box      [mscorlib]System.Int32
0xf070  stelem.ref
0xf071  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf076  ldc.i4.0
0xf077  newarr   [mscorlib]System.Object
0xf07c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf081  ldloc.s  7
0xf083  ldc.i4   0x80048061
0xf088  ldloc.0
0xf089  stloc.s  6
0xf08b  ldloc.s  6
0xf08d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(class [mscorlib]System.Exception, int32, object[])
0xf092  throw
0xf093  ret
```
