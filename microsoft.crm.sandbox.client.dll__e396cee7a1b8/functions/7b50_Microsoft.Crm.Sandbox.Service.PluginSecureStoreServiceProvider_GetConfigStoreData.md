# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetConfigStoreData

- ea: `0x7b50`
- end: `0x7bed`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetConfigStoreData`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x96d0`

## string_xrefs

- `0x7b92`: `PluginSecureStoreServiceProvider.GetConfigStoreData - started. CallInfo {0}`
- `0x7bcd`: `PluginSecureStoreServiceProvider.GetConfigStoreData - successfully finished. CallInfo {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7b50  newobj   instance void <>c__DisplayClass14_0::.ctor()
0x7b55  stloc.0
0x7b56  ldloc.0
0x7b57  ldarg.0
0x7b58  stfld    class Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider <>c__DisplayClass14_0::<>4__this
0x7b5d  ldloc.0
0x7b5e  ldarg.3
0x7b5f  stfld    string <>c__DisplayClass14_0::keyName
0x7b64  ldarg.1
0x7b65  ldstr    aCallinfo// "callInfo"
0x7b6a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7b6f  ldarg.2
0x7b70  ldstr    aContext// "context"
0x7b75  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7b7a  ldloc.0
0x7b7b  ldfld    string <>c__DisplayClass14_0::keyName
0x7b80  ldstr    aKeyname// "keyName"
0x7b85  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7b8a  ldarg.2
0x7b8b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7b90  ldc.i4.s 0x1F
0x7b92  ldstr    aPluginsecurest_11// "PluginSecureStoreServiceProvider.GetCon"...
0x7b97  ldc.i4.1
0x7b98  newarr   [mscorlib]System.Object
0x7b9d  dup
0x7b9e  ldc.i4.0
0x7b9f  ldarg.1
0x7ba0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x7ba5  box      [mscorlib]System.Guid
0x7baa  stelem.ref
0x7bab  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7bb0  ldarg.0
0x7bb1  ldarg.1
0x7bb2  ldarg.2
0x7bb3  ldloc.0
0x7bb4  ldftn    instance unsigned int8[] <>c__DisplayClass14_0::<GetConfigStoreData>b__0(string assemblyName, string publicToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext sqlContext)
0x7bba  newobj   instance void class [mscorlib]System.Func`4<string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, unsigned int8[]>::.ctor(object, native int)
0x7bbf  call     T0x2B00001E
0x7bc4  stloc.1
0x7bc5  ldarg.2
0x7bc6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7bcb  ldc.i4.s 0x1F
0x7bcd  ldstr    aPluginsecurest_12// "PluginSecureStoreServiceProvider.GetCon"...
0x7bd2  ldc.i4.1
0x7bd3  newarr   [mscorlib]System.Object
0x7bd8  dup
0x7bd9  ldc.i4.0
0x7bda  ldarg.1
0x7bdb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x7be0  box      [mscorlib]System.Guid
0x7be5  stelem.ref
0x7be6  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7beb  ldloc.1
0x7bec  ret
```
