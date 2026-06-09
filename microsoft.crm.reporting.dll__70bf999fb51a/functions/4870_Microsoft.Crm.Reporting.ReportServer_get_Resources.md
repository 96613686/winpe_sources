# Microsoft.Crm.Reporting.ReportServer::get_Resources

- ea: `0x4870`
- end: `0x489e`
- name: `Microsoft.Crm.Reporting.ReportServer::get_Resources`
- size: `46`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6cd0`
- `0x7710`
- `0x7c20`
- `0x7cc0`
- `0x7d00`
- `0x7dc0`

## callees

- `0x4870`

## pseudocode

```c

```

## disassembly

```asm
0x4870  ldarg.0
0x4871  ldfld    class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::_resources
0x4876  brtrue.s loc_4897
0x4878  ldarg.0
0x4879  ldstr    aMicrosoftCrmRe// "Microsoft.Crm.Reporting.Strings"
0x487e  ldtoken  Microsoft.Crm.Reporting.ReportServer
0x4883  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4888  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x488d  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x4892  stfld    class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::_resources
0x4897  ldarg.0
0x4898  ldfld    class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::_resources
0x489d  ret
```
