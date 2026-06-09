# Microsoft.Crm.Common.Web.Activities.TemplateTargetDialog::FillLists

- ea: `0xbed0`
- end: `0xbf7d`
- name: `Microsoft.Crm.Common.Web.Activities.TemplateTargetDialog::FillLists`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xbf80`

## callees

- `0xbed0`
- `0x1dcb0`
- `0x1dcd0`
- `0x1dcf0`
- `0x1dd00`

## pseudocode

```c

```

## disassembly

```asm
0xbed0  ldarg.0
0xbed1  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xbed6  stfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Common.Web.Activities.TemplateTargetDialog::_ToEntries
0xbedb  ldarg.0
0xbedc  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xbee1  stfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Common.Web.Activities.TemplateTargetDialog::_CCEntries
0xbee6  ldarg.0
0xbee7  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xbeec  stfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Common.Web.Activities.TemplateTargetDialog::_RegardingEntries
0xbef1  ldc.i4.0
0xbef2  stloc.0
0xbef3  br.s     loc_BF73
0xbef5  newobj   instance void TargetEntry::.ctor()
0xbefa  stloc.1
0xbefb  ldloc.1
0xbefc  ldarg.1
0xbefd  ldloc.0
0xbefe  ldelem.ref
0xbeff  callvirt instance void TargetEntry::set_Id(string value)
0xbf04  ldloc.1
0xbf05  ldarg.2
0xbf06  ldloc.0
0xbf07  ldelem.ref
0xbf08  callvirt instance void TargetEntry::set_ObjectTypeCode(string value)
0xbf0d  ldloc.1
0xbf0e  ldarg.s  4
0xbf10  ldloc.0
0xbf11  ldelem.ref
0xbf12  callvirt instance void TargetEntry::set_Name(string value)
0xbf17  ldarg.3
0xbf18  ldloc.0
0xbf19  ldelem.ref
0xbf1a  stloc.2
0xbf1b  ldloc.2
0xbf1c  ldstr    aTo// "to"
0xbf21  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbf26  brtrue.s loc_BF44
0xbf28  ldloc.2
0xbf29  ldstr    aCc// "cc"
0xbf2e  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbf33  brtrue.s loc_BF53
0xbf35  ldloc.2
0xbf36  ldstr    aRe// "re"
0xbf3b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbf40  brtrue.s loc_BF62
0xbf42  br.s     loc_BF6F
0xbf44  ldarg.0
0xbf45  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Common.Web.Activities.TemplateTargetDialog::_ToEntries
0xbf4a  ldloc.1
0xbf4b  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xbf50  pop
0xbf51  br.s     loc_BF6F
0xbf53  ldarg.0
0xbf54  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Common.Web.Activities.TemplateTargetDialog::_CCEntries
0xbf59  ldloc.1
0xbf5a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xbf5f  pop
0xbf60  br.s     loc_BF6F
0xbf62  ldarg.0
0xbf63  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Common.Web.Activities.TemplateTargetDialog::_RegardingEntries
0xbf68  ldloc.1
0xbf69  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xbf6e  pop
0xbf6f  ldloc.0
0xbf70  ldc.i4.1
0xbf71  add
0xbf72  stloc.0
0xbf73  ldloc.0
0xbf74  ldarg.1
0xbf75  ldlen
0xbf76  conv.i4
0xbf77  blt      loc_BEF5
0xbf7c  ret
```
