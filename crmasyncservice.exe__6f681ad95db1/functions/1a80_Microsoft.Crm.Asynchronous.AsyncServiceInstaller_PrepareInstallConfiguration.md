# Microsoft.Crm.Asynchronous.AsyncServiceInstaller::PrepareInstallConfiguration

- ea: `0x1a80`
- end: `0x1b8d`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceInstaller::PrepareInstallConfiguration`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1a40`

## callees

- `0x1880`
- `0x1a80`
- `0x1c20`
- `0x1c60`
- `0x1c80`
- `0x1ca0`
- `0x1cc0`
- `0x1ce0`
- `0x1d20`
- `0x1d80`
- `0x1de0`

## pseudocode

```c

```

## disassembly

```asm
0x1a80  ldarg.0
0x1a81  ldfld    class [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller Microsoft.Crm.Asynchronous.AsyncServiceInstaller::_processInstaller
0x1a86  ldarg.0
0x1a87  call     instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceAccount Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceAccount()
0x1a8c  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller::set_Account(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceAccount)
0x1a91  ldarg.0
0x1a92  ldfld    class [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller Microsoft.Crm.Asynchronous.AsyncServiceInstaller::_processInstaller
0x1a97  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceAccount [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller::get_Account()
0x1a9c  ldc.i4.3
0x1a9d  bne.un.s loc_1AC1
0x1a9f  ldarg.0
0x1aa0  ldfld    class [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller Microsoft.Crm.Asynchronous.AsyncServiceInstaller::_processInstaller
0x1aa5  ldarg.0
0x1aa6  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceAccountName()
0x1aab  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller::set_Username(string)
0x1ab0  ldarg.0
0x1ab1  ldfld    class [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller Microsoft.Crm.Asynchronous.AsyncServiceInstaller::_processInstaller
0x1ab6  ldarg.0
0x1ab7  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceAccountPassword()
0x1abc  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller::set_Password(string)
0x1ac1  ldarg.0
0x1ac2  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Asynchronous.AsyncServiceInstaller::_serviceInstaller
0x1ac7  ldc.i4.2
0x1ac8  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceInstaller::set_StartType(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceStartMode)
0x1acd  ldarg.0
0x1ace  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Asynchronous.AsyncServiceInstaller::_serviceInstaller
0x1ad3  ldarg.0
0x1ad4  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceName()
0x1ad9  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceInstaller::set_ServiceName(string)
0x1ade  ldarg.0
0x1adf  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Asynchronous.AsyncServiceInstaller::_serviceInstaller
0x1ae4  ldarg.0
0x1ae5  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceDescription()
0x1aea  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceInstaller::set_Description(string)
0x1aef  ldarg.0
0x1af0  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Asynchronous.AsyncServiceInstaller::_serviceInstaller
0x1af5  ldarg.0
0x1af6  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceDisplayName()
0x1afb  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceInstaller::set_DisplayName(string)
0x1b00  ldarg.0
0x1b01  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Asynchronous.AsyncServiceInstaller::_serviceInstaller
0x1b06  ldc.i4.1
0x1b07  callvirt instance void [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller::set_RestartOnFailure(bool)
0x1b0c  ldarg.0
0x1b0d  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceName()
0x1b12  call     valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::DetermineContext(string serviceName)
0x1b17  brtrue.s loc_1B25
0x1b19  ldarg.0
0x1b1a  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Asynchronous.AsyncServiceInstaller::_serviceInstaller
0x1b1f  ldc.i4.1
0x1b20  callvirt instance void [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller::set_InfiniteRetries(bool)
0x1b25  ldarg.0
0x1b26  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Asynchronous.AsyncServiceInstaller::_serviceInstaller
0x1b2b  ldarg.0
0x1b2c  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceFailureCountResetTime()
0x1b31  callvirt instance void [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller::set_FailureCountResetTime(valuetype [mscorlib]System.TimeSpan)
0x1b36  ldarg.0
0x1b37  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Asynchronous.AsyncServiceInstaller::_serviceInstaller
0x1b3c  ldarg.0
0x1b3d  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceFailRestartDelay()
0x1b42  callvirt instance void [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller::set_FailRestartDelay(valuetype [mscorlib]System.TimeSpan)
0x1b47  ldarg.0
0x1b48  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Asynchronous.AsyncServiceInstaller::_serviceInstaller
0x1b4d  ldc.i4.1
0x1b4e  callvirt instance void [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller::set_StartOnInstall(bool)
0x1b53  ldarg.0
0x1b54  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_SqlServerName()
0x1b59  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b5e  brtrue.s loc_1B8C
0x1b60  ldarg.0
0x1b61  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_SqlServerName()
0x1b66  call     string [mscorlib]System.Environment::get_MachineName()
0x1b6b  ldc.i4.5
0x1b6c  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x1b71  brfalse.s loc_1B8C
0x1b73  ldarg.0
0x1b74  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Asynchronous.AsyncServiceInstaller::_serviceInstaller
0x1b79  ldc.i4.1
0x1b7a  newarr   [mscorlib]System.String
0x1b7f  dup
0x1b80  ldc.i4.0
0x1b81  ldstr    aMssqlserver// "MSSQLSERVER"
0x1b86  stelem.ref
0x1b87  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceInstaller::set_ServicesDependedOn(string[])
0x1b8c  ret
```
