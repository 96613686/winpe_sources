# Microsoft.Crm.SharedDatabase.DatabaseMetadata::LoadMetadataXmlFromDatabase_1

- ea: `0x60410`
- end: `0x6049f`
- name: `Microsoft.Crm.SharedDatabase.DatabaseMetadata::LoadMetadataXmlFromDatabase_1`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x603c0`

## callees

- `0xd5f0`
- `0xdaf0`
- `0x60410`

## string_xrefs

- `0x60422`: `SELECT TOP 1 {0}MetadataXml, MaxReplBlobLengthBytes FROM {0}Metadata ORDER BY InstalledOn DESC`
- `0x60441`: `LoadMetadataXmlFromDatabase`
- `0x60446`: `D:\a\1\s\src\Platform\Core\DataServices\Cache\StaticDatabaseCache.cs`
- `0x60456`: `{0}MetadataXml`

## pseudocode

```c

```

## disassembly

```asm
0x60410  ldarg.2
0x60411  ldc.i4.0
0x60412  stind.i4
0x60413  ldnull
0x60414  stloc.0
0x60415  ldarg.0
0x60416  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand()
0x6041b  stloc.1
0x6041c  ldloc.1
0x6041d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x60422  ldstr    aSelectTop10Met// "SELECT TOP 1 {0}MetadataXml, MaxReplBlo"...
0x60427  ldc.i4.1
0x60428  newarr   [mscorlib]System.Object
0x6042d  dup
0x6042e  ldc.i4.0
0x6042f  ldarg.1
0x60430  stelem.ref
0x60431  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x60436  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6043b  ldloc.1
0x6043c  ldc.i4   0xA4
0x60441  ldstr    aLoadmetadataxm// "LoadMetadataXmlFromDatabase"
0x60446  ldstr    aDA1SSrcPlatfor_43// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x6044b  call     class [System.Data]System.Data.IDataReader Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x60450  stloc.2
0x60451  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x60456  ldstr    a0Metadataxml// "{0}MetadataXml"
0x6045b  ldc.i4.1
0x6045c  newarr   [mscorlib]System.Object
0x60461  dup
0x60462  ldc.i4.0
0x60463  ldarg.1
0x60464  stelem.ref
0x60465  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6046a  stloc.3
0x6046b  ldloc.2
0x6046c  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x60471  pop
0x60472  ldloc.2
0x60473  ldloc.3
0x60474  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x60479  isinst   [mscorlib]System.String
0x6047e  stloc.0
0x6047f  ldarg.2
0x60480  ldloc.2
0x60481  ldstr    aMaxreplbloblen// "MaxReplBlobLengthBytes"
0x60486  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x6048b  unbox.any [mscorlib]System.Int32
0x60490  stind.i4
0x60491  leave.s  loc_6049D
0x60493  ldloc.2
0x60494  brfalse.s loc_6049C
0x60496  ldloc.2
0x60497  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6049c  endfinally
0x6049d  ldloc.0
0x6049e  ret
```
