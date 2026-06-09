# Microsoft.Crm.Sdk.ServiceDescription::LoadTypeFormatters

- ea: `0x8ae0`
- end: `0x8b4b`
- name: `Microsoft.Crm.Sdk.ServiceDescription::LoadTypeFormatters`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x8a40`

## callees

- `0x8ae0`
- `0x8b50`

## pseudocode

```c

```

## disassembly

```asm
0x8ae0  ldarg.0
0x8ae1  call     instance class [mscorlib]System.Collections.IEnumerable Microsoft.Crm.Sdk.ServiceDescription::GetTypeFormatters()
0x8ae6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x8aeb  stloc.0
0x8aec  br.s     loc_8B2F
0x8aee  ldloc.0
0x8aef  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8af4  castclass [mscorlib]System.Type
0x8af9  stloc.1
0x8afa  ldloc.1
0x8afb  callvirt instance bool [mscorlib]System.Type::get_IsAbstract()
0x8b00  brtrue.s loc_8B2F
0x8b02  ldloc.1
0x8b03  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x8b08  castclass Microsoft.Crm.Sdk.IFieldFormatter
0x8b0d  stloc.2
0x8b0e  ldarg.0
0x8b0f  ldfld    class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Sdk.ServiceDescription::_fieldFormatters
0x8b14  ldloc.1
0x8b15  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x8b1a  ldstr    aFormatter_0// "Formatter"
0x8b1f  ldsfld   string [mscorlib]System.String::Empty
0x8b24  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x8b29  ldloc.2
0x8b2a  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x8b2f  ldloc.0
0x8b30  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8b35  brtrue.s loc_8AEE
0x8b37  leave.s  loc_8B4A
0x8b39  ldloc.0
0x8b3a  isinst   [mscorlib]System.IDisposable
0x8b3f  stloc.3
0x8b40  ldloc.3
0x8b41  brfalse.s loc_8B49
0x8b43  ldloc.3
0x8b44  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8b49  endfinally
0x8b4a  ret
```
