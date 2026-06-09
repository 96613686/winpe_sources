# Microsoft.Crm.Caching.MailboxCacheLoader::LoadCacheData

- ea: `0x4fe30`
- end: `0x5006e`
- name: `Microsoft.Crm.Caching.MailboxCacheLoader::LoadCacheData`
- size: `574`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x4dcb0`
- `0x4fe30`
- `0x126760`

## string_xrefs

- `0x4fe46`: `Mailbox OM Cache Loader started loading cache at: {0}`
- `0x4fe93`: `incomingemaildeliverymethod`
- `0x4feb3`: `processanddeleteemails`
- `0x4fedf`: `emailrouteraccessapproval`
- `0x4ff30`: `lastsuccessfulsynccompletedon`
- `0x4ff39`: `enabledforincomingemail`
- `0x4ff4b`: `incomingemailstatus`
- `0x4ffa5`: `MailboxCacheLoader.LoadCacheData(): could not add column '`
- `0x50043`: `MailboxCacheLoader.LoadCacheData(): completed in {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4fe30  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x4fe35  stloc.0
0x4fe36  ldarg.2
0x4fe37  ldc.i4.0
0x4fe38  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x4fe3d  stloc.3
0x4fe3e  ldarg.2
0x4fe3f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x4fe44  ldc.i4.s 0x11
0x4fe46  ldstr    aMailboxOmCache// "Mailbox OM Cache Loader started loading"...
0x4fe4b  ldc.i4.1
0x4fe4c  newarr   [mscorlib]System.Object
0x4fe51  dup
0x4fe52  ldc.i4.0
0x4fe53  ldloca.s 0
0x4fe55  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4fe5a  call     instance string [mscorlib]System.DateTime::ToString(class [mscorlib]System.IFormatProvider)
0x4fe5f  stelem.ref
0x4fe60  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4fe65  ldstr    aMailbox// "Mailbox"
0x4fe6a  ldarg.2
0x4fe6b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x4fe70  stloc.s  4
0x4fe72  ldc.i4.s 0x1E
0x4fe74  newarr   [mscorlib]System.String
0x4fe79  dup
0x4fe7a  ldc.i4.0
0x4fe7b  ldstr    aName// "name"
0x4fe80  stelem.ref
0x4fe81  dup
0x4fe82  ldc.i4.1
0x4fe83  ldstr    aEmailaddress// "emailaddress"
0x4fe88  stelem.ref
0x4fe89  dup
0x4fe8a  ldc.i4.2
0x4fe8b  ldstr    aEmailserverpro_1// "emailserverprofile"
0x4fe90  stelem.ref
0x4fe91  dup
0x4fe92  ldc.i4.3
0x4fe93  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x4fe98  stelem.ref
0x4fe99  dup
0x4fe9a  ldc.i4.4
0x4fe9b  ldstr    aIsforwardmailb// "isforwardmailbox"
0x4fea0  stelem.ref
0x4fea1  dup
0x4fea2  ldc.i4.5
0x4fea3  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x4fea8  stelem.ref
0x4fea9  dup
0x4feaa  ldc.i4.6
0x4feab  ldstr    aPassword// "password"
0x4feb0  stelem.ref
0x4feb1  dup
0x4feb2  ldc.i4.7
0x4feb3  ldstr    aProcessanddele// "processanddeleteemails"
0x4feb8  stelem.ref
0x4feb9  dup
0x4feba  ldc.i4.8
0x4febb  ldstr    aRegardingobjec_0// "regardingobjectid"
0x4fec0  stelem.ref
0x4fec1  dup
0x4fec2  ldc.i4.s 9
0x4fec4  ldstr    aRegardingobjec_1// "regardingobjecttypecode"
0x4fec9  stelem.ref
0x4feca  dup
0x4fecb  ldc.i4.s 0xA
0x4fecd  ldstr    aStatecode// "statecode"
0x4fed2  stelem.ref
0x4fed3  dup
0x4fed4  ldc.i4.s 0xB
0x4fed6  ldstr    aUsername// "username"
0x4fedb  stelem.ref
0x4fedc  dup
0x4fedd  ldc.i4.s 0xC
0x4fedf  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x4fee4  stelem.ref
0x4fee5  dup
0x4fee6  ldc.i4.s 0xD
0x4fee8  ldstr    aAllowemailconn// "allowemailconnectortousecredentials"
0x4feed  stelem.ref
0x4feee  dup
0x4feef  ldc.i4.s 0xE
0x4fef1  ldstr    aOwnerid// "ownerid"
0x4fef6  stelem.ref
0x4fef7  dup
0x4fef8  ldc.i4.s 0xF
0x4fefa  ldstr    aOwneridtype// "owneridtype"
0x4feff  stelem.ref
0x4ff00  dup
0x4ff01  ldc.i4.s 0x10
0x4ff03  ldstr    aActdeliverymet// "actdeliverymethod"
0x4ff08  stelem.ref
0x4ff09  dup
0x4ff0a  ldc.i4.s 0x11
0x4ff0c  ldstr    aUndeliverablef// "undeliverablefolder"
0x4ff11  stelem.ref
0x4ff12  dup
0x4ff13  ldc.i4.s 0x12
0x4ff15  ldstr    aEwsurl// "ewsurl"
0x4ff1a  stelem.ref
0x4ff1b  dup
0x4ff1c  ldc.i4.s 0x13
0x4ff1e  ldstr    aLastautodiscov// "lastautodiscoveredon"
0x4ff23  stelem.ref
0x4ff24  dup
0x4ff25  ldc.i4.s 0x14
0x4ff27  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x4ff2c  stelem.ref
0x4ff2d  dup
0x4ff2e  ldc.i4.s 0x15
0x4ff30  ldstr    aLastsuccessful// "lastsuccessfulsynccompletedon"
0x4ff35  stelem.ref
0x4ff36  dup
0x4ff37  ldc.i4.s 0x16
0x4ff39  ldstr    aEnabledforinco// "enabledforincomingemail"
0x4ff3e  stelem.ref
0x4ff3f  dup
0x4ff40  ldc.i4.s 0x17
0x4ff42  ldstr    aPostponesendin// "postponesendinguntil"
0x4ff47  stelem.ref
0x4ff48  dup
0x4ff49  ldc.i4.s 0x18
0x4ff4b  ldstr    aIncomingemails// "incomingemailstatus"
0x4ff50  stelem.ref
0x4ff51  dup
0x4ff52  ldc.i4.s 0x19
0x4ff54  ldstr    aActstatus// "actstatus"
0x4ff59  stelem.ref
0x4ff5a  dup
0x4ff5b  ldc.i4.s 0x1A
0x4ff5d  ldstr    aFolderhierarch// "folderhierarchy"
0x4ff62  stelem.ref
0x4ff63  dup
0x4ff64  ldc.i4.s 0x1B
0x4ff66  ldstr    aVerboselogging// "verboseloggingenabled"
0x4ff6b  stelem.ref
0x4ff6c  dup
0x4ff6d  ldc.i4.s 0x1C
0x4ff6f  ldstr    aDataencryption// "dataencryptionkey"
0x4ff74  stelem.ref
0x4ff75  dup
0x4ff76  ldc.i4.s 0x1D
0x4ff78  ldstr    aCredentialinfo// "credentialinfo"
0x4ff7d  stelem.ref
0x4ff7e  stloc.s  5
0x4ff80  ldc.i4.0
0x4ff81  stloc.s  6
0x4ff83  br.s     loc_4FFC7
0x4ff85  ldloc.s  5
0x4ff87  ldloc.s  6
0x4ff89  ldelem.ref
0x4ff8a  stloc.s  7
0x4ff8c  ldloc.s  4
0x4ff8e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x4ff93  ldloc.s  7
0x4ff95  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::TryAddColumn(string)
0x4ff9a  brtrue.s loc_4FFC1
0x4ff9c  ldnull
0x4ff9d  ldarg.2
0x4ff9e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x4ffa3  ldc.i4.s 0x3D
0x4ffa5  ldstr    aMailboxcachelo// "MailboxCacheLoader.LoadCacheData(): cou"...
0x4ffaa  ldloc.s  7
0x4ffac  ldstr    asc_26CCB8// "'"
0x4ffb1  call     string [mscorlib]System.String::Concat(string, string, string)
0x4ffb6  ldc.i4.0
0x4ffb7  newarr   [mscorlib]System.Object
0x4ffbc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4ffc1  ldloc.s  6
0x4ffc3  ldc.i4.1
0x4ffc4  add
0x4ffc5  stloc.s  6
0x4ffc7  ldloc.s  6
0x4ffc9  ldloc.s  5
0x4ffcb  ldlen
0x4ffcc  conv.i4
0x4ffcd  blt.s    loc_4FF85
0x4ffcf  ldloc.s  4
0x4ffd1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x4ffd6  ldloc.s  4
0x4ffd8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x4ffdd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x4ffe2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x4ffe7  ldc.i4.0
0x4ffe8  ldarg.1
0x4ffe9  box      [mscorlib]System.Guid
0x4ffee  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x4fff3  pop
0x4fff4  newobj   instance void Microsoft.Crm.ObjectModel.MailboxService::.ctor()
0x4fff9  ldloc.s  4
0x4fffb  ldarg.2
0x4fffc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x50001  stloc.1
0x50002  leave.s  loc_5000E
0x50004  ldloc.3
0x50005  brfalse.s loc_5000D
0x50007  ldloc.3
0x50008  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5000d  endfinally
0x5000e  ldnull
0x5000f  stloc.2
0x50010  ldloc.1
0x50011  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x50016  ldc.i4.0
0x50017  ble.s    loc_5003B
0x50019  ldloc.1
0x5001a  ldc.i4.0
0x5001b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x50020  newobj   instance void Microsoft.Crm.Caching.BusinessEntityCacheEntityWrapper::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity)
0x50025  stloc.s  8
0x50027  ldarg.2
0x50028  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5002d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxCacheData::.ctor(valuetype [mscorlib]System.Guid)
0x50032  stloc.2
0x50033  ldloc.2
0x50034  ldloc.s  8
0x50036  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxCacheData::Initialize(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheEntityWrapper)
0x5003b  ldarg.2
0x5003c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x50041  ldc.i4.s 0x3D
0x50043  ldstr    aMailboxcachelo_0// "MailboxCacheLoader.LoadCacheData(): com"...
0x50048  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x5004d  stloc.s  9
0x5004f  ldloca.s 9
0x50051  ldloc.0
0x50052  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0x50057  box      [mscorlib]System.TimeSpan
0x5005c  call     string [mscorlib]System.String::Format(string, object)
0x50061  ldc.i4.0
0x50062  newarr   [mscorlib]System.Object
0x50067  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5006c  ldloc.2
0x5006d  ret
```
