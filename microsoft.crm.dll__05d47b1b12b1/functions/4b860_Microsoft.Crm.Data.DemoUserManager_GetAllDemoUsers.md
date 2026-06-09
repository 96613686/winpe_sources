# Microsoft.Crm.Data.DemoUserManager::GetAllDemoUsers

- ea: `0x4b860`
- end: `0x4b8c4`
- name: `Microsoft.Crm.Data.DemoUserManager::GetAllDemoUsers`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4b8d0`

## callees

- `0x50b40`

## string_xrefs

- `0x4b883`: `crmdemo.dynamics.com`
- `0x4b876`: `select CreatedOn,DomainName,SystemUserId from SystemUserBase where DomainName like '%@{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x4b860  newobj   instance void <>c__DisplayClass6_0::.ctor()
0x4b865  stloc.0
0x4b866  ldloc.0
0x4b867  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Data.DemoUserInfo>::.ctor()
0x4b86c  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Data.DemoUserInfo> <>c__DisplayClass6_0::userInfo
0x4b871  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4b876  ldstr    aSelectCreatedo// "select CreatedOn,DomainName,SystemUserI"...
0x4b87b  ldc.i4.1
0x4b87c  newarr   [mscorlib]System.Object
0x4b881  dup
0x4b882  ldc.i4.0
0x4b883  ldstr    aCrmdemoDynamic// "crmdemo.dynamics.com"
0x4b888  stelem.ref
0x4b889  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4b88e  ldc.i4.1
0x4b88f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x4b894  stloc.1
0x4b895  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::DefaultInstance
0x4b89a  ldarg.1
0x4b89b  ldc.i4.0
0x4b89c  ldc.i4.0
0x4b89d  ldc.i4.0
0x4b89e  ldnull
0x4b89f  ldc.i4.0
0x4b8a0  ldc.i4.0
0x4b8a1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::Get(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ConnectionAccessType, int32, string, bool, int32)
0x4b8a6  ldloc.1
0x4b8a7  ldloc.0
0x4b8a8  ldftn    instance void <>c__DisplayClass6_0::<GetAllDemoUsers>b__0(class [System.Data]System.Data.IDataReader sqlDataReader)
0x4b8ae  newobj   instance void class [mscorlib]System.Action`1<class [System.Data]System.Data.IDataReader>::.ctor(object, native int)
0x4b8b3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess::ExecuteReaderAction(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, class [mscorlib]System.Action`1<class [System.Data]System.Data.IDataReader>)
0x4b8b8  ldloc.0
0x4b8b9  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Data.DemoUserInfo> <>c__DisplayClass6_0::userInfo
0x4b8be  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Data.DemoUserInfo>::ToArray()
0x4b8c3  ret
```
