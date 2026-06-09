# Microsoft.Crm.Web.Sfa.EntityForm::ConfigurePage

- ea: `0x42da0`
- end: `0x42f98`
- name: `Microsoft.Crm.Web.Sfa.EntityForm::ConfigurePage`
- size: `504`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x42da0`
- `0x42fd0`
- `0x437a0`
- `0x437f0`

## string_xrefs

- `0x42db6`: `/_common/styles/miniCal.css.aspx`
- `0x42da6`: `/_common/styles/select.css.aspx`
- `0x42ee4`: `Web.SFA.Workflow.CreateStep.RequiredFail`
- `0x42df6`: `/_static/_common/scripts/details.js`
- `0x42e76`: `LOCID_NO_TEMPLATE_SELECTED`
- `0x42e81`: `Web.SFA.Workflow.WorkflowTemplate.NoTemplateSelected`

## pseudocode

```c

```

## disassembly

```asm
0x42da0  ldarg.0
0x42da1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42da6  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0x42dab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x42db0  ldarg.0
0x42db1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42db6  ldstr    aCommonStylesMi// "/_common/styles/miniCal.css.aspx"
0x42dbb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x42dc0  ldarg.0
0x42dc1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42dc6  ldstr    aNavTabsCssAspx// "/_nav/tabs.css.aspx"
0x42dcb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x42dd0  ldarg.0
0x42dd1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42dd6  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x42ddb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x42de0  ldarg.0
0x42de1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42de6  ldstr    aNavMenuCssAspx// "/_nav/menu.css.aspx"
0x42deb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x42df0  ldarg.0
0x42df1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42df6  ldstr    aStaticCommonSc_24// "/_static/_common/scripts/details.js"
0x42dfb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x42e00  ldarg.0
0x42e01  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42e06  ldstr    aStaticGridActi// "/_static/_grid/action.js"
0x42e0b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x42e10  ldarg.0
0x42e11  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42e16  ldstr    aStaticControls_1// "/_static/_controls/lookup/lookup.js"
0x42e1b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x42e20  ldarg.0
0x42e21  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42e26  ldstr    aStaticControls// "/_static/_controls/datetime/date.js"
0x42e2b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x42e30  ldarg.0
0x42e31  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42e36  ldstr    aStaticSfaSfaut// "/_static/sfa/sfautil.js"
0x42e3b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x42e40  ldarg.0
0x42e41  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42e46  ldstr    aStaticSfaWorkf_3// "/_static/sfa/workflow/sendemailstep.js"
0x42e4b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x42e50  ldarg.0
0x42e51  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42e56  ldstr    aStaticSfaWorkf_0// "/_static/SFA/workflow/slugsupport.js"
0x42e5b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x42e60  ldarg.0
0x42e61  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42e66  ldstr    aStaticSfaWorkf// "/_static/SFA/workflow/workflowstep.js"
0x42e6b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x42e70  ldarg.0
0x42e71  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42e76  ldstr    aLocidNoTemplat// "LOCID_NO_TEMPLATE_SELECTED"
0x42e7b  ldarg.0
0x42e7c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x42e81  ldstr    aWebSfaWorkflow_72// "Web.SFA.Workflow.WorkflowTemplate.NoTem"...
0x42e86  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x42e8b  ldc.i4.0
0x42e8c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x42e91  ldarg.0
0x42e92  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42e97  ldstr    aLocidSelectbox// "LOCID_SELECTBOX_BUTTON_ALT"
0x42e9c  ldarg.0
0x42e9d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x42ea2  ldstr    aSelectButtonAl// "Select.Button.AltTag"
0x42ea7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x42eac  ldc.i4.0
0x42ead  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x42eb2  ldarg.0
0x42eb3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42eb8  ldstr    aLocidContractE// "LOCID_CONTRACT_ED_DT_LT_ST_DT"
0x42ebd  ldarg.0
0x42ebe  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x42ec3  ldstr    aWebCsContracts// "Web.cs.contracts.end_date_earlier_than_"...
0x42ec8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x42ecd  ldc.i4.0
0x42ece  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x42ed3  ldarg.0
0x42ed4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42ed9  ldstr    aLocidRequiredF_0// "LOCID_REQUIRED_FIELDS_EMPTY"
0x42ede  ldarg.0
0x42edf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x42ee4  ldstr    aWebSfaWorkflow_2// "Web.SFA.Workflow.CreateStep.RequiredFai"...
0x42ee9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x42eee  ldc.i4.0
0x42eef  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x42ef4  ldarg.0
0x42ef5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42efa  ldstr    aEntityid_3// "ENTITYID"
0x42eff  ldarg.0
0x42f00  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x42f05  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x42f0a  ldstr    aWorkflowid_0// "workflowId"
0x42f0f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x42f14  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x42f19  ldarg.0
0x42f1a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42f1f  ldstr    aStepid_2// "STEPID"
0x42f24  ldarg.0
0x42f25  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x42f2a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x42f2f  ldstr    aStepid_0// "stepId"
0x42f34  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x42f39  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x42f3e  ldarg.0
0x42f3f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42f44  ldstr    aIsWorkflowEdit// "IS_WORKFLOW_EDITOR"
0x42f49  ldstr    aTrue// "TRUE"
0x42f4e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x42f53  ldarg.0
0x42f54  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42f59  ldarg.0
0x42f5a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x42f5f  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.WorkflowRelatedCategory::SetStringResources(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager)
0x42f64  ldarg.0
0x42f65  call     instance void Microsoft.Crm.Web.Sfa.EntityForm::SetUpdateMode()
0x42f6a  ldarg.0
0x42f6b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Web.Sfa.EntityForm::get_FormEntity()
0x42f70  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x42f75  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x42f7a  stloc.0
0x42f7b  ldarg.0
0x42f7c  ldloc.0
0x42f7d  call     instance void Microsoft.Crm.Web.Sfa.EntityForm::SetFormTitle(int32 entityTypeCode)
0x42f82  ldloc.0
0x42f83  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsActivityObject(int32)
0x42f88  brfalse.s loc_42F97
0x42f8a  ldarg.0
0x42f8b  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentAppHeader()
0x42f90  ldc.i4.s 0x10
0x42f92  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AppControlType)
0x42f97  ret
```
