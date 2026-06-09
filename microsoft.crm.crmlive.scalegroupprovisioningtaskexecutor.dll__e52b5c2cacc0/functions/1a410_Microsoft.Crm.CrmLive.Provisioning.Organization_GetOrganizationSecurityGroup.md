# Microsoft.Crm.CrmLive.Provisioning.Organization::GetOrganizationSecurityGroup

- ea: `0x1a410`
- end: `0x1a4f2`
- name: `Microsoft.Crm.CrmLive.Provisioning.Organization::GetOrganizationSecurityGroup`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x10290`
- `0x33450`

## callees

- `0x1a410`

## string_xrefs

- `0x1a459`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Organization.cs`
- `0x1a43f`: `SecurityGroup`
- `0x1a4ca`: `SecurityGroup`
- `0x1a454`: `GetOrganizationSecurityGroup`

## pseudocode

```c

```

## disassembly

```asm
0x1a410  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a415  stloc.0
0x1a416  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1a41b  stloc.1
0x1a41c  ldloc.1
0x1a41d  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x1a422  ldarg.0
0x1a423  box      [mscorlib]System.Guid
0x1a428  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1a42d  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x1a432  ldstr    aOrganizationli// "OrganizationLifecycle"
0x1a437  ldc.i4.1
0x1a438  newarr   [mscorlib]System.String
0x1a43d  dup
0x1a43e  ldc.i4.0
0x1a43f  ldstr    aSecuritygroup// "SecurityGroup"
0x1a444  stelem.ref
0x1a445  ldc.i4.1
0x1a446  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x1a44b  dup
0x1a44c  ldc.i4.0
0x1a44d  ldloc.1
0x1a44e  stelem.ref
0x1a44f  ldc.i4   0x5BA
0x1a454  ldstr    aGetorganizatio_1// "GetOrganizationSecurityGroup"
0x1a459  ldstr    aDDbsShDccm2110_30// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x1a45e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x1a463  stloc.2
0x1a464  ldloc.2
0x1a465  brfalse  loc_1A4F0
0x1a46a  ldloc.2
0x1a46b  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x1a470  ldc.i4.0
0x1a471  ble.s    loc_1A4F0
0x1a473  ldloc.2
0x1a474  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> <>c::<>9__42_0
0x1a479  dup
0x1a47a  brtrue.s loc_1A493
0x1a47c  pop
0x1a47d  ldsfld   class <>c <>c::<>9
0x1a482  ldftn    instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag <>c::<GetOrganizationSecurityGroup>b__42_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> keyValuePair)
0x1a488  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::.ctor(object, native int)
0x1a48d  dup
0x1a48e  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> <>c::<>9__42_0
0x1a493  call     T0x2B000092
0x1a498  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, bool> <>c::<>9__42_1
0x1a49d  dup
0x1a49e  brtrue.s loc_1A4B7
0x1a4a0  pop
0x1a4a1  ldsfld   class <>c <>c::<>9
0x1a4a6  ldftn    instance bool <>c::<GetOrganizationSecurityGroup>b__42_1(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag pBag)
0x1a4ac  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, bool>::.ctor(object, native int)
0x1a4b1  dup
0x1a4b2  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, bool> <>c::<>9__42_1
0x1a4b7  call     T0x2B00004B
0x1a4bc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x1a4c1  stloc.3
0x1a4c2  br.s     loc_1A4DC
0x1a4c4  ldloc.3
0x1a4c5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x1a4ca  ldstr    aSecuritygroup// "SecurityGroup"
0x1a4cf  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1a4d4  unbox.any [mscorlib]System.Guid
0x1a4d9  stloc.0
0x1a4da  leave.s  loc_1A4F0
0x1a4dc  ldloc.3
0x1a4dd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1a4e2  brtrue.s loc_1A4C4
0x1a4e4  leave.s  loc_1A4F0
0x1a4e6  ldloc.3
0x1a4e7  brfalse.s loc_1A4EF
0x1a4e9  ldloc.3
0x1a4ea  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a4ef  endfinally
0x1a4f0  ldloc.0
0x1a4f1  ret
```
