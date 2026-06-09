# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelatedInformationControl::AddCustomContext

- ea: `0x2c240`
- end: `0x2c81e`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelatedInformationControl::AddCustomContext`
- size: `1502`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2bff0`

## callees

- `0x2c240`
- `0x2c880`
- `0x2c900`

## string_xrefs

- `0x2c281`: `contractservicelevelcode`
- `0x2c339`: `RelatedInformation_Category_ServiceLevelsByContract`

## pseudocode

```c

```

## disassembly

```asm
0x2c240  ldnull
0x2c241  stloc.0
0x2c242  ldarg.1
0x2c243  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl
0x2c248  stloc.2
0x2c249  ldarg.1
0x2c24a  isinst   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl
0x2c24f  stloc.3
0x2c250  ldsfld   string [mscorlib]System.String::Empty
0x2c255  stloc.s  4
0x2c257  ldarg.s  5
0x2c259  brtrue.s loc_2C25D
0x2c25b  ldnull
0x2c25c  ret
0x2c25d  ldarg.1
0x2c25e  brfalse.s loc_2C268
0x2c260  ldarg.1
0x2c261  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c266  stloc.s  4
0x2c268  ldarg.3
0x2c269  ldc.i4.1
0x2c26a  beq      loc_2C722
0x2c26f  ldarg.3
0x2c270  ldc.i4.2
0x2c271  bne.un   loc_2C81C
0x2c276  ldarg.s  4
0x2c278  ldc.i4.s 0x70
0x2c27a  bne.un   loc_2C81C
0x2c27f  ldloc.s  4
0x2c281  ldstr    aContractservic// "contractservicelevelcode"
0x2c286  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c28b  brtrue.s loc_2C2E7
0x2c28d  ldloc.s  4
0x2c28f  ldstr    aContractid// "contractid"
0x2c294  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c299  brtrue   loc_2C35A
0x2c29e  ldloc.s  4
0x2c2a0  ldstr    aContractdetail// "contractdetailid"
0x2c2a5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c2aa  brtrue   loc_2C3FE
0x2c2af  ldloc.s  4
0x2c2b1  ldstr    aProductserialn// "productserialnumber"
0x2c2b6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c2bb  brtrue   loc_2C45B
0x2c2c0  ldloc.s  4
0x2c2c2  ldstr    aProductid// "productid"
0x2c2c7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c2cc  brtrue   loc_2C4DC
0x2c2d1  ldloc.s  4
0x2c2d3  ldstr    aKbarticleid// "kbarticleid"
0x2c2d8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c2dd  brtrue   loc_2C56D
0x2c2e2  br       loc_2C81C
0x2c2e7  ldarg.0
0x2c2e8  ldarg.3
0x2c2e9  ldarg.s  4
0x2c2eb  ldarg.1
0x2c2ec  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c2f1  ldloc.2
0x2c2f2  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::get_TabIndex()
0x2c2f7  ldarg.2
0x2c2f8  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Context Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelatedInformationControl::GetContext(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType formType, int32 formObjectType, string contextId, int32 tabIndex, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell formCell)
0x2c2fd  stloc.0
0x2c2fe  ldarg.1
0x2c2ff  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c304  ldarg.1
0x2c305  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c30a  ldc.i4.1
0x2c30b  newarr   [mscorlib]System.String
0x2c310  dup
0x2c311  ldc.i4.0
0x2c312  ldstr    aContractid// "contractid"
0x2c317  stelem.ref
0x2c318  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.CustomGridProviderFactory::.ctor()
0x2c31d  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.FetchListCategory::.ctor(string, string, string[], class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ICustomGridProviderFactory)
0x2c322  stloc.1
0x2c323  ldloc.1
0x2c324  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.EntityCategory
0x2c329  ldc.i4   0x3F2
0x2c32e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.EntityCategory::set_ObjectType(int32)
0x2c333  ldloc.1
0x2c334  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2c339  ldstr    aRelatedinforma_2// "RelatedInformation_Category_ServiceLeve"...
0x2c33e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2c343  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.Category::set_DisplayName(string)
0x2c348  ldloc.0
0x2c349  callvirt instance class [mscorlib]System.Collections.IList [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Context::get_Categories()
0x2c34e  ldloc.1
0x2c34f  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x2c354  pop
0x2c355  br       loc_2C81C
0x2c35a  ldarg.0
0x2c35b  ldarg.3
0x2c35c  ldarg.s  4
0x2c35e  ldarg.1
0x2c35f  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c364  ldloc.2
0x2c365  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::get_TabIndex()
0x2c36a  ldarg.2
0x2c36b  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Context Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelatedInformationControl::GetContext(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType formType, int32 formObjectType, string contextId, int32 tabIndex, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell formCell)
0x2c370  stloc.0
0x2c371  ldstr    aTitle// "title"
0x2c376  ldarg.1
0x2c377  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c37c  ldc.i4.1
0x2c37d  newarr   [mscorlib]System.String
0x2c382  dup
0x2c383  ldc.i4.0
0x2c384  ldstr    aCustomerid// "customerid"
0x2c389  stelem.ref
0x2c38a  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.CustomGridProviderFactory::.ctor()
0x2c38f  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.DynamicApiListCategory::.ctor(string, string, string[], class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ICustomGridProviderFactory)
0x2c394  stloc.1
0x2c395  ldloc.1
0x2c396  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.EntityCategory
0x2c39b  ldc.i4   0x3F2
0x2c3a0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.EntityCategory::set_ObjectType(int32)
0x2c3a5  ldloc.1
0x2c3a6  dup
0x2c3a7  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.Category::get_CategoryId()
0x2c3ac  ldstr    aChildowned// "ChildOwned"
0x2c3b1  call     string [mscorlib]System.String::Concat(string, string)
0x2c3b6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.Category::set_CategoryId(string)
0x2c3bb  ldloc.1
0x2c3bc  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.DynamicApiListCategory
0x2c3c1  dup
0x2c3c2  ldc.i4.1
0x2c3c3  ldstr    aContract// "Contract"
0x2c3c8  ldstr    aRetrieveactive// "RetrieveActiveChildOwnedContractsByAcco"...
0x2c3cd  ldstr    aRelatedinforma_3// "RelatedInformation_Category_ChildOwnedC"...
0x2c3d2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.DynamicApiListCategory::AddTypeCodeMap(int32, string, string, string)
0x2c3d7  ldc.i4.2
0x2c3d8  ldstr    aContract// "Contract"
0x2c3dd  ldstr    aRetrieveactive_0// "RetrieveActiveParentOwnedContractsByCon"...
0x2c3e2  ldstr    aRelatedinforma_4// "RelatedInformation_Category_ParentOwned"...
0x2c3e7  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.DynamicApiListCategory::AddTypeCodeMap(int32, string, string, string)
0x2c3ec  ldloc.0
0x2c3ed  callvirt instance class [mscorlib]System.Collections.IList [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Context::get_Categories()
0x2c3f2  ldloc.1
0x2c3f3  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x2c3f8  pop
0x2c3f9  br       loc_2C81C
0x2c3fe  ldarg.0
0x2c3ff  ldarg.3
0x2c400  ldarg.s  4
0x2c402  ldarg.1
0x2c403  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c408  ldloc.2
0x2c409  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::get_TabIndex()
0x2c40e  ldarg.2
0x2c40f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Context Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelatedInformationControl::GetContext(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType formType, int32 formObjectType, string contextId, int32 tabIndex, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell formCell)
0x2c414  stloc.0
0x2c415  ldstr    aTitle// "title"
0x2c41a  ldarg.1
0x2c41b  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c420  ldc.i4.1
0x2c421  newarr   [mscorlib]System.String
0x2c426  dup
0x2c427  ldc.i4.0
0x2c428  ldstr    aContractid// "contractid"
0x2c42d  stelem.ref
0x2c42e  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.CustomGridProviderFactory::.ctor()
0x2c433  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.FetchListCategory::.ctor(string, string, string[], class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ICustomGridProviderFactory)
0x2c438  stloc.1
0x2c439  ldloc.1
0x2c43a  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.EntityCategory
0x2c43f  ldc.i4   0x3F3
0x2c444  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.EntityCategory::set_ObjectType(int32)
0x2c449  ldloc.0
0x2c44a  callvirt instance class [mscorlib]System.Collections.IList [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Context::get_Categories()
0x2c44f  ldloc.1
0x2c450  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x2c455  pop
0x2c456  br       loc_2C81C
0x2c45b  ldarg.0
0x2c45c  ldarg.3
0x2c45d  ldarg.s  4
0x2c45f  ldarg.1
0x2c460  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c465  ldloc.2
0x2c466  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::get_TabIndex()
0x2c46b  ldarg.2
0x2c46c  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Context Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelatedInformationControl::GetContext(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType formType, int32 formObjectType, string contextId, int32 tabIndex, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell formCell)
0x2c471  stloc.0
0x2c472  ldstr    aProductserialn// "productserialnumber"
0x2c477  ldstr    aProductserialn// "productserialnumber"
0x2c47c  ldc.i4.1
0x2c47d  newarr   [mscorlib]System.String
0x2c482  dup
0x2c483  ldc.i4.0
0x2c484  ldstr    aContractdetail// "contractdetailid"
0x2c489  stelem.ref
0x2c48a  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.CustomGridProviderFactory::.ctor()
0x2c48f  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.FetchListCategory::.ctor(string, string, string[], class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ICustomGridProviderFactory)
0x2c494  stloc.1
0x2c495  ldloc.1
0x2c496  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.EntityCategory
0x2c49b  ldc.i4   0x3F3
0x2c4a0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.EntityCategory::set_ObjectType(int32)
0x2c4a5  ldloc.1
0x2c4a6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2c4ab  ldstr    aRelatedinforma_5// "RelatedInformation_Category_SerialNumbe"...
0x2c4b0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2c4b5  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.Category::set_DisplayName(string)
0x2c4ba  ldloc.1
0x2c4bb  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.ListCategory
0x2c4c0  ldstr    aRelatedinforma_6// "RelatedInformation_NoSerialNumberInCont"...
0x2c4c5  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.ListCategory::set_GridEmptyMessageResourceId(string)
0x2c4ca  ldloc.0
0x2c4cb  callvirt instance class [mscorlib]System.Collections.IList [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Context::get_Categories()
0x2c4d0  ldloc.1
0x2c4d1  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x2c4d6  pop
0x2c4d7  br       loc_2C81C
0x2c4dc  ldarg.0
0x2c4dd  ldarg.3
0x2c4de  ldarg.s  4
0x2c4e0  ldarg.1
0x2c4e1  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c4e6  ldloc.2
0x2c4e7  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::get_TabIndex()
0x2c4ec  ldarg.2
0x2c4ed  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Context Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelatedInformationControl::GetContext(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType formType, int32 formObjectType, string contextId, int32 tabIndex, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell formCell)
0x2c4f2  stloc.0
0x2c4f3  ldstr    aName// "name"
0x2c4f8  ldstr    aName// "name"
0x2c4fd  ldarg.1
0x2c4fe  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c503  ldstr    aProduct_0// "Product"
0x2c508  ldstr    aRetrieveproduc// "RetrieveProductsByContractDetail"
0x2c50d  ldc.i4.1
0x2c50e  newarr   [mscorlib]System.String
0x2c513  dup
0x2c514  ldc.i4.0
0x2c515  ldstr    aContractdetail// "contractdetailid"
0x2c51a  stelem.ref
0x2c51b  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.CustomGridProviderFactory::.ctor()
0x2c520  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.ApiListCategory::.ctor(string, string, string, string, string, string[], class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ICustomGridProviderFactory)
0x2c525  stloc.1
0x2c526  ldloc.1
0x2c527  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.EntityCategory
0x2c52c  ldc.i4   0x400
0x2c531  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.EntityCategory::set_ObjectType(int32)
0x2c536  ldloc.1
0x2c537  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2c53c  ldstr    aRelatedinforma_7// "RelatedInformation_Category_ProductsByC"...
0x2c541  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2c546  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.Category::set_DisplayName(string)
0x2c54b  ldloc.1
0x2c54c  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.ListCategory
0x2c551  ldc.i4   0x400
0x2c556  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.ListCategory::set_TargetObjectType(int32)
0x2c55b  ldloc.0
0x2c55c  callvirt instance class [mscorlib]System.Collections.IList [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Context::get_Categories()
0x2c561  ldloc.1
0x2c562  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x2c567  pop
0x2c568  br       loc_2C81C
0x2c56d  ldarg.0
0x2c56e  ldarg.3
0x2c56f  ldarg.s  4
0x2c571  ldarg.1
0x2c572  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c577  ldloc.2
0x2c578  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::get_TabIndex()
0x2c57d  ldarg.2
0x2c57e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Context Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelatedInformationControl::GetContext(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType formType, int32 formObjectType, string contextId, int32 tabIndex, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell formCell)
0x2c583  stloc.0
0x2c584  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x2c589  brfalse  loc_2C698
0x2c58e  ldstr    aTitle// "title"
0x2c593  ldstr    aTitle// "title"
0x2c598  ldarg.1
0x2c599  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c59e  ldstr    aArticle// "Article"
0x2c5a3  ldstr    aRetrievebytopi// "RetrieveByTopIncidentProduct"
0x2c5a8  ldc.i4.1
0x2c5a9  newarr   [mscorlib]System.String
0x2c5ae  dup
0x2c5af  ldc.i4.0
0x2c5b0  ldstr    aProductid// "productid"
0x2c5b5  stelem.ref
0x2c5b6  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.CustomGridProviderFactory::.ctor()
0x2c5bb  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.ApiListCategory::.ctor(string, string, string, string, string, string[], class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ICustomGridProviderFactory)
0x2c5c0  stloc.1
0x2c5c1  ldloc.1
0x2c5c2  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.EntityCategory
0x2c5c7  ldc.i4.s 0x7F
0x2c5c9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.EntityCategory::set_ObjectType(int32)
0x2c5ce  ldloc.1
0x2c5cf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2c5d4  ldstr    aRelatedinforma_8// "RelatedInformation_Category_MostAttache"...
0x2c5d9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2c5de  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.Category::set_DisplayName(string)
0x2c5e3  ldloc.1
0x2c5e4  dup
0x2c5e5  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.Category::get_CategoryId()
0x2c5ea  ldstr    aTopbyproduct// "TopByProduct"
0x2c5ef  call     string [mscorlib]System.String::Concat(string, string)
0x2c5f4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.Category::set_CategoryId(string)
  ... truncated ...
```
