# Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::RetrieveDeploymentProperties

- ea: `0x80d0`
- end: `0x8180`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::RetrieveDeploymentProperties`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14d0`
- `0x3d20`
- `0x8090`
- `0x80d0`

## string_xrefs

- `0x80d5`: `LocatorService.Instance`
- `0x811a`: `SandboxWorkerConfiguration.RetrieveDeploymentProperties: deploymentSettingName: {0}`
- `0x814f`: `SandboxWorkerConfiguration.RetrieveDeploymentProperties: setting: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x80d0  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x80d5  ldstr    aLocatorservice_0// "LocatorService.Instance"
0x80da  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x80df  call     valuetype Microsoft.Crm.Sandbox.SandboxWorkerProperty[] Microsoft.Crm.Sandbox.SandboxDeploymentProperties::get_WorkerDeploymentProperties()
0x80e4  stloc.0
0x80e5  ldc.i4.0
0x80e6  stloc.1
0x80e7  br       loc_8176
0x80ec  ldloc.0
0x80ed  ldloc.1
0x80ee  ldelem.i4
0x80ef  stloc.2
0x80f0  ldc.i4.3
0x80f1  stloc.s  5
0x80f3  ldloca.s 5
0x80f5  constrained. Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x80fb  callvirt instance string [mscorlib]System.Object::ToString()
0x8100  ldloca.s 2
0x8102  constrained. Microsoft.Crm.Sandbox.SandboxWorkerProperty
0x8108  callvirt instance string [mscorlib]System.Object::ToString()
0x810d  call     string [mscorlib]System.String::Concat(string, string)
0x8112  stloc.3
0x8113  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8118  ldc.i4.s 0x26
0x811a  ldstr    aSandboxworkerc// "SandboxWorkerConfiguration.RetrieveDepl"...
0x811f  ldc.i4.1
0x8120  newarr   [mscorlib]System.Object
0x8125  dup
0x8126  ldc.i4.0
0x8127  ldloc.3
0x8128  stelem.ref
0x8129  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x812e  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x8133  ldloc.3
0x8134  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentSetting(string)
0x8139  stloc.s  4
0x813b  ldloc.s  4
0x813d  brfalse.s loc_8172
0x813f  ldloc.s  4
0x8141  isinst   [mscorlib]System.Int32
0x8146  brfalse.s loc_8172
0x8148  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x814d  ldc.i4.s 0x26
0x814f  ldstr    aSandboxworkerc_0// "SandboxWorkerConfiguration.RetrieveDepl"...
0x8154  ldc.i4.1
0x8155  newarr   [mscorlib]System.Object
0x815a  dup
0x815b  ldc.i4.0
0x815c  ldloc.s  4
0x815e  stelem.ref
0x815f  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x8164  ldarg.0
0x8165  ldloc.2
0x8166  ldloc.s  4
0x8168  unbox.any [mscorlib]System.Int32
0x816d  call     instance void Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::set_Item(valuetype Microsoft.Crm.Sandbox.SandboxWorkerProperty key, int32 value)
0x8172  ldloc.1
0x8173  ldc.i4.1
0x8174  add
0x8175  stloc.1
0x8176  ldloc.1
0x8177  ldloc.0
0x8178  ldlen
0x8179  conv.i4
0x817a  blt      loc_80EC
0x817f  ret
```
