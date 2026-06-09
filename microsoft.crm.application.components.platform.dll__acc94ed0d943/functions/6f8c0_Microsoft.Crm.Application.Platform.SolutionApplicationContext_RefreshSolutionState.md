# Microsoft.Crm.Application.Platform.SolutionApplicationContext::RefreshSolutionState

- ea: `0x6f8c0`
- end: `0x6fac3`
- name: `Microsoft.Crm.Application.Platform.SolutionApplicationContext::RefreshSolutionState`
- size: `515`
- prototype: ``
- caller_count: `9`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6f840`
- `0x6f860`
- `0x6f880`
- `0x6f8a0`
- `0x6fb80`
- `0x6fba0`
- `0x6fc20`
- `0x6fc70`
- `0x6fc90`

## callees

- `0xe920`
- `0x2fb90`
- `0x2fbc0`
- `0x30e70`
- `0x59710`
- `0x59800`
- `0x5be20`
- `0x5be50`
- `0x5be60`
- `0x6f8c0`
- `0x6fd20`

## string_xrefs

- `0x6f93d`: `configurationpageid`
- `0x6f9af`: `configurationpageid`
- `0x6f9bd`: `configurationpageid`

## pseudocode

```c

```

## disassembly

```asm
0x6f8c0  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadSolution()
0x6f8c5  ldc.i4.2
0x6f8c6  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6f8cb  call     bool Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition pd, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth privilegeDepth, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6f8d0  brfalse.s loc_6F8E4
0x6f8d2  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadPublisher()
0x6f8d7  ldc.i4.2
0x6f8d8  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6f8dd  call     bool Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition pd, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth privilegeDepth, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6f8e2  brtrue.s loc_6F8E5
0x6f8e4  ret
0x6f8e5  ldarg.0
0x6f8e6  ldfld    string Microsoft.Crm.Application.Platform.SolutionApplicationContext::_solutionId
0x6f8eb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6f8f0  brtrue.s loc_6F901
0x6f8f2  ldloca.s 0
0x6f8f4  ldarg.0
0x6f8f5  ldfld    string Microsoft.Crm.Application.Platform.SolutionApplicationContext::_solutionId
0x6f8fa  call     instance void [mscorlib]System.Guid::.ctor(string)
0x6f8ff  br.s     loc_6F907
0x6f901  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x6f906  stloc.0
0x6f907  ldstr    aSolution_0// "solution"
0x6f90c  ldloc.0
0x6f90d  ldc.i4.7
0x6f90e  newarr   [mscorlib]System.String
0x6f913  dup
0x6f914  ldc.i4.0
0x6f915  ldstr    aFriendlyname// "friendlyname"
0x6f91a  stelem.ref
0x6f91b  dup
0x6f91c  ldc.i4.1
0x6f91d  ldstr    aUniquename// "uniquename"
0x6f922  stelem.ref
0x6f923  dup
0x6f924  ldc.i4.2
0x6f925  ldstr    aIsmanaged// "ismanaged"
0x6f92a  stelem.ref
0x6f92b  dup
0x6f92c  ldc.i4.3
0x6f92d  ldstr    aPublisherid// "publisherid"
0x6f932  stelem.ref
0x6f933  dup
0x6f934  ldc.i4.4
0x6f935  ldstr    aVersion// "version"
0x6f93a  stelem.ref
0x6f93b  dup
0x6f93c  ldc.i4.5
0x6f93d  ldstr    aConfigurationp// "configurationpageid"
0x6f942  stelem.ref
0x6f943  dup
0x6f944  ldc.i4.6
0x6f945  ldstr    aParentsolution// "parentsolutionid"
0x6f94a  stelem.ref
0x6f94b  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6f950  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.DataSource::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, string[] columns, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6f955  stloc.1
0x6f956  ldarg.0
0x6f957  ldloc.1
0x6f958  ldstr    aUniquename// "uniquename"
0x6f95d  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x6f962  isinst   [mscorlib]System.String
0x6f967  stfld    string Microsoft.Crm.Application.Platform.SolutionApplicationContext::_solutionUniqueName
0x6f96c  ldarg.0
0x6f96d  ldloc.1
0x6f96e  ldstr    aFriendlyname// "friendlyname"
0x6f973  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x6f978  isinst   [mscorlib]System.String
0x6f97d  stfld    string Microsoft.Crm.Application.Platform.SolutionApplicationContext::_solutionFriendlyName
0x6f982  ldarg.0
0x6f983  ldloc.1
0x6f984  ldstr    aIsmanaged// "ismanaged"
0x6f989  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x6f98e  unbox.any [mscorlib]System.Boolean
0x6f993  stfld    bool Microsoft.Crm.Application.Platform.SolutionApplicationContext::_isManaged
0x6f998  ldarg.0
0x6f999  ldloc.1
0x6f99a  ldstr    aVersion// "version"
0x6f99f  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x6f9a4  isinst   [mscorlib]System.String
0x6f9a9  stfld    string Microsoft.Crm.Application.Platform.SolutionApplicationContext::_solutionVersion
0x6f9ae  ldloc.1
0x6f9af  ldstr    aConfigurationp// "configurationpageid"
0x6f9b4  callvirt instance bool Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string name)
0x6f9b9  brfalse.s loc_6F9E0
0x6f9bb  ldarg.0
0x6f9bc  ldloc.1
0x6f9bd  ldstr    aConfigurationp// "configurationpageid"
0x6f9c2  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x6f9c7  castclass Microsoft.Crm.Application.Types.LookupValue
0x6f9cc  callvirt instance string Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x6f9d1  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6f9d6  call     string Microsoft.Crm.Application.Platform.SolutionApplicationContext::GetConfigurationPathById(valuetype [mscorlib]System.Guid configurationPageId)
0x6f9db  stfld    string Microsoft.Crm.Application.Platform.SolutionApplicationContext::_configurationpagepath
0x6f9e0  ldloc.1
0x6f9e1  ldstr    aParentsolution// "parentsolutionid"
0x6f9e6  callvirt instance bool Microsoft.Crm.Application.Platform.EntityBase::HasAttributeAndNotNull(string name)
0x6f9eb  brfalse.s loc_6F9F4
0x6f9ed  ldarg.0
0x6f9ee  ldc.i4.1
0x6f9ef  stfld    bool Microsoft.Crm.Application.Platform.SolutionApplicationContext::_isPatch
0x6f9f4  ldstr    aSolution_0// "solution"
0x6f9f9  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x6f9fe  stloc.2
0x6f9ff  ldloc.2
0x6fa00  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x6fa05  ldstr    aSolutionid_0// "solutionid"
0x6fa0a  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x6fa0f  ldloc.2
0x6fa10  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6fa15  ldstr    aParentsolution// "parentsolutionid"
0x6fa1a  ldc.i4.0
0x6fa1b  ldloc.0
0x6fa1c  box      [mscorlib]System.Guid
0x6fa21  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6fa26  ldarg.0
0x6fa27  ldloc.2
0x6fa28  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6fa2d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x6fa32  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x6fa37  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6fa3c  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x6fa41  ldc.i4.0
0x6fa42  cgt
0x6fa44  stfld    bool Microsoft.Crm.Application.Platform.SolutionApplicationContext::_isParent
0x6fa49  ldloca.s 3
0x6fa4b  ldloc.1
0x6fa4c  ldstr    aPublisherid// "publisherid"
0x6fa51  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x6fa56  castclass Microsoft.Crm.Application.Types.LookupValue
0x6fa5b  callvirt instance string Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x6fa60  call     instance void [mscorlib]System.Guid::.ctor(string)
0x6fa65  ldstr    aPublisher// "publisher"
0x6fa6a  ldloc.3
0x6fa6b  ldc.i4.2
0x6fa6c  newarr   [mscorlib]System.String
0x6fa71  dup
0x6fa72  ldc.i4.0
0x6fa73  ldstr    aCustomizationp// "customizationprefix"
0x6fa78  stelem.ref
0x6fa79  dup
0x6fa7a  ldc.i4.1
0x6fa7b  ldstr    aCustomizationo// "customizationoptionvalueprefix"
0x6fa80  stelem.ref
0x6fa81  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6fa86  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.DataSource::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, string[] columns, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6fa8b  stloc.1
0x6fa8c  ldarg.0
0x6fa8d  ldloc.1
0x6fa8e  ldstr    aCustomizationp// "customizationprefix"
0x6fa93  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x6fa98  isinst   [mscorlib]System.String
0x6fa9d  ldstr    asc_A93D6// "_"
0x6faa2  call     string [mscorlib]System.String::Concat(string, string)
0x6faa7  stfld    string Microsoft.Crm.Application.Platform.SolutionApplicationContext::_publisherIdPrefix
0x6faac  ldarg.0
0x6faad  ldloc.1
0x6faae  ldstr    aCustomizationo// "customizationoptionvalueprefix"
0x6fab3  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x6fab8  unbox.any [mscorlib]System.Int32
0x6fabd  stfld    int32 Microsoft.Crm.Application.Platform.SolutionApplicationContext::_publisherIdOptionValuePrefix
0x6fac2  ret
```
