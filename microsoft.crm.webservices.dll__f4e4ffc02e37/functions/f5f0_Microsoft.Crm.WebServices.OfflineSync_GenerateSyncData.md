# Microsoft.Crm.WebServices.OfflineSync::GenerateSyncData

- ea: `0xf5f0`
- end: `0xf763`
- name: `Microsoft.Crm.WebServices.OfflineSync::GenerateSyncData`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xf490`

## callees

- `0xf560`
- `0xf5f0`

## string_xrefs

- `0xf5f7`: `CRM_Server_InstallDir`
- `0xf6b4`: `Exception during BCP file generation {0}.{3} Error code:  {1}.{3}. Stack Trace Info:{3} {2} `
- `0xf706`: `Exception during BCP file generation. Details: {0}`
- `0xf72c`: `GenerateSyncData() completed with hResult={0} for bcpFile={1} with {2} rows`

## pseudocode

```c

```

## disassembly

```asm
0xf5f0  ldarg.0
0xf5f1  ldarg.1
0xf5f2  call     instance void Microsoft.Crm.WebServices.OfflineSync::ValidateParameters(class [System.Web]System.Web.HttpContext context)
0xf5f7  ldstr    aCrmServerInsta// "CRM_Server_InstallDir"
0xf5fc  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0xf601  castclass [mscorlib]System.String
0xf606  stloc.0
0xf607  ldarg.0
0xf608  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf60d  ldstr    a012Bin// "{0}\\{1}\\{2}.bin"
0xf612  ldc.i4.3
0xf613  newarr   [mscorlib]System.Object
0xf618  dup
0xf619  ldc.i4.0
0xf61a  ldloc.0
0xf61b  stelem.ref
0xf61c  dup
0xf61d  ldc.i4.1
0xf61e  ldstr    aServerOfflined// "Server\\OfflineData"
0xf623  stelem.ref
0xf624  dup
0xf625  ldc.i4.2
0xf626  ldarg.0
0xf627  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.WebServices.OfflineSync::subscriptionId
0xf62c  box      [mscorlib]System.Guid
0xf631  stelem.ref
0xf632  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf637  stfld    string Microsoft.Crm.WebServices.OfflineSync::bcpFilePath
0xf63c  ldarg.2
0xf63d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0xf642  ldc.i4.0
0xf643  ldc.i4.0
0xf644  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xf649  stloc.1
0xf64a  ldloc.1
0xf64b  ldarg.2
0xf64c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_UserId()
0xf651  ldc.i4.0
0xf652  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0xf657  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SubscriptionService::.ctor()
0xf65c  stloc.2
0xf65d  ldarg.0
0xf65e  ldloc.2
0xf65f  ldarg.0
0xf660  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.WebServices.OfflineSync::subscriptionId
0xf665  ldarg.0
0xf666  ldfld    string Microsoft.Crm.WebServices.OfflineSync::entityName
0xf66b  ldarg.0
0xf66c  ldfld    valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SyncAction Microsoft.Crm.WebServices.OfflineSync::syncAction
0xf671  ldarg.0
0xf672  ldfld    int32 Microsoft.Crm.WebServices.OfflineSync::batchSize
0xf677  ldarg.0
0xf678  ldfld    string Microsoft.Crm.WebServices.OfflineSync::bcpFilePath
0xf67d  ldloc.1
0xf67e  callvirt instance int64 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SubscriptionService::GenerateSyncData(valuetype [mscorlib]System.Guid, string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SyncAction, int32, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf683  stfld    int64 Microsoft.Crm.WebServices.OfflineSync::rowCount
0xf688  ldloc.1
0xf689  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0xf68e  leave.s  loc_F699
0xf690  pop
0xf691  ldloc.1
0xf692  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0xf697  rethrow
0xf699  leave.s  loc_F6A5
0xf69b  ldloc.1
0xf69c  brfalse.s loc_F6A4
0xf69e  ldloc.1
0xf69f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf6a4  endfinally
0xf6a5  leave    loc_F762
0xf6aa  stloc.3
0xf6ab  ldloc.3
0xf6ac  ldarg.2
0xf6ad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0xf6b2  ldc.i4.s 0x14
0xf6b4  ldstr    aExceptionDurin_0// "Exception during BCP file generation {0"...
0xf6b9  ldc.i4.4
0xf6ba  newarr   [mscorlib]System.Object
0xf6bf  dup
0xf6c0  ldc.i4.0
0xf6c1  ldloc.3
0xf6c2  callvirt instance string [mscorlib]System.Exception::get_Message()
0xf6c7  stelem.ref
0xf6c8  dup
0xf6c9  ldc.i4.1
0xf6ca  ldloc.3
0xf6cb  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0xf6d0  box      [mscorlib]System.Int32
0xf6d5  stelem.ref
0xf6d6  dup
0xf6d7  ldc.i4.2
0xf6d8  ldloc.3
0xf6d9  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0xf6de  stelem.ref
0xf6df  dup
0xf6e0  ldc.i4.3
0xf6e1  call     string [mscorlib]System.Environment::get_NewLine()
0xf6e6  stelem.ref
0xf6e7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf6ec  ldarg.0
0xf6ed  ldloc.3
0xf6ee  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0xf6f3  stfld    int32 Microsoft.Crm.WebServices.OfflineSync::hResult
0xf6f8  leave.s  loc_F762
0xf6fa  stloc.s  4
0xf6fc  ldloc.s  4
0xf6fe  ldarg.2
0xf6ff  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0xf704  ldc.i4.s 0x14
0xf706  ldstr    aExceptionDurin_1// "Exception during BCP file generation. D"...
0xf70b  ldc.i4.1
0xf70c  newarr   [mscorlib]System.Object
0xf711  dup
0xf712  ldc.i4.0
0xf713  ldloc.s  4
0xf715  stelem.ref
0xf716  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf71b  ldarg.0
0xf71c  ldc.i4.1
0xf71d  stfld    int32 Microsoft.Crm.WebServices.OfflineSync::hResult
0xf722  leave.s  loc_F762
0xf724  ldarg.2
0xf725  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0xf72a  ldc.i4.s 0x14
0xf72c  ldstr    aGeneratesyncda// "GenerateSyncData() completed with hResu"...
0xf731  ldc.i4.3
0xf732  newarr   [mscorlib]System.Object
0xf737  dup
0xf738  ldc.i4.0
0xf739  ldarg.0
0xf73a  ldfld    int32 Microsoft.Crm.WebServices.OfflineSync::hResult
0xf73f  box      [mscorlib]System.Int32
0xf744  stelem.ref
0xf745  dup
0xf746  ldc.i4.1
0xf747  ldarg.0
0xf748  ldfld    string Microsoft.Crm.WebServices.OfflineSync::bcpFilePath
0xf74d  stelem.ref
0xf74e  dup
0xf74f  ldc.i4.2
0xf750  ldarg.0
0xf751  ldfld    int64 Microsoft.Crm.WebServices.OfflineSync::rowCount
0xf756  box      [mscorlib]System.Int64
0xf75b  stelem.ref
0xf75c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf761  endfinally
0xf762  ret
```
