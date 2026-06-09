# Microsoft.Crm.ServerLocatorService::GetSiteSetting

- ea: `0x7190`
- end: `0x7238`
- name: `Microsoft.Crm.ServerLocatorService::GetSiteSetting`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7190`
- `0x9620`
- `0x1c060`
- `0x1eaa0`
- `0x1f510`
- `0x444f0`

## string_xrefs

- `0x71b5`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x720f`: `Error occurred getting site setting in ServerLocatorService : {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7190  ldarg.1
0x7191  ldstr    aSettingname// "settingName"
0x7196  call     void Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string parameter, string name)
0x719b  ldarg.0
0x719c  ldc.i4.1
0x719d  stloc.1
0x719e  ldloca.s 1
0x71a0  constrained. Microsoft.Crm.CrmConfigDatabaseTable
0x71a6  callvirt instance string [mscorlib]System.Object::ToString()
0x71ab  ldc.i4   0x1B5
0x71b0  ldstr    aGetsitesetting_2// "GetSiteSetting"
0x71b5  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x71ba  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x71bf  dup
0x71c0  brtrue.s loc_71C6
0x71c2  pop
0x71c3  ldnull
0x71c4  br.s     loc_71D0
0x71c6  call     instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x71cb  call     T0x2B00002A
0x71d0  stloc.0
0x71d1  ldloc.0
0x71d2  brfalse.s loc_71EC
0x71d4  ldloc.0
0x71d5  ldarg.1
0x71d6  call     instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x71db  brfalse.s loc_71EC
0x71dd  ldloc.0
0x71de  ldarg.1
0x71df  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x71e4  unbox.any mvar<u1>
0x71e9  stloc.2
0x71ea  leave.s  loc_7236
0x71ec  ldarg.2
0x71ed  brfalse.s loc_71FB
0x71ef  ldloca.s 3
0x71f1  initobj  mvar<u1>
0x71f7  ldloc.3
0x71f8  stloc.2
0x71f9  leave.s  loc_7236
0x71fb  ldnull
0x71fc  unbox.any mvar<u1>
0x7201  stloc.2
0x7202  leave.s  loc_7236
0x7204  stloc.s  4
0x7206  ldloc.s  4
0x7208  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x720d  ldc.i4.s 0x14
0x720f  ldstr    aErrorOccurredG_0// "Error occurred getting site setting in "...
0x7214  ldc.i4.1
0x7215  newarr   [mscorlib]System.Object
0x721a  dup
0x721b  ldc.i4.0
0x721c  ldloc.s  4
0x721e  stelem.ref
0x721f  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x7224  ldarg.2
0x7225  brfalse.s loc_7233
0x7227  ldloca.s 3
0x7229  initobj  mvar<u1>
0x722f  ldloc.3
0x7230  stloc.2
0x7231  leave.s  loc_7236
0x7233  ldloc.s  4
0x7235  throw
0x7236  ldloc.2
0x7237  ret
```
