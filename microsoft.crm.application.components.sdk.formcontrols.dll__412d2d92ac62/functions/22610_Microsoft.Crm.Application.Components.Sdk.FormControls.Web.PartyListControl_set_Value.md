# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::set_Value

- ea: `0x22610`
- end: `0x22828`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::set_Value`
- size: `536`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x17990`
- `0x17cf0`
- `0x182d0`
- `0x1fc00`
- `0x22610`
- `0x22840`
- `0x22870`
- `0x22950`

## pseudocode

```c

```

## disassembly

```asm
0x22610  ldarg.0
0x22611  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x22616  isinst   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup
0x2261b  stloc.0
0x2261c  ldloc.0
0x2261d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItemCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup::get_Items()
0x22622  callvirt instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x22627  ldarg.1
0x22628  brfalse  loc_2281B
0x2262d  ldarg.1
0x2262e  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0x22633  stloc.1
0x22634  ldloc.1
0x22635  brfalse.s loc_22652
0x22637  ldloc.1
0x22638  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x2263d  ldc.i4.0
0x2263e  ble.s    loc_2266D
0x22640  ldloc.1
0x22641  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::get_EntityName()
0x22646  ldstr    aActivityparty// "activityparty"
0x2264b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x22650  brfalse.s loc_2266D
0x22652  ldstr    aWrongValueType_0// "Wrong value type is passed to the looku"...
0x22657  ldarg.0
0x22658  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2265d  ldstr    aThisControlOnl_7// ". This control only accepts a Applicati"...
0x22662  call     string [mscorlib]System.String::Concat(string, string, string)
0x22667  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2266c  throw
0x2266d  ldarg.0
0x2266e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x22673  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata
0x22678  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x2267d  stloc.2
0x2267e  ldstr    aMulti// "multi"
0x22683  ldarg.0
0x22684  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_LookupStyle()
0x22689  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2268e  brfalse.s loc_226BC
0x22690  ldloc.1
0x22691  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x22696  ldc.i4.1
0x22697  ble.s    loc_226BC
0x22699  ldloc.2
0x2269a  ldstr    aFaxpartylist// "faxpartylist"
0x2269f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x226a4  brtrue.s loc_226BC
0x226a6  ldstr    aThisLookupCanO// "This lookup can only display one item. "...
0x226ab  ldarg.0
0x226ac  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x226b1  call     string [mscorlib]System.String::Concat(string, string)
0x226b6  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x226bb  throw
0x226bc  ldloc.2
0x226bd  ldstr    aEmailpartylist// "emailpartylist"
0x226c2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x226c7  brtrue.s loc_226F8
0x226c9  ldloc.2
0x226ca  ldstr    aFaxpartylist// "faxpartylist"
0x226cf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x226d4  brtrue.s loc_22705
0x226d6  ldloc.2
0x226d7  ldstr    aPhonepartylist// "phonepartylist"
0x226dc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x226e1  brtrue.s loc_22761
0x226e3  ldloc.2
0x226e4  ldstr    aLetterpartylis// "letterpartylist"
0x226e9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x226ee  brtrue   loc_227BA
0x226f3  br       loc_22813
0x226f8  ldarg.0
0x226f9  ldloc.1
0x226fa  ldloc.0
0x226fb  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::AddEmailPartyMembersToLookup(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection partyCollection, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup innerLookup)
0x22700  br       loc_2281B
0x22705  ldarg.0
0x22706  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x2270b  ldstr    aStatecode// "statecode"
0x22710  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x22715  stloc.s  4
0x22717  ldloc.s  4
0x22719  brtrue.s loc_2272D
0x2271b  ldc.i4.0
0x2271c  stloc.s  5
0x2271e  ldloca.s 5
0x22720  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.FaxState
0x22726  callvirt instance string [mscorlib]System.Object::ToString()
0x2272b  br.s     loc_22734
0x2272d  ldloc.s  4
0x2272f  castclass [mscorlib]System.String
0x22734  stloc.3
0x22735  ldarg.0
0x22736  ldloc.1
0x22737  ldloc.0
0x22738  ldstr    aDonotfax// "donotfax"
0x2273d  ldloc.3
0x2273e  ldc.i4.0
0x2273f  stloc.s  5
0x22741  ldloca.s 5
0x22743  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.FaxState
0x22749  callvirt instance string [mscorlib]System.Object::ToString()
0x2274e  ldc.i4.5
0x2274f  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x22754  ldc.i4.0
0x22755  ceq
0x22757  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::AddActivityPartyMembersToLookup(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection partyCollection, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup innerLookup, string doNotSendFieldName, bool isEntityStateOpen)
0x2275c  br       loc_2281B
0x22761  ldarg.0
0x22762  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x22767  ldstr    aStatecode// "statecode"
0x2276c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x22771  stloc.s  4
0x22773  ldloc.s  4
0x22775  brtrue.s loc_22789
0x22777  ldc.i4.0
0x22778  stloc.s  6
0x2277a  ldloca.s 6
0x2277c  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.PhoneCallState
0x22782  callvirt instance string [mscorlib]System.Object::ToString()
0x22787  br.s     loc_22790
0x22789  ldloc.s  4
0x2278b  castclass [mscorlib]System.String
0x22790  stloc.3
0x22791  ldarg.0
0x22792  ldloc.1
0x22793  ldloc.0
0x22794  ldstr    aDonotphone// "donotphone"
0x22799  ldloc.3
0x2279a  ldc.i4.0
0x2279b  stloc.s  6
0x2279d  ldloca.s 6
0x2279f  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.PhoneCallState
0x227a5  callvirt instance string [mscorlib]System.Object::ToString()
0x227aa  ldc.i4.5
0x227ab  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x227b0  ldc.i4.0
0x227b1  ceq
0x227b3  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::AddActivityPartyMembersToLookup(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection partyCollection, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup innerLookup, string doNotSendFieldName, bool isEntityStateOpen)
0x227b8  br.s     loc_2281B
0x227ba  ldarg.0
0x227bb  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x227c0  ldstr    aStatecode// "statecode"
0x227c5  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x227ca  stloc.s  4
0x227cc  ldloc.s  4
0x227ce  brtrue.s loc_227E2
0x227d0  ldc.i4.0
0x227d1  stloc.s  7
0x227d3  ldloca.s 7
0x227d5  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.LetterState
0x227db  callvirt instance string [mscorlib]System.Object::ToString()
0x227e0  br.s     loc_227E9
0x227e2  ldloc.s  4
0x227e4  castclass [mscorlib]System.String
0x227e9  stloc.3
0x227ea  ldarg.0
0x227eb  ldloc.1
0x227ec  ldloc.0
0x227ed  ldstr    aDonotpostalmai// "donotpostalmail"
0x227f2  ldloc.3
0x227f3  ldc.i4.0
0x227f4  stloc.s  7
0x227f6  ldloca.s 7
0x227f8  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.LetterState
0x227fe  callvirt instance string [mscorlib]System.Object::ToString()
0x22803  ldc.i4.5
0x22804  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x22809  ldc.i4.0
0x2280a  ceq
0x2280c  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::AddActivityPartyMembersToLookup(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection partyCollection, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup innerLookup, string doNotSendFieldName, bool isEntityStateOpen)
0x22811  br.s     loc_2281B
0x22813  ldarg.0
0x22814  ldloc.1
0x22815  ldloc.0
0x22816  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::AddPartyMembersToLookup(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection partyCollection, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup innerLookup)
0x2281b  ldarg.0
0x2281c  ldarg.1
0x2281d  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0x22822  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::_partyList
0x22827  ret
```
