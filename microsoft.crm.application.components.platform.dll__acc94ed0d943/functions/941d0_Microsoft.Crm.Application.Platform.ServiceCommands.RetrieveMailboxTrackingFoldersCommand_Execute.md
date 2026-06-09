# Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMailboxTrackingFoldersCommand::Execute

- ea: `0x941d0`
- end: `0x94222`
- name: `Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMailboxTrackingFoldersCommand::Execute`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x90e70`
- `0x941d0`

## string_xrefs

- `0x941d5`: `RetrieveMailboxTrackingFoldersCommand_BEGIN_{0}.mailboxid`
- `0x94206`: `RetrieveMailboxTrackingFoldersCommand_END_{0}.mailboxid`

## pseudocode

```c

```

## disassembly

```asm
0x941d0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x941d5  ldstr    aRetrievemailbo// "RetrieveMailboxTrackingFoldersCommand_B"...
0x941da  ldc.i4.1
0x941db  newarr   [mscorlib]System.Object
0x941e0  dup
0x941e1  ldc.i4.0
0x941e2  ldarg.0
0x941e3  stelem.ref
0x941e4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x941e9  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x941ee  ldarg.0
0x941ef  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::XrmExecuteInternal()
0x941f4  castclass [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RetrieveMailboxTrackingFoldersResponse
0x941f9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.MailboxTrackingFolderMappingCollection [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RetrieveMailboxTrackingFoldersResponse::get_MailboxTrackingFolderMappings()
0x941fe  stloc.0
0x941ff  leave.s  loc_94220
0x94201  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x94206  ldstr    aRetrievemailbo_0// "RetrieveMailboxTrackingFoldersCommand_E"...
0x9420b  ldc.i4.1
0x9420c  newarr   [mscorlib]System.Object
0x94211  dup
0x94212  ldc.i4.0
0x94213  ldarg.0
0x94214  stelem.ref
0x94215  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9421a  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x9421f  endfinally
0x94220  ldloc.0
0x94221  ret
```
