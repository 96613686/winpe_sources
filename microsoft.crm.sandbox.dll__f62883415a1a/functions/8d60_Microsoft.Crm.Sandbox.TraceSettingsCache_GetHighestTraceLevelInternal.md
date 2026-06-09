# Microsoft.Crm.Sandbox.TraceSettingsCache::GetHighestTraceLevelInternal

- ea: `0x8d60`
- end: `0x8e71`
- name: `Microsoft.Crm.Sandbox.TraceSettingsCache::GetHighestTraceLevelInternal`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8d00`

## callees

- `0x8d60`

## pseudocode

```c

```

## disassembly

```asm
0x8d60  ldarg.1
0x8d61  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8d66  brtrue.s loc_8D70
0x8d68  ldarg.2
0x8d69  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8d6e  brfalse.s loc_8D72
0x8d70  ldc.i4.0
0x8d71  ret
0x8d72  ldc.i4.0
0x8d73  stloc.0
0x8d74  ldc.i4.1
0x8d75  newarr   [mscorlib]System.Char
0x8d7a  dup
0x8d7b  ldc.i4.0
0x8d7c  ldc.i4.s 0x3B
0x8d7e  stelem.i2
0x8d7f  stloc.1
0x8d80  ldc.i4.1
0x8d81  newarr   [mscorlib]System.Char
0x8d86  dup
0x8d87  ldc.i4.0
0x8d88  ldc.i4.s 0x3A
0x8d8a  stelem.i2
0x8d8b  stloc.2
0x8d8c  ldarg.2
0x8d8d  ldloc.1
0x8d8e  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x8d93  stloc.3
0x8d94  ldc.i4.0
0x8d95  stloc.s  4
0x8d97  br       loc_8E65
0x8d9c  ldloc.3
0x8d9d  ldloc.s  4
0x8d9f  ldelem.ref
0x8da0  stloc.s  5
0x8da2  ldloc.s  5
0x8da4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8da9  brtrue   loc_8E5F
0x8dae  ldloc.s  5
0x8db0  ldloc.2
0x8db1  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x8db6  stloc.s  6
0x8db8  ldloc.s  6
0x8dba  ldlen
0x8dbb  conv.i4
0x8dbc  ldc.i4.2
0x8dbd  bne.un   loc_8E5F
0x8dc2  ldloc.s  6
0x8dc4  ldc.i4.0
0x8dc5  ldelem.ref
0x8dc6  callvirt instance string [mscorlib]System.String::Trim()
0x8dcb  stloc.s  7
0x8dcd  ldloc.s  7
0x8dcf  ldstr    asc_1156E// "*"
0x8dd4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8dd9  brfalse.s loc_8DE2
0x8ddb  ldstr    asc_11572// ".*"
0x8de0  stloc.s  7
0x8de2  nop
0x8de3  ldloc.s  7
0x8de5  call     class [System]System.Text.RegularExpressions.Regex [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::GetRegex(string)
0x8dea  ldarg.1
0x8deb  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0x8df0  brtrue.s loc_8DF4
0x8df2  leave.s  loc_8E5F
0x8df4  leave.s  loc_8DF9
0x8df6  pop
0x8df7  leave.s  loc_8E5F
0x8df9  ldloc.s  6
0x8dfb  ldc.i4.1
0x8dfc  ldelem.ref
0x8dfd  callvirt instance string [mscorlib]System.String::Trim()
0x8e02  stloc.s  8
0x8e04  ldc.i4.0
0x8e05  stloc.s  9
0x8e07  ldloc.s  8
0x8e09  ldstr    aVerbose// "Verbose"
0x8e0e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8e13  brtrue.s loc_8E41
0x8e15  ldloc.s  8
0x8e17  ldstr    aInfo// "Info"
0x8e1c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8e21  brtrue.s loc_8E46
0x8e23  ldloc.s  8
0x8e25  ldstr    aWarning// "Warning"
0x8e2a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8e2f  brtrue.s loc_8E4B
0x8e31  ldloc.s  8
0x8e33  ldstr    aError// "Error"
0x8e38  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8e3d  brtrue.s loc_8E50
0x8e3f  br.s     loc_8E53
0x8e41  ldc.i4.4
0x8e42  stloc.s  9
0x8e44  br.s     loc_8E53
0x8e46  ldc.i4.3
0x8e47  stloc.s  9
0x8e49  br.s     loc_8E53
0x8e4b  ldc.i4.2
0x8e4c  stloc.s  9
0x8e4e  br.s     loc_8E53
0x8e50  ldc.i4.1
0x8e51  stloc.s  9
0x8e53  ldloc.0
0x8e54  ldloc.s  9
0x8e56  bge.s    loc_8E5B
0x8e58  ldloc.s  9
0x8e5a  stloc.0
0x8e5b  ldc.i4.4
0x8e5c  ldloc.0
0x8e5d  beq.s    loc_8E6F
0x8e5f  ldloc.s  4
0x8e61  ldc.i4.1
0x8e62  add
0x8e63  stloc.s  4
0x8e65  ldloc.s  4
0x8e67  ldloc.3
0x8e68  ldlen
0x8e69  conv.i4
0x8e6a  blt      loc_8D9C
0x8e6f  ldloc.0
0x8e70  ret
```
