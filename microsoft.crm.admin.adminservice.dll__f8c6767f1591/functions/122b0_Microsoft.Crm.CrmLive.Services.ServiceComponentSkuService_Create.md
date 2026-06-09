# Microsoft.Crm.CrmLive.Services.ServiceComponentSkuService::Create

- ea: `0x122b0`
- end: `0x122ec`
- name: `Microsoft.Crm.CrmLive.Services.ServiceComponentSkuService::Create`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x12230`
- `0x122b0`

## string_xrefs

- `0x122cf`: `Create`
- `0x122b1`: `serviceComponentSku`
- `0x122c2`: `ServiceComponentSku`
- `0x122d4`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceComponentSkuService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x122b0  ldarg.1
0x122b1  ldstr    aServicecompone_3// "serviceComponentSku"
0x122b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x122bb  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x122c0  stloc.0
0x122c1  ldloc.0
0x122c2  ldstr    aServicecompone_4// "ServiceComponentSku"
0x122c7  ldarg.1
0x122c8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.CrmLive.Services.ServiceComponentSku::ToPropertyBag()
0x122cd  ldc.i4.s 0x28
0x122cf  ldstr    aCreate// "Create"
0x122d4  ldstr    aDA1SSrcCrmlive_24// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x122d9  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x122de  pop
0x122df  leave.s  loc_122EB
0x122e1  ldloc.0
0x122e2  brfalse.s loc_122EA
0x122e4  ldloc.0
0x122e5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x122ea  endfinally
0x122eb  ret
```
