# Microsoft.Crm.Application.Components.UI.Button::.ctor_5

- ea: `0x14fc0`
- end: `0x15060`
- name: `Microsoft.Crm.Application.Components.UI.Button::.ctor_5`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14f70`
- `0x14fb0`

## callees

- `0x14fc0`
- `0x15090`
- `0x150d0`
- `0x15110`
- `0x151b0`
- `0x23c30`
- `0x24040`

## pseudocode

```c

```

## disassembly

```asm
0x14fc0  ldarg.0
0x14fc1  ldsfld   string [mscorlib]System.String::Empty
0x14fc6  stfld    string Microsoft.Crm.Application.Components.UI.Button::_resourceId
0x14fcb  ldarg.0
0x14fcc  ldsfld   string [mscorlib]System.String::Empty
0x14fd1  stfld    string Microsoft.Crm.Application.Components.UI.Button::_cssClass
0x14fd6  ldarg.0
0x14fd7  ldsfld   string [mscorlib]System.String::Empty
0x14fdc  stfld    string Microsoft.Crm.Application.Components.UI.Button::_title
0x14fe1  ldarg.0
0x14fe2  ldsfld   string [mscorlib]System.String::Empty
0x14fe7  stfld    string Microsoft.Crm.Application.Components.UI.Button::_text
0x14fec  ldarg.0
0x14fed  ldsfld   string [mscorlib]System.String::Empty
0x14ff2  stfld    string Microsoft.Crm.Application.Components.UI.Button::_accessKey
0x14ff7  ldarg.0
0x14ff8  ldsfld   string [mscorlib]System.String::Empty
0x14ffd  stfld    string Microsoft.Crm.Application.Components.UI.Button::_innerHtml
0x15002  ldarg.0
0x15003  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::.ctor()
0x15008  ldarg.0
0x15009  ldarg.1
0x1500a  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1500f  ldarg.s  6
0x15011  brfalse.s loc_15041
0x15013  ldarg.0
0x15014  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15019  ldarg.2
0x1501a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1501f  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x15024  call     instance void Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string value)
0x15029  ldarg.0
0x1502a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1502f  ldarg.2
0x15030  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15035  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x1503a  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x1503f  br.s     loc_15048
0x15041  ldarg.0
0x15042  ldarg.2
0x15043  call     instance void Microsoft.Crm.Application.Components.UI.Button::set_ResourceId(string value)
0x15048  ldarg.0
0x15049  ldarg.3
0x1504a  call     instance void Microsoft.Crm.Application.Components.UI.Button::set_OnClick(string value)
0x1504f  ldarg.0
0x15050  ldarg.s  4
0x15052  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x15057  ldarg.0
0x15058  ldarg.s  5
0x1505a  call     instance void Microsoft.Crm.Application.Components.UI.Button::set_CssClass(string value)
0x1505f  ret
```
