# Microsoft.Crm.Reporting.RuntimeReportServer::DeserializeCrmParameterValues

- ea: `0x6880`
- end: `0x68ff`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::DeserializeCrmParameterValues`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6000`

## callees

- `0x6880`

## pseudocode

```c

```

## disassembly

```asm
0x6880  ldarg.0
0x6881  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x6886  stloc.2
0x6887  ldtoken  class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.CrmParameterValue[]
0x688c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6891  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type)
0x6896  ldloc.2
0x6897  callvirt instance object [System.Xml]System.Xml.Serialization.XmlSerializer::Deserialize(class [mscorlib]System.IO.TextReader)
0x689c  castclass class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.CrmParameterValue[]
0x68a1  stloc.0
0x68a2  leave.s  loc_68AE
0x68a4  ldloc.2
0x68a5  brfalse.s loc_68AD
0x68a7  ldloc.2
0x68a8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x68ad  endfinally
0x68ae  ldloc.0
0x68af  ldlen
0x68b0  conv.i4
0x68b1  newarr   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue
0x68b6  stloc.1
0x68b7  ldc.i4.0
0x68b8  stloc.3
0x68b9  br.s     loc_68F7
0x68bb  ldloc.1
0x68bc  ldloc.3
0x68bd  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue::.ctor()
0x68c2  stelem.ref
0x68c3  ldloc.1
0x68c4  ldloc.3
0x68c5  ldelem.ref
0x68c6  ldloc.0
0x68c7  ldloc.3
0x68c8  ldelem.ref
0x68c9  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.CrmParameterValue::get_Name()
0x68ce  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue::set_Name(string)
0x68d3  ldloc.1
0x68d4  ldloc.3
0x68d5  ldelem.ref
0x68d6  ldloc.0
0x68d7  ldloc.3
0x68d8  ldelem.ref
0x68d9  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.CrmParameterValue::get_Name()
0x68de  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue::set_Label(string)
0x68e3  ldloc.1
0x68e4  ldloc.3
0x68e5  ldelem.ref
0x68e6  ldloc.0
0x68e7  ldloc.3
0x68e8  ldelem.ref
0x68e9  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.CrmParameterValue::get_Value()
0x68ee  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue::set_Value(string)
0x68f3  ldloc.3
0x68f4  ldc.i4.1
0x68f5  add
0x68f6  stloc.3
0x68f7  ldloc.3
0x68f8  ldloc.0
0x68f9  ldlen
0x68fa  conv.i4
0x68fb  blt.s    loc_68BB
0x68fd  ldloc.1
0x68fe  ret
```
