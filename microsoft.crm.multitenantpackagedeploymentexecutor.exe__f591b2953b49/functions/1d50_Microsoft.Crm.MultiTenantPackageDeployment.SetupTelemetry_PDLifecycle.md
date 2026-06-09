# Microsoft.Crm.MultiTenantPackageDeployment.SetupTelemetry::PDLifecycle

- ea: `0x1d50`
- end: `0x1d86`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.SetupTelemetry::PDLifecycle`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x830`
- `0x850`

## pseudocode

```c

```

## disassembly

```asm
0x1d50  ldnull
0x1d51  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1d56  ldc.i4.s 0x14
0x1d58  ldc.i4   0x3E7
0x1d5d  ldstr    aNotAnErrorPdli// "NOT AN ERROR PDLifecycle: {0}, cmdline:"...
0x1d62  ldc.i4.5
0x1d63  newarr   [mscorlib]System.Object
0x1d68  dup
0x1d69  ldc.i4.0
0x1d6a  ldsfld   string Microsoft.Crm.MultiTenantPackageDeployment.SetupTelemetry::applicationVersion
0x1d6f  stelem.ref
0x1d70  dup
0x1d71  ldc.i4.1
0x1d72  ldarg.0
0x1d73  stelem.ref
0x1d74  dup
0x1d75  ldc.i4.2
0x1d76  ldarg.1
0x1d77  stelem.ref
0x1d78  dup
0x1d79  ldc.i4.3
0x1d7a  ldarg.2
0x1d7b  stelem.ref
0x1d7c  dup
0x1d7d  ldc.i4.4
0x1d7e  ldarg.3
0x1d7f  stelem.ref
0x1d80  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x1d85  ret
```
