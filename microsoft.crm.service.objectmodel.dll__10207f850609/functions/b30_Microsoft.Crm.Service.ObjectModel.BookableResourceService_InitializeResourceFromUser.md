# Microsoft.Crm.Service.ObjectModel.BookableResourceService::InitializeResourceFromUser

- ea: `0xb30`
- end: `0xc7c`
- name: `Microsoft.Crm.Service.ObjectModel.BookableResourceService::InitializeResourceFromUser`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xaa0`

## callees

- `0xb30`

## pseudocode

```c

```

## disassembly

```asm
0xb30  ldarg.1
0xb31  ldstr    aUserid// "userid"
0xb36  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0xb3b  brtrue   loc_C7B
0xb40  ldstr    aSystemuser// "SystemUser"
0xb45  ldarg.2
0xb46  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xb4b  stloc.0
0xb4c  ldloc.0
0xb4d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xb52  ldstr    aCalendarid// "calendarid"
0xb57  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xb5c  ldloc.0
0xb5d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xb62  ldstr    aFullname// "fullname"
0xb67  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xb6c  ldarg.1
0xb6d  ldstr    aUserid// "userid"
0xb72  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xb77  unbox.any [mscorlib]System.Guid
0xb7c  ldstr    aSystemuser// "SystemUser"
0xb81  ldarg.2
0xb82  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb87  stloc.1
0xb88  ldarg.0
0xb89  ldloc.1
0xb8a  ldloc.0
0xb8b  ldarg.2
0xb8c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xb91  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SystemUser
0xb96  stloc.2
0xb97  ldarg.1
0xb98  ldstr    aCalendarid// "calendarid"
0xb9d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0xba2  brfalse.s loc_BC7
0xba4  ldloc.2
0xba5  ldstr    aCalendarid// "calendarid"
0xbaa  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0xbaf  brtrue.s loc_BC7
0xbb1  ldarg.1
0xbb2  ldstr    aCalendarid// "calendarid"
0xbb7  ldloc.2
0xbb8  ldstr    aCalendarid// "calendarid"
0xbbd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xbc2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xbc7  ldarg.1
0xbc8  ldstr    aName// "name"
0xbcd  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0xbd2  brfalse.s loc_BEA
0xbd4  ldarg.1
0xbd5  ldstr    aName// "name"
0xbda  ldloc.2
0xbdb  ldstr    aFullname// "fullname"
0xbe0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xbe5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xbea  ldstr    aUsersettings// "UserSettings"
0xbef  ldarg.2
0xbf0  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xbf5  stloc.0
0xbf6  ldloc.0
0xbf7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xbfc  ldstr    aTimezonecode// "timezonecode"
0xc01  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xc06  ldarg.1
0xc07  ldstr    aUserid// "userid"
0xc0c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xc11  unbox.any [mscorlib]System.Guid
0xc16  ldstr    aUsersettings// "UserSettings"
0xc1b  ldarg.2
0xc1c  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc21  stloc.1
0xc22  ldarg.0
0xc23  ldloc.1
0xc24  ldloc.0
0xc25  ldarg.2
0xc26  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xc2b  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.UserSettings
0xc30  stloc.3
0xc31  ldloc.3
0xc32  ldstr    aTimezonecode// "timezonecode"
0xc37  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0xc3c  brtrue.s loc_C63
0xc3e  ldarg.1
0xc3f  ldstr    aTimezone// "timezone"
0xc44  ldloc.3
0xc45  ldstr    aTimezonecode// "timezonecode"
0xc4a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xc4f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc54  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0xc59  box      [mscorlib]System.Int32
0xc5e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xc63  ldarg.1
0xc64  ldstr    aContactid// "contactid"
0xc69  ldnull
0xc6a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xc6f  ldarg.1
0xc70  ldstr    aAccountid// "accountid"
0xc75  ldnull
0xc76  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xc7b  ret
```
