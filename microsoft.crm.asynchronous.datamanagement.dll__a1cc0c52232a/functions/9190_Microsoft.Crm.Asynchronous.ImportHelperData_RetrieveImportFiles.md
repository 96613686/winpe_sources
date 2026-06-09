# Microsoft.Crm.Asynchronous.ImportHelperData::RetrieveImportFiles

- ea: `0x9190`
- end: `0x9378`
- name: `Microsoft.Crm.Asynchronous.ImportHelperData::RetrieveImportFiles`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x8fd0`

## string_xrefs

- `0x9338`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x9190  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x9195  stloc.0
0x9196  ldloc.0
0x9197  ldstr    aImportid_1// "importid"
0x919c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x91a1  ldloc.0
0x91a2  ldc.i4.0
0x91a3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x91a8  ldloc.0
0x91a9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x91ae  ldarg.1
0x91af  box      [mscorlib]System.Guid
0x91b4  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x91b9  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x91be  stloc.1
0x91bf  ldloc.1
0x91c0  ldstr    aStatuscode// "statuscode"
0x91c5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x91ca  ldloc.1
0x91cb  ldc.i4.1
0x91cc  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x91d1  ldloc.1
0x91d2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x91d7  ldc.i4.5
0x91d8  box      [mscorlib]System.Int32
0x91dd  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x91e2  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x91e7  stloc.2
0x91e8  ldloc.2
0x91e9  ldstr    aProcesscode// "processcode"
0x91ee  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x91f3  ldloc.2
0x91f4  ldc.i4.0
0x91f5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x91fa  ldloc.2
0x91fb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x9200  ldc.i4.1
0x9201  box      [mscorlib]System.Int32
0x9206  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x920b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x9210  stloc.3
0x9211  ldloc.3
0x9212  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x9217  ldc.i4.3
0x9218  newarr   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression
0x921d  dup
0x921e  ldc.i4.0
0x921f  ldloc.0
0x9220  stelem.ref
0x9221  dup
0x9222  ldc.i4.1
0x9223  ldloc.1
0x9224  stelem.ref
0x9225  dup
0x9226  ldc.i4.2
0x9227  ldloc.2
0x9228  stelem.ref
0x9229  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::AddRange(var<u1>[])
0x922e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0x9233  stloc.s  4
0x9235  ldloc.s  4
0x9237  ldstr    aImportfile// "importfile"
0x923c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0x9241  ldloc.s  4
0x9243  ldc.i4.s 0x16
0x9245  newarr   [mscorlib]System.String
0x924a  dup
0x924b  ldc.i4.0
0x924c  ldstr    aImportfileid_2// "importfileid"
0x9251  stelem.ref
0x9252  dup
0x9253  ldc.i4.1
0x9254  ldstr    aSourceentityna// "sourceentityname"
0x9259  stelem.ref
0x925a  dup
0x925b  ldc.i4.2
0x925c  ldstr    aTargetentityna// "targetentityname"
0x9261  stelem.ref
0x9262  dup
0x9263  ldc.i4.3
0x9264  ldstr    aDatadelimiterc// "datadelimitercode"
0x9269  stelem.ref
0x926a  dup
0x926b  ldc.i4.4
0x926c  ldstr    aImportmapid// "importmapid"
0x9271  stelem.ref
0x9272  dup
0x9273  ldc.i4.5
0x9274  ldstr    aFielddelimiter// "fielddelimitercode"
0x9279  stelem.ref
0x927a  dup
0x927b  ldc.i4.6
0x927c  ldstr    aIsfirstrowhead// "isfirstrowheader"
0x9281  stelem.ref
0x9282  dup
0x9283  ldc.i4.7
0x9284  ldstr    aParsedtablenam_0// "parsedtablename"
0x9289  stelem.ref
0x928a  dup
0x928b  ldc.i4.8
0x928c  ldstr    aParsedtablecol_0// "parsedtablecolumnsnumber"
0x9291  stelem.ref
0x9292  dup
0x9293  ldc.i4.s 9
0x9295  ldstr    aParsedtablecol// "parsedtablecolumnprefix"
0x929a  stelem.ref
0x929b  dup
0x929c  ldc.i4.s 0xA
0x929e  ldstr    aRecordsownerid// "recordsownerid"
0x92a3  stelem.ref
0x92a4  dup
0x92a5  ldc.i4.s 0xB
0x92a7  ldstr    aUsesystemmap// "usesystemmap"
0x92ac  stelem.ref
0x92ad  dup
0x92ae  ldc.i4.s 0xC
0x92b0  ldstr    aEnableduplicat// "enableduplicatedetection"
0x92b5  stelem.ref
0x92b6  dup
0x92b7  ldc.i4.s 0xD
0x92b9  ldstr    aSource// "source"
0x92be  stelem.ref
0x92bf  dup
0x92c0  ldc.i4.s 0xE
0x92c2  ldstr    aProgresscounte_0// "progresscounter"
0x92c7  stelem.ref
0x92c8  dup
0x92c9  ldc.i4.s 0xF
0x92cb  ldstr    aProcessingstat_0// "processingstatus"
0x92d0  stelem.ref
0x92d1  dup
0x92d2  ldc.i4.s 0x10
0x92d4  ldstr    aName_0// "name"
0x92d9  stelem.ref
0x92da  dup
0x92db  ldc.i4.s 0x11
0x92dd  ldstr    aFiletypecode// "filetypecode"
0x92e2  stelem.ref
0x92e3  dup
0x92e4  ldc.i4.s 0x12
0x92e6  ldstr    aAdditionalhead// "additionalheaderrow"
0x92eb  stelem.ref
0x92ec  dup
0x92ed  ldc.i4.s 0x13
0x92ef  ldstr    aRelatedentityc// "relatedentitycolumns"
0x92f4  stelem.ref
0x92f5  dup
0x92f6  ldc.i4.s 0x14
0x92f8  ldstr    aUpsertmodecode// "upsertmodecode"
0x92fd  stelem.ref
0x92fe  dup
0x92ff  ldc.i4.s 0x15
0x9301  ldstr    aEntitykeyid// "entitykeyid"
0x9306  stelem.ref
0x9307  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x930c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x9311  ldloc.s  4
0x9313  ldloc.3
0x9314  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0x9319  ldc.i4.1
0x931a  newarr   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression
0x931f  stloc.s  5
0x9321  ldloc.s  5
0x9323  ldc.i4.0
0x9324  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression::.ctor()
0x9329  stelem.ref
0x932a  ldloc.s  5
0x932c  ldc.i4.0
0x932d  ldelem.ref
0x932e  ldc.i4.0
0x932f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression::set_OrderType(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x9334  ldloc.s  5
0x9336  ldc.i4.0
0x9337  ldelem.ref
0x9338  ldstr    aCreatedon// "createdon"
0x933d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression::set_AttributeName(string)
0x9342  ldloc.s  4
0x9344  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Orders()
0x9349  ldloc.s  5
0x934b  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression>::AddRange(var<u1>[])
0x9350  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::.ctor()
0x9355  stloc.s  6
0x9357  ldloc.s  6
0x9359  ldloc.s  4
0x935b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x9360  ldarg.0
0x9361  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportHelperData::_crmService
0x9366  ldloc.s  6
0x9368  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x936d  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse
0x9372  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse::get_EntityCollection()
0x9377  ret
```
