# Microsoft.Crm.ServerLocatorService::PopulateOrganizationStatesIfOnline

- ea: `0xa2a0`
- end: `0xa417`
- name: `Microsoft.Crm.ServerLocatorService::PopulateOrganizationStatesIfOnline`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xa280`

## callees

- `0x8370`
- `0x9710`
- `0xa2a0`
- `0xa570`
- `0xbae0`
- `0x17d50`
- `0x17d80`
- `0x1f4f0`
- `0x44400`
- `0x444f0`
- `0x44510`

## string_xrefs

- `0xa2d5`: `MSCRMLocatorService`
- `0xa354`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xa3a5`: `The locator service cannot find an organization sql server. Organization: {0}, SqlServerName: {1}. The organization will be treated as disabled.`

## pseudocode

```c

```

## disassembly

```asm
0xa2a0  ldc.i4.2
0xa2a1  ldarg.0
0xa2a2  call     instance valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.ServerLocatorService::GetSku()
0xa2a7  bne.un   loc_A416
0xa2ac  ldarg.0
0xa2ad  ldarg.0
0xa2ae  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ServerLocatorService::GetScaleGroupId()
0xa2b3  call     instance bool Microsoft.Crm.ServerLocatorService::IsXdbScaleGroup(valuetype [mscorlib]System.Guid scaleGroupId)
0xa2b8  brtrue   loc_A416
0xa2bd  ldarg.1
0xa2be  brfalse  loc_A416
0xa2c3  ldarg.1
0xa2c4  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0xa2c9  brfalse  loc_A416
0xa2ce  newobj   instance void [System]System.Diagnostics.EventLog::.ctor()
0xa2d3  stloc.0
0xa2d4  ldloc.0
0xa2d5  ldstr    aMscrmlocatorse// "MSCRMLocatorService"
0xa2da  callvirt instance void [System]System.Diagnostics.EventLog::set_Source(string)
0xa2df  ldloc.0
0xa2e0  newobj   instance void Microsoft.Crm.CrmEventLog::.ctor(class [System]System.Diagnostics.EventLog eventLog)
0xa2e5  stloc.1
0xa2e6  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xa2eb  stloc.2
0xa2ec  ldc.i4.1
0xa2ed  newarr   [mscorlib]System.String
0xa2f2  dup
0xa2f3  ldc.i4.0
0xa2f4  ldstr    aState// "State"
0xa2f9  stelem.ref
0xa2fa  stloc.3
0xa2fb  ldarg.1
0xa2fc  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0xa301  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0xa306  stloc.s  4
0xa308  br       loc_A3E6
0xa30d  ldloca.s 4
0xa30f  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0xa314  stloc.s  5
0xa316  ldloc.s  5
0xa318  ldstr    aSqlservername// "SqlServerName"
0xa31d  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xa322  isinst   [mscorlib]System.String
0xa327  stloc.s  6
0xa329  ldloc.s  6
0xa32b  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xa330  brtrue   loc_A3E6
0xa335  ldloc.2
0xa336  ldstr    aName// "Name"
0xa33b  ldloc.s  6
0xa33d  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xa342  ldarg.0
0xa343  ldstr    aServer// "Server"
0xa348  ldloc.3
0xa349  ldloc.2
0xa34a  ldc.i4   0x936
0xa34f  ldstr    aPopulateorgani// "PopulateOrganizationStatesIfOnline"
0xa354  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xa359  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ServerLocatorService::RetrieveSingleRow(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xa35e  stloc.s  7
0xa360  ldloc.s  7
0xa362  brfalse.s loc_A378
0xa364  ldc.i4.1
0xa365  ldloc.s  7
0xa367  ldstr    aState// "State"
0xa36c  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xa371  unbox.any [mscorlib]System.Int32
0xa376  beq.s    loc_A3E6
0xa378  ldloc.s  5
0xa37a  ldstr    aState// "State"
0xa37f  ldc.i4.0
0xa380  box      [mscorlib]System.Int32
0xa385  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xa38a  ldloc.s  7
0xa38c  brtrue.s loc_A3E6
0xa38e  ldloc.s  5
0xa390  ldstr    aId// "Id"
0xa395  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xa39a  unbox.any [mscorlib]System.Guid
0xa39f  stloc.s  8
0xa3a1  ldloc.s  8
0xa3a3  ldc.i4.s 0x14
0xa3a5  ldstr    aTheLocatorServ// "The locator service cannot find an orga"...
0xa3aa  ldc.i4.2
0xa3ab  newarr   [mscorlib]System.Object
0xa3b0  dup
0xa3b1  ldc.i4.0
0xa3b2  ldloc.s  8
0xa3b4  box      [mscorlib]System.Guid
0xa3b9  stelem.ref
0xa3ba  dup
0xa3bb  ldc.i4.1
0xa3bc  ldloc.s  6
0xa3be  stelem.ref
0xa3bf  call     void Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0xa3c4  ldloc.1
0xa3c5  ldc.i4.2
0xa3c6  ldc.i4   0xC0004805
0xa3cb  conv.u8
0xa3cc  ldc.i4.2
0xa3cd  newarr   [mscorlib]System.Object
0xa3d2  dup
0xa3d3  ldc.i4.0
0xa3d4  ldloc.s  8
0xa3d6  box      [mscorlib]System.Guid
0xa3db  stelem.ref
0xa3dc  dup
0xa3dd  ldc.i4.1
0xa3de  ldloc.s  6
0xa3e0  stelem.ref
0xa3e1  callvirt instance void Microsoft.Crm.CrmEventLog::WriteEntry(valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventId, object[] values)
0xa3e6  ldloca.s 4
0xa3e8  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0xa3ed  brtrue   loc_A30D
0xa3f2  leave.s  loc_A416
0xa3f4  ldloca.s 4
0xa3f6  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0xa3fc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa401  endfinally
0xa402  ldloc.1
0xa403  brfalse.s loc_A40B
0xa405  ldloc.1
0xa406  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa40b  endfinally
0xa40c  ldloc.0
0xa40d  brfalse.s loc_A415
0xa40f  ldloc.0
0xa410  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa415  endfinally
0xa416  ret
```
