# Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionHelper::IsSolutionComponentAttribute

- ea: `0x37fc0`
- end: `0x37ff8`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionHelper::IsSolutionComponentAttribute`
- size: `56`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x34240`
- `0x34910`
- `0x35010`
- `0x3f9d0`
- `0x3faa0`
- `0x3fdb0`

## callees

- `0x37fc0`

## string_xrefs

- `0x37fc1`: `componentstate`
- `0x37fce`: `overwritetime`

## pseudocode

```c

```

## disassembly

```asm
0x37fc0  ldarg.0
0x37fc1  ldstr    aComponentstate// "componentstate"
0x37fc6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x37fcb  brtrue.s loc_37FF4
0x37fcd  ldarg.0
0x37fce  ldstr    aOverwritetime_0// "overwritetime"
0x37fd3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x37fd8  brtrue.s loc_37FF4
0x37fda  ldarg.0
0x37fdb  ldstr    aSolutionid_0// "solutionid"
0x37fe0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x37fe5  brtrue.s loc_37FF4
0x37fe7  ldarg.0
0x37fe8  ldstr    aSupportingsolu// "supportingsolutionid"
0x37fed  call     bool [mscorlib]System.String::op_Equality(string, string)
0x37ff2  brfalse.s loc_37FF6
0x37ff4  ldc.i4.1
0x37ff5  ret
0x37ff6  ldc.i4.0
0x37ff7  ret
```
