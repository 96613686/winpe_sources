# Microsoft.Crm.Authentication.Claims.OAuth.OAuthUtility::GetApplicationMasterInformation

- ea: `0x13ab0`
- end: `0x13b0d`
- name: `Microsoft.Crm.Authentication.Claims.OAuth.OAuthUtility::GetApplicationMasterInformation`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x13ae4`: `WebSiteUri`
- `0x13af4`: `RedirectUri`

## pseudocode

```c

```

## disassembly

```asm
0x13ab0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x13ab5  stloc.0
0x13ab6  ldloc.0
0x13ab7  ldstr    aClientid// "ClientID"
0x13abc  ldarg.0
0x13abd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x13ac2  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x13ac7  ldstr    aOauthapplicati// "OAuthApplicationMaster"
0x13acc  ldc.i4.5
0x13acd  newarr   [mscorlib]System.String
0x13ad2  dup
0x13ad3  ldc.i4.0
0x13ad4  ldstr    aApplicationnam// "ApplicationName"
0x13ad9  stelem.ref
0x13ada  dup
0x13adb  ldc.i4.1
0x13adc  ldstr    aState// "State"
0x13ae1  stelem.ref
0x13ae2  dup
0x13ae3  ldc.i4.2
0x13ae4  ldstr    aWebsiteuri// "WebSiteUri"
0x13ae9  stelem.ref
0x13aea  dup
0x13aeb  ldc.i4.3
0x13aec  ldstr    aDescription// "Description"
0x13af1  stelem.ref
0x13af2  dup
0x13af3  ldc.i4.4
0x13af4  ldstr    aRedirecturi// "RedirectUri"
0x13af9  stelem.ref
0x13afa  ldloc.0
0x13afb  ldc.i4.s 0x36
0x13afd  ldstr    aGetapplication// "GetApplicationMasterInformation"
0x13b02  ldstr    aDA1SSrcPlatfor_7// "D:\\a\\1\\s\\src\\Platform\\Authenticat"...
0x13b07  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x13b0c  ret
```
