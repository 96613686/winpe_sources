# Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::WriteToFile

- ea: `0x13300`
- end: `0x1339f`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::WriteToFile`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x15d30`

## callees

- `0x13300`

## string_xrefs

- `0x13301`: `filePath must be provided to write the RollbackDescriptor from file`
- `0x13382`: `Error occured while writing rollback descriptor: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x13300  ldarg.1
0x13301  ldstr    aFilepathMustBe_0// "filePath must be provided to write the "...
0x13306  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1330b  ldarg.0
0x1330c  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x13311  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type)
0x13316  stloc.0
0x13317  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x1331c  stloc.1
0x1331d  ldloc.1
0x1331e  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x13323  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Encoding(class [mscorlib]System.Text.Encoding)
0x13328  ldloc.1
0x13329  ldc.i4.1
0x1332a  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Indent(bool)
0x1332f  ldarg.1
0x13330  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(string)
0x13335  stloc.2
0x13336  ldloc.2
0x13337  ldloc.1
0x13338  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.IO.TextWriter, class [System.Xml]System.Xml.XmlWriterSettings)
0x1333d  stloc.3
0x1333e  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces::.ctor()
0x13343  stloc.s  4
0x13345  ldloc.s  4
0x13347  ldsfld   string [mscorlib]System.String::Empty
0x1334c  ldsfld   string [mscorlib]System.String::Empty
0x13351  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces::Add(string, string)
0x13356  ldloc.0
0x13357  ldloc.3
0x13358  ldarg.0
0x13359  ldloc.s  4
0x1335b  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializer::Serialize(class [System.Xml]System.Xml.XmlWriter, object, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x13360  leave.s  loc_1336C
0x13362  ldloc.3
0x13363  brfalse.s loc_1336B
0x13365  ldloc.3
0x13366  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1336b  endfinally
0x1336c  ldloc.2
0x1336d  callvirt instance void [mscorlib]System.IO.TextWriter::Close()
0x13372  leave.s  loc_1337E
0x13374  ldloc.2
0x13375  brfalse.s loc_1337D
0x13377  ldloc.2
0x13378  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1337d  endfinally
0x1337e  leave.s  loc_1339E
0x13380  stloc.s  5
0x13382  ldstr    aErrorOccuredWh// "Error occured while writing rollback de"...
0x13387  ldc.i4.1
0x13388  newarr   [mscorlib]System.Object
0x1338d  dup
0x1338e  ldc.i4.0
0x1338f  ldloc.s  5
0x13391  callvirt instance string [mscorlib]System.Exception::get_Message()
0x13396  stelem.ref
0x13397  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x1339c  rethrow
0x1339e  ret
```
