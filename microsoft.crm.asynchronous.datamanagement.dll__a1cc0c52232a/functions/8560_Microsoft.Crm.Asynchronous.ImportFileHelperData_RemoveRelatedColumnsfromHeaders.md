# Microsoft.Crm.Asynchronous.ImportFileHelperData::RemoveRelatedColumnsfromHeaders

- ea: `0x8560`
- end: `0x863f`
- name: `Microsoft.Crm.Asynchronous.ImportFileHelperData::RemoveRelatedColumnsfromHeaders`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x82e0`

## callees

- `0x8560`

## pseudocode

```c

```

## disassembly

```asm
0x8560  ldarg.1
0x8561  brfalse  loc_863E
0x8566  ldarg.0
0x8567  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::_importFile
0x856c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x8571  ldstr    aDatadelimiterc// "datadelimitercode"
0x8576  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x857b  brfalse  loc_863E
0x8580  ldarg.0
0x8581  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::_importFile
0x8586  ldstr    aDatadelimiterc// "datadelimitercode"
0x858b  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x8590  brfalse  loc_863E
0x8595  ldarg.0
0x8596  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::_importFile
0x859b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x85a0  ldstr    aFielddelimiter// "fielddelimitercode"
0x85a5  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x85aa  brfalse  loc_863E
0x85af  ldarg.0
0x85b0  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::_importFile
0x85b5  ldstr    aFielddelimiter// "fielddelimitercode"
0x85ba  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x85bf  brfalse.s loc_863E
0x85c1  ldarg.0
0x85c2  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::_importFile
0x85c7  ldstr    aFielddelimiter// "fielddelimitercode"
0x85cc  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x85d1  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x85d6  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x85db  stloc.0
0x85dc  ldarg.0
0x85dd  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::_importFile
0x85e2  ldstr    aDatadelimiterc// "datadelimitercode"
0x85e7  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x85ec  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x85f1  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x85f6  ldloc.0
0x85f7  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CsvDataParser::GetFieldDelimiter(int32)
0x85fc  stloc.1
0x85fd  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CsvDataParser::GetDataDelimiter(int32)
0x8602  stloc.2
0x8603  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ColumnHeaderHelper::.ctor()
0x8608  ldloc.1
0x8609  ldloc.2
0x860a  ldarg.1
0x860b  call     instance string[] [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ColumnHeaderHelper::GetHeaderColumns(string, string, string)
0x8610  stloc.3
0x8611  ldc.i4.0
0x8612  stloc.s  4
0x8614  br.s     loc_8637
0x8616  ldloc.3
0x8617  ldloc.s  4
0x8619  ldelem.ref
0x861a  stloc.s  5
0x861c  ldarg.2
0x861d  ldind.ref
0x861e  ldloc.s  5
0x8620  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x8625  brfalse.s loc_8631
0x8627  ldarg.2
0x8628  ldind.ref
0x8629  ldloc.s  5
0x862b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Remove(var<u1>)
0x8630  pop
0x8631  ldloc.s  4
0x8633  ldc.i4.1
0x8634  add
0x8635  stloc.s  4
0x8637  ldloc.s  4
0x8639  ldloc.3
0x863a  ldlen
0x863b  conv.i4
0x863c  blt.s    loc_8616
0x863e  ret
```
