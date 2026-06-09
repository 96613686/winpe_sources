# Microsoft.Crm.Setup.Common.AsyncServiceInstaller::.ctor_0

- ea: `0x830`
- end: `0x883`
- name: `Microsoft.Crm.Setup.Common.AsyncServiceInstaller::.ctor_0`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x810`

## callees

- `0x830`
- `0x890`
- `0x8b0`
- `0x8d0`
- `0x8f0`
- `0x920`

## pseudocode

```c

```

## disassembly

```asm
0x830  ldarg.0
0x831  ldarg.2
0x832  call     instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::.ctor(class [mscorlib]System.Collections.IDictionary)
0x837  ldarg.0
0x838  ldarg.3
0x839  stfld    valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType Microsoft.Crm.Setup.Common.AsyncServiceInstaller::_installTypeOverride
0x83e  ldarg.0
0x83f  ldarg.1
0x840  call     instance void Microsoft.Crm.Setup.Common.AsyncServiceInstaller::set_AsyncServiceInstance(string value)
0x845  ldarg.0
0x846  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::get_Operation()
0x84b  stloc.0
0x84c  ldloc.0
0x84d  ldc.i4.1
0x84e  sub
0x84f  switch   loc_866, loc_86E, loc_876, loc_87C
0x864  br.s     loc_87C
0x866  ldarg.0
0x867  call     instance void Microsoft.Crm.Setup.Common.AsyncServiceInstaller::InitializeInstall()
0x86c  br.s     loc_87C
0x86e  ldarg.0
0x86f  call     instance void Microsoft.Crm.Setup.Common.AsyncServiceInstaller::InitializeUpgrade()
0x874  br.s     loc_87C
0x876  ldarg.0
0x877  call     instance void Microsoft.Crm.Setup.Common.AsyncServiceInstaller::InitializeRepair()
0x87c  ldarg.0
0x87d  call     instance void Microsoft.Crm.Setup.Common.AsyncServiceInstaller::InitializeUninstall()
0x882  ret
```
