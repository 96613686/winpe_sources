# Microsoft.Crm.Common.Application.Platform.MenuBuilderFactory::Microsoft.Crm.Application.Ribbon.IMenuBuilderFactory.RetrieveMenu

- ea: `0x45e0`
- end: `0x462c`
- name: `Microsoft.Crm.Common.Application.Platform.MenuBuilderFactory::Microsoft.Crm.Application.Ribbon.IMenuBuilderFactory.RetrieveMenu`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xf20`
- `0x1490`
- `0x45e0`

## pseudocode

```c

```

## disassembly

```asm
0x45e0  ldarg.1
0x45e1  switch   loc_4600, loc_4600, loc_4610, loc_4610, loc_4610, loc_4600
0x45fe  br.s     loc_461C
0x4600  ldarg.2
0x4601  ldarg.3
0x4602  ldarg.s  4
0x4604  ldarg.s  5
0x4606  ldarg.s  6
0x4608  ldarg.s  7
0x460a  newobj   instance void Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::.ctor(string commandPrefix, string idPrefix, bool isWebClient, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, int32 languageCode, bool replaceLocalStrings)
0x460f  ret
0x4610  ldarg.2
0x4611  ldarg.3
0x4612  ldarg.s  5
0x4614  ldarg.s  7
0x4616  newobj   instance void Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::.ctor(string commandPrefix, string idPrefix, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, bool replaceLocalStrings)
0x461b  ret
0x461c  ldstr    aUnsupportedMen// "Unsupported menuValidator."
0x4621  ldstr    aMenuvalidator// "menuValidator"
0x4626  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x462b  throw
```
