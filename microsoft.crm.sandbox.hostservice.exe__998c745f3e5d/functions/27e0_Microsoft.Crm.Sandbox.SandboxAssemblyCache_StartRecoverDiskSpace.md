# Microsoft.Crm.Sandbox.SandboxAssemblyCache::StartRecoverDiskSpace

- ea: `0x27e0`
- end: `0x281a`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyCache::StartRecoverDiskSpace`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x27e0`
- `0x2820`

## string_xrefs

- `0x27e7`: `cache`
- `0x2803`: `SandboxAssemblyCache.StartRecoverDiskSpace:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x27e0  ldarg.0
0x27e1  isinst   Microsoft.Crm.Sandbox.SandboxAssemblyCache
0x27e6  dup
0x27e7  ldstr    aCache// "cache"
0x27ec  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x27f1  ldc.i4.0
0x27f2  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxAssemblyCache::RecoverDiskSpace(bool fullScan)
0x27f7  pop
0x27f8  leave.s  loc_2819
0x27fa  stloc.0
0x27fb  ldloc.0
0x27fc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2801  ldc.i4.s 0x26
0x2803  ldstr    aSandboxassembl_7// "SandboxAssemblyCache.StartRecoverDiskSp"...
0x2808  ldc.i4.1
0x2809  newarr   [mscorlib]System.Object
0x280e  dup
0x280f  ldc.i4.0
0x2810  ldloc.0
0x2811  stelem.ref
0x2812  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2817  rethrow
0x2819  ret
```
