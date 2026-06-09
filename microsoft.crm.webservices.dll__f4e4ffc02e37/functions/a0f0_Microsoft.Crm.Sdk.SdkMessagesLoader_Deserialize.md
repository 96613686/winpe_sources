# Microsoft.Crm.Sdk.SdkMessagesLoader::Deserialize

- ea: `0xa0f0`
- end: `0xa125`
- name: `Microsoft.Crm.Sdk.SdkMessagesLoader::Deserialize`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa020`

## callees

- `0xa0f0`

## pseudocode

```c

```

## disassembly

```asm
0xa0f0  ldarg.0
0xa0f1  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type)
0xa0f6  stloc.0
0xa0f7  ldarg.1
0xa0f8  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0xa0fd  stloc.1
0xa0fe  ldloc.1
0xa0ff  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0xa104  stloc.2
0xa105  ldloc.0
0xa106  ldloc.2
0xa107  callvirt instance object [System.Xml]System.Xml.Serialization.XmlSerializer::Deserialize(class [System.Xml]System.Xml.XmlReader)
0xa10c  stloc.3
0xa10d  leave.s  loc_A123
0xa10f  ldloc.2
0xa110  brfalse.s loc_A118
0xa112  ldloc.2
0xa113  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa118  endfinally
0xa119  ldloc.1
0xa11a  brfalse.s loc_A122
0xa11c  ldloc.1
0xa11d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa122  endfinally
0xa123  ldloc.3
0xa124  ret
```
