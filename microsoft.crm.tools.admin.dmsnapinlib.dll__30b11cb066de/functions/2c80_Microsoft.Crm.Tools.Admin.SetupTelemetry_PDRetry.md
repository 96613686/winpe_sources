# Microsoft.Crm.Tools.Admin.SetupTelemetry::PDRetry

- ea: `0x2c80`
- end: `0x2cae`
- name: `Microsoft.Crm.Tools.Admin.SetupTelemetry::PDRetry`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18310`

## string_xrefs

- `0x2c88`: `NOT AN ERROR PDRetry: {0}, attempt: {1}, package: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x2c80  ldnull
0x2c81  ldarg.1
0x2c82  ldc.i4.3
0x2c83  ldc.i4   0x3E7
0x2c88  ldstr    aNotAnErrorPdre// "NOT AN ERROR PDRetry: {0}, attempt: {1}"...
0x2c8d  ldc.i4.3
0x2c8e  newarr   [mscorlib]System.Object
0x2c93  dup
0x2c94  ldc.i4.0
0x2c95  ldsfld   string Microsoft.Crm.Tools.Admin.SetupTelemetry::applicationVersion
0x2c9a  stelem.ref
0x2c9b  dup
0x2c9c  ldc.i4.1
0x2c9d  ldarg.0
0x2c9e  box      [mscorlib]System.Int32
0x2ca3  stelem.ref
0x2ca4  dup
0x2ca5  ldc.i4.2
0x2ca6  ldarg.2
0x2ca7  stelem.ref
0x2ca8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x2cad  ret
```
