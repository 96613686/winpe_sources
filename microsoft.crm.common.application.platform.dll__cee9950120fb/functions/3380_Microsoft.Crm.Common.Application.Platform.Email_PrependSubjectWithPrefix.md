# Microsoft.Crm.Common.Application.Platform.Email::PrependSubjectWithPrefix

- ea: `0x3380`
- end: `0x3401`
- name: `Microsoft.Crm.Common.Application.Platform.Email::PrependSubjectWithPrefix`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3320`

## callees

- `0x3380`

## pseudocode

```c

```

## disassembly

```asm
0x3380  ldarg.0
0x3381  ldstr    aSubject// "subject"
0x3386  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x338b  isinst   [mscorlib]System.String
0x3390  stloc.0
0x3391  ldloc.0
0x3392  brtrue.s loc_339A
0x3394  ldsfld   string [mscorlib]System.String::Empty
0x3399  stloc.0
0x339a  ldloc.0
0x339b  ldarg.1
0x339c  ldc.i4.4
0x339d  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x33a2  brtrue.s loc_33F4
0x33a4  ldarg.1
0x33a5  ldstr    asc_9552// " "
0x33aa  ldarg.1
0x33ab  callvirt instance int32 [mscorlib]System.String::get_Length()
0x33b0  ldc.i4.1
0x33b1  add
0x33b2  ldloc.0
0x33b3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x33b8  add
0x33b9  ldc.i4   0xC8
0x33be  bgt.s    loc_33C3
0x33c0  ldloc.0
0x33c1  br.s     loc_33EE
0x33c3  ldloc.0
0x33c4  ldc.i4.0
0x33c5  ldloc.0
0x33c6  callvirt instance int32 [mscorlib]System.String::get_Length()
0x33cb  ldarg.1
0x33cc  callvirt instance int32 [mscorlib]System.String::get_Length()
0x33d1  sub
0x33d2  ldstr    asc_9556// "..."
0x33d7  call     instance int32 [mscorlib]System.String::get_Length()
0x33dc  sub
0x33dd  ldc.i4.1
0x33de  sub
0x33df  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x33e4  ldstr    asc_9556// "..."
0x33e9  call     string [mscorlib]System.String::Concat(string, string)
0x33ee  call     string [mscorlib]System.String::Concat(string, string, string)
0x33f3  stloc.0
0x33f4  ldarg.0
0x33f5  ldstr    aSubject// "subject"
0x33fa  ldloc.0
0x33fb  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3400  ret
```
