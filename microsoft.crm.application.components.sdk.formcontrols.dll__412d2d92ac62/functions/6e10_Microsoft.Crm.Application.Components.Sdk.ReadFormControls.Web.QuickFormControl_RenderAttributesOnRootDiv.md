# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::RenderAttributesOnRootDiv

- ea: `0x6e10`
- end: `0x6f9f`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::RenderAttributesOnRootDiv`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x6bb0`

## callees

- `0x1330`
- `0x1450`
- `0x6910`
- `0x6950`
- `0x6980`
- `0x69a0`
- `0x69c0`
- `0x6e10`
- `0x7270`
- `0x72c0`

## string_xrefs

- `0x6e20`: `If QuickFormDescriptor is null, QuickFormControl.RenderAttributesOnRootDiv shouldnt even be called. FormId={0}`

## pseudocode

```c

```

## disassembly

```asm
0x6e10  ldarg.0
0x6e11  ldfld    class [mscorlib]System.Lazy`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_quickFormDescriptor
0x6e16  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor>::get_Value()
0x6e1b  stloc.0
0x6e1c  ldloc.0
0x6e1d  ldnull
0x6e1e  cgt.un
0x6e20  ldstr    aIfQuickformdes// "If QuickFormDescriptor is null, QuickFo"...
0x6e25  ldc.i4.1
0x6e26  newarr   [mscorlib]System.Object
0x6e2b  dup
0x6e2c  ldc.i4.0
0x6e2d  ldarg.0
0x6e2e  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::get_FormId()
0x6e33  box      [mscorlib]System.Guid
0x6e38  stelem.ref
0x6e39  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x6e3e  ldarg.1
0x6e3f  ldstr    aClass// "class"
0x6e44  ldstr    aMsCrmQuickform// "ms-crm-QuickForm"
0x6e49  ldc.i4.0
0x6e4a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string, bool)
0x6e4f  ldarg.1
0x6e50  ldstr    aDataControlmod// "data-controlmode"
0x6e55  ldarg.0
0x6e56  call     instance valuetype Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControlMode Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::get_ControlMode()
0x6e5b  stloc.1
0x6e5c  ldloca.s 1
0x6e5e  constrained. Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControlMode
0x6e64  callvirt instance string [mscorlib]System.Object::ToString()
0x6e69  ldc.i4.0
0x6e6a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string, bool)
0x6e6f  ldarg.1
0x6e70  ldstr    aDataFormid// "data-formid"
0x6e75  ldarg.0
0x6e76  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::get_FormId()
0x6e7b  stloc.2
0x6e7c  ldloca.s 2
0x6e7e  constrained. [mscorlib]System.Guid
0x6e84  callvirt instance string [mscorlib]System.Object::ToString()
0x6e89  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0x6e8e  ldarg.1
0x6e8f  ldstr    aDataFormstart// "data-formstart"
0x6e94  ldstr    a1_0// "1"
0x6e99  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0x6e9e  ldarg.1
0x6e9f  ldstr    aDataFdeid// "data-fdeid"
0x6ea4  ldarg.0
0x6ea5  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::get_FormDataEntityId()
0x6eaa  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0x6eaf  ldarg.1
0x6eb0  ldstr    aDataParentfdei// "data-parentfdeid"
0x6eb5  ldarg.0
0x6eb6  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x6ebb  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_FormDataEntityId()
0x6ec0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0x6ec5  ldarg.1
0x6ec6  ldstr    aDataUniqueid// "data-uniqueid"
0x6ecb  ldarg.0
0x6ecc  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::get_UniqueId()
0x6ed1  callvirt instance string [mscorlib]System.Object::ToString()
0x6ed6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0x6edb  ldarg.1
0x6edc  ldstr    aDataRelatedent// "data-relatedentityname"
0x6ee1  ldloc.0
0x6ee2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_EntityMetadata()
0x6ee7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x6eec  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0x6ef1  ldloc.0
0x6ef2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_EntityMetadata()
0x6ef7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x6efc  brfalse.s loc_6F19
0x6efe  ldarg.1
0x6eff  ldstr    aDataRelatedent_0// "data-relatedentity-primaryfieldname"
0x6f04  ldloc.0
0x6f05  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_EntityMetadata()
0x6f0a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x6f0f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x6f14  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0x6f19  ldarg.0
0x6f1a  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::get_Relationship()
0x6f1f  brfalse.s loc_6F50
0x6f21  ldarg.1
0x6f22  ldstr    aDataRelationsh// "data-relationshiproleordinal"
0x6f27  ldarg.0
0x6f28  call     instance int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::get_QuickFormRelationshipRoleOrdinal()
0x6f2d  stloc.3
0x6f2e  ldloca.s 3
0x6f30  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6f35  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x6f3a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0x6f3f  ldarg.1
0x6f40  ldstr    aDataQfrelname// "data-qfrelname"
0x6f45  ldarg.0
0x6f46  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::get_QuickFormRelationshipName()
0x6f4b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0x6f50  ldarg.0
0x6f51  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x6f56  brfalse.s loc_6F6E
0x6f58  ldarg.1
0x6f59  ldstr    aDataQfattribut// "data-qfattribute"
0x6f5e  ldarg.0
0x6f5f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x6f64  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x6f69  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0x6f6e  ldarg.0
0x6f6f  ldfld    bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_isVisible
0x6f74  brtrue.s loc_6F83
0x6f76  ldarg.1
0x6f77  ldc.i4.s 0x12
0x6f79  ldstr    aNone// "none"
0x6f7e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x6f83  ldarg.1
0x6f84  ldstr    aQuickformdefau// "quickformdefaultvisibility"
0x6f89  ldarg.0
0x6f8a  ldflda   bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_isVisible
0x6f8f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6f94  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x6f99  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0x6f9e  ret
```
