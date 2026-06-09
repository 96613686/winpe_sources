# Microsoft.Crm.Tools.Admin.SetupTelemetry::PDConnected

- ea: `0x2be0`
- end: `0x2c17`
- name: `Microsoft.Crm.Tools.Admin.SetupTelemetry::PDConnected`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x183f0`

## string_xrefs

- `0x2be8`: `NOT AN ERROR PDConnected: {0}, package: {1}, started by this: {2}, attempt count: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x2be0  ldnull
0x2be1  ldarg.0
0x2be2  ldc.i4.3
0x2be3  ldc.i4   0x3E7
0x2be8  ldstr    aNotAnErrorPdco// "NOT AN ERROR PDConnected: {0}, package:"...
0x2bed  ldc.i4.4
0x2bee  newarr   [mscorlib]System.Object
0x2bf3  dup
0x2bf4  ldc.i4.0
0x2bf5  ldsfld   string Microsoft.Crm.Tools.Admin.SetupTelemetry::applicationVersion
0x2bfa  stelem.ref
0x2bfb  dup
0x2bfc  ldc.i4.1
0x2bfd  ldarg.1
0x2bfe  stelem.ref
0x2bff  dup
0x2c00  ldc.i4.2
0x2c01  ldarg.2
0x2c02  box      [mscorlib]System.Boolean
0x2c07  stelem.ref
0x2c08  dup
0x2c09  ldc.i4.3
0x2c0a  ldarg.3
0x2c0b  box      [mscorlib]System.Int32
0x2c10  stelem.ref
0x2c11  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x2c16  ret
```
