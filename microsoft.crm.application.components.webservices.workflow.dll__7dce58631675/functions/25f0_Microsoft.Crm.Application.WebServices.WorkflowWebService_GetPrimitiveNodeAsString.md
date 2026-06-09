# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetPrimitiveNodeAsString

- ea: `0x25f0`
- end: `0x262c`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetPrimitiveNodeAsString`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2630`

## callees

- `0x25c0`
- `0x25f0`

## pseudocode

```c

```

## disassembly

```asm
0x25f0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25f5  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x25fa  stloc.0
0x25fb  ldloc.0
0x25fc  ldc.i4.1
0x25fd  call     class [System.Xml]System.Xml.XmlWriter [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlWriter(class [mscorlib]System.IO.TextWriter, bool)
0x2602  stloc.1
0x2603  ldarg.0
0x2604  ldloc.1
0x2605  ldarg.1
0x2606  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::WritePrimitiveSlugNode(class [System.Xml]System.Xml.XmlWriter xmlWriter, string value)
0x260b  leave.s  loc_2617
0x260d  ldloc.1
0x260e  brfalse.s loc_2616
0x2610  ldloc.1
0x2611  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2616  endfinally
0x2617  ldloc.0
0x2618  callvirt instance string [mscorlib]System.Object::ToString()
0x261d  stloc.2
0x261e  leave.s  loc_262A
0x2620  ldloc.0
0x2621  brfalse.s loc_2629
0x2623  ldloc.0
0x2624  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2629  endfinally
0x262a  ldloc.2
0x262b  ret
```
