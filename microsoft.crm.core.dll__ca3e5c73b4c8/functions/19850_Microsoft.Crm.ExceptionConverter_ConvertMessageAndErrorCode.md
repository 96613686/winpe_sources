# Microsoft.Crm.ExceptionConverter::ConvertMessageAndErrorCode

- ea: `0x19850`
- end: `0x19b7b`
- name: `Microsoft.Crm.ExceptionConverter::ConvertMessageAndErrorCode`
- size: `811`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x19510`

## callees

- `0x18910`
- `0x18930`
- `0x19850`
- `0x19b80`
- `0x19c20`
- `0x19df0`
- `0x1be80`
- `0x1f4b0`
- `0x66c00`
- `0x66c20`

## string_xrefs

- `0x1989f`: `ExceptionFromPluginConstructor`
- `0x198df`: `ExceptionFromPluginConstructor`
- `0x198fb`: `ExceptionFromPluginConstructor`
- `0x1990b`: `ExceptionFromPluginExecute`
- `0x19940`: `ExceptionFromPluginExecute`
- `0x1995c`: `ExceptionFromPluginExecute`
- `0x198c3`: `found ExceptionFromPluginConstructor. Exception Message: `
- `0x1992f`: `found ExceptionFromPluginExecute`

## pseudocode

```c

```

## disassembly

```asm
0x19850  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x19855  ldarg.0
0x19856  call     instance valuetype Microsoft.Crm.TraceCategory Microsoft.Crm.ExceptionConverter::get_TraceCategory()
0x1985b  ldstr    a0// "{0}"
0x19860  ldc.i4.1
0x19861  newarr   [mscorlib]System.Object
0x19866  dup
0x19867  ldc.i4.0
0x19868  ldstr    aEnterConvertme// "enter: ConvertMessageAndErrorCode: "
0x1986d  ldarg.1
0x1986e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x19873  call     string [mscorlib]System.String::Concat(object, object)
0x19878  stelem.ref
0x19879  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x1987e  ldarg.1
0x1987f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x19884  stloc.0
0x19885  ldc.i4.0
0x19886  stloc.1
0x19887  ldc.i4.0
0x19888  stloc.2
0x19889  ldarg.1
0x1988a  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException
0x1988f  ldnull
0x19890  cgt.un
0x19892  stloc.3
0x19893  ldloc.3
0x19894  brtrue   loc_19966
0x19899  ldarg.1
0x1989a  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x1989f  ldstr    aExceptionfromp// "ExceptionFromPluginConstructor"
0x198a4  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x198a9  brfalse.s loc_19905
0x198ab  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x198b0  ldarg.0
0x198b1  call     instance valuetype Microsoft.Crm.TraceCategory Microsoft.Crm.ExceptionConverter::get_TraceCategory()
0x198b6  ldstr    a0// "{0}"
0x198bb  ldc.i4.1
0x198bc  newarr   [mscorlib]System.Object
0x198c1  dup
0x198c2  ldc.i4.0
0x198c3  ldstr    aFoundException// "found ExceptionFromPluginConstructor. E"...
0x198c8  ldarg.1
0x198c9  callvirt instance string [mscorlib]System.Exception::get_Message()
0x198ce  call     string [mscorlib]System.String::Concat(string, string)
0x198d3  stelem.ref
0x198d4  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x198d9  ldarg.1
0x198da  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x198df  ldstr    aExceptionfromp// "ExceptionFromPluginConstructor"
0x198e4  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x198e9  isinst   [mscorlib]System.String
0x198ee  stsfld   string Microsoft.Crm.ExceptionConverter::_pluginTypeName
0x198f3  ldc.i4.1
0x198f4  stloc.1
0x198f5  ldarg.1
0x198f6  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x198fb  ldstr    aExceptionfromp// "ExceptionFromPluginConstructor"
0x19900  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0x19905  ldarg.1
0x19906  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x1990b  ldstr    aExceptionfromp_0// "ExceptionFromPluginExecute"
0x19910  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x19915  brfalse.s loc_19966
0x19917  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1991c  ldarg.0
0x1991d  call     instance valuetype Microsoft.Crm.TraceCategory Microsoft.Crm.ExceptionConverter::get_TraceCategory()
0x19922  ldstr    a0// "{0}"
0x19927  ldc.i4.1
0x19928  newarr   [mscorlib]System.Object
0x1992d  dup
0x1992e  ldc.i4.0
0x1992f  ldstr    aFoundException_0// "found ExceptionFromPluginExecute"
0x19934  stelem.ref
0x19935  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x1993a  ldarg.1
0x1993b  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x19940  ldstr    aExceptionfromp_0// "ExceptionFromPluginExecute"
0x19945  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x1994a  isinst   [mscorlib]System.String
0x1994f  stsfld   string Microsoft.Crm.ExceptionConverter::_pluginTypeName
0x19954  ldc.i4.1
0x19955  stloc.2
0x19956  ldarg.1
0x19957  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x1995c  ldstr    aExceptionfromp_0// "ExceptionFromPluginExecute"
0x19961  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0x19966  ldarg.2
0x19967  ldc.i4   0x80040216
0x1996c  stind.i4
0x1996d  ldarg.0
0x1996e  call     instance bool Microsoft.Crm.ExceptionConverter::get_IsExceptionShieldingEnabled()
0x19973  stloc.s  4
0x19975  ldc.i4.0
0x19976  stloc.s  5
0x19978  ldarg.1
0x19979  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x1997e  stloc.s  6
0x19980  ldsfld   string Microsoft.Crm.ExceptionConverter::_pluginTypeName
0x19985  brfalse.s loc_19996
0x19987  ldarg.2
0x19988  ldc.i4   0x80040224
0x1998d  stind.i4
0x1998e  ldc.i4.0
0x1998f  stloc.s  4
0x19991  br       loc_19A1A
0x19996  ldarg.0
0x19997  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class ExceptionConversionParameters> Microsoft.Crm.ExceptionConverter::_exceptionConversionDictionary
0x1999c  ldloc.s  6
0x1999e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class ExceptionConversionParameters>::ContainsKey(var<u1>)
0x199a3  brfalse.s loc_19A1A
0x199a5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x199aa  ldarg.0
0x199ab  call     instance valuetype Microsoft.Crm.TraceCategory Microsoft.Crm.ExceptionConverter::get_TraceCategory()
0x199b0  ldstr    a0// "{0}"
0x199b5  ldc.i4.1
0x199b6  newarr   [mscorlib]System.Object
0x199bb  dup
0x199bc  ldc.i4.0
0x199bd  ldstr    aFoundException_1// "found exception conversion parameters"
0x199c2  stelem.ref
0x199c3  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x199c8  ldarg.0
0x199c9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class ExceptionConversionParameters> Microsoft.Crm.ExceptionConverter::_exceptionConversionDictionary
0x199ce  ldloc.s  6
0x199d0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class ExceptionConversionParameters>::get_Item(void)
0x199d5  stloc.s  8
0x199d7  ldarg.2
0x199d8  ldloc.s  8
0x199da  callvirt instance int32 ExceptionConversionParameters::get_ErrorCode()
0x199df  stind.i4
0x199e0  ldloc.s  8
0x199e2  callvirt instance bool ExceptionConversionParameters::get_UseMessageFromErrorCode()
0x199e7  brfalse.s loc_19A04
0x199e9  ldarg.2
0x199ea  ldind.i4
0x199eb  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x199f0  stloc.0
0x199f1  ldloc.0
0x199f2  ldstr    aMessage// "message"
0x199f7  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x199fc  ldc.i4.1
0x199fd  stloc.s  4
0x199ff  ldc.i4.1
0x19a00  stloc.s  5
0x19a02  br.s     loc_19A1A
0x19a04  ldc.i4.0
0x19a05  stloc.s  4
0x19a07  ldloc.s  6
0x19a09  ldstr    asc_7CC52// ": "
0x19a0e  ldarg.1
0x19a0f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x19a14  call     string [mscorlib]System.String::Concat(object, object, object)
0x19a19  stloc.0
0x19a1a  ldsfld   string Microsoft.Crm.ExceptionConverter::_pluginTypeName
0x19a1f  brfalse.s loc_19A70
0x19a21  ldc.i4.0
0x19a22  stloc.s  4
0x19a24  ldloc.1
0x19a25  brfalse.s loc_19A2F
0x19a27  ldstr    aUnexpectedExce_0// "Unexpected exception from plug-in (Cons"...
0x19a2c  stloc.0
0x19a2d  br.s     loc_19A38
0x19a2f  ldloc.2
0x19a30  brfalse.s loc_19A38
0x19a32  ldstr    aUnexpectedExce_1// "Unexpected exception from plug-in (Exec"...
0x19a37  stloc.0
0x19a38  ldc.i4.6
0x19a39  newarr   [mscorlib]System.Object
0x19a3e  dup
0x19a3f  ldc.i4.0
0x19a40  ldloc.0
0x19a41  stelem.ref
0x19a42  dup
0x19a43  ldc.i4.1
0x19a44  ldsfld   string Microsoft.Crm.ExceptionConverter::_pluginTypeName
0x19a49  stelem.ref
0x19a4a  dup
0x19a4b  ldc.i4.2
0x19a4c  ldstr    asc_7CC52// ": "
0x19a51  stelem.ref
0x19a52  dup
0x19a53  ldc.i4.3
0x19a54  ldloc.s  6
0x19a56  stelem.ref
0x19a57  dup
0x19a58  ldc.i4.4
0x19a59  ldstr    asc_7CC52// ": "
0x19a5e  stelem.ref
0x19a5f  dup
0x19a60  ldc.i4.5
0x19a61  ldarg.1
0x19a62  callvirt instance string [mscorlib]System.Exception::get_Message()
0x19a67  stelem.ref
0x19a68  call     string [mscorlib]System.String::Concat(object[])
0x19a6d  stloc.0
0x19a6e  br.s     loc_19A7D
0x19a70  ldloc.3
0x19a71  brfalse.s loc_19A7D
0x19a73  ldarg.1
0x19a74  callvirt instance string [mscorlib]System.Exception::get_Message()
0x19a79  stloc.0
0x19a7a  ldc.i4.0
0x19a7b  stloc.s  4
0x19a7d  ldarg.1
0x19a7e  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.SdkExceptionBase
0x19a83  ldnull
0x19a84  cgt.un
0x19a86  brfalse.s loc_19AED
0x19a88  ldnull
0x19a89  stloc.s  9
0x19a8b  ldarg.0
0x19a8c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class ExceptionConversionParameters> Microsoft.Crm.ExceptionConverter::_exceptionConversionDictionary
0x19a91  ldloc.s  6
0x19a93  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class ExceptionConversionParameters>::ContainsKey(var<u1>)
0x19a98  brfalse.s loc_19AAB
0x19a9a  ldarg.0
0x19a9b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class ExceptionConversionParameters> Microsoft.Crm.ExceptionConverter::_exceptionConversionDictionary
0x19aa0  ldloc.s  6
0x19aa2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class ExceptionConversionParameters>::get_Item(void)
0x19aa7  stloc.s  9
0x19aa9  br.s     loc_19ABF
0x19aab  ldarg.0
0x19aac  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class ExceptionConversionParameters> Microsoft.Crm.ExceptionConverter::_exceptionConversionDictionary
0x19ab1  ldloc.s  6
0x19ab3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::get_BaseType()
0x19ab8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class ExceptionConversionParameters>::get_Item(void)
0x19abd  stloc.s  9
0x19abf  ldarg.1
0x19ac0  callvirt instance string [mscorlib]System.Exception::get_Message()
0x19ac5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19aca  brtrue.s loc_19AD4
0x19acc  ldarg.1
0x19acd  callvirt instance string [mscorlib]System.Exception::get_Message()
0x19ad2  br.s     loc_19AE0
0x19ad4  ldloc.s  9
0x19ad6  callvirt instance int32 ExceptionConversionParameters::get_ErrorCode()
0x19adb  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x19ae0  stloc.0
0x19ae1  ldc.i4.0
0x19ae2  stloc.s  4
0x19ae4  ldarg.2
0x19ae5  ldloc.s  9
0x19ae7  callvirt instance int32 ExceptionConversionParameters::get_ErrorCode()
0x19aec  stind.i4
0x19aed  ldloc.s  4
0x19aef  brfalse.s loc_19B14
0x19af1  ldloc.s  5
0x19af3  brfalse.s loc_19B0B
0x19af5  ldloc.0
0x19af6  call     string [mscorlib]System.Environment::get_NewLine()
0x19afb  ldarg.0
0x19afc  ldarg.1
0x19afd  ldc.i4.1
0x19afe  call     instance string Microsoft.Crm.ExceptionConverter::GetExceptionShieldedMessage(class [mscorlib]System.Exception exception, [opt] bool fullText)
0x19b03  call     string [mscorlib]System.String::Concat(string, string, string)
0x19b08  stloc.0
0x19b09  br.s     loc_19B14
0x19b0b  ldarg.0
0x19b0c  ldarg.1
0x19b0d  ldc.i4.1
0x19b0e  call     instance string Microsoft.Crm.ExceptionConverter::GetExceptionShieldedMessage(class [mscorlib]System.Exception exception, [opt] bool fullText)
0x19b13  stloc.0
0x19b14  ldstr    aErrorcode0x// "errorCode: 0x"
0x19b19  ldarg.2
0x19b1a  ldstr    aX8// "X8"
0x19b1f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19b24  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x19b29  call     string [mscorlib]System.String::Concat(string, string)
0x19b2e  stloc.s  7
0x19b30  ldloc.s  7
0x19b32  ldstr    aMessage_0// "; message: "
0x19b37  ldarg.0
0x19b38  call     instance bool Microsoft.Crm.ExceptionConverter::get_SkipExceptionMessage()
0x19b3d  brtrue.s loc_19B42
0x19b3f  ldloc.0
0x19b40  br.s     loc_19B48
0x19b42  ldloc.0
0x19b43  call     string Microsoft.Crm.ExceptionConverter::GetHash(string source)
0x19b48  call     string [mscorlib]System.String::Concat(string, string, string)
0x19b4d  stloc.s  7
0x19b4f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x19b54  ldarg.0
0x19b55  call     instance valuetype Microsoft.Crm.TraceCategory Microsoft.Crm.ExceptionConverter::get_TraceCategory()
0x19b5a  ldstr    a0// "{0}"
0x19b5f  ldc.i4.1
0x19b60  newarr   [mscorlib]System.Object
0x19b65  dup
0x19b66  ldc.i4.0
0x19b67  ldstr    aExitConvertmes// "exit: ConvertMessageAndErrorCode: "
0x19b6c  ldloc.s  7
0x19b6e  call     string [mscorlib]System.String::Concat(string, string)
0x19b73  stelem.ref
0x19b74  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x19b79  ldloc.0
0x19b7a  ret
```
