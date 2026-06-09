# <>c__DisplayClass4_0::<.ctor>b__0

- ea: `0x1c50`
- end: `0x1ca0`
- name: `<>c__DisplayClass4_0::<.ctor>b__0`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x530`
- `0x1c50`

## string_xrefs

- `0x1c6f`: `Data source cache entry evicted because {0}. Evicted assembly name: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1c50  nop
0x1c51  ldarg.2
0x1c52  isinst   Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContext
0x1c57  stloc.0
0x1c58  ldloc.0
0x1c59  brfalse.s loc_1C69
0x1c5b  ldloc.0
0x1c5c  callvirt instance class [mscorlib]System.Reflection.Assembly Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContext::get_EntityTypes()
0x1c61  ldnull
0x1c62  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x1c67  br.s     loc_1C6A
0x1c69  ldc.i4.0
0x1c6a  stloc.1
0x1c6b  ldloc.1
0x1c6c  brfalse.s loc_1C9F
0x1c6e  nop
0x1c6f  ldstr    aDataSourceCach// "Data source cache entry evicted because"...
0x1c74  ldarg.3
0x1c75  box      [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.EvictionReason
0x1c7a  ldloc.0
0x1c7b  callvirt instance class [mscorlib]System.Reflection.Assembly Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContext::get_EntityTypes()
0x1c80  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x1c85  call     string [mscorlib]System.String::Format(string, object, object)
0x1c8a  stloc.2
0x1c8b  ldarg.0
0x1c8c  ldfld    class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger <>c__DisplayClass4_0::logger
0x1c91  ldloc.2
0x1c92  ldc.i4.0
0x1c93  newarr   [mscorlib]System.Object
0x1c98  call     void [Microsoft.Xrm.Log]Microsoft.Xrm.Log.LoggerExtension::Debug(class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger, string, object[])
0x1c9d  nop
0x1c9e  nop
0x1c9f  ret
```
