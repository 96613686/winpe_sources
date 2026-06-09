# Microsoft.Crm.Sdk.CrmSchemaFixer::ReplaceSchemas

- ea: `0xa480`
- end: `0xa506`
- name: `Microsoft.Crm.Sdk.CrmSchemaFixer::ReplaceSchemas`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0xa140`

## callees

- `0x67b0`
- `0x68b0`
- `0x6da0`
- `0x6f70`
- `0x77d0`
- `0x7db0`
- `0x86f0`
- `0xa480`
- `0xa510`

## pseudocode

```c

```

## disassembly

```asm
0xa480  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSchemas::.ctor()
0xa485  stloc.0
0xa486  ldloc.0
0xa487  ldarg.0
0xa488  ldfld    class Microsoft.Crm.Sdk.ServiceDescription Microsoft.Crm.Sdk.CrmSchemaFixer::_serviceDescription
0xa48d  ldarg.0
0xa48e  ldfld    string Microsoft.Crm.Sdk.CrmSchemaFixer::_currentNamespace
0xa493  ldarg.0
0xa494  ldfld    bool Microsoft.Crm.Sdk.CrmSchemaFixer::_renderPrivateMethods
0xa499  newobj   instance void Microsoft.Crm.Sdk.SchemaContext::.ctor(class [System.Xml]System.Xml.Serialization.XmlSchemas schemas, class Microsoft.Crm.Sdk.ServiceDescription serviceDescription, string namespaceName, bool renderPrivate)
0xa49e  stloc.1
0xa49f  newobj   instance void Microsoft.Crm.Sdk.ConcreteBusinessEntitySchemaBuilder::.ctor()
0xa4a4  ldloc.1
0xa4a5  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName Microsoft.Crm.Sdk.ConcreteBusinessEntitySchemaBuilder::BuildSchema(class Microsoft.Crm.Sdk.SchemaContext context)
0xa4aa  pop
0xa4ab  ldarg.0
0xa4ac  ldfld    class Microsoft.Crm.Sdk.ServiceDescription Microsoft.Crm.Sdk.CrmSchemaFixer::_serviceDescription
0xa4b1  callvirt instance class [mscorlib]System.Collections.IList Microsoft.Crm.Sdk.ServiceDescription::get_TypesToExport()
0xa4b6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0xa4bb  stloc.2
0xa4bc  br.s     loc_A4D5
0xa4be  ldloc.2
0xa4bf  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa4c4  castclass [mscorlib]System.Type
0xa4c9  call     class Microsoft.Crm.Sdk.ISchemaBuilder Microsoft.Crm.Sdk.SchemaBuilderFactory::Create(class [mscorlib]System.Type type)
0xa4ce  ldloc.1
0xa4cf  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName Microsoft.Crm.Sdk.ISchemaBuilder::BuildSchema(class Microsoft.Crm.Sdk.SchemaContext context)
0xa4d4  pop
0xa4d5  ldloc.2
0xa4d6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa4db  brtrue.s loc_A4BE
0xa4dd  leave.s  loc_A4F0
0xa4df  ldloc.2
0xa4e0  isinst   [mscorlib]System.IDisposable
0xa4e5  stloc.3
0xa4e6  ldloc.3
0xa4e7  brfalse.s loc_A4EF
0xa4e9  ldloc.3
0xa4ea  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa4ef  endfinally
0xa4f0  ldarg.0
0xa4f1  ldarg.1
0xa4f2  ldloc.1
0xa4f3  call     instance void Microsoft.Crm.Sdk.CrmSchemaFixer::CopyElementDeclarations(class [System.Xml]System.Xml.Serialization.XmlSchemas oldSchemas, class Microsoft.Crm.Sdk.SchemaContext context)
0xa4f8  ldloc.0
0xa4f9  ldarg.1
0xa4fa  ldarg.0
0xa4fb  ldfld    string Microsoft.Crm.Sdk.CrmSchemaFixer::_currentNamespace
0xa500  call     void Microsoft.Crm.Sdk.SchemaHelper::CopySortedSchemas(class [System.Xml]System.Xml.Serialization.XmlSchemas source, class [System.Xml]System.Xml.Serialization.XmlSchemas destination, string currentNameSpace)
0xa505  ret
```
