# Microsoft.Crm.Extensibility.RetryHelper::GetDefaultSolutionImportRetryAttempts

- ea: `0xc620`
- end: `0xc653`
- name: `Microsoft.Crm.Extensibility.RetryHelper::GetDefaultSolutionImportRetryAttempts`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xc050`

## string_xrefs

- `0xc622`: `SolutionImportRetryAttempts`
- `0xc62f`: `SolutionImportRetryAttempts`
- `0xc63b`: `SolutionImportRetryAttempts`

## pseudocode

```c

```

## disassembly

```asm
0xc620  ldc.i4.2
0xc621  stloc.0
0xc622  ldstr    aSolutionimport// "SolutionImportRetryAttempts"
0xc627  ldloc.0
0xc628  call     T0x2B000045
0xc62d  stloc.0
0xc62e  ldarg.1
0xc62f  ldstr    aSolutionimport// "SolutionImportRetryAttempts"
0xc634  ldloc.0
0xc635  call     T0x2B000046
0xc63a  stloc.0
0xc63b  ldstr    aSolutionimport// "SolutionImportRetryAttempts"
0xc640  ldloc.0
0xc641  box      [mscorlib]System.Int32
0xc646  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0xc64b  unbox.any [mscorlib]System.Int32
0xc650  stloc.0
0xc651  ldloc.0
0xc652  ret
```
