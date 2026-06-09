# Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetRestrictedAppDomain

- ea: `0x1ba20`
- end: `0x1bace`
- name: `Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetRestrictedAppDomain`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1bc90`

## callees

- `0x1ba20`

## string_xrefs

- `0x1ba52`: `PartialTrustAppDomain.Config`

## pseudocode

```c

```

## disassembly

```asm
0x1ba20  newobj   instance void [mscorlib]System.AppDomainSetup::.ctor()
0x1ba25  stloc.0
0x1ba26  ldloc.0
0x1ba27  call     string[] [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfo::GetPartialTrustAssemblyList()
0x1ba2c  callvirt instance void [mscorlib]System.AppDomainSetup::set_PartialTrustVisibleAssemblies(string[])
0x1ba31  ldloc.0
0x1ba32  call     string [Microsoft.Crm]Microsoft.Crm.Extensibility.PluginAssemblyFactory::get_AssemblyFolder()
0x1ba37  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x1ba3c  call     instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::get_Parent()
0x1ba41  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x1ba46  callvirt instance void [mscorlib]System.AppDomainSetup::set_ApplicationBase(string)
0x1ba4b  ldloc.0
0x1ba4c  ldloc.0
0x1ba4d  callvirt instance string [mscorlib]System.AppDomainSetup::get_ApplicationBase()
0x1ba52  ldstr    aPartialtrustap// "PartialTrustAppDomain.Config"
0x1ba57  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1ba5c  callvirt instance void [mscorlib]System.AppDomainSetup::set_ConfigurationFile(string)
0x1ba61  ldnull
0x1ba62  stloc.1
0x1ba63  ldarg.1
0x1ba64  ldc.i4.2
0x1ba65  bne.un.s loc_1BAA1
0x1ba67  ldc.i4.0
0x1ba68  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x1ba6d  stloc.1
0x1ba6e  ldloc.1
0x1ba6f  ldc.i4.s 0x20
0x1ba71  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.SecurityPermissionFlag)
0x1ba76  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x1ba7b  pop
0x1ba7c  ldloc.1
0x1ba7d  ldc.i4.8
0x1ba7e  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.SecurityPermissionFlag)
0x1ba83  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x1ba88  pop
0x1ba89  ldc.i4.0
0x1ba8a  newobj   instance void [mscorlib]System.Security.Permissions.FileIOPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x1ba8f  stloc.2
0x1ba90  ldloc.2
0x1ba91  ldc.i4.8
0x1ba92  callvirt instance void [mscorlib]System.Security.Permissions.FileIOPermission::set_AllLocalFiles(valuetype [mscorlib]System.Security.Permissions.FileIOPermissionAccess)
0x1ba97  ldloc.1
0x1ba98  ldloc.2
0x1ba99  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x1ba9e  pop
0x1ba9f  br.s     loc_1BAA8
0x1baa1  ldc.i4.1
0x1baa2  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x1baa7  stloc.1
0x1baa8  ldstr    aAppdomain// "AppDomain: "
0x1baad  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x1bab2  stloc.3
0x1bab3  ldloca.s 3
0x1bab5  ldstr    aB// "B"
0x1baba  call     instance string [mscorlib]System.Guid::ToString(string)
0x1babf  call     string [mscorlib]System.String::Concat(string, string)
0x1bac4  ldnull
0x1bac5  ldloc.0
0x1bac6  ldloc.1
0x1bac7  ldnull
0x1bac8  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::CreateDomain(string, class [mscorlib]System.Security.Policy.Evidence, class [mscorlib]System.AppDomainSetup, class [mscorlib]System.Security.PermissionSet, class [mscorlib]System.Security.Policy.StrongName[])
0x1bacd  ret
```
