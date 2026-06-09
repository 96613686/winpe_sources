# Microsoft.Crm.Sandbox.SandboxUtility::AssemblyCachePath

- ea: `0x2d30`
- end: `0x2d6a`
- name: `Microsoft.Crm.Sandbox.SandboxUtility::AssemblyCachePath`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x2d10`
- `0x2d30`

## string_xrefs

- `0x2d4a`: `AssemblyCache`
- `0x2d5e`: `assemblyCachePath`

## pseudocode

```c

```

## disassembly

```asm
0x2d30  ldarg.0
0x2d31  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2d36  brtrue.s loc_2D3B
0x2d38  ldarg.0
0x2d39  br.s     loc_2D40
0x2d3b  call     string Microsoft.Crm.Sandbox.SandboxUtility::SandboxFilesPath()
0x2d40  starg.s  0
0x2d42  ldc.i4.s 0xC
0x2d44  ldarg.0
0x2d45  call     T0x2B000009
0x2d4a  ldstr    aAssemblycache// "AssemblyCache"
0x2d4f  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2d54  stloc.0
0x2d55  ldc.i4.7
0x2d56  ldloc.0
0x2d57  call     T0x2B000009
0x2d5c  stloc.0
0x2d5d  ldloc.0
0x2d5e  ldstr    aAssemblycachep// "assemblyCachePath"
0x2d63  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x2d68  ldloc.0
0x2d69  ret
```
