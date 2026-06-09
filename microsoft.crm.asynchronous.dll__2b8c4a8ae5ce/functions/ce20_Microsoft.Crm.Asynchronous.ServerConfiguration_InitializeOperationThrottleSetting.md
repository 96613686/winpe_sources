# Microsoft.Crm.Asynchronous.ServerConfiguration::InitializeOperationThrottleSetting

- ea: `0xce20`
- end: `0xd025`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::InitializeOperationThrottleSetting`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xbda0`

## callees

- `0xc960`
- `0xce20`

## string_xrefs

- `0xce25`: `AsyncThrottlingConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0xce20  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xce25  ldstr    aAsyncthrottlin// "AsyncThrottlingConfiguration"
0xce2a  call     object Microsoft.Crm.Asynchronous.ServerConfiguration::ReadServerSetting(class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService locatorService, string settingName)
0xce2f  isinst   [mscorlib]System.String
0xce34  stloc.0
0xce35  ldloc.0
0xce36  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xce3b  brtrue   loc_CF72
0xce40  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xce45  stloc.1
0xce46  ldloc.0
0xce47  ldc.i4.1
0xce48  newarr   [mscorlib]System.Char
0xce4d  dup
0xce4e  ldc.i4.0
0xce4f  ldc.i4.s 0x3B
0xce51  stelem.i2
0xce52  ldc.i4.1
0xce53  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0xce58  stloc.2
0xce59  ldloc.2
0xce5a  brfalse  loc_CF44
0xce5f  ldloc.2
0xce60  ldlen
0xce61  brfalse  loc_CF44
0xce66  ldtoken  [Microsoft.Crm.Constants]Microsoft.Crm.AsyncOperationType
0xce6b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xce70  stloc.3
0xce71  ldloc.2
0xce72  stloc.s  4
0xce74  ldc.i4.0
0xce75  stloc.s  5
0xce77  br       loc_CF39
0xce7c  ldloc.s  4
0xce7e  ldloc.s  5
0xce80  ldelem.ref
0xce81  ldc.i4.1
0xce82  newarr   [mscorlib]System.Char
0xce87  dup
0xce88  ldc.i4.0
0xce89  ldc.i4.s 0x3D
0xce8b  stelem.i2
0xce8c  ldc.i4.1
0xce8d  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0xce92  stloc.s  6
0xce94  ldloc.s  6
0xce96  brfalse  loc_CF33
0xce9b  ldloc.s  6
0xce9d  ldlen
0xce9e  conv.i4
0xce9f  ldc.i4.2
0xcea0  bne.un   loc_CF33
0xcea5  ldloc.3
0xcea6  ldloc.s  6
0xcea8  ldc.i4.0
0xcea9  ldelem.ref
0xceaa  callvirt instance class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Type::GetField(string)
0xceaf  stloc.s  7
0xceb1  ldloc.s  7
0xceb3  ldnull
0xceb4  call     bool [mscorlib]System.Reflection.FieldInfo::op_Inequality(class [mscorlib]System.Reflection.FieldInfo, class [mscorlib]System.Reflection.FieldInfo)
0xceb9  brfalse.s loc_CF33
0xcebb  ldc.i4.0
0xcebc  stloc.s  8
0xcebe  ldloc.s  6
0xcec0  ldc.i4.1
0xcec1  ldelem.ref
0xcec2  ldloca.s 8
0xcec4  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0xcec9  brfalse.s loc_CF33
0xcecb  ldloc.s  8
0xcecd  ldc.i4.0
0xcece  blt.s    loc_CF33
0xced0  ldloc.s  7
0xced2  callvirt instance object [mscorlib]System.Reflection.FieldInfo::GetRawConstantValue()
0xced7  unbox.any [mscorlib]System.Int32
0xcedc  stloc.s  9
0xcede  ldarg.0
0xcedf  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Threading.SemaphoreSlim> Microsoft.Crm.Asynchronous.ServerConfiguration::_operationTypeThrottle
0xcee4  ldloc.s  9
0xcee6  ldloc.s  8
0xcee8  newobj   instance void [mscorlib]System.Threading.SemaphoreSlim::.ctor(int32)
0xceed  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Threading.SemaphoreSlim>::set_Item(var<u1>, !!T0)
0xcef2  ldarg.0
0xcef3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Asynchronous.ServerConfiguration::_maxOperationTypeThrottle
0xcef8  ldloc.s  9
0xcefa  ldloc.s  8
0xcefc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::set_Item(var<u1>, !!T0)
0xcf01  ldloc.1
0xcf02  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcf07  ldstr    a012// "{0}({1})={2};"
0xcf0c  ldc.i4.3
0xcf0d  newarr   [mscorlib]System.Object
0xcf12  dup
0xcf13  ldc.i4.0
0xcf14  ldloc.s  6
0xcf16  ldc.i4.0
0xcf17  ldelem.ref
0xcf18  stelem.ref
0xcf19  dup
0xcf1a  ldc.i4.1
0xcf1b  ldloc.s  9
0xcf1d  box      [mscorlib]System.Int32
0xcf22  stelem.ref
0xcf23  dup
0xcf24  ldc.i4.2
0xcf25  ldloc.s  8
0xcf27  box      [mscorlib]System.Int32
0xcf2c  stelem.ref
0xcf2d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xcf32  pop
0xcf33  ldloc.s  5
0xcf35  ldc.i4.1
0xcf36  add
0xcf37  stloc.s  5
0xcf39  ldloc.s  5
0xcf3b  ldloc.s  4
0xcf3d  ldlen
0xcf3e  conv.i4
0xcf3f  blt      loc_CE7C
0xcf44  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xcf49  ldc.i4.s 0x15
0xcf4b  ldstr    aOperationThrot// "Operation throttling{0}Setting: {1}.{0}"...
0xcf50  ldc.i4.3
0xcf51  newarr   [mscorlib]System.Object
0xcf56  dup
0xcf57  ldc.i4.0
0xcf58  call     string [mscorlib]System.Environment::get_NewLine()
0xcf5d  stelem.ref
0xcf5e  dup
0xcf5f  ldc.i4.1
0xcf60  ldloc.0
0xcf61  stelem.ref
0xcf62  dup
0xcf63  ldc.i4.2
0xcf64  ldloc.1
0xcf65  callvirt instance string [mscorlib]System.Object::ToString()
0xcf6a  stelem.ref
0xcf6b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcf70  br.s     loc_CF91
0xcf72  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xcf77  ldc.i4.s 0x15
0xcf79  ldstr    a0_0// "{0}"
0xcf7e  ldc.i4.1
0xcf7f  newarr   [mscorlib]System.Object
0xcf84  dup
0xcf85  ldc.i4.0
0xcf86  ldstr    aOperationThrot_0// "Operation throttling is disabled."
0xcf8b  stelem.ref
0xcf8c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcf91  ldarg.0
0xcf92  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Threading.SemaphoreSlim> Microsoft.Crm.Asynchronous.ServerConfiguration::_operationTypeThrottle
0xcf97  ldc.i4.s 0x44
0xcf99  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Threading.SemaphoreSlim>::ContainsKey(var<u1>)
0xcf9e  brtrue.s loc_CFC2
0xcfa0  ldarg.0
0xcfa1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Threading.SemaphoreSlim> Microsoft.Crm.Asynchronous.ServerConfiguration::_operationTypeThrottle
0xcfa6  ldc.i4.s 0x44
0xcfa8  ldc.i4.2
0xcfa9  ldc.i4.2
0xcfaa  newobj   instance void [mscorlib]System.Threading.SemaphoreSlim::.ctor(int32, int32)
0xcfaf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Threading.SemaphoreSlim>::set_Item(var<u1>, !!T0)
0xcfb4  ldarg.0
0xcfb5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Asynchronous.ServerConfiguration::_maxOperationTypeThrottle
0xcfba  ldc.i4.s 0x44
0xcfbc  ldc.i4.2
0xcfbd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::set_Item(var<u1>, !!T0)
0xcfc2  ldarg.0
0xcfc3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Threading.SemaphoreSlim> Microsoft.Crm.Asynchronous.ServerConfiguration::_operationTypeThrottle
0xcfc8  ldc.i4.s 0x45
0xcfca  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Threading.SemaphoreSlim>::ContainsKey(var<u1>)
0xcfcf  brtrue.s loc_CFF3
0xcfd1  ldarg.0
0xcfd2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Threading.SemaphoreSlim> Microsoft.Crm.Asynchronous.ServerConfiguration::_operationTypeThrottle
0xcfd7  ldc.i4.s 0x45
0xcfd9  ldc.i4.2
0xcfda  ldc.i4.2
0xcfdb  newobj   instance void [mscorlib]System.Threading.SemaphoreSlim::.ctor(int32, int32)
0xcfe0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Threading.SemaphoreSlim>::set_Item(var<u1>, !!T0)
0xcfe5  ldarg.0
0xcfe6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Asynchronous.ServerConfiguration::_maxOperationTypeThrottle
0xcfeb  ldc.i4.s 0x45
0xcfed  ldc.i4.2
0xcfee  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::set_Item(var<u1>, !!T0)
0xcff3  ldarg.0
0xcff4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Threading.SemaphoreSlim> Microsoft.Crm.Asynchronous.ServerConfiguration::_operationTypeThrottle
0xcff9  ldc.i4.s 0x48
0xcffb  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Threading.SemaphoreSlim>::ContainsKey(var<u1>)
0xd000  brtrue.s loc_D024
0xd002  ldarg.0
0xd003  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Threading.SemaphoreSlim> Microsoft.Crm.Asynchronous.ServerConfiguration::_operationTypeThrottle
0xd008  ldc.i4.s 0x48
0xd00a  ldc.i4.5
0xd00b  ldc.i4.5
0xd00c  newobj   instance void [mscorlib]System.Threading.SemaphoreSlim::.ctor(int32, int32)
0xd011  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Threading.SemaphoreSlim>::set_Item(var<u1>, !!T0)
0xd016  ldarg.0
0xd017  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Asynchronous.ServerConfiguration::_maxOperationTypeThrottle
0xd01c  ldc.i4.s 0x48
0xd01e  ldc.i4.5
0xd01f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::set_Item(var<u1>, !!T0)
0xd024  ret
```
