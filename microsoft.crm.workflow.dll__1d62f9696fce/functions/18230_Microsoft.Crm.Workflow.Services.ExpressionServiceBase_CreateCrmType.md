# Microsoft.Crm.Workflow.Services.ExpressionServiceBase::CreateCrmType

- ea: `0x18230`
- end: `0x18517`
- name: `Microsoft.Crm.Workflow.Services.ExpressionServiceBase::CreateCrmType`
- size: `743`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x17690`

## callees

- `0x8e70`
- `0x8ef0`
- `0x14770`
- `0x18230`
- `0x18520`
- `0x2cd50`

## string_xrefs

- `0x18239`: `Cannot create the given type({0}) without the required parameters.`

## pseudocode

```c

```

## disassembly

```asm
0x18230  ldarg.2
0x18231  brfalse.s loc_18239
0x18233  ldarg.2
0x18234  ldlen
0x18235  conv.i4
0x18236  ldc.i4.2
0x18237  bge.s    loc_18254
0x18239  ldstr    aCannotCreateTh// "Cannot create the given type({0}) witho"...
0x1823e  ldarg.1
0x1823f  box      [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowPropertyType
0x18244  call     string [mscorlib]System.String::Format(string, object)
0x18249  ldc.i4   0x80040216
0x1824e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x18253  throw
0x18254  ldc.i4.1
0x18255  stloc.1
0x18256  br.s     loc_1827D
0x18258  ldarg.2
0x18259  ldloc.1
0x1825a  ldelem.ref
0x1825b  isinst   [mscorlib]System.String
0x18260  stloc.2
0x18261  ldloc.2
0x18262  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x18267  brtrue.s loc_18279
0x18269  ldloc.2
0x1826a  call     string Microsoft.Crm.Workflow.ObjectModel.XamlVBEncodeDecode::Decode(string encoded)
0x1826f  stloc.2
0x18270  ldarg.2
0x18271  ldloc.1
0x18272  ldloc.2
0x18273  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlDecode(string)
0x18278  stelem.ref
0x18279  ldloc.1
0x1827a  ldc.i4.1
0x1827b  add
0x1827c  stloc.1
0x1827d  ldloc.1
0x1827e  ldarg.2
0x1827f  ldlen
0x18280  conv.i4
0x18281  blt.s    loc_18258
0x18283  ldnull
0x18284  stloc.0
0x18285  ldarg.1
0x18286  switch   loc_182BC, loc_18303, loc_1836C, loc_18389, loc_183A6, loc_183C3, loc_183D0, loc_183ED, loc_1845D, loc_1847A, loc_18492
0x182b7  br       loc_184FF
0x182bc  ldarg.2
0x182bd  ldc.i4.1
0x182be  ldelem.ref
0x182bf  callvirt instance string [mscorlib]System.Object::ToString()
0x182c4  stloc.3
0x182c5  ldloc.3
0x182c6  ldstr    a1// "1"
0x182cb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x182d0  brfalse.s loc_182D9
0x182d2  ldc.i4.1
0x182d3  box      [mscorlib]System.Boolean
0x182d8  ret
0x182d9  ldloc.3
0x182da  ldstr    a0_1// "0"
0x182df  call     bool [mscorlib]System.String::op_Equality(string, string)
0x182e4  brfalse.s loc_182ED
0x182e6  ldc.i4.0
0x182e7  box      [mscorlib]System.Boolean
0x182ec  ret
0x182ed  ldloc.3
0x182ee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x182f3  call     bool [mscorlib]System.Convert::ToBoolean(string, class [mscorlib]System.IFormatProvider)
0x182f8  box      [mscorlib]System.Boolean
0x182fd  stloc.0
0x182fe  br       loc_18515
0x18303  ldarg.2
0x18304  ldc.i4.1
0x18305  ldelem.ref
0x18306  callvirt instance string [mscorlib]System.Object::ToString()
0x1830b  stloc.s  4
0x1830d  ldloc.s  4
0x1830f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18314  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0x18319  stloc.s  5
0x1831b  ldloca.s 5
0x1831d  call     instance valuetype [mscorlib]System.DateTimeKind [mscorlib]System.DateTime::get_Kind()
0x18322  ldc.i4.2
0x18323  bne.un.s loc_18332
0x18325  ldloca.s 5
0x18327  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x1832c  box      [mscorlib]System.DateTime
0x18331  stloc.0
0x18332  ldloca.s 5
0x18334  call     instance valuetype [mscorlib]System.DateTimeKind [mscorlib]System.DateTime::get_Kind()
0x18339  brtrue   loc_18515
0x1833e  ldloc.s  4
0x18340  ldstr    aT// "T"
0x18345  callvirt instance bool [mscorlib]System.String::Contains(string)
0x1834a  brtrue.s loc_1835F
0x1834c  ldloc.s  5
0x1834e  ldc.i4.1
0x1834f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x18354  box      [mscorlib]System.DateTime
0x18359  stloc.0
0x1835a  br       loc_18515
0x1835f  ldloc.s  5
0x18361  box      [mscorlib]System.DateTime
0x18366  stloc.0
0x18367  br       loc_18515
0x1836c  ldarg.2
0x1836d  ldc.i4.1
0x1836e  ldelem.ref
0x1836f  callvirt instance string [mscorlib]System.Object::ToString()
0x18374  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18379  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Convert::ToDecimal(string, class [mscorlib]System.IFormatProvider)
0x1837e  box      [mscorlib]System.Decimal
0x18383  stloc.0
0x18384  br       loc_18515
0x18389  ldarg.2
0x1838a  ldc.i4.1
0x1838b  ldelem.ref
0x1838c  callvirt instance string [mscorlib]System.Object::ToString()
0x18391  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18396  call     float64 [mscorlib]System.Convert::ToDouble(string, class [mscorlib]System.IFormatProvider)
0x1839b  box      [mscorlib]System.Double
0x183a0  stloc.0
0x183a1  br       loc_18515
0x183a6  ldarg.2
0x183a7  ldc.i4.1
0x183a8  ldelem.ref
0x183a9  callvirt instance string [mscorlib]System.Object::ToString()
0x183ae  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x183b3  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x183b8  box      [mscorlib]System.Int32
0x183bd  stloc.0
0x183be  br       loc_18515
0x183c3  ldarg.0
0x183c4  ldarg.2
0x183c5  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Workflow.Services.ExpressionServiceBase::CreateEntityReference(object[] values)
0x183ca  stloc.0
0x183cb  br       loc_18515
0x183d0  ldarg.2
0x183d1  ldc.i4.1
0x183d2  ldelem.ref
0x183d3  callvirt instance string [mscorlib]System.Object::ToString()
0x183d8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x183dd  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Convert::ToDecimal(string, class [mscorlib]System.IFormatProvider)
0x183e2  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Money::.ctor(valuetype [mscorlib]System.Decimal)
0x183e7  stloc.0
0x183e8  br       loc_18515
0x183ed  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::.ctor()
0x183f2  stloc.s  6
0x183f4  ldc.i4.1
0x183f5  stloc.s  7
0x183f7  br.s     loc_1844E
0x183f9  ldarg.2
0x183fa  ldloc.s  7
0x183fc  ldelem.ref
0x183fd  brfalse.s loc_18448
0x183ff  ldstr    aActivityparty// "activityparty"
0x18404  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x18409  stloc.s  8
0x1840b  ldarg.2
0x1840c  ldloc.s  7
0x1840e  ldelem.ref
0x1840f  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x18414  stloc.s  9
0x18416  ldloc.s  9
0x18418  brfalse.s loc_1842A
0x1841a  ldloc.s  8
0x1841c  ldstr    aPartyid// "partyid"
0x18421  ldloc.s  9
0x18423  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x18428  br.s     loc_1843A
0x1842a  ldloc.s  8
0x1842c  ldstr    aAddressused// "addressused"
0x18431  ldarg.2
0x18432  ldloc.s  7
0x18434  ldelem.ref
0x18435  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1843a  ldloc.s  6
0x1843c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x18441  ldloc.s  8
0x18443  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x18448  ldloc.s  7
0x1844a  ldc.i4.1
0x1844b  add
0x1844c  stloc.s  7
0x1844e  ldloc.s  7
0x18450  ldarg.2
0x18451  ldlen
0x18452  conv.i4
0x18453  blt.s    loc_183F9
0x18455  ldloc.s  6
0x18457  stloc.0
0x18458  br       loc_18515
0x1845d  ldarg.2
0x1845e  ldc.i4.1
0x1845f  ldelem.ref
0x18460  callvirt instance string [mscorlib]System.Object::ToString()
0x18465  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1846a  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x1846f  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x18474  stloc.0
0x18475  br       loc_18515
0x1847a  ldarg.2
0x1847b  ldc.i4.1
0x1847c  ldelem.ref
0x1847d  callvirt instance string [mscorlib]System.Object::ToString()
0x18482  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x18487  box      [mscorlib]System.Guid
0x1848c  stloc.0
0x1848d  br       loc_18515
0x18492  ldarg.2
0x18493  ldc.i4.1
0x18494  ldelem.ref
0x18495  callvirt instance string [mscorlib]System.Object::ToString()
0x1849a  stloc.0
0x1849b  ldarg.2
0x1849c  ldlen
0x1849d  conv.i4
0x1849e  ldc.i4.3
0x1849f  ble.s    loc_18515
0x184a1  ldarg.2
0x184a2  ldc.i4.3
0x184a3  ldelem.ref
0x184a4  isinst   [mscorlib]System.Guid
0x184a9  brfalse.s loc_18515
0x184ab  ldarg.0
0x184ac  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x184b1  newobj   instance void Microsoft.Crm.Workflow.WorkflowUserContext::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext workflowContext)
0x184b6  stloc.s  0xA
0x184b8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCache::Instance()
0x184bd  ldloc.s  0xA
0x184bf  callvirt instance int32 Microsoft.Crm.Workflow.WorkflowUserContext::get_LanguageId()
0x184c4  ldarg.2
0x184c5  ldc.i4.3
0x184c6  ldelem.ref
0x184c7  unbox.any [mscorlib]System.Guid
0x184cc  ldstr    aDescription// "description"
0x184d1  ldarg.0
0x184d2  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x184d7  castclass [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext
0x184dc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCache::TryLookupEntry(int32, valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x184e1  stloc.s  0xB
0x184e3  ldloc.s  0xB
0x184e5  brfalse.s loc_18515
0x184e7  ldloc.s  0xB
0x184e9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x184ee  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x184f3  brtrue.s loc_18515
0x184f5  ldloc.s  0xB
0x184f7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x184fc  stloc.0
0x184fd  br.s     loc_18515
0x184ff  ldstr    aUnexpectedWork// "Unexpected WorkflowPropertyType: "
0x18504  ldarg.1
0x18505  box      [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowPropertyType
0x1850a  call     string [mscorlib]System.String::Concat(object, object)
0x1850f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x18514  throw
0x18515  ldloc.0
0x18516  ret
```
