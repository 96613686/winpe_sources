# Microsoft.Xrm.Sdk.Linq.QueryProvider::GetLinkEntityAlias

- ea: `0xcc70`
- end: `0xcc93`
- name: `Microsoft.Xrm.Sdk.Linq.QueryProvider::GetLinkEntityAlias`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xcca0`
- `0xcd80`

## callees

- `0x9410`
- `0xcc70`
- `0x225f0`

## pseudocode

```c

```

## disassembly

```asm
0xcc70  ldnull
0xcc71  stloc.0
0xcc72  ldarg.2
0xcc73  ldarg.1
0xcc74  callvirt instance var<u1> class [mscorlib]System.Func`2<class [System.Core]System.Linq.Expressions.Expression, class LinkLookup>::Invoke(void)
0xcc79  stloc.1
0xcc7a  ldloc.1
0xcc7b  brfalse.s loc_CC91
0xcc7d  ldloc.1
0xcc7e  callvirt instance class Microsoft.Xrm.Sdk.Query.LinkEntity LinkLookup::get_Link()
0xcc83  brfalse.s loc_CC91
0xcc85  ldloc.1
0xcc86  callvirt instance class Microsoft.Xrm.Sdk.Query.LinkEntity LinkLookup::get_Link()
0xcc8b  callvirt instance string Microsoft.Xrm.Sdk.Query.LinkEntity::get_EntityAlias()
0xcc90  stloc.0
0xcc91  ldloc.0
0xcc92  ret
```
