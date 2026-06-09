# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::SetConfigStoreData_0

- ea: `0x7ab0`
- end: `0x7b4c`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::SetConfigStoreData_0`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x9690`

## string_xrefs

- `0x7af2`: `PluginSecureStoreServiceProvider.SetConfigStoreData_Dictionary<string, byte[]> - started. CallInfo {0}`
- `0x7b2d`: `PluginSecureStoreServiceProvider.SetConfigStoreData_Dictionary<string, byte[]> - successfully finished. CallInfo {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7ab0  newobj   instance void <>c__DisplayClass13_0::.ctor()
0x7ab5  stloc.0
0x7ab6  ldloc.0
0x7ab7  ldarg.0
0x7ab8  stfld    class Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider <>c__DisplayClass13_0::<>4__this
0x7abd  ldloc.0
0x7abe  ldarg.3
0x7abf  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> <>c__DisplayClass13_0::keyData
0x7ac4  ldarg.1
0x7ac5  ldstr    aCallinfo// "callInfo"
0x7aca  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7acf  ldarg.2
0x7ad0  ldstr    aContext// "context"
0x7ad5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7ada  ldloc.0
0x7adb  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> <>c__DisplayClass13_0::keyData
0x7ae0  ldstr    aKeydata// "keyData"
0x7ae5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7aea  ldarg.2
0x7aeb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7af0  ldc.i4.s 0x1F
0x7af2  ldstr    aPluginsecurest_9// "PluginSecureStoreServiceProvider.SetCon"...
0x7af7  ldc.i4.1
0x7af8  newarr   [mscorlib]System.Object
0x7afd  dup
0x7afe  ldc.i4.0
0x7aff  ldarg.1
0x7b00  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x7b05  box      [mscorlib]System.Guid
0x7b0a  stelem.ref
0x7b0b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7b10  ldarg.0
0x7b11  ldarg.1
0x7b12  ldarg.2
0x7b13  ldloc.0
0x7b14  ldftn    instance object <>c__DisplayClass13_0::<SetConfigStoreData>b__0(string assemblyName, string publicToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext sqlContext)
0x7b1a  newobj   instance void class [mscorlib]System.Func`4<string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, object>::.ctor(object, native int)
0x7b1f  call     T0x2B00001D
0x7b24  pop
0x7b25  ldarg.2
0x7b26  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7b2b  ldc.i4.s 0x1F
0x7b2d  ldstr    aPluginsecurest_10// "PluginSecureStoreServiceProvider.SetCon"...
0x7b32  ldc.i4.1
0x7b33  newarr   [mscorlib]System.Object
0x7b38  dup
0x7b39  ldc.i4.0
0x7b3a  ldarg.1
0x7b3b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x7b40  box      [mscorlib]System.Guid
0x7b45  stelem.ref
0x7b46  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7b4b  ret
```
