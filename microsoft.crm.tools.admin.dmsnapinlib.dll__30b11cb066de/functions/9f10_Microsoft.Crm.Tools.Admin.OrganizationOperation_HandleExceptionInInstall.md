# Microsoft.Crm.Tools.Admin.OrganizationOperation::HandleExceptionInInstall

- ea: `0x9f10`
- end: `0x9fbd`
- name: `Microsoft.Crm.Tools.Admin.OrganizationOperation::HandleExceptionInInstall`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9b70`

## callees

- `0x9f10`

## string_xrefs

- `0x9f96`: `HandleExceptionInInstall threw an exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x9f10  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x9f15  stloc.0
0x9f16  ldloc.0
0x9f17  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9f1c  ldstr    a012_0// "{0} {1}: {2}"
0x9f21  ldc.i4.3
0x9f22  newarr   [mscorlib]System.Object
0x9f27  dup
0x9f28  ldc.i4.0
0x9f29  ldarg.2
0x9f2a  stelem.ref
0x9f2b  dup
0x9f2c  ldc.i4.1
0x9f2d  ldarg.0
0x9f2e  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x9f33  callvirt instance string [mscorlib]System.Object::ToString()
0x9f38  stelem.ref
0x9f39  dup
0x9f3a  ldc.i4.2
0x9f3b  ldarg.1
0x9f3c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x9f41  stelem.ref
0x9f42  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9f47  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x9f4c  pop
0x9f4d  br.s     loc_9F75
0x9f4f  ldloc.0
0x9f50  ldstr    aInnerexception// "InnerException:"
0x9f55  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x9f5a  pop
0x9f5b  ldloc.0
0x9f5c  ldarg.1
0x9f5d  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x9f62  callvirt instance string [mscorlib]System.Object::ToString()
0x9f67  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x9f6c  pop
0x9f6d  ldarg.1
0x9f6e  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x9f73  starg.s  1
0x9f75  ldarg.1
0x9f76  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x9f7b  brtrue.s loc_9F4F
0x9f7d  ldloc.0
0x9f7e  callvirt instance string [mscorlib]System.Object::ToString()
0x9f83  ldc.i4.0
0x9f84  newarr   [mscorlib]System.Object
0x9f89  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, object[])
0x9f8e  leave.s  loc_9FBC
0x9f90  stloc.1
0x9f91  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9f96  ldstr    aHandleexceptio// "HandleExceptionInInstall threw an excep"...
0x9f9b  ldc.i4.1
0x9f9c  newarr   [mscorlib]System.Object
0x9fa1  dup
0x9fa2  ldc.i4.0
0x9fa3  ldloc.1
0x9fa4  callvirt instance string [mscorlib]System.Exception::get_Message()
0x9fa9  stelem.ref
0x9faa  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9faf  ldc.i4.0
0x9fb0  newarr   [mscorlib]System.Object
0x9fb5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, object[])
0x9fba  leave.s  loc_9FBC
0x9fbc  ret
```
