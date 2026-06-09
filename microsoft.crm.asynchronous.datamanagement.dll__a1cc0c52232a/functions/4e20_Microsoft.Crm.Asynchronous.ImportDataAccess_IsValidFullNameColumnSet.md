# Microsoft.Crm.Asynchronous.ImportDataAccess::IsValidFullNameColumnSet

- ea: `0x4e20`
- end: `0x4f1a`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::IsValidFullNameColumnSet`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x48f0`

## callees

- `0x4e20`

## pseudocode

```c

```

## disassembly

```asm
0x4e20  ldarg.2
0x4e21  ldc.i4.0
0x4e22  ldelem.ref
0x4e23  stloc.0
0x4e24  ldarg.2
0x4e25  ldc.i4.1
0x4e26  ldelem.ref
0x4e27  stloc.1
0x4e28  ldarg.2
0x4e29  ldc.i4.2
0x4e2a  ldelem.ref
0x4e2b  stloc.2
0x4e2c  ldarg.1
0x4e2d  switch   loc_4E57, loc_4E6F, loc_4E87, loc_4EA4, loc_4EBE, loc_4ED8, loc_4EF2, loc_4F04
0x4e52  br       loc_4F16
0x4e57  ldloc.0
0x4e58  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4e5d  brfalse  loc_4F18
0x4e62  ldloc.2
0x4e63  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4e68  brfalse  loc_4F18
0x4e6d  ldc.i4.0
0x4e6e  ret
0x4e6f  ldloc.0
0x4e70  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4e75  brfalse  loc_4F18
0x4e7a  ldloc.2
0x4e7b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4e80  brfalse  loc_4F18
0x4e85  ldc.i4.0
0x4e86  ret
0x4e87  ldloc.0
0x4e88  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4e8d  brfalse  loc_4F18
0x4e92  ldloc.1
0x4e93  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4e98  brfalse.s loc_4F18
0x4e9a  ldloc.2
0x4e9b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4ea0  brfalse.s loc_4F18
0x4ea2  ldc.i4.0
0x4ea3  ret
0x4ea4  ldloc.0
0x4ea5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4eaa  brfalse.s loc_4F18
0x4eac  ldloc.1
0x4ead  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4eb2  brfalse.s loc_4F18
0x4eb4  ldloc.2
0x4eb5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4eba  brfalse.s loc_4F18
0x4ebc  ldc.i4.0
0x4ebd  ret
0x4ebe  ldloc.0
0x4ebf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4ec4  brfalse.s loc_4F18
0x4ec6  ldloc.1
0x4ec7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4ecc  brfalse.s loc_4F18
0x4ece  ldloc.2
0x4ecf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4ed4  brfalse.s loc_4F18
0x4ed6  ldc.i4.0
0x4ed7  ret
0x4ed8  ldloc.0
0x4ed9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4ede  brfalse.s loc_4F18
0x4ee0  ldloc.1
0x4ee1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4ee6  brfalse.s loc_4F18
0x4ee8  ldloc.2
0x4ee9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4eee  brfalse.s loc_4F18
0x4ef0  ldc.i4.0
0x4ef1  ret
0x4ef2  ldloc.0
0x4ef3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4ef8  brfalse.s loc_4F18
0x4efa  ldloc.2
0x4efb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4f00  brfalse.s loc_4F18
0x4f02  ldc.i4.0
0x4f03  ret
0x4f04  ldloc.0
0x4f05  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4f0a  brfalse.s loc_4F18
0x4f0c  ldloc.2
0x4f0d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4f12  brfalse.s loc_4F18
0x4f14  ldc.i4.0
0x4f15  ret
0x4f16  ldc.i4.0
0x4f17  ret
0x4f18  ldc.i4.1
0x4f19  ret
```
