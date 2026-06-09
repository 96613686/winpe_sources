# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::.ctor

- ea: `0x1f550`
- end: `0x1f5ec`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::.ctor`
- size: `156`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1a520`
- `0x22e00`
- `0x24800`

## callees

- `0x17cf0`
- `0x182a0`
- `0x1f600`
- `0x1f940`

## pseudocode

```c

```

## disassembly

```asm
0x1f550  ldarg.0
0x1f551  ldstr    aSingle// "single"
0x1f556  stfld    string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_lookupStyle
0x1f55b  ldarg.0
0x1f55c  ldc.i4.1
0x1f55d  stfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_autoResolve
0x1f562  ldarg.0
0x1f563  ldc.i4.1
0x1f564  stfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_allowFilterOff
0x1f569  ldarg.0
0x1f56a  ldc.i4.1
0x1f56b  stfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_showProperty
0x1f570  ldarg.0
0x1f571  ldsfld   string [mscorlib]System.String::Empty
0x1f576  stfld    string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_relationshipName
0x1f57b  ldarg.0
0x1f57c  ldsfld   string [mscorlib]System.String::Empty
0x1f581  stfld    string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_dependentAttributeName
0x1f586  ldarg.0
0x1f587  ldsfld   string [mscorlib]System.String::Empty
0x1f58c  stfld    string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_dependentAttributeType
0x1f591  ldarg.0
0x1f592  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f597  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_defaultViewId
0x1f59c  ldarg.0
0x1f59d  ldsfld   string [mscorlib]System.String::Empty
0x1f5a2  stfld    string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_savedQueryType
0x1f5a7  ldarg.0
0x1f5a8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f5ad  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_crmAttributeId
0x1f5b2  ldarg.0
0x1f5b3  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup::.ctor()
0x1f5b8  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::.ctor(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl uiControl)
0x1f5bd  ldarg.0
0x1f5be  ldc.i4.0
0x1f5bf  newarr   [mscorlib]System.Int32
0x1f5c4  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[] value)
0x1f5c9  ldarg.0
0x1f5ca  ldarg.0
0x1f5cb  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x1f5d0  isinst   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup
0x1f5d5  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_innerLookup
0x1f5da  ldarg.0
0x1f5db  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_innerLookup
0x1f5e0  ldarg.0
0x1f5e1  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_EnableTouchBehavior()
0x1f5e6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup::set_UseTouchSkin(bool)
0x1f5eb  ret
```
