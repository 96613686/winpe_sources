# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::SetConfigStoreData

- ea: `0x7a00`
- end: `0x7aa4`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::SetConfigStoreData`
- size: `164`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x9640`

## string_xrefs

- `0x7a4a`: `PluginSecureStoreServiceProvider.SetConfigStoreData_StringByte[] - started. CallInfo {0}`
- `0x7a85`: `PluginSecureStoreServiceProvider.SetConfigStoreData_StringByte[] - successfully finished. CallInfo {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7a00  newobj   instance void <>c__DisplayClass12_0::.ctor()
0x7a05  stloc.0
0x7a06  ldloc.0
0x7a07  ldarg.0
0x7a08  stfld    class Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider <>c__DisplayClass12_0::<>4__this
0x7a0d  ldloc.0
0x7a0e  ldarg.3
0x7a0f  stfld    string <>c__DisplayClass12_0::keyName
0x7a14  ldloc.0
0x7a15  ldarg.s  4
0x7a17  stfld    unsigned int8[] <>c__DisplayClass12_0::data
0x7a1c  ldarg.1
0x7a1d  ldstr    aCallinfo// "callInfo"
0x7a22  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7a27  ldarg.2
0x7a28  ldstr    aContext// "context"
0x7a2d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7a32  ldloc.0
0x7a33  ldfld    unsigned int8[] <>c__DisplayClass12_0::data
0x7a38  ldstr    aData// "data"
0x7a3d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7a42  ldarg.2
0x7a43  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7a48  ldc.i4.s 0x1F
0x7a4a  ldstr    aPluginsecurest_7// "PluginSecureStoreServiceProvider.SetCon"...
0x7a4f  ldc.i4.1
0x7a50  newarr   [mscorlib]System.Object
0x7a55  dup
0x7a56  ldc.i4.0
0x7a57  ldarg.1
0x7a58  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x7a5d  box      [mscorlib]System.Guid
0x7a62  stelem.ref
0x7a63  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7a68  ldarg.0
0x7a69  ldarg.1
0x7a6a  ldarg.2
0x7a6b  ldloc.0
0x7a6c  ldftn    instance object <>c__DisplayClass12_0::<SetConfigStoreData>b__0(string assemblyName, string publicToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext sqlContext)
0x7a72  newobj   instance void class [mscorlib]System.Func`4<string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, object>::.ctor(object, native int)
0x7a77  call     T0x2B00001D
0x7a7c  pop
0x7a7d  ldarg.2
0x7a7e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7a83  ldc.i4.s 0x1F
0x7a85  ldstr    aPluginsecurest_8// "PluginSecureStoreServiceProvider.SetCon"...
0x7a8a  ldc.i4.1
0x7a8b  newarr   [mscorlib]System.Object
0x7a90  dup
0x7a91  ldc.i4.0
0x7a92  ldarg.1
0x7a93  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x7a98  box      [mscorlib]System.Guid
0x7a9d  stelem.ref
0x7a9e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7aa3  ret
```
