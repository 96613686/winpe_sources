# Microsoft.Crm.Controls.TimeSheet::ConfigureHeader

- ea: `0xaec0`
- end: `0xb1e0`
- name: `Microsoft.Crm.Controls.TimeSheet::ConfigureHeader`
- size: `800`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2ef0`
- `0x2f20`
- `0x2f40`
- `0x2f60`
- `0x30a0`
- `0x3160`
- `0x3380`
- `0xb1e0`
- `0x23b60`
- `0x24080`

## string_xrefs

- `0xaf24`: `TemplateStartTime`
- `0xaf3a`: `TemplateEndTime`
- `0xaf50`: `TemplateApptsStartEvery`
- `0xb1a9`: `/_static/_common/styles/AutoToolTip.js`

## pseudocode

```c

```

## disassembly

```asm
0xaec0  ldarg.0
0xaec1  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0xaec6  ldarg.0
0xaec7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xaecc  ldstr    aBformchanged// "bFormChanged"
0xaed1  ldc.i4.0
0xaed2  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0xaed7  ldarg.0
0xaed8  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xaedd  ldstr    aDaystarttime// "DayStartTime"
0xaee2  ldarg.0
0xaee3  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Controls.TimeSheet::_startTime
0xaee8  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0xaeed  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, valuetype [mscorlib]System.DateTime varValue)
0xaef2  ldarg.0
0xaef3  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xaef8  ldstr    aDayendtime// "DayEndTime"
0xaefd  ldarg.0
0xaefe  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Controls.TimeSheet::_startTime
0xaf03  ldc.r8   1.0
0xaf0c  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xaf11  stloc.0
0xaf12  ldloca.s 0
0xaf14  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0xaf19  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, valuetype [mscorlib]System.DateTime varValue)
0xaf1e  ldarg.0
0xaf1f  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xaf24  ldstr    aTemplatestartt// "TemplateStartTime"
0xaf29  ldarg.0
0xaf2a  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Controls.TimeSheet::_startTime
0xaf2f  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, valuetype [mscorlib]System.DateTime varValue)
0xaf34  ldarg.0
0xaf35  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xaf3a  ldstr    aTemplateendtim// "TemplateEndTime"
0xaf3f  ldarg.0
0xaf40  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Controls.TimeSheet::_endTime
0xaf45  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, valuetype [mscorlib]System.DateTime varValue)
0xaf4a  ldarg.0
0xaf4b  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xaf50  ldstr    aTemplateapptss// "TemplateApptsStartEvery"
0xaf55  ldarg.0
0xaf56  ldfld    int32 Microsoft.Crm.Controls.TimeSheet::_apptStartEvery
0xaf5b  conv.i8
0xaf5c  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, int64 varValue)
0xaf61  ldarg.0
0xaf62  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xaf67  ldstr    aDefaulteffort// "DefaultEffort"
0xaf6c  ldarg.0
0xaf6d  ldfld    float64 Microsoft.Crm.Controls.TimeSheet::_defaultEffort
0xaf72  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, float64 varValue)
0xaf77  ldarg.0
0xaf78  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xaf7d  ldstr    aRulerownum// "RuleRowNum"
0xaf82  ldarg.0
0xaf83  ldfld    int32 Microsoft.Crm.Controls.TimeSheet::_ruleRowNumber
0xaf88  conv.i8
0xaf89  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, int64 varValue)
0xaf8e  ldarg.0
0xaf8f  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xaf94  ldstr    aImaxrange// "iMaxRange"
0xaf99  ldarg.0
0xaf9a  ldfld    int32 Microsoft.Crm.Controls.TimeSheet::_maxRange
0xaf9f  conv.i8
0xafa0  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, int64 varValue)
0xafa5  ldarg.0
0xafa6  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xafab  ldstr    aInsertrulename// "InsertRuleName"
0xafb0  ldarg.0
0xafb1  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.TimeSheet::_uiElements
0xafb6  ldstr    aInsertrulename// "InsertRuleName"
0xafbb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xafc0  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0xafc5  ldarg.0
0xafc6  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xafcb  ldstr    aSplitrulename// "SplitRuleName"
0xafd0  ldarg.0
0xafd1  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.TimeSheet::_uiElements
0xafd6  ldstr    aSplitrulename// "SplitRuleName"
0xafdb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xafe0  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0xafe5  ldarg.0
0xafe6  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xafeb  ldstr    aEffortrulename// "EffortRuleName"
0xaff0  ldarg.0
0xaff1  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.TimeSheet::_uiElements
0xaff6  ldstr    aEffortrulename// "EffortRuleName"
0xaffb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb000  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0xb005  ldarg.0
0xb006  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb00b  ldstr    aInsertactionna// "InsertActionName"
0xb010  ldarg.0
0xb011  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.TimeSheet::_uiElements
0xb016  ldstr    aInsertactionna// "InsertActionName"
0xb01b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb020  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0xb025  ldarg.0
0xb026  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb02b  ldstr    aSplitactionnam// "SplitActionName"
0xb030  ldarg.0
0xb031  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.TimeSheet::_uiElements
0xb036  ldstr    aSplitactionnam// "SplitActionName"
0xb03b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb040  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0xb045  ldarg.0
0xb046  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb04b  ldstr    aMergeactionnam// "MergeActionName"
0xb050  ldarg.0
0xb051  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.TimeSheet::_uiElements
0xb056  ldstr    aMergeactionnam// "MergeActionName"
0xb05b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb060  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0xb065  ldarg.0
0xb066  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb06b  ldstr    aStarttimelater// "StartTimeLater"
0xb070  ldarg.0
0xb071  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.TimeSheet::_uiElements
0xb076  ldstr    aStarttimelater// "StartTimeLater"
0xb07b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb080  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0xb085  ldarg.0
0xb086  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb08b  ldstr    aEndtimeearlier// "EndTimeEarlier"
0xb090  ldarg.0
0xb091  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.TimeSheet::_uiElements
0xb096  ldstr    aEndtimeearlier// "EndTimeEarlier"
0xb09b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb0a0  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0xb0a5  ldarg.0
0xb0a6  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb0ab  ldstr    aErrorinrow// "ErrorInRow"
0xb0b0  ldarg.0
0xb0b1  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.TimeSheet::_uiElements
0xb0b6  ldstr    aErrorinrow// "ErrorInRow"
0xb0bb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb0c0  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0xb0c5  ldarg.0
0xb0c6  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb0cb  ldstr    aEffortcolumnhe// "EffortColumnHeader"
0xb0d0  ldarg.0
0xb0d1  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.TimeSheet::_uiElements
0xb0d6  ldstr    aColumnheaderef// "ColumnHeaderEffort"
0xb0db  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb0e0  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0xb0e5  ldarg.0
0xb0e6  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb0eb  ldstr    aEnableeffort// "EnableEffort"
0xb0f0  ldarg.0
0xb0f1  ldfld    bool Microsoft.Crm.Controls.TimeSheet::_enableEffort
0xb0f6  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0xb0fb  ldarg.0
0xb0fc  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb101  ldstr    aMaxRows// "MAX_ROWS"
0xb106  ldc.i4.s 0x40
0xb108  conv.i8
0xb109  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, int64 varValue)
0xb10e  ldarg.0
0xb10f  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb114  ldstr    aOverlapmessage// "OverlapMessage"
0xb119  ldarg.0
0xb11a  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.TimeSheet::_uiElements
0xb11f  ldstr    aOverlapmessage// "OverlapMessage"
0xb124  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb129  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0xb12e  ldarg.0
0xb12f  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb134  ldstr    aConflictmessag// "ConflictMessage"
0xb139  ldarg.0
0xb13a  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.TimeSheet::_uiElements
0xb13f  ldstr    aConflictmessag// "ConflictMessage"
0xb144  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb149  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0xb14e  ldarg.0
0xb14f  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb154  ldstr    aValidrangemess// "ValidRangeMessage"
0xb159  ldarg.0
0xb15a  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.TimeSheet::_uiElements
0xb15f  ldstr    aValidrangemess// "ValidRangeMessage"
0xb164  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb169  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0xb16e  ldarg.0
0xb16f  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb174  ldstr    aMergemessage// "MergeMessage"
0xb179  ldarg.0
0xb17a  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.TimeSheet::_uiElements
0xb17f  ldstr    aMergerangesnam// "MergeRangesName"
0xb184  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb189  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0xb18e  ldarg.0
0xb18f  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb194  ldstr    aZonpageload// "zOnPageLoad"
0xb199  ldstr    aOnpageload// "OnPageLoad();"
0xb19e  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string key, string scriptBlock)
0xb1a3  ldarg.0
0xb1a4  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb1a9  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0xb1ae  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0xb1b3  ldarg.0
0xb1b4  ldstr    aTotalC// "total_c"
0xb1b9  call     instance void Microsoft.Crm.Controls.TimeSheet::AddAutoToolTipControl(string elementId)
0xb1be  ldarg.0
0xb1bf  ldstr    aTypecolumn// "typeColumn"
0xb1c4  call     instance void Microsoft.Crm.Controls.TimeSheet::AddAutoToolTipControl(string elementId)
0xb1c9  ldarg.0
0xb1ca  ldstr    aStartC// "start_c"
0xb1cf  call     instance void Microsoft.Crm.Controls.TimeSheet::AddAutoToolTipControl(string elementId)
0xb1d4  ldarg.0
0xb1d5  ldstr    aEndC// "end_c"
0xb1da  call     instance void Microsoft.Crm.Controls.TimeSheet::AddAutoToolTipControl(string elementId)
0xb1df  ret
```
