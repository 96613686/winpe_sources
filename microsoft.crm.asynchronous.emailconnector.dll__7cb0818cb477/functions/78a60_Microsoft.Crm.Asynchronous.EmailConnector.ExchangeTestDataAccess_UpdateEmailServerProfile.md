# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTestDataAccess::UpdateEmailServerProfile

- ea: `0x78a60`
- end: `0x78bdf`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTestDataAccess::UpdateEmailServerProfile`
- size: `383`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7950`
- `0x53210`

## callees

- `0x75260`
- `0x75280`
- `0x752c0`
- `0x75300`
- `0x75340`
- `0x75380`
- `0x753a0`
- `0x753c0`
- `0x75400`
- `0x77a30`
- `0x77de0`
- `0x78a60`

## string_xrefs

- `0x78a78`: `UPDATE EmailServerProfileBase SET`

## pseudocode

```c

```

## disassembly

```asm
0x78a60  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x78a65  stloc.0
0x78a66  ldloc.0
0x78a67  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x78a6c  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x78a71  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x78a76  stloc.1
0x78a77  ldloc.1
0x78a78  ldstr    aUpdateEmailser// "UPDATE EmailServerProfileBase SET"
0x78a7d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x78a82  pop
0x78a83  ldloc.1
0x78a84  ldstr    aLastauthorizat// "LastAuthorizationStatus=@lastAuthorizat"...
0x78a89  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x78a8e  pop
0x78a8f  ldloc.1
0x78a90  ldstr    aLasttestexecut// "LastTestExecutionStatus=@lastTestExecut"...
0x78a95  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x78a9a  pop
0x78a9b  ldloc.1
0x78a9c  ldstr    aLasttestvalida// "LastTestValidationStatus=@lastTestValid"...
0x78aa1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x78aa6  pop
0x78aa7  ldloc.1
0x78aa8  ldstr    aLastteststartt// "LastTestStartTime=@lastTestStartTime,"
0x78aad  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x78ab2  pop
0x78ab3  ldloc.1
0x78ab4  ldstr    aLasttesttotale// "LastTestTotalExecutionTime=@lastTestTot"...
0x78ab9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x78abe  pop
0x78abf  ldloc.1
0x78ac0  ldstr    aLasttestreques// "LastTestRequest=@lasttestrequest,"
0x78ac5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x78aca  pop
0x78acb  ldloc.1
0x78acc  ldstr    aLasttestrespon// "LastTestResponse=@lasttestresponse,"
0x78ad1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x78ad6  pop
0x78ad7  ldloc.1
0x78ad8  ldstr    aLastcrmmessage// "LastCrmMessage=@lastcrmmessage"
0x78add  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x78ae2  pop
0x78ae3  ldloc.1
0x78ae4  ldstr    aWhereEmailserv_0// "WHERE EmailServerProfileId=@emailServer"...
0x78ae9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x78aee  pop
0x78aef  dup
0x78af0  ldstr    aLastauthorizat_0// "@lastAuthorizationStatus"
0x78af5  ldarg.1
0x78af6  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.EmailServerProfileTestStatus Microsoft.Crm.Asynchronous.EmailConnector.EmailServerProfileStatus::get_LastAuthorizationStatus()
0x78afb  box      Microsoft.Crm.Asynchronous.EmailConnector.EmailServerProfileTestStatus
0x78b00  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x78b05  pop
0x78b06  dup
0x78b07  ldstr    aLasttestvalida_0// "@lastTestValidationStatus"
0x78b0c  ldarg.1
0x78b0d  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.EmailServerProfileTestStatus Microsoft.Crm.Asynchronous.EmailConnector.EmailServerProfileStatus::get_LastTestValidationStatus()
0x78b12  box      Microsoft.Crm.Asynchronous.EmailConnector.EmailServerProfileTestStatus
0x78b17  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x78b1c  pop
0x78b1d  dup
0x78b1e  ldstr    aLasttestexecut_0// "@lastTestExecutionStatus"
0x78b23  ldarg.1
0x78b24  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.EmailServerProfileTestStatus Microsoft.Crm.Asynchronous.EmailConnector.EmailServerProfileStatus::get_LastTestExecutionStatus()
0x78b29  box      Microsoft.Crm.Asynchronous.EmailConnector.EmailServerProfileTestStatus
0x78b2e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x78b33  pop
0x78b34  dup
0x78b35  ldstr    aLastteststartt_0// "@lastTestStartTime"
0x78b3a  ldarg.1
0x78b3b  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.EmailServerProfileStatus::get_LastTestStartTime()
0x78b40  box      [mscorlib]System.DateTime
0x78b45  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x78b4a  pop
0x78b4b  dup
0x78b4c  ldstr    aLasttesttotale_0// "@lastTestTotalExecutionTime"
0x78b51  ldarg.1
0x78b52  callvirt instance int64 Microsoft.Crm.Asynchronous.EmailConnector.EmailServerProfileStatus::get_LastTestTotalExecutionTime()
0x78b57  box      [mscorlib]System.Int64
0x78b5c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x78b61  pop
0x78b62  dup
0x78b63  ldstr    aLasttestreques_0// "@lasttestrequest"
0x78b68  ldarg.1
0x78b69  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.EmailServerProfileStatus::get_LastTestRequest()
0x78b6e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x78b73  pop
0x78b74  dup
0x78b75  ldstr    aLasttestrespon_0// "@lasttestresponse"
0x78b7a  ldarg.1
0x78b7b  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.EmailServerProfileStatus::get_LastTestResponse()
0x78b80  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x78b85  pop
0x78b86  dup
0x78b87  ldstr    aLastcrmmessage_0// "@lastcrmmessage"
0x78b8c  ldarg.1
0x78b8d  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.EmailServerProfileStatus::get_LastCrmMessage()
0x78b92  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x78b97  pop
0x78b98  ldstr    aEmailserverpro_6// "@emailServerProfile"
0x78b9d  ldarg.1
0x78b9e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile Microsoft.Crm.Asynchronous.EmailConnector.EmailServerProfileStatus::get_EmailServerProfile()
0x78ba3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile::get_EmailServerProfileId()
0x78ba8  box      [mscorlib]System.Guid
0x78bad  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x78bb2  pop
0x78bb3  ldloc.0
0x78bb4  ldloc.1
0x78bb5  callvirt instance string [mscorlib]System.Object::ToString()
0x78bba  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x78bbf  ldarg.0
0x78bc0  ldloc.0
0x78bc1  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x78bc6  pop
0x78bc7  call     class Microsoft.Crm.Asynchronous.EmailConnector.ServerSideSyncTelemetryEventSource Microsoft.Crm.Asynchronous.EmailConnector.ServerSideSyncTelemetryEventSource::get_Instance()
0x78bcc  ldarg.1
0x78bcd  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ServerSideSyncTelemetryEventSource::GetExchangeConnectivityInformation(class Microsoft.Crm.Asynchronous.EmailConnector.EmailServerProfileStatus exchangeConnectivityStatus)
0x78bd2  leave.s  loc_78BDE
0x78bd4  ldloc.0
0x78bd5  brfalse.s loc_78BDD
0x78bd7  ldloc.0
0x78bd8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x78bdd  endfinally
0x78bde  ret
```
