# Microsoft.Crm.Admin.AdminService.CrmOrganizationService::SetLastTaskStatus

- ea: `0x26b20`
- end: `0x26bc4`
- name: `Microsoft.Crm.Admin.AdminService.CrmOrganizationService::SetLastTaskStatus`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x15a00`

## callees

- `0x26b20`

## string_xrefs

- `0x26b5f`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`
- `0x26b32`: `LastTaskStatus`
- `0x26b5a`: `SetLastTaskStatus`
- `0x26b9e`: `Updated LastTaskStatus for Organization, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x26b20  ldarg.1
0x26b21  ldstr    aOrganizationId_0// "Organization ID"
0x26b26  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x26b2b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x26b30  stloc.0
0x26b31  ldloc.0
0x26b32  ldstr    aLasttaskstatus// "LastTaskStatus"
0x26b37  ldarg.2
0x26b38  box      [Microsoft.Crm.Core]Microsoft.Crm.OrganizationTaskStatus
0x26b3d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x26b42  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x26b47  stloc.1
0x26b48  ldloc.1
0x26b49  ldstr    aOrganization// "Organization"
0x26b4e  ldarg.1
0x26b4f  box      [mscorlib]System.Guid
0x26b54  ldloc.0
0x26b55  ldc.i4   0x2B9
0x26b5a  ldstr    aSetlasttasksta// "SetLastTaskStatus"
0x26b5f  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x26b64  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x26b69  brtrue.s loc_26B9B
0x26b6b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26b70  ldstr    aOrganiztionWit// "Organiztion with ID {0} does not exist."
0x26b75  ldc.i4.1
0x26b76  newarr   [mscorlib]System.Object
0x26b7b  dup
0x26b7c  ldc.i4.0
0x26b7d  ldarga.s 1
0x26b7f  constrained. [mscorlib]System.Guid
0x26b85  callvirt instance string [mscorlib]System.Object::ToString()
0x26b8a  stelem.ref
0x26b8b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26b90  ldc.i4   0x80040217
0x26b95  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x26b9a  throw
0x26b9b  ldarg.1
0x26b9c  ldc.i4.s 0x14
0x26b9e  ldstr    aUpdatedLasttas// "Updated LastTaskStatus for Organization"...
0x26ba3  ldc.i4.1
0x26ba4  newarr   [mscorlib]System.Object
0x26ba9  dup
0x26baa  ldc.i4.0
0x26bab  ldarg.1
0x26bac  box      [mscorlib]System.Guid
0x26bb1  stelem.ref
0x26bb2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x26bb7  leave.s  loc_26BC3
0x26bb9  ldloc.1
0x26bba  brfalse.s loc_26BC2
0x26bbc  ldloc.1
0x26bbd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26bc2  endfinally
0x26bc3  ret
```
