# Microsoft.Crm.Authentication.UserManagementFactory::RetrieveUserInOrganization

- ea: `0x11760`
- end: `0x1184c`
- name: `Microsoft.Crm.Authentication.UserManagementFactory::RetrieveUserInOrganization`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x10e20`

## callees

- `0x11760`
- `0x11bd0`
- `0x13b10`
- `0x13eb0`
- `0x18520`
- `0x18540`
- `0x18800`
- `0x1ae30`
- `0x58f50`

## string_xrefs

- `0x117d6`: `activedirectoryguid`
- `0x11761`: `systemUserService`

## pseudocode

```c

```

## disassembly

```asm
0x11760  ldarg.3
0x11761  ldstr    aSystemuserserv// "systemUserService"
0x11766  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1176b  ldarg.s  4
0x1176d  ldstr    aContext// "context"
0x11772  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x11777  ldarg.2
0x11778  ldstr    aUserinformatio// "userInformation"
0x1177d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x11782  ldstr    aSystemuser_0// "SystemUser"
0x11787  ldarg.s  4
0x11789  newobj   instance void Microsoft.Crm.Query.EntityExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x1178e  stloc.0
0x1178f  ldarg.1
0x11790  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11795  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1179a  brfalse.s loc_117B4
0x1179c  ldloc.0
0x1179d  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x117a2  ldstr    aSystemuserid_0// "systemuserid"
0x117a7  ldc.i4.1
0x117a8  ldarg.1
0x117a9  box      [mscorlib]System.Guid
0x117ae  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x117b3  pop
0x117b4  ldarg.2
0x117b5  call     class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.ActiveDirectoryUserInformation Microsoft.Crm.Authentication.UserManagementFactory::GetActiveDirectoryInformation(class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation userInformation)
0x117ba  stloc.1
0x117bb  ldloc.1
0x117bc  brfalse.s loc_117EF
0x117be  ldloc.1
0x117bf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::get_ActiveDirectoryId()
0x117c4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x117c9  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x117ce  brfalse.s loc_117EF
0x117d0  ldloc.0
0x117d1  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x117d6  ldstr    aActivedirector// "activedirectoryguid"
0x117db  ldc.i4.0
0x117dc  ldloc.1
0x117dd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::get_ActiveDirectoryId()
0x117e2  box      [mscorlib]System.Guid
0x117e7  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x117ec  pop
0x117ed  br.s     loc_11807
0x117ef  ldloc.0
0x117f0  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x117f5  ldstr    aDomainname// "domainname"
0x117fa  ldc.i4.0
0x117fb  ldarg.2
0x117fc  callvirt instance string [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_UniqueName()
0x11801  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x11806  pop
0x11807  ldloc.0
0x11808  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1180d  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x11812  ldloc.0
0x11813  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x11818  ldstr    aDomainname// "domainname"
0x1181d  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x11822  ldloc.0
0x11823  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x11828  ldstr    aWindowsliveid// "windowsliveid"
0x1182d  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x11832  ldloc.0
0x11833  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x11838  ldstr    aInternalemaila// "internalemailaddress"
0x1183d  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x11842  ldarg.3
0x11843  ldloc.0
0x11844  ldarg.s  4
0x11846  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class Microsoft.Crm.Query.EntityExpression entityExpression, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1184b  ret
```
