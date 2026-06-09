# Microsoft.Crm.CrossSiteScriptingValidation::IsDangerousOnString

- ea: `0x40`
- end: `0xc2`
- name: `Microsoft.Crm.CrossSiteScriptingValidation::IsDangerousOnString`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1e0`

## callees

- `0x20`
- `0x40`

## pseudocode

```c

```

## disassembly

```asm
0x40  ldarg.0
0x41  ldarg.1
0x42  ldc.i4.1
0x43  add
0x44  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x49  ldc.i4.s 0x6E
0x4b  beq.s    loc_5C
0x4d  ldarg.0
0x4e  ldarg.1
0x4f  ldc.i4.1
0x50  add
0x51  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x56  ldc.i4.s 0x4E
0x58  beq.s    loc_5C
0x5a  ldc.i4.0
0x5b  ret
0x5c  ldarg.1
0x5d  ldc.i4.0
0x5e  ble.s    loc_72
0x60  ldarg.0
0x61  ldarg.1
0x62  ldc.i4.1
0x63  sub
0x64  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x69  call     bool Microsoft.Crm.CrossSiteScriptingValidation::IsAtoZ(char c)
0x6e  brfalse.s loc_72
0x70  ldc.i4.0
0x71  ret
0x72  ldarg.0
0x73  callvirt instance int32 [mscorlib]System.String::get_Length()
0x78  stloc.0
0x79  ldarg.1
0x7a  ldc.i4.2
0x7b  add
0x7c  starg.s  1
0x7e  br.s     loc_85
0x80  ldarg.1
0x81  ldc.i4.1
0x82  add
0x83  starg.s  1
0x85  ldarg.1
0x86  ldloc.0
0x87  bge.s    loc_9E
0x89  ldarg.0
0x8a  ldarg.1
0x8b  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x90  call     bool Microsoft.Crm.CrossSiteScriptingValidation::IsAtoZ(char c)
0x95  brtrue.s loc_80
0x97  br.s     loc_9E
0x99  ldarg.1
0x9a  ldc.i4.1
0x9b  add
0x9c  starg.s  1
0x9e  ldarg.1
0x9f  ldloc.0
0xa0  bge.s    loc_B0
0xa2  ldarg.0
0xa3  ldarg.1
0xa4  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xa9  call     bool [mscorlib]System.Char::IsWhiteSpace(char)
0xae  brtrue.s loc_99
0xb0  ldarg.1
0xb1  ldloc.0
0xb2  bge.s    loc_C0
0xb4  ldarg.0
0xb5  ldarg.1
0xb6  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xbb  ldc.i4.s 0x3D
0xbd  ceq
0xbf  ret
0xc0  ldc.i4.0
0xc1  ret
```
