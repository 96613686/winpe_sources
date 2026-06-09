# Microsoft.Crm.Common.Application.Pages.Common.GlobalHandler::Write_Crm_8_0_CompatibilityWrappers

- ea: `0x1bed0`
- end: `0x1bf28`
- name: `Microsoft.Crm.Common.Application.Pages.Common.GlobalHandler::Write_Crm_8_0_CompatibilityWrappers`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1bc80`

## callees

- `0x1bed0`

## string_xrefs

- `0x1bed5`: `Compatibility\8.0.1-.js`

## pseudocode

```c

```

## disassembly

```asm
0x1bed0  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x1bed5  ldstr    aCompatibility8// "Compatibility\\8.0.1-.js"
0x1beda  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.Reflection.Assembly::GetManifestResourceStream(string)
0x1bedf  stloc.0
0x1bee0  ldloc.0
0x1bee1  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x1bee6  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream, class [mscorlib]System.Text.Encoding)
0x1beeb  stloc.1
0x1beec  ldloc.1
0x1beed  callvirt instance string [mscorlib]System.IO.TextReader::ReadLine()
0x1bef2  stloc.2
0x1bef3  br.s     loc_1BF0E
0x1bef5  ldarg.1
0x1bef6  ldloc.2
0x1bef7  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1befc  ldarg.1
0x1befd  call     string [mscorlib]System.Environment::get_NewLine()
0x1bf02  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1bf07  ldloc.1
0x1bf08  callvirt instance string [mscorlib]System.IO.TextReader::ReadLine()
0x1bf0d  stloc.2
0x1bf0e  ldloc.2
0x1bf0f  brtrue.s loc_1BEF5
0x1bf11  leave.s  loc_1BF27
0x1bf13  ldloc.1
0x1bf14  brfalse.s loc_1BF1C
0x1bf16  ldloc.1
0x1bf17  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1bf1c  endfinally
0x1bf1d  ldloc.0
0x1bf1e  brfalse.s loc_1BF26
0x1bf20  ldloc.0
0x1bf21  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1bf26  endfinally
0x1bf27  ret
```
