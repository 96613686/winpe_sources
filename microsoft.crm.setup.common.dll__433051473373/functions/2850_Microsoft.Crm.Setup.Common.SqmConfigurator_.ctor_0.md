# Microsoft.Crm.Setup.Common.SqmConfigurator::.ctor_0

- ea: `0x2850`
- end: `0x294c`
- name: `Microsoft.Crm.Setup.Common.SqmConfigurator::.ctor_0`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x2830`

## callees

- `0xff0`
- `0x2850`
- `0x2990`
- `0x2a50`
- `0x2ab0`
- `0x2b30`

## string_xrefs

- `0x286e`: `{0}.ProgressMessage.Install`
- `0x28a9`: `{0}.ProgressMessage.Uninstall`

## pseudocode

```c

```

## disassembly

```asm
0x2850  ldarg.0
0x2851  ldarg.2
0x2852  call     instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::.ctor(class [mscorlib]System.Collections.IDictionary)
0x2857  ldarg.3
0x2858  ldc.i4.1
0x2859  sub
0x285a  ldc.i4.2
0x285b  ble.un.s loc_2863
0x285d  ldarg.3
0x285e  ldc.i4.4
0x285f  beq.s    loc_289E
0x2861  br.s     loc_28D7
0x2863  ldarg.0
0x2864  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer/InstallerDescription [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::get_Description()
0x2869  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x286e  ldstr    a0Progressmessa// "{0}.ProgressMessage.Install"
0x2873  ldc.i4.1
0x2874  newarr   [mscorlib]System.Object
0x2879  dup
0x287a  ldc.i4.0
0x287b  ldarg.0
0x287c  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2881  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2886  stelem.ref
0x2887  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x288c  ldc.i4.0
0x288d  newarr   [mscorlib]System.Object
0x2892  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x2897  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer/InstallerDescription::set_ProgressMessage(string)
0x289c  br.s     loc_28D7
0x289e  ldarg.0
0x289f  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer/InstallerDescription [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::get_Description()
0x28a4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x28a9  ldstr    a0Progressmessa_0// "{0}.ProgressMessage.Uninstall"
0x28ae  ldc.i4.1
0x28af  newarr   [mscorlib]System.Object
0x28b4  dup
0x28b5  ldc.i4.0
0x28b6  ldarg.0
0x28b7  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x28bc  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x28c1  stelem.ref
0x28c2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x28c7  ldc.i4.0
0x28c8  newarr   [mscorlib]System.Object
0x28cd  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x28d2  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer/InstallerDescription::set_ProgressMessage(string)
0x28d7  ldarg.1
0x28d8  newobj   instance void Microsoft.Crm.Setup.Common.CreateSqmRegistryAction::.ctor(class Microsoft.Crm.Setup.Common.SqmConfiguratorArgument argument)
0x28dd  stloc.0
0x28de  ldarg.0
0x28df  ldloc.0
0x28e0  ldc.i4.s 0x32
0x28e2  call     instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::AllocateProgress(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction, int32)
0x28e7  ldarg.0
0x28e8  call     instance class [mscorlib]System.Collections.IList [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::get_InstallActions()
0x28ed  ldloc.0
0x28ee  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x28f3  pop
0x28f4  ldarg.1
0x28f5  newobj   instance void Microsoft.Crm.Setup.Common.CreateSqmQueueLocationAction::.ctor(class Microsoft.Crm.Setup.Common.SqmConfiguratorArgument argument)
0x28fa  stloc.0
0x28fb  ldarg.0
0x28fc  ldloc.0
0x28fd  ldc.i4.s 0x32
0x28ff  call     instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::AllocateProgress(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction, int32)
0x2904  ldarg.0
0x2905  call     instance class [mscorlib]System.Collections.IList [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::get_InstallActions()
0x290a  ldloc.0
0x290b  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x2910  pop
0x2911  ldarg.1
0x2912  newobj   instance void Microsoft.Crm.Setup.Common.RemoveSqmRegistryAction::.ctor(class Microsoft.Crm.Setup.Common.SqmConfiguratorArgument argument)
0x2917  stloc.0
0x2918  ldarg.0
0x2919  ldloc.0
0x291a  ldc.i4.s 0x32
0x291c  call     instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::AllocateProgress(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction, int32)
0x2921  ldarg.0
0x2922  call     instance class [mscorlib]System.Collections.IList [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::get_UninstallActions()
0x2927  ldloc.0
0x2928  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x292d  pop
0x292e  ldarg.1
0x292f  newobj   instance void Microsoft.Crm.Setup.Common.RemoveSqmQueueLocationAction::.ctor(class Microsoft.Crm.Setup.Common.SqmConfiguratorArgument argument)
0x2934  stloc.0
0x2935  ldarg.0
0x2936  ldloc.0
0x2937  ldc.i4.s 0x32
0x2939  call     instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::AllocateProgress(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction, int32)
0x293e  ldarg.0
0x293f  call     instance class [mscorlib]System.Collections.IList [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::get_UninstallActions()
0x2944  ldloc.0
0x2945  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x294a  pop
0x294b  ret
```
