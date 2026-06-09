# Microsoft.Crm.Asynchronous.OrganizationStatisticDataAccess::ExecuteSqlScalarCommand

- ea: `0xbee0`
- end: `0xbf68`
- name: `Microsoft.Crm.Asynchronous.OrganizationStatisticDataAccess::ExecuteSqlScalarCommand`
- size: `136`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb640`
- `0xb990`

## callees

- `0xbee0`

## pseudocode

```c

```

## disassembly

```asm
0xbee0  ldarg.0
0xbee1  ldarg.1
0xbee2  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0xbee7  stloc.0
0xbee8  ldloc.0
0xbee9  isinst   valuetype [mscorlib]System.Nullable`1<int32>
0xbeee  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0xbef3  stloc.1
0xbef4  ldloca.s 1
0xbef6  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xbefb  brfalse.s loc_BF05
0xbefd  ldloca.s 1
0xbeff  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xbf04  ret
0xbf05  ldloc.0
0xbf06  isinst   valuetype [mscorlib]System.Nullable`1<int64>
0xbf0b  unbox.any valuetype [mscorlib]System.Nullable`1<int64>
0xbf10  stloc.2
0xbf11  ldloca.s 2
0xbf13  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0xbf18  brfalse.s loc_BF52
0xbf1a  ldloc.2
0xbf1b  stloc.3
0xbf1c  ldc.i4   0x7FFFFFFF
0xbf21  conv.i8
0xbf22  stloc.s  4
0xbf24  ldloca.s 3
0xbf26  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::GetValueOrDefault()
0xbf2b  ldloc.s  4
0xbf2d  bge.s    loc_BF32
0xbf2f  ldc.i4.0
0xbf30  br.s     loc_BF39
0xbf32  ldloca.s 3
0xbf34  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0xbf39  brfalse.s loc_BF41
0xbf3b  ldc.i4   0x7FFFFFFF
0xbf40  ret
0xbf41  ldloc.2
0xbf42  box      valuetype [mscorlib]System.Nullable`1<int64>
0xbf47  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbf4c  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0xbf51  ret
0xbf52  ldstr    aUnsupportedObj// "Unsupported object type returned from q"...
0xbf57  ldloc.0
0xbf58  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xbf5d  call     string [mscorlib]System.String::Concat(object, object)
0xbf62  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0xbf67  throw
```
