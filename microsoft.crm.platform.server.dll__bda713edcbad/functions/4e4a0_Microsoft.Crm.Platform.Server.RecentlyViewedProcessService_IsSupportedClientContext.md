# Microsoft.Crm.Platform.Server.RecentlyViewedProcessService::IsSupportedClientContext

- ea: `0x4e4a0`
- end: `0x4e61f`
- name: `Microsoft.Crm.Platform.Server.RecentlyViewedProcessService::IsSupportedClientContext`
- size: `383`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x4e2e0`
- `0x4e390`

## callees

- `0x4df40`
- `0x4e4a0`
- `0x66d80`
- `0x66f10`

## string_xrefs

- `0x4e594`: `ServiceDesk`
- `0x4e5d7`: `XRMServices/2011/Organization.svc`

## pseudocode

```c

```

## disassembly

```asm
0x4e4a0  ldarg.0
0x4e4a1  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.RecentlyViewedProcessService::context
0x4e4a6  brfalse  loc_4E61D
0x4e4ab  ldarg.0
0x4e4ac  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.RecentlyViewedProcessService::context
0x4e4b1  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x4e4b6  brfalse  loc_4E61D
0x4e4bb  ldarg.0
0x4e4bc  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.RecentlyViewedProcessService::context
0x4e4c1  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x4e4c6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerOriginToken()
0x4e4cb  brfalse  loc_4E61D
0x4e4d0  ldarg.0
0x4e4d1  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.RecentlyViewedProcessService::context
0x4e4d6  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x4e4db  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerOriginToken()
0x4e4e0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::get_CallerOrigin()
0x4e4e5  isinst   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ApplicationOrigin
0x4e4ea  brfalse.s loc_4E4EE
0x4e4ec  ldc.i4.1
0x4e4ed  ret
0x4e4ee  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x4e4f3  brtrue.s loc_4E536
0x4e4f5  call     class [Microsoft.Crm.Core]Microsoft.Crm.IServerInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ServerInfoProvider::get_Instance()
0x4e4fa  brfalse.s loc_4E536
0x4e4fc  call     class [Microsoft.Crm.Core]Microsoft.Crm.IServerInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ServerInfoProvider::get_Instance()
0x4e501  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles [Microsoft.Crm.Core]Microsoft.Crm.IServerInfoProvider::GetServerRoles()
0x4e506  box      [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles
0x4e50b  ldc.i4.2
0x4e50c  box      [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles
0x4e511  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x4e516  brfalse.s loc_4E536
0x4e518  call     class [Microsoft.Crm.Core]Microsoft.Crm.IServerInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ServerInfoProvider::get_Instance()
0x4e51d  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles [Microsoft.Crm.Core]Microsoft.Crm.IServerInfoProvider::GetServerRoles()
0x4e522  box      [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles
0x4e527  ldc.i4.1
0x4e528  box      [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles
0x4e52d  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x4e532  brtrue.s loc_4E536
0x4e534  ldc.i4.0
0x4e535  ret
0x4e536  ldarg.0
0x4e537  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.RecentlyViewedProcessService::context
0x4e53c  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x4e541  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerOriginToken()
0x4e546  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::get_CallerOrigin()
0x4e54b  isinst   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.WebServiceApiOrigin
0x4e550  brtrue.s loc_4E571
0x4e552  ldarg.0
0x4e553  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.RecentlyViewedProcessService::context
0x4e558  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x4e55d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerOriginToken()
0x4e562  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::get_CallerOrigin()
0x4e567  isinst   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OData4Origin
0x4e56c  brfalse  loc_4E61D
0x4e571  call     string [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_CurrentClientType()
0x4e576  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4e57b  brtrue.s loc_4E5B5
0x4e57d  call     string [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_CurrentClientType()
0x4e582  ldstr    aMobileclient// "MobileClient"
0x4e587  ldc.i4.3
0x4e588  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x4e58d  brtrue.s loc_4E5B3
0x4e58f  call     string [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_CurrentClientType()
0x4e594  ldstr    aServicedesk// "ServiceDesk"
0x4e599  ldc.i4.3
0x4e59a  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x4e59f  brtrue.s loc_4E5B3
0x4e5a1  call     string [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_CurrentClientType()
0x4e5a6  ldstr    aUciclient// "UCIClient"
0x4e5ab  ldc.i4.3
0x4e5ac  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x4e5b1  brfalse.s loc_4E5B5
0x4e5b3  ldc.i4.1
0x4e5b4  ret
0x4e5b5  call     class [System.Web]System.Web.HttpRequestBase [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmHttpContext::get_Request()
0x4e5ba  brfalse.s loc_4E5E7
0x4e5bc  call     class [System.Web]System.Web.HttpRequestBase [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmHttpContext::get_Request()
0x4e5c1  callvirt instance string [System.Web]System.Web.HttpRequestBase::get_CurrentExecutionFilePath()
0x4e5c6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4e5cb  brtrue.s loc_4E5E7
0x4e5cd  call     class [System.Web]System.Web.HttpRequestBase [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmHttpContext::get_Request()
0x4e5d2  callvirt instance string [System.Web]System.Web.HttpRequestBase::get_CurrentExecutionFilePath()
0x4e5d7  ldstr    aXrmservices201// "XRMServices/2011/Organization.svc"
0x4e5dc  ldc.i4.3
0x4e5dd  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x4e5e2  ldc.i4.0
0x4e5e3  bge.s    loc_4E5E7
0x4e5e5  ldc.i4.1
0x4e5e6  ret
0x4e5e7  ldarg.0
0x4e5e8  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.RecentlyViewedProcessService::context
0x4e5ed  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x4e5f2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x4e5f7  brfalse.s loc_4E61D
0x4e5f9  ldstr    aNavigatetonext// "NavigateToNextEntity"
0x4e5fe  ldarg.0
0x4e5ff  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.RecentlyViewedProcessService::context
0x4e604  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x4e609  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x4e60e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x4e613  ldc.i4.3
0x4e614  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x4e619  brfalse.s loc_4E61D
0x4e61b  ldc.i4.1
0x4e61c  ret
0x4e61d  ldc.i4.0
0x4e61e  ret
```
