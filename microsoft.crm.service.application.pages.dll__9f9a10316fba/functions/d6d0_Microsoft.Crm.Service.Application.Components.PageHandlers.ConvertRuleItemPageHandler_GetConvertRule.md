# Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::GetConvertRule

- ea: `0xd6d0`
- end: `0xd73d`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::GetConvertRule`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xd240`
- `0xd880`

## callees

- `0xd6d0`

## pseudocode

```c

```

## disassembly

```asm
0xd6d0  ldarg.1
0xd6d1  brfalse.s loc_D6F4
0xd6d3  ldc.i4.3
0xd6d4  newarr   [mscorlib]System.String
0xd6d9  dup
0xd6da  ldc.i4.0
0xd6db  ldstr    aSourcechannelt// "sourcechanneltypecode"
0xd6e0  stelem.ref
0xd6e1  dup
0xd6e2  ldc.i4.1
0xd6e3  ldstr    aChannelpropert// "channelpropertygroupid"
0xd6e8  stelem.ref
0xd6e9  dup
0xd6ea  ldc.i4.2
0xd6eb  ldstr    aStatecode// "statecode"
0xd6f0  stelem.ref
0xd6f1  stloc.0
0xd6f2  br.s     loc_D70B
0xd6f4  ldc.i4.2
0xd6f5  newarr   [mscorlib]System.String
0xd6fa  dup
0xd6fb  ldc.i4.0
0xd6fc  ldstr    aSourcetypecode// "sourcetypecode"
0xd701  stelem.ref
0xd702  dup
0xd703  ldc.i4.1
0xd704  ldstr    aStatecode// "statecode"
0xd709  stelem.ref
0xd70a  stloc.0
0xd70b  ldarg.0
0xd70c  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd711  ldstr    aConvertruleid// "convertruleid"
0xd716  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd71b  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xd720  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xd725  stloc.1
0xd726  ldstr    aConvertrule// "convertrule"
0xd72b  ldloc.1
0xd72c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xd731  ldloc.0
0xd732  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd737  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd73c  ret
```
