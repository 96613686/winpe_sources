# Microsoft.Crm.MultiTenantPackageDeployment.SetupTelemetry::PDCacheFlush

- ea: `0x1de0`
- end: `0x1e0a`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.SetupTelemetry::PDCacheFlush`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x590`

## string_xrefs

- `0x1de9`: `NOT AN ERROR PDCacheFlush: {0}, exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1de0  ldnull
0x1de1  ldarg.0
0x1de2  ldc.i4.s 0x14
0x1de4  ldc.i4   0x3E7
0x1de9  ldstr    aNotAnErrorPdca// "NOT AN ERROR PDCacheFlush: {0}, excepti"...
0x1dee  ldc.i4.2
0x1def  newarr   [mscorlib]System.Object
0x1df4  dup
0x1df5  ldc.i4.0
0x1df6  ldarg.1
0x1df7  ldnull
0x1df8  ceq
0x1dfa  box      [mscorlib]System.Boolean
0x1dff  stelem.ref
0x1e00  dup
0x1e01  ldc.i4.1
0x1e02  ldarg.1
0x1e03  stelem.ref
0x1e04  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x1e09  ret
```
