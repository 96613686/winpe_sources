# Microsoft.Crm.ACIAuthUtility::GetUCISHttpClient

- ea: `0x186e0`
- end: `0x1878c`
- name: `Microsoft.Crm.ACIAuthUtility::GetUCISHttpClient`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x186e0`
- `0x18790`

## string_xrefs

- `0x18780`: `RootManageSharedAccessKey`

## pseudocode

```c

```

## disassembly

```asm
0x186e0  ldarg.0
0x186e1  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ACIAuthUtility::GetACISEndPointData(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x186e6  stloc.0
0x186e7  ldloc.0
0x186e8  ldstr    aTenantprimaryk// "TenantPrimaryKey"
0x186ed  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x186f2  brfalse.s loc_18701
0x186f4  ldloc.0
0x186f5  ldstr    aTenantprimaryk// "TenantPrimaryKey"
0x186fa  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x186ff  brtrue.s loc_18721
0x18701  ldstr    aAcissecretkeyI// "ACISSecretKey is missing for OrgID {0}."
0x18706  ldc.i4.1
0x18707  newarr   [mscorlib]System.Object
0x1870c  dup
0x1870d  ldc.i4.0
0x1870e  ldarg.0
0x1870f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x18714  box      [mscorlib]System.Guid
0x18719  stelem.ref
0x1871a  call     void [System]System.Diagnostics.Trace::TraceError(string, object[])
0x1871f  ldnull
0x18720  ret
0x18721  ldloc.0
0x18722  ldstr    aConnectionstri// "ConnectionString"
0x18727  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1872c  castclass [mscorlib]System.String
0x18731  stloc.1
0x18732  ldloc.1
0x18733  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x18738  brfalse.s loc_1875A
0x1873a  ldstr    aAcisendpointIs// "ACISEndpoint is missing for OrgID {0}."
0x1873f  ldc.i4.1
0x18740  newarr   [mscorlib]System.Object
0x18745  dup
0x18746  ldc.i4.0
0x18747  ldarg.0
0x18748  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1874d  box      [mscorlib]System.Guid
0x18752  stelem.ref
0x18753  call     void [System]System.Diagnostics.Trace::TraceError(string, object[])
0x18758  ldnull
0x18759  ret
0x1875a  ldloc.0
0x1875b  ldstr    aTenantprimaryk// "TenantPrimaryKey"
0x18760  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x18765  castclass [mscorlib]System.Security.SecureString
0x1876a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmKeyService::GetStringFromSecureString(class [mscorlib]System.Security.SecureString)
0x1876f  stloc.2
0x18770  ldloc.1
0x18771  newobj   instance void [System]System.Uri::.ctor(string)
0x18776  ldstr    aData// "/data/"
0x1877b  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, string)
0x18780  ldstr    aRootmanageshar// "RootManageSharedAccessKey"
0x18785  ldloc.2
0x18786  newobj   instance void [Microsoft.Crm.RelationshipIntelligence.UCISClient]Microsoft.Crm.RelationshipIntelligence.UCISClient.UCISHttpClient::.ctor(class [System]System.Uri, string, string)
0x1878b  ret
```
