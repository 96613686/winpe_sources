# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::ConfigureControl

- ea: `0x18670`
- end: `0x18877`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::ConfigureControl`
- size: `519`
- prototype: ``
- caller_count: `9`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x15990`
- `0x1ace0`
- `0x1ba90`
- `0x1ec90`
- `0x1ee20`
- `0x1fe30`
- `0x23a60`
- `0x23dd0`
- `0x2aba0`

## callees

- `0x17cf0`
- `0x17d00`
- `0x182d0`
- `0x18360`
- `0x18430`
- `0x18480`
- `0x184c0`
- `0x18620`
- `0x18670`

## string_xrefs

- `0x18722`: `Recommended_Fields_Background_Color`

## pseudocode

```c

```

## disassembly

```asm
0x18670  ldarg.0
0x18671  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::ConfigureControl()
0x18676  ldarg.0
0x18677  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Required()
0x1867c  brfalse.s loc_186ED
0x1867e  ldarg.0
0x1867f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x18684  ldstr    aReq// "req"
0x18689  ldstr    a2// "2"
0x1868e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x18693  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x18698  ldstr    aRequiredFields// "Required_Fields_Background_Color"
0x1869d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x186a2  stloc.0
0x186a3  ldloc.0
0x186a4  brfalse  loc_18783
0x186a9  ldloc.0
0x186aa  callvirt instance int32 [mscorlib]System.String::get_Length()
0x186af  brfalse  loc_18783
0x186b4  ldarg.0
0x186b5  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x186ba  isinst   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI
0x186bf  brtrue.s loc_186DC
0x186c1  ldarg.0
0x186c2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x186c7  ldstr    aStyle_0// "Style"
0x186cc  ldstr    aBackgroundColo_1// "background-color:"
0x186d1  ldloc.0
0x186d2  call     string [mscorlib]System.String::Concat(string, string)
0x186d7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x186dc  ldarg.0
0x186dd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x186e2  ldc.i4.2
0x186e3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::set_Required(int32)
0x186e8  br       loc_18783
0x186ed  ldarg.0
0x186ee  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::_metadata
0x186f3  brfalse.s loc_18702
0x186f5  ldarg.0
0x186f6  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::_metadata
0x186fb  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x18700  br.s     loc_18703
0x18702  ldc.i4.0
0x18703  stloc.1
0x18704  ldloc.1
0x18705  ldc.i4.3
0x18706  bne.un.s loc_1876E
0x18708  ldarg.0
0x18709  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x1870e  ldstr    aReq// "req"
0x18713  ldstr    a3// "3"
0x18718  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x1871d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x18722  ldstr    aRecommendedFie// "Recommended_Fields_Background_Color"
0x18727  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1872c  stloc.2
0x1872d  ldloc.2
0x1872e  brfalse.s loc_18783
0x18730  ldloc.2
0x18731  callvirt instance int32 [mscorlib]System.String::get_Length()
0x18736  brfalse.s loc_18783
0x18738  ldarg.0
0x18739  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x1873e  isinst   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI
0x18743  brtrue.s loc_18760
0x18745  ldarg.0
0x18746  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x1874b  ldstr    aStyle_0// "Style"
0x18750  ldstr    aBackgroundColo_1// "background-color:"
0x18755  ldloc.2
0x18756  call     string [mscorlib]System.String::Concat(string, string)
0x1875b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x18760  ldarg.0
0x18761  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x18766  ldc.i4.3
0x18767  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::set_Required(int32)
0x1876c  br.s     loc_18783
0x1876e  ldarg.0
0x1876f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x18774  ldstr    aReq// "req"
0x18779  ldstr    a0// "0"
0x1877e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x18783  ldarg.0
0x18784  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x18789  ldstr    aStyle_0// "Style"
0x1878e  ldstr    aMsImeMode_0// "-ms-ime-mode:"
0x18793  ldarg.0
0x18794  ldfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::_imeMode
0x18799  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode
0x1879e  ldstr    aG// "g"
0x187a3  call     instance string [mscorlib]System.Enum::ToString(string)
0x187a8  call     string [mscorlib]System.String::Concat(string, string)
0x187ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x187b2  ldarg.0
0x187b3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x187b8  ldarg.0
0x187b9  ldfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::_imeMode
0x187be  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::set_ImeMode(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode)
0x187c3  ldarg.0
0x187c4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x187c9  brtrue.s loc_187E1
0x187cb  ldarg.0
0x187cc  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x187d1  ldstr    aDonotsubmit// "DoNotSubmit"
0x187d6  ldstr    a1_0// "1"
0x187db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x187e0  ret
0x187e1  ldarg.0
0x187e2  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_RegisterClientSideAttribute()
0x187e7  brfalse  loc_18876
0x187ec  ldarg.0
0x187ed  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x187f2  ldstr    aAttrname_0// "attrName"
0x187f7  ldarg.0
0x187f8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x187fd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x18802  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x18807  ldarg.0
0x18808  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_IsSecuredCreate()
0x1880d  brtrue.s loc_18812
0x1880f  ldc.i4.1
0x18810  br.s     loc_18813
0x18812  ldc.i4.0
0x18813  ldarg.0
0x18814  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_IsSecuredRead()
0x18819  brtrue.s loc_1881E
0x1881b  ldc.i4.2
0x1881c  br.s     loc_1881F
0x1881e  ldc.i4.0
0x1881f  or
0x18820  ldarg.0
0x18821  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_IsSecuredUpdate()
0x18826  brtrue.s loc_1882B
0x18828  ldc.i4.4
0x18829  br.s     loc_1882C
0x1882b  ldc.i4.0
0x1882c  or
0x1882d  stloc.3
0x1882e  ldarg.0
0x1882f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x18834  ldstr    aAttrpriv_0// "attrPriv"
0x18839  ldloc.3
0x1883a  box      Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FormDataAttributePrivileges
0x1883f  ldstr    aD// "D"
0x18844  call     instance string [mscorlib]System.Enum::ToString(string)
0x18849  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x1884e  ldarg.0
0x1884f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x18854  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x18859  stloc.s  4
0x1885b  ldloc.s  4
0x1885d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x18862  brtrue.s loc_18876
0x18864  ldarg.0
0x18865  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x1886a  ldstr    aAttrformat_0// "attrFormat"
0x1886f  ldloc.s  4
0x18871  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x18876  ret
```
