# Microsoft.Crm.Application.Components.UI.Radio::ConfigureHeader

- ea: `0x21190`
- end: `0x212b7`
- name: `Microsoft.Crm.Application.Components.UI.Radio::ConfigureHeader`
- size: `295`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3160`
- `0x3380`
- `0x38d0`
- `0x21110`
- `0x21190`
- `0x238a0`
- `0x238d0`
- `0x23b60`
- `0x23c50`
- `0x23f10`

## pseudocode

```c

```

## disassembly

```asm
0x21190  ldarg.0
0x21191  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::ConfigureHeader()
0x21196  ldarg.0
0x21197  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2119c  ldstr    aLocidDeverrorB_0// "LOCID_DEVERROR_BADDATATYPE_BOOL"
0x211a1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x211a6  ldstr    aDeverrorBaddat_1// "DevError.BadDataType.Boolean"
0x211ab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x211b0  ldc.i4.0
0x211b1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x211b6  ldarg.0
0x211b7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x211bc  ldstr    aLocidDeverrorB// "LOCID_DEVERROR_BADDATATYPE_INT"
0x211c1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x211c6  ldstr    aDeverrorBaddat_0// "DevError.BadDataType.Integer"
0x211cb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x211d0  ldc.i4.0
0x211d1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x211d6  ldarg.0
0x211d7  ldfld    class Microsoft.Crm.Application.Components.UI.RadioOptionCollection Microsoft.Crm.Application.Components.UI.Radio::_options
0x211dc  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x211e1  stloc.1
0x211e2  br.s     loc_211F6
0x211e4  ldloc.1
0x211e5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x211ea  castclass Microsoft.Crm.Application.Components.UI.RadioOption
0x211ef  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x211f4  leave.s  loc_21211
0x211f6  ldloc.1
0x211f7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x211fc  brtrue.s loc_211E4
0x211fe  leave.s  loc_21211
0x21200  ldloc.1
0x21201  isinst   [mscorlib]System.IDisposable
0x21206  stloc.2
0x21207  ldloc.2
0x21208  brfalse.s loc_21210
0x2120a  ldloc.2
0x2120b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x21210  endfinally
0x21211  ldarg.0
0x21212  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x21217  ldstr    aStaticFormsRad// "/_static/_forms/radiogroup.js"
0x2121c  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x21221  ldarg.0
0x21222  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x21227  brtrue.s loc_2122A
0x21229  ret
0x2122a  ldarg.0
0x2122b  ldstr    aMscrmForminput_17// "Mscrm.FormInputControl.RadioGroupBehavi"...
0x21230  ldnull
0x21231  ldnull
0x21232  ldnull
0x21233  ldarg.0
0x21234  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x21239  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x2123e  ldarg.0
0x2123f  ldarg.0
0x21240  call     instance string Microsoft.Crm.Application.Components.UI.Radio::get_ClientSideAttributeClassName()
0x21245  ldstr    aMscrmFormdatac// "Mscrm.FormDataControl"
0x2124a  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::RegisterClientSideControl(string attributeClassName, string controlClassName)
0x2124f  ldsfld   string [mscorlib]System.String::Empty
0x21254  stloc.0
0x21255  ldarg.0
0x21256  ldfld    string Microsoft.Crm.Application.Components.UI.Radio::_onChange
0x2125b  brfalse.s loc_212B6
0x2125d  ldarg.0
0x2125e  ldfld    string Microsoft.Crm.Application.Components.UI.Radio::_onChange
0x21263  callvirt instance int32 [mscorlib]System.String::get_Length()
0x21268  ldc.i4.0
0x21269  ble.s    loc_212B6
0x2126b  ldarg.0
0x2126c  ldfld    string Microsoft.Crm.Application.Components.UI.Radio::_onChange
0x21271  stloc.0
0x21272  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21277  ldstr    aVarRadioctrlMs// "var radioCtrl = Mscrm.FormControlInputB"...
0x2127c  ldc.i4.2
0x2127d  newarr   [mscorlib]System.Object
0x21282  dup
0x21283  ldc.i4.0
0x21284  ldarg.0
0x21285  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x2128a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x2128f  stelem.ref
0x21290  dup
0x21291  ldc.i4.1
0x21292  ldloc.0
0x21293  stelem.ref
0x21294  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x21299  stloc.3
0x2129a  ldarg.0
0x2129b  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x212a0  ldstr    aMscrmForminput_17// "Mscrm.FormInputControl.RadioGroupBehavi"...
0x212a5  ldarg.0
0x212a6  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x212ab  call     string [mscorlib]System.String::Concat(string, string)
0x212b0  ldloc.3
0x212b1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string key, string scriptBlock)
0x212b6  ret
```
