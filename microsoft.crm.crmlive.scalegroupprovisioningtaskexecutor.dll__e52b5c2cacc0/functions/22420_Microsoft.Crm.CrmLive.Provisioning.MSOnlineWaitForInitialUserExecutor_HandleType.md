# Microsoft.Crm.CrmLive.Provisioning.MSOnlineWaitForInitialUserExecutor::HandleType

- ea: `0x22420`
- end: `0x224b3`
- name: `Microsoft.Crm.CrmLive.Provisioning.MSOnlineWaitForInitialUserExecutor::HandleType`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x223a0`

## callees

- `0x22420`
- `0x224c0`
- `0x224d0`

## string_xrefs

- `0x2242d`: `Type not specified in DirectoryObjectState for objectId='{0}'`
- `0x22490`: `Type '{0}' is not valid for WaitForInitialUser. Only Company and User types are supported.  ObjectId='{1}'`

## pseudocode

```c

```

## disassembly

```asm
0x22420  ldarg.2
0x22421  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x22426  brfalse.s loc_2244C
0x22428  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2242d  ldstr    aTypeNotSpecifi// "Type not specified in DirectoryObjectSt"...
0x22432  ldc.i4.1
0x22433  newarr   [mscorlib]System.Object
0x22438  dup
0x22439  ldc.i4.0
0x2243a  ldarg.1
0x2243b  box      [mscorlib]System.Guid
0x22440  stelem.ref
0x22441  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22446  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2244b  throw
0x2244c  ldarg.2
0x2244d  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User
0x22452  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22457  call     string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObjectSerializer::GetStringFromType(class [mscorlib]System.Type)
0x2245c  ldc.i4.5
0x2245d  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x22462  brfalse.s loc_2246A
0x22464  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.CrmLive.Provisioning.MSOnlineWaitForInitialUserExecutor::HandleUser()
0x22469  ret
0x2246a  ldarg.2
0x2246b  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company
0x22470  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22475  call     string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObjectSerializer::GetStringFromType(class [mscorlib]System.Type)
0x2247a  ldc.i4.5
0x2247b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x22480  brfalse.s loc_2248B
0x22482  ldarg.0
0x22483  ldarg.1
0x22484  ldarg.3
0x22485  call     instance class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.CrmLive.Provisioning.MSOnlineWaitForInitialUserExecutor::HandleCompany(valuetype [mscorlib]System.Guid objectId, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider directoryProvider)
0x2248a  ret
0x2248b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22490  ldstr    aType0IsNotVali// "Type '{0}' is not valid for WaitForInit"...
0x22495  ldc.i4.2
0x22496  newarr   [mscorlib]System.Object
0x2249b  dup
0x2249c  ldc.i4.0
0x2249d  ldarg.2
0x2249e  stelem.ref
0x2249f  dup
0x224a0  ldc.i4.1
0x224a1  ldarg.1
0x224a2  box      [mscorlib]System.Guid
0x224a7  stelem.ref
0x224a8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x224ad  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x224b2  throw
```
