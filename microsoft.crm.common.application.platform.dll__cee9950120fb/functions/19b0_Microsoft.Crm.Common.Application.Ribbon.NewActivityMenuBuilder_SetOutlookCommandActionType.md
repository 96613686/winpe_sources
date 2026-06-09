# Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::SetOutlookCommandActionType

- ea: `0x19b0`
- end: `0x1a2d`
- name: `Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::SetOutlookCommandActionType`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1990`

## callees

- `0x19b0`
- `0x1a30`

## pseudocode

```c

```

## disassembly

```asm
0x19b0  ldarg.0
0x19b1  ldarg.1
0x19b2  call     instance bool Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::HasOutlookForm(int32 activityTypeCode)
0x19b7  brfalse.s loc_1A2C
0x19b9  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::.ctor()
0x19be  stloc.0
0x19bf  ldloc.0
0x19c0  ldc.i4.4
0x19c1  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::ActionType
0x19c6  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::.ctor()
0x19cb  stloc.1
0x19cc  ldloc.1
0x19cd  ldc.i4.7
0x19ce  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::ActionType
0x19d3  ldloc.1
0x19d4  ldarga.s 1
0x19d6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19db  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x19e0  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::Data
0x19e5  ldloc.0
0x19e6  ldloc.1
0x19e7  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.ActionAttributes [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Attributes
0x19ec  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler>::.ctor()
0x19f1  stloc.2
0x19f2  ldloc.2
0x19f3  ldloc.0
0x19f4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler>::Add(var<u1>)
0x19f9  ldarg.2
0x19fa  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Actions
0x19ff  stloc.3
0x1a00  ldc.i4.0
0x1a01  stloc.s  4
0x1a03  br.s     loc_1A19
0x1a05  ldloc.3
0x1a06  ldloc.s  4
0x1a08  ldelem.ref
0x1a09  stloc.s  5
0x1a0b  ldloc.2
0x1a0c  ldloc.s  5
0x1a0e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler>::Add(var<u1>)
0x1a13  ldloc.s  4
0x1a15  ldc.i4.1
0x1a16  add
0x1a17  stloc.s  4
0x1a19  ldloc.s  4
0x1a1b  ldloc.3
0x1a1c  ldlen
0x1a1d  conv.i4
0x1a1e  blt.s    loc_1A05
0x1a20  ldarg.2
0x1a21  ldloc.2
0x1a22  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler>::ToArray()
0x1a27  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Actions
0x1a2c  ret
```
