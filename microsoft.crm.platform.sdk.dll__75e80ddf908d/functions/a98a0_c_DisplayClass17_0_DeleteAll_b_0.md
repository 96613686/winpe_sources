# <>c__DisplayClass17_0::<DeleteAll>b__0

- ea: `0xa98a0`
- end: `0xa9b6e`
- name: `<>c__DisplayClass17_0::<DeleteAll>b__0`
- size: `718`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task`

## callees

- `0x2500`
- `0x2520`
- `0x2560`
- `0xaf40`
- `0xaf50`
- `0xaff0`
- `0xa98a0`

## string_xrefs

- `0xa98ba`: `DeletionService: Inside DeletionService.DeleteAll`
- `0xa98da`: `DeletionService: Inside DeletionService.DeleteAll`
- `0xa98d5`: `DeleteAll`
- `0xa995a`: `DeleteAll`
- `0xa9aaa`: `DeleteAll`
- `0xa9b23`: `DeleteAll`
- `0xa993f`: `DeletionService: No table qualify to delete records. Exiting DeleteAll...`
- `0xa995f`: `DeletionService: No table qualify to delete records. Exiting DeleteAll...`
- `0xa99d9`: `DeletionService: Calling DeleteAll on Table {0} for ObjectTypeCode {1}`
- `0xa9a8a`: `DeletionService: All stale MatchCode<> table records deleted`
- `0xa9aaf`: `DeletionService: All stale MatchCode<> table records deleted`
- `0xa9afa`: `DeletionService: {0} MatchCode<> table(s) pending stale records delete and need reference to table SubscriptionTrackingDeletedObject`
- `0xa9b2d`: `DeletionService: {0} MatchCode<> table(s) pending stale records delete and need reference to table SubscriptionTrackingDeletedObject`

## pseudocode

```c

```

## disassembly

```asm
0xa98a0  ldarg.0
0xa98a1  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass17_0::<>4__this
0xa98a6  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa98ab  ldc.i4.s 0x14
0xa98ad  ldstr    a0// "{0}"
0xa98b2  ldc.i4.1
0xa98b3  newarr   [mscorlib]System.Object
0xa98b8  dup
0xa98b9  ldc.i4.0
0xa98ba  ldstr    aDeletionservic_70// "DeletionService: Inside DeletionService"...
0xa98bf  stelem.ref
0xa98c0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa98c5  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0xa98ca  ldarg.0
0xa98cb  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass17_0::<>4__this
0xa98d0  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa98d5  ldstr    aDeleteall// "DeleteAll"
0xa98da  ldstr    aDeletionservic_70// "DeletionService: Inside DeletionService"...
0xa98df  ldc.i4.0
0xa98e0  ldc.i4.0
0xa98e1  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0xa98e6  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xa98eb  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xa98f0  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xa98f5  ldc.i4.0
0xa98f6  ldsfld   string [mscorlib]System.String::Empty
0xa98fb  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0xa9900  ldarg.0
0xa9901  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass17_0::<>4__this
0xa9906  ldc.i4.0
0xa9907  stfld    bool Microsoft.Crm.DeletionService::_verifyStaleMatchCodeRecordsDeleted
0xa990c  ldarg.0
0xa990d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.TableEntity> <>c__DisplayClass17_0::tables
0xa9912  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.TableEntity>::get_Count()
0xa9917  brtrue.s loc_A9990
0xa9919  ldarg.0
0xa991a  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass17_0::<>4__this
0xa991f  ldc.i4.1
0xa9920  stfld    bool Microsoft.Crm.DeletionService::_verifyStaleMatchCodeRecordsDeleted
0xa9925  ldarg.0
0xa9926  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass17_0::<>4__this
0xa992b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa9930  ldc.i4.s 0x14
0xa9932  ldstr    a0// "{0}"
0xa9937  ldc.i4.1
0xa9938  newarr   [mscorlib]System.Object
0xa993d  dup
0xa993e  ldc.i4.0
0xa993f  ldstr    aDeletionservic_71// "DeletionService: No table qualify to de"...
0xa9944  stelem.ref
0xa9945  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa994a  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0xa994f  ldarg.0
0xa9950  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass17_0::<>4__this
0xa9955  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa995a  ldstr    aDeleteall// "DeleteAll"
0xa995f  ldstr    aDeletionservic_71// "DeletionService: No table qualify to de"...
0xa9964  ldc.i4.0
0xa9965  ldc.i4.m1
0xa9966  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0xa996b  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xa9970  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xa9975  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xa997a  ldarg.0
0xa997b  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass17_0::<>4__this
0xa9980  ldfld    bool Microsoft.Crm.DeletionService::_verifyStaleMatchCodeRecordsDeleted
0xa9985  ldsfld   string [mscorlib]System.String::Empty
0xa998a  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0xa998f  ret
0xa9990  ldarg.0
0xa9991  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass17_0::<>4__this
0xa9996  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa999b  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xa99a0  ldc.i4.0
0xa99a1  ldc.i4.0
0xa99a2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xa99a7  stloc.1
0xa99a8  ldloc.1
0xa99a9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xa99ae  ldloc.1
0xa99af  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0xa99b4  stloc.2
0xa99b5  ldarg.0
0xa99b6  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.TableEntity> <>c__DisplayClass17_0::tables
0xa99bb  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.TableEntity>::GetEnumerator()
0xa99c0  stloc.3
0xa99c1  br.s     loc_A9A16
0xa99c3  ldloca.s 3
0xa99c5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.TableEntity>::get_Current()
0xa99ca  stloc.s  4
0xa99cc  ldarg.0
0xa99cd  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass17_0::<>4__this
0xa99d2  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa99d7  ldc.i4.s 0x14
0xa99d9  ldstr    aDeletionservic_72// "DeletionService: Calling DeleteAll on T"...
0xa99de  ldc.i4.2
0xa99df  newarr   [mscorlib]System.Object
0xa99e4  dup
0xa99e5  ldc.i4.0
0xa99e6  ldloc.s  4
0xa99e8  callvirt instance string Microsoft.Crm.TableEntity::get_BaseTableName()
0xa99ed  stelem.ref
0xa99ee  dup
0xa99ef  ldc.i4.1
0xa99f0  ldloc.s  4
0xa99f2  callvirt instance int32 Microsoft.Crm.TableEntity::get_ObjectTypeCode()
0xa99f7  box      [mscorlib]System.Int32
0xa99fc  stelem.ref
0xa99fd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa9a02  ldloc.s  4
0xa9a04  ldloc.1
0xa9a05  ldloc.2
0xa9a06  ldarg.0
0xa9a07  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass17_0::<>4__this
0xa9a0c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa9a11  callvirt instance void Microsoft.Crm.TableEntity::DeleteAll(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection, class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, valuetype [mscorlib]System.Guid orgId)
0xa9a16  ldloca.s 3
0xa9a18  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.TableEntity>::MoveNext()
0xa9a1d  brtrue.s loc_A99C3
0xa9a1f  leave.s  loc_A9A43
0xa9a21  ldloca.s 3
0xa9a23  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.TableEntity>
0xa9a29  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa9a2e  endfinally
0xa9a2f  ldloc.2
0xa9a30  brfalse.s loc_A9A38
0xa9a32  ldloc.2
0xa9a33  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa9a38  endfinally
0xa9a39  ldloc.1
0xa9a3a  brfalse.s loc_A9A42
0xa9a3c  ldloc.1
0xa9a3d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa9a42  endfinally
0xa9a43  ldarg.0
0xa9a44  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.TableEntity> <>c__DisplayClass17_0::tables
0xa9a49  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.TableEntity, bool> <>c::<>9__17_1
0xa9a4e  dup
0xa9a4f  brtrue.s loc_A9A68
0xa9a51  pop
0xa9a52  ldsfld   class <>c <>c::<>9
0xa9a57  ldftn    instance bool <>c::<DeleteAll>b__17_1(class Microsoft.Crm.TableEntity t)
0xa9a5d  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.TableEntity, bool>::.ctor(object, native int)
0xa9a62  dup
0xa9a63  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.TableEntity, bool> <>c::<>9__17_1
0xa9a68  call     T0x2B00010A
0xa9a6d  stloc.0
0xa9a6e  ldloc.0
0xa9a6f  brtrue.s loc_A9AE0
0xa9a71  ldarg.0
0xa9a72  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass17_0::<>4__this
0xa9a77  ldc.i4.1
0xa9a78  stfld    bool Microsoft.Crm.DeletionService::_verifyStaleMatchCodeRecordsDeleted
0xa9a7d  ldarg.0
0xa9a7e  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass17_0::<>4__this
0xa9a83  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa9a88  ldc.i4.s 0x14
0xa9a8a  ldstr    aDeletionservic_73// "DeletionService: All stale MatchCode<> "...
0xa9a8f  ldc.i4.0
0xa9a90  newarr   [mscorlib]System.Object
0xa9a95  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa9a9a  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0xa9a9f  ldarg.0
0xa9aa0  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass17_0::<>4__this
0xa9aa5  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa9aaa  ldstr    aDeleteall// "DeleteAll"
0xa9aaf  ldstr    aDeletionservic_73// "DeletionService: All stale MatchCode<> "...
0xa9ab4  ldc.i4.0
0xa9ab5  ldc.i4.m1
0xa9ab6  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0xa9abb  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xa9ac0  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xa9ac5  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xa9aca  ldarg.0
0xa9acb  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass17_0::<>4__this
0xa9ad0  ldfld    bool Microsoft.Crm.DeletionService::_verifyStaleMatchCodeRecordsDeleted
0xa9ad5  ldsfld   string [mscorlib]System.String::Empty
0xa9ada  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0xa9adf  ret
0xa9ae0  ldarg.0
0xa9ae1  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass17_0::<>4__this
0xa9ae6  ldc.i4.0
0xa9ae7  stfld    bool Microsoft.Crm.DeletionService::_verifyStaleMatchCodeRecordsDeleted
0xa9aec  ldnull
0xa9aed  ldarg.0
0xa9aee  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass17_0::<>4__this
0xa9af3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa9af8  ldc.i4.s 0x15
0xa9afa  ldstr    aDeletionservic_74// "DeletionService: {0} MatchCode<> table("...
0xa9aff  ldc.i4.1
0xa9b00  newarr   [mscorlib]System.Object
0xa9b05  dup
0xa9b06  ldc.i4.0
0xa9b07  ldloc.0
0xa9b08  box      [mscorlib]System.Int32
0xa9b0d  stelem.ref
0xa9b0e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa9b13  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0xa9b18  ldarg.0
0xa9b19  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass17_0::<>4__this
0xa9b1e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa9b23  ldstr    aDeleteall// "DeleteAll"
0xa9b28  ldsfld   string [mscorlib]System.String::Empty
0xa9b2d  ldstr    aDeletionservic_74// "DeletionService: {0} MatchCode<> table("...
0xa9b32  ldloc.0
0xa9b33  box      [mscorlib]System.Int32
0xa9b38  call     string [mscorlib]System.String::Format(string, object)
0xa9b3d  ldc.i4.0
0xa9b3e  ldc.i4.m1
0xa9b3f  call     string [mscorlib]System.Environment::get_StackTrace()
0xa9b44  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0xa9b49  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xa9b4e  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xa9b53  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xa9b58  ldarg.0
0xa9b59  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass17_0::<>4__this
0xa9b5e  ldfld    bool Microsoft.Crm.DeletionService::_verifyStaleMatchCodeRecordsDeleted
0xa9b63  ldsfld   string [mscorlib]System.String::Empty
0xa9b68  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceError(valuetype [mscorlib]System.Guid organizationId, string moduleName, string crmTraceMessage, string errorMessage, int32 recordsDeleted, int32 durationInSecs, string stackTrace, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0xa9b6d  ret
```
