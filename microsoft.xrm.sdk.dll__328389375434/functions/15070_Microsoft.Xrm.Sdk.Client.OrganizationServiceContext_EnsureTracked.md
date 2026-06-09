# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::EnsureTracked

- ea: `0x15070`
- end: `0x150b0`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::EnsureTracked`
- size: `64`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x134b0`
- `0x13d50`
- `0x13dd0`
- `0x13fd0`
- `0x150b0`

## callees

- `0x3b90`
- `0x15070`

## pseudocode

```c

```

## disassembly

```asm
0x15070  ldarg.1
0x15071  brtrue.s loc_1507A
0x15073  ldarg.2
0x15074  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x15079  throw
0x1507a  ldarg.0
0x1507b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_descriptors
0x15080  ldarg.1
0x15081  ldloca.s 0
0x15083  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor>::TryGetValue(var<u1>, !!T0)
0x15088  brtrue.s loc_150AE
0x1508a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1508f  ldstr    aTheContextIsNo// "The context is not currently tracking t"...
0x15094  ldc.i4.1
0x15095  newarr   [mscorlib]System.Object
0x1509a  dup
0x1509b  ldc.i4.0
0x1509c  ldarg.1
0x1509d  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x150a2  stelem.ref
0x150a3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x150a8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x150ad  throw
0x150ae  ldloc.0
0x150af  ret
```
