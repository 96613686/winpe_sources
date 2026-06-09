# Microsoft.Crm.CrmLive.Provisioning.ManifestEncryptionDecryptionHelper::CreateFromKeyType

- ea: `0xe500`
- end: `0xe597`
- name: `Microsoft.Crm.CrmLive.Provisioning.ManifestEncryptionDecryptionHelper::CreateFromKeyType`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe1d0`

## callees

- `0xe500`
- `0xe5a0`
- `0xe5f0`

## string_xrefs

- `0xe538`: `CreateFromKeyType`
- `0xe53d`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\ManifestEncryptionDecryptionHelper.cs`

## pseudocode

```c

```

## disassembly

```asm
0xe500  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xe505  stloc.0
0xe506  ldloc.0
0xe507  ldstr    aName// "Name"
0xe50c  ldarg.0
0xe50d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe512  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xe517  ldstr    aExternalkey// "ExternalKey"
0xe51c  ldc.i4.2
0xe51d  newarr   [mscorlib]System.String
0xe522  dup
0xe523  ldc.i4.0
0xe524  ldstr    aApplicationsec// "ApplicationSecret"
0xe529  stelem.ref
0xe52a  dup
0xe52b  ldc.i4.1
0xe52c  ldstr    aExpireson// "ExpiresOn"
0xe531  stelem.ref
0xe532  ldloc.0
0xe533  ldc.i4   0xB9
0xe538  ldstr    aCreatefromkeyt// "CreateFromKeyType"
0xe53d  ldstr    aDDbsShDccm2110_16// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0xe542  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xe547  stloc.1
0xe548  ldloc.1
0xe549  brtrue.s loc_E54D
0xe54b  ldnull
0xe54c  ret
0xe54d  ldloc.1
0xe54e  ldstr    aApplicationsec// "ApplicationSecret"
0xe553  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xe558  castclass [mscorlib]System.Security.SecureString
0xe55d  stloc.2
0xe55e  ldloc.2
0xe55f  brtrue.s loc_E564
0xe561  ldnull
0xe562  br.s     loc_E56A
0xe564  ldloc.2
0xe565  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmKeyService::GetStringFromSecureString(class [mscorlib]System.Security.SecureString)
0xe56a  ldloc.1
0xe56b  ldstr    aExpireson// "ExpiresOn"
0xe570  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xe575  brtrue.s loc_E57A
0xe577  ldnull
0xe578  br.s     loc_E58A
0xe57a  ldloc.1
0xe57b  ldstr    aExpireson// "ExpiresOn"
0xe580  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xe585  callvirt instance string [mscorlib]System.Object::ToString()
0xe58a  stloc.3
0xe58b  ldloc.3
0xe58c  call     valuetype [mscorlib]System.DateTime Microsoft.Crm.CrmLive.Provisioning.ManifestEncryptionDecryptionHelper::GetUtcDateFromString(string input)
0xe591  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.ManifestEncryptionKey::.ctor(string key, valuetype [mscorlib]System.DateTime expiresOn)
0xe596  ret
```
