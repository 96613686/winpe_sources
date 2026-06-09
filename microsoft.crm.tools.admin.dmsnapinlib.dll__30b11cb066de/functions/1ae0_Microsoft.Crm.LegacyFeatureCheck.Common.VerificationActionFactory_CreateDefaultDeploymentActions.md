# Microsoft.Crm.LegacyFeatureCheck.Common.VerificationActionFactory::CreateDefaultDeploymentActions

- ea: `0x1ae0`
- end: `0x1b27`
- name: `Microsoft.Crm.LegacyFeatureCheck.Common.VerificationActionFactory::CreateDefaultDeploymentActions`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x590`

## callees

- `0x1ae0`
- `0x1c80`
- `0x1f50`
- `0x2050`

## string_xrefs

- `0x1b16`: `Checking for the 2007 web service calls in the IIS logs`

## pseudocode

```c

```

## disassembly

```asm
0x1ae0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationAction>::.ctor()
0x1ae5  stloc.0
0x1ae6  ldloc.0
0x1ae7  newobj   instance void Microsoft.Crm.LegacyFeatureCheck.Actions.VerifyISVFolderAction::.ctor()
0x1aec  dup
0x1aed  ldstr    aCheckingForThe// "Checking for the ISV folder when runnin"...
0x1af2  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationAction::set_Name(string value)
0x1af7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationAction>::Add(var<u1>)
0x1afc  ldarg.0
0x1afd  ldfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::IISLogsPath
0x1b02  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1b07  brtrue.s loc_1B25
0x1b09  ldloc.0
0x1b0a  ldarg.0
0x1b0b  ldfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::IISLogsPath
0x1b10  newobj   instance void Microsoft.Crm.LegacyFeatureCheck.Actions.VerifyIISLogsAction::.ctor(string logPath)
0x1b15  dup
0x1b16  ldstr    aCheckingForThe_0// "Checking for the 2007 web service calls"...
0x1b1b  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationAction::set_Name(string value)
0x1b20  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationAction>::Add(var<u1>)
0x1b25  ldloc.0
0x1b26  ret
```
