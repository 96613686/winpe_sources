# Microsoft.Crm.CrmLive.Provisioning.MtpOrganizationProvisioner::GetTemplatePath

- ea: `0x8fc0`
- end: `0x8ffe`
- name: `Microsoft.Crm.CrmLive.Provisioning.MtpOrganizationProvisioner::GetTemplatePath`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x8a80`
- `0x8c60`

## callees

- `0x8fc0`

## string_xrefs

- `0x8fe6`: `No template path\share found for this scalegroup`
- `0x8ff2`: `organizationtemplate`

## pseudocode

```c

```

## disassembly

```asm
0x8fc0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x8fc5  ldstr    aDatabasebackup// "DatabaseBackupShareLocation"
0x8fca  callvirt T0x2B000018
0x8fcf  stloc.0
0x8fd0  ldloc.0
0x8fd1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8fd6  brtrue.s loc_8FE6
0x8fd8  ldloc.0
0x8fd9  ldstr    aNone// "none"
0x8fde  ldc.i4.5
0x8fdf  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x8fe4  brfalse.s loc_8FF1
0x8fe6  ldstr    aNoTemplatePath// "No template path\\share found for this "...
0x8feb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x8ff0  throw
0x8ff1  ldloc.0
0x8ff2  ldstr    aOrganizationte// "organizationtemplate"
0x8ff7  ldarg.0
0x8ff8  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x8ffd  ret
```
