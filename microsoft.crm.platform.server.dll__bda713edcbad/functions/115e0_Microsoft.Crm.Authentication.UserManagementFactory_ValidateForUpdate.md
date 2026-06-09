# Microsoft.Crm.Authentication.UserManagementFactory::ValidateForUpdate

- ea: `0x115e0`
- end: `0x116c5`
- name: `Microsoft.Crm.Authentication.UserManagementFactory::ValidateForUpdate`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x115e0`
- `0x13b10`
- `0x18520`
- `0x18800`
- `0x56d40`

## string_xrefs

- `0x115ec`: `systemUserService`
- `0x11602`: `azureactivedirectoryobjectid`
- `0x11663`: `issyncwithdirectory`
- `0x11693`: `issyncwithdirectory`

## pseudocode

```c

```

## disassembly

```asm
0x115e0  ldarg.1
0x115e1  ldstr    aSystemuser// "systemUser"
0x115e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x115eb  ldarg.2
0x115ec  ldstr    aSystemuserserv// "systemUserService"
0x115f1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x115f6  ldarg.3
0x115f7  ldstr    aContext// "context"
0x115fc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x11601  ldarg.1
0x11602  ldstr    aAzureactivedir// "azureactivedirectoryobjectid"
0x11607  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1160c  brtrue.s loc_1161F
0x1160e  ldc.i4   0x80041D4F
0x11613  ldc.i4.0
0x11614  newarr   [mscorlib]System.Object
0x11619  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1161e  throw
0x1161f  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x11624  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x11629  ldc.i4.2
0x1162a  bne.un   loc_116C4
0x1162f  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x11634  ldarg.3
0x11635  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1163a  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x1163f  brfalse  loc_116C4
0x11644  ldarg.1
0x11645  ldstr    aIslicensed// "islicensed"
0x1164a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1164f  brtrue.s loc_11662
0x11651  ldc.i4   0x80041D4C
0x11656  ldc.i4.0
0x11657  newarr   [mscorlib]System.Object
0x1165c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x11661  throw
0x11662  ldarg.1
0x11663  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x11668  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1166d  brtrue.s loc_11680
0x1166f  ldc.i4   0x80041D4E
0x11674  ldc.i4.0
0x11675  newarr   [mscorlib]System.Object
0x1167a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1167f  throw
0x11680  ldarg.1
0x11681  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x11686  ldarg.3
0x11687  newobj   instance void Microsoft.Crm.Query.EntityExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x1168c  stloc.0
0x1168d  ldloc.0
0x1168e  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x11693  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x11698  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x1169d  ldarg.1
0x1169e  ldstr    aSystemuserid_0// "systemuserid"
0x116a3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x116a8  unbox.any [mscorlib]System.Guid
0x116ad  ldarg.1
0x116ae  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x116b3  ldarg.3
0x116b4  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x116b9  stloc.1
0x116ba  ldarg.2
0x116bb  ldloc.1
0x116bc  ldloc.0
0x116bd  ldarg.3
0x116be  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class Microsoft.Crm.Query.EntityExpression entityExpression, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x116c3  pop
0x116c4  ret
```
