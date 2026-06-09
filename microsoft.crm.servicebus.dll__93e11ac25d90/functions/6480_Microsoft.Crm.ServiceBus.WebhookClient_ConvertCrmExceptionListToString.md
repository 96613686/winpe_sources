# Microsoft.Crm.ServiceBus.WebhookClient::ConvertCrmExceptionListToString

- ea: `0x6480`
- end: `0x64ec`
- name: `Microsoft.Crm.ServiceBus.WebhookClient::ConvertCrmExceptionListToString`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x68c0`

## callees

- `0x6480`

## pseudocode

```c

```

## disassembly

```asm
0x6480  ldarg.1
0x6481  brfalse.s loc_648B
0x6483  ldarg.1
0x6484  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.CrmException>::get_Count()
0x6489  brtrue.s loc_648D
0x648b  ldnull
0x648c  ret
0x648d  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x6492  stloc.0
0x6493  ldarg.1
0x6494  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.CrmException>::GetEnumerator()
0x6499  stloc.1
0x649a  br.s     loc_64CC
0x649c  ldloca.s 1
0x649e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.CrmException>::get_Current()
0x64a3  stloc.2
0x64a4  ldloc.0
0x64a5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x64aa  ldstr    a0Detail1// "{0}Detail: {1}"
0x64af  ldc.i4.2
0x64b0  newarr   [mscorlib]System.Object
0x64b5  dup
0x64b6  ldc.i4.0
0x64b7  call     string [mscorlib]System.Environment::get_NewLine()
0x64bc  stelem.ref
0x64bd  dup
0x64be  ldc.i4.1
0x64bf  ldloc.2
0x64c0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x64c5  stelem.ref
0x64c6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x64cb  pop
0x64cc  ldloca.s 1
0x64ce  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.CrmException>::MoveNext()
0x64d3  brtrue.s loc_649C
0x64d5  leave.s  loc_64E5
0x64d7  ldloca.s 1
0x64d9  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.CrmException>
0x64df  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x64e4  endfinally
0x64e5  ldloc.0
0x64e6  callvirt instance string [mscorlib]System.Object::ToString()
0x64eb  ret
```
