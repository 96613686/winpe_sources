# Microsoft.Crm.Sandbox.SandboxAssemblyManager::MaxCacheSizePerOrgInMByte

- ea: `0x3880`
- end: `0x38f1`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyManager::MaxCacheSizePerOrgInMByte`
- size: `113`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3030`
- `0x34b0`
- `0x36a0`

## callees

- `0x3880`
- `0x48e0`

## string_xrefs

- `0x3887`: `SandboxAssemblyManager.MaxCacheSizePerOrgInMByte: numberOfOrgs: {0}`
- `0x38d6`: `SandboxAssemblyManager.MaxCacheSizePerOrgInMByte: maxCacheSizePerOrgInMByte: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3880  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3885  ldc.i4.s 0x22
0x3887  ldstr    aSandboxassembl_57// "SandboxAssemblyManager.MaxCacheSizePerO"...
0x388c  ldc.i4.1
0x388d  newarr   [mscorlib]System.Object
0x3892  dup
0x3893  ldc.i4.0
0x3894  ldarg.0
0x3895  box      [mscorlib]System.Int32
0x389a  stelem.ref
0x389b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x38a0  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0x38a5  ldc.i4.2
0x38a6  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0x38ab  conv.r8
0x38ac  stloc.0
0x38ad  ldarg.0
0x38ae  ldc.i4.1
0x38af  ble.s    loc_38B6
0x38b1  ldloc.0
0x38b2  ldarg.0
0x38b3  conv.r8
0x38b4  div
0x38b5  stloc.0
0x38b6  ldloc.0
0x38b7  ldc.r8   1.0
0x38c0  blt.s    loc_38C5
0x38c2  ldloc.0
0x38c3  br.s     loc_38CE
0x38c5  ldc.r8   1.0
0x38ce  stloc.0
0x38cf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x38d4  ldc.i4.s 0x22
0x38d6  ldstr    aSandboxassembl_58// "SandboxAssemblyManager.MaxCacheSizePerO"...
0x38db  ldc.i4.1
0x38dc  newarr   [mscorlib]System.Object
0x38e1  dup
0x38e2  ldc.i4.0
0x38e3  ldloc.0
0x38e4  box      [mscorlib]System.Double
0x38e9  stelem.ref
0x38ea  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x38ef  ldloc.0
0x38f0  ret
```
