# Microsoft.Crm.Application.Components.UI.Number::ConfigureHeader

- ea: `0x20820`
- end: `0x20904`
- name: `Microsoft.Crm.Application.Components.UI.Number::ConfigureHeader`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x20210`

## callees

- `0x3380`
- `0x38d0`
- `0x20820`
- `0x20910`
- `0x238a0`
- `0x238c0`
- `0x23b60`
- `0x23f10`

## pseudocode

```c

```

## disassembly

```asm
0x20820  ldarg.0
0x20821  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::ConfigureHeader()
0x20826  ldarg.0
0x20827  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2082c  ldstr    aLocidNumberRan// "LOCID_NUMBER_RANGE_MASK"
0x20831  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x20836  ldstr    aCCrmSrcApplica_1// "C:.crm.src.Application.Web._controls.nu"...
0x2083b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x20840  ldc.i4.0
0x20841  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x20846  ldarg.0
0x20847  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2084c  ldstr    aLocidFloatRang// "LOCID_FLOAT_RANGE_MASK"
0x20851  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x20856  ldstr    aCCrmSrcApplica_2// "C:.crm.src.Application.Web._controls.nu"...
0x2085b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x20860  ldc.i4.0
0x20861  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x20866  ldarg.0
0x20867  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2086c  ldstr    aLocidDeverrorB// "LOCID_DEVERROR_BADDATATYPE_INT"
0x20871  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x20876  ldstr    aDeverrorBaddat_0// "DevError.BadDataType.Integer"
0x2087b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x20880  ldc.i4.0
0x20881  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x20886  ldarg.0
0x20887  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2088c  ldstr    aLocidAccuracyR// "LOCID_ACCURACY_RANGE_MESSAGE"
0x20891  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x20896  ldstr    aCCrmSrcApplica_3// "C:.crm.src.Application.Web._forms.contr"...
0x2089b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x208a0  ldc.i4.0
0x208a1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x208a6  ldarg.0
0x208a7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x208ac  ldstr    aLocidPrecision// "LOCID_PRECISION_RANGE_MESSAGE"
0x208b1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x208b6  ldstr    aPrecisionValue// "Precision_value_range_message"
0x208bb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x208c0  ldc.i4.0
0x208c1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x208c6  ldarg.0
0x208c7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x208cc  ldstr    aStaticFormsNum_1// "/_static/_forms/NumberInputBehavior.js"
0x208d1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x208d6  ldarg.0
0x208d7  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x208dc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x208e1  brtrue.s loc_20903
0x208e3  ldarg.0
0x208e4  ldarg.0
0x208e5  callvirt instance string Microsoft.Crm.Application.Components.UI.Number::get_ClientAjaxBehavior()
0x208ea  ldnull
0x208eb  ldnull
0x208ec  ldnull
0x208ed  ldarg.0
0x208ee  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x208f3  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x208f8  ldarg.0
0x208f9  ldstr    aMscrmNumberatt// "Mscrm.NumberAttribute"
0x208fe  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::RegisterClientSideControl(string attributeClassName)
0x20903  ret
```
