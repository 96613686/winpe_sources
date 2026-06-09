# Microsoft.Crm.Sandbox.HostServiceInstaller::.ctor

- ea: `0x730`
- end: `0x78a`
- name: `Microsoft.Crm.Sandbox.HostServiceInstaller::.ctor`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x730  ldarg.0
0x731  call     instance void [System.Configuration.Install]System.Configuration.Install.Installer::.ctor()
0x736  ldarg.0
0x737  newobj   instance void [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller::.ctor()
0x73c  stfld    class [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_processInstaller
0x741  ldarg.0
0x742  newobj   instance void [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller::.ctor()
0x747  stfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_serviceInstaller
0x74c  ldarg.0
0x74d  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_serviceInstaller
0x752  ldc.r8   20.0
0x75b  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x760  callvirt instance void [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller::set_StartTimeout(valuetype [mscorlib]System.TimeSpan)
0x765  ldarg.0
0x766  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallerCollection [System.Configuration.Install]System.Configuration.Install.Installer::get_Installers()
0x76b  ldarg.0
0x76c  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_serviceInstaller
0x771  callvirt instance int32 [System.Configuration.Install]System.Configuration.Install.InstallerCollection::Add(class [System.Configuration.Install]System.Configuration.Install.Installer)
0x776  pop
0x777  ldarg.0
0x778  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallerCollection [System.Configuration.Install]System.Configuration.Install.Installer::get_Installers()
0x77d  ldarg.0
0x77e  ldfld    class [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_processInstaller
0x783  callvirt instance int32 [System.Configuration.Install]System.Configuration.Install.InstallerCollection::Add(class [System.Configuration.Install]System.Configuration.Install.Installer)
0x788  pop
0x789  ret
```
