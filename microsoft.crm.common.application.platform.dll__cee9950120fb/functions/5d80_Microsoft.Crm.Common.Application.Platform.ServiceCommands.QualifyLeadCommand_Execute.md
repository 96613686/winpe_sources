# Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyLeadCommand::Execute

- ea: `0x5d80`
- end: `0x5e5a`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyLeadCommand::Execute`
- size: `218`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2540`
- `0x2560`

## callees

- `0x5d80`

## pseudocode

```c

```

## disassembly

```asm
0x5d80  ldarg.0
0x5d81  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::XrmExecuteInternal()
0x5d86  castclass [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QualifyLeadResponse
0x5d8b  stloc.0
0x5d8c  leave.s  loc_5DC5
0x5d8e  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x5d93  ldc.i4   0x8004F800
0x5d98  bne.un.s loc_5DC3
0x5d9a  ldc.i4.4
0x5d9b  ldarg.0
0x5d9c  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::get_OrganizationContext()
0x5da1  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5da6  stloc.2
0x5da7  ldc.i4   0x8004F800
0x5dac  ldc.i4.1
0x5dad  newarr   [mscorlib]System.Object
0x5db2  dup
0x5db3  ldc.i4.0
0x5db4  ldloc.2
0x5db5  ldc.i4.1
0x5db6  ldnull
0x5db7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::GetDisplayName(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle, class [mscorlib]System.Globalization.CultureInfo)
0x5dbc  stelem.ref
0x5dbd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x5dc2  throw
0x5dc3  rethrow
0x5dc5  ldnull
0x5dc6  stloc.1
0x5dc7  ldloc.0
0x5dc8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReferenceCollection [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QualifyLeadResponse::get_CreatedEntities()
0x5dcd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::GetEnumerator()
0x5dd2  stloc.3
0x5dd3  br.s     loc_5E22
0x5dd5  ldloc.3
0x5dd6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::get_Current()
0x5ddb  stloc.s  4
0x5ddd  ldloc.s  4
0x5ddf  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x5de4  stloc.s  5
0x5de6  ldloc.s  5
0x5de8  ldstr    aOpportunity// "opportunity"
0x5ded  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5df2  brtrue.s loc_5E12
0x5df4  ldloc.s  5
0x5df6  ldstr    aAccount// "account"
0x5dfb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e00  brtrue.s loc_5E22
0x5e02  ldloc.s  5
0x5e04  ldstr    aContact// "contact"
0x5e09  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e0e  brtrue.s loc_5E22
0x5e10  br.s     loc_5E17
0x5e12  ldloc.s  4
0x5e14  stloc.1
0x5e15  br.s     loc_5E22
0x5e17  ldstr    aOnlyOneOfAccou// "Only one of account/contact/opportunity"...
0x5e1c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x5e21  throw
0x5e22  ldloc.3
0x5e23  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5e28  brtrue.s loc_5DD5
0x5e2a  leave.s  loc_5E36
0x5e2c  ldloc.3
0x5e2d  brfalse.s loc_5E35
0x5e2f  ldloc.3
0x5e30  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5e35  endfinally
0x5e36  ldarg.0
0x5e37  ldfld    bool Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyLeadCommand::_hasCampaignId
0x5e3c  brtrue.s loc_5E53
0x5e3e  ldarg.0
0x5e3f  ldfld    bool Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyLeadCommand::_showNew
0x5e44  brfalse.s loc_5E53
0x5e46  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReferenceCollection::.ctor()
0x5e4b  dup
0x5e4c  ldloc.1
0x5e4d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::Add(var<u1>)
0x5e52  ret
0x5e53  ldloc.0
0x5e54  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReferenceCollection [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QualifyLeadResponse::get_CreatedEntities()
0x5e59  ret
```
