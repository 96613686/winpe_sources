# Microsoft.Crm.Common.Application.Platform.ActivityBase::CheckPartyStatus

- ea: `0x2940`
- end: `0x2a1c`
- name: `Microsoft.Crm.Common.Application.Platform.ActivityBase::CheckPartyStatus`
- size: `220`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2a90`
- `0x3300`

## callees

- `0x2940`
- `0x2b70`

## pseudocode

```c

```

## disassembly

```asm
0x2940  ldc.i4.0
0x2941  stloc.0
0x2942  ldarg.0
0x2943  brtrue.s loc_2947
0x2945  ldloc.0
0x2946  ret
0x2947  ldc.i4.0
0x2948  stloc.1
0x2949  br       loc_2A0E
0x294e  ldarg.0
0x294f  ldloc.1
0x2950  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x2955  stloc.2
0x2956  ldloc.2
0x2957  ldstr    aPartyobjecttyp// "partyobjecttypecode"
0x295c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x2961  brtrue.s loc_2967
0x2963  ldloc.0
0x2964  ldc.i4.2
0x2965  or
0x2966  stloc.0
0x2967  ldloc.2
0x2968  ldstr    aAddressused// "addressused"
0x296d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x2972  castclass [mscorlib]System.String
0x2977  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x297c  brfalse.s loc_2982
0x297e  ldloc.0
0x297f  ldc.i4.1
0x2980  or
0x2981  stloc.0
0x2982  ldsfld   string [mscorlib]System.String::Empty
0x2987  stloc.3
0x2988  ldarg.1
0x2989  brfalse.s loc_29DF
0x298b  ldarg.1
0x298c  ldstr    aFax// "fax"
0x2991  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2996  brtrue.s loc_29C1
0x2998  ldarg.1
0x2999  ldstr    aEmail// "email"
0x299e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x29a3  brtrue.s loc_29C9
0x29a5  ldarg.1
0x29a6  ldstr    aPhonecall// "phonecall"
0x29ab  call     bool [mscorlib]System.String::op_Equality(string, string)
0x29b0  brtrue.s loc_29D1
0x29b2  ldarg.1
0x29b3  ldstr    aLetter// "letter"
0x29b8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x29bd  brtrue.s loc_29D9
0x29bf  br.s     loc_29DF
0x29c1  ldstr    aDonotfax// "donotfax"
0x29c6  stloc.3
0x29c7  br.s     loc_29DF
0x29c9  ldstr    aDonotemail// "donotemail"
0x29ce  stloc.3
0x29cf  br.s     loc_29DF
0x29d1  ldstr    aDonotphone// "donotphone"
0x29d6  stloc.3
0x29d7  br.s     loc_29DF
0x29d9  ldstr    aDonotpostalmai// "donotpostalmail"
0x29de  stloc.3
0x29df  ldloc.3
0x29e0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x29e5  brtrue.s loc_2A02
0x29e7  ldloc.2
0x29e8  ldloc.3
0x29e9  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29ee  brfalse.s loc_2A02
0x29f0  ldloc.2
0x29f1  ldloc.3
0x29f2  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29f7  unbox.any [mscorlib]System.Boolean
0x29fc  brfalse.s loc_2A02
0x29fe  ldloc.0
0x29ff  ldc.i4.4
0x2a00  or
0x2a01  stloc.0
0x2a02  ldloc.0
0x2a03  call     bool Microsoft.Crm.Common.Application.Platform.ActivityBase::FoundOneBadParty(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PartyStatusType partyStatus)
0x2a08  brtrue.s loc_2A1A
0x2a0a  ldloc.1
0x2a0b  ldc.i4.1
0x2a0c  add
0x2a0d  stloc.1
0x2a0e  ldloc.1
0x2a0f  ldarg.0
0x2a10  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x2a15  blt      loc_294E
0x2a1a  ldloc.0
0x2a1b  ret
```
