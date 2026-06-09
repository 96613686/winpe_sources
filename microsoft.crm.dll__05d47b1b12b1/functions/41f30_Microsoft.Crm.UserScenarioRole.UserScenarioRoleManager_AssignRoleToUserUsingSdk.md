# Microsoft.Crm.UserScenarioRole.UserScenarioRoleManager::AssignRoleToUserUsingSdk

- ea: `0x41f30`
- end: `0x41fe5`
- name: `Microsoft.Crm.UserScenarioRole.UserScenarioRoleManager::AssignRoleToUserUsingSdk`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x41ed0`

## callees

- `0x41a80`
- `0x41e50`
- `0x41f30`
- `0x41ff0`

## string_xrefs

- `0x41f45`: `RoleTemplateId:`
- `0x41f53`: `RoleTemplateId:`

## pseudocode

```c

```

## disassembly

```asm
0x41f30  ldarg.1
0x41f31  ldloca.s 0
0x41f33  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x41f38  brfalse.s loc_41F44
0x41f3a  ldarg.0
0x41f3b  ldloc.0
0x41f3c  ldarg.2
0x41f3d  ldarg.3
0x41f3e  call     void Microsoft.Crm.UserScenarioRole.UserScenarioRoleManager::AssignRoleIdToUserUsingSdk(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid roleId, valuetype [mscorlib]System.Guid crmUserId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdk)
0x41f43  ret
0x41f44  ldarg.1
0x41f45  ldstr    aRoletemplateid_0// "RoleTemplateId:"
0x41f4a  ldc.i4.5
0x41f4b  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x41f50  brfalse.s loc_41F7B
0x41f52  ldarg.1
0x41f53  ldstr    aRoletemplateid_0// "RoleTemplateId:"
0x41f58  call     instance int32 [mscorlib]System.String::get_Length()
0x41f5d  callvirt instance string [mscorlib]System.String::Substring(int32)
0x41f62  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x41f67  stloc.2
0x41f68  ldarg.0
0x41f69  ldloc.2
0x41f6a  ldarg.3
0x41f6b  call     valuetype [mscorlib]System.Guid Microsoft.Crm.UserScenarioRole.UserScenarioRoleManager::GetRoleIdFromRoleTemplateId(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid roleTemplateId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdk)
0x41f70  stloc.0
0x41f71  ldarg.0
0x41f72  ldloc.0
0x41f73  ldarg.2
0x41f74  ldarg.3
0x41f75  call     void Microsoft.Crm.UserScenarioRole.UserScenarioRoleManager::AssignRoleIdToUserUsingSdk(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid roleId, valuetype [mscorlib]System.Guid crmUserId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdk)
0x41f7a  ret
0x41f7b  ldarg.1
0x41f7c  ldloca.s 1
0x41f7e  call     T0x2B00003A
0x41f83  brfalse.s loc_41FB6
0x41f85  ldloc.1
0x41f86  ldarg.0
0x41f87  ldarg.3
0x41f88  ldc.i4.0
0x41f89  call     valuetype [mscorlib]System.Guid[] Microsoft.Crm.UserScenarioRole.UserScenarioRoleManager::GetSystemRoleIds(int32 userScenarioRole, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdk, [opt] bool verifyRoleIdExists)
0x41f8e  stloc.3
0x41f8f  ldc.i4.0
0x41f90  stloc.s  4
0x41f92  br.s     loc_41FAE
0x41f94  ldloc.3
0x41f95  ldloc.s  4
0x41f97  ldelem   [mscorlib]System.Guid
0x41f9c  stloc.s  5
0x41f9e  ldarg.0
0x41f9f  ldloc.s  5
0x41fa1  ldarg.2
0x41fa2  ldarg.3
0x41fa3  call     void Microsoft.Crm.UserScenarioRole.UserScenarioRoleManager::AssignRoleIdToUserUsingSdk(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid roleId, valuetype [mscorlib]System.Guid crmUserId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdk)
0x41fa8  ldloc.s  4
0x41faa  ldc.i4.1
0x41fab  add
0x41fac  stloc.s  4
0x41fae  ldloc.s  4
0x41fb0  ldloc.3
0x41fb1  ldlen
0x41fb2  conv.i4
0x41fb3  blt.s    loc_41F94
0x41fb5  ret
0x41fb6  ldarg.1
0x41fb7  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x41fbc  ldarg.0
0x41fbd  ldc.i4.6
0x41fbe  ldstr    aUserscenarioro// "UserScenarioRoleManager: Unable to pars"...
0x41fc3  ldc.i4.3
0x41fc4  newarr   [mscorlib]System.Object
0x41fc9  dup
0x41fca  ldc.i4.0
0x41fcb  ldarg.1
0x41fcc  stelem.ref
0x41fcd  dup
0x41fce  ldc.i4.1
0x41fcf  ldarg.2
0x41fd0  box      [mscorlib]System.Guid
0x41fd5  stelem.ref
0x41fd6  dup
0x41fd7  ldc.i4.2
0x41fd8  ldarg.0
0x41fd9  box      [mscorlib]System.Guid
0x41fde  stelem.ref
0x41fdf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x41fe4  ret
```
