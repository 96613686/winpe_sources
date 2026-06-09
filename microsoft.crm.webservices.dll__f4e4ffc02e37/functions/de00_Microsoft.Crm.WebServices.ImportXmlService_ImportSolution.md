# Microsoft.Crm.WebServices.ImportXmlService::ImportSolution

- ea: `0xde00`
- end: `0xde12`
- name: `Microsoft.Crm.WebServices.ImportXmlService::ImportSolution`
- size: `18`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe080`
- `0xe0a0`

## callees

- `0xde20`

## pseudocode

```c

```

## disassembly

```asm
0xde00  ldarg.0
0xde01  ldarg.1
0xde02  ldarg.2
0xde03  ldarg.3
0xde04  ldarg.s  4
0xde06  ldarg.s  5
0xde08  ldc.i4.0
0xde09  ldc.i4.0
0xde0a  ldarg.s  6
0xde0c  call     instance void Microsoft.Crm.WebServices.ImportXmlService::ImportSolutionSkipCapable(bool overwriteUnmanagedCustomizations, bool publishWorkflows, unsigned int8[] customizationFile, valuetype [mscorlib]System.Guid importJobId, bool convertToManaged, bool skipProductUpdateDependencies, bool holdingSolution, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xde11  ret
```
