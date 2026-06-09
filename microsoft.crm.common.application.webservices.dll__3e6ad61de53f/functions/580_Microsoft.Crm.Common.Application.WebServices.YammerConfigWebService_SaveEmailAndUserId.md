# Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::SaveEmailAndUserId

- ea: `0x580`
- end: `0x5be`
- name: `Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::SaveEmailAndUserId`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x130`

## callees

- `0x580`
- `0x5c0`

## pseudocode

```c

```

## disassembly

```asm
0x580  ldarg.1
0x581  ldarg.2
0x582  call     bool Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::TrySaveEmailAndUserId(string yammerEmailAddress, string yammerUserId)
0x587  brtrue.s loc_5BD
0x589  ldarg.0
0x58a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x58f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x594  ldstr    aErrorMessage0x// "Error_Message_0x8004b016"
0x599  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x59e  ldc.i4.1
0x59f  newarr   [mscorlib]System.Object
0x5a4  dup
0x5a5  ldc.i4.0
0x5a6  ldarg.1
0x5a7  stelem.ref
0x5a8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5ad  ldc.i4   0x8004B016
0x5b2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x5b7  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x5bc  throw
0x5bd  ret
```
