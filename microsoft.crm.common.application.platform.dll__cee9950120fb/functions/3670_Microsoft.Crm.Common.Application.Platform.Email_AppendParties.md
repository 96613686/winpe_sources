# Microsoft.Crm.Common.Application.Platform.Email::AppendParties

- ea: `0x3670`
- end: `0x36eb`
- name: `Microsoft.Crm.Common.Application.Platform.Email::AppendParties`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x35f0`

## callees

- `0x35a0`
- `0x3670`

## pseudocode

```c

```

## disassembly

```asm
0x3670  ldarg.0
0x3671  brfalse.s loc_367B
0x3673  ldarg.0
0x3674  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x3679  brtrue.s loc_367C
0x367b  ret
0x367c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x3681  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x3686  stloc.0
0x3687  ldarg.0
0x3688  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x368d  stloc.1
0x368e  br.s     loc_36D6
0x3690  ldloc.1
0x3691  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x3696  stloc.2
0x3697  ldarg.2
0x3698  brfalse.s loc_36C9
0x369a  ldloc.2
0x369b  ldstr    aPartyid// "partyid"
0x36a0  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x36a5  brfalse.s loc_36C9
0x36a7  ldloc.2
0x36a8  ldstr    aPartyid// "partyid"
0x36ad  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x36b2  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x36b7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x36bc  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x36c1  ldloc.0
0x36c2  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x36c7  brfalse.s loc_36D6
0x36c9  ldloc.2
0x36ca  call     void Microsoft.Crm.Common.Application.Platform.Email::ClearAttributesForNewEmail(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity currentSender)
0x36cf  ldarg.1
0x36d0  ldloc.2
0x36d1  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::Add(var<u1>)
0x36d6  ldloc.1
0x36d7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x36dc  brtrue.s loc_3690
0x36de  leave.s  loc_36EA
0x36e0  ldloc.1
0x36e1  brfalse.s loc_36E9
0x36e3  ldloc.1
0x36e4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36e9  endfinally
0x36ea  ret
```
