# Microsoft.Crm.Asynchronous.LegacyOrganizationRetriever::GetOrganizationList

- ea: `0xd3d0`
- end: `0xd4cd`
- name: `Microsoft.Crm.Asynchronous.LegacyOrganizationRetriever::GetOrganizationList`
- size: `253`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xd3b0`
- `0xd3c0`
- `0xd3d0`

## string_xrefs

- `0xd43b`: `Exception while {0} attemp in getting organization list: {1}`

## pseudocode

```c

```

## disassembly

```asm
0xd3d0  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.Crm]Microsoft.Crm.AsyncConstants::AsyncOrganizationStateColumns
0xd3d5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0xd3da  dup
0xd3db  ldstr    aId_0// "Id"
0xd3e0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xd3e5  stloc.0
0xd3e6  ldc.i4.0
0xd3e7  stloc.1
0xd3e8  ldc.i4.0
0xd3e9  stloc.2
0xd3ea  br       loc_D4B7
0xd3ef  nop
0xd3f0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationStateInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStateInfoProvider::get_Instance()
0xd3f5  ldloc.0
0xd3f6  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0xd3fb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationStateInfoProvider::GetDeploymentOrganizationStates(string[])
0xd400  stloc.3
0xd401  ldloc.1
0xd402  brtrue.s loc_D42A
0xd404  ldarg.0
0xd405  call     instance bool Microsoft.Crm.Asynchronous.LegacyOrganizationRetriever::get_ReliabilitySettingsRetrieved()
0xd40a  brtrue.s loc_D423
0xd40c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xd411  ldc.i4.s 0x15
0xd413  ldstr    aReliabilitySet// "Reliability settings loaded successfull"...
0xd418  ldc.i4.0
0xd419  newarr   [mscorlib]System.Object
0xd41e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd423  ldarg.0
0xd424  ldc.i4.1
0xd425  call     instance void Microsoft.Crm.Asynchronous.LegacyOrganizationRetriever::set_ReliabilitySettingsRetrieved(bool value)
0xd42a  ldloc.3
0xd42b  stloc.s  4
0xd42d  leave    loc_D4CA
0xd432  stloc.s  5
0xd434  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xd439  ldc.i4.s 0x15
0xd43b  ldstr    aExceptionWhile_1// "Exception while {0} attemp in getting o"...
0xd440  ldc.i4.2
0xd441  newarr   [mscorlib]System.Object
0xd446  dup
0xd447  ldc.i4.0
0xd448  ldloc.2
0xd449  box      [mscorlib]System.Int32
0xd44e  stelem.ref
0xd44f  dup
0xd450  ldc.i4.1
0xd451  ldloc.s  5
0xd453  stelem.ref
0xd454  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd459  ldarg.0
0xd45a  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.LegacyOrganizationRetriever::LocatorServiceAttemptInterval
0xd45f  call     void [mscorlib]System.Threading.Thread::Sleep(valuetype [mscorlib]System.TimeSpan)
0xd464  leave.s  loc_D4B3
0xd466  stloc.s  6
0xd468  ldarg.0
0xd469  call     instance bool Microsoft.Crm.Asynchronous.LegacyOrganizationRetriever::get_ReliabilitySettingsRetrieved()
0xd46e  brfalse.s loc_D48E
0xd470  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xd475  ldc.i4.s 0x15
0xd477  ldstr    aErrorWhenLoadi// "Error when loading reliability settings"...
0xd47c  ldloc.s  6
0xd47e  call     string [mscorlib]System.String::Concat(object, object)
0xd483  ldc.i4.0
0xd484  newarr   [mscorlib]System.Object
0xd489  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd48e  ldarg.0
0xd48f  ldc.i4.0
0xd490  call     instance void Microsoft.Crm.Asynchronous.LegacyOrganizationRetriever::set_ReliabilitySettingsRetrieved(bool value)
0xd495  ldc.i4.1
0xd496  stloc.1
0xd497  ldloc.0
0xd498  ldstr    aIsdisabledfora// "IsDisabledForAsyncProcessing"
0xd49d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::IndexOf(var<u1>)
0xd4a2  stloc.s  7
0xd4a4  ldloc.s  7
0xd4a6  ldc.i4.m1
0xd4a7  beq.s    loc_D4B1
0xd4a9  ldloc.0
0xd4aa  ldloc.s  7
0xd4ac  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::RemoveAt(int32)
0xd4b1  leave.s  loc_D4B3
0xd4b3  ldloc.2
0xd4b4  ldc.i4.1
0xd4b5  add
0xd4b6  stloc.2
0xd4b7  ldloc.2
0xd4b8  ldc.i4.s 0xB
0xd4ba  blt      loc_D3EF
0xd4bf  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationStateInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStateInfoProvider::get_Instance()
0xd4c4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationStateInfoProvider::GetDeploymentOrganizationStates()
0xd4c9  ret
0xd4ca  ldloc.s  4
0xd4cc  ret
```
