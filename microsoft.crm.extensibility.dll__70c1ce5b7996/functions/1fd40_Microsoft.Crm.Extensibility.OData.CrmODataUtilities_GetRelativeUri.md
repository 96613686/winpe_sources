# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetRelativeUri

- ea: `0x1fd40`
- end: `0x1fd82`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetRelativeUri`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x33e0`

## callees

- `0x1fd40`

## string_xrefs

- `0x1fd5b`: `AbsoluteUri should contain ServiceRouteUri`

## pseudocode

```c

```

## disassembly

```asm
0x1fd40  ldarg.0
0x1fd41  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x1fd46  brtrue.s loc_1FD4A
0x1fd48  ldarg.0
0x1fd49  ret
0x1fd4a  ldarg.0
0x1fd4b  callvirt instance string [mscorlib]System.Object::ToString()
0x1fd50  ldarg.1
0x1fd51  callvirt instance string [mscorlib]System.Object::ToString()
0x1fd56  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x1fd5b  ldstr    aAbsoluteuriSho// "AbsoluteUri should contain ServiceRoute"...
0x1fd60  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1fd65  ldarg.0
0x1fd66  callvirt instance string [mscorlib]System.Object::ToString()
0x1fd6b  ldarg.1
0x1fd6c  callvirt instance string [mscorlib]System.Object::ToString()
0x1fd71  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1fd76  callvirt instance string [mscorlib]System.String::Substring(int32)
0x1fd7b  ldc.i4.2
0x1fd7c  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x1fd81  ret
```
