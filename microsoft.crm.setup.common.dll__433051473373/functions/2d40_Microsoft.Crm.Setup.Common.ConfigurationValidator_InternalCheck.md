# Microsoft.Crm.Setup.Common.ConfigurationValidator::InternalCheck

- ea: `0x2d40`
- end: `0x2d99`
- name: `Microsoft.Crm.Setup.Common.ConfigurationValidator::InternalCheck`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xff0`
- `0x2d40`

## string_xrefs

- `0x2d70`: `InstallInfo.ConfigFile`
- `0x2d7c`: `Error.ConfigFileNotSpecified`

## pseudocode

```c

```

## disassembly

```asm
0x2d40  ldarg.1
0x2d41  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x2d46  stloc.0
0x2d47  ldloc.0
0x2d48  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.UIMode [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_UIMode()
0x2d4d  brfalse.s loc_2D92
0x2d4f  ldloc.0
0x2d50  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_InstallType()
0x2d55  ldc.i4.4
0x2d56  beq.s    loc_2D92
0x2d58  ldloc.0
0x2d59  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_InstallType()
0x2d5e  ldc.i4.2
0x2d5f  beq.s    loc_2D92
0x2d61  ldloc.0
0x2d62  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_InstallType()
0x2d67  ldc.i4.3
0x2d68  beq.s    loc_2D92
0x2d6a  ldloc.0
0x2d6b  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x2d70  ldstr    aInstallinfoCon// "InstallInfo.ConfigFile"
0x2d75  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x2d7a  brtrue.s loc_2D92
0x2d7c  ldstr    aErrorConfigfil// "Error.ConfigFileNotSpecified"
0x2d81  ldc.i4.0
0x2d82  newarr   [mscorlib]System.Object
0x2d87  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x2d8c  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupException::.ctor(string)
0x2d91  throw
0x2d92  ldc.i4.0
0x2d93  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0x2d98  ret
```
