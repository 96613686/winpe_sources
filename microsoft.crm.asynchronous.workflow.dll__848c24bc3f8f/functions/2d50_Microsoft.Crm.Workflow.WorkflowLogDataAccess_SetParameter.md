# Microsoft.Crm.Workflow.WorkflowLogDataAccess::SetParameter

- ea: `0x2d50`
- end: `0x2e0d`
- name: `Microsoft.Crm.Workflow.WorkflowLogDataAccess::SetParameter`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2a60`
- `0x2bd0`

## callees

- `0x2d50`

## pseudocode

```c

```

## disassembly

```asm
0x2d50  ldarg.s  4
0x2d52  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2d57  ldarg.2
0x2d58  callvirt instance bool [System.Data]System.Data.IDataParameterCollection::Contains(string)
0x2d5d  brfalse.s loc_2D60
0x2d5f  ret
0x2d60  ldarg.1
0x2d61  brfalse.s loc_2DB9
0x2d63  ldarg.1
0x2d64  ldc.i4.7
0x2d65  sub
0x2d66  switch   loc_2D95, loc_2DF8, loc_2DF8, loc_2D95, loc_2DF8, loc_2DB9, loc_2DF8, loc_2DB9, loc_2DB9, loc_2DDD
0x2d93  br.s     loc_2DF8
0x2d95  ldarg.s  4
0x2d97  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2d9c  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x2da1  ldarg.2
0x2da2  ldarg.3
0x2da3  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x2da8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x2dad  box      [mscorlib]System.Guid
0x2db2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2db7  pop
0x2db8  ret
0x2db9  ldarg.s  4
0x2dbb  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2dc0  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x2dc5  ldarg.2
0x2dc6  ldarg.3
0x2dc7  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x2dcc  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x2dd1  box      [mscorlib]System.Int32
0x2dd6  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2ddb  pop
0x2ddc  ret
0x2ddd  ldarg.s  4
0x2ddf  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2de4  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x2de9  ldarg.2
0x2dea  ldarg.3
0x2deb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2df0  ldc.i4.s 0xB
0x2df2  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x2df7  ret
0x2df8  ldarg.s  4
0x2dfa  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2dff  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x2e04  ldarg.2
0x2e05  ldarg.3
0x2e06  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2e0b  pop
0x2e0c  ret
```
