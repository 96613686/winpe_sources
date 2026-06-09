# Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::CreateInstallParameters

- ea: `0xb70`
- end: `0xdb4`
- name: `Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::CreateInstallParameters`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xa40`

## callees

- `0x930`
- `0x950`
- `0x990`
- `0xb70`
- `0x1000`

## string_xrefs

- `0xbc3`: `AsyncServiceDisplayName`
- `0xbf6`: `AsyncServiceDescription`
- `0xcca`: `CrmAsyncService.log`
- `0xd74`: `CrmAsyncService.log`

## pseudocode

```c

```

## disassembly

```asm
0xb70  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xb75  stloc.0
0xb76  ldsfld   string [mscorlib]System.String::Empty
0xb7b  stloc.1
0xb7c  ldarg.0
0xb7d  ldfld    class Microsoft.Crm.Setup.Common.AsyncServiceInstaller Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::_asyncInstaller
0xb82  callvirt instance class [mscorlib]System.Security.SecureString Microsoft.Crm.Setup.Common.AsyncServiceInstaller::get_CrmServiceAccountName()
0xb87  callvirt instance int32 [mscorlib]System.Security.SecureString::get_Length()
0xb8c  ldc.i4.0
0xb8d  ble.s    loc_BAB
0xb8f  ldarg.0
0xb90  ldfld    class Microsoft.Crm.Setup.Common.AsyncServiceInstaller Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::_asyncInstaller
0xb95  callvirt instance class [mscorlib]System.Security.SecureString Microsoft.Crm.Setup.Common.AsyncServiceInstaller::get_CrmServiceAccountName()
0xb9a  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::SecureStringToBSTR(class [mscorlib]System.Security.SecureString)
0xb9f  dup
0xba0  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringBSTR(native int)
0xba5  stloc.1
0xba6  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ZeroFreeBSTR(native int)
0xbab  ldloc.0
0xbac  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xbb1  ldstr    aDisplayname0// "/displayname={0}"
0xbb6  ldc.i4.1
0xbb7  newarr   [mscorlib]System.Object
0xbbc  dup
0xbbd  ldc.i4.0
0xbbe  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Setup.Common.CommonResource::get_ResourceManager()
0xbc3  ldstr    aAsyncservicedi// "AsyncServiceDisplayName"
0xbc8  ldc.i4.0
0xbc9  newarr   [mscorlib]System.Object
0xbce  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupBase::GetResourceString(class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager, string, object[])
0xbd3  stelem.ref
0xbd4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbd9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbde  ldloc.0
0xbdf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xbe4  ldstr    aDescription0// "/description={0}"
0xbe9  ldc.i4.1
0xbea  newarr   [mscorlib]System.Object
0xbef  dup
0xbf0  ldc.i4.0
0xbf1  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Setup.Common.CommonResource::get_ResourceManager()
0xbf6  ldstr    aAsyncservicede// "AsyncServiceDescription"
0xbfb  ldc.i4.0
0xbfc  newarr   [mscorlib]System.Object
0xc01  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupBase::GetResourceString(class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager, string, object[])
0xc06  stelem.ref
0xc07  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc0c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc11  ldloc.0
0xc12  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc17  ldstr    aSqlserver0// "/sqlserver={0}"
0xc1c  ldc.i4.1
0xc1d  newarr   [mscorlib]System.Object
0xc22  dup
0xc23  ldc.i4.0
0xc24  ldarg.0
0xc25  ldfld    class Microsoft.Crm.Setup.Common.AsyncServiceInstaller Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::_asyncInstaller
0xc2a  callvirt instance string Microsoft.Crm.Setup.Common.AsyncServiceInstaller::get_SqlServerName()
0xc2f  stelem.ref
0xc30  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc35  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc3a  ldarg.0
0xc3b  ldfld    string Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::_instance
0xc40  ldarg.0
0xc41  ldfld    string Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::_serverInstance
0xc46  ldc.i4.5
0xc47  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xc4c  brfalse  loc_CE4
0xc51  ldloc.0
0xc52  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc57  ldstr    aAccount0// "/account={0}"
0xc5c  ldc.i4.1
0xc5d  newarr   [mscorlib]System.Object
0xc62  dup
0xc63  ldc.i4.0
0xc64  ldarg.0
0xc65  ldfld    class Microsoft.Crm.Setup.Common.AsyncServiceInstaller Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::_asyncInstaller
0xc6a  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceAccount Microsoft.Crm.Setup.Common.AsyncServiceInstaller::get_CrmServiceAccount()
0xc6f  box      [System.ServiceProcess]System.ServiceProcess.ServiceAccount
0xc74  stelem.ref
0xc75  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc7a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc7f  ldarg.0
0xc80  ldfld    class Microsoft.Crm.Setup.Common.AsyncServiceInstaller Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::_asyncInstaller
0xc85  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceAccount Microsoft.Crm.Setup.Common.AsyncServiceInstaller::get_CrmServiceAccount()
0xc8a  ldc.i4.3
0xc8b  bne.un.s loc_CAC
0xc8d  ldloc.0
0xc8e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc93  ldstr    aUser0// "/user={0}"
0xc98  ldc.i4.1
0xc99  newarr   [mscorlib]System.Object
0xc9e  dup
0xc9f  ldc.i4.0
0xca0  ldloc.1
0xca1  stelem.ref
0xca2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xca7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcac  ldloc.0
0xcad  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcb2  ldstr    aLogfile0// "/logfile={0}"
0xcb7  ldc.i4.1
0xcb8  newarr   [mscorlib]System.Object
0xcbd  dup
0xcbe  ldc.i4.0
0xcbf  ldarg.1
0xcc0  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_LogFile()
0xcc5  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0xcca  ldstr    aCrmasyncservic_0// "CrmAsyncService.log"
0xccf  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xcd4  stelem.ref
0xcd5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xcda  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcdf  br       loc_DAD
0xce4  ldarg.0
0xce5  ldfld    string Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::_instance
0xcea  ldarg.0
0xceb  ldfld    string Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::_maintenanceInstance
0xcf0  ldc.i4.5
0xcf1  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xcf6  brfalse  loc_DAD
0xcfb  ldloc.0
0xcfc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd01  ldstr    aAccount0// "/account={0}"
0xd06  ldc.i4.1
0xd07  newarr   [mscorlib]System.Object
0xd0c  dup
0xd0d  ldc.i4.0
0xd0e  ldarg.0
0xd0f  ldfld    class Microsoft.Crm.Setup.Common.AsyncServiceInstaller Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::_asyncInstaller
0xd14  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceAccount Microsoft.Crm.Setup.Common.AsyncServiceInstaller::get_CrmServiceAccount()
0xd19  box      [System.ServiceProcess]System.ServiceProcess.ServiceAccount
0xd1e  stelem.ref
0xd1f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd24  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xd29  ldarg.0
0xd2a  ldfld    class Microsoft.Crm.Setup.Common.AsyncServiceInstaller Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::_asyncInstaller
0xd2f  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceAccount Microsoft.Crm.Setup.Common.AsyncServiceInstaller::get_CrmServiceAccount()
0xd34  ldc.i4.3
0xd35  bne.un.s loc_D56
0xd37  ldloc.0
0xd38  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd3d  ldstr    aUser0// "/user={0}"
0xd42  ldc.i4.1
0xd43  newarr   [mscorlib]System.Object
0xd48  dup
0xd49  ldc.i4.0
0xd4a  ldloc.1
0xd4b  stelem.ref
0xd4c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd51  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xd56  ldloc.0
0xd57  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd5c  ldstr    aLogfile0// "/logfile={0}"
0xd61  ldc.i4.1
0xd62  newarr   [mscorlib]System.Object
0xd67  dup
0xd68  ldc.i4.0
0xd69  ldarg.1
0xd6a  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_LogFile()
0xd6f  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0xd74  ldstr    aCrmasyncservic_0// "CrmAsyncService.log"
0xd79  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xd7e  stelem.ref
0xd7f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd84  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xd89  ldloc.0
0xd8a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd8f  ldstr    aInstance0// "/instance={0}"
0xd94  ldc.i4.1
0xd95  newarr   [mscorlib]System.Object
0xd9a  dup
0xd9b  ldc.i4.0
0xd9c  ldarg.0
0xd9d  ldfld    string Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::_instance
0xda2  stelem.ref
0xda3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xda8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xdad  ldloc.0
0xdae  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0xdb3  ret
```
