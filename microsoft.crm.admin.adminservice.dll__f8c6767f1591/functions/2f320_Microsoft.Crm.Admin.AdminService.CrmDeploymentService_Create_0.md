# Microsoft.Crm.Admin.AdminService.CrmDeploymentService::Create_0

- ea: `0x2f320`
- end: `0x2f475`
- name: `Microsoft.Crm.Admin.AdminService.CrmDeploymentService::Create_0`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2f310`

## callees

- `0x2f320`
- `0x2f830`
- `0x30990`

## string_xrefs

- `0x2f3f7`: `Create`
- `0x2f3af`: `TraceDirectory`
- `0x2f3fc`: `D:\a\1\s\src\CrmLive\Admin\Deployment\CrmDeploymentService.cs`
- `0x2f42a`: `Created Deployment, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x2f320  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2f325  ldc.i4.s 0x14
0x2f327  ldstr    aCreatingDeploy// "Creating Deployment, Id=({0})"
0x2f32c  ldc.i4.1
0x2f32d  newarr   [mscorlib]System.Object
0x2f332  dup
0x2f333  ldc.i4.0
0x2f334  ldarg.1
0x2f335  box      [mscorlib]System.Guid
0x2f33a  stelem.ref
0x2f33b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f340  ldarg.1
0x2f341  ldstr    aDeploymentIden// "Deployment identifier"
0x2f346  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2f34b  ldarg.2
0x2f34c  ldstr    aDeploymentProp// "Deployment property bag"
0x2f351  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2f356  ldarg.2
0x2f357  ldstr    aId// "Id"
0x2f35c  ldarg.1
0x2f35d  box      [mscorlib]System.Guid
0x2f362  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2f367  ldarg.2
0x2f368  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddDefaults(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f36d  ldstr    aTraceenabled// "TraceEnabled"
0x2f372  ldc.i4.0
0x2f373  box      [mscorlib]System.Boolean
0x2f378  ldarg.2
0x2f379  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f37e  ldstr    aTracecallstack// "TraceCallStack"
0x2f383  ldc.i4.1
0x2f384  box      [mscorlib]System.Boolean
0x2f389  ldarg.2
0x2f38a  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f38f  ldstr    aTracecategorie// "TraceCategories"
0x2f394  ldstr    aError// "*:Error"
0x2f399  ldarg.2
0x2f39a  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f39f  ldstr    aTracefilesize// "TraceFileSize"
0x2f3a4  ldstr    a10// "10"
0x2f3a9  ldarg.2
0x2f3aa  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f3af  ldstr    aTracedirectory// "TraceDirectory"
0x2f3b4  ldstr    aCCrmdropLogs// "c:\\crmdrop\\logs"
0x2f3b9  ldarg.2
0x2f3ba  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f3bf  ldstr    aPaginglimit// "PagingLimit"
0x2f3c4  ldc.i4   0x1F4
0x2f3c9  box      [mscorlib]System.Int32
0x2f3ce  ldarg.2
0x2f3cf  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f3d4  ldstr    aSqmenabled// "SQMEnabled"
0x2f3d9  ldc.i4.0
0x2f3da  box      [mscorlib]System.Boolean
0x2f3df  ldarg.2
0x2f3e0  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f3e5  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x2f3ea  stloc.1
0x2f3eb  ldloc.1
0x2f3ec  ldstr    aDeployment// "Deployment"
0x2f3f1  ldarg.2
0x2f3f2  ldc.i4   0x229
0x2f3f7  ldstr    aCreate// "Create"
0x2f3fc  ldstr    aDA1SSrcCrmlive_58// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Deplo"...
0x2f401  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x2f406  unbox.any [mscorlib]System.Guid
0x2f40b  stloc.0
0x2f40c  leave.s  loc_2F418
0x2f40e  ldloc.1
0x2f40f  brfalse.s loc_2F417
0x2f411  ldloc.1
0x2f412  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f417  endfinally
0x2f418  ldloc.0
0x2f419  ldstr    aDeploymentIden// "Deployment identifier"
0x2f41e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2f423  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2f428  ldc.i4.s 0x14
0x2f42a  ldstr    aCreatedDeploym// "Created Deployment, Id=({0})"
0x2f42f  ldc.i4.1
0x2f430  newarr   [mscorlib]System.Object
0x2f435  dup
0x2f436  ldc.i4.0
0x2f437  ldarg.1
0x2f438  box      [mscorlib]System.Guid
0x2f43d  stelem.ref
0x2f43e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f443  ldloc.0
0x2f444  stloc.2
0x2f445  leave.s  loc_2F473
0x2f447  stloc.3
0x2f448  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2f44d  ldc.i4.s 0x14
0x2f44f  ldstr    aExceptionCreat_8// "Exception creating Deployment, Id=({0} "...
0x2f454  ldc.i4.2
0x2f455  newarr   [mscorlib]System.Object
0x2f45a  dup
0x2f45b  ldc.i4.0
0x2f45c  ldarg.1
0x2f45d  box      [mscorlib]System.Guid
0x2f462  stelem.ref
0x2f463  dup
0x2f464  ldc.i4.1
0x2f465  ldloc.3
0x2f466  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2f46b  stelem.ref
0x2f46c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f471  rethrow
0x2f473  ldloc.2
0x2f474  ret
```
