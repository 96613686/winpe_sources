# Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::CancelPendingAsyncOperations

- ea: `0x27150`
- end: `0x271fa`
- name: `Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::CancelPendingAsyncOperations`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x26b20`

## callees

- `0x27150`

## string_xrefs

- `0x2716a`: `UPDATE [dbo].[AsyncOperationBase] SET [StatusCode] = @CancelStatus, [StateCode] = @CancelState, [FriendlyMessage] = @CancelMessage WHERE [StateCode] IN (@LockedState, @ReadyState, @SuspendedState) AND [RecurrencePattern] IS NULL`
- `0x271c4`: `ReadyState`

## pseudocode

```c

```

## disassembly

```asm
0x27150  ldstr    aBackgroundproc// "BackgroundProcessingDisabled.AsyncOpera"...
0x27155  ldarg.0
0x27156  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2715b  stloc.0
0x2715c  ldarg.0
0x2715d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x27162  ldc.i4.1
0x27163  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(bool)
0x27168  stloc.1
0x27169  ldloc.1
0x2716a  ldstr    aUpdateDboAsync// "UPDATE [dbo].[AsyncOperationBase] SET ["...
0x2716f  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x27174  ldloc.1
0x27175  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2717a  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x2717f  dup
0x27180  ldstr    aCancelstatus// "CancelStatus"
0x27185  ldc.i4.s 0x20
0x27187  box      [mscorlib]System.Int32
0x2718c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x27191  pop
0x27192  dup
0x27193  ldstr    aCancelstate// "CancelState"
0x27198  ldc.i4.3
0x27199  box      [mscorlib]System.Int32
0x2719e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x271a3  pop
0x271a4  dup
0x271a5  ldstr    aCancelmessage// "CancelMessage"
0x271aa  ldloc.0
0x271ab  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x271b0  pop
0x271b1  dup
0x271b2  ldstr    aLockedstate// "LockedState"
0x271b7  ldc.i4.2
0x271b8  box      [mscorlib]System.Int32
0x271bd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x271c2  pop
0x271c3  dup
0x271c4  ldstr    aReadystate// "ReadyState"
0x271c9  ldc.i4.0
0x271ca  box      [mscorlib]System.Int32
0x271cf  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x271d4  pop
0x271d5  ldstr    aSuspendedstate// "SuspendedState"
0x271da  ldc.i4.1
0x271db  box      [mscorlib]System.Int32
0x271e0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x271e5  pop
0x271e6  ldloc.1
0x271e7  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x271ec  pop
0x271ed  leave.s  loc_271F9
0x271ef  ldloc.1
0x271f0  brfalse.s loc_271F8
0x271f2  ldloc.1
0x271f3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x271f8  endfinally
0x271f9  ret
```
