# Microsoft.Crm.Sdk.ServiceDescription::LoadTypeParsers

- ea: `0x8a60`
- end: `0x8ac3`
- name: `Microsoft.Crm.Sdk.ServiceDescription::LoadTypeParsers`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x8a40`

## callees

- `0x8a60`
- `0x8ad0`

## pseudocode

```c

```

## disassembly

```asm
0x8a60  ldarg.0
0x8a61  call     instance class [mscorlib]System.Collections.IEnumerable Microsoft.Crm.Sdk.ServiceDescription::GetTypeParsers()
0x8a66  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x8a6b  stloc.0
0x8a6c  br.s     loc_8AA7
0x8a6e  ldloc.0
0x8a6f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8a74  castclass [mscorlib]System.Type
0x8a79  stloc.1
0x8a7a  ldloc.1
0x8a7b  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x8a80  castclass Microsoft.Crm.Sdk.IFieldParser
0x8a85  stloc.2
0x8a86  ldarg.0
0x8a87  ldfld    class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Sdk.ServiceDescription::_fieldParsers
0x8a8c  ldloc.1
0x8a8d  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x8a92  ldstr    aParser_0// "Parser"
0x8a97  ldsfld   string [mscorlib]System.String::Empty
0x8a9c  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x8aa1  ldloc.2
0x8aa2  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x8aa7  ldloc.0
0x8aa8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8aad  brtrue.s loc_8A6E
0x8aaf  leave.s  loc_8AC2
0x8ab1  ldloc.0
0x8ab2  isinst   [mscorlib]System.IDisposable
0x8ab7  stloc.3
0x8ab8  ldloc.3
0x8ab9  brfalse.s loc_8AC1
0x8abb  ldloc.3
0x8abc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ac1  endfinally
0x8ac2  ret
```
