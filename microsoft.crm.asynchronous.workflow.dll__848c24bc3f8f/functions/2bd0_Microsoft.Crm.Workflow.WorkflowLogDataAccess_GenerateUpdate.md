# Microsoft.Crm.Workflow.WorkflowLogDataAccess::GenerateUpdate

- ea: `0x2bd0`
- end: `0x2d4d`
- name: `Microsoft.Crm.Workflow.WorkflowLogDataAccess::GenerateUpdate`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2920`

## callees

- `0x2bd0`
- `0x2d50`

## string_xrefs

- `0x2bd5`: `UPDATE [WorkflowLogBase] SET `

## pseudocode

```c

```

## disassembly

```asm
0x2bd0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2bd5  ldstr    aUpdateWorkflow_0// "UPDATE [WorkflowLogBase] SET "
0x2bda  call     instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2bdf  stloc.0
0x2be0  ldloc.0
0x2be1  ldstr    aModifiedbyUser// " [ModifiedBy] = @userid "
0x2be6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2beb  pop
0x2bec  ldarg.s  4
0x2bee  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2bf3  ldstr    aUserid// "@userid"
0x2bf8  callvirt instance bool [System.Data]System.Data.IDataParameterCollection::Contains(string)
0x2bfd  brtrue.s loc_2C22
0x2bff  ldarg.s  4
0x2c01  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2c06  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x2c0b  ldstr    aUserid// "@userid"
0x2c10  ldarg.s  5
0x2c12  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_UserId()
0x2c17  box      [mscorlib]System.Guid
0x2c1c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2c21  pop
0x2c22  ldarg.2
0x2c23  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x2c28  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Keys()
0x2c2d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x2c32  stloc.2
0x2c33  br       loc_2CE0
0x2c38  ldloc.2
0x2c39  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x2c3e  stloc.3
0x2c3f  ldarg.3
0x2c40  ldloc.3
0x2c41  ldc.i4.1
0x2c42  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x2c47  stloc.s  4
0x2c49  ldloc.s  4
0x2c4b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsPrimaryKey()
0x2c50  brtrue   loc_2CE0
0x2c55  ldloc.0
0x2c56  ldstr    asc_68E6// ", ["
0x2c5b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2c60  pop
0x2c61  ldloc.0
0x2c62  ldloc.s  4
0x2c64  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x2c69  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2c6e  ldstr    asc_6984// "] = "
0x2c73  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2c78  pop
0x2c79  ldarg.2
0x2c7a  ldloc.3
0x2c7b  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x2c80  brfalse.s loc_2CD4
0x2c82  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2c87  ldstr    a01_0// "@{0}{1}"
0x2c8c  ldc.i4.2
0x2c8d  newarr   [mscorlib]System.Object
0x2c92  dup
0x2c93  ldc.i4.0
0x2c94  ldloc.s  4
0x2c96  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x2c9b  stelem.ref
0x2c9c  dup
0x2c9d  ldc.i4.1
0x2c9e  ldarg.1
0x2c9f  box      [mscorlib]System.Int32
0x2ca4  stelem.ref
0x2ca5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2caa  stloc.s  5
0x2cac  ldloc.0
0x2cad  ldloc.s  5
0x2caf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2cb4  pop
0x2cb5  ldarg.0
0x2cb6  ldloc.s  4
0x2cb8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x2cbd  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x2cc2  ldloc.s  5
0x2cc4  ldarg.2
0x2cc5  ldloc.3
0x2cc6  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x2ccb  ldarg.s  4
0x2ccd  call     instance void Microsoft.Crm.Workflow.WorkflowLogDataAccess::SetParameter(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType attributeType, string parameterName, object value, class [System.Data]System.Data.IDbCommand command)
0x2cd2  br.s     loc_2CE0
0x2cd4  ldloc.0
0x2cd5  ldstr    aNull// "NULL"
0x2cda  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2cdf  pop
0x2ce0  ldloc.2
0x2ce1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2ce6  brtrue   loc_2C38
0x2ceb  leave.s  loc_2CF7
0x2ced  ldloc.2
0x2cee  brfalse.s loc_2CF6
0x2cf0  ldloc.2
0x2cf1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2cf6  endfinally
0x2cf7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2cfc  ldstr    aWorkflowlogid0// "@WorkflowLogId{0}"
0x2d01  ldc.i4.1
0x2d02  newarr   [mscorlib]System.Object
0x2d07  dup
0x2d08  ldc.i4.0
0x2d09  ldarg.1
0x2d0a  box      [mscorlib]System.Int32
0x2d0f  stelem.ref
0x2d10  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2d15  stloc.1
0x2d16  ldarg.s  4
0x2d18  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2d1d  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x2d22  ldloc.1
0x2d23  ldarg.2
0x2d24  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x2d29  box      [mscorlib]System.Guid
0x2d2e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2d33  pop
0x2d34  ldloc.0
0x2d35  ldstr    aWhereWorkflowl// " WHERE WorkflowLogId = "
0x2d3a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2d3f  ldloc.1
0x2d40  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2d45  pop
0x2d46  ldloc.0
0x2d47  callvirt instance string [mscorlib]System.Object::ToString()
0x2d4c  ret
```
