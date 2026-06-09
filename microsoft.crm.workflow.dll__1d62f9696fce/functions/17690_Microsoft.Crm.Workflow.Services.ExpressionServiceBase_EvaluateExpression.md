# Microsoft.Crm.Workflow.Services.ExpressionServiceBase::EvaluateExpression

- ea: `0x17690`
- end: `0x17dd6`
- name: `Microsoft.Crm.Workflow.Services.ExpressionServiceBase::EvaluateExpression`
- size: `1862`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x6a00`
- `0x6a20`
- `0xe690`
- `0xe6b0`
- `0xe6f0`
- `0xee50`
- `0x14770`
- `0x17600`
- `0x17690`
- `0x17de0`
- `0x17e50`
- `0x17ef0`
- `0x17f20`
- `0x18230`
- `0x18640`
- `0x18670`
- `0x186b0`

## string_xrefs

- `0x17846`: `Expect the target type of fetch xml to be string`

## pseudocode

```c

```

## disassembly

```asm
0x17690  ldnull
0x17691  stloc.0
0x17692  ldarg.1
0x17693  switch   loc_177B4, loc_177B4, loc_177B4, loc_177B4, loc_17745, loc_17792, loc_1793F, loc_17767, loc_1777D, loc_17AC4, loc_1798C, loc_1798C, loc_17A76, loc_17B01, loc_17B01, loc_17C04, loc_17752, loc_17D23, loc_17836, loc_17AF1, loc_17DD4, loc_17C85, loc_17DD4, loc_17DD4, loc_17DD4, loc_17DD4, loc_17DD4, loc_17DD4, loc_17DD4, loc_17DD4, loc_17DD4, loc_17DD4, loc_17DD4, loc_17DD4, loc_17DD4, loc_17DD4, loc_17DD4, loc_17DD4, loc_17DD4, loc_17DD4, loc_17C3B, loc_17DCC
0x17740  br       loc_17DD4
0x17745  ldarg.0
0x17746  ldarg.2
0x17747  call     instance object Microsoft.Crm.Workflow.Services.ExpressionServiceBase::SelectFirstNonNull(object[] values)
0x1774c  stloc.0
0x1774d  br       loc_17DD4
0x17752  ldarg.0
0x17753  ldarg.2
0x17754  call     instance object Microsoft.Crm.Workflow.Services.ExpressionServiceBase::SelectFirstNonNull(object[] values)
0x17759  stloc.0
0x1775a  ldarg.0
0x1775b  ldloc.0
0x1775c  call     instance object Microsoft.Crm.Workflow.Services.ExpressionServiceBase::XmlEncodeSelectedValue(object value)
0x17761  stloc.0
0x17762  br       loc_17DD4
0x17767  ldarg.2
0x17768  ldc.i4.0
0x17769  ldelem.ref
0x1776a  unbox.any [mscorlib]System.Boolean
0x1776f  stloc.1
0x17770  ldarg.0
0x17771  ldloc.1
0x17772  call     instance object Microsoft.Crm.Workflow.Services.ExpressionServiceBase::RetrieveActivityCount(bool includeActivitiesCreatedByWorkflow)
0x17777  stloc.0
0x17778  br       loc_17DD4
0x1777d  ldarg.0
0x1777e  ldarg.2
0x1777f  ldc.i4.0
0x17780  ldelem.ref
0x17781  unbox.any [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowPropertyType
0x17786  ldarg.2
0x17787  call     instance object Microsoft.Crm.Workflow.Services.ExpressionServiceBase::CreateCrmType(valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowPropertyType type, object[] values)
0x1778c  stloc.0
0x1778d  br       loc_17DD4
0x17792  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x17797  stloc.3
0x17798  ldloca.s 3
0x1779a  ldstr    aYyyyMmDdthhMmS// "yyyy/MM/ddTHH:mm:ssZ"
0x1779f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x177a4  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x177a9  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::.ctor(string)
0x177ae  stloc.0
0x177af  br       loc_17DD4
0x177b4  ldarg.3
0x177b5  ldnull
0x177b6  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x177bb  brfalse.s loc_177FE
0x177bd  ldc.i4.0
0x177be  stloc.s  4
0x177c0  br.s     loc_177D9
0x177c2  ldarg.2
0x177c3  ldloc.s  4
0x177c5  ldelem.ref
0x177c6  brfalse.s loc_177D3
0x177c8  ldarg.2
0x177c9  ldloc.s  4
0x177cb  ldelem.ref
0x177cc  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x177d1  starg.s  3
0x177d3  ldloc.s  4
0x177d5  ldc.i4.1
0x177d6  add
0x177d7  stloc.s  4
0x177d9  ldloc.s  4
0x177db  ldarg.2
0x177dc  ldlen
0x177dd  conv.i4
0x177de  bge.s    loc_177E9
0x177e0  ldarg.3
0x177e1  ldnull
0x177e2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x177e7  brtrue.s loc_177C2
0x177e9  ldarg.3
0x177ea  ldnull
0x177eb  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x177f0  brfalse.s loc_177FE
0x177f2  ldtoken  [mscorlib]System.String
0x177f7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x177fc  starg.s  3
0x177fe  ldc.i4.0
0x177ff  stloc.s  5
0x17801  br.s     loc_1781C
0x17803  ldarg.2
0x17804  ldloc.s  5
0x17806  ldarg.0
0x17807  ldarg.3
0x17808  ldarg.2
0x17809  ldloc.s  5
0x1780b  ldelem.ref
0x1780c  ldnull
0x1780d  ldnull
0x1780e  ldc.i4.1
0x1780f  ldnull
0x17810  callvirt instance object Microsoft.Crm.Workflow.Services.ExpressionServiceBase::ConvertToCrmTypeWithMetadata(class [mscorlib]System.Type targetType, object sourceValue, string entityName, string attributeName, bool automaticConvetCrmToXrm, [opt] class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.FormattedValueCollection formattedValues)
0x17815  stelem.ref
0x17816  ldloc.s  5
0x17818  ldc.i4.1
0x17819  add
0x1781a  stloc.s  5
0x1781c  ldloc.s  5
0x1781e  ldarg.2
0x1781f  ldlen
0x17820  conv.i4
0x17821  blt.s    loc_17803
0x17823  ldarg.0
0x17824  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x17829  ldarg.1
0x1782a  ldarg.2
0x1782b  callvirt instance object Microsoft.Crm.Workflow.ICommonWorkflowContext::EvaluateExpression(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Activities.ExpressionOperator op, object[] values)
0x17830  stloc.0
0x17831  br       loc_17DD4
0x17836  ldtoken  [mscorlib]System.String
0x1783b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17840  ldarg.3
0x17841  call     bool [mscorlib]System.Object::Equals(object, object)
0x17846  ldstr    aExpectTheTarge// "Expect the target type of fetch xml to "...
0x1784b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x17850  ldc.i4.0
0x17851  stloc.s  6
0x17853  br       loc_17922
0x17858  ldarg.2
0x17859  ldloc.s  6
0x1785b  ldelem.ref
0x1785c  brfalse  loc_1791C
0x17861  ldarg.2
0x17862  ldloc.s  6
0x17864  ldelem.ref
0x17865  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1786a  callvirt instance string [mscorlib]System.Type::get_FullName()
0x1786f  stloc.s  7
0x17871  ldloc.s  7
0x17873  ldstr    aSystemString// "System.String"
0x17878  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1787d  brtrue   loc_1791C
0x17882  ldloc.s  7
0x17884  ldstr    aSystemInt32// "System.Int32"
0x17889  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1788e  brtrue.s loc_178AE
0x17890  ldloc.s  7
0x17892  ldstr    aSystemDouble// "System.Double"
0x17897  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1789c  brtrue.s loc_178CB
0x1789e  ldloc.s  7
0x178a0  ldstr    aSystemDatetime// "System.DateTime"
0x178a5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x178aa  brtrue.s loc_178E8
0x178ac  br.s     loc_17909
0x178ae  ldarg.2
0x178af  ldloc.s  6
0x178b1  ldarg.2
0x178b2  ldloc.s  6
0x178b4  ldelem.ref
0x178b5  unbox.any [mscorlib]System.Int32
0x178ba  stloc.s  8
0x178bc  ldloca.s 8
0x178be  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x178c3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x178c8  stelem.ref
0x178c9  br.s     loc_1791C
0x178cb  ldarg.2
0x178cc  ldloc.s  6
0x178ce  ldarg.2
0x178cf  ldloc.s  6
0x178d1  ldelem.ref
0x178d2  unbox.any [mscorlib]System.Double
0x178d7  stloc.s  9
0x178d9  ldloca.s 9
0x178db  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x178e0  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0x178e5  stelem.ref
0x178e6  br.s     loc_1791C
0x178e8  ldarg.2
0x178e9  ldloc.s  6
0x178eb  ldarg.2
0x178ec  ldloc.s  6
0x178ee  ldelem.ref
0x178ef  unbox.any [mscorlib]System.DateTime
0x178f4  stloc.3
0x178f5  ldloca.s 3
0x178f7  ldstr    aU// "u"
0x178fc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17901  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x17906  stelem.ref
0x17907  br.s     loc_1791C
0x17909  ldarg.2
0x1790a  ldloc.s  6
0x1790c  ldarg.0
0x1790d  ldarg.3
0x1790e  ldarg.2
0x1790f  ldloc.s  6
0x17911  ldelem.ref
0x17912  ldnull
0x17913  ldnull
0x17914  ldc.i4.1
0x17915  ldnull
0x17916  callvirt instance object Microsoft.Crm.Workflow.Services.ExpressionServiceBase::ConvertToCrmTypeWithMetadata(class [mscorlib]System.Type targetType, object sourceValue, string entityName, string attributeName, bool automaticConvetCrmToXrm, [opt] class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.FormattedValueCollection formattedValues)
0x1791b  stelem.ref
0x1791c  ldloc.s  6
0x1791e  ldc.i4.1
0x1791f  add
0x17920  stloc.s  6
0x17922  ldloc.s  6
0x17924  ldarg.2
0x17925  ldlen
0x17926  conv.i4
0x17927  blt      loc_17858
0x1792c  ldarg.0
0x1792d  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x17932  ldc.i4.0
0x17933  ldarg.2
0x17934  callvirt instance object Microsoft.Crm.Workflow.ICommonWorkflowContext::EvaluateExpression(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Activities.ExpressionOperator op, object[] values)
0x17939  stloc.0
0x1793a  br       loc_17DD4
0x1793f  ldarg.0
0x17940  ldarg.2
0x17941  ldc.i4.1
0x17942  call     instance void Microsoft.Crm.Workflow.Services.ExpressionServiceBase::EnsureParametersPresent(object[] parameters, int32 minNumber)
0x17947  ldarg.0
0x17948  ldarg.2
0x17949  ldc.i4.0
0x1794a  ldelem.ref
0x1794b  ldtoken  [mscorlib]System.DateTime
0x17950  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17955  call     instance void Microsoft.Crm.Workflow.Services.ExpressionServiceBase::EnsureParameterType(object parameter, class [mscorlib]System.Type type)
0x1795a  ldarg.2
0x1795b  ldc.i4.0
0x1795c  ldelem.ref
0x1795d  unbox.any [mscorlib]System.DateTime
0x17962  stloc.2
0x17963  ldloc.2
0x17964  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x17969  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1796e  brfalse.s loc_17980
0x17970  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x17975  box      [mscorlib]System.DateTime
0x1797a  stloc.0
0x1797b  br       loc_17DD4
0x17980  ldloc.2
0x17981  box      [mscorlib]System.DateTime
0x17986  stloc.0
0x17987  br       loc_17DD4
0x1798c  ldarg.2
0x1798d  ldlen
0x1798e  brfalse  loc_17DD4
0x17993  ldarg.0
0x17994  ldarg.2
0x17995  ldc.i4.0
0x17996  ldelem.ref
0x17997  ldtoken  Microsoft.Crm.Workflow.InteractionActivityResult
0x1799c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x179a1  call     instance void Microsoft.Crm.Workflow.Services.ExpressionServiceBase::EnsureParameterType(object parameter, class [mscorlib]System.Type type)
0x179a6  ldarg.2
0x179a7  ldc.i4.0
0x179a8  ldelem.ref
0x179a9  castclass Microsoft.Crm.Workflow.InteractionActivityResult
0x179ae  stloc.s  0xA
0x179b0  ldloc.s  0xA
0x179b2  callvirt instance object Microsoft.Crm.Workflow.InteractionActivityResult::get_ResponseValue()
0x179b7  stloc.0
0x179b8  ldnull
0x179b9  ldarg.3
0x179ba  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x179bf  brfalse  loc_17DD4
0x179c4  ldarg.3
0x179c5  ldtoken  [mscorlib]System.String
0x179ca  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x179cf  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x179d4  brfalse  loc_17DD4
0x179d9  ldloc.0
0x179da  brfalse  loc_17DD4
0x179df  ldloc.s  0xA
0x179e1  callvirt instance string Microsoft.Crm.Workflow.InteractionActivityResult::get_ResponseContainerType()
0x179e6  ldc.i4.6
0x179e7  call     string Microsoft.Crm.Workflow.PageTypeConvertors::GetResponseContainer(int32 responseContainerType)
0x179ec  call     bool [mscorlib]System.String::op_Equality(string, string)
0x179f1  brfalse.s loc_17A29
0x179f3  ldloc.0
0x179f4  unbox.any [mscorlib]System.DateTime
0x179f9  stloc.s  0xB
0x179fb  ldarg.0
0x179fc  ldloc.s  0xB
0x179fe  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.Services.ExpressionServiceBase::ConvertToLocalTime(valuetype [mscorlib]System.DateTime dateTime)
0x17a03  ldarg.0
0x17a04  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x17a09  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_UserId()
0x17a0e  ldarg.0
0x17a0f  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x17a14  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x17a19  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x17a1e  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Formatting.CrmFormatter::FormatDate(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17a23  stloc.0
0x17a24  br       loc_17DD4
0x17a29  ldloc.s  0xA
0x17a2b  callvirt instance string Microsoft.Crm.Workflow.InteractionActivityResult::get_ResponseContainerType()
0x17a30  ldc.i4.5
0x17a31  call     string Microsoft.Crm.Workflow.PageTypeConvertors::GetResponseContainer(int32 responseContainerType)
  ... truncated ...
```
