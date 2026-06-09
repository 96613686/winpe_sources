# Microsoft.Crm.Asynchronous.EventOperation::GetStepSecureConfiguration

- ea: `0x2bd0`
- end: `0x2c26`
- name: `Microsoft.Crm.Asynchronous.EventOperation::GetStepSecureConfiguration`
- size: `86`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2db0`
- `0x32d0`

## callees

- `0x2bd0`

## string_xrefs

- `0x2bd6`: `SecureStepConfigurationOverride`
- `0x2bed`: `Invalid secure configuration`

## pseudocode

```c

```

## disassembly

```asm
0x2bd0  ldarg.0
0x2bd1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_SharedVariables()
0x2bd6  ldstr    aSecurestepconf// "SecureStepConfigurationOverride"
0x2bdb  ldloca.s 0
0x2bdd  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::TryGetValue(var<u1>, !!T0)
0x2be2  brfalse.s loc_2BFE
0x2be4  ldloc.0
0x2be5  isinst   [mscorlib]System.String
0x2bea  ldnull
0x2beb  cgt.un
0x2bed  ldstr    aInvalidSecureC// "Invalid secure configuration"
0x2bf2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2bf7  ldloc.0
0x2bf8  castclass [mscorlib]System.String
0x2bfd  ret
0x2bfe  ldarg.0
0x2bff  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_OrganizationId()
0x2c04  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x2c09  stloc.1
0x2c0a  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.StepDescriptionCache [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.StepDescriptionCache::get_Instance()
0x2c0f  ldarg.0
0x2c10  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_OwningExtension()
0x2c15  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x2c1a  ldloc.1
0x2c1b  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.StepDescription>::LookupEntry(void, var<u1>)
0x2c20  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.StepDescription::get_SecureConfiguration()
0x2c25  ret
```
