# Microsoft.Crm.Application.WebServices.SystemCustomization.CustomControlDelete::Execute

- ea: `0x23e0`
- end: `0x250f`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.CustomControlDelete::Execute`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb0d0`

## callees

- `0x23e0`

## string_xrefs

- `0x2425`: `createdbyname`
- `0x24bc`: `SystemCustomization.CustomControlUtil.Messages.CannotDeleteSystemCustomControl`

## pseudocode

```c

```

## disassembly

```asm
0x23e0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x23e5  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionAdapter::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x23ea  ldarg.0
0x23eb  ldc.i4.s 0x42
0x23ed  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionAdapter::RetrieveDependentComponents(valuetype [mscorlib]System.Guid, int32)
0x23f2  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x23f7  ldc.i4.0
0x23f8  ble.s    loc_2414
0x23fa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x23ff  ldstr    aSystemcustomiz// "SystemCustomization.CustomControlUtil.M"...
0x2404  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2409  ldc.i4   0x8004F01F
0x240e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2413  throw
0x2414  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x2419  dup
0x241a  ldstr    aCustomcontroli// "customcontrolid"
0x241f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2424  dup
0x2425  ldstr    aCreatedbyname// "createdbyname"
0x242a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x242f  stloc.0
0x2430  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::.ctor()
0x2435  dup
0x2436  ldc.i4.0
0x2437  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x243c  dup
0x243d  ldc.i4.0
0x243e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x2443  stloc.1
0x2444  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<object>::.ctor()
0x2449  dup
0x244a  ldarg.0
0x244b  box      [mscorlib]System.Guid
0x2450  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0x2455  dup
0x2456  ldstr    aSystem// "system"
0x245b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0x2460  stloc.2
0x2461  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x2466  dup
0x2467  ldstr    aCustomcontroli// "customcontrolid"
0x246c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2471  stloc.3
0x2472  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2477  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x247c  ldc.i4.0
0x247d  ldc.i4.0
0x247e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x2483  stloc.s  4
0x2485  ldloc.s  4
0x2487  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x248c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x2491  ldc.i4.0
0x2492  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x2497  ldloc.3
0x2498  ldloc.0
0x2499  ldloc.1
0x249a  ldloc.2
0x249b  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<object>::ToArray()
0x24a0  ldloc.s  4
0x24a2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ConverterUtilities::GetCustomControls(class [mscorlib]System.Collections.Generic.List`1<string>, class [mscorlib]System.Collections.Generic.List`1<string>, class [mscorlib]System.Collections.Generic.List`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>, object[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x24a7  stloc.s  5
0x24a9  ldloc.s  5
0x24ab  brfalse.s loc_24D1
0x24ad  ldloc.s  5
0x24af  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x24b4  ldc.i4.0
0x24b5  ble.s    loc_24D1
0x24b7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24bc  ldstr    aSystemcustomiz_0// "SystemCustomization.CustomControlUtil.M"...
0x24c1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24c6  ldc.i4   0x8004F035
0x24cb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x24d0  throw
0x24d1  ldarg.0
0x24d2  ldstr    aCustomcontrol// "CustomControl"
0x24d7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24dc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x24e1  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x24e6  stloc.s  6
0x24e8  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CustomControlService::.ctor()
0x24ed  ldloc.s  6
0x24ef  ldloc.s  4
0x24f1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x24f6  leave.s  loc_2504
0x24f8  ldloc.s  4
0x24fa  brfalse.s loc_2503
0x24fc  ldloc.s  4
0x24fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2503  endfinally
0x2504  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2509  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::FlushMetadataCache(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x250e  ret
```
