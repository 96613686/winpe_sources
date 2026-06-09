# Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::AddCaseWhenClauseForAssociatedSecuredAttribute

- ea: `0x26a00`
- end: `0x26bf2`
- name: `Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::AddCaseWhenClauseForAssociatedSecuredAttribute`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x26970`

## callees

- `0x26a00`
- `0x2b690`
- `0x2b740`
- `0x2b760`
- `0x2b910`
- `0x2cd10`
- `0x2d050`

## string_xrefs

- `0x26a40`: `dbo.fn_UserSharedAttributeAccessForObject({0},{1},"{2}".{3},{4}) = 1`
- `0x26acd`: `{0}.ReadAccess = 1`

## pseudocode

```c

```

## disassembly

```asm
0x26a00  ldarg.s  0xC
0x26a02  ldarg.1
0x26a03  ldarg.s  6
0x26a05  ldarg.3
0x26a06  callvirt instance class Microsoft.Crm.Query.SecuredAttributeJoinInfo Microsoft.Crm.Query.SecuredAttributeJoinInfoCollectionWrapper::FindOrCreateSecuredAttributeJoinInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata joinAttribute, string tableAlias, valuetype Microsoft.Crm.Query.SecuredAttributeJoinType joinType)
0x26a0b  stloc.0
0x26a0c  ldloc.0
0x26a0d  ldarg.1
0x26a0e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAssociatedSecuredAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AssociatedSecuredAttributeInfo()
0x26a13  callvirt instance void Microsoft.Crm.Query.SecuredAttributeJoinInfo::set_AssociatedSecuredAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAssociatedSecuredAttributeInfo value)
0x26a18  ldloc.0
0x26a19  ldarg.0
0x26a1a  callvirt instance void Microsoft.Crm.Query.SecuredAttributeJoinInfo::set_IndirectlySecuredAttributeMetadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata value)
0x26a1f  ldarg.s  4
0x26a21  ldind.ref
0x26a22  ldarg.1
0x26a23  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x26a28  ldloc.0
0x26a29  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Query.SecuredAttributeJoinInfo>::Add(var<u1>, !!T0)
0x26a2e  ldarg.s  8
0x26a30  ldarg.s  9
0x26a32  and
0x26a33  ldarg.s  5
0x26a35  or
0x26a36  brfalse  loc_26AC8
0x26a3b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26a40  ldstr    aDboFnUsershare// "dbo.fn_UserSharedAttributeAccessForObje"...
0x26a45  ldc.i4.5
0x26a46  newarr   [mscorlib]System.Object
0x26a4b  dup
0x26a4c  ldc.i4.0
0x26a4d  ldarg.s  0xA
0x26a4f  ldstr    aFlssecuredsyst// "flsSecuredSystemUserId"
0x26a54  ldarg.s  0xB
0x26a56  box      [mscorlib]System.Guid
0x26a5b  ldc.i4.0
0x26a5c  newobj   instance void Microsoft.Crm.Query.ParameterValueAndType::.ctor(object value, bool isNVarCharMax)
0x26a61  callvirt instance string Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string baseParameterName, class Microsoft.Crm.Query.ParameterValueAndType parameterData)
0x26a66  stelem.ref
0x26a67  dup
0x26a68  ldc.i4.1
0x26a69  ldarg.s  0xA
0x26a6b  ldstr    aSecuredattribu_1// "securedAttributeId"
0x26a70  ldarg.1
0x26a71  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x26a76  box      [mscorlib]System.Guid
0x26a7b  ldc.i4.0
0x26a7c  newobj   instance void Microsoft.Crm.Query.ParameterValueAndType::.ctor(object value, bool isNVarCharMax)
0x26a81  callvirt instance string Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string baseParameterName, class Microsoft.Crm.Query.ParameterValueAndType parameterData)
0x26a86  stelem.ref
0x26a87  dup
0x26a88  ldc.i4.2
0x26a89  ldarg.s  6
0x26a8b  stelem.ref
0x26a8c  dup
0x26a8d  ldc.i4.3
0x26a8e  ldarg.1
0x26a8f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAssociatedSecuredAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AssociatedSecuredAttributeInfo()
0x26a94  ldarg.0
0x26a95  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAssociatedSecuredAttributeInfo::JoinConditionOnObjectIdAttributeName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x26a9a  stelem.ref
0x26a9b  dup
0x26a9c  ldc.i4.4
0x26a9d  ldarg.s  0xA
0x26a9f  ldstr    aSecuredattribu// "securedAttributeObjectTypeCode"
0x26aa4  ldarg.1
0x26aa5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x26aaa  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x26aaf  box      [mscorlib]System.Int32
0x26ab4  ldc.i4.0
0x26ab5  newobj   instance void Microsoft.Crm.Query.ParameterValueAndType::.ctor(object value, bool isNVarCharMax)
0x26aba  callvirt instance string Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string baseParameterName, class Microsoft.Crm.Query.ParameterValueAndType parameterData)
0x26abf  stelem.ref
0x26ac0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26ac5  stloc.1
0x26ac6  br.s     loc_26AE7
0x26ac8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26acd  ldstr    a0Readaccess1// "{0}.ReadAccess = 1"
0x26ad2  ldc.i4.1
0x26ad3  newarr   [mscorlib]System.Object
0x26ad8  dup
0x26ad9  ldc.i4.0
0x26ada  ldloc.0
0x26adb  callvirt instance string Microsoft.Crm.Query.SecuredAttributeJoinInfo::get_PoaaTableAlias()
0x26ae0  stelem.ref
0x26ae1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26ae6  stloc.1
0x26ae7  ldarg.1
0x26ae8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAssociatedSecuredAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AssociatedSecuredAttributeInfo()
0x26aed  stloc.2
0x26aee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26af3  ldstr    a012_0// "\"{0}\".{1}={2}"
0x26af8  ldc.i4.3
0x26af9  newarr   [mscorlib]System.Object
0x26afe  dup
0x26aff  ldc.i4.0
0x26b00  ldarg.s  6
0x26b02  stelem.ref
0x26b03  dup
0x26b04  ldc.i4.1
0x26b05  ldloc.2
0x26b06  ldarg.0
0x26b07  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAssociatedSecuredAttributeInfo::ConditionOneAttributeName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x26b0c  stelem.ref
0x26b0d  dup
0x26b0e  ldc.i4.2
0x26b0f  ldarg.s  0xA
0x26b11  brfalse.s loc_26B33
0x26b13  ldarg.s  0xA
0x26b15  ldstr    aFlsassociateds// "flsAssociatedSecuredCondition"
0x26b1a  ldloc.2
0x26b1b  ldarg.0
0x26b1c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAssociatedSecuredAttributeInfo::ConditionOneValue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x26b21  box      [mscorlib]System.Int32
0x26b26  ldc.i4.0
0x26b27  newobj   instance void Microsoft.Crm.Query.ParameterValueAndType::.ctor(object value, bool isNVarCharMax)
0x26b2c  callvirt instance string Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string baseParameterName, class Microsoft.Crm.Query.ParameterValueAndType parameterData)
0x26b31  br.s     loc_26B48
0x26b33  ldloc.2
0x26b34  ldarg.0
0x26b35  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAssociatedSecuredAttributeInfo::ConditionOneValue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x26b3a  stloc.s  5
0x26b3c  ldloca.s 5
0x26b3e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26b43  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x26b48  stelem.ref
0x26b49  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26b4e  stloc.3
0x26b4f  ldloc.2
0x26b50  ldarg.0
0x26b51  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAssociatedSecuredAttributeInfo::ConditionTwoAttributeName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x26b56  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x26b5b  brtrue.s loc_26BC4
0x26b5d  ldloc.3
0x26b5e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26b63  ldstr    aAnd012_0// " and \"{0}\".{1}={2}"
0x26b68  ldc.i4.3
0x26b69  newarr   [mscorlib]System.Object
0x26b6e  dup
0x26b6f  ldc.i4.0
0x26b70  ldarg.s  6
0x26b72  stelem.ref
0x26b73  dup
0x26b74  ldc.i4.1
0x26b75  ldloc.2
0x26b76  ldarg.0
0x26b77  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAssociatedSecuredAttributeInfo::ConditionTwoAttributeName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x26b7c  stelem.ref
0x26b7d  dup
0x26b7e  ldc.i4.2
0x26b7f  ldarg.s  0xA
0x26b81  brfalse.s loc_26BA3
0x26b83  ldarg.s  0xA
0x26b85  ldstr    aFlsassociateds_0// "flsAssociatedSecuredSecondCondition"
0x26b8a  ldloc.2
0x26b8b  ldarg.0
0x26b8c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAssociatedSecuredAttributeInfo::ConditionTwoValue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x26b91  box      [mscorlib]System.Int32
0x26b96  ldc.i4.0
0x26b97  newobj   instance void Microsoft.Crm.Query.ParameterValueAndType::.ctor(object value, bool isNVarCharMax)
0x26b9c  callvirt instance string Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string baseParameterName, class Microsoft.Crm.Query.ParameterValueAndType parameterData)
0x26ba1  br.s     loc_26BB8
0x26ba3  ldloc.2
0x26ba4  ldarg.0
0x26ba5  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAssociatedSecuredAttributeInfo::ConditionTwoValue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x26baa  stloc.s  5
0x26bac  ldloca.s 5
0x26bae  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26bb3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x26bb8  stelem.ref
0x26bb9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26bbe  call     string [mscorlib]System.String::Concat(string, string)
0x26bc3  stloc.3
0x26bc4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26bc9  ldstr    aWhen0ThenCaseW// "\twhen {0} \r\n\t\tthen case when {1} t"...
0x26bce  ldc.i4.3
0x26bcf  newarr   [mscorlib]System.Object
0x26bd4  dup
0x26bd5  ldc.i4.0
0x26bd6  ldloc.3
0x26bd7  stelem.ref
0x26bd8  dup
0x26bd9  ldc.i4.1
0x26bda  ldloc.1
0x26bdb  stelem.ref
0x26bdc  dup
0x26bdd  ldc.i4.2
0x26bde  ldarg.2
0x26bdf  stelem.ref
0x26be0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26be5  stloc.s  4
0x26be7  ldarg.s  7
0x26be9  ldloc.s  4
0x26beb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x26bf0  pop
0x26bf1  ret
```
