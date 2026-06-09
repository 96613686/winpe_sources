# Microsoft.Crm.Authentication.ServerRolePredicate::GetMachineRoles

- ea: `0x4230`
- end: `0x4320`
- name: `Microsoft.Crm.Authentication.ServerRolePredicate::GetMachineRoles`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4210`

## callees

- `0x4230`

## string_xrefs

- `0x4290`: `Server must be found in configuration database.`
- `0x42a3`: `Server name must be unique in configuration database.`

## pseudocode

```c

```

## disassembly

```asm
0x4230  ldsflda  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles> Microsoft.Crm.Authentication.ServerRolePredicate::_machineRoles
0x4235  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles>::get_HasValue()
0x423a  brtrue   loc_4301
0x423f  call     string [mscorlib]System.Environment::get_MachineName()
0x4244  stloc.0
0x4245  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x424a  stloc.1
0x424b  ldloc.1
0x424c  ldstr    aName// "Name"
0x4251  ldloc.0
0x4252  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x4257  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x425c  stloc.2
0x425d  ldloc.2
0x425e  ldstr    aServer// "Server"
0x4263  ldc.i4.1
0x4264  newarr   [mscorlib]System.String
0x4269  dup
0x426a  ldc.i4.0
0x426b  ldstr    aRoles// "Roles"
0x4270  stelem.ref
0x4271  ldc.i4.1
0x4272  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x4277  dup
0x4278  ldc.i4.0
0x4279  ldloc.1
0x427a  stelem.ref
0x427b  ldc.i4.s 0x2E
0x427d  ldstr    aGetmachinerole// "GetMachineRoles"
0x4282  ldstr    aDA1SSrcPlatfor_0// "D:\\a\\1\\s\\src\\Platform\\Authenticat"...
0x4287  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x428c  dup
0x428d  ldnull
0x428e  cgt.un
0x4290  ldstr    aServerMustBeFo// "Server must be found in configuration d"...
0x4295  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x429a  dup
0x429b  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x42a0  ldc.i4.1
0x42a1  ceq
0x42a3  ldstr    aServerNameMust// "Server name must be unique in configura"...
0x42a8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x42ad  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x42b2  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x42b7  stloc.3
0x42b8  br.s     loc_42DE
0x42ba  ldloca.s 3
0x42bc  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x42c1  ldstr    aRoles// "Roles"
0x42c6  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x42cb  unbox.any [mscorlib]System.Int32
0x42d0  stloc.s  4
0x42d2  ldloc.s  4
0x42d4  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles>::.ctor(var<u1>)
0x42d9  stsfld   valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles> Microsoft.Crm.Authentication.ServerRolePredicate::_machineRoles
0x42de  ldloca.s 3
0x42e0  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x42e5  brtrue.s loc_42BA
0x42e7  leave.s  loc_4301
0x42e9  ldloca.s 3
0x42eb  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x42f1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x42f6  endfinally
0x42f7  ldloc.2
0x42f8  brfalse.s loc_4300
0x42fa  ldloc.2
0x42fb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4300  endfinally
0x4301  ldsflda  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles> Microsoft.Crm.Authentication.ServerRolePredicate::_machineRoles
0x4306  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles>::get_HasValue()
0x430b  ldstr    aCurrentMachine// "Current machine must have roles."
0x4310  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x4315  ldsflda  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles> Microsoft.Crm.Authentication.ServerRolePredicate::_machineRoles
0x431a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles>::get_Value()
0x431f  ret
```
