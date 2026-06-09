# Microsoft.Crm.PageParametersCache::ReadParameterType

- ea: `0x6a0`
- end: `0x703`
- name: `Microsoft.Crm.PageParametersCache::ReadParameterType`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x660`
- `0x7d0`

## callees

- `0x350`
- `0x360`
- `0x380`
- `0x6a0`
- `0x990`
- `0xba0`
- `0xc60`

## pseudocode

```c

```

## disassembly

```asm
0x6a0  ldarg.1
0x6a1  call     class Microsoft.Crm.IWebParameter Microsoft.Crm.ParameterFactory::GetTypeSpecificParameter(class Microsoft.Crm.IWebParameter parameter)
0x6a6  stloc.0
0x6a7  ldarg.2
0x6a8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6ad  brtrue.s loc_6B6
0x6af  ldloc.0
0x6b0  ldarg.2
0x6b1  callvirt instance void Microsoft.Crm.IWebParameter::set_AssociatedControlName(string value)
0x6b6  ldarg.1
0x6b7  callvirt instance valuetype Microsoft.Crm.ParameterSources Microsoft.Crm.WebParameterAttribute::get_Sources()
0x6bc  ldc.i4.1
0x6bd  and
0x6be  brfalse.s loc_6CD
0x6c0  ldarg.0
0x6c1  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Crm.PageParameters::get_QueryStringParameters()
0x6c6  ldloc.0
0x6c7  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x6cc  pop
0x6cd  ldarg.1
0x6ce  callvirt instance valuetype Microsoft.Crm.ParameterSources Microsoft.Crm.WebParameterAttribute::get_Sources()
0x6d3  ldc.i4.2
0x6d4  and
0x6d5  brfalse.s loc_6E4
0x6d7  ldarg.0
0x6d8  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Crm.PageParameters::get_FormParameters()
0x6dd  ldloc.0
0x6de  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x6e3  pop
0x6e4  ldarg.1
0x6e5  callvirt instance valuetype Microsoft.Crm.ParameterSources Microsoft.Crm.WebParameterAttribute::get_Sources()
0x6ea  ldc.i4.4
0x6eb  and
0x6ec  brfalse.s loc_702
0x6ee  ldarg.0
0x6ef  ldc.i4.1
0x6f0  callvirt instance void Microsoft.Crm.PageParameters::set_ExpectsFormStream(bool value)
0x6f5  ldarg.0
0x6f6  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Crm.PageParameters::get_FormParameters()
0x6fb  ldloc.0
0x6fc  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x701  pop
0x702  ret
```
