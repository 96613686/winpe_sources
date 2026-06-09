# Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::ProcessPackageDeploymentResult

- ea: `0x6670`
- end: `0x66d5`
- name: `Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::ProcessPackageDeploymentResult`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6260`

## callees

- `0x6670`
- `0x70f0`

## string_xrefs

- `0x6678`: `Package {0} was installed successfully on attempt {1}.`
- `0x6694`: `PackageDeployer Logs for attempt {0}: {1}`
- `0x66b1`: `Package {0} failed to install on attempt {1}.\n{2}`

## pseudocode

```c

```

## disassembly

```asm
0x6670  ldarg.0
0x6671  ldfld    bool Microsoft.Crm.Tools.Admin.PackageDeployerResult::IsSuccess
0x6676  brfalse.s loc_66B1
0x6678  ldstr    aPackage0WasIns// "Package {0} was installed successfully "...
0x667d  ldarg.2
0x667e  ldarg.3
0x667f  box      [mscorlib]System.Int32
0x6684  call     string [mscorlib]System.String::Format(string, object, object)
0x6689  ldc.i4.0
0x668a  newarr   [mscorlib]System.Object
0x668f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x6694  ldstr    aPackagedeploye_0// "PackageDeployer Logs for attempt {0}: {"...
0x6699  ldarg.3
0x669a  box      [mscorlib]System.Int32
0x669f  ldarg.1
0x66a0  call     string [mscorlib]System.String::Format(string, object, object)
0x66a5  ldc.i4.0
0x66a6  newarr   [mscorlib]System.Object
0x66ab  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x66b0  ret
0x66b1  ldstr    aPackage0Failed// "Package {0} failed to install on attemp"...
0x66b6  ldarg.2
0x66b7  ldarg.3
0x66b8  box      [mscorlib]System.Int32
0x66bd  ldarg.1
0x66be  call     string [mscorlib]System.String::Format(string, object, object, object)
0x66c3  newobj   instance void [Microsoft.Crm.PackageDeployment]Microsoft.Crm.PackageDeployment.PackageDeployerException::.ctor(string)
0x66c8  dup
0x66c9  ldarg.0
0x66ca  callvirt instance string Microsoft.Crm.Tools.Admin.PackageDeployerResult::get_Error()
0x66cf  callvirt instance void [Microsoft.Crm.PackageDeployment]Microsoft.Crm.PackageDeployment.PackageDeployerException::set_Error(string)
0x66d4  throw
```
