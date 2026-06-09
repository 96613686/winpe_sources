# Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::InitializeOrganizationList

- ea: `0xe800`
- end: `0xe936`
- name: `Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::InitializeOrganizationList`
- size: `310`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0xe660`
- `0xe7d0`
- `0xe940`

## callees

- `0x7e80`
- `0xe590`
- `0xe7b0`
- `0xe800`
- `0x156a0`
- `0x157c0`
- `0x17c20`

## pseudocode

```c

```

## disassembly

```asm
0xe800  newobj   instance void <>c__DisplayClass22_0::.ctor()
0xe805  stloc.0
0xe806  ldloc.0
0xe807  ldarg.0
0xe808  stfld    class Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase <>c__DisplayClass22_0::<>4__this
0xe80d  ldloc.0
0xe80e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::.ctor()
0xe813  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> <>c__DisplayClass22_0::newOrganizations
0xe818  ldloc.0
0xe819  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::.ctor()
0xe81e  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> <>c__DisplayClass22_0::inactiveOrganizationsInQueue
0xe823  ldarg.1
0xe824  brfalse.s loc_E868
0xe826  ldarg.1
0xe827  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Keys()
0xe82c  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::GetEnumerator()
0xe831  stloc.2
0xe832  br.s     loc_E84F
0xe834  ldloca.s 2
0xe836  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Current()
0xe83b  stloc.3
0xe83c  ldloc.0
0xe83d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> <>c__DisplayClass22_0::inactiveOrganizationsInQueue
0xe842  ldloc.3
0xe843  ldarg.1
0xe844  ldloc.3
0xe845  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Item(void)
0xe84a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::set_Item(var<u1>, !!T0)
0xe84f  ldloca.s 2
0xe851  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::MoveNext()
0xe856  brtrue.s loc_E834
0xe858  leave.s  loc_E868
0xe85a  ldloca.s 2
0xe85c  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>
0xe862  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe867  endfinally
0xe868  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.Operations.IServiceOperation>::.ctor()
0xe86d  stloc.1
0xe86e  ldarg.0
0xe86f  ldfld    class Microsoft.Crm.Asynchronous.ISharedQueueConfiguration Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::_sharedConfiguration
0xe874  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationList::get_Organizations()
0xe879  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Keys()
0xe87e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0xe883  stloc.s  4
0xe885  br.s     loc_E8ED
0xe887  ldloc.s  4
0xe889  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0xe88e  stloc.s  5
0xe890  ldarg.0
0xe891  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::get_OperationsFactory()
0xe896  ldarg.0
0xe897  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xe89c  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xe8a1  ldstr    aIsOrganization// ": Is Organization Valid"
0xe8a6  call     string [mscorlib]System.String::Concat(string, string)
0xe8ab  ldarg.0
0xe8ac  ldfld    class Microsoft.Crm.Asynchronous.ISharedQueueConfiguration Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::_sharedConfiguration
0xe8b1  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationList::get_Organizations()
0xe8b6  ldloc.s  5
0xe8b8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Item(void)
0xe8bd  ldloc.0
0xe8be  ldfld    class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction <>c__DisplayClass22_0::<>9__0
0xe8c3  dup
0xe8c4  brtrue.s loc_E8DE
0xe8c6  pop
0xe8c7  ldloc.0
0xe8c8  ldloc.0
0xe8c9  ldftn    instance void <>c__DisplayClass22_0::<InitializeOrganizationList>b__0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation serviceOperation)
0xe8cf  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0xe8d4  dup
0xe8d5  stloc.s  7
0xe8d7  stfld    class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction <>c__DisplayClass22_0::<>9__0
0xe8dc  ldloc.s  7
0xe8de  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string name, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction)
0xe8e3  stloc.s  6
0xe8e5  ldloc.1
0xe8e6  ldloc.s  6
0xe8e8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.Operations.IServiceOperation>::Add(var<u1>)
0xe8ed  ldloc.s  4
0xe8ef  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe8f4  brtrue.s loc_E887
0xe8f6  leave.s  loc_E904
0xe8f8  ldloc.s  4
0xe8fa  brfalse.s loc_E903
0xe8fc  ldloc.s  4
0xe8fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe903  endfinally
0xe904  ldloc.1
0xe905  call     void Microsoft.Crm.Asynchronous.SequentialExecutionEngine::ExecuteOperations(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Asynchronous.Operations.IServiceOperation> operations)
0xe90a  ldarg.0
0xe90b  ldloc.0
0xe90c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> <>c__DisplayClass22_0::newOrganizations
0xe911  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::_organizations
0xe916  ldarg.0
0xe917  ldfld    class [mscorlib]System.EventHandler Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::OrganizationsChanged
0xe91c  brfalse.s loc_E935
0xe91e  ldarg.0
0xe91f  ldfld    class [mscorlib]System.EventHandler Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::OrganizationsChanged
0xe924  ldarg.0
0xe925  ldloc.0
0xe926  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> <>c__DisplayClass22_0::inactiveOrganizationsInQueue
0xe92b  newobj   instance void Microsoft.Crm.Asynchronous.OrganizationChangedEventArgs::.ctor(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> inactiveOrganizations)
0xe930  callvirt instance void [mscorlib]System.EventHandler::Invoke(object, class [mscorlib]System.EventArgs)
0xe935  ret
```
