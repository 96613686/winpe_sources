# Microsoft.Crm.Metadata.SecurityHelper::CreatePrivilege

- ea: `0x59df0`
- end: `0x5a19d`
- name: `Microsoft.Crm.Metadata.SecurityHelper::CreatePrivilege`
- size: `941`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x5a390`

## callees

- `0x59df0`
- `0x5a1a0`
- `0x5a2f0`

## string_xrefs

- `0x5a121`: `Create`
- `0x5a110`: `Privilege`
- `0x59e93`: `@privilegeid`
- `0x59fcd`: `@privilegeid`
- `0x5a07a`: `@privilegeid`
- `0x59f35`: `@accessright`
- `0x5a015`: `@accessright`
- `0x5a0b0`: `@accessright`
- `0x59f7b`: `PrivilegeBase`
- `0x5a03a`: `PrivilegeBase`
- `0x59f83`: `PrivilegeId`
- `0x5a042`: `PrivilegeId`
- `0x59fc4`: `AccessRight`
- `0x5a072`: `AccessRight`
- `0x5a0cd`: `CreatePrivilege`
- `0x5a0d2`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\SecurityHelper.cs`
- `0x5a16b`: `Created Privilege Id: {0} Name: {1} For Entity ObjectTypeCode: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x59df0  ldc.i4.0
0x59df1  stloc.0
0x59df2  ldstr    aCanbeentityref// "canbeentityreference"
0x59df7  stloc.1
0x59df8  ldstr    aCanbeparentent// "canbeparententityreference"
0x59dfd  stloc.2
0x59dfe  ldarg.s  0xA
0x59e00  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x59e05  ldc.i4   0x3FF
0x59e0a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x59e0f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesSortedByColumnNumber()
0x59e14  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::GetEnumerator()
0x59e19  stloc.3
0x59e1a  br.s     loc_59E66
0x59e1c  ldloc.3
0x59e1d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Current()
0x59e22  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x59e27  stloc.s  4
0x59e29  ldloc.1
0x59e2a  ldc.i4.0
0x59e2b  ldloc.1
0x59e2c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x59e31  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x59e36  ldloc.s  4
0x59e38  callvirt instance string [mscorlib]System.String::ToLower()
0x59e3d  callvirt instance bool [mscorlib]System.String::Contains(string)
0x59e42  brtrue.s loc_59E5F
0x59e44  ldloc.2
0x59e45  ldc.i4.0
0x59e46  ldloc.2
0x59e47  callvirt instance int32 [mscorlib]System.String::get_Length()
0x59e4c  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x59e51  ldloc.s  4
0x59e53  callvirt instance string [mscorlib]System.String::ToLower()
0x59e58  callvirt instance bool [mscorlib]System.String::Contains(string)
0x59e5d  br.s     loc_59E60
0x59e5f  ldc.i4.1
0x59e60  brfalse.s loc_59E66
0x59e62  ldc.i4.1
0x59e63  stloc.0
0x59e64  leave.s  loc_59E7A
0x59e66  ldloc.3
0x59e67  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x59e6c  brtrue.s loc_59E1C
0x59e6e  leave.s  loc_59E7A
0x59e70  ldloc.3
0x59e71  brfalse.s loc_59E79
0x59e73  ldloc.3
0x59e74  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x59e79  endfinally
0x59e7a  ldarg.s  0xA
0x59e7c  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x59e81  stloc.s  5
0x59e83  ldloc.s  5
0x59e85  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x59e8a  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x59e8f  stloc.s  6
0x59e91  ldloc.s  6
0x59e93  ldstr    aPrivilegeid_0// "@privilegeid"
0x59e98  ldarg.0
0x59e99  box      [mscorlib]System.Guid
0x59e9e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x59ea3  pop
0x59ea4  ldloc.s  6
0x59ea6  ldstr    aName_1// "@name"
0x59eab  ldc.i4.s 0xC
0x59ead  ldc.i4.s 0x64
0x59eaf  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x59eb4  ldarg.1
0x59eb5  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x59eba  ldloc.s  6
0x59ebc  ldstr    aCanbebasic_0// "@canbebasic"
0x59ec1  ldarg.2
0x59ec2  box      [mscorlib]System.Boolean
0x59ec7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x59ecc  pop
0x59ecd  ldloc.s  6
0x59ecf  ldstr    aCanbelocal_0// "@canbelocal"
0x59ed4  ldarg.3
0x59ed5  box      [mscorlib]System.Boolean
0x59eda  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x59edf  pop
0x59ee0  ldloc.s  6
0x59ee2  ldstr    aCanbedeep_0// "@canbedeep"
0x59ee7  ldarg.s  4
0x59ee9  box      [mscorlib]System.Boolean
0x59eee  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x59ef3  pop
0x59ef4  ldloc.s  6
0x59ef6  ldstr    aCanbeglobal_0// "@canbeglobal"
0x59efb  ldarg.s  5
0x59efd  box      [mscorlib]System.Boolean
0x59f02  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x59f07  pop
0x59f08  ldloc.0
0x59f09  brfalse.s loc_59F33
0x59f0b  ldloc.s  6
0x59f0d  ldstr    aCanbeentityref_0// "@canbeentityreference"
0x59f12  ldarg.s  6
0x59f14  box      [mscorlib]System.Boolean
0x59f19  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x59f1e  pop
0x59f1f  ldloc.s  6
0x59f21  ldstr    aCanbeparentent_0// "@canbeparententityreference"
0x59f26  ldarg.s  7
0x59f28  box      [mscorlib]System.Boolean
0x59f2d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x59f32  pop
0x59f33  ldloc.s  6
0x59f35  ldstr    aAccessright_0// "@accessright"
0x59f3a  ldarg.s  8
0x59f3c  box      [mscorlib]System.Int32
0x59f41  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x59f46  pop
0x59f47  ldloc.s  6
0x59f49  ldstr    aObjecttypecode_1// "@objecttypecode"
0x59f4e  ldarg.s  9
0x59f50  box      [mscorlib]System.Int32
0x59f55  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x59f5a  pop
0x59f5b  ldstr    asc_804C0// ""
0x59f60  stloc.s  7
0x59f62  ldloc.0
0x59f63  brfalse  loc_5A027
0x59f68  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x59f6d  ldstr    aInsertInto0123// "insert into {0} ({1},{2},{3},{4},{5},{6"...
0x59f72  ldc.i4.s 0x13
0x59f74  newarr   [mscorlib]System.Object
0x59f79  dup
0x59f7a  ldc.i4.0
0x59f7b  ldstr    aPrivilegebase// "PrivilegeBase"
0x59f80  stelem.ref
0x59f81  dup
0x59f82  ldc.i4.1
0x59f83  ldstr    aPrivilegeid_1// "PrivilegeId"
0x59f88  stelem.ref
0x59f89  dup
0x59f8a  ldc.i4.2
0x59f8b  ldstr    aName_0// "Name"
0x59f90  stelem.ref
0x59f91  dup
0x59f92  ldc.i4.3
0x59f93  ldstr    aCanbebasic_1// "CanBeBasic"
0x59f98  stelem.ref
0x59f99  dup
0x59f9a  ldc.i4.4
0x59f9b  ldstr    aCanbelocal_1// "CanBeLocal"
0x59fa0  stelem.ref
0x59fa1  dup
0x59fa2  ldc.i4.5
0x59fa3  ldstr    aCanbedeep_1// "CanBeDeep"
0x59fa8  stelem.ref
0x59fa9  dup
0x59faa  ldc.i4.6
0x59fab  ldstr    aCanbeglobal_1// "CanBeGlobal"
0x59fb0  stelem.ref
0x59fb1  dup
0x59fb2  ldc.i4.7
0x59fb3  ldstr    aCanbeentityref_1// "CanBeEntityReference"
0x59fb8  stelem.ref
0x59fb9  dup
0x59fba  ldc.i4.8
0x59fbb  ldstr    aCanbeparentent_1// "CanBeParentEntityReference"
0x59fc0  stelem.ref
0x59fc1  dup
0x59fc2  ldc.i4.s 9
0x59fc4  ldstr    aAccessright_1// "AccessRight"
0x59fc9  stelem.ref
0x59fca  dup
0x59fcb  ldc.i4.s 0xA
0x59fcd  ldstr    aPrivilegeid_0// "@privilegeid"
0x59fd2  stelem.ref
0x59fd3  dup
0x59fd4  ldc.i4.s 0xB
0x59fd6  ldstr    aName_1// "@name"
0x59fdb  stelem.ref
0x59fdc  dup
0x59fdd  ldc.i4.s 0xC
0x59fdf  ldstr    aCanbebasic_0// "@canbebasic"
0x59fe4  stelem.ref
0x59fe5  dup
0x59fe6  ldc.i4.s 0xD
0x59fe8  ldstr    aCanbelocal_0// "@canbelocal"
0x59fed  stelem.ref
0x59fee  dup
0x59fef  ldc.i4.s 0xE
0x59ff1  ldstr    aCanbedeep_0// "@canbedeep"
0x59ff6  stelem.ref
0x59ff7  dup
0x59ff8  ldc.i4.s 0xF
0x59ffa  ldstr    aCanbeglobal_0// "@canbeglobal"
0x59fff  stelem.ref
0x5a000  dup
0x5a001  ldc.i4.s 0x10
0x5a003  ldstr    aCanbeentityref_0// "@canbeentityreference"
0x5a008  stelem.ref
0x5a009  dup
0x5a00a  ldc.i4.s 0x11
0x5a00c  ldstr    aCanbeparentent_0// "@canbeparententityreference"
0x5a011  stelem.ref
0x5a012  dup
0x5a013  ldc.i4.s 0x12
0x5a015  ldstr    aAccessright_0// "@accessright"
0x5a01a  stelem.ref
0x5a01b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5a020  stloc.s  7
0x5a022  br       loc_5A0BD
0x5a027  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5a02c  ldstr    aInsertInto0123_0// "insert into {0} ({1},{2},{3},{4},{5},{6"...
0x5a031  ldc.i4.s 0xF
0x5a033  newarr   [mscorlib]System.Object
0x5a038  dup
0x5a039  ldc.i4.0
0x5a03a  ldstr    aPrivilegebase// "PrivilegeBase"
0x5a03f  stelem.ref
0x5a040  dup
0x5a041  ldc.i4.1
0x5a042  ldstr    aPrivilegeid_1// "PrivilegeId"
0x5a047  stelem.ref
0x5a048  dup
0x5a049  ldc.i4.2
0x5a04a  ldstr    aName_0// "Name"
0x5a04f  stelem.ref
0x5a050  dup
0x5a051  ldc.i4.3
0x5a052  ldstr    aCanbebasic_1// "CanBeBasic"
0x5a057  stelem.ref
0x5a058  dup
0x5a059  ldc.i4.4
0x5a05a  ldstr    aCanbelocal_1// "CanBeLocal"
0x5a05f  stelem.ref
0x5a060  dup
0x5a061  ldc.i4.5
0x5a062  ldstr    aCanbedeep_1// "CanBeDeep"
0x5a067  stelem.ref
0x5a068  dup
0x5a069  ldc.i4.6
0x5a06a  ldstr    aCanbeglobal_1// "CanBeGlobal"
0x5a06f  stelem.ref
0x5a070  dup
0x5a071  ldc.i4.7
0x5a072  ldstr    aAccessright_1// "AccessRight"
0x5a077  stelem.ref
0x5a078  dup
0x5a079  ldc.i4.8
0x5a07a  ldstr    aPrivilegeid_0// "@privilegeid"
0x5a07f  stelem.ref
0x5a080  dup
0x5a081  ldc.i4.s 9
0x5a083  ldstr    aName_1// "@name"
0x5a088  stelem.ref
0x5a089  dup
0x5a08a  ldc.i4.s 0xA
0x5a08c  ldstr    aCanbebasic_0// "@canbebasic"
0x5a091  stelem.ref
0x5a092  dup
0x5a093  ldc.i4.s 0xB
0x5a095  ldstr    aCanbelocal_0// "@canbelocal"
0x5a09a  stelem.ref
0x5a09b  dup
0x5a09c  ldc.i4.s 0xC
0x5a09e  ldstr    aCanbedeep_0// "@canbedeep"
0x5a0a3  stelem.ref
0x5a0a4  dup
0x5a0a5  ldc.i4.s 0xD
0x5a0a7  ldstr    aCanbeglobal_0// "@canbeglobal"
0x5a0ac  stelem.ref
0x5a0ad  dup
0x5a0ae  ldc.i4.s 0xE
0x5a0b0  ldstr    aAccessright_0// "@accessright"
0x5a0b5  stelem.ref
0x5a0b6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5a0bb  stloc.s  7
0x5a0bd  ldloc.s  5
0x5a0bf  ldloc.s  7
0x5a0c1  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x5a0c6  ldloc.s  5
0x5a0c8  ldc.i4   0x1BB
0x5a0cd  ldstr    aCreateprivileg// "CreatePrivilege"
0x5a0d2  ldstr    aDA1SSrcCoreObj_6// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0x5a0d7  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x5a0dc  pop
0x5a0dd  ldarg.s  0xA
0x5a0df  call     bool [Microsoft.Crm]Microsoft.Crm.CrmCacheUtility::IsInStagingContextAndStagedCacheEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5a0e4  brfalse.s loc_5A11A
0x5a0e6  ldarg.0
0x5a0e7  ldarg.1
0x5a0e8  ldarg.2
0x5a0e9  ldarg.3
0x5a0ea  ldarg.s  4
0x5a0ec  ldarg.s  5
0x5a0ee  ldarg.s  6
0x5a0f0  ldarg.s  7
0x5a0f2  ldarg.s  8
0x5a0f4  ldarg.s  9
0x5a0f6  ldarg.s  0xA
0x5a0f8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag Microsoft.Crm.Metadata.SecurityHelper::CreatePrivilegeDescription(valuetype [mscorlib]System.Guid privilegeId, string privilegeName, bool canbeBasic, bool canbeLocal, bool canbeDeep, bool canbeGlobal, bool canbeEntityReference, bool canbeParentEntityReference, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights accessRight, int32 objectTypeCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x5a0fd  stloc.s  8
0x5a0ff  ldloc.s  8
0x5a101  ldc.i4.1
  ... truncated ...
```
