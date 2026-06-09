# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::InitializeForInstallation

- ea: `0x15250`
- end: `0x15336`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::InitializeForInstallation`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x150b0`

## callees

- `0x14790`
- `0x14f20`
- `0x14f30`
- `0x14f40`
- `0x14f50`
- `0x14f70`
- `0x14f90`
- `0x14fb0`
- `0x15020`
- `0x15030`
- `0x15050`
- `0x15080`
- `0x15090`
- `0x16420`
- `0x16c70`

## string_xrefs

- `0x15269`: `InstallationPathRoot`
- `0x1527e`: `InstallationPathRoot token must be provided`

## pseudocode

```c

```

## disassembly

```asm
0x15250  ldarg.1
0x15251  ldstr    aPackinglist// "packingList"
0x15256  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1525b  ldarg.0
0x1525c  ldarg.1
0x1525d  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_PackingList(class Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList value)
0x15262  ldarg.0
0x15263  ldarg.1
0x15264  callvirt instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.TokenValueMap Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList::get_PrimaryTokenMap()
0x15269  ldstr    aInstallationpa// "InstallationPathRoot"
0x1526e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x15273  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_InstallationPathRoot(string value)
0x15278  ldarg.0
0x15279  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_InstallationPathRoot()
0x1527e  ldstr    aInstallationpa_0// "InstallationPathRoot token must be prov"...
0x15283  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x15288  ldarg.0
0x15289  ldarg.0
0x1528a  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_InstallationPathRoot()
0x1528f  ldstr    aDeployment// "Deployment"
0x15294  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x15299  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_DeploymentSupportDirectoryPath(string value)
0x1529e  ldarg.0
0x1529f  ldarg.0
0x152a0  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_PrimaryPackageDescriptor()
0x152a5  callvirt instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor::get_PackageName()
0x152aa  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_PackageName(string value)
0x152af  ldstr    aPackageName0// "Package name: {0}"
0x152b4  ldc.i4.1
0x152b5  newarr   [mscorlib]System.Object
0x152ba  dup
0x152bb  ldc.i4.0
0x152bc  ldarg.0
0x152bd  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_PackageName()
0x152c2  stelem.ref
0x152c3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x152c8  ldarg.0
0x152c9  ldarg.0
0x152ca  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_DeploymentSupportDirectoryPath()
0x152cf  ldstr    a0Staging// "{0}_Staging"
0x152d4  ldc.i4.1
0x152d5  newarr   [mscorlib]System.Object
0x152da  dup
0x152db  ldc.i4.0
0x152dc  ldarg.0
0x152dd  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_PackageName()
0x152e2  stelem.ref
0x152e3  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x152e8  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x152ed  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_StagingDirectoryPath(string value)
0x152f2  ldarg.0
0x152f3  ldarg.0
0x152f4  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_DeploymentSupportDirectoryPath()
0x152f9  ldstr    a0Backup// "{0}_Backup"
0x152fe  ldc.i4.1
0x152ff  newarr   [mscorlib]System.Object
0x15304  dup
0x15305  ldc.i4.0
0x15306  ldarg.0
0x15307  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_PackageName()
0x1530c  stelem.ref
0x1530d  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x15312  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x15317  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_BackupDirectoryPath(string value)
0x1531c  ldarg.1
0x1531d  callvirt instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.TokenValueMap Microsoft.Crm.Setup.Common.OnlinePackageSupport.PackingList::get_PrimaryTokenMap()
0x15322  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.TokenValueMap::LogContents()
0x15327  ldarg.0
0x15328  ldc.i4.0
0x15329  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_RebootRequired(bool value)
0x1532e  ldarg.0
0x1532f  ldc.i4.m1
0x15330  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::set_ResultCode(valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageResult value)
0x15335  ret
```
