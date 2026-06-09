# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::GetErrorMessage_0

- ea: `0x1e540`
- end: `0x1e5f0`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::GetErrorMessage_0`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1e230`
- `0x1e530`

## callees

- `0x1cda0`
- `0x1e540`

## string_xrefs

- `0x1e5b3`: `EmptyGridMessageMissingPrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x1e540  ldsfld   string [mscorlib]System.String::Empty
0x1e545  stloc.0
0x1e546  ldarg.1
0x1e547  ldc.i4.1
0x1e548  sub
0x1e549  switch   loc_1E560, loc_1E59C, loc_1E5AE, loc_1E5C0
0x1e55e  br.s     loc_1E5D0
0x1e560  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1e565  ldstr    aWebDashboardIn// "Web.Dashboard.InvalidEntityType"
0x1e56a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e56f  stloc.0
0x1e570  ldarg.0
0x1e571  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsGridAvailable()
0x1e576  brtrue.s loc_1E589
0x1e578  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1e57d  ldstr    aWebDashboardCh// "Web.Dashboard.Chart"
0x1e582  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e587  br.s     loc_1E598
0x1e589  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1e58e  ldstr    aWebDashboardLi// "Web.Dashboard.List"
0x1e593  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e598  starg.s  2
0x1e59a  br.s     loc_1E5D0
0x1e59c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1e5a1  ldstr    aWebDashboardTa// "Web.Dashboard.TargetEntityTypeMismatch"
0x1e5a6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e5ab  stloc.0
0x1e5ac  br.s     loc_1E5D0
0x1e5ae  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1e5b3  ldstr    aEmptygridmessa_0// "EmptyGridMessageMissingPrivilege"
0x1e5b8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e5bd  stloc.0
0x1e5be  br.s     loc_1E5D0
0x1e5c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1e5c5  ldstr    aGridLoadingDat// "Grid.Loading.Data.Failed"
0x1e5ca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e5cf  stloc.0
0x1e5d0  ldarg.2
0x1e5d1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1e5d6  brtrue.s loc_1E5EE
0x1e5d8  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1e5dd  ldloc.0
0x1e5de  ldc.i4.1
0x1e5df  newarr   [mscorlib]System.Object
0x1e5e4  dup
0x1e5e5  ldc.i4.0
0x1e5e6  ldarg.2
0x1e5e7  stelem.ref
0x1e5e8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e5ed  ret
0x1e5ee  ldloc.0
0x1e5ef  ret
```
