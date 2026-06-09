# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::ConfigureAppGridQueryFilter

- ea: `0x1de10`
- end: `0x1dee6`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::ConfigureAppGridQueryFilter`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1d330`

## callees

- `0x1c790`
- `0x1c7f0`
- `0x1c8a0`
- `0x1cb30`
- `0x1cbb0`
- `0x1cc10`
- `0x1cda0`
- `0x1de10`

## pseudocode

```c

```

## disassembly

```asm
0x1de10  ldarg.0
0x1de11  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGridQueryFilter Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_QueryFilter()
0x1de16  ldarg.0
0x1de17  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_EnableQuickFind()
0x1de1c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGridQueryFilter::set_ShowQuickFind(bool)
0x1de21  ldarg.0
0x1de22  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGridQueryFilter Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_QueryFilter()
0x1de27  ldarg.0
0x1de28  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_EnableContextualActions()
0x1de2d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGridQueryFilter::set_EnableContextualActions(bool)
0x1de32  ldarg.0
0x1de33  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_EnableViewPicker()
0x1de38  brfalse  loc_1DEE5
0x1de3d  ldarg.0
0x1de3e  ldfld    string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::_viewIds
0x1de43  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1de48  brfalse.s loc_1DE53
0x1de4a  ldc.i4.0
0x1de4b  newarr   [mscorlib]System.String
0x1de50  stloc.0
0x1de51  br.s     loc_1DEC7
0x1de53  ldarg.0
0x1de54  ldfld    string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::_viewIds
0x1de59  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1de5e  ldc.i4   0x9C40
0x1de63  ble.s    loc_1DEB0
0x1de65  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x1de6a  stloc.1
0x1de6b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1de70  ldstr    aInOrgWithId0AF// "In Org with ID: {0}, a form has a grid "...
0x1de75  ldc.i4.2
0x1de76  newarr   [mscorlib]System.Object
0x1de7b  dup
0x1de7c  ldc.i4.0
0x1de7d  ldloc.1
0x1de7e  box      [mscorlib]System.Guid
0x1de83  stelem.ref
0x1de84  dup
0x1de85  ldc.i4.1
0x1de86  ldarg.0
0x1de87  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1de8c  stelem.ref
0x1de8d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1de92  stloc.2
0x1de93  ldloc.1
0x1de94  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x1de99  ldloc.2
0x1de9a  ldc.i4.0
0x1de9b  newarr   [mscorlib]System.Object
0x1dea0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1dea5  ldstr    aTheFormHasView// "The form has viewIds with too many view"...
0x1deaa  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1deaf  throw
0x1deb0  ldarg.0
0x1deb1  ldfld    string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::_viewIds
0x1deb6  ldc.i4.1
0x1deb7  newarr   [mscorlib]System.Char
0x1debc  dup
0x1debd  ldc.i4.0
0x1debe  ldc.i4.s 0x2C
0x1dec0  stelem.i2
0x1dec1  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1dec6  stloc.0
0x1dec7  ldarg.0
0x1dec8  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGridQueryFilter Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_QueryFilter()
0x1decd  ldarg.0
0x1dece  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0x1ded3  ldarg.0
0x1ded4  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_ViewId()
0x1ded9  ldloc.0
0x1deda  ldarg.0
0x1dedb  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsGridAvailable()
0x1dee0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGridQueryFilter::ShowViewPicker(string, valuetype [mscorlib]System.Guid, string[], bool)
0x1dee5  ret
```
