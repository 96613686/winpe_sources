# Microsoft.Crm.Sdk.ServiceDescription::LoadConversionDescription

- ea: `0x92b0`
- end: `0x9395`
- name: `Microsoft.Crm.Sdk.ServiceDescription::LoadConversionDescription`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x91c0`

## callees

- `0x92b0`

## pseudocode

```c

```

## disassembly

```asm
0x92b0  ldarg.1
0x92b1  ldstr    aText// "text"
0x92b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x92bb  ldarg.1
0x92bc  ldc.i4.s 0x28
0x92be  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x92c3  stloc.0
0x92c4  ldloc.0
0x92c5  ldc.i4.m1
0x92c6  bne.un.s loc_92FD
0x92c8  ldarg.1
0x92c9  ldc.i4.s 0x3A
0x92cb  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x92d0  ldc.i4.m1
0x92d1  bne.un.s loc_92E8
0x92d3  ldc.i4.1
0x92d4  newarr   [mscorlib]System.String
0x92d9  dup
0x92da  ldc.i4.0
0x92db  ldarg.1
0x92dc  stelem.ref
0x92dd  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.SingleFieldConverter::.ctor()
0x92e2  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionDescription::.ctor(string[], class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.IConverter)
0x92e7  ret
0x92e8  ldc.i4.1
0x92e9  newarr   [mscorlib]System.String
0x92ee  dup
0x92ef  ldc.i4.0
0x92f0  ldarg.1
0x92f1  stelem.ref
0x92f2  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConstantConverter::.ctor()
0x92f7  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionDescription::.ctor(string[], class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.IConverter)
0x92fc  ret
0x92fd  ldarg.1
0x92fe  ldarg.1
0x92ff  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9304  ldc.i4.1
0x9305  sub
0x9306  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x930b  ldc.i4.s 0x29
0x930d  beq.s    loc_932E
0x930f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9314  ldstr    aInvalidConvert// "Invalid converter call syntax: '{0}'"
0x9319  ldc.i4.1
0x931a  newarr   [mscorlib]System.Object
0x931f  dup
0x9320  ldc.i4.0
0x9321  ldarg.1
0x9322  stelem.ref
0x9323  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9328  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x932d  throw
0x932e  ldarg.1
0x932f  ldc.i4.0
0x9330  ldloc.0
0x9331  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x9336  stloc.1
0x9337  ldarg.2
0x9338  ldloc.1
0x9339  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.IConverter>::get_Item(void)
0x933e  stloc.2
0x933f  ldloc.2
0x9340  brtrue.s loc_9353
0x9342  ldstr    aUnknownConvert// "Unknown converter: "
0x9347  ldloc.1
0x9348  call     string [mscorlib]System.String::Concat(string, string)
0x934d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x9352  throw
0x9353  ldarg.1
0x9354  ldloc.0
0x9355  ldc.i4.1
0x9356  add
0x9357  ldarg.1
0x9358  callvirt instance int32 [mscorlib]System.String::get_Length()
0x935d  ldloc.0
0x935e  sub
0x935f  ldc.i4.2
0x9360  sub
0x9361  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x9366  stloc.3
0x9367  ldloc.3
0x9368  callvirt instance int32 [mscorlib]System.String::get_Length()
0x936d  brtrue.s loc_9379
0x936f  ldc.i4.0
0x9370  newarr   [mscorlib]System.String
0x9375  stloc.s  4
0x9377  br.s     loc_938C
0x9379  ldloc.3
0x937a  ldc.i4.1
0x937b  newarr   [mscorlib]System.Char
0x9380  dup
0x9381  ldc.i4.0
0x9382  ldc.i4.s 0x2C
0x9384  stelem.i2
0x9385  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x938a  stloc.s  4
0x938c  ldloc.s  4
0x938e  ldloc.2
0x938f  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionDescription::.ctor(string[], class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.IConverter)
0x9394  ret
```
