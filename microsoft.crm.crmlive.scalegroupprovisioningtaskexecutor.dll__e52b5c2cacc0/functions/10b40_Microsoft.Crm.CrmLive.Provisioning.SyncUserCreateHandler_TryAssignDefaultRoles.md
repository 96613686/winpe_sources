# Microsoft.Crm.CrmLive.Provisioning.SyncUserCreateHandler::TryAssignDefaultRoles

- ea: `0x10b40`
- end: `0x10c7c`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncUserCreateHandler::TryAssignDefaultRoles`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10a80`

## callees

- `0xff10`
- `0xff50`
- `0xfff0`
- `0x10b40`
- `0x10c80`
- `0x1c190`
- `0x1c3b0`
- `0x1e500`
- `0x2e900`
- `0x2eb50`

## string_xrefs

- `0x10b9f`: `RoleTemplateId:`
- `0x10bb2`: `RoleTemplateId:`

## pseudocode

```c

```

## disassembly

```asm
0x10b40  ldarg.1
0x10b41  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_OrganizationId()
0x10b46  call     string Microsoft.Crm.CrmLive.Provisioning.SyncUserCreateHandler::GetDefaultSecurityRolesSetting(valuetype [mscorlib]System.Guid orgId)
0x10b4b  stloc.0
0x10b4c  ldloc.0
0x10b4d  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x10b52  brtrue   loc_10C7B
0x10b57  ldloc.0
0x10b58  ldc.i4.1
0x10b59  newarr   [mscorlib]System.Char
0x10b5e  dup
0x10b5f  ldc.i4.0
0x10b60  ldc.i4.s 0x2C
0x10b62  stelem.i2
0x10b63  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x10b68  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__3_0
0x10b6d  dup
0x10b6e  brtrue.s loc_10B87
0x10b70  pop
0x10b71  ldsfld   class <>c <>c::<>9
0x10b76  ldftn    instance string <>c::<TryAssignDefaultRoles>b__3_0(string x)
0x10b7c  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x10b81  dup
0x10b82  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__3_0
0x10b87  call     T0x2B000066
0x10b8c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x10b91  stloc.1
0x10b92  br       loc_10C64
0x10b97  ldloc.1
0x10b98  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x10b9d  stloc.2
0x10b9e  ldloc.2
0x10b9f  ldstr    aRoletemplateid_1// "RoleTemplateId:"
0x10ba4  ldc.i4.5
0x10ba5  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x10baa  brfalse.s loc_10BDD
0x10bac  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x10bb1  ldloc.2
0x10bb2  ldstr    aRoletemplateid_1// "RoleTemplateId:"
0x10bb7  call     instance int32 [mscorlib]System.String::get_Length()
0x10bbc  callvirt instance string [mscorlib]System.String::Substring(int32)
0x10bc1  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x10bc6  stloc.s  4
0x10bc8  ldarg.1
0x10bc9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_OrganizationId()
0x10bce  ldloc.s  4
0x10bd0  ldarg.1
0x10bd1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_CrmUserId()
0x10bd6  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::AssignRoleToUserUsingTemplateId(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid roleTemplateId, valuetype [mscorlib]System.Guid crmUserId)
0x10bdb  br.s     loc_10C31
0x10bdd  ldloc.2
0x10bde  ldstr    aRoleid_1// "RoleId:"
0x10be3  ldc.i4.5
0x10be4  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x10be9  brfalse.s loc_10C15
0x10beb  ldloc.2
0x10bec  ldstr    aRoleid_1// "RoleId:"
0x10bf1  call     instance int32 [mscorlib]System.String::get_Length()
0x10bf6  callvirt instance string [mscorlib]System.String::Substring(int32)
0x10bfb  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x10c00  stloc.3
0x10c01  ldarg.1
0x10c02  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_OrganizationId()
0x10c07  ldloc.3
0x10c08  ldarg.1
0x10c09  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_CrmUserId()
0x10c0e  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::AssignRoleToUserUsingSdk(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid roleId, valuetype [mscorlib]System.Guid crmUserId)
0x10c13  br.s     loc_10C31
0x10c15  ldloc.2
0x10c16  ldloca.s 3
0x10c18  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x10c1d  brfalse.s loc_10C31
0x10c1f  ldarg.1
0x10c20  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_OrganizationId()
0x10c25  ldloc.3
0x10c26  ldarg.1
0x10c27  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_CrmUserId()
0x10c2c  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::AssignRoleToUserUsingSdk(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid roleId, valuetype [mscorlib]System.Guid crmUserId)
0x10c31  leave.s  loc_10C64
0x10c33  stloc.s  5
0x10c35  call     class Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentEventSource Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentEventSource::get_Instance()
0x10c3a  ldarg.1
0x10c3b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_CrmUserId()
0x10c40  ldarg.1
0x10c41  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_DirectoryObjectId()
0x10c46  ldarg.1
0x10c47  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_OrganizationId()
0x10c4c  ldstr    aTryassigndefau// "TryAssignDefaultRoles"
0x10c51  ldloc.s  5
0x10c53  callvirt instance string [mscorlib]System.Object::ToString()
0x10c58  call     string [mscorlib]System.String::Concat(string, string)
0x10c5d  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentEventSource::RoleAssignmentFailedForDefaultRoles(valuetype [mscorlib]System.Guid crmUserId, valuetype [mscorlib]System.Guid objectId, valuetype [mscorlib]System.Guid organizationId, string exception)
0x10c62  leave.s  loc_10C64
0x10c64  ldloc.1
0x10c65  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10c6a  brtrue   loc_10B97
0x10c6f  leave.s  loc_10C7B
0x10c71  ldloc.1
0x10c72  brfalse.s loc_10C7A
0x10c74  ldloc.1
0x10c75  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10c7a  endfinally
0x10c7b  ret
```
