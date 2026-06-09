# Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::AddRootNodeDisableDisplayRule

- ea: `0x50bb0`
- end: `0x50c07`
- name: `Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::AddRootNodeDisableDisplayRule`
- size: `87`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x50380`
- `0x995c0`
- `0x99f20`
- `0x9a6d0`

## callees

- `0x50bb0`

## string_xrefs

- `0x50bc9`: `Command`
- `0x50bdb`: `Command`
- `0x50bf7`: `Command`

## pseudocode

```c

```

## disassembly

```asm
0x50bb0  ldarg.0
0x50bb1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_rootNodeAttributes
0x50bb6  brtrue.s loc_50BC3
0x50bb8  ldarg.0
0x50bb9  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x50bbe  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_rootNodeAttributes
0x50bc3  ldarg.0
0x50bc4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_rootNodeAttributes
0x50bc9  ldstr    aCommand// "Command"
0x50bce  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x50bd3  brfalse.s loc_50BF1
0x50bd5  ldarg.0
0x50bd6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_rootNodeAttributes
0x50bdb  ldstr    aCommand// "Command"
0x50be0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x50be5  ldstr    aMscrmDisabled// "Mscrm.Disabled"
0x50bea  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x50bef  brfalse.s loc_50C06
0x50bf1  ldarg.0
0x50bf2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_rootNodeAttributes
0x50bf7  ldstr    aCommand// "Command"
0x50bfc  ldstr    aMscrmDisabled// "Mscrm.Disabled"
0x50c01  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x50c06  ret
```
