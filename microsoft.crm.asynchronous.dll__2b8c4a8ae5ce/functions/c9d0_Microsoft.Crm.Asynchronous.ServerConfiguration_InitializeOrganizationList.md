# Microsoft.Crm.Asynchronous.ServerConfiguration::InitializeOrganizationList

- ea: `0xc9d0`
- end: `0xcb31`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::InitializeOrganizationList`
- size: `353`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0xbda0`
- `0xcc30`

## callees

- `0x5a40`
- `0xc9d0`
- `0xcb40`
- `0xd150`
- `0xd390`
- `0xe590`
- `0x156b0`
- `0x157c0`
- `0x17ac0`
- `0x17b30`
- `0x17b50`

## string_xrefs

- `0xca22`: `d:\dbs\sh\dccm2\1101_190851\cmd\13\src\Core\ObjectModel\Async\Shared\Configuration.cs`
- `0xcad4`: `Initialize Configuration`

## pseudocode

```c

```

## disassembly

```asm
0xc9d0  newobj   instance void <>c__DisplayClass153_2::.ctor()
0xc9d5  stloc.0
0xc9d6  ldloc.0
0xc9d7  ldarg.0
0xc9d8  stfld    class Microsoft.Crm.Asynchronous.ServerConfiguration <>c__DisplayClass153_2::<>4__this
0xc9dd  ldloc.0
0xc9de  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::.ctor()
0xc9e3  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> <>c__DisplayClass153_2::newOrganizations
0xc9e8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::.ctor()
0xc9ed  stloc.1
0xc9ee  ldarg.1
0xc9ef  brfalse.s loc_CA41
0xc9f1  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.Crm]Microsoft.Crm.AsyncConstants::AsyncOrganizationStateColumns
0xc9f6  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0xc9fb  dup
0xc9fc  ldstr    aId_0// "Id"
0xca01  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xca06  stloc.2
0xca07  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0xca0c  ldarg.1
0xca0d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncDebugContext::get_OrganizationId()
0xca12  ldloc.2
0xca13  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0xca18  ldc.i4   0x2BF
0xca1d  ldstr    aInitializeorga// "InitializeOrganizationList"
0xca22  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\1"...
0xca27  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganization(valuetype [mscorlib]System.Guid, string[], int32, string, string)
0xca2c  stloc.3
0xca2d  ldloc.1
0xca2e  ldarg.1
0xca2f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncDebugContext::get_OrganizationId()
0xca34  box      [mscorlib]System.Guid
0xca39  ldloc.3
0xca3a  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>, !!T0)
0xca3f  br.s     loc_CA4D
0xca41  ldarg.0
0xca42  ldfld    class Microsoft.Crm.Asynchronous.IOrganizationRetriever Microsoft.Crm.Asynchronous.ServerConfiguration::retriever
0xca47  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.Asynchronous.IOrganizationRetriever::GetOrganizationList()
0xca4c  stloc.1
0xca4d  ldloc.0
0xca4e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::.ctor()
0xca53  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> <>c__DisplayClass153_2::inactiveOrganizations
0xca58  ldloc.1
0xca59  brfalse  loc_CB18
0xca5e  newobj   instance void <>c__DisplayClass153_1::.ctor()
0xca63  stloc.s  4
0xca65  ldloc.s  4
0xca67  ldloc.0
0xca68  stfld    class <>c__DisplayClass153_2 <>c__DisplayClass153_1::CS$<>8__locals1
0xca6d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.Operations.IServiceOperation>::.ctor()
0xca72  stloc.s  5
0xca74  ldloc.s  4
0xca76  call     class [Microsoft.Crm.Core]Microsoft.Crm.IServerInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ServerInfoProvider::get_Instance()
0xca7b  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles [Microsoft.Crm.Core]Microsoft.Crm.IServerInfoProvider::GetServerRoles()
0xca80  stfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles <>c__DisplayClass153_1::roles
0xca85  ldloc.1
0xca86  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0xca8b  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0xca90  stloc.s  6
0xca92  br.s     loc_CAF8
0xca94  ldloca.s 6
0xca96  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0xca9b  stloc.s  7
0xca9d  newobj   instance void <>c__DisplayClass153_0::.ctor()
0xcaa2  stloc.s  8
0xcaa4  ldloc.s  8
0xcaa6  ldloc.s  4
0xcaa8  stfld    class <>c__DisplayClass153_1 <>c__DisplayClass153_0::CS$<>8__locals2
0xcaad  ldloc.s  8
0xcaaf  ldloc.s  7
0xcab1  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag <>c__DisplayClass153_0::currentOrganization
0xcab6  ldloc.s  8
0xcab8  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag <>c__DisplayClass153_0::currentOrganization
0xcabd  ldstr    aId_0// "Id"
0xcac2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xcac7  unbox.any [mscorlib]System.Guid
0xcacc  stloc.s  9
0xcace  ldarg.0
0xcacf  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.ServerConfiguration::get_OperationsFactory()
0xcad4  ldstr    aInitializeConf// "Initialize Configuration"
0xcad9  ldloc.s  9
0xcadb  ldloc.s  8
0xcadd  ldftn    instance void <>c__DisplayClass153_0::<InitializeOrganizationList>b__0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation serviceOperation)
0xcae3  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0xcae8  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string name, valuetype [mscorlib]System.Guid organizationId, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction)
0xcaed  stloc.s  0xA
0xcaef  ldloc.s  5
0xcaf1  ldloc.s  0xA
0xcaf3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.Operations.IServiceOperation>::Add(var<u1>)
0xcaf8  ldloca.s 6
0xcafa  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0xcaff  brtrue.s loc_CA94
0xcb01  leave.s  loc_CB11
0xcb03  ldloca.s 6
0xcb05  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0xcb0b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcb10  endfinally
0xcb11  ldloc.s  5
0xcb13  call     void Microsoft.Crm.Asynchronous.SequentialExecutionEngine::ExecuteOperations(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Asynchronous.Operations.IServiceOperation> operations)
0xcb18  ldarg.0
0xcb19  ldloc.0
0xcb1a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> <>c__DisplayClass153_2::newOrganizations
0xcb1f  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> Microsoft.Crm.Asynchronous.ServerConfiguration::_organizations
0xcb24  ldarg.0
0xcb25  ldloc.0
0xcb26  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> <>c__DisplayClass153_2::inactiveOrganizations
0xcb2b  call     instance void Microsoft.Crm.Asynchronous.ServerConfiguration::RaiseOrganizationsChangedEvent(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> inactiveOrganizations)
0xcb30  ret
```
