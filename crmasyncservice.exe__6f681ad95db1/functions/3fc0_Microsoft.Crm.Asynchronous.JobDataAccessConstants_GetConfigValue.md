# Microsoft.Crm.Asynchronous.JobDataAccessConstants::GetConfigValue

- ea: `0x3fc0`
- end: `0x4088`
- name: `Microsoft.Crm.Asynchronous.JobDataAccessConstants::GetConfigValue`
- size: `200`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3f80`
- `0x3f90`
- `0x3fa0`

## callees

- `0x3fc0`
- `0x4320`

## string_xrefs

- `0x403a`: `Reading setting {0}, returning {1}. Site Value: {2}, SG Value {3}, Default Value {4}, Min Value {5}`

## pseudocode

```c

```

## disassembly

```asm
0x3fc0  ldarg.1
0x3fc1  ldc.i4.1
0x3fc2  sub
0x3fc3  stloc.0
0x3fc4  ldloc.0
0x3fc5  stloc.1
0x3fc6  ldloc.0
0x3fc7  stloc.2
0x3fc8  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x3fcd  ldarg.0
0x3fce  ldarg.1
0x3fcf  ldc.i4.1
0x3fd0  sub
0x3fd1  callvirt T0x2B00000C
0x3fd6  stloc.1
0x3fd7  leave.s  loc_3FF8
0x3fd9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3fde  ldc.i4.s 0x15
0x3fe0  ldstr    aSgSettingsDepl// "SG settings (deployment property) for {"...
0x3fe5  ldarg.0
0x3fe6  call     string [mscorlib]System.String::Format(string, object)
0x3feb  ldc.i4.0
0x3fec  newarr   [mscorlib]System.Object
0x3ff1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3ff6  leave.s  loc_3FF8
0x3ff8  ldloc.1
0x3ff9  ldloc.0
0x3ffa  bne.un.s loc_402A
0x3ffc  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x4001  ldarg.0
0x4002  ldc.i4.0
0x4003  callvirt T0x2B00000D
0x4008  stloc.2
0x4009  leave.s  loc_402A
0x400b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4010  ldc.i4.s 0x15
0x4012  ldstr    aSiteSettingsSe// "Site settings (server settings) for {0}"...
0x4017  ldarg.0
0x4018  call     string [mscorlib]System.String::Format(string, object)
0x401d  ldc.i4.0
0x401e  newarr   [mscorlib]System.Object
0x4023  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4028  leave.s  loc_402A
0x402a  ldloc.1
0x402b  ldarg.1
0x402c  bge.s    loc_4038
0x402e  ldloc.2
0x402f  ldarg.1
0x4030  bge.s    loc_4035
0x4032  ldarg.2
0x4033  br.s     loc_4039
0x4035  ldloc.2
0x4036  br.s     loc_4039
0x4038  ldloc.1
0x4039  stloc.3
0x403a  ldstr    aReadingSetting// "Reading setting {0}, returning {1}. Sit"...
0x403f  ldc.i4.6
0x4040  newarr   [mscorlib]System.Object
0x4045  dup
0x4046  ldc.i4.0
0x4047  ldarg.0
0x4048  stelem.ref
0x4049  dup
0x404a  ldc.i4.1
0x404b  ldloc.3
0x404c  box      [mscorlib]System.Int32
0x4051  stelem.ref
0x4052  dup
0x4053  ldc.i4.2
0x4054  ldloc.2
0x4055  box      [mscorlib]System.Int32
0x405a  stelem.ref
0x405b  dup
0x405c  ldc.i4.3
0x405d  ldloc.1
0x405e  box      [mscorlib]System.Int32
0x4063  stelem.ref
0x4064  dup
0x4065  ldc.i4.4
0x4066  ldarg.2
0x4067  box      [mscorlib]System.Int32
0x406c  stelem.ref
0x406d  dup
0x406e  ldc.i4.5
0x406f  ldarg.1
0x4070  box      [mscorlib]System.Int32
0x4075  stelem.ref
0x4076  call     string [mscorlib]System.String::Format(string, object[])
0x407b  ldc.i4.0
0x407c  newarr   [mscorlib]System.Object
0x4081  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateThrottlingTelemetry(string messageFormat, object[] args)
0x4086  ldloc.3
0x4087  ret
```
