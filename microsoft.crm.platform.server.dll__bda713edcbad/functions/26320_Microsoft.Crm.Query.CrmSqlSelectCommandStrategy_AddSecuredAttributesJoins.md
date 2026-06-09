# Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::AddSecuredAttributesJoins

- ea: `0x26320`
- end: `0x264b4`
- name: `Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::AddSecuredAttributesJoins`
- size: `404`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x18590`
- `0x185d0`
- `0x187a0`
- `0x23c50`
- `0x23e40`
- `0x23e60`
- `0x23e90`
- `0x23fd0`
- `0x26320`
- `0x26570`
- `0x27d30`
- `0x2b4e0`
- `0x2b4f0`
- `0x2b670`
- `0x2b690`
- `0x2b6d0`
- `0x2b770`
- `0x2b7e0`

## string_xrefs

- `0x26348`: `Secured attribute joins were already added for this EntityExpression with table alias {0}`
- `0x2645e`: `\ncase when {0}.ReadAccess is null then 0 else {0}.ReadAccess end as '{1}'`

## pseudocode

```c

```

## disassembly

```asm
0x26320  ldarg.1
0x26321  ldstr    aEntity_0// "entity"
0x26326  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2632b  ldarg.1
0x2632c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata> Microsoft.Crm.Query.EntityExpression::get_SecuredAttributeAccessAliases()
0x26331  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::Clear()
0x26336  ldarg.0
0x26337  call     instance class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_SecuredAttributeJoins()
0x2633c  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x26341  brfalse.s loc_2636C
0x26343  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26348  ldstr    aSecuredAttribu// "Secured attribute joins were already ad"...
0x2634d  ldc.i4.1
0x2634e  newarr   [mscorlib]System.Object
0x26353  dup
0x26354  ldc.i4.0
0x26355  ldarg.1
0x26356  callvirt instance string Microsoft.Crm.Query.EntityExpression::get_TableAlias()
0x2635b  stelem.ref
0x2635c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26361  ldc.i4   0x80041101
0x26366  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2636b  throw
0x2636c  ldarg.0
0x2636d  call     instance class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollectionWrapper Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_SecuredAttributesWrapper()
0x26372  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollection> Microsoft.Crm.Query.SecuredAttributeJoinInfoCollectionWrapper::get_SecuredAttributes()
0x26377  ldarg.0
0x26378  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_CallerId()
0x2637d  ldarg.0
0x2637e  call     instance class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_SecuredAttributeJoins()
0x26383  ldarg.0
0x26384  ldfld    class Microsoft.Crm.Query.QueryParameterManager Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_parameters
0x26389  call     void Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::AddSecuredAttributesJoins(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollection> securedAttributes, valuetype [mscorlib]System.Guid callerId, class [mscorlib]System.Text.StringBuilder sb, class Microsoft.Crm.Query.QueryParameterManager queryParameters)
0x2638e  ldarg.0
0x2638f  call     instance class Microsoft.Crm.Query.FromClauseInfo Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_FromClause()
0x26394  callvirt instance string Microsoft.Crm.Query.FromClauseInfo::get_FromClauseFormat()
0x26399  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x2639e  stloc.0
0x2639f  ldarg.0
0x263a0  call     instance class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollectionWrapper Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_SecuredAttributesWrapper()
0x263a5  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollection> Microsoft.Crm.Query.SecuredAttributeJoinInfoCollectionWrapper::get_SecuredAttributes()
0x263aa  ldarg.0
0x263ab  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_CallerId()
0x263b0  ldloc.0
0x263b1  ldarg.0
0x263b2  ldfld    class Microsoft.Crm.Query.QueryParameterManager Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_parameters
0x263b7  call     void Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::AddSecuredAttributesJoins(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollection> securedAttributes, valuetype [mscorlib]System.Guid callerId, class [mscorlib]System.Text.StringBuilder sb, class Microsoft.Crm.Query.QueryParameterManager queryParameters)
0x263bc  ldarg.0
0x263bd  call     instance class Microsoft.Crm.Query.FromClauseInfo Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_FromClause()
0x263c2  ldloc.0
0x263c3  callvirt instance string [mscorlib]System.Object::ToString()
0x263c8  callvirt instance void Microsoft.Crm.Query.FromClauseInfo::set_FromClauseFormat(string value)
0x263cd  ldarg.1
0x263ce  callvirt instance bool Microsoft.Crm.Query.EntityExpression::get_HasAggregates()
0x263d3  brtrue   loc_264B3
0x263d8  ldarg.0
0x263d9  call     instance class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollectionWrapper Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_SecuredAttributesWrapper()
0x263de  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollection> Microsoft.Crm.Query.SecuredAttributeJoinInfoCollectionWrapper::get_SecuredAttributes()
0x263e3  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollection>::GetEnumerator()
0x263e8  stloc.1
0x263e9  br       loc_26497
0x263ee  ldloca.s 1
0x263f0  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollection>::get_Current()
0x263f5  stloc.2
0x263f6  ldloca.s 2
0x263f8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollection>::get_Key()
0x263fd  stloc.3
0x263fe  ldarg.0
0x263ff  call     instance class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollectionWrapper Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_SecuredAttributesWrapper()
0x26404  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollection> Microsoft.Crm.Query.SecuredAttributeJoinInfoCollectionWrapper::get_SecuredAttributes()
0x26409  ldloc.3
0x2640a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollection>::get_Item(void)
0x2640f  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.SecuredAttributeJoinInfo>::GetEnumerator()
0x26414  stloc.s  4
0x26416  br.s     loc_2647E
0x26418  ldloca.s 4
0x2641a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Query.SecuredAttributeJoinInfo>::get_Current()
0x2641f  stloc.s  5
0x26421  ldloc.s  5
0x26423  callvirt instance bool Microsoft.Crm.Query.SecuredAttributeJoinInfo::get_FilterWholeRow()
0x26428  brtrue.s loc_2647E
0x2642a  ldloc.s  5
0x2642c  callvirt instance string Microsoft.Crm.Query.SecuredAttributeJoinInfo::get_AliasForReadAccessBit()
0x26431  stloc.s  6
0x26433  ldarg.1
0x26434  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata> Microsoft.Crm.Query.EntityExpression::get_SecuredAttributeAccessAliases()
0x26439  ldloc.s  6
0x2643b  ldloc.s  5
0x2643d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.SecuredAttributeJoinInfo::get_AttributeMetadata()
0x26442  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::Add(var<u1>, !!T0)
0x26447  ldarg.0
0x26448  ldarg.0
0x26449  call     instance class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_SelectClause()
0x2644e  callvirt instance void Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::AddSeparator(class [mscorlib]System.Text.StringBuilder sqlString)
0x26453  ldarg.0
0x26454  call     instance class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_SelectClause()
0x26459  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2645e  ldstr    aCaseWhen0Reada// "\r\ncase when {0}.ReadAccess is null th"...
0x26463  ldc.i4.2
0x26464  newarr   [mscorlib]System.Object
0x26469  dup
0x2646a  ldc.i4.0
0x2646b  ldloc.s  5
0x2646d  callvirt instance string Microsoft.Crm.Query.SecuredAttributeJoinInfo::get_PoaaTableAlias()
0x26472  stelem.ref
0x26473  dup
0x26474  ldc.i4.1
0x26475  ldloc.s  6
0x26477  stelem.ref
0x26478  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x2647d  pop
0x2647e  ldloca.s 4
0x26480  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Query.SecuredAttributeJoinInfo>::MoveNext()
0x26485  brtrue.s loc_26418
0x26487  leave.s  loc_26497
0x26489  ldloca.s 4
0x2648b  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Query.SecuredAttributeJoinInfo>
0x26491  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26496  endfinally
0x26497  ldloca.s 1
0x26499  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollection>::MoveNext()
0x2649e  brtrue   loc_263EE
0x264a3  leave.s  loc_264B3
0x264a5  ldloca.s 1
0x264a7  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.Crm.Query.SecuredAttributeJoinInfoCollection>
0x264ad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x264b2  endfinally
0x264b3  ret
```
