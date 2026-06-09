# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddInlineLookupDivToTitleContainer

- ea: `0xc300`
- end: `0xc50b`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddInlineLookupDivToTitleContainer`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0xbee0`

## callees

- `0x2c50`
- `0x2e30`
- `0x2e70`
- `0x2eb0`
- `0x2f50`
- `0x2f70`
- `0xc300`
- `0xf5e0`
- `0x109b0`
- `0x1c730`
- `0x1c7b0`
- `0x1cb30`
- `0x1e7e0`
- `0x1e8f0`

## pseudocode

```c

```

## disassembly

```asm
0xc300  ldarg.0
0xc301  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xc306  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xc30b  stloc.0
0xc30c  ldarg.0
0xc30d  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0xc312  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xc317  stloc.1
0xc318  ldarg.0
0xc319  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_ConnectionToEntity()
0xc31e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xc323  stloc.2
0xc324  ldnull
0xc325  stloc.3
0xc326  ldstr    aDiv// "div"
0xc32b  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xc330  dup
0xc331  stloc.3
0xc332  stloc.s  4
0xc334  ldloc.3
0xc335  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xc33a  ldstr    aClass// "class"
0xc33f  ldstr    aMsCrmInlineLoo_0// "ms-crm-Inline-Lookup-Subgrid ms-crm-Inl"...
0xc344  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xc349  ldloc.3
0xc34a  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xc34f  ldstr    aId// "id"
0xc354  ldstr    aInlinelookupco// "inlineLookupControlForSubgrid_"
0xc359  ldloc.0
0xc35a  call     string [mscorlib]System.String::Concat(string, string)
0xc35f  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xc364  ldloc.3
0xc365  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xc36a  ldstr    aTargetentityty// "targetEntityType"
0xc36f  ldloc.1
0xc370  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xc375  ldloc.3
0xc376  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xc37b  ldstr    aConnectiontoen// "connectionToEntity"
0xc380  ldloc.2
0xc381  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xc386  ldloc.3
0xc387  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xc38c  ldstr    aConnectiontoca// "connectionToCategory"
0xc391  ldarg.0
0xc392  call     instance unsigned int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_ConnectionToCategory()
0xc397  stloc.s  5
0xc399  ldloca.s 5
0xc39b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xc3a0  call     instance string [mscorlib]System.UInt32::ToString(class [mscorlib]System.IFormatProvider)
0xc3a5  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xc3aa  newobj   instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::.ctor()
0xc3af  stloc.s  6
0xc3b1  ldarg.0
0xc3b2  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0xc3b7  stloc.s  7
0xc3b9  ldarg.0
0xc3ba  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0xc3bf  ldstr    aConnection// "connection"
0xc3c4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc3c9  brfalse.s loc_C3E2
0xc3cb  ldarg.0
0xc3cc  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_ConnectionToEntity()
0xc3d1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc3d6  brtrue.s loc_C3E2
0xc3d8  ldarg.0
0xc3d9  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_ConnectionToEntity()
0xc3de  stloc.s  7
0xc3e0  br.s     loc_C3F1
0xc3e2  ldarg.0
0xc3e3  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::IsProductsGrid()
0xc3e8  brfalse.s loc_C3F1
0xc3ea  ldstr    aProductpricele// "productpricelevel"
0xc3ef  stloc.s  7
0xc3f1  ldarg.0
0xc3f2  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::IsProductAssociationInlineGrid()
0xc3f7  brfalse.s loc_C40A
0xc3f9  ldloc.s  6
0xc3fb  ldstr    a89a80f99F38841// "89A80F99-F388-412A-ADD2-D75C6ACD930F"
0xc400  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xc405  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::set_DefaultViewId(valuetype [mscorlib]System.Guid value)
0xc40a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc40f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc414  ldloc.s  7
0xc416  ldc.i4.1
0xc417  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xc41c  stloc.s  8
0xc41e  ldloc.s  6
0xc420  ldloc.s  7
0xc422  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::set_EntityLogicalName(string value)
0xc427  ldloc.s  6
0xc429  ldloc.0
0xc42a  ldstr    aAddimagebutton// "_addImageButton"
0xc42f  call     string [mscorlib]System.String::Concat(string, string)
0xc434  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::set_AddLookupImageButton(string value)
0xc439  ldloc.s  6
0xc43b  ldloc.s  8
0xc43d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xc442  stloc.s  9
0xc444  ldloca.s 9
0xc446  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc44b  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc450  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::set_UnboundLookupTypes(string value)
0xc455  ldloc.s  6
0xc457  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xc45c  ldstr    aId// "id"
0xc461  ldstr    aLookup_0// "lookup_"
0xc466  ldloc.0
0xc467  call     string [mscorlib]System.String::Concat(string, string)
0xc46c  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xc471  ldloc.s  6
0xc473  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xc478  ldstr    aDummyDataAttri// "dummy-data-attributename"
0xc47d  ldstr    asc_359D6// "_"
0xc482  ldloc.0
0xc483  call     string [mscorlib]System.String::Concat(string, string)
0xc488  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xc48d  ldloc.s  6
0xc48f  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xc494  ldstr    aDataLayout// "data-layout"
0xc499  ldstr    a0// "0"
0xc49e  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xc4a3  ldloc.s  6
0xc4a5  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xc4aa  ldstr    aDataFdeid// "data-fdeid"
0xc4af  ldstr    aPrimaryentity// "PrimaryEntity"
0xc4b4  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xc4b9  ldloc.s  6
0xc4bb  ldc.i4.0
0xc4bc  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0xc4c1  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::set_LookupBrowse(valuetype [mscorlib]System.Nullable`1<bool> value)
0xc4c6  ldloc.s  6
0xc4c8  ldloc.s  7
0xc4ca  ldc.i4.0
0xc4cb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc4d0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc4d5  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::set_IsInlineNewEnabled(bool value)
0xc4da  ldloc.s  6
0xc4dc  ldc.i4.1
0xc4dd  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::set_LookupDialogMultipleSelect(bool value)
0xc4e2  ldloc.3
0xc4e3  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xc4e8  ldloc.s  6
0xc4ea  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xc4ef  leave.s  loc_C509
0xc4f1  ldloc.s  6
0xc4f3  brfalse.s loc_C4FC
0xc4f5  ldloc.s  6
0xc4f7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc4fc  endfinally
0xc4fd  ldloc.s  4
0xc4ff  brfalse.s loc_C508
0xc501  ldloc.s  4
0xc503  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc508  endfinally
0xc509  ldloc.3
0xc50a  ret
```
