# Microsoft.Crm.Sandbox.HostServiceInstaller::PrepareInstallConfiguration

- ea: `0x7b0`
- end: `0x8e6`
- name: `Microsoft.Crm.Sandbox.HostServiceInstaller::PrepareInstallConfiguration`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x790`

## callees

- `0x7b0`
- `0x910`
- `0x950`
- `0x970`
- `0x990`
- `0x9b0`
- `0x9d0`
- `0x9e0`
- `0xa20`

## string_xrefs

- `0x848`: `SYSTEM\CurrentControlSet\Services\{0}`
- `0x855`: `MSCRMSandboxService`

## pseudocode

```c

```

## disassembly

```asm
0x7b0  ldarg.0
0x7b1  ldfld    class [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_processInstaller
0x7b6  ldarg.0
0x7b7  call     instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceAccount Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceAccount()
0x7bc  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller::set_Account(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceAccount)
0x7c1  ldarg.0
0x7c2  ldfld    class [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_processInstaller
0x7c7  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceAccount [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller::get_Account()
0x7cc  ldc.i4.3
0x7cd  bne.un.s loc_7F1
0x7cf  ldarg.0
0x7d0  ldfld    class [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_processInstaller
0x7d5  ldarg.0
0x7d6  call     instance string Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceAccountName()
0x7db  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller::set_Username(string)
0x7e0  ldarg.0
0x7e1  ldfld    class [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_processInstaller
0x7e6  ldarg.0
0x7e7  call     instance string Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceAccountPassword()
0x7ec  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller::set_Password(string)
0x7f1  ldarg.0
0x7f2  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_serviceInstaller
0x7f7  ldc.i4.2
0x7f8  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceInstaller::set_StartType(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceStartMode)
0x7fd  ldarg.0
0x7fe  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_serviceInstaller
0x803  ldc.i4.1
0x804  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceInstaller::set_DelayedAutoStart(bool)
0x809  ldarg.0
0x80a  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_serviceInstaller
0x80f  ldarg.0
0x810  call     instance string Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceName()
0x815  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceInstaller::set_ServiceName(string)
0x81a  ldarg.0
0x81b  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_serviceInstaller
0x820  ldarg.0
0x821  call     instance string Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceDescription()
0x826  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceInstaller::set_Description(string)
0x82b  ldarg.0
0x82c  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_serviceInstaller
0x831  ldarg.0
0x832  call     instance string Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceDisplayName()
0x837  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceInstaller::set_DisplayName(string)
0x83c  ldc.i4.0
0x83d  stloc.0
0x83e  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x843  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x848  ldstr    aSystemCurrentc// "SYSTEM\\CurrentControlSet\\Services\\{0"...
0x84d  ldc.i4.1
0x84e  newarr   [mscorlib]System.Object
0x853  dup
0x854  ldc.i4.0
0x855  ldstr    aMscrmsandboxse// "MSCRMSandboxService"
0x85a  stelem.ref
0x85b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x860  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x865  stloc.1
0x866  ldloc.1
0x867  brfalse.s loc_883
0x869  ldloc.1
0x86a  ldstr    aSinglebox// "SingleBox"
0x86f  ldc.i4.0
0x870  box      [mscorlib]System.Int32
0x875  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x87a  unbox.any [mscorlib]System.Int32
0x87f  ldc.i4.0
0x880  cgt.un
0x882  stloc.0
0x883  leave.s  loc_88F
0x885  ldloc.1
0x886  brfalse.s loc_88E
0x888  ldloc.1
0x889  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x88e  endfinally
0x88f  ldloc.0
0x890  brtrue.s loc_8AB
0x892  ldarg.0
0x893  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_serviceInstaller
0x898  ldc.i4.1
0x899  newarr   [mscorlib]System.String
0x89e  dup
0x89f  ldc.i4.0
0x8a0  ldstr    aNettcpportshar// "NetTcpPortSharing"
0x8a5  stelem.ref
0x8a6  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceInstaller::set_ServicesDependedOn(string[])
0x8ab  ldarg.0
0x8ac  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_serviceInstaller
0x8b1  ldc.i4.1
0x8b2  callvirt instance void [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller::set_RestartOnFailure(bool)
0x8b7  ldarg.0
0x8b8  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_serviceInstaller
0x8bd  ldarg.0
0x8be  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceFailureCountResetTime()
0x8c3  callvirt instance void [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller::set_FailureCountResetTime(valuetype [mscorlib]System.TimeSpan)
0x8c8  ldarg.0
0x8c9  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_serviceInstaller
0x8ce  ldarg.0
0x8cf  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceFailRestartDelay()
0x8d4  callvirt instance void [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller::set_FailRestartDelay(valuetype [mscorlib]System.TimeSpan)
0x8d9  ldarg.0
0x8da  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_serviceInstaller
0x8df  ldc.i4.1
0x8e0  callvirt instance void [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller::set_StartOnInstall(bool)
0x8e5  ret
```
