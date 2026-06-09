# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelatedInformationControl::AddLookupContext

- ea: `0x2c0b0`
- end: `0x2c234`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelatedInformationControl::AddLookupContext`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x2bff0`

## callees

- `0x179d0`
- `0x17a10`
- `0x2c0b0`
- `0x2c880`

## string_xrefs

- `0x2c0fe`: `serviceid`
- `0x2c1f6`: `Category_CustomerPreferredServices`
- `0x2c206`: `RelatedInformation_Category_CustomerPreferred_Service`

## pseudocode

```c

```

## disassembly

```asm
0x2c0b0  ldnull
0x2c0b1  stloc.0
0x2c0b2  ldarg.1
0x2c0b3  brfalse  loc_2C232
0x2c0b8  ldarg.1
0x2c0b9  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x2c0be  brtrue   loc_2C232
0x2c0c3  ldarg.1
0x2c0c4  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_ReadOnly()
0x2c0c9  brtrue   loc_2C232
0x2c0ce  ldarg.2
0x2c0cf  ldnull
0x2c0d0  cgt.un
0x2c0d2  ldstr    aLookupcontrolS// "LookupControl's parent must be of type "...
0x2c0d7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2c0dc  ldarg.1
0x2c0dd  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c0e2  stloc.2
0x2c0e3  ldloc.2
0x2c0e4  ldstr    aSubjectid// "subjectid"
0x2c0e9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c0ee  brtrue.s loc_2C112
0x2c0f0  ldloc.2
0x2c0f1  ldstr    aResources// "resources"
0x2c0f6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c0fb  brtrue.s loc_2C141
0x2c0fd  ldloc.2
0x2c0fe  ldstr    aServiceid// "serviceid"
0x2c103  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c108  brtrue   loc_2C1CB
0x2c10d  br       loc_2C232
0x2c112  ldarg.0
0x2c113  ldarg.3
0x2c114  ldarg.s  4
0x2c116  ldarg.1
0x2c117  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c11c  ldarg.1
0x2c11d  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x2c122  ldarg.2
0x2c123  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Context Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelatedInformationControl::GetContext(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType formType, int32 formObjectType, string contextId, int32 tabIndex, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell formCell)
0x2c128  stloc.0
0x2c129  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.SubjectTreeCategory::.ctor()
0x2c12e  stloc.1
0x2c12f  ldloc.0
0x2c130  callvirt instance class [mscorlib]System.Collections.IList [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Context::get_Categories()
0x2c135  ldloc.1
0x2c136  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x2c13b  pop
0x2c13c  br       loc_2C232
0x2c141  ldarg.0
0x2c142  ldarg.3
0x2c143  ldarg.s  4
0x2c145  ldarg.1
0x2c146  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c14b  ldarg.1
0x2c14c  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x2c151  ldarg.2
0x2c152  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Context Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelatedInformationControl::GetContext(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType formType, int32 formObjectType, string contextId, int32 tabIndex, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell formCell)
0x2c157  stloc.0
0x2c158  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x2c15d  brfalse.s loc_2C179
0x2c15f  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.ResourceSpecificationTreeCategory::.ctor()
0x2c164  stloc.1
0x2c165  ldloc.1
0x2c166  ldc.i4.2
0x2c167  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.Category::set_OrderIndex(int32)
0x2c16c  ldloc.0
0x2c16d  callvirt instance class [mscorlib]System.Collections.IList [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Context::get_Categories()
0x2c172  ldloc.1
0x2c173  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x2c178  pop
0x2c179  ldc.i4.1
0x2c17a  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.CustomGridProviderFactory::.ctor()
0x2c17f  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.CustomerPreferencesListCategory::.ctor(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.CustomerPreferenceType, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ICustomGridProviderFactory)
0x2c184  stloc.1
0x2c185  ldloc.1
0x2c186  ldc.i4.1
0x2c187  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.Category::set_OrderIndex(int32)
0x2c18c  ldloc.1
0x2c18d  ldstr    aCategoryCustom// "Category_CustomerPreferredResources"
0x2c192  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.Category::set_CategoryId(string)
0x2c197  ldloc.1
0x2c198  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2c19d  ldstr    aRelatedinforma// "RelatedInformation_Category_CustomerPre"...
0x2c1a2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2c1a7  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.Category::set_DisplayName(string)
0x2c1ac  ldloc.1
0x2c1ad  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.ListCategory
0x2c1b2  ldstr    aRelatedinforma_0// "RelatedInformation_NoPreference"
0x2c1b7  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.ListCategory::set_GridEmptyMessageResourceId(string)
0x2c1bc  ldloc.0
0x2c1bd  callvirt instance class [mscorlib]System.Collections.IList [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Context::get_Categories()
0x2c1c2  ldloc.1
0x2c1c3  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x2c1c8  pop
0x2c1c9  br.s     loc_2C232
0x2c1cb  ldarg.0
0x2c1cc  ldarg.3
0x2c1cd  ldarg.s  4
0x2c1cf  ldarg.1
0x2c1d0  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c1d5  ldarg.1
0x2c1d6  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x2c1db  ldarg.2
0x2c1dc  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Context Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelatedInformationControl::GetContext(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType formType, int32 formObjectType, string contextId, int32 tabIndex, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell formCell)
0x2c1e1  stloc.0
0x2c1e2  ldc.i4.2
0x2c1e3  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.CustomGridProviderFactory::.ctor()
0x2c1e8  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.CustomerPreferencesListCategory::.ctor(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.CustomerPreferenceType, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ICustomGridProviderFactory)
0x2c1ed  stloc.1
0x2c1ee  ldloc.1
0x2c1ef  ldc.i4.1
0x2c1f0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.Category::set_OrderIndex(int32)
0x2c1f5  ldloc.1
0x2c1f6  ldstr    aCategoryCustom_0// "Category_CustomerPreferredServices"
0x2c1fb  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.Category::set_CategoryId(string)
0x2c200  ldloc.1
0x2c201  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2c206  ldstr    aRelatedinforma_1// "RelatedInformation_Category_CustomerPre"...
0x2c20b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2c210  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.Category::set_DisplayName(string)
0x2c215  ldloc.1
0x2c216  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.ListCategory
0x2c21b  ldstr    aRelatedinforma_0// "RelatedInformation_NoPreference"
0x2c220  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.ListCategory::set_GridEmptyMessageResourceId(string)
0x2c225  ldloc.0
0x2c226  callvirt instance class [mscorlib]System.Collections.IList [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Context::get_Categories()
0x2c22b  ldloc.1
0x2c22c  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x2c231  pop
0x2c232  ldloc.0
0x2c233  ret
```
