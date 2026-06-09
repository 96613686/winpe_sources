# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetDeltaToken

- ea: `0x21300`
- end: `0x21324`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetDeltaToken`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1d5e0`

## callees

- `0x21300`

## string_xrefs

- `0x21301`: `$deltatoken`
- `0x2130e`: `$deltatoken`

## pseudocode

```c

```

## disassembly

```asm
0x21300  ldarg.0
0x21301  ldstr    aDeltatoken// "$deltatoken"
0x21306  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x2130b  brfalse.s loc_2131E
0x2130d  ldarg.0
0x2130e  ldstr    aDeltatoken// "$deltatoken"
0x21313  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x21318  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlDecode(string)
0x2131d  ret
0x2131e  ldsfld   string [mscorlib]System.String::Empty
0x21323  ret
```
