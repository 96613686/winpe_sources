# Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::ConfigurePage

- ea: `0xab3a0`
- end: `0xab648`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::ConfigurePage`
- size: `680`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xab3a0`

## string_xrefs

- `0xab3a6`: `/_static/_common/scripts/stage.js`
- `0xab57e`: `readonlymode`
- `0xab59a`: `readonlymode`
- `0xab604`: `ruleconditionxml`
- `0xab61d`: `ruleconditionxml`

## pseudocode

```c

```

## disassembly

```asm
0xab3a0  ldarg.0
0xab3a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xab3a6  ldstr    aStaticCommonSc_4// "/_static/_common/scripts/stage.js"
0xab3ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xab3b0  ldarg.0
0xab3b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xab3b6  ldstr    aStaticToolsSys_22// "/_static/tools/systemcustomization/simi"...
0xab3bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xab3c0  ldarg.0
0xab3c1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xab3c6  ldstr    aStaticAdvanced// "/_static/advancedfind/advancedfindcontr"...
0xab3cb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xab3d0  ldarg.0
0xab3d1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xab3d6  ldstr    aStaticAdvanced_0// "/_static/advancedfind/advfind.js"
0xab3db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xab3e0  ldarg.0
0xab3e1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xab3e6  ldstr    aStaticControls_5// "/_static/_controls/GridFilters/GridFilt"...
0xab3eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xab3f0  ldarg.0
0xab3f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xab3f6  ldstr    aLocidInvalidAt// "LOCID_INVALID_ATTRIBUTE_TYPE"
0xab3fb  ldarg.0
0xab3fc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xab401  ldstr    aSimilarityrule// "SimilarityRuleCondition_AttributeNotSup"...
0xab406  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xab40b  ldc.i4.0
0xab40c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xab411  ldarg.0
0xab412  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xab417  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xab41c  ldstr    aBaseentitycode// "baseentitycode"
0xab421  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xab426  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xab42b  call     unsigned int32 [mscorlib]System.UInt32::Parse(string, class [mscorlib]System.IFormatProvider)
0xab430  stloc.0
0xab431  ldarg.0
0xab432  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::similarityRuleAppCondition
0xab437  ldloc.0
0xab438  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition::set_PrimaryEntityCode(unsigned int32)
0xab43d  ldarg.0
0xab43e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xab443  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xab448  ldstr    aMatchingentity// "matchingentitycode"
0xab44d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xab452  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xab457  call     unsigned int32 [mscorlib]System.UInt32::Parse(string, class [mscorlib]System.IFormatProvider)
0xab45c  stloc.1
0xab45d  ldloc.0
0xab45e  ldloc.1
0xab45f  bne.un.s loc_AB480
0xab461  ldarg.0
0xab462  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::similarityRuleAppCondition
0xab467  ldarg.0
0xab468  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::similarityRuleAppCondition
0xab46d  callvirt instance unsigned int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition::get_PrimaryEntityCode()
0xab472  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition::set_SecondaryEntityCode(unsigned int32)
0xab477  ldarg.0
0xab478  ldc.i4.1
0xab479  stfld    bool Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::_isSingleEntityRule
0xab47e  br.s     loc_AB493
0xab480  ldarg.0
0xab481  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::similarityRuleAppCondition
0xab486  ldloc.1
0xab487  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition::set_SecondaryEntityCode(unsigned int32)
0xab48c  ldarg.0
0xab48d  ldc.i4.0
0xab48e  stfld    bool Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::_isSingleEntityRule
0xab493  ldstr    aColbaseattribu// "colBaseAttribute"
0xab498  ldc.i4.3
0xab499  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ConditionColumn::.ctor(string, valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ColumnType)
0xab49e  stloc.2
0xab49f  ldarg.0
0xab4a0  ldfld    bool Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::_isSingleEntityRule
0xab4a5  brfalse.s loc_AB4BF
0xab4a7  ldloc.2
0xab4a8  ldarg.0
0xab4a9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xab4ae  ldstr    aSimilarityrule_0// "SimilarityRules_AttributeHeader"
0xab4b3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xab4b8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ConditionColumn::set_Title(string)
0xab4bd  br.s     loc_AB4D5
0xab4bf  ldloc.2
0xab4c0  ldarg.0
0xab4c1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xab4c6  ldstr    aSimilarityrule_1// "SimilarityRules_BaseAttributeHeader"
0xab4cb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xab4d0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ConditionColumn::set_Title(string)
0xab4d5  ldstr    aColcriteria// "colCriteria"
0xab4da  ldc.i4.0
0xab4db  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ConditionColumn::.ctor(string, valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ColumnType)
0xab4e0  stloc.3
0xab4e1  ldloc.3
0xab4e2  ldarg.0
0xab4e3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xab4e8  ldstr    aSimilarityrule_2// "SimilarityRules_OperatorTypeHeader"
0xab4ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xab4f2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ConditionColumn::set_Title(string)
0xab4f7  ldstr    aColmatchingatt// "colMatchingAttribute"
0xab4fc  ldc.i4.3
0xab4fd  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ConditionColumn::.ctor(string, valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ColumnType)
0xab502  stloc.s  4
0xab504  ldloc.s  4
0xab506  ldarg.0
0xab507  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xab50c  ldstr    aSimilarityrule_3// "SimilarityRules_MatchingAttributeHeader"
0xab511  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xab516  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ConditionColumn::set_Title(string)
0xab51b  ldarg.0
0xab51c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::similarityRuleAppCondition
0xab521  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ConditionColumn> [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition::get_ConditionColumns()
0xab526  ldloc.2
0xab527  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ConditionColumn>::Add(var<u1>)
0xab52c  ldarg.0
0xab52d  ldfld    bool Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::_isSingleEntityRule
0xab532  brtrue.s loc_AB546
0xab534  ldarg.0
0xab535  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::similarityRuleAppCondition
0xab53a  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ConditionColumn> [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition::get_ConditionColumns()
0xab53f  ldloc.s  4
0xab541  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ConditionColumn>::Add(var<u1>)
0xab546  ldarg.0
0xab547  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::similarityRuleAppCondition
0xab54c  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ConditionColumn> [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition::get_ConditionColumns()
0xab551  ldloc.3
0xab552  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ConditionColumn>::Add(var<u1>)
0xab557  ldarg.0
0xab558  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::similarityRuleAppCondition
0xab55d  ldc.i4.1
0xab55e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition::set_ShowHeader(bool)
0xab563  ldarg.0
0xab564  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::similarityRuleAppCondition
0xab569  ldc.i4   0xE6
0xab56e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition::set_ColumnWidthInPix(int32)
0xab573  ldarg.0
0xab574  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xab579  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xab57e  ldstr    aReadonlymode// "readonlymode"
0xab583  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xab588  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xab58d  brtrue.s loc_AB5B9
0xab58f  ldarg.0
0xab590  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xab595  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xab59a  ldstr    aReadonlymode// "readonlymode"
0xab59f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xab5a4  call     bool [mscorlib]System.Boolean::Parse(string)
0xab5a9  brfalse.s loc_AB5B9
0xab5ab  ldarg.0
0xab5ac  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::similarityRuleAppCondition
0xab5b1  ldc.i4.1
0xab5b2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition::set_ReadOnlyMode(bool)
0xab5b7  br.s     loc_AB5C5
0xab5b9  ldarg.0
0xab5ba  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::similarityRuleAppCondition
0xab5bf  ldc.i4.0
0xab5c0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCondition::set_ReadOnlyMode(bool)
0xab5c5  ldarg.0
0xab5c6  ldsfld   string [mscorlib]System.String::Empty
0xab5cb  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::conditionXml
0xab5d0  ldarg.0
0xab5d1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xab5d6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xab5db  ldstr    aSimilarityrule_4// "similarityruleid"
0xab5e0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xab5e5  stloc.s  5
0xab5e7  ldloc.s  5
0xab5e9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xab5ee  brtrue.s loc_AB631
0xab5f0  ldstr    aSimilarityrule_5// "similarityrule"
0xab5f5  ldloc.s  5
0xab5f7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xab5fc  ldc.i4.1
0xab5fd  newarr   [mscorlib]System.String
0xab602  dup
0xab603  ldc.i4.0
0xab604  ldstr    aRuleconditionx// "ruleconditionxml"
0xab609  stelem.ref
0xab60a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xab60f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xab614  stloc.s  6
0xab616  ldloc.s  6
0xab618  brfalse.s loc_AB631
0xab61a  ldarg.0
0xab61b  ldloc.s  6
0xab61d  ldstr    aRuleconditionx// "ruleconditionxml"
0xab622  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xab627  castclass [mscorlib]System.String
0xab62c  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::conditionXml
0xab631  ldarg.0
0xab632  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xab637  ldstr    aIssingleentity// "_isSingleEntityRule"
0xab63c  ldarg.0
0xab63d  ldfld    bool Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRuleConditionPage::_isSingleEntityRule
0xab642  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xab647  ret
```
