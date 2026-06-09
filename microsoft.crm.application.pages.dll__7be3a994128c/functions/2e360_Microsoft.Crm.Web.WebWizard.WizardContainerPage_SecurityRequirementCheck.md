# Microsoft.Crm.Web.WebWizard.WizardContainerPage::SecurityRequirementCheck

- ea: `0x2e360`
- end: `0x2e4e8`
- name: `Microsoft.Crm.Web.WebWizard.WizardContainerPage::SecurityRequirementCheck`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x2e1b0`

## callees

- `0x2e360`

## string_xrefs

- `0x2e370`: `privilegename`
- `0x2e403`: `privilegename`
- `0x2e3a6`: `wizardaccessprivilege`
- `0x2e45a`: `Privilege with id `
- `0x2e4b3`: `Privilege with id `

## pseudocode

```c

```

## disassembly

```asm
0x2e360  ldc.i4.2
0x2e361  newarr   [mscorlib]System.String
0x2e366  dup
0x2e367  ldc.i4.0
0x2e368  ldstr    aEntityname// "entityname"
0x2e36d  stelem.ref
0x2e36e  dup
0x2e36f  ldc.i4.1
0x2e370  ldstr    aPrivilegename// "privilegename"
0x2e375  stelem.ref
0x2e376  stloc.0
0x2e377  ldstr    aWebwizardid// "webwizardid"
0x2e37c  ldc.i4.0
0x2e37d  ldc.i4.1
0x2e37e  newarr   [mscorlib]System.Object
0x2e383  dup
0x2e384  ldc.i4.0
0x2e385  ldarg.1
0x2e386  box      [mscorlib]System.Guid
0x2e38b  stelem.ref
0x2e38c  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x2e391  stloc.1
0x2e392  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x2e397  stloc.2
0x2e398  ldloc.2
0x2e399  ldc.i4.0
0x2e39a  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x2e39f  ldloc.2
0x2e3a0  ldloc.1
0x2e3a1  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x2e3a6  ldstr    aWizardaccesspr// "wizardaccessprivilege"
0x2e3ab  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x2e3b0  dup
0x2e3b1  ldloc.0
0x2e3b2  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x2e3b7  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x2e3bc  dup
0x2e3bd  ldloc.2
0x2e3be  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x2e3c3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2e3c8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2e3cd  stloc.3
0x2e3ce  ldloc.3
0x2e3cf  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x2e3d4  ldc.i4.0
0x2e3d5  ble      loc_2E4E7
0x2e3da  ldc.i4.0
0x2e3db  stloc.s  4
0x2e3dd  br       loc_2E4DA
0x2e3e2  ldloc.3
0x2e3e3  ldloc.s  4
0x2e3e5  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x2e3ea  ldstr    aEntityname// "entityname"
0x2e3ef  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x2e3f4  castclass [mscorlib]System.String
0x2e3f9  stloc.s  5
0x2e3fb  ldloc.3
0x2e3fc  ldloc.s  4
0x2e3fe  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x2e403  ldstr    aPrivilegename// "privilegename"
0x2e408  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x2e40d  castclass [mscorlib]System.String
0x2e412  stloc.s  6
0x2e414  ldloc.s  5
0x2e416  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e41b  brtrue.s loc_2E42B
0x2e41d  ldloc.s  5
0x2e41f  ldstr    aNone_0// "none"
0x2e424  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x2e429  brtrue.s loc_2E47B
0x2e42b  ldtoken  [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges
0x2e430  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e435  ldloc.s  6
0x2e437  ldc.i4.s 0x18
0x2e439  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x2e43e  ldnull
0x2e43f  ldnull
0x2e440  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x2e445  castclass [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition
0x2e44a  stloc.s  7
0x2e44c  ldloc.s  7
0x2e44e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2e453  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2e458  brtrue.s loc_2E4D4
0x2e45a  ldstr    aPrivilegeWithI// "Privilege with id "
0x2e45f  ldloc.s  7
0x2e461  ldfld    string [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition::guid
0x2e466  ldstr    aNotAvailableFo// " not available for this user"
0x2e46b  call     string [mscorlib]System.String::Concat(string, string, string)
0x2e470  ldc.i4   0x80040220
0x2e475  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2e47a  throw
0x2e47b  ldloc.s  5
0x2e47d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2e482  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2e487  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x2e48c  ldtoken  [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId
0x2e491  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e496  ldloc.s  6
0x2e498  ldc.i4.1
0x2e499  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x2e49e  unbox.any [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId
0x2e4a3  stloc.s  8
0x2e4a5  ldloc.s  8
0x2e4a7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2e4ac  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2e4b1  brtrue.s loc_2E4D4
0x2e4b3  ldstr    aPrivilegeWithI// "Privilege with id "
0x2e4b8  ldloc.s  8
0x2e4ba  box      [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId
0x2e4bf  ldstr    aNotAvailableFo// " not available for this user"
0x2e4c4  call     string [mscorlib]System.String::Concat(object, object, object)
0x2e4c9  ldc.i4   0x80040220
0x2e4ce  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2e4d3  throw
0x2e4d4  ldloc.s  4
0x2e4d6  ldc.i4.1
0x2e4d7  add
0x2e4d8  stloc.s  4
0x2e4da  ldloc.s  4
0x2e4dc  ldloc.3
0x2e4dd  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x2e4e2  blt      loc_2E3E2
0x2e4e7  ret
```
