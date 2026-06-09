# Microsoft.Crm.WebServices.OfflineSync::ValidateParameters

- ea: `0xf560`
- end: `0xf5ef`
- name: `Microsoft.Crm.WebServices.OfflineSync::ValidateParameters`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xf5f0`

## callees

- `0xf560`

## pseudocode

```c

```

## disassembly

```asm
0xf560  ldarg.1
0xf561  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xf566  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf56b  stloc.0
0xf56c  ldarg.0
0xf56d  ldloc.0
0xf56e  ldstr    aSubscriptionid// "SubscriptionId"
0xf573  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf578  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xf57d  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.WebServices.OfflineSync::subscriptionId
0xf582  ldarg.0
0xf583  ldloc.0
0xf584  ldstr    aEntityname// "EntityName"
0xf589  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf58e  stfld    string Microsoft.Crm.WebServices.OfflineSync::entityName
0xf593  ldarg.0
0xf594  ldloc.0
0xf595  ldstr    aBatchsize// "BatchSize"
0xf59a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf59f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf5a4  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xf5a9  stfld    int32 Microsoft.Crm.WebServices.OfflineSync::batchSize
0xf5ae  ldloc.0
0xf5af  ldstr    aAction// "Action"
0xf5b4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf5b9  stloc.1
0xf5ba  ldloc.1
0xf5bb  ldstr    a1// "1"
0xf5c0  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf5c5  brfalse.s loc_F5CF
0xf5c7  ldarg.0
0xf5c8  ldc.i4.1
0xf5c9  stfld    valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SyncAction Microsoft.Crm.WebServices.OfflineSync::syncAction
0xf5ce  ret
0xf5cf  ldloc.1
0xf5d0  ldstr    a2// "2"
0xf5d5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf5da  brfalse.s loc_F5E4
0xf5dc  ldarg.0
0xf5dd  ldc.i4.2
0xf5de  stfld    valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SyncAction Microsoft.Crm.WebServices.OfflineSync::syncAction
0xf5e3  ret
0xf5e4  ldstr    aActionIsNotVal// "Action is not valid."
0xf5e9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xf5ee  throw
```
