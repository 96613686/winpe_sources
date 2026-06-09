# Microsoft.Crm.Workflow.WorkflowContextBase::RetrieveActivityCount

- ea: `0x7c70`
- end: `0x7cd4`
- name: `Microsoft.Crm.Workflow.WorkflowContextBase::RetrieveActivityCount`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x7350`
- `0x7a00`
- `0x7c70`
- `0x8ad0`

## string_xrefs

- `0x7c76`: `<condition attribute='isworkflowcreated' operator='ne' value='1' />`

## pseudocode

```c

```

## disassembly

```asm
0x7c70  ldstr    aFetchDistinctT// "\r\n<fetch distinct='true' mapping='log"...
0x7c75  stloc.0
0x7c76  ldstr    aConditionAttri// "<condition attribute='isworkflowcreated"...
0x7c7b  stloc.1
0x7c7c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7c81  ldloc.0
0x7c82  ldc.i4.2
0x7c83  newarr   [mscorlib]System.Object
0x7c88  dup
0x7c89  ldc.i4.0
0x7c8a  ldarg.0
0x7c8b  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowContextBase::get_PrimaryEntityId()
0x7c90  stloc.3
0x7c91  ldloca.s 3
0x7c93  ldstr    aB// "B"
0x7c98  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7c9d  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x7ca2  stelem.ref
0x7ca3  dup
0x7ca4  ldc.i4.1
0x7ca5  ldarg.1
0x7ca6  brtrue.s loc_7CAB
0x7ca8  ldloc.1
0x7ca9  br.s     loc_7CB0
0x7cab  ldstr    asc_30690// ""
0x7cb0  stelem.ref
0x7cb1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7cb6  ldarg.0
0x7cb7  ldc.i4.0
0x7cb8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Workflow.WorkflowContextBase::CreateSdkService(bool asAdminUser)
0x7cbd  stloc.2
0x7cbe  ldstr    aResultsetResul// "/resultset/result/activitycount"
0x7cc3  ldloc.2
0x7cc4  call     string Microsoft.Crm.Workflow.WorkflowContextHelper::ExecuteFetchGetScalar(string fetchXml, string resultNode, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdkService)
0x7cc9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7cce  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x7cd3  ret
```
