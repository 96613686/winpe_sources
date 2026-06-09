# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreatePicklistValues

- ea: `0x5a20`
- end: `0x5a5e`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreatePicklistValues`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5a60`

## callees

- `0x5a20`

## pseudocode

```c

```

## disassembly

```asm
0x5a20  ldarg.3
0x5a21  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x5a26  newarr   [mscorlib]System.Int32
0x5a2b  stloc.0
0x5a2c  ldc.i4.0
0x5a2d  stloc.1
0x5a2e  br.s     loc_5A53
0x5a30  ldarg.3
0x5a31  ldloc.1
0x5a32  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x5a37  stloc.2
0x5a38  ldarg.1
0x5a39  ldarg.2
0x5a3a  ldloc.2
0x5a3b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5a40  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.AddPicklistValuesCommand::.ctor(string, string, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5a45  stloc.3
0x5a46  ldloc.0
0x5a47  ldloc.1
0x5a48  ldloc.3
0x5a49  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.AddPicklistValuesCommand::Execute()
0x5a4e  stelem.i4
0x5a4f  ldloc.1
0x5a50  ldc.i4.1
0x5a51  add
0x5a52  stloc.1
0x5a53  ldloc.1
0x5a54  ldarg.3
0x5a55  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x5a5a  blt.s    loc_5A30
0x5a5c  ldloc.0
0x5a5d  ret
```
