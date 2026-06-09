# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsQuerySupportedForCaching

- ea: `0x20b30`
- end: `0x20b77`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsQuerySupportedForCaching`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x20b30`
- `0x247c0`

## string_xrefs

- `0x20b63`: `$skiptoken`
- `0x20b56`: `$deltatoken`

## pseudocode

```c

```

## disassembly

```asm
0x20b30  ldc.i4.0
0x20b31  stloc.0
0x20b32  ldarg.0
0x20b33  brfalse.s loc_20B73
0x20b35  ldarg.0
0x20b36  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.OData.CustomQueryOptions::get_QueryParameters()
0x20b3b  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Count()
0x20b40  stloc.1
0x20b41  ldloc.1
0x20b42  brfalse.s loc_20B4A
0x20b44  ldloc.1
0x20b45  ldc.i4.1
0x20b46  beq.s    loc_20B4E
0x20b48  br.s     loc_20B75
0x20b4a  ldc.i4.1
0x20b4b  stloc.0
0x20b4c  br.s     loc_20B75
0x20b4e  ldarg.0
0x20b4f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.OData.CustomQueryOptions::get_QueryParameters()
0x20b54  stloc.2
0x20b55  ldloc.2
0x20b56  ldstr    aDeltatoken// "$deltatoken"
0x20b5b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x20b60  brtrue.s loc_20B6F
0x20b62  ldloc.2
0x20b63  ldstr    aSkiptoken// "$skiptoken"
0x20b68  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x20b6d  brfalse.s loc_20B75
0x20b6f  ldc.i4.1
0x20b70  stloc.0
0x20b71  br.s     loc_20B75
0x20b73  ldc.i4.1
0x20b74  stloc.0
0x20b75  ldloc.0
0x20b76  ret
```
