# Microsoft.Crm.Application.ProcessControl.Configuration.Services.ProcessConfigurationService::RetrieveWorkflowEntity

- ea: `0x505d0`
- end: `0x5064d`
- name: `Microsoft.Crm.Application.ProcessControl.Configuration.Services.ProcessConfigurationService::RetrieveWorkflowEntity`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x504b0`
- `0x50590`
- `0x505b0`
- `0x51220`
- `0x51300`
- `0x51330`
- `0x51380`

## string_xrefs

- `0x505d9`: `Expected ProcessConfigurationPrivilegeService to be not null.`
- `0x505ec`: `Expected CommandFactory to be not null.`
- `0x50611`: `Expected command to be not null.`

## pseudocode

```c

```

## disassembly

```asm
0x505d0  ldarg.0
0x505d1  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.Services.IProcessConfigurationPrivilegeService Microsoft.Crm.Application.ProcessControl.Configuration.Services.ProcessConfigurationService::get_ProcessConfigurationPrivilegeService()
0x505d6  ldnull
0x505d7  cgt.un
0x505d9  ldstr    aExpectedProces_6// "Expected ProcessConfigurationPrivilegeS"...
0x505de  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x505e3  ldarg.0
0x505e4  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.Commands.ICommandFactory Microsoft.Crm.Application.ProcessControl.Configuration.Services.ProcessConfigurationService::get_CommandFactory()
0x505e9  ldnull
0x505ea  cgt.un
0x505ec  ldstr    aExpectedComman// "Expected CommandFactory to be not null."
0x505f1  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x505f6  ldarg.0
0x505f7  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.Services.IProcessConfigurationPrivilegeService Microsoft.Crm.Application.ProcessControl.Configuration.Services.ProcessConfigurationService::get_ProcessConfigurationPrivilegeService()
0x505fc  callvirt instance void Microsoft.Crm.Application.ProcessControl.Configuration.Services.IProcessConfigurationPrivilegeService::AssertUserHasReadPrivilege()
0x50601  ldarg.0
0x50602  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.Commands.ICommandFactory Microsoft.Crm.Application.ProcessControl.Configuration.Services.ProcessConfigurationService::get_CommandFactory()
0x50607  ldarg.1
0x50608  callvirt instance class Microsoft.Crm.Application.ProcessControl.Configuration.Commands.IRetrieveProcessConfigurationWorkflowCommand Microsoft.Crm.Application.ProcessControl.Configuration.Commands.ICommandFactory::CreateRetrieveProcessConfigurationWorkflowCommand(valuetype [mscorlib]System.Guid processId)
0x5060d  dup
0x5060e  ldnull
0x5060f  cgt.un
0x50611  ldstr    aExpectedComman_0// "Expected command to be not null."
0x50616  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x5061b  dup
0x5061c  callvirt instance void Microsoft.Crm.Application.ProcessControl.Configuration.Commands.IRetrieveProcessConfigurationWorkflowCommand::Execute()
0x50621  callvirt instance class Microsoft.Crm.Application.ProcessControl.Configuration.Commands.IRetrieveProcessConfigurationWorkflowResponse Microsoft.Crm.Application.ProcessControl.Configuration.Commands.IRetrieveProcessConfigurationWorkflowCommand::get_Response()
0x50626  dup
0x50627  ldnull
0x50628  cgt.un
0x5062a  ldstr    aExpectedRespon// "Expected response to be not null."
0x5062f  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x50634  dup
0x50635  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Application.ProcessControl.Configuration.Commands.IRetrieveProcessConfigurationWorkflowResponse::get_WorkflowEntity()
0x5063a  ldnull
0x5063b  cgt.un
0x5063d  ldstr    aExpectedRespon_0// "Expected response.WorkflowEntity to be "...
0x50642  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x50647  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Application.ProcessControl.Configuration.Commands.IRetrieveProcessConfigurationWorkflowResponse::get_WorkflowEntity()
0x5064c  ret
```
