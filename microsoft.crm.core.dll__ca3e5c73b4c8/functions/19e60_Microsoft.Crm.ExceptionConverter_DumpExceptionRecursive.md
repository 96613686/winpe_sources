# Microsoft.Crm.ExceptionConverter::DumpExceptionRecursive

- ea: `0x19e60`
- end: `0x1a122`
- name: `Microsoft.Crm.ExceptionConverter::DumpExceptionRecursive`
- size: `706`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x19e10`
- `0x19e60`

## callees

- `0x18890`
- `0x19c20`
- `0x19d50`
- `0x19db0`
- `0x19dd0`
- `0x19df0`
- `0x19e30`
- `0x19e60`
- `0x1a130`
- `0x1a140`
- `0x1a920`

## string_xrefs

- `0x19fe0`: `PluginTrace`
- `0x19ff5`: `PluginTrace`
- `0x1a08b`: `no PluginTrace`
- `0x1a024`: `PluginTrace length: {0}`
- `0x1a03e`: `PluginTrace: present: `
- `0x1a057`: `>>>>> PluginTrace ({0}): `
- `0x1a071`: `<<<<< PluginTrace:`
- `0x1a07e`: `PluginTrace <null>`

## pseudocode

```c

```

## disassembly

```asm
0x19e60  ldnull
0x19e61  stloc.0
0x19e62  ldarg.1
0x19e63  ldstr    aException_0// ">>>>> EXCEPTION: "
0x19e68  ldarg.0
0x19e69  ldfld    int32 Microsoft.Crm.ExceptionConverter::_exceptionDepth
0x19e6e  box      [mscorlib]System.Int32
0x19e73  call     string [mscorlib]System.String::Concat(object, object)
0x19e78  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x19e7d  ldarg.1
0x19e7e  ldstr    aType_0// "Type: "
0x19e83  ldarg.2
0x19e84  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x19e89  call     string [mscorlib]System.String::Concat(object, object)
0x19e8e  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x19e93  ldarg.2
0x19e94  isinst   Microsoft.Crm.CrmException
0x19e99  stloc.1
0x19e9a  ldloc.1
0x19e9b  brfalse.s loc_19F08
0x19e9d  ldloc.1
0x19e9e  callvirt instance int32 Microsoft.Crm.CrmException::get_ErrorCode()
0x19ea3  call     string Microsoft.Crm.ExceptionConverter::GetErrorCodeName(int32 errorCode)
0x19ea8  stloc.3
0x19ea9  ldarg.1
0x19eaa  ldstr    aErrorcode0x_0// "ErrorCode: 0x"
0x19eaf  ldloc.1
0x19eb0  callvirt instance int32 Microsoft.Crm.CrmException::get_ErrorCode()
0x19eb5  stloc.s  4
0x19eb7  ldloca.s 4
0x19eb9  ldstr    aX8// "X8"
0x19ebe  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19ec3  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x19ec8  ldstr    asc_7CC52// ": "
0x19ecd  ldloc.3
0x19ece  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x19ed3  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x19ed8  ldarg.2
0x19ed9  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x19ede  brfalse.s loc_19F08
0x19ee0  ldarg.2
0x19ee1  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x19ee6  ldstr    aCrmexceptionfa// "CrmExceptionFaults"
0x19eeb  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x19ef0  brfalse.s loc_19F08
0x19ef2  ldarg.2
0x19ef3  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x19ef8  ldstr    aCrmexceptionfa// "CrmExceptionFaults"
0x19efd  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x19f02  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault
0x19f07  stloc.0
0x19f08  ldarg.2
0x19f09  callvirt instance string [mscorlib]System.Exception::get_Message()
0x19f0e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19f13  brfalse.s loc_19F22
0x19f15  ldarg.1
0x19f16  ldstr    aMessageNull// "Message <null>"
0x19f1b  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x19f20  br.s     loc_19F5E
0x19f22  ldarg.0
0x19f23  call     instance bool Microsoft.Crm.ExceptionConverter::get_SkipExceptionMessage()
0x19f28  brfalse.s loc_19F3D
0x19f2a  ldarg.1
0x19f2b  ldstr    aSkippingExcept// "Skipping Exception Message: ExceptionTy"...
0x19f30  ldarg.2
0x19f31  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x19f36  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string, object)
0x19f3b  br.s     loc_19F5E
0x19f3d  ldarg.1
0x19f3e  ldstr    aMessage01// "Message ({0}): {1}"
0x19f43  ldarg.2
0x19f44  callvirt instance string [mscorlib]System.Exception::get_Message()
0x19f49  callvirt instance int32 [mscorlib]System.String::get_Length()
0x19f4e  box      [mscorlib]System.Int32
0x19f53  ldarg.2
0x19f54  callvirt instance string [mscorlib]System.Exception::get_Message()
0x19f59  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string, object, object)
0x19f5e  ldarg.2
0x19f5f  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x19f64  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19f69  brfalse.s loc_19F78
0x19f6b  ldarg.1
0x19f6c  ldstr    aStacktraceNull// "StackTrace <null>"
0x19f71  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x19f76  br.s     loc_19FCF
0x19f78  ldarg.0
0x19f79  call     instance bool Microsoft.Crm.ExceptionConverter::get_SkipCallStack()
0x19f7e  brfalse.s loc_19F9D
0x19f80  ldarg.1
0x19f81  ldstr    aStacktracePres// "StackTrace: present: "
0x19f86  ldarg.2
0x19f87  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x19f8c  call     string Microsoft.Crm.ExceptionConverter::GetHash(string source)
0x19f91  call     string [mscorlib]System.String::Concat(string, string)
0x19f96  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x19f9b  br.s     loc_19FCF
0x19f9d  ldarg.1
0x19f9e  ldstr    aStacktrace0// ">>>>> StackTrace ({0}):"
0x19fa3  ldarg.2
0x19fa4  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x19fa9  callvirt instance int32 [mscorlib]System.String::get_Length()
0x19fae  box      [mscorlib]System.Int32
0x19fb3  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string, object)
0x19fb8  ldarg.1
0x19fb9  ldarg.2
0x19fba  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x19fbf  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x19fc4  ldarg.1
0x19fc5  ldstr    aStacktrace// "<<<<< StackTrace:"
0x19fca  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x19fcf  ldarg.2
0x19fd0  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x19fd5  brfalse  loc_1A08A
0x19fda  ldarg.2
0x19fdb  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x19fe0  ldstr    aPlugintrace// "PluginTrace"
0x19fe5  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x19fea  brfalse  loc_1A08A
0x19fef  ldarg.2
0x19ff0  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x19ff5  ldstr    aPlugintrace// "PluginTrace"
0x19ffa  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x19fff  isinst   [mscorlib]System.String
0x1a004  stloc.s  5
0x1a006  ldloc.s  5
0x1a008  brtrue.s loc_1A00D
0x1a00a  ldc.i4.0
0x1a00b  br.s     loc_1A014
0x1a00d  ldloc.s  5
0x1a00f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1a014  stloc.s  6
0x1a016  ldloc.s  6
0x1a018  ldc.i4.0
0x1a019  ble.s    loc_1A07D
0x1a01b  ldarg.0
0x1a01c  call     instance bool Microsoft.Crm.ExceptionConverter::get_SkipTraceTextLength()
0x1a021  brtrue.s loc_1A035
0x1a023  ldarg.1
0x1a024  ldstr    aPlugintraceLen// "PluginTrace length: {0}"
0x1a029  ldloc.s  6
0x1a02b  box      [mscorlib]System.Int32
0x1a030  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string, object)
0x1a035  ldarg.0
0x1a036  call     instance bool Microsoft.Crm.ExceptionConverter::get_SkipTraceText()
0x1a03b  brfalse.s loc_1A056
0x1a03d  ldarg.1
0x1a03e  ldstr    aPlugintracePre// "PluginTrace: present: "
0x1a043  ldloc.s  5
0x1a045  call     string Microsoft.Crm.ExceptionConverter::GetHash(string source)
0x1a04a  call     string [mscorlib]System.String::Concat(string, string)
0x1a04f  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1a054  br.s     loc_1A095
0x1a056  ldarg.1
0x1a057  ldstr    aPlugintrace0// ">>>>> PluginTrace ({0}): "
0x1a05c  ldloc.s  6
0x1a05e  box      [mscorlib]System.Int32
0x1a063  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string, object)
0x1a068  ldarg.1
0x1a069  ldloc.s  5
0x1a06b  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1a070  ldarg.1
0x1a071  ldstr    aPlugintrace_0// "<<<<< PluginTrace:"
0x1a076  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1a07b  br.s     loc_1A095
0x1a07d  ldarg.1
0x1a07e  ldstr    aPlugintraceNul// "PluginTrace <null>"
0x1a083  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1a088  br.s     loc_1A095
0x1a08a  ldarg.1
0x1a08b  ldstr    aNoPlugintrace// "no PluginTrace"
0x1a090  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1a095  ldarg.0
0x1a096  ldarg.2
0x1a097  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault Microsoft.Crm.ExceptionConverter::ExtractFault(class [mscorlib]System.Exception exception)
0x1a09c  stloc.2
0x1a09d  ldloc.2
0x1a09e  brfalse.s loc_1A0A2
0x1a0a0  ldloc.2
0x1a0a1  stloc.0
0x1a0a2  ldloc.0
0x1a0a3  brfalse.s loc_1A0AD
0x1a0a5  ldarg.0
0x1a0a6  ldarg.1
0x1a0a7  ldloc.0
0x1a0a8  call     instance void Microsoft.Crm.ExceptionConverter::DumpFault(class [mscorlib]System.IO.StreamWriter streamWriter, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault fault)
0x1a0ad  ldarg.2
0x1a0ae  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x1a0b3  brtrue.s loc_1A0DC
0x1a0b5  ldarg.1
0x1a0b6  ldstr    aInnerexception// "InnerException <null>"
0x1a0bb  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1a0c0  ldarg.1
0x1a0c1  ldstr    aException_1// "<<<<< EXCEPTION: "
0x1a0c6  ldarg.0
0x1a0c7  ldfld    int32 Microsoft.Crm.ExceptionConverter::_exceptionDepth
0x1a0cc  box      [mscorlib]System.Int32
0x1a0d1  call     string [mscorlib]System.String::Concat(object, object)
0x1a0d6  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1a0db  ret
0x1a0dc  ldarg.0
0x1a0dd  ldarg.0
0x1a0de  ldfld    int32 Microsoft.Crm.ExceptionConverter::_exceptionDepth
0x1a0e3  ldc.i4.1
0x1a0e4  add
0x1a0e5  stfld    int32 Microsoft.Crm.ExceptionConverter::_exceptionDepth
0x1a0ea  ldarg.0
0x1a0eb  ldfld    int32 Microsoft.Crm.ExceptionConverter::_exceptionDepth
0x1a0f0  ldarg.0
0x1a0f1  callvirt instance int32 Microsoft.Crm.ExceptionConverter::get_NestingDepth()
0x1a0f6  ble.s    loc_1A114
0x1a0f8  ldarg.1
0x1a0f9  ldstr    aRecursionLimit// "### RECURSION LIMIT EXCEEDED: "
0x1a0fe  ldarg.0
0x1a0ff  ldfld    int32 Microsoft.Crm.ExceptionConverter::_exceptionDepth
0x1a104  box      [mscorlib]System.Int32
0x1a109  call     string [mscorlib]System.String::Concat(object, object)
0x1a10e  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1a113  ret
0x1a114  ldarg.0
0x1a115  ldarg.1
0x1a116  ldarg.2
0x1a117  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x1a11c  call     instance void Microsoft.Crm.ExceptionConverter::DumpExceptionRecursive(class [mscorlib]System.IO.StreamWriter streamWriter, class [mscorlib]System.Exception exception)
0x1a121  ret
```
