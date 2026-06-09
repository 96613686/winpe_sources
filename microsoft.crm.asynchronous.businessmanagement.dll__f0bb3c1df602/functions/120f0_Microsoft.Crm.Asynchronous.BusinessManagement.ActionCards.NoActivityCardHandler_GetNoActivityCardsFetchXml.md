# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::GetNoActivityCardsFetchXml

- ea: `0x120f0`
- end: `0x1219a`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::GetNoActivityCardsFetchXml`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x11c70`

## callees

- `0x133e0`
- `0x13420`
- `0x13460`
- `0x134a0`

## string_xrefs

- `0x120f0`: `\n							<fetch distinct='true' mapping='logical' output-format='xml-platform' version='1.0' >\n								<entity name='{0}' >\n									<attribute name='{1}' />\n									<attribute name='{2}' />\n									<attribute name='{3}' />\n									<attribute name='ownerid' />\n									<filter type='and' >\n										<condition attribute='statecode' operator='eq' value='0' />\n										<condition attribute='modifiedon' operator='between' entityname='{4}' >\n											<value>\n												{5`

## pseudocode

```c

```

## disassembly

```asm
0x120f0  ldstr    aFetchDistinctT// "\r\n\t\t\t\t\t\t\t<fetch distinct='true"...
0x120f5  ldc.i4.s 0xD
0x120f7  newarr   [mscorlib]System.Object
0x120fc  dup
0x120fd  ldc.i4.0
0x120fe  ldarg.1
0x120ff  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_EntityLogicalName()
0x12104  stelem.ref
0x12105  dup
0x12106  ldc.i4.1
0x12107  ldarg.1
0x12108  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_Subject()
0x1210d  stelem.ref
0x1210e  dup
0x1210f  ldc.i4.2
0x12110  ldarg.1
0x12111  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_EntityId()
0x12116  stelem.ref
0x12117  dup
0x12118  ldc.i4.3
0x12119  ldstr    aModifiedon// "modifiedon"
0x1211e  stelem.ref
0x1211f  dup
0x12120  ldc.i4.4
0x12121  ldarg.1
0x12122  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_EntityLogicalName()
0x12127  stelem.ref
0x12128  dup
0x12129  ldc.i4.5
0x1212a  ldarga.s 3
0x1212c  ldc.r8   -180.0
0x12135  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x1213a  stloc.0
0x1213b  ldloca.s 0
0x1213d  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x12142  box      [mscorlib]System.DateTime
0x12147  stelem.ref
0x12148  dup
0x12149  ldc.i4.6
0x1214a  ldarg.2
0x1214b  box      [mscorlib]System.DateTime
0x12150  stelem.ref
0x12151  dup
0x12152  ldc.i4.7
0x12153  ldstr    aActioncard// "actioncard"
0x12158  stelem.ref
0x12159  dup
0x1215a  ldc.i4.8
0x1215b  ldarg.1
0x1215c  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_EntityId()
0x12161  stelem.ref
0x12162  dup
0x12163  ldc.i4.s 9
0x12165  ldarg.1
0x12166  callvirt instance valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_CardType()
0x1216b  box      [mscorlib]System.Int32
0x12170  stelem.ref
0x12171  dup
0x12172  ldc.i4.s 0xA
0x12174  ldc.i4.2
0x12175  box      [mscorlib]System.Int32
0x1217a  stelem.ref
0x1217b  dup
0x1217c  ldc.i4.s 0xB
0x1217e  ldarg.1
0x1217f  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_EntityId()
0x12184  stelem.ref
0x12185  dup
0x12186  ldc.i4.s 0xC
0x12188  ldarg.2
0x12189  box      [mscorlib]System.DateTime
0x1218e  stelem.ref
0x1218f  call     string [mscorlib]System.String::Format(string, object[])
0x12194  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FetchExpression::.ctor(string)
0x12199  ret
```
