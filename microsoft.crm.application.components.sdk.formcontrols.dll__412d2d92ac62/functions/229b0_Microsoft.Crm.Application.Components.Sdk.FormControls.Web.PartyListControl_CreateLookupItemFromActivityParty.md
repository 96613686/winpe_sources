# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::CreateLookupItemFromActivityParty

- ea: `0x229b0`
- end: `0x22b55`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::CreateLookupItemFromActivityParty`
- size: `421`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x22840`
- `0x22870`
- `0x22950`

## callees

- `0x1f360`
- `0x22430`
- `0x229b0`
- `0x22b60`

## string_xrefs

- `0x22b05`: `ispartydeleted`
- `0x22b12`: `ispartydeleted`

## pseudocode

```c

```

## disassembly

```asm
0x229b0  ldarg.1
0x229b1  ldstr    aPartyid// "partyid"
0x229b6  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x229bb  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x229c0  stloc.0
0x229c1  ldloc.0
0x229c2  brfalse.s loc_229CC
0x229c4  ldloc.0
0x229c5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Name()
0x229ca  br.s     loc_229D1
0x229cc  ldsfld   string [mscorlib]System.String::Empty
0x229d1  stloc.1
0x229d2  ldloc.0
0x229d3  brfalse.s loc_229DD
0x229d5  ldloc.0
0x229d6  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Type()
0x229db  br.s     loc_229E2
0x229dd  ldc.i4   0x23F6
0x229e2  ldloc.0
0x229e3  brfalse.s loc_229ED
0x229e5  ldloc.0
0x229e6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x229eb  br.s     loc_22A1A
0x229ed  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x229f2  stloc.s  9
0x229f4  ldloca.s 9
0x229f6  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x229fb  stloc.s  0xA
0x229fd  ldloca.s 0xA
0x229ff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22a04  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x22a09  ldarga.s 2
0x22a0b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22a10  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x22a15  call     string [mscorlib]System.String::Concat(string, string)
0x22a1a  stloc.2
0x22a1b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x22a20  stloc.3
0x22a21  ldarg.1
0x22a22  ldstr    aResourcespecid// "resourcespecid"
0x22a27  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x22a2c  brfalse.s loc_22A4E
0x22a2e  ldarg.1
0x22a2f  ldstr    aResourcespecid// "resourcespecid"
0x22a34  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x22a39  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x22a3e  stloc.s  0xB
0x22a40  ldloca.s 3
0x22a42  ldloc.s  0xB
0x22a44  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x22a49  call     instance void [mscorlib]System.Guid::.ctor(string)
0x22a4e  ldc.r8   -1.797693134862316e308
0x22a57  stloc.s  4
0x22a59  ldarg.1
0x22a5a  ldstr    aEffort// "effort"
0x22a5f  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x22a64  brfalse.s loc_22A78
0x22a66  ldarg.1
0x22a67  ldstr    aEffort// "effort"
0x22a6c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x22a71  unbox.any [mscorlib]System.Double
0x22a76  stloc.s  4
0x22a78  ldsfld   string [mscorlib]System.String::Empty
0x22a7d  stloc.s  5
0x22a7f  ldarg.1
0x22a80  ldstr    aExchangeentryi// "exchangeentryid"
0x22a85  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x22a8a  brfalse.s loc_22A9E
0x22a8c  ldarg.1
0x22a8d  ldstr    aExchangeentryi// "exchangeentryid"
0x22a92  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x22a97  castclass [mscorlib]System.String
0x22a9c  stloc.s  5
0x22a9e  ldsfld   string [mscorlib]System.String::Empty
0x22aa3  stloc.s  6
0x22aa5  ldarg.1
0x22aa6  ldstr    aActivitypartyi// "activitypartyid"
0x22aab  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x22ab0  brfalse.s loc_22AC9
0x22ab2  ldarg.1
0x22ab3  ldstr    aActivitypartyi// "activitypartyid"
0x22ab8  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x22abd  unbox.any [mscorlib]System.Guid
0x22ac2  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x22ac7  stloc.s  6
0x22ac9  ldloc.1
0x22aca  ldloc.3
0x22acb  ldloc.s  4
0x22acd  ldloc.s  6
0x22acf  ldloc.s  5
0x22ad1  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListLookupItem::.ctor(int32 type, string name, valuetype [mscorlib]System.Guid resourceSpecId, float64 effort, string activityPartyId, string exchangeEntryId)
0x22ad6  stloc.s  7
0x22ad8  ldloc.s  7
0x22ada  ldloc.2
0x22adb  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x22ae0  ldarg.1
0x22ae1  ldstr    aAddressused// "addressused"
0x22ae6  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x22aeb  isinst   [mscorlib]System.String
0x22af0  stloc.s  8
0x22af2  ldloc.s  8
0x22af4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x22af9  brtrue.s loc_22B04
0x22afb  ldloc.s  7
0x22afd  ldloc.s  8
0x22aff  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmLookupItem::set_SipAddress(string value)
0x22b04  ldarg.1
0x22b05  ldstr    aIspartydeleted// "ispartydeleted"
0x22b0a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x22b0f  brfalse.s loc_22B3B
0x22b11  ldarg.1
0x22b12  ldstr    aIspartydeleted// "ispartydeleted"
0x22b17  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x22b1c  unbox.any [mscorlib]System.Boolean
0x22b21  brfalse.s loc_22B3B
0x22b23  ldloc.s  7
0x22b25  ldsfld   string [mscorlib]System.String::Empty
0x22b2a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::set_Callback(string)
0x22b2f  ldloc.s  7
0x22b31  ldsfld   string [mscorlib]System.String::Empty
0x22b36  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::set_Style(string)
0x22b3b  ldloc.s  7
0x22b3d  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TypedLookupItem::get_Type()
0x22b42  ldc.i4   0x23F6
0x22b47  bne.un.s loc_22B52
0x22b49  ldarg.0
0x22b4a  ldarg.1
0x22b4b  ldloc.s  7
0x22b4d  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::PopulateUnresolvedPartyItem(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity party, class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListLookupItem partyItem)
0x22b52  ldloc.s  7
0x22b54  ret
```
