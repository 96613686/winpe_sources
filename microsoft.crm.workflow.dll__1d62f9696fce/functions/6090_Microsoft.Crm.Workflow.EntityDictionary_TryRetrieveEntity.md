# Microsoft.Crm.Workflow.EntityDictionary::TryRetrieveEntity

- ea: `0x6090`
- end: `0x6186`
- name: `Microsoft.Crm.Workflow.EntityDictionary::TryRetrieveEntity`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x6040`

## callees

- `0x6090`
- `0x6190`
- `0x6900`

## string_xrefs

- `0x611e`: `relatedlinked_`

## pseudocode

```c

```

## disassembly

```asm
0x6090  ldarg.0
0x6091  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.EntityDictionary::_context
0x6096  ldc.i4.0
0x6097  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Workflow.ICommonWorkflowContext::CreateSdkService(bool asAdminUser)
0x609c  stloc.0
0x609d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor()
0x60a2  stloc.1
0x60a3  ldarg.1
0x60a4  ldstr    aPrimaryentity// "primaryEntity"
0x60a9  ldc.i4.4
0x60aa  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x60af  brfalse.s loc_60CE
0x60b1  ldarg.0
0x60b2  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.EntityDictionary::_context
0x60b7  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PrimaryEntityName()
0x60bc  stloc.2
0x60bd  ldarg.0
0x60be  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.EntityDictionary::_context
0x60c3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PrimaryEntityId()
0x60c8  stloc.3
0x60c9  br       loc_6162
0x60ce  ldarg.1
0x60cf  ldstr    aRelated// "related_"
0x60d4  ldc.i4.4
0x60d5  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x60da  brfalse.s loc_611D
0x60dc  ldarg.1
0x60dd  ldc.i4.s 0x23
0x60df  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x60e4  stloc.s  4
0x60e6  ldloc.s  4
0x60e8  ldc.i4.0
0x60e9  blt.s    loc_60F5
0x60eb  ldloc.s  4
0x60ed  ldarg.1
0x60ee  callvirt instance int32 [mscorlib]System.String::get_Length()
0x60f3  bne.un.s loc_60F7
0x60f5  ldloc.1
0x60f6  ret
0x60f7  ldarg.1
0x60f8  ldc.i4.8
0x60f9  ldloc.s  4
0x60fb  ldc.i4.8
0x60fc  sub
0x60fd  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x6102  stloc.s  5
0x6104  ldarg.1
0x6105  ldloc.s  4
0x6107  ldc.i4.1
0x6108  add
0x6109  callvirt instance string [mscorlib]System.String::Substring(int32)
0x610e  stloc.2
0x610f  ldarg.0
0x6110  ldarg.1
0x6111  ldloc.s  5
0x6113  ldloc.2
0x6114  ldc.i4.0
0x6115  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.EntityDictionary::GetRelatedEntityId(string key, string attributeName, string entityName, bool isRelatedLinked)
0x611a  stloc.3
0x611b  br.s     loc_6162
0x611d  ldarg.1
0x611e  ldstr    aRelatedlinked// "relatedlinked_"
0x6123  ldc.i4.4
0x6124  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x6129  brfalse.s loc_6160
0x612b  ldarg.1
0x612c  ldc.i4.1
0x612d  newarr   [mscorlib]System.Char
0x6132  dup
0x6133  ldc.i4.0
0x6134  ldc.i4.s 0x23
0x6136  stelem.i2
0x6137  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x613c  stloc.s  6
0x613e  ldloc.s  6
0x6140  ldlen
0x6141  conv.i4
0x6142  ldc.i4.2
0x6143  bgt.s    loc_6147
0x6145  ldloc.1
0x6146  ret
0x6147  ldloc.s  6
0x6149  ldc.i4.1
0x614a  ldelem.ref
0x614b  stloc.s  7
0x614d  ldloc.s  6
0x614f  ldc.i4.2
0x6150  ldelem.ref
0x6151  stloc.2
0x6152  ldarg.0
0x6153  ldarg.1
0x6154  ldloc.s  7
0x6156  ldloc.2
0x6157  ldc.i4.1
0x6158  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.EntityDictionary::GetRelatedEntityId(string key, string attributeName, string entityName, bool isRelatedLinked)
0x615d  stloc.3
0x615e  br.s     loc_6162
0x6160  ldloc.1
0x6161  ret
0x6162  nop
0x6163  ldloc.3
0x6164  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6169  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x616e  brfalse.s loc_617F
0x6170  ldloc.0
0x6171  ldloc.2
0x6172  ldloc.3
0x6173  ldc.i4.1
0x6174  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(bool)
0x6179  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x617e  stloc.1
0x617f  leave.s  loc_6184
0x6181  pop
0x6182  leave.s  loc_6184
0x6184  ldloc.1
0x6185  ret
```
