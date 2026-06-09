# Microsoft.Crm.BusinessEntities.SoapContext::CaptureInOfflineQueue

- ea: `0x78ed0`
- end: `0x78ffb`
- name: `Microsoft.Crm.BusinessEntities.SoapContext::CaptureInOfflineQueue`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8c1d0`

## callees

- `0x66ae0`
- `0x785f0`
- `0x78640`
- `0x78c30`
- `0x78ed0`
- `0x79370`

## string_xrefs

- `0x78f2b`: `SOAP XML being captured in offline queue is {0}`
- `0x78f4b`: `INSERT INTO OfflineQueue(ObjectId, ObjectTypeCode, Data, CommandId, URL, HttpHeader, MethodName) VALUES (@ObjectId, @ObjectTypeCode, @Data,@OperationType,@Url,@HttpHeader, @MethodName)`

## pseudocode

```c

```

## disassembly

```asm
0x78ed0  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0x78ed5  brtrue.s loc_78ED8
0x78ed7  ret
0x78ed8  ldarg.0
0x78ed9  ldfld    bool Microsoft.Crm.BusinessEntities.SoapContext::_isCaptured
0x78ede  brfalse.s loc_78EE1
0x78ee0  ret
0x78ee1  ldarg.0
0x78ee2  call     instance bool Microsoft.Crm.BusinessEntities.SoapContext::get_IsEmpty()
0x78ee7  brfalse.s loc_78EF9
0x78ee9  ldarg.0
0x78eea  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest Microsoft.Crm.BusinessEntities.SoapContext::_request
0x78eef  brfalse.s loc_78EF9
0x78ef1  ldarg.0
0x78ef2  ldarg.s  4
0x78ef4  call     instance void Microsoft.Crm.BusinessEntities.SoapContext::SerializeRequest(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x78ef9  ldarg.0
0x78efa  call     instance bool Microsoft.Crm.BusinessEntities.SoapContext::get_IsEmpty()
0x78eff  brfalse.s loc_78F11
0x78f01  ldarg.0
0x78f02  call     instance object Microsoft.Crm.BusinessEntities.SoapContext::get_RawRequest()
0x78f07  brfalse.s loc_78F11
0x78f09  ldarg.0
0x78f0a  ldarg.s  4
0x78f0c  call     instance void Microsoft.Crm.BusinessEntities.SoapContext::SerializeRawRequest(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x78f11  ldarg.0
0x78f12  call     instance bool Microsoft.Crm.BusinessEntities.SoapContext::get_IsEmpty()
0x78f17  ldc.i4.0
0x78f18  ceq
0x78f1a  ldstr    aSoapPacketIsNo// "Soap Packet is not stored on Execution "...
0x78f1f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x78f24  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x78f29  ldc.i4.s 0x1B
0x78f2b  ldstr    aSoapXmlBeingCa// "SOAP XML being captured in offline queu"...
0x78f30  ldc.i4.1
0x78f31  newarr   [mscorlib]System.Object
0x78f36  dup
0x78f37  ldc.i4.0
0x78f38  ldarg.0
0x78f39  ldfld    string Microsoft.Crm.BusinessEntities.SoapContext::_soapXml
0x78f3e  stelem.ref
0x78f3f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x78f44  ldarg.s  4
0x78f46  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x78f4b  ldstr    aInsertIntoOffl// "INSERT INTO OfflineQueue(ObjectId, Obje"...
0x78f50  ldc.i4.1
0x78f51  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(string, bool)
0x78f56  dup
0x78f57  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x78f5c  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x78f61  dup
0x78f62  ldstr    aObjectid_3// "@ObjectId"
0x78f67  ldarg.2
0x78f68  box      [mscorlib]System.Guid
0x78f6d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x78f72  pop
0x78f73  dup
0x78f74  ldstr    aObjecttypecode_86// "@ObjectTypeCode"
0x78f79  ldarg.3
0x78f7a  box      [mscorlib]System.Int32
0x78f7f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x78f84  pop
0x78f85  dup
0x78f86  ldstr    aData_0// "@Data"
0x78f8b  ldarg.0
0x78f8c  ldfld    string Microsoft.Crm.BusinessEntities.SoapContext::_soapXml
0x78f91  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x78f96  pop
0x78f97  dup
0x78f98  ldstr    aOperationtype_0// "@OperationType"
0x78f9d  ldarg.1
0x78f9e  box      Microsoft.Crm.BusinessEntities.OfflineOperationType
0x78fa3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x78fa8  pop
0x78fa9  dup
0x78faa  ldstr    aUrl// "@Url"
0x78faf  ldarg.0
0x78fb0  ldfld    string Microsoft.Crm.BusinessEntities.SoapContext::_endpoint
0x78fb5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x78fba  pop
0x78fbb  dup
0x78fbc  ldstr    aHttpheader// "@HttpHeader"
0x78fc1  ldarg.0
0x78fc2  ldfld    string Microsoft.Crm.BusinessEntities.SoapContext::_httpHeader
0x78fc7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x78fcc  pop
0x78fcd  ldstr    aMethodname// "@MethodName"
0x78fd2  ldarg.0
0x78fd3  ldfld    string Microsoft.Crm.BusinessEntities.SoapContext::_crmMethodName
0x78fd8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x78fdd  pop
0x78fde  ldc.i4   0x2A6
0x78fe3  ldstr    aCaptureinoffli// "CaptureInOfflineQueue"
0x78fe8  ldstr    aDA1SSrcManaged_17// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x78fed  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x78ff2  pop
0x78ff3  ldarg.0
0x78ff4  ldc.i4.1
0x78ff5  stfld    bool Microsoft.Crm.BusinessEntities.SoapContext::_isCaptured
0x78ffa  ret
```
