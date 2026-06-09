# Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::ConfigureSelectedGroup

- ea: `0x7950`
- end: `0x79ec`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::ConfigureSelectedGroup`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7890`

## callees

- `0x76c0`
- `0x76f0`
- `0x7710`
- `0x7750`
- `0x7950`

## pseudocode

```c

```

## disassembly

```asm
0x7950  ldarg.0
0x7951  ldarg.0
0x7952  call     instance string Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::get_AllCompany()
0x7957  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::set_SelectedGroup(string value)
0x795c  ldarg.1
0x795d  brfalse  loc_79EB
0x7962  ldarg.0
0x7963  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::get_Config()
0x7968  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_YammerGroupId()
0x796d  brfalse.s loc_79EB
0x796f  ldarg.1
0x7970  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmKeyService::GetStringFromSecureString(class [mscorlib]System.Security.SecureString)
0x7975  stloc.0
0x7976  ldloc.0
0x7977  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x797c  brtrue.s loc_79EB
0x797e  ldarg.0
0x797f  ldloc.0
0x7980  call     valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Common.Application.WebServices]Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::get_YammerConnectionTimeout()
0x7985  newobj   instance void [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerProxy::.ctor(string, valuetype [mscorlib]System.TimeSpan)
0x798a  ldarg.0
0x798b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::get_Config()
0x7990  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_YammerGroupId()
0x7995  call     instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.Group [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerProxy::GetGroup(int32)
0x799a  callvirt instance string [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.Group::get_FullName()
0x799f  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::set_SelectedGroup(string value)
0x79a4  leave.s  loc_79EB
0x79a6  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x79ab  stloc.1
0x79ac  ldloc.1
0x79ad  ldc.i4   0x8005F101
0x79b2  beq.s    loc_79BE
0x79b4  ldloc.1
0x79b5  ldc.i4   0x8005F104
0x79ba  beq.s    loc_79C7
0x79bc  br.s     loc_79E7
0x79be  ldarg.0
0x79bf  ldc.i4.0
0x79c0  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::set_HasValidConfig(bool value)
0x79c5  br.s     loc_79E9
0x79c7  ldarg.0
0x79c8  ldarg.0
0x79c9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::get_Config()
0x79ce  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_YammerGroupId()
0x79d3  stloc.1
0x79d4  ldloca.s 1
0x79d6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x79db  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x79e0  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::set_SelectedGroup(string value)
0x79e5  br.s     loc_79E9
0x79e7  rethrow
0x79e9  leave.s  loc_79EB
0x79eb  ret
```
