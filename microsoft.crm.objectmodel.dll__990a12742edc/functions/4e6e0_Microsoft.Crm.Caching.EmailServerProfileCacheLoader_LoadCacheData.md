# Microsoft.Crm.Caching.EmailServerProfileCacheLoader::LoadCacheData

- ea: `0x4e6e0`
- end: `0x4e978`
- name: `Microsoft.Crm.Caching.EmailServerProfileCacheLoader::LoadCacheData`
- size: `664`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x4dcb0`
- `0x4e6e0`
- `0xf6940`

## string_xrefs

- `0x4e794`: `createdon`
- `0x4e6f9`: `Email Server Profile OM Cache Loader started loading cache at: {0}`
- `0x4e78b`: `timeoutmailboxconnectionafteramount`
- `0x4e7b8`: `incomingcredentialretrieval`
- `0x4e7c1`: `incomingauthenticationprotocol`
- `0x4e7ca`: `incomingpassword`
- `0x4e7d3`: `incomingportnumber`
- `0x4e7dc`: `incomingserverlocation`
- `0x4e7e5`: `incomingusername`
- `0x4e7ee`: `incomingusessl`
- `0x4e7f7`: `incominguseimpersonation`
- `0x4e800`: `moveundeliveredemails`
- `0x4e812`: `incomingpartnerapplication`
- `0x4e824`: `outgoingauthenticationprotocol`
- `0x4e82d`: `outgoinguseimpersonation`
- `0x4e836`: `outgoingautograntdelegateaccess`
- `0x4e94c`: `Email Server Profile OM Cache Loader finished loading cache at: {0}\nTotal time taken; {1}`

## pseudocode

```c

```

## disassembly

```asm
0x4e6e0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x4e6e5  stloc.0
0x4e6e6  ldnull
0x4e6e7  stloc.1
0x4e6e8  ldarg.2
0x4e6e9  ldc.i4.0
0x4e6ea  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x4e6ef  stloc.s  5
0x4e6f1  ldarg.2
0x4e6f2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x4e6f7  ldc.i4.s 0x11
0x4e6f9  ldstr    aEmailServerPro// "Email Server Profile OM Cache Loader st"...
0x4e6fe  ldc.i4.1
0x4e6ff  newarr   [mscorlib]System.Object
0x4e704  dup
0x4e705  ldc.i4.0
0x4e706  ldloca.s 0
0x4e708  call     instance string [mscorlib]System.DateTime::ToString()
0x4e70d  stelem.ref
0x4e70e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4e713  ldstr    aEmailserverpro// "EmailServerProfile"
0x4e718  ldarg.2
0x4e719  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x4e71e  stloc.s  6
0x4e720  ldloc.s  6
0x4e722  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x4e727  ldc.i4.s 0x25
0x4e729  newarr   [mscorlib]System.String
0x4e72e  dup
0x4e72f  ldc.i4.0
0x4e730  ldstr    aEmailserverpro_0// "emailserverprofileid"
0x4e735  stelem.ref
0x4e736  dup
0x4e737  ldc.i4.1
0x4e738  ldstr    aName// "name"
0x4e73d  stelem.ref
0x4e73e  dup
0x4e73f  ldc.i4.2
0x4e740  ldstr    aUseautodiscove// "useautodiscover"
0x4e745  stelem.ref
0x4e746  dup
0x4e747  ldc.i4.3
0x4e748  ldstr    aServertype// "servertype"
0x4e74d  stelem.ref
0x4e74e  dup
0x4e74f  ldc.i4.4
0x4e750  ldstr    aExchangeversio// "exchangeversion"
0x4e755  stelem.ref
0x4e756  dup
0x4e757  ldc.i4.5
0x4e758  ldstr    aStatecode// "statecode"
0x4e75d  stelem.ref
0x4e75e  dup
0x4e75f  ldc.i4.6
0x4e760  ldstr    aEncodingcodepa// "encodingcodepage"
0x4e765  stelem.ref
0x4e766  dup
0x4e767  ldc.i4.7
0x4e768  ldstr    aProcessemailsr// "processemailsreceivedafter"
0x4e76d  stelem.ref
0x4e76e  dup
0x4e76f  ldc.i4.8
0x4e770  ldstr    aMaxconcurrentc// "maxconcurrentconnections"
0x4e775  stelem.ref
0x4e776  dup
0x4e777  ldc.i4.s 9
0x4e779  ldstr    aOrganizationid_1// "organizationid"
0x4e77e  stelem.ref
0x4e77f  dup
0x4e780  ldc.i4.s 0xA
0x4e782  ldstr    aOwneremailaddr// "owneremailaddress"
0x4e787  stelem.ref
0x4e788  dup
0x4e789  ldc.i4.s 0xB
0x4e78b  ldstr    aTimeoutmailbox// "timeoutmailboxconnectionafteramount"
0x4e790  stelem.ref
0x4e791  dup
0x4e792  ldc.i4.s 0xC
0x4e794  ldstr    aCreatedon// "createdon"
0x4e799  stelem.ref
0x4e79a  dup
0x4e79b  ldc.i4.s 0xD
0x4e79d  ldstr    aSendemailalert// "sendemailalert"
0x4e7a2  stelem.ref
0x4e7a3  dup
0x4e7a4  ldc.i4.s 0xE
0x4e7a6  ldstr    aExchangeonline// "exchangeonlinetenantid"
0x4e7ab  stelem.ref
0x4e7ac  dup
0x4e7ad  ldc.i4.s 0xF
0x4e7af  ldstr    aDefaultserverl// "defaultserverlocation"
0x4e7b4  stelem.ref
0x4e7b5  dup
0x4e7b6  ldc.i4.s 0x10
0x4e7b8  ldstr    aIncomingcreden// "incomingcredentialretrieval"
0x4e7bd  stelem.ref
0x4e7be  dup
0x4e7bf  ldc.i4.s 0x11
0x4e7c1  ldstr    aIncomingauthen// "incomingauthenticationprotocol"
0x4e7c6  stelem.ref
0x4e7c7  dup
0x4e7c8  ldc.i4.s 0x12
0x4e7ca  ldstr    aIncomingpasswo// "incomingpassword"
0x4e7cf  stelem.ref
0x4e7d0  dup
0x4e7d1  ldc.i4.s 0x13
0x4e7d3  ldstr    aIncomingportnu// "incomingportnumber"
0x4e7d8  stelem.ref
0x4e7d9  dup
0x4e7da  ldc.i4.s 0x14
0x4e7dc  ldstr    aIncomingserver// "incomingserverlocation"
0x4e7e1  stelem.ref
0x4e7e2  dup
0x4e7e3  ldc.i4.s 0x15
0x4e7e5  ldstr    aIncominguserna// "incomingusername"
0x4e7ea  stelem.ref
0x4e7eb  dup
0x4e7ec  ldc.i4.s 0x16
0x4e7ee  ldstr    aIncomingusessl// "incomingusessl"
0x4e7f3  stelem.ref
0x4e7f4  dup
0x4e7f5  ldc.i4.s 0x17
0x4e7f7  ldstr    aIncominguseimp// "incominguseimpersonation"
0x4e7fc  stelem.ref
0x4e7fd  dup
0x4e7fe  ldc.i4.s 0x18
0x4e800  ldstr    aMoveundelivere// "moveundeliveredemails"
0x4e805  stelem.ref
0x4e806  dup
0x4e807  ldc.i4.s 0x19
0x4e809  ldstr    aMinpollinginte// "minpollingintervalinminutes"
0x4e80e  stelem.ref
0x4e80f  dup
0x4e810  ldc.i4.s 0x1A
0x4e812  ldstr    aIncomingpartne// "incomingpartnerapplication"
0x4e817  stelem.ref
0x4e818  dup
0x4e819  ldc.i4.s 0x1B
0x4e81b  ldstr    aOutgoingcreden// "outgoingcredentialretrieval"
0x4e820  stelem.ref
0x4e821  dup
0x4e822  ldc.i4.s 0x1C
0x4e824  ldstr    aOutgoingauthen// "outgoingauthenticationprotocol"
0x4e829  stelem.ref
0x4e82a  dup
0x4e82b  ldc.i4.s 0x1D
0x4e82d  ldstr    aOutgoinguseimp// "outgoinguseimpersonation"
0x4e832  stelem.ref
0x4e833  dup
0x4e834  ldc.i4.s 0x1E
0x4e836  ldstr    aOutgoingautogr// "outgoingautograntdelegateaccess"
0x4e83b  stelem.ref
0x4e83c  dup
0x4e83d  ldc.i4.s 0x1F
0x4e83f  ldstr    aOutgoingpasswo// "outgoingpassword"
0x4e844  stelem.ref
0x4e845  dup
0x4e846  ldc.i4.s 0x20
0x4e848  ldstr    aOutgoingportnu// "outgoingportnumber"
0x4e84d  stelem.ref
0x4e84e  dup
0x4e84f  ldc.i4.s 0x21
0x4e851  ldstr    aOutgoingserver// "outgoingserverlocation"
0x4e856  stelem.ref
0x4e857  dup
0x4e858  ldc.i4.s 0x22
0x4e85a  ldstr    aOutgoinguserna// "outgoingusername"
0x4e85f  stelem.ref
0x4e860  dup
0x4e861  ldc.i4.s 0x23
0x4e863  ldstr    aOutgoingusessl// "outgoingusessl"
0x4e868  stelem.ref
0x4e869  dup
0x4e86a  ldc.i4.s 0x24
0x4e86c  ldstr    aOutgoingpartne// "outgoingpartnerapplication"
0x4e871  stelem.ref
0x4e872  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x4e877  ldc.i4.2
0x4e878  newarr   [mscorlib]System.String
0x4e87d  dup
0x4e87e  ldc.i4.0
0x4e87f  ldstr    aDataencryption// "dataencryptionkey"
0x4e884  stelem.ref
0x4e885  dup
0x4e886  ldc.i4.1
0x4e887  ldstr    aCredentialinfo// "credentialinfo"
0x4e88c  stelem.ref
0x4e88d  stloc.s  7
0x4e88f  ldc.i4.0
0x4e890  stloc.s  8
0x4e892  br.s     loc_4E8C4
0x4e894  ldloc.s  7
0x4e896  ldloc.s  8
0x4e898  ldelem.ref
0x4e899  stloc.s  9
0x4e89b  ldloc.s  6
0x4e89d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x4e8a2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::get_EntityMetadata()
0x4e8a7  ldloc.s  9
0x4e8a9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x4e8ae  brfalse.s loc_4E8BE
0x4e8b0  ldloc.s  6
0x4e8b2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x4e8b7  ldloc.s  9
0x4e8b9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x4e8be  ldloc.s  8
0x4e8c0  ldc.i4.1
0x4e8c1  add
0x4e8c2  stloc.s  8
0x4e8c4  ldloc.s  8
0x4e8c6  ldloc.s  7
0x4e8c8  ldlen
0x4e8c9  conv.i4
0x4e8ca  blt.s    loc_4E894
0x4e8cc  ldloc.s  6
0x4e8ce  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x4e8d3  ldloc.s  6
0x4e8d5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x4e8da  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x4e8df  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x4e8e4  ldc.i4.0
0x4e8e5  ldarg.1
0x4e8e6  box      [mscorlib]System.Guid
0x4e8eb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x4e8f0  pop
0x4e8f1  newobj   instance void Microsoft.Crm.ObjectModel.EmailServerProfileService::.ctor()
0x4e8f6  ldloc.s  6
0x4e8f8  ldarg.2
0x4e8f9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4e8fe  stloc.1
0x4e8ff  leave.s  loc_4E90D
0x4e901  ldloc.s  5
0x4e903  brfalse.s loc_4E90C
0x4e905  ldloc.s  5
0x4e907  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e90c  endfinally
0x4e90d  ldnull
0x4e90e  stloc.2
0x4e90f  ldloc.1
0x4e910  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x4e915  ldc.i4.0
0x4e916  ble.s    loc_4E934
0x4e918  ldloc.1
0x4e919  ldc.i4.0
0x4e91a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x4e91f  newobj   instance void Microsoft.Crm.Caching.BusinessEntityCacheEntityWrapper::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity)
0x4e924  stloc.s  0xA
0x4e926  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerProfileData::.ctor()
0x4e92b  stloc.2
0x4e92c  ldloc.2
0x4e92d  ldloc.s  0xA
0x4e92f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerProfileData::Initialize(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheEntityWrapper)
0x4e934  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x4e939  stloc.3
0x4e93a  ldloca.s 3
0x4e93c  ldloc.0
0x4e93d  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0x4e942  stloc.s  4
0x4e944  ldarg.2
0x4e945  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x4e94a  ldc.i4.s 0x11
0x4e94c  ldstr    aEmailServerPro_0// "Email Server Profile OM Cache Loader fi"...
0x4e951  ldc.i4.2
0x4e952  newarr   [mscorlib]System.Object
0x4e957  dup
0x4e958  ldc.i4.0
0x4e959  ldloca.s 3
0x4e95b  call     instance string [mscorlib]System.DateTime::ToString()
0x4e960  stelem.ref
0x4e961  dup
0x4e962  ldc.i4.1
0x4e963  ldloca.s 4
0x4e965  constrained. [mscorlib]System.TimeSpan
0x4e96b  callvirt instance string [mscorlib]System.Object::ToString()
0x4e970  stelem.ref
0x4e971  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4e976  ldloc.2
0x4e977  ret
```
