# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::CheckEntitySubclass

- ea: `0x14d50`
- end: `0x14dc1`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::CheckEntitySubclass`
- size: `113`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x13280`
- `0x13300`

## callees

- `0x4e40`
- `0x4e80`
- `0x14d50`

## pseudocode

```c

```

## disassembly

```asm
0x14d50  ldarg.0
0x14d51  ldtoken  Microsoft.Xrm.Sdk.Entity
0x14d56  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14d5b  callvirt instance bool [mscorlib]System.Type::IsSubclassOf(class [mscorlib]System.Type)
0x14d60  brtrue.s loc_14D8E
0x14d62  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14d67  ldstr    aTheSpecifiedTy// "The specified type '{0}' must be a subc"...
0x14d6c  ldc.i4.2
0x14d6d  newarr   [mscorlib]System.Object
0x14d72  dup
0x14d73  ldc.i4.0
0x14d74  ldarg.0
0x14d75  stelem.ref
0x14d76  dup
0x14d77  ldc.i4.1
0x14d78  ldtoken  Microsoft.Xrm.Sdk.Entity
0x14d7d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14d82  stelem.ref
0x14d83  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14d88  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x14d8d  throw
0x14d8e  ldc.i4.1
0x14d8f  call     class Microsoft.Xrm.Sdk.KnownProxyTypesProvider Microsoft.Xrm.Sdk.KnownProxyTypesProvider::GetInstance(bool supportIndividualAssemblies)
0x14d94  ldarg.0
0x14d95  callvirt instance string Microsoft.Xrm.Sdk.KnownProxyTypesProvider::GetNameForType(class [mscorlib]System.Type type)
0x14d9a  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x14d9f  brfalse.s loc_14DC0
0x14da1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14da6  ldstr    aTheSpecifiedTy_0// "The specified type '{0}' is not a known"...
0x14dab  ldc.i4.1
0x14dac  newarr   [mscorlib]System.Object
0x14db1  dup
0x14db2  ldc.i4.0
0x14db3  ldarg.0
0x14db4  stelem.ref
0x14db5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14dba  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x14dbf  throw
0x14dc0  ret
```
