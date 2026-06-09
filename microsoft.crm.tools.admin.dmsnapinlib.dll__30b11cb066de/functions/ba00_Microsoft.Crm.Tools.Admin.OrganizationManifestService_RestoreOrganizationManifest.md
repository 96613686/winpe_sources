# Microsoft.Crm.Tools.Admin.OrganizationManifestService::RestoreOrganizationManifest

- ea: `0xba00`
- end: `0xbb07`
- name: `Microsoft.Crm.Tools.Admin.OrganizationManifestService::RestoreOrganizationManifest`
- size: `263`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xba00`

## string_xrefs

- `0xba01`: `manifestPath`
- `0xba85`: `ConfigDB state restore for Organization: {0} Failed with Exception: {1}`
- `0xbac4`: `Undo of ConfigDB state restore for Organization: {0} Failed with Exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0xba00  ldarg.1
0xba01  ldstr    aManifestpath// "manifestPath"
0xba06  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xba0b  ldarg.2
0xba0c  ldstr    aOrguniquename// "orgUniqueName"
0xba11  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xba16  ldarg.1
0xba17  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationManifest [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationManifestFactory::CreateFromFile(string)
0xba1c  dup
0xba1d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationManifest::GetOrganizationId()
0xba22  stloc.0
0xba23  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xba28  dup
0xba29  ldstr    aOrganization// "Organization"
0xba2e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xba33  pop
0xba34  dup
0xba35  ldstr    aOrganizationfe// "OrganizationFeatureMap"
0xba3a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xba3f  pop
0xba40  dup
0xba41  ldstr    aSystemuser// "SystemUser"
0xba46  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xba4b  pop
0xba4c  dup
0xba4d  ldstr    aSystemuserauth// "SystemUserAuthentication"
0xba52  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xba57  pop
0xba58  ldtoken  [mscorlib]System.String
0xba5d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xba62  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0xba67  castclass string[]
0xba6c  stloc.1
0xba6d  ldloc.1
0xba6e  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ImportOrganizationManifestAction::.ctor(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationManifest, string[])
0xba73  stloc.2
0xba74  ldloc.2
0xba75  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ImportOrganizationManifestAction::Do()
0xba7a  leave    loc_BB06
0xba7f  stloc.3
0xba80  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xba85  ldstr    aConfigdbStateR// "ConfigDB state restore for Organization"...
0xba8a  ldc.i4.2
0xba8b  newarr   [mscorlib]System.Object
0xba90  dup
0xba91  ldc.i4.0
0xba92  ldloc.0
0xba93  box      [mscorlib]System.Guid
0xba98  stelem.ref
0xba99  dup
0xba9a  ldc.i4.1
0xba9b  ldloc.3
0xba9c  stelem.ref
0xba9d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbaa2  stloc.s  4
0xbaa4  ldloc.3
0xbaa5  ldloc.0
0xbaa6  ldc.i4.s 0x3B
0xbaa8  ldloc.s  4
0xbaaa  ldc.i4.0
0xbaab  newarr   [mscorlib]System.Object
0xbab0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xbab5  ldloc.2
0xbab6  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ImportOrganizationManifestAction::Undo()
0xbabb  leave.s  loc_BAF8
0xbabd  stloc.s  5
0xbabf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbac4  ldstr    aUndoOfConfigdb// "Undo of ConfigDB state restore for Orga"...
0xbac9  ldc.i4.2
0xbaca  newarr   [mscorlib]System.Object
0xbacf  dup
0xbad0  ldc.i4.0
0xbad1  ldloc.0
0xbad2  box      [mscorlib]System.Guid
0xbad7  stelem.ref
0xbad8  dup
0xbad9  ldc.i4.1
0xbada  ldloc.s  5
0xbadc  stelem.ref
0xbadd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbae2  stloc.s  6
0xbae4  ldloc.s  5
0xbae6  ldloc.0
0xbae7  ldc.i4.s 0x3B
0xbae9  ldloc.s  6
0xbaeb  ldc.i4.0
0xbaec  newarr   [mscorlib]System.Object
0xbaf1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xbaf6  leave.s  loc_BAF8
0xbaf8  ldloc.s  4
0xbafa  ldloc.3
0xbafb  ldc.i4   0x80048532
0xbb00  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception, int32)
0xbb05  throw
0xbb06  ret
```
