# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::AddEmailPartyMembersToLookup

- ea: `0x22870`
- end: `0x22946`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::AddEmailPartyMembersToLookup`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x22610`

## callees

- `0x17990`
- `0x22870`
- `0x229b0`

## string_xrefs

- `0x2291d`: `OpenItemForceSubmit(new Sys.UI.DomEvent(event))`

## pseudocode

```c

```

## disassembly

```asm
0x22870  ldc.i4.0
0x22871  stloc.2
0x22872  ldloca.s 2
0x22874  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.EmailState
0x2287a  callvirt instance string [mscorlib]System.Object::ToString()
0x2287f  stloc.0
0x22880  ldarg.0
0x22881  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x22886  ldstr    aStatecode// "statecode"
0x2288b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x22890  stloc.1
0x22891  ldloc.1
0x22892  brfalse.s loc_2289B
0x22894  ldloc.1
0x22895  castclass [mscorlib]System.String
0x2289a  stloc.0
0x2289b  ldc.i4.0
0x2289c  stloc.3
0x2289d  br       loc_22939
0x228a2  ldarg.1
0x228a3  ldloc.3
0x228a4  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x228a9  stloc.s  4
0x228ab  ldarg.0
0x228ac  ldloc.s  4
0x228ae  ldloc.3
0x228af  call     instance class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListLookupItem Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::CreateLookupItemFromActivityParty(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity party, int32 index)
0x228b4  stloc.s  5
0x228b6  ldloc.s  5
0x228b8  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TypedLookupItem::get_Type()
0x228bd  brfalse.s loc_22927
0x228bf  ldloc.0
0x228c0  ldc.i4.0
0x228c1  stloc.2
0x228c2  ldloca.s 2
0x228c4  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.EmailState
0x228ca  callvirt instance string [mscorlib]System.Object::ToString()
0x228cf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x228d4  brfalse.s loc_22927
0x228d6  ldloc.s  4
0x228d8  ldstr    aAddressused// "addressused"
0x228dd  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x228e2  castclass [mscorlib]System.String
0x228e7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x228ec  brtrue.s loc_2290F
0x228ee  ldloc.s  4
0x228f0  ldstr    aDonotemail// "donotemail"
0x228f5  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x228fa  brfalse.s loc_22927
0x228fc  ldloc.s  4
0x228fe  ldstr    aDonotemail// "donotemail"
0x22903  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x22908  unbox.any [mscorlib]System.Boolean
0x2290d  brfalse.s loc_22927
0x2290f  ldloc.s  5
0x22911  ldstr    aMsCrmLookupPar_0// "ms-crm-Lookup-PartyItem-NoAddress"
0x22916  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::set_Style(string)
0x2291b  ldloc.s  5
0x2291d  ldstr    aOpenitemforces// "OpenItemForceSubmit(new Sys.UI.DomEvent"...
0x22922  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::set_Callback(string)
0x22927  ldarg.2
0x22928  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItemCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup::get_Items()
0x2292d  ldloc.s  5
0x2292f  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItemCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem)
0x22934  pop
0x22935  ldloc.3
0x22936  ldc.i4.1
0x22937  add
0x22938  stloc.3
0x22939  ldloc.3
0x2293a  ldarg.1
0x2293b  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x22940  blt      loc_228A2
0x22945  ret
```
