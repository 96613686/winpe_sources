# Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GetDirectlySecuredFieldSql

- ea: `0x26c00`
- end: `0x26d33`
- name: `Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GetDirectlySecuredFieldSql`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x268d0`

## callees

- `0x13590`
- `0x26c00`
- `0x2b690`
- `0x2b6d0`
- `0x2b910`
- `0x2cd10`
- `0x2d050`

## string_xrefs

- `0x26c39`: `dbo.fn_UserSharedAttributeAccessForObject({0},{1},"{2}".{3},{4}) = 1`
- `0x26ce1`: `{0}.ReadAccess = 1`

## pseudocode

```c

```

## disassembly

```asm
0x26c00  ldarg.s  0xA
0x26c02  ldarga.s 4
0x26c04  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Value()
0x26c09  ldarga.s 4
0x26c0b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Key()
0x26c10  ldarg.1
0x26c11  callvirt instance class Microsoft.Crm.Query.SecuredAttributeJoinInfo Microsoft.Crm.Query.SecuredAttributeJoinInfoCollectionWrapper::FindOrCreateSecuredAttributeJoinInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata joinAttribute, string tableAlias, valuetype Microsoft.Crm.Query.SecuredAttributeJoinType joinType)
0x26c16  stloc.0
0x26c17  ldarg.s  7
0x26c19  brfalse.s loc_26C28
0x26c1b  ldarg.s  7
0x26c1d  ldloc.0
0x26c1e  callvirt instance string Microsoft.Crm.Query.SecuredAttributeJoinInfo::get_AliasForReadAccessBit()
0x26c23  callvirt instance void Microsoft.Crm.Query.AttributeExpression::set_SharedAccessColumnAlias(string value)
0x26c28  ldarg.s  5
0x26c2a  ldarg.s  6
0x26c2c  and
0x26c2d  ldarg.3
0x26c2e  or
0x26c2f  brfalse  loc_26CDC
0x26c34  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26c39  ldstr    aDboFnUsershare// "dbo.fn_UserSharedAttributeAccessForObje"...
0x26c3e  ldc.i4.5
0x26c3f  newarr   [mscorlib]System.Object
0x26c44  dup
0x26c45  ldc.i4.0
0x26c46  ldarg.s  8
0x26c48  ldstr    aFlssecuredsyst// "flsSecuredSystemUserId"
0x26c4d  ldarg.s  9
0x26c4f  box      [mscorlib]System.Guid
0x26c54  ldc.i4.0
0x26c55  newobj   instance void Microsoft.Crm.Query.ParameterValueAndType::.ctor(object value, bool isNVarCharMax)
0x26c5a  callvirt instance string Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string baseParameterName, class Microsoft.Crm.Query.ParameterValueAndType parameterData)
0x26c5f  stelem.ref
0x26c60  dup
0x26c61  ldc.i4.1
0x26c62  ldarg.s  8
0x26c64  ldstr    aSecuredattribu_1// "securedAttributeId"
0x26c69  ldarga.s 4
0x26c6b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Value()
0x26c70  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x26c75  box      [mscorlib]System.Guid
0x26c7a  ldc.i4.0
0x26c7b  newobj   instance void Microsoft.Crm.Query.ParameterValueAndType::.ctor(object value, bool isNVarCharMax)
0x26c80  callvirt instance string Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string baseParameterName, class Microsoft.Crm.Query.ParameterValueAndType parameterData)
0x26c85  stelem.ref
0x26c86  dup
0x26c87  ldc.i4.2
0x26c88  ldarga.s 4
0x26c8a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Key()
0x26c8f  stelem.ref
0x26c90  dup
0x26c91  ldc.i4.3
0x26c92  ldarga.s 4
0x26c94  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Value()
0x26c99  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x26c9e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x26ca3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x26ca8  stelem.ref
0x26ca9  dup
0x26caa  ldc.i4.4
0x26cab  ldarg.s  8
0x26cad  ldstr    aSecuredattribu// "securedAttributeObjectTypeCode"
0x26cb2  ldarga.s 4
0x26cb4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Value()
0x26cb9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x26cbe  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x26cc3  box      [mscorlib]System.Int32
0x26cc8  ldc.i4.0
0x26cc9  newobj   instance void Microsoft.Crm.Query.ParameterValueAndType::.ctor(object value, bool isNVarCharMax)
0x26cce  callvirt instance string Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string baseParameterName, class Microsoft.Crm.Query.ParameterValueAndType parameterData)
0x26cd3  stelem.ref
0x26cd4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26cd9  stloc.1
0x26cda  br.s     loc_26CFB
0x26cdc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26ce1  ldstr    a0Readaccess1// "{0}.ReadAccess = 1"
0x26ce6  ldc.i4.1
0x26ce7  newarr   [mscorlib]System.Object
0x26cec  dup
0x26ced  ldc.i4.0
0x26cee  ldloc.0
0x26cef  callvirt instance string Microsoft.Crm.Query.SecuredAttributeJoinInfo::get_PoaaTableAlias()
0x26cf4  stelem.ref
0x26cf5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26cfa  stloc.1
0x26cfb  ldarg.2
0x26cfc  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Query.SecuredAttributeJoinInfo>::.ctor()
0x26d01  dup
0x26d02  ldarga.s 4
0x26d04  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Value()
0x26d09  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x26d0e  ldloc.0
0x26d0f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Query.SecuredAttributeJoinInfo>::Add(var<u1>, !!T0)
0x26d14  stind.ref
0x26d15  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26d1a  ldstr    aCaseWhen0Then1// "case when {0} then {1} else null end"
0x26d1f  ldc.i4.2
0x26d20  newarr   [mscorlib]System.Object
0x26d25  dup
0x26d26  ldc.i4.0
0x26d27  ldloc.1
0x26d28  stelem.ref
0x26d29  dup
0x26d2a  ldc.i4.1
0x26d2b  ldarg.0
0x26d2c  stelem.ref
0x26d2d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26d32  ret
```
