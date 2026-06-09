# Microsoft.Crm.Application.Pages.Business.GettingStarted.GettingStartedHome::ConfigurePage

- ea: `0xf46a0`
- end: `0xf4947`
- name: `Microsoft.Crm.Application.Pages.Business.GettingStarted.GettingStartedHome::ConfigurePage`
- size: `679`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xf46a0`

## string_xrefs

- `0xf475e`: `accesskey`
- `0xf48ec`: `accesskey`
- `0xf489e`: `helpLink`
- `0xf48b9`: `GettingStarted.Task.Printing.Text`

## pseudocode

```c

```

## disassembly

```asm
0xf46a0  ldstr    aDiv// "div"
0xf46a5  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xf46aa  stloc.0
0xf46ab  ldloc.0
0xf46ac  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xf46b1  ldstr    aClass// "class"
0xf46b6  ldstr    aMsCrmGettingst// "ms-crm-GettingStarted-Title"
0xf46bb  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xf46c0  ldloc.0
0xf46c1  ldarg.0
0xf46c2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf46c7  ldstr    aGettingstarted_0// "GettingStarted.Home.Title"
0xf46cc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf46d1  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0xf46d6  ldarg.0
0xf46d7  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Business.GettingStarted.GettingStartedHome::topSection
0xf46dc  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xf46e1  ldloc.0
0xf46e2  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xf46e7  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.NextButton::.ctor()
0xf46ec  stloc.1
0xf46ed  ldarg.0
0xf46ee  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf46f3  ldstr    aGettingstarted_1// "GettingStarted.Home.ChangeHomePageButto"...
0xf46f8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf46fd  dup
0xf46fe  ldstr    asc_138B50// "&"
0xf4703  ldsfld   string [mscorlib]System.String::Empty
0xf4708  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xf470d  stloc.2
0xf470e  ldloc.1
0xf470f  ldstr    aJavascriptChan// "javascript:ChangeHomePage();"
0xf4714  ldloc.2
0xf4715  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.NextButton::LinkTo(string, string)
0xf471a  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0xf471f  stloc.3
0xf4720  ldloc.1
0xf4721  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xf4726  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Web]System.Web.UI.ControlCollection::GetEnumerator()
0xf472b  stloc.s  8
0xf472d  br       loc_F47EF
0xf4732  ldloc.s  8
0xf4734  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xf4739  castclass [System.Web]System.Web.UI.HtmlControls.HtmlControl
0xf473e  stloc.s  9
0xf4740  ldloc.s  9
0xf4742  isinst   [System.Web]System.Web.UI.HtmlControls.HtmlAnchor
0xf4747  brfalse  loc_F47EF
0xf474c  ldloc.3
0xf474d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf4752  brtrue   loc_F47EF
0xf4757  ldloc.s  9
0xf4759  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xf475e  ldstr    aAccesskey// "accesskey"
0xf4763  ldloc.3
0xf4764  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xf4769  ldloc.s  9
0xf476b  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xf4770  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Web]System.Web.UI.ControlCollection::GetEnumerator()
0xf4775  stloc.s  0xA
0xf4777  br.s     loc_F47CF
0xf4779  ldloc.s  0xA
0xf477b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xf4780  castclass [System.Web]System.Web.UI.HtmlControls.HtmlControl
0xf4785  stloc.s  0xB
0xf4787  ldloc.s  0xB
0xf4789  isinst   [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl
0xf478e  brfalse.s loc_F47CF
0xf4790  ldloc.s  0xB
0xf4792  castclass [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl
0xf4797  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf479c  ldstr    aSpan0Span// "<span>{0}</span>"
0xf47a1  ldc.i4.1
0xf47a2  newarr   [mscorlib]System.Object
0xf47a7  dup
0xf47a8  ldc.i4.0
0xf47a9  ldloc.2
0xf47aa  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xf47af  ldloc.3
0xf47b0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xf47b5  ldstr    aU_1// "<u>"
0xf47ba  ldstr    aU_2// "</u>"
0xf47bf  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::StringInjector(string, string, string, string)
0xf47c4  stelem.ref
0xf47c5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf47ca  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0xf47cf  ldloc.s  0xA
0xf47d1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xf47d6  brtrue.s loc_F4779
0xf47d8  leave.s  loc_F47EF
0xf47da  ldloc.s  0xA
0xf47dc  isinst   [mscorlib]System.IDisposable
0xf47e1  stloc.s  0xC
0xf47e3  ldloc.s  0xC
0xf47e5  brfalse.s loc_F47EE
0xf47e7  ldloc.s  0xC
0xf47e9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf47ee  endfinally
0xf47ef  ldloc.s  8
0xf47f1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xf47f6  brtrue   loc_F4732
0xf47fb  leave.s  loc_F4812
0xf47fd  ldloc.s  8
0xf47ff  isinst   [mscorlib]System.IDisposable
0xf4804  stloc.s  0xC
0xf4806  ldloc.s  0xC
0xf4808  brfalse.s loc_F4811
0xf480a  ldloc.s  0xC
0xf480c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf4811  endfinally
0xf4812  ldarg.0
0xf4813  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Business.GettingStarted.GettingStartedHome::topSection
0xf4818  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xf481d  ldloc.1
0xf481e  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xf4823  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::.ctor()
0xf4828  stloc.s  4
0xf482a  ldloc.s  4
0xf482c  ldstr    aImgsIco16Print// "/_imgs/ico/16_print.gif"
0xf4831  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0xf4836  ldloc.s  4
0xf4838  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xf483d  ldstr    aOnclick// "onclick"
0xf4842  ldstr    aShowprintpage// "showPrintPage();"
0xf4847  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xf484c  ldloc.s  4
0xf484e  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xf4853  ldstr    aClass// "class"
0xf4858  ldstr    aMsCrmWizardfor// "ms-crm-WizardForm-Header-Help"
0xf485d  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xf4862  ldloc.s  4
0xf4864  ldarg.0
0xf4865  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf486a  ldstr    aTooltipPrintpr// "ToolTip_PrintPreview"
0xf486f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf4874  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Alt(string)
0xf4879  ldarg.0
0xf487a  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Business.GettingStarted.GettingStartedHome::printSection
0xf487f  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xf4884  ldloc.s  4
0xf4886  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xf488b  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::.ctor()
0xf4890  stloc.s  5
0xf4892  ldloc.s  5
0xf4894  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xf4899  ldstr    aClass// "class"
0xf489e  ldstr    aHelplink// "helpLink"
0xf48a3  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xf48a8  ldloc.s  5
0xf48aa  ldstr    aJavascriptShow// "javascript:showPrintPage();"
0xf48af  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_HRef(string)
0xf48b4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf48b9  ldstr    aGettingstarted_2// "GettingStarted.Task.Printing.Text"
0xf48be  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf48c3  dup
0xf48c4  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0xf48c9  stloc.s  6
0xf48cb  ldstr    asc_138B50// "&"
0xf48d0  ldsfld   string [mscorlib]System.String::Empty
0xf48d5  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xf48da  stloc.s  7
0xf48dc  ldloc.s  6
0xf48de  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf48e3  brtrue.s loc_F48F8
0xf48e5  ldloc.s  5
0xf48e7  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xf48ec  ldstr    aAccesskey// "accesskey"
0xf48f1  ldloc.s  6
0xf48f3  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xf48f8  ldloc.s  5
0xf48fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf48ff  ldstr    aSpan0Span// "<span>{0}</span>"
0xf4904  ldc.i4.1
0xf4905  newarr   [mscorlib]System.Object
0xf490a  dup
0xf490b  ldc.i4.0
0xf490c  ldloc.s  7
0xf490e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xf4913  ldloc.s  6
0xf4915  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xf491a  ldstr    aU_1// "<u>"
0xf491f  ldstr    aU_2// "</u>"
0xf4924  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::StringInjector(string, string, string, string)
0xf4929  stelem.ref
0xf492a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf492f  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0xf4934  ldarg.0
0xf4935  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Business.GettingStarted.GettingStartedHome::printSection
0xf493a  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xf493f  ldloc.s  5
0xf4941  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xf4946  ret
```
