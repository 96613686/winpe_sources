# Microsoft.Crm.Asynchronous.EventOperation::GetPluginTypeId

- ea: `0x2c60`
- end: `0x2d1a`
- name: `Microsoft.Crm.Asynchronous.EventOperation::GetPluginTypeId`
- size: `186`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x2c30`
- `0x2d80`
- `0x2db0`

## callees

- `0x2c60`

## string_xrefs

- `0x2d00`: `serviceendpoint`
- `0x2c66`: `PluginTypeIdOverride`
- `0x2c7d`: `Invalid plugin type id`
- `0x2cc5`: `AsyncOperationCommand.GetPluginType: loading id '{0}', type '{1}', pluginTypeId:{2}`

## pseudocode

```c

```

## disassembly

```asm
0x2c60  ldarg.1
0x2c61  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_SharedVariables()
0x2c66  ldstr    aPlugintypeidov// "PluginTypeIdOverride"
0x2c6b  ldloca.s 0
0x2c6d  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::TryGetValue(var<u1>, !!T0)
0x2c72  brfalse.s loc_2C8E
0x2c74  ldloc.0
0x2c75  isinst   [mscorlib]System.Guid
0x2c7a  ldnull
0x2c7b  cgt.un
0x2c7d  ldstr    aInvalidPluginT// "Invalid plugin type id"
0x2c82  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2c87  ldloc.0
0x2c88  unbox.any [mscorlib]System.Guid
0x2c8d  ret
0x2c8e  ldarg.1
0x2c8f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_OrganizationId()
0x2c94  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x2c99  stloc.1
0x2c9a  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.StepDescriptionCache [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.StepDescriptionCache::get_Instance()
0x2c9f  ldarg.1
0x2ca0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_OwningExtension()
0x2ca5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x2caa  ldloc.1
0x2cab  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.StepDescription>::LookupEntry(void, var<u1>)
0x2cb0  stloc.2
0x2cb1  ldloc.2
0x2cb2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.StepDescription::get_EventHandler()
0x2cb7  stloc.3
0x2cb8  ldarg.0
0x2cb9  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x2cbe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x2cc3  ldc.i4.s 0x15
0x2cc5  ldstr    aAsyncoperation// "AsyncOperationCommand.GetPluginType: lo"...
0x2cca  ldc.i4.3
0x2ccb  newarr   [mscorlib]System.Object
0x2cd0  dup
0x2cd1  ldc.i4.0
0x2cd2  ldloc.3
0x2cd3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x2cd8  box      [mscorlib]System.Guid
0x2cdd  stelem.ref
0x2cde  dup
0x2cdf  ldc.i4.1
0x2ce0  ldloc.3
0x2ce1  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x2ce6  stelem.ref
0x2ce7  dup
0x2ce8  ldc.i4.2
0x2ce9  ldloc.2
0x2cea  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.StepDescription::get_PluginTypeId()
0x2cef  box      [mscorlib]System.Guid
0x2cf4  stelem.ref
0x2cf5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2cfa  ldloc.3
0x2cfb  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x2d00  ldstr    aServiceendpoin// "serviceendpoint"
0x2d05  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d0a  brtrue.s loc_2D13
0x2d0c  ldloc.3
0x2d0d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x2d12  ret
0x2d13  ldloc.2
0x2d14  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.StepDescription::get_PluginTypeId()
0x2d19  ret
```
