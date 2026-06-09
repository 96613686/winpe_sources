# Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GetHierarchicalCommonTableExpression

- ea: `0x25a80`
- end: `0x25ece`
- name: `Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GetHierarchicalCommonTableExpression`
- size: `1102`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1e050`
- `0x25a10`

## callees

- `0x23c10`
- `0x25a80`
- `0x25ed0`
- `0x25ee0`
- `0x25ef0`
- `0x25f10`
- `0x27e60`
- `0x288a0`
- `0x2cd10`
- `0x2d050`
- `0x66b10`

## string_xrefs

- `0x25b91`: `,\nISNULL((SELECT ReadAccess FROM fn_UserSharedAttributeAccess({0}, {1}, {2}) poaa WHERE poaa.ObjectId = "{3}".{4}), 0)`
- `0x25c7c`: `\nAND "{3}".{4} IN (SELECT ObjectId FROM fn_UserSharedAttributeAccess({0}, {1}, {2}) WHERE ReadAccess = 1)`

## pseudocode

```c

```

## disassembly

```asm
0x25a80  ldarg.1
0x25a81  ldstr    aParametername// "parameterName"
0x25a86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x25a8b  ldarg.3
0x25a8c  ldstr    aEntityplatform// "entityPlatformName"
0x25a91  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x25a96  ldarg.s  4
0x25a98  ldstr    aParametername// "parameterName"
0x25a9d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x25aa2  ldarg.0
0x25aa3  ldarg.1
0x25aa4  callvirt instance void Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::ValidateHierarchicalOperatorParameterName(string parameterName)
0x25aa9  ldarg.0
0x25aaa  ldarg.3
0x25aab  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GetHierarchicalRelationship(string entityPlaformName)
0x25ab0  stloc.0
0x25ab1  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x25ab6  stloc.1
0x25ab7  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x25abc  stloc.2
0x25abd  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x25ac2  stloc.3
0x25ac3  ldarg.0
0x25ac4  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_context
0x25ac9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x25ace  ldarg.3
0x25acf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x25ad4  stloc.s  4
0x25ad6  ldloc.0
0x25ad7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x25adc  stloc.s  5
0x25ade  ldloc.s  5
0x25ae0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x25ae5  stloc.s  6
0x25ae7  ldarg.0
0x25ae8  ldloc.0
0x25ae9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x25aee  callvirt instance string Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GetAttributeColumnName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute)
0x25af3  stloc.s  6
0x25af5  leave.s  loc_25AFA
0x25af7  pop
0x25af8  leave.s  loc_25AFA
0x25afa  call     string Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GetCustomFieldLevelAlias()
0x25aff  stloc.s  7
0x25b01  ldloc.s  4
0x25b03  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_UniqueIdAttribute()
0x25b08  stloc.s  8
0x25b0a  ldarg.0
0x25b0b  ldloc.s  8
0x25b0d  callvirt instance string Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GetAttributeColumnName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute)
0x25b12  stloc.s  9
0x25b14  ldloc.s  4
0x25b16  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x25b1b  stloc.s  0xA
0x25b1d  ldstr    aSelect0From12W// "SELECT {0} FROM {1} \"{2}\" WHERE \"{2}"...
0x25b22  stloc.s  0xB
0x25b24  ldstr    aIsparentfields// "IsParentFieldSecure"
0x25b29  stloc.s  0xC
0x25b2b  ldsfld   string [mscorlib]System.String::Empty
0x25b30  stloc.s  0xD
0x25b32  ldsfld   string [mscorlib]System.String::Empty
0x25b37  stloc.s  0xE
0x25b39  ldsfld   string [mscorlib]System.String::Empty
0x25b3e  stloc.s  0xF
0x25b40  ldsfld   string [mscorlib]System.String::Empty
0x25b45  stloc.s  0x10
0x25b47  ldsfld   string [mscorlib]System.String::Empty
0x25b4c  stloc.s  0x11
0x25b4e  ldloc.s  5
0x25b50  ldarg.0
0x25b51  callvirt instance valuetype Microsoft.Crm.Query.SecuredAttributeRetrieveBehavior Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_SecuredAttributeRetrieveBehavior()
0x25b56  ldarg.0
0x25b57  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_context
0x25b5c  call     bool Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::NeedFieldLevelSecurityJoin(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype Microsoft.Crm.Query.SecuredAttributeRetrieveBehavior behavior, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x25b61  stloc.s  0x12
0x25b63  ldarg.2
0x25b64  ldc.i4.s 0x4B
0x25b66  sub
0x25b67  ldc.i4.2
0x25b68  ble.un   loc_25C62
0x25b6d  ldarg.2
0x25b6e  ldc.i4.s 0x4E
0x25b70  sub
0x25b71  ldc.i4.1
0x25b72  bgt.un   loc_25D0B
0x25b77  ldstr    aSelect0From123// "SELECT {0} FROM {1} \"{2}\",\"{3}\" \"{"...
0x25b7c  stloc.s  0xD
0x25b7e  ldstr    a1_0// "-1"
0x25b83  stloc.s  0xE
0x25b85  ldloc.s  0x12
0x25b87  brfalse  loc_25D0B
0x25b8c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25b91  ldstr    aIsnullSelectRe// ",\nISNULL((SELECT ReadAccess FROM fn_Us"...
0x25b96  ldc.i4.5
0x25b97  newarr   [mscorlib]System.Object
0x25b9c  dup
0x25b9d  ldc.i4.0
0x25b9e  ldarg.0
0x25b9f  ldfld    class Microsoft.Crm.Query.QueryParameterManager Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_parameters
0x25ba4  ldstr    aFlssecuredsyst// "flsSecuredSystemUserId"
0x25ba9  ldarg.0
0x25baa  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_context
0x25baf  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x25bb4  box      [mscorlib]System.Guid
0x25bb9  ldc.i4.0
0x25bba  newobj   instance void Microsoft.Crm.Query.ParameterValueAndType::.ctor(object value, bool isNVarCharMax)
0x25bbf  callvirt instance string Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string baseParameterName, class Microsoft.Crm.Query.ParameterValueAndType parameterData)
0x25bc4  stelem.ref
0x25bc5  dup
0x25bc6  ldc.i4.1
0x25bc7  ldarg.0
0x25bc8  ldfld    class Microsoft.Crm.Query.QueryParameterManager Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_parameters
0x25bcd  ldstr    aHierarchicalat// "hierarchicalAttributeId"
0x25bd2  ldloc.s  5
0x25bd4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x25bd9  box      [mscorlib]System.Guid
0x25bde  ldc.i4.0
0x25bdf  newobj   instance void Microsoft.Crm.Query.ParameterValueAndType::.ctor(object value, bool isNVarCharMax)
0x25be4  callvirt instance string Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string baseParameterName, class Microsoft.Crm.Query.ParameterValueAndType parameterData)
0x25be9  stelem.ref
0x25bea  dup
0x25beb  ldc.i4.2
0x25bec  ldarg.0
0x25bed  ldfld    class Microsoft.Crm.Query.QueryParameterManager Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_parameters
0x25bf2  ldstr    aSecuredattribu// "securedAttributeObjectTypeCode"
0x25bf7  ldloc.s  4
0x25bf9  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x25bfe  box      [mscorlib]System.Int32
0x25c03  ldc.i4.0
0x25c04  newobj   instance void Microsoft.Crm.Query.ParameterValueAndType::.ctor(object value, bool isNVarCharMax)
0x25c09  callvirt instance string Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string baseParameterName, class Microsoft.Crm.Query.ParameterValueAndType parameterData)
0x25c0e  stelem.ref
0x25c0f  dup
0x25c10  ldc.i4.3
0x25c11  ldloc.s  0xA
0x25c13  stelem.ref
0x25c14  dup
0x25c15  ldc.i4.4
0x25c16  ldloc.s  9
0x25c18  stelem.ref
0x25c19  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25c1e  stloc.s  0xF
0x25c20  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25c25  ldstr    a0_9// ", {0}"
0x25c2a  ldc.i4.1
0x25c2b  newarr   [mscorlib]System.Object
0x25c30  dup
0x25c31  ldc.i4.0
0x25c32  ldloc.s  0xC
0x25c34  stelem.ref
0x25c35  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25c3a  stloc.s  0x10
0x25c3c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25c41  ldstr    aAnd011// "\n AND \"{0}\".{1} = 1"
0x25c46  ldc.i4.2
0x25c47  newarr   [mscorlib]System.Object
0x25c4c  dup
0x25c4d  ldc.i4.0
0x25c4e  ldarg.s  4
0x25c50  stelem.ref
0x25c51  dup
0x25c52  ldc.i4.1
0x25c53  ldloc.s  0xC
0x25c55  stelem.ref
0x25c56  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25c5b  stloc.s  0x11
0x25c5d  br       loc_25D0B
0x25c62  ldstr    aSelect0From123_0// "SELECT {0} FROM {1} \"{2}\",\"{3}\" \"{"...
0x25c67  stloc.s  0xD
0x25c69  ldstr    a1_1// "+1"
0x25c6e  stloc.s  0xE
0x25c70  ldloc.s  0x12
0x25c72  brfalse  loc_25D0B
0x25c77  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25c7c  ldstr    aAnd34InSelectO// "\nAND \"{3}\".{4} IN (SELECT ObjectId F"...
0x25c81  ldc.i4.5
0x25c82  newarr   [mscorlib]System.Object
0x25c87  dup
0x25c88  ldc.i4.0
0x25c89  ldarg.0
0x25c8a  ldfld    class Microsoft.Crm.Query.QueryParameterManager Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_parameters
0x25c8f  ldstr    aFlssecuredsyst// "flsSecuredSystemUserId"
0x25c94  ldarg.0
0x25c95  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_context
0x25c9a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x25c9f  box      [mscorlib]System.Guid
0x25ca4  ldc.i4.0
0x25ca5  newobj   instance void Microsoft.Crm.Query.ParameterValueAndType::.ctor(object value, bool isNVarCharMax)
0x25caa  callvirt instance string Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string baseParameterName, class Microsoft.Crm.Query.ParameterValueAndType parameterData)
0x25caf  stelem.ref
0x25cb0  dup
0x25cb1  ldc.i4.1
0x25cb2  ldarg.0
0x25cb3  ldfld    class Microsoft.Crm.Query.QueryParameterManager Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_parameters
0x25cb8  ldstr    aHierarchicalat// "hierarchicalAttributeId"
0x25cbd  ldloc.s  5
0x25cbf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x25cc4  box      [mscorlib]System.Guid
0x25cc9  ldc.i4.0
0x25cca  newobj   instance void Microsoft.Crm.Query.ParameterValueAndType::.ctor(object value, bool isNVarCharMax)
0x25ccf  callvirt instance string Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string baseParameterName, class Microsoft.Crm.Query.ParameterValueAndType parameterData)
0x25cd4  stelem.ref
0x25cd5  dup
0x25cd6  ldc.i4.2
0x25cd7  ldarg.0
0x25cd8  ldfld    class Microsoft.Crm.Query.QueryParameterManager Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_parameters
0x25cdd  ldstr    aSecuredattribu// "securedAttributeObjectTypeCode"
0x25ce2  ldloc.s  4
0x25ce4  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x25ce9  box      [mscorlib]System.Int32
0x25cee  ldc.i4.0
0x25cef  newobj   instance void Microsoft.Crm.Query.ParameterValueAndType::.ctor(object value, bool isNVarCharMax)
0x25cf4  callvirt instance string Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string baseParameterName, class Microsoft.Crm.Query.ParameterValueAndType parameterData)
0x25cf9  stelem.ref
0x25cfa  dup
0x25cfb  ldc.i4.3
0x25cfc  ldloc.s  0xA
0x25cfe  stelem.ref
0x25cff  dup
0x25d00  ldc.i4.4
0x25d01  ldloc.s  9
0x25d03  stelem.ref
0x25d04  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25d09  stloc.s  0x11
0x25d0b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x25d10  stloc.s  0x13
0x25d12  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x25d17  stloc.s  0x14
0x25d19  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x25d1e  stloc.s  0x15
0x25d20  ldloc.s  0x13
0x25d22  ldc.i4.s 9
0x25d24  newarr   [mscorlib]System.String
0x25d29  dup
0x25d2a  ldc.i4.0
0x25d2b  ldstr    a0_10// "0, \""
0x25d30  stelem.ref
0x25d31  dup
0x25d32  ldc.i4.1
0x25d33  ldloc.s  0xA
0x25d35  stelem.ref
0x25d36  dup
0x25d37  ldc.i4.2
0x25d38  ldstr    asc_D3176// "\"."
0x25d3d  stelem.ref
0x25d3e  dup
0x25d3f  ldc.i4.3
0x25d40  ldloc.s  9
0x25d42  stelem.ref
0x25d43  dup
0x25d44  ldc.i4.4
0x25d45  ldstr    asc_D317C// ", \""
0x25d4a  stelem.ref
0x25d4b  dup
0x25d4c  ldc.i4.5
0x25d4d  ldloc.s  0xA
0x25d4f  stelem.ref
0x25d50  dup
0x25d51  ldc.i4.6
0x25d52  ldstr    asc_D3176// "\"."
0x25d57  stelem.ref
0x25d58  dup
0x25d59  ldc.i4.7
0x25d5a  ldloc.s  6
0x25d5c  stelem.ref
0x25d5d  dup
0x25d5e  ldc.i4.8
0x25d5f  ldloc.s  0xF
0x25d61  stelem.ref
0x25d62  call     string [mscorlib]System.String::Concat(string[])
0x25d67  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x25d6c  pop
0x25d6d  ldloc.s  0x14
0x25d6f  ldc.i4.s 0xB
0x25d71  newarr   [mscorlib]System.String
0x25d76  dup
0x25d77  ldc.i4.0
0x25d78  ldloc.s  7
0x25d7a  stelem.ref
0x25d7b  dup
0x25d7c  ldc.i4.1
0x25d7d  ldloc.s  0xE
0x25d7f  stelem.ref
0x25d80  dup
0x25d81  ldc.i4.2
0x25d82  ldstr    asc_D317C// ", \""
0x25d87  stelem.ref
0x25d88  dup
0x25d89  ldc.i4.3
0x25d8a  ldloc.s  0xA
0x25d8c  stelem.ref
0x25d8d  dup
0x25d8e  ldc.i4.4
0x25d8f  ldstr    asc_D3176// "\"."
0x25d94  stelem.ref
0x25d95  dup
0x25d96  ldc.i4.5
0x25d97  ldloc.s  9
0x25d99  stelem.ref
0x25d9a  dup
  ... truncated ...
```
