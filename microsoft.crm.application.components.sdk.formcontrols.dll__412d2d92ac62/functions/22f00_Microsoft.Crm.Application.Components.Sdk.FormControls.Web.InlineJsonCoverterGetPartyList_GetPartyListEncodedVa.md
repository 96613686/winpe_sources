# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.InlineJsonCoverterGetPartyList::GetPartyListEncodedValue

- ea: `0x22f00`
- end: `0x22faf`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.InlineJsonCoverterGetPartyList::GetPartyListEncodedValue`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x179a0`
- `0x17a00`
- `0x182e0`
- `0x185e0`
- `0x1fc10`
- `0x22e00`
- `0x22f00`

## pseudocode

```c

```

## disassembly

```asm
0x22f00  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListControl::.ctor()
0x22f05  stloc.1
0x22f06  ldloc.1
0x22f07  ldarg.1
0x22f08  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::set_DataSource(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity value)
0x22f0d  ldarg.3
0x22f0e  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty::get_RawValue()
0x22f13  brfalse.s loc_22F3F
0x22f15  ldarg.3
0x22f16  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty::get_RawValue()
0x22f1b  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0x22f20  stloc.3
0x22f21  ldloc.1
0x22f22  ldloc.3
0x22f23  brfalse.s loc_22F2E
0x22f25  ldloc.3
0x22f26  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x22f2b  ldc.i4.1
0x22f2c  bgt.s    loc_22F35
0x22f2e  ldstr    aSingle// "single"
0x22f33  br.s     loc_22F3A
0x22f35  ldstr    aMulti// "multi"
0x22f3a  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupStyle(string value)
0x22f3f  ldloc.1
0x22f40  ldarg.2
0x22f41  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata value)
0x22f46  ldloc.1
0x22f47  ldarg.3
0x22f48  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProperty::get_RawValue()
0x22f4d  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object value)
0x22f52  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x22f57  stloc.2
0x22f58  ldloc.2
0x22f59  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x22f5e  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x22f63  stloc.s  4
0x22f65  ldloc.s  4
0x22f67  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x22f6c  stloc.s  5
0x22f6e  ldloc.1
0x22f6f  ldc.i4.6
0x22f70  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::set_RenderMode(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlRenderMode value)
0x22f75  ldloc.1
0x22f76  ldloc.s  5
0x22f78  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x22f7d  ldloc.2
0x22f7e  callvirt instance string [mscorlib]System.Object::ToString()
0x22f83  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x22f88  stloc.0
0x22f89  leave.s  loc_22FAD
0x22f8b  ldloc.s  5
0x22f8d  brfalse.s loc_22F96
0x22f8f  ldloc.s  5
0x22f91  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22f96  endfinally
0x22f97  ldloc.s  4
0x22f99  brfalse.s loc_22FA2
0x22f9b  ldloc.s  4
0x22f9d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22fa2  endfinally
0x22fa3  ldloc.1
0x22fa4  brfalse.s loc_22FAC
0x22fa6  ldloc.1
0x22fa7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22fac  endfinally
0x22fad  ldloc.0
0x22fae  ret
```
