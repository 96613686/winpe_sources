# Microsoft.Crm.Asynchronous.CheckForLanguagePackUpdatesOperation::InternalExecute

- ea: `0xc920`
- end: `0xca3e`
- name: `Microsoft.Crm.Asynchronous.CheckForLanguagePackUpdatesOperation::InternalExecute`
- size: `286`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0xc920`
- `0xca50`
- `0xca70`
- `0xcb10`
- `0xcb60`

## string_xrefs

- `0xc9dd`: `Reprovisioning language {0}. Version {1} provisioned and Version {2} installed`

## pseudocode

```c

```

## disassembly

```asm
0xc920  ldarg.1
0xc921  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xc926  ldc.i4.s 0x2A
0xc928  ceq
0xc92a  ldstr    aOperationTypeM_17// "Operation type must be 'ReprovisionMuiP"...
0xc92f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xc934  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0xc939  ldstr    aAutomaticallyr// "AutomaticallyReprovisionLanguagePacks"
0xc93e  callvirt T0x2B000025
0xc943  brtrue.s loc_C94B
0xc945  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0xc94a  ret
0xc94b  ldarg.0
0xc94c  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.CheckForLanguagePackUpdatesOperation::_orgConfig
0xc951  newobj   instance void Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config)
0xc956  stloc.0
0xc957  ldloc.0
0xc958  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Version> Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::RetrieveInstalledLanguages()
0xc95d  stloc.1
0xc95e  ldloc.0
0xc95f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Version> Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::RetrieveProvisionedLanguages()
0xc964  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xc969  stloc.3
0xc96a  ldloca.s 3
0xc96c  ldc.r8   15.0
0xc975  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0xc97a  stloc.2
0xc97b  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Version>::GetEnumerator()
0xc980  stloc.s  4
0xc982  br       loc_CA1C
0xc987  ldloca.s 4
0xc989  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<int32, class [mscorlib]System.Version>::get_Current()
0xc98e  stloc.s  5
0xc990  ldloca.s 5
0xc992  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class [mscorlib]System.Version>::get_Key()
0xc997  stloc.s  6
0xc999  ldloca.s 5
0xc99b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class [mscorlib]System.Version>::get_Value()
0xc9a0  stloc.s  7
0xc9a2  ldloc.1
0xc9a3  ldloc.s  6
0xc9a5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Version>::ContainsKey(var<u1>)
0xc9aa  brfalse.s loc_CA1C
0xc9ac  ldloc.1
0xc9ad  ldloc.s  6
0xc9af  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Version>::get_Item(void)
0xc9b4  stloc.s  8
0xc9b6  ldloc.s  8
0xc9b8  ldloc.s  7
0xc9ba  call     bool [mscorlib]System.Version::op_GreaterThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xc9bf  brfalse.s loc_CA1C
0xc9c1  ldarg.0
0xc9c2  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.CheckForLanguagePackUpdatesOperation::_orgConfig
0xc9c7  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationBuildVersion()
0xc9cc  ldloc.s  8
0xc9ce  call     bool [mscorlib]System.Version::op_GreaterThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xc9d3  brfalse.s loc_CA1C
0xc9d5  ldarg.1
0xc9d6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xc9db  ldc.i4.s 0x15
0xc9dd  ldstr    aReprovisioning// "Reprovisioning language {0}. Version {1"...
0xc9e2  ldc.i4.3
0xc9e3  newarr   [mscorlib]System.Object
0xc9e8  dup
0xc9e9  ldc.i4.0
0xc9ea  ldloc.s  6
0xc9ec  box      [mscorlib]System.Int32
0xc9f1  stelem.ref
0xc9f2  dup
0xc9f3  ldc.i4.1
0xc9f4  ldloc.s  7
0xc9f6  stelem.ref
0xc9f7  dup
0xc9f8  ldc.i4.2
0xc9f9  ldloc.s  8
0xc9fb  stelem.ref
0xc9fc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xca01  ldloc.0
0xca02  ldloc.s  6
0xca04  ldloc.2
0xca05  ldarg.1
0xca06  callvirt instance void Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::CreateWorkerAsyncOperation(int32 lcid, valuetype [mscorlib]System.DateTime postponeUntil, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent)
0xca0b  ldloca.s 2
0xca0d  ldc.r8   15.0
0xca16  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0xca1b  stloc.2
0xca1c  ldloca.s 4
0xca1e  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<int32, class [mscorlib]System.Version>::MoveNext()
0xca23  brtrue   loc_C987
0xca28  leave.s  loc_CA38
0xca2a  ldloca.s 4
0xca2c  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<int32, class [mscorlib]System.Version>
0xca32  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xca37  endfinally
0xca38  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0xca3d  ret
```
