# Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::BuildAddCustomActivityMenu

- ea: `0xf50`
- end: `0xfe7`
- name: `Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::BuildAddCustomActivityMenu`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf40`

## callees

- `0xf50`
- `0xff0`

## pseudocode

```c

```

## disassembly

```asm
0xf50  ldarg.0
0xf51  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_commands
0xf56  brfalse.s loc_F59
0xf58  ret
0xf59  ldarg.0
0xf5a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xf5f  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_controlToCommandMap
0xf64  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::.ctor()
0xf69  stloc.0
0xf6a  ldarg.0
0xf6b  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_IdPrefix()
0xf70  ldstr    aMenu// "Menu"
0xf75  call     string [mscorlib]System.String::Concat(string, string)
0xf7a  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Menu::.ctor(string)
0xf7f  stloc.1
0xf80  ldc.i4   0x1068
0xf85  ldc.i4.s 0x20
0xf87  ldarg.0
0xf88  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_Context()
0xf8d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf92  brfalse.s loc_FBF
0xf94  ldc.i4   0x1068
0xf99  ldc.i4.1
0xf9a  ldarg.0
0xf9b  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_Context()
0xfa0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfa5  brfalse.s loc_FBF
0xfa7  ldc.i4.s 0xA
0xfa9  stloc.2
0xfaa  ldc.i4.1
0xfab  stloc.3
0xfac  call     class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::get_CustomActivitiesByName()
0xfb1  stloc.s  4
0xfb3  ldarg.0
0xfb4  ldloc.1
0xfb5  ldloc.0
0xfb6  ldloc.s  4
0xfb8  ldloc.2
0xfb9  ldloc.3
0xfba  call     instance void Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::AddCustomActivityButtons(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.Menu menu, class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition> commands, class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata> activities, int32 menuSectionSequence, int32 menuSectionIndex)
0xfbf  ldarg.0
0xfc0  ldloc.0
0xfc1  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::ToArray()
0xfc6  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_commands
0xfcb  ldarg.0
0xfcc  ldloc.1
0xfcd  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::RenderXml(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer)
0xfd2  stfld    string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_layoutXml
0xfd7  ldarg.0
0xfd8  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_commands
0xfdd  ldlen
0xfde  brtrue.s loc_FE6
0xfe0  ldarg.0
0xfe1  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::AddRootNodeDisableDisplayRule()
0xfe6  ret
```
