# Microsoft.Crm.Extensibility.Retry.Policy.SolutionRequestRetryPolicy`1::GetDefaultSolutionImportRetryCount

- ea: `0xe300`
- end: `0xe338`
- name: `Microsoft.Crm.Extensibility.Retry.Policy.SolutionRequestRetryPolicy`1::GetDefaultSolutionImportRetryCount`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0xe302`: `SolutionImportRetryAttempts`
- `0xe314`: `SolutionImportRetryAttempts`
- `0xe320`: `SolutionImportRetryAttempts`

## pseudocode

```c

```

## disassembly

```asm
0xe300  ldc.i4.3
0xe301  stloc.0
0xe302  ldstr    aSolutionimport// "SolutionImportRetryAttempts"
0xe307  ldloc.0
0xe308  call     T0x2B00005B
0xe30d  stloc.0
0xe30e  ldarg.0
0xe30f  ldfld    valuetype [mscorlib]System.Guid class Microsoft.Crm.Extensibility.Retry.Policy.SolutionRequestRetryPolicy`1<var<u1>>::_organizationId
0xe314  ldstr    aSolutionimport// "SolutionImportRetryAttempts"
0xe319  ldloc.0
0xe31a  call     T0x2B00005C
0xe31f  stloc.0
0xe320  ldstr    aSolutionimport// "SolutionImportRetryAttempts"
0xe325  ldloc.0
0xe326  box      [mscorlib]System.Int32
0xe32b  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0xe330  unbox.any [mscorlib]System.Int32
0xe335  stloc.0
0xe336  ldloc.0
0xe337  ret
```
