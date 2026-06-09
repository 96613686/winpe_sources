# Microsoft.Crm.Sandbox.SandboxClientConfiguration::RetrieveDeploymentProperties

- ea: `0xdb0`
- end: `0xe1c`
- name: `Microsoft.Crm.Sandbox.SandboxClientConfiguration::RetrieveDeploymentProperties`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xd70`
- `0xdb0`
- `0x3d00`

## string_xrefs

- `0xdb8`: `LocatorService.Instance is null`

## pseudocode

```c

```

## disassembly

```asm
0xdb0  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xdb5  ldnull
0xdb6  cgt.un
0xdb8  ldstr    aLocatorservice// "LocatorService.Instance is null"
0xdbd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xdc2  call     valuetype Microsoft.Crm.Sandbox.SandboxClientProperty[] Microsoft.Crm.Sandbox.SandboxDeploymentProperties::get_ClientDeploymentProperties()
0xdc7  stloc.0
0xdc8  ldc.i4.0
0xdc9  stloc.1
0xdca  br.s     loc_E15
0xdcc  ldloc.0
0xdcd  ldloc.1
0xdce  ldelem.i4
0xdcf  stloc.2
0xdd0  ldc.i4.1
0xdd1  stloc.s  4
0xdd3  ldloca.s 4
0xdd5  constrained. Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0xddb  callvirt instance string [mscorlib]System.Object::ToString()
0xde0  ldloca.s 2
0xde2  constrained. Microsoft.Crm.Sandbox.SandboxClientProperty
0xde8  callvirt instance string [mscorlib]System.Object::ToString()
0xded  call     string [mscorlib]System.String::Concat(string, string)
0xdf2  ldnull
0xdf3  call     T0x2B000006
0xdf8  stloc.3
0xdf9  ldloc.3
0xdfa  brfalse.s loc_E11
0xdfc  ldloc.3
0xdfd  isinst   [mscorlib]System.Int32
0xe02  brfalse.s loc_E11
0xe04  ldarg.0
0xe05  ldloc.2
0xe06  ldloc.3
0xe07  unbox.any [mscorlib]System.Int32
0xe0c  call     instance void Microsoft.Crm.Sandbox.SandboxClientConfiguration::set_Item(valuetype Microsoft.Crm.Sandbox.SandboxClientProperty key, int32 value)
0xe11  ldloc.1
0xe12  ldc.i4.1
0xe13  add
0xe14  stloc.1
0xe15  ldloc.1
0xe16  ldloc.0
0xe17  ldlen
0xe18  conv.i4
0xe19  blt.s    loc_DCC
0xe1b  ret
```
