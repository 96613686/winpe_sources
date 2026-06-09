# Microsoft.Crm.PluginExceptionConvertor::ConvertPluginException_1

- ea: `0x155a0`
- end: `0x15638`
- name: `Microsoft.Crm.PluginExceptionConvertor::ConvertPluginException_1`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x15580`

## callees

- `0x15490`
- `0x155a0`
- `0x15640`

## string_xrefs

- `0x155da`: `PluginTrace`
- `0x15600`: `PluginTrace`
- `0x1561c`: `PluginTrace`
- `0x15627`: `PluginTrace`

## pseudocode

```c

```

## disassembly

```asm
0x155a0  ldarg.1
0x155a1  brtrue.s loc_155AA
0x155a3  ldsfld   string [mscorlib]System.String::Empty
0x155a8  starg.s  1
0x155aa  ldarg.2
0x155ab  brtrue.s loc_155B4
0x155ad  ldsfld   string [mscorlib]System.String::Empty
0x155b2  starg.s  2
0x155b4  ldarg.3
0x155b5  brtrue.s loc_155BE
0x155b7  ldsfld   string [mscorlib]System.String::Empty
0x155bc  starg.s  3
0x155be  ldarg.s  5
0x155c0  brtrue.s loc_155C9
0x155c2  ldsfld   string [mscorlib]System.String::Empty
0x155c7  starg.s  5
0x155c9  ldarg.0
0x155ca  ldarg.s  6
0x155cc  ldarg.s  8
0x155ce  call     class [mscorlib]System.Exception Microsoft.Crm.PluginExceptionConvertor::ConvertPluginException(class [mscorlib]System.Exception originalException, bool isAsync, bool unwrapTargetInvocationException)
0x155d3  stloc.0
0x155d4  ldloc.0
0x155d5  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x155da  ldstr    aPlugintrace// "PluginTrace"
0x155df  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x155e4  isinst   [mscorlib]System.String
0x155e9  stloc.1
0x155ea  ldloc.0
0x155eb  ldloc.1
0x155ec  ldarg.1
0x155ed  ldarg.2
0x155ee  ldarg.3
0x155ef  ldarg.s  4
0x155f1  ldarg.s  5
0x155f3  ldarg.s  7
0x155f5  call     void Microsoft.Crm.PluginExceptionConvertor::AddPluginTrace(class [mscorlib]System.Exception exception, string childTrace, string pluginTrace, string assemblyName, string pluginType, string stepIdOrWorkflowGroup, string stepDescription, bool addTrace)
0x155fa  ldloc.0
0x155fb  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x15600  ldstr    aPlugintrace// "PluginTrace"
0x15605  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x1560a  isinst   [mscorlib]System.String
0x1560f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15614  brtrue.s loc_15636
0x15616  ldarg.0
0x15617  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x1561c  ldstr    aPlugintrace// "PluginTrace"
0x15621  ldloc.0
0x15622  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x15627  ldstr    aPlugintrace// "PluginTrace"
0x1562c  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x15631  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x15636  ldloc.0
0x15637  ret
```
