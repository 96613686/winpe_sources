# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::.cctor

- ea: `0x320`
- end: `0x32b`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::.cctor`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x320`: `Specify all of the following arguments in this format:\nPackageDeploymentExecutor.exe organizationid="<GUID: organizationId>" userid="<GUID: userId>" packagelocation="<string: package location filepath>" packagename="<string: package name>" allowpackagecodeexecution="<bool: allow package code execution>" islive="<bool: is Live deployment>" issystemconvertedsolutionupgrade="<bool: is system converted solution upgrade>" usessl="<bool: use SSL>" isinternalcrmappsinstall="<bool: is internal crm apps`

## pseudocode

```c

```

## disassembly

```asm
0x320  ldstr    aSpecifyAllOfTh// "Specify all of the following arguments "...
0x325  stsfld   string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeploymentExecutorArgs::ArgumentsHelpMessage
0x32a  ret
```
