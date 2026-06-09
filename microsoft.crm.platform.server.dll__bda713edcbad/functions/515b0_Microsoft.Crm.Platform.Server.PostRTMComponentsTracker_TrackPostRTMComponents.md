# Microsoft.Crm.Platform.Server.PostRTMComponentsTracker::TrackPostRTMComponents

- ea: `0x515b0`
- end: `0x51669`
- name: `Microsoft.Crm.Platform.Server.PostRTMComponentsTracker::TrackPostRTMComponents`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x43360`
- `0x5b740`

## callees

- `0x515b0`

## string_xrefs

- `0x515b6`: `componentId`
- `0x51603`: `IF EXISTS (SELECT * FROM sys.objects WHERE object_id = OBJECT_ID(N'PostRTMComponents') AND type in (N'U')) BEGIN INSERT INTO PostRTMComponents (ObjectId, ComponentType) VALUES (@Id, @Type) END`
- `0x5164c`: `TrackPostRTMComponents`
- `0x51651`: `D:\a\1\s\src\ManagedPlatform\Server\PostRTMComponentsTracker.cs`

## pseudocode

```c

```

## disassembly

```asm
0x515b0  ldarg.0
0x515b1  box      [mscorlib]System.Guid
0x515b6  ldstr    aComponentid// "componentId"
0x515bb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x515c0  ldarg.2
0x515c1  ldstr    aContext// "context"
0x515c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x515cb  ldarg.2
0x515cc  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_IsSystemContext()
0x515d1  brfalse  loc_51668
0x515d6  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInCrmInternalToolContext()
0x515db  brtrue   loc_51668
0x515e0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x515e5  ldarg.2
0x515e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x515eb  ldarg.2
0x515ec  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x515f1  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x515f6  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x515fb  brfalse.s loc_51668
0x515fd  ldarg.1
0x515fe  ldc.i4.s 0x16
0x51600  bne.un.s loc_51603
0x51602  ret
0x51603  ldstr    aIfExistsSelect_2// "IF EXISTS (SELECT * FROM sys.objects WH"...
0x51608  stloc.0
0x51609  ldarg.2
0x5160a  ldloc.0
0x5160b  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(string)
0x51610  stloc.1
0x51611  ldloc.1
0x51612  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x51617  ldstr    aId_6// "@Id"
0x5161c  ldarg.0
0x5161d  box      [mscorlib]System.Guid
0x51622  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x51627  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x5162c  pop
0x5162d  ldloc.1
0x5162e  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x51633  ldstr    aType_1// "@Type"
0x51638  ldarg.1
0x51639  box      [mscorlib]System.Int32
0x5163e  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x51643  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x51648  pop
0x51649  ldloc.1
0x5164a  ldc.i4.s 0x22
0x5164c  ldstr    aTrackpostrtmco// "TrackPostRTMComponents"
0x51651  ldstr    aDA1SSrcManaged_11// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x51656  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x5165b  pop
0x5165c  leave.s  loc_51668
0x5165e  ldloc.1
0x5165f  brfalse.s loc_51667
0x51661  ldloc.1
0x51662  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x51667  endfinally
0x51668  ret
```
