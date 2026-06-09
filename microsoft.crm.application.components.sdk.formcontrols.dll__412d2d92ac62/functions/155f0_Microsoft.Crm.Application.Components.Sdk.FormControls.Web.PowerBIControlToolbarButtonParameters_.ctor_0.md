# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::.ctor_0

- ea: `0x155f0`
- end: `0x1569b`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::.ctor_0`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x17230`

## callees

- `0x15530`
- `0x15550`
- `0x15570`
- `0x15590`
- `0x155b0`
- `0x155d0`
- `0x155f0`

## pseudocode

```c

```

## disassembly

```asm
0x155f0  ldarg.0
0x155f1  call     instance void [mscorlib]System.Object::.ctor()
0x155f6  ldsfld   string [mscorlib]System.String::Empty
0x155fb  stloc.0
0x155fc  ldsfld   string [mscorlib]System.String::Empty
0x15601  stloc.1
0x15602  ldarg.1
0x15603  switch   loc_15616, loc_1562E, loc_15646
0x15614  br.s     loc_1565C
0x15616  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1561b  ldstr    aPowerbiruntime// "PowerBIRuntime_ContextButton_Refresh"
0x15620  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15625  stloc.1
0x15626  ldstr    aImgsRefreshPng// "/_imgs/refresh.png"
0x1562b  stloc.0
0x1562c  br.s     loc_1565C
0x1562e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15633  ldstr    aPowerbiruntime_0// "PowerBIRuntime_ContextButton_ViewDetail"
0x15638  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1563d  stloc.1
0x1563e  ldstr    aImgsPowerbidas// "/_imgs/powerbidashboard.png"
0x15643  stloc.0
0x15644  br.s     loc_1565C
0x15646  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1564b  ldstr    aPowerbiruntime_1// "PowerBIRuntime_ContextButton_Enlarge"
0x15650  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15655  stloc.1
0x15656  ldstr    aImgsEnlargePng// "/_imgs/enlarge.png"
0x1565b  stloc.0
0x1565c  ldarg.0
0x1565d  ldarga.s 1
0x1565f  constrained. Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonOptions
0x15665  callvirt instance string [mscorlib]System.Object::ToString()
0x1566a  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::set_ButtonId(string value)
0x1566f  ldarg.0
0x15670  ldstr    aMsCrmPowerbiTo// "ms-crm-powerbi-toolbar-buttons"
0x15675  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::set_ClassName(string value)
0x1567a  ldarg.0
0x1567b  ldloc.0
0x1567c  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::set_ButtonImageBase(string value)
0x15681  ldarg.0
0x15682  ldloc.1
0x15683  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::set_ButtonImageAltText(string value)
0x15688  ldarg.0
0x15689  ldloc.1
0x1568a  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::set_ButtonImageTitle(string value)
0x1568f  ldarg.0
0x15690  ldstr    aJavascript// "javascript:;"
0x15695  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::set_ButtonImageHref(string value)
0x1569a  ret
```
