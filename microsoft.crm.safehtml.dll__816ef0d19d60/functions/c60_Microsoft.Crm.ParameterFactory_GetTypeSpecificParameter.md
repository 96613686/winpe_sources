# Microsoft.Crm.ParameterFactory::GetTypeSpecificParameter

- ea: `0xc60`
- end: `0xe36`
- name: `Microsoft.Crm.ParameterFactory::GetTypeSpecificParameter`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x6a0`

## callees

- `0x930`
- `0x940`
- `0x950`
- `0x960`
- `0xc60`
- `0x1570`
- `0x15d0`
- `0x1640`
- `0x1680`
- `0x1770`
- `0x17f0`
- `0x1820`
- `0x1850`
- `0x1890`
- `0x18d0`
- `0x1920`
- `0x1950`
- `0x1980`

## pseudocode

```c

```

## disassembly

```asm
0xc60  ldarg.0
0xc61  callvirt instance bool Microsoft.Crm.IWebParameter::get_IsPassThrough()
0xc66  brfalse.s loc_C6A
0xc68  ldarg.0
0xc69  ret
0xc6a  ldarg.0
0xc6b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc70  stloc.0
0xc71  ldloc.0
0xc72  ldtoken  Microsoft.Crm.FormParameterAttribute
0xc77  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc7c  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xc81  brfalse.s loc_CA9
0xc83  ldloc.0
0xc84  ldtoken  Microsoft.Crm.QueryStringParameterAttribute
0xc89  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc8e  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xc93  brfalse.s loc_CA9
0xc95  ldloc.0
0xc96  ldtoken  Microsoft.Crm.FormStreamParameterAttribute
0xc9b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xca0  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xca5  brfalse.s loc_CA9
0xca7  ldarg.0
0xca8  ret
0xca9  ldarg.0
0xcaa  callvirt instance valuetype Microsoft.Crm.ParameterType Microsoft.Crm.IWebParameter::get_ParameterType()
0xcaf  stloc.1
0xcb0  ldloc.1
0xcb1  switch   loc_CF7, loc_D09, loc_D1B, loc_D2D, loc_D3F, loc_D3F, loc_D68, loc_D7A, loc_D8C, loc_D98, loc_DAA, loc_DBC, loc_DCE, loc_DE0, loc_DF2
0xcf2  br       loc_E04
0xcf7  ldarg.0
0xcf8  callvirt instance string Microsoft.Crm.IWebParameter::get_Name()
0xcfd  ldarg.0
0xcfe  callvirt instance valuetype Microsoft.Crm.ParameterSources Microsoft.Crm.IWebParameter::get_Sources()
0xd03  newobj   instance void Microsoft.Crm.Base64ParameterAttribute::.ctor(string name, valuetype Microsoft.Crm.ParameterSources sources)
0xd08  ret
0xd09  ldarg.0
0xd0a  callvirt instance string Microsoft.Crm.IWebParameter::get_Name()
0xd0f  ldarg.0
0xd10  callvirt instance valuetype Microsoft.Crm.ParameterSources Microsoft.Crm.IWebParameter::get_Sources()
0xd15  newobj   instance void Microsoft.Crm.BooleanParameterAttribute::.ctor(string name, valuetype Microsoft.Crm.ParameterSources sources)
0xd1a  ret
0xd1b  ldarg.0
0xd1c  callvirt instance string Microsoft.Crm.IWebParameter::get_Name()
0xd21  ldarg.0
0xd22  callvirt instance valuetype Microsoft.Crm.ParameterSources Microsoft.Crm.IWebParameter::get_Sources()
0xd27  newobj   instance void Microsoft.Crm.DateTimeParameterAttribute::.ctor(string name, valuetype Microsoft.Crm.ParameterSources sources)
0xd2c  ret
0xd2d  ldarg.0
0xd2e  callvirt instance string Microsoft.Crm.IWebParameter::get_Name()
0xd33  ldarg.0
0xd34  callvirt instance valuetype Microsoft.Crm.ParameterSources Microsoft.Crm.IWebParameter::get_Sources()
0xd39  newobj   instance void Microsoft.Crm.DoubleParameterAttribute::.ctor(string name, valuetype Microsoft.Crm.ParameterSources sources)
0xd3e  ret
0xd3f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd44  ldstr    aParameterType0// "Parameter type '{0}' cannot be used wit"...
0xd49  ldc.i4.1
0xd4a  newarr   [mscorlib]System.Object
0xd4f  dup
0xd50  ldc.i4.0
0xd51  ldarg.0
0xd52  callvirt instance valuetype Microsoft.Crm.ParameterType Microsoft.Crm.IWebParameter::get_ParameterType()
0xd57  box      Microsoft.Crm.ParameterType
0xd5c  stelem.ref
0xd5d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd62  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xd67  throw
0xd68  ldarg.0
0xd69  callvirt instance string Microsoft.Crm.IWebParameter::get_Name()
0xd6e  ldarg.0
0xd6f  callvirt instance valuetype Microsoft.Crm.ParameterSources Microsoft.Crm.IWebParameter::get_Sources()
0xd74  newobj   instance void Microsoft.Crm.IntegerParameterAttribute::.ctor(string name, valuetype Microsoft.Crm.ParameterSources sources)
0xd79  ret
0xd7a  ldarg.0
0xd7b  callvirt instance string Microsoft.Crm.IWebParameter::get_Name()
0xd80  ldarg.0
0xd81  callvirt instance valuetype Microsoft.Crm.ParameterSources Microsoft.Crm.IWebParameter::get_Sources()
0xd86  newobj   instance void Microsoft.Crm.LongParameterAttribute::.ctor(string name, valuetype Microsoft.Crm.ParameterSources sources)
0xd8b  ret
0xd8c  ldarg.0
0xd8d  callvirt instance valuetype Microsoft.Crm.ParameterSources Microsoft.Crm.IWebParameter::get_Sources()
0xd92  newobj   instance void Microsoft.Crm.NoParametersAttribute::.ctor(valuetype Microsoft.Crm.ParameterSources sources)
0xd97  ret
0xd98  ldarg.0
0xd99  callvirt instance string Microsoft.Crm.IWebParameter::get_Name()
0xd9e  ldarg.0
0xd9f  callvirt instance valuetype Microsoft.Crm.ParameterSources Microsoft.Crm.IWebParameter::get_Sources()
0xda4  newobj   instance void Microsoft.Crm.PositiveIntegerParameterAttribute::.ctor(string name, valuetype Microsoft.Crm.ParameterSources sources)
0xda9  ret
0xdaa  ldarg.0
0xdab  callvirt instance string Microsoft.Crm.IWebParameter::get_Name()
0xdb0  ldarg.0
0xdb1  callvirt instance valuetype Microsoft.Crm.ParameterSources Microsoft.Crm.IWebParameter::get_Sources()
0xdb6  newobj   instance void Microsoft.Crm.SafeStringParameterAttribute::.ctor(string name, valuetype Microsoft.Crm.ParameterSources sources)
0xdbb  ret
0xdbc  ldarg.0
0xdbd  callvirt instance string Microsoft.Crm.IWebParameter::get_Name()
0xdc2  ldarg.0
0xdc3  callvirt instance valuetype Microsoft.Crm.ParameterSources Microsoft.Crm.IWebParameter::get_Sources()
0xdc8  newobj   instance void Microsoft.Crm.UniqueIdParameterAttribute::.ctor(string name, valuetype Microsoft.Crm.ParameterSources sources)
0xdcd  ret
0xdce  ldarg.0
0xdcf  callvirt instance string Microsoft.Crm.IWebParameter::get_Name()
0xdd4  ldarg.0
0xdd5  callvirt instance valuetype Microsoft.Crm.ParameterSources Microsoft.Crm.IWebParameter::get_Sources()
0xdda  newobj   instance void Microsoft.Crm.UnsafeStringParameterAttribute::.ctor(string name, valuetype Microsoft.Crm.ParameterSources sources)
0xddf  ret
0xde0  ldarg.0
0xde1  callvirt instance string Microsoft.Crm.IWebParameter::get_Name()
0xde6  ldarg.0
0xde7  callvirt instance valuetype Microsoft.Crm.ParameterSources Microsoft.Crm.IWebParameter::get_Sources()
0xdec  newobj   instance void Microsoft.Crm.UnsignedIntParameterAttribute::.ctor(string name, valuetype Microsoft.Crm.ParameterSources sources)
0xdf1  ret
0xdf2  ldarg.0
0xdf3  callvirt instance string Microsoft.Crm.IWebParameter::get_Name()
0xdf8  ldarg.0
0xdf9  callvirt instance valuetype Microsoft.Crm.ParameterSources Microsoft.Crm.IWebParameter::get_Sources()
0xdfe  newobj   instance void Microsoft.Crm.XmlStringParameterAttribute::.ctor(string name, valuetype Microsoft.Crm.ParameterSources sources)
0xe03  ret
0xe04  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe09  ldstr    aParameter0HasI// "Parameter {0} has invalid type {1}"
0xe0e  ldc.i4.2
0xe0f  newarr   [mscorlib]System.Object
0xe14  dup
0xe15  ldc.i4.0
0xe16  ldarg.0
0xe17  callvirt instance string Microsoft.Crm.IWebParameter::get_Name()
0xe1c  stelem.ref
0xe1d  dup
0xe1e  ldc.i4.1
0xe1f  ldarg.0
0xe20  callvirt instance valuetype Microsoft.Crm.ParameterType Microsoft.Crm.IWebParameter::get_ParameterType()
0xe25  box      Microsoft.Crm.ParameterType
0xe2a  stelem.ref
0xe2b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe30  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xe35  throw
```
