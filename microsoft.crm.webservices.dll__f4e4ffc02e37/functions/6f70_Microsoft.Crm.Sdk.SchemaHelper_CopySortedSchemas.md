# Microsoft.Crm.Sdk.SchemaHelper::CopySortedSchemas

- ea: `0x6f70`
- end: `0x708b`
- name: `Microsoft.Crm.Sdk.SchemaHelper::CopySortedSchemas`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xa480`

## callees

- `0x6f50`
- `0x6f70`
- `0x7090`
- `0x100f0`

## string_xrefs

- `0x7078`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x6f70  ldarg.1
0x6f71  callvirt instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x6f76  ldarg.0
0x6f77  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x6f7c  stloc.0
0x6f7d  br       loc_7056
0x6f82  ldloc.0
0x6f83  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6f88  castclass [System.Xml]System.Xml.Schema.XmlSchema
0x6f8d  stloc.1
0x6f8e  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchema::.ctor()
0x6f93  stloc.2
0x6f94  ldloc.2
0x6f95  ldloc.1
0x6f96  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchema::get_TargetNamespace()
0x6f9b  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchema::set_TargetNamespace(string)
0x6fa0  ldloc.2
0x6fa1  ldloc.1
0x6fa2  callvirt instance valuetype [System.Xml]System.Xml.Schema.XmlSchemaForm [System.Xml]System.Xml.Schema.XmlSchema::get_ElementFormDefault()
0x6fa7  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchema::set_ElementFormDefault(valuetype [System.Xml]System.Xml.Schema.XmlSchemaForm)
0x6fac  ldloc.1
0x6fad  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchema::get_Includes()
0x6fb2  newobj   instance void XmlSchemaObjectComparer::.ctor()
0x6fb7  call     class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Sdk.SchemaHelper::CreateSortedList(class [mscorlib]System.Collections.ICollection source, class [mscorlib]System.Collections.IComparer comparer)
0x6fbc  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x6fc1  stloc.3
0x6fc2  br.s     loc_6FDF
0x6fc4  ldloc.3
0x6fc5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6fca  castclass [System.Xml]System.Xml.Schema.XmlSchemaObject
0x6fcf  stloc.s  4
0x6fd1  ldloc.2
0x6fd2  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchema::get_Includes()
0x6fd7  ldloc.s  4
0x6fd9  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x6fde  pop
0x6fdf  ldloc.3
0x6fe0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6fe5  brtrue.s loc_6FC4
0x6fe7  leave.s  loc_6FFD
0x6fe9  ldloc.3
0x6fea  isinst   [mscorlib]System.IDisposable
0x6fef  stloc.s  5
0x6ff1  ldloc.s  5
0x6ff3  brfalse.s loc_6FFC
0x6ff5  ldloc.s  5
0x6ff7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6ffc  endfinally
0x6ffd  ldloc.1
0x6ffe  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchema::get_Items()
0x7003  newobj   instance void XmlSchemaObjectComparer::.ctor()
0x7008  call     class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Sdk.SchemaHelper::CreateSortedList(class [mscorlib]System.Collections.ICollection source, class [mscorlib]System.Collections.IComparer comparer)
0x700d  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x7012  stloc.3
0x7013  br.s     loc_7030
0x7015  ldloc.3
0x7016  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x701b  castclass [System.Xml]System.Xml.Schema.XmlSchemaObject
0x7020  stloc.s  6
0x7022  ldloc.2
0x7023  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchema::get_Items()
0x7028  ldloc.s  6
0x702a  callvirt instance int32 [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::Add(class [System.Xml]System.Xml.Schema.XmlSchemaObject)
0x702f  pop
0x7030  ldloc.3
0x7031  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7036  brtrue.s loc_7015
0x7038  leave.s  loc_704E
0x703a  ldloc.3
0x703b  isinst   [mscorlib]System.IDisposable
0x7040  stloc.s  5
0x7042  ldloc.s  5
0x7044  brfalse.s loc_704D
0x7046  ldloc.s  5
0x7048  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x704d  endfinally
0x704e  ldarg.1
0x704f  ldloc.2
0x7050  callvirt instance int32 [System.Xml]System.Xml.Serialization.XmlSchemas::Add(class [System.Xml]System.Xml.Schema.XmlSchema)
0x7055  pop
0x7056  ldloc.0
0x7057  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x705c  brtrue   loc_6F82
0x7061  leave.s  loc_7077
0x7063  ldloc.0
0x7064  isinst   [mscorlib]System.IDisposable
0x7069  stloc.s  5
0x706b  ldloc.s  5
0x706d  brfalse.s loc_7076
0x706f  ldloc.s  5
0x7071  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7076  endfinally
0x7077  ldarg.2
0x7078  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0x707d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7082  brfalse.s loc_708A
0x7084  ldarg.1
0x7085  call     void Microsoft.Crm.Sdk.SchemaHelper::SortByDependency(class [System.Xml]System.Xml.Serialization.XmlSchemas schemas)
0x708a  ret
```
