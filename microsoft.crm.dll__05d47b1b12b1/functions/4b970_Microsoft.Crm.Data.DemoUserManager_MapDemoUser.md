# Microsoft.Crm.Data.DemoUserManager::MapDemoUser

- ea: `0x4b970`
- end: `0x4b9fc`
- name: `Microsoft.Crm.Data.DemoUserManager::MapDemoUser`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4b790`
- `0x4b970`

## string_xrefs

- `0x4b983`: `UPDATE SystemUserBase SET DomainName=@NewUpn,WindowsLiveId=@NewUpn WHERE SystemUserId=@SystemUserId AND DomainName like @DemoUserLike`
- `0x4b9c4`: `%@crmdemo.dynamics.com`

## pseudocode

```c

```

## disassembly

```asm
0x4b970  ldarg.3
0x4b971  call     bool Microsoft.Crm.Data.DemoUserManager::IsDemoUserUpn(string upn)
0x4b976  brfalse.s loc_4B983
0x4b978  ldstr    aCannotUseMapde// "Cannot use MapDemoUser to map to anothe"...
0x4b97d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x4b982  throw
0x4b983  ldstr    aUpdateSystemus// "UPDATE SystemUserBase SET DomainName=@N"...
0x4b988  ldc.i4.1
0x4b989  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x4b98e  stloc.0
0x4b98f  ldloc.0
0x4b990  ldstr    aNewupn// "@NewUpn"
0x4b995  ldarg.3
0x4b996  ldloca.s 1
0x4b998  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x4b99e  ldloc.1
0x4b99f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x4b9a4  ldloc.0
0x4b9a5  ldstr    aSystemuserid_0// "@SystemUserId"
0x4b9aa  ldarg.2
0x4b9ab  box      [mscorlib]System.Guid
0x4b9b0  ldloca.s 1
0x4b9b2  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x4b9b8  ldloc.1
0x4b9b9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x4b9be  ldloc.0
0x4b9bf  ldstr    aDemouserlike// "@DemoUserLike"
0x4b9c4  ldstr    aCrmdemoDynamic_0// "%@crmdemo.dynamics.com"
0x4b9c9  ldloca.s 1
0x4b9cb  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x4b9d1  ldloc.1
0x4b9d2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x4b9d7  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::DefaultInstance
0x4b9dc  ldarg.1
0x4b9dd  ldc.i4.0
0x4b9de  ldc.i4.0
0x4b9df  ldc.i4.0
0x4b9e0  ldnull
0x4b9e1  ldc.i4.0
0x4b9e2  ldc.i4.0
0x4b9e3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::Get(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ConnectionAccessType, int32, string, bool, int32)
0x4b9e8  ldloc.0
0x4b9e9  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess::ExecuteNonQuery(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo)
0x4b9ee  brtrue.s loc_4B9FB
0x4b9f0  ldstr    aMapdemouserWas// "MapDemoUser was unsuccessful. This coul"...
0x4b9f5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x4b9fa  throw
0x4b9fb  ret
```
