# Microsoft.Crm.Asynchronous.EventOperation::GetStepConfiguration

- ea: `0x2b40`
- end: `0x2bc8`
- name: `Microsoft.Crm.Asynchronous.EventOperation::GetStepConfiguration`
- size: `136`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2db0`
- `0x32d0`

## callees

- `0x2b40`

## string_xrefs

- `0x2b46`: `StepConfigurationOverride`
- `0x2b5d`: `Invalid configuration`
- `0x2b9c`: `serviceendpoint`

## pseudocode

```c

```

## disassembly

```asm
0x2b40  ldarg.0
0x2b41  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_SharedVariables()
0x2b46  ldstr    aStepconfigurat// "StepConfigurationOverride"
0x2b4b  ldloca.s 0
0x2b4d  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::TryGetValue(var<u1>, !!T0)
0x2b52  brfalse.s loc_2B6E
0x2b54  ldloc.0
0x2b55  isinst   [mscorlib]System.String
0x2b5a  ldnull
0x2b5b  cgt.un
0x2b5d  ldstr    aInvalidConfigu// "Invalid configuration"
0x2b62  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2b67  ldloc.0
0x2b68  castclass [mscorlib]System.String
0x2b6d  ret
0x2b6e  ldarg.0
0x2b6f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_OrganizationId()
0x2b74  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x2b79  stloc.1
0x2b7a  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.StepDescriptionCache [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.StepDescriptionCache::get_Instance()
0x2b7f  ldarg.0
0x2b80  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_OwningExtension()
0x2b85  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x2b8a  ldloc.1
0x2b8b  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.StepDescription>::LookupEntry(void, var<u1>)
0x2b90  stloc.2
0x2b91  ldloc.2
0x2b92  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.StepDescription::get_EventHandler()
0x2b97  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x2b9c  ldstr    aServiceendpoin// "serviceendpoint"
0x2ba1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ba6  brtrue.s loc_2BAF
0x2ba8  ldloc.2
0x2ba9  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.StepDescription::get_Configuration()
0x2bae  ret
0x2baf  ldloc.2
0x2bb0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.StepDescription::get_EventHandler()
0x2bb5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x2bba  stloc.3
0x2bbb  ldloca.s 3
0x2bbd  ldstr    aB// "B"
0x2bc2  call     instance string [mscorlib]System.Guid::ToString(string)
0x2bc7  ret
```
