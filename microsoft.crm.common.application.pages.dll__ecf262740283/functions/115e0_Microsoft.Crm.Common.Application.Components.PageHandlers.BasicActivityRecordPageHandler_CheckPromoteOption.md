# Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::CheckPromoteOption

- ea: `0x115e0`
- end: `0x117d7`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::CheckPromoteOption`
- size: `503`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x114f0`
- `0x115e0`

## pseudocode

```c

```

## disassembly

```asm
0x115e0  ldarg.0
0x115e1  call     instance bool Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_PromoteToResponse()
0x115e6  brtrue.s loc_115E9
0x115e8  ret
0x115e9  ldc.i4.0
0x115ea  stloc.0
0x115eb  ldc.i4.0
0x115ec  stloc.1
0x115ed  ldc.i4.0
0x115ee  stloc.2
0x115ef  ldarg.2
0x115f0  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x115f5  ldstr    aRegardingobjec_0// "regardingobjectid"
0x115fa  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x115ff  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x11604  stloc.3
0x11605  ldarg.2
0x11606  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x1160b  ldstr    aDirectioncode// "directioncode"
0x11610  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x11615  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x1161a  stloc.s  4
0x1161c  ldarg.2
0x1161d  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x11622  ldstr    aFrom// "from"
0x11627  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x1162c  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x11631  stloc.s  5
0x11633  ldarg.2
0x11634  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x11639  ldstr    aTo// "to"
0x1163e  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x11643  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x11648  stloc.s  6
0x1164a  ldarg.2
0x1164b  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x11650  ldstr    aRequiredattend// "requiredattendees"
0x11655  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x1165a  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x1165f  stloc.s  7
0x11661  ldloc.3
0x11662  brfalse.s loc_116AE
0x11664  ldloc.3
0x11665  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::get_Value()
0x1166a  brfalse.s loc_116AE
0x1166c  ldloc.3
0x1166d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::get_Value()
0x11672  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValueCollection
0x11677  stloc.s  9
0x11679  ldloc.s  9
0x1167b  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x11680  ldc.i4.1
0x11681  bne.un.s loc_116AE
0x11683  ldloc.s  9
0x11685  ldc.i4.0
0x11686  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValueCollection::get_Item(int32)
0x1168b  stloc.s  0xA
0x1168d  ldloc.s  0xA
0x1168f  brfalse.s loc_116AE
0x11691  ldloc.s  0xA
0x11693  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Type()
0x11698  stloc.s  0xB
0x1169a  ldloc.s  0xB
0x1169c  ldc.i4   0x1132
0x116a1  beq.s    loc_116AC
0x116a3  ldloc.s  0xB
0x116a5  ldc.i4   0x1136
0x116aa  bne.un.s loc_116AE
0x116ac  ldc.i4.1
0x116ad  stloc.0
0x116ae  ldloc.s  4
0x116b0  brfalse.s loc_116D0
0x116b2  ldloc.s  4
0x116b4  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::get_Value()
0x116b9  brfalse.s loc_116D0
0x116bb  ldloc.s  4
0x116bd  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::get_Value()
0x116c2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x116c7  call     bool [mscorlib]System.Convert::ToBoolean(object, class [mscorlib]System.IFormatProvider)
0x116cc  ldc.i4.0
0x116cd  ceq
0x116cf  stloc.2
0x116d0  ldnull
0x116d1  stloc.s  8
0x116d3  ldloc.2
0x116d4  brfalse.s loc_116F3
0x116d6  ldloc.s  5
0x116d8  brfalse.s loc_1170E
0x116da  ldloc.s  5
0x116dc  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::get_Value()
0x116e1  brfalse.s loc_1170E
0x116e3  ldloc.s  5
0x116e5  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::get_Value()
0x116ea  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0x116ef  stloc.s  8
0x116f1  br.s     loc_1170E
0x116f3  ldloc.s  6
0x116f5  brfalse.s loc_1170E
0x116f7  ldloc.s  6
0x116f9  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::get_Value()
0x116fe  brfalse.s loc_1170E
0x11700  ldloc.s  6
0x11702  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::get_Value()
0x11707  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0x1170c  stloc.s  8
0x1170e  ldarg.0
0x1170f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentType()
0x11714  ldstr    aAppointment// "appointment"
0x11719  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1171e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11723  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::op_Equality(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x11728  brfalse.s loc_11745
0x1172a  ldloc.s  7
0x1172c  brfalse.s loc_11745
0x1172e  ldloc.s  7
0x11730  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::get_Value()
0x11735  brfalse.s loc_11745
0x11737  ldloc.s  7
0x11739  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::get_Value()
0x1173e  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0x11743  stloc.s  8
0x11745  ldloc.s  8
0x11747  brfalse.s loc_117AE
0x11749  ldloc.s  8
0x1174b  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x11750  ldc.i4.1
0x11751  bne.un.s loc_117AE
0x11753  ldloc.s  8
0x11755  ldc.i4.0
0x11756  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x1175b  stloc.s  0xC
0x1175d  ldloc.s  0xC
0x1175f  brfalse.s loc_117AE
0x11761  ldloc.s  0xC
0x11763  ldstr    aPartyobjecttyp// "partyobjecttypecode"
0x11768  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1176d  brfalse.s loc_117AE
0x1176f  ldloc.s  0xC
0x11771  ldstr    aPartyobjecttyp// "partyobjecttypecode"
0x11776  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1177b  castclass [mscorlib]System.String
0x11780  stloc.s  0xD
0x11782  ldloc.s  0xD
0x11784  ldstr    aAccount// "account"
0x11789  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1178e  brtrue.s loc_117AC
0x11790  ldloc.s  0xD
0x11792  ldstr    aContact// "contact"
0x11797  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1179c  brtrue.s loc_117AC
0x1179e  ldloc.s  0xD
0x117a0  ldstr    aLead// "lead"
0x117a5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x117aa  brfalse.s loc_117AE
0x117ac  ldc.i4.1
0x117ad  stloc.1
0x117ae  ldloc.0
0x117af  ldloc.1
0x117b0  and
0x117b1  brfalse.s loc_117C5
0x117b3  ldarg.0
0x117b4  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x117b9  ldstr    aLocidPromoteTo// "LOCID_PROMOTE_TO_RESPONSE"
0x117be  ldc.i4.1
0x117bf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x117c4  ret
0x117c5  ldarg.0
0x117c6  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x117cb  ldstr    aLocidPromoteTo// "LOCID_PROMOTE_TO_RESPONSE"
0x117d0  ldc.i4.0
0x117d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x117d6  ret
```
