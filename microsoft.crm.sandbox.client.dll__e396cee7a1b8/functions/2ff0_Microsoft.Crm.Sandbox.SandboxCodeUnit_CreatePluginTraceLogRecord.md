# Microsoft.Crm.Sandbox.SandboxCodeUnit::CreatePluginTraceLogRecord

- ea: `0x2ff0`
- end: `0x30ae`
- name: `Microsoft.Crm.Sandbox.SandboxCodeUnit::CreatePluginTraceLogRecord`
- size: `190`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x23d0`
- `0x2c40`

## callees

- `0x2310`
- `0x2320`
- `0x2330`
- `0x2ff0`
- `0x63c0`
- `0x6420`

## pseudocode

```c

```

## disassembly

```asm
0x2ff0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2ff5  ldarg.2
0x2ff6  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x2ffb  stloc.3
0x2ffc  ldloca.s 3
0x2ffe  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x3003  conv.i4
0x3004  stloc.0
0x3005  ldc.i4.1
0x3006  stloc.1
0x3007  ldarg.1
0x3008  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext
0x300d  brfalse.s loc_3011
0x300f  ldc.i4.2
0x3010  stloc.1
0x3011  ldarg.1
0x3012  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x3017  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x301c  ldarg.0
0x301d  call     instance string Microsoft.Crm.Sandbox.SandboxCodeUnit::get_PluginConfig()
0x3022  ldarg.1
0x3023  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x3028  ldarg.1
0x3029  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_Depth()
0x302e  ldarg.1
0x302f  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_Mode()
0x3034  ldloc.1
0x3035  ldc.i4.0
0x3036  ldarg.2
0x3037  ldloc.0
0x3038  ldarg.2
0x3039  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x303e  ldarg.1
0x303f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PrimaryEntityName()
0x3044  ldnull
0x3045  ldarg.1
0x3046  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_RequestId()
0x304b  stloc.s  4
0x304d  ldloca.s 4
0x304f  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x3054  brtrue.s loc_305D
0x3056  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x305b  br.s     loc_306C
0x305d  ldarg.1
0x305e  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_RequestId()
0x3063  stloc.s  4
0x3065  ldloca.s 4
0x3067  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x306c  ldarg.0
0x306d  call     instance string Microsoft.Crm.Sandbox.SandboxCodeUnit::get_PluginSecureConfig()
0x3072  ldarg.0
0x3073  call     instance string Microsoft.Crm.Sandbox.SandboxCodeUnit::get_TypeName()
0x3078  ldarg.1
0x3079  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OwningExtension()
0x307e  brtrue.s loc_3087
0x3080  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3085  br.s     loc_3092
0x3087  ldarg.1
0x3088  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OwningExtension()
0x308d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x3092  ldarg.3
0x3093  ldarg.s  4
0x3095  ldarg.1
0x3096  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0x309b  ldc.i4.1
0x309c  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::.ctor(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string, string, int32, int32, int32, int32, valuetype [mscorlib]System.DateTime, int32, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.Guid, string, string, valuetype [mscorlib]System.Guid, string, string, valuetype [mscorlib]System.Guid, string, string, valuetype [mscorlib]System.Guid, bool)
0x30a1  stloc.2
0x30a2  call     class Microsoft.Crm.Sandbox.IPluginTraceLogQueuesManager Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::get_Instance()
0x30a7  ldloc.2
0x30a8  callvirt instance void Microsoft.Crm.Sandbox.IPluginTraceLogQueuesManager::QueuePluginTraceLogRecord(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord pluginTraceLogRecord)
0x30ad  ret
```
