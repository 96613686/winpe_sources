# Microsoft.Crm.Sandbox.SandboxHostConfiguration::RetrieveDeploymentProperties

- ea: `0x5580`
- end: `0x562c`
- name: `Microsoft.Crm.Sandbox.SandboxHostConfiguration::RetrieveDeploymentProperties`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14d0`
- `0x3d10`
- `0x5520`
- `0x5580`

## string_xrefs

- `0x5585`: `LocatorService.Instance`
- `0x55ca`: `SandboxHostConfiguration.RetrieveDeploymentProperties: deploymentSettingName: {0}`
- `0x55fb`: `SandboxHostConfiguration.RetrieveDeploymentProperties: setting: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5580  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x5585  ldstr    aLocatorservice_0// "LocatorService.Instance"
0x558a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x558f  call     valuetype Microsoft.Crm.Sandbox.SandboxHostProperty[] Microsoft.Crm.Sandbox.SandboxDeploymentProperties::get_HostDeploymentProperties()
0x5594  stloc.0
0x5595  ldc.i4.0
0x5596  stloc.1
0x5597  br       loc_5622
0x559c  ldloc.0
0x559d  ldloc.1
0x559e  ldelem.i4
0x559f  stloc.2
0x55a0  ldc.i4.2
0x55a1  stloc.s  5
0x55a3  ldloca.s 5
0x55a5  constrained. Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x55ab  callvirt instance string [mscorlib]System.Object::ToString()
0x55b0  ldloca.s 2
0x55b2  constrained. Microsoft.Crm.Sandbox.SandboxHostProperty
0x55b8  callvirt instance string [mscorlib]System.Object::ToString()
0x55bd  call     string [mscorlib]System.String::Concat(string, string)
0x55c2  stloc.3
0x55c3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x55c8  ldc.i4.s 0x26
0x55ca  ldstr    aSandboxhostcon// "SandboxHostConfiguration.RetrieveDeploy"...
0x55cf  ldc.i4.1
0x55d0  newarr   [mscorlib]System.Object
0x55d5  dup
0x55d6  ldc.i4.0
0x55d7  ldloc.3
0x55d8  stelem.ref
0x55d9  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x55de  ldloc.3
0x55df  ldnull
0x55e0  call     T0x2B000006
0x55e5  stloc.s  4
0x55e7  ldloc.s  4
0x55e9  brfalse.s loc_561E
0x55eb  ldloc.s  4
0x55ed  isinst   [mscorlib]System.Int32
0x55f2  brfalse.s loc_561E
0x55f4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x55f9  ldc.i4.s 0x26
0x55fb  ldstr    aSandboxhostcon_0// "SandboxHostConfiguration.RetrieveDeploy"...
0x5600  ldc.i4.1
0x5601  newarr   [mscorlib]System.Object
0x5606  dup
0x5607  ldc.i4.0
0x5608  ldloc.s  4
0x560a  stelem.ref
0x560b  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x5610  ldarg.0
0x5611  ldloc.2
0x5612  ldloc.s  4
0x5614  unbox.any [mscorlib]System.Int32
0x5619  call     instance void Microsoft.Crm.Sandbox.SandboxHostConfiguration::set_Item(valuetype Microsoft.Crm.Sandbox.SandboxHostProperty key, int32 value)
0x561e  ldloc.1
0x561f  ldc.i4.1
0x5620  add
0x5621  stloc.1
0x5622  ldloc.1
0x5623  ldloc.0
0x5624  ldlen
0x5625  conv.i4
0x5626  blt      loc_559C
0x562b  ret
```
