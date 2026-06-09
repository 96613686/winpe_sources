# Microsoft.Crm.Common.Application.Commands.ApplicationCommand::FillResponseObject

- ea: `0x20b0`
- end: `0x21b3`
- name: `Microsoft.Crm.Common.Application.Commands.ApplicationCommand::FillResponseObject`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1cb0`

## callees

- `0x20b0`

## pseudocode

```c

```

## disassembly

```asm
0x20b0  ldarg.2
0x20b1  ldarg.3
0x20b2  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x20b7  stloc.0
0x20b8  ldc.i4.2
0x20b9  newarr   [mscorlib]System.String
0x20be  dup
0x20bf  ldc.i4.0
0x20c0  ldstr    aSubject// "subject"
0x20c5  stelem.ref
0x20c6  dup
0x20c7  ldc.i4.1
0x20c8  ldstr    aPrioritycode// "prioritycode"
0x20cd  stelem.ref
0x20ce  stloc.1
0x20cf  ldloc.0
0x20d0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x20d5  ldarg.1
0x20d6  ldloc.1
0x20d7  ldarg.3
0x20d8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x20dd  stloc.2
0x20de  ldarg.0
0x20df  ldstr    aSubject// "subject"
0x20e4  ldloc.2
0x20e5  ldstr    aSubject// "subject"
0x20ea  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x20ef  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x20f4  ldloc.2
0x20f5  ldstr    aPrioritycode// "prioritycode"
0x20fa  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0x20ff  brfalse.s loc_2117
0x2101  ldarg.0
0x2102  ldstr    aPrioritycode// "prioritycode"
0x2107  ldloc.2
0x2108  ldstr    aPrioritycode// "prioritycode"
0x210d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x2112  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2117  ldarg.0
0x2118  ldstr    aOriginatingact_0// "originatingactivityidtypecode"
0x211d  ldarg.2
0x211e  box      [mscorlib]System.Int32
0x2123  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2128  ldarg.2
0x2129  ldc.i4   0x1069
0x212e  sub
0x212f  switch   loc_21A1, loc_2159, loc_21B2, loc_216B, loc_21B2, loc_21B2, loc_217D
0x2150  ldarg.2
0x2151  ldc.i4   0x1072
0x2156  beq.s    loc_218F
0x2158  ret
0x2159  ldarg.0
0x215a  ldstr    aChanneltypecod// "channeltypecode"
0x215f  ldc.i4.1
0x2160  box      [mscorlib]System.Int32
0x2165  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x216a  ret
0x216b  ldarg.0
0x216c  ldstr    aChanneltypecod// "channeltypecode"
0x2171  ldc.i4.3
0x2172  box      [mscorlib]System.Int32
0x2177  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x217c  ret
0x217d  ldarg.0
0x217e  ldstr    aChanneltypecod// "channeltypecode"
0x2183  ldc.i4.4
0x2184  box      [mscorlib]System.Int32
0x2189  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x218e  ret
0x218f  ldarg.0
0x2190  ldstr    aChanneltypecod// "channeltypecode"
0x2195  ldc.i4.2
0x2196  box      [mscorlib]System.Int32
0x219b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x21a0  ret
0x21a1  ldarg.0
0x21a2  ldstr    aChanneltypecod// "channeltypecode"
0x21a7  ldc.i4.5
0x21a8  box      [mscorlib]System.Int32
0x21ad  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x21b2  ret
```
