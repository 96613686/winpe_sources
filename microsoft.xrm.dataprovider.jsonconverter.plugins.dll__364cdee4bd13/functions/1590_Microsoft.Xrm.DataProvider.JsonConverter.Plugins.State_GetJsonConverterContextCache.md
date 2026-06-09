# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.State::GetJsonConverterContextCache

- ea: `0x1590`
- end: `0x15ed`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.State::GetJsonConverterContextCache`
- size: `93`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1d60`
- `0x1ee0`
- `0x1fc0`
- `0x2080`

## callees

- `0x550`
- `0x1590`

## pseudocode

```c

```

## disassembly

```asm
0x1590  nop
0x1591  ldsfld   class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.Interfaces.IJsonConverterContextCache Microsoft.Xrm.DataProvider.JsonConverter.Plugins.State::JsonConverterContextCache
0x1596  ldnull
0x1597  ceq
0x1599  stloc.0
0x159a  ldloc.0
0x159b  brfalse.s loc_15E1
0x159d  nop
0x159e  ldsfld   object Microsoft.Xrm.DataProvider.JsonConverter.Plugins.State::Padlock
0x15a3  stloc.1
0x15a4  ldc.i4.0
0x15a5  stloc.2
0x15a6  ldloc.1
0x15a7  ldloca.s 2
0x15a9  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x15ae  nop
0x15af  nop
0x15b0  ldsfld   class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.Interfaces.IJsonConverterContextCache Microsoft.Xrm.DataProvider.JsonConverter.Plugins.State::JsonConverterContextCache
0x15b5  ldnull
0x15b6  ceq
0x15b8  stloc.3
0x15b9  ldloc.3
0x15ba  brfalse.s loc_15D2
0x15bc  nop
0x15bd  ldarg.0
0x15be  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger>::get_Value()
0x15c3  stloc.s  4
0x15c5  ldloc.s  4
0x15c7  newobj   instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::.ctor(class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger logger)
0x15cc  stsfld   class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.Interfaces.IJsonConverterContextCache Microsoft.Xrm.DataProvider.JsonConverter.Plugins.State::JsonConverterContextCache
0x15d1  nop
0x15d2  nop
0x15d3  leave.s  loc_15E0
0x15d5  ldloc.2
0x15d6  brfalse.s loc_15DF
0x15d8  ldloc.1
0x15d9  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x15de  nop
0x15df  endfinally
0x15e0  nop
0x15e1  ldsfld   class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.Interfaces.IJsonConverterContextCache Microsoft.Xrm.DataProvider.JsonConverter.Plugins.State::JsonConverterContextCache
0x15e6  stloc.s  5
0x15e8  br.s     loc_15EA
0x15ea  ldloc.s  5
0x15ec  ret
```
