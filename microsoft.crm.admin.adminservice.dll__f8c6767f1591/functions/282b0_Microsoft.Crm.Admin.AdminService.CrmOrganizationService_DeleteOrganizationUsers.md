# Microsoft.Crm.Admin.AdminService.CrmOrganizationService::DeleteOrganizationUsers

- ea: `0x282b0`
- end: `0x2837f`
- name: `Microsoft.Crm.Admin.AdminService.CrmOrganizationService::DeleteOrganizationUsers`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x25e50`

## callees

- `0x282b0`
- `0x34c90`

## string_xrefs

- `0x28302`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`
- `0x282b3`: `DeleteOrganizationUsers`
- `0x282fd`: `DeleteOrganizationUsers`
- `0x28362`: `Exception in DeleteOrganizationUsers {0}`

## pseudocode

```c

```

## disassembly

```asm
0x282b0  ldarg.0
0x282b1  ldc.i4.s 0x14
0x282b3  ldstr    aDeleteorganiza_4// "DeleteOrganizationUsers"
0x282b8  ldc.i4.0
0x282b9  newarr   [mscorlib]System.Object
0x282be  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x282c3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x282c8  stloc.0
0x282c9  ldloc.0
0x282ca  ldstr    aOrganizationid_0// "OrganizationId"
0x282cf  ldarg.0
0x282d0  box      [mscorlib]System.Guid
0x282d5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x282da  ldarg.1
0x282db  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x282e0  ldc.i4.1
0x282e1  newarr   [mscorlib]System.String
0x282e6  dup
0x282e7  ldc.i4.0
0x282e8  ldstr    aCrmuserid// "CrmUserId"
0x282ed  stelem.ref
0x282ee  ldc.i4.1
0x282ef  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x282f4  dup
0x282f5  ldc.i4.0
0x282f6  ldloc.0
0x282f7  stelem.ref
0x282f8  ldc.i4   0x6F2
0x282fd  ldstr    aDeleteorganiza_4// "DeleteOrganizationUsers"
0x28302  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x28307  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x2830c  stloc.1
0x2830d  ldloc.1
0x2830e  brfalse.s loc_28359
0x28310  ldloc.1
0x28311  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x28316  stloc.2
0x28317  br.s     loc_28340
0x28319  ldloca.s 2
0x2831b  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x28320  stloc.s  4
0x28322  ldloca.s 4
0x28324  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x28329  ldstr    aCrmuserid// "CrmUserId"
0x2832e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x28333  unbox.any [mscorlib]System.Guid
0x28338  stloc.3
0x28339  ldarg.0
0x2833a  ldloc.3
0x2833b  call     void Microsoft.Crm.Admin.AdminService.UserService::RemovePrincipalFromConfigDB(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid crmId)
0x28340  ldloca.s 2
0x28342  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x28347  brtrue.s loc_28319
0x28349  leave.s  loc_28359
0x2834b  ldloca.s 2
0x2834d  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x28353  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x28358  endfinally
0x28359  leave.s  loc_2837E
0x2835b  stloc.s  5
0x2835d  ldloc.s  5
0x2835f  ldarg.0
0x28360  ldc.i4.s 0x14
0x28362  ldstr    aExceptionInDel_2// "Exception in DeleteOrganizationUsers {0"...
0x28367  ldc.i4.1
0x28368  newarr   [mscorlib]System.Object
0x2836d  dup
0x2836e  ldc.i4.0
0x2836f  ldloc.s  5
0x28371  callvirt instance string [mscorlib]System.Exception::get_Message()
0x28376  stelem.ref
0x28377  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2837c  rethrow
0x2837e  ret
```
