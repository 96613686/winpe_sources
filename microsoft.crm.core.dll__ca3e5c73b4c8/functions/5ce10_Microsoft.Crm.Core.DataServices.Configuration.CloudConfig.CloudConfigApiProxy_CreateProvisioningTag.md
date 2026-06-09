# Microsoft.Crm.Core.DataServices.Configuration.CloudConfig.CloudConfigApiProxy::CreateProvisioningTag

- ea: `0x5ce10`
- end: `0x5ce52`
- name: `Microsoft.Crm.Core.DataServices.Configuration.CloudConfig.CloudConfigApiProxy::CreateProvisioningTag`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1be80`
- `0x5c3a0`

## string_xrefs

- `0x5ce11`: `ProvisioningTagEntity`
- `0x5ce20`: `{0}provisioningtagentity/?ForMultiGeo={1}`

## pseudocode

```c

```

## disassembly

```asm
0x5ce10  ldarg.1
0x5ce11  ldstr    aProvisioningta// "ProvisioningTagEntity"
0x5ce16  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x5ce1b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5ce20  ldstr    a0Provisioningt_0// "{0}provisioningtagentity/?ForMultiGeo={"...
0x5ce25  ldc.i4.2
0x5ce26  newarr   [mscorlib]System.Object
0x5ce2b  dup
0x5ce2c  ldc.i4.0
0x5ce2d  ldarg.0
0x5ce2e  ldfld    class [System]System.Uri Microsoft.Crm.Core.DataServices.Configuration.CloudConfig.CloudConfigApiProxy::_cloudConfigApiUrl
0x5ce33  stelem.ref
0x5ce34  dup
0x5ce35  ldc.i4.1
0x5ce36  ldc.i4.0
0x5ce37  box      [mscorlib]System.Boolean
0x5ce3c  stelem.ref
0x5ce3d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5ce42  stloc.0
0x5ce43  ldarg.0
0x5ce44  ldloc.0
0x5ce45  newobj   instance void [System]System.Uri::.ctor(string)
0x5ce4a  ldarg.1
0x5ce4b  callvirt instance string Microsoft.Crm.Core.DataServices.Configuration.CloudConfig.CloudApiClient::PerformJsonPostRequest(class [System]System.Uri fullUrl, object content)
0x5ce50  pop
0x5ce51  ret
```
