# Microsoft.Crm.Sdk.ServiceDescription::LoadType

- ea: `0x8810`
- end: `0x8849`
- name: `Microsoft.Crm.Sdk.ServiceDescription::LoadType`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8b80`

## callees

- `0x8810`

## pseudocode

```c

```

## disassembly

```asm
0x8810  ldarg.0
0x8811  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string)
0x8816  stloc.0
0x8817  ldloc.0
0x8818  ldc.i4.0
0x8819  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string, bool)
0x881e  stloc.1
0x881f  ldloc.1
0x8820  ldnull
0x8821  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x8826  brfalse.s loc_8847
0x8828  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x882d  ldstr    aCannotLoadType// "Cannot load type '{0}'."
0x8832  ldc.i4.1
0x8833  newarr   [mscorlib]System.Object
0x8838  dup
0x8839  ldc.i4.0
0x883a  ldloc.0
0x883b  stelem.ref
0x883c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8841  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x8846  throw
0x8847  ldloc.1
0x8848  ret
```
