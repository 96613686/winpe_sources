# Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::UnlockMailbox_0

- ea: `0x746d0`
- end: `0x74888`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::UnlockMailbox_0`
- size: `440`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x72600`
- `0x75740`

## callees

- `0x4d8c0`
- `0x746d0`

## string_xrefs

- `0x746e3`: `UPDATE MailboxBase\n													SET \n													HostId = NULL, \n													ProcessingStateCode = @waitingState, \n													PostponeMailboxProcessingUntil = CASE WHEN PostponeMailboxProcessingUntil > @postponeUntil THEN @postponeUntil ELSE PostponeMailboxProcessingUntil END\n													WHERE \n													MailboxId = @mailboxId`
- `0x747c3`: `Unlocking mailbox: {0} failed permanently after 15 attempts with exception. Exception: {1}.`
- `0x7483d`: `Mailbox: {0} found already unlocked.`
- `0x74862`: `Failed to fetch the data for mailbox: {0} from the MailboxCache. Exception: {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x746d0  ldc.i4.0
0x746d1  stloc.0
0x746d2  ldc.i4.1
0x746d3  stloc.1
0x746d4  ldc.i4.0
0x746d5  stloc.2
0x746d6  ldloc.0
0x746d7  ldc.i4.1
0x746d8  add
0x746d9  stloc.0
0x746da  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x746df  stloc.s  4
0x746e1  ldloc.s  4
0x746e3  ldstr    aUpdateMailboxb_1// "UPDATE MailboxBase\r\n\t\t\t\t\t\t\t\t"...
0x746e8  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x746ed  ldloc.s  4
0x746ef  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x746f4  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x746f9  dup
0x746fa  ldstr    aWaitingstate// "@waitingState"
0x746ff  ldc.i4.0
0x74700  box      [mscorlib]System.Int32
0x74705  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7470a  pop
0x7470b  dup
0x7470c  ldstr    aPostponeuntil// "@postponeUntil"
0x74711  ldarg.2
0x74712  box      [mscorlib]System.DateTime
0x74717  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7471c  pop
0x7471d  ldstr    aMailboxid_1// "@mailboxId"
0x74722  ldarg.1
0x74723  box      [mscorlib]System.Guid
0x74728  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7472d  pop
0x7472e  ldarg.0
0x7472f  ldloc.s  4
0x74731  ldloca.s 5
0x74733  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x74739  ldloc.s  5
0x7473b  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Nullable`1<int32>)
0x74740  stloc.2
0x74741  leave.s  loc_7474F
0x74743  ldloc.s  4
0x74745  brfalse.s loc_7474E
0x74747  ldloc.s  4
0x74749  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7474e  endfinally
0x7474f  leave    loc_747E8
0x74754  stloc.s  6
0x74756  ldloc.0
0x74757  ldc.i4.s 0xF
0x74759  bgt.s    loc_747B9
0x7475b  ldloc.s  6
0x7475d  ldarg.0
0x7475e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x74763  ldc.i4.s 0x3D
0x74765  ldstr    aUnlockingMailb_0// "Unlocking mailbox: {0} failed {1} time("...
0x7476a  ldc.i4.4
0x7476b  newarr   [mscorlib]System.Object
0x74770  dup
0x74771  ldc.i4.0
0x74772  ldarg.1
0x74773  box      [mscorlib]System.Guid
0x74778  stelem.ref
0x74779  dup
0x7477a  ldc.i4.1
0x7477b  ldloc.0
0x7477c  box      [mscorlib]System.Int32
0x74781  stelem.ref
0x74782  dup
0x74783  ldc.i4.2
0x74784  ldloc.1
0x74785  box      [mscorlib]System.Int32
0x7478a  stelem.ref
0x7478b  dup
0x7478c  ldc.i4.3
0x7478d  ldloc.s  6
0x7478f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x74794  stelem.ref
0x74795  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7479a  ldloc.1
0x7479b  ldc.i4   0xEA60
0x747a0  mul
0x747a1  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x747a6  ldloc.0
0x747a7  ldc.i4.8
0x747a8  bge.s    loc_747B0
0x747aa  ldloc.1
0x747ab  ldc.i4.2
0x747ac  mul
0x747ad  stloc.1
0x747ae  br.s     loc_747B4
0x747b0  ldloc.1
0x747b1  ldc.i4.2
0x747b2  div
0x747b3  stloc.1
0x747b4  leave    loc_746D6
0x747b9  ldloc.s  6
0x747bb  ldarg.0
0x747bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x747c1  ldc.i4.s 0x3D
0x747c3  ldstr    aUnlockingMailb_1// "Unlocking mailbox: {0} failed permanent"...
0x747c8  ldc.i4.2
0x747c9  newarr   [mscorlib]System.Object
0x747ce  dup
0x747cf  ldc.i4.0
0x747d0  ldarg.1
0x747d1  box      [mscorlib]System.Guid
0x747d6  stelem.ref
0x747d7  dup
0x747d8  ldc.i4.1
0x747d9  ldloc.s  6
0x747db  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x747e0  stelem.ref
0x747e1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x747e6  rethrow
0x747e8  nop
0x747e9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxCache::Instance()
0x747ee  ldarg.1
0x747ef  ldarg.0
0x747f0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x747f5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x747fa  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData>::LookupEntry(void, var<u1>)
0x747ff  stloc.3
0x74800  ldloc.2
0x74801  ldc.i4.0
0x74802  ble.s    loc_7482E
0x74804  ldarg.0
0x74805  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x7480a  ldloc.3
0x7480b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x74810  ldc.i4.s 0x3D
0x74812  ldc.i4.3
0x74813  ldstr    aSuccessfullyUn// "Successfully unlocked mailbox: {0}."
0x74818  ldc.i4.1
0x74819  newarr   [mscorlib]System.Object
0x7481e  dup
0x7481f  ldc.i4.0
0x74820  ldarg.1
0x74821  box      [mscorlib]System.Guid
0x74826  stelem.ref
0x74827  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x7482c  br.s     loc_74856
0x7482e  ldarg.0
0x7482f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x74834  ldloc.3
0x74835  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7483a  ldc.i4.s 0x3D
0x7483c  ldc.i4.3
0x7483d  ldstr    aMailbox0FoundA// "Mailbox: {0} found already unlocked."
0x74842  ldc.i4.1
0x74843  newarr   [mscorlib]System.Object
0x74848  dup
0x74849  ldc.i4.0
0x7484a  ldarg.1
0x7484b  box      [mscorlib]System.Guid
0x74850  stelem.ref
0x74851  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x74856  leave.s  loc_74887
0x74858  stloc.s  7
0x7485a  ldarg.0
0x7485b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x74860  ldc.i4.s 0x3D
0x74862  ldstr    aFailedToFetchT_2// "Failed to fetch the data for mailbox: {"...
0x74867  ldc.i4.2
0x74868  newarr   [mscorlib]System.Object
0x7486d  dup
0x7486e  ldc.i4.0
0x7486f  ldarg.1
0x74870  box      [mscorlib]System.Guid
0x74875  stelem.ref
0x74876  dup
0x74877  ldc.i4.1
0x74878  ldloc.s  7
0x7487a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x7487f  stelem.ref
0x74880  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x74885  leave.s  loc_74887
0x74887  ret
```
