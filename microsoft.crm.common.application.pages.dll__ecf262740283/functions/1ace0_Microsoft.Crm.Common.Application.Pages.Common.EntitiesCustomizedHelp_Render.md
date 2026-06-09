# Microsoft.Crm.Common.Application.Pages.Common.EntitiesCustomizedHelp::Render

- ea: `0x1ace0`
- end: `0x1ad14`
- name: `Microsoft.Crm.Common.Application.Pages.Common.EntitiesCustomizedHelp::Render`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1ad20`
- `0x1ad60`
- `0x1ad80`
- `0x1ade0`

## pseudocode

```c

```

## disassembly

```asm
0x1ace0  ldc.i4   0x2800
0x1ace5  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x1acea  stloc.0
0x1aceb  ldarg.0
0x1acec  ldloc.0
0x1aced  call     instance void Microsoft.Crm.Common.Application.Pages.Common.EntitiesCustomizedHelp::StartDynamicJavaScriptFunction(class [mscorlib]System.Text.StringBuilder stringBuilder)
0x1acf2  ldarg.0
0x1acf3  ldloc.0
0x1acf4  call     instance void Microsoft.Crm.Common.Application.Pages.Common.EntitiesCustomizedHelp::WriteGetEntityCustomizedHelpUrlMethod(class [mscorlib]System.Text.StringBuilder stringBuilder)
0x1acf9  ldarg.0
0x1acfa  ldloc.0
0x1acfb  call     instance void Microsoft.Crm.Common.Application.Pages.Common.EntitiesCustomizedHelp::WriteEntitiesCustomizedHelpUrlMap(class [mscorlib]System.Text.StringBuilder stringBuilder)
0x1ad00  ldarg.0
0x1ad01  ldloc.0
0x1ad02  call     instance void Microsoft.Crm.Common.Application.Pages.Common.EntitiesCustomizedHelp::EndDynamicJavaScriptFunction(class [mscorlib]System.Text.StringBuilder stringBuilder)
0x1ad07  ldarg.1
0x1ad08  ldloc.0
0x1ad09  callvirt instance string [mscorlib]System.Object::ToString()
0x1ad0e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ad13  ret
```
