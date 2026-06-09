# Microsoft.Crm.Admin.AdminService.CrmOrganizationService::InternalUpdate

- ea: `0x26420`
- end: `0x2657e`
- name: `Microsoft.Crm.Admin.AdminService.CrmOrganizationService::InternalUpdate`
- size: `350`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x26080`
- `0x26090`
- `0x260a0`

## callees

- `0x18790`
- `0x26420`
- `0x269f0`
- `0x285a0`

## string_xrefs

- `0x264ed`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`
- `0x26468`: `Update Organization, Id=({0})`
- `0x264fb`: `Update Organization, Id=({0})`
- `0x264e8`: `InternalUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x26420  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x26425  stloc.0
0x26426  ldarg.1
0x26427  ldstr    aOrganizationDa// "Organization data"
0x2642c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x26431  ldarg.1
0x26432  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x26437  ldstr    aId// "Id"
0x2643c  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x26441  brtrue.s loc_26453
0x26443  ldstr    aOrganizationda_7// "organizationData.Id"
0x26448  ldstr    aOrganizationId_3// "Organization identifier must be set"
0x2644d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string, string)
0x26452  throw
0x26453  ldarg.1
0x26454  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x26459  stloc.0
0x2645a  ldloc.0
0x2645b  ldstr    aOrganizationId_1// "Organization identifier"
0x26460  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x26465  ldloc.0
0x26466  ldc.i4.s 0x14
0x26468  ldstr    aUpdateOrganiza// "Update Organization, Id=({0})"
0x2646d  ldc.i4.1
0x2646e  newarr   [mscorlib]System.Object
0x26473  dup
0x26474  ldc.i4.0
0x26475  ldloc.0
0x26476  box      [mscorlib]System.Guid
0x2647b  stelem.ref
0x2647c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x26481  ldarg.2
0x26482  brfalse.s loc_264BB
0x26484  ldarg.0
0x26485  ldloc.0
0x26486  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState Microsoft.Crm.Admin.AdminService.CrmOrganizationService::GetState(valuetype [mscorlib]System.Guid organizationId)
0x2648b  stloc.1
0x2648c  ldc.i4.1
0x2648d  ldloc.1
0x2648e  bne.un.s loc_264BB
0x26490  ldc.i4   0x8004D237
0x26495  ldc.i4.3
0x26496  newarr   [mscorlib]System.Object
0x2649b  dup
0x2649c  ldc.i4.0
0x2649d  ldstr    aOrganization// "Organization"
0x264a2  stelem.ref
0x264a3  dup
0x264a4  ldc.i4.1
0x264a5  ldloc.0
0x264a6  box      [mscorlib]System.Guid
0x264ab  stelem.ref
0x264ac  dup
0x264ad  ldc.i4.2
0x264ae  ldloc.1
0x264af  box      [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState
0x264b4  stelem.ref
0x264b5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x264ba  throw
0x264bb  ldarg.1
0x264bc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x264c1  ldstr    aId// "Id"
0x264c6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Remove(string)
0x264cb  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x264d0  stloc.2
0x264d1  ldloc.2
0x264d2  ldstr    aOrganization// "Organization"
0x264d7  ldloc.0
0x264d8  box      [mscorlib]System.Guid
0x264dd  ldarg.1
0x264de  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x264e3  ldc.i4   0x1C1
0x264e8  ldstr    aInternalupdate// "InternalUpdate"
0x264ed  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x264f2  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x264f7  pop
0x264f8  ldloc.0
0x264f9  ldc.i4.s 0x14
0x264fb  ldstr    aUpdateOrganiza// "Update Organization, Id=({0})"
0x26500  ldc.i4.1
0x26501  newarr   [mscorlib]System.Object
0x26506  dup
0x26507  ldc.i4.0
0x26508  ldloc.0
0x26509  box      [mscorlib]System.Guid
0x2650e  stelem.ref
0x2650f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x26514  ldc.i4.s 0x1F
0x26516  ldloca.s 0
0x26518  ldstr    aB// "B"
0x2651d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26522  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x26527  ldloc.0
0x26528  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x2652d  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x26532  leave.s  loc_2653E
0x26534  ldloc.2
0x26535  brfalse.s loc_2653D
0x26537  ldloc.2
0x26538  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2653d  endfinally
0x2653e  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x26543  ldstr    aOrganization// "Organization"
0x26548  ldloc.0
0x26549  box      [mscorlib]System.Guid
0x2654e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Flush(string, object)
0x26553  leave.s  loc_2657D
0x26555  stloc.3
0x26556  ldloc.0
0x26557  ldc.i4.s 0x14
0x26559  ldstr    aExceptionUpdat_0// "Exception updating Organization, Id=({0"...
0x2655e  ldc.i4.2
0x2655f  newarr   [mscorlib]System.Object
0x26564  dup
0x26565  ldc.i4.0
0x26566  ldloc.0
0x26567  box      [mscorlib]System.Guid
0x2656c  stelem.ref
0x2656d  dup
0x2656e  ldc.i4.1
0x2656f  ldloc.3
0x26570  callvirt instance string [mscorlib]System.Exception::get_Message()
0x26575  stelem.ref
0x26576  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2657b  rethrow
0x2657d  ret
```
