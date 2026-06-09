# Microsoft.Crm.Common.Application.Platform.ActivityBase::GetRecipientsStatusType

- ea: `0x2a30`
- end: `0x2a87`
- name: `Microsoft.Crm.Common.Application.Platform.ActivityBase::GetRecipientsStatusType`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x2a20`
- `0x6da0`

## callees

- `0x28c0`
- `0x2a30`
- `0x2a90`
- `0x2b70`

## pseudocode

```c

```

## disassembly

```asm
0x2a30  ldc.i4.0
0x2a31  stloc.0
0x2a32  ldarg.0
0x2a33  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_LogicalName()
0x2a38  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Crm.Common.Application.Platform.ActivityBase::GetPartyListProperties(string entityName)
0x2a3d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x2a42  stloc.1
0x2a43  br.s     loc_2A71
0x2a45  ldloc.1
0x2a46  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x2a4b  stloc.2
0x2a4c  ldloc.0
0x2a4d  ldarg.0
0x2a4e  ldloc.2
0x2a4f  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x2a54  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0x2a59  ldloc.2
0x2a5a  ldarg.0
0x2a5b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_LogicalName()
0x2a60  call     valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PartyStatusType Microsoft.Crm.Common.Application.Platform.ActivityBase::GetRecipientsPartyStatusType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection recipients, string partyProperty, string activityLogicalName)
0x2a65  or
0x2a66  stloc.0
0x2a67  ldloc.0
0x2a68  call     bool Microsoft.Crm.Common.Application.Platform.ActivityBase::FoundOneBadParty(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PartyStatusType partyStatus)
0x2a6d  brfalse.s loc_2A71
0x2a6f  leave.s  loc_2A85
0x2a71  ldloc.1
0x2a72  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2a77  brtrue.s loc_2A45
0x2a79  leave.s  loc_2A85
0x2a7b  ldloc.1
0x2a7c  brfalse.s loc_2A84
0x2a7e  ldloc.1
0x2a7f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a84  endfinally
0x2a85  ldloc.0
0x2a86  ret
```
