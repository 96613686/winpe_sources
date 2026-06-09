# Microsoft.Crm.Asynchronous.OptInFcbUpdate::DoPatchImport

- ea: `0xd580`
- end: `0xd683`
- name: `Microsoft.Crm.Asynchronous.OptInFcbUpdate::DoPatchImport`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd560`

## callees

- `0xd580`

## string_xrefs

- `0xd5a8`: `uninstall`
- `0xd5bd`: `Attempting to OptOut dbUpdates for org {0}`
- `0xd5f8`: `Applying OptOut dbUpdates for org {0} was successful`
- `0xd624`: `Attempting to apply Optin dbUpdates for org {0}`
- `0xd65f`: `Applying Optin dbUpdates for org {0} was successful`

## pseudocode

```c

```

## disassembly

```asm
0xd580  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xd585  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xd58a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_LeoServiceFeatures()
0xd58f  ldarg.0
0xd590  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xd595  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationBuildVersion()
0xd59a  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsAvailable(class [mscorlib]System.Version)
0xd59f  brtrue.s loc_D5A2
0xd5a1  ret
0xd5a2  ldarg.1
0xd5a3  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_JobParameters()
0xd5a8  ldstr    aUninstall// "uninstall"
0xd5ad  ldc.i4.5
0xd5ae  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xd5b3  brtrue.s loc_D61C
0xd5b5  ldarg.1
0xd5b6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd5bb  ldc.i4.s 0x15
0xd5bd  ldstr    aAttemptingToOp// "Attempting to OptOut dbUpdates for org "...
0xd5c2  ldc.i4.1
0xd5c3  newarr   [mscorlib]System.Object
0xd5c8  dup
0xd5c9  ldc.i4.0
0xd5ca  ldarg.0
0xd5cb  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xd5d0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xd5d5  box      [mscorlib]System.Guid
0xd5da  stelem.ref
0xd5db  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd5e0  ldarg.0
0xd5e1  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xd5e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xd5eb  call     void [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::UninstallOptIn(valuetype [mscorlib]System.Guid)
0xd5f0  ldarg.1
0xd5f1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd5f6  ldc.i4.s 0x15
0xd5f8  ldstr    aApplyingOptout// "Applying OptOut dbUpdates for org {0} w"...
0xd5fd  ldc.i4.1
0xd5fe  newarr   [mscorlib]System.Object
0xd603  dup
0xd604  ldc.i4.0
0xd605  ldarg.0
0xd606  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xd60b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xd610  box      [mscorlib]System.Guid
0xd615  stelem.ref
0xd616  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd61b  ret
0xd61c  ldarg.1
0xd61d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd622  ldc.i4.s 0x15
0xd624  ldstr    aAttemptingToAp_0// "Attempting to apply Optin dbUpdates for"...
0xd629  ldc.i4.1
0xd62a  newarr   [mscorlib]System.Object
0xd62f  dup
0xd630  ldc.i4.0
0xd631  ldarg.0
0xd632  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xd637  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xd63c  box      [mscorlib]System.Guid
0xd641  stelem.ref
0xd642  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd647  ldarg.0
0xd648  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xd64d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xd652  call     void [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::InstallOptIn(valuetype [mscorlib]System.Guid)
0xd657  ldarg.1
0xd658  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd65d  ldc.i4.s 0x15
0xd65f  ldstr    aApplyingOptinD// "Applying Optin dbUpdates for org {0} wa"...
0xd664  ldc.i4.1
0xd665  newarr   [mscorlib]System.Object
0xd66a  dup
0xd66b  ldc.i4.0
0xd66c  ldarg.0
0xd66d  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xd672  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xd677  box      [mscorlib]System.Guid
0xd67c  stelem.ref
0xd67d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd682  ret
```
