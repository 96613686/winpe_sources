# Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::ReadKeys

- ea: `0x8580`
- end: `0x860f`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::ReadKeys`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x8540`

## callees

- `0x8580`

## string_xrefs

- `0x85c5`: `ReadKeys`
- `0x85ca`: `d:\dbs\sh\dccm2\1101_190851\cmd\23\src\Common\Application\WebPages\Tools\Yammer\YammerOAuthCommon.cs`

## pseudocode

```c

```

## disassembly

```asm
0x8580  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x8585  ldstr    aId_1// "Id"
0x858a  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.ExternalKeyConstants::YammerApplication
0x858f  box      [mscorlib]System.Guid
0x8594  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x8599  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x859e  ldstr    aExternalkey// "ExternalKey"
0x85a3  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.ExternalKeyConstants::YammerApplication
0x85a8  box      [mscorlib]System.Guid
0x85ad  ldc.i4.2
0x85ae  newarr   [mscorlib]System.String
0x85b3  dup
0x85b4  ldc.i4.0
0x85b5  ldstr    aApplicationid// "ApplicationId"
0x85ba  stelem.ref
0x85bb  dup
0x85bc  ldc.i4.1
0x85bd  ldstr    aApplicationsec// "ApplicationSecret"
0x85c2  stelem.ref
0x85c3  ldc.i4.s 0x36
0x85c5  ldstr    aReadkeys// "ReadKeys"
0x85ca  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\2"...
0x85cf  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveById(string, object, string[], int32, string, string)
0x85d4  stloc.0
0x85d5  ldarg.0
0x85d6  ldloc.0
0x85d7  ldstr    aApplicationid// "ApplicationId"
0x85dc  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x85e1  castclass [mscorlib]System.String
0x85e6  stfld    string Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::applicationId
0x85eb  ldloc.0
0x85ec  ldstr    aApplicationsec// "ApplicationSecret"
0x85f1  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x85f6  castclass [mscorlib]System.Security.SecureString
0x85fb  stloc.1
0x85fc  ldarg.0
0x85fd  ldloc.1
0x85fe  brtrue.s loc_8603
0x8600  ldnull
0x8601  br.s     loc_8609
0x8603  ldloc.1
0x8604  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmKeyService::GetStringFromSecureString(class [mscorlib]System.Security.SecureString)
0x8609  stfld    string Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::applicationSecret
0x860e  ret
```
