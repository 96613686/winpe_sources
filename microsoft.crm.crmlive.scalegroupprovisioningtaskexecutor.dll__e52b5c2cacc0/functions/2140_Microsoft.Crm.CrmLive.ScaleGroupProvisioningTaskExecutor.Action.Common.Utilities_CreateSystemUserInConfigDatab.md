# Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.Common.Utilities::CreateSystemUserInConfigDatabase

- ea: `0x2140`
- end: `0x2329`
- name: `Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.Common.Utilities::CreateSystemUserInConfigDatabase`
- size: `489`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x23c0`
- `0x3100`

## callees

- `0x2140`

## string_xrefs

- `0x2191`: `CreateSystemUserInConfigDatabase`
- `0x21ee`: `CreateSystemUserInConfigDatabase`
- `0x229c`: `CreateSystemUserInConfigDatabase`
- `0x230c`: `CreateSystemUserInConfigDatabase`
- `0x2196`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\Common\Utilities.cs`
- `0x21f3`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\Common\Utilities.cs`
- `0x22a1`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\Common\Utilities.cs`
- `0x2311`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\Common\Utilities.cs`

## pseudocode

```c

```

## disassembly

```asm
0x2140  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x2145  stloc.0
0x2146  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x214b  stloc.1
0x214c  ldloc.1
0x214d  ldstr    aName// "Name"
0x2152  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2157  ldarg.3
0x2158  ldc.i4.1
0x2159  newarr   [mscorlib]System.Object
0x215e  dup
0x215f  ldc.i4.0
0x2160  ldarg.1
0x2161  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x2166  stelem.ref
0x2167  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x216c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2171  ldloc.0
0x2172  ldstr    aSystemuser// "SystemUser"
0x2177  ldc.i4.1
0x2178  newarr   [mscorlib]System.String
0x217d  dup
0x217e  ldc.i4.0
0x217f  ldstr    aId// "Id"
0x2184  stelem.ref
0x2185  ldc.i4.1
0x2186  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x218b  dup
0x218c  ldc.i4.0
0x218d  ldloc.1
0x218e  stelem.ref
0x218f  ldc.i4.s 0x1F
0x2191  ldstr    aCreatesystemus// "CreateSystemUserInConfigDatabase"
0x2196  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x219b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x21a0  stloc.2
0x21a1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x21a6  stloc.3
0x21a7  ldloc.2
0x21a8  brfalse.s loc_21BF
0x21aa  ldloc.2
0x21ab  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x21b0  brfalse.s loc_21BF
0x21b2  ldloc.2
0x21b3  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x21b8  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x21bd  brtrue.s loc_2205
0x21bf  ldloc.1
0x21c0  ldstr    aDefaultorganiz// "DefaultOrganizationId"
0x21c5  ldarg.0
0x21c6  box      [mscorlib]System.Guid
0x21cb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x21d0  ldloc.1
0x21d1  ldstr    aId// "Id"
0x21d6  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x21db  box      [mscorlib]System.Guid
0x21e0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x21e5  ldloc.0
0x21e6  ldstr    aSystemuser// "SystemUser"
0x21eb  ldloc.1
0x21ec  ldc.i4.s 0x28
0x21ee  ldstr    aCreatesystemus// "CreateSystemUserInConfigDatabase"
0x21f3  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x21f8  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x21fd  unbox.any [mscorlib]System.Guid
0x2202  stloc.3
0x2203  br.s     loc_2252
0x2205  ldloc.2
0x2206  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x220b  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x2210  ldc.i4.1
0x2211  bne.un.s loc_2252
0x2213  ldloc.2
0x2214  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x2219  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x221e  stloc.s  4
0x2220  br.s     loc_2239
0x2222  ldloca.s 4
0x2224  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x2229  ldstr    aId// "Id"
0x222e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2233  unbox.any [mscorlib]System.Guid
0x2238  stloc.3
0x2239  ldloca.s 4
0x223b  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x2240  brtrue.s loc_2222
0x2242  leave.s  loc_2252
0x2244  ldloca.s 4
0x2246  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x224c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2251  endfinally
0x2252  ldloc.3
0x2253  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2258  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x225d  brfalse  loc_231C
0x2262  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2267  stloc.s  5
0x2269  ldloc.s  5
0x226b  ldstr    aCrmuserid// "CrmUserId"
0x2270  ldarg.2
0x2271  box      [mscorlib]System.Guid
0x2276  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x227b  ldloc.0
0x227c  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x2281  ldc.i4.1
0x2282  newarr   [mscorlib]System.String
0x2287  dup
0x2288  ldc.i4.0
0x2289  ldstr    aId// "Id"
0x228e  stelem.ref
0x228f  ldc.i4.1
0x2290  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x2295  dup
0x2296  ldc.i4.0
0x2297  ldloc.s  5
0x2299  stelem.ref
0x229a  ldc.i4.s 0x37
0x229c  ldstr    aCreatesystemus// "CreateSystemUserInConfigDatabase"
0x22a1  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x22a6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x22ab  stloc.s  6
0x22ad  ldloc.s  6
0x22af  brfalse.s loc_22C8
0x22b1  ldloc.s  6
0x22b3  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x22b8  brfalse.s loc_22C8
0x22ba  ldloc.s  6
0x22bc  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x22c1  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x22c6  brtrue.s loc_231C
0x22c8  ldloc.s  5
0x22ca  ldstr    aOrganizationid_0// "OrganizationId"
0x22cf  ldarg.0
0x22d0  box      [mscorlib]System.Guid
0x22d5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x22da  ldloc.s  5
0x22dc  ldstr    aUserid// "UserId"
0x22e1  ldloc.3
0x22e2  box      [mscorlib]System.Guid
0x22e7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x22ec  ldloc.s  5
0x22ee  ldstr    aId// "Id"
0x22f3  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x22f8  box      [mscorlib]System.Guid
0x22fd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2302  ldloc.0
0x2303  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x2308  ldloc.s  5
0x230a  ldc.i4.s 0x3F
0x230c  ldstr    aCreatesystemus// "CreateSystemUserInConfigDatabase"
0x2311  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x2316  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x231b  pop
0x231c  leave.s  loc_2328
0x231e  ldloc.0
0x231f  brfalse.s loc_2327
0x2321  ldloc.0
0x2322  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2327  endfinally
0x2328  ret
```
