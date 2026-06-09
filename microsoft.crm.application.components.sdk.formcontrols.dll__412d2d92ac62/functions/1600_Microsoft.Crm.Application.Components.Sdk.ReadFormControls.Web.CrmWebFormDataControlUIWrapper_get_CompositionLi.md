# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_CompositionLinkControlDescriptor

- ea: `0x1600`
- end: `0x169f`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_CompositionLinkControlDescriptor`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1450`
- `0x15b0`
- `0x1600`

## string_xrefs

- `0x1611`: `Control does not host composite data.`
- `0x1621`: `_compositionLinkControl`
- `0x162c`: `CompositeFieldType`

## pseudocode

```c

```

## disassembly

```asm
0x1600  ldarg.0
0x1601  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::_compositionLinkControlDescriptor
0x1606  brtrue   loc_1698
0x160b  ldarg.0
0x160c  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_HasCompositeData()
0x1611  ldstr    aControlDoesNot// "Control does not host composite data."
0x1616  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x161b  ldarg.0
0x161c  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1621  ldstr    aCompositionlin// "_compositionLinkControl"
0x1626  call     string [mscorlib]System.String::Concat(string, string)
0x162b  stloc.0
0x162c  ldstr    aCompositefield// "CompositeFieldType"
0x1631  ldarg.0
0x1632  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CompositeFieldType> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::_compositeFieldType
0x1637  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CompositeFieldType>::get_Value()
0x163c  stloc.2
0x163d  ldloca.s 2
0x163f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1644  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1649  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ParameterDescriptor::.ctor(string, string)
0x164e  stloc.1
0x164f  ldarg.0
0x1650  ldloc.0
0x1651  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.FormControlClassId::CompositionLinkControl
0x1656  stloc.3
0x1657  ldloca.s 3
0x1659  constrained. [mscorlib]System.Guid
0x165f  callvirt instance string [mscorlib]System.Object::ToString()
0x1664  ldarg.0
0x1665  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x166a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x166f  ldarg.0
0x1670  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x1675  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x167a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x167f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1684  ldc.i4.1
0x1685  newarr   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ParameterDescriptor
0x168a  dup
0x168b  ldc.i4.0
0x168c  ldloc.1
0x168d  stelem.ref
0x168e  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::.ctor(string, string, string, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ParameterDescriptor>)
0x1693  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::_compositionLinkControlDescriptor
0x1698  ldarg.0
0x1699  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::_compositionLinkControlDescriptor
0x169e  ret
```
