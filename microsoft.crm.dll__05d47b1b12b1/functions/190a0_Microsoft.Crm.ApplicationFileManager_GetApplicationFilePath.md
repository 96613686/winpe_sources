# Microsoft.Crm.ApplicationFileManager::GetApplicationFilePath

- ea: `0x190a0`
- end: `0x190ed`
- name: `Microsoft.Crm.ApplicationFileManager::GetApplicationFilePath`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4a1f0`
- `0x4af30`

## callees

- `0x190a0`
- `0x190f0`

## string_xrefs

- `0x190a7`: `SolutionComponents.xml`

## pseudocode

```c

```

## disassembly

```asm
0x190a0  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInCrmInternalToolContext()
0x190a5  brfalse.s loc_190D7
0x190a7  ldstr    aSolutioncompon// "SolutionComponents.xml"
0x190ac  ldarg.0
0x190ad  ldc.i4.5
0x190ae  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x190b3  brtrue.s loc_190C1
0x190b5  call     string [mscorlib]System.Environment::get_CurrentDirectory()
0x190ba  ldarg.0
0x190bb  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x190c0  ret
0x190c1  call     string [mscorlib]System.Environment::get_CurrentDirectory()
0x190c6  ldstr    aCrm// "CRM"
0x190cb  ldstr    aSchemas// "Schemas"
0x190d0  ldarg.0
0x190d1  call     string [mscorlib]System.IO.Path::Combine(string, string, string, string)
0x190d6  ret
0x190d7  call     string Microsoft.Crm.ApplicationFileManager::GetServerFolder()
0x190dc  ldstr    aApplicationfil// "ApplicationFiles"
0x190e1  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x190e6  ldarg.0
0x190e7  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x190ec  ret
```
