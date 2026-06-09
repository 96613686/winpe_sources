# Microsoft.Crm.Sdk.CrmSchemaFixer::CopyElementDeclarations

- ea: `0xa510`
- end: `0xa5c8`
- name: `Microsoft.Crm.Sdk.CrmSchemaFixer::CopyElementDeclarations`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xa480`

## callees

- `0x6910`
- `0xa510`
- `0xa6c0`

## pseudocode

```c

```

## disassembly

```asm
0xa510  ldarg.1
0xa511  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xa516  stloc.0
0xa517  br       loc_A5A6
0xa51c  ldloc.0
0xa51d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa522  castclass [System.Xml]System.Xml.Schema.XmlSchema
0xa527  stloc.1
0xa528  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchema::.ctor()
0xa52d  stloc.2
0xa52e  ldloc.2
0xa52f  ldloc.1
0xa530  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchema::get_TargetNamespace()
0xa535  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchema::set_TargetNamespace(string)
0xa53a  ldloc.1
0xa53b  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchema::get_Items()
0xa540  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::GetEnumerator()
0xa545  stloc.3
0xa546  br.s     loc_A588
0xa548  ldloc.3
0xa549  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObject [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator::get_Current()
0xa54e  isinst   [System.Xml]System.Xml.Schema.XmlSchemaElement
0xa553  stloc.s  4
0xa555  ldloc.s  4
0xa557  brfalse.s loc_A574
0xa559  ldarg.0
0xa55a  ldarg.2
0xa55b  ldloc.s  4
0xa55d  ldloca.s 5
0xa55f  call     instance bool Microsoft.Crm.Sdk.CrmSchemaFixer::KeepElement(class Microsoft.Crm.Sdk.SchemaContext context, class [System.Xml]System.Xml.Schema.XmlSchemaElement element, [out] class [System.Xml]System.Xml.Schema.XmlSchemaElement& target)
0xa564  brfalse.s loc_A574
0xa566  ldloc.2
0xa567  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchema::get_Items()
0xa56c  ldloc.s  5
0xa56e  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0xa573  pop
0xa574  ldloc.2
0xa575  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchema::get_Items()
0xa57a  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xa57f  brfalse.s loc_A588
0xa581  ldarg.2
0xa582  ldloc.2
0xa583  callvirt instance void Microsoft.Crm.Sdk.SchemaContext::AddSchema(class [System.Xml]System.Xml.Schema.XmlSchema newSchema)
0xa588  ldloc.3
0xa589  callvirt instance bool [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator::MoveNext()
0xa58e  brtrue.s loc_A548
0xa590  leave.s  loc_A5A6
0xa592  ldloc.3
0xa593  isinst   [mscorlib]System.IDisposable
0xa598  stloc.s  6
0xa59a  ldloc.s  6
0xa59c  brfalse.s loc_A5A5
0xa59e  ldloc.s  6
0xa5a0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa5a5  endfinally
0xa5a6  ldloc.0
0xa5a7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa5ac  brtrue   loc_A51C
0xa5b1  leave.s  loc_A5C7
0xa5b3  ldloc.0
0xa5b4  isinst   [mscorlib]System.IDisposable
0xa5b9  stloc.s  6
0xa5bb  ldloc.s  6
0xa5bd  brfalse.s loc_A5C6
0xa5bf  ldloc.s  6
0xa5c1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa5c6  endfinally
0xa5c7  ret
```
