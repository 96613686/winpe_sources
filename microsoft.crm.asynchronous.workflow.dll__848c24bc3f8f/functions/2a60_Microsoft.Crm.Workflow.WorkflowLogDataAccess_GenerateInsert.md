# Microsoft.Crm.Workflow.WorkflowLogDataAccess::GenerateInsert

- ea: `0x2a60`
- end: `0x2bc2`
- name: `Microsoft.Crm.Workflow.WorkflowLogDataAccess::GenerateInsert`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2920`

## callees

- `0x2a60`
- `0x2d50`

## string_xrefs

- `0x2a65`: `INSERT INTO [WorkflowLogBase] ([ModifiedOnBehalfBy], [ModifiedBy], [CreatedBy],[ObjectTypeCode] `

## pseudocode

```c

```

## disassembly

```asm
0x2a60  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2a65  ldstr    aInsertIntoWork// "INSERT INTO [WorkflowLogBase] ([Modifie"...
0x2a6a  call     instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2a6f  stloc.0
0x2a70  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2a75  ldstr    aValuesNullUser// " VALUES( NULL, @userid, @userid, 4700"
0x2a7a  call     instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2a7f  stloc.1
0x2a80  ldarg.s  4
0x2a82  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2a87  ldstr    aUserid// "@userid"
0x2a8c  callvirt instance bool [System.Data]System.Data.IDataParameterCollection::Contains(string)
0x2a91  brtrue.s loc_2AB6
0x2a93  ldarg.s  4
0x2a95  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2a9a  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x2a9f  ldstr    aUserid// "@userid"
0x2aa4  ldarg.s  5
0x2aa6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_UserId()
0x2aab  box      [mscorlib]System.Guid
0x2ab0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2ab5  pop
0x2ab6  ldarg.2
0x2ab7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x2abc  ldstr    aWorkflowlogid// "workflowlogid"
0x2ac1  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x2ac6  brtrue.s loc_2AE3
0x2ac8  ldarg.2
0x2ac9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x2ace  ldstr    aWorkflowlogid// "workflowlogid"
0x2ad3  ldarg.2
0x2ad4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x2ad9  box      [mscorlib]System.Guid
0x2ade  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x2ae3  ldarg.2
0x2ae4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x2ae9  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Keys()
0x2aee  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x2af3  stloc.2
0x2af4  br       loc_2B86
0x2af9  ldloc.2
0x2afa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x2aff  stloc.3
0x2b00  ldarg.3
0x2b01  ldloc.3
0x2b02  ldc.i4.1
0x2b03  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x2b08  stloc.s  4
0x2b0a  ldloc.0
0x2b0b  ldstr    asc_68E6// ", ["
0x2b10  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2b15  ldloc.s  4
0x2b17  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x2b1c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2b21  ldstr    asc_68EE// "]"
0x2b26  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2b2b  pop
0x2b2c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2b31  ldstr    a01_0// "@{0}{1}"
0x2b36  ldc.i4.2
0x2b37  newarr   [mscorlib]System.Object
0x2b3c  dup
0x2b3d  ldc.i4.0
0x2b3e  ldloc.s  4
0x2b40  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x2b45  stelem.ref
0x2b46  dup
0x2b47  ldc.i4.1
0x2b48  ldarg.1
0x2b49  box      [mscorlib]System.Int32
0x2b4e  stelem.ref
0x2b4f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2b54  stloc.s  5
0x2b56  ldloc.1
0x2b57  ldstr    asc_6902// ", "
0x2b5c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2b61  ldloc.s  5
0x2b63  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2b68  pop
0x2b69  ldarg.0
0x2b6a  ldloc.s  4
0x2b6c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x2b71  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x2b76  ldloc.s  5
0x2b78  ldarg.2
0x2b79  ldloc.3
0x2b7a  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x2b7f  ldarg.s  4
0x2b81  call     instance void Microsoft.Crm.Workflow.WorkflowLogDataAccess::SetParameter(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType attributeType, string parameterName, object value, class [System.Data]System.Data.IDbCommand command)
0x2b86  ldloc.2
0x2b87  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2b8c  brtrue   loc_2AF9
0x2b91  leave.s  loc_2B9D
0x2b93  ldloc.2
0x2b94  brfalse.s loc_2B9C
0x2b96  ldloc.2
0x2b97  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b9c  endfinally
0x2b9d  ldloc.0
0x2b9e  ldstr    asc_6908// ") "
0x2ba3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2ba8  pop
0x2ba9  ldloc.1
0x2baa  ldstr    asc_690E// " ) "
0x2baf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2bb4  pop
0x2bb5  ldloc.0
0x2bb6  ldloc.1
0x2bb7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x2bbc  callvirt instance string [mscorlib]System.Object::ToString()
0x2bc1  ret
```
