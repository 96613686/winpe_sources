# Microsoft.Crm.Tools.Admin.ImportUserMapper::CompleteUserMapping

- ea: `0x12410`
- end: `0x12485`
- name: `Microsoft.Crm.Tools.Admin.ImportUserMapper::CompleteUserMapping`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x123c0`

## callees

- `0x122a0`
- `0x122b0`
- `0x12410`
- `0x13650`
- `0x13770`

## string_xrefs

- `0x12410`: `CompleteUserMapping for {0} running`
- `0x12460`: `CompleteUserMapping for {0} completed`

## pseudocode

```c

```

## disassembly

```asm
0x12410  ldstr    aCompleteuserma// "CompleteUserMapping for {0} running"
0x12415  ldc.i4.1
0x12416  newarr   [mscorlib]System.Object
0x1241b  dup
0x1241c  ldc.i4.0
0x1241d  ldarg.0
0x1241e  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x12423  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x12428  stelem.ref
0x12429  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x1242e  ldnull
0x1242f  stloc.0
0x12430  ldarg.0
0x12431  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> Microsoft.Crm.Tools.Admin.ImportUserMapper::_invalidUserMaps
0x12436  ldloc.0
0x12437  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.MapUsersResult Microsoft.Crm.Tools.Admin.ADUserMappingHelper::ClearUsersForInvalidMapping(class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> usersMapInvalid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.MapUsersResult mapResult)
0x1243c  stloc.0
0x1243d  ldloc.0
0x1243e  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.MapUsersResult Microsoft.Crm.Tools.Admin.ADUserMappingHelper::BuildAndReturnMapResult(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.MapUsersResult mapResult)
0x12443  stloc.0
0x12444  ldarg.0
0x12445  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.MapUsersResult Microsoft.Crm.Tools.Admin.ImportUserMapper::get_MappingResult()
0x1244a  brfalse.s loc_12459
0x1244c  ldarg.0
0x1244d  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.MapUsersResult Microsoft.Crm.Tools.Admin.ImportUserMapper::get_MappingResult()
0x12452  callvirt instance valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.MapResultType [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.MapUsersResult::get_Result()
0x12457  brtrue.s loc_12460
0x12459  ldarg.0
0x1245a  ldloc.0
0x1245b  call     instance void Microsoft.Crm.Tools.Admin.ImportUserMapper::set_MappingResult(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.MapUsersResult value)
0x12460  ldstr    aCompleteuserma_0// "CompleteUserMapping for {0} completed"
0x12465  ldc.i4.1
0x12466  newarr   [mscorlib]System.Object
0x1246b  dup
0x1246c  ldc.i4.0
0x1246d  ldarg.0
0x1246e  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x12473  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x12478  stelem.ref
0x12479  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x1247e  ldarg.0
0x1247f  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.MapUsersResult Microsoft.Crm.Tools.Admin.ImportUserMapper::get_MappingResult()
0x12484  ret
```
