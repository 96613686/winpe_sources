# Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::.ctor_0

- ea: `0xfee0`
- end: `0x10013`
- name: `Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::.ctor_0`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x117b0`

## callees

- `0xfee0`
- `0x10030`
- `0x10050`
- `0x10070`
- `0x10090`
- `0x100b0`
- `0x100d0`
- `0x100f0`
- `0x10110`
- `0x10130`
- `0x10150`
- `0x10170`
- `0x10190`

## string_xrefs

- `0xffe8`: `CreatedOn`
- `0xffad`: `ConfigurationStatusCode`

## pseudocode

```c

```

## disassembly

```asm
0xfee0  ldarg.0
0xfee1  call     instance void [mscorlib]System.Object::.ctor()
0xfee6  ldarg.0
0xfee7  ldarg.1
0xfee8  ldstr    aCrmorganizatio// "CrmOrganizationId"
0xfeed  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xfef2  unbox.any [mscorlib]System.Guid
0xfef7  call     instance void Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::set_CrmOrganizationId(valuetype [mscorlib]System.Guid value)
0xfefc  ldarg.0
0xfefd  ldarg.1
0xfefe  ldstr    aOrganizationun// "OrganizationUniqueName"
0xff03  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xff08  castclass [mscorlib]System.String
0xff0d  call     instance void Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::set_OrganizationUniqueName(string value)
0xff12  ldarg.0
0xff13  ldarg.1
0xff14  ldstr    aOrganizationfr// "OrganizationFriendlyName"
0xff19  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xff1e  castclass [mscorlib]System.String
0xff23  call     instance void Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::set_OrganizationFriendlyName(string value)
0xff28  ldarg.0
0xff29  ldarg.1
0xff2a  ldstr    aStatuscode// "StatusCode"
0xff2f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xff34  unbox.any [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus
0xff39  call     instance void Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::set_OrganizationLifecycleState(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus value)
0xff3e  ldarg.0
0xff3f  ldarg.1
0xff40  ldstr    aInitialuserema// "InitialUserEmail"
0xff45  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xff4a  castclass [mscorlib]System.String
0xff4f  call     instance void Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::set_InitialUserEmail(string value)
0xff54  ldarg.0
0xff55  ldarg.1
0xff56  ldstr    aInitialuserfir// "InitialUserFirstName"
0xff5b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xff60  castclass [mscorlib]System.String
0xff65  call     instance void Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::set_InitialUserFirstName(string value)
0xff6a  ldarg.0
0xff6b  ldarg.1
0xff6c  ldstr    aInitialuserlas// "InitialUserLastName"
0xff71  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xff76  castclass [mscorlib]System.String
0xff7b  call     instance void Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::set_InitialUserLastName(string value)
0xff80  ldarg.0
0xff81  ldarg.1
0xff82  ldstr    aInitialuserliv// "InitialUserLiveId"
0xff87  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xff8c  castclass [mscorlib]System.String
0xff91  call     instance void Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::set_InitialUserLiveId(string value)
0xff96  ldarg.0
0xff97  ldarg.1
0xff98  ldstr    aInitialuserpui// "InitialUserPuid"
0xff9d  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xffa2  castclass [mscorlib]System.String
0xffa7  call     instance void Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::set_InitialUserPuid(string value)
0xffac  ldarg.1
0xffad  ldstr    aConfigurations// "ConfigurationStatusCode"
0xffb2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xffb7  stloc.0
0xffb8  ldloc.0
0xffb9  brfalse.s loc_FFC3
0xffbb  ldloc.0
0xffbc  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xffc1  bne.un.s loc_FFCA
0xffc3  ldc.i4.0
0xffc4  box      [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleConfigurationStatus
0xffc9  stloc.0
0xffca  ldarg.0
0xffcb  ldloc.0
0xffcc  unbox.any [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleConfigurationStatus
0xffd1  call     instance void Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::set_ConfigurationState(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleConfigurationStatus value)
0xffd6  ldarg.1
0xffd7  ldstr    aModifiedon// "ModifiedOn"
0xffdc  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xffe1  unbox.any [mscorlib]System.DateTime
0xffe6  stloc.1
0xffe7  ldarg.1
0xffe8  ldstr    aCreatedon// "CreatedOn"
0xffed  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xfff2  unbox.any [mscorlib]System.DateTime
0xfff7  stloc.2
0xfff8  ldarg.0
0xfff9  ldloc.1
0xfffa  ldc.i4.1
0xfffb  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x10000  call     instance void Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::set_ModifiedOn(valuetype [mscorlib]System.DateTime value)
0x10005  ldarg.0
0x10006  ldloc.2
0x10007  ldc.i4.1
0x10008  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x1000d  call     instance void Microsoft.Crm.CrmLive.Services.OrganizationLifecycleData::set_CreatedOn(valuetype [mscorlib]System.DateTime value)
0x10012  ret
```
