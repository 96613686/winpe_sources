# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.HiddenInputControl::ConfigureHeader

- ea: `0xe520`
- end: `0xe810`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.HiddenInputControl::ConfigureHeader`
- size: `752`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1450`
- `0x1550`
- `0xe520`
- `0x2cb60`

## string_xrefs

- `0xe777`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0xe787`: `/_static/_common/scripts/Mscrm.Caching.js`

## pseudocode

```c

```

## disassembly

```asm
0xe520  ldarg.0
0xe521  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0xe526  ldarg.0
0xe527  ldc.i4.0
0xe528  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::set_Required(bool value)
0xe52d  ldarg.0
0xe52e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xe533  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0xe538  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0xe53d  stloc.0
0xe53e  ldloc.0
0xe53f  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0xe544  stloc.1
0xe545  ldloc.1
0xe546  ldc.i4   0xBA4B77EF
0xe54b  bgt.un.s loc_E5C1
0xe54d  ldloc.1
0xe54e  ldc.i4   0x783132F6
0xe553  bgt.un.s loc_E58B
0xe555  ldloc.1
0xe556  ldc.i4   0x5BC874BE
0xe55b  bgt.un.s loc_E574
0xe55d  ldloc.1
0xe55e  ldc.i4   0x1F088D4C
0xe563  beq      loc_E67B
0xe568  ldloc.1
0xe569  ldc.i4   0x5BC874BE
0xe56e  beq      loc_E648
0xe573  ret
0xe574  ldloc.1
0xe575  ldc.i4   0x60CAE230
0xe57a  beq      loc_E700
0xe57f  ldloc.1
0xe580  ldc.i4   0x783132F6
0xe585  beq      loc_E722
0xe58a  ret
0xe58b  ldloc.1
0xe58c  ldc.i4   0xA4BDAA19
0xe591  bgt.un.s loc_E5AA
0xe593  ldloc.1
0xe594  ldc.i4   0x95E97E5E
0xe599  beq      loc_E69D
0xe59e  ldloc.1
0xe59f  ldc.i4   0xA4BDAA19
0xe5a4  beq      loc_E6BF
0xe5a9  ret
0xe5aa  ldloc.1
0xe5ab  ldc.i4   0xA6C45D85
0xe5b0  beq      loc_E68C
0xe5b5  ldloc.1
0xe5b6  ldc.i4   0xBA4B77EF
0xe5bb  beq      loc_E733
0xe5c0  ret
0xe5c1  ldloc.1
0xe5c2  ldc.i4   0xD9844140
0xe5c7  bgt.un.s loc_E5FC
0xe5c9  ldloc.1
0xe5ca  ldc.i4   0xC1C33E1F
0xe5cf  bgt.un.s loc_E5E5
0xe5d1  ldloc.1
0xe5d2  ldc.i4   0xBDE64E3E
0xe5d7  beq.s    loc_E637
0xe5d9  ldloc.1
0xe5da  ldc.i4   0xC1C33E1F
0xe5df  beq      loc_E6F2
0xe5e4  ret
0xe5e5  ldloc.1
0xe5e6  ldc.i4   0xCCEA6D90
0xe5eb  beq      loc_E741
0xe5f0  ldloc.1
0xe5f1  ldc.i4   0xD9844140
0xe5f6  beq      loc_E711
0xe5fb  ret
0xe5fc  ldloc.1
0xe5fd  ldc.i4   0xE150C94F
0xe602  bgt.un.s loc_E618
0xe604  ldloc.1
0xe605  ldc.i4   0xE0333069
0xe60a  beq.s    loc_E66A
0xe60c  ldloc.1
0xe60d  ldc.i4   0xE150C94F
0xe612  beq      loc_E6AE
0xe617  ret
0xe618  ldloc.1
0xe619  ldc.i4   0xE98BD702
0xe61e  beq.s    loc_E659
0xe620  ldloc.1
0xe621  ldc.i4   0xF5674CD4
0xe626  beq      loc_E6E1
0xe62b  ldloc.1
0xe62c  ldc.i4   0xF758858B
0xe631  beq      loc_E6D0
0xe636  ret
0xe637  ldloc.0
0xe638  ldstr    aText// "text"
0xe63d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe642  brtrue   loc_E74F
0xe647  ret
0xe648  ldloc.0
0xe649  ldstr    aNvarchar// "nvarchar"
0xe64e  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe653  brtrue   loc_E74F
0xe658  ret
0xe659  ldloc.0
0xe65a  ldstr    aNtext// "ntext"
0xe65f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe664  brtrue   loc_E74F
0xe669  ret
0xe66a  ldloc.0
0xe66b  ldstr    aNchar// "nchar"
0xe670  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe675  brtrue   loc_E74F
0xe67a  ret
0xe67b  ldloc.0
0xe67c  ldstr    aDecimal// "decimal"
0xe681  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe686  brtrue   loc_E760
0xe68b  ret
0xe68c  ldloc.0
0xe68d  ldstr    aFloat// "float"
0xe692  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe697  brtrue   loc_E760
0xe69c  ret
0xe69d  ldloc.0
0xe69e  ldstr    aInt// "int"
0xe6a3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe6a8  brtrue   loc_E760
0xe6ad  ret
0xe6ae  ldloc.0
0xe6af  ldstr    aMoney// "money"
0xe6b4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe6b9  brtrue   loc_E760
0xe6be  ret
0xe6bf  ldloc.0
0xe6c0  ldstr    aCustomer// "customer"
0xe6c5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe6ca  brtrue   loc_E771
0xe6cf  ret
0xe6d0  ldloc.0
0xe6d1  ldstr    aLookup// "lookup"
0xe6d6  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe6db  brtrue   loc_E771
0xe6e0  ret
0xe6e1  ldloc.0
0xe6e2  ldstr    aOwner// "owner"
0xe6e7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe6ec  brtrue   loc_E771
0xe6f1  ret
0xe6f2  ldloc.0
0xe6f3  ldstr    aPartylist// "partylist"
0xe6f8  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe6fd  brtrue.s loc_E771
0xe6ff  ret
0xe700  ldloc.0
0xe701  ldstr    aBit// "bit"
0xe706  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe70b  brtrue   loc_E7B2
0xe710  ret
0xe711  ldloc.0
0xe712  ldstr    aPicklist// "picklist"
0xe717  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe71c  brtrue   loc_E7B2
0xe721  ret
0xe722  ldloc.0
0xe723  ldstr    aState// "state"
0xe728  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe72d  brtrue   loc_E7B2
0xe732  ret
0xe733  ldloc.0
0xe734  ldstr    aStatus// "status"
0xe739  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe73e  brtrue.s loc_E7B2
0xe740  ret
0xe741  ldloc.0
0xe742  ldstr    aDatetime// "datetime"
0xe747  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe74c  brtrue.s loc_E7C3
0xe74e  ret
0xe74f  ldarg.0
0xe750  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe755  ldstr    aStaticFormsTex// "/_static/_forms/textinputbehavior.js"
0xe75a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe75f  ret
0xe760  ldarg.0
0xe761  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe766  ldstr    aStaticFormsNum// "/_static/_forms/numberinputbehavior.js"
0xe76b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe770  ret
0xe771  ldarg.0
0xe772  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe777  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/CrmInternalUti"...
0xe77c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe781  ldarg.0
0xe782  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe787  ldstr    aStaticCommonSc_7// "/_static/_common/scripts/Mscrm.Caching."...
0xe78c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe791  ldarg.0
0xe792  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe797  ldstr    aStaticControls// "/_static/_controls/lookup/lookup.js"
0xe79c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe7a1  ldarg.0
0xe7a2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe7a7  ldstr    aStaticFormsLoo// "/_static/_forms/LookupBehavior.js"
0xe7ac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe7b1  ret
0xe7b2  ldarg.0
0xe7b3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe7b8  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0xe7bd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe7c2  ret
0xe7c3  ldarg.0
0xe7c4  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe7c9  ldc.i4.1
0xe7ca  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0xe7cf  ldarg.0
0xe7d0  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe7d5  ldstr    aStaticControls_4// "/_static/_controls/datetime/date.js"
0xe7da  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe7df  ldarg.0
0xe7e0  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe7e5  ldstr    aStaticControls_5// "/_static/_controls/datetime/time.js"
0xe7ea  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe7ef  ldarg.0
0xe7f0  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe7f5  ldstr    aStaticControls_6// "/_static/_controls/editableselect/edita"...
0xe7fa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe7ff  ldarg.0
0xe800  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xe805  ldstr    aStaticFormsDat// "/_static/_forms/datetime.js"
0xe80a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe80f  ret
```
