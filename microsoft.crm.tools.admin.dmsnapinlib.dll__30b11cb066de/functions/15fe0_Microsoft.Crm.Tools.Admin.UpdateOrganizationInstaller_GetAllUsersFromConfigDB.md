# Microsoft.Crm.Tools.Admin.UpdateOrganizationInstaller::GetAllUsersFromConfigDB

- ea: `0x15fe0`
- end: `0x16083`
- name: `Microsoft.Crm.Tools.Admin.UpdateOrganizationInstaller::GetAllUsersFromConfigDB`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x15f60`

## callees

- `0x15fe0`

## string_xrefs

- `0x16026`: `GetAllUsersFromConfigDB`
- `0x1602b`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Organization\Update\UpdateOrganizationInstaller.cs`

## pseudocode

```c

```

## disassembly

```asm
0x15fe0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x15fe5  stloc.0
0x15fe6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x15feb  stloc.1
0x15fec  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x15ff1  stloc.2
0x15ff2  ldloc.2
0x15ff3  ldstr    aOrganizationid// "OrganizationId"
0x15ff8  ldarg.1
0x15ff9  box      [mscorlib]System.Guid
0x15ffe  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x16003  ldloc.1
0x16004  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x16009  ldc.i4.1
0x1600a  newarr   [mscorlib]System.String
0x1600f  dup
0x16010  ldc.i4.0
0x16011  ldstr    aCrmuserid// "CrmUserId"
0x16016  stelem.ref
0x16017  ldc.i4.1
0x16018  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x1601d  dup
0x1601e  ldc.i4.0
0x1601f  ldloc.2
0x16020  stelem.ref
0x16021  ldc.i4   0x124
0x16026  ldstr    aGetallusersfro// "GetAllUsersFromConfigDB"
0x1602b  ldstr    aDDbsShDccm2110_11// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x16030  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x16035  stloc.3
0x16036  ldloc.3
0x16037  brfalse.s loc_16075
0x16039  ldloc.3
0x1603a  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x1603f  stloc.s  4
0x16041  br.s     loc_1606C
0x16043  ldloca.s 4
0x16045  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x1604a  stloc.s  6
0x1604c  ldloca.s 6
0x1604e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x16053  ldstr    aCrmuserid// "CrmUserId"
0x16058  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1605d  unbox.any [mscorlib]System.Guid
0x16062  stloc.s  5
0x16064  ldloc.0
0x16065  ldloc.s  5
0x16067  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x1606c  ldloca.s 4
0x1606e  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x16073  brtrue.s loc_16043
0x16075  leave.s  loc_16081
0x16077  ldloc.1
0x16078  brfalse.s loc_16080
0x1607a  ldloc.1
0x1607b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16080  endfinally
0x16081  ldloc.0
0x16082  ret
```
