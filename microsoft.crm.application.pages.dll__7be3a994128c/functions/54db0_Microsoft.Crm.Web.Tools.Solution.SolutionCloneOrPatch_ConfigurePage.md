# Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::ConfigurePage

- ea: `0x54db0`
- end: `0x5516a`
- name: `Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::ConfigurePage`
- size: `954`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x54d10`
- `0x54d30`
- `0x54d50`
- `0x54d70`
- `0x54d90`
- `0x54db0`

## string_xrefs

- `0x54f86`: `/_common/styles/Dialogs.css.aspx`
- `0x54ead`: `createdon`
- `0x54fa7`: `/_static/_controls/SolutionComponentFilter/SolutionComponentFilter.js`
- `0x54fb7`: `/_static/tools/solution/scripts/solutioncomponentlist.js`

## pseudocode

```c

```

## disassembly

```asm
0x54db0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0x54db5  pop
0x54db6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x54dbb  pop
0x54dbc  ldarg.0
0x54dbd  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x54dc2  ldarg.0
0x54dc3  ldarg.0
0x54dc4  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x54dc9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x54dce  ldstr    aSolutionname// "solutionname"
0x54dd3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x54dd8  stfld    string Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::parentSolutionName
0x54ddd  ldarg.0
0x54dde  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x54de3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x54de8  ldstr    aDisplayname// "displayname"
0x54ded  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x54df2  stloc.0
0x54df3  ldarg.0
0x54df4  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x54df9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x54dfe  ldstr    aVersion// "version"
0x54e03  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x54e08  stloc.1
0x54e09  ldarg.0
0x54e0a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x54e0f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x54e14  ldstr    aClonetype// "clonetype"
0x54e19  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x54e1e  stloc.2
0x54e1f  ldloca.s 3
0x54e21  ldarg.0
0x54e22  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x54e27  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x54e2c  ldstr    aSolutionid// "solutionid"
0x54e31  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x54e36  call     instance void [mscorlib]System.Guid::.ctor(string)
0x54e3b  ldloc.2
0x54e3c  ldstr    aCloneaspatch// "CloneAsPatch"
0x54e41  call     bool [mscorlib]System.String::op_Equality(string, string)
0x54e46  brfalse.s loc_54E51
0x54e48  ldarg.0
0x54e49  ldc.i4.1
0x54e4a  stfld    bool Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::isCloneTypePatch
0x54e4f  br.s     loc_54E73
0x54e51  ldloc.2
0x54e52  ldstr    aCloneassolutio// "CloneAsSolution"
0x54e57  call     bool [mscorlib]System.String::op_Equality(string, string)
0x54e5c  brfalse.s loc_54E67
0x54e5e  ldarg.0
0x54e5f  ldc.i4.0
0x54e60  stfld    bool Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::isCloneTypePatch
0x54e65  br.s     loc_54E73
0x54e67  ldstr    aInvalidClonety// "Invalid cloneType parameter: {0}"
0x54e6c  ldloc.2
0x54e6d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x54e72  throw
0x54e73  ldarg.0
0x54e74  ldfld    bool Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::isCloneTypePatch
0x54e79  brfalse.s loc_54EF2
0x54e7b  ldstr    aSolution// "solution"
0x54e80  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x54e85  dup
0x54e86  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x54e8b  ldstr    aVersion// "version"
0x54e90  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x54e95  dup
0x54e96  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x54e9b  ldstr    aParentsolution// "parentsolutionid"
0x54ea0  ldc.i4.0
0x54ea1  ldloc.3
0x54ea2  box      [mscorlib]System.Guid
0x54ea7  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x54eac  dup
0x54ead  ldstr    aCreatedon// "createdon"
0x54eb2  ldc.i4.1
0x54eb3  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::AddOrder(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.OrderType)
0x54eb8  dup
0x54eb9  ldc.i4.1
0x54eba  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x54ebf  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_TopCount(valuetype [mscorlib]System.Nullable`1<int32>)
0x54ec4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x54ec9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x54ece  stloc.s  7
0x54ed0  ldloc.s  7
0x54ed2  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x54ed7  ldc.i4.1
0x54ed8  bne.un.s loc_54EF2
0x54eda  ldloc.s  7
0x54edc  ldc.i4.0
0x54edd  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x54ee2  ldstr    aVersion// "version"
0x54ee7  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x54eec  castclass [mscorlib]System.String
0x54ef1  stloc.1
0x54ef2  ldarg.0
0x54ef3  ldloc.1
0x54ef4  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x54ef9  stfld    class [mscorlib]System.Version Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::clonedPatchVersion
0x54efe  ldarg.0
0x54eff  ldloc.1
0x54f00  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x54f05  stfld    class [mscorlib]System.Version Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::clonedSolutionVersion
0x54f0a  ldarg.0
0x54f0b  ldfld    class [mscorlib]System.Version Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::clonedPatchVersion
0x54f10  callvirt instance int32 [mscorlib]System.Version::get_Build()
0x54f15  stloc.s  4
0x54f17  ldarg.0
0x54f18  ldfld    class [mscorlib]System.Version Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::clonedPatchVersion
0x54f1d  callvirt instance int32 [mscorlib]System.Version::get_Revision()
0x54f22  stloc.s  5
0x54f24  ldloc.s  4
0x54f26  ldc.i4.0
0x54f27  bge.s    loc_54F2C
0x54f29  ldc.i4.0
0x54f2a  stloc.s  4
0x54f2c  ldloc.s  5
0x54f2e  ldc.i4.0
0x54f2f  bge.s    loc_54F34
0x54f31  ldc.i4.0
0x54f32  stloc.s  5
0x54f34  ldarg.0
0x54f35  ldarg.0
0x54f36  ldfld    class [mscorlib]System.Version Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::clonedSolutionVersion
0x54f3b  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x54f40  ldarg.0
0x54f41  ldfld    class [mscorlib]System.Version Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::clonedSolutionVersion
0x54f46  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x54f4b  ldc.i4.1
0x54f4c  add
0x54f4d  ldc.i4.0
0x54f4e  ldc.i4.0
0x54f4f  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x54f54  stfld    class [mscorlib]System.Version Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::clonedSolutionVersion
0x54f59  ldarg.0
0x54f5a  ldarg.0
0x54f5b  ldfld    class [mscorlib]System.Version Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::clonedPatchVersion
0x54f60  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x54f65  ldarg.0
0x54f66  ldfld    class [mscorlib]System.Version Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::clonedPatchVersion
0x54f6b  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x54f70  ldloc.s  4
0x54f72  ldc.i4.1
0x54f73  add
0x54f74  ldloc.s  5
0x54f76  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x54f7b  stfld    class [mscorlib]System.Version Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::clonedPatchVersion
0x54f80  ldarg.0
0x54f81  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x54f86  ldstr    aCommonStylesDi_0// "/_common/styles/Dialogs.css.aspx"
0x54f8b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x54f90  ldarg.0
0x54f91  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x54f96  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x54f9b  ldnull
0x54f9c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x54fa1  ldarg.0
0x54fa2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x54fa7  ldstr    aStaticControls_19// "/_static/_controls/SolutionComponentFil"...
0x54fac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x54fb1  ldarg.0
0x54fb2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x54fb7  ldstr    aStaticToolsSol_1// "/_static/tools/solution/scripts/solutio"...
0x54fbc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x54fc1  ldarg.0
0x54fc2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x54fc7  ldstr    aStaticToolsSol_2// "/_static/tools/solution/scripts/solutio"...
0x54fcc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x54fd1  ldarg.0
0x54fd2  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x54fd7  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x54fdc  stloc.s  6
0x54fde  ldarg.0
0x54fdf  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x54fe4  ldarg.0
0x54fe5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x54fea  ldarg.0
0x54feb  ldfld    bool Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::isCloneTypePatch
0x54ff0  brtrue.s loc_54FF9
0x54ff2  ldstr    aClonetosolutio// "ClonetoSolution_Dialog_Title"
0x54ff7  br.s     loc_54FFE
0x54ff9  ldstr    aClonetopatchDi// "ClonetoPatch_Dialog_Title"
0x54ffe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x55003  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x55008  ldloc.s  6
0x5500a  ldarg.0
0x5500b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x55010  ldarg.0
0x55011  ldfld    bool Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::isCloneTypePatch
0x55016  brtrue.s loc_5501F
0x55018  ldstr    aClonetosolutio// "ClonetoSolution_Dialog_Title"
0x5501d  br.s     loc_55024
0x5501f  ldstr    aClonetopatchDi// "ClonetoPatch_Dialog_Title"
0x55024  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x55029  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x5502e  ldloc.s  6
0x55030  ldarg.0
0x55031  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x55036  ldarg.0
0x55037  ldfld    bool Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::isCloneTypePatch
0x5503c  brtrue.s loc_55045
0x5503e  ldstr    aClonetosolutio_0// "ClonetoSolution_Dialog_Title_Descriptio"...
0x55043  br.s     loc_5504A
0x55045  ldstr    aClonetopatchDi_0// "ClonetoPatch_Dialog_Title_Description"
0x5504a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5504f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x55054  ldloc.s  6
0x55056  ldc.i4   0x402
0x5505b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x55060  ldarg.0
0x55061  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x55066  ldstr    aLocidCloningEr// "LOCID_CLONING_ERROR"
0x5506b  ldarg.0
0x5506c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x55071  ldstr    aClonesolutione// "CloneSolutionError"
0x55076  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5507b  ldc.i4.0
0x5507c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x55081  ldarg.0
0x55082  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x55087  ldstr    aLocidCloningPa// "LOCID_CLONING_PATCH_ERROR"
0x5508c  ldarg.0
0x5508d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x55092  ldstr    aClonecannotpat// "CloneCannotPatch"
0x55097  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5509c  ldc.i4.0
0x5509d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x550a2  ldarg.0
0x550a3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x550a8  ldstr    aLocidInvalidVe// "LOCID_INVALID_VERSION_FORMAT"
0x550ad  ldarg.0
0x550ae  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x550b3  ldstr    aErrorMessage0x_5// "Error_Message_0x8004f01e"
0x550b8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x550bd  ldc.i4.0
0x550be  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x550c3  ldarg.0
0x550c4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x550c9  ldstr    aClonetype_0// "cloneType"
0x550ce  ldloc.2
0x550cf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x550d4  ldarg.0
0x550d5  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::get_txtPatchDisplayName()
0x550da  ldloc.0
0x550db  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x550e0  ldarg.0
0x550e1  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::get_txtMajorVersion()
0x550e6  ldarg.0
0x550e7  ldfld    class [mscorlib]System.Version Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::clonedSolutionVersion
0x550ec  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x550f1  stloc.s  8
0x550f3  ldloca.s 8
0x550f5  call     instance string [mscorlib]System.Int32::ToString()
0x550fa  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x550ff  ldarg.0
0x55100  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::get_txtMinorVersion()
0x55105  ldarg.0
0x55106  ldfld    class [mscorlib]System.Version Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::clonedSolutionVersion
0x5510b  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x55110  stloc.s  8
0x55112  ldloca.s 8
0x55114  call     instance string [mscorlib]System.Int32::ToString()
0x55119  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x5511e  ldarg.0
0x5511f  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::get_txtBuildVersion()
0x55124  ldarg.0
0x55125  ldfld    class [mscorlib]System.Version Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::clonedPatchVersion
0x5512a  callvirt instance int32 [mscorlib]System.Version::get_Build()
0x5512f  stloc.s  8
0x55131  ldloca.s 8
0x55133  call     instance string [mscorlib]System.Int32::ToString()
0x55138  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x5513d  ldarg.0
0x5513e  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::get_txtRevisionVersion()
0x55143  ldarg.0
0x55144  ldfld    class [mscorlib]System.Version Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::clonedPatchVersion
0x55149  callvirt instance int32 [mscorlib]System.Version::get_Revision()
0x5514e  stloc.s  8
0x55150  ldloca.s 8
0x55152  call     instance string [mscorlib]System.Int32::ToString()
0x55157  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x5515c  ldarg.0
0x5515d  ldloc.s  6
0x5515f  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::get_DialogTitle()
0x55164  stfld    string Microsoft.Crm.Web.Tools.Solution.SolutionCloneOrPatch::SpinCaption
0x55169  ret
```
