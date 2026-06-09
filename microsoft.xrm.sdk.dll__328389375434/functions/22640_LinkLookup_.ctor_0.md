# LinkLookup::.ctor_0

- ea: `0x22640`
- end: `0x22664`
- name: `LinkLookup::.ctor_0`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0xc680`
- `0x22630`

## callees

- `0x225c0`
- `0x225e0`
- `0x22600`
- `0x22620`

## pseudocode

```c

```

## disassembly

```asm
0x22640  ldarg.0
0x22641  call     instance void [mscorlib]System.Object::.ctor()
0x22646  ldarg.0
0x22647  ldarg.1
0x22648  call     instance void LinkLookup::set_ParameterName(string value)
0x2264d  ldarg.0
0x2264e  ldarg.2
0x2264f  call     instance void LinkLookup::set_Environment(string value)
0x22654  ldarg.0
0x22655  ldarg.3
0x22656  call     instance void LinkLookup::set_Link(class Microsoft.Xrm.Sdk.Query.LinkEntity value)
0x2265b  ldarg.0
0x2265c  ldarg.s  4
0x2265e  call     instance void LinkLookup::set_SelectManyEnvironment(string value)
0x22663  ret
```
