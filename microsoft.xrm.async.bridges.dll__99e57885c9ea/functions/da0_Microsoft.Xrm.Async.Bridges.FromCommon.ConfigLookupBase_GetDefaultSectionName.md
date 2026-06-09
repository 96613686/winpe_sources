# Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::GetDefaultSectionName

- ea: `0xda0`
- end: `0xdc8`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::GetDefaultSectionName`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xd10`

## callees

- `0xda0`
- `0xf30`

## pseudocode

```c

```

## disassembly

```asm
0xda0  ldarg.1
0xda1  call     T0x2B000022
0xda6  stloc.0
0xda7  ldloc.0
0xda8  brtrue.s loc_DAD
0xdaa  ldnull
0xdab  br.s     loc_DB3
0xdad  ldloc.0
0xdae  call     instance string Microsoft.Xrm.Async.Bridges.FromCommon.ConfigSectionNameAttribute::get_SectionName()
0xdb3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xdb8  brtrue.s loc_DC1
0xdba  ldloc.0
0xdbb  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommon.ConfigSectionNameAttribute::get_SectionName()
0xdc0  ret
0xdc1  ldarg.1
0xdc2  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xdc7  ret
```
