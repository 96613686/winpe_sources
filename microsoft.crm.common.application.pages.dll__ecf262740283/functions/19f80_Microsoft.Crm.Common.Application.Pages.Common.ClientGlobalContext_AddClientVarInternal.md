# Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVarInternal

- ea: `0x19f80`
- end: `0x19fbf`
- name: `Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVarInternal`
- size: `63`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x19f10`
- `0x19f20`
- `0x19f40`
- `0x19f60`
- `0x19fc0`

## callees

- `0x19f80`

## pseudocode

```c

```

## disassembly

```asm
0x19f80  ldarg.2
0x19f81  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Script::IsValidJavaScriptIdentifier(string)
0x19f86  brtrue.s loc_19F9A
0x19f88  ldstr    aInvalidJavascr// "Invalid javascript variable name: "
0x19f8d  ldarg.2
0x19f8e  call     string [mscorlib]System.String::Concat(string, string)
0x19f93  ldarg.2
0x19f94  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x19f99  throw
0x19f9a  ldarg.1
0x19f9b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19fa0  ldstr    aWindow01// "window.{0}={1};"
0x19fa5  ldc.i4.2
0x19fa6  newarr   [mscorlib]System.Object
0x19fab  dup
0x19fac  ldc.i4.0
0x19fad  ldarg.2
0x19fae  stelem.ref
0x19faf  dup
0x19fb0  ldc.i4.1
0x19fb1  ldarg.3
0x19fb2  stelem.ref
0x19fb3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x19fb8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x19fbd  pop
0x19fbe  ret
```
